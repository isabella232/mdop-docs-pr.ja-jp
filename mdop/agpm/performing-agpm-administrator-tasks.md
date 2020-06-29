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
# <span data-ttu-id="ca33e-103">AGPM 管理者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="ca33e-103">Performing AGPM Administrator Tasks</span></span>


<span data-ttu-id="ca33e-104">AGPM 管理者 (フルコントロール) は、承認者、編集者、他の AGPM 管理者に対して、ドメイン全体のオプションと代理アクセス許可を構成します。</span><span class="sxs-lookup"><span data-stu-id="ca33e-104">An AGPM Administrator (Full Control) configures domain-wide options and delegates permissions to Approvers, Editors, Reviewers, and other AGPM Administrators.</span></span> <span data-ttu-id="ca33e-105">既定では、AGPM 管理者はフルコントロール (すべての高度なグループポリシー管理 \ [AGPM \] 権限) を持つ個人であるため、役割に関連付けられたタスクを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="ca33e-105">By default, an AGPM Administrator is an individual with Full Control (all Advanced Group Policy Management \[AGPM\] permissions) and therefore can also perform tasks associated with any role.</span></span>

<span data-ttu-id="ca33e-106">複数のユーザーがグループポリシーオブジェクト (Gpo) を開発している環境では、すべての高度なグループポリシー管理 (AGPM) ユーザーが同じタスクを実行し、同じレベルのアクセス権を持っているかどうか、または、gpo を変更している編集者に対して AGPM 管理者が権限を委任するか、または Gpo を運用環境</span><span class="sxs-lookup"><span data-stu-id="ca33e-106">In an environment in which multiple people develop Group Policy objects (GPOs), you can choose whether all Advanced Group Policy Management (AGPM) users perform the same tasks and have the same level of access or whether AGPM Administrators delegate permissions to Editors who make changes to GPOs and to Approvers who deploy GPOs to the production environment.</span></span> <span data-ttu-id="ca33e-107">AGPM 管理者は、組織のニーズに合わせてアクセス許可を構成できます。</span><span class="sxs-lookup"><span data-stu-id="ca33e-107">AGPM Administrators can configure permissions to meet the needs of your organization.</span></span>

-   [<span data-ttu-id="ca33e-108">AGPM サーバー接続を構成する</span><span class="sxs-lookup"><span data-stu-id="ca33e-108">Configure the AGPM Server Connection</span></span>](configure-the-agpm-server-connection.md)

-   [<span data-ttu-id="ca33e-109">電子メール通知を構成する</span><span class="sxs-lookup"><span data-stu-id="ca33e-109">Configure E-Mail Notification</span></span>](configure-e-mail-notification.md)

-   [<span data-ttu-id="ca33e-110">ドメイン レベルのアクセスを委任する</span><span class="sxs-lookup"><span data-stu-id="ca33e-110">Delegate Domain-Level Access</span></span>](delegate-domain-level-access.md)

-   [<span data-ttu-id="ca33e-111">個々 の GPO へのアクセスを委任する</span><span class="sxs-lookup"><span data-stu-id="ca33e-111">Delegate Access to an Individual GPO</span></span>](delegate-access-to-an-individual-gpo.md)

-   [<span data-ttu-id="ca33e-112">ログとトレースを構成する</span><span class="sxs-lookup"><span data-stu-id="ca33e-112">Configure Logging and Tracing</span></span>](configure-logging-and-tracing.md)

-   [<span data-ttu-id="ca33e-113">AGPM サービスの管理</span><span class="sxs-lookup"><span data-stu-id="ca33e-113">Managing the AGPM Service</span></span>](managing-the-agpm-service.md)

    -   [<span data-ttu-id="ca33e-114">AGPM サービスを開始および停止する</span><span class="sxs-lookup"><span data-stu-id="ca33e-114">Start and Stop the AGPM Service</span></span>](start-and-stop-the-agpm-service.md)

    -   [<span data-ttu-id="ca33e-115">アーカイブのパスを変更する</span><span class="sxs-lookup"><span data-stu-id="ca33e-115">Modify the Archive Path</span></span>](modify-the-archive-path.md)

    -   [<span data-ttu-id="ca33e-116">AGPM サービス アカウントを変更する</span><span class="sxs-lookup"><span data-stu-id="ca33e-116">Modify the AGPM Service Account</span></span>](modify-the-agpm-service-account.md)

    -   [<span data-ttu-id="ca33e-117">AGPM サービスがリッスンするポートを変更する</span><span class="sxs-lookup"><span data-stu-id="ca33e-117">Modify the Port on Which the AGPM Service Listens</span></span>](modify-the-port-on-which-the-agpm-service-listens.md)

<span data-ttu-id="ca33e-118">また、AGPM 管理者の役割には他のすべての役割の権限が含まれているため、AGPM 管理者は、他の役割に通常関連付けられているタスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="ca33e-118">Also, because the AGPM Administrator role includes the permissions for all other roles, an AGPM Administrator can perform the tasks normally associated with any other role.</span></span>

-   <span data-ttu-id="ca33e-119">Gpo の作成、展開、削除など、[承認者のタスクを実行](performing-approver-tasks.md)する</span><span class="sxs-lookup"><span data-stu-id="ca33e-119">[Performing Approver Tasks](performing-approver-tasks.md), such as creating, deploying, or deleting GPOs</span></span>

-   <span data-ttu-id="ca33e-120">編集、名前の変更、ラベル付け、Gpo のインポート、テンプレートの作成、既定のテンプレートの設定などの[エディタータスクを実行](performing-editor-tasks.md)する</span><span class="sxs-lookup"><span data-stu-id="ca33e-120">[Performing Editor Tasks](performing-editor-tasks.md), such as editing, renaming, labeling, or importing GPOs, creating templates, or setting a default template</span></span>

-   <span data-ttu-id="ca33e-121">設定の確認や Gpo の比較など、[校閲者のタスクを実行](performing-reviewer-tasks.md)する</span><span class="sxs-lookup"><span data-stu-id="ca33e-121">[Performing Reviewer Tasks](performing-reviewer-tasks.md), such as reviewing settings and comparing GPOs</span></span>

### <span data-ttu-id="ca33e-122">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="ca33e-122">Additional considerations</span></span>

<span data-ttu-id="ca33e-123">既定では、AGPM 管理者の役割にはフルコントロールがあります。すべての AGPM 権限は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ca33e-123">By default, the AGPM Administrator role has Full Control—all AGPM permissions:</span></span>

-   <span data-ttu-id="ca33e-124">リストの内容</span><span class="sxs-lookup"><span data-stu-id="ca33e-124">List Contents</span></span>

-   <span data-ttu-id="ca33e-125">設定の読み取り</span><span class="sxs-lookup"><span data-stu-id="ca33e-125">Read Settings</span></span>

-   <span data-ttu-id="ca33e-126">設定を編集する</span><span class="sxs-lookup"><span data-stu-id="ca33e-126">Edit Settings</span></span>

-   <span data-ttu-id="ca33e-127">GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="ca33e-127">Create GPO</span></span>

-   <span data-ttu-id="ca33e-128">GPO の展開</span><span class="sxs-lookup"><span data-stu-id="ca33e-128">Deploy GPO</span></span>

-   <span data-ttu-id="ca33e-129">GPO を削除する</span><span class="sxs-lookup"><span data-stu-id="ca33e-129">Delete GPO</span></span>

-   <span data-ttu-id="ca33e-130">オプションの変更</span><span class="sxs-lookup"><span data-stu-id="ca33e-130">Modify Options</span></span>

-   <span data-ttu-id="ca33e-131">セキュリティを変更する</span><span class="sxs-lookup"><span data-stu-id="ca33e-131">Modify Security</span></span>

-   <span data-ttu-id="ca33e-132">テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="ca33e-132">Create Template</span></span>

<span data-ttu-id="ca33e-133">[**変更] オプション**と [**セキュリティの変更**] のアクセス許可は、AGPM 管理者の役割に対して一意です。</span><span class="sxs-lookup"><span data-stu-id="ca33e-133">The **Modify Options** and **Modify Security** permissions are unique to the role of AGPM Administrator.</span></span>

 

 





