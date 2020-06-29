---
title: UE-V 2.x の構成を管理する
description: UE-V 2.x の構成を管理する
author: dansimp
ms.assetid: e2332eca-a9cd-4446-8f7c-d17058b03466
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 20d5d2942dbd805a4054a9431b237c821cbb70fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827384"
---
# <span data-ttu-id="3e49f-103">UE-V 2.x の構成を管理する</span><span class="sxs-lookup"><span data-stu-id="3e49f-103">Manage Configurations for UE-V 2.x</span></span>


<span data-ttu-id="3e49f-104">Microsoft User Experience Virtualization (UE-V) 2.0、2.1、または 2.1 SP1 のライフサイクルでは、UE-V Agent の構成を管理し、設定パッケージファイルなどのリソースの保存場所を管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e49f-104">In the course of the Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, or 2.1 SP1 lifecycle, you have to manage the configuration of the UE-V Agent and also manage storage locations for resources such as settings package files.</span></span> <span data-ttu-id="3e49f-105">ユーザーが UE-V を操作する方法を定義するために、会社設定センターの構成など、他のタスクを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3e49f-105">You might have to perform other tasks, for example, configuring the Company Settings Center to define how users interact with UE-V.</span></span> <span data-ttu-id="3e49f-106">次のトピックでは、これらの UE-V リソースを管理するためのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="3e49f-106">The following topics provide guidance for managing these UE-V resources.</span></span>

## <span data-ttu-id="3e49f-107">グループポリシーオブジェクトを使用して UE-V を構成する</span><span class="sxs-lookup"><span data-stu-id="3e49f-107">Configuring UE-V 2.x by using Group Policy Objects</span></span>


<span data-ttu-id="3e49f-108">グループポリシーオブジェクトを使用して、UE-V によるコンピューター上の設定の同期方法を定義する設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="3e49f-108">You can use Group Policy Objects to modify the settings that define how UE-V synchronizes settings on computers.</span></span>

[<span data-ttu-id="3e49f-109">グループポリシーオブジェクトを使用して UE-V 2. x を構成する</span><span class="sxs-lookup"><span data-stu-id="3e49f-109">Configuring UE-V 2.x with Group Policy Objects</span></span>](configuring-ue-v-2x-with-group-policy-objects-both-uevv2.md)

## <span data-ttu-id="3e49f-110">System Center Configuration Manager 2012 で UE-V を構成する</span><span class="sxs-lookup"><span data-stu-id="3e49f-110">Configuring UE-V 2.x with System Center Configuration Manager 2012</span></span>


<span data-ttu-id="3e49f-111">SystemCenter2012 ConfigurationManager を使用して、ue-v Agent を管理するには、UE-V 2 構成パックを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e49f-111">You can use SystemCenter2012 ConfigurationManager to manage the UE-V Agent by using the UE-V 2 Configuration Pack.</span></span>

[<span data-ttu-id="3e49f-112">System Center Configuration Manager 2012 で UE-V を構成する</span><span class="sxs-lookup"><span data-stu-id="3e49f-112">Configuring UE-V 2.x with System Center Configuration Manager 2012</span></span>](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md)

## <span data-ttu-id="3e49f-113">PowerShell と WMI を使った UE-V 2. x の管理</span><span class="sxs-lookup"><span data-stu-id="3e49f-113">Administering UE-V 2.x with PowerShell and WMI</span></span>


<span data-ttu-id="3e49f-114">UE-V は、Windows PowerShell コマンドレットを提供します。これは、管理者がさまざまな UE-V タスクを実行するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3e49f-114">UE-V provides Windows PowerShell cmdlets, which can help administrators perform various UE-V tasks.</span></span>

[<span data-ttu-id="3e49f-115">Windows PowerShell と WMI を使用した UE-V 2. x の管理</span><span class="sxs-lookup"><span data-stu-id="3e49f-115">Administering UE-V 2.x with Windows PowerShell and WMI</span></span>](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

## <span data-ttu-id="3e49f-116">UE-V 2. x 用の会社設定センターを構成する</span><span class="sxs-lookup"><span data-stu-id="3e49f-116">Configuring the Company Settings Center for UE-V 2.x</span></span>


<span data-ttu-id="3e49f-117">UE-V Agent を使用してインストールされた会社設定センターを構成すると、ユーザーが UE-V を操作する方法を定義できます。</span><span class="sxs-lookup"><span data-stu-id="3e49f-117">You can configure the Company Settings Center that is installed by using the UE-V Agent to define how users interact with UE-V.</span></span>

[<span data-ttu-id="3e49f-118">UE-V 2. x 用の会社設定センターを構成する</span><span class="sxs-lookup"><span data-stu-id="3e49f-118">Configuring the Company Settings Center for UE-V 2.x</span></span>](configuring-the-company-settings-center-for-ue-v-2x-both-uevv2.md)

## <span data-ttu-id="3e49f-119">UE-V 2. x の構成設定の例</span><span class="sxs-lookup"><span data-stu-id="3e49f-119">Examples of configuration settings for UE-V 2.x</span></span>


<span data-ttu-id="3e49f-120">UE-V 構成の設定の例をいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="3e49f-120">Here are some examples of UE-V configuration settings:</span></span>

-   <span data-ttu-id="3e49f-121">**設定の記憶域のパス:** UE-V の設定を保存するファイル共有の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="3e49f-121">**Settings Storage Path:** Specifies the location of the file share that stores the UE-V settings.</span></span>

-   <span data-ttu-id="3e49f-122">**設定テンプレートカタログのパス:** 新しい設定場所テンプレートがチェックされた場所を定義する汎用名前付け規則 (UNC) パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3e49f-122">**Settings Template Catalog Path:** Specifies the Universal Naming Convention (UNC) path that defines the location that was checked for new settings location templates.</span></span>

-   <span data-ttu-id="3e49f-123">**Microsoft テンプレートの登録:** インストール時に既定の Microsoft テンプレートを登録する必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3e49f-123">**Register Microsoft Templates:** Specifies whether the default Microsoft templates should be registered during installation.</span></span>

-   <span data-ttu-id="3e49f-124">**同期方法:** UE-V で同期プロバイダーを使うか、"none" を使うかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3e49f-124">**Synchronization Method:** Specifies whether UE-V uses the sync provider or "none".</span></span> <span data-ttu-id="3e49f-125">"SyncProvider" は、ネットワークに接続されていないコンピューターをサポートします。</span><span class="sxs-lookup"><span data-stu-id="3e49f-125">The "SyncProvider" supports computers that are disconnected from the network.</span></span> <span data-ttu-id="3e49f-126">[なし] は、コンピューターが常にネットワークに接続されているときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="3e49f-126">"None" applies when the computer is always connected to the network.</span></span> <span data-ttu-id="3e49f-127">Sync メソッドの詳細については、「 [ue-v の同期メソッド](sync-methods-for-ue-v-2x-both-uevv2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e49f-127">For more information about the Sync Method, see [Sync Methods for UE-V 2.x](sync-methods-for-ue-v-2x-both-uevv2.md).</span></span>

-   <span data-ttu-id="3e49f-128">**同期タイムアウト:** コンピューターが設定の保存場所からユーザー設定を取得したときにタイムアウトするまでの時間 (ミリ秒単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="3e49f-128">**Synchronization Timeout:** Specifies the number of milliseconds that the computer waits before time-out when it retrieves the user settings from the settings storage location.</span></span>

-   <span data-ttu-id="3e49f-129">**同期有効:** UE-V 設定の同期を有効または無効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3e49f-129">**Synchronization Enable:** Specifies whether the UE-V settings synchronization is enabled or disabled.</span></span>

-   <span data-ttu-id="3e49f-130">**最大パッケージサイズ:** UE-V Agent が警告を報告する設定パッケージファイルのしきい値のサイズ (バイト単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="3e49f-130">**Maximum Package Size:** Specifies a settings package file threshold size in bytes at which the UE-V Agent reports a warning.</span></span>

-   <span data-ttu-id="3e49f-131">**Windows アプリの設定を同期しない:** UE-V で Windows アプリを同期させないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="3e49f-131">**Don’t Sync Windows App Settings:** Specifies that UE-V should not synchronize Windows apps.</span></span>

-   <span data-ttu-id="3e49f-132">**最初の使用通知を有効/無効**にする:ユーザーのコンピューターで UE-V Agent を初めて実行するときに、UE-V がダイアログボックスを表示するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3e49f-132">**Enable/Disable First Use Notification:** Specifies whether UE-V displays a dialog box the first time that the UE-V Agent runs on a user’s computer.</span></span>

-   <span data-ttu-id="3e49f-133">**トレイアイコンを有効/無効にする:** 通知領域のアイコンと、関連付けられた通知を表示するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="3e49f-133">**Enable/Disable Tray Icon:** Specifies whether UE-V displays an icon in the notification area and any notifications associated with it.</span></span> <span data-ttu-id="3e49f-134">このアイコンは、会社設定センターへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="3e49f-134">The icon provides a link to the Company Settings Center.</span></span>

-   <span data-ttu-id="3e49f-135">**ユーザー設定の連絡先のハイパーリンク:** 会社設定センターの [**連絡先に連絡**する] ハイパーリンクのパス、テキスト、説明を定義します。</span><span class="sxs-lookup"><span data-stu-id="3e49f-135">**Custom Contact IT Hyperlink:** Defines the path, text, and description for the **Contact IT** hyperlink in the Company Settings Center.</span></span>






## <span data-ttu-id="3e49f-136">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3e49f-136">Related topics</span></span>


[<span data-ttu-id="3e49f-137">UE-V 2. x の管理</span><span class="sxs-lookup"><span data-stu-id="3e49f-137">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="3e49f-138">UE-V 2.x の必要な機能を展開する</span><span class="sxs-lookup"><span data-stu-id="3e49f-138">Deploy Required Features for UE-V 2.x</span></span>](deploy-required-features-for-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="3e49f-139">カスタムアプリケーションの UE-V 2. x の展開</span><span class="sxs-lookup"><span data-stu-id="3e49f-139">Deploy UE-V 2.x for Custom Applications</span></span>](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)

 

 





