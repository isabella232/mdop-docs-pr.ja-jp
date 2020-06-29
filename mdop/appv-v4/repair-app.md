---
title: REPAIR APP
description: REPAIR APP
author: dansimp
ms.assetid: 892b556b-612d-4531-890e-4cfc2ac88d9f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 791628efd22b0ad429a09e48a82e2d55b45783bd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815724"
---
# REPAIR APP


このコマンドを実行すると、アプリケーションの個人設定がリセットされます。

`SFTMIME REPAIR APP:application [/LOG log-pathname | /CONSOLE | /GUI]`

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
<td align="left"><p>アプリ: &lt; アプリケーション&gt;</p></td>
<td align="left"><p>アプリケーションの名前とバージョン (省略可能)。</p></td>
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

 

 





