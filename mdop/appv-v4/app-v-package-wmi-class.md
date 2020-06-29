---
title: App-V Package WMI クラス
description: App-V Package WMI クラス
author: dansimp
ms.assetid: 0fc26c3b-9706-4804-be2d-645771dc33ae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa452afaaeb2f490c179a928b24de47207d6dc63
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819797"
---
# <span data-ttu-id="2ee9a-103">App-V Package WMI クラス</span><span class="sxs-lookup"><span data-stu-id="2ee9a-103">App-V Package WMI Class</span></span>


<span data-ttu-id="2ee9a-104">Application Virtualization (App-v) クライアントでは、 **Package**クラスは、クライアント上のすべての仮想パッケージを表す Windows Management INSTRUMENTATION (WMI) クラスです。</span><span class="sxs-lookup"><span data-stu-id="2ee9a-104">In the Application Virtualization (App-V) Client, the **Package** class is a Windows Management Instrumentation (WMI) class that represents all the virtual packages on the client.</span></span> <span data-ttu-id="2ee9a-105">仮想パッケージには、多くの仮想アプリケーションを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2ee9a-105">The virtual packages can contain many virtual applications.</span></span>

## <span data-ttu-id="2ee9a-106">構文</span><span class="sxs-lookup"><span data-stu-id="2ee9a-106">Syntax</span></span>


``` syntax
class Package
{
      string Name;
      string Version;
      string PackageGUID;
      string SftPath;
      uint64 TotalSize;
      uint64 CachedSize;
      uint64 LaunchSize;
      uint64 CachedLaunchSize;
      boolean InUse;
      boolean Locked;
      uint16 CachedPercentage;
      string VersionGUID;
 };
```

## <span data-ttu-id="2ee9a-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2ee9a-107">Properties</span></span>


<a href="" id="name"></a>**<span data-ttu-id="2ee9a-108">名前</span><span class="sxs-lookup"><span data-stu-id="2ee9a-108">Name</span></span>**  
<span data-ttu-id="2ee9a-109">データ型:**文字列**</span><span class="sxs-lookup"><span data-stu-id="2ee9a-109">Data type: **String**</span></span>

<span data-ttu-id="2ee9a-110">アクセスの種類: 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="2ee9a-110">Access type: Read-only</span></span>

<span data-ttu-id="2ee9a-111">限定子: なし</span><span class="sxs-lookup"><span data-stu-id="2ee9a-111">Qualifiers: None</span></span>

<span data-ttu-id="2ee9a-112">仮想パッケージのユーザーフレンドリ名。</span><span class="sxs-lookup"><span data-stu-id="2ee9a-112">The user-friendly name of the virtual package.</span></span>

<a href="" id="version"></a>**<span data-ttu-id="2ee9a-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="2ee9a-113">Version</span></span>**  
<span data-ttu-id="2ee9a-114">データ型:**文字列**</span><span class="sxs-lookup"><span data-stu-id="2ee9a-114">Data type: **String**</span></span>

<span data-ttu-id="2ee9a-115">アクセスの種類: 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="2ee9a-115">Access type: Read-only</span></span>

<span data-ttu-id="2ee9a-116">限定子: なし</span><span class="sxs-lookup"><span data-stu-id="2ee9a-116">Qualifiers: None</span></span>

<span data-ttu-id="2ee9a-117">仮想パッケージのバージョン。</span><span class="sxs-lookup"><span data-stu-id="2ee9a-117">The version of the virtual package.</span></span>

<a href="" id="packageguid"></a>**<span data-ttu-id="2ee9a-118">PackageGUID</span><span class="sxs-lookup"><span data-stu-id="2ee9a-118">PackageGUID</span></span>**  
<span data-ttu-id="2ee9a-119">データ型:**文字列**</span><span class="sxs-lookup"><span data-stu-id="2ee9a-119">Data type: **String**</span></span>

<span data-ttu-id="2ee9a-120">アクセスの種類: 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="2ee9a-120">Access type: Read-only</span></span>

<span data-ttu-id="2ee9a-121">修飾子: キー</span><span class="sxs-lookup"><span data-stu-id="2ee9a-121">Qualifiers: Key</span></span>

<span data-ttu-id="2ee9a-122">パッケージ構成とソースファイルの GUID 識別子。</span><span class="sxs-lookup"><span data-stu-id="2ee9a-122">The GUID identifier of the package configuration and source files.</span></span>

<a href="" id="sftpath"></a>**<span data-ttu-id="2ee9a-123">SftPath</span><span class="sxs-lookup"><span data-stu-id="2ee9a-123">SftPath</span></span>**  
<span data-ttu-id="2ee9a-124">データ型:**文字列**</span><span class="sxs-lookup"><span data-stu-id="2ee9a-124">Data type: **String**</span></span>

<span data-ttu-id="2ee9a-125">アクセスの種類: 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="2ee9a-125">Access type: Read-only</span></span>

<span data-ttu-id="2ee9a-126">限定子: なし</span><span class="sxs-lookup"><span data-stu-id="2ee9a-126">Qualifiers: None</span></span>

<span data-ttu-id="2ee9a-127">SFT ファイルのファイルパス。</span><span class="sxs-lookup"><span data-stu-id="2ee9a-127">The file path of the SFT file.</span></span>

<a href="" id="totalsize"></a>**<span data-ttu-id="2ee9a-128">TotalSize</span><span class="sxs-lookup"><span data-stu-id="2ee9a-128">TotalSize</span></span>**  
<span data-ttu-id="2ee9a-129">データ型: **UInt64**</span><span class="sxs-lookup"><span data-stu-id="2ee9a-129">Data type: **UInt64**</span></span>

<span data-ttu-id="2ee9a-130">アクセスの種類: 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="2ee9a-130">Access type: Read-only</span></span>

<span data-ttu-id="2ee9a-131">限定子: なし</span><span class="sxs-lookup"><span data-stu-id="2ee9a-131">Qualifiers: None</span></span>

<span data-ttu-id="2ee9a-132">仮想パッケージの合計サイズ (kb 単位)。</span><span class="sxs-lookup"><span data-stu-id="2ee9a-132">The total size of the virtual package, in kilobytes.</span></span>

<a href="" id="cachedsize"></a>**<span data-ttu-id="2ee9a-133">CachedSize</span><span class="sxs-lookup"><span data-stu-id="2ee9a-133">CachedSize</span></span>**  
<span data-ttu-id="2ee9a-134">データ型: **UInt64**</span><span class="sxs-lookup"><span data-stu-id="2ee9a-134">Data type: **UInt64**</span></span>

<span data-ttu-id="2ee9a-135">アクセスの種類: 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="2ee9a-135">Access type: Read-only</span></span>

<span data-ttu-id="2ee9a-136">限定子: なし</span><span class="sxs-lookup"><span data-stu-id="2ee9a-136">Qualifiers: None</span></span>

<span data-ttu-id="2ee9a-137">仮想パッケージのキャッシュの合計サイズ (kb 単位)。</span><span class="sxs-lookup"><span data-stu-id="2ee9a-137">The total size of the cache for the virtual package, in kilobytes.</span></span>

<a href="" id="launchsize"></a>**<span data-ttu-id="2ee9a-138">LaunchSize</span><span class="sxs-lookup"><span data-stu-id="2ee9a-138">LaunchSize</span></span>**  
<span data-ttu-id="2ee9a-139">データ型: **UInt64**</span><span class="sxs-lookup"><span data-stu-id="2ee9a-139">Data type: **UInt64**</span></span>

<span data-ttu-id="2ee9a-140">アクセスの種類: 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="2ee9a-140">Access type: Read-only</span></span>

<span data-ttu-id="2ee9a-141">限定子: なし</span><span class="sxs-lookup"><span data-stu-id="2ee9a-141">Qualifiers: None</span></span>

<span data-ttu-id="2ee9a-142">仮想パッケージのプライマリ機能ブロックの合計サイズ (kb 単位)。</span><span class="sxs-lookup"><span data-stu-id="2ee9a-142">The total size of the virtual package’s primary feature block, in kilobytes.</span></span>

<a href="" id="cachedlaunchsize"></a>**<span data-ttu-id="2ee9a-143">CachedLaunchSize</span><span class="sxs-lookup"><span data-stu-id="2ee9a-143">CachedLaunchSize</span></span>**  
<span data-ttu-id="2ee9a-144">データ型: **UInt64**</span><span class="sxs-lookup"><span data-stu-id="2ee9a-144">Data type: **UInt64**</span></span>

<span data-ttu-id="2ee9a-145">アクセスの種類: 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="2ee9a-145">Access type: Read-only</span></span>

<span data-ttu-id="2ee9a-146">限定子: なし</span><span class="sxs-lookup"><span data-stu-id="2ee9a-146">Qualifiers: None</span></span>

<span data-ttu-id="2ee9a-147">キャッシュされている仮想パッケージのプライマリ機能ブロックの合計サイズ (kb 単位)。</span><span class="sxs-lookup"><span data-stu-id="2ee9a-147">Total size of the virtual package’s primary feature block that has been cached, in kilobytes.</span></span>

<a href="" id="inuse"></a>**<span data-ttu-id="2ee9a-148">InUse</span><span class="sxs-lookup"><span data-stu-id="2ee9a-148">InUse</span></span>**  
<span data-ttu-id="2ee9a-149">データ型:**ブール**型</span><span class="sxs-lookup"><span data-stu-id="2ee9a-149">Data type: **Boolean**</span></span>

<span data-ttu-id="2ee9a-150">アクセスの種類: 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="2ee9a-150">Access type: Read-only</span></span>

<span data-ttu-id="2ee9a-151">限定子: なし</span><span class="sxs-lookup"><span data-stu-id="2ee9a-151">Qualifiers: None</span></span>

<span data-ttu-id="2ee9a-152">仮想パッケージ内の仮想アプリケーションが実行されている場合は**true** 。それ以外の場合は**false**。</span><span class="sxs-lookup"><span data-stu-id="2ee9a-152">**true** if any virtual application in the virtual package is running; otherwise **false**.</span></span>

<a href="" id="locked"></a>**<span data-ttu-id="2ee9a-153">ロック</span><span class="sxs-lookup"><span data-stu-id="2ee9a-153">Locked</span></span>**  
<span data-ttu-id="2ee9a-154">データ型:**ブール**型</span><span class="sxs-lookup"><span data-stu-id="2ee9a-154">Data type: **Boolean**</span></span>

<span data-ttu-id="2ee9a-155">アクセスの種類: 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="2ee9a-155">Access type: Read-only</span></span>

<span data-ttu-id="2ee9a-156">限定子: なし</span><span class="sxs-lookup"><span data-stu-id="2ee9a-156">Qualifiers: None</span></span>

<span data-ttu-id="2ee9a-157">仮想パッケージがロックされている場合は**true** 。それ以外の場合は**false**。</span><span class="sxs-lookup"><span data-stu-id="2ee9a-157">**true** if the virtual package is locked; otherwise **false**.</span></span>

<a href="" id="cachedpercentage"></a>**<span data-ttu-id="2ee9a-158">CachedPercentage</span><span class="sxs-lookup"><span data-stu-id="2ee9a-158">CachedPercentage</span></span>**  
<span data-ttu-id="2ee9a-159">データ型: **UInt16**</span><span class="sxs-lookup"><span data-stu-id="2ee9a-159">Data type: **UInt16**</span></span>

<span data-ttu-id="2ee9a-160">アクセスの種類: 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="2ee9a-160">Access type: Read-only</span></span>

<span data-ttu-id="2ee9a-161">限定子: なし</span><span class="sxs-lookup"><span data-stu-id="2ee9a-161">Qualifiers: None</span></span>

<span data-ttu-id="2ee9a-162">キャッシュファイルの割合。</span><span class="sxs-lookup"><span data-stu-id="2ee9a-162">The percentage of the cache files.</span></span> <span data-ttu-id="2ee9a-163">次の式に基づいて、CachedSize/TotalSize ラ100を計算します。</span><span class="sxs-lookup"><span data-stu-id="2ee9a-163">Based on the following formula: CachedSize / TotalSize × 100.</span></span>

<a href="" id="versionguid"></a>**<span data-ttu-id="2ee9a-164">VersionGUID</span><span class="sxs-lookup"><span data-stu-id="2ee9a-164">VersionGUID</span></span>**  
<span data-ttu-id="2ee9a-165">データ型:**文字列**</span><span class="sxs-lookup"><span data-stu-id="2ee9a-165">Data type: **String**</span></span>

<span data-ttu-id="2ee9a-166">アクセスの種類: 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="2ee9a-166">Access type: Read-only</span></span>

<span data-ttu-id="2ee9a-167">限定子: なし</span><span class="sxs-lookup"><span data-stu-id="2ee9a-167">Qualifiers: None</span></span>

<span data-ttu-id="2ee9a-168">パッケージバージョンの GUID 識別子。</span><span class="sxs-lookup"><span data-stu-id="2ee9a-168">The GUID identifier of the package version.</span></span>

 

 





