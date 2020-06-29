---
title: Microsoft Advanced Group Policy Management 2.5 運用ガイド
description: Microsoft Advanced Group Policy Management 2.5 運用ガイド
author: dansimp
ms.assetid: 005f0bb5-789f-42a9-bcaf-7e8c31a8df66
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c0ae04e0e8dcf62d3ea840de28a9248827ec62e4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822514"
---
# <span data-ttu-id="31307-103">Microsoft Advanced Group Policy Management 2.5 運用ガイド</span><span class="sxs-lookup"><span data-stu-id="31307-103">Operations Guide for Microsoft Advanced Group Policy Management 2.5</span></span>


<span data-ttu-id="31307-104">Microsoft Advanced グループポリシー管理 (AGPM) を使用して、グループポリシー管理コンソール (GPMC) の機能を拡張し、包括的な変更の制御と、グループポリシーオブジェクト (Gpo) の管理の強化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="31307-104">You can use Microsoft Advanced Group Policy Management (AGPM) to extend the capabilities of the Group Policy Management Console (GPMC), providing comprehensive change control and enhanced management for Group Policy objects (GPOs).</span></span>

<span data-ttu-id="31307-105">AGPM では、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="31307-105">With AGPM you can:</span></span>

-   <span data-ttu-id="31307-106">Gpo のオフライン編集を実行します。これにより、運用環境に展開する前に、それらを作成してテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="31307-106">Perform offline editing of GPOs, so you can create and test them before deploying to a production environment.</span></span>

-   <span data-ttu-id="31307-107">複数のバージョンの GPO を中央のアーカイブに保持して、問題が発生した場合にロールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="31307-107">Retain multiple versions of a GPO in a central archive, so you can roll back if a problem occurs.</span></span>

-   <span data-ttu-id="31307-108">役割ベースの委任を使用して、複数のユーザー間で Gpo の編集、承認、確認を行う責任を共有します。</span><span class="sxs-lookup"><span data-stu-id="31307-108">Share the responsibility for editing, approving, and reviewing GPOs among multiple people using role-based delegation.</span></span>

-   <span data-ttu-id="31307-109">Gpo のチェックイン/チェックアウト機能を使用して、複数のグループポリシー管理者が互いの作業を上書きする危険性を排除します。</span><span class="sxs-lookup"><span data-stu-id="31307-109">Eliminate the danger of multiple Group Policy administrators overwriting each other's work by using a check-in/check-out capability for GPOs.</span></span>

-   <span data-ttu-id="31307-110">GPO の変更を分析して、別の GPO または同じ GPO の別のバージョンと比較します。差分レポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="31307-110">Analyze changes to a GPO, comparing it to another GPO or another version of the same GPO using difference reporting.</span></span>

-   <span data-ttu-id="31307-111">新しい gpo の開始点として使う標準の設定を保存して、GPO テンプレートを使用して新しい Gpo の作成を簡素化します。</span><span class="sxs-lookup"><span data-stu-id="31307-111">Simplify the creation of new GPOs by using GPO templates, storing standard settings to use as starting points for new GPOs.</span></span>

<span data-ttu-id="31307-112">AGPM によって、GPMC に表示される各ドメインの下に**変更コントロール**ノードが追加され、gpmc に表示される各 GPO およびグループポリシーリンクの**履歴**と**拡張機能**のタブも追加されます。</span><span class="sxs-lookup"><span data-stu-id="31307-112">AGPM adds a **Change Control** node under each domain displayed in the GPMC, as well as **History** and **Extensions** tabs for each GPO and Group Policy link displayed in the GPMC.</span></span>

-   [<span data-ttu-id="31307-113">高度なグループ ポリシーの管理の概要</span><span class="sxs-lookup"><span data-stu-id="31307-113">Overview of Advanced Group Policy Management</span></span>](overview-of-advanced-group-policy-management.md)

-   [<span data-ttu-id="31307-114">チェックリスト: GPO の作成、編集、展開</span><span class="sxs-lookup"><span data-stu-id="31307-114">Checklist: Create, Edit, and Deploy a GPO</span></span>](checklist-create-edit-and-deploy-a-gpo.md)

-   [<span data-ttu-id="31307-115">AGPM 管理者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="31307-115">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

-   [<span data-ttu-id="31307-116">編集者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="31307-116">Performing Editor Tasks</span></span>](performing-editor-tasks.md)

-   [<span data-ttu-id="31307-117">承認者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="31307-117">Performing Approver Tasks</span></span>](performing-approver-tasks.md)

-   [<span data-ttu-id="31307-118">レビュー担当者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="31307-118">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks.md)

-   [<span data-ttu-id="31307-119">高度なグループ ポリシーの管理のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="31307-119">Troubleshooting Advanced Group Policy Management</span></span>](troubleshooting-advanced-group-policy-management.md)

-   [<span data-ttu-id="31307-120">ユーザー インターフェイス: 高度なグループ ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="31307-120">User Interface: Advanced Group Policy Management</span></span>](user-interface-advanced-group-policy-management.md)

 

 





