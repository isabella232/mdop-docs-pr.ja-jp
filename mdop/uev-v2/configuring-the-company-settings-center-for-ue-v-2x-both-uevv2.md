---
title: UE-V 2. x 用の会社設定センターを構成する
description: UE-V 2. x 用の会社設定センターを構成する
author: dansimp
ms.assetid: 48fadb0a-c0dc-4287-9474-f94ce1417003
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0226b3c156a6d6ca39b0214de8acf0c5990db349
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823294"
---
# <span data-ttu-id="64f07-103">UE-V 2. x 用の会社設定センターを構成する</span><span class="sxs-lookup"><span data-stu-id="64f07-103">Configuring the Company Settings Center for UE-V 2.x</span></span>


<span data-ttu-id="64f07-104">Microsoft User Experience Virtualization (UE-V) 2.0、2.1、2.1 SP1 には、ユーザーが同期の設定を管理するために役立つ、会社設定センターの新しいアプリケーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="64f07-104">Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 include a new application, the Company Settings Center, which helps users manage settings to synchronize.</span></span> <span data-ttu-id="64f07-105">会社設定センターは、UE-V Agent を使用してインストールされます。</span><span class="sxs-lookup"><span data-stu-id="64f07-105">The Company Settings Center is installed by using the UE-V Agent.</span></span> <span data-ttu-id="64f07-106">ユーザーは、コントロールパネルの [**スタート**] メニューまたは**スタート**画面、および ue-v 通知領域のアイコンを使って、会社の設定センターにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="64f07-106">Users access the Company Settings Center in Control Panel, in the **Start** menu or on the **Start** screen, and via the UE-V notification area icon.</span></span> <span data-ttu-id="64f07-107">[会社設定センター] には、同期されている設定が表示され、ユーザーは UE-V の同期状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="64f07-107">Company Settings Center displays which settings are synchronized and helps users see the synchronization status of UE-V.</span></span> <span data-ttu-id="64f07-108">ユーザーは、[会社設定センター] を使って、設定をコンピューター間で同期するアプリケーションまたは Windows 機能を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="64f07-108">Users can use the Company Settings Center to select which applications or Windows features synchronize their settings between computers.</span></span> <span data-ttu-id="64f07-109">[**今すぐ同期**] ボタンをクリックして、すべての設定をすぐに同期することもできます。</span><span class="sxs-lookup"><span data-stu-id="64f07-109">They can also click the **Sync Now** button to synchronize all settings immediately.</span></span> <span data-ttu-id="64f07-110">管理者は、会社設定センターでサポートのリンクを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="64f07-110">The administrator can also include a link for support in the Company Settings Center.</span></span>

## <span data-ttu-id="64f07-111">会社設定センターについて</span><span class="sxs-lookup"><span data-stu-id="64f07-111">About the Company Settings Center</span></span>


<span data-ttu-id="64f07-112">[会社設定センター] デスクトップアプリケーションは、ユーザーに UE-V 設定の同期に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="64f07-112">The Company Settings Center desktop application provides users with information about UE-V settings synchronization.</span></span> <span data-ttu-id="64f07-113">会社設定センターには、さまざまな方法でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="64f07-113">The Company Settings Center is accessible in several different ways:</span></span>

-   <span data-ttu-id="64f07-114">通知領域アイコン–**トレイアイコン**のグループポリシー設定または Windows PowerShell 構成が有効になっていると、通知領域に ue-v アイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="64f07-114">Notification area icon – With the **Tray Icon** Group Policy setting or Windows PowerShell configuration enabled, the UE-V icon appears in the notification area.</span></span> <span data-ttu-id="64f07-115">[UE-V] アイコンをクリックして、会社の設定センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="64f07-115">Click the UE-V icon to open the Company Settings Center.</span></span>

    <span data-ttu-id="64f07-116">**注** 通知領域アイコンは、次の設定を使用して無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="64f07-116">**Note** The notification area icon can be disabled by using the following settings:</span></span>

    -   <span data-ttu-id="64f07-117">グループポリシーの設定:</span><span class="sxs-lookup"><span data-stu-id="64f07-117">Group Policy setting:</span></span> `Policy Tray Icon`

    -   <span data-ttu-id="64f07-118">Windows PowerShell コマンドレット:</span><span class="sxs-lookup"><span data-stu-id="64f07-118">Windows PowerShell cmdlet:</span></span> `TrayIconEnabled`

    -   <span data-ttu-id="64f07-119">SystemCenter2012 ConfigurationManager の UE-V 構成パックの構成項目:</span><span class="sxs-lookup"><span data-stu-id="64f07-119">Configuration item in the UE-V Configuration Pack for SystemCenter2012 ConfigurationManager:</span></span> `Tray icon enabled`

     

-   <span data-ttu-id="64f07-120">コントロールパネルアプリケーション–コントロールパネルで、[**デスクトップのカスタマイズ**] を参照し、[**会社設定センター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64f07-120">Control Panel application – In Control Panel, browse to **Appearance and Personalization**, and then click **Company Settings Center**.</span></span>

-   <span data-ttu-id="64f07-121">最初の使用通知–無効の場合、UE-V Agent は、コンピューターでの初回実行時に設定が同期されるようにユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="64f07-121">First use notification – Unless disabled, the UE-V Agent alerts the user that settings are now synchronized when the UE-V agent runs for the first time on a computer.</span></span> <span data-ttu-id="64f07-122">[通知] ダイアログボックスをクリックして、[会社の設定センター] を開きます。</span><span class="sxs-lookup"><span data-stu-id="64f07-122">Click the notification dialog box to open the Company Settings Center.</span></span>

-   <span data-ttu-id="64f07-123">**スタート**画面または [**スタート**] メニューには、会社設定センターへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="64f07-123">The **Start** screen or **Start** menu includes a link to the Company Settings Center.</span></span> <span data-ttu-id="64f07-124">[会社の設定] センターを検索すると、アプリケーションが検索されます。</span><span class="sxs-lookup"><span data-stu-id="64f07-124">A search for Company Settings Center finds the application.</span></span>

## <span data-ttu-id="64f07-125">会社設定センターでのサポートリンクの設定</span><span class="sxs-lookup"><span data-stu-id="64f07-125">Configuring the support link in the Company Settings Center</span></span>


<span data-ttu-id="64f07-126">[会社設定センター] には、ユーザーがクリックして UE-V 設定の同期の問題に関するサポートを受けることができるハイパーリンクを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="64f07-126">The Company Settings Center can include a hyperlink that users can click to get support with UE-V settings synchronization problems.</span></span> <span data-ttu-id="64f07-127">このリンクでは、web ページの http://やメールの mailto://など、有効な URL プロトコルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="64f07-127">This link can open any valid URL protocol, such as http:// for a webpage or mailto:// for an email.</span></span> <span data-ttu-id="64f07-128">[サポート] リンクは、グループポリシー、Windows PowerShell、または System Center 2012 Configuration Manager UE-V 構成パックを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="64f07-128">The support link can be configured by using Group Policy, Windows PowerShell, or the System Center 2012 Configuration Manager UE-V Configuration Pack.</span></span>

**<span data-ttu-id="64f07-129">会社設定センターのサポートリンクを構成する方法</span><span class="sxs-lookup"><span data-stu-id="64f07-129">How to configure the Company Settings Center support link</span></span>**

1.  <span data-ttu-id="64f07-130">優先する管理ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="64f07-130">Open your preferred management tool:</span></span>

    -   <span data-ttu-id="64f07-131">**グループポリシー** : [MDOP 管理用テンプレート](https://go.microsoft.com/fwlink/p/?LinkId=393941)から UE-V 2 用の ADMX テンプレートをダウンロードしていない場合は、ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="64f07-131">**Group Policy** - If you have not already done so, download the ADMX template for UE-V 2 from [MDOP Administrative Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941).</span></span>

    -   <span data-ttu-id="64f07-132">**Windows powershell** – ue-v エージェントがインストールされているコンピューターでは、 **Windows powershell**を開きます。</span><span class="sxs-lookup"><span data-stu-id="64f07-132">**Windows PowerShell** – On a computer with the UE-V Agent installed, open **Windows PowerShell**.</span></span> <span data-ttu-id="64f07-133">Windows PowerShell を使用した UE-V の管理について詳しくは、「 [Windows powershell と WMI を使った ue-v 2. x の管理](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="64f07-133">For more information about administering UE-V by using Windows PowerShell, see [Administering UE-V 2.x with Windows PowerShell and WMI](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md).</span></span>

    -   <span data-ttu-id="64f07-134">**Microsoft User Experience Virtualization (ue-v) 向け System Center 2012 構成パック**– Ue-v 構成パックをインポートし、構成パックのドキュメントに従って構成項目を作成します。</span><span class="sxs-lookup"><span data-stu-id="64f07-134">**System Center 2012 Configuration Pack for Microsoft User Experience Virtualization (UE-V)** – Import the UE-V Configuration Pack and follow the Configuration Pack documentation to create configuration items.</span></span> <span data-ttu-id="64f07-135">UE-V 構成パックの詳細については、「 [System Center Configuration Manager 2012 で ue-v を構成する](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64f07-135">For more information about the UE-V Configuration Pack, see [Configuring UE-V 2.x with System Center Configuration Manager 2012](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md).</span></span>

2.  <span data-ttu-id="64f07-136">次のポリシーの設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="64f07-136">Edit the settings for the following policies:</span></span>

    -   <span data-ttu-id="64f07-137">[**お問い合わせ先] リンクテキスト**-この設定では、[会社の設定] センターの [連絡先に連絡する] URL ハイパーリンクのテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="64f07-137">**Contact IT Link Text** - This setting specifies the text of the Contact IT URL hyperlink in the Company Settings Center.</span></span> <span data-ttu-id="64f07-138">この設定を有効にした場合、[会社設定センター] の URL へのリンクに、指定されたテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="64f07-138">If you enable this setting, the Company Settings Center displays the specified text in the link to the Contact IT URL.</span></span>

        -   <span data-ttu-id="64f07-139">グループポリシーの設定:</span><span class="sxs-lookup"><span data-stu-id="64f07-139">Group Policy settings:</span></span> `Contact IT Link Text`

        -   <span data-ttu-id="64f07-140">Windows PowerShell コマンドレット:</span><span class="sxs-lookup"><span data-stu-id="64f07-140">Windows PowerShell cmdlet:</span></span> `ContactITDescription`

        -   <span data-ttu-id="64f07-141">構成パック構成項目:</span><span class="sxs-lookup"><span data-stu-id="64f07-141">Configuration Pack configuration item:</span></span> `IT contact descriptive text`

    -   <span data-ttu-id="64f07-142">[ **IT URL に連絡**する]-この設定では、web ページの http://やメールの mailto://などの有効な URL プロトコルで、会社設定センターの [連絡先 IT] リンクの url を指定します。</span><span class="sxs-lookup"><span data-stu-id="64f07-142">**Contact IT URL** - This setting specifies the URL for the Contact IT link in the Company Settings Center in a valid URL protocol, such as http:// for a webpage or mailto:// for an email.</span></span>

        -   <span data-ttu-id="64f07-143">グループポリシーの設定:</span><span class="sxs-lookup"><span data-stu-id="64f07-143">Group Policy settings:</span></span> `Contact IT URL`

        -   <span data-ttu-id="64f07-144">Windows PowerShell コマンドレット:</span><span class="sxs-lookup"><span data-stu-id="64f07-144">Windows PowerShell cmdlet:</span></span> `ContactITUrl`

        -   <span data-ttu-id="64f07-145">構成パック構成項目:</span><span class="sxs-lookup"><span data-stu-id="64f07-145">Configuration Pack configuration item:</span></span> `IT contact URL`

3.  <span data-ttu-id="64f07-146">管理ツールを使用して、ユーザーのコンピューターに設定を展開します。</span><span class="sxs-lookup"><span data-stu-id="64f07-146">Deploy settings to users’ computers by using the management tool.</span></span>






 

 





