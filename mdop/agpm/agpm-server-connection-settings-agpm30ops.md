---
title: AGPM サーバー接続の設定
description: AGPM サーバー接続の設定
author: dansimp
ms.assetid: 5f03e397-b868-4c49-9cbf-a5f5d0ddcc39
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d9ee1e67eb2c565bcf833314d82cdf611e2caa85
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812987"
---
# AGPM サーバー接続の設定


高度なグループポリシー管理 (AGPM) 用の管理用テンプレート設定を使用して、これらの設定が適用されているグループポリシーオブジェクト (GPO) のグループポリシー管理者向けの AGPM サーバー接続を一元的に構成することができます。

GPO を編集するときに、ユーザー Configuration\\Policies\\Administrative Templates\\Windows Components\\AGPM で次の設定を使用できます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">設定</th>
<th align="left">効果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>AGPM: 既定の AGPM サーバー (すべてのドメイン) を指定する</strong></p></td>
<td align="left"><p>このポリシー設定では、すべてのドメインに対して既定の AGPM サーバーを指定できます。 これは、AGPM クライアントでのみ使用され、グループポリシー管理者が別のアーカイブに接続することを制限します。 <strong>Agpm: Agpm サーバー設定を使用して、個々のドメインに対してこの既定値を上書きできます </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>AGPM: AGPM サーバーを指定する</strong></p></td>
<td align="left"><p>このポリシー設定では、個々のドメインに対して AGPM サーバーを指定できます。 これは、AGPM クライアントでのみ使用され、グループポリシー管理者が指定したドメインの別のアーカイブに接続することを制限します。 既定の AGPM サーバーを指定するには、 <strong> agpm: DEFAULT Agpm server (すべてのドメイン) の設定を使用 </strong> し、このポリシー設定を使用して、ドメインごとに既定値を上書きします。</p></td>
</tr>
</tbody>
</table>

 

### その他の参照情報

-   [[管理用テンプレート] フォルダー](administrative-templates-folder-agpm30ops.md)

-   [AGPM 管理者タスクの実行](performing-agpm-administrator-tasks-agpm30ops.md)

 

 





