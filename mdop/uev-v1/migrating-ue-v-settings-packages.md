---
title: UE-V 設定パッケージの移行
description: UE-V 設定パッケージの移行
author: dansimp
ms.assetid: 93d99254-3e17-4e96-92ad-87059d8554a7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d0087f334e916c06e7611d2671d0b50e7d1dd916
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823207"
---
# <span data-ttu-id="4782e-103">UE-V 設定パッケージの移行</span><span class="sxs-lookup"><span data-stu-id="4782e-103">Migrating UE-V Settings Packages</span></span>


<span data-ttu-id="4782e-104">Microsoft User Experience Virtualization (UE-V) の展開のライフサイクルでは、新しいサーバーまたはバックアップ目的で、ユーザー設定パッケージを再配置する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="4782e-104">In the lifecycle of a Microsoft User Experience Virtualization (UE-V) deployment, you might need to relocate the user settings packages either when migrating to a new server or for backup purposes.</span></span> <span data-ttu-id="4782e-105">設定パッケージの移行は、次のシナリオで必要となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4782e-105">Migration of settings packages might be needed in the following scenarios:</span></span>

-   <span data-ttu-id="4782e-106">既存のサーバーハードウェアをより先進のサーバーにアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="4782e-106">Upgrade of existing server hardware to a more modern server.</span></span>

-   <span data-ttu-id="4782e-107">設定の保存場所の移行ラボから運用サーバーへの共有。</span><span class="sxs-lookup"><span data-stu-id="4782e-107">Migration of a settings storage location share from a lab to a production server.</span></span>

<span data-ttu-id="4782e-108">ファイルとフォルダーをコピーするだけでは、セキュリティ設定とアクセス許可は維持されません。</span><span class="sxs-lookup"><span data-stu-id="4782e-108">Simply copying the files and folders will not preserve the security settings and permissions.</span></span> <span data-ttu-id="4782e-109">次の手順では、設定パッケージのファイルが、NTFS アクセス許可を持つ新しい共有に適切にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="4782e-109">The following described steps will properly copy the settings package files with their NTFS permissions to a new share.</span></span>

**<span data-ttu-id="4782e-110">新しいサーバーに移行するときに、UE-V 設定パッケージを保存する方法</span><span class="sxs-lookup"><span data-stu-id="4782e-110">How to preserve UE-V settings packages when migrating to a new server</span></span>**

1.  <span data-ttu-id="4782e-111">別のサーバー上の新しい場所で、新しいフォルダーを作成します。たとえば、MySettings などです。</span><span class="sxs-lookup"><span data-stu-id="4782e-111">In a new location on a different server, create a new folder; for example, MySettings.</span></span>

2.  <span data-ttu-id="4782e-112">古いサーバー上の古いフォルダー共有の共有を無効にします。</span><span class="sxs-lookup"><span data-stu-id="4782e-112">Disable sharing for the old folder share on the old server.</span></span>

3.  <span data-ttu-id="4782e-113">コマンドラインから Robocopy を使用して、既存の設定パッケージを新しいサーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="4782e-113">Move the existing settings packages to the new server with Robocopy from the command line.</span></span> <span data-ttu-id="4782e-114">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="4782e-114">For example:</span></span>

    ``` syntax
    c:\start robocopy "\\servername\E$\MySettings" "\\servername\E$\MySettings" /b /sec /secfix /e /LOG:D:\Robocopylogs\MySettings.txt
    ```

    <span data-ttu-id="4782e-115">**注** コピーの進行状況を監視するには、Trace32 などのログファイルリーダーで MySettings.txt を開きます。</span><span class="sxs-lookup"><span data-stu-id="4782e-115">**Note** To monitor the copy progress, open MySettings.txt with a log file reader such as Trace32.</span></span>

     

4.  <span data-ttu-id="4782e-116">新しい共有に共有レベルのアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="4782e-116">Grant share-level permissions to the new share.</span></span> <span data-ttu-id="4782e-117">Robocopy によって設定された NTFS アクセス許可をそのままにします。</span><span class="sxs-lookup"><span data-stu-id="4782e-117">Leave the NTFS permissions as they were set by Robocopy.</span></span>

    <span data-ttu-id="4782e-118">UE-V agent を実行しているコンピューターで、SettingsStoragePath 構成設定を新しい共有の UNC パスに更新します。</span><span class="sxs-lookup"><span data-stu-id="4782e-118">On computers that run the UE-V agent, update the SettingsStoragePath configuration setting to the UNC path of the new share.</span></span>

## <span data-ttu-id="4782e-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4782e-119">Related topics</span></span>


[<span data-ttu-id="4782e-120">UE-V 1.0 の管理</span><span class="sxs-lookup"><span data-stu-id="4782e-120">Administering UE-V 1.0</span></span>](administering-ue-v-10.md)

[<span data-ttu-id="4782e-121">UE-V 1.0 の操作</span><span class="sxs-lookup"><span data-stu-id="4782e-121">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





