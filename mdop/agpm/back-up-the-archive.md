---
title: アーカイブをバックアップする
description: アーカイブをバックアップする
author: dansimp
ms.assetid: 400176da-3518-4475-ad19-c96cda6ca7ba
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a75099e7a6624850ee0511cf65feddf63909a0c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819207"
---
# <span data-ttu-id="86a03-103">アーカイブをバックアップする</span><span class="sxs-lookup"><span data-stu-id="86a03-103">Back Up the Archive</span></span>


<span data-ttu-id="86a03-104">高度なグループポリシー管理 (AGPM) のアーカイブを回復するのに役立ちます。障害が発生した場合は、AGPM 管理者 (フルコントロール) が頻繁にアーカイブをバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="86a03-104">To help in the recovery of the archive for Advanced Group Policy Management (AGPM) if there is a disaster, an AGPM Administrator (Full Control) should back up the archive frequently.</span></span> <span data-ttu-id="86a03-105">既定では、アーカイブは% ¥で作成されます。</span><span class="sxs-lookup"><span data-stu-id="86a03-105">By default, the archive is created in %ProgramData%\\Microsoft\\AGPM.</span></span> <span data-ttu-id="86a03-106">ただし、Microsoft Advanced グループポリシー管理サーバーのセットアップ中は、別のパスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="86a03-106">However, you can specify a different path during the setup of Microsoft Advanced Group Policy Management - Server.</span></span>

<span data-ttu-id="86a03-107">この手順を完了するには、agpm サービスがインストールされているコンピューターと、そのアーカイブを含むフォルダーの両方へのアクセス権を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="86a03-107">A user account that has access to both the AGPM Server—the computer on which the AGPM Service is installed—and to the folder that contains the archive is required to complete this procedure.</span></span>

**<span data-ttu-id="86a03-108">アーカイブのバックアップを作成するには</span><span class="sxs-lookup"><span data-stu-id="86a03-108">To back up the archive</span></span>**

1.  <span data-ttu-id="86a03-109">AGPM サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="86a03-109">Stop the AGPM Service.</span></span> <span data-ttu-id="86a03-110">詳細については、「 [AGPM サービスの開始と停止](start-and-stop-the-agpm-service-agpm30ops.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86a03-110">For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service-agpm30ops.md).</span></span>

2.  <span data-ttu-id="86a03-111">Windows エクスプローラー、Xcopy、Windows Server®バックアップ、または別のバックアップツールを使用して、[アーカイブ] フォルダーをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="86a03-111">Back up the archive folder by using Windows Explorer, Xcopy, Windows Server® Backup, or another backup tool.</span></span> <span data-ttu-id="86a03-112">非表示、システム、および読み取り専用のファイルをバックアップしてください。</span><span class="sxs-lookup"><span data-stu-id="86a03-112">Make sure that you back up hidden, system, and read-only files.</span></span>

3.  <span data-ttu-id="86a03-113">アーカイブバックアップを安全な場所に保存します。</span><span class="sxs-lookup"><span data-stu-id="86a03-113">Store the archive backup in a secure location.</span></span>

4.  <span data-ttu-id="86a03-114">AGPM サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="86a03-114">Restart the AGPM Service.</span></span> <span data-ttu-id="86a03-115">詳細については、「 [AGPM サービスの開始と停止](start-and-stop-the-agpm-service-agpm30ops.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86a03-115">For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service-agpm30ops.md).</span></span>

<span data-ttu-id="86a03-116">**注** AGPM 管理者がアーカイブを頻繁にバックアップしない場合、アーカイブバックアップのグループポリシーオブジェクト (Gpo) は最新の状態にはなりません。</span><span class="sxs-lookup"><span data-stu-id="86a03-116">**Note** If an AGPM Administrator backs up the archive infrequently, the Group Policy Objects (GPOs) in the archive backup will not be current.</span></span> <span data-ttu-id="86a03-117">アーカイブバックアップが最新の状態になるように、組織のデイリーバックアップ戦略の一部としてアーカイブをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="86a03-117">To better ensure that the archive backup is current, back up the archive as part of your organization’s daily backup strategy.</span></span>

 

### <span data-ttu-id="86a03-118">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="86a03-118">Additional references</span></span>

-   [<span data-ttu-id="86a03-119">バックアップからアーカイブを復元する</span><span class="sxs-lookup"><span data-stu-id="86a03-119">Restore the Archive from a Backup</span></span>](restore-the-archive-from-a-backup.md)

-   [<span data-ttu-id="86a03-120">AGPM サーバーとアーカイブを移動する</span><span class="sxs-lookup"><span data-stu-id="86a03-120">Move the AGPM Server and the Archive</span></span>](move-the-agpm-server-and-the-archive.md)

-   [<span data-ttu-id="86a03-121">アーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="86a03-121">Managing the Archive</span></span>](managing-the-archive.md)

 

 





