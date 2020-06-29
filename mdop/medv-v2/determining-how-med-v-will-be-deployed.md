---
title: MED-V を展開する方法の決定
description: MED-V を展開する方法の決定
author: dansimp
ms.assetid: addbfef6-799e-4fe7-87d2-7e096a5ef5a5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a8812ac848147186b92ff3c43c40437e2d4443db
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826184"
---
# <span data-ttu-id="c8a53-103">MED-V を展開する方法の決定</span><span class="sxs-lookup"><span data-stu-id="c8a53-103">Determining How MED-V Will Be Deployed</span></span>


<span data-ttu-id="c8a53-104">既存のインフラストラクチャを評価することによって、企業全体で MED-V を展開する方法を決めることができます。これは、お客様の展開に対して利用できるレビューです。</span><span class="sxs-lookup"><span data-stu-id="c8a53-104">You can determine how you might deploy MED-V throughout your enterprise by evaluating your existing infrastructure, a review of which you can take advantage of for your deployment.</span></span>

## <span data-ttu-id="c8a53-105">MED-V の展開方法を決定する</span><span class="sxs-lookup"><span data-stu-id="c8a53-105">Determine How You Will Deploy MED-V</span></span>


<span data-ttu-id="c8a53-106">MED-V はデスクトップベースのソリューションであるため、既存のインフラストラクチャと連携して動作します。</span><span class="sxs-lookup"><span data-stu-id="c8a53-106">Because MED-V is a desktop-based solution, it works with your existing infrastructure.</span></span> <span data-ttu-id="c8a53-107">たとえば、現在、電子ソフトウェア配布システムを使用して物理コンピューターにアプリケーションを展開する場合は、電子ソフトウェア配布システムを使用して、MED-V ワークスペースに展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="c8a53-107">For example, if you currently deploy applications to physical computers by using an electronic software distribution system, you can also use your electronic software distribution system to deploy to MED-V workspaces.</span></span>

<span data-ttu-id="c8a53-108">現在、電子ソフトウェア配布ソリューションを使用している場合は、そのソリューションを使用して、MED-V のワークスペースとそれに依存するアプリケーションを配布できます。</span><span class="sxs-lookup"><span data-stu-id="c8a53-108">If you are currently using an electronic software distribution solution, you can use that to distribute MED-V workspaces and their dependent applications.</span></span> <span data-ttu-id="c8a53-109">このソリューションは、MED-V が展開された後の後続のアプリケーションの配布に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c8a53-109">You can also use this solution for distribution of subsequent applications after MED-V is deployed.</span></span> <span data-ttu-id="c8a53-110">ESD での MED-V の展開の詳細については、「[電子ソフトウェア配布システムを使用して Med-v ワークスペースを展開する方法](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8a53-110">For more information about deploying MED-V with an ESD, see [How to Deploy a MED-V Workspace Through an Electronic Software Distribution System](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md).</span></span>

<span data-ttu-id="c8a53-111">**注** どのような電子ソフトウェア配布ソリューションを使用する場合でも、特定の解決策の要件について理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8a53-111">**Note** Whichever electronic software distribution solution that you use, you must be familiar with the requirements of your particular solution.</span></span> <span data-ttu-id="c8a53-112">System Center Configuration Manager 2007 R2 またはそれ以降のバージョンを使用している場合は、Microsoft テクニカルライブラリの[Configuration Manager ドキュメントライブラリ](https://go.microsoft.com/fwlink/?LinkId=66999)を参照してください ( https://go.microsoft.com/fwlink/?LinkId=66999) .</span><span class="sxs-lookup"><span data-stu-id="c8a53-112">If you are using System Center Configuration Manager 2007 R2 or a later version, see the [Configuration Manager Documentation Library](https://go.microsoft.com/fwlink/?LinkId=66999) in the Microsoft Technical Library (https://go.microsoft.com/fwlink/?LinkId=66999).</span></span>

 

<span data-ttu-id="c8a53-113">Windows 7 のイメージに MED-V をインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c8a53-113">You might prefer to install MED-V in a Windows 7 image.</span></span> <span data-ttu-id="c8a53-114">次に、エンタープライズ全体で Windows 7 の画像を展開した後、エンドユーザーが必要に応じて MED-V をインストールする準備ができました。</span><span class="sxs-lookup"><span data-stu-id="c8a53-114">Then, after you deploy the Windows 7 images throughout your enterprise, MED-V is ready to be installed when an end user needs it.</span></span> <span data-ttu-id="c8a53-115">詳細については、「 [Windows 7 イメージで Med-v ワークスペースを展開する方法](how-to-deploy-a-med-v-workspace-in-a-windows-7-image.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8a53-115">For more information, see [How to Deploy a MED-V Workspace in a Windows 7 Image](how-to-deploy-a-med-v-workspace-in-a-windows-7-image.md).</span></span>

## <span data-ttu-id="c8a53-116">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c8a53-116">Related topics</span></span>


[<span data-ttu-id="c8a53-117">MED-V 展開を定義して計画する</span><span class="sxs-lookup"><span data-stu-id="c8a53-117">Define and Plan your MED-V Deployment</span></span>](define-and-plan-your-med-v-deployment.md)

[<span data-ttu-id="c8a53-118">MED-V の計画</span><span class="sxs-lookup"><span data-stu-id="c8a53-118">Planning for MED-V</span></span>](planning-for-med-v.md)

 

 





