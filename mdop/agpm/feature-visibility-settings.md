---
title: 機能の表示の設定
description: 機能の表示の設定
author: dansimp
ms.assetid: 9db2ba03-fb75-4f95-9138-ec89b9fc8d01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 26f19895d0a9163885779688ba7d89f6d16f2a17
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820807"
---
# 機能の表示の設定


高度なグループポリシー管理 (AGPM) の管理用テンプレート設定を使用すると、これらの設定が適用されているグループポリシーオブジェクト (GPO) の**変更コントロール**ノードと [**履歴**] タブの表示を一元的に構成できます。

グループポリシー管理コンソール (GPMC) で GPO を編集するときに、**グループポリシーオブジェクトエディター**で、[ユーザー構成] \\ [管理 Templates\\Windows Components\\Microsoft 管理コンソール \ \ 制限/許可されている Snap-ins\\Extension スナップイン] の下の設定を使用できます。 このパスが表示されない場合は、[**管理用テンプレート**] を右クリックして、agpm または agpm テンプレートを追加します。

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
<td align="left"><p><strong>AGPM 変更の制御</strong></p></td>
<td align="left"><p>有効になっているか、構成されていない場合は、 <strong> GPMC に [変更コントロール] </strong> ノードが表示されます。</p>
<p>無効にすると、 <strong> GPMC で [変更コントロール] </strong> ノードが表示されなくなります。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>AGPM リンク拡張機能</strong></p></td>
<td align="left"><p>有効になっているか、構成されていない場合は、 <strong> </strong> リンクされた各 GPO の [履歴] タブが GPMC に表示されます。</p>
<p>無効にした場合、 <strong> </strong> リンクされた gpo の [履歴] タブは表示されません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>AGPM GPO 拡張機能</strong></p></td>
<td align="left"><p>有効になっているか、構成されていない場合は、 <strong> </strong> 各 GPO の GPMC に [履歴] タブが表示されます。</p>
<p>無効にした場合、[ <strong> 履歴 </strong> ] タブは gpo に表示されません。</p></td>
</tr>
</tbody>
</table>

 

### その他の参照情報

-   [管理用テンプレートの設定](administrative-template-settings.md)

 

 





