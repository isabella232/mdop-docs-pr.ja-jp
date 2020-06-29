---
title: スタンドアロン トポロジを使用した MBAM 2.5 のアーキテクチャ概要
description: スタンドアロン トポロジを使用した MBAM 2.5 のアーキテクチャ概要
author: dansimp
ms.assetid: 35f8c5f6-8be3-443d-baf0-56d68b08f3bc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 75e878e24b4675f2f2f574791d0f06ecadd0196d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826557"
---
# スタンドアロン トポロジを使用した MBAM 2.5 のアーキテクチャ概要


このトピックでは、構成マネージャー単体のトポロジを使用して、Microsoft BitLocker 管理と監視 (MBAM) を展開するための推奨アーキテクチャについて説明します。 このトポロジでは、MBAM はスタンドアロン製品として展開されています。 または、Configuration manager の統合トポロジを使用して MBAM を展開することもできます。これは、構成マネージャーとして MBAM を統合します。 詳細については、「 [MBAM 2.5 の高レベルアーキテクチャと構成マネージャーの統合トポロジ](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)」を参照してください。

このトピックで説明しているソフトウェアのサポートされているバージョンの一覧については、「 [Mbam 2.5 でサポートされている構成](mbam-25-supported-configurations.md)」を参照してください。

**注** テスト環境でのみ、単一サーバーアーキテクチャを使用することをお勧めします。

 

## 推奨されるサーバー数とクライアント数


運用環境での推奨されるサーバー数とサポートされているクライアント数は、次のとおりです。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">運用環境での推奨アーキテクチャ</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>サーバーとその他のコンピューターの数</p></td>
<td align="left"><p>2つのサーバー</p>
<p>1つのワークステーション</p></td>
</tr>
<tr class="even">
<td align="left"><p>サポートされているクライアントコンピューターの数</p></td>
<td align="left"><p>50万</p></td>
</tr>
</tbody>
</table>

 

## 単体のトポロジを備えた、お勧めの MBAM 高レベルのアーキテクチャ


次の図と表は、スタンドアロントポロジでの MBAM の推奨される高レベルの 2 server アーキテクチャを示しています。 MBAM 複数フォレスト展開には、一方向または双方向の信頼が必要です。 一方向の信頼には、サーバーのドメインがクライアントドメインを信頼する必要があります。

![mbam2](images/mbam2-5-2servers.png)

このサーバーの説明データベースサーバーで構成するサーバー機能

コンプライアンスと監査データベース

この機能は、Windows Server とサポートされている SQL Server インスタンスを実行しているサーバーで構成されています。

**コンプライアンスと監査データベース**は、主に SQL Server Reporting Services がホストするレポートに使用されるコンプライアンスデータを格納します。

回復用データベース

この機能は、Windows Server とサポートされている SQL Server インスタンスを実行しているサーバーで構成されています。

**回復データベース**には、mbam クライアントコンピューターから収集された回復データが格納されます。

レポート

この機能は、Windows Server とサポートされている SQL Server インスタンスを実行しているサーバーで構成されています。

**レポート**は、企業内のクライアントコンピューターに関する回復監査およびコンプライアンスステータスのデータを提供します。 管理と監視の Web サイトから、または SQL Server Reporting Services から直接レポートにアクセスできます。

管理と監視サーバー

管理と監視の Web サイト

この機能は、Windows Server が実行されているコンピューターで構成されます。

**管理と監視の Web サイト**を使用して、次の操作を行います。

-   ロックアウトされている場合、エンドユーザーが自分のコンピューターにアクセスできるようにします。(Web サイトのこの領域は、一般にヘルプデスクと呼ばれます)。

-   クライアントコンピューターのコンプライアンス状態と回復アクティビティを表示するレポートを表示します。

セルフサービスポータル

この機能は、Windows Server が実行されているコンピューターで構成されます。

**セルフサービスポータル**は、クライアントコンピューターのエンドユーザーが、自分の BitLocker パスワードを紛失または忘れるということを確認するために、個別に web サイトにログオンして回復キーを取得できるようにする web サイトです。

この web サイトの web サービスを監視する

この機能は、Windows Server が実行されているコンピューターで構成されます。

この**監視 web サービス**は、Mbam クライアントと web サイトでデータベースと通信するために使用されます。

**重要** MBAM web サイトは、回復データベースと直接通信しているため、監視 Web サービスは Microsoft BitLocker の管理と監視 (MBAM) 2.5 SP1 では利用できなくなりました。

 

管理ワークステーション

MBAM グループポリシーテンプレート

-   MBAM グループポリシーテンプレートは、BitLocker ドライブ暗号化を管理するための、MBAM の実装設定を定義するグループポリシー設定です。

-   MBAM を実行する前に、グループポリシーテンプレートをダウンロードして、 [MDOP グループポリシー (admx) テンプレートを取得](https://go.microsoft.com/fwlink/p/?LinkId=393941)し、サポートされている windows サーバーまたは windows オペレーティングシステムを実行しているサーバーまたはワークステーションにコピーする必要があります。

-   ワークステーションは専用のコンピュータである必要はありません。

MBAM クライアントと Configuration Manager クライアントコンピューター

MBAM クライアントソフトウェア

MBAM クライアント:

-   グループポリシーオブジェクトを使用して、企業内のクライアントコンピューターで BitLocker ドライブ暗号化を適用します。

-   オペレーティングシステムドライブ、固定データドライブ、およびリムーバブル (USB) データドライブの3種類のデータドライブの Bitlocker 回復キーを収集します。

-   クライアントコンピューターに関する回復情報とコンピューターに関する情報を収集します。



## 関連トピック


[MBAM 2.5 をお使いになる前に](getting-started-with-mbam-25.md)

[Configuration Manager 統合トポロジを使用した MBAM 2.5 のアーキテクチャ概要](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)

[MBAM 2.5 展開の機能の図](illustrated-features-of-an-mbam-25-deployment.md)

 

## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





