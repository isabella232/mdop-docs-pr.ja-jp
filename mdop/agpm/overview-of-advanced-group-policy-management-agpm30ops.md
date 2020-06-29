---
title: 高度なグループ ポリシーの管理の概要
description: 高度なグループ ポリシーの管理の概要
author: dansimp
ms.assetid: 3a8d1e58-12b9-42bd-898f-6d57514dfbb9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: feb43972c78ed12501e372800c1f5ec19609477a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822494"
---
# <span data-ttu-id="0b64e-103">高度なグループ ポリシーの管理の概要</span><span class="sxs-lookup"><span data-stu-id="0b64e-103">Overview of Advanced Group Policy Management</span></span>


<span data-ttu-id="0b64e-104">高度なグループポリシー管理 (AGPM) を使用して、グループポリシー管理コンソール (GPMC) の機能を拡張し、包括的な変更の制御と、グループポリシーオブジェクト (Gpo) の管理の改善を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0b64e-104">You can use Advanced Group Policy Management (AGPM) to extend the capabilities of the Group Policy Management Console (GPMC) to provide comprehensive change control and improved management for Group Policy Objects (GPOs).</span></span>

## <span data-ttu-id="0b64e-105">グループポリシーオブジェクトの開発と変更の制御</span><span class="sxs-lookup"><span data-stu-id="0b64e-105">Group Policy object development with change control</span></span>


<span data-ttu-id="0b64e-106">AGPM を使用すると、グループポリシーの管理者が、展開されたバージョンの GPO に影響を与えずに、オフラインでの表示と変更を行うことができるように、各 GPO のコピーを中央のアーカイブに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="0b64e-106">With AGPM, you can store a copy of each GPO in a central archive so that Group Policy administrators can view and change it offline without immediately affecting the deployed version of the GPO.</span></span> <span data-ttu-id="0b64e-107">さらに、AGPM では、必要に応じて以前のバージョンにロールバックできるように、各コントロールされた GPO の各バージョンのコピーがアーカイブに保存されます。</span><span class="sxs-lookup"><span data-stu-id="0b64e-107">Additionally, AGPM stores a copy of each version of each controlled GPO in the archive so that you can roll back to an earlier version if necessary.</span></span>

<span data-ttu-id="0b64e-108">"チェックイン" と "チェックアウト" という用語は、ライブラリの場合と同様に使用されます (または、プログラミング開発用の変更制御、バージョン管理、またはソースコントロールを提供するアプリケーションの場合)。</span><span class="sxs-lookup"><span data-stu-id="0b64e-108">The terms "check in" and "check out" are used just as in a library (or in applications that provide change control, version control, or source control for programming development).</span></span> <span data-ttu-id="0b64e-109">ライブラリ内のブックを使用するには、ライブラリからチェックアウトします。</span><span class="sxs-lookup"><span data-stu-id="0b64e-109">To use a book that is in a library, you check it out from the library.</span></span> <span data-ttu-id="0b64e-110">チェックアウトしている間は、他のユーザーはそのファイルを使用できません。ブックの作成が完了したら、ライブラリにチェックインして、他のユーザーが使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0b64e-110">No one else can use it while you have it checked out. When you are finished with the book, you check it back into the library, so others can use it.</span></span>

<span data-ttu-id="0b64e-111">AGPM を使って Gpo を開発する場合は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="0b64e-111">When you develop GPOs by using AGPM:</span></span>

1.  <span data-ttu-id="0b64e-112">新しい制御された GPO を作成するか、以前に制御されていない GPO を制御します。</span><span class="sxs-lookup"><span data-stu-id="0b64e-112">Create a new controlled GPO or control a previously uncontrolled GPO.</span></span>

2.  <span data-ttu-id="0b64e-113">GPO を確認して、自分だけが変更できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0b64e-113">Check out the GPO, so that you and only you can change it.</span></span>

3.  <span data-ttu-id="0b64e-114">GPO を編集します。</span><span class="sxs-lookup"><span data-stu-id="0b64e-114">Edit the GPO.</span></span>

4.  <span data-ttu-id="0b64e-115">編集された GPO をチェックインして、他のユーザーがそれを変更したり、展開したりできるようにします。</span><span class="sxs-lookup"><span data-stu-id="0b64e-115">Check in the edited GPO, so that others can change it, or so that it can be deployed.</span></span>

5.  <span data-ttu-id="0b64e-116">変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="0b64e-116">Review the changes.</span></span>

6.  <span data-ttu-id="0b64e-117">GPO を運用環境に展開します。</span><span class="sxs-lookup"><span data-stu-id="0b64e-117">Deploy the GPO to the production environment.</span></span>

## <span data-ttu-id="0b64e-118">役割ベースの委任</span><span class="sxs-lookup"><span data-stu-id="0b64e-118">Role-based delegation</span></span>


<span data-ttu-id="0b64e-119">AGPM は、アーカイブ内の Gpo へのアクセスを管理するための包括的で使いやすい役割ベースの委任を提供します。</span><span class="sxs-lookup"><span data-stu-id="0b64e-119">AGPM provides comprehensive, easy-to-use role-based delegation for managing access to GPOs in the archive.</span></span> <span data-ttu-id="0b64e-120">ドメインレベルのアクセス許可を有効にすると、AGPM 管理者は、他のドメインへのアクセスを提供せずに個々のドメインへのアクセスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="0b64e-120">Domain-level permissions enable AGPM Administrators to provide access to individual domains without providing access to other domains.</span></span> <span data-ttu-id="0b64e-121">GPO ベースの委任を使用すると、AGPM 管理者は、ドメイン全体のアクセスを提供せずに特定の Gpo へのアクセスを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="0b64e-121">GPO-based delegation enables AGPM Administrators to provide access to specific GPOs without providing domain-wide access.</span></span>

<span data-ttu-id="0b64e-122">AGPM 内には、明確に定義された役割があります。 AGPM 管理者 (フルコントロール)、承認者、編集者、レビューアー。</span><span class="sxs-lookup"><span data-stu-id="0b64e-122">Within AGPM, there are specifically defined roles: AGPM Administrator (Full Control), Approver, Editor, and Reviewer.</span></span> <span data-ttu-id="0b64e-123">AGPM 管理者ロールには、他のすべての役割の権限が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0b64e-123">The AGPM Administrator role includes the permissions for all other roles.</span></span> <span data-ttu-id="0b64e-124">既定では、承認者のみが運用環境に Gpo を展開して、経験の少ないエディターで間違いから環境を保護することができます。</span><span class="sxs-lookup"><span data-stu-id="0b64e-124">By default, only Approvers have the power to deploy GPOs to the production environment, protecting the environment from mistakes by less experienced Editors.</span></span> <span data-ttu-id="0b64e-125">また、既定では、すべての役割には校閲者の役割が含まれているため、レポートで GPO の設定を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="0b64e-125">Also by default, all roles include the Reviewer role and therefore the ability to view GPO settings in reports.</span></span> <span data-ttu-id="0b64e-126">ただし、AGPM は、組織のニーズに合わせて GPO アクセスをカスタマイズする柔軟性を備えた AGPM 管理者を提供します。</span><span class="sxs-lookup"><span data-stu-id="0b64e-126">However, AGPM provides an AGPM Administrator with the flexibility to customize GPO access to fit the needs of your organization.</span></span>

## <span data-ttu-id="0b64e-127">複数のグループポリシー管理者環境での委任</span><span class="sxs-lookup"><span data-stu-id="0b64e-127">Delegation in a multiple Group Policy administrator environment</span></span>


<span data-ttu-id="0b64e-128">複数のユーザーが Gpo を変更する環境では、AGPM 管理者は、グループまたは個人として、エディター、承認者、および校閲者にアクセス許可を委任します。</span><span class="sxs-lookup"><span data-stu-id="0b64e-128">In an environment where multiple people change GPOs, an AGPM Administrator delegates permission to Editors, Approvers, and Reviewers, either as groups or as individuals.</span></span> <span data-ttu-id="0b64e-129">エディターと承認者向けの一般的な GPO 開発プロセスについては、「[チェックリスト: GPO を作成、編集、展開](checklist-create-edit-and-deploy-a-gpo-agpm30ops.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b64e-129">For a typical GPO development process for an Editor and an Approver, see [Checklist: Create, Edit, and Deploy a GPO](checklist-create-edit-and-deploy-a-gpo-agpm30ops.md).</span></span>

### <span data-ttu-id="0b64e-130">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="0b64e-130">Additional references</span></span>

-   [<span data-ttu-id="0b64e-131">Microsoft Advanced Group Policy Management 3.0 運用ガイド</span><span class="sxs-lookup"><span data-stu-id="0b64e-131">Operations Guide for Microsoft Advanced Group Policy Management 3.0</span></span>](operations-guide-for-microsoft-advanced-group-policy-management-30-agpm30ops.md)

 

 





