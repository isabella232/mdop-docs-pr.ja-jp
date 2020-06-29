---
title: 高度なグループ ポリシーの管理の概要
description: 高度なグループ ポリシーの管理の概要
author: dansimp
ms.assetid: 028de9dd-848b-42bc-a982-65ba5c433772
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 38396de6bd8bdace72d3add1bba09769ae26de32
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822484"
---
# <span data-ttu-id="51baa-103">高度なグループ ポリシーの管理の概要</span><span class="sxs-lookup"><span data-stu-id="51baa-103">Overview of Advanced Group Policy Management</span></span>


<span data-ttu-id="51baa-104">高度なグループポリシー管理 (AGPM) を使用して、グループポリシー管理コンソール (GPMC) の機能を拡張し、包括的な変更の制御と、グループポリシーオブジェクト (Gpo) の管理の強化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="51baa-104">You can use Advanced Group Policy Management (AGPM) to extend the capabilities of the Group Policy Management Console (GPMC), providing comprehensive change control and enhanced management for Group Policy objects (GPOs).</span></span>

## <span data-ttu-id="51baa-105">グループポリシーオブジェクトの開発と変更の制御</span><span class="sxs-lookup"><span data-stu-id="51baa-105">Group Policy object development with change control</span></span>


<span data-ttu-id="51baa-106">AGPM を使用すると、各 GPO のコピーを中央のアーカイブに保存できるため、グループポリシー管理者は、展開されたバージョンの GPO にすぐに影響を与えることなく、オフラインでの表示と変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="51baa-106">With AGPM, you can store a copy of each GPO in a central archive, so Group Policy administrators can view and modify it offline without immediately impacting the deployed version of the GPO.</span></span> <span data-ttu-id="51baa-107">さらに、AGPM によって、各コントロールされた GPO のコピーがアーカイブに保存されるため、必要に応じて以前のバージョンにロールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="51baa-107">Additionally, AGPM stores a copy of each version of each controlled GPO in the archive so that you can roll back to an earlier version if needed.</span></span>

<span data-ttu-id="51baa-108">"チェックイン" と "チェックアウト" は、ライブラリ (またはプログラミング開発のための変更制御、バージョン管理、ソースコード管理を提供するアプリケーション) とほぼ同じように使用されます。</span><span class="sxs-lookup"><span data-stu-id="51baa-108">The terms "check in" and "check out" are used in much the same way as in a library (or in applications that provide change control, version control, or source code control for programming development).</span></span> <span data-ttu-id="51baa-109">ライブラリ内のブックを使用するには、ライブラリからチェックアウトします。</span><span class="sxs-lookup"><span data-stu-id="51baa-109">To use a book that is in a library, you check it out from the library.</span></span> <span data-ttu-id="51baa-110">チェックアウトしている間は、他のユーザーはそのファイルを使用できません。ブックの作成が完了したら、ライブラリにチェックインして、他のユーザーが使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="51baa-110">No one else can use it while you have it checked out. When you are finished with the book, you check it back into the library, so others can use it.</span></span>

<span data-ttu-id="51baa-111">AGPM を使って Gpo を開発する場合:</span><span class="sxs-lookup"><span data-stu-id="51baa-111">When developing GPOs using AGPM:</span></span>

1.  <span data-ttu-id="51baa-112">新しい制御された GPO を作成するか、以前に制御されていない GPO を制御します。</span><span class="sxs-lookup"><span data-stu-id="51baa-112">Create a new controlled GPO or control a previously uncontrolled GPO.</span></span>

2.  <span data-ttu-id="51baa-113">GPO をチェックアウトして、自分だけが変更できるようにします。</span><span class="sxs-lookup"><span data-stu-id="51baa-113">Check out the GPO, so you and only you can modify it.</span></span>

3.  <span data-ttu-id="51baa-114">GPO を編集します。</span><span class="sxs-lookup"><span data-stu-id="51baa-114">Edit the GPO.</span></span>

4.  <span data-ttu-id="51baa-115">編集された GPO をチェックインして、他のユーザーが変更できるようにしたり、展開したりできるようにします。</span><span class="sxs-lookup"><span data-stu-id="51baa-115">Check in the edited GPO, so others can modify it, or so it can be deployed.</span></span>

5.  <span data-ttu-id="51baa-116">変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="51baa-116">Review the changes.</span></span>

6.  <span data-ttu-id="51baa-117">GPO を運用環境に展開します。</span><span class="sxs-lookup"><span data-stu-id="51baa-117">Deploy the GPO to the production environment.</span></span>

## <span data-ttu-id="51baa-118">役割ベースの委任</span><span class="sxs-lookup"><span data-stu-id="51baa-118">Role-based delegation</span></span>


<span data-ttu-id="51baa-119">AGPM には、包括的で使いやすい役割ベースの委任が用意されています。</span><span class="sxs-lookup"><span data-stu-id="51baa-119">AGPM provides comprehensive, easy-to-use role-based delegation.</span></span> <span data-ttu-id="51baa-120">ドメインレベルのアクセス許可を使用すると、AGPM 管理者は、他のドメインへのアクセスを提供せずに個々のドメインへのアクセスを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="51baa-120">Domain-level permissions allow AGPM Administrators to provide access to individual domains without providing access to other domains.</span></span> <span data-ttu-id="51baa-121">GPO ベースの委任を使用すると、AGPM 管理者は特定の Gpo へのアクセスのみを許可することができます。</span><span class="sxs-lookup"><span data-stu-id="51baa-121">GPO-based delegation enables AGPM Administrators to allow access only to specific GPOs.</span></span>

<span data-ttu-id="51baa-122">AGPM 内には、明確に定義された役割があります。 AGPM 管理者 (フルコントロール)、承認者、編集者、レビューアー。</span><span class="sxs-lookup"><span data-stu-id="51baa-122">Within AGPM, there are specifically defined roles: AGPM Administrator (Full Control), Approver, Editor, and Reviewer.</span></span> <span data-ttu-id="51baa-123">AGPM 管理者ロールには、他のすべての役割の権限が含まれています。</span><span class="sxs-lookup"><span data-stu-id="51baa-123">The AGPM Administrator role includes the permissions for all other roles.</span></span> <span data-ttu-id="51baa-124">既定では、承認者のみが運用環境に Gpo を展開し、経験の少ないエディターによる不注意によるミスから環境を保護します。</span><span class="sxs-lookup"><span data-stu-id="51baa-124">By default, only Approvers have the power to deploy GPOs to the production environment, protecting the environment from inadvertent mistakes by less experienced Editors.</span></span> <span data-ttu-id="51baa-125">また、既定では、すべての役割には校閲者の役割が含まれているため、レポートで GPO の設定を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="51baa-125">Also by default, all roles include the Reviewer role and therefore the ability to view GPO settings in reports.</span></span> <span data-ttu-id="51baa-126">ただし、AGPM は、組織のニーズに合わせて GPO アクセスをカスタマイズする柔軟性を備えた AGPM 管理者を提供します。</span><span class="sxs-lookup"><span data-stu-id="51baa-126">However, AGPM provides an AGPM Administrator with the flexibility to customize GPO access to fit the needs of your organization.</span></span>

## <span data-ttu-id="51baa-127">複数のグループポリシー管理者環境での委任</span><span class="sxs-lookup"><span data-stu-id="51baa-127">Delegation in a multiple Group Policy administrator environment</span></span>


<span data-ttu-id="51baa-128">複数のユーザーが Gpo に変更を加えている環境では、AGPM 管理者は、グループまたは個人として、エディター、承認者、および校閲者にアクセス許可を委任します。</span><span class="sxs-lookup"><span data-stu-id="51baa-128">In an environment where multiple people make changes to GPOs, an AGPM Administrator delegates permission to Editors, Approvers, and Reviewers, either as groups or as individuals.</span></span> <span data-ttu-id="51baa-129">エディターと承認者向けの一般的な GPO 開発プロセスについては、「[チェックリスト: GPO を作成、編集、展開](checklist-create-edit-and-deploy-a-gpo.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51baa-129">For a typical GPO development process for an Editor and an Approver, see [Checklist: Create, Edit, and Deploy a GPO](checklist-create-edit-and-deploy-a-gpo.md).</span></span>

### <span data-ttu-id="51baa-130">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="51baa-130">Additional references</span></span>

-   [<span data-ttu-id="51baa-131">チェックリスト: GPO の作成、編集、展開</span><span class="sxs-lookup"><span data-stu-id="51baa-131">Checklist: Create, Edit, and Deploy a GPO</span></span>](checklist-create-edit-and-deploy-a-gpo.md)

-   [<span data-ttu-id="51baa-132">AGPM 管理者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="51baa-132">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

-   [<span data-ttu-id="51baa-133">編集者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="51baa-133">Performing Editor Tasks</span></span>](performing-editor-tasks.md)

-   [<span data-ttu-id="51baa-134">承認者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="51baa-134">Performing Approver Tasks</span></span>](performing-approver-tasks.md)

-   [<span data-ttu-id="51baa-135">レビュー担当者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="51baa-135">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks.md)

-   [<span data-ttu-id="51baa-136">高度なグループ ポリシーの管理のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="51baa-136">Troubleshooting Advanced Group Policy Management</span></span>](troubleshooting-advanced-group-policy-management.md)

-   [<span data-ttu-id="51baa-137">ユーザー インターフェイス: 高度なグループ ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="51baa-137">User Interface: Advanced Group Policy Management</span></span>](user-interface-advanced-group-policy-management.md)

 

 





