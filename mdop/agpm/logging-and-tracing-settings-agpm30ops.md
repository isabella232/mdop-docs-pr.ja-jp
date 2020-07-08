---
title: ログとトレースの設定
description: ログとトレースの設定
author: dansimp
ms.assetid: 858b6fbf-65b4-42fa-95a9-69b04e5734d7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 078bda16b5fcf968d45e0c4890487471105e8c44
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820594"
---
# ログとトレースの設定


高度なグループポリシー管理 (AGPM) の管理用テンプレート設定では、これらの設定が適用されたグループポリシーオブジェクト (GPO) を適用する AGPM サーバーとクライアントのログとトレースオプションを一元的に構成することができます。

GPO を編集するときに、[コンピューター Configuration\\Policies\\Administrative Templates\\Windows Components\\AGPM で次の設定を使用できます。

**トレースファイルの場所**:

-   クライアント:%LocalAppData%\\Microsoft\\AGPM\\agpm.log

-   サーバー:%ProgramData%\\Microsoft\\AGPM\\agpmserv.log

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
<td align="left"><p><strong>AGPM: ログを構成する</strong></p></td>
<td align="left"><p>このポリシー設定では、AGPM のログを有効にし、構成することができます。 この設定は、AGPM のクライアントコンポーネントとサーバーコンポーネントの両方に影響します。</p></td>
</tr>
</tbody>
</table>

 

### その他の参照情報

-   [[管理用テンプレート] フォルダー](administrative-templates-folder-agpm30ops.md)

 

 





