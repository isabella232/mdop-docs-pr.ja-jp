---
title: Application Virtualization Client のログ ファイル
description: Application Virtualization Client のログ ファイル
author: dansimp
ms.assetid: ac4b3e4a-a220-4c06-bd60-af7dc318b3a9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 52908aa583d3d673b8a229df14e56f1c71633ef4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816227"
---
# Application Virtualization Client のログ ファイル


Application Virtualization (App-v) クライアントのログファイルには、操作とエラー状態に関する詳細情報がキャプチャされます。 機能を確認するとき、および問題のトラブルシューティングを行うときに使用できます。

App-v クライアントが最初にインストールされると、次の表に示す場所に既定でログファイルが作成されます。 ログファイルの場所は Application Virtualization (App-v) 4.5 では新しくなりましたが、クライアントが以前のバージョンからアップグレードされた場合、場所は変更されません。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ログファイル名</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>sftlog.txt</strong></p></td>
<td align="left"><p>App-v クライアントの操作とエラーに関する一般的な情報を提供します。 このログは、App-v クライアントエラーのトラブルシューティングの出発点として使用します。</p>
<p>デスクトップクライアント、またはリモートデスクトップサービス (以前のターミナルサービス) のクライアントのログファイルの場所:</p>
<ul>
<li><p><em>C:\documents and と Settings\All Users\Application Data\Microsoft\Application Virtualization クライアント </em> : WindowsXP、Windows Server 2003</p></li>
<li><p><em>C:\ProgramData\Microsoft\Application 仮想化クライアント </em> : Windows Vista、Windows Server 2008</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[Application Virtualization Client リファレンス](application-virtualization-client-reference.md)

 

 





