---
title: MED-V ワークスペースの Web 設定を構成する方法
description: MED-V ワークスペースの Web 設定を構成する方法
author: dansimp
ms.assetid: 9a6cd28f-7e4f-468f-830a-7b1d9abd3af3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 770d3fa9a03c9754db86ca348390d0b916de6d5d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827067"
---
# MED-V ワークスペースの Web 設定を構成する方法


Internet Explorer の以前のバージョンでしか表示できない、またはホストオペレーティングシステムに存在しない Web サイトは、MED-V ワークスペース内の Internet Explorer の以前のバージョンで表示できます。 指定した Web サイトを表示するために、ユーザーは MED-V ワークスペースでブラウザーを開く必要はありません。 ユーザーは、ホストでブラウザーを開き、MED-V ワークスペースに自動的にリダイレクトされます。また、その逆も可能です。

次の手順では、MED-V ワークスペースの Web 参照ルールのリストを設定する方法について説明します。 ルールに含まれるすべてのサイトは、管理者によって定義された MED-V ワークスペースまたはホストのいずれかで参照できます。 ルール内に定義されていないすべてのサイトは、要求された環境から参照されます。 ただし、それらをグループとして構成し、MED-V ワークスペースまたはホストで参照できるようにすることもできます。

**注**  
[Web 設定] は、Internet Explorer および他のブラウザーに対してのみ適用されます。



すべての Web 設定は、[ **web** ] タブの**ポリシー**モジュールで構成されます。

## MED-V ワークスペースの Web 設定を構成する方法


**MED-V ワークスペースの Web 設定を構成するには**

1.  構成する MED-V ワークスペースをクリックします。

2.  [**次のテーブルで定義された url のリストを参照**する] チェックボックスをオンにして、ユーザーが指定した Web ルールに準拠した url を参照するときに、med-v workspace または host 内のブラウザーにユーザーをリダイレクトします。

3.  次のいずれかをクリックします。

    -   **ワークスペースで**、med-v ワークスペースのブラウザーにリダイレクトします。

    -   **ホストで**、ホスト上のブラウザーにリダイレクトします。

4.  [**その他のすべての url を参照**] チェックボックスをオンにして、Web ルールから除外するすべての url を host または med-v ワークスペースにリダイレクトします。

5.  次のいずれかをクリックします。

    -   **ワークスペースで、** med-v ワークスペース内のすべての url をブラウザーにリダイレクトします。

    -   **ホスト**の場合: ホスト上のブラウザーに他のすべての url をリダイレクトします。

6.  [**ポリシー** ] メニューで、[**コミット**] を選びます。

## Web ルールを追加する方法


**Web ルールを追加するには**

1.  [**次のテーブルで定義された url のリストを参照**します] チェックボックスをオンにして、Web 参照ルールを有効にします。

2.  **[追加]** をクリックします。

    新しい Web ルールが追加されます。

3.  次の表で説明するように、Web ルールのプロパティを構成します。

4.  [**ポリシー** ] メニューで、[**コミット**] を選びます。

**MED-V ワークスペース Web プロパティ**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">プロパティ</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>種類</p></td>
<td align="left"><ul>
<li><p><strong>ドメインサフィックス </strong> : Value プロパティで指定されているサフィックスで終わる任意のホストアドレスへのアクセス <strong> </strong> 、および Web 閲覧で設定されたオプションに従って設定され <strong> </strong> ます。</p></li>
<li><p><strong>[IP Prefix] </strong> : Value プロパティで指定されたプレフィックスの範囲に含まれる完全な ip アドレスまたは部分的な ip アドレスへのアクセス、 <strong> </strong> および Web 閲覧で設定されたオプションに従って設定され <strong> </strong> ます。</p></li>
<li><p><strong>すべてのローカルアドレス </strong> -&#39; のないすべてのアドレスへのアクセス。 &#39; は、 <strong> Web 閲覧で設定されたオプションに従って設定されます。 </strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>値</p></td>
<td align="left"><ul>
<li><p>[ <strong> </strong> Type] プロパティで [domain suffix] が選択されている場合は <strong> </strong> 、ドメインサフィックスを入力します。</p>
<div class="alert">
<strong>注</strong><br/><ul>
<li><p>&quot; * &quot; サフィックスの前には入力しないでください。</p></li>
<li><p>ドメインサフィックスでもエイリアスがサポートされます。</p></li>
</ul>
</div>
<div>

</div></li>
<li><p>[Type] プロパティで IP プレフィックスが選択されている場合は <strong> </strong> 、完全な ip アドレスまたは一部の ip アドレスを入力します。</p></li>
</ul></td>
</tr>
</tbody>
</table>



## Web ルールを削除する方法


**Web ルールを削除するには**

1.  [ **Web** ] ウィンドウで、削除する web ルールを選びます。

2.  [**削除**] をクリックします。

    Web ルールが削除されます。

## 関連トピック


[MED-V 管理コンソールのユーザー インターフェイスの使用](using-the-med-v-management-console-user-interface.md)

[MED-V ワークスペースの作成](creating-a-med-v-workspacemedv-10-sp1.md)









