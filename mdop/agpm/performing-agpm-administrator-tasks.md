---
title: AGPM 管理者タスクの実行
description: AGPM 管理者タスクの実行
author: dansimp
ms.assetid: 32e694a7-be64-4943-bce2-2a3a15e5341f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0daa8df93a88ed155e9f894011d4dd835761948b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820477"
---
# AGPM 管理者タスクの実行


AGPM 管理者 (フルコントロール) は、承認者、編集者、他の AGPM 管理者に対して、ドメイン全体のオプションと代理アクセス許可を構成します。 既定では、AGPM 管理者はフルコントロール (すべての高度なグループポリシー管理 \ [AGPM \] 権限) を持つ個人であるため、役割に関連付けられたタスクを実行することもできます。

複数のユーザーがグループポリシーオブジェクト (Gpo) を開発している環境では、すべての高度なグループポリシー管理 (AGPM) ユーザーが同じタスクを実行し、同じレベルのアクセス権を持っているかどうか、または、gpo を変更している編集者に対して AGPM 管理者が権限を委任するか、または Gpo を運用環境 AGPM 管理者は、組織のニーズに合わせてアクセス許可を構成できます。

-   [AGPM サーバー接続を構成する](configure-the-agpm-server-connection.md)

-   [電子メール通知を構成する](configure-e-mail-notification.md)

-   [ドメイン レベルのアクセスを委任する](delegate-domain-level-access.md)

-   [個々 の GPO へのアクセスを委任する](delegate-access-to-an-individual-gpo.md)

-   [ログとトレースを構成する](configure-logging-and-tracing.md)

-   [AGPM サービスの管理](managing-the-agpm-service.md)

    -   [AGPM サービスを開始および停止する](start-and-stop-the-agpm-service.md)

    -   [アーカイブのパスを変更する](modify-the-archive-path.md)

    -   [AGPM サービス アカウントを変更する](modify-the-agpm-service-account.md)

    -   [AGPM サービスがリッスンするポートを変更する](modify-the-port-on-which-the-agpm-service-listens.md)

また、AGPM 管理者の役割には他のすべての役割の権限が含まれているため、AGPM 管理者は、他の役割に通常関連付けられているタスクを実行することができます。

-   Gpo の作成、展開、削除など、[承認者のタスクを実行](performing-approver-tasks.md)する

-   編集、名前の変更、ラベル付け、Gpo のインポート、テンプレートの作成、既定のテンプレートの設定などの[エディタータスクを実行](performing-editor-tasks.md)する

-   設定の確認や Gpo の比較など、[校閲者のタスクを実行](performing-reviewer-tasks.md)する

### その他の考慮事項

既定では、AGPM 管理者の役割にはフルコントロールがあります。すべての AGPM 権限は次のとおりです。

-   リストの内容

-   設定の読み取り

-   設定を編集する

-   GPO を作成する

-   GPO の展開

-   GPO を削除する

-   オプションの変更

-   セキュリティを変更する

-   テンプレートを作成する

[**変更] オプション**と [**セキュリティの変更**] のアクセス許可は、AGPM 管理者の役割に対して一意です。

 

 





