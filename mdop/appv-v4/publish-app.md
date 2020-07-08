---
title: PUBLISH APP
description: PUBLISH APP
author: dansimp
ms.assetid: f25f06a8-ca23-435b-a0c2-16a5f39b6b97
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b2ccb19255786ee47a8356feef14be1c4d9b4fb2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815817"
---
# PUBLISH APP


ユーザーのスタートメニュー、デスクトップ、またはその他の指定した場所にアプリケーションのショートカットを公開します。

`SFTMIME PUBLISH APP:application                 {/DESKTOP | /START | /TARGET target-path} [/ICON icon-pathname]                 [/DISPLAY display-name] [/ARGS command-args...]                 [/LOG log-pathname | /CONSOLE | /GUI]`

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
<td align="left"><p>アプリケーション: &lt; アプリケーション&gt;</p></td>
<td align="left"><p>アプリケーションの名前とバージョン (省略可能)。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/デスクトップ</p></td>
<td align="left"><p>ユーザーのデスクトップへのショートカットを公開します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/START</p></td>
<td align="left"><p>[スタート] メニューの [プログラム] フォルダーにある Application Virtualization Applications フォルダーへのショートカットを公開します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/TARGET &lt; TARGET-path&gt;</p></td>
<td align="left"><p>ショートカットが公開される絶対パス。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/アイコン &lt; のアイコン-パス名&gt;</p></td>
<td align="left"><p>アイコンファイルのパスまたは URL。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/DISPLAY &lt; の表示名&gt;</p></td>
<td align="left"><p>ショートカットの表示名。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/Args &lt; コマンド-引数&gt;</p></td>
<td align="left"><p>アプリケーションに渡されるパラメーター。</p></td>
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

 

 





