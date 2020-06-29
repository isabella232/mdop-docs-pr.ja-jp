---
title: 高度なグループ ポリシーの管理の概要
description: 高度なグループ ポリシーの管理の概要
author: dansimp
ms.assetid: 2c12f3b4-8472-4c5b-b7f8-1c98a80d6b47
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 94e47075ae865096f9fe7d327cc7b11cb54217d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822487"
---
# <span data-ttu-id="73504-103">高度なグループ ポリシーの管理の概要</span><span class="sxs-lookup"><span data-stu-id="73504-103">Overview of Advanced Group Policy Management</span></span>


<span data-ttu-id="73504-104">高度なグループポリシー管理 (AGPM) を使用して、グループポリシー管理コンソール (GPMC) の機能を拡張し、包括的な変更の制御と、グループポリシーオブジェクト (Gpo) の管理の改善を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="73504-104">You can use Advanced Group Policy Management (AGPM) to extend the capabilities of the Group Policy Management Console (GPMC) to provide comprehensive change control and improved management for Group Policy Objects (GPOs).</span></span>

## <span data-ttu-id="73504-105">グループポリシーオブジェクトの開発と変更の制御</span><span class="sxs-lookup"><span data-stu-id="73504-105">Group Policy object development with change control</span></span>


<span data-ttu-id="73504-106">AGPM を使用すると、グループポリシーの管理者が、展開されたバージョンの GPO に影響を与えずに、オフラインでの表示と変更を行うことができるように、各 GPO のコピーを中央のアーカイブに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="73504-106">With AGPM, you can store a copy of each GPO in a central archive so that Group Policy administrators can view and change it offline without immediately affecting the deployed version of the GPO.</span></span> <span data-ttu-id="73504-107">さらに、AGPM では、必要に応じて以前のバージョンにロールバックできるように、各コントロールされた GPO の各バージョンのコピーがアーカイブに保存されます。</span><span class="sxs-lookup"><span data-stu-id="73504-107">Additionally, AGPM stores a copy of each version of each controlled GPO in the archive so that you can roll back to an earlier version if necessary.</span></span>

<span data-ttu-id="73504-108">"チェックイン" と "チェックアウト" という用語は、ライブラリの場合と同様に使用されます (または、プログラミング開発用の変更制御、バージョン管理、またはソースコントロールを提供するアプリケーションの場合)。</span><span class="sxs-lookup"><span data-stu-id="73504-108">The terms "check in" and "check out" are used just as in a library (or in applications that provide change control, version control, or source control for programming development).</span></span> <span data-ttu-id="73504-109">ライブラリ内のブックを使用するには、ライブラリからチェックアウトします。</span><span class="sxs-lookup"><span data-stu-id="73504-109">To use a book that is in a library, you check it out from the library.</span></span> <span data-ttu-id="73504-110">チェックアウトしている間は、他のユーザーはそのファイルを使用できません。ブックの作成が完了したら、ライブラリにチェックインして、他のユーザーが使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="73504-110">No one else can use it while you have it checked out. When you are finished with the book, you check it back into the library, so others can use it.</span></span>

<span data-ttu-id="73504-111">これらの GPO コントロール機能を使用するには、[グループポリシー管理エディター] で [変更制御] ノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="73504-111">To use these GPO control features, you will click a Change Control node in the Group Policy Management editor.</span></span> <span data-ttu-id="73504-112">変更コントロールノードは、AGPM クライアントがインストールされている場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="73504-112">The Change Control node appears only if you have installed the AGPM Client.</span></span>

<span data-ttu-id="73504-113">AGPM を使って Gpo を開発する場合は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="73504-113">When you develop GPOs by using AGPM:</span></span>

1.  <span data-ttu-id="73504-114">新しい制御された GPO を作成するか、以前に制御されていない GPO を制御します。</span><span class="sxs-lookup"><span data-stu-id="73504-114">Create a new controlled GPO or control a previously uncontrolled GPO.</span></span>

2.  <span data-ttu-id="73504-115">GPO を確認して、自分だけが変更できるようにします。</span><span class="sxs-lookup"><span data-stu-id="73504-115">Check out the GPO, so that you and only you can change it.</span></span>

3.  <span data-ttu-id="73504-116">GPO を編集します。</span><span class="sxs-lookup"><span data-stu-id="73504-116">Edit the GPO.</span></span>

4.  <span data-ttu-id="73504-117">編集された GPO をチェックインして、他のユーザーがそれを変更したり、展開したりできるようにします。</span><span class="sxs-lookup"><span data-stu-id="73504-117">Check in the edited GPO, so that others can change it, or so that it can be deployed.</span></span>

5.  <span data-ttu-id="73504-118">変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="73504-118">Review the changes.</span></span>

6.  <span data-ttu-id="73504-119">GPO を運用環境に展開します。</span><span class="sxs-lookup"><span data-stu-id="73504-119">Deploy the GPO to the production environment.</span></span>

## <span data-ttu-id="73504-120">役割ベースの委任</span><span class="sxs-lookup"><span data-stu-id="73504-120">Role-based delegation</span></span>


<span data-ttu-id="73504-121">AGPM は、アーカイブ内の Gpo へのアクセスを管理するための包括的で使いやすい役割ベースの委任を提供します。</span><span class="sxs-lookup"><span data-stu-id="73504-121">AGPM provides comprehensive, easy-to-use role-based delegation for managing access to GPOs in the archive.</span></span> <span data-ttu-id="73504-122">ドメインレベルのアクセス許可を有効にすると、AGPM 管理者は、他のドメインへのアクセスを提供せずに個々のドメインへのアクセスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="73504-122">Domain-level permissions enable AGPM Administrators to provide access to individual domains without providing access to other domains.</span></span> <span data-ttu-id="73504-123">GPO ベースの委任を使用すると、AGPM 管理者は、ドメイン全体のアクセスを提供せずに特定の Gpo へのアクセスを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="73504-123">GPO-based delegation enables AGPM Administrators to provide access to specific GPOs without providing domain-wide access.</span></span>

<span data-ttu-id="73504-124">AGPM 内には、明確に定義された役割があります。 AGPM 管理者 (フルコントロール)、承認者、編集者、レビューアー。</span><span class="sxs-lookup"><span data-stu-id="73504-124">Within AGPM, there are specifically defined roles: AGPM Administrator (Full Control), Approver, Editor, and Reviewer.</span></span> <span data-ttu-id="73504-125">AGPM 管理者ロールには、他のすべての役割の権限が含まれています。</span><span class="sxs-lookup"><span data-stu-id="73504-125">The AGPM Administrator role includes the permissions for all other roles.</span></span> <span data-ttu-id="73504-126">既定では、承認者のみがドメインの運用環境に Gpo を展開し、経験の少ないエディターによって環境を保護することができます。</span><span class="sxs-lookup"><span data-stu-id="73504-126">By default, only Approvers have the power to deploy GPOs to the production environment of a domain, protecting the environment from mistakes by less experienced Editors.</span></span> <span data-ttu-id="73504-127">また、既定では、すべての役割には校閲者の役割が含まれているため、レポートで GPO の設定を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="73504-127">Also by default, all roles include the Reviewer role and therefore the ability to view GPO settings in reports.</span></span> <span data-ttu-id="73504-128">ただし、AGPM は、組織のニーズに合わせて GPO アクセスをカスタマイズする柔軟性を備えた AGPM 管理者を提供します。</span><span class="sxs-lookup"><span data-stu-id="73504-128">However, AGPM provides an AGPM Administrator with the flexibility to customize GPO access to fit the needs of your organization.</span></span>

## <span data-ttu-id="73504-129">複数のグループポリシー管理者環境での委任</span><span class="sxs-lookup"><span data-stu-id="73504-129">Delegation in a multiple Group Policy administrator environment</span></span>


<span data-ttu-id="73504-130">複数のユーザーが Gpo を変更する環境では、AGPM 管理者は、グループまたは個人として、エディター、承認者、および校閲者にアクセス許可を委任します。</span><span class="sxs-lookup"><span data-stu-id="73504-130">In an environment where multiple people change GPOs, an AGPM Administrator delegates permission to Editors, Approvers, and Reviewers, either as groups or as individuals.</span></span> <span data-ttu-id="73504-131">エディターと承認者向けの一般的な GPO 開発プロセスについては、「[チェックリスト: GPO を作成、編集、展開](checklist-create-edit-and-deploy-a-gpo-agpm40.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73504-131">For a typical GPO development process for an Editor and an Approver, see [Checklist: Create, Edit, and Deploy a GPO](checklist-create-edit-and-deploy-a-gpo-agpm40.md).</span></span>

### <span data-ttu-id="73504-132">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="73504-132">Additional references</span></span>

-   [<span data-ttu-id="73504-133">Advanced Group Policy Management 4.0</span><span class="sxs-lookup"><span data-stu-id="73504-133">Advanced Group Policy Management 4.0</span></span>](advanced-group-policy-management-40.md)

 

 





