---
title: CONFIGURE SERVER
description: CONFIGURE SERVER
author: dansimp
ms.assetid: c916eddd-74f2-46e4-953d-120b23284e37
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7757f281ec57645d20367056ba0013ef476a91a1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821974"
---
# CONFIGURE SERVER


ユーザーがサーバーのセットアップを変更できるようにします。指定されていない設定は変更されません。

`SFTMIME CONFIGURE SERVER:server-name [/NAME display-name] [/HOST hostname]                 [/PORT port] [/PATH path] [/TYPE {HTTP|RTSP}]                 [/REFRESH {ON|OFF}] [/SECURE]                 [/LOG log-pathname | /CONSOLE | /GUI]`

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
<td align="left"><p>サーバー: &lt; サーバー名&gt;</p></td>
<td align="left"><p>発行サーバーの表示名。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/NAME &lt; 表示名&gt;</p></td>
<td align="left"><p>サーバーの新しい表示名。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/HOST &lt; hostname&gt;</p></td>
<td align="left"><p>発行サーバーのホスト名または IP アドレス。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/PORT &lt; ポート&gt;</p></td>
<td align="left"><p>発行サーバーがリッスンするポート。 既定では、標準の HTTP サーバーの場合443は80、強化されたセキュリティを使用する場合は554、標準のアプリケーション仮想化サーバーの場合は、強化されたセキュリティを使用しているサーバーの場合は322が使用されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/PATH &lt; パス&gt;</p></td>
<td align="left"><p>発行要求で使用される URL のパス部分です。 TYPE パラメーターが RTSP に設定されている場合、パスは省略可能です。既定値は &quot; / &quot; です。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/TYPE</p></td>
<td align="left"><p>発行サーバーが Web サーバー (HTTP) であるか、 &quot; &quot; Application Virtualization サーバー (RTSP) であるかを示し &quot; &quot; ます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/更新</p></td>
<td align="left"><p>[オン] に設定した場合、ユーザーがログインすると公開情報が更新されます。 既定値はオンです。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/セキュリティ</p></td>
<td align="left"><p>存在する場合は、セキュリティが強化された接続を発行サーバーに対して確立する必要があることを示します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/LOG</p></td>
<td align="left"><p>指定した場合、出力は指定したパス名に記録されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/CONSOLE</p></td>
<td align="left"><p>指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</p></td>
</tr>
<tr class="odd">
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

 

 





