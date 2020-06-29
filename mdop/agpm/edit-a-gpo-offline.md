---
title: オフラインで GPO を編集する
description: オフラインで GPO を編集する
author: dansimp
ms.assetid: 4a148952-9fe9-4ec4-8df1-b25e37c97a54
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6753ad21adb810e60e0b284204a61d4dd58c2384
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820887"
---
# オフラインで GPO を編集する


グループポリシーオブジェクト (GPO) に変更を加えるには、まず、その GPO のコピーをアーカイブからチェックアウトする必要があります。 他のユーザーは、もう一度チェックインするまで GPO を変更することはできません。これにより、複数のグループポリシー管理者による競合している変更の導入を防ぐことができます。 GPO の変更が完了したら、それをアーカイブにチェックインして、運用環境に確認して展開できるようにします。

この手順を完了するには、Editor または AGPM 管理者 (フルコントロール) の役割を持つユーザーアカウント、または高度なグループポリシー管理で必要なアクセス許可を持つユーザーアカウントを使用する必要があります。 詳細については、このトピックの「その他の考慮事項」を参照してください。

## GPO をオフラインで編集する


GPO を編集するには、アーカイブから GPO をチェックアウトして、オフラインでその gpo を編集してから、GPO をアーカイブにチェックインして、その GPO が確認および展開されるようにします (他のエディターによって変更された場合)。

-   [GPO をチェックアウトする](#bkmk-checkout)

-   [GPO を編集する](#bkmk-edit)

-   [GPO をチェックインする](#bkmk-checkin)

### <a href="" id="bkmk-checkout"></a>

**アーカイブから GPO をチェックアウトして編集するには**

1.  [**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。

2.  [詳細] ウィンドウの [**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理されている gpo を表示します。

3.  編集する GPO を右クリックし、[チェックアウト] をクリック**します。**

4.  チェックアウトされているときに、GPO の履歴に表示されるコメントを入力して、[ **OK]** をクリックします。

5.  **進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。 [**コントロール**] タブで、GPO の状態が**チェックアウト済み**として識別されるようになりました。

### <a href="" id="bkmk-edit"></a>

**GPO をオフラインで編集するには**

1.  [**コントロール**] タブで、編集する GPO を右クリックし、[**編集**] をクリックします。

2.  **グループポリシーオブジェクトエディター**で、GPO のオフラインコピーに変更を加えます。

3.  GPO の変更が完了したら、**グループポリシーオブジェクトエディター**を閉じます。

### <a href="" id="bkmk-checkin"></a>

**GPO をアーカイブにチェックインするには**

1.  [**コントロール**] タブで、次の操作を行います。

    -   GPO に変更を加えていない場合は、GPO を右クリックし、[**元に戻す**] をクリックします。次に、[**はい**] をクリックして確認します。

    -   GPO に変更を加えた場合は、その GPO を右クリックして [**チェックイン**] をクリックします。

2.  GPO の監査トレールに表示されるコメントを入力し、[ **OK]** をクリックします。

3.  **進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。 [**コントロール**] タブでは、GPO の状態は**チェックイン済み**として識別されます。

### その他の考慮事項

-   GPO をチェックアウトして編集するには、既定で、GPO、エディター、または AGPM 管理者 (フルコントロール) を作成または管理する承認者である必要があります。 具体的には、GPO の [**リストコンテンツ]** と [**編集設定**] のアクセス許可が必要です。 さらに、GPO を編集するには、GPO をチェックアウトした個人である必要があります。

-   GPO をチェックインするには、既定で、編集者、承認者、または AGPM 管理者 (フルコントロール) である必要があります。 具体的には、その GPO の [**コンテンツの一覧]** と [**設定の編集**] または [gpo のアクセス許可の**展開**] を行う必要があります。 承認者または AGPM 管理者 (または**gpo の展開**に関するその他のグループポリシー管理者) ではない場合は、gpo をチェックアウトしたエディターである必要があります。

-   GPO を編集する場合、別の GPO にあるパッケージのグループポリシーソフトウェアのインストールアップグレードは、チェックアウトしたコピーではなく、展開された GPO を参照する必要があります。

### その他の参照情報

-   [GPO の編集](editing-a-gpo.md)

-   GPO を確認する

    -   [GPO の設定を確認する](review-gpo-settings.md)

    -   [GPO のリンクを確認する](review-gpo-links.md)

    -   [GPO、GPO のバージョン、またはテンプレート間の相違点を識別する](identify-differences-between-gpos-gpo-versions-or-templates.md)

-   GPO の展開

    -   [GPO の展開を要求する](request-deployment-of-a-gpo.md)

    -   [GPO を展開する](deploy-a-gpo.md)

 

 




