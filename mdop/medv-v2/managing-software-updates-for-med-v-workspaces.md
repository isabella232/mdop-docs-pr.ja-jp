---
title: MED-V ワークスペースのソフトウェア更新プログラムの管理
description: MED-V ワークスペースのソフトウェア更新プログラムの管理
author: dansimp
ms.assetid: a28d6dcd-cb9f-46ba-8dac-1d990837a3a3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 696238a2f5ad9b7e5120f75f6cd09d890d12519b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824814"
---
# <span data-ttu-id="09994-103">MED-V ワークスペースのソフトウェア更新プログラムの管理</span><span class="sxs-lookup"><span data-stu-id="09994-103">Managing Software Updates for MED-V Workspaces</span></span>


<span data-ttu-id="09994-104">展開された MED-V ワークスペースでアプリケーションのソフトウェア更新プログラムを提供するために、いくつかの異なるオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="09994-104">You have several different options available to you for providing software updates for the applications in the deployed MED-V workspace.</span></span>

<span data-ttu-id="09994-105">**注** MED-V で自動更新を受信する方法を定義する構成設定を指定する方法については、「 [Med-v ワークスペースの自動更新を管理](managing-automatic-updates-for-med-v-workspaces.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09994-105">**Note** For information about how to specify the configuration settings that define how MED-V receives automatic updates, see [Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md).</span></span>

 

**<span data-ttu-id="09994-106">MED-V ワークスペースでのソフトウェアの更新</span><span class="sxs-lookup"><span data-stu-id="09994-106">Updating Software in a MED-V Workspace</span></span>**

1.  **<span data-ttu-id="09994-107">電子ソフトウェア配布システムを使用する</span><span class="sxs-lookup"><span data-stu-id="09994-107">Using an Electronic Software Distribution System</span></span>**

    <span data-ttu-id="09994-108">組織でソフトウェア配布システム (ESD) システムを使ってソフトウェアを展開している場合は、物理コンピューター上のアプリケーションの更新プログラムを提供する場合と同じように、MED-V ワークスペースでアプリケーションのソフトウェア更新プログラムを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="09994-108">If your organization uses an Electronic Software Distribution System (ESD) system to deploy software, you can use it to provide software updates for applications on MED-V workspaces just as you provide updates for applications on physical computers.</span></span>

2.  **<span data-ttu-id="09994-109">グループポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="09994-109">Using Group Policy</span></span>**

    <span data-ttu-id="09994-110">組織がグループポリシーを使用してソフトウェアを展開する場合は、物理コンピューター上のアプリケーションの更新プログラムを提供する場合と同じように、アプリを使用して、MED-V ワークスペースのアプリケーションのソフトウェア更新プログラムを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="09994-110">If your organization deploys software by using Group Policy, you can use it to provide software updates for applications on MED-V workspaces just as you provide updates for applications on physical computers.</span></span>

3.  **<span data-ttu-id="09994-111">Application Virtualization (APP-V) を使用する</span><span class="sxs-lookup"><span data-stu-id="09994-111">Using Application Virtualization (APP-V)</span></span>**

    <span data-ttu-id="09994-112">MED-V と App-v を併用する場合は、ソフトウェアの更新に必要な手順に従って、MED-V ワークスペース内のアプリケーションのソフトウェア更新プログラムを提供できます。</span><span class="sxs-lookup"><span data-stu-id="09994-112">If you use MED-V together with App-V, you can provide software updates to applications in the MED-V workspace by following the steps that are required by App-V for updating software.</span></span> <span data-ttu-id="09994-113">詳細については、「 [Application Virtualization](https://go.microsoft.com/fwlink/?LinkId=122939) (」を参照してください https://go.microsoft.com/fwlink/?LinkId=122939) 。</span><span class="sxs-lookup"><span data-stu-id="09994-113">For more information, see [Application Virtualization](https://go.microsoft.com/fwlink/?LinkId=122939) (https://go.microsoft.com/fwlink/?LinkId=122939).</span></span>

4.  **<span data-ttu-id="09994-114">コアイメージのソフトウェアの更新</span><span class="sxs-lookup"><span data-stu-id="09994-114">Updating Software in the Core Image</span></span>**

    <span data-ttu-id="09994-115">MED-V のベストプラクティスと見なされることはありませんが、ソフトウェア更新プログラムをコアイメージ上のアプリケーションにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="09994-115">Although not considered a MED-V best practice, you can install software updates to applications on the core image.</span></span> <span data-ttu-id="09994-116">更新プログラムをインストールした後で、元のアプリを展開したときと同じように、MED-V ワークスペースをエンタープライズに再展開することができます。</span><span class="sxs-lookup"><span data-stu-id="09994-116">After you have installed the updates, you can then redeploy the MED-V workspace back out to your enterprise just as you deployed it originally.</span></span>

    <span data-ttu-id="09994-117">**重要** この方法では、ソフトウェアの更新プログラムを管理することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="09994-117">**Important** We do not recommend this method of managing software updates.</span></span> <span data-ttu-id="09994-118">また、コアイメージのソフトウェアを更新して、MED-V ワークスペースをエンタープライズに再展開する場合は、最初にセットアップをもう一度実行する必要があります。仮想マシンに保存されたデータはすべて失われます。</span><span class="sxs-lookup"><span data-stu-id="09994-118">In addition, if you update software in the core image and redeploy the MED-V workspace back out to your enterprise, first time setup must run again, and any data saved in the virtual machine is lost.</span></span>

     

## <span data-ttu-id="09994-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="09994-119">Related topics</span></span>


[<span data-ttu-id="09994-120">MED-V ワークスペースの自動更新の管理</span><span class="sxs-lookup"><span data-stu-id="09994-120">Managing Automatic Updates for MED-V Workspaces</span></span>](managing-automatic-updates-for-med-v-workspaces.md)

[<span data-ttu-id="09994-121">アプリケーションの公開をテストする方法</span><span class="sxs-lookup"><span data-stu-id="09994-121">How to Test Application Publishing</span></span>](how-to-test-application-publishing.md)

[<span data-ttu-id="09994-122">MED-V ワークスペースでアプリケーションを公開および公開を取り消す方法</span><span class="sxs-lookup"><span data-stu-id="09994-122">How to Publish and Unpublish an Application on the MED-V Workspace</span></span>](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)

 

 





