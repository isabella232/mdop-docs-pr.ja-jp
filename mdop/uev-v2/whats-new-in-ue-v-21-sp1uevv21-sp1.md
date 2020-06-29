---
title: UE-V 2.1 SP1 の新機能
description: UE-V 2.1 SP1 の新機能
author: dansimp
ms.assetid: 9a40c737-ad9a-4ec1-b42b-31bfabe0f170
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 1f4b6210d95795c352a7ef1402b0353c6f52774b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827427"
---
# <span data-ttu-id="d162d-103">UE-V 2.1 SP1 の新機能</span><span class="sxs-lookup"><span data-stu-id="d162d-103">What's New in UE-V 2.1 SP1</span></span>


<span data-ttu-id="d162d-104">User Experience Virtualization 2.1 SP1 は、UE-V 2.1 と比較して、これらの新機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="d162d-104">User Experience Virtualization 2.1 SP1 provides these new features and functionality compared to UE-V 2.1.</span></span> <span data-ttu-id="d162d-105">[Microsoft User Experience Virtualization (ue-v) 2.1 SP1 のリリースノート](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md)には、UE-V 2.1 SP1 のリリースに関する詳細情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="d162d-105">The [Microsoft User Experience Virtualization (UE-V) 2.1 SP1 Release Notes](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md) provide more information about the UE-V 2.1 SP1 release.</span></span>

## <span data-ttu-id="d162d-106">Windows 10 のサポート</span><span class="sxs-lookup"><span data-stu-id="d162d-106">Support for Windows 10</span></span>


<span data-ttu-id="d162d-107">UE-V 2.1 SP1 は、以前のバージョンの UE-V でサポートされているのと同じソフトウェアに加えて、Windows 10 のサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="d162d-107">UE-V 2.1 SP1 adds support for Windows 10, in addition to the same software that is supported in earlier versions of UE-V.</span></span>

### <span data-ttu-id="d162d-108">Microsoft Azure との互換性</span><span class="sxs-lookup"><span data-stu-id="d162d-108">Compatibility with Microsoft Azure</span></span>

<span data-ttu-id="d162d-109">Windows 10 では、エンタープライズユーザーは、Windows アプリの設定と Windows オペレーティングシステムの設定を OneDrive ではなく Azure に同期することができます。</span><span class="sxs-lookup"><span data-stu-id="d162d-109">Windows 10 lets enterprise users synchronize Windows app settings and Windows operating system settings to Azure instead of to OneDrive.</span></span> <span data-ttu-id="d162d-110">オンプレミスのドメインに参加しているコンピューターでのみ、Windows 10 enterprise の同期機能を UE-V と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="d162d-110">You can use the Windows 10 enterprise sync functionality together with UE-V for on-premises domain-joined computers only.</span></span> <span data-ttu-id="d162d-111">Windows 10 と UE-V の共存を有効にするには、各クライアントまたはグループポリシーのいずれかの PowerShell を使用して、次の UE-V テンプレートを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d162d-111">To enable coexistence between Windows 10 and UE-V, you must disable the following UE-V templates using either PowerShell on each client or Group Policy.</span></span>

<span data-ttu-id="d162d-112">[Microsoft ユーザーエクスペリエンスの仮想化] ノードの下にある [グループポリシー] で、次のポリシー設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="d162d-112">In Group Policy, under the Microsoft User Experience Virtualization node, configure these policy settings:</span></span>

-   <span data-ttu-id="d162d-113">"Windows アプリを同期しない" を有効にする</span><span class="sxs-lookup"><span data-stu-id="d162d-113">Enable “Do Not Synchronize Windows Apps”</span></span>

-   <span data-ttu-id="d162d-114">"Windows の設定の同期" を無効にする</span><span class="sxs-lookup"><span data-stu-id="d162d-114">Disable “Sync Windows Settings”</span></span>

### <span data-ttu-id="d162d-115">Windows 10 のサポートで設定の同期動作が変更されました</span><span class="sxs-lookup"><span data-stu-id="d162d-115">Settings Synchronization Behavior Changed for Windows 10 Support</span></span>

<span data-ttu-id="d162d-116">UE-V 2.1 SP1 では、Windows 10 デバイス間のタスクバーの設定が移動します。</span><span class="sxs-lookup"><span data-stu-id="d162d-116">UE-V 2.1 SP1 roams taskbar settings between Windows 10 devices.</span></span> <span data-ttu-id="d162d-117">ただし、UE-V は、以前のオペレーティングシステムが実行されている Windows 10 デバイスとデバイスとの間で、タスクバーの設定を同期しません。</span><span class="sxs-lookup"><span data-stu-id="d162d-117">However, UE-V does not synchronize taskbar settings between Windows 10 devices and devices running previous operating systems.</span></span>

<span data-ttu-id="d162d-118">また、UE-V 2.1 SP1 では、Windows 10 での Microsoft 電卓と以前のオペレーティングシステムの Microsoft 電卓の間での設定は同期されません。</span><span class="sxs-lookup"><span data-stu-id="d162d-118">In addition, UE-V 2.1 SP1 does not synchronize settings between the Microsoft Calculator in Windows 10 and the Microsoft Calculator in previous operating systems.</span></span>

## <span data-ttu-id="d162d-119">ローミングネットワークプリンターに追加されたサポート</span><span class="sxs-lookup"><span data-stu-id="d162d-119">Support Added for Roaming Network Printers</span></span>


<span data-ttu-id="d162d-120">UE-V 2.1 SP1 では、ネットワークプリンターをデバイス間でローミングできるため、ネットワーク上のデバイスにログオンしたときに、ユーザーはネットワークプリンターにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d162d-120">UE-V 2.1 SP1 lets network printers roam between devices so that a user has access to their network printers when logged on to any device on the network.</span></span> <span data-ttu-id="d162d-121">これには、既定として設定したプリンターのローミングも含まれます。</span><span class="sxs-lookup"><span data-stu-id="d162d-121">This includes roaming the printer that they set as the default.</span></span>

<span data-ttu-id="d162d-122">UE-V でのプリンターローミングには、次のいずれかのシナリオが必要です。</span><span class="sxs-lookup"><span data-stu-id="d162d-122">Printer roaming in UE-V requires one of these scenarios:</span></span>

-   <span data-ttu-id="d162d-123">プリントサーバーは、新しいデバイスにローミングしたときに必要なドライバーをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="d162d-123">The print server can download the required driver when it roams to a new device.</span></span>

-   <span data-ttu-id="d162d-124">ローミングネットワークプリンターのドライバーは、そのネットワークプリンターにアクセスする必要があるすべてのデバイスにプレインストールされています。</span><span class="sxs-lookup"><span data-stu-id="d162d-124">The driver for the roaming network printer is pre-installed on any device that needs to access that network printer.</span></span>

-   <span data-ttu-id="d162d-125">プリンタードライバーは、Windows Update から入手できます。</span><span class="sxs-lookup"><span data-stu-id="d162d-125">The printer driver can be obtained from Windows Update.</span></span>

<span data-ttu-id="d162d-126">**注** UE-V プリンターローミング機能では、両面印刷などのプリンター設定や基本設定はローミング**されません**。</span><span class="sxs-lookup"><span data-stu-id="d162d-126">**Note** The UE-V printer roaming feature does **not** roam printer settings or preferences, such as printing double-sided.</span></span>

 

## <span data-ttu-id="d162d-127">Office 2013 の設定場所テンプレート</span><span class="sxs-lookup"><span data-stu-id="d162d-127">Office 2013 Settings Location Template</span></span>


<span data-ttu-id="d162d-128">UE-V 2.1 および 2.1 SP1 には、Outlook 署名のサポートが強化された Microsoft Office 2013 設定場所テンプレートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d162d-128">UE-V 2.1 and 2.1 SP1 include the Microsoft Office 2013 settings location template with improved Outlook signature support.</span></span> <span data-ttu-id="d162d-129">新規、返信、転送メールの既定の署名設定の同期が追加されました。</span><span class="sxs-lookup"><span data-stu-id="d162d-129">We’ve added synchronization of default signature settings for new, reply, and forwarded emails.</span></span> <span data-ttu-id="d162d-130">ユーザーは、既定の署名設定を選択する必要がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d162d-130">Customers no longer have to choose the default signature settings.</span></span>

<span data-ttu-id="d162d-131">**注** ユーザーが Outlook の署名を同期するすべてのデバイスに対して、Outlook プロファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d162d-131">**Note** An Outlook profile must be created for any device on which a user wants to sync their Outlook signature.</span></span> <span data-ttu-id="d162d-132">プロファイルがまだ作成されていない場合は、ユーザーがそれを作成し、そのデバイスで Outlook を再起動して、署名の同期を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d162d-132">If the profile is not already created, the user can create one and then restart Outlook on that device to enable signature synchronization.</span></span>

 

<span data-ttu-id="d162d-133">以前の UE-V には、自動的に配布され、UE-V エージェントに登録された Microsoft Office 2010 設定場所テンプレートが含まれていました。</span><span class="sxs-lookup"><span data-stu-id="d162d-133">Previously UE-V included Microsoft Office 2010 settings location templates that were automatically distributed and registered with the UE-V Agent.</span></span> <span data-ttu-id="d162d-134">UE-V 2.1 は Office 365 と連携して、office 2013 の設定が Office 365 によってローミングされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d162d-134">UE-V 2.1 works with Office 365 to determine whether Office 2013 settings are roamed by Office 365.</span></span> <span data-ttu-id="d162d-135">設定が Office 365 によってローミングされている場合は、UE-V でローミングされません。</span><span class="sxs-lookup"><span data-stu-id="d162d-135">If settings are roamed by Office 365 they are not roamed by UE-V.</span></span> <span data-ttu-id="d162d-136">[Office 2013 のユーザーとローミングの設定の概要](https://go.microsoft.com/fwlink/p/?LinkID=391220)については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d162d-136">[Overview of user and roaming settings for Office 2013](https://go.microsoft.com/fwlink/p/?LinkID=391220) provides more information.</span></span>

<span data-ttu-id="d162d-137">UE-V 2.1 を使用して設定の同期を有効にするには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d162d-137">To enable settings synchronization using UE-V 2.1, do one of the following:</span></span>

-   <span data-ttu-id="d162d-138">グループポリシーを使用して Office 365 の同期を無効にする</span><span class="sxs-lookup"><span data-stu-id="d162d-138">Use Group Policy to disable Office 365 synchronization</span></span>

-   <span data-ttu-id="d162d-139">Office 2013 のインストール中に Office 365 の同期操作を有効にしない</span><span class="sxs-lookup"><span data-stu-id="d162d-139">Do not enable the Office 365 synchronization experience during Office 2013 installation</span></span>

<span data-ttu-id="d162d-140">UE-V 2.1 は[、office 2013 と office 2010 のテンプレートを](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings)同梱しています。</span><span class="sxs-lookup"><span data-stu-id="d162d-140">UE-V 2.1 ships [Office 2013 and Office 2010 templates](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings).</span></span> <span data-ttu-id="d162d-141">このリリースでは、Office 2007 テンプレートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="d162d-141">This release removes the Office 2007 templates.</span></span> <span data-ttu-id="d162d-142">ユーザーは、引き続き UE-V 2.0 以前の Office 2007 テンプレートを使うことができます。また、[ここ](https://go.microsoft.com/fwlink/p/?LinkID=246589)に記載されている ue-v テンプレートギャラリーからテンプレートを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="d162d-142">Users can still use Office 2007 templates from UE-V 2.0 or earlier and can still get the templates from the UE-V template gallery located [here](https://go.microsoft.com/fwlink/p/?LinkID=246589).</span></span>






## <span data-ttu-id="d162d-143">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d162d-143">Related topics</span></span>


[<span data-ttu-id="d162d-144">UE-V 2.x の概要</span><span class="sxs-lookup"><span data-stu-id="d162d-144">Get Started with UE-V 2.x</span></span>](get-started-with-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="d162d-145">UE-V の展開を準備する</span><span class="sxs-lookup"><span data-stu-id="d162d-145">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[<span data-ttu-id="d162d-146">Microsoft User Experience Virtualization (UE-V) 2.1 SP1 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="d162d-146">Microsoft User Experience Virtualization (UE-V) 2.1 SP1 Release Notes</span></span>](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md)

 

 





