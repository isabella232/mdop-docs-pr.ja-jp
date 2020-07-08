---
title: 運用環境へのアクセスを委任する
description: 運用環境へのアクセスを委任する
author: dansimp
ms.assetid: c1ebae2e-909b-4e64-b368-b7d3cc67b1eb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4667a23f1584d7aab6143860721e326da6407afb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821014"
---
# 運用環境へのアクセスを委任する


運用環境のグループポリシーオブジェクト (Gpo) へのアクセスを変更し、それらの Gpo に対する既存のアクセス許可を置き換えます。 ドメインレベルでアクセス許可を構成して、ユーザーがグループポリシー管理コンソール (GPMC) で**Change Control**フォルダーを使用していない場合に、運用環境で gpo のセキュリティを編集、削除、または変更できないようにすることができます。

**注**  
-   運用環境へのアクセスを委任しても、ユーザーが Gpo をリンクする機能には影響しません。

-   Gpo が制御または展開されている場合は、他のアカウント ([**読み取り**] および [**適用**] のアクセス許可を持つアカウントを除く) へのアクセスは削除されます。

 

この手順を完了するには、高度なグループポリシー管理 (AGPM) で必要な権限または AGPM 管理者 (フルコントロール) の役割を持つユーザーアカウントが必要です。 詳細については、このトピックの「その他の考慮事項」を参照してください。

**運用環境で Gpo へのアクセスを変更するには**

1.  [**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。

2.  [**運用の委任**] タブをクリックします。

3.  運用環境にアクセスできないユーザーまたはグループにアクセス許可を追加するか、またはアクセス権があるユーザーまたはグループのアクセス許可を置き換えるには、次の操作を行います。

    1.  [**追加**] をクリックし、ユーザーまたはグループを選択して、[ **OK]** をクリックします。

    2.  [権限] を選択して、実稼働環境のユーザーまたはグループに委任し、[ **OK]** をクリックします。

4.  ユーザーまたはグループの運用環境に対するすべての権限を削除するには、ユーザーまたはグループを選択し、[**削除**] をクリックして、[ **OK]** をクリックします。

### その他の考慮事項

-   既定では、この手順を実行するには AGPM 管理者 (フルコントロール) である必要があります。 具体的には、ドメインの [**セキュリティの変更**] アクセス許可を持っている必要があります。

-   AGPM サービスアカウントのアクセス許可は、[運用の**委任**] タブで変更することはできません。

-   既定では、次のアカウントには、実稼働環境の Gpo に対する権限があります。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">Account</th>
    <th align="left">Gpo の既定のアクセス許可</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>&lt;AGPM サービスアカウント&gt;</p></td>
    <td align="left"><p>設定の編集、削除、セキュリティの変更</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>認証済みユーザー</p></td>
    <td align="left"><p>読み取り、適用</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>ドメイン管理者</p></td>
    <td align="left"><p>設定の編集、削除、セキュリティの変更</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>エンタープライズ管理者</p></td>
    <td align="left"><p>設定の編集、削除、セキュリティの変更</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>エンタープライズドメインコントローラー</p></td>
    <td align="left"><p>Read</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>システム</p></td>
    <td align="left"><p>設定の編集、削除、セキュリティの変更</p></td>
    </tr>
    </tbody>
    </table>

     

-   グループポリシー Creator Owners グループのメンバーシップは制限されている必要があります。 soit は、Gpo へのアクセスの AGPM 管理を回避するために使用されることはありません。 (**グループポリシー管理コンソール**で、gpo を管理するフォレストとドメインの [**グループポリシーオブジェクト**] をクリックし、[**委任**] をクリックして、組織のニーズに合わせて設定を構成します)。

### その他の参照情報

-   [高度なグループ ポリシーの管理の構成](configuring-advanced-group-policy-management.md)

 

 





