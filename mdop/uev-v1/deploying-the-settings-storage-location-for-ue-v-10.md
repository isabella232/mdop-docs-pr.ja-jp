---
title: UE-V 1.0 の設定の保存場所の展開
description: UE-V 1.0 の設定の保存場所の展開
author: dansimp
ms.assetid: b187d44d-649b-487e-98d3-a61ee2be8c2f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c179be0882bc6a0efc0f11f21fc231f03b63b0fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826637"
---
# <span data-ttu-id="0cbe8-103">UE-V 1.0 の設定の保存場所の展開</span><span class="sxs-lookup"><span data-stu-id="0cbe8-103">Deploying the Settings Storage Location for UE-V 1.0</span></span>


<span data-ttu-id="0cbe8-104">Microsoft User Experience Virtualization (UE-V) の展開には、設定パッケージファイルにユーザー設定が保存されている設定の保存場所が必要です。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-104">Microsoft User Experience Virtualization (UE-V) deployment requires a settings storage location where the user settings are stored in a settings package file.</span></span> <span data-ttu-id="0cbe8-105">設定の保存場所は、次の2つの方法のいずれかで構成できます。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-105">The settings storage location can be configured in one of the following two ways:</span></span>

-   <span data-ttu-id="0cbe8-106">**Active directory ホームディレクトリ**– active directory のユーザーに対してホームディレクトリが定義されている場合、ue-v agent はこの場所を使用して、設定場所パッケージを保存します。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-106">**Active Directory home directory** – if a home directory is defined for the user in Active Directory, the UE-V agent will use this location to store settings location packages.</span></span> <span data-ttu-id="0cbe8-107">UE-V agent は、ホームディレクトリのルートの下にユーザー固有のストレージフォルダーを動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-107">The UE-V agent dynamically creates the user-specific storage folder below the root of the home directory.</span></span> <span data-ttu-id="0cbe8-108">設定の保存場所が定義されていない場合、エージェントは Active Directory のホームディレクトリのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-108">The agent only uses the home directory of the Active Directory if a settings storage location is not defined.</span></span>

-   <span data-ttu-id="0cbe8-109">**設定の保存共有を作成**する–設定の記憶域の共有は、ue-v ユーザーがアクセスできる標準ネットワーク共有です。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-109">**Create a settings storage share** – the settings storage share is a standard network share that is accessible by UE-V users.</span></span>

## <span data-ttu-id="0cbe8-110">UE-V 設定の記憶域共有を展開する</span><span class="sxs-lookup"><span data-stu-id="0cbe8-110">Deploy a UE-V settings storage share</span></span>


<span data-ttu-id="0cbe8-111">設定の保存共有を作成する場合は、アクセス権が必要なユーザーにのみアクセスを制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-111">When you create the settings storage share, you should limit access only to users that need access.</span></span> <span data-ttu-id="0cbe8-112">以下の表に必要な権限が表示されています。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-112">The necessary permissions are shown in the tables below.</span></span>

**<span data-ttu-id="0cbe8-113">UE-V ネットワーク共有を展開するには</span><span class="sxs-lookup"><span data-stu-id="0cbe8-113">To deploy the UE-V network share</span></span>**

1.  <span data-ttu-id="0cbe8-114">UE-V ユーザーの新しいセキュリティグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-114">Create a new security group for UE-V users.</span></span>

2.  <span data-ttu-id="0cbe8-115">UE-V 設定パッケージを保存する中央のコンピューターに新しいフォルダーを作成し、そのフォルダーへのグループアクセス許可を UE-V ユーザーに付与します。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-115">Create a new folder on the centrally located computer that will store the UE-V settings packages, and then grant the UE-V users with group permissions to the folder.</span></span> <span data-ttu-id="0cbe8-116">UE-V をサポートしている管理者には、この共有フォルダーへのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-116">The administrator supporting UE-V will need permissions to this shared folder.</span></span>

3.  <span data-ttu-id="0cbe8-117">[記憶域の場所の設定] フォルダーに対して、次の共有レベル (SMB) の権限を設定します。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-117">Set the following share-level (SMB) permissions for the setting storage location folder:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="0cbe8-118">ユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="0cbe8-118">User account</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="0cbe8-119">推奨されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0cbe8-119">Recommended permissions</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="0cbe8-120">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="0cbe8-120">Everyone</span></span></p></td>
    <td align="left"><p><span data-ttu-id="0cbe8-121">権限なし</span><span class="sxs-lookup"><span data-stu-id="0cbe8-121">No Permissions</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="0cbe8-122">UE-V ユーザーのセキュリティグループ</span><span class="sxs-lookup"><span data-stu-id="0cbe8-122">Security group of UE-V users</span></span></p></td>
    <td align="left"><p><span data-ttu-id="0cbe8-123">フルコントロール</span><span class="sxs-lookup"><span data-stu-id="0cbe8-123">Full Control</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

4.  <span data-ttu-id="0cbe8-124">[設定の保存場所] フォルダーに、次の NTFS 権限を設定します。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-124">Set the following NTFS permissions for the settings storage location folder:</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="0cbe8-125">ユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="0cbe8-125">User account</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="0cbe8-126">推奨されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0cbe8-126">Recommended permissions</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="0cbe8-127">Folder</span><span class="sxs-lookup"><span data-stu-id="0cbe8-127">Folder</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="0cbe8-128">作成者/所有者</span><span class="sxs-lookup"><span data-stu-id="0cbe8-128">Creator/Owner</span></span></p></td>
    <td align="left"><p><span data-ttu-id="0cbe8-129">フルコントロール</span><span class="sxs-lookup"><span data-stu-id="0cbe8-129">Full Control</span></span></p></td>
    <td align="left"><p><span data-ttu-id="0cbe8-130">サブフォルダーとファイルのみ</span><span class="sxs-lookup"><span data-stu-id="0cbe8-130">Subfolders and Files Only</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="0cbe8-131">UE-V ユーザーのセキュリティグループ</span><span class="sxs-lookup"><span data-stu-id="0cbe8-131">Security group of UE-V users</span></span></p></td>
    <td align="left"><p><span data-ttu-id="0cbe8-132">フォルダーの一覧/データの読み取り、フォルダーの作成/データの追加を行う</span><span class="sxs-lookup"><span data-stu-id="0cbe8-132">List Folder/Read Data, Create Folders/Append Data</span></span></p></td>
    <td align="left"><p><span data-ttu-id="0cbe8-133">このフォルダーのみ</span><span class="sxs-lookup"><span data-stu-id="0cbe8-133">This Folder Only</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

5.  <span data-ttu-id="0cbe8-134">[ **OK** ] をクリックしてダイアログボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-134">Click **OK** to close the dialog boxes.</span></span>

<span data-ttu-id="0cbe8-135">このアクセス許可構成により、ユーザーは設定ストレージのフォルダーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-135">This permission configuration allows users to create folders for settings storage.</span></span> <span data-ttu-id="0cbe8-136">UE-V agent は、 `settingspackage` ユーザーのコンテキストで実行されているときに、フォルダーを作成し、セキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-136">The UE-V agent creates and secures a `settingspackage` folder while running in the context of the user.</span></span> <span data-ttu-id="0cbe8-137">ユーザーは、フォルダーに対してフルコントロールを受け取り `settingspackage` ます。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-137">The user receives full control to their `settingspackage` folder.</span></span> <span data-ttu-id="0cbe8-138">他のユーザーがこのフォルダーへのアクセス権を継承していない。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-138">Other users do not inherit access to this folder.</span></span> <span data-ttu-id="0cbe8-139">個々のユーザーディレクトリを作成してセキュリティで保護する必要はありません。これは、ユーザーのコンテキストで実行されるエージェントによって自動的に実行されるためです。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-139">You do not need to create and secure individual user directories, because this will be done automatically by the agent that runs in the context of the user.</span></span>

<span data-ttu-id="0cbe8-140">**注** セキュリティの追加は、設定の記憶域共有に対して Windows server を使用したときに構成できます。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-140">**Note** Additional security can be configured when a Windows server is utilized for the settings storage share.</span></span> <span data-ttu-id="0cbe8-141">UE-V は、ローカル管理者のグループまたは現在のユーザーが、設定パッケージが保存されているフォルダーの所有者であるかどうかを確認するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-141">UE-V can be configured to verify that either the local administrator's group or the current user is the owner of the folder where settings packages are stored.</span></span> <span data-ttu-id="0cbe8-142">追加のセキュリティを有効にするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-142">To enable additional security complete the following:</span></span>

1.  <span data-ttu-id="0cbe8-143">"RepositoryOwnerCheckEnabled" という名前の**REG \ _DWORD**のレジストリキーを**HKEY \ _LOCAL \ _MACHINE ¥ # ¥ agent¥に追加します。**</span><span class="sxs-lookup"><span data-stu-id="0cbe8-143">Add a **REG\_DWORD** registry key named "RepositoryOwnerCheckEnabled" to **HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\UEV\\Agent\\Configuration.**</span></span>

2.  <span data-ttu-id="0cbe8-144">レジストリキーの値を1に設定します。</span><span class="sxs-lookup"><span data-stu-id="0cbe8-144">Set registry key value to 1.</span></span>

 

## <span data-ttu-id="0cbe8-145">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0cbe8-145">Related topics</span></span>


[<span data-ttu-id="0cbe8-146">UE-V 1.0 の展開</span><span class="sxs-lookup"><span data-stu-id="0cbe8-146">Deploying UE-V 1.0</span></span>](deploying-ue-v-10.md)

[<span data-ttu-id="0cbe8-147">UE-V 1.0 でサポートされている構成</span><span class="sxs-lookup"><span data-stu-id="0cbe8-147">Supported Configurations for UE-V 1.0</span></span>](supported-configurations-for-ue-v-10.md)

<span data-ttu-id="0cbe8-148">ユーザーエクスペリエンスの仮想化設定のテンプレートと設定パッケージ用の中央記憶域の展開[Ue-v Generator のインストール](installing-the-ue-v-generator.md)</span><span class="sxs-lookup"><span data-stu-id="0cbe8-148">Deploy the Central Storage for User Experience Virtualization Settings Templates and Settings Packages [Installing the UE-V Generator](installing-the-ue-v-generator.md)</span></span>

[<span data-ttu-id="0cbe8-149">UE-V エージェントの展開</span><span class="sxs-lookup"><span data-stu-id="0cbe8-149">Deploying the UE-V Agent</span></span>](deploying-the-ue-v-agent.md)

 

 





