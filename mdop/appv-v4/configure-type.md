---
title: CONFIGURE TYPE
description: CONFIGURE TYPE
author: dansimp
ms.assetid: 2caf9433-5449-486f-ab94-83ee8e44d7f1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9b70cdd1b27eba0109183f1eb9cfb42f08b3f341
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821937"
---
# CONFIGURE TYPE


ユーザーがファイルの種類の関連付けの設定を変更できるようにします。

`SFTMIME CONFIGURE TYPE:file-extension [/GLOBAL] [/APP application]                 [/ICON icon-pathname] [/DESCRIPTION type-desc]                 [/CONTENT-TYPE content-type] [/PERCEIVED-TYPE perceived-type]                 [/PROGID progid] [/CONFIRMOPEN {YES|NO}]                 [/SHOWEXT {YES|NO}] [/NEWMENU {YES|NO}]                 [/LOG log-pathname | /CONSOLE | /GUI]`

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
<td align="left"><p>種類: &lt; ファイル拡張子&gt;</p></td>
<td align="left"><p>構成するファイル名の拡張子。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/APP &lt; application&gt;</p></td>
<td align="left"><p>このファイルの種類を関連付けるアプリケーションの名前とバージョン (省略可能)。 PROGID で指定することはできません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/アイコン &lt; のアイコン-パス名&gt;</p></td>
<td align="left"><p>アイコンファイルのパスまたは URL。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/DESCRIPTION &lt; type-desc&gt;</p></td>
<td align="left"><p>ファイルの種類のわかりやすい名前です。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>コンテンツタイプを入力してください &lt;&gt;</p></td>
<td align="left"><p>ファイルのコンテンツタイプ。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/グローバル</p></td>
<td align="left"><p>存在する場合、ユーザー固有のものではなく、すべてのユーザーに適用される関連付けを編集する必要があることを示します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/PERCEIVED-TYPE &lt; の知覚型&gt;</p></td>
<td align="left"><p>認識されているファイルの種類。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/Progid &lt; progid&gt;</p></td>
<td align="left"><p>拡張子が別のファイルの種類に関連付けられていることを示します。 以前のファイルの種類は削除されません。 アプリ、アイコン、説明、CONFIRMOPEN、または SHOWEXT と共に指定することはできません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/CONFIRMOPEN</p></td>
<td align="left"><p>この種類のファイルをダウンロードするユーザーに対して、ファイルを開くか保存するかをたずねるメッセージを表示するかどうかを示します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/SHOWEXT</p></td>
<td align="left"><p>ユーザーがすべての拡張機能を非表示にすることを要求している場合でも、ファイルの拡張子を常に表示する必要があるかどうかを示します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/新規メニュー</p></td>
<td align="left"><p>シェルの <strong> [新規] メニューにエントリを追加する必要があるかどうかを示し </strong> ます。</p></td>
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

 

 





