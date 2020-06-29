---
title: Sequencer をインストールする方法
description: Sequencer をインストールする方法
author: dansimp
ms.assetid: 2cd16427-a0ba-4870-82d1-3e3c79e1959b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 75a0f987fcc76d1ed92631085a4364ae6e06c9ce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817267"
---
# <span data-ttu-id="9b56b-103">Sequencer をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="9b56b-103">How to Install the Sequencer</span></span>


<span data-ttu-id="9b56b-104">Microsoft Application Virtualization (App-v) Sequencer は、アプリケーションを仮想アプリケーションとして実行できるように、アプリケーションのインストールとセットアップのプロセスを監視および記録します。</span><span class="sxs-lookup"><span data-stu-id="9b56b-104">The Microsoft Application Virtualization (App-V) Sequencer monitors and records the installation and setup process for applications so that the application can be run as a virtual application.</span></span> <span data-ttu-id="9b56b-105">オペレーティングシステムのみがインストールされているコンピューターに Sequencer をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b56b-105">You should install the Sequencer on a computer that has only the operating system installed.</span></span> <span data-ttu-id="9b56b-106">または、仮想環境を実行しているコンピューター (Microsoft Virtual PC など) に Sequencer をインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9b56b-106">Alternatively, you can install the Sequencer on a computer running a virtual environment—for example, Microsoft Virtual PC.</span></span> <span data-ttu-id="9b56b-107">この方法は、最小限の追加構成で再利用できるクリーンなシーケンス環境を維持するのが簡単なため便利です。</span><span class="sxs-lookup"><span data-stu-id="9b56b-107">This method is useful because it is easier to maintain a clean sequencing environment that can be reused with minimal additional configuration.</span></span>

<span data-ttu-id="9b56b-108">アプリケーションのシーケンスに使用しているコンピューターの管理者権限が必要であり、コンピューターがネットワークに接続されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b56b-108">You must have administrative rights on the computer you are using to sequence the application and the computer must be connected to the network.</span></span> <span data-ttu-id="9b56b-109">このコンピューターでは、Application Virtualization (App-v) クライアントのいずれかのバージョンを実行していない必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b56b-109">The computer must not be running any version of the Application Virtualization (App-V) client.</span></span> <span data-ttu-id="9b56b-110">Sequencer を使用した仮想アプリケーションの作成はリソースを大量に消費するため、推奨された要件を満たしている、または超えているコンピューターに Sequencer をインストールすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="9b56b-110">Creating a virtual application using the Sequencer is very resource intensive, so it is important that you install the Sequencer on a computer that meets or exceeds the recommended requirements.</span></span> <span data-ttu-id="9b56b-111">システム要件の詳細については、「 [Sequencer のハードウェア要件とソフトウェア要件](sequencer-hardware-and-software-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b56b-111">For more information about the system requirements, see [Sequencer Hardware and Software Requirements](sequencer-hardware-and-software-requirements.md)..</span></span>

**<span data-ttu-id="9b56b-112">Microsoft Application Virtualization Sequencer をインストールするには</span><span class="sxs-lookup"><span data-stu-id="9b56b-112">To install the Microsoft Application Virtualization Sequencer</span></span>**

1.  <span data-ttu-id="9b56b-113">Microsoft Application Virtualization Sequencer インストールファイルをインストールするコンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="9b56b-113">Copy the Microsoft Application Virtualization Sequencer installation files to the computer that you want to install it on.</span></span>

2.  <span data-ttu-id="9b56b-114">Microsoft Application Virtualization Sequencer のインストールウィザードを開始するには、[ **setup.exe**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b56b-114">To start the Microsoft Application Virtualization Sequencer installation wizard, select **setup.exe**.</span></span> <span data-ttu-id="9b56b-115">**Microsoft Visual C++ SP1 の再頒布可能パッケージ (x86)** がインストール前に検出されない場合は、 **setup.exe**によってインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9b56b-115">If the **Microsoft Visual C++ SP1 Redistributable Package (x86)** is not detected prior to installation, **setup.exe** will install it.</span></span>

3.  <span data-ttu-id="9b56b-116">[**ようこそ**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b56b-116">On the **Welcome** page, click **Next**.</span></span>

4.  <span data-ttu-id="9b56b-117">[**使用**許諾契約書] ページで、使用許諾契約書に同意する場合は、[**使用許諾契約書に同意**します] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b56b-117">On the **License Agreement** page, to accept the terms of the license agreement, select **I accept the terms in the license agreement**.</span></span> <span data-ttu-id="9b56b-118">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b56b-118">Click **Next**.</span></span>

5.  <span data-ttu-id="9b56b-119">[**インポート先のフォルダー** ] ページで、既定のインストールフォルダーを承認するには、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b56b-119">On the **Destination Folder** page, to accept the default installation folder, click **Next**.</span></span> <span data-ttu-id="9b56b-120">別の保存先フォルダーを指定するには、[**変更**] をクリックし、インストールに使用するインストールフォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="9b56b-120">To specify a different destination folder, click **Change** and specify the installation folder that will be used for the installation.</span></span> <span data-ttu-id="9b56b-121">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b56b-121">Click **Next**.</span></span>

6.  <span data-ttu-id="9b56b-122">[**プログラムをインストールする準備ができ**ました] ページで、インストールを開始するには、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b56b-122">On the **Ready to Install the Program** page, to start the installation, click **Install**.</span></span>

7.  <span data-ttu-id="9b56b-123">**InstallShield ウィザード**の [完了] ページで、インストールウィザードを閉じて Sequencer を開くには、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b56b-123">On the **InstallShield Wizard Completed** page, to close the installation wizard and open the Sequencer, click **Finish**.</span></span> <span data-ttu-id="9b56b-124">Sequencer を開かずにインストールウィザードを閉じるには、[**プログラムの起動**] をオフにし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b56b-124">To close the installation wizard without opening the Sequencer, deselect **Launch the program** and click **Finish**.</span></span>

## <span data-ttu-id="9b56b-125">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9b56b-125">Related topics</span></span>


[<span data-ttu-id="9b56b-126">Application Virtualization Sequencer の構成</span><span class="sxs-lookup"><span data-stu-id="9b56b-126">Configuring the Application Virtualization Sequencer</span></span>](configuring-the-application-virtualization-sequencer.md)

 

 





