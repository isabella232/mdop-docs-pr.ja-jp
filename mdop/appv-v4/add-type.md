---
title: ADD TYPE
description: ADD TYPE
author: dansimp
ms.assetid: 8f1d3978-9977-4851-9f46-fee6aefa3535
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4d2dcfb24a32dc733aa91b5534e0011090ef12b9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822384"
---
# ADD TYPE


指定したファイルの種類の関連付けを追加します。

`SFTMIME ADD TYPE:file-extension /APP application [/ICON icon-pathname]                 [/DESCRIPTION type-desc] [/CONTENT-TYPE content-type] [/GLOBAL]                 [/PERCEIVED-TYPE perceived-type] [/PROGID progid]                 [/CONFIRMOPEN {YES|NO}] [/SHOWEXT {YES|NO}]                 [/NEWMENU {YES|NO}]  [/LOG log-pathname | /CONSOLE | /GUI]`

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
<td align="left"><p>指定されたアプリケーションに関連付けられるファイル名拡張子。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/APP &lt; application&gt;</p></td>
<td align="left"><p>アプリケーションの名前とバージョン (省略可能)。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/アイコン &lt; のアイコン-パス名&gt;</p></td>
<td align="left"><p>アイコンファイルのパスまたは URL。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/DESCRIPTION &lt; type-desc&gt;</p></td>
<td align="left"><p>ファイルの種類のわかりやすい名前です。 既定値は &quot; EXTENSION ファイルです。&quot;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>コンテンツタイプを入力してください &lt;&gt;</p></td>
<td align="left"><p>ファイルのコンテンツタイプ。 既定値は &quot; application/softricity です。&quot;</p></td>
</tr>
<tr class="even">
<td align="left"><p>/グローバル</p></td>
<td align="left"><p>存在する場合、このコンピューター上のすべてのユーザーがパッケージを使用できるようになります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/PERCEIVED-TYPE &lt; の知覚型&gt;</p></td>
<td align="left"><p>認識されているファイルの種類。 既定値は何もありません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/Progid &lt; progid&gt;</p></td>
<td align="left"><p>ファイルの種類のプログラム識別子。 既定では、Virt に設定します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/CONFIRMOPEN</p></td>
<td align="left"><p>この種類のファイルをダウンロードするユーザーに対して、ファイルを開くか保存するかをたずねるメッセージを表示するかどうかを示します。 既定値は [はい] です。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/SHOWEXT</p></td>
<td align="left"><p>ユーザーがすべての拡張機能を非表示にすることを要求している場合でも、ファイルの拡張子を常に表示する必要があるかどうかを示します。 既定値は NO です。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/新規メニュー</p></td>
<td align="left"><p>シェルの <strong> [新規] メニューにエントリを追加する必要があるかどうかを示し </strong> ます。 既定値は NO です。</p></td>
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

 

 





