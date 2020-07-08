---
title: PowerShell を使用して App-V 5.0 Client のレポート機能を有効にする方法
description: PowerShell を使用して App-V 5.0 Client のレポート機能を有効にする方法
author: dansimp
ms.assetid: a7aaf553-0f83-4cd0-8df8-93a5f1ebe497
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c004b4900a9814a11cb2706659a2edb99de6cc1b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814090"
---
# PowerShell を使用して App-V 5.0 Client のレポート機能を有効にする方法


レポート用に App-v 5.0 を構成するには、次の手順を使用します。

**レポート用に App-v 5.0 クライアントを実行しているコンピューターを構成するには**

1. App-v 5.0 クライアントをインストールします。 クライアントのインストールの詳細については、「 [App-v クライアントを展開する方法」を](how-to-deploy-the-app-v-client-gb18030.md)参照してください。

2. App-v 5.0 クライアントをインストールしたら、 **AppvClientConfiguration** PowerShell を使用して、適切なレポート構成設定を構成します。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">設定</th>
   <th align="left">説明</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>ReportingEnabled</p></td>
   <td align="left"><p>クライアントが情報をレポートサーバーに返すことができるようにします。 この設定は、クライアントがクライアントのレポートデータを収集するために必要です。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>ReportingServerURL</p></td>
   <td align="left"><p>クライアント情報が保存されている、レポートサーバー上の場所を指定します。 たとえば、http:// &lt; reportingservername &gt; : &lt; reportingservername 番号 &gt; 。</p>
   <div class="alert">
   <strong>注</strong><br/><p>これは、レポートサーバーのセットアップ時に割り当てられたポート番号です</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>レポート開始時刻</p></td>
   <td align="left"><p>これは、クライアントが自動的にデータをサーバーに送信するようにスケジュールするように設定されています。 この設定は、レポートデータが送信を開始する時間を示します。 24時間形式で、0-23 の間には数値がかかります。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>ReportingRandomDelay</p></td>
   <td align="left"><p>レポートサーバーに送信されるデータの最大遅延 (分単位) を指定します。 スケジュールされたタスクが開始されると、クライアントは0と ReportingRandomDelay の間のランダムな遅延を生成し、データを送信する前に指定された期間待機します。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>ReportingInterval</p></td>
   <td align="left"><p>クライアントがデータをレポートサーバーに再送信するために使用する再試行間隔を指定します。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>Reportingdatacachlimit</p></td>
   <td align="left"><p>レポート情報を格納する XML キャッシュの最大サイズ (MB) を指定します。 サイズは、メモリ内のキャッシュに適用されます。 上限に達すると、ログファイルがロールオーバーされます。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>Reportingの各の Locksize</p></td>
   <td align="left"><p>レポート情報を格納する XML キャッシュの最大サイズ (MB) を指定します。 サイズは、メモリ内のキャッシュに適用されます。 上限に達すると、ログファイルがロールオーバーされます。</p></td>
   </tr>
   </tbody>
   </table>



3. 適切な設定が構成された後、App-v 5.0 クライアントを実行しているコンピューターはデータを自動的に収集し、データをレポートサーバーに送ります。

   さらに、管理者は、 **AppvClientReport** PowerShell コマンドレットを使用して、手動でオンデマンド方式でデータを戻すことができます。

   App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[PowerShell を使用した App-V の管理](administering-app-v-by-using-powershell.md)









