---
title: 管理者のみが接続グループを有効にできるようにする方法
description: 管理者のみが接続グループを有効にできるようにする方法
author: dansimp
ms.assetid: 42ca3157-5d85-467b-a148-09404f8f737a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 083d6386f02996d35255f90958705798f2cd5fb9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814451"
---
# 管理者のみが接続グループを有効にできるようにする方法


(エンドユーザーではなく) 管理者のみが接続グループを有効または無効にできるように、App-v クライアントを構成することができます。 以前のバージョンの App-v では、エンドユーザーがこれらのタスクを実行できないようにすることはできませんでした。

**注** 
**この機能は、app-v 5.0 SP3 以降でサポートされています。**

 

管理者のみが接続グループを有効または無効にできるようにするには、次のいずれかの方法を使用します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">メソッド</th>
<th align="left">手順</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>グループ ポリシー設定</p></td>
<td align="left"><p>次のグループポリシーオブジェクトノードにある [管理者として公開する] グループポリシー設定を有効にします。</p>
<p><strong>コンピューター構成 &gt; ポリシー &gt; 管理用テンプレート &gt; システム &gt; アプリ-V の &gt; 発行</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>PowerShell コマンドレット</p></td>
<td align="left"><p><strong> </strong> <strong> – Requirepublishasadmin パラメーターを指定して AppvClientConfiguration コマンドレットを実行し </strong> ます。</p>
<p>パラメーターの値:</p>
<ul>
<li><p>0-偽</p></li>
<li><p>1-True</p></li>
</ul>
<p><strong>例: </strong> AppvClientConfiguration – RequirePublishAsAdmin1</p></td>
</tr>
</tbody>
</table>

 

App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[接続グループの管理](managing-connection-groups51.md)

 

 





