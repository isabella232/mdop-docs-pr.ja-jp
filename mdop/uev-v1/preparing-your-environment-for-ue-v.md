---
title: UE-V に対応する環境の準備
description: UE-V に対応する環境の準備
author: dansimp
ms.assetid: c93d3b33-e032-451a-9e1b-8534e1625396
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8f806f3c326bad5204a7f1ee69e11b61177e3cce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824647"
---
# <span data-ttu-id="ce942-103">UE-V に対応する環境の準備</span><span class="sxs-lookup"><span data-stu-id="ce942-103">Preparing Your Environment for UE-V</span></span>


<span data-ttu-id="ce942-104">Microsoft User Experience Virtualization (UE-V) では、設定の保存場所を使用してコンピューター間のローミング設定が行われます。</span><span class="sxs-lookup"><span data-stu-id="ce942-104">Microsoft User Experience Virtualization (UE-V) roams settings between computers by the use of a settings storage location.</span></span> <span data-ttu-id="ce942-105">設定の保存場所はファイル共有であり、UE-V エージェントの展開時に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce942-105">The settings storage location is a file share and should be configured during the UE-V Agent deployment.</span></span> <span data-ttu-id="ce942-106">これは、設定の保存場所または Active Directory のホームディレクトリとして定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce942-106">It must be defined either as a settings storage location or as an Active Directory home directory.</span></span> <span data-ttu-id="ce942-107">さらに、一貫した同期をサポートするようにタイムサーバーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce942-107">In addition, the administrator should configure a time server to support consistent synchronization.</span></span> <span data-ttu-id="ce942-108">UE-V の環境を準備するには、次の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce942-108">To prepare your environment for UE-V, you should consider the following:</span></span>

-   <span data-ttu-id="ce942-109">[Ue-v の設定ストレージ](#bkmk-uevsettingsstorage):</span><span class="sxs-lookup"><span data-stu-id="ce942-109">[UE-V Settings Storage](#bkmk-uevsettingsstorage):</span></span>

    -   [<span data-ttu-id="ce942-110">設定の保存場所を定義する</span><span class="sxs-lookup"><span data-stu-id="ce942-110">Defining a Settings Storage Location</span></span>](#bkmk-definingsettingsstoragelocation)

    -   [<span data-ttu-id="ce942-111">UE-V で Active Directory ホームディレクトリを使用する</span><span class="sxs-lookup"><span data-stu-id="ce942-111">Using Active Directory Home Directory with UE-V</span></span>](#bkmk-usingactivedirectoryhomedirectory)

-   [<span data-ttu-id="ce942-112">コンピューターの時計を同期させる (UE-V 設定の同期)</span><span class="sxs-lookup"><span data-stu-id="ce942-112">Synchronize Computer Clocks for UE-V Settings Synchronization</span></span>](#bkmk-synchronizecomputerclocks)

-   [<span data-ttu-id="ce942-113">パフォーマンスとキャパシティの計画</span><span class="sxs-lookup"><span data-stu-id="ce942-113">Performance and Capacity Planning</span></span>](#bkmk-performancecapacityplanning)

<span data-ttu-id="ce942-114">オペレーティングシステムとコンピューターの要件の詳細については、「 [ue-v 1.0 でサポートされている構成](supported-configurations-for-ue-v-10.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce942-114">For more information about operating system and computer requirements, see [Supported Configurations for UE-V 1.0](supported-configurations-for-ue-v-10.md).</span></span>

## <a href="" id="bkmk-uevsettingsstorage"></a><span data-ttu-id="ce942-115">UE-V の設定ストレージ</span><span class="sxs-lookup"><span data-stu-id="ce942-115">UE-V settings storage</span></span>


<span data-ttu-id="ce942-116">ユーザーエクスペリエンスの仮想化設定ストレージは、設定の保存場所または Active Directory のホームディレクトリのいずれかで定義できます。</span><span class="sxs-lookup"><span data-stu-id="ce942-116">You can define the User Experience Virtualization settings storage in one of two configurations: a settings storage location or an Active Directory home directory.</span></span>

### <a href="" id="bkmk-definingsettingsstoragelocation"></a><span data-ttu-id="ce942-117">設定の保存場所を定義する</span><span class="sxs-lookup"><span data-stu-id="ce942-117">Define a settings storage location</span></span>

<span data-ttu-id="ce942-118">UE-V の設定の保存場所は、UE-V ユーザーがアクセスできる標準ネットワーク共有です。</span><span class="sxs-lookup"><span data-stu-id="ce942-118">The UE-V settings storage location is a standard network share that is accessible by UE-V users.</span></span> <span data-ttu-id="ce942-119">設定の保存場所を定義する前に、ルートディレクトリを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce942-119">Before you define the settings storage location, you must create a root directory.</span></span> <span data-ttu-id="ce942-120">共有に設定を保存するユーザーは、保存場所の読み取り/書き込みアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce942-120">Users who will store settings on the share must have read/write permissions to the storage location.</span></span> <span data-ttu-id="ce942-121">UE-V Agent は、このルートディレクトリの下にユーザー固有のフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ce942-121">The UE-V Agent will create user-specific folders under this root directory.</span></span> <span data-ttu-id="ce942-122">設定の保存場所は、 **Settingsstoragepath**構成オプションを設定することによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="ce942-122">The settings storage location is defined by setting the **SettingsStoragePath** configuration option.</span></span> <span data-ttu-id="ce942-123">このオプションは、次の方法で構成できます。</span><span class="sxs-lookup"><span data-stu-id="ce942-123">This option can be configured in the following ways:</span></span>

-   <span data-ttu-id="ce942-124">UE-V agent をコマンドラインパラメーターまたはバッチスクリプトを使ってインストールしているとき。</span><span class="sxs-lookup"><span data-stu-id="ce942-124">During the installation of the UE-V agent through a command-line parameter or in a batch script.</span></span>

-   <span data-ttu-id="ce942-125">グループポリシーを使用する。</span><span class="sxs-lookup"><span data-stu-id="ce942-125">Using Group Policy.</span></span>

-   <span data-ttu-id="ce942-126">インストール後、PowerShell または WMI を使用します。</span><span class="sxs-lookup"><span data-stu-id="ce942-126">After installation, by using PowerShell or WMI.</span></span>

<span data-ttu-id="ce942-127">パスは、サーバーと共有の汎用名前付け規則 (UNC) パスに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce942-127">The path must be in a universal naming convention (UNC) path of the server and share.</span></span> <span data-ttu-id="ce942-128">たとえば、 \**\\ ¥ server¥¥ \ \**のように設定します。</span><span class="sxs-lookup"><span data-stu-id="ce942-128">For example, **\\\\server\\settingsshare\\**.</span></span> <span data-ttu-id="ce942-129">この構成オプションは、特定のローミングシナリオを可能にするための変数の使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ce942-129">This configuration option supports the use of variables to enable specific roaming scenarios.</span></span>

<span data-ttu-id="ce942-130">この変数は、 `%username%` サーバーの UNC パスと共有で使うことができます。</span><span class="sxs-lookup"><span data-stu-id="ce942-130">You can use the `%username%` variable with the UNC path of the server and share.</span></span> <span data-ttu-id="ce942-131">これにより、ユーザーがログインするすべてのコンピューターまたはセッションで同じ設定エクスペリエンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="ce942-131">This will provide the same settings experience on all computers or sessions that a user logs into.</span></span> <span data-ttu-id="ce942-132">次のシナリオについては、次の構成を検討してください。</span><span class="sxs-lookup"><span data-stu-id="ce942-132">Consider this configuration for the following scenarios:</span></span>

1.  <span data-ttu-id="ce942-133">組織内のユーザーには、同じように構成された複数の物理コンピューターがあり、各ユーザーの設定は、すべてのコンピューターで同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce942-133">Users in the enterprise have multiple, similarly configured physical computers and each user’s settings should be the same across all computers.</span></span>

2.  <span data-ttu-id="ce942-134">エンタープライズ内のユーザーは、各ユーザーの VDI セッション間で設定を保持する必要がある仮想デスクトップインフラストラクチャ (VDI) プールを使用します。</span><span class="sxs-lookup"><span data-stu-id="ce942-134">Users in the enterprise use virtual desktop infrastructure (VDI) pools where settings should be retained across each user’s VDI sessions.</span></span>

3.  <span data-ttu-id="ce942-135">企業のユーザーには、1つの物理コンピューターがあり、さらに VDI を使用します。</span><span class="sxs-lookup"><span data-stu-id="ce942-135">Users in the enterprise have one physical computer and additionally use a VDI.</span></span> <span data-ttu-id="ce942-136">各ユーザーの設定エクスペリエンスは、物理コンピューターと VDI セッションのどちらを使うかにかかわらず同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce942-136">Each user’s settings experience should be the same whether using the physical computer or VDI session.</span></span>

4.  <span data-ttu-id="ce942-137">複数のエンタープライズコンピューターが複数のユーザーによって使用されている。</span><span class="sxs-lookup"><span data-stu-id="ce942-137">Multiple enterprise computers are used by multiple users.</span></span> <span data-ttu-id="ce942-138">各ユーザーの設定エクスペリエンスは、すべてのコンピューターで同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce942-138">Each user’s settings experience should be the same across all computers.</span></span>

<span data-ttu-id="ce942-139">**%Username%\\%computername%** 変数は、サーバーの UNC パスと共有を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="ce942-139">You can use the **%username%\\%computername%** variables with the UNC path of the server and share.</span></span> <span data-ttu-id="ce942-140">これにより、各コンピューターの設定の操作性が維持されます。</span><span class="sxs-lookup"><span data-stu-id="ce942-140">This will preserve the settings experience for each computer.</span></span> <span data-ttu-id="ce942-141">次のシナリオについては、次の構成を検討してください。</span><span class="sxs-lookup"><span data-stu-id="ce942-141">Consider this configuration for the following scenarios:</span></span>

1.  <span data-ttu-id="ce942-142">組織内のユーザーには、複数の物理コンピューターがあり、各コンピューターの設定を維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce942-142">Users in the enterprise have multiple physical computers and you want to preserve the settings experience for each computer.</span></span>

2.  <span data-ttu-id="ce942-143">エンタープライズコンピューターは、複数のユーザーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="ce942-143">The enterprise computers are used by multiple users.</span></span> <span data-ttu-id="ce942-144">設定エクスペリエンスは、ユーザーがログインする各コンピューターで保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce942-144">The settings experience should be preserved for each computer that the user logs into.</span></span>

<span data-ttu-id="ce942-145">UE-V agent は、UE-V `SettingsStoragePath` 構成の設定と定義されている変数に基づいて、ユーザー固有の設定の記憶域のパスを動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="ce942-145">The UE-V agent dynamically creates the user-specific settings storage path based on a UE-V `SettingsStoragePath` configuration setting and the variables that are defined.</span></span>

<span data-ttu-id="ce942-146">UE-V agent は、ユーザー固有の各記憶域の場所に名前が付けられた非表示のシステムフォルダーを動的に作成し `SettingsPackages` ます。</span><span class="sxs-lookup"><span data-stu-id="ce942-146">The UE-V agent dynamically creates a hidden system folder named `SettingsPackages` within each user-specific storage location.</span></span> <span data-ttu-id="ce942-147">UE-V agent は、登録されている UE-V 設定の場所テンプレートで定義されている場所の設定を読み取り、書き込みを行います。</span><span class="sxs-lookup"><span data-stu-id="ce942-147">The UE-V agent reads and writes settings to this location as defined by registered UE-V settings location templates.</span></span>

<span data-ttu-id="ce942-148">設定の保存場所が、ユーザーの管理されたコンピューターのセットに対して同じである場合は、適用可能な UE-V の設定は "最終書き込み wins" ルールによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="ce942-148">If the settings storage location is the same for a set of managed computers of a user, the applicable UE-V settings are determined by a “Last write wins” rule.</span></span> <span data-ttu-id="ce942-149">1台のコンピューターで実行されるエージェントは、他のコンピューターで実行されているエージェントとは別に、設定の場所の読み取りと書き込みを行います。</span><span class="sxs-lookup"><span data-stu-id="ce942-149">The agent that runs on one computer reads and writes to the settings location independently of agents that run on other computers.</span></span> <span data-ttu-id="ce942-150">記録された最後の設定と値は、次のエージェントが設定の保存場所から読み取りを行うときに適用される設定です。</span><span class="sxs-lookup"><span data-stu-id="ce942-150">The last settings and values written are the settings that are applied when the next agent reads from the settings storage location.</span></span> <span data-ttu-id="ce942-151">詳細については、「 [ue-v 1.0 用の設定の保存場所の配置](deploying-the-settings-storage-location-for-ue-v-10.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce942-151">For more information, see [Deploying the Settings Storage Location for UE-V 1.0](deploying-the-settings-storage-location-for-ue-v-10.md).</span></span>

### <a href="" id="bkmk-usingactivedirectoryhomedirectory"></a><span data-ttu-id="ce942-152">UE-V で Active Directory ホームディレクトリを使用する</span><span class="sxs-lookup"><span data-stu-id="ce942-152">Use Active Directory home directory with UE-V</span></span>

<span data-ttu-id="ce942-153">エージェントが展開されているときに、設定の保存場所が UE-V 用に構成されていない場合は、ユーザーの Active Directory (AD) ホームディレクトリを使用して、設定場所パッケージを保存します。</span><span class="sxs-lookup"><span data-stu-id="ce942-153">If no settings storage location is configured for UE-V when the agent is deployed, then the user’s Active Directory (AD) home directory is used to store settings location packages.</span></span> <span data-ttu-id="ce942-154">UE-V agent は、各ユーザーの AD ホームディレクトリのルートの下に [設定の保存] フォルダーを動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="ce942-154">The UE-V agent dynamically creates the settings storage folder below the root of the AD home directory of each user.</span></span> <span data-ttu-id="ce942-155">エージェントは、設定の保存場所 (SettingsStoragePath) が定義されていない場合にのみ Active Directory ホームディレクトリを使用します。</span><span class="sxs-lookup"><span data-stu-id="ce942-155">The agent only uses the Active Directory home directory if a settings storage location (SettingsStoragePath) is not otherwise defined.</span></span>

## <a href="" id="bkmk-synchronizecomputerclocks"></a><span data-ttu-id="ce942-156">コンピューターの時計を同期させる (UE-V 設定の同期)</span><span class="sxs-lookup"><span data-stu-id="ce942-156">Synchronize computer clocks for UE-V settings synchronization</span></span>


<span data-ttu-id="ce942-157">UE-V agent を実行して設定を同期するコンピューターでは、タイムサーバーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce942-157">Computers that run the UE-V agent to synchronize settings must use a time server.</span></span> <span data-ttu-id="ce942-158">タイムスタンプは、設定の保存場所から設定を同期する必要があるかどうかを判断するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ce942-158">Time stamps are used to determine if settings need to be synchronized from the settings storage location.</span></span> <span data-ttu-id="ce942-159">コンピューターの時計が間違っている場合は、古い設定で新しい設定が上書きされる可能性があります。また、新しい設定が、設定の保存場所に保存されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="ce942-159">If the computer clock is inaccurate, older settings can overwrite newer settings, or the new settings might not be saved to the settings storage location.</span></span> <span data-ttu-id="ce942-160">Time server を使用すると、UE-V で一貫した設定エクスペリエンスを維持できます。</span><span class="sxs-lookup"><span data-stu-id="ce942-160">The use of a time server enables UE-V to maintain a consistent settings experience.</span></span>

## <a href="" id="bkmk-performancecapacityplanning"></a><span data-ttu-id="ce942-161">パフォーマンスとキャパシティの計画</span><span class="sxs-lookup"><span data-stu-id="ce942-161">Performance and capacity planning</span></span>


<span data-ttu-id="ce942-162">UE-V の容量要件は、標準のディスク容量とネットワーク正常性監視を使用して決定できます。</span><span class="sxs-lookup"><span data-stu-id="ce942-162">Capacity requirements for UE-V can be determined by use of standard disk capacity and network health monitoring.</span></span> <span data-ttu-id="ce942-163">UE-V は、設定パッケージの保存にサーバーメッセージブロック (SMB) 共有を使用します。</span><span class="sxs-lookup"><span data-stu-id="ce942-163">UE-V uses a Server Message Block (SMB) share for the storage of settings packages.</span></span> <span data-ttu-id="ce942-164">設定パッケージのサイズは、特定のアプリケーションの設定情報によって異なります。</span><span class="sxs-lookup"><span data-stu-id="ce942-164">The size of settings packages varies depending on the settings information for a specific application.</span></span> <span data-ttu-id="ce942-165">ほとんどの設定パッケージは小さいですが、デスクトップイメージなどの大きなファイルを同期すると、パフォーマンスが低下する可能性があります (特に低速ネットワーク)。</span><span class="sxs-lookup"><span data-stu-id="ce942-165">While most settings packages are small, the synchronization of potentially large files, such as desktop images, can result in poor performance, particularly on slower networks.</span></span> <span data-ttu-id="ce942-166">ネットワーク待ち時間の問題を最小限に抑えるために、ユーザーのコンピューターが存在する同じローカルネットワーク上に設定の保存場所を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ce942-166">To minimize problems with network latency, you should create settings storage locations on the same local networks where the users’ computers reside.</span></span>

<span data-ttu-id="ce942-167">既定では、ネットワークが低速であるか、設定パッケージが大きい場合、UE-V の同期は2秒後にタイムアウトします。</span><span class="sxs-lookup"><span data-stu-id="ce942-167">By default, the UE-V synchronization will time out after 2 seconds if the network is slow or the settings package is large.</span></span> <span data-ttu-id="ce942-168">グループポリシーを使ってタイムアウトを構成できます。</span><span class="sxs-lookup"><span data-stu-id="ce942-168">You can configure the timeout with Group Policy.</span></span> <span data-ttu-id="ce942-169">タイムアウトの設定方法の詳細については、「[グループポリシーオブジェクトを使用](configuring-ue-v-with-group-policy-objects.md)して Ue-v を構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ce942-169">For more information about how to set the timeout, see [Configuring UE-V with Group Policy Objects](configuring-ue-v-with-group-policy-objects.md).</span></span>

## <span data-ttu-id="ce942-170">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ce942-170">Related topics</span></span>


[<span data-ttu-id="ce942-171">Microsoft User Experience Virtualization (UE-V) 1.0</span><span class="sxs-lookup"><span data-stu-id="ce942-171">Microsoft User Experience Virtualization (UE-V) 1.0</span></span>](index.md)

[<span data-ttu-id="ce942-172">UE-V 1.0 の計画</span><span class="sxs-lookup"><span data-stu-id="ce942-172">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

[<span data-ttu-id="ce942-173">UE-V 1.0 でサポートされている構成</span><span class="sxs-lookup"><span data-stu-id="ce942-173">Supported Configurations for UE-V 1.0</span></span>](supported-configurations-for-ue-v-10.md)

 

 





