---
title: PowerShell コマンドを使用して DaRT のタスクを実行する方法
description: PowerShell コマンドを使用して DaRT のタスクを実行する方法
author: dansimp
ms.assetid: bc788b00-38c7-4f57-a832-916b68264d89
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f8ff87aa09555b93ca04a6ec7fa5dd4ba8504514
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824304"
---
# PowerShell コマンドを使用して DaRT のタスクを実行する方法


Microsoft 診断/回復ツールセット (DaRT) 8.0 には、次のような Windows PowerShell コマンドレットのセットが用意されています。 管理者は、これらの PowerShell コマンドレットを使用して、DaRT 回復イメージウィザードではなく、コマンドプロンプトからさまざまな DaRT 8.0 サーバタスクを実行できます。

## PowerShell コマンドを使用して DaRT を管理するには


DaRT を管理するには、ここで説明する PowerShell コマンドレットを使用します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名前</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>コピー-DartImage</p></td>
<td align="left"><p>ISO を CD、DVD、または USB ドライブに焼きます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>エクスポート-DartImage</p></td>
<td align="left"><p>DaRT イメージを含むソース WIM ファイルを ISO ファイルに変換できます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>新規-DartConfiguration</p></td>
<td align="left"><p>DaRT のツールセットを Windows イメージに適用するために必要な DaRT 構成オブジェクトを作成します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Set-DartImage</p></td>
<td align="left"><p>マウントされた Windows イメージに DartConfiguration オブジェクトを適用します。 これには、すべてのファイル、構成、パッケージの依存関係の追加が含まれます。</p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[PowerShell を使用した DaRT 8.0 の管理](administering-dart-80-using-powershell-dart-8.md)

 

 





