---
title: UE-V の設定パッケージを移行する
description: UE-V の設定パッケージを移行する
author: dansimp
ms.assetid: f79381f4-e142-405c-b728-5c048502aa70
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0aa1f1c36594d69de40306dfa70a4a0cf5c86dbb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825517"
---
# <span data-ttu-id="1a4e6-103">UE-V の設定パッケージを移行する</span><span class="sxs-lookup"><span data-stu-id="1a4e6-103">Migrating UE-V 2.x Settings Packages</span></span>


<span data-ttu-id="1a4e6-104">Microsoft User Experience Virtualization (UE-V) 2.0、2.1、または 2.1 SP1 の展開のライフサイクルでは、新しいサーバーに移行するとき、またはバックアップを実行するときに、ユーザー設定パッケージを再配置することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a4e6-104">In the lifecycle of a Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, or 2.1 SP1 deployment, you might have to relocate the user settings packages either when you migrate to a new server or when you perform backups.</span></span> <span data-ttu-id="1a4e6-105">次のシナリオでは、設定パッケージを移行する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a4e6-105">Settings packages might have to be migrated in the following scenarios:</span></span>

-   <span data-ttu-id="1a4e6-106">既存のサーバーハードウェアをより先進のサーバーにアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="1a4e6-106">Upgrade of existing server hardware to a more modern server.</span></span>

-   <span data-ttu-id="1a4e6-107">設定の保存場所の移行テストサーバーから運用サーバーに共有します。</span><span class="sxs-lookup"><span data-stu-id="1a4e6-107">Migration of a settings storage location share from a test server to a production server.</span></span>

<span data-ttu-id="1a4e6-108">ファイルとフォルダーをコピーするだけでは、セキュリティ設定とアクセス許可は維持されません。</span><span class="sxs-lookup"><span data-stu-id="1a4e6-108">Simply copying the files and folders does not preserve the security settings and permissions.</span></span> <span data-ttu-id="1a4e6-109">次の手順では、設定パッケージを NTFS ファイルシステムのアクセス許可と共に新しい共有に適切にコピーする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a4e6-109">The following steps describe how to correctly copy the settings package along with their NTFS file system permissions to a new share.</span></span>

**<span data-ttu-id="1a4e6-110">新しいサーバーに移行するときに、UE-V 2 設定パッケージを保存するには</span><span class="sxs-lookup"><span data-stu-id="1a4e6-110">To preserve UE-V 2 settings packages when you migrate to a new server</span></span>**

1.  <span data-ttu-id="1a4e6-111">別のサーバー上の新しい場所に、新しいフォルダー (MySettings など) を作成します。</span><span class="sxs-lookup"><span data-stu-id="1a4e6-111">In a new location on a different server, create a new folder, for example, MySettings.</span></span>

2.  <span data-ttu-id="1a4e6-112">古いサーバー上の古いフォルダー共有の共有を無効にします。</span><span class="sxs-lookup"><span data-stu-id="1a4e6-112">Disable sharing for the old folder share on the old server.</span></span>

3.  <span data-ttu-id="1a4e6-113">Robocopy で既存の設定パッケージを新しいサーバーにコピーするには</span><span class="sxs-lookup"><span data-stu-id="1a4e6-113">To copy the existing settings packages to the new server with Robocopy</span></span>

    ``` syntax
    C:\start robocopy "\\servername\E$\MySettings" "\\servername\E$\MySettings" /b /sec /secfix /e /LOG:D:\Robocopylogs\MySettings.txt
    ```

    <span data-ttu-id="1a4e6-114">**注** コピーの進行状況を監視するには、Trace32 などのログビューアーで MySettings.txt を開きます。</span><span class="sxs-lookup"><span data-stu-id="1a4e6-114">**Note** To monitor the copy progress, open MySettings.txt with a log viewer such as Trace32.</span></span>

     

4.  <span data-ttu-id="1a4e6-115">新しい共有に共有レベルのアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="1a4e6-115">Grant share-level permissions to the new share.</span></span> <span data-ttu-id="1a4e6-116">Robocopy によって設定された NTFS ファイルシステム権限をそのままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="1a4e6-116">Leave the NTFS file system permissions as they were set by Robocopy.</span></span>

    <span data-ttu-id="1a4e6-117">UE-V Agent を実行しているコンピューターでは、 **Settingsstoragepath**構成設定を新しい共有の汎用名前付け規則 (UNC) パスに更新します。</span><span class="sxs-lookup"><span data-stu-id="1a4e6-117">On computers that run the UE-V Agent, update the **SettingsStoragePath** configuration setting to the Universal Naming Convention (UNC) path of the new share.</span></span>

    <span data-ttu-id="1a4e6-118">**Ue-v のご提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="1a4e6-118">**Got a suggestion for UE-V**?</span></span> <span data-ttu-id="1a4e6-119">[ここで](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="1a4e6-119">Add or vote on suggestions [here](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization).</span></span> <span data-ttu-id="1a4e6-120">**Ue-v の問題が発生した場合**</span><span class="sxs-lookup"><span data-stu-id="1a4e6-120">**Got a UE-V issue**?</span></span> <span data-ttu-id="1a4e6-121">Ue-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)を使用します。</span><span class="sxs-lookup"><span data-stu-id="1a4e6-121">Use the [UE-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopuev).</span></span>

## <span data-ttu-id="1a4e6-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1a4e6-122">Related topics</span></span>


[<span data-ttu-id="1a4e6-123">UE-V 2. x の管理</span><span class="sxs-lookup"><span data-stu-id="1a4e6-123">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

 

 





