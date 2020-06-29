---
title: サーバー管理コンソールでレポートを管理する方法
description: サーバー管理コンソールでレポートを管理する方法
author: dansimp
ms.assetid: 28d99620-6339-43f6-9288-4aa958607c59
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 3d70734be04df380e6ce3f4ee8de126503e482e2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817144"
---
# <span data-ttu-id="75ec7-103">サーバー管理コンソールでレポートを管理する方法</span><span class="sxs-lookup"><span data-stu-id="75ec7-103">How to Manage Reports in the Server Management Console</span></span>


<span data-ttu-id="75ec7-104">Application virtualization システムを効果的に管理するために、Application Virtualization Server 管理コンソールを使用して、システムに関する情報を提供するさまざまなレポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="75ec7-104">To effectively manage the Application Virtualization System, you can use the Application Virtualization Server Management Console to generate a variety of reports that provide information about the system.</span></span> <span data-ttu-id="75ec7-105">この情報には、特定のアプリケーションまたはすべてのアプリケーションの毎日の利用状況情報、およびシステムエラー追跡が含まれます。</span><span class="sxs-lookup"><span data-stu-id="75ec7-105">This information includes daily usage information for a specific application or all applications, and system error tracking.</span></span>

**<span data-ttu-id="75ec7-106">注</span><span class="sxs-lookup"><span data-stu-id="75ec7-106">Note</span></span>**  
-   <span data-ttu-id="75ec7-107">インストールスクリプトでは、インストール時に英語版のレポートビューアーのみがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="75ec7-107">During installation, the installation script installs only the English language version of report viewer.</span></span> <span data-ttu-id="75ec7-108">レポートビューアーで、他の言語で正しい情報が表示されるようにするには、次の場所から言語パックをインストールする必要が <https://go.microsoft.com/fwlink/?LinkId=131645> あります。</span><span class="sxs-lookup"><span data-stu-id="75ec7-108">For the report viewer to display the correct information in other languages, it is necessary to install a language pack from the following location: <https://go.microsoft.com/fwlink/?LinkId=131645>.</span></span>

-   <span data-ttu-id="75ec7-109">サーバー管理コンソールでアプリケーションを追加または編集するときは、アプリケーション名とバージョンが OSD ファイルのものと正確に一致していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75ec7-109">When you add or edit an application in the Server Management Console, you must make sure that the application names and versions exactly match those in the OSD files.</span></span> <span data-ttu-id="75ec7-110">レポート機能は、レポート対象のアプリケーションの利用状況データを識別するときに、アプリケーション名とバージョンのデータフィールドを使います。</span><span class="sxs-lookup"><span data-stu-id="75ec7-110">The reporting feature uses the application names and versions data fields when it identifies application usage data on which to report.</span></span> <span data-ttu-id="75ec7-111">データフィールドが一致しない場合、使用状況レコードはスキップされます。</span><span class="sxs-lookup"><span data-stu-id="75ec7-111">If the data fields do not match, the usage records will be skipped.</span></span>

 

## <span data-ttu-id="75ec7-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="75ec7-112">In This Section</span></span>


<a href="" id="application-virtualization-report-types"></a>[<span data-ttu-id="75ec7-113">Application Virtualization レポートの種類</span><span class="sxs-lookup"><span data-stu-id="75ec7-113">Application Virtualization Report Types</span></span>](application-virtualization-report-types.md)  
<span data-ttu-id="75ec7-114">利用可能なレポートの種類に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="75ec7-114">Contains information about the available report types.</span></span>

<a href="" id="how-to-create-a-report"></a>[<span data-ttu-id="75ec7-115">レポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="75ec7-115">How to Create a Report</span></span>](how-to-create-a-reportserver.md)  
<span data-ttu-id="75ec7-116">レポートを作成するためのステップバイステップのプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="75ec7-116">Provides a step-by-step process for creating a report.</span></span>

<a href="" id="how-to-run-a-report"></a>[<span data-ttu-id="75ec7-117">レポートを実行する方法</span><span class="sxs-lookup"><span data-stu-id="75ec7-117">How to Run a Report</span></span>](how-to-run-a-reportserver.md)  
<span data-ttu-id="75ec7-118">レポートを実行するためのステップバイステップのプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="75ec7-118">Provides a step-by-step process for running a report.</span></span>

<a href="" id="how-to-print-a-report"></a>[<span data-ttu-id="75ec7-119">レポートを印刷する方法</span><span class="sxs-lookup"><span data-stu-id="75ec7-119">How to Print a Report</span></span>](how-to-print-a-reportserver.md)  
<span data-ttu-id="75ec7-120">レポートを印刷するためのステップバイステップのプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="75ec7-120">Provides a step-by-step process for printing a report.</span></span>

<a href="" id="how-to-export-a-report"></a>[<span data-ttu-id="75ec7-121">レポートをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="75ec7-121">How to Export a Report</span></span>](how-to-export-a-reportserver.md)  
<span data-ttu-id="75ec7-122">レポートをエクスポートするためのステップバイステップのプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="75ec7-122">Provides a step-by-step process for exporting a report.</span></span>

<a href="" id="how-to-delete-a-report"></a>[<span data-ttu-id="75ec7-123">レポートを削除する方法</span><span class="sxs-lookup"><span data-stu-id="75ec7-123">How to Delete a Report</span></span>](how-to-delete-a-reportserver.md)  
<span data-ttu-id="75ec7-124">レポートを削除するためのステップバイステップのプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="75ec7-124">Provides a step-by-step process for deleting a report.</span></span>

## <span data-ttu-id="75ec7-125">関連トピック</span><span class="sxs-lookup"><span data-stu-id="75ec7-125">Related topics</span></span>


[<span data-ttu-id="75ec7-126">アプリケーション利用状況レポート</span><span class="sxs-lookup"><span data-stu-id="75ec7-126">Application Utilization Report</span></span>](application-utilization-reportserver.md)

[<span data-ttu-id="75ec7-127">Application Virtualization サーバー管理コンソールで管理タスクを実行する方法</span><span class="sxs-lookup"><span data-stu-id="75ec7-127">How to Perform Administrative Tasks in the Application Virtualization Server Management Console</span></span>](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)

[<span data-ttu-id="75ec7-128">ソフトウェア監査レポート</span><span class="sxs-lookup"><span data-stu-id="75ec7-128">Software Audit Report</span></span>](software-audit-reportserver.md)

[<span data-ttu-id="75ec7-129">システム エラー レポート</span><span class="sxs-lookup"><span data-stu-id="75ec7-129">System Error Report</span></span>](system-error-reportserver.md)

[<span data-ttu-id="75ec7-130">システム使用率レポート</span><span class="sxs-lookup"><span data-stu-id="75ec7-130">System Utilization Report</span></span>](system-utilization-reportserver.md)

 

 





