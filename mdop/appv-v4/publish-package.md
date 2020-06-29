---
title: PUBLISH PACKAGE
description: PUBLISH PACKAGE
author: dansimp
ms.assetid: a33e72dd-194f-4283-8e99-4584ab13de53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 00b63389986f495d9405939245a50575bae453f9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815814"
---
# PUBLISH PACKAGE


パッケージ全体のコンテンツを公開します。

`SFTMIME PUBLISH PACKAGE:package-name /MANIFEST manifest-path [/GLOBAL]                 [/LOG log-pathname | /CONSOLE | /GUI]`

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

 

**重要** パッケージは、既に Application Virtualization クライアントに追加されている必要があります。マニフェストファイルが必要です。

**グローバル**パラメーターを使用するには、[パッケージの発行] コマンドをローカルの管理者として実行する必要があります。それ以外の場合は、 **Managetypes**と**publishshortcut**のアクセス許可しか必要ありません。

**グローバル**パラメーターを指定せずに発行すると、ユーザーはパッケージ内のアプリケーションにアクセスできるようになり、マニフェストに記載されているファイルの種類とショートカットが、ユーザーのプロファイルに発行されます。

**グローバル**パラメーターを指定して発行すると、マニフェストに記載されているファイルの種類とショートカットが "すべてのユーザー" プロファイルに追加されます。

パッケージがグローバルではなく、**グローバル**パラメーターを使用している場合は、パッケージはグローバルになり、すべてのユーザーが使用できるようになります。

 

## 関連トピック


[SFTMIME コマンドリファレンス](sftmime--command-reference.md)

 

 





