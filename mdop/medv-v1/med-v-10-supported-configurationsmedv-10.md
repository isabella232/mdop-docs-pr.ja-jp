---
title: MED-V 1.0 でサポートされる構成
description: MED-V 1.0 でサポートされる構成
author: dansimp
ms.assetid: 74643de6-549e-4177-a559-6407e156ed3a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3b8ffdfb6e34fe7888ea5ace0ff7264bd978a548
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812610"
---
# <span data-ttu-id="2fc7a-103">MED-V 1.0 でサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="2fc7a-103">MED-V 1.0 Supported Configurations</span></span>


<span data-ttu-id="2fc7a-104">このトピックでは、お客様の環境に Microsoft Enterprise Desktop Virtualization (MED-V) 1.0 をインストールして実行するために必要な要件を示します。</span><span class="sxs-lookup"><span data-stu-id="2fc7a-104">This topic specifies the requirements necessary to install and run Microsoft Enterprise Desktop Virtualization (MED-V) 1.0 in your environment.</span></span>

## <span data-ttu-id="2fc7a-105">MED-V 1.0 クライアントシステム要件</span><span class="sxs-lookup"><span data-stu-id="2fc7a-105">MED-V 1.0 Client System Requirements</span></span>


### <span data-ttu-id="2fc7a-106">MED-V クライアントオペレーティングシステム要件</span><span class="sxs-lookup"><span data-stu-id="2fc7a-106">MED-V Client Operating System Requirements</span></span>

<span data-ttu-id="2fc7a-107">次の表は、MED-V 1.0 クライアントインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="2fc7a-107">The following table lists the operating systems that are supported for MED-V 1.0 client installation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2fc7a-108">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="2fc7a-108">Operating System</span></span></th>
<th align="left"><span data-ttu-id="2fc7a-109">エディション</span><span class="sxs-lookup"><span data-stu-id="2fc7a-109">Edition</span></span></th>
<th align="left"><span data-ttu-id="2fc7a-110">Service Pack</span><span class="sxs-lookup"><span data-stu-id="2fc7a-110">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="2fc7a-111">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="2fc7a-111">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2fc7a-112">Windows XP</span><span class="sxs-lookup"><span data-stu-id="2fc7a-112">Windows XP</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fc7a-113">プロフェッショナルエディション</span><span class="sxs-lookup"><span data-stu-id="2fc7a-113">Professional Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fc7a-114">SP2 または SP3</span><span class="sxs-lookup"><span data-stu-id="2fc7a-114">SP2 or SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fc7a-115">x86</span><span class="sxs-lookup"><span data-stu-id="2fc7a-115">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2fc7a-116">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="2fc7a-116">Windows Vista</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fc7a-117">ビジネス、エンタープライズ、または究極のエディション</span><span class="sxs-lookup"><span data-stu-id="2fc7a-117">Business, Enterprise, or Ultimate Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fc7a-118">SP1 または SP2</span><span class="sxs-lookup"><span data-stu-id="2fc7a-118">SP1 or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fc7a-119">x86</span><span class="sxs-lookup"><span data-stu-id="2fc7a-119">x86</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="2fc7a-120">注</span><span class="sxs-lookup"><span data-stu-id="2fc7a-120">Note</span></span>**  
<span data-ttu-id="2fc7a-121">MED-V クライアントは、ネイティブ x64 モードでは実行されません。</span><span class="sxs-lookup"><span data-stu-id="2fc7a-121">MED-V client does not run in native x64 mode.</span></span> <span data-ttu-id="2fc7a-122">代わりに、MED-V は、64ビットコンピューター上の windows 64 ビット (WOW64) モードの Windows で実行されます。</span><span class="sxs-lookup"><span data-stu-id="2fc7a-122">Instead, MED-V runs in Windows on Windows 64-bit (WOW64) mode on 64-bit computers.</span></span>



### <a href="" id="med-v-1-0-client-configuration-"></a><span data-ttu-id="2fc7a-123">MED-V 1.0 クライアント構成</span><span class="sxs-lookup"><span data-stu-id="2fc7a-123">MED-V 1.0 Client Configuration</span></span>

**<span data-ttu-id="2fc7a-124">.NET Framework のバージョン</span><span class="sxs-lookup"><span data-stu-id="2fc7a-124">.NET Framework Version</span></span>**

<span data-ttu-id="2fc7a-125">以下のバージョンの Microsoft .NET Framework は、MED-V 1.0 クライアントのインストールでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2fc7a-125">The following versions of the Microsoft .NET Framework are supported for MED-V 1.0 client installation:</span></span>

-   <span data-ttu-id="2fc7a-126">.NET Framework 2.0 または .NET Framework 2.0 SP1</span><span class="sxs-lookup"><span data-stu-id="2fc7a-126">.NET Framework 2.0 or .NET Framework 2.0 SP1</span></span>

-   <span data-ttu-id="2fc7a-127">.NET Framework 3.0 または .NET Framework 3.0 SP1</span><span class="sxs-lookup"><span data-stu-id="2fc7a-127">.NET Framework 3.0 or .NET Framework 3.0 SP1</span></span>

-   <span data-ttu-id="2fc7a-128">.NET Framework 3.5 または .NET Framework 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="2fc7a-128">.NET Framework 3.5 or .NET Framework 3.5 SP1</span></span>

**<span data-ttu-id="2fc7a-129">仮想化エンジン</span><span class="sxs-lookup"><span data-stu-id="2fc7a-129">Virtualization Engine</span></span>**

<span data-ttu-id="2fc7a-130">Microsoft サポート技術情報の記事974918で説明されている修正プログラムを含む microsoft Virtual PC 2007 SP1 は、次の構成での MED-V 1.0 クライアントのインストールでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2fc7a-130">Microsoft Virtual PC 2007 SP1 with the hotfix that is described in Microsoft Knowledge Base article 974918 is supported for MED-V 1.0 client installation in the following configurations:</span></span>

-   <span data-ttu-id="2fc7a-131">静的仮想ハードディスク (VHD) ファイル</span><span class="sxs-lookup"><span data-stu-id="2fc7a-131">Static Virtual Hard Disk (VHD) file</span></span>

-   <span data-ttu-id="2fc7a-132">同じディレクトリ内にある複数の VHD ファイル</span><span class="sxs-lookup"><span data-stu-id="2fc7a-132">Multiple VHD files located within the same directory</span></span>

-   <span data-ttu-id="2fc7a-133">動的 VHD ファイル</span><span class="sxs-lookup"><span data-stu-id="2fc7a-133">Dynamic VHD file</span></span>

**<span data-ttu-id="2fc7a-134">インターネット ブラウザー</span><span class="sxs-lookup"><span data-stu-id="2fc7a-134">Internet Browser</span></span>**

<span data-ttu-id="2fc7a-135">Windows Internet Explorer 7 と Windows Internet Explorer 8 は、MED-V 1.0 クライアントのインストールでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2fc7a-135">Windows Internet Explorer 7 and Windows Internet Explorer 8 are supported for MED-V 1.0 client installation.</span></span>

**<span data-ttu-id="2fc7a-136">Microsoft Hyper-V Server</span><span class="sxs-lookup"><span data-stu-id="2fc7a-136">Microsoft Hyper-V Server</span></span>**

<span data-ttu-id="2fc7a-137">MED-V クライアントは、Microsoft Hyper-v server 環境ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2fc7a-137">The MED-V client is not supported in a Microsoft Hyper-V server environment.</span></span>

## <span data-ttu-id="2fc7a-138">MED-V 1.0 ワークスペースシステム要件</span><span class="sxs-lookup"><span data-stu-id="2fc7a-138">MED-V 1.0 Workspace System Requirements</span></span>


### <span data-ttu-id="2fc7a-139">MED-V ワークスペースのオペレーティングシステム要件</span><span class="sxs-lookup"><span data-stu-id="2fc7a-139">MED-V Workspace Operating System Requirements</span></span>

<span data-ttu-id="2fc7a-140">次の表は、MED-V 1.0 ワークスペースでサポートされているオペレーティングシステムの一覧です。</span><span class="sxs-lookup"><span data-stu-id="2fc7a-140">The following table lists the operating systems supported for MED-V 1.0 workspaces.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2fc7a-141">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="2fc7a-141">Operating System</span></span></th>
<th align="left"><span data-ttu-id="2fc7a-142">エディション</span><span class="sxs-lookup"><span data-stu-id="2fc7a-142">Edition</span></span></th>
<th align="left"><span data-ttu-id="2fc7a-143">Service Pack</span><span class="sxs-lookup"><span data-stu-id="2fc7a-143">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="2fc7a-144">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="2fc7a-144">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2fc7a-145">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="2fc7a-145">Windows 2000</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fc7a-146">Professional</span><span class="sxs-lookup"><span data-stu-id="2fc7a-146">Professional</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fc7a-147">SP4</span><span class="sxs-lookup"><span data-stu-id="2fc7a-147">SP4</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fc7a-148">X86</span><span class="sxs-lookup"><span data-stu-id="2fc7a-148">X86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2fc7a-149">Windows XP</span><span class="sxs-lookup"><span data-stu-id="2fc7a-149">Windows XP</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fc7a-150">プロフェッショナルエディション</span><span class="sxs-lookup"><span data-stu-id="2fc7a-150">Professional Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fc7a-151">SP2 または SP3</span><span class="sxs-lookup"><span data-stu-id="2fc7a-151">SP2 or SP3</span></span></p>
<div class="alert">
<strong><span data-ttu-id="2fc7a-152">注</span><span class="sxs-lookup"><span data-stu-id="2fc7a-152">Note</span></span></strong><br/><p><span data-ttu-id="2fc7a-153">MED-V ワークスペースが将来のバージョンの MED-V と互換性があることを確認するには、SP3 をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2fc7a-153">SP3 is recommended to ensure that the MED-V workspace will be compatible with future versions of MED-V.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="2fc7a-154">x86</span><span class="sxs-lookup"><span data-stu-id="2fc7a-154">x86</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="med-v-1-0-workspace-configuration-"></a><span data-ttu-id="2fc7a-155">MED-V 1.0 ワークスペースの構成</span><span class="sxs-lookup"><span data-stu-id="2fc7a-155">MED-V 1.0 Workspace Configuration</span></span>

**<span data-ttu-id="2fc7a-156">.NET Framework のバージョン</span><span class="sxs-lookup"><span data-stu-id="2fc7a-156">.NET Framework Version</span></span>**

<span data-ttu-id="2fc7a-157">MED-V を使用するには、MED-V 1.0 workspace のインストールでサポートされている次のいずれかのバージョンの Microsoft .NET Framework が必要です。</span><span class="sxs-lookup"><span data-stu-id="2fc7a-157">MED-V requires one of the following supported versions of the Microsoft .NET Framework for MED-V 1.0 workspace installation:</span></span>

-   <span data-ttu-id="2fc7a-158">.NET Framework 2.0 SP1</span><span class="sxs-lookup"><span data-stu-id="2fc7a-158">.NET Framework 2.0 SP1</span></span>

-   <span data-ttu-id="2fc7a-159">.NET Framework 3.0 SP1</span><span class="sxs-lookup"><span data-stu-id="2fc7a-159">.NET Framework 3.0 SP1</span></span>

-   <span data-ttu-id="2fc7a-160">.NET Framework 3.5 または .NET Framework 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="2fc7a-160">.NET Framework 3.5 or .NET Framework 3.5 SP1</span></span>

**<span data-ttu-id="2fc7a-161">注</span><span class="sxs-lookup"><span data-stu-id="2fc7a-161">Note</span></span>**  
<span data-ttu-id="2fc7a-162">MED-V ワークスペースが将来のバージョンの MED-V と互換性があることを確認するには、.NET Framework 3.5 SP1 が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="2fc7a-162">.NET Framework 3.5 SP1 is recommended to ensure that the MED-V workspace will be compatible with future versions of MED-V.</span></span>



**<span data-ttu-id="2fc7a-163">インターネット ブラウザー</span><span class="sxs-lookup"><span data-stu-id="2fc7a-163">Internet Browser</span></span>**

<span data-ttu-id="2fc7a-164">Windows Internet Explorer 6 SP2 と Windows Internet Explorer 7 は、MED-V 1.0 ワークスペースのインストールでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2fc7a-164">Windows Internet Explorer 6 SP2 and Windows Internet Explorer 7 are supported for the MED-V 1.0 workspace installation.</span></span>

### <a href="" id="med-v-workspace-images-"></a><span data-ttu-id="2fc7a-165">MED-V ワークスペースのイメージ</span><span class="sxs-lookup"><span data-stu-id="2fc7a-165">MED-V Workspace Images</span></span>

<span data-ttu-id="2fc7a-166">MED-V ワークスペースの画像は、Virtual PC 2007 SP1 を使用して作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fc7a-166">MED-V workspace images must be created by using Virtual PC 2007 SP1.</span></span>

## <span data-ttu-id="2fc7a-167">MED-V 1.0 サーバーシステム要件</span><span class="sxs-lookup"><span data-stu-id="2fc7a-167">MED-V 1.0 Server System Requirements</span></span>


### <span data-ttu-id="2fc7a-168">MED-V 1.0 サーバーオペレーティングシステム要件</span><span class="sxs-lookup"><span data-stu-id="2fc7a-168">MED-V 1.0 Server Operating System Requirements</span></span>

<span data-ttu-id="2fc7a-169">次の表は、MED-V 1.0 サーバーインストールでサポートされているオペレーティングシステムの一覧です。</span><span class="sxs-lookup"><span data-stu-id="2fc7a-169">The following table lists the operating systems supported for MED-V 1.0 server installations.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2fc7a-170">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="2fc7a-170">Operating System</span></span></th>
<th align="left"><span data-ttu-id="2fc7a-171">エディション</span><span class="sxs-lookup"><span data-stu-id="2fc7a-171">Edition</span></span></th>
<th align="left"><span data-ttu-id="2fc7a-172">Service Pack</span><span class="sxs-lookup"><span data-stu-id="2fc7a-172">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="2fc7a-173">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="2fc7a-173">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2fc7a-174">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="2fc7a-174">Windows Server 2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fc7a-175">Standard または Enterprise</span><span class="sxs-lookup"><span data-stu-id="2fc7a-175">Standard or Enterprise</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fc7a-176">なし</span><span class="sxs-lookup"><span data-stu-id="2fc7a-176">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fc7a-177">X86 または x64</span><span class="sxs-lookup"><span data-stu-id="2fc7a-177">X86 or x64</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="med-v-1-0-server-configuration-"></a><span data-ttu-id="2fc7a-178">MED-V 1.0 サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="2fc7a-178">MED-V 1.0 Server Configuration</span></span>

**<span data-ttu-id="2fc7a-179">.NET Framework のバージョン</span><span class="sxs-lookup"><span data-stu-id="2fc7a-179">.NET Framework Version</span></span>**

<span data-ttu-id="2fc7a-180">MED-V を使用するには、MED-V 1.0 workspace のインストールでサポートされている次のいずれかのバージョンの Microsoft .NET Framework が必要です。</span><span class="sxs-lookup"><span data-stu-id="2fc7a-180">MED-V requires one of the following supported versions of the Microsoft .NET Framework for MED-V 1.0 workspace installation:</span></span>

-   <span data-ttu-id="2fc7a-181">.NET Framework 2.0 または .NET Framework 2.0 SP1</span><span class="sxs-lookup"><span data-stu-id="2fc7a-181">.NET Framework 2.0 or .NET Framework 2.0 SP1</span></span>

-   <span data-ttu-id="2fc7a-182">.NET Framework 3.0 または .NET Framework 3.0 SP1</span><span class="sxs-lookup"><span data-stu-id="2fc7a-182">.NET Framework 3.0 or .NET Framework 3.0 SP1</span></span>

-   <span data-ttu-id="2fc7a-183">.NET Framework 3.5 または .NET Framework 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="2fc7a-183">.NET Framework 3.5 or .NET Framework 3.5 SP1</span></span>

**<span data-ttu-id="2fc7a-184">Microsoft SQL Server バージョン</span><span class="sxs-lookup"><span data-stu-id="2fc7a-184">Microsoft SQL Server Version</span></span>**

<span data-ttu-id="2fc7a-185">次のバージョンの Microsoft SQL Server は、SQL Server がローカルにインストールされているか、または MED-V 1.0 サーバーからリモートでインストールされている場合に、MED-V 1.0 でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2fc7a-185">The following versions of Microsoft SQL Server are supported for MED-V 1.0 when SQL Server is installed locally or remotely from the MED-V 1.0 Server:</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2fc7a-186">SQL Server のバージョン</span><span class="sxs-lookup"><span data-stu-id="2fc7a-186">SQL Server Version</span></span></th>
<th align="left"><span data-ttu-id="2fc7a-187">エディション</span><span class="sxs-lookup"><span data-stu-id="2fc7a-187">Edition</span></span></th>
<th align="left"><span data-ttu-id="2fc7a-188">Service Pack</span><span class="sxs-lookup"><span data-stu-id="2fc7a-188">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="2fc7a-189">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="2fc7a-189">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2fc7a-190">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="2fc7a-190">SQL Server 2005</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fc7a-191">Express、Standard、Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="2fc7a-191">Express, Standard, or Enterprise Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fc7a-192">SP2</span><span class="sxs-lookup"><span data-stu-id="2fc7a-192">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fc7a-193">X86 または x64</span><span class="sxs-lookup"><span data-stu-id="2fc7a-193">X86 or x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2fc7a-194">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="2fc7a-194">SQL Server 2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fc7a-195">エクスプレス、標準、またはエンタープライズ</span><span class="sxs-lookup"><span data-stu-id="2fc7a-195">Express, Standard, or Enterprise</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fc7a-196">なし</span><span class="sxs-lookup"><span data-stu-id="2fc7a-196">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="2fc7a-197">X86 または x64</span><span class="sxs-lookup"><span data-stu-id="2fc7a-197">X86 or x64</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="2fc7a-198">Microsoft Hyper-V Server</span><span class="sxs-lookup"><span data-stu-id="2fc7a-198">Microsoft Hyper-V Server</span></span>**

<span data-ttu-id="2fc7a-199">MED-V サーバーは、Microsoft Hyper-v server 環境でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2fc7a-199">The MED-V server is supported in a Microsoft Hyper-V server environment.</span></span>

## <span data-ttu-id="2fc7a-200">MED-V 1.0 のグローバリゼーション情報</span><span class="sxs-lookup"><span data-stu-id="2fc7a-200">MED-V 1.0 Globalization Information</span></span>


<span data-ttu-id="2fc7a-201">MED-V は英語以外の言語ではリリースされませんが、MED-V 1.0 クライアント、ワークスペース、サーバーのインストールでは、次の Windows オペレーティングシステム言語バージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2fc7a-201">Although MED-V is not released in languages other than English, the following Windows operating system language versions are supported for the MED-V 1.0 client, workspace, and server installations:</span></span>

-   <span data-ttu-id="2fc7a-202">英語</span><span class="sxs-lookup"><span data-stu-id="2fc7a-202">English</span></span>

-   <span data-ttu-id="2fc7a-203">フランス語</span><span class="sxs-lookup"><span data-stu-id="2fc7a-203">French</span></span>

-   <span data-ttu-id="2fc7a-204">ドイツ語</span><span class="sxs-lookup"><span data-stu-id="2fc7a-204">German</span></span>

-   <span data-ttu-id="2fc7a-205">イタリア語</span><span class="sxs-lookup"><span data-stu-id="2fc7a-205">Italian</span></span>

-   <span data-ttu-id="2fc7a-206">スペイン語</span><span class="sxs-lookup"><span data-stu-id="2fc7a-206">Spanish</span></span>

-   <span data-ttu-id="2fc7a-207">ポルトガル語 (ブラジル)</span><span class="sxs-lookup"><span data-stu-id="2fc7a-207">Portuguese (Brazil)</span></span>









