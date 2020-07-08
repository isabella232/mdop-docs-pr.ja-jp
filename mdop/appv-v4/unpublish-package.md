---
title: UNPUBLISH PACKAGE
description: UNPUBLISH PACKAGE
author: dansimp
ms.assetid: 1651427c-72a5-4701-bb57-71e14a7a3803
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7704fb3ed03be4864a837767d9e890d28b63f175
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815134"
---
# UNPUBLISH PACKAGE


パッケージ全体のショートカットとファイルの種類を削除することができます。

`SFTMIME UNPUBLISH PACKAGE:package-name [/CLEAR] [/GLOBAL]                 [/LOG log-pathname | /CONSOLE | /GUI]`

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
<td align="left"><p>パッケージの名前。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/CLEAR</p></td>
<td align="left"><p>存在する場合、ユーザー設定も削除されます。 (詳細については、このトピックで後述する重要なメモを参照してください)。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/グローバル</p></td>
<td align="left"><p>存在する場合、このコンピューター上のすべてのユーザーについてパッケージは非公開になります。</p></td>
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

 

**重要** [パッケージの発行を**取り消す**] コマンドを実行する前に、アプリの仮想化クライアントにパッケージが既に追加されている必要があります。

**グローバル**を使用するには、**未発行パッケージ**をローカル管理者として実行する必要があります。それ以外の場合は、 **Clearapp**権限のみが必要です。

[**グローバル**で**パッケージを公開**しない] を使用すると、パッケージのグローバルファイルの種類とショートカットがすべて削除されます。 **CLEAR**は適用されません。

[**グローバル**で**パッケージを発行**しない] を使用すると、パッケージのユーザーショートカットとファイルの種類が削除され、**明確**に設定されている場合は、ユーザー設定が削除され、ユーザーのコンテキストに応じてバックグラウンドの読み込みが停止します。

"**非公開" パッケージ**は、パッケージの**追加**、**編集**、**公開**のソース ID として使用されたものと同じパッケージ名または GUID から、アプリケーションで動作します。

[**パッケージの発行を取り消す**] は、/CLEAR スイッチの使用に関係なく、常にすべてのユーザー設定、ショートカット、およびファイルの種類をクリアします。

 

## 関連トピック


[SFTMIME コマンドリファレンス](sftmime--command-reference.md)

 

 





