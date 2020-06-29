---
title: 編集者タスクの実行
description: 編集者タスクの実行
author: dansimp
ms.assetid: 81976a01-2a95-4256-b703-9fb3c884ef34
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b8e23bb91d8762d19eed9ae817967ba5a57505a9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820407"
---
# 編集者タスクの実行


[高度なグループポリシー管理 (AGPM)] のエディターは、AGPM 管理者 (フルコントロール) によって承認されたユーザーで、グループポリシーオブジェクト (Gpo) を変更したり、GPO テンプレートを作成したりします。 さらに、編集者は、GPO の作成、削除、復元を要求することができます。 承認者は、実装の要求を承認する必要があります。 エディターでは、GPO をファイルにエクスポートして、別のフォレストのドメインにコピーできるようにしたり、別のドメインからコピーした GPO をインポートしたりすることができます。

**重要** Gpo の中央アーカイブに接続していることを確認します。 詳細については、「 [AGPM サーバー接続を構成](configure-an-agpm-server-connection-agpm40.md)する」を参照してください。

 

-   [GPO の作成または制御](creating-or-controlling-a-gpo-agpm40-ed.md)

-   [GPO の編集](editing-a-gpo-agpm40.md)

-   [テスト環境の使用](using-a-test-environment.md)

-   [GPO の展開を要求する](request-deployment-of-a-gpo-agpm40.md)

-   [テンプレートの作成と既定のテンプレートの設定](creating-a-template-and-setting-a-default-template-agpm40.md)

-   [GPO の削除または復元](deleting-or-restoring-a-gpo-agpm40.md)

**注** 編集者ロールにはレビュー担当者ロールの権限が含まれているため、編集者は設定を確認して Gpo を比較することもできます。 詳細については、「[校閲者タスクを実行](performing-reviewer-tasks-agpm40.md)する」を参照してください。

 

### その他の考慮事項

既定では、編集者の役割に対して次の権限が提供されます。

-   リストの内容

-   設定の読み取り

-   設定を編集する

-   GPO をエクスポートする

-   GPO をインポートする

-   テンプレートを作成する

 

 





