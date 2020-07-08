---
title: AGPM サーバー接続を構成する
description: AGPM サーバー接続を構成する
author: dansimp
ms.assetid: 74e8f348-a8ed-4d69-a8e0-9c974aaeca2d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 83a2437ee8c2fe562141ff167cb85c6a06b7cefe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818917"
---
# AGPM サーバー接続を構成する


正しい中央のアーカイブに接続されていることを確認するには、AGPM サーバー接続の構成を確認します。 AGPM 管理者 (フルコントロール) で AGPM サーバー接続が構成されていない場合は、手動で構成する必要があります。

**AGPM サーバーを選ぶには**

1.  [**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。

2.  詳細ウィンドウで、[ **AGPM サーバー** ] タブをクリックします。

    -   **Agpm サーバー**タブのオプションが使用できない場合は、Agpm 管理者によって一元的に構成されています。

    -   [ **Agpm サーバー** ] タブのオプションが使用可能な場合は、agpm サーバーの完全修飾コンピューター名 (server.contoso.com など) と、agpm サービスがリッスンするポート (既定では、ポート 4600) を入力します。 [**適用**] をクリックし、[**はい**] をクリックして確認します。

### その他の考慮事項

-   選択された AGPM サーバーによって、[**コンテンツ**] タブに表示される gpo と、[**ドメイン委任**] タブの設定が適用される場所が決まります。 管理用テンプレートで一元管理されていない場合は、各グループポリシー管理者がこの設定を構成して、ドメインの AGPM サーバーを指すようにする必要があります。

### その他の参照情報

-   [編集者タスクの実行](performing-editor-tasks.md)

-   [承認者タスクの実行](performing-approver-tasks.md)

-   [レビュー担当者タスクの実行](performing-reviewer-tasks.md)

 

 





