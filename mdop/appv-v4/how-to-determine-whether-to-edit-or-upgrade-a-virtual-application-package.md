---
title: 仮想アプリケーション パッケージを編集またはアップグレードするかを決定する方法
description: 仮想アプリケーション パッケージを編集またはアップグレードするかを決定する方法
author: dansimp
ms.assetid: 33dd5332-6802-46e0-9748-43fcc8f80aa3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b256a4927231613b6f2e688b5951adf57c9cb89a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817504"
---
# 仮想アプリケーション パッケージを編集またはアップグレードするかを決定する方法


次の表は、仮想アプリケーションパッケージを編集用に開くことができるかどうかを判断するのに役立ちます。新しいバージョンのパッケージを作成する必要がある場合、またはどちらかのオプションを使用できるかどうかを確認するには、App-v Sequencer を使います。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作</th>
<th align="left">編集用に開く</th>
<th align="left">アップグレードのために開く</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>パッケージのプロパティを表示します。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>要</p></td>
</tr>
<tr class="even">
<td align="left"><p>パッケージの変更履歴を表示します。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>要</p></td>
</tr>
<tr class="odd">
<td align="left"><p>関連付けられたパッケージファイルを表示します。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>要</p></td>
</tr>
<tr class="even">
<td align="left"><p>レジストリ設定を編集します。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>要</p></td>
</tr>
<tr class="odd">
<td align="left"><p>追加のパッケージ設定を確認します (オペレーティングシステムのファイルプロパティを除く)。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>要</p></td>
</tr>
<tr class="even">
<td align="left"><p>関連付けられた Windows インストーラー (MSI) を作成します。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>要</p></td>
</tr>
<tr class="odd">
<td align="left"><p>OSD ファイルを変更します。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>要</p></td>
</tr>
<tr class="even">
<td align="left"><p>パッケージの圧縮と圧縮解除を行います。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>要</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ファイルの種類の関連付けを追加します。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>要</p></td>
</tr>
<tr class="even">
<td align="left"><p>ショートカットの名前を変更します。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>要</p></td>
</tr>
<tr class="odd">
<td align="left"><p>仮想化されたレジストリキーの状態 (上書き/マージ) を設定します。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>要</p></td>
</tr>
<tr class="even">
<td align="left"><p>仮想化されたフォルダーの状態を設定します。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>要</p></td>
</tr>
<tr class="odd">
<td align="left"><p>仮想ファイルシステムのマッピングを編集します。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>要</p></td>
</tr>
<tr class="even">
<td align="left"><p>パッケージの関連するすべてのオペレーティングシステムファイルプロパティを確認します。</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>あり</p></td>
</tr>
<tr class="odd">
<td align="left"><p>その他のサービスを追加します。</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>あり</p></td>
</tr>
<tr class="even">
<td align="left"><p>その他のファイルを追加します。</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>あり</p></td>
</tr>
<tr class="odd">
<td align="left"><p>関連するセキュリティ記述子を収集して構成します。</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>あり</p></td>
</tr>
<tr class="even">
<td align="left"><p>セキュリティ更新プログラムを適用するか、新しいバージョンにアップグレードします。</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>あり</p></td>
</tr>
<tr class="odd">
<td align="left"><p>その他のアプリケーションを追加します。</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>あり</p></td>
</tr>
<tr class="even">
<td align="left"><p>アプリケーションを開く必要がある更新プログラムを適用します。</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>あり</p></td>
</tr>
<tr class="odd">
<td align="left"><p>コンピューターを再起動する必要がある更新プログラムを適用します。</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>○</p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[既存の仮想アプリケーションを編集する方法](how-to-edit-an-existing-virtual-application.md)

[既存の仮想アプリケーションをアップグレードする方法](how-to-upgrade-an-existing-virtual-application.md)

 

 





