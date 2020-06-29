---
title: UE-V 1.0 の基幹業務アプリケーションを評価するためのチェックリスト
description: UE-V 1.0 の基幹業務アプリケーションを評価するためのチェックリスト
author: dansimp
ms.assetid: 3bfaab30-59f7-4099-abb1-d248ce0086b8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 133bc5d195763b7281fd8d152e153231ac4c4d47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826457"
---
# UE-V 1.0 の基幹業務アプリケーションを評価するためのチェックリスト


UE-V の展開に含める基幹業務アプリケーションを評価するには、次の点を考慮します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>このアプリケーションには、ユーザーがカスタマイズできる設定が含まれていますか。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>これらの設定がローミングしていることは、ユーザーにとって重要ですか?</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>これらのユーザー設定は、既にアプリケーション管理または設定ポリシーソリューションによって管理されていますか。 UE-V は、アプリケーションの起動と Windows の設定で、ログオン、ロック解除、またはリモート接続イベントにアプリケーション設定を適用します。 UE-V を他の設定ポリシーソリューションと共に使用している場合、ユーザーによっては、ローミング設定で不整合が発生する可能性があります。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>アプリケーションの設定はコンピューターに固有のものですか? ハードウェアまたは特定のコンピューター構成に関連付けられたアプリケーションの環境設定とカスタマイズは、セッション間で一貫してローミングされず、アプリケーションのパフォーマンスが低下する可能性があります。</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>アプリケーションは、Program Files ディレクトリまたは <strong> ユーザー </strong> \ [ユーザー名] \ AppData locallow ディレクトリにあるファイルディレクトリの設定を保存してい <strong> </strong>  \  <strong> </strong> ますか? これらの場所のいずれかに保存されているアプリケーションデータは、通常、コンピューターに固有のデータであるため、またはデータが大きすぎてローミングできないため、ユーザーと共に移動することはできません。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>ローミングしてはいけない他のアプリケーションデータを含むファイルの設定が、アプリケーションに格納されますか。 UE-V は、1つの単位としてファイルを同期します。 設定が [設定] 以外のアプリケーションデータを含むファイルに保存されている場合、この追加データを同期すると、アプリケーションのパフォーマンスが低下する可能性があります。</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>設定を含むファイルのサイズはどのくらいですか? 設定の同期のパフォーマンスは、大きなファイルの影響を受ける可能性があります。 大きなファイルを含めると、設定の同期のパフォーマンスに影響する可能性があります。</p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[UE-V の構成方法の計画](planning-for-ue-v-configuration-methods.md)

[UE-V 1.0 の計画](planning-for-ue-v-10.md)

 

 





