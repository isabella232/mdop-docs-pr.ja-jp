---
title: Sequencer のインストール方法 (App-v 4.6 SP1)
description: Sequencer のインストール方法 (App-v 4.6 SP1)
author: dansimp
ms.assetid: fe8eb876-28fb-46ae-b592-da055107e639
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 611564e861d65dcd357c58732fb60dab21c05abe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817274"
---
# <span data-ttu-id="ce3b6-103">Sequencer のインストール方法 (App-v 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="ce3b6-103">How to Install the Sequencer (App-V 4.6 SP1)</span></span>


<span data-ttu-id="ce3b6-104">Microsoft Application Virtualization (App-v) Sequencer は、アプリケーションを仮想アプリケーションとして実行できるように、アプリケーションのインストールとセットアップのプロセスを監視および記録します。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-104">The Microsoft Application Virtualization (App-V) Sequencer monitors and records the installation and setup process for applications so that the application can be run as a virtual application.</span></span> <span data-ttu-id="ce3b6-105">オペレーティングシステムのみがインストールされているコンピューターに、App-v Sequencer をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-105">You should install the App-V Sequencer on a computer that has only the operating system installed.</span></span> <span data-ttu-id="ce3b6-106">または、仮想コンピューターなどの仮想環境で実行されているコンピューターに Sequencer をインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-106">Alternatively, you can install the Sequencer on a computer running in a virtual environment, for example, a virtual computer.</span></span> <span data-ttu-id="ce3b6-107">この方法は、最小限の追加構成で再利用できるクリーンなシーケンス環境を維持するのが容易であるために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-107">This method is useful because it is easier to maintain a clean sequencing environment that you can reuse with minimal additional configuration.</span></span>

<span data-ttu-id="ce3b6-108">アプリケーションのシーケンスに使用しているコンピューターの管理者資格情報を持っている必要があります。また、コンピューターは、どのバージョンの App-v クライアントも実行していない必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-108">You must have administrative credentials on the computer you are using to sequence the application, and the computer must not be running any version of App-V client.</span></span> <span data-ttu-id="ce3b6-109">App-v Sequencer を使用して仮想アプリケーションを作成するには、複数の操作が必要であるため、 [Application Virtualization Sequencer ハードウェアとソフトウェアの要件](application-virtualization-sequencer-hardware-and-software-requirements.md)を満たしているか超えているコンピューターに Sequencer をインストールすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-109">Creating a virtual application by using the App-V Sequencer requires multiple operations, so it is important that you install the Sequencer on a computer that meets or exceeds the [Application Virtualization Sequencer Hardware and Software Requirements](application-virtualization-sequencer-hardware-and-software-requirements.md).</span></span>

**<span data-ttu-id="ce3b6-110">注</span><span class="sxs-lookup"><span data-stu-id="ce3b6-110">Note</span></span>**  
<span data-ttu-id="ce3b6-111">セーフモードでの App-v sequencer の実行はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-111">Running the App-V sequencer in Safe Mode is not supported.</span></span>



**<span data-ttu-id="ce3b6-112">Microsoft Application Virtualization Sequencer をインストールするには</span><span class="sxs-lookup"><span data-stu-id="ce3b6-112">To install the Microsoft Application Virtualization Sequencer</span></span>**

1.  <span data-ttu-id="ce3b6-113">Microsoft Application Virtualization Sequencer インストールファイルをインストールするコンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-113">Copy the Microsoft Application Virtualization Sequencer installation files to the computer on which you want to install it.</span></span>

2.  <span data-ttu-id="ce3b6-114">Microsoft Application Virtualization Sequencer のインストールウィザードを開始するには、[ **Setup.exe**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-114">To start the Microsoft Application Virtualization Sequencer installation wizard, double-click **Setup.exe**.</span></span> <span data-ttu-id="ce3b6-115">**Microsoft Visual C++ SP1 再頒布可能パッケージ (x86)** がインストール前に検出されない場合は、[**インストール**] をクリックして必要な前提条件をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-115">If the **Microsoft Visual C++ SP1 Redistributable Package (x86)** is not detected prior to installation, click **Install** to install the required prerequisite.</span></span>

3.  <span data-ttu-id="ce3b6-116">インストールを続行するには、[**ようこそ**] ページで [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-116">To continue the installation, on the **Welcome** page, click **Next**.</span></span>

4.  <span data-ttu-id="ce3b6-117">[**使用**許諾契約書] ページで、使用許諾契約書に同意し、[**使用許諾契約書に同意**します] をクリックして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-117">On the **License Agreement** page, to accept the terms of the license agreement, click **I accept the terms in the license agreement**, and then click **Next**.</span></span>

5.  <span data-ttu-id="ce3b6-118">[**インポート先のフォルダー** ] ページで、既定のインストールフォルダーを承認するには、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-118">On the **Destination Folder** page, to accept the default installation folder, click **Next**.</span></span> <span data-ttu-id="ce3b6-119">別の保存先フォルダーを指定するには、[**変更**] をクリックし、インストールに使用するインストールフォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-119">To specify a different destination folder, click **Change** and specify the installation folder that will be used for the installation.</span></span> <span data-ttu-id="ce3b6-120">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-120">Click **Next**.</span></span>

6.  <span data-ttu-id="ce3b6-121">[**仮想ドライブ**] ページで、アプリケーションの仮想化の既定のドライブ**Q:\\** (既定) を、すべてのシーケンスされたアプリケーションの実行元のドライブとして構成するには、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-121">On the **Virtual Drive** page, to configure the Application Virtualization default drive **Q:\\** (default) as the drive that all sequenced applications will run from, click **Next**.</span></span> <span data-ttu-id="ce3b6-122">別のドライブ文字を指定する場合は、一覧を使用し、適切なドライブ文字を選択して使用するドライブ文字を選び、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-122">If you want to specify a different drive letter, use the list and select the drive letter that you want to use by selecting the appropriate drive letter, and then click **Next**.</span></span>

    **<span data-ttu-id="ce3b6-123">重要</span><span class="sxs-lookup"><span data-stu-id="ce3b6-123">Important</span></span>**  
    <span data-ttu-id="ce3b6-124">この手順で指定した Application Virtualization のドライブ文字は、仮想アプリケーションがターゲットコンピューター上で実行されるドライブ文字です。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-124">The Application Virtualization drive letter specified with this step is the drive letter that virtual applications will be run from on target computers.</span></span> <span data-ttu-id="ce3b6-125">指定されたドライブ文字は、使用可能であり、App-v クライアントを実行しているコンピューターで現在使用されていないものである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-125">The drive letter specified must be available, and not currently in use on the computers running the App-V client.</span></span> <span data-ttu-id="ce3b6-126">指定したドライブが既に使われている場合、仮想アプリケーションはターゲットコンピューターで失敗します。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-126">If the specified drive is already in use, the virtual application fails on the target computer.</span></span>



7.  <span data-ttu-id="ce3b6-127">[**プログラムをインストールする準備ができ**ました] ページで、インストールを開始するには、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-127">On the **Ready to Install the Program** page, to start the installation, click **Install**.</span></span>

8.  <span data-ttu-id="ce3b6-128">**InstallShield ウィザード**の [完了] ページで、インストールウィザードを終了して app-v Sequencer を開くには、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-128">On the **InstallShield Wizard Completed** page, to close the installation wizard and open the App-V Sequencer, click **Finish**.</span></span> <span data-ttu-id="ce3b6-129">Sequencer を開かずにインストールウィザードを閉じるには、[**プログラムの起動**] をオフにして、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-129">To close the installation wizard without opening the Sequencer, clear **Launch the program**, and then click **Finish**.</span></span>

    **<span data-ttu-id="ce3b6-130">注</span><span class="sxs-lookup"><span data-stu-id="ce3b6-130">Note</span></span>**  
    <span data-ttu-id="ce3b6-131">仮想環境を実行しているコンピューター (たとえば仮想マシン) に app-v Sequencer をインストールした場合は、スナップショットを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-131">If you installed the App-V Sequencer on a computer running a virtual environment, for example a virtual machine, you must now take a snapshot.</span></span> <span data-ttu-id="ce3b6-132">アプリケーションをシーケンスした後は、この画像に戻すことができます。そのため、次のアプリケーションをシーケンスできます。</span><span class="sxs-lookup"><span data-stu-id="ce3b6-132">After you sequence an application, you can revert to this image, so you can sequence the next application.</span></span>



~~~
When you uninstall the Sequencer, the following registry keys are not removed from the computer that the Sequencer was installed on. Additionally, you must restart the computer after you have uninstalled the Sequencer so that all associated drivers can be stopped and the operation can be completed.

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid**

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5**

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard**

-   **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\SecKey**
~~~

## <span data-ttu-id="ce3b6-133">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ce3b6-133">Related topics</span></span>


[<span data-ttu-id="ce3b6-134">Application Virtualization Sequencer の構成 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="ce3b6-134">Configuring the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](configuring-the-application-virtualization-sequencer--app-v-46-sp1-.md)









