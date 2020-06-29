---
title: 編集者タスクの実行
description: 編集者タスクの実行
author: dansimp
ms.assetid: d4ac3277-2557-41cf-ac90-5adb6c30687c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e70a56ff01313e3b502ebde5bb486ec18db60643
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820397"
---
# <span data-ttu-id="6de39-103">編集者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="6de39-103">Performing Editor Tasks</span></span>


<span data-ttu-id="6de39-104">エディターとは、AGPM 管理者 (フルコントロール) によって承認されたユーザーで、グループポリシーオブジェクト (Gpo) に変更を加え、GPO テンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="6de39-104">An Editor is a person authorized by an AGPM Administrator (Full Control) to make changes to Group Policy Objects (GPOs) and create GPO templates.</span></span> <span data-ttu-id="6de39-105">さらに、編集者は、GPO の作成、削除、復元のプロセスを開始できますが、既定では、承認者に承認を要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6de39-105">Additionally, an Editor can initiate the process of creating, deleting, or restoring a GPO, but by default must request approval from an Approver.</span></span>

<span data-ttu-id="6de39-106">**重要** Gpo の中央アーカイブに接続していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6de39-106">**Important** Ensure that you are connecting to the central archive for GPOs.</span></span> <span data-ttu-id="6de39-107">詳細については、「 [AGPM サーバー接続を構成](configure-an-agpm-server-connection-reviewer-agpm30ops.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6de39-107">For more information, see [Configure an AGPM Server Connection](configure-an-agpm-server-connection-reviewer-agpm30ops.md).</span></span>

 

-   [<span data-ttu-id="6de39-108">GPO の作成、制御、インポート</span><span class="sxs-lookup"><span data-stu-id="6de39-108">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-agpm30ops.md)

-   [<span data-ttu-id="6de39-109">GPO の編集</span><span class="sxs-lookup"><span data-stu-id="6de39-109">Editing a GPO</span></span>](editing-a-gpo-agpm30ops.md)

-   [<span data-ttu-id="6de39-110">テンプレートの作成と既定のテンプレートの設定</span><span class="sxs-lookup"><span data-stu-id="6de39-110">Creating a Template and Setting a Default Template</span></span>](creating-a-template-and-setting-a-default-template-agpm30ops.md)

-   [<span data-ttu-id="6de39-111">GPO の削除または復元</span><span class="sxs-lookup"><span data-stu-id="6de39-111">Deleting or Restoring a GPO</span></span>](deleting-or-restoring-a-gpo-agpm30ops.md)

<span data-ttu-id="6de39-112">**注** 編集者ロールにはレビュー担当者ロールの権限が含まれているため、編集者は設定を確認して Gpo を比較することもできます。</span><span class="sxs-lookup"><span data-stu-id="6de39-112">**Note** Because the Editor role includes the permissions for the Reviewer role, an Editor can also review settings and compare GPOs.</span></span> <span data-ttu-id="6de39-113">詳細については、「[校閲者タスクを実行](performing-reviewer-tasks-agpm30ops.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6de39-113">See [Performing Reviewer Tasks](performing-reviewer-tasks-agpm30ops.md) for more information.</span></span>

 

### <span data-ttu-id="6de39-114">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="6de39-114">Additional considerations</span></span>

<span data-ttu-id="6de39-115">既定では、編集者の役割に対して次の権限が提供されます。</span><span class="sxs-lookup"><span data-stu-id="6de39-115">By default, the following permissions are provided for the Editor role:</span></span>

-   <span data-ttu-id="6de39-116">リストの内容</span><span class="sxs-lookup"><span data-stu-id="6de39-116">List Contents</span></span>

-   <span data-ttu-id="6de39-117">設定の読み取り</span><span class="sxs-lookup"><span data-stu-id="6de39-117">Read Settings</span></span>

-   <span data-ttu-id="6de39-118">設定を編集する</span><span class="sxs-lookup"><span data-stu-id="6de39-118">Edit Settings</span></span>

-   <span data-ttu-id="6de39-119">テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="6de39-119">Create Template</span></span>

 

 





