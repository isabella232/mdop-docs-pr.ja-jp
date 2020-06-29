---
title: 承認者タスクの実行
description: 承認者タスクの実行
author: dansimp
ms.assetid: e0a4b7fe-ce69-4755-9104-c7f523ea6b62
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2a0815bdd6c34a7a23b27075b3b5367757c1f84e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820467"
---
# 承認者タスクの実行


承認者は、AGPM 管理者 (フルコントロール) によって承認されたユーザーであり、グループポリシーオブジェクト (Gpo) を作成、展開、削除したり、要求を承認または拒否 (通常は編集者) して、Gpo の作成、展開、削除を行います。

**重要** Gpo の中央アーカイブに接続していることを確認します。 詳細については、「 [AGPM サーバー接続を構成](configure-an-agpm-server-connection-agpm40.md)する」を参照してください。

 

-   [保留中のアクションを承認または拒否する](approve-or-reject-a-pending-action-agpm40.md)

-   [GPO の作成または制御](creating-or-controlling-a-gpo-agpm40-app.md)

-   [GPO をチェックインする](check-in-a-gpo-agpm40.md)

-   [GPO を展開する](deploy-a-gpo-agpm40.md)

-   [GPO の以前のバージョンにロールバックする](roll-back-to-an-earlier-version-of-a-gpo-agpm40.md)

-   [GPO の削除、復元、破棄](deleting-restoring-or-destroying-a-gpo-agpm40.md)

**注** 承認前に、GPO に含まれているポリシー設定を確認する必要があります。 承認者ロールには、レビュー担当者ロールの権限が含まれているので、承認者はポリシー設定を確認して Gpo を比較することができます。 詳細については、「[校閲者タスクを実行](performing-reviewer-tasks-agpm40.md)する」を参照してください。

 

### その他の考慮事項

既定では、承認者の役割に対して次の権限が提供されます。

-   リストの内容

-   設定の読み取り

-   GPO を作成する

-   GPO の展開

-   GPO を削除する

また、承認者は、作成または管理された Gpo を完全に制御できます。

 

 





