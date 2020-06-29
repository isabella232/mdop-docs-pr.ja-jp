---
title: AGPM 管理者タスクの実行
description: AGPM 管理者タスクの実行
author: dansimp
ms.assetid: 9678b0f4-70a5-411e-a896-afa4dc9ea6c4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 26b412e5b22e46af938d127751fdca1da722a8c6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822424"
---
# AGPM 管理者タスクの実行


[高度なグループポリシー管理 (AGPM)] では、AGPM 管理者 (フルコントロール) によって、ドメイン全体のオプションが構成され、承認者、編集者、その他の AGPM 管理者に対して権限が付与されます。 既定では、AGPM 管理者は、すべての AGPM アクセス許可を持っている個人であり、すべての役割に関連付けられているタスクを実行できます。

複数のユーザーがグループポリシーオブジェクト (Gpo) を開発している環境では、すべての AGPM ユーザーが同じタスクを実行し、同じレベルのアクセスを持つことができるようにするか、または AGPM 管理者が Gpo を変更している編集者に対してアクセス許可を委任するか、または Gpo を運用環境に展開する承認者に AGPM 管理者は、組織のニーズに合わせてアクセス許可を構成できます。

-   [高度なグループポリシー管理を構成する](configuring-advanced-group-policy-management.md): AGPM サーバー接続とメール通知の構成、運用環境での gpo へのアクセスの委任、トラブルシューティングのためのログとトレースの構成を行います。

-   [アーカイブの管理](managing-the-archive.md): アーカイブ内の gpo へのアクセスを委任し、保存されている各 gpo のバージョンの数を制限します。

-   [Agpm サービスの管理](managing-the-agpm-service-agpm30ops.md): agpm サービスを停止して開始します。または、agpm サービスがリッスンするアーカイブパス、Agpm サービスアカウント、またはポートを変更します。

-   [Agpm サーバーとアーカイブの移動](move-the-agpm-server-and-the-archive.md): agpm サービス、アーカイブ、またはその両方を別のサーバーに移動します。

また、AGPM 管理者の役割には他のすべての役割の権限が含まれているため、AGPM 管理者は、他の役割に通常関連付けられているタスクを実行することができます。

-   Gpo の作成、展開、削除など、[承認者のタスクを実行](performing-approver-tasks-agpm30ops.md)する

-   編集、名前の変更、ラベル付け、Gpo のインポート、テンプレートの作成、既定のテンプレートの設定などの[エディタータスクを実行](performing-editor-tasks-agpm30ops.md)する

-   設定の確認や Gpo の比較など、[校閲者のタスクを実行](performing-reviewer-tasks-agpm30ops.md)する

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

 

 





