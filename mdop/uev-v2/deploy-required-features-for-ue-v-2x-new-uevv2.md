---
title: UE-V 2.x の必要な機能を展開する
description: UE-V 2.x の必要な機能を展開する
author: dansimp
ms.assetid: 10399bb3-cc7b-4578-bc0c-2f6b597abe4d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f2123ec75fb151a8f5b836b9b2522a9d6090b043
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824667"
---
# <span data-ttu-id="339eb-103">UE-V 2.x の必要な機能を展開する</span><span class="sxs-lookup"><span data-stu-id="339eb-103">Deploy Required Features for UE-V 2.x</span></span>


<span data-ttu-id="339eb-104">すべての Microsoft User Experience Virtualization (UE-V) 2.0、2.1、2.1 SP1 の展開には、次の機能が必要です。</span><span class="sxs-lookup"><span data-stu-id="339eb-104">All Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 deployments require these features</span></span>

-   <span data-ttu-id="339eb-105">エンドユーザーがアクセスできる[設定の保存場所を展開](#ssl)します。</span><span class="sxs-lookup"><span data-stu-id="339eb-105">[Deploy a Settings Storage Location](#ssl) that is accessible to end users.</span></span>

    <span data-ttu-id="339eb-106">これは、ユーザー設定を保存して取得する標準ネットワーク共有です。</span><span class="sxs-lookup"><span data-stu-id="339eb-106">This is a standard network share that stores and retrieves user settings.</span></span>

-   [<span data-ttu-id="339eb-107">UE-V の構成方法を選択する</span><span class="sxs-lookup"><span data-stu-id="339eb-107">Choose the Configuration Method for UE-V</span></span>](#config)

    <span data-ttu-id="339eb-108">UE-V は、グループポリシー、構成マネージャー、Windows 管理インフラストラクチャ、Powershell などの一般的な管理ツールを使用して展開および構成できます。</span><span class="sxs-lookup"><span data-stu-id="339eb-108">UE-V can be deployed and configured using common management tools including group policy, Configuration Manager, or Windows Management Infrastructure and Powershell.</span></span>

-   <span data-ttu-id="339eb-109">設定を同期するすべてのコンピューターにインストールされる[Ue-v agent を展開](#agent)します。</span><span class="sxs-lookup"><span data-stu-id="339eb-109">[Deploy a UE-V Agent](#agent) to be installed on every computer that synchronizes settings.</span></span>

    <span data-ttu-id="339eb-110">これにより、登録されているアプリケーションとオペレーティングシステムがすべての設定の変更を監視し、コンピューター間でそれらの設定が同期されます。</span><span class="sxs-lookup"><span data-stu-id="339eb-110">This monitors registered applications and the operating system for any settings changes and synchronizes those settings between computers.</span></span>

<span data-ttu-id="339eb-111">このセクションのトピックでは、これらの機能を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="339eb-111">The topics in this section describe how to deploy these features.</span></span>

## <a href="" id="ssl"></a><span data-ttu-id="339eb-112">UE-V の設定の保存場所を展開する</span><span class="sxs-lookup"><span data-stu-id="339eb-112">Deploy a UE-V Settings Storage Location</span></span>


<span data-ttu-id="339eb-113">UE-V では、ユーザー設定を保存する場所を設定パッケージファイルに格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="339eb-113">UE-V requires a location in which to store user settings in settings package files.</span></span> <span data-ttu-id="339eb-114">この設定の保存場所は、次のいずれかの方法で構成できます。</span><span class="sxs-lookup"><span data-stu-id="339eb-114">You can configure this settings storage location in one of these ways:</span></span>

-   <span data-ttu-id="339eb-115">独自の設定の保存場所を作成する</span><span class="sxs-lookup"><span data-stu-id="339eb-115">Create your own settings storage location</span></span>

-   <span data-ttu-id="339eb-116">設定の保存場所に既存の Active Directory を使用する</span><span class="sxs-lookup"><span data-stu-id="339eb-116">Use existing Active Directory for your settings storage location</span></span>

<span data-ttu-id="339eb-117">設定の保存場所を作成しない場合、UE-V Agent では既定で Active Directory (AD) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="339eb-117">If you don’t create a settings storage location, the UE-V Agent will use Active Directory (AD) by default.</span></span>

**<span data-ttu-id="339eb-118">注</span><span class="sxs-lookup"><span data-stu-id="339eb-118">Note</span></span>**  
<span data-ttu-id="339eb-119">[パフォーマンスとキャパシティの計画](https://technet.microsoft.com/library/dn458932.aspx#capacity)の問題で、ネットワーク待ち時間の問題を減らすために、ユーザーのコンピューターが存在する同じローカルネットワーク上に設定の保存場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="339eb-119">As a matter of [performance and capacity planning](https://technet.microsoft.com/library/dn458932.aspx#capacity) and to reduce problems with network latency, create settings storage locations on the same local networks where the users’ computers reside.</span></span> <span data-ttu-id="339eb-120">設定の保存場所については、ユーザー1人につき 20 MB のディスク領域をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="339eb-120">We recommend 20 MB of disk space per user for the settings storage location.</span></span>



### <span data-ttu-id="339eb-121">UE-V の設定の保存場所を作成する</span><span class="sxs-lookup"><span data-stu-id="339eb-121">Create a UE-V Settings Storage Location</span></span>

<span data-ttu-id="339eb-122">設定の保存場所を定義する前に、共有に設定を保存しているユーザーの読み取り/書き込みアクセス許可を持つルートディレクトリを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="339eb-122">Before you define the settings storage location, you must create a root directory with read/write permissions for users who store settings on the share.</span></span> <span data-ttu-id="339eb-123">UE-V Agent は、このルートディレクトリの下にユーザー固有のフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="339eb-123">The UE-V Agent creates user-specific folders under this root directory.</span></span>

<span data-ttu-id="339eb-124">設定の保存場所は、SettingsStoragePath 構成オプションを設定することによって定義されます。これは、次のいずれかの方法を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="339eb-124">The settings storage location is defined by setting the SettingsStoragePath configuration option, which you can configure by using one of these methods:</span></span>

-   <span data-ttu-id="339eb-125">コマンドラインパラメーターまたはバッチスクリプトを使用[して Ue-v agent を展開](#agent)する場合</span><span class="sxs-lookup"><span data-stu-id="339eb-125">When you [Deploy the UE-V Agent](#agent) through a command-line parameter or in a batch script</span></span>

-   <span data-ttu-id="339eb-126">[グループポリシー](https://technet.microsoft.com/library/dn458893.aspx)設定を使用する</span><span class="sxs-lookup"><span data-stu-id="339eb-126">Through [Group Policy](https://technet.microsoft.com/library/dn458893.aspx) settings</span></span>

-   <span data-ttu-id="339eb-127">UE-V の[System Center 構成パック](https://technet.microsoft.com/library/dn458917.aspx)</span><span class="sxs-lookup"><span data-stu-id="339eb-127">With the [System Center Configuration Pack](https://technet.microsoft.com/library/dn458917.aspx) for UE-V</span></span>

-   <span data-ttu-id="339eb-128">UE-V Agent をインストールした後、 [Windows PowerShell または Windows Management Instrumentation (WMI)](https://technet.microsoft.com/library/dn458937.aspx)を使用する</span><span class="sxs-lookup"><span data-stu-id="339eb-128">After installation of the UE-V Agent, by using [Windows PowerShell or Windows Management Instrumentation (WMI)](https://technet.microsoft.com/library/dn458937.aspx)</span></span>

<span data-ttu-id="339eb-129">パスは、サーバーと共有の汎用名前付け規則 (UNC) パスに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="339eb-129">The path must be in a universal naming convention (UNC) path of the server and share.</span></span> <span data-ttu-id="339eb-130">たとえば、 \**\\ ¥ server¥¥ \ \**のように設定します。</span><span class="sxs-lookup"><span data-stu-id="339eb-130">For example, **\\\\Server\\Settingsshare\\**.</span></span> <span data-ttu-id="339eb-131">この構成オプションは、特定の同期シナリオを有効にするための変数の使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="339eb-131">This configuration option supports the use of variables to enable specific synchronization scenarios.</span></span> <span data-ttu-id="339eb-132">たとえば、次のシナリオでは、変数を使用して `%username%\%computername%` エンドユーザーによる設定のエクスペリエンスを維持できます。</span><span class="sxs-lookup"><span data-stu-id="339eb-132">For example, you can use the `%username%\%computername%` variables to preserve the end user settings experience in these scenarios:</span></span>

-   <span data-ttu-id="339eb-133">企業内の複数の物理コンピューターを使用するエンドユーザー</span><span class="sxs-lookup"><span data-stu-id="339eb-133">End users that use multiple physical computers in your enterprise</span></span>

-   <span data-ttu-id="339eb-134">複数のエンドユーザーによって使用されるエンタープライズコンピューター</span><span class="sxs-lookup"><span data-stu-id="339eb-134">Enterprise computers that are used by multiple end users</span></span>

<span data-ttu-id="339eb-135">UE-V Agent は、 `SettingsPackages` **Settingsstoragepath**の構成設定に基づいて、という名前の隠しシステムフォルダーを使って、ユーザー固有の設定の記憶域のパスを動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="339eb-135">The UE-V Agent dynamically creates a user-specific settings storage path, with a hidden system folder named `SettingsPackages`, based on the configuration setting of **SettingsStoragePath**.</span></span> <span data-ttu-id="339eb-136">エージェントは、登録されている UE-V 設定の場所テンプレートで定義されている場所に対して、設定を読み取りおよび書き込みします。</span><span class="sxs-lookup"><span data-stu-id="339eb-136">The agent reads and writes settings to this location as defined by the registered UE-V settings location templates.</span></span>

<span data-ttu-id="339eb-137">**Ue-v の設定は、"最終書き込み wins" ルールによって決定されます。** 設定の保存場所が、複数の管理コンピューターを持つユーザーに対して同じである場合、1つの UE-V Agent は、他のコンピューターで実行されているエージェントとは別に、設定の場所に対して読み取りと書き込みを行います。</span><span class="sxs-lookup"><span data-stu-id="339eb-137">**UE-V settings are determined by a "Last write wins" rule:** If the settings storage location is the same for user with multiple managed computers, one UE-V Agent reads and writes to the settings location independently of agents running on other computers.</span></span> <span data-ttu-id="339eb-138">最後に書き込まれた設定と値は、次のエージェントが設定の保存場所から読み取りを行ったときに適用されるものです。</span><span class="sxs-lookup"><span data-stu-id="339eb-138">The last written settings and values are the ones applied when the next agent reads from the settings storage location.</span></span>

<span data-ttu-id="339eb-139">**設定の保存場所を展開します。** 既存の Active Directory サービスを使うのではなく、設定の保存場所を定義するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="339eb-139">**Deploy the settings storage location:** Follow these steps to define the settings storage location rather than using your existing Active Directory service.</span></span> <span data-ttu-id="339eb-140">次の表に示すように、設定の記憶域の共有へのアクセスを必要とするユーザーだけに制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="339eb-140">You should limit access to the settings storage share to those users that require it, as shown in the tables below.</span></span>

**<span data-ttu-id="339eb-141">UE-V ネットワーク共有を展開するには</span><span class="sxs-lookup"><span data-stu-id="339eb-141">To deploy the UE-V network share</span></span>**

1.  <span data-ttu-id="339eb-142">UE-V ユーザーの新しいセキュリティグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="339eb-142">Create a new security group for UE-V users.</span></span>

2.  <span data-ttu-id="339eb-143">UE-V 設定パッケージが保存されている中央のコンピューターに新しいフォルダーを作成し、そのフォルダーへのグループアクセス許可を使用して、UE-V ユーザーにアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="339eb-143">Create a new folder on the centrally located computer that stores the UE-V settings packages, and then grant the UE-V users access with group permissions to the folder.</span></span> <span data-ttu-id="339eb-144">UE-V をサポートしている管理者は、この共有フォルダーへのアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="339eb-144">The administrator who supports UE-V must have permissions to this shared folder.</span></span>

3.  <span data-ttu-id="339eb-145">[設定の保存場所] フォルダーに対して、次の共有レベルのサーバーメッセージブロック (SMB) 権限を設定します。</span><span class="sxs-lookup"><span data-stu-id="339eb-145">Set the following share-level Server Message Block (SMB) permissions for the settings storage location folder.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="339eb-146">ユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="339eb-146">User account</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="339eb-147">推奨されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="339eb-147">Recommended permissions</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="339eb-148">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="339eb-148">Everyone</span></span></p></td>
    <td align="left"><p><span data-ttu-id="339eb-149">権限なし</span><span class="sxs-lookup"><span data-stu-id="339eb-149">No permissions</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="339eb-150">UE-V ユーザーのセキュリティグループ</span><span class="sxs-lookup"><span data-stu-id="339eb-150">Security group of UE-V users</span></span></p></td>
    <td align="left"><p><span data-ttu-id="339eb-151">フルコントロール</span><span class="sxs-lookup"><span data-stu-id="339eb-151">Full control</span></span></p></td>
    </tr>
    </tbody>
    </table>



4.  <span data-ttu-id="339eb-152">[設定の保存場所] フォルダーに、次の NTFS ファイルシステムの権限を設定します。</span><span class="sxs-lookup"><span data-stu-id="339eb-152">Set the following NTFS file system permissions for the settings storage location folder.</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="339eb-153">ユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="339eb-153">User account</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="339eb-154">推奨されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="339eb-154">Recommended permissions</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="339eb-155">Folder</span><span class="sxs-lookup"><span data-stu-id="339eb-155">Folder</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="339eb-156">作成者/所有者</span><span class="sxs-lookup"><span data-stu-id="339eb-156">Creator/owner</span></span></p></td>
    <td align="left"><p><span data-ttu-id="339eb-157">フルコントロール</span><span class="sxs-lookup"><span data-stu-id="339eb-157">Full control</span></span></p></td>
    <td align="left"><p><span data-ttu-id="339eb-158">サブフォルダーとファイルのみ</span><span class="sxs-lookup"><span data-stu-id="339eb-158">Subfolders and files only</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="339eb-159">UE-V ユーザーのセキュリティグループ</span><span class="sxs-lookup"><span data-stu-id="339eb-159">Security group of UE-V users</span></span></p></td>
    <td align="left"><p><span data-ttu-id="339eb-160">フォルダーの一覧/データの読み取り、フォルダーの作成/データの追加を行う</span><span class="sxs-lookup"><span data-stu-id="339eb-160">List folder/read data, create folders/append data</span></span></p></td>
    <td align="left"><p><span data-ttu-id="339eb-161">このフォルダーのみ</span><span class="sxs-lookup"><span data-stu-id="339eb-161">This folder only</span></span></p></td>
    </tr>
    </tbody>
    </table>



<span data-ttu-id="339eb-162">この構成では、UE-V Agent はユーザーのコンテキストで実行されているときに Settingspackage フォルダーを作成して、セキュリティで保護し、各ユーザーに設定ストレージのフォルダーを作成するためのアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="339eb-162">With this configuration, the UE-V Agent creates and secures a Settingspackage folder while it runs in the context of the user, and grants each user permission to create folders for settings storage.</span></span> <span data-ttu-id="339eb-163">ユーザーは、他のユーザーがアクセスできない Settingspackage フォルダーに対してフルコントロールを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="339eb-163">Users receive full control to their Settingspackage folder while other users cannot access it.</span></span>

**<span data-ttu-id="339eb-164">注</span><span class="sxs-lookup"><span data-stu-id="339eb-164">Note</span></span>**  
<span data-ttu-id="339eb-165">Windows Server オペレーティングシステムを実行しているコンピューターで設定記憶域共有を作成する場合は、UE-V を構成して、ローカル管理者グループまたは現在のユーザーが、設定パッケージが保存されているフォルダーの所有者であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="339eb-165">If you create the settings storage share on a computer running a Windows Server operating system, configure UE-V to verify that either the local Administrators group or the current user is the owner of the folder where settings packages are stored.</span></span> <span data-ttu-id="339eb-166">この追加のセキュリティを有効にするには、Windows Server レジストリエディターで次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="339eb-166">To enable this additional security, specify this setting in the Windows Server Registry Editor:</span></span>

1.  <span data-ttu-id="339eb-167">**"RepositoryOwnerCheckEnabled"** という名前の**REG \ _DWORD**のレジストリキーを**HKEY \ _LOCAL \ _MACHINE ¥**$ ¥の設定に追加します。</span><span class="sxs-lookup"><span data-stu-id="339eb-167">Add a **REG\_DWORD** registry key named **"RepositoryOwnerCheckEnabled"** to **HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\UEV\\Agent\\Configuration**.</span></span>

2.  <span data-ttu-id="339eb-168">レジストリキーの値を*1*に設定します。</span><span class="sxs-lookup"><span data-stu-id="339eb-168">Set the registry key value to *1*.</span></span>



### <span data-ttu-id="339eb-169">UE-V 2 x で Active Directory を使用する</span><span class="sxs-lookup"><span data-stu-id="339eb-169">Use Active Directory with UE-V 2.x</span></span>

<span data-ttu-id="339eb-170">UE-V Agent では、設定の保存場所が定義されていない場合、既定で Active Directory (AD) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="339eb-170">The UE-V Agent uses Active Directory (AD) by default if a settings storage location is not otherwise defined.</span></span> <span data-ttu-id="339eb-171">このような場合、UE-V Agent では、各ユーザーの AD ホームディレクトリのルートの下に [設定の保存] フォルダーが動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="339eb-171">In these cases, the UE-V Agent dynamically creates the settings storage folder under the root of the AD home directory of each user.</span></span> <span data-ttu-id="339eb-172">ただし、カスタムディレクトリ設定が AD で構成されている場合は、代わりにそのディレクトリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="339eb-172">But, if a custom directory setting is configured in AD, then that directory is used instead.</span></span>

## <a href="" id="config"></a><span data-ttu-id="339eb-173">UE-V 2. x の構成方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="339eb-173">Choose the Configuration Method for UE-V 2.x</span></span>


<span data-ttu-id="339eb-174">展開後に UE-V を管理するために使用する構成方法を理解する必要があります。これは、UE-V Agent の展開に使用する構成方法になります。</span><span class="sxs-lookup"><span data-stu-id="339eb-174">You want to figure out which configuration method you'll use to manage UE-V after deployment since this will be the configuration method you use to deploy the UE-V Agent.</span></span> <span data-ttu-id="339eb-175">通常、これは、Windows PowerShell や Configuration Manager など、環境で既に使用している構成方法です。</span><span class="sxs-lookup"><span data-stu-id="339eb-175">Typically, this is the configuration method that you already use in your environment, such as Windows PowerShell or Configuration Manager.</span></span>

<span data-ttu-id="339eb-176">使用している構成方法によっては、UE-V Agent をインストールする前、実行中、または後で UE-V を構成できます。</span><span class="sxs-lookup"><span data-stu-id="339eb-176">You can configure UE-V before, during, or after UE-V Agent installation, depending on the configuration method that you use.</span></span>

-   <span data-ttu-id="339eb-177">[グループポリシー](https://technet.microsoft.com/library/dn458893.aspx)**:** 既存のグループポリシーインフラストラクチャを使用して、ue-v エージェントの展開前または後の ue-v を構成できます。</span><span class="sxs-lookup"><span data-stu-id="339eb-177">[Group Policy](https://technet.microsoft.com/library/dn458893.aspx)**:** You can use your existing Group Policy infrastructure to configure UE-V before or after UE-V Agent deployment.</span></span> <span data-ttu-id="339eb-178">UE-V グループポリシー ADMX テンプレートを使用すると、一般的な UE-V Agent 構成オプションの中央管理を有効にすることができます。また、UE-V の同期を構成する設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="339eb-178">The UE-V Group Policy ADMX template enables the central management of common UE-V Agent configuration options, and it includes settings to configure UE-V synchronization.</span></span>

    <span data-ttu-id="339eb-179">**Ue-v グループポリシーの ADMX テンプレートをインストールする:** UE-V のグループポリシー ADMX テンプレートでは、UE-V エージェントの同期設定を構成し、既存のグループポリシーインフラストラクチャを使用して、共通の UE-V エージェント構成設定の中央管理を有効にします。</span><span class="sxs-lookup"><span data-stu-id="339eb-179">**Installing the UE-V Group Policy ADMX Templates:** Group Policy ADMX templates for UE-V configure the synchronization settings for the UE-V Agent and enable the central management of common UE-V Agent configuration settings by using an existing Group Policy infrastructure.</span></span>

    <span data-ttu-id="339eb-180">グループポリシーオブジェクトを展開するドメインコントローラーでサポートされているオペレーティングシステムには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="339eb-180">Supported operating systems for the domain controller that deploys the Group Policy Objects include the following:</span></span>

    <span data-ttu-id="339eb-181">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="339eb-181">Windows Server 2008 R2</span></span>

    <span data-ttu-id="339eb-182">Windows Server 2012 および Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="339eb-182">Windows Server 2012 and Windows Server 2012 R2</span></span>

-   <span data-ttu-id="339eb-183">[構成マネージャー](https://technet.microsoft.com/library/dn458917.aspx)**:** ue-v 構成パックを使用すると、System Center configuration manager 2012 SP1 以降のコンプライアンス設定機能を使用して、ue-v および Configuration manager がインストールされているサイト間で一貫した構成を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="339eb-183">[Configuration Manager](https://technet.microsoft.com/library/dn458917.aspx)**:** The UE-V Configuration Pack lets you use the Compliance Settings feature of System Center Configuration Manager 2012 SP1 or later to apply consistent configurations across sites where UE-V and Configuration Manager are installed.</span></span>

-   <span data-ttu-id="339eb-184">[Windows powershell と wmi](https://technet.microsoft.com/library/dn458937.aspx)**:** windows powershell 用のスクリプトコマンドと windows Management Instrumentation (WMI) を使って、ue-v agent をインストールした後に構成を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="339eb-184">[Windows PowerShell and WMI](https://technet.microsoft.com/library/dn458937.aspx)**:** You can use scripted commands for Windows PowerShell and Windows Management Instrumentation (WMI) to modify configurations after you install the UE-V Agent.</span></span>

    **<span data-ttu-id="339eb-185">注</span><span class="sxs-lookup"><span data-stu-id="339eb-185">Note</span></span>**  
    <span data-ttu-id="339eb-186">レジストリの変更が原因でデータが失われる、またはコンピューターが応答しなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="339eb-186">Registry modification can result in data loss, or the computer becomes unresponsive.</span></span> <span data-ttu-id="339eb-187">他の構成方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="339eb-187">We recommend that you use other configuration methods.</span></span>



-   <span data-ttu-id="339eb-188">**コマンドラインまたはバッチスクリプトのインストール:**[Ue-v agent を展開](#agent)するときに使用されるパラメーターによって、多くの ue-v の設定が構成されます。</span><span class="sxs-lookup"><span data-stu-id="339eb-188">**Command-line or Batch Script Installation:** Parameters that are used when you [Deploy the UE-V Agent](#agent) configure many UE-V settings.</span></span> <span data-ttu-id="339eb-189">System Center 2012 構成マネージャーなどの電子ソフトウェア配布システムでは、これらのパラメーターを使用して、UE-V Agent ソフトウェアを展開してインストールするときにクライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="339eb-189">Electronic software distribution systems, such as System Center 2012 Configuration Manager, use these parameters to configure their clients when they deploy and install the UE-V Agent software.</span></span>

## <a href="" id="agent"></a><span data-ttu-id="339eb-190">UE-V Agent を展開する</span><span class="sxs-lookup"><span data-stu-id="339eb-190">Deploy the UE-V 2.x Agent</span></span>


<span data-ttu-id="339eb-191">UE-V Agent は、ue-v の展開の中核であり、アプリケーションと Windows の設定を同期するために UE-V を使用する各コンピューターで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="339eb-191">The UE-V Agent is the core of a UE-V deployment and must run on each computer that uses UE-V to synchronize application and Windows settings.</span></span>

<span data-ttu-id="339eb-192">**Ue-v agent のインストールファイル:** 1つのインストールファイル (AgentSetup.exe) は、32ビットと64ビットの両方のオペレーティングシステムに UE-V エージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="339eb-192">**UE-V Agent Installation Files:** A single installation file, AgentSetup.exe, installs the UE-V Agent on both 32-bit and 64-bit operating systems.</span></span> <span data-ttu-id="339eb-193">また、AgentSetupx86.msi または AgentSetupx64.msi アーキテクチャ固有の Windows インストーラーファイルが用意されているため、それが小さいため、エージェントの展開が合理化される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="339eb-193">In addition, AgentSetupx86.msi or AgentSetupx64.msi architecture-specific Windows Installer files are provided, and since they are smaller, they might streamline the agent deployments.</span></span> <span data-ttu-id="339eb-194">[AgentSetup.exe installer のコマンドラインパラメーター](#params)も、Windows インストーラーのインストールでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="339eb-194">The [command-line parameters for the AgentSetup.exe installer](#params) are supported for the Windows Installer installation as well.</span></span>

**<span data-ttu-id="339eb-195">重要</span><span class="sxs-lookup"><span data-stu-id="339eb-195">Important</span></span>**  
<span data-ttu-id="339eb-196">UE-V Agent のインストールまたはアンインストール時には、AgentSetup.exe ファイルまたは AgentSetup arch ファイルは使用できますが、両方を使用することはでき &lt; &gt; ません。</span><span class="sxs-lookup"><span data-stu-id="339eb-196">During UE-V Agent installation or uninstallation, you can either use the AgentSetup.exe file or the AgentSetup&lt;arch&gt;.msi file, but not both.</span></span> <span data-ttu-id="339eb-197">UE-V Agent のインストールに使用した UE-V エージェントをアンインストールするには、同じファイルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="339eb-197">The same file must be used to uninstall the UE-V Agent that was used to install the UE-V Agent.</span></span>



### <span data-ttu-id="339eb-198">UE-V エージェントを展開するには</span><span class="sxs-lookup"><span data-stu-id="339eb-198">To Deploy the UE-V Agent</span></span>

<span data-ttu-id="339eb-199">UE-V Agent を展開するには、次のメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="339eb-199">You can use the following methods to deploy the UE-V Agent:</span></span>

-   <span data-ttu-id="339eb-200">Windows Installer (.msi) ファイルをインストールできる、構成マネージャーなどの電子ソフトウェア配布 (ESD) ソリューションシステム。</span><span class="sxs-lookup"><span data-stu-id="339eb-200">An electronic software distribution (ESD) solution system, such as Configuration Manager, that can install a Windows Installer (.msi) file.</span></span>

-   <span data-ttu-id="339eb-201">共有に一元的に保存されている Windows Installer (.msi) ファイルを参照するインストールスクリプト。</span><span class="sxs-lookup"><span data-stu-id="339eb-201">An installation script that references the Windows Installer (.msi) file that is stored centrally on a share.</span></span>

-   <span data-ttu-id="339eb-202">コンピューターで手動で実行するインストールプログラム。</span><span class="sxs-lookup"><span data-stu-id="339eb-202">An installation program that you run manually on the computer.</span></span>

<span data-ttu-id="339eb-203">ネットワーク共有から UE-V Agent を展開するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="339eb-203">Use the following procedure to deploy the UE-V Agent from a network share.</span></span>

**<span data-ttu-id="339eb-204">ネットワーク共有から UE-V Agent をインストールして構成するには</span><span class="sxs-lookup"><span data-stu-id="339eb-204">To install and configure the UE-V Agent from a network share</span></span>**

1.  <span data-ttu-id="339eb-205">UE-V Agent インストールファイル AgentSetup.exe、ユーザーが読み取りアクセス許可を持つネットワーク共有上にステージングします。</span><span class="sxs-lookup"><span data-stu-id="339eb-205">Stage the UE-V Agent installation file AgentSetup.exe on a network share to which users have Read permission.</span></span>

2.  <span data-ttu-id="339eb-206">UE-V Agent をインストールするユーザーコンピューターにスクリプトを展開します。</span><span class="sxs-lookup"><span data-stu-id="339eb-206">Deploy a script to user computers that installs the UE-V Agent.</span></span> <span data-ttu-id="339eb-207">スクリプトでは、設定の保存場所を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="339eb-207">The script should specify the settings storage location.</span></span>

<span data-ttu-id="339eb-208">**展開オプション:** UE-V Agent をインストールする場合は、必ず正しい変数形式を使用してください。</span><span class="sxs-lookup"><span data-stu-id="339eb-208">**Deployment options:** Be sure to use the correct variable format when you install the UE-V Agent.</span></span> <span data-ttu-id="339eb-209">次の表では、AgentSetup.exe または Windows Installer (.msi) ファイルを使用するための展開オプションの例を示します。</span><span class="sxs-lookup"><span data-stu-id="339eb-209">The following table provides examples of deployment options for using the AgentSetup.exe or the Windows Installer (.msi) files.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="339eb-210">展開の種類</span><span class="sxs-lookup"><span data-stu-id="339eb-210">Deployment type</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="339eb-211">展開の説明</span><span class="sxs-lookup"><span data-stu-id="339eb-211">Deployment description</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="339eb-212">例</span><span class="sxs-lookup"><span data-stu-id="339eb-212">Example</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="339eb-213">コマンドプロンプト</span><span class="sxs-lookup"><span data-stu-id="339eb-213">Command prompt</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-214">コマンドプロンプトで UE-V Agent をインストールする場合は、 <em> % ^ username% 変数形式を使用し </em> ます。</span><span class="sxs-lookup"><span data-stu-id="339eb-214">When you install the UE-V Agent at a command prompt, use the <em>%^username%</em> variable format.</span></span> <span data-ttu-id="339eb-215">設定の記憶域のパスにスペースが含まれているために引用符が必要な場合は、展開用のバッチスクリプトファイルを使います。</span><span class="sxs-lookup"><span data-stu-id="339eb-215">If quotation marks are required because of spaces in the settings storage path, use a batch script file for deployment.</span></span></p>
<p></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="339eb-216">バッチスクリプト</span><span class="sxs-lookup"><span data-stu-id="339eb-216">Batch script</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-217">UE-V Agent をバッチスクリプトファイルからインストールする場合は、 <em> %% username%% 変数形式を使い </em> ます。</span><span class="sxs-lookup"><span data-stu-id="339eb-217">When you install the UE-V Agent from a batch script file, use the <em>%%username%%</em> variable format.</span></span> <span data-ttu-id="339eb-218">このインストール方法を使う場合は、%% 文字の変数をエスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="339eb-218">If you use this installation method, you must escape the variable with the %% characters.</span></span> <span data-ttu-id="339eb-219">この文字がないと、スクリプトは <em> 実行時ではなく、インストール時にユーザー名変数を展開し </em> ます。これにより、ue-v は、すべてのユーザーに対して1つの設定の保存場所を使用します。</span><span class="sxs-lookup"><span data-stu-id="339eb-219">Without this character, the script expands the <em>username</em> variable at installation time, rather than at run time, which causes UE-V to use a single settings storage location for all users.</span></span></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="339eb-220">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="339eb-220">Windows PowerShell</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-221">Windows PowerShell プロンプトまたは Windows PowerShell スクリプトから UE-V Agent をインストールする場合は、 <em> % username% 変数形式を使用し </em> ます。</span><span class="sxs-lookup"><span data-stu-id="339eb-221">When you install the UE-V Agent from a Windows PowerShell prompt or a Windows PowerShell script, use the <em>%username%</em> variable format.</span></span></p></td>
<td align="left"><p><code>&amp; AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p>
<p><code>&amp; msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="339eb-222">Configuration Manager ソフトウェアの展開などの電子ソフトウェアの配布</span><span class="sxs-lookup"><span data-stu-id="339eb-222">Electronic software distribution, such as deployment of Configuration Manager Software Deployment</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-223">Configuration Manager を使用して UE-V Agent をインストールする場合は、 <em> ^% username ^% </em> 変数形式を使います。</span><span class="sxs-lookup"><span data-stu-id="339eb-223">When you install the UE-V Agent by using Configuration Manager, use the <em>^%username^%</em> variable format.</span></span></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="339eb-224">注</span><span class="sxs-lookup"><span data-stu-id="339eb-224">Note</span></span>**  
<span data-ttu-id="339eb-225">UE-V エージェントをインストールするには、管理者権限が必要です。 UE-V Agent を実行するには、コンピューターの再起動が必要です。</span><span class="sxs-lookup"><span data-stu-id="339eb-225">The installation of the UE-V Agent requires administrator rights, and the computer requires a restart before the UE-V Agent can run.</span></span>



### <a href="" id="params"></a><span data-ttu-id="339eb-226">UE-V エージェントの展開用のコマンドラインパラメーター</span><span class="sxs-lookup"><span data-stu-id="339eb-226">Command-line parameters for UE-V Agent deployment</span></span>

<span data-ttu-id="339eb-227">UE-V Agent のコマンドラインパラメーターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="339eb-227">The command-line parameters of the UE-V Agent are as follows.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="339eb-228">コマンドラインパラメーター</span><span class="sxs-lookup"><span data-stu-id="339eb-228">Command-line parameter</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="339eb-229">定義</span><span class="sxs-lookup"><span data-stu-id="339eb-229">Definition</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="339eb-230">備考</span><span class="sxs-lookup"><span data-stu-id="339eb-230">Notes</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="339eb-231">/help または/h または/?</span><span class="sxs-lookup"><span data-stu-id="339eb-231">/help or /h or /?</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-232">[AgentSetup.exe 使用状況] ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="339eb-232">Displays the AgentSetup.exe usage dialog box.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="339eb-233">SettingsStoragePath</span><span class="sxs-lookup"><span data-stu-id="339eb-233">SettingsStoragePath</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-234">設定が保存される場所を定義する汎用名前付け規則 (UNC) パスを示します。</span><span class="sxs-lookup"><span data-stu-id="339eb-234">Indicates the Universal Naming Convention (UNC) path that defines where settings are stored.</span></span></p></td>
<td align="left"><div class="alert">
<strong><span data-ttu-id="339eb-235">重要</span><span class="sxs-lookup"><span data-stu-id="339eb-235">Important</span></span></strong><br/><p><span data-ttu-id="339eb-236">UE-V 2.1 および UE-V 2.1 SP1 では、SettingsStoragePath を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="339eb-236">You must specify a SettingsStoragePath in UE-V 2.1 and UE-V 2.1 SP1.</span></span> <span data-ttu-id="339eb-237">Adhome Path 文字列を設定して、ユーザー&#39;s の Active Directory ホームパスを使用することを指定できます。</span><span class="sxs-lookup"><span data-stu-id="339eb-237">You can set the AdHomePath string to specify that the user&#39;s Active Directory home path is used.</span></span> <span data-ttu-id="339eb-238">(<code>SettingsStoragePath = \share\path|AdHomePath</code> など)。</span><span class="sxs-lookup"><span data-stu-id="339eb-238">For example, <code>SettingsStoragePath = \share\path|AdHomePath</code>.</span></span></p>
<p><span data-ttu-id="339eb-239">UE-V 2.0 では、SettingsStoragePath を空のままにして、代わりに Active Directory ホームパスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="339eb-239">In UE-V 2.0, you can leave SettingsStoragePath blank to use the Active Directory home path instead.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="339eb-240">% username% または% computername% の環境変数が受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="339eb-240">%username% or %computername% environment variables are accepted.</span></span> <span data-ttu-id="339eb-241">スクリプトでは、変数をエスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="339eb-241">Scripting can require escaped variables.</span></span></p>
<p><strong><span data-ttu-id="339eb-242">既定値 </strong> : &lt; なし&gt;</span><span class="sxs-lookup"><span data-stu-id="339eb-242">Default</strong>: &lt;none&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="339eb-243">Settingsstoragepaん g</span><span class="sxs-lookup"><span data-stu-id="339eb-243">SettingsStoragePathReg</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-244">インストール時にレジストリから SettingsStoragePath の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="339eb-244">Gets the SettingsStoragePath value from the registry during installation.</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-245">コマンドプロンプトで、次の例を入力して、特定の UNC ではなく Active Directory のホームパスを強制的に使用するように指定します。</span><span class="sxs-lookup"><span data-stu-id="339eb-245">At the command prompt, type the following example to force UE-V to use the Active Directory home path instead of a specific UNC.</span></span></p>
<p><code>msiexec.exe /i AgentSetupx64.msi acceptlicenseterms=true SettingsStoragePathReg=TRUE /quiet /norestart</code></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="339eb-246">SettingsTemplateCatalogPath</span><span class="sxs-lookup"><span data-stu-id="339eb-246">SettingsTemplateCatalogPath</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-247">新しい設定場所テンプレートがチェックされた場所を定義する汎用名前付け規則 (UNC) パスを示します。</span><span class="sxs-lookup"><span data-stu-id="339eb-247">Indicates the Universal Naming Convention (UNC) path that defines the location that was checked for new settings location templates.</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-248">カスタム設定の場所テンプレートでのみ必須</span><span class="sxs-lookup"><span data-stu-id="339eb-248">Only required for custom settings location templates</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="339eb-249">RegisterMSTemplates</span><span class="sxs-lookup"><span data-stu-id="339eb-249">RegisterMSTemplates</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-250">インストール時に既定の Microsoft テンプレートを登録する必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="339eb-250">Specifies whether the default Microsoft templates should be registered during installation.</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-251">True |返し</span><span class="sxs-lookup"><span data-stu-id="339eb-251">True | False</span></span></p>
<p><strong><span data-ttu-id="339eb-252">既定値 </strong> : True</span><span class="sxs-lookup"><span data-stu-id="339eb-252">Default</strong>: True</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="339eb-253">方法</span><span class="sxs-lookup"><span data-stu-id="339eb-253">SyncMethod</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-254">使用する同期方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="339eb-254">Specifies which synchronization method should be used.</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-255">SyncProvider |-</span><span class="sxs-lookup"><span data-stu-id="339eb-255">SyncProvider | None</span></span></p>
<p><strong><span data-ttu-id="339eb-256">既定 </strong> : syncprovider</span><span class="sxs-lookup"><span data-stu-id="339eb-256">Default</strong>: SyncProvider</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="339eb-257">SyncTimeoutInMilliseconds</span><span class="sxs-lookup"><span data-stu-id="339eb-257">SyncTimeoutInMilliseconds</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-258">コンピューターが設定の保存場所からユーザー設定を取得したときにタイムアウトするまでの時間 (ミリ秒単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="339eb-258">Specifies the number of milliseconds that the computer waits before time-out when it retrieves user settings from the settings storage location.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="339eb-259">既定値 </strong> : 2000 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="339eb-259">Default</strong>: 2000 milliseconds</span></span></p>
<p><span data-ttu-id="339eb-260">(最大2秒待ちます)</span><span class="sxs-lookup"><span data-stu-id="339eb-260">(wait up to 2 seconds)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="339eb-261">SyncEnabled</span><span class="sxs-lookup"><span data-stu-id="339eb-261">SyncEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-262">UE-V の同期を有効にするか、無効にするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="339eb-262">Specifies whether UE-V synchronization is enabled or disabled.</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-263">True |返し</span><span class="sxs-lookup"><span data-stu-id="339eb-263">True | False</span></span></p>
<p><strong><span data-ttu-id="339eb-264">既定値 </strong> : True</span><span class="sxs-lookup"><span data-stu-id="339eb-264">Default</strong>: True</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="339eb-265">Maxパッケージパッケージ</span><span class="sxs-lookup"><span data-stu-id="339eb-265">MaxPackageSizeInBytes</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-266">UE-V Agent でファイルのしきい値を超えたことを報告した場合に、設定パッケージのファイルサイズをバイト単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="339eb-266">Specifies a settings package file size in bytes when the UE-V Agent reports that files exceed the threshold.</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-267">&lt;大きさ&gt;</span><span class="sxs-lookup"><span data-stu-id="339eb-267">&lt;size&gt;</span></span></p>
<p><strong><span data-ttu-id="339eb-268">既定値 </strong> : なし (警告のしきい値なし)</span><span class="sxs-lookup"><span data-stu-id="339eb-268">Default</strong>: none (no warning threshold)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="339eb-269">CEIPEnabled</span><span class="sxs-lookup"><span data-stu-id="339eb-269">CEIPEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-270">カスタマーエクスペリエンス向上プログラムに参加するための設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="339eb-270">Specifies the setting for participation in the Customer Experience Improvement program.</span></span> <span data-ttu-id="339eb-271">True に設定 <strong> する </strong> と、インストーラー情報が Microsoft カスタマーエクスペリエンス向上プログラムのサイトにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="339eb-271">If set to <strong>True</strong>, installer information is uploaded to the Microsoft Customer Experience Improvement Program site.</span></span> <span data-ttu-id="339eb-272">False に設定 <strong> する </strong> と、情報はアップロードされません。</span><span class="sxs-lookup"><span data-stu-id="339eb-272">If set to <strong>False</strong>, no information is uploaded.</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-273">True |返し</span><span class="sxs-lookup"><span data-stu-id="339eb-273">True | False</span></span></p>
<p><strong><span data-ttu-id="339eb-274">既定値 </strong> : False</span><span class="sxs-lookup"><span data-stu-id="339eb-274">Default</strong>: False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="339eb-275">NoRestart</span><span class="sxs-lookup"><span data-stu-id="339eb-275">NoRestart</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-276">UE-V エージェントがインストールされた後のコンピューターの再起動の遅延をサポートします。</span><span class="sxs-lookup"><span data-stu-id="339eb-276">Supports deferral of the restart of the computer after the UE-V Agent is installed.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="339eb-277">INSTALLFOLDER</span><span class="sxs-lookup"><span data-stu-id="339eb-277">INSTALLFOLDER</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-278">UE-V Generator または UE-V Generator で別のインストールフォルダーを設定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="339eb-278">Enables a different installation folder to be set for the UE-V Agent or UE-V Generator.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="339eb-279">MUENABLED</span><span class="sxs-lookup"><span data-stu-id="339eb-279">MUENABLED</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-280">セットアップで、Microsoft Update プログラムに含まれるオプションを受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="339eb-280">Enables Setup to accept the option to be included in the Microsoft Update program.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="339eb-281">ACCEPTLICENSETERMS</span><span class="sxs-lookup"><span data-stu-id="339eb-281">ACCEPTLICENSETERMS</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-282">UE-V をサイレントインストールできるようにします。</span><span class="sxs-lookup"><span data-stu-id="339eb-282">Lets UE-V be installed silently.</span></span> <span data-ttu-id="339eb-283"><strong> </strong> Ue-v をサイレントインストールして、ユーザーが ue-v ライセンス条項を受け入れるという要件を回避するには、この設定を True にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="339eb-283">This must be set to <strong>True</strong> to install UE-V silently and bypass the requirement that the user accepts the UE-V license terms.</span></span> <span data-ttu-id="339eb-284">False に設定 <strong> する </strong> か、空白のままにすると、エラーメッセージが表示され、ue-v はインストールされません。</span><span class="sxs-lookup"><span data-stu-id="339eb-284">If set to <strong>False</strong> or left empty, the user receives an error message and UE-V is not installed.</span></span></p></td>
<td align="left"><div class="alert">
<strong><span data-ttu-id="339eb-285">重要</span><span class="sxs-lookup"><span data-stu-id="339eb-285">Important</span></span></strong><br/><p><span data-ttu-id="339eb-286">UE-V をサイレントモードでインストールする場合は、このパラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="339eb-286">This parameter is required to install UE-V silently.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="339eb-287">NORESTART</span><span class="sxs-lookup"><span data-stu-id="339eb-287">NORESTART</span></span></p></td>
<td align="left"><p><span data-ttu-id="339eb-288">UE-V エージェントをインストールした後に、必須の再起動が行われないようにします。</span><span class="sxs-lookup"><span data-stu-id="339eb-288">Prevents a mandatory restart after the UE-V Agent is installed.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="339eb-289">UE-V Agent を更新する</span><span class="sxs-lookup"><span data-stu-id="339eb-289">Update the UE-V Agent</span></span>

<span data-ttu-id="339eb-290">UE-V Agent ソフトウェアの更新プログラムは、Microsoft Update を通じて提供されます。</span><span class="sxs-lookup"><span data-stu-id="339eb-290">Updates for the UE-V Agent software are provided through Microsoft Update.</span></span> <span data-ttu-id="339eb-291">UE-V Agent の更新プログラムを展開するには、エンタープライズソフトウェア配布 (ESD) インフラストラクチャシステムを使用します。</span><span class="sxs-lookup"><span data-stu-id="339eb-291">You can deploy UE-V Agent updates by using Enterprise Software Distribution (ESD) infrastructure systems.</span></span>

<span data-ttu-id="339eb-292">UE-V Agent のアップグレード中に、一般的な Microsoft アプリケーションと Windows 設定用の設定場所テンプレートの既定のグループが更新されることがあります。</span><span class="sxs-lookup"><span data-stu-id="339eb-292">During a UE-V Agent upgrade, the default group of settings location templates for common Microsoft applications and Windows settings can be updated.</span></span>

### <span data-ttu-id="339eb-293">UE-V Agent をアップグレードする</span><span class="sxs-lookup"><span data-stu-id="339eb-293">Upgrade the UE-V 2.x Agent</span></span>

<span data-ttu-id="339eb-294">UE-V Agent では、さまざまな新機能が導入され、エージェントが設定記憶域の共有にコンテンツをアップロードする方法とタイミングが変更されます。</span><span class="sxs-lookup"><span data-stu-id="339eb-294">The UE-V 2.x Agent introduces many new features and modifies how and when the agent uploads content to the settings storage share.</span></span> <span data-ttu-id="339eb-295">アップグレードプロセスによって、これらの変更が自動化されます。</span><span class="sxs-lookup"><span data-stu-id="339eb-295">The upgrade process automates these changes.</span></span> <span data-ttu-id="339eb-296">UE-V Agent をアップグレードするには、ユーザーのコンピューターで UE-V Agent インストールパッケージ (AgentSetup.exe、AgentSetupx86.msi、または AgentSetupx64.msi) を実行します。</span><span class="sxs-lookup"><span data-stu-id="339eb-296">To upgrade the UE-V Agent, run the UE-V Agent install package (AgentSetup.exe, AgentSetupx86.msi, or AgentSetupx64.msi) on users’ computers.</span></span>

**<span data-ttu-id="339eb-297">注</span><span class="sxs-lookup"><span data-stu-id="339eb-297">Note</span></span>**  
<span data-ttu-id="339eb-298">UE-V Agent をアップグレードする場合は、前の UE-V Agent をインストールしたのと同じインストーラータイプ (.exe ファイルまたは .msi パケット) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="339eb-298">When you upgrade the UE-V Agent, you must use the same installer type (.exe file or .msi packet) that installed the previous UE-V Agent.</span></span> <span data-ttu-id="339eb-299">たとえば、AgentSetup.exe を使用してインストールされた UE-V 1.0 エージェントをアップグレードするには、UE-V 2 AgentSetup.exe を使います。</span><span class="sxs-lookup"><span data-stu-id="339eb-299">For example, use the UE-V 2 AgentSetup.exe to upgrade UE-V 1.0 Agents that were installed by using AgentSetup.exe.</span></span>



<span data-ttu-id="339eb-300">エージェントセットアッププログラムを実行すると、次の構成が維持されます。</span><span class="sxs-lookup"><span data-stu-id="339eb-300">The following configurations are preserved when the Agent Setup program runs:</span></span>

-   <span data-ttu-id="339eb-301">設定の記憶域のパス</span><span class="sxs-lookup"><span data-stu-id="339eb-301">Settings storage path</span></span>

-   <span data-ttu-id="339eb-302">レジストリの設定</span><span class="sxs-lookup"><span data-stu-id="339eb-302">Registry settings</span></span>

-   <span data-ttu-id="339eb-303">スケジュールされたタスク (間隔の設定が既定値にリセットされる)</span><span class="sxs-lookup"><span data-stu-id="339eb-303">Scheduled tasks (Interval settings are reset to their defaults)</span></span>

**<span data-ttu-id="339eb-304">注</span><span class="sxs-lookup"><span data-stu-id="339eb-304">Note</span></span>**  
<span data-ttu-id="339eb-305">Ue-v 1.0 Agent register エラーに登録されている UE-V 2. x 設定の場所テンプレートが Windows イベントログに登録されているコンピューター。</span><span class="sxs-lookup"><span data-stu-id="339eb-305">A computer with UE-V 2.x settings location templates that are registered in the UE-V 1.0 Agent register errors in the Windows Event Log.</span></span>



<span data-ttu-id="339eb-306">Microsoft System Center 2012 構成マネージャー、または別のエンタープライズソフトウェア配布ツールを使用して、UE-V Agent のアップグレードを自動化および配布することができます。</span><span class="sxs-lookup"><span data-stu-id="339eb-306">You can use Microsoft System Center 2012 Configuration Manager or another enterprise software distribution tool to automate and distribute the UE-V Agent upgrade.</span></span>

<span data-ttu-id="339eb-307">**推奨事項:** すべての UE-V 1.0 エージェントをコンピューティング環境でアップグレードすることをお勧めしますが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="339eb-307">**Recommendations:** We recommend that you upgrade all of the UE-V 1.0 Agents in a computing environment, but it is not required.</span></span> <span data-ttu-id="339eb-308">UE-V の設定の場所テンプレートは、設定の記憶域のパスの設定のみを共有するため、UE-V 1.0 エージェントとやり取りすることができます。</span><span class="sxs-lookup"><span data-stu-id="339eb-308">UE-V 2.x settings location templates can interact with a UE-V 1.0 Agent because they only share the settings from the settings storage path.</span></span> <span data-ttu-id="339eb-309">ただし、管理を簡素化して UE-V をサポートするために、展開を単一のエージェントバージョンに移行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="339eb-309">We recommend, however, that you move the deployments to a single agent version to simplify management and to support UE-V.</span></span>

### <span data-ttu-id="339eb-310">アップグレードに失敗した後に UE-V Agent を修復する</span><span class="sxs-lookup"><span data-stu-id="339eb-310">Repair the UE-V Agent after an unsuccessful upgrade</span></span>

<span data-ttu-id="339eb-311">次のいずれかの操作を実行しようとすると、エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="339eb-311">You might experience errors after you attempt one of the following operations:</span></span>

-   <span data-ttu-id="339eb-312">UE-V 1.0 から UE-V 2 へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="339eb-312">Upgrade from UE-V 1.0 to UE-V 2</span></span>

-   <span data-ttu-id="339eb-313">新しいバージョンの Windows にアップグレードします。たとえば、Windows 7 から Windows 8 へ、または Windows 8 から Windows 8.1 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="339eb-313">Upgrade to a newer version of Windows, for example, from Windows 7 to Windows 8 or from Windows 8 to Windows 8.1.</span></span>

-   <span data-ttu-id="339eb-314">UE-V エージェントのアップグレード後にエージェントをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="339eb-314">Uninstall the agent after upgrading the UE-V Agent</span></span>

<span data-ttu-id="339eb-315">問題を解決するには、エージェントがインストールされているコンピューターのコマンドプロンプトで次のコマンドを入力して、UE-V Agent の修復を試みます。</span><span class="sxs-lookup"><span data-stu-id="339eb-315">To resolve any issues, attempt to repair the UE-V Agent by entering this command at a command prompt on the computer where the agent is installed.</span></span>

``` syntax
msiexec.exe /f "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log
```

<span data-ttu-id="339eb-316">次に、新しいバージョンの UE-V Agent をインストールすることで、アンインストールプロセスまたはアップグレードを再試行できます。</span><span class="sxs-lookup"><span data-stu-id="339eb-316">You can then retry the uninstall process or upgrade by installing the newer version of the UE-V Agent.</span></span>






## <span data-ttu-id="339eb-317">関連トピック</span><span class="sxs-lookup"><span data-stu-id="339eb-317">Related topics</span></span>


[<span data-ttu-id="339eb-318">UE-V の展開を準備する</span><span class="sxs-lookup"><span data-stu-id="339eb-318">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[<span data-ttu-id="339eb-319">カスタムアプリケーションの UE-V 2. x の展開</span><span class="sxs-lookup"><span data-stu-id="339eb-319">Deploy UE-V 2.x for Custom Applications</span></span>](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)









