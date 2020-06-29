---
title: ログとトレースを構成する
description: ログとトレースを構成する
author: dansimp
ms.assetid: 4f89552f-e949-48b0-9325-23746034eaa4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e6edcb643dd34a20a845cb3d44a0fe8b353a6291
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818984"
---
# <span data-ttu-id="3a0a2-103">ログとトレースを構成する</span><span class="sxs-lookup"><span data-stu-id="3a0a2-103">Configure Logging and Tracing</span></span>


<span data-ttu-id="3a0a2-104">管理用テンプレートを使用して、オプションのログとトレースを一元的に構成できます。</span><span class="sxs-lookup"><span data-stu-id="3a0a2-104">You can centrally configure optional logging and tracing using Administrative templates.</span></span> <span data-ttu-id="3a0a2-105">これは、高度なグループポリシー管理 (AGPM) に関連した問題を診断するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3a0a2-105">This may be helpful when diagnosing any problems related to Advanced Group Policy Management (AGPM).</span></span>

<span data-ttu-id="3a0a2-106">AGPM 管理者 (フルコントロール) の役割を持つユーザーアカウント、これらの手順で使用するグループポリシーオブジェクト (GPO) を作成した承認者のユーザーアカウント、または AGPM で必要なアクセス許可を持つユーザーアカウントは、これらの手順を完了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3a0a2-106">A user account with the AGPM Administrator (Full Control) role, the user account of the Approver who created the Group Policy Object (GPO) used in these procedures, or a user account with the necessary permissions in AGPM is required to complete these procedures.</span></span> <span data-ttu-id="3a0a2-107">さらに、agpm サーバーへのアクセス権を持つユーザーアカウントは、AGPM サーバーでログを開始するために必要です。</span><span class="sxs-lookup"><span data-stu-id="3a0a2-107">Additionally, a user account with access to the AGPM Server is required to initiate logging on the AGPM Server.</span></span> <span data-ttu-id="3a0a2-108">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a0a2-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="3a0a2-109">AGPM のログとトレースを構成するには</span><span class="sxs-lookup"><span data-stu-id="3a0a2-109">To configure logging and tracing for AGPM</span></span>**

1.  <span data-ttu-id="3a0a2-110">[**グループポリシー管理コンソール**] ツリーで、ログとトレースを有効にするすべてのグループポリシー管理者に適用される GPO を編集します。</span><span class="sxs-lookup"><span data-stu-id="3a0a2-110">In the **Group Policy Management Console** tree, edit a GPO that is applied to all Group Policy administrators for which you want to turn on logging and tracing.</span></span> <span data-ttu-id="3a0a2-111">詳細については、「 [GPO を編集する](editing-a-gpo-agpm30ops.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a0a2-111">(For more information, see [Editing a GPO](editing-a-gpo-agpm30ops.md).)</span></span>

2.  <span data-ttu-id="3a0a2-112">[**グループポリシー管理エディター** ] ウィンドウで、[**コンピューターの構成**]、[**ポリシー**]、[**管理用テンプレート**]、[Windows コンポーネント]、[ **AGPM**] の**各項目**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a0a2-112">In the **Group Policy Management Editor** window, click **Computer Configuration**, **Policies**, **Administrative Templates**, **Windows Components**, and **AGPM**.</span></span>

3.  <span data-ttu-id="3a0a2-113">詳細ウィンドウで、[ **AGPM: ログを構成する**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a0a2-113">In the details pane, double-click **AGPM: Configure logging**.</span></span>

4.  <span data-ttu-id="3a0a2-114">[**プロパティ**] ウィンドウで、[**有効**] をクリックし、ログに記録する詳細レベルを構成します。</span><span class="sxs-lookup"><span data-stu-id="3a0a2-114">In the **Properties** window, click **Enabled**, and configure the level of detail to record in the logs.</span></span>

5.  <span data-ttu-id="3a0a2-115">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a0a2-115">Click **OK**.</span></span>

6.  <span data-ttu-id="3a0a2-116">[**グループポリシー管理エディター** ] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="3a0a2-116">Close the **Group Policy Management Editor** window.</span></span> <span data-ttu-id="3a0a2-117">(詳細については、「 [GPO の展開](deploy-a-gpo-agpm30ops.md)」を参照してください)。グループポリシーが更新された後、agpm サービスを再起動して、AGPM サーバーでのログの開始、変更、停止を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a0a2-117">(For more information, see [Deploy a GPO](deploy-a-gpo-agpm30ops.md).) After Group Policy is updated, you must restart the AGPM Service to start, modify, or stop logging on the AGPM Server.</span></span> <span data-ttu-id="3a0a2-118">グループポリシー管理者は、GPMC を閉じて再起動し、コンピューターのログの開始、変更、または停止を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a0a2-118">Group Policy administrators must close and restart the GPMC to start, modify, or stop logging on their computers.</span></span>

    <span data-ttu-id="3a0a2-119">**トレースファイルの場所**:</span><span class="sxs-lookup"><span data-stu-id="3a0a2-119">**Trace file locations**:</span></span>

    -   <span data-ttu-id="3a0a2-120">クライアント:%LocalAppData%\\Microsoft\\AGPM\\agpm.log</span><span class="sxs-lookup"><span data-stu-id="3a0a2-120">Client: %LocalAppData%\\Microsoft\\AGPM\\agpm.log</span></span>

    -   <span data-ttu-id="3a0a2-121">サーバー:%ProgramData%\\Microsoft\\AGPM\\agpmserv.log</span><span class="sxs-lookup"><span data-stu-id="3a0a2-121">Server: %ProgramData%\\Microsoft\\AGPM\\agpmserv.log</span></span>

### <span data-ttu-id="3a0a2-122">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="3a0a2-122">Additional considerations</span></span>

-   <span data-ttu-id="3a0a2-123">AGPM のログとトレースを構成するには、GPO の編集と展開が可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a0a2-123">You must be able to edit and deploy a GPO to configure AGPM logging and tracing.</span></span> <span data-ttu-id="3a0a2-124">詳細については、「 [gpo を編集](editing-a-gpo-agpm30ops.md)する」と「 [gpo を展開](deploy-a-gpo-agpm30ops.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a0a2-124">See [Editing a GPO](editing-a-gpo-agpm30ops.md) and [Deploy a GPO](deploy-a-gpo-agpm30ops.md) for additional detail.</span></span>

### <span data-ttu-id="3a0a2-125">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="3a0a2-125">Additional references</span></span>

-   [<span data-ttu-id="3a0a2-126">高度なグループ ポリシーの管理の構成</span><span class="sxs-lookup"><span data-stu-id="3a0a2-126">Configuring Advanced Group Policy Management</span></span>](configuring-advanced-group-policy-management.md)

 

 





