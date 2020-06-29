---
title: Application Virtualization Sequencer をインストールする方法
description: Application Virtualization Sequencer をインストールする方法
author: dansimp
ms.assetid: 89cdf60d-18b0-4204-aa9f-b402610f8f0e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 56a6fe03f2149504b6c34c70b2b82ce2ba0b55ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817307"
---
# <span data-ttu-id="aeae6-103">Application Virtualization Sequencer をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="aeae6-103">How to Install the Application Virtualization Sequencer</span></span>


<span data-ttu-id="aeae6-104">Microsoft Application Virtualization Sequencer は、アプリケーションを仮想アプリケーションとして実行できるように、アプリのインストールとセットアップのプロセスを監視および記録します。</span><span class="sxs-lookup"><span data-stu-id="aeae6-104">The Microsoft Application Virtualization Sequencer monitors and records the installation and setup process for applications so that the application can be run as a virtual application.</span></span> <span data-ttu-id="aeae6-105">オペレーティングシステムのみがインストールされているコンピューターに Sequencer をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeae6-105">You should install the Sequencer on a computer that has only the operating system installed.</span></span> <span data-ttu-id="aeae6-106">または、仮想環境を実行しているコンピューター (Microsoft Virtual PC など) に Sequencer をインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="aeae6-106">Alternatively, you can install the Sequencer on a computer running a virtual environment—for example, Microsoft Virtual PC.</span></span> <span data-ttu-id="aeae6-107">この方法は、最小限の追加構成で再利用できるクリーンなシーケンス環境を維持するのが簡単なため便利です。</span><span class="sxs-lookup"><span data-stu-id="aeae6-107">This method is useful because it is easier to maintain a clean sequencing environment that can be reused with minimal additional configuration.</span></span>

<span data-ttu-id="aeae6-108">アプリケーションのシーケンスに使用しているコンピューターの管理者権限を持っている必要があります。また、コンピューターは、Application Virtualization (App-v) クライアントのいずれかのバージョンを実行していない必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeae6-108">You must have administrative rights on the computer you are using to sequence the application and the computer must not be running any version of the Application Virtualization (App-V) client.</span></span> <span data-ttu-id="aeae6-109">Sequencer を使用した仮想アプリケーションの作成はリソースを大量に消費するため、推奨された要件を満たしている、または超えているコンピューターに Sequencer をインストールすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="aeae6-109">Creating a virtual application by using the Sequencer is very resource intensive, so it is important that you install the Sequencer on a computer that meets or exceeds the recommended requirements.</span></span> <span data-ttu-id="aeae6-110">セーフモードでの App-v sequencer の実行はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="aeae6-110">Running the App-V sequencer in Safe Mode is not supported.</span></span> <span data-ttu-id="aeae6-111">システム要件の詳細については、「 [Application Virtualization のシステム要件](application-virtualization-system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aeae6-111">For more information about the system requirements, see [Application Virtualization System Requirements](application-virtualization-system-requirements.md).</span></span>

<span data-ttu-id="aeae6-112">**重要** アプリケーションの順序を設定した後で、新しいアプリケーションを正しい順序で処理するには、アプリケーションのシーケンスに使用しているコンピューターに、オペレーティングシステムと Sequencer を再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aeae6-112">**Important** After you have sequenced an application, before you can properly sequence a new application you must reinstall the operating system and the Sequencer on the computer you are using to sequence applications.</span></span>

 

**<span data-ttu-id="aeae6-113">Microsoft Application Virtualization Sequencer をインストールするには</span><span class="sxs-lookup"><span data-stu-id="aeae6-113">To install the Microsoft Application Virtualization Sequencer</span></span>**

1.  <span data-ttu-id="aeae6-114">Microsoft Application Virtualization Sequencer インストールファイルをインストールするコンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="aeae6-114">Copy the Microsoft Application Virtualization Sequencer installation files to the computer that you want to install it on.</span></span>

2.  <span data-ttu-id="aeae6-115">Microsoft Application Virtualization Sequencer のインストールウィザードを開始するには、[ **setup.exe**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="aeae6-115">To start the Microsoft Application Virtualization Sequencer installation wizard, select **setup.exe**.</span></span> <span data-ttu-id="aeae6-116">**Microsoft Visual C++ SP1 の再頒布可能パッケージ (x86)** がインストール前に検出されない場合は、 **setup.exe**によってインストールされます。</span><span class="sxs-lookup"><span data-stu-id="aeae6-116">If the **Microsoft Visual C++ SP1 Redistributable Package (x86)** is not detected prior to installation, **setup.exe** will install it.</span></span>

3.  <span data-ttu-id="aeae6-117">[**ようこそ**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aeae6-117">On the **Welcome** page, click **Next**.</span></span>

4.  <span data-ttu-id="aeae6-118">[**使用**許諾契約書] ページで、使用許諾契約書に同意する場合は、[**使用許諾契約書に同意**します] を選択します。</span><span class="sxs-lookup"><span data-stu-id="aeae6-118">On the **License Agreement** page, to accept the terms of the license agreement, select **I accept the terms in the license agreement**.</span></span> <span data-ttu-id="aeae6-119">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aeae6-119">Click **Next**.</span></span>

5.  <span data-ttu-id="aeae6-120">[**インポート先のフォルダー** ] ページで、既定のインストールフォルダーを承認するには、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aeae6-120">On the **Destination Folder** page, to accept the default installation folder, click **Next**.</span></span> <span data-ttu-id="aeae6-121">別の保存先フォルダーを指定するには、[**変更**] をクリックし、インストールに使用するインストールフォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="aeae6-121">To specify a different destination folder, click **Change** and specify the installation folder that will be used for the installation.</span></span> <span data-ttu-id="aeae6-122">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aeae6-122">Click **Next**.</span></span>

6.  <span data-ttu-id="aeae6-123">[**プログラムをインストールする準備ができ**ました] ページで、インストールを開始するには、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aeae6-123">On the **Ready to Install the Program** page, to start the installation, click **Install**.</span></span>

7.  <span data-ttu-id="aeae6-124">**InstallShield ウィザード**の [完了] ページで、インストールウィザードを閉じて Sequencer を開くには、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aeae6-124">On the **InstallShield Wizard Completed** page, to close the installation wizard and open the Sequencer, click **Finish**.</span></span> <span data-ttu-id="aeae6-125">Sequencer を開かずにインストールウィザードを閉じるには、[**プログラムの起動**] をオフにし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aeae6-125">To close the installation wizard without opening the Sequencer, deselect **Launch the program** and click **Finish**.</span></span>

## <span data-ttu-id="aeae6-126">関連トピック</span><span class="sxs-lookup"><span data-stu-id="aeae6-126">Related topics</span></span>


[<span data-ttu-id="aeae6-127">Application Virtualization Sequencer をアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="aeae6-127">How to Upgrade the Application Virtualization Sequencer</span></span>](how-to-upgrade-the-application-virtualization-sequencer.md)

[<span data-ttu-id="aeae6-128">Application Virtualization の展開要件</span><span class="sxs-lookup"><span data-stu-id="aeae6-128">Application Virtualization Deployment Requirements</span></span>](application-virtualization-deployment-requirements.md)

 

 





