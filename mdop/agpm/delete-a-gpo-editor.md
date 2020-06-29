---
title: GPO を削除する
description: GPO を削除する
author: dansimp
ms.assetid: 66be3dde-653e-4c25-8cb7-00e7090c8d31
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6c27ddf87a12ed6010c481d93bfc85bb531f3d4f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820974"
---
# GPO を削除する


編集者は、グループポリシーオブジェクト (GPO) の削除を完了するアクセス許可が与えられていない可能性がありますが、プロセスを開始して要求を承認者に送信するために必要なアクセス許可を持っている可能性があります。

この手順を完了するには、編集者の役割を持つユーザーアカウント、または高度なグループポリシーの管理に必要なアクセス許可が必要です。 詳細については、このトピックの「その他の考慮事項」を参照してください。

**コントロールされた GPO の削除を要求するには**

1.  [**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。

2.  [**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理された gpo を表示します。

3.  削除する GPO を右クリックし、[**削除**] をクリックします。

    -   展開されたバージョンの GPO を運用環境でそのまま残して、アーカイブから GPO を削除するには、[ **gpo の削除**] をクリックします。

    -   アーカイブと運用環境の両方から GPO を削除するには、[**アーカイブと運用] から [gpo の削除**] をクリックします。

        Gpo を削除するための特別なアクセス許可を持っていない場合は、展開された GPO の削除の要求を送信する必要があります。 要求のコピーを受信するには、[ **Cc** ] フィールドにメールアドレスを入力します。 GPO の監査トレールに表示されるコメントを入力し、[**送信**] をクリックします。

4.  **進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。 GPO は、[**保留中**] タブの gpo の一覧に表示されます。承認者が要求を承認した場合、GPO は [**保留中**] タブから [**ごみ箱**] タブに移動され、そこで復元または破棄することができます。

### その他の考慮事項

-   既定では、展開された GPO の削除を要求するエディターが必要です。 具体的には、GPO の [**リストコンテンツ]** と [**編集設定**] のアクセス許可が必要です。

-   既定では、アーカイブから GPO を削除するには、編集者、承認者、AGPM 管理者 (フルコントロール) である必要があります。 具体的には、GPO の [**コンテンツの一覧]** と [**設定の編集**] または [ **gpo の削除**] のアクセス許可を持っている必要があります。

-   承認される前に要求を取り消すには、[**保留中**] タブをクリックします。 GPO を右クリックし、[**取り消し] をクリックし**ます。 GPO は [**コントロール**] タブに戻ります。

-   制御されていない GPO を運用環境から削除するには、まず**グループポリシー管理コンソール**で、[**フォレスト**] をクリックし、[**ドメイン**] をクリックして、[ ** &lt; MyDomain &gt; **] をクリックし、[**グループポリシーオブジェクト**] をクリックします。 非制御 GPO を右クリックし、[**削除**] をクリックします。

### その他の参照情報

-   [編集者タスクの実行](performing-editor-tasks.md)

 

 




