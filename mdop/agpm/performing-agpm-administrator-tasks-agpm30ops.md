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
# <span data-ttu-id="bc27b-103">AGPM 管理者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="bc27b-103">Performing AGPM Administrator Tasks</span></span>


<span data-ttu-id="bc27b-104">[高度なグループポリシー管理 (AGPM)] では、AGPM 管理者 (フルコントロール) によって、ドメイン全体のオプションが構成され、承認者、編集者、その他の AGPM 管理者に対して権限が付与されます。</span><span class="sxs-lookup"><span data-stu-id="bc27b-104">In Advanced Group Policy Management (AGPM), an AGPM Administrator (Full Control) configures domain-wide options and delegates permissions to Approvers, Editors, Reviewers, and other AGPM Administrators.</span></span> <span data-ttu-id="bc27b-105">既定では、AGPM 管理者は、すべての AGPM アクセス許可を持っている個人であり、すべての役割に関連付けられているタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="bc27b-105">By default, an AGPM Administrator is an individual with Full Control—all AGPM permissions—and who therefore can perform tasks associated with any role.</span></span>

<span data-ttu-id="bc27b-106">複数のユーザーがグループポリシーオブジェクト (Gpo) を開発している環境では、すべての AGPM ユーザーが同じタスクを実行し、同じレベルのアクセスを持つことができるようにするか、または AGPM 管理者が Gpo を変更している編集者に対してアクセス許可を委任するか、または Gpo を運用環境に展開する承認者に</span><span class="sxs-lookup"><span data-stu-id="bc27b-106">In an environment in which multiple people develop Group Policy Objects (GPOs), you can choose whether all AGPM users perform the same tasks and have the same level of access or whether AGPM Administrators delegate permissions to Editors who make changes to GPOs and to Approvers who deploy GPOs to the production environment.</span></span> <span data-ttu-id="bc27b-107">AGPM 管理者は、組織のニーズに合わせてアクセス許可を構成できます。</span><span class="sxs-lookup"><span data-stu-id="bc27b-107">AGPM Administrators can configure permissions to meet the needs of your organization.</span></span>

-   <span data-ttu-id="bc27b-108">[高度なグループポリシー管理を構成する](configuring-advanced-group-policy-management.md): AGPM サーバー接続とメール通知の構成、運用環境での gpo へのアクセスの委任、トラブルシューティングのためのログとトレースの構成を行います。</span><span class="sxs-lookup"><span data-stu-id="bc27b-108">[Configuring Advanced Group Policy Management](configuring-advanced-group-policy-management.md): Configure the AGPM Server Connection and e-mail notification, delegate access to GPOs in the production environment, and configure logging and tracing for troubleshooting.</span></span>

-   <span data-ttu-id="bc27b-109">[アーカイブの管理](managing-the-archive.md): アーカイブ内の gpo へのアクセスを委任し、保存されている各 gpo のバージョンの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="bc27b-109">[Managing the Archive](managing-the-archive.md): Delegate access to GPOs in the archive and limit the number of versions of each GPO stored.</span></span>

-   <span data-ttu-id="bc27b-110">[Agpm サービスの管理](managing-the-agpm-service-agpm30ops.md): agpm サービスを停止して開始します。または、agpm サービスがリッスンするアーカイブパス、Agpm サービスアカウント、またはポートを変更します。</span><span class="sxs-lookup"><span data-stu-id="bc27b-110">[Managing the AGPM Service](managing-the-agpm-service-agpm30ops.md): Stop and start the AGPM Service or change the archive path, the AGPM Service Account, or the port on which the AGPM Service listens.</span></span>

-   <span data-ttu-id="bc27b-111">[Agpm サーバーとアーカイブの移動](move-the-agpm-server-and-the-archive.md): agpm サービス、アーカイブ、またはその両方を別のサーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="bc27b-111">[Move the AGPM Server and the Archive](move-the-agpm-server-and-the-archive.md): Move the AGPM Service, the archive, or both to a different server.</span></span>

<span data-ttu-id="bc27b-112">また、AGPM 管理者の役割には他のすべての役割の権限が含まれているため、AGPM 管理者は、他の役割に通常関連付けられているタスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="bc27b-112">Also, because the AGPM Administrator role includes the permissions for all other roles, an AGPM Administrator can perform the tasks normally associated with any other role.</span></span>

-   <span data-ttu-id="bc27b-113">Gpo の作成、展開、削除など、[承認者のタスクを実行](performing-approver-tasks-agpm30ops.md)する</span><span class="sxs-lookup"><span data-stu-id="bc27b-113">[Performing Approver Tasks](performing-approver-tasks-agpm30ops.md), such as creating, deploying, or deleting GPOs</span></span>

-   <span data-ttu-id="bc27b-114">編集、名前の変更、ラベル付け、Gpo のインポート、テンプレートの作成、既定のテンプレートの設定などの[エディタータスクを実行](performing-editor-tasks-agpm30ops.md)する</span><span class="sxs-lookup"><span data-stu-id="bc27b-114">[Performing Editor Tasks](performing-editor-tasks-agpm30ops.md), such as editing, renaming, labeling, or importing GPOs, creating templates, or setting a default template</span></span>

-   <span data-ttu-id="bc27b-115">設定の確認や Gpo の比較など、[校閲者のタスクを実行](performing-reviewer-tasks-agpm30ops.md)する</span><span class="sxs-lookup"><span data-stu-id="bc27b-115">[Performing Reviewer Tasks](performing-reviewer-tasks-agpm30ops.md), such as reviewing settings and comparing GPOs</span></span>

### <span data-ttu-id="bc27b-116">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="bc27b-116">Additional considerations</span></span>

<span data-ttu-id="bc27b-117">既定では、AGPM 管理者の役割にはフルコントロールがあります。すべての AGPM 権限は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bc27b-117">By default, the AGPM Administrator role has Full Control—all AGPM permissions:</span></span>

-   <span data-ttu-id="bc27b-118">リストの内容</span><span class="sxs-lookup"><span data-stu-id="bc27b-118">List Contents</span></span>

-   <span data-ttu-id="bc27b-119">設定の読み取り</span><span class="sxs-lookup"><span data-stu-id="bc27b-119">Read Settings</span></span>

-   <span data-ttu-id="bc27b-120">設定を編集する</span><span class="sxs-lookup"><span data-stu-id="bc27b-120">Edit Settings</span></span>

-   <span data-ttu-id="bc27b-121">GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="bc27b-121">Create GPO</span></span>

-   <span data-ttu-id="bc27b-122">GPO の展開</span><span class="sxs-lookup"><span data-stu-id="bc27b-122">Deploy GPO</span></span>

-   <span data-ttu-id="bc27b-123">GPO を削除する</span><span class="sxs-lookup"><span data-stu-id="bc27b-123">Delete GPO</span></span>

-   <span data-ttu-id="bc27b-124">オプションの変更</span><span class="sxs-lookup"><span data-stu-id="bc27b-124">Modify Options</span></span>

-   <span data-ttu-id="bc27b-125">セキュリティを変更する</span><span class="sxs-lookup"><span data-stu-id="bc27b-125">Modify Security</span></span>

-   <span data-ttu-id="bc27b-126">テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="bc27b-126">Create Template</span></span>

<span data-ttu-id="bc27b-127">[**変更] オプション**と [**セキュリティの変更**] のアクセス許可は、AGPM 管理者の役割に対して一意です。</span><span class="sxs-lookup"><span data-stu-id="bc27b-127">The **Modify Options** and **Modify Security** permissions are unique to the role of AGPM Administrator.</span></span>

 

 





