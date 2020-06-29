---
title: Advanced Group Policy Management 4.0
description: Advanced Group Policy Management 4.0
author: dansimp
ms.assetid: 9873a1f7-97fc-4546-9538-b4c0308529c0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 66dea6141430ee107ab85312b772d3c5ff3c5e02
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812603"
---
# <span data-ttu-id="7ec7d-103">Advanced Group Policy Management 4.0</span><span class="sxs-lookup"><span data-stu-id="7ec7d-103">Advanced Group Policy Management 4.0</span></span>


<span data-ttu-id="7ec7d-104">Microsoft Advanced グループポリシー管理 (AGPM) を使用して、グループポリシー管理コンソール (GPMC) の機能を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="7ec7d-104">You can use Microsoft Advanced Group Policy Management (AGPM) to extend the capabilities of the Group Policy Management Console (GPMC).</span></span> <span data-ttu-id="7ec7d-105">AGPM は、グループポリシーオブジェクト (Gpo) の包括的な変更管理と改善された管理を提供します。</span><span class="sxs-lookup"><span data-stu-id="7ec7d-105">AGPM provides comprehensive change control and improved management of Group Policy Objects (GPOs).</span></span>

<span data-ttu-id="7ec7d-106">AGPM を使うと、次の作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7ec7d-106">Using AGPM, you can do these tasks:</span></span>

-   <span data-ttu-id="7ec7d-107">実稼働環境に展開する前に、Gpo のオフライン編集を実行して、それらを作成してテストできるようにします。</span><span class="sxs-lookup"><span data-stu-id="7ec7d-107">Perform offline editing of GPOs so that you can create and test them before you deploy them to a production environment.</span></span>

-   <span data-ttu-id="7ec7d-108">問題が発生した場合にロールバックできるように、複数のバージョンの GPO を中央のアーカイブで管理します。</span><span class="sxs-lookup"><span data-stu-id="7ec7d-108">Maintain multiple versions of a GPO in a central archive so that you can roll back if a problem occurs.</span></span>

-   <span data-ttu-id="7ec7d-109">ロールベースの委任を使用して、Gpo の編集、承認、確認の責任を複数のユーザー間で共有します。</span><span class="sxs-lookup"><span data-stu-id="7ec7d-109">Share the responsibility for editing, approving, and reviewing GPOs among multiple people by using role-based delegation.</span></span>

-   <span data-ttu-id="7ec7d-110">Gpo のチェックイン機能とチェックアウト機能を使用して、複数のグループポリシー管理者が1つの別の作業を上書きする危険性を排除します。</span><span class="sxs-lookup"><span data-stu-id="7ec7d-110">Eliminate the danger of multiple Group Policy administrators overwriting one another's work by using the check-in and check-out capability for GPOs.</span></span>

-   <span data-ttu-id="7ec7d-111">異なる gpo への変更を分析し、別の GPO または同じ GPO の別のバージョンと比較するには、差分レポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="7ec7d-111">Analyze changes to a GPO, comparing it to another GPO or another version of the same GPO by using difference reporting.</span></span>

-   <span data-ttu-id="7ec7d-112">新しい gpo の開始点として使用する、共通のポリシー設定と基本設定を保存する GPO テンプレートを使用して、新しい Gpo の作成を簡素化します。</span><span class="sxs-lookup"><span data-stu-id="7ec7d-112">Simplify creating new GPOs by using GPO templates, storing common policy settings and preference settings to use as starting points for new GPOs.</span></span>

-   <span data-ttu-id="7ec7d-113">運用環境へのアクセスを委任します。</span><span class="sxs-lookup"><span data-stu-id="7ec7d-113">Delegate access to the production environment.</span></span>

-   <span data-ttu-id="7ec7d-114">特定の属性を持つ Gpo を検索し、表示される Gpo の一覧をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="7ec7d-114">Search for GPOs with specific attributes and filter the list of GPOs displayed.</span></span>

-   <span data-ttu-id="7ec7d-115">テストフォレストのドメインから実稼働フォレストのドメインに GPO をコピーできるように、GPO をファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="7ec7d-115">Export a GPO to a file so that you can copy it from a domain in a test forest to a domain in a production forest.</span></span>

<span data-ttu-id="7ec7d-116">AGPM は、gpmc に表示される各ドメインの下に**変更コントロール**フォルダーを追加します。また、gpmc に表示される各 GPO とグループポリシーリンクの [**履歴**] タブも追加します。</span><span class="sxs-lookup"><span data-stu-id="7ec7d-116">AGPM adds a **Change Control** folder under each domain displayed in the GPMC, in addition to a **History** tab for each GPO and Group Policy link displayed in the GPMC.</span></span>

-   [<span data-ttu-id="7ec7d-117">高度なグループ ポリシーの管理の概要</span><span class="sxs-lookup"><span data-stu-id="7ec7d-117">Overview of Advanced Group Policy Management</span></span>](overview-of-advanced-group-policy-management-agpm40.md)

-   [<span data-ttu-id="7ec7d-118">バージョン管理のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="7ec7d-118">Best Practices for Version Control</span></span>](best-practices-for-version-control-agpm40.md)

-   [<span data-ttu-id="7ec7d-119">チェックリスト: AGPM サーバーとアーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="7ec7d-119">Checklist: Administer the AGPM Server and Archive</span></span>](checklist-administer-the-agpm-server-and-archive-agpm40.md)

-   [<span data-ttu-id="7ec7d-120">チェックリスト: GPO の作成、編集、展開</span><span class="sxs-lookup"><span data-stu-id="7ec7d-120">Checklist: Create, Edit, and Deploy a GPO</span></span>](checklist-create-edit-and-deploy-a-gpo-agpm40.md)

-   [<span data-ttu-id="7ec7d-121">GPO の一覧を検索およびフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="7ec7d-121">Search and Filter the List of GPOs</span></span>](search-and-filter-the-list-of-gpos.md)

-   [<span data-ttu-id="7ec7d-122">AGPM 管理者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="7ec7d-122">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks-agpm40.md)

-   [<span data-ttu-id="7ec7d-123">編集者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="7ec7d-123">Performing Editor Tasks</span></span>](performing-editor-tasks-agpm40.md)

-   [<span data-ttu-id="7ec7d-124">承認者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="7ec7d-124">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm40.md)

-   [<span data-ttu-id="7ec7d-125">レビュー担当者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="7ec7d-125">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm40.md)

-   [<span data-ttu-id="7ec7d-126">AGPM のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="7ec7d-126">Troubleshooting AGPM</span></span>](troubleshooting-agpm-agpm40.md)

-   [<span data-ttu-id="7ec7d-127">ユーザー インターフェイス: 高度なグループ ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="7ec7d-127">User Interface: Advanced Group Policy Management</span></span>](user-interface-advanced-group-policy-management-agpm40.md)

 

 





