---
title: Windows 仮想 PC イメージ上でのアプリケーションのインストール
description: Windows 仮想 PC イメージ上でのアプリケーションのインストール
author: dansimp
ms.assetid: 32651eff-e3c6-4ef4-947d-2beddc695eac
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9bf73fec0b33b37c2553dfe6f923917aa926b8e8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826834"
---
# <span data-ttu-id="823b4-103">Windows 仮想 PC イメージ上でのアプリケーションのインストール</span><span class="sxs-lookup"><span data-stu-id="823b4-103">Installing Applications on a Windows Virtual PC Image</span></span>


<span data-ttu-id="823b4-104">Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 で使用する Windows 仮想 PC イメージを作成した後、電子ソフトウェア配布 (ESD) システムやウイルス対策ソフトウェアなど、MED-V を実行するときに役立つその他のコンポーネントをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="823b4-104">After you have created a Windows Virtual PC image for use with Microsoft Enterprise Desktop Virtualization (MED-V) 2.0, you can install other components that are helpful when running MED-V, such as an electronic software distribution (ESD) system and antivirus software.</span></span>

<span data-ttu-id="823b4-105">以下のセクションでは、MED-V イメージにソフトウェアをインストールするのに役立つ情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="823b4-105">The following section provides information to help you install software on the MED-V image.</span></span>

<span data-ttu-id="823b4-106">**注意** 展開後に MED-V ワークスペースの管理が簡単になるようにするには、MED-V イメージにインストールするコンポーネントの数を、必要に応じて、または MED-V の使用時に役立つものに制限することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="823b4-106">**Caution** For ease of MED-V workspace management after deployment, we recommend that you limit the number of components that you install on the MED-V image to those components that are required or that are helpful when using MED-V.</span></span> <span data-ttu-id="823b4-107">たとえば、MED-V の実行は必須ではありませんが、アプリケーションを MED-V ワークスペースにインストールしたり、ウイルス対策ソフトウェアを使用して、イメージのセキュリティを確保したりするために、後で使う ESD システムをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="823b4-107">For example, although they are not required to run MED-V, you can install an ESD system to use later for installing applications to a MED-V workspace and antivirus software for security on the image.</span></span>

 

**<span data-ttu-id="823b4-108">MED-V イメージにソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="823b4-108">Installing Software on a MED-V Image</span></span>**

1.  <span data-ttu-id="823b4-109">現在実行されていない場合は、MED-V 仮想マシンを開きます。</span><span class="sxs-lookup"><span data-stu-id="823b4-109">If it is not currently running, open your MED-V virtual machine.</span></span>

    1.  <span data-ttu-id="823b4-110">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **windows 仮想 Pc** ]、[ **windows 仮想 pc**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="823b4-110">Click **Start**, click **All Programs**, click **Windows Virtual PC** and then click **Windows Virtual PC**.</span></span>

    2.  <span data-ttu-id="823b4-111">MED-V 仮想マシンをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="823b4-111">Double-click your MED-V virtual machine.</span></span>

2.  <span data-ttu-id="823b4-112">仮想マシンのオペレーティングシステム内から、インストールするソフトウェアのインストールファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="823b4-112">From inside the virtual machine operating system, locate the installation files for the software that you want to install.</span></span>

3.  <span data-ttu-id="823b4-113">ソフトウェアベンダーから提供されているインストール手順に従います。</span><span class="sxs-lookup"><span data-stu-id="823b4-113">Follow the installation instructions that are provided by the software vendor.</span></span>

    <span data-ttu-id="823b4-114">**注** インストールが完了したら、仮想マシンを終了して再起動する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="823b4-114">**Note** After installation is complete, you might have to close and then restart the virtual machine.</span></span>

     

<span data-ttu-id="823b4-115">MED-V イメージにインストールするソフトウェアまたはアプリケーションについて、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="823b4-115">Repeat these steps for any software or application that you want to install on the MED-V image.</span></span> <span data-ttu-id="823b4-116">イメージにプレインストールするアプリケーションの数を制限することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="823b4-116">We recommend that you limit the number of applications that you preinstall on the image.</span></span> <span data-ttu-id="823b4-117">イメージにアプリケーションやその他のソフトウェアをインストールする場合に推奨される手順は、ESD システムを今すぐプレインストールし、後で使ってソフトウェアをイメージに展開することです。</span><span class="sxs-lookup"><span data-stu-id="823b4-117">The recommended process for installing applications and other software on the image is to preinstall an ESD system now and to use it later to deploy software to the image.</span></span> <span data-ttu-id="823b4-118">または、グループポリシーまたは App-v を使用して、MED-V ワークスペースのアプリケーションを追加または削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="823b4-118">Alternately, you can also use Group Policy or App-V to add or remove applications on a MED-V workspace.</span></span> <span data-ttu-id="823b4-119">詳細については、「 [Med-v ワークスペースに展開されたアプリケーションを管理する](managing-applications-deployed-to-med-v-workspaces.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="823b4-119">For more information, see [Managing Applications Deployed to MED-V Workspaces](managing-applications-deployed-to-med-v-workspaces.md).</span></span>

<span data-ttu-id="823b4-120">仮想イメージにソフトウェアをインストールする方法の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="823b4-120">For more information about how to install software on a virtual image, see the following articles:</span></span>

-   <span data-ttu-id="823b4-121">[仮想アプリケーションを公開して使用する](https://go.microsoft.com/fwlink/?LinkId=195926)( https://go.microsoft.com/fwlink/?LinkId=195926) .</span><span class="sxs-lookup"><span data-stu-id="823b4-121">[Publish and Use Virtual Applications](https://go.microsoft.com/fwlink/?LinkId=195926) (https://go.microsoft.com/fwlink/?LinkId=195926).</span></span>

-   <span data-ttu-id="823b4-122">[Windows VIRTUAL PC ヘルプ](https://go.microsoft.com/fwlink/?LinkId=182378)( https://go.microsoft.com/fwlink/?LinkId=182378) .</span><span class="sxs-lookup"><span data-stu-id="823b4-122">[Windows Virtual PC Help](https://go.microsoft.com/fwlink/?LinkId=182378) (https://go.microsoft.com/fwlink/?LinkId=182378).</span></span>

<span data-ttu-id="823b4-123">必要なソフトウェアをすべて、MED-V イメージにインストールすると、画像をパッケージ化する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="823b4-123">After you have installed all of the software that you want on the MED-V image, your image is ready to be packaged.</span></span>

## <span data-ttu-id="823b4-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="823b4-124">Related topics</span></span>


[<span data-ttu-id="823b4-125">MED-V の Windows 仮想 PC イメージの構成</span><span class="sxs-lookup"><span data-stu-id="823b4-125">Configuring a Windows Virtual PC Image for MED-V</span></span>](configuring-a-windows-virtual-pc-image-for-med-v.md)

[<span data-ttu-id="823b4-126">MED-V イメージを準備する</span><span class="sxs-lookup"><span data-stu-id="823b4-126">Prepare a MED-V Image</span></span>](prepare-a-med-v-image.md)

 

 





