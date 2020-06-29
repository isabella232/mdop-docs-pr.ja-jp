---
title: MBAM 2.0 グループ ポリシー テンプレートをインストールする方法
description: MBAM 2.0 グループ ポリシー テンプレートをインストールする方法
author: dansimp
ms.assetid: bc193232-d060-4285-842e-d194a74dd3c9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6420fc4d499de05ed740b038b40aff6a9cd8a05f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826254"
---
# <span data-ttu-id="131d5-103">MBAM 2.0 グループ ポリシー テンプレートをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="131d5-103">How to Install the MBAM 2.0 Group Policy Template</span></span>


<span data-ttu-id="131d5-104">サーバーに関連する Microsoft BitLocker の管理と監視 (MBAM) 機能に加えて、サーバーセットアップアプリケーションには Microsoft BitLocker の管理と監視のグループポリシーテンプレートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="131d5-104">In addition to the server-related Microsoft BitLocker Administration and Monitoring (MBAM) features, the server setup application includes an Microsoft BitLocker Administration and Monitoring Group Policy template.</span></span> <span data-ttu-id="131d5-105">このテンプレートは、グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) を実行できる任意のコンピューターにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="131d5-105">This template can be installed on any computer capable of running the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span>

<span data-ttu-id="131d5-106">次の手順では、MBAM グループポリシーテンプレートをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="131d5-106">The following steps describe how to install the MBAM Group Policy template.</span></span>

<span data-ttu-id="131d5-107">**注** 32ビットサーバーでは32ビットセットアップ、64ビットサーバーでは64ビットセットアップを使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="131d5-107">**Note** Make sure that you use the 32-bit setup on 32-bit servers and the 64-bit setup on 64-bit servers.</span></span>

 

**<span data-ttu-id="131d5-108">MBAM グループポリシーテンプレートをインストールするには</span><span class="sxs-lookup"><span data-stu-id="131d5-108">To install the MBAM Group Policy template</span></span>**

1.  <span data-ttu-id="131d5-109">MBAM をインストールするサーバーで**MBAMSetup.exe**を実行して、mbam インストールウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="131d5-109">On the server where you want to install MBAM, run **MBAMSetup.exe** to start the MBAM installation wizard.</span></span>

2.  <span data-ttu-id="131d5-110">[**ようこそ**] ページで、必要に応じて [**カスタマーエクスペリエンス向上プログラム**] を選択し、[**開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="131d5-110">On the **Welcome** page, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="131d5-111">Microsoft ソフトウェアライセンス条項を読んで同意し、[**次へ**] をクリックしてインストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="131d5-111">Read and accept the Microsoft Software License Terms, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="131d5-112">既定では、すべての Microsoft BitLocker の管理機能と監視機能がインストール対象として選択されています。</span><span class="sxs-lookup"><span data-stu-id="131d5-112">By default, all Microsoft BitLocker Administration and Monitoring features are selected for installation.</span></span> <span data-ttu-id="131d5-113">**ポリシーテンプレート**を除くすべての機能オプションをオフにし、[**次へ**] をクリックしてインストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="131d5-113">Clear all feature options except for **Policy Template**, and then click **Next** to continue the installation.</span></span>

    <span data-ttu-id="131d5-114">**注** インストールウィザードによってインストールの前提条件がチェックされ、不足している前提条件が表示されます。</span><span class="sxs-lookup"><span data-stu-id="131d5-114">**Note** The installation wizard checks the prerequisites for your installation and displays prerequisites that are missing.</span></span> <span data-ttu-id="131d5-115">すべての前提条件が満たされている場合は、インストールが続行されます。</span><span class="sxs-lookup"><span data-stu-id="131d5-115">If all the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="131d5-116">見つからない前提条件が検出された場合は、不足している前提条件を解決し、[**前提条件の確認] をもう一度**クリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="131d5-116">If a missing prerequisite is detected, you have to resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span> <span data-ttu-id="131d5-117">すべての前提条件が満たされると、インストールが再開されます。</span><span class="sxs-lookup"><span data-stu-id="131d5-117">Once all prerequisites are met, the installation will resume.</span></span>

     

5.  <span data-ttu-id="131d5-118">テンプレートのインストール方法とその場所に関する具体的な手順については、「 [MDOP グループポリシー (admx) テンプレートをダウンロードして展開する方法](https://technet.microsoft.com/library/dn659707.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="131d5-118">For specific steps about how and where to install the templates, see [How to Download and Deploy MDOP Group Policy (.admx) Templates](https://technet.microsoft.com/library/dn659707.aspx).</span></span>

6.  <span data-ttu-id="131d5-119">Microsoft BitLocker の管理と監視のセットアップウィザードで、選択した機能のインストールページが表示されたら、[**完了**] をクリックして Mbam セットアップを閉じます。</span><span class="sxs-lookup"><span data-stu-id="131d5-119">After the Microsoft BitLocker Administration and Monitoring Setup wizard displays installation pages for the selected features, click **Finish** to close MBAM Setup.</span></span>

## <span data-ttu-id="131d5-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="131d5-120">Related topics</span></span>


[<span data-ttu-id="131d5-121">MBAM 2.0 グループ ポリシー オブジェクトの展開</span><span class="sxs-lookup"><span data-stu-id="131d5-121">Deploying MBAM 2.0 Group Policy Objects</span></span>](deploying-mbam-20-group-policy-objects-mbam-2.md)

 

 





