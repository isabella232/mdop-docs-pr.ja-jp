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
ms.openlocfilehash: 9ec9b1e4391fde3083564f34b5f89d1c5bd174f7
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910672"
---
# <a name="high-level-architecture-of-mbam-25-with-stand-alone-topology"></a>スタンドアロン トポロジを使用した MBAM 2.5 のアーキテクチャ概要


このトピックでは、Configuration Manager スタンドアロン トポロジを使用して Microsoft BitLocker Administration and Monitoring (MBAM) を展開する場合の推奨アーキテクチャについて説明します。 このトポロジでは、MBAM はスタンドアロン製品として展開されます。 また、MBAM を Configuration Manager と統合する Configuration Manager 統合トポロジを使用して、MBAM を展開できます。 詳細については、「Configuration Manager Integration Topology を使用した [MBAM 2.5 のハイレベル アーキテクチャ」を参照してください](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)。

このトピックで説明するソフトウェアのサポートされているバージョンの一覧については [、「MBAM 2.5 サポートされる構成」を参照してください](mbam-25-supported-configurations.md)。

**備考**  
テスト環境でのみ単一サーバー アーキテクチャを使用することをお勧めします。

 

## <a name="recommended-number-of-servers-and-supported-number-of-clients"></a>推奨されるサーバー数とサポートされるクライアント数


実稼働環境で推奨されるサーバー数とサポートされるクライアント数は次のとおりです。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">実稼働環境での推奨アーキテクチャ</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>サーバーと他のコンピューターの数</p></td>
<td align="left"><p>2 台のサーバー</p>
<p>1 つのワークステーション</p></td>
</tr>
<tr class="even">
<td align="left"><p>サポートされているクライアント コンピューターの数</p></td>
<td align="left"><p>500,000</p></td>
</tr>
</tbody>
</table>

 

## <a name="recommended-mbam-high-level-architecture-with-the-stand-alone-topology"></a>スタンドアロン トポロジを使用した推奨 MBAM ハイレベル アーキテクチャ


次の図と表は、スタンドアロン トポロジを使用した MBAM の推奨される高レベルの 2 サーバー アーキテクチャについて説明します。 MBAM マルチフォレスト展開では、一方通行または 2 ウェイの信頼が必要です。 一方通行の信頼では、サーバー ドメインがクライアント ドメインを信頼している必要があります。

![mbam2。](images/mbam2-5-2servers.png)

このサーバーの説明データベース サーバーで構成するサーバー機能

コンプライアンスと監査データベース

この機能は、サーバーを実行しているサーバー WindowsインスタンスでSQL Serverされます。

コンプライアンス**データベースと監査データベースには**コンプライアンス データが格納されます。これは、主にホストを管理するレポートSQL Server Reporting Servicesされます。

回復データベース

この機能は、サーバーを実行しているサーバー WindowsインスタンスでSQL Serverされます。

回復 **データベースには、MBAM** クライアント コンピューターから収集された回復データが格納されます。

レポート

この機能は、サーバーを実行しているサーバー WindowsインスタンスでSQL Serverされます。

レポート **は** 、企業内のクライアント コンピューターに関する回復監査とコンプライアンス状態データを提供します。 レポートには、管理および監視 Web サイトから、または管理 Web サイトから直接アクセスSQL Server Reporting Services。

管理および監視サーバー

管理と監視の Web サイト

この機能は、サーバーを実行しているコンピューター Windowsされます。

管理 **および監視 Web サイトは、次の** 場合に使用されます。

-   エンド ユーザーがロックアウト時にコンピューターへのアクセスを回復するのに役立ちます。(Web サイトのこの領域は、一般にヘルプ デスクと呼ばれる)

-   クライアント コンピューターのコンプライアンス状態と回復アクティビティを示すレポートを表示します。

Self-Service ポータル

この機能は、サーバーを実行しているコンピューター Windowsされます。

セルフサービス **ポータルは** 、クライアント コンピューター上のエンド ユーザーが、BitLocker パスワードを紛失または忘れた場合に回復キーを取得するために Web サイトに個別にログオンできる Web サイトです。

この Web サイトの Web サービスの監視

この機能は、サーバーを実行しているコンピューター Windowsされます。

監視 **Web サービスは** 、MBAM クライアントと Web サイトがデータベースと通信するために使用します。

**重要**  
MbAM Web サイトは回復データベースと直接通信するために、Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1 で監視 Web サービスを使用できなくなりました。

 

管理ワークステーション

MBAM グループ ポリシー テンプレート

-   MBAM グループ ポリシー テンプレートは、MBAM の実装設定を定義するグループ ポリシー設定で、BitLocker ドライブの暗号化を管理できます。

-   MBAM を実行する前に、[MDOP グループ ポリシー [(.admx)](https://go.microsoft.com/fwlink/p/?LinkId=393941)テンプレートを取得する方法] からグループ ポリシー テンプレートをダウンロードし、サポートされている Windows Server または Windows オペレーティング システムを実行しているサーバーまたはワークステーションにコピーする必要があります。

-   ワークステーションは専用のコンピューターである必要はない。

MBAM クライアント および Configuration Manager クライアント コンピューター

MBAM クライアント ソフトウェア

MBAM クライアント:

-   グループ ポリシー オブジェクトを使用して、企業のクライアント コンピューターに BitLocker ドライブ暗号化を適用します。

-   オペレーティング システム ドライブ、固定データ ドライブ、リムーバブル (USB) データ ドライブの 3 種類の Bitlocker 回復キーを収集します。

-   クライアント コンピューターに関する回復情報とコンピューター情報を収集します。



## <a name="related-topics"></a>関連トピック


[MBAM 2.5 をお使いになる前に](getting-started-with-mbam-25.md)

[Configuration Manager 統合トポロジを使用した MBAM 2.5 のアーキテクチャ概要](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)

[MBAM 2.5 展開の機能の図](illustrated-features-of-an-mbam-25-deployment.md)

 

## <a name="got-a-suggestion-for-mbam"></a>MBAM の提案を受け取った場合
- ここで提案を追加または投票 [します](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)。 
- MBAM の問題については [、MBAM TechNet フォーラムを使用します](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





