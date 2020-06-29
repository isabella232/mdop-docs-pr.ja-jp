---
title: CONFIGURE PACKAGE
description: CONFIGURE PACKAGE
author: dansimp
ms.assetid: acc7eaa8-6ada-47b9-a655-2ca2537605b9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dc8b315b68349cc9834316786b0bf15d4ac3c5cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819347"
---
# CONFIGURE PACKAGE


パッケージマニフェストファイル、パッケージソース、ロードトリガーの種類、またはパッケージのターゲットの読み込みをユーザーが変更できるようにします。

`SFTMIME CONFIGURE PACKAGE:package-name [/MANIFEST manifest-path]                 [/OVERRIDEURL url] [/AUTOLOADNEVER] [/AUTOLOADONREFRESH]                 [/AUTOLOADONLOGIN] [/AUTOLOADONLAUNCH]                 [/AUTOLOADTARGET {NONE|ALL|PREVUSED}]                 [/LOG log-pathname | /CONSOLE | /GUI]                 [/NO-UPDATE-FTA-SHORTCUT {TRUE|FALSE} {/GLOBAL}]`

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
<td align="left"><p>パッケージに含まれているアプリケーションとそのすべての発行情報を一覧表示するマニフェストファイルのパスまたは URL。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/OVERRIDEURL &lt; URL&gt;</p></td>
<td align="left"><p>パッケージの SFT ファイルの場所。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/Autoloadnever</p></td>
<td align="left"><p>パッケージのバックグラウンド読み込みが無効になっています。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/Autoloadonrefresh</p></td>
<td align="left"><p>バックグラウンド読み込みは、発行の更新後に実行されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/Autoloadonlogin</p></td>
<td align="left"><p>バックグラウンド読み込みは、ユーザーがログインしたときに実行されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/Autoloadonlaunch</p></td>
<td align="left"><p>バックグラウンド読み込みは、ユーザーがパッケージからアプリケーションを開始した後に実行されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/Autoloadターゲット &lt; ターゲット&gt;</p></td>
<td align="left"><p>パッケージから自動読み込みされるアプリケーションを示します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>-</p></td>
<td align="left"><p>Autoloadonxxx フラグの有無にかかわらず、自動読み込みは実行されません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>[ALL] (すべて)</p></td>
<td align="left"><p>自動ロードトリガーが有効になっている場合、パッケージ内のすべてのアプリケーションは、起動されたかどうかに関係なく、キャッシュに読み込まれます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>PREVUSED</p></td>
<td align="left"><p>自動ロードトリガーが有効になっている場合、このパッケージ内のアプリケーションがユーザーによって以前に起動された場合、パッケージは読み込まれます。</p></td>
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

 

バージョン 4.6 SP2 の場合、次のオプションが追加されています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>[/NO-UPDATE-FTA-SHORTCUT {TRUE |FALSE} {/GLOBAL}]</p></td>
<td align="left"><p>TRUE に設定すると、ユーザーごと、または/グローバルフラグが指定されている場合はグローバルに、パッケージのレジストリ値が作成されます。</p>
<p>FALSE に設定すると、レジストリ値が削除され、パッケージのファイルの種類の関連付け (FTA) が再インストールされます。</p>
<p>指定しない場合、標準の FTA とショートカットの発行動作が行われます。 App-v 4.6 SP2 クライアントでその後の公開更新操作を実行した場合は、このレジストリ値が設定されているパッケージのショートカットと FTAs は変更されません。また、フラグをリセットしない限り、ショートカットと FTAs はシステムのスタートアップまたはユーザーログインで登録されません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/グローバル</p></td>
<td align="left"><p>/NO-UPDATE-FTA-SHORTCUT フラグと連携して動作します。 /グローバルフラグが存在する場合は、そのパッケージのレジストリ値がすべてのユーザーに対して作成されることを示します。 既定では、このユーザーに対してのみレジストリ値が作成されます。</p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[SFTMIME コマンドリファレンス](sftmime--command-reference.md)

 

 





