---
title: Application Virtualization Sequencer のログ ファイル
description: Application Virtualization Sequencer のログ ファイル
author: dansimp
ms.assetid: 1a296544-eab4-46f9-82ce-3136f8b578af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d8cdf9dbc78ccdd03df5903ef4d42990099a2c53
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816217"
---
# Application Virtualization Sequencer のログ ファイル


Application Virtualization (App-v) Sequencer のログファイルには、アプリケーションの優先順位に関する詳細情報が記載されています。また、機能を確認するときや、問題のトラブルシューティングを行うときに役立ちます。

次の表は、Sequencer を使用するときに作成されるログファイルとその既定の場所に関する情報を示しています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ログファイル名</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>sft-seq-log.txt</strong></p></td>
<td align="left"><p>アプリケーションの順序付けに関する一般的な情報を提供します。 このログは、Sequencer エラーのトラブルシューティングの出発点として使用します。</p>
<p>ログファイルの場所: <em> %Windir%\Microsoft Application Virtualization Sequencer\Logs</em></p>
<p>[Template Token の値]App-v 4.6 log file location: <em> %windir%\Program Valuapplication Virtualization Sequencer\Logs </em> [Template Token Value]</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>sftbt.txt</strong></p></td>
<td align="left"><p>Sequencer のシミュレートされた再起動時に発生する、コンピューターの再起動タスクに関する情報を提供します。</p>
<p>ログファイルの場所: <em> %Windir%\Microsoft Application Virtualization Sequencer\Logs</em></p>
<p>[Template Token の値]App-v 4.6 log file location: <em> %windir%\Program Valuapplication Virtualization Sequencer\Logs </em> [Template Token Value]</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>SftCallBack.txt</strong></p></td>
<td align="left"><p>シーケンス中に使用されるプロセスに関する一般的な情報を提供します。</p>
<p>ログファイルの場所: <em> %Windir%\Microsoft Application Virtualization Sequencer\Logs</em></p>
<p>[Template Token の値]App-v 4.6 log file location: <em> %windir%\Program Valuapplication Virtualization Sequencer\Logs </em> [Template Token Value]</p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[Application Virtualization Sequencer リファレンス](application-virtualization-sequencer-reference.md)

 

 





