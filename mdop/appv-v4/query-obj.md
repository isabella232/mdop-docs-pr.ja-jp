---
title: QUERY OBJ
description: QUERY OBJ
author: dansimp
ms.assetid: 55abf0d1-c779-4172-8357-552ab010933b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 328e9feb96c70080531cbbc666d8ff1b86045ba5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815737"
---
# QUERY OBJ


現在のアプリケーション、パッケージ、ファイルの種類の関連付け、または公開サーバーのタブ区切りのリストを返します。

`SFTMIME QUERY OBJ:{APP|PACKAGE|TYPE|SERVER} [/SHORT] [/GLOBAL]                 [/LOG log-pathname | /CONSOLE ]`

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
<td align="left"><p>アプリケーション</p></td>
<td align="left"><p>アプリケーションのリストを返します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>プレゼンテーション</p></td>
<td align="left"><p>パッケージの一覧を返します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>TYPE</p></td>
<td align="left"><p>ファイルの種類の関連付けのリストを返します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SERVER</p></td>
<td align="left"><p>発行サーバーのリストを返します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/短い</p></td>
<td align="left"><p>各プロパティの完全なプロパティを表示せずに、アプリケーション名、パッケージ、関連付け、またはサーバー名の一覧を返します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/グローバル</p></td>
<td align="left"><p>アプリケーションの場合は、現在のユーザーがアクセスできるすべてのアプリケーションではなく、既知のすべてのアプリケーションを返します。 パッケージの場合、現在のユーザーがアクセス権を持っているものだけでなく、すべての既知のパッケージを返します。 関連付けの場合は、ユーザー固有の関連付けではなく、すべてのユーザーに適用される関連付けだけが返されます。 サーバーに対して無効です。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/LOG</p></td>
<td align="left"><p>指定した場合、出力は指定したパス名に記録されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/CONSOLE</p></td>
<td align="left"><p>指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</p></td>
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

 

**注** バージョン4.6 では、新しい列が SFTMIME クエリ OBJ の出力に追加されました。アプリ \ [/GLOBAL\]。 出力の最後の列は、アプリケーションが公開されているかどうかを示す数値です。

発行済み = 1 は、Windows インストーラーファイル (.) を使ってアプリケーションをインストールすることで、発行サーバーの更新によってアプリケーションが公開されたことを意味します。MSI)、または SFTMIME のパッケージ追加を実行するか、パッケージマニフェストを使ってパッケージを構成するか、[パッケージの発行] コマンドを実行します。

発行済み = 0 は、アプリケーションが公開されていないか、クリア操作を実行しているか、SFTMIME の未発行コマンドを実行しているために、そのアプリケーションが公開されていないことを意味します。

/グローバルパラメーターを使用する場合、公開された状態は、グローバルに公開されているアプリケーションの場合は1、ユーザーコンテキストで公開されたアプリケーションの場合は0になります。 /グローバルパラメーターを指定しなければ、コマンドを実行しているユーザーのコンテキストで公開されたアプリケーションに対して、公開された状態1が返されます。グローバルに公開されているアプリケーションに対しては、0の状態が返されます。

 

SFTMIME QUERY OBJ コマンドを使って、上に示したすべてのオブジェクト (アプリケーション、パッケージ、ファイルの種類の関連付け、サーバー) に関する情報を照会できます。通常の運用タスクで SFTMIME クエリ OBJ コマンドを使用する方法を示すために、次の例は、特定のパッケージの OVERRIDEURL パラメーターの値を設定して、パッケージコンテンツへの新しいパスを指定する場合の手順を示しています。 

1.  構成するパッケージを見つけるには、次のコマンドを実行します。

    `SFTMIME QUERY OBJ:PACKAGE`

    このコマンドは、検出された各パッケージ名を、出力の最初の列 ({AF78ABE1-57D4-4297-89DE-C308684AEDD6} など) の GUID として返します。

2.  OVERRIDEURL パラメーターの値を設定するには、SFTMIME [CONFIGURE パッケージ](configure-package.md)コマンドを使用します。 たとえば、このパッケージの OVERRIDEURL 値を、 *\\ ¥ server¥*¥¥の値に設定するには、次のように、SFTMIME CONFIGURE package コマンドを使用して、手順1の SFTMIME クエリ OBJ コマンドの出力から選んだパッケージ GUID を指定します。次のようにします。

    `SFTMIME CONFIGURE PACKAGE:"{AF78ABE1-57D4-4297-89DE-C308684AEDD6}" /OVERRIDEURL "\\\\server\\share\\mypackage.sft "`

バージョン 4.6 SP2 の場合、次のオプションが追加されています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>/NO-UPDATE-FTA-SHORTCUT</p></td>
<td align="left"><p>/NO-UPDATE-FTA-SHORTCUT フラグの現在の状態を示します。</p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[SFTMIME コマンドリファレンス](sftmime--command-reference.md)

 

 





