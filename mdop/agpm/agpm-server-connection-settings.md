---
title: AGPM サーバー接続の設定
description: AGPM サーバー接続の設定
author: dansimp
ms.assetid: faf78e5b-2b0d-4069-9b8c-910add892200
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d63163de0a1adf744e6d442b8073e5b32352ed67
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813019"
---
# AGPM サーバー接続の設定


高度なグループポリシー管理 (AGPM) 用の管理用テンプレート設定を使用して、これらの設定が適用されているグループポリシーオブジェクト (GPO) のグループポリシー管理者向けの AGPM サーバー接続を一元的に構成することができます。

GPO を編集している場合は、ユーザー構成 \\ 管理 Templates\\Windows Components\\AGPM の下で次の設定を使用できます。 このパスが表示されない場合は、[**管理用テンプレート**] を右クリックして、agpm または agpm テンプレートを追加します。

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
<td align="left"><p><strong>AGPM サーバー (すべてのドメイン)</strong></p></td>
<td align="left"><p>この設定を有効にすると、すべてのドメインで使用する AGPM サーバー接続を1つだけ構成し、 <strong> グループポリシー管理者の [Agpm サーバー] タブの設定を無効にすることが </strong> できます。 複数の AGPM サーバーの場合は、既定のサーバーを使用してこの設定を構成した後、 <strong> 管理用テンプレートで AGPM サーバー設定を構成して、 </strong> 他のドメインに対してこのサーバーを上書きします。</p>
<p>無効にした場合、または構成しなかった場合、各グループポリシー管理者は、 <strong> agpm の Agpm サーバータブの各ドメインに対して表示する Agpm サーバーを選択する必要があり </strong> ます。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>AGPM サーバー</strong></p></td>
<td align="left"><p>この設定を有効にすると、 <strong> 管理テンプレートの Agpm サーバー (すべてのドメイン) の設定を上書きして、複数のドメイン固有の Agpm サーバーを一元的に構成することが </strong> できます。 環境に1つの AGPM サーバーのみが必要な場合は、 <strong> 管理用テンプレートの Agpm サーバー (すべてのドメイン) の設定のみを使用し </strong> ます。</p>
<p>無効にした場合、または構成しなかった場合は、 <strong> 管理用テンプレートの Agpm サーバー (すべてのドメイン) の設定によって </strong> agpm サーバー接続が構成されます。</p></td>
</tr>
</tbody>
</table>

 

### その他の参照情報

-   [管理用テンプレートの設定](administrative-template-settings.md)

-   [AGPM 管理者タスクの実行](performing-agpm-administrator-tasks.md)

 

 





