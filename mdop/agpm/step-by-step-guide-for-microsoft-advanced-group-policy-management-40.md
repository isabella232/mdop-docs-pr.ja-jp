---
title: Microsoft Advanced Group Policy Management 4.0 ステップ バイ ステップ ガイド
description: Microsoft Advanced Group Policy Management 4.0 ステップ バイ ステップ ガイド
author: dansimp
ms.assetid: dc6f9b16-b1d4-48f3-88bb-f29301f0131c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 819d536451095d23080115799016aa0ac5242dee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820197"
---
# <span data-ttu-id="652e1-103">Microsoft Advanced Group Policy Management 4.0 ステップ バイ ステップ ガイド</span><span class="sxs-lookup"><span data-stu-id="652e1-103">Step-by-Step Guide for Microsoft Advanced Group Policy Management 4.0</span></span>


<span data-ttu-id="652e1-104">このステップバイステップガイドでは、グループポリシー管理コンソール (GPMC) と Microsoft Advanced グループポリシー管理 (AGPM) を使用するグループポリシー管理の高度な手法を示します。</span><span class="sxs-lookup"><span data-stu-id="652e1-104">This step-by-step guide demonstrates advanced techniques for Group Policy management that use the Group Policy Management Console (GPMC) and Microsoft Advanced Group Policy Management (AGPM).</span></span> <span data-ttu-id="652e1-105">AGPM によって GPMC の機能が向上し、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="652e1-105">AGPM increases the capabilities of the GPMC, providing:</span></span>

-   <span data-ttu-id="652e1-106">グループポリシーオブジェクト (Gpo) を複数のグループポリシー管理者に委任するための標準的な役割。また、運用環境で Gpo へのアクセスを委任する機能もあります。</span><span class="sxs-lookup"><span data-stu-id="652e1-106">Standard roles for delegating permissions to manage Group Policy Objects (GPOs) to multiple Group Policy administrators, in addition to the ability to delegate access to GPOs in the production environment.</span></span>

-   <span data-ttu-id="652e1-107">グループポリシー管理者が、gpo を運用環境に展開する前に、オフラインで Gpo を作成して変更できるようにするアーカイブ。</span><span class="sxs-lookup"><span data-stu-id="652e1-107">An archive to enable Group Policy administrators to create and modify GPOs offline before the GPOs are deployed into a production environment.</span></span>

-   <span data-ttu-id="652e1-108">以前のバージョンの GPO にロールバックして、アーカイブに保存されているバージョンの数を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="652e1-108">The ability to roll back to any earlier version of a GPO in the archive and to limit the number of versions stored in the archive.</span></span>

-   <span data-ttu-id="652e1-109">Gpo のチェックイン/チェックアウト機能で、グループポリシーの管理者が互いの作業を誤って上書きしないようにします。</span><span class="sxs-lookup"><span data-stu-id="652e1-109">Check-in and check-out capability for GPOs to make sure that Group Policy administrators do not unintentionally overwrite each other's work.</span></span>

-   <span data-ttu-id="652e1-110">特定の属性を持つ Gpo を検索し、表示される Gpo の一覧をフィルター処理する機能。</span><span class="sxs-lookup"><span data-stu-id="652e1-110">The ability to search for GPOs with specific attributes and to filter the list of GPOs displayed.</span></span>

## <span data-ttu-id="652e1-111">AGPM シナリオの概要</span><span class="sxs-lookup"><span data-stu-id="652e1-111">AGPM scenario overview</span></span>


<span data-ttu-id="652e1-112">このシナリオでは、AGPM の各役割に対して個別のユーザーアカウントを使用して、さまざまなレベルの権限を持つ複数のグループポリシー管理者がいる環境でグループポリシーを管理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="652e1-112">For this scenario, you will use a separate user account for each role in AGPM to demonstrate how Group Policy can be managed in an environment that has multiple Group Policy administrators who have different levels of permissions.</span></span> <span data-ttu-id="652e1-113">具体的には、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="652e1-113">Specifically, you will perform the following tasks:</span></span>

-   <span data-ttu-id="652e1-114">Domain Admins グループのメンバーであるアカウントを使用して、AGPM サーバーをインストールし、アカウントまたはグループに AGPM 管理者の役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="652e1-114">Using an account that is a member of the Domain Admins group, install AGPM Server and assign the AGPM Administrator role to an account or group.</span></span>

-   <span data-ttu-id="652e1-115">AGPM ロールを割り当てるアカウントを使用し、AGPM クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="652e1-115">Using accounts to which you will assign AGPM roles, install AGPM Client.</span></span>

-   <span data-ttu-id="652e1-116">AGPM 管理者の役割を持つアカウントを使用して、他のアカウントに役割を割り当てることによって、Gpo への AGPM アクセスと代理人アクセスを構成します。</span><span class="sxs-lookup"><span data-stu-id="652e1-116">Using an account that has the AGPM Administrator role, configure AGPM and delegate access to GPOs by assigning roles to other accounts.</span></span>

-   <span data-ttu-id="652e1-117">編集者の役割を持つアカウントから、承認者の役割を持つアカウントを使用して承認する新しい GPO の作成を要求します。</span><span class="sxs-lookup"><span data-stu-id="652e1-117">From an account that has the Editor role, request that a new GPO be created that you then approve by using an account that has the Approver role.</span></span> <span data-ttu-id="652e1-118">エディターアカウントを使用して、アーカイブから GPO をチェックアウトし、GPO を編集し、GPO をアーカイブにチェックインして、展開を要求します。</span><span class="sxs-lookup"><span data-stu-id="652e1-118">Use the Editor account to check the GPO out of the archive, edit the GPO, check the GPO into the archive, and then request deployment.</span></span>

-   <span data-ttu-id="652e1-119">承認者の役割を持つアカウントを使用して、GPO を確認し、実稼働環境に展開します。</span><span class="sxs-lookup"><span data-stu-id="652e1-119">Using an account that has the Approver role, review the GPO and deploy it to your production environment.</span></span>

-   <span data-ttu-id="652e1-120">エディターロールを持つアカウントを使用して、GPO テンプレートを作成し、それを出発点として使用して新しい GPO を作成します。</span><span class="sxs-lookup"><span data-stu-id="652e1-120">Using an account that has the Editor role, create a GPO template and use it as a starting point to create a new GPO.</span></span>

-   <span data-ttu-id="652e1-121">承認者の役割を持つアカウントを使用して、GPO を削除および復元します。</span><span class="sxs-lookup"><span data-stu-id="652e1-121">Using an account that has the Approver role, delete and restore a GPO.</span></span>

![グループポリシーオブジェクトの開発プロセス](images/ab77a1f3-f430-4e7d-be58-ee8f9bd1140e.gif)

## <span data-ttu-id="652e1-123">要件</span><span class="sxs-lookup"><span data-stu-id="652e1-123">Requirements</span></span>


<span data-ttu-id="652e1-124">AGPM をインストールするコンピューターは、次の要件を満たしている必要があります。このシナリオで使用するには、アカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="652e1-124">Computers on which you want to install AGPM must meet the following requirements, and you must create accounts for use in this scenario.</span></span>

<span data-ttu-id="652e1-125">**注** AGPM 2.5 がインストールされていて、Windows Server®2003から Windows Server2008R2 または Windows Server2008 にアップグレードしている場合、または service Pack1 (SP1) で Windows7 または windowsvista Vista にインストールされていない windows Vista からのアップグレードが必要な場合は、AGPM 4.0 にアップグレードする前に、オペレーティングシステムをアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="652e1-125">**Note** If you have AGPM 2.5 installed and are upgrading from Windows Server®2003 to Windows Server2008R2 or Windows Server2008, or are upgrading from WindowsVista with no service packs installed to Windows7 or WindowsVista® with Service Pack1 (SP1), you must upgrade the operating system before you can upgrade to AGPM4.0.</span></span>

<span data-ttu-id="652e1-126">AGPM 3.0 がインストールされている場合、AGPM 4.0 にアップグレードする前に、オペレーティングシステムをアップグレードする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="652e1-126">If you have AGPM 3.0 installed, you do not have to upgrade the operating system before you upgrade to AGPM 4.0</span></span>

 

<span data-ttu-id="652e1-127">新しいオペレーティングシステムと古いオペレーティングシステムの両方が含まれている混在環境では、次の表に示すように、機能にいくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="652e1-127">In a mixed environment that includes both newer and older operating systems, there are some limitations to functionality, as indicated in the following table.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="652e1-128">AGPM サーバー4.0 が実行されているオペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="652e1-128">Operating system on which AGPM Server 4.0 runs</span></span></th>
<th align="left"><span data-ttu-id="652e1-129">AGPM クライアント4.0 が実行されるオペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="652e1-129">Operating system on which AGPM Client 4.0 runs</span></span></th>
<th align="left"><span data-ttu-id="652e1-130">AGPM 4.0 サポートの状態</span><span class="sxs-lookup"><span data-stu-id="652e1-130">Status of AGPM 4.0 support</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="652e1-131">Windows Server2008R2 または Windows7</span><span class="sxs-lookup"><span data-stu-id="652e1-131">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="652e1-132">Windows Server2008R2 または Windows7</span><span class="sxs-lookup"><span data-stu-id="652e1-132">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="652e1-133">サポートされています</span><span class="sxs-lookup"><span data-stu-id="652e1-133">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="652e1-134">Windows Server2008R2 または Windows7</span><span class="sxs-lookup"><span data-stu-id="652e1-134">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="652e1-135">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="652e1-135">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="652e1-136">サポートされていますが、Windows Server2008R2 または Windows7 にのみ存在するポリシー設定や設定項目は編集できません。</span><span class="sxs-lookup"><span data-stu-id="652e1-136">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2008R2 or Windows7</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="652e1-137">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="652e1-137">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="652e1-138">Windows Server2008R2 または Windows7</span><span class="sxs-lookup"><span data-stu-id="652e1-138">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="652e1-139">サポートされていません</span><span class="sxs-lookup"><span data-stu-id="652e1-139">Unsupported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="652e1-140">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="652e1-140">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="652e1-141">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="652e1-141">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="652e1-142">サポートされますが、Windows Server2008R2 または Windows7 にのみ存在するポリシー設定や基本設定項目は報告または編集できません。</span><span class="sxs-lookup"><span data-stu-id="652e1-142">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2008R2 or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="652e1-143">AGPM サーバーの要件</span><span class="sxs-lookup"><span data-stu-id="652e1-143">AGPM Server requirements</span></span>

<span data-ttu-id="652e1-144">AGPM サーバー4.0 を使用するには、リモートサーバー管理ツール (RSAT)、または Windows Vista SP1 と RSAT がインストールされている windows Server2008R2、Windows Server2008、Windows7、GPMC が必要です。</span><span class="sxs-lookup"><span data-stu-id="652e1-144">AGPM Server4.0 requires Windows Server2008R2, Windows Server2008, Windows7 and the GPMC from Remote Server Administration Tools (RSAT), or Windows Vista with SP1 and the GPMC from RSAT installed.</span></span> <span data-ttu-id="652e1-145">32ビットと64ビットの両方のバージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="652e1-145">Both 32-bit and 64-bit versions are supported.</span></span>

<span data-ttu-id="652e1-146">AGPM サーバーをインストールする前に、ドメイン管理者グループのメンバーであり、特に記載されていない限り、次の Windows 機能が存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="652e1-146">Before you install AGPM Server, you must be a member of the Domain Admins group and the following Windows features must be present unless otherwise noted:</span></span>

-   <span data-ttu-id="652e1-147">GPMC.MSC</span><span class="sxs-lookup"><span data-stu-id="652e1-147">GPMC</span></span>

    -   <span data-ttu-id="652e1-148">Windows Server2008R2 または Windows Server2008: GPMC が存在しない場合は、AGPM によって自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="652e1-148">Windows Server2008R2 or Windows Server2008: If the GPMC is not present, it is automatically installed by AGPM.</span></span>

    -   <span data-ttu-id="652e1-149">Windows7: AGPM をインストールする前に、RSAT から GPMC をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="652e1-149">Windows7: You must install the GPMC from RSAT before you install AGPM.</span></span> <span data-ttu-id="652e1-150">詳細については、「 [Windows 7 用リモートサーバー管理ツール](https://go.microsoft.com/fwlink/?LinkID=131280)(.」) を参照してください https://go.microsoft.com/fwlink/?LinkID=131280) 。</span><span class="sxs-lookup"><span data-stu-id="652e1-150">For more information, see [Remote Server Administration Tools for Windows 7](https://go.microsoft.com/fwlink/?LinkID=131280) (https://go.microsoft.com/fwlink/?LinkID=131280).</span></span>

    -   <span data-ttu-id="652e1-151">Windows Vista SP1 の場合: AGPM をインストールする前に、RSAT から GPMC をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="652e1-151">Windows Vista with SP1: You must install the GPMC from RSAT before you install AGPM.</span></span> <span data-ttu-id="652e1-152">詳細については、「 [Windows Vista のリモートサーバー管理ツール (Service Pack 1](https://go.microsoft.com/fwlink/?LinkID=116179) )」を参照してください https://go.microsoft.com/fwlink/?LinkID=116179) 。</span><span class="sxs-lookup"><span data-stu-id="652e1-152">For more information, see [Remote Server Administration Tools for Windows Vista with Service Pack 1](https://go.microsoft.com/fwlink/?LinkID=116179) (https://go.microsoft.com/fwlink/?LinkID=116179).</span></span>

-   <span data-ttu-id="652e1-153">.NET Framework 3.5 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="652e1-153">The .NET Framework 3.5 or later versions</span></span>

    -   <span data-ttu-id="652e1-154">Windows Server2008R2 または Windows7: .NET Framework 3.5 以降のバージョンが存在しない場合、.NET Framework 3.5 は AGPM によって自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="652e1-154">Windows Server2008R2 or Windows7: If the .NET Framework 3.5 or later version is not present, the .NET Framework 3.5 is automatically installed by AGPM.</span></span>

    -   <span data-ttu-id="652e1-155">Windows Server2008 または Windows Vista SP1 の場合: AGPM をインストールする前に、.NET Framework 3.5 またはそれ以降のバージョンをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="652e1-155">Windows Server2008 or Windows Vista with SP1: You must install the .NET Framework 3.5 or a later version before you install AGPM.</span></span>

<span data-ttu-id="652e1-156">次の Windows 機能は、AGPM サーバーによって必要とされ、存在しない場合は自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="652e1-156">The following Windows features are required by AGPM Server and will be automatically installed if they are not present:</span></span>

-   <span data-ttu-id="652e1-157">WCF のアクティベーションHTTP 以外のアクティベーション</span><span class="sxs-lookup"><span data-stu-id="652e1-157">WCF Activation; Non-HTTP Activation</span></span>

-   <span data-ttu-id="652e1-158">Windows プロセス アクティブ化サービス</span><span class="sxs-lookup"><span data-stu-id="652e1-158">Windows Process Activation Service</span></span>

    -   <span data-ttu-id="652e1-159">プロセスモデル</span><span class="sxs-lookup"><span data-stu-id="652e1-159">Process Model</span></span>

    -   <span data-ttu-id="652e1-160">.NET 環境</span><span class="sxs-lookup"><span data-stu-id="652e1-160">The .NET Environment</span></span>

    -   <span data-ttu-id="652e1-161">構成 Api</span><span class="sxs-lookup"><span data-stu-id="652e1-161">Configuration APIs</span></span>

### <span data-ttu-id="652e1-162">AGPM クライアントの要件</span><span class="sxs-lookup"><span data-stu-id="652e1-162">AGPM Client requirements</span></span>

<span data-ttu-id="652e1-163">AGPM クライアント4.0 では、Windows Server2008R2、Windows Server2008、Windows7、および RSAT からの GPMC、または Windows Vista with SP1 と、RSAT をインストールした GPMC をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="652e1-163">AGPM Client4.0 requires Windows Server2008R2, Windows Server2008, Windows7 and the GPMC from RSAT, or Windows Vista with SP1 and the GPMC from RSAT installed.</span></span> <span data-ttu-id="652e1-164">32ビットと64ビットの両方のバージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="652e1-164">Both 32-bit and 64-bit versions are supported.</span></span> <span data-ttu-id="652e1-165">Agpm クライアントは、AGPM サーバーを実行しているコンピューターにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="652e1-165">AGPM Client can be installed on a computer that is running AGPM Server.</span></span>

<span data-ttu-id="652e1-166">表示されていない場合は、次の Windows 機能が AGPM クライアントによって必要となります。特に記載されていない場合は、これらの機能はインストールされない</span><span class="sxs-lookup"><span data-stu-id="652e1-166">The following Windows features are required by AGPM Client and unless otherwise noted are automatically installed if they are not present:</span></span>

-   <span data-ttu-id="652e1-167">GPMC.MSC</span><span class="sxs-lookup"><span data-stu-id="652e1-167">GPMC</span></span>

    -   <span data-ttu-id="652e1-168">Windows Server2008R2 または Windows Server2008: GPMC が存在しない場合は、AGPM によって自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="652e1-168">Windows Server2008R2 or Windows Server2008: If the GPMC is not present, it is automatically installed by AGPM.</span></span>

    -   <span data-ttu-id="652e1-169">Windows7: AGPM をインストールする前に、RSAT から GPMC をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="652e1-169">Windows7: You must install the GPMC from RSAT before you install AGPM.</span></span> <span data-ttu-id="652e1-170">詳細については、「 [Windows 7 用リモートサーバー管理ツール](https://go.microsoft.com/fwlink/?LinkID=131280)(.」) を参照してください https://go.microsoft.com/fwlink/?LinkID=131280) 。</span><span class="sxs-lookup"><span data-stu-id="652e1-170">For more information, see [Remote Server Administration Tools for Windows 7](https://go.microsoft.com/fwlink/?LinkID=131280) (https://go.microsoft.com/fwlink/?LinkID=131280).</span></span>

    -   <span data-ttu-id="652e1-171">Windows Vista SP1 の場合: AGPM をインストールする前に、RSAT から GPMC をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="652e1-171">Windows Vista with SP1: You must install the GPMC from RSAT before you install AGPM.</span></span> <span data-ttu-id="652e1-172">詳細については、「 [Windows Vista のリモートサーバー管理ツール (Service Pack 1](https://go.microsoft.com/fwlink/?LinkID=116179) )」を参照してください https://go.microsoft.com/fwlink/?LinkID=116179) 。</span><span class="sxs-lookup"><span data-stu-id="652e1-172">For more information, see [Remote Server Administration Tools for Windows Vista with Service Pack 1](https://go.microsoft.com/fwlink/?LinkID=116179) (https://go.microsoft.com/fwlink/?LinkID=116179).</span></span>

-   <span data-ttu-id="652e1-173">.NET Framework 3.0 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="652e1-173">The .NET Framework 3.0 or later version</span></span>

    -   <span data-ttu-id="652e1-174">Windows Server2008R2 または Windows7: .NET Framework 3.0 以降のバージョンが存在しない場合、.NET Framework 3.5 は AGPM によって自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="652e1-174">Windows Server2008R2 or Windows7: If the .NET Framework 3.0 or later version is not present, the .NET Framework 3.5 is automatically installed by AGPM.</span></span>

    -   <span data-ttu-id="652e1-175">Windows Server2008 または Windows Vista SP1 の場合: .NET Framework 3.0 以降のバージョンが存在しない場合、.NET Framework 3.0 は AGPM によって自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="652e1-175">Windows Server2008 or Windows Vista with SP1: If the .NET Framework 3.0 or later version is not present, the .NET Framework 3.0 is automatically installed by AGPM.</span></span>

### <span data-ttu-id="652e1-176">シナリオの要件</span><span class="sxs-lookup"><span data-stu-id="652e1-176">Scenario requirements</span></span>

<span data-ttu-id="652e1-177">このシナリオを始める前に、4つのユーザーアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="652e1-177">Before you begin this scenario, create four user accounts.</span></span> <span data-ttu-id="652e1-178">このシナリオでは、これらの各アカウントに、AGPM 管理者 (フルコントロール)、承認者、編集者、および校閲者といういずれかの AGPM ロールを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="652e1-178">During the scenario, you will assign one of the following AGPM roles to each of these accounts: AGPM Administrator (Full Control), Approver, Editor, and Reviewer.</span></span> <span data-ttu-id="652e1-179">これらのアカウントでは、電子メールメッセージの送受信が可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="652e1-179">These accounts must be able to send and receive e-mail messages.</span></span> <span data-ttu-id="652e1-180">AGPM 管理者、承認者、(必要に応じて) エディターの各役割を持つアカウントに**リンク gpo**のアクセス許可を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="652e1-180">Assign **Link GPOs** permission to the accounts that have the AGPM Administrator, Approver, and (optionally) Editor roles.</span></span>

<span data-ttu-id="652e1-181">**注** 
[ **Gpo のリンク**] 権限は、既定でドメイン管理者とエンタープライズ管理者のメンバーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="652e1-181">**Note**
**Link GPOs** permission is assigned to members of Domain Administrators and Enterprise Administrators by default.</span></span> <span data-ttu-id="652e1-182">追加のユーザーまたはグループ (AGPM 管理者または承認者の役割を持つアカウントなど) に**リンク gpo**のアクセス許可を割り当てるには、そのドメインのノードをクリックし、[**委任**] タブをクリックし、[ **gpo のリンク**]、[**追加**] の順にクリックして、アクセス許可を割り当てるユーザーまたはグループを選びます。</span><span class="sxs-lookup"><span data-stu-id="652e1-182">To assign **Link GPOs** permission to additional users or groups (such as accounts that have the roles of AGPM Administrator or Approver), click the node for the domain and then click the **Delegation** tab, select **Link GPOs**, click **Add**, and select users or groups to which you want to assign the permission.</span></span>

 

## <span data-ttu-id="652e1-183">AGPM のインストールと構成の手順</span><span class="sxs-lookup"><span data-stu-id="652e1-183">Steps for installing and configuring AGPM</span></span>


<span data-ttu-id="652e1-184">AGPM をインストールして構成するには、次の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="652e1-184">You must complete the following steps to install and configure AGPM.</span></span>

[<span data-ttu-id="652e1-185">手順 1: AGPM サーバーをインストールする</span><span class="sxs-lookup"><span data-stu-id="652e1-185">Step 1: Install AGPM Server</span></span>](#bkmk-config1)

[<span data-ttu-id="652e1-186">手順 2: AGPM クライアントをインストールする</span><span class="sxs-lookup"><span data-stu-id="652e1-186">Step 2: Install AGPM Client</span></span>](#bkmk-config2)

[<span data-ttu-id="652e1-187">手順 3: AGPM サーバー接続を構成する</span><span class="sxs-lookup"><span data-stu-id="652e1-187">Step 3: Configure an AGPM Server connection</span></span>](#bkmk-config3)

[<span data-ttu-id="652e1-188">手順 4: 電子メール通知を構成する</span><span class="sxs-lookup"><span data-stu-id="652e1-188">Step 4: Configure e-mail notification</span></span>](#bkmk-config4)

[<span data-ttu-id="652e1-189">手順 5: 代理人アクセス</span><span class="sxs-lookup"><span data-stu-id="652e1-189">Step 5: Delegate access</span></span>](#bkmk-config5)

### <a href="" id="bkmk-config1"></a><span data-ttu-id="652e1-190">手順 1: AGPM サーバーをインストールする</span><span class="sxs-lookup"><span data-stu-id="652e1-190">Step 1: Install AGPM Server</span></span>

<span data-ttu-id="652e1-191">この手順では、AGPM サービスを実行するメンバーサーバーまたはドメインコントローラーに AGPM サーバーをインストールし、アーカイブを構成します。</span><span class="sxs-lookup"><span data-stu-id="652e1-191">In this step, you install AGPM Server on the member server or domain controller that will run the AGPM Service, and you configure the archive.</span></span> <span data-ttu-id="652e1-192">すべての AGPM 操作は、この Windows サービスを通じて管理され、サービスの資格情報を使って実行されます。</span><span class="sxs-lookup"><span data-stu-id="652e1-192">All AGPM operations are managed through this Windows service and are executed with the service's credentials.</span></span> <span data-ttu-id="652e1-193">AGPM サーバーによって管理されるアーカイブは、そのサーバーまたは同じフォレスト内の別のサーバー上でホストすることができます。</span><span class="sxs-lookup"><span data-stu-id="652e1-193">The archive managed by an AGPM Server can be hosted on that server or on another server in the same forest.</span></span>

**<span data-ttu-id="652e1-194">AGPM サービスをホストするコンピューターに AGPM サーバーをインストールするには</span><span class="sxs-lookup"><span data-stu-id="652e1-194">To install AGPM Server on the computer that will host the AGPM Service</span></span>**

1.  <span data-ttu-id="652e1-195">Domain Admins グループのメンバーであるアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="652e1-195">Log on with an account that is a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="652e1-196">Microsoft デスクトップ最適化パック CD を起動し、画面の指示に従って [**高度なグループポリシー管理-サーバー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="652e1-196">Start the Microsoft Desktop Optimization Pack CD and follow the instructions on screen to select **Advanced Group Policy Management - Server**.</span></span>

3.  <span data-ttu-id="652e1-197">[**ようこそ**] ダイアログボックスで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-197">In the **Welcome** dialog box, click **Next**.</span></span>

4.  <span data-ttu-id="652e1-198">[ **Microsoft ソフトウェアライセンス条項**] ダイアログボックスで、条項に同意し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-198">In the **Microsoft Software License Terms** dialog box, accept the terms and then click **Next**.</span></span>

5.  <span data-ttu-id="652e1-199">[**アプリケーションパス**] ダイアログボックスで、AGPM サーバーをインストールする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="652e1-199">In the **Application Path** dialog box, select a location in which to install AGPM Server.</span></span> <span data-ttu-id="652e1-200">AGPM サーバーがインストールされているコンピューターは、AGPM サービスをホストし、アーカイブを管理します。</span><span class="sxs-lookup"><span data-stu-id="652e1-200">The computer on which AGPM Server is installed will host the AGPM Service and manage the archive.</span></span> <span data-ttu-id="652e1-201">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-201">Click **Next**.</span></span>

6.  <span data-ttu-id="652e1-202">[**アーカイブパス**] ダイアログボックスで、AGPM サーバーに対するアーカイブの場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="652e1-202">In the **Archive Path** dialog box, select a location for the archive in relation to the AGPM Server.</span></span> <span data-ttu-id="652e1-203">アーカイブパスは、AGPM サーバー上のフォルダーまたは他の場所から参照できます。</span><span class="sxs-lookup"><span data-stu-id="652e1-203">The archive path can point to a folder on the AGPM Server or elsewhere.</span></span> <span data-ttu-id="652e1-204">ただし、この AGPM サーバーで管理されているすべての Gpo と履歴データを保存する場所を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="652e1-204">However, you should select a location with sufficient space to store all GPOs and history data managed by this AGPM Server.</span></span> <span data-ttu-id="652e1-205">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-205">Click **Next**.</span></span>

7.  <span data-ttu-id="652e1-206">[ **Agpm サービスアカウント**] ダイアログボックスで、agpm サービスを実行するサービスアカウントを選び、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-206">In the **AGPM Service Account** dialog box, select a service account under which the AGPM Service will run and then click **Next**.</span></span>

    <span data-ttu-id="652e1-207">このアカウントは、"Domain Admins" グループのメンバーであるか、または AGPM サーバーで管理されている各ドメインの次のグループに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="652e1-207">This account must be a member of the either the Domain Admins group or, for a least-privilege configuration, the following groups in each domain managed by the AGPM Server:</span></span>

    -   <span data-ttu-id="652e1-208">グループポリシーの作成者</span><span class="sxs-lookup"><span data-stu-id="652e1-208">Group Policy Creator Owners</span></span>

    -   <span data-ttu-id="652e1-209">バックアップオペレーター</span><span class="sxs-lookup"><span data-stu-id="652e1-209">Backup Operators</span></span>

    <span data-ttu-id="652e1-210">さらに、このアカウントには、次のフォルダーに対するフルコントロールのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="652e1-210">Additionally, this account requires Full Control permission for the following folders:</span></span>

    -   <span data-ttu-id="652e1-211">AGPM アーカイブフォルダー。このアクセス許可は、AGPM サーバーがローカルドライブにインストールされている場合に、そのインストール中に自動的に付与されます。</span><span class="sxs-lookup"><span data-stu-id="652e1-211">The AGPM archive folder, for which this permission is automatically granted during the installation of AGPM Server if it is installed on a local drive.</span></span>

    -   <span data-ttu-id="652e1-212">ローカルシステムの temp フォルダー (通常は%windir%\\temp.</span><span class="sxs-lookup"><span data-stu-id="652e1-212">The local system temp folder, typically %windir%\\temp.</span></span>

8.  <span data-ttu-id="652e1-213">[**アーカイブの所有者**] ダイアログボックスで、AGPM 管理者 (フルコントロール) の役割を割り当てるアカウントまたはグループを選びます。</span><span class="sxs-lookup"><span data-stu-id="652e1-213">In the **Archive Owner** dialog box, select an account or group to which you assign the AGPM Administrator (Full Control) role.</span></span> <span data-ttu-id="652e1-214">AGPM 管理者は、他のグループポリシー管理者に AGPM の役割とアクセス許可を割り当てることができます。そのため、後で AGPM 管理者の役割を追加のグループポリシー管理者に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="652e1-214">AGPM Administrators can assign AGPM roles and permissions to other Group Policy administrators, so that later you can assign the role of AGPM Administrator to additional Group Policy administrators.</span></span> <span data-ttu-id="652e1-215">このシナリオでは、AGPM 管理者の役割で利用するアカウントを選びます。</span><span class="sxs-lookup"><span data-stu-id="652e1-215">For this scenario, select the account to serve in the AGPM Administrator role.</span></span> <span data-ttu-id="652e1-216">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-216">Click **Next**.</span></span>

9.  <span data-ttu-id="652e1-217">[**ポートの構成**] ダイアログボックスで、AGPM サービスがリッスンするポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="652e1-217">In the **Port Configuration** dialog box, type a port on which the AGPM Service should listen.</span></span> <span data-ttu-id="652e1-218">手動でポートの例外を構成するか、ルールを使用してポートの例外を構成する場合以外は、[**ファイアウォールにポートの例外を追加**する] チェックボックスをオフにしないでください。</span><span class="sxs-lookup"><span data-stu-id="652e1-218">Do not clear the **Add port exception to firewall** check box unless you manually configure port exceptions or use rules to configure port exceptions.</span></span> <span data-ttu-id="652e1-219">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-219">Click **Next**.</span></span>

10. <span data-ttu-id="652e1-220">[**言語**の選択] ダイアログボックスで、AGPM サーバー用にインストールする1つ以上の表示言語を選びます。</span><span class="sxs-lookup"><span data-stu-id="652e1-220">In the **Languages** dialog box, select one or more display languages to install for AGPM Server.</span></span>

11. <span data-ttu-id="652e1-221">[**インストール**] をクリックし、[**完了**] をクリックして、セットアップウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="652e1-221">Click **Install**, and then click **Finish** to exit the Setup Wizard.</span></span>

    <span data-ttu-id="652e1-222">**注意** AGPM サービスの設定は、オペレーティングシステムの**管理ツール**と**サービス**を使って変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="652e1-222">**Caution** Do not change settings for the AGPM Service through **Administrative Tools** and **Services** in the operating system.</span></span> <span data-ttu-id="652e1-223">これにより、AGPM サービスが開始されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="652e1-223">Doing this can prevent the AGPM Service from starting.</span></span> <span data-ttu-id="652e1-224">サービスの設定を変更する方法については、「高度なグループポリシー管理のヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="652e1-224">For information about how to change settings for the service, see Help for Advanced Group Policy Management.</span></span>

     

### <a href="" id="bkmk-config2"></a><span data-ttu-id="652e1-225">手順 2: AGPM クライアントをインストールする</span><span class="sxs-lookup"><span data-stu-id="652e1-225">Step 2: Install AGPM Client</span></span>

<span data-ttu-id="652e1-226">各グループポリシー管理者 (Gpo の作成、編集、展開、確認、削除) には、Gpo を管理するために使用するコンピューターに AGPM クライアントがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="652e1-226">Each Group Policy administrator—anyone who creates, edits, deploys, reviews, or deletes GPOs—must have AGPM Client installed on computers that they use to manage GPOs.</span></span> <span data-ttu-id="652e1-227">GPO の管理タスクの多くを実行するために使用する変更コントロールノードは、AGPM クライアントをインストールした場合にのみ、グループポリシー管理コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="652e1-227">The Change Control node, which you use to perform many of the GPO management tasks, appears in the Group Policy Management Console only if you install the AGPM Client.</span></span> <span data-ttu-id="652e1-228">このシナリオでは、少なくとも1台のコンピューターに AGPM クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="652e1-228">For this scenario, you install AGPM Client on at least one computer.</span></span> <span data-ttu-id="652e1-229">グループポリシー管理を実行しないエンドユーザーのコンピューターに AGPM クライアントをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="652e1-229">You do not need to install AGPM Client on the computers of end users who do not perform Group Policy administration.</span></span>

**<span data-ttu-id="652e1-230">グループポリシー管理者のコンピューターに AGPM クライアントをインストールするには</span><span class="sxs-lookup"><span data-stu-id="652e1-230">To install AGPM Client on the computer of a Group Policy administrator</span></span>**

1.  <span data-ttu-id="652e1-231">Microsoft デスクトップ最適化パック CD を起動し、画面の指示に従って [**高度なグループポリシーの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="652e1-231">Start the Microsoft Desktop Optimization Pack CD and follow the instructions on screen to select **Advanced Group Policy Management - Client**.</span></span>

2.  <span data-ttu-id="652e1-232">[**ようこそ**] ダイアログボックスで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-232">In the **Welcome** dialog box, click **Next**.</span></span>

3.  <span data-ttu-id="652e1-233">[ **Microsoft ソフトウェアライセンス条項**] ダイアログボックスで、条項に同意し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-233">In the **Microsoft Software License Terms** dialog box, accept the terms and then click **Next**.</span></span>

4.  <span data-ttu-id="652e1-234">[**アプリケーションパス**] ダイアログボックスで、AGPM クライアントをインストールする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="652e1-234">In the **Application Path** dialog box, select a location in which to install AGPM Client.</span></span> <span data-ttu-id="652e1-235">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-235">Click **Next**.</span></span>

5.  <span data-ttu-id="652e1-236">[ **Agpm サーバー** ] ダイアログボックスで、agpm サーバーの DNS 名または IP アドレスと、接続するポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="652e1-236">In the **AGPM Server** dialog box, type the DNS name or IP address for the AGPM Server and the port to which you want to connect.</span></span> <span data-ttu-id="652e1-237">AGPM サービスの既定のポートは4600です。</span><span class="sxs-lookup"><span data-stu-id="652e1-237">The default port for the AGPM Service is 4600.</span></span> <span data-ttu-id="652e1-238">手動でポートの例外を構成するか、ルールを使用してポートの例外を構成する場合以外は、[ **Microsoft 管理コンソールをファイアウォールで許可**する] チェックボックスをオフにしないようにします。</span><span class="sxs-lookup"><span data-stu-id="652e1-238">Do not clear the **Allow Microsoft Management Console through the firewall** check box unless you manually configure port exceptions or use rules to configure port exceptions.</span></span> <span data-ttu-id="652e1-239">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-239">Click **Next**.</span></span>

6.  <span data-ttu-id="652e1-240">[**言語**の選択] ダイアログボックスで、AGPM クライアント用にインストールする1つ以上の表示言語を選びます。</span><span class="sxs-lookup"><span data-stu-id="652e1-240">In the **Languages** dialog box, select one or more display languages to install for AGPM Client.</span></span>

7.  <span data-ttu-id="652e1-241">[**インストール**] をクリックし、[**完了**] をクリックして、セットアップウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="652e1-241">Click **Install**, and then click **Finish** to exit the Setup Wizard.</span></span>

### <a href="" id="bkmk-config3"></a><span data-ttu-id="652e1-242">手順 3: AGPM サーバー接続を構成する</span><span class="sxs-lookup"><span data-stu-id="652e1-242">Step 3: Configure an AGPM Server connection</span></span>

<span data-ttu-id="652e1-243">AGPM には、各コントロールのグループポリシーオブジェクト (GPO) のすべてのバージョンが格納されます。これは、AGPM が変更コントロールを提供する各 GPO を中央のアーカイブで管理します。</span><span class="sxs-lookup"><span data-stu-id="652e1-243">AGPM stores all versions of each controlled Group Policy Object (GPO), that is, each GPO for which AGPM provides change control, in a central archive.</span></span> <span data-ttu-id="652e1-244">これにより、グループポリシー管理者は、各 GPO の展開されたバージョンに影響を与えずに、Gpo をオフラインで表示して変更することができます。</span><span class="sxs-lookup"><span data-stu-id="652e1-244">This lets Group Policy administrators view and change GPOs offline without immediately affecting the deployed version of each GPO.</span></span>

<span data-ttu-id="652e1-245">この手順では、AGPM サーバー接続を構成し、すべてのグループポリシー管理者が同じ AGPM サーバーに接続できるようにします。</span><span class="sxs-lookup"><span data-stu-id="652e1-245">In this step, you configure an AGPM Server connection and ensure that all Group Policy administrators connect to the same AGPM Server.</span></span> <span data-ttu-id="652e1-246">複数の AGPM サーバーを構成する方法について詳しくは、「高度なグループポリシー管理のヘルプ」をご覧ください。)</span><span class="sxs-lookup"><span data-stu-id="652e1-246">(For information about how to configure multiple AGPM Servers, see Help for Advanced Group Policy Management.)</span></span>

**<span data-ttu-id="652e1-247">すべてのグループポリシー管理者に対して AGPM サーバー接続を構成するには</span><span class="sxs-lookup"><span data-stu-id="652e1-247">To configure an AGPM Server connection for all Group Policy administrators</span></span>**

1.  <span data-ttu-id="652e1-248">AGPM クライアントをインストールしたコンピューターで、アーカイブの所有者として選択したユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="652e1-248">On a computer on which you have installed AGPM Client, log on with the user account that you selected as the Archive Owner.</span></span> <span data-ttu-id="652e1-249">このユーザーは、AGPM 管理者 (フルコントロール) の役割を持っています。</span><span class="sxs-lookup"><span data-stu-id="652e1-249">This user has the role of AGPM Administrator (Full Control).</span></span>

2.  <span data-ttu-id="652e1-250">[**スタート**] をクリックし、[**管理ツール**] をポイントして、[**グループポリシーの管理**] をクリックして GPMC を開きます。</span><span class="sxs-lookup"><span data-stu-id="652e1-250">Click **Start**, point to **Administrative Tools**, and then click **Group Policy Management** to open the GPMC.</span></span>

3.  <span data-ttu-id="652e1-251">すべてのグループポリシー管理者に適用される GPO を編集します。</span><span class="sxs-lookup"><span data-stu-id="652e1-251">Edit a GPO that is applied to all Group Policy administrators.</span></span>

4.  <span data-ttu-id="652e1-252">[**グループポリシー管理エディター** ] ウィンドウで、[**ユーザーの構成**]、[**ポリシー**]、[**管理用テンプレート**]、[ **Windows コンポーネント**]、[ **AGPM**] の順にダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-252">In the **Group Policy Management Editor** window, double-click **User Configuration**, **Policies**, **Administrative Templates**, **Windows Components**, and **AGPM**.</span></span>

5.  <span data-ttu-id="652e1-253">詳細ウィンドウで、[ **agpm: 既定の AGPM サーバーを指定してください (すべてのドメイン)**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-253">In the details pane, double-click **AGPM: Specify default AGPM Server (all domains)**.</span></span>

6.  <span data-ttu-id="652e1-254">[**プロパティ**] ウィンドウで、[**有効**] を選び、アーカイブをホストしているサーバーの DNS 名または IP アドレスとポート ( **server.contoso.com:4600**など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="652e1-254">In the **Properties** window, select **Enabled** and type the DNS name or IP address and port (for example, **server.contoso.com:4600**) for the server hosting the archive.</span></span> <span data-ttu-id="652e1-255">既定では、AGPM サービスはポート4600を使用します。</span><span class="sxs-lookup"><span data-stu-id="652e1-255">By default, the AGPM Service uses port 4600.</span></span>

7.  <span data-ttu-id="652e1-256">[ **OK**] をクリックし、[**グループポリシー管理エディター** ] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="652e1-256">Click **OK**, and then close the **Group Policy Management Editor** window.</span></span> <span data-ttu-id="652e1-257">グループポリシーが更新されると、各グループポリシーの管理者に対して AGPM サーバー接続が構成されます。</span><span class="sxs-lookup"><span data-stu-id="652e1-257">When Group Policy is updated, the AGPM Server connection is configured for each Group Policy administrator.</span></span>

### <a href="" id="bkmk-config4"></a><span data-ttu-id="652e1-258">手順 4: 電子メール通知を構成する</span><span class="sxs-lookup"><span data-stu-id="652e1-258">Step 4: Configure e-mail notification</span></span>

<span data-ttu-id="652e1-259">AGPM 管理者 (フルコントロール) として、エディターが GPO を作成、展開、削除しようとしたときに、要求を含む電子メールメッセージが送信される承認者の電子メールアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="652e1-259">As an AGPM Administrator (Full Control), you designate the e-mail addresses of Approvers and AGPM Administrators to whom an e-mail message that contains a request is sent when an Editor tries to create, deploy, or delete a GPO.</span></span> <span data-ttu-id="652e1-260">また、これらのメッセージの送信元のエイリアスを指定します。</span><span class="sxs-lookup"><span data-stu-id="652e1-260">You also determine the alias from which these messages are sent.</span></span>

**<span data-ttu-id="652e1-261">AGPM の電子メール通知を構成するには</span><span class="sxs-lookup"><span data-stu-id="652e1-261">To configure e-mail notification for AGPM</span></span>**

1.  <span data-ttu-id="652e1-262">**グループポリシー管理エディター**で、[変更]**コントロール**フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="652e1-262">In **Group Policy Management Editor** , navigate to the **Change Control** folder</span></span> 

2.  <span data-ttu-id="652e1-263">詳細ウィンドウで、[ **Domain Delegation** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-263">In the details pane, click the **Domain Delegation** tab.</span></span>

3.  <span data-ttu-id="652e1-264">[**差出人の電子メールアドレス**] フィールドに、通知の送信先となる AGPM の電子メールエイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="652e1-264">In the **From e-mail address** field, type the e-mail alias for AGPM from which notifications should be sent.</span></span>

4.  <span data-ttu-id="652e1-265">[**宛先の電子メールアドレス**] フィールドに、承認者の役割を割り当てるユーザーアカウントの電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="652e1-265">In the **To e-mail address** field, type the e-mail address for the user account to which you intend to assign the Approver role.</span></span>

5.  <span data-ttu-id="652e1-266">[ **Smtp server** ] フィールドに、有効な smtp メールサーバーを入力します。</span><span class="sxs-lookup"><span data-stu-id="652e1-266">In the **SMTP server** field, type a valid SMTP mail server.</span></span>

6.  <span data-ttu-id="652e1-267">[**ユーザー名**] フィールドと [**パスワード**] フィールドに、SMTP サービスへのアクセス権を持つユーザーの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="652e1-267">In the **User name** and **Password** fields, type the credentials of a user who has access to the SMTP service.</span></span> <span data-ttu-id="652e1-268">**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-268">Click **Apply**.</span></span>

### <a href="" id="bkmk-config5"></a><span data-ttu-id="652e1-269">手順 5: 代理人アクセス</span><span class="sxs-lookup"><span data-stu-id="652e1-269">Step 5: Delegate access</span></span>

<span data-ttu-id="652e1-270">AGPM 管理者 (フルコントロール) として、Gpo へのドメインレベルのアクセスを委任し、各グループポリシー管理者のアカウントに役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="652e1-270">As an AGPM Administrator (Full Control), you delegate domain-level access to GPOs, assigning roles to the account of each Group Policy administrator.</span></span>

<span data-ttu-id="652e1-271">**注** また、ドメインレベルではなく、GPO レベルでアクセスを委任することもできます。</span><span class="sxs-lookup"><span data-stu-id="652e1-271">**Note** You can also delegate access at the GPO level instead of the domain level.</span></span> <span data-ttu-id="652e1-272">詳細については、「高度なグループポリシー管理のヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="652e1-272">For more information, see Help for Advanced Group Policy Management.</span></span>

 

<span data-ttu-id="652e1-273">**重要** グループポリシーの作成者グループのメンバーシップを制限して、Gpo へのアクセスの AGPM 管理を回避することができないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="652e1-273">**Important** You should restrict membership in the Group Policy Creator Owners group so that it cannot be used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="652e1-274">(**グループポリシー管理コンソール**で、gpo を管理するフォレストとドメインの [**グループポリシーオブジェクト**] をクリックし、[**委任**] をクリックして、組織のニーズに合わせて設定を構成します)。</span><span class="sxs-lookup"><span data-stu-id="652e1-274">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

 

**<span data-ttu-id="652e1-275">ドメイン全体のすべての Gpo へのアクセスを委任するには</span><span class="sxs-lookup"><span data-stu-id="652e1-275">To delegate access to all GPOs throughout a domain</span></span>**

1.  <span data-ttu-id="652e1-276">[ **Domain Delegation** ] タブで、[**追加**] ボタンをクリックし、承認者として使用するグループポリシー管理者のユーザーアカウントを選択して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-276">On the **Domain Delegation** tab, click the **Add** button, select the user account of the Group Policy administrator to serve as Approver, and then click **OK**.</span></span>

2.  <span data-ttu-id="652e1-277">[**グループまたはユーザーの追加**] ダイアログボックスで、**承認者**ロールを選択して、その役割をアカウントに割り当て、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-277">In the **Add Group or User** dialog box, select the **Approver** role to assign that role to the account, and then click **OK**.</span></span> <span data-ttu-id="652e1-278">(この役割にはレビュー担当者の役割が含まれます。)</span><span class="sxs-lookup"><span data-stu-id="652e1-278">(This role includes the Reviewer role.)</span></span>

3.  <span data-ttu-id="652e1-279">[**追加**] ボタンをクリックし、編集者として使用するグループポリシー管理者のユーザーアカウントを選んで、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-279">Click the **Add** button, select the user account of the Group Policy administrator to serve as Editor, and then click **OK**.</span></span>

4.  <span data-ttu-id="652e1-280">[**グループまたはユーザーの追加**] ダイアログボックスで、その役割をアカウントに割り当てるための**エディター**の役割を選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-280">In the **Add Group or User** dialog box, select the **Editor** role to assign that role to the account, and then click **OK**.</span></span> <span data-ttu-id="652e1-281">(この役割にはレビュー担当者の役割が含まれます。)</span><span class="sxs-lookup"><span data-stu-id="652e1-281">(This role includes the Reviewer role.)</span></span>

5.  <span data-ttu-id="652e1-282">[**追加**] ボタンをクリックし、校閲者として使用するグループポリシー管理者のユーザーアカウントを選んで、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-282">Click the **Add** button, select the user account of the Group Policy administrator to serve as Reviewer, and then click **OK**.</span></span>

6.  <span data-ttu-id="652e1-283">[**グループまたはユーザーの追加**] ダイアログボックスで、[**校閲者**] の役割を選択して、その役割のみをアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="652e1-283">In the **Add Group or User** dialog box, select the **Reviewer** role to assign only that role to the account.</span></span>

## <span data-ttu-id="652e1-284">Gpo を管理する手順</span><span class="sxs-lookup"><span data-stu-id="652e1-284">Steps for managing GPOs</span></span>


<span data-ttu-id="652e1-285">AGPM を使って Gpo を作成、編集、確認、展開するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="652e1-285">You must complete the following steps to create, edit, review, and deploy GPOs by using AGPM.</span></span> <span data-ttu-id="652e1-286">さらに、テンプレートを作成し、GPO を削除して、削除された GPO を復元します。</span><span class="sxs-lookup"><span data-stu-id="652e1-286">Additionally, you will create a template, delete a GPO, and restore a deleted GPO.</span></span>

[<span data-ttu-id="652e1-287">手順 1: GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="652e1-287">Step 1: Create a GPO</span></span>](#bkmk-manage1)

[<span data-ttu-id="652e1-288">手順 2: GPO を編集する</span><span class="sxs-lookup"><span data-stu-id="652e1-288">Step 2: Edit a GPO</span></span>](#bkmk-manage2)

[<span data-ttu-id="652e1-289">手順 3: GPO を確認して展開する</span><span class="sxs-lookup"><span data-stu-id="652e1-289">Step 3: Review and deploy a GPO</span></span>](#bkmk-manage3)

[<span data-ttu-id="652e1-290">手順 4: テンプレートを使用して GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="652e1-290">Step 4: Use a template to create a GPO</span></span>](#bkmk-manage4)

[<span data-ttu-id="652e1-291">手順 5: GPO を削除および復元する</span><span class="sxs-lookup"><span data-stu-id="652e1-291">Step 5: Delete and restore a GPO</span></span>](#bkmk-manage5)

### <a href="" id="bkmk-manage1"></a><span data-ttu-id="652e1-292">手順 1: GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="652e1-292">Step 1: Create a GPO</span></span>

<span data-ttu-id="652e1-293">複数のグループポリシー管理者がいる環境では、編集者の役割を持つユーザーが新しい Gpo の作成を要求できます。</span><span class="sxs-lookup"><span data-stu-id="652e1-293">In an environment that has multiple Group Policy administrators, those with the Editor role can request that new GPOs be created.</span></span> <span data-ttu-id="652e1-294">ただし、その要求は、承認者の役割を持つユーザーによって承認される必要があります。</span><span class="sxs-lookup"><span data-stu-id="652e1-294">However, that request must be approved by someone with the Approver role.</span></span>

<span data-ttu-id="652e1-295">この手順では、新しい GPO の作成を要求するエディターロールを持つアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="652e1-295">In this step, you use an account that has the Editor role to request that a new GPO be created.</span></span> <span data-ttu-id="652e1-296">承認者の役割を持つアカウントを使用して、この要求を承認して、GPO を作成します。</span><span class="sxs-lookup"><span data-stu-id="652e1-296">Using an account that has the Approver role, you approve this request to create the GPO.</span></span>

**<span data-ttu-id="652e1-297">新しい GPO を AGPM で作成して管理するように要求するには</span><span class="sxs-lookup"><span data-stu-id="652e1-297">To request that a new GPO be created and managed through AGPM</span></span>**

1.  <span data-ttu-id="652e1-298">AGPM クライアントがインストールされているコンピューターで、AGPM のエディターロールが割り当てられているユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="652e1-298">On a computer on which you have installed AGPM Client, log on with a user account that is assigned the Editor role in AGPM.</span></span>

2.  <span data-ttu-id="652e1-299">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-299">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="652e1-300">[ **Change Control** ] ノードを右クリックし、[**新しい**コントロールされた GPO] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-300">Right-click the **Change Control** node, and then click **New Controlled GPO**.</span></span>

4.  <span data-ttu-id="652e1-301">[**新しいコントロール**された GPO] ダイアログボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="652e1-301">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="652e1-302">要求のコピーを受信するには、[ **Cc** ] フィールドにメールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="652e1-302">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span>

    2.  <span data-ttu-id="652e1-303">新しい GPO の名前として「 **Mygpo** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="652e1-303">Type **MyGPO** as the name for the new GPO.</span></span>

    3.  <span data-ttu-id="652e1-304">新しい GPO にコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="652e1-304">Type a comment for the new GPO.</span></span>

    4.  <span data-ttu-id="652e1-305">[**ライブの作成**] をクリックして、新しい GPO が承認直後に運用環境に展開されるようにします。</span><span class="sxs-lookup"><span data-stu-id="652e1-305">Click **Create live** so that the new GPO will be deployed to the production environment immediately upon approval.</span></span> <span data-ttu-id="652e1-306">**[送信]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-306">Click **Submit**.</span></span>

5.  <span data-ttu-id="652e1-307">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-307">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="652e1-308">新しい GPO が [**保留中**] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="652e1-308">The new GPO is displayed on the **Pending** tab.</span></span>

**<span data-ttu-id="652e1-309">保留中の要求を承認して GPO を作成するには</span><span class="sxs-lookup"><span data-stu-id="652e1-309">To approve the pending request to create a GPO</span></span>**

1.  <span data-ttu-id="652e1-310">AGPM クライアントがインストールされているコンピューターで、AGPM で承認者の役割を持つユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="652e1-310">On a computer on which you have installed AGPM Client, log on with a user account that has the role of Approver in AGPM.</span></span>

2.  <span data-ttu-id="652e1-311">アカウントのメールの受信トレイを開き、GPO を作成するための編集要求を含む、AGPM エイリアスからの電子メールメッセージを受信したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="652e1-311">Open the e-mail inbox for the account, and notice that you have received an e-mail message from the AGPM alias with the Editor's request to create a GPO.</span></span>

3.  <span data-ttu-id="652e1-312">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-312">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

4.  <span data-ttu-id="652e1-313">[**コンテンツ**] タブで、[**保留中**] タブをクリックして、保留中の gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="652e1-313">On the **Contents** tab, click the **Pending** tab to display the pending GPOs.</span></span>

5.  <span data-ttu-id="652e1-314">[ **Mygpo**] を右クリックし、[**承認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-314">Right-click **MyGPO**, and then click **Approve**.</span></span>

6.  <span data-ttu-id="652e1-315">承認を確認し、[**コントロール**] タブに GPO を移動するには、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-315">Click **Yes** to confirm approval and move the GPO to the **Controlled** tab.</span></span>

### <a href="" id="bkmk-manage2"></a><span data-ttu-id="652e1-316">手順 2: GPO を編集する</span><span class="sxs-lookup"><span data-stu-id="652e1-316">Step 2: Edit a GPO</span></span>

<span data-ttu-id="652e1-317">Gpo を使って、コンピューターやユーザーの設定を構成し、多くのコンピューターまたはユーザーに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="652e1-317">You can use GPOs to configure computer or user settings and deploy them to many computers or users.</span></span> <span data-ttu-id="652e1-318">この手順では、編集者の役割を持つアカウントを使用して、アーカイブから GPO をチェックアウトし、その gpo をオフラインで編集し、編集した GPO をアーカイブにチェックインして、GPO の展開を実行して運用環境に要求します。</span><span class="sxs-lookup"><span data-stu-id="652e1-318">In this step, you use an account that has the Editor role to check out a GPO from the archive, edit the GPO offline, check the edited GPO into the archive, and request deployment of the GPO to the production environment.</span></span> <span data-ttu-id="652e1-319">このシナリオでは、パスワードの長さが8文字以上になるように、GPO の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="652e1-319">For this scenario, you configure a setting in the GPO to require that the password be at least eight characters long.</span></span>

**<span data-ttu-id="652e1-320">編集のためにアーカイブから GPO をチェックアウトするには</span><span class="sxs-lookup"><span data-stu-id="652e1-320">To check the GPO out from the archive for editing</span></span>**

1.  <span data-ttu-id="652e1-321">AGPM クライアントがインストールされているコンピューターで、AGPM のエディターの役割を持つユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="652e1-321">On a computer on which you have installed AGPM Client, log on with a user account that has the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="652e1-322">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-322">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="652e1-323">[詳細] ウィンドウの [**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理されている gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="652e1-323">On the **Contents** tab in the details pane, click the **Controlled** tab to display the controlled GPOs.</span></span>

4.  <span data-ttu-id="652e1-324">[ **Mygpo**] を右クリックし、 **[チェックアウト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-324">Right-click **MyGPO**, and then click **Check Out**.</span></span>

5.  <span data-ttu-id="652e1-325">チェックアウトされているときに、GPO の履歴に表示されるコメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-325">Type a comment to be displayed in the history of the GPO while it is checked out, and then click **OK**.</span></span>

6.  <span data-ttu-id="652e1-326">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-326">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="652e1-327">[**コントロール**] タブでは、GPO の状態は**チェックアウト済み**として識別されます。</span><span class="sxs-lookup"><span data-stu-id="652e1-327">On the **Controlled** tab, the state of the GPO is identified as **Checked Out**.</span></span>

**<span data-ttu-id="652e1-328">GPO をオフラインで編集し、パスワードの最小文字数を構成するには</span><span class="sxs-lookup"><span data-stu-id="652e1-328">To edit the GPO offline and configure the minimum password length</span></span>**

1.  <span data-ttu-id="652e1-329">[**コントロール**] タブで、[ **mygpo**] を右クリックし、[**編集**] をクリックして [**グループポリシー管理エディター** ] ウィンドウを開き、GPO のオフラインコピーを変更します。</span><span class="sxs-lookup"><span data-stu-id="652e1-329">On the **Controlled** tab, right-click **MyGPO**, and then click **Edit** to open the **Group Policy Management Editor** window and change an offline copy of the GPO.</span></span> <span data-ttu-id="652e1-330">このシナリオでは、パスワードの最小文字数を構成します。</span><span class="sxs-lookup"><span data-stu-id="652e1-330">For this scenario, configure the minimum password length:</span></span>

    1.  <span data-ttu-id="652e1-331">[**コンピューターの構成**] で、[**ポリシー**]、[ **Windows の設定**]、[**セキュリティの設定**]、[**アカウントポリシー**]、[**パスワードポリシー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-331">Under **Computer Configuration**, double-click **Policies**, **Windows Settings**, **Security Settings**, **Account Policies**, and **Password Policy**.</span></span>

    2.  <span data-ttu-id="652e1-332">詳細ウィンドウで、[**パスワードの最小文字数**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-332">In the details pane, double-click **Minimum password length**.</span></span>

    3.  <span data-ttu-id="652e1-333">[プロパティ] ウィンドウで、[**このポリシー設定を定義**する] チェックボックスをオンにし、文字数を**8**に設定して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-333">In the properties window, select the **Define this policy setting** check box, set the number of characters to **8**, and then click **OK**.</span></span>

2.  <span data-ttu-id="652e1-334">[**グループポリシー管理エディター** ] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="652e1-334">Close the **Group Policy Management Editor** window.</span></span>

**<span data-ttu-id="652e1-335">GPO をアーカイブにチェックインするには</span><span class="sxs-lookup"><span data-stu-id="652e1-335">To check the GPO into the archive</span></span>**

1.  <span data-ttu-id="652e1-336">[**コントロール**] タブで、[ **mygpo** ] を右クリックし、[**チェックイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-336">On the **Controlled** tab, right-click **MyGPO** and then click **Check In**.</span></span>

2.  <span data-ttu-id="652e1-337">コメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-337">Type a comment, and then click **OK**.</span></span>

3.  <span data-ttu-id="652e1-338">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-338">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="652e1-339">[**コントロール**] タブでは、GPO の状態は**チェックイン済み**として識別されます。</span><span class="sxs-lookup"><span data-stu-id="652e1-339">On the **Controlled** tab, the state of the GPO is identified as **Checked In**.</span></span>

**<span data-ttu-id="652e1-340">GPO の展開を運用環境に要求するには</span><span class="sxs-lookup"><span data-stu-id="652e1-340">To request the deployment of the GPO to the production environment</span></span>**

1.  <span data-ttu-id="652e1-341">[**コントロール**] タブで、[ **mygpo** ] を右クリックし、[**展開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-341">On the **Controlled** tab, right-click **MyGPO** and then click **Deploy**.</span></span>

2.  <span data-ttu-id="652e1-342">このアカウントは承認者または AGPM 管理者ではないため、展開の要求を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="652e1-342">Because this account is not an Approver or AGPM Administrator, you must submit a request for deployment.</span></span> <span data-ttu-id="652e1-343">要求のコピーを受信するには、[ **Cc** ] フィールドにメールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="652e1-343">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="652e1-344">GPO の履歴に表示するコメントを入力し、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-344">Type a comment to be displayed in the history of the GPO, and then click **Submit**.</span></span>

3.  <span data-ttu-id="652e1-345">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-345">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="652e1-346">[**保留中**] タブの gpo の一覧に**mygpo**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="652e1-346">**MyGPO** is displayed on the list of GPOs on the **Pending** tab.</span></span>

### <a href="" id="bkmk-manage3"></a><span data-ttu-id="652e1-347">手順 3: GPO を確認して展開する</span><span class="sxs-lookup"><span data-stu-id="652e1-347">Step 3: Review and deploy a GPO</span></span>

<span data-ttu-id="652e1-348">この手順では、承認者は、承認が必要かどうかを判断するために、承認者として、また GPO の設定を作成し、設定を分析します。</span><span class="sxs-lookup"><span data-stu-id="652e1-348">In this step, you act as an Approver, creating reports and analyzing the settings and changes to settings in the GPO to determine whether you should approve them.</span></span> <span data-ttu-id="652e1-349">GPO を評価したら、それを運用環境に展開し、GPO をドメインまたは組織単位 (OU) にリンクします。</span><span class="sxs-lookup"><span data-stu-id="652e1-349">After you evaluate the GPO, you deploy it to the production environment and link the GPO to a domain or an organizational unit (OU).</span></span> <span data-ttu-id="652e1-350">GPO は、そのドメインまたは OU 内のコンピューターのグループポリシーが更新された場合に有効になります。</span><span class="sxs-lookup"><span data-stu-id="652e1-350">The GPO takes effect when Group Policy is refreshed for computers in that domain or OU.</span></span>

**<span data-ttu-id="652e1-351">GPO の設定を確認するには</span><span class="sxs-lookup"><span data-stu-id="652e1-351">To review settings in the GPO</span></span>**

1. <span data-ttu-id="652e1-352">AGPM クライアントをインストールしたコンピューターで、AGPM で承認者の役割が割り当てられているユーザーアカウントを使用してログオンします。</span><span class="sxs-lookup"><span data-stu-id="652e1-352">On a computer on which you have installed AGPM Client, log on with a user account that is assigned the role of Approver in AGPM.</span></span> <span data-ttu-id="652e1-353">他のすべての役割に含まれるレビュー担当者の役割を持つグループポリシー管理者は、GPO の設定を確認できます。</span><span class="sxs-lookup"><span data-stu-id="652e1-353">Any Group Policy administrator with the Reviewer role, which is included in all of the other roles, can review the settings in a GPO.</span></span>

2. <span data-ttu-id="652e1-354">アカウントのメールの受信トレイを開き、GPO を展開するためのエディター要求で AGPM エイリアスからのメールメッセージを受信したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="652e1-354">Open the e-mail inbox for the account and notice that you have received an e-mail message from the AGPM alias with an Editor's request to deploy a GPO.</span></span>

3. <span data-ttu-id="652e1-355">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-355">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

4. <span data-ttu-id="652e1-356">[詳細] ウィンドウの [**コンテンツ**] タブで、[**保留中**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-356">On the **Contents** tab in the details pane, click the **Pending** tab.</span></span>

5. <span data-ttu-id="652e1-357">[ **Mygpo** ] をダブルクリックして、その履歴を表示します。</span><span class="sxs-lookup"><span data-stu-id="652e1-357">Double-click **MyGPO** to display its history.</span></span>

6. <span data-ttu-id="652e1-358">最新バージョンの MyGPO の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="652e1-358">Review the settings in the most recent version of MyGPO:</span></span>

   1.  <span data-ttu-id="652e1-359">[**履歴**] ウィンドウで、最新のタイムスタンプが付いた gpo のバージョンを右クリックし、[**設定**] をクリックし、[ **HTML レポート**] をクリックして、gpo の設定の概要を表示します。</span><span class="sxs-lookup"><span data-stu-id="652e1-359">In the **History** window, right-click the GPO version with the most recent time stamp, click **Settings**, and then click **HTML Report** to display a summary of the GPO's settings.</span></span>

   2.  <span data-ttu-id="652e1-360">Web ブラウザーで、[**すべて表示**] をクリックして、GPO のすべての設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="652e1-360">In the Web browser, click **show all** to display all the settings in the GPO.</span></span> <span data-ttu-id="652e1-361">ブラウザーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="652e1-361">Close the browser.</span></span>

7. <span data-ttu-id="652e1-362">最新バージョンの MyGPO と、アーカイブにチェックインされた最初のバージョンを比較します。</span><span class="sxs-lookup"><span data-stu-id="652e1-362">Compare the most recent version of MyGPO to the first version checked in to the archive:</span></span>

   1. <span data-ttu-id="652e1-363">[**履歴**] ウィンドウで、最新のタイムスタンプが付いた GPO バージョンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-363">In the **History** window, click the GPO version with the most recent time stamp.</span></span> <span data-ttu-id="652e1-364">CTRL キーを押した後、**コンピューターのバージョン**が \* \* \ \ \ \* \* \* の最も古い GPO バージョンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-364">Press CTRL and then click the oldest GPO version for which the **Computer Version** is not \*\*\\*\*\*.</span></span>

   2. <span data-ttu-id="652e1-365">[**差分**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-365">Click the **Differences** button.</span></span> <span data-ttu-id="652e1-366">[ **Account Policy/Password Policy** ] セクションが緑色で、前に**\ [+ \]** という番号が強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="652e1-366">The **Account Policies/Password Policy** section is highlighted in green and preceded by **\[+\]**.</span></span> <span data-ttu-id="652e1-367">これは、設定が GPO の後者のバージョンでのみ構成されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="652e1-367">This indicates that the setting is configured only in the latter version of the GPO.</span></span>

   3. <span data-ttu-id="652e1-368">[**アカウントポリシー**] の [パスワードポリシー] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-368">Click **Account Policies/Password Policy**.</span></span> <span data-ttu-id="652e1-369">[**パスワードの長さ**] の設定は緑で、その前に**\ [+ \]** が強調表示されています。これは、GPO の後者のバージョンでのみ構成されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="652e1-369">The **Minimum password length** setting is also highlighted in green and preceded by **\[+\]**, indicating that it is configured only in the latter version of the GPO.</span></span>

   4. <span data-ttu-id="652e1-370">Web ブラウザーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="652e1-370">Close the Web browser.</span></span>

**<span data-ttu-id="652e1-371">GPO を運用環境に展開するには</span><span class="sxs-lookup"><span data-stu-id="652e1-371">To deploy the GPO to the production environment</span></span>**

1.  <span data-ttu-id="652e1-372">[**保留中**] タブで、[ **mygpo** ] を右クリックし、[**承認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-372">On the **Pending** tab, right-click **MyGPO** and then click **Approve**.</span></span>

2.  <span data-ttu-id="652e1-373">GPO の履歴に含めるコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="652e1-373">Type a comment to include in the history of the GPO.</span></span>

3.  <span data-ttu-id="652e1-374">**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-374">Click **Yes**.</span></span> <span data-ttu-id="652e1-375">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-375">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="652e1-376">この GPO は、運用環境に展開されます。</span><span class="sxs-lookup"><span data-stu-id="652e1-376">The GPO is deployed to the production environment.</span></span>

**<span data-ttu-id="652e1-377">GPO をドメインまたは組織単位にリンクするには</span><span class="sxs-lookup"><span data-stu-id="652e1-377">To link the GPO to a domain or organizational unit</span></span>**

1.  <span data-ttu-id="652e1-378">GPMC で、構成した GPO を適用するドメインまたは組織単位 (OU) を右クリックし、[**既存の gpo にリンク**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-378">In the GPMC, right-click either the domain or an organizational unit (OU) to which you want to apply the GPO that you configured, and then click **Link an Existing GPO**.</span></span>

2.  <span data-ttu-id="652e1-379">[ **GPO の選択**] ダイアログボックスで、[ **mygpo**] をクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-379">In the **Select GPO** dialog box, click **MyGPO**, and then click **OK**.</span></span>

### <a href="" id="bkmk-manage4"></a><span data-ttu-id="652e1-380">手順 4: テンプレートを使用して GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="652e1-380">Step 4: Use a template to create a GPO</span></span>

<span data-ttu-id="652e1-381">この手順では、テンプレートを作成して使用するために、編集者ロールを持つアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="652e1-381">In this step, you use an account that has the Editor role to create and use a template.</span></span> <span data-ttu-id="652e1-382">このテンプレートは、新しい Gpo を作成するための出発点として使用する GPO の静的なバージョンです。</span><span class="sxs-lookup"><span data-stu-id="652e1-382">That template is a static version of a GPO for use as a starting point for creating new GPOs.</span></span> <span data-ttu-id="652e1-383">テンプレートを編集することはできませんが、テンプレートに基づいて新しい GPO を作成することはできます。</span><span class="sxs-lookup"><span data-stu-id="652e1-383">Although you cannot edit a template, you can create a new GPO based on a template.</span></span> <span data-ttu-id="652e1-384">テンプレートは、同じポリシー設定の多くを含む複数の Gpo をすばやく作成する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="652e1-384">Templates are useful for quickly creating multiple GPOs that include many of the same policy settings.</span></span>

**<span data-ttu-id="652e1-385">既存の GPO に基づいてテンプレートを作成するには</span><span class="sxs-lookup"><span data-stu-id="652e1-385">To create a template based on an existing GPO</span></span>**

1.  <span data-ttu-id="652e1-386">AGPM クライアントをインストールしたコンピューターで、AGPM のエディターの役割が割り当てられているユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="652e1-386">On a computer on which you have installed AGPM Client, log on with a user account that is assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="652e1-387">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-387">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="652e1-388">[詳細] ウィンドウの [**コンテンツ**] タブで、[**コントロール**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-388">On the **Contents** tab in the details pane, click the **Controlled** tab.</span></span>

4.  <span data-ttu-id="652e1-389">[ **Mygpo**] を右クリックし、[**テンプレートとして保存**] をクリックして、現在 mygpo に設定されているすべての設定が組み込まれているテンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="652e1-389">Right-click **MyGPO**, and then click **Save as Template** to create a template incorporating all settings currently in MyGPO.</span></span>

5.  <span data-ttu-id="652e1-390">テンプレートの名前として「 **MyTemplate** 」と入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-390">Type **MyTemplate** as the name for the template and a comment, and then click **OK**.</span></span>

6.  <span data-ttu-id="652e1-391">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-391">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="652e1-392">新しいテンプレートが [**テンプレート**] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="652e1-392">The new template appears on the **Templates** tab.</span></span>

**<span data-ttu-id="652e1-393">新しい GPO を AGPM で作成して管理するように要求するには</span><span class="sxs-lookup"><span data-stu-id="652e1-393">To request that a new GPO be created and managed through AGPM</span></span>**

1.  <span data-ttu-id="652e1-394">[**コントロール**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-394">Click the **Controlled** tab.</span></span>

2.  <span data-ttu-id="652e1-395">[ **Change Control** ] ノードを右クリックし、[**新しい**コントロールされた GPO] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-395">Right-click the **Change Control** node, and then click **New Controlled GPO**.</span></span>

3.  <span data-ttu-id="652e1-396">[**新しいコントロール**された GPO] ダイアログボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="652e1-396">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="652e1-397">要求のコピーを受信するには、[ **Cc** ] フィールドにメールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="652e1-397">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span>

    2.  <span data-ttu-id="652e1-398">新しい GPO の名前として「 **Myothergpo** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="652e1-398">Type **MyOtherGPO** as the name for the new GPO.</span></span>

    3.  <span data-ttu-id="652e1-399">新しい GPO にコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="652e1-399">Type a comment for the new GPO.</span></span>

    4.  <span data-ttu-id="652e1-400">[**ライブの作成**] をクリックして、新しい GPO が承認直後に運用環境に展開されるようにします。</span><span class="sxs-lookup"><span data-stu-id="652e1-400">Click **Create live** so that the new GPO will be deployed to the production environment immediately upon approval.</span></span>

    5.  <span data-ttu-id="652e1-401">[ **GPO テンプレート] から**[ **MyTemplate**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="652e1-401">For **From GPO template**, select **MyTemplate**.</span></span> <span data-ttu-id="652e1-402">**[送信]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-402">Click **Submit**.</span></span>

4.  <span data-ttu-id="652e1-403">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-403">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="652e1-404">新しい GPO が [**保留中**] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="652e1-404">The new GPO is displayed on the **Pending** tab.</span></span>

<span data-ttu-id="652e1-405">承認者の役割が割り当てられているアカウントを使用して、 [「手順 1: gpo を作成](#bkmk-manage1)する」の手順に従って、gpo を作成する保留中の要求を承認します。</span><span class="sxs-lookup"><span data-stu-id="652e1-405">Use an account that is assigned the role of Approver to approve the pending request to create the GPO as you did in [Step 1: Create a GPO](#bkmk-manage1).</span></span> <span data-ttu-id="652e1-406">MyTemplate には、MyGPO で構成したすべての設定が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="652e1-406">MyTemplate incorporates all the settings that you configured in MyGPO.</span></span> <span data-ttu-id="652e1-407">MyOtherGPO は MyTemplate を使用して作成されたため、最初に、MyTemplate が作成された時点で MyGPO に含まれていたすべての設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="652e1-407">Because MyOtherGPO was created using MyTemplate, it at first contains all the settings that MyGPO contained at the time that MyTemplate was created.</span></span> <span data-ttu-id="652e1-408">これを確認するには、MyOtherGPO と MyTemplate を比較するための差分レポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="652e1-408">You can confirm this by generating a difference report to compare MyOtherGPO to MyTemplate.</span></span>

**<span data-ttu-id="652e1-409">編集のためにアーカイブから GPO をチェックアウトするには</span><span class="sxs-lookup"><span data-stu-id="652e1-409">To check the GPO out from the archive for editing</span></span>**

1.  <span data-ttu-id="652e1-410">AGPM クライアントをインストールしたコンピューターで、AGPM のエディターの役割が割り当てられているユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="652e1-410">On a computer on which you have installed AGPM Client, log on with a user account that is assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="652e1-411">[ **Myothergpo**] を右クリックし、 **[チェックアウト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-411">Right-click **MyOtherGPO**, and then click **Check Out**.</span></span>

3.  <span data-ttu-id="652e1-412">チェックアウトされているときに、GPO の履歴に表示されるコメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-412">Type a comment to be displayed in the history of the GPO while it is checked out, and then click **OK**.</span></span>

4.  <span data-ttu-id="652e1-413">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-413">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="652e1-414">[**コントロール**] タブでは、GPO の状態は**チェックアウト済み**として識別されます。</span><span class="sxs-lookup"><span data-stu-id="652e1-414">On the **Controlled** tab, the state of the GPO is identified as **Checked Out**.</span></span>

**<span data-ttu-id="652e1-415">GPO をオフラインで編集して、アカウントのロックアウト期間を構成するには</span><span class="sxs-lookup"><span data-stu-id="652e1-415">To edit the GPO offline and configure the account lockout duration</span></span>**

1.  <span data-ttu-id="652e1-416">[**コントロール**] タブで、[ **myothergpo**] を右クリックし、[**編集**] をクリックして [**グループポリシー管理エディター** ] ウィンドウを開き、GPO のオフラインコピーを変更します。</span><span class="sxs-lookup"><span data-stu-id="652e1-416">On the **Controlled** tab, right-click **MyOtherGPO**, and then click **Edit** to open the **Group Policy Management Editor** window and change an offline copy of the GPO.</span></span> <span data-ttu-id="652e1-417">このシナリオでは、パスワードの最小文字数を構成します。</span><span class="sxs-lookup"><span data-stu-id="652e1-417">For this scenario, configure the minimum password length:</span></span>

    1.  <span data-ttu-id="652e1-418">[**コンピューターの構成**] で、 **[ポリシー**]、[ **Windows の設定**]、[セキュリティの**設定**]、[**アカウントポリシー**]、[**アカウントロックアウトのポリシー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-418">Under **Computer Configuration**, double-click **Policies**, **Windows Settings**, **Security Settings**, **Account Policies**, and **Account Lockout Policy**.</span></span>

    2.  <span data-ttu-id="652e1-419">詳細ウィンドウで、[**アカウントのロックアウトの期間**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-419">In the details pane, double-click **Account lockout duration**.</span></span>

    3.  <span data-ttu-id="652e1-420">[プロパティ] ウィンドウで、[**このポリシー設定を定義**する] チェックボックスをオンにし、期間を**30**分に設定して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-420">In the properties window, check **Define this policy setting**, set the duration to **30** minutes, and then click **OK**.</span></span>

2.  <span data-ttu-id="652e1-421">[**グループポリシー管理エディター** ] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="652e1-421">Close the **Group Policy Management Editor** window.</span></span>

<span data-ttu-id="652e1-422">[「手順 2: GPO を編集](#bkmk-manage2)する」の手順に従って、myothergpo をアーカイブに確認し、展開を要求します。</span><span class="sxs-lookup"><span data-stu-id="652e1-422">Check MyOtherGPO into the archive and request deployment as you did for MyGPO in [Step 2: Edit a GPO](#bkmk-manage2).</span></span> <span data-ttu-id="652e1-423">MyOtherGPO を MyGPO または MyTemplate に比較するには、差分レポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="652e1-423">You can compare MyOtherGPO to MyGPO or to MyTemplate by using difference reports.</span></span> <span data-ttu-id="652e1-424">レビュー担当者の役割を含むすべてのアカウント (AGPM 管理者 \ [フルコントロール \]、承認者、編集者、または校閲者) は、レポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="652e1-424">Any account that includes the Reviewer role (AGPM Administrator \[Full Control\], Approver, Editor, or Reviewer) can generate reports.</span></span>

**<span data-ttu-id="652e1-425">GPO を別の GPO とテンプレートに比較するには</span><span class="sxs-lookup"><span data-stu-id="652e1-425">To compare a GPO to another GPO and to a template</span></span>**

1.  <span data-ttu-id="652e1-426">MyGPO と MyOtherGPO を比較するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="652e1-426">To compare MyGPO and MyOtherGPO:</span></span>

    1.  <span data-ttu-id="652e1-427">[**コントロール**] タブで、[ **mygpo**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-427">On the **Controlled** tab, click **MyGPO**.</span></span> <span data-ttu-id="652e1-428">CTRL キーを押してから、[ **Myothergpo**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-428">Press CTRL and then click **MyOtherGPO**.</span></span>

    2.  <span data-ttu-id="652e1-429">[ **Myothergpo**] を右クリックし、[**相違点**] をポイントして、[ **HTML レポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-429">Right-click **MyOtherGPO**, point to **Differences**, and then click **HTML Report**.</span></span>

2.  <span data-ttu-id="652e1-430">MyOtherGPO と MyTemplate を比較するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="652e1-430">To compare MyOtherGPO and MyTemplate:</span></span>

    1.  <span data-ttu-id="652e1-431">[**コントロール**] タブで、[ **myothergpo**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-431">On the **Controlled** tab, click **MyOtherGPO**.</span></span>

    2.  <span data-ttu-id="652e1-432">[ **Myothergpo**] を右クリックし、[**相違点**] をポイントして、[**テンプレート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-432">Right-click **MyOtherGPO**, point to **Differences**, and then click **Template**.</span></span>

    3.  <span data-ttu-id="652e1-433">[ **MyTemplate** And **HTML レポート**] を選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-433">Select **MyTemplate** and **HTML Report**, and then click **OK**.</span></span>

### <a href="" id="bkmk-manage5"></a><span data-ttu-id="652e1-434">手順 5: GPO を削除および復元する</span><span class="sxs-lookup"><span data-stu-id="652e1-434">Step 5: Delete and restore a GPO</span></span>

<span data-ttu-id="652e1-435">この手順では、GPO を削除するための承認者としての役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="652e1-435">In this step, you act as an Approver to delete a GPO.</span></span>

**<span data-ttu-id="652e1-436">GPO を削除するには</span><span class="sxs-lookup"><span data-stu-id="652e1-436">To delete a GPO</span></span>**

1.  <span data-ttu-id="652e1-437">AGPM クライアントがインストールされているコンピューターで、承認者の役割が割り当てられているユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="652e1-437">On a computer on which you have installed AGPM Client, log on with a user account that is assigned the role of Approver.</span></span>

2.  <span data-ttu-id="652e1-438">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-438">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="652e1-439">[**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="652e1-439">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

4.  <span data-ttu-id="652e1-440">[ **Mygpo**] を右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-440">Right-click **MyGPO**, and then click **Delete**.</span></span> <span data-ttu-id="652e1-441">[**アーカイブと運用] から [gpo の削除**] をクリックして、アーカイブ内のバージョンと、展開されたバージョンの両方が、運用環境で削除されるようにします。</span><span class="sxs-lookup"><span data-stu-id="652e1-441">Click **Delete GPO from archive and production** to delete both the version in the archive and the deployed version of the GPO in the production environment.</span></span>

5.  <span data-ttu-id="652e1-442">GPO の監査トレールに表示されるコメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-442">Type a comment to be displayed in the audit trail for the GPO, and then click **OK**.</span></span>

6.  <span data-ttu-id="652e1-443">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-443">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="652e1-444">GPO は [**コントロール**] タブから削除され、[**ごみ箱**] タブに表示され、そこで復元または破棄することができます。</span><span class="sxs-lookup"><span data-stu-id="652e1-444">The GPO is removed from the **Controlled** tab and is displayed on the **Recycle Bin** tab, where it can be restored or destroyed.</span></span>

<span data-ttu-id="652e1-445">場合によっては、GPO を削除した後で問題が解決されることがあります。</span><span class="sxs-lookup"><span data-stu-id="652e1-445">Occasionally you may discover after you delete a GPO that it is still needed.</span></span> <span data-ttu-id="652e1-446">この手順では、削除された GPO を復元するための承認者としての役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="652e1-446">In this step, you act as an Approver to restore a GPO that was deleted.</span></span>

**<span data-ttu-id="652e1-447">削除された GPO を復元するには</span><span class="sxs-lookup"><span data-stu-id="652e1-447">To restore a deleted GPO</span></span>**

1.  <span data-ttu-id="652e1-448">[**コンテンツ**] タブで、[**ごみ箱**] タブをクリックして、削除された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="652e1-448">On the **Contents** tab, click the **Recycle Bin** tab to display deleted GPOs.</span></span>

2.  <span data-ttu-id="652e1-449">[ **Mygpo**] を右クリックし、[**復元**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-449">Right-click **MyGPO**, and then click **Restore**.</span></span>

3.  <span data-ttu-id="652e1-450">GPO の履歴に表示するコメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-450">Type a comment to be displayed in the history of the GPO, and then click **OK**.</span></span>

4.  <span data-ttu-id="652e1-451">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-451">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="652e1-452">GPO は [**ごみ箱**] タブから削除され、[**コントロール**] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="652e1-452">The GPO is removed from the **Recycle Bin** tab and is displayed on the **Controlled** tab.</span></span>

    <span data-ttu-id="652e1-453">**注** GPO をアーカイブに復元しても、運用環境に自動的に再配置されることはありません。</span><span class="sxs-lookup"><span data-stu-id="652e1-453">**Note** Restoring a GPO to the archive does not automatically redeploy it to the production environment.</span></span> <span data-ttu-id="652e1-454">GPO を運用環境に戻すには、「[手順 3: gpo を確認して展開](#bkmk-manage3)する」のように gpo を展開します。</span><span class="sxs-lookup"><span data-stu-id="652e1-454">To return the GPO to the production environment, deploy the GPO as in [Step 3: Review and deploy a GPO](#bkmk-manage3).</span></span>

     

<span data-ttu-id="652e1-455">GPO の編集と展開を行った後に、GPO の最近の変更によって問題が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="652e1-455">After editing and deploying a GPO, you may discover that recent changes to the GPO are causing a problem.</span></span> <span data-ttu-id="652e1-456">この手順では、以前のバージョンの GPO にロールバックするための承認者としての役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="652e1-456">In this step, you act as an Approver to roll back to an earlier version of the GPO.</span></span> <span data-ttu-id="652e1-457">GPO の履歴で任意のバージョンにロールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="652e1-457">You can roll back to any version in the history of the GPO.</span></span> <span data-ttu-id="652e1-458">コメントとラベルを使用して既知の適切なバージョンを識別したり、特定の変更が行われた日時を確認したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="652e1-458">You can use comments and labels to identify known good versions and when specific changes were made.</span></span>

**<span data-ttu-id="652e1-459">以前のバージョンの GPO にロールバックするには</span><span class="sxs-lookup"><span data-stu-id="652e1-459">To roll back to an earlier version of a GPO</span></span>**

1.  <span data-ttu-id="652e1-460">[**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="652e1-460">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

2.  <span data-ttu-id="652e1-461">[ **Mygpo** ] をダブルクリックして、その履歴を表示します。</span><span class="sxs-lookup"><span data-stu-id="652e1-461">Double-click **MyGPO** to display its history.</span></span>

3.  <span data-ttu-id="652e1-462">展開するバージョンを右クリックし、[**展開**] をクリックして、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-462">Right-click the version to be deployed, click **Deploy**, and then click **Yes**.</span></span>

4.  <span data-ttu-id="652e1-463">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-463">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="652e1-464">[**履歴**] ウィンドウで、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-464">In the **History** window, click **Close**.</span></span>

    <span data-ttu-id="652e1-465">**注** 再展開されたバージョンが目的のバージョンであることを確認するには、2つのバージョンについての差異レポートを確認します。</span><span class="sxs-lookup"><span data-stu-id="652e1-465">**Note** To verify that the version that was redeployed is the version intended, examine a difference report for the two versions.</span></span> <span data-ttu-id="652e1-466">GPO の [**履歴**] ウィンドウで、2つのバージョンを選択して右クリックし、[**相違**点] をポイントして、[ **HTML レポート**] または [ **XML レポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="652e1-466">In the **History** window for the GPO, select the two versions, right-click them, point to **Difference**, and then click either **HTML Report** or **XML Report**.</span></span>

     

 

 





