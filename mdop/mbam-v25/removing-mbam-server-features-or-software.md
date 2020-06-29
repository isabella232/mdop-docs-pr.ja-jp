---
title: MBAM サーバーの機能またはソフトウェアの削除
description: MBAM サーバーの機能またはソフトウェアの削除
author: dansimp
ms.assetid: 5212ba3f-124d-43c5-824a-608e9a192e86
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2e6e57c3d2a62a4e01242ade7a82a7bfa551da83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824977"
---
# <span data-ttu-id="e800a-103">MBAM サーバーの機能またはソフトウェアの削除</span><span class="sxs-lookup"><span data-stu-id="e800a-103">Removing MBAM Server Features or Software</span></span>


<span data-ttu-id="e800a-104">次の手順では、Microsoft BitLocker の管理と監視 (MBAM) からソフトウェアと機能を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e800a-104">These instructions explain how to remove software and features from Microsoft BitLocker Administration and Monitoring (MBAM).</span></span> <span data-ttu-id="e800a-105">MBAM サーバー機能を削除した場合は、MBAM サーバーソフトウェアではなく、構成された機能のみがサーバーから削除されます。</span><span class="sxs-lookup"><span data-stu-id="e800a-105">If you remove MBAM Server features, only the configured features are removed from the server, not the MBAM Server software.</span></span> <span data-ttu-id="e800a-106">MBAM サーバーソフトウェアを削除すると、そのサーバー上で構成したソフトウェアと MBAM サーバー機能は削除されます。</span><span class="sxs-lookup"><span data-stu-id="e800a-106">If you remove the MBAM Server software, the software and any MBAM Server features that you configured on that server are removed.</span></span>

<span data-ttu-id="e800a-107">**注** データが誤って削除されるのを防ぐため、MBAM にはデータベースを削除するメカニズムはありません。この操作は手動で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e800a-107">**Note** To prevent the accidental removal of data, MBAM provides no mechanism for removing the databases; you must do that manually.</span></span>

 

## <a href="" id="bkmk-removeserverfeatures"></a><span data-ttu-id="e800a-108">MBAM サーバー機能の削除</span><span class="sxs-lookup"><span data-stu-id="e800a-108">Removing MBAM Server features</span></span>


<span data-ttu-id="e800a-109">以下のいずれかの方法を使用して、設定済みの MBAM サーバー機能を削除できます。</span><span class="sxs-lookup"><span data-stu-id="e800a-109">You can use either of the following methods to remove MBAM Server features that you have configured:</span></span>

-   <span data-ttu-id="e800a-110">MBAM サーバー構成ウィザード</span><span class="sxs-lookup"><span data-stu-id="e800a-110">MBAM Server Configuration wizard</span></span>

-   <span data-ttu-id="e800a-111">Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="e800a-111">Windows PowerShell cmdlets</span></span>

### <span data-ttu-id="e800a-112">MBAM サーバー構成ウィザードを使用して機能を削除する</span><span class="sxs-lookup"><span data-stu-id="e800a-112">Using the MBAM Server Configuration wizard to remove features</span></span>

<span data-ttu-id="e800a-113">次の手順に従って、MBAM サーバー構成ウィザードを使用して、構成済みの MBAM サーバー機能をサーバーから削除します。</span><span class="sxs-lookup"><span data-stu-id="e800a-113">Follow these instructions to use the MBAM Server Configuration wizard to remove configured MBAM Server features from a server.</span></span>

**<span data-ttu-id="e800a-114">ウィザードを使用して MBAM 機能を削除するには</span><span class="sxs-lookup"><span data-stu-id="e800a-114">To remove MBAM features by using the wizard</span></span>**

1.  <span data-ttu-id="e800a-115">機能を削除するサーバーで、[ **Mbam Server 構成**] を選択して、構成ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="e800a-115">On the server where you want to remove features, select **MBAM Server Configuration** to open the configuration wizard.</span></span>

2.  <span data-ttu-id="e800a-116">[**機能の削除**] をクリックし、削除する機能を選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e800a-116">Click **Remove Features**, select the features to remove, and then click **Next**.</span></span> <span data-ttu-id="e800a-117">[**概要**] ページには、削除するために選択した機能が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e800a-117">A **Summary** page displays the features you selected for removal.</span></span>

3.  <span data-ttu-id="e800a-118">機能の削除を開始するには、[**削除**] をクリックし、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e800a-118">Click **Remove** to start removing the features, and then click **Close**.</span></span>

### <span data-ttu-id="e800a-119">Windows PowerShell を使用して機能を削除する</span><span class="sxs-lookup"><span data-stu-id="e800a-119">Using Windows PowerShell to remove features</span></span>

<span data-ttu-id="e800a-120">Windows PowerShell コマンドレットを使用して、MBAM サーバー機能を削除する一般的なガイドとして、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="e800a-120">Use the following steps as a general guide to remove MBAM Server features by using Windows PowerShell cmdlets.</span></span>

**<span data-ttu-id="e800a-121">Windows PowerShell を使用して MBAM 機能を削除するには</span><span class="sxs-lookup"><span data-stu-id="e800a-121">To remove MBAM features by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="e800a-122">機能を削除するには、「Windows PowerShell を使用して Windows PowerShell を使用するための前提条件を確認する」を参照して、 [MBAM 2.5 サーバー機能を構成](configuring-mbam-25-server-features-by-using-windows-powershell.md)するを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e800a-122">Before removing any features, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md) to review the prerequisites for using Windows PowerShell.</span></span>

2.  <span data-ttu-id="e800a-123">次のコマンドレットを使用して、MBAM サーバー機能を削除します。</span><span class="sxs-lookup"><span data-stu-id="e800a-123">Use the following cmdlets to remove MBAM Server features:</span></span>

    -   <span data-ttu-id="e800a-124">無効化-MbamReport</span><span class="sxs-lookup"><span data-stu-id="e800a-124">Disable-MbamReport</span></span>

    -   <span data-ttu-id="e800a-125">Disable-MbamWebApplication</span><span class="sxs-lookup"><span data-stu-id="e800a-125">Disable-MbamWebApplication</span></span>

    -   <span data-ttu-id="e800a-126">Disable-MbamCMIntegration</span><span class="sxs-lookup"><span data-stu-id="e800a-126">Disable-MbamCMIntegration</span></span>

    <span data-ttu-id="e800a-127">Windows powershell コマンドレットに関するヘルプを表示するには、「 **get-ヘルプ**」 &lt; *コマンドレット*を入力する &gt; か、mbam windows powershell コマンドレットの[windows powershell ページで Microsoft デスクトップ最適化パックオートメーション](https://go.microsoft.com/fwlink/?LinkId=393498)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e800a-127">To get help with Windows PowerShell cmdlets, type **Get-Help** &lt;*cmdlet*&gt; or see the [Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=393498) page for the MBAM Windows PowerShell cmdlets.</span></span>

## <span data-ttu-id="e800a-128">MBAM サーバーソフトウェアの削除</span><span class="sxs-lookup"><span data-stu-id="e800a-128">Removing MBAM Server software</span></span>


<span data-ttu-id="e800a-129">次の手順を使用して、MBAM サーバーソフトウェアと、そのサーバーに構成した MBAM サーバー機能を削除します。</span><span class="sxs-lookup"><span data-stu-id="e800a-129">Use the following steps to remove the MBAM Server software and any MBAM Server features that you configured on that server.</span></span>

**<span data-ttu-id="e800a-130">MBAM サーバーソフトウェアを削除するには</span><span class="sxs-lookup"><span data-stu-id="e800a-130">To remove the MBAM Server software</span></span>**

1.  <span data-ttu-id="e800a-131">MBAM サーバーソフトウェアをアンインストールするサーバーで**MBAMserversetup.exe**を実行して、Microsoft BitLocker の管理と監視のセットアップウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="e800a-131">On the server where you want to uninstall the MBAM Server software, run **MBAMserversetup.exe** to start the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

2.  <span data-ttu-id="e800a-132">[**アンインストール**] を選択し、残りの指示に従って Mbam サーバーソフトウェアのアンインストールプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="e800a-132">Select **Uninstall**, and follow the remaining prompts to complete the process of uninstalling the MBAM Server software.</span></span>



## <span data-ttu-id="e800a-133">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e800a-133">Related topics</span></span>


[<span data-ttu-id="e800a-134">MBAM 2.5 の展開</span><span class="sxs-lookup"><span data-stu-id="e800a-134">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)

 

 

## <span data-ttu-id="e800a-135">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="e800a-135">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="e800a-136">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="e800a-136">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="e800a-137">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="e800a-137">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>



