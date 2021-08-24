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
ms.openlocfilehash: a0f9349391794100a670e382bb18d0713f4b5b60
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910722"
---
# <a name="high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology"></a>Configuration Manager 統合トポロジを使用した MBAM 2.5 のハイレベル アーキテクチャ

このトピックでは、Configuration Manager 統合トポロジを使用して Microsoft BitLocker Administration and Monitoring (MBAM) を展開する場合の推奨アーキテクチャについて説明します。 このトポロジでは、MBAM とデータベースSystem Center Configuration Manager。 スタンドアロン トポロジを使用して MBAM を展開するには、「スタンドアロン トポロジを使用した [MBAM 2.5 のハイレベル アーキテクチャ」を参照してください](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)。

このトピックで説明するソフトウェアのサポートされているバージョンの一覧については [、「MBAM 2.5 サポートされる構成」を参照してください](mbam-25-supported-configurations.md)。

**重要**  
WindowsConfiguration Manager 2007 を使用している場合、To Go は Configuration Manager 統合トポロジ のインストールではサポートされていません。

 

## <a name="recommended-number-of-servers-and-supported-number-of-clients"></a>推奨されるサーバー数とサポートされるクライアント数


実稼働環境で推奨されるサーバー数とサポートされるクライアント数は次のとおりです。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">推奨アーキテクチャ</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>サーバーと他のコンピューターの数</p></td>
<td align="left"><p>3 つのサーバー</p>
<p>1 つのワークステーション</p></td>
</tr>
<tr class="even">
<td align="left"><p>サポートされているクライアント コンピューターの数</p></td>
<td align="left"><p>500,000</p></td>
</tr>
</tbody>
</table>

 

## <a name="differences-between-configuration-manager-integration-and-stand-alone-topologies"></a>Configuration Manager 統合とスタンドアロン トポロジの違い


トポロジの主な違いは次のとおりです。

-   コンプライアンス機能とレポート機能は MBAM から削除され、Configuration Manager からアクセスされます。

-   レポートは、MBAM 管理および監視 Web サイトから引き続き表示される回復監査レポートを除き、Configuration Manager 管理コンソールから表示されます。

## <a name="recommended-mbam-high-level-architecture-with-the-configuration-manager-integration-topology"></a>Configuration Manager 統合トポロジを使用した推奨 MBAM ハイレベル アーキテクチャ


次の図と表に、Configuration Manager 統合トポロジを使用した MBAM の推奨されるハイレベル アーキテクチャについて説明します。 MBAM マルチフォレスト展開では、一方通行または 2 ウェイの信頼が必要です。 一方通行の信頼では、サーバー ドメインがクライアント ドメインを信頼している必要があります。

![mbam2\-5。](images/mbam2-5-cmserver.png)

### <a name="database-server"></a>データベース サーバー

#### <a name="recovery-database"></a>回復データベース

この機能は、サーバーを実行しているコンピューター Windows構成され、インスタンスSQL Serverされます。

回復 **データベースには、MBAM** クライアント コンピューターから収集された回復データが格納されます。

#### <a name="audit-database"></a>監査データベース

この機能は、サーバーを実行しているコンピューター Windows構成され、インスタンスSQL Serverされます。

Audit **Database には** 、回復データにアクセスしたクライアント コンピューターから収集された監査アクティビティ データが格納されます。

#### <a name="reports"></a>レポート

この機能は、サーバーを実行しているコンピューター Windows構成され、インスタンスSQL Serverされます。

レポート **は** 、企業内のクライアント コンピューターの回復監査データを提供します。 レポートは、Configuration Manager コンソールから、または管理者から直接SQL Server Reporting Services。

### <a name="configuration-manager-primary-site-server"></a>Configuration Manager プライマリ サイト サーバー

System Center Configuration Manager統合機能

-   この機能は、Configuration Manager インフラストラクチャのトップ層サーバーである Configuration Manager プライマリ サイト サーバーで構成されます。

-   **Configuration Manager Server は、** クライアント コンピューターからハードウェア インベントリ情報を収集し、クライアント コンピューターの BitLocker 準拠を報告するために使用されます。

-   Microsoft BitLocker 管理と監視セットアップ ウィザードを実行してサーバー ソフトウェアをインストールすると、MBAM サポートされているコンピューターのコレクション、構成基準、およびレポートが Configuration Manager プライマリ サイト サーバーで構成されます。

-   **Configuration Manager コンソールは、MBAM** Server ソフトウェアをインストールするコンピューターと同じコンピューターにインストールする必要があります。

### <a name="administration-and-monitoring-server"></a>管理サーバーと監視サーバー

#### <a name="administration-and-monitoring-website"></a>Web サイトの管理と監視

この機能は、サーバーを実行しているコンピューター Windowsされます。

管理 **および監視 Web サイトは、次の** 場合に使用されます。

-   エンド ユーザーがロックアウト時にコンピューターへのアクセスを回復するのに役立ちます。(Web サイトのこの領域は、一般にヘルプ デスクと呼ばれる)

-   クライアント コンピューターの回復アクティビティを示す回復監査レポートを表示します。 その他のレポートは、Configuration Manager コンソールから表示されます。

#### <a name="self-service-portal"></a>セルフサービス ポータル

この機能は、サーバーを実行しているコンピューター Windowsされます。

セルフサービス **ポータルは** 、クライアント コンピューター上のエンド ユーザーが、BitLocker パスワードを紛失または忘れた場合に回復キーを取得するために Web サイトに個別にログオンできる Web サイトです。

#### <a name="monitoring-web-services-for-this-website"></a>この Web サイトの Web サービスの監視

この機能は、サーバーを実行しているコンピューター Windowsされます。

監視 **Web サービスは** 、MBAM クライアントと Web サイトがデータベースと通信するために使用します。

**重要**<br>MbAM Web サイトは回復データベースと直接通信するために、Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1 で監視 Web サービスを使用できなくなりました。 

 

### <a name="management-workstation"></a>管理ワークステーション

#### <a name="mbam-group-policy-templates"></a>MBAM グループ ポリシー テンプレート

-   **MBAM グループ ポリシー テンプレート**は、MBAM の実装設定を定義するグループ ポリシー設定で、BitLocker ドライブの暗号化を管理できます。

-   MBAM を実行する前に、[MDOP グループ ポリシー [(.admx)](https://go.microsoft.com/fwlink/p/?LinkId=393941)テンプレートを取得する方法] からグループ ポリシー テンプレートをダウンロードし、サポートされている Windows Server または Windows オペレーティング システムを実行しているサーバーまたはワークステーションにコピーする必要があります。

    **注**<br>ワークステーションは専用のコンピューターである必要はない。

     

### <a name="mbam-client-and-configuration-manager-client-computer"></a>MBAM クライアント および Configuration Manager クライアント コンピューター

#### <a name="mbam-client-software"></a>MBAM クライアント ソフトウェア

**MBAM クライアント**:

-   グループ ポリシー オブジェクトを使用して、企業のクライアント コンピューターに BitLocker ドライブの暗号化を適用します。

-   オペレーティング システム ドライブ、固定データ ドライブ、リムーバブル (USB) データ ドライブの 3 種類の BitLocker 回復キーを収集します。

-   クライアント コンピューターに関する回復情報とコンピューター情報を収集します。

#### <a name="configuration-manager-client"></a>構成マネージャー クライアント

**Configuration Manager クライアントを使用**すると、Configuration Manager はクライアント コンピューターに関するハードウェア互換性データを収集し、コンプライアンス情報を報告できます。

 

## <a name="differences-in-mbam-deployment-for-supported-configuration-manager-versions"></a>サポートされている Configuration Manager バージョンの MBAM 展開の違い


Configuration Manager 統合トポロジを使用して MBAM を展開する場合は、プライマリ サイト サーバーに MBAM をインストールできます。 ただし、MBAM インストールは、2012 Configuration Manager と Configuration Manager 2007 System Centerの動作が異なります。

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
<td align="left"><p>System Center 2012 R2 Configuration Manager</p>
<p>System Center 2012 Configuration Manager</p></td>
<td align="left"><p>MBAM をプライマリ サイト サーバーまたはサーバーの全体管理サーバーにインストールする場合、MBAM は、そのサイト サーバー上のすべてのインストール 操作を実行します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Configuration Manager 2007 R2</p>
<p>Configuration Manager 2007</p></td>
<td align="left"><p>中央サイトの親サーバーを持つ大規模な Configuration Manager 階層の一部であるプライマリ サイト サーバーに MBAM をインストールすると、MBAM は中央サイトの親サーバーを識別し、その親サーバー上のすべてのインストール 操作を実行します。 インストールには、前提条件の確認と Configuration Manager オブジェクトとレポートのインストールが含まれます。</p>
<p>たとえば、中央サイトの親サーバーの子であるプライマリ サイト サーバーに MBAM をインストールすると、MBAM は、すべての Configuration Manager オブジェクトとレポートを親サーバーにインストールします。 MBAM を親サーバーにインストールすると、MBAM は、その親サーバー上のすべてのインストール 操作を実行します。</p></td>
</tr>
</tbody>
</table>

 

## <a name="how-mbam-works-with-configuration-manager"></a>構成マネージャーでの MBAM の動作


MBAM と Configuration Manager の統合は、次の表に示すアイテムをインストールする構成パックに基づいて行います。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Configuration Manager にインストールされているアイテム</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>構成データ</p></td>
<td align="left"><p>構成データは、次の 2 つの構成項目を含む "BitLocker Protection" と呼ばれる構成基準をインストールします。</p>
<ul>
<li><p>BitLocker オペレーティング システム ドライブ保護</p></li>
<li><p>BitLocker 固定データ ドライブ保護</p></li>
</ul>
<p>構成基準は、MBAM のインストール時にも作成される MBAM サポートされているコンピューター コレクションに展開されます。</p>
<p>2 つの構成項目は、クライアント コンピューターのコンプライアンス状態を評価するための基礎となります。 この情報は、Configuration Manager でキャプチャ、保存、および評価されます。</p>
<p>構成項目は、オペレーティング システム ドライブと固定データ ドライブのコンプライアンス要件に基づいて行います。 展開されたコンピューターに必要な詳細が収集され、それらのドライブの種類に対するコンプライアンスを評価できます。</p>
<p>既定では、構成基準は 12 時間ごとにコンプライアンス状態を評価し、コンプライアンス データを Configuration Manager に送信します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM サポートされているコンピューター コレクション</p></td>
<td align="left"><p>MBAM は、MBAM サポートされているコンピューターと呼ばれるコレクションを作成します。 構成基準は、このコレクション内のクライアント コンピューターを対象とします。</p>
<p>これは動的コレクションです。 既定では、12 時間ごとに実行され、3 つの条件に基づいてメンバーシップが評価されます。</p>
<ul>
<li><p>コンピューターは、サポートされているバージョンのオペレーティング システムWindowsです。</p></li>
<li><p>コンピューターは物理コンピューターです。 仮想マシンはサポートされていません。</p></li>
<li><p>コンピューターには、利用可能なトラステッド プラットフォーム モジュール (TPM) があります。 互換性のあるバージョンの TPM 1.2 以降は、7 以降Windowsです。 Windows 10、Windows 8.1、Windows 8、Windows移動には TPM は必要ではありません。</p></li>
</ul>
<p>コレクションは、すべてのコンピューターに対して評価され、互換性のあるコンピューターのサブセットが作成され、MBAM 統合のコンプライアンス評価とレポート作成の基礎となります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>レポート</p></td>
<td align="left"><p>Configuration Manager 統合トポロジを使用して MBAM を構成すると、回復監査レポートを除くすべてのレポートが Configuration Manager に表示され、そのレポートは MBAM 管理および監視 Web サイトで引き続き表示されます。 Configuration Manager で使用できるレポートは次のとおりです。</p>
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
<td align="left"><p>BitLocker エンタープライズコンプライアンス ダッシュボード</p></td>
<td align="left"><p>IT 管理者は、1 つのレポートで 3 つのビューの情報を提供します。コンプライアンス状態の配布、非準拠 - エラーの配布、およびドライブの種類別のコンプライアンス状態の配布。 レポートのドリルダウン オプションを使用すると、IT 管理者はデータをクリックし、選択した状態に一致するコンピューターの一覧を表示できます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>BitLocker エンタープライズコンプライアンスの詳細</p></td>
<td align="left"><p>IT 管理者は、企業の BitLocker 暗号化コンプライアンス状態に関する情報を表示し、各コンピューターのコンプライアンス状態を含めます。 レポートのドリルダウン オプションを使用すると、IT 管理者はデータをクリックし、選択した状態に一致するコンピューターの一覧を表示できます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>BitLocker コンピューターのコンプライアンス</p></td>
<td align="left"><p>IT 管理者は、個々のコンピューターを表示し、準拠または準拠していない状態で報告された理由を特定できます。 このレポートには、オペレーティング システム ドライブと固定データ ドライブの暗号化状態も表示されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>BitLocker エンタープライズコンプライアンスの概要</p></td>
<td align="left"><p>IT 管理者は、企業の MBAM ポリシーコンプライアンスの状態を表示できます。 各コンピューターの状態が評価され、ポリシーに対する企業内のすべてのコンピューターのコンプライアンスの概要がレポートに表示されます。 レポートのドリルダウン オプションを使用すると、IT 管理者はデータをクリックし、選択した状態に一致するコンピューターの一覧を表示できます。</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 


## <a name="related-topics"></a>関連トピック


[MBAM 2.5 をお使いになる前に](getting-started-with-mbam-25.md)

[スタンドアロン トポロジを使用した MBAM 2.5 のアーキテクチャ概要](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)

[MBAM 2.5 展開の機能の図](illustrated-features-of-an-mbam-25-deployment.md)

 

 
## <a name="got-a-suggestion-for-mbam"></a>MBAM の提案を受け取った場合
- ここで提案を追加または投票 [します](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)。 
- MBAM の問題については [、MBAM TechNet フォーラムを使用します](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




