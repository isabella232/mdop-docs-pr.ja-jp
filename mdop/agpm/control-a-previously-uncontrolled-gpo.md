---
title: 未制御の GPO を制御する
description: 未制御の GPO を制御する
author: dansimp
ms.assetid: 452689a9-4e32-4e3b-8208-56353a82bf36
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9d7349b16b326a49b701efae5379c313bde0964f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818887"
---
# 未制御の GPO を制御する


高度なグループポリシー管理 (AGPM) を使ってグループポリシーオブジェクト (GPO) の変更制御を提供するには、まず、AGPM で GPO を制御する必要があります。

この手順を完了するには、承認者または AGPM 管理者 (フルコントロール) の役割、または高度なグループポリシーの管理に必要なアクセス許可を持つユーザーアカウントが必要です。 詳細については、このトピックの「その他の考慮事項」を参照してください。

**以前に制御していない GPO を制御するには**

1.  [**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。

2.  [詳細] ウィンドウの [**コンテンツ**] タブで、[**非コントロール**] タブをクリックして、制御されていない gpo を表示します。

3.  AGPM で制御する GPO を右クリックし、[**コントロール**] をクリックします。

4.  GPO の履歴に表示するコメントを入力し、[ **OK]** をクリックします。

5.  **進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。 [**非コントロール**] タブの一覧から GPO が削除され、[**コントロール**] タブに追加されます。

### その他の考慮事項

-   既定では、この手順を実行するには、承認者または AGPM 管理者 (フルコントロール) である必要があります。 具体的には、ドメインの [**コンテンツの一覧表示**] と [GPO のアクセス許可の**作成**] を設定する必要があります。

### その他の参照情報

-   [GPO の作成、制御、インポート](creating-controlling-or-importing-a-gpo-approver.md)

 

 





