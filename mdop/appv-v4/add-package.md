---
title: ADD PACKAGE
description: ADD PACKAGE
author: dansimp
ms.assetid: aa83928d-a234-4395-831e-2a7ef786ff53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 925349ce5bdf041b6a8768b5413692966e1cfc1e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822397"
---
# ADD PACKAGE


パッケージレコードを追加します。 パッケージが既に存在する場合は、このコマンドによって既存のパッケージの構成が更新されます。

`SFTMIME ADD PACKAGE:package-name /MANIFEST manifest-path                 [/OVERRIDEURL url [/AUTOLOADONREFRESH] [/AUTOLOADONLOGIN]                 [/AUTOLOADONLAUNCH] [/AUTOLOADTARGET {NONE|ALL|PREVUSED}]                 [/GLOBAL] [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">パラメーター</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>パッケージ: &lt; パッケージ名&gt;</p></td>
<td align="left"><p>ユーザーが表示できるパッケージのわかりやすい名前。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/マニフェスト &lt; マニフェストパス&gt;</p></td>
<td align="left"><p>パッケージに含まれているアプリケーションとそのすべての発行情報を一覧表示するマニフェストファイルのパス。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/OVERRIDEURL &lt; URL&gt;</p></td>
<td align="left"><p>パッケージの SFT ファイルの場所。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/Autoloadonrefresh</p></td>
<td align="left"><p>バックグラウンド読み込みは、発行の更新後に実行されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/Autoloadonlogin</p></td>
<td align="left"><p>バックグラウンド読み込みは、ユーザーがログインしたときに実行されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/Autoloadonlaunch</p></td>
<td align="left"><p>バックグラウンド読み込みは、ユーザーがパッケージからアプリケーションを開始した後に実行されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/Autoloadターゲットターゲット</p></td>
<td align="left"><p>パッケージから自動読み込みされるアプリケーションを示します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>-</p></td>
<td align="left"><p>Autoloadonxxx フラグが存在するにもかかわらず、自動読み込みは実行されません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>[ALL] (すべて)</p></td>
<td align="left"><p>自動ロードトリガーが有効になっている場合、パッケージ内のすべてのアプリケーションは、前に開始されたかどうかにかかわらずキャッシュに読み込まれます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>PREVUSED</p></td>
<td align="left"><p>自動ロードトリガーが有効になっている場合、このパッケージ内のアプリケーションがユーザーによって以前に起動された場合、パッケージは読み込まれます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/グローバル</p></td>
<td align="left"><p>存在する場合、このコンピューター上のすべてのユーザーがパッケージを使用できるようになります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/LOG</p></td>
<td align="left"><p>指定した場合、出力は指定したパス名に記録されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/CONSOLE</p></td>
<td align="left"><p>指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/GUI</p></td>
<td align="left"><p>指定すると、Windows のダイアログボックスに出力が表示されます。</p></td>
</tr>
</tbody>
</table>

 

バージョン4.6 の場合、次のオプションが追加されています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>/Logu</p></td>
<td align="left"><p>指定すると、指定したパス名の UNICODE 形式で出力されます。</p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[SFTMIME コマンドリファレンス](sftmime--command-reference.md)

 

 





