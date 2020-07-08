---
title: GPO を破棄する
description: GPO を破棄する
author: dansimp
ms.assetid: d74941a3-beef-46cd-a4ca-80a324dcfadf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5545918c417fce16bfc2369ebc6fc2199390adc6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818647"
---
# GPO を破棄する


高度なグループポリシー管理 (AGPM) では、承認者がグループポリシーオブジェクト (GPO) を破棄し、ごみ箱から削除し、復元できないように完全に削除することができます。

この手順を完了するには、承認者または AGPM 管理者 (フルコントロール) の役割、または高度なグループポリシーの管理に必要なアクセス許可を持つユーザーアカウントが必要です。 詳細については、このトピックの「その他の考慮事項」を参照してください。

**GPO を復元できなくなるように完全に削除するには**

1.  [**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。

2.  [**コンテンツ**] タブで、[**ごみ箱**] タブをクリックして、削除された gpo を表示します。

3.  破棄する GPO を右クリックし、[**破棄**] をクリックします。

4.  [**はい**] をクリックして、選んだ GPO とアーカイブからすべてのバックアップを完全に削除することを確認します。

5.  **進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。 GPO は [**ごみ箱**] タブから削除され、完全に削除されます。

### その他の考慮事項

-   既定では、この手順を実行するには、承認者または AGPM 管理者 (フルコントロール) である必要があります。 具体的には、GPO の [**コンテンツの一覧表示**] および [ **gpo の削除**] のアクセス許可を持っている必要があります。

### その他の参照情報

-   [GPO の削除、復元、破棄](deleting-restoring-or-destroying-a-gpo.md)

 

 





