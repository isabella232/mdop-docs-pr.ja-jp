---
title: MBAM 1.0 グループ ポリシー テンプレートをインストールする方法
description: MBAM 1.0 グループ ポリシー テンプレートをインストールする方法
author: dansimp
ms.assetid: 451a50b0-939c-47ad-9248-a138deade550
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a055c84fb6b1645592b53d957daf157a6055880
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825337"
---
# <span data-ttu-id="46ee1-103">MBAM 1.0 グループ ポリシー テンプレートをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="46ee1-103">How to Install the MBAM 1.0 Group Policy Template</span></span>


<span data-ttu-id="46ee1-104">サーバーセットアップアプリケーションには、Microsoft BitLocker の管理と監視 (MBAM) のサーバー関連機能に加えて、MBAM グループポリシーテンプレートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="46ee1-104">In addition to the server-related features of Microsoft BitLocker Administration and Monitoring (MBAM), the server setup application includes an MBAM Group Policy template.</span></span> <span data-ttu-id="46ee1-105">このテンプレートは、グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) を実行できる任意のコンピューターにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="46ee1-105">You can install this template on any computer that is capable of running the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span>

<span data-ttu-id="46ee1-106">次の手順では、MBAM グループポリシーテンプレートをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="46ee1-106">The following steps describe how to install the MBAM Group Policy template.</span></span>

<span data-ttu-id="46ee1-107">**注** 32ビットサーバーでは32ビットセットアップ、64ビットサーバーでは64ビットセットアップを使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="46ee1-107">**Note** Make sure that you use the 32-bit setup on 32-bit servers and the 64-bit setup on 64-bit servers.</span></span>

 

**<span data-ttu-id="46ee1-108">MBAM グループポリシーテンプレートをインストールするには</span><span class="sxs-lookup"><span data-stu-id="46ee1-108">To install the MBAM Group Policy template</span></span>**

1.  <span data-ttu-id="46ee1-109">MBAM インストールウィザードを開始します。次に、[ようこそ] ページの [**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46ee1-109">Start the MBAM installation wizard; then, click **Install** on the Welcome page.</span></span>

2.  <span data-ttu-id="46ee1-110">Microsoft ソフトウェアライセンス条項を読んで同意し、[**次へ**] をクリックしてインストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="46ee1-110">Read and accept the Microsoft Software License Terms, and then click **Next** to continue the installation.</span></span>

3.  <span data-ttu-id="46ee1-111">既定では、すべての MBAM 機能がインストール対象として選択されています。</span><span class="sxs-lookup"><span data-stu-id="46ee1-111">By default, all MBAM features are selected for installation.</span></span> <span data-ttu-id="46ee1-112">**ポリシーテンプレート**を除くすべての機能オプションをオフにし、[**次へ**] をクリックしてインストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="46ee1-112">Clear all feature options except for **Policy Template**, and then click **Next** to continue the installation.</span></span>

    <span data-ttu-id="46ee1-113">**注** インストールウィザードによってインストールの前提条件がチェックされ、不足している前提条件が表示されます。</span><span class="sxs-lookup"><span data-stu-id="46ee1-113">**Note** The installation wizard checks the prerequisites for your installation and displays the prerequisites that are missing.</span></span> <span data-ttu-id="46ee1-114">すべての前提条件が満たされている場合は、インストールが続行されます。</span><span class="sxs-lookup"><span data-stu-id="46ee1-114">If all the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="46ee1-115">見つからない前提条件が検出された場合は、不足している前提条件を解決し、[**前提条件の確認] をもう一度**クリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="46ee1-115">If a missing prerequisite is detected, you must resolve the missing prerequisite and then click **Check prerequisites again**.</span></span> <span data-ttu-id="46ee1-116">すべての前提条件が満たされると、インストールが再開されます。</span><span class="sxs-lookup"><span data-stu-id="46ee1-116">Once all prerequisites are met, the installation will resume.</span></span>

     

4.  <span data-ttu-id="46ee1-117">MBAM セットアップウィザードに、選択した機能のインストールページが表示されたら、[**完了**] をクリックして Mbam セットアップを閉じます。</span><span class="sxs-lookup"><span data-stu-id="46ee1-117">After the MBAM Setup wizard displays installation pages for the selected features, click **Finish** to close MBAM Setup.</span></span>

## <span data-ttu-id="46ee1-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="46ee1-118">Related topics</span></span>


[<span data-ttu-id="46ee1-119">MBAM 1.0 グループ ポリシー オブジェクトの展開</span><span class="sxs-lookup"><span data-stu-id="46ee1-119">Deploying MBAM 1.0 Group Policy Objects</span></span>](deploying-mbam-10-group-policy-objects.md)

 

 





