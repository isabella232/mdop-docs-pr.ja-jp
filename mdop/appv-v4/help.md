---
title: HELP
description: HELP
author: dansimp
ms.assetid: 0ddb5f18-0c0a-45ea-b7c7-2d4749e3d35d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 395e6199529ccbe708aa7d1ac6673ea6f9494ae4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821464"
---
# HELP


Application Virtualization (App-v) で使うことができるさまざまな SFTMIME コマンドに関する情報を表示します。

## HELP


`SFTMIME [/? | /HELP [VERB:<verb>]]`

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
<td align="left"><p>/?,/HELP</p></td>
<td align="left"><p>使用状況の情報を表示します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>動詞</p></td>
<td align="left"><p>実行するコマンド ([追加]、[更新]、[ヘルプ]、[削除] など)。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>object</p></td>
<td align="left"><p>コマンドの適用対象 (アプリ: 既定のアプリケーションなど) &quot;&quot;</p></td>
</tr>
<tr class="even">
<td align="left"><p>引き</p></td>
<td align="left"><p>指定した動詞とオブジェクトの省略可能なパラメーター。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/LOG</p></td>
<td align="left"><p>指定したパス名にログ出力を記録します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/CONSOLE</p></td>
<td align="left"><p>アクティブなコンソールウィンドウに出力を表示します (既定)。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/GUI</p></td>
<td align="left"><p>ダイアログボックスでエラーを表示します (クエリに対しては有効ではありません)。</p></td>
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

 

次の表で説明されている動詞はサポートされています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>ADD</p></td>
<td align="left"><p>新しいアプリケーション、パッケージ、ファイルの種類の関連付け、または発行サーバーを App-v クライアントに追加します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定</p></td>
<td align="left"><p>アプリケーション、パッケージ、ファイルの種類の関連付け、または発行サーバーの構成を変更します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DELETE</p></td>
<td align="left"><p>アプリケーション、パッケージ、ファイルの種類の関連付け、またはサーバーを削除します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>込む</p></td>
<td align="left"><p>ファイルシステムキャッシュにパッケージを読み込みます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>]5D</p></td>
<td align="left"><p>アプリケーションの個人設定をリセットします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>非</p></td>
<td align="left"><p>発行サーバーの更新をトリガーします。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>出版</p></td>
<td align="left"><p>ユーザーの [スタート] メニュー、デスクトップ、またはその他の指定した場所にアプリケーションのショートカットを公開します。または、パッケージ全体のコンテンツを公開するために使うこともできます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>発行</p></td>
<td align="left"><p>パッケージ全体のショートカットとファイルの種類を削除します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>照会</p></td>
<td align="left"><p>アプリケーション、パッケージ、ファイルの種類の関連付け、または公開サーバーの現在の一覧を取得します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>CLEAR</p></td>
<td align="left"><p>1つまたは複数のアプリケーションの個人用設定とデスクトップの構成を削除します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>アドイン</p></td>
<td align="left"><p>ファイルシステムキャッシュからパッケージをアンロードします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LOCK</p></td>
<td align="left"><p>ファイルシステムキャッシュで指定されたアプリケーションをロックします。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ロック</p></td>
<td align="left"><p>ファイルシステムキャッシュで指定されたアプリケーションのロックを解除します。</p></td>
</tr>
</tbody>
</table>

 

上記の操作の詳細については、次のコマンドを使用します。

`SFTMIME /HELP VERB:verb`

たとえば、次のコマンドでは、ADD 動詞の情報が表示されます。

`SFTMIME /HELP VERB:ADD`

## 関連トピック


[SFTMIME コマンドリファレンス](sftmime--command-reference.md)

 

 





