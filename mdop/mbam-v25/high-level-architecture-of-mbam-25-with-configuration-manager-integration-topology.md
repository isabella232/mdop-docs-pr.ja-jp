---
title: Configuration Manager 統合トポロジを使用した MBAM 2.5 のアーキテクチャ概要
description: Configuration Manager 統合トポロジを使用した MBAM 2.5 のアーキテクチャ概要
author: dansimp
ms.assetid: 075bafa1-792b-4c24-9d8e-5d3153e2112c
ms.reviewer: ''
manager: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/23/2018
ms.author: dansimp
ms.openlocfilehash: 75af2e22981d76568916c36acadbbb25648b1f1d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825764"
---
# MBAM 2.5 の高レベルアーキテクチャと構成マネージャーの統合トポロジ

このトピックでは、Configuration Manager 統合トポロジを使用して、Microsoft BitLocker 管理と監視 (MBAM) を展開するための推奨アーキテクチャについて説明します。 このトポロジは、MBAM を System Center Configuration Manager と統合したものです。 スタンドアロントポロジで MBAM を導入する場合は、「 [mbam 2.5 の高レベルアーキテクチャとスタンドアロントポロジ](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)」を参照してください。

このトピックで説明しているソフトウェアのサポートされているバージョンの一覧については、「 [Mbam 2.5 でサポートされている構成](mbam-25-supported-configurations.md)」を参照してください。

**重要** Configuration Manager 2007 を使用している場合、Configuration Manager 統合トポロジのインストールでは、Windows To Go はサポートされません。

 

## 推奨されるサーバー数とクライアント数


運用環境での推奨されるサーバー数とサポートされているクライアント数は、次のとおりです。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">推奨されるアーキテクチャ</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>サーバーとその他のコンピューターの数</p></td>
<td align="left"><p>3台のサーバー</p>
<p>1つのワークステーション</p></td>
</tr>
<tr class="even">
<td align="left"><p>サポートされているクライアントコンピューターの数</p></td>
<td align="left"><p>50万</p></td>
</tr>
</tbody>
</table>

 

## Configuration Manager の統合とスタンドアロントポロジの違い


トポロジ間の主な違いは次のとおりです。

-   コンプライアンス機能とレポート機能は、MBAM から削除され、構成マネージャーからアクセスされます。

-   レポートは、Configuration Manager 管理コンソールから表示されます。回復監査レポートは除き、MBAM 管理と監視 Web サイトから引き続き表示できます。

## Configuration Manager の統合トポロジを使用した、推奨される MBAM 高レベルアーキテクチャ


次の図と表は、Configuration Manager 統合トポロジでの MBAM の推奨される高レベルアーキテクチャを示しています。 MBAM 複数フォレスト展開には、一方向または双方向の信頼が必要です。 一方向の信頼には、サーバーのドメインがクライアントドメインを信頼する必要があります。

![mbam2\-5](images/mbam2-5-cmserver.png)

### データベースサーバー

#### 回復用データベース

この機能は、Windows Server とサポートされている SQL Server インスタンスを実行しているコンピューターで構成されます。

**回復データベース**には、Mbam クライアントコンピューターから収集された回復データが格納されます。

#### 監査データベース

この機能は、Windows Server とサポートされている SQL Server インスタンスを実行しているコンピューターで構成されます。

**監査データベース**には、回復データにアクセスしたクライアントコンピューターから収集された監査アクティビティデータが格納されます。

#### レポート

この機能は、Windows Server とサポートされている SQL Server インスタンスを実行しているコンピューターで構成されます。

組織内のクライアントコンピューターの回復監査データは、**レポート**によって提供されます。 レポートは、Configuration Manager コンソールから、または SQL Server Reporting Services から直接表示できます。

### Configuration Manager プライマリサイトサーバー

System Center Configuration Manager の統合機能

-   この機能は構成マネージャーのプライマリサイトサーバーで構成されます。これは、構成マネージャーインフラストラクチャのトップ層サーバーです。

-   **Configuration Manager サーバー**は、クライアントコンピューターからハードウェアインベントリ情報を収集し、クライアントコンピューターの BitLocker のコンプライアンスを報告するために使用されます。

-   Microsoft BitLocker の管理と監視のセットアップウィザードを実行してサーバーソフトウェアをインストールする場合、MBAM がサポートするコンピューターのコレクション、構成基準、およびレポートは、Configuration Manager プライマリサイトサーバーで構成されます。

-   MBAM サーバーソフトウェアをインストールするコンピューターと同じコンピューターに**Configuration Manager コンソール**をインストールする必要があります。

### 管理と監視サーバー

#### 管理と監視の web サイト

この機能は、Windows Server が実行されているコンピューターで構成されます。

**管理と監視の web サイト**を使用して、次の操作を行います。

-   ロックアウトされている場合、エンドユーザーが自分のコンピューターにアクセスできるようにします。(Web サイトのこの領域は、一般にヘルプデスクと呼ばれます)。

-   クライアントコンピューターの回復アクティビティが表示されている回復監査レポートを表示します。 その他のレポートは、Configuration Manager コンソールから表示されます。

#### セルフサービスポータル

この機能は、Windows Server が実行されているコンピューターで構成されます。

**セルフサービスポータル**は、クライアントコンピューターのエンドユーザーが、自分の BitLocker パスワードを紛失または忘れるということを確認するために、個別に web サイトにログオンして回復キーを取得できるようにする web サイトです。

#### この web サイトの web サービスを監視する

この機能は、Windows Server が実行されているコンピューターにインストールされています。

この**監視 web サービス**は、Mbam クライアントと web サイトでデータベースと通信するために使用されます。

**重要**<br>MBAM web サイトは、回復データベースと直接通信しているため、監視 Web サービスは Microsoft BitLocker の管理と監視 (MBAM) 2.5 SP1 では利用できなくなりました。 

 

### 管理ワークステーション

#### MBAM グループポリシーテンプレート

-   **Mbam グループポリシーテンプレート**は、BitLocker ドライブ暗号化を管理するための、mbam の実装設定を定義するグループポリシー設定です。

-   MBAM を実行する前に、グループポリシーテンプレートをダウンロードして、 [MDOP グループポリシー (admx) テンプレートを取得](https://go.microsoft.com/fwlink/p/?LinkId=393941)し、サポートされている windows サーバーまたは windows オペレーティングシステムを実行しているサーバーまたはワークステーションにコピーする必要があります。

    **注**<br>ワークステーションは専用のコンピュータである必要はありません。

     

### MBAM クライアントと Configuration Manager クライアントコンピューター

#### MBAM クライアントソフトウェア

**Mbam クライアント**:

-   グループポリシーオブジェクトを使用して、企業内のクライアントコンピューターで BitLocker ドライブ暗号化を適用します。

-   オペレーティングシステムドライブ、固定データドライブ、およびリムーバブル (USB) データドライブの3種類のデータドライブの BitLocker 回復キーを収集します。

-   クライアントコンピューターに関する回復情報とコンピューターに関する情報を収集します。

#### 構成マネージャー クライアント

Configuration manager**クライアント**は、クライアントコンピューターに関するハードウェア互換性データを収集し、コンプライアンス情報を報告できるようにします。

 

## サポートされている Configuration Manager バージョン向けの MBAM 展開の相違点


Configuration Manager の統合トポロジを使用して MBAM を展開する場合は、プライマリサイトサーバーに MBAM をインストールできます。 ただし、MBAM インストールの動作は、システム Center2012 構成マネージャーと構成 Manager2007 によって異なります。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Configuration Manager のバージョン</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>System Center2012 R2 構成マネージャー</p>
<p>System Center2012 Configuration Manager</p></td>
<td align="left"><p>MBAM をプライマリサイトサーバーまたはサーバーの全体管理サーバーにインストールする場合、MBAM はそのサイトサーバー上のすべてのインストールアクションを実行します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>構成 Manager2007 R2</p>
<p>構成 Manager2007</p></td>
<td align="left"><p>大規模なサイトの親サーバーを持つ大きな Configuration Manager 階層の一部であるプライマリサイトサーバーに MBAM をインストールする場合、MBAM はセントラルサイトの親サーバーを識別し、その親サーバー上のすべてのインストールアクションを実行します。 インストールには、前提条件の確認および Configuration Manager のオブジェクトとレポートのインストールが含まれます。</p>
<p>たとえば、セントラルサイトの親サーバーの子であるプライマリサイトサーバーに MBAM をインストールすると、MBAM は親サーバー上のすべての Configuration Manager オブジェクトとレポートをインストールします。 MBAM を親サーバーにインストールする場合、MBAM はその親サーバー上のすべてのインストールアクションを実行します。</p></td>
</tr>
</tbody>
</table>

 

## 構成マネージャーを使用した MBAM の動作


MBAM と Configuration Manager の統合は、次の表で説明されている項目をインストールする構成パックに基づいています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">構成マネージャーにインストールされたアイテム</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>構成データ</p></td>
<td align="left"><p>構成データは、次の2つの構成項目を含む、"BitLocker Protection" と呼ばれる構成基準をインストールします。</p>
<ul>
<li><p>BitLocker オペレーティングシステムドライブの保護</p></li>
<li><p>BitLocker 固定データドライブの保護</p></li>
</ul>
<p>構成基準は、mbam でサポートされているコンピューターのコレクションに展開されます。これは、MBAM をインストールしたときにも作成されます。</p>
<p>2つの構成項目は、クライアントコンピューターのコンプライアンスの状態を評価するための基礎となります。 この情報は、構成マネージャーでキャプチャ、保存、評価されます。</p>
<p>構成項目は、オペレーティングシステムドライブと固定データドライブのコンプライアンス要件に基づいています。 展開されたコンピューターに必要な詳細情報が収集されて、それらのドライブの種類のコンプライアンスが評価されるようになります。</p>
<p>既定では、構成基準はコンプライアンスの状態の every12 hours を評価し、コンプライアンスデータを Configuration Manager に送信します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM サポートされているコンピューターコレクション</p></td>
<td align="left"><p>MBAM サポートされているコンピューターと呼ばれるコレクションを作成します。 構成基準は、このコレクション内のクライアントコンピューターを対象としています。</p>
<p>これは動的なコレクションです。 既定では、every12 時間が実行され、次の3つの条件に基づいてメンバーシップが評価されます。</p>
<ul>
<li><p>コンピューターは、サポートされている Windows オペレーティングシステムのバージョンです。</p></li>
<li><p>コンピューターは物理コンピューターです。 仮想マシンはサポートされていません。</p></li>
<li><p>コンピューターには、利用可能なトラステッドプラットフォームモジュール (TPM) があります。 Windows7 には、互換性のあるバージョンの TPM 1.2 以降が必要です。 Windows 10、Windows 8.1、Windows8、および Windows To Go では、TPM は必要ありません。</p></li>
</ul>
<p>コレクションは、すべてのコンピューターに対して評価され、互換性のあるコンピューターのサブセットが作成されます。これにより、MBAM 統合のコンプライアンス評価と報告の基礎が提供されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>レポート</p></td>
<td align="left"><p>Configuration Manager の統合トポロジで MBAM を構成すると、[Configuration Manager] ですべてのレポートを表示します。回復監査レポートは、従来の MBAM 管理と監視の Web サイトで引き続き表示されます。 構成マネージャーで利用可能なレポートは、次のとおりです。</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">レポート</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>BitLocker エンタープライズコンプライアンスダッシュボード</p></td>
<td align="left"><p>IT 管理者に対して、1つのレポート内の情報の3つのビューを提供します。これは、コンプライアンスステータスの配布、非準拠–エラーの分布、およびドライブの種類別のコンプライアンスステータスの配布です。 レポートのドリルダウンオプションを使用すると、IT 管理者はデータをクリックして、選択した状態に一致するコンピューターの一覧を表示することができます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>BitLocker Enterprise コンプライアンスの詳細</p></td>
<td align="left"><p>IT 管理者は、企業の BitLocker 暗号化のコンプライアンスステータスに関する情報を表示し、各コンピューターのコンプライアンスの状態を含めることができます。 レポートのドリルダウンオプションを使用すると、IT 管理者はデータをクリックして、選択した状態に一致するコンピューターの一覧を表示することができます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>BitLocker コンピューターのコンプライアンス</p></td>
<td align="left"><p>IT 管理者が個々のコンピューターを表示し、それが準拠しているかどうかについて報告された理由を確認できます。 このレポートには、オペレーティングシステムドライブと固定データドライブの暗号化状態も表示されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>BitLocker Enterprise コンプライアンスの概要</p></td>
<td align="left"><p>IT 管理者は、組織内の MBAM ポリシーのコンプライアンスの状態を表示できます。 各コンピューターの状態が評価され、ポリシーに対する企業内のすべてのコンピューターのコンプライアンスの概要がレポートに表示されます。 レポートのドリルダウンオプションを使用すると、IT 管理者はデータをクリックして、選択した状態に一致するコンピューターの一覧を表示することができます。</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 


## 関連トピック


[MBAM 2.5 をお使いになる前に](getting-started-with-mbam-25.md)

[スタンドアロン トポロジを使用した MBAM 2.5 のアーキテクチャ概要](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)

[MBAM 2.5 展開の機能の図](illustrated-features-of-an-mbam-25-deployment.md)

 

 
## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。




