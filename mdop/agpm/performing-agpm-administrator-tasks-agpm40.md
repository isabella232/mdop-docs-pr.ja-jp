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
# <span data-ttu-id="20585-103">AGPM 管理者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="20585-103">Performing AGPM Administrator Tasks</span></span>


<span data-ttu-id="20585-104">高度なグループポリシー管理 (AGPM) を使うと、AGPM 管理者 (フルコントロール) によって、ドメイン全体のオプションを構成し、承認者、エディター、レビューアー、AGPM 管理者にアクセス許可を委任することができます。</span><span class="sxs-lookup"><span data-stu-id="20585-104">Advanced Group Policy Management (AGPM) lets an AGPM Administrator (Full Control) configure domain-wide options and delegate permissions to Approvers, Editors, Reviewers, and AGPM Administrators.</span></span> <span data-ttu-id="20585-105">既定では、AGPM 管理者はフルコントロール (すべての AGPM アクセス許可) を持っているユーザーであり、すべての役割に関連付けられているタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="20585-105">By default, an AGPM Administrator is someone who has Full Control— all AGPM permissions—and who therefore can perform tasks associated with any role.</span></span>

<span data-ttu-id="20585-106">複数のユーザーがグループポリシーオブジェクト (Gpo) を開発している環境では、すべてのグループポリシー管理者が同じタスクを実行し、同じレベルのアクセス権を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="20585-106">In an environment in which multiple people develop Group Policy Objects (GPOs), you can choose to let all Group Policy administrators perform the same tasks and have the same level of access.</span></span> <span data-ttu-id="20585-107">または、AGPM 管理者に対して、Gpo を変更できる編集者と、運用環境に Gpo を展開する承認者へのアクセス許可を委任することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="20585-107">Or, you can choose to let AGPM Administrators delegate permissions to Editors who can change GPOs and to Approvers who deploy GPOs to the production environment.</span></span> <span data-ttu-id="20585-108">AGPM 管理者は、組織のニーズに合わせてアクセス許可を構成できます。</span><span class="sxs-lookup"><span data-stu-id="20585-108">AGPM Administrators can configure permissions to meet the needs of your organization.</span></span>

-   <span data-ttu-id="20585-109">[高度なグループポリシー管理を構成する](configuring-advanced-group-policy-management-agpm40.md): AGPM サーバー接続とメール通知の構成、運用環境での gpo へのアクセスの委任、トラブルシューティングのためのログとトレースの構成を行います。</span><span class="sxs-lookup"><span data-stu-id="20585-109">[Configuring Advanced Group Policy Management](configuring-advanced-group-policy-management-agpm40.md): Configure the AGPM Server Connection and e-mail notification, delegate access to GPOs in the production environment, and configure logging and tracing for troubleshooting.</span></span>

-   <span data-ttu-id="20585-110">[アーカイブの管理](managing-the-archive-agpm40.md): アーカイブ内の gpo へのアクセスを委任し、保存されている各 gpo のバージョンの数を制限し、別のドメインから gpo をインポートして、アーカイブをバックアップして復元します。</span><span class="sxs-lookup"><span data-stu-id="20585-110">[Managing the Archive](managing-the-archive-agpm40.md): Delegate access to GPOs in the archive, limit the number of versions of each GPO stored, import a GPO from another domain, and back up and restore the archive.</span></span>

-   <span data-ttu-id="20585-111">[Agpm サービスの管理](managing-the-agpm-service-agpm40.md): agpm サービスを停止して開始します。または、agpm サービスがリッスンするアーカイブパス、Agpm サービスアカウント、またはポートを変更します。</span><span class="sxs-lookup"><span data-stu-id="20585-111">[Managing the AGPM Service](managing-the-agpm-service-agpm40.md): Stop and start the AGPM Service or change the archive path, the AGPM Service Account, or the port on which the AGPM Service listens.</span></span>

-   <span data-ttu-id="20585-112">[Agpm サーバーとアーカイブの移動](move-the-agpm-server-and-the-archive-agpm40.md): agpm サービス、アーカイブ、またはその両方を別のサーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="20585-112">[Move the AGPM Server and the Archive](move-the-agpm-server-and-the-archive-agpm40.md): Move the AGPM Service, the archive, or both to a different server.</span></span>

<span data-ttu-id="20585-113">**注** AGPM 管理者の役割には他のすべての役割の権限が含まれているため、AGPM 管理者は、通常、他の役割に関連付けられているタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="20585-113">**Note** Because the AGPM Administrator role includes the permissions for all other roles, an AGPM Administrator can perform the tasks usually associated with any other role.</span></span>

<span data-ttu-id="20585-114">Gpo の作成、展開、削除など、[承認者のタスクを実行](performing-approver-tasks-agpm40.md)する</span><span class="sxs-lookup"><span data-stu-id="20585-114">[Performing Approver Tasks](performing-approver-tasks-agpm40.md), such as creating, deploying, or deleting GPOs</span></span>

<span data-ttu-id="20585-115">編集、名前の変更、ラベル付け、Gpo のインポート、テンプレートの作成、既定のテンプレートの設定などの[エディタータスクを実行](performing-editor-tasks-agpm40.md)する</span><span class="sxs-lookup"><span data-stu-id="20585-115">[Performing Editor Tasks](performing-editor-tasks-agpm40.md), such as editing, renaming, labeling, or importing GPOs, creating templates, or setting a default template</span></span>

<span data-ttu-id="20585-116">設定の確認や Gpo の比較など、[校閲者のタスクを実行](performing-reviewer-tasks-agpm40.md)する</span><span class="sxs-lookup"><span data-stu-id="20585-116">[Performing Reviewer Tasks](performing-reviewer-tasks-agpm40.md), such as reviewing settings and comparing GPOs</span></span>

 

### <span data-ttu-id="20585-117">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="20585-117">Additional considerations</span></span>

<span data-ttu-id="20585-118">既定では、AGPM 管理者の役割にはフルコントロールがあります。すべての AGPM 権限は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="20585-118">By default, the AGPM Administrator role has Full Control—all AGPM permissions:</span></span>

-   <span data-ttu-id="20585-119">リストの内容</span><span class="sxs-lookup"><span data-stu-id="20585-119">List Contents</span></span>

-   <span data-ttu-id="20585-120">設定の読み取り</span><span class="sxs-lookup"><span data-stu-id="20585-120">Read Settings</span></span>

-   <span data-ttu-id="20585-121">設定を編集する</span><span class="sxs-lookup"><span data-stu-id="20585-121">Edit Settings</span></span>

-   <span data-ttu-id="20585-122">GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="20585-122">Create GPO</span></span>

-   <span data-ttu-id="20585-123">GPO の展開</span><span class="sxs-lookup"><span data-stu-id="20585-123">Deploy GPO</span></span>

-   <span data-ttu-id="20585-124">GPO を削除する</span><span class="sxs-lookup"><span data-stu-id="20585-124">Delete GPO</span></span>

-   <span data-ttu-id="20585-125">GPO をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="20585-125">Export GPO</span></span>

-   <span data-ttu-id="20585-126">GPO をインポートする</span><span class="sxs-lookup"><span data-stu-id="20585-126">Import GPO</span></span>

-   <span data-ttu-id="20585-127">テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="20585-127">Create Template</span></span>

-   <span data-ttu-id="20585-128">オプションの変更</span><span class="sxs-lookup"><span data-stu-id="20585-128">Modify Options</span></span>

-   <span data-ttu-id="20585-129">セキュリティを変更する</span><span class="sxs-lookup"><span data-stu-id="20585-129">Modify Security</span></span>

<span data-ttu-id="20585-130">[**変更] オプション**と [**セキュリティの変更**] のアクセス許可は、AGPM 管理者の役割に対して一意です。</span><span class="sxs-lookup"><span data-stu-id="20585-130">The **Modify Options** and **Modify Security** permissions are unique to the role of AGPM Administrator.</span></span>

 

 





