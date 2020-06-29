---
title: Microsoft Advanced Group Policy Management 3.0 運用ガイド
description: Microsoft Advanced Group Policy Management 3.0 運用ガイド
author: dansimp
ms.assetid: aaefe6d1-a9e5-43eb-b4d8-85880798cb8b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4958609444a62560060a565fb8626bcc9680fd9e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822507"
---
# <span data-ttu-id="45409-103">Microsoft Advanced Group Policy Management 3.0 運用ガイド</span><span class="sxs-lookup"><span data-stu-id="45409-103">Operations Guide for Microsoft Advanced Group Policy Management 3.0</span></span>


<span data-ttu-id="45409-104">Microsoft Advanced グループポリシー管理 (AGPM) を使用して、グループポリシー管理コンソール (GPMC) の機能を拡張し、包括的な変更の制御と、グループポリシーオブジェクト (Gpo) の管理の強化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="45409-104">You can use Microsoft Advanced Group Policy Management (AGPM) to extend the capabilities of the Group Policy Management Console (GPMC), providing comprehensive change control and enhanced management for Group Policy Objects (GPOs).</span></span>

<span data-ttu-id="45409-105">AGPM では、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="45409-105">With AGPM you can:</span></span>

-   <span data-ttu-id="45409-106">Gpo のオフライン編集を実行します。これにより、運用環境に展開する前に、それらを作成してテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="45409-106">Perform offline editing of GPOs, so you can create and test them before deploying to a production environment.</span></span>

-   <span data-ttu-id="45409-107">複数のバージョンの GPO を中央のアーカイブに保持して、問題が発生した場合にロールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="45409-107">Retain multiple versions of a GPO in a central archive, so you can roll back if a problem occurs.</span></span>

-   <span data-ttu-id="45409-108">役割ベースの委任を使用して、複数のユーザー間で Gpo の編集、承認、確認を行う責任を共有します。</span><span class="sxs-lookup"><span data-stu-id="45409-108">Share the responsibility for editing, approving, and reviewing GPOs among multiple people using role-based delegation.</span></span>

-   <span data-ttu-id="45409-109">Gpo のチェックイン/チェックアウト機能を使用して、複数のグループポリシー管理者が互いの作業を上書きする危険性を排除します。</span><span class="sxs-lookup"><span data-stu-id="45409-109">Eliminate the danger of multiple Group Policy administrators overwriting each other's work by using a check-in/check-out capability for GPOs.</span></span>

-   <span data-ttu-id="45409-110">GPO の変更を分析して、別の GPO または同じ GPO の別のバージョンと比較します。差分レポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="45409-110">Analyze changes to a GPO, comparing it to another GPO or another version of the same GPO using difference reporting.</span></span>

-   <span data-ttu-id="45409-111">新しい gpo の開始点として使う標準の設定を保存して、GPO テンプレートを使用して新しい Gpo の作成を簡素化します。</span><span class="sxs-lookup"><span data-stu-id="45409-111">Simplify the creation of new GPOs by using GPO templates, storing standard settings to use as starting points for new GPOs.</span></span>

<span data-ttu-id="45409-112">AGPM では、GPMC に表示される各ドメインの下に**変更コントロール**フォルダーと、gpmc に表示される各 GPO とグループポリシーリンクの [**履歴**] タブが追加されます。</span><span class="sxs-lookup"><span data-stu-id="45409-112">AGPM adds a **Change Control** folder under each domain displayed in the GPMC, as well as a **History** tab for each GPO and Group Policy link displayed in the GPMC.</span></span>

-   [<span data-ttu-id="45409-113">高度なグループ ポリシーの管理の概要</span><span class="sxs-lookup"><span data-stu-id="45409-113">Overview of Advanced Group Policy Management</span></span>](overview-of-advanced-group-policy-management-agpm30ops.md)

-   [<span data-ttu-id="45409-114">バージョン管理のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="45409-114">Best Practices for Version Control</span></span>](best-practices-for-version-control.md)

-   [<span data-ttu-id="45409-115">チェックリスト: AGPM サーバーとアーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="45409-115">Checklist: Administer the AGPM Server and Archive</span></span>](checklist-administer-the-agpm-server-and-archive.md)

-   [<span data-ttu-id="45409-116">チェックリスト: GPO の作成、編集、展開</span><span class="sxs-lookup"><span data-stu-id="45409-116">Checklist: Create, Edit, and Deploy a GPO</span></span>](checklist-create-edit-and-deploy-a-gpo-agpm30ops.md)

-   [<span data-ttu-id="45409-117">AGPM 管理者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="45409-117">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks-agpm30ops.md)

-   [<span data-ttu-id="45409-118">編集者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="45409-118">Performing Editor Tasks</span></span>](performing-editor-tasks-agpm30ops.md)

-   [<span data-ttu-id="45409-119">承認者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="45409-119">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm30ops.md)

-   [<span data-ttu-id="45409-120">レビュー担当者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="45409-120">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm30ops.md)

-   [<span data-ttu-id="45409-121">高度なグループ ポリシーの管理のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="45409-121">Troubleshooting Advanced Group Policy Management</span></span>](troubleshooting-advanced-group-policy-management-agpm30ops.md)

-   [<span data-ttu-id="45409-122">ユーザー インターフェイス: 高度なグループ ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="45409-122">User Interface: Advanced Group Policy Management</span></span>](user-interface-advanced-group-policy-management-agpm30ops.md)

 

 





