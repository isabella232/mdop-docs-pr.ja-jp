---
title: AGPM 管理者タスクの実行
description: AGPM 管理者タスクの実行
author: dansimp
ms.assetid: bc746f39-bdc9-4e2a-bc48-c3c7905de098
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 609b5b8b27fe24ff93e86bea7113929b1e04984d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822417"
---
# AGPM 管理者タスクの実行


高度なグループポリシー管理 (AGPM) を使うと、AGPM 管理者 (フルコントロール) によって、ドメイン全体のオプションを構成し、承認者、エディター、レビューアー、AGPM 管理者にアクセス許可を委任することができます。 既定では、AGPM 管理者はフルコントロール (すべての AGPM アクセス許可) を持っているユーザーであり、すべての役割に関連付けられているタスクを実行できます。

複数のユーザーがグループポリシーオブジェクト (Gpo) を開発している環境では、すべてのグループポリシー管理者が同じタスクを実行し、同じレベルのアクセス権を持つことができます。 または、AGPM 管理者に対して、Gpo を変更できる編集者と、運用環境に Gpo を展開する承認者へのアクセス許可を委任することを選択できます。 AGPM 管理者は、組織のニーズに合わせてアクセス許可を構成できます。

-   [高度なグループポリシー管理を構成する](configuring-advanced-group-policy-management-agpm40.md): AGPM サーバー接続とメール通知の構成、運用環境での gpo へのアクセスの委任、トラブルシューティングのためのログとトレースの構成を行います。

-   [アーカイブの管理](managing-the-archive-agpm40.md): アーカイブ内の gpo へのアクセスを委任し、保存されている各 gpo のバージョンの数を制限し、別のドメインから gpo をインポートして、アーカイブをバックアップして復元します。

-   [Agpm サービスの管理](managing-the-agpm-service-agpm40.md): agpm サービスを停止して開始します。または、agpm サービスがリッスンするアーカイブパス、Agpm サービスアカウント、またはポートを変更します。

-   [Agpm サーバーとアーカイブの移動](move-the-agpm-server-and-the-archive-agpm40.md): agpm サービス、アーカイブ、またはその両方を別のサーバーに移動します。

**注** AGPM 管理者の役割には他のすべての役割の権限が含まれているため、AGPM 管理者は、通常、他の役割に関連付けられているタスクを実行できます。

Gpo の作成、展開、削除など、[承認者のタスクを実行](performing-approver-tasks-agpm40.md)する

編集、名前の変更、ラベル付け、Gpo のインポート、テンプレートの作成、既定のテンプレートの設定などの[エディタータスクを実行](performing-editor-tasks-agpm40.md)する

設定の確認や Gpo の比較など、[校閲者のタスクを実行](performing-reviewer-tasks-agpm40.md)する

 

### その他の考慮事項

既定では、AGPM 管理者の役割にはフルコントロールがあります。すべての AGPM 権限は次のとおりです。

-   リストの内容

-   設定の読み取り

-   設定を編集する

-   GPO を作成する

-   GPO の展開

-   GPO を削除する

-   GPO をエクスポートする

-   GPO をインポートする

-   テンプレートを作成する

-   オプションの変更

-   セキュリティを変更する

[**変更] オプション**と [**セキュリティの変更**] のアクセス許可は、AGPM 管理者の役割に対して一意です。

 

 





