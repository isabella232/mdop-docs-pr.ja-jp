---
title: ログとトレースの設定
description: ログとトレースの設定
author: dansimp
ms.assetid: db6b43c7-fdde-4d11-b5ab-a81346e56940
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bef0f8367647aad688c2aec7586ecdaae2e22143
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820587"
---
# ログとトレースの設定


高度なグループポリシー管理 (AGPM) の管理用テンプレート設定では、これらの設定が適用されたグループポリシーオブジェクト (GPO) を適用する AGPM サーバーとクライアントのログとトレースオプションを一元的に構成することができます。

グループポリシー管理コンソール (GPMC) で GPO を編集するときに、**グループポリシーオブジェクトエディター**のコンピューター構成 \\ 管理 Templates\\Windows Components\\AGPM の下で、次の設定を使用できます。 このパスが表示されない場合は、[**管理用テンプレート**] を右クリックして、agpm または agpm テンプレートを追加します。

**トレースファイルの場所**:

-   クライアント:%LocalAppData%\\Microsoft\\AGPM\\agpm.log

-   サーバー:%CommonAppData%\\Microsoft\\AGPM\\agpmserv.log

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
<td align="left"><p><strong>AGPM ログ</strong></p></td>
<td align="left"><p>この設定を有効にすると、トレースを有効にするか、詳細レベルを設定するかが構成されます。 この設定は、AGPM のクライアントコンポーネントとサーバーコンポーネントの両方に影響します。</p>
<p>無効にした場合、または構成しなかった場合、この設定には影響はありません。</p></td>
</tr>
</tbody>
</table>

 

### その他の参照情報

-   [管理用テンプレートの設定](administrative-template-settings.md)

 

 





