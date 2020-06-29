---
title: MED-V の Windows 仮想 PC イメージの構成
description: MED-V の Windows 仮想 PC イメージの構成
author: dansimp
ms.assetid: d87a0df8-9e08-4d1e-bfb0-9dc3cebf0d28
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 340754b33576651c8ba89c85f369c48c0a0ab957
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826817"
---
# <span data-ttu-id="b5e3e-103">MED-V の Windows 仮想 PC イメージの構成</span><span class="sxs-lookup"><span data-stu-id="b5e3e-103">Configuring a Windows Virtual PC Image for MED-V</span></span>


<span data-ttu-id="b5e3e-104">MED-V イメージに含めるすべての項目をインストールしたら、Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 で使用するようにイメージを構成できます。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-104">After you have installed everything that you want to include in your MED-V image, you can configure the image for use in Microsoft Enterprise Desktop Virtualization (MED-V) 2.0.</span></span> <span data-ttu-id="b5e3e-105">このセクションのトピックでは、med-v ワークスペースパッケージを作成する前に、初回のセットアップを実行するように MED-V イメージを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-105">The topics in this section provide guidance for configuring your MED-V image to run first time setup before you create your MED-V workspace package.</span></span>

<span data-ttu-id="b5e3e-106">初回は、セットアップでエンドユーザー用の MED-V ワークスペースを準備します。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-106">First time setup prepares the MED-V workspace for an end user.</span></span> <span data-ttu-id="b5e3e-107">このプロセスでは、MED-V ワークスペースにパッケージ化されたイメージから仮想マシンを作成し、仮想マシン上で Windows ミニセットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-107">The process creates a virtual machine from the image packaged in the MED-V workspace and then runs Windows Mini-Setup on the virtual machine.</span></span> <span data-ttu-id="b5e3e-108">これには、カスタムセットアップスクリプトと、セットアップ完了アプリケーションの1回目の実行 (FtsCompletion.exe) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-108">This includes the running of both custom setup scripts and the first time setup completion application, FtsCompletion.exe.</span></span>

<span data-ttu-id="b5e3e-109">次の手順に従って、初回のセットアップを実行するために MED-V イメージを構成します。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-109">Follow these steps to configure your MED-V image for running first time setup:</span></span>

1. <span data-ttu-id="b5e3e-110">オプションとして、仮想ハードディスク (VHD) を最適化して、Windows 仮想 PC イメージの構成を続行する前に、空のディスク領域を再利用し、VHD のサイズを小さくすることができます。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-110">As an option, you can compact the virtual hard disk (VHD) to reclaim empty disk space and reduce the size of the VHD before you continue with configuring the Windows Virtual PC image.</span></span> <span data-ttu-id="b5e3e-111">詳細については、「 [Med-v 仮想ハードディスクの最適化](compacting-the-med-v-virtual-hard-disk.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-111">For more information, see [Compacting the MED-V Virtual Hard Disk](compacting-the-med-v-virtual-hard-disk.md).</span></span>

2. <span data-ttu-id="b5e3e-112">仮想マシンのセットアッププロセスをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-112">Customize the virtual machine setup process.</span></span>

3. <span data-ttu-id="b5e3e-113">Sysprep を使用して、MED-V イメージを封印します。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-113">Seal the MED-V image by using Sysprep.</span></span>

   **<span data-ttu-id="b5e3e-114">仮想マシンのセットアッププロセスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="b5e3e-114">Customizing the Virtual Machine Setup Process</span></span>**

4. <span data-ttu-id="b5e3e-115">MED-V で使用する画像の準備の一部として、Windows Update を実行するための設定の指定など、仮想マシンのさまざまな設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-115">As part of preparing your image for use with MED-V, you can configure various settings on the virtual machine, such as specifying the settings for running Windows Update.</span></span> <span data-ttu-id="b5e3e-116">MED-V ワークスペースパッケージを作成する前に、必要な仮想マシンの設定をすべて指定します。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-116">Specify all the necessary virtual machine settings before you create the MED-V workspace package.</span></span>

5. <span data-ttu-id="b5e3e-117">MED-V ワークスペースパッケージを作成する前に、仮想マシン上の復元ポイントを無効にして差分ディスクの拡張を禁止することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-117">Before you create the MED-V workspace package, we recommend that you disable restore points on the virtual machine to prevent the differencing disk from growing unbounded.</span></span> <span data-ttu-id="b5e3e-118">詳細については、「 [WINDOWS XP でシステムの復元を有効または無効にする方法](https://go.microsoft.com/fwlink/?LinkId=195927)」を参照してください ( https://go.microsoft.com/fwlink/?LinkId=195927) .</span><span class="sxs-lookup"><span data-stu-id="b5e3e-118">For more information, see [How to turn off and turn on System Restore in Windows XP](https://go.microsoft.com/fwlink/?LinkId=195927) (https://go.microsoft.com/fwlink/?LinkId=195927).</span></span>

   **<span data-ttu-id="b5e3e-119">注</span><span class="sxs-lookup"><span data-stu-id="b5e3e-119">Note</span></span>**  
   <span data-ttu-id="b5e3e-120">初回セットアップの実行時に、復元ポイントを無効にするように Sysprep.inf ファイルを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-120">You can set up your Sysprep.inf file to disable restore points when first time setup is run.</span></span> <span data-ttu-id="b5e3e-121">この GuiRunOnce キーを設定する例については、このセクションで後述するサンプルの Sysprep.inf ファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-121">For an example of setting this GuiRunOnce key, see the sample Sysprep.inf file later in this section.</span></span>



6. <span data-ttu-id="b5e3e-122">既定の Windows Welcome ではなく、ミニセットアップを実行するようにセットアッププロセスを構成します。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-122">Configure the setup process to run Mini-Setup instead of the default Windows Welcome.</span></span> <span data-ttu-id="b5e3e-123">Sysprep ツールは、 **-ミニ**スイッチを使用して実行するか、グラフィカルユーザーインターフェイスで [**ミニセットアップ**] チェックボックスをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-123">You must either run the Sysprep tool by using the **-mini** switch, or select the **MiniSetup** check box in the graphical user interface.</span></span> <span data-ttu-id="b5e3e-124">詳細については、「 [Sysprep でイメージを封印する方法](#bkmk-seal)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-124">For more information, see [How to Seal the Image with Sysprep](#bkmk-seal).</span></span>

   **<span data-ttu-id="b5e3e-125">初回のセットアップ完了時のファイルの呼び出し</span><span class="sxs-lookup"><span data-stu-id="b5e3e-125">Calling the First time setup Completion File</span></span>**

   1.  <span data-ttu-id="b5e3e-126">FtsCompletion.exe という名前の実行可能ファイルは、MED-V ゲストエージェントのインストールの一部として含まれています。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-126">An executable called FtsCompletion.exe is included as part of the installation of the MED-V Guest Agent.</span></span> <span data-ttu-id="b5e3e-127">既定では、[ **Program Files – Microsoft Enterprise デスクトップ仮想化**] の下にある med-v イメージのシステムドライブにあります。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-127">By default, it is located in the system drive of your MED-V image under **Program Files – Microsoft Enterprise Desktop Virtualization**.</span></span>

       **<span data-ttu-id="b5e3e-128">重要</span><span class="sxs-lookup"><span data-stu-id="b5e3e-128">Important</span></span>**  
       <span data-ttu-id="b5e3e-129">初回のセットアッププロセスでの最終手順として、この実行可能プログラムを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-129">As the final step in the first time setup process, you must run this executable program.</span></span> <span data-ttu-id="b5e3e-130">実行可能プログラムが呼び出されるユーザーは、ゲストのローカル管理者グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-130">The user for whom the executable program is being called must be a member of the guest’s local administrator group.</span></span>



   2.  <span data-ttu-id="b5e3e-131">たとえば、MED-V ワークスペースと共に展開されるスクリプトを使用して、この実行可能プログラムを呼び出す方法を決定することができます。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-131">You can decide how you want to call this executable program, for example, through a script that is deployed with the MED-V workspace.</span></span> <span data-ttu-id="b5e3e-132">この実行可能ファイルは、Sysprep.inf ファイルの最後の行として呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-132">You can call this executable as the last line of your Sysprep.inf file.</span></span> <span data-ttu-id="b5e3e-133">Sysprep.inf ファイルでこの実行可能プログラムを呼び出す方法の例については、このセクションで後述するサンプルファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-133">For an example of how to call this executable program in your Sysprep.inf file, see the sample file later in this section.</span></span>

<span data-ttu-id="b5e3e-134">MED-V イメージのカスタマイズを完了したら、Sysprep を使用してイメージを封印することができます。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-134">After you have completed customization of your MED-V image, you are ready to seal the image by using Sysprep.</span></span>

<a href="" id="bkmk-seal"></a>**<span data-ttu-id="b5e3e-135">Sysprep を使用した MED-V イメージの封印</span><span class="sxs-lookup"><span data-stu-id="b5e3e-135">Sealing the MED-V Image by Using Sysprep</span></span>**

1.  <span data-ttu-id="b5e3e-136">システム準備ツール (Sysprep) は、管理者または IT プロフェッショナルによるネットワーク全体でイメージベースのインストールを実行するために使用できるテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-136">The System Preparation tool (Sysprep) is a technology that you can use to perform image-based installations throughout the network with minimal intervention by an administrator or IT-Professional.</span></span>

2.  <span data-ttu-id="b5e3e-137">MED-V 環境では、Sysprep を使って、一意のセキュリティ Id (SID) とその他の設定を、最初に起動したときに各 MED-V ワークスペースに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-137">In a MED-V environment, you can use Sysprep to assign unique security IDs (SID) and other settings to each MED-V workspace the first time that they are started.</span></span>

    **<span data-ttu-id="b5e3e-138">注</span><span class="sxs-lookup"><span data-stu-id="b5e3e-138">Note</span></span>**  
    <span data-ttu-id="b5e3e-139">Sysprep の使い方の詳細については、「 [Sysprep テクニカルリファレンス](https://go.microsoft.com/fwlink/?LinkId=195930)(」) を参照してください https://go.microsoft.com/fwlink/?LinkId=195930) 。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-139">For more information about how to use Sysprep, see [Sysprep Technical Reference](https://go.microsoft.com/fwlink/?LinkId=195930) (https://go.microsoft.com/fwlink/?LinkId=195930).</span></span>



~~~
**Caution**  
When you use non-ASCII characters in the Sysprep.inf file, you must save the file by using the encoding appropriate for the characters entered. Windows XP expects the Sysprep.inf file to be encoded by using the code page for the language that you are targeting.

You must also make sure that the System Locale of the computers to which the MED-V workspace is deployed is set to handle the language specific characters that might be present in the Sysprep.inf file. To change the settings for the System Locale, follow these steps:

1.  To open Region and Language, click **Start**, click **Control Panel**, and then click **Region and Language**.

2.  Click the **Administrative** tab, and then click **Change System Locale** under **Language for non-Unicode programs**.

    If you are prompted for an administrator password or confirmation, type the administrator password or provide confirmation.

3.  Select your preferred language and then click **OK**.



**To configure Sysprep on the MED-V Guest Computer**

1.  Create a folder named *Sysprep* in the root of the MED-V image system drive.

2.  Download the deploy.cab file. For more information, see [Windows XP Service Pack 3 Deployment Tools](https://go.microsoft.com/fwlink/?LinkId=195928) From the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=195928).

3.  From the deploy.cab file, copy or extract the Setupmgr.exe, Sysprep.exe, and Setupcl.exe files to the Sysprep folder.

4.  In the Sysprep folder, run **Setup Manager** (Setupmgr.exe) to create a Sysprep.inf answer file.

    Or, you can create this file manually or use your company’s existing file. For more information, see [How to use the Sysprep tool to automate successful deployment of Windows XP](https://go.microsoft.com/fwlink/?LinkId=195929) (https://go.microsoft.com/fwlink/?LinkId=195929).

5.  Follow the **Setup Manager** wizard.

    **Important**  
    You must configure the MED-V guest to join a domain that lets users log on by using the credentials that they use to log on to the MED-V host.



    **Caution**  
    When you configure a proxy account for joining virtual machines to the domain, know that it is possible for an end user to obtain the proxy account credentials. Take all the necessary security precautions to minimize risk, such as limiting account user rights. For more information about security concerns when you configure a Windows Virtual PC image for MED-V, see [Security Best Practices for MED-V Operations](security-best-practices-for-med-v-operations.md).



    If end users must provide information during the first time setup process based on the parameters specified in the Sysprep.inf file, you must also specify that first time setup is run in **Attended** mode when you are creating your MED-V workspace package. If no information will be required from the end user, you can specify that first time setup is run in **Unattended** mode when you are creating your MED-V workspace package. For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).

    Although you can specify any settings that you prefer, a MED-V best practice is that you create the Sysprep.inf file so that first time setup can be run in **Unattended** mode. This requires that you provide all of the required settings information as you continue through the **Setup Manager** wizard.

    **Caution**  
    If you have set a local policy or registry entry to include a service level agreement (SLA) in your image (VHD), you must specify that first time setup is run in **Attended** mode or first time setup will fail. Or, a MED-V best practice is to enforce the SLA through Group Policy later so that the SLA is displayed to the end user after first time setup is finished.



    **Note**  
    You can configure the MED-V workspace to set certain Sysprep.inf settings based on the configuration of the host and the identity of the end user. For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).



6.  Seal the MED-V image.

    **Important**  
    We recommend that you make a backup copy of the MED-V image before sealing it.



    After you have completed all the steps in the **Setup Manager** wizard, you are ready to run Sysprep to seal the MED-V image.

**To run Sysprep**

1.  Run the System Preparation Tool (Sysprep.exe) from the *Sysprep* folder that you created when you configured Sysprep in the MED-V virtual machine.

2.  In the warning message box that appears, click **OK**.

3.  In the **Options** dialog box, select the **Don't reset grace period for activation** and **Use Mini-Setup** check boxes. Also, make sure that the **Shutdown mode** box is set to **Shut down**.

4.  Click **Reseal**. This removes identity information and clears event logs to prepare for first time setup.

5.  If you are not satisfied with the information listed in the confirmation message box that appears, click **Cancel** and then change the selections.

6.  Click **OK** to complete the system preparation process.

After you have run Sysprep on your MED-V image, the virtual machine shuts down and is ready for use in creating a MED-V workspace.
~~~

## <span data-ttu-id="b5e3e-140">例</span><span class="sxs-lookup"><span data-stu-id="b5e3e-140">Example</span></span>


<span data-ttu-id="b5e3e-141">Sysprep.inf ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b5e3e-141">Here is an example of a Sysprep.inf file.</span></span>

``` syntax
;SetupMgrTag
[GuiUnattended]
    EncryptedAdminPassword=NO
    TimeZone=10
    OEMDuplicatorstring="MED_V v2 Host"
    AdminPassword="administrator"
    AutoLogon=Yes
    AutoLogonCount=1
    OEMSkipRegional=1
    OemSkipWelcome=1

[UserData]
    ProductKey=
    FullName="MED-V User"
    OrgName="Contoso"
    ComputerName=*

[Identification]
    JoinDomain=domain.corp.contoso.com
    DomainAdmin=UserName
    DomainAdminPassword=Password

[Networking]
    InstallDefaultComponents=Yes

[Branding]
    BrandIEUsingUnattended=Yes

[Proxy]
    Proxy_Enable=0
    Use_Same_Proxy=0

[Unattended]
    InstallFilesPath=C:\sysprep\i386
    TargetPath=\WINDOWS
    UpdateServerProfileDirectory=1
    OemSkipEula=Yes

[RegionalSettings]
    LanguageGroup=1
    Language=00000409

[GuiRunOnce]
    Command0="wmic /namespace:\\root\default path SystemRestore call Disable %SystemDrive%\"
    Command1="c:\Program Files\Microsoft Enterprise Desktop Virtualization\FtsCompletion.exe"

[sysprepcleanup]
```

## <span data-ttu-id="b5e3e-142">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b5e3e-142">Related topics</span></span>


[<span data-ttu-id="b5e3e-143">MED-V ワークスペース パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="b5e3e-143">Create a MED-V Workspace Package</span></span>](create-a-med-v-workspace-package.md)

[<span data-ttu-id="b5e3e-144">MED-V イメージを準備する</span><span class="sxs-lookup"><span data-stu-id="b5e3e-144">Prepare a MED-V Image</span></span>](prepare-a-med-v-image.md)









