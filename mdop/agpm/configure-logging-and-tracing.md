---
title: ログとトレースを構成する
description: ログとトレースを構成する
author: dansimp
ms.assetid: 419231f9-e9db-4f91-a7cf-a0a73db25256
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa3dfa71edb25f6641ade595cd4469e846410ac2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818974"
---
# <span data-ttu-id="007c7-103">ログとトレースを構成する</span><span class="sxs-lookup"><span data-stu-id="007c7-103">Configure Logging and Tracing</span></span>


<span data-ttu-id="007c7-104">管理用テンプレートを使用して、高度なグループポリシー管理 (AGPM) のオプションのログとトレースを一元的に構成することができます。</span><span class="sxs-lookup"><span data-stu-id="007c7-104">You can centrally configure optional logging and tracing for Advanced Group Policy Management (AGPM) using Administrative templates.</span></span>

<span data-ttu-id="007c7-105">これらの手順を完了するには、AGPM 管理者 (フルコントロール) の役割を持つユーザーアカウント、これらの手順で使用される GPO を作成した承認者のユーザーアカウント、または高度なグループポリシーの管理で必要なアクセス許可を持つユーザーアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="007c7-105">A user account with the AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO used in these procedures, or a user account with the necessary permissions in Advanced Group Policy Management is required to complete these procedures.</span></span> <span data-ttu-id="007c7-106">さらに、agpm サーバーへのアクセス権を持つユーザーアカウントは、AGPM サーバーでログを開始するために必要です。</span><span class="sxs-lookup"><span data-stu-id="007c7-106">Additionally, a user account with access to the AGPM Server is required to initiate logging on the AGPM Server.</span></span> <span data-ttu-id="007c7-107">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="007c7-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="007c7-108">AGPM のログとトレースを構成するには</span><span class="sxs-lookup"><span data-stu-id="007c7-108">To configure logging and tracing for AGPM</span></span>**

1.  <span data-ttu-id="007c7-109">[**グループポリシー管理コンソール**] ツリーで、ログとトレースを有効にするすべてのグループポリシー管理者に適用される GPO を編集します。</span><span class="sxs-lookup"><span data-stu-id="007c7-109">In the **Group Policy Management Console** tree, edit a GPO that is applied to all Group Policy administrators for which you want to turn on logging and tracing.</span></span> <span data-ttu-id="007c7-110">詳細については、「 [GPO を編集する](editing-a-gpo.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="007c7-110">(For more information, see [Editing a GPO](editing-a-gpo.md).)</span></span>

2.  <span data-ttu-id="007c7-111">**グループポリシーオブジェクトエディター**で、[**コンピューターの構成**]、[**管理用テンプレート**]、[ **Windows コンポーネント**] の順番にクリックします。</span><span class="sxs-lookup"><span data-stu-id="007c7-111">In the **Group Policy Object Editor**, click **Computer Configuration**, **Administrative Templates**, and **Windows Components**.</span></span>

3.  <span data-ttu-id="007c7-112">[ **Windows コンポーネント**] の下に [ **AGPM** ] が表示されない場合:</span><span class="sxs-lookup"><span data-stu-id="007c7-112">If **AGPM** is not listed under **Windows Components**:</span></span>

    1.  <span data-ttu-id="007c7-113">[**管理用テンプレート**] を右クリックし、[**テンプレートの追加と削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="007c7-113">Right-click **Administrative Templates** and click **Add/Remove Templates**.</span></span>

    2.  <span data-ttu-id="007c7-114">[**追加**] をクリックして、[ **agpm** ] または [ **agpm**] を選択し、[**開く**] をクリックして、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="007c7-114">Click **Add**, select **agpm.admx** or **agpm.adm**, click **Open**, and then click **Close**.</span></span>

4.  <span data-ttu-id="007c7-115">[ **Windows コンポーネント**] で、[ **AGPM**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="007c7-115">Under **Windows Components**, double-click **AGPM**.</span></span>

5.  <span data-ttu-id="007c7-116">詳細ウィンドウで、[ **AGPM ログ**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="007c7-116">In the details pane, double-click **AGPM Logging**.</span></span>

6.  <span data-ttu-id="007c7-117">[ **AGPM ログのプロパティ**] ウィンドウで、[**有効**] をクリックし、ログに記録する詳細レベルを構成します。</span><span class="sxs-lookup"><span data-stu-id="007c7-117">In the **AGPM Logging Properties** window, click **Enabled**, and configure the level of detail to record in the logs.</span></span>

7.  <span data-ttu-id="007c7-118">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="007c7-118">Click **OK**.</span></span>

8.  <span data-ttu-id="007c7-119">**グループポリシーオブジェクトエディター**を閉じます。</span><span class="sxs-lookup"><span data-stu-id="007c7-119">Close the **Group Policy Object Editor**.</span></span> <span data-ttu-id="007c7-120">(詳細については、「 [GPO の展開](deploy-a-gpo.md)」を参照してください)。グループポリシーが更新されたら、agpm サービスを再起動して AGPM サーバーでログを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="007c7-120">(For more information, see [Deploy a GPO](deploy-a-gpo.md).) After Group Policy is updated, you must restart the AGPM Service to begin logging on the AGPM Server.</span></span> <span data-ttu-id="007c7-121">グループポリシーの管理者は、GPMC を閉じてから再起動して、コンピューターでのログの記録を開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="007c7-121">Group Policy administrators must close and restart the GPMC to begin logging on their computers.</span></span>

    <span data-ttu-id="007c7-122">**トレースファイルの場所**:</span><span class="sxs-lookup"><span data-stu-id="007c7-122">**Trace file locations**:</span></span>

    -   <span data-ttu-id="007c7-123">クライアント:%LocalAppData%\\Microsoft\\AGPM\\agpm.log</span><span class="sxs-lookup"><span data-stu-id="007c7-123">Client: %LocalAppData%\\Microsoft\\AGPM\\agpm.log</span></span>

    -   <span data-ttu-id="007c7-124">サーバー:%ProgramData%\\Microsoft\\AGPM\\agpmserv.log</span><span class="sxs-lookup"><span data-stu-id="007c7-124">Server: %ProgramData%\\Microsoft\\AGPM\\agpmserv.log</span></span>

### <span data-ttu-id="007c7-125">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="007c7-125">Additional considerations</span></span>

-   <span data-ttu-id="007c7-126">AGPM のログとトレースを構成するには、GPO の編集と展開が可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="007c7-126">You must be able to edit and deploy a GPO to configure AGPM logging and tracing.</span></span> <span data-ttu-id="007c7-127">詳細については、「 [gpo を編集](editing-a-gpo.md)する」と「 [gpo を展開](deploy-a-gpo.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="007c7-127">See [Editing a GPO](editing-a-gpo.md) and [Deploy a GPO](deploy-a-gpo.md) for additional detail.</span></span>

### <span data-ttu-id="007c7-128">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="007c7-128">Additional references</span></span>

-   [<span data-ttu-id="007c7-129">AGPM 管理者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="007c7-129">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

 

 





