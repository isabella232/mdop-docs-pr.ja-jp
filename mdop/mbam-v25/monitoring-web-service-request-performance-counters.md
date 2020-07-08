---
title: Web サービス要求のパフォーマンス カウンターの監視
description: Web サービス要求のパフォーマンス カウンターの監視
author: dansimp
ms.assetid: bdb812a1-465a-4098-b4c0-cb99890d1b0d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2db96e3375562b48d289ea5a21dc7e89b800d1ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823877"
---
# Web サービス要求のパフォーマンス カウンターの監視


Microsoft BitLocker の管理と監視 (MBAM) では、次の web サービスに送信された要求のパフォーマンスを記録するパフォーマンスカウンターが提供されています。

-   **Statusreportingservice. svc** –コンプライアンスの状態の要求を受信するサービス

-   **Coreservice .svc** –キーの回復試行の要求を受信するサービス

## MBAM が提供するパフォーマンスカウンター


MBAM には、StatusReportingService と CoreService web サービスによって実装されるパブリックメソッドごとに、次のパフォーマンスカウンターが用意されています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">パフォーマンスカウンターの種類</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>要求の合計数</p></td>
<td align="left"><p>サーバーの起動時または再起動時にゼロから始まるインクリメントカウントを提供します。</p>
<p>システムアクティビティの全体的なビューを提供します。 自動ツールで監視して、サーバーの正常性を確保し、カウンターが指定された期間にわたって継続的にインクリメントされることを検証することができます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>1秒あたりの要求数</p></td>
<td align="left"><p>Mbam クライアントベースでサポートされている MBAM サーバーの現在のスループットを示します。</p>
<p>サイト管理者が次のことをできるようにします。</p>
<ul>
<li><p>MBAM クライアントの数とその報告頻度に基づいて、1秒あたりの要求の平均数を計算します。</p></li>
<li><p>1秒あたりの要求数が、1秒あたりの合計要求数に大きく関連していることを確認します。 重大な差異は、MBAM クライアントがクライアントベースの割合でインストールされていないか、MBAM グループポリシーオブジェクトが正常に展開されていないことを示している可能性があります。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>要求期間</p></td>
<td align="left"><p>要求の期間 (ミリ秒単位) を記録します。</p>
<p>このカウンターは各要求の期間によって更新されますが、Windows パフォーマンスモニターでは、定期的に (通常は1秒ごとに) サンプリングされるため、値の可変性がいくつか表示されることがあります。 このため、パフォーマンスモニターによって表示される平均値の使用を検討してください。</p></td>
</tr>
</tbody>
</table>

 

## パフォーマンスカウンターの結果と推奨事項


空き容量がある MBAM サーバーに新しい MBAM クライアントを追加すると、要求数が1秒あたり増加することを期待しています。 この増加は、新しいクライアントコンピューターの数に比例します。 平均要求期間は、比較的静的なまま維持されます。 サーバーが最大キャパシティに近づくと、1秒あたりの要求が平準化され、平均要求期間が長くなります。

MBAM サーバーがクライアントベースをサポートしているかどうかが心配な場合は、クライアントコンピューターのさまざまなコレクション間で MBAM を段階的に導入することを検討してください。 クライアントコンピューターの各コレクションに MBAM を展開するときは、パフォーマンスカウンターのスナップショットを取得して、新しい各クライアントコレクションへの展開の相対的な影響を確認することをお勧めします。 1秒あたりの要求数がレベルオフになり、平均要求期間が長くなった場合は、次のいずれかの操作を行って、MBAM サーバーインフラストラクチャを拡張することを検討してください。

-   MBAM データベースを専用の Microsoft SQL Server または SQL Server クラスターに移動する

-   複数のインターネットインフォメーションサービス (IIS) web サーバーでのロードバランシング MBAM

-   より強力なサーバーハードウェアでの MBAM の展開

## パフォーマンスカウンターの表示


MBAM パフォーマンスカウンターを表示するための推奨ツールは、windows に付属している Windows のパフォーマンスモニターです。 Windows PowerShell を使用している場合は、表示する前にカウンターを有効にする必要はありません。これらは、Windows PowerShell の**enable-webapplication**コマンドレットによって自動的に登録されるためです。

パフォーマンスカウンターの表示方法の詳細については、「 [MBAM パフォーマンスカウンターを表示する方法](https://go.microsoft.com/fwlink/?LinkId=393457)」を参照してください。



## 関連トピック


[MBAM 2.5 の保守](maintaining-mbam-25.md)

 

 


## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。


