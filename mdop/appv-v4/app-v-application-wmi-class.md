---
title: App-V Application WMI クラス
description: App-V Application WMI クラス
author: dansimp
ms.assetid: b79b0d5a-ba57-442f-8bb4-d7154fc056f9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a4e1e49e35b231ddb2a480a06c46e364121ac2d2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822324"
---
# <span data-ttu-id="8bf6d-103">App-V Application WMI クラス</span><span class="sxs-lookup"><span data-stu-id="8bf6d-103">App-V Application WMI Class</span></span>


<span data-ttu-id="8bf6d-104">Application Virtualization (App-v) クライアントでは、 **application**クラスは、クライアント上のすべての仮想アプリケーションを表す Windows Management INSTRUMENTATION (WMI) クラスです。</span><span class="sxs-lookup"><span data-stu-id="8bf6d-104">In the Application Virtualization (App-V) Client, the **Application** class is a Windows Management Instrumentation (WMI) class that represents all the virtual applications on the client.</span></span>

<span data-ttu-id="8bf6d-105">次の構文は、管理オブジェクト形式 (MOF) コードから簡素化されています。</span><span class="sxs-lookup"><span data-stu-id="8bf6d-105">The following syntax is simplified from Managed Object Format (MOF) code.</span></span> <span data-ttu-id="8bf6d-106">このコードには、継承されたすべてのプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8bf6d-106">The code includes all the inherited properties.</span></span>

## <span data-ttu-id="8bf6d-107">構文</span><span class="sxs-lookup"><span data-stu-id="8bf6d-107">Syntax</span></span>


``` syntax
class Application
{
      string Name;
      string Version;
      string PackageGUID;
      datetime LastLaunchOnSystem;
      uint32 GlobalRunningCount;
      boolean Loading;
      string OriginalOsdPath;
      string CachedOsdPath;
};
```

## <span data-ttu-id="8bf6d-108">要件</span><span class="sxs-lookup"><span data-stu-id="8bf6d-108">Requirements</span></span>


## <span data-ttu-id="8bf6d-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8bf6d-109">Properties</span></span>


<a href="" id="name"></a>**<span data-ttu-id="8bf6d-110">名前</span><span class="sxs-lookup"><span data-stu-id="8bf6d-110">Name</span></span>**  
<span data-ttu-id="8bf6d-111">データ型:**文字列**</span><span class="sxs-lookup"><span data-stu-id="8bf6d-111">Data type: **String**</span></span>

<span data-ttu-id="8bf6d-112">アクセスの種類: 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="8bf6d-112">Access type: Read-only</span></span>

<span data-ttu-id="8bf6d-113">修飾子: キー</span><span class="sxs-lookup"><span data-stu-id="8bf6d-113">Qualifiers: Key</span></span>

<span data-ttu-id="8bf6d-114">仮想アプリケーションの表示名。</span><span class="sxs-lookup"><span data-stu-id="8bf6d-114">The display name of the virtual application.</span></span>

<a href="" id="version"></a>**<span data-ttu-id="8bf6d-115">バージョン</span><span class="sxs-lookup"><span data-stu-id="8bf6d-115">Version</span></span>**  
<span data-ttu-id="8bf6d-116">データ型:**文字列**</span><span class="sxs-lookup"><span data-stu-id="8bf6d-116">Data type: **String**</span></span>

<span data-ttu-id="8bf6d-117">アクセスの種類: 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="8bf6d-117">Access type: Read-only</span></span>

<span data-ttu-id="8bf6d-118">修飾子: キー</span><span class="sxs-lookup"><span data-stu-id="8bf6d-118">Qualifiers: Key</span></span>

<span data-ttu-id="8bf6d-119">仮想アプリケーションのバージョン。</span><span class="sxs-lookup"><span data-stu-id="8bf6d-119">The version of the virtual application.</span></span>

<a href="" id="packageguid"></a>**<span data-ttu-id="8bf6d-120">PackageGUID</span><span class="sxs-lookup"><span data-stu-id="8bf6d-120">PackageGUID</span></span>**  
<span data-ttu-id="8bf6d-121">データ型:**文字列**</span><span class="sxs-lookup"><span data-stu-id="8bf6d-121">Data type: **String**</span></span>

<span data-ttu-id="8bf6d-122">アクセスの種類: 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="8bf6d-122">Access type: Read-only</span></span>

<span data-ttu-id="8bf6d-123">限定子: なし</span><span class="sxs-lookup"><span data-stu-id="8bf6d-123">Qualifiers: None</span></span>

<span data-ttu-id="8bf6d-124">仮想アプリケーションが関連付けられているパッケージの GUID です。</span><span class="sxs-lookup"><span data-stu-id="8bf6d-124">The GUID of the package that the virtual application is associated with.</span></span>

<a href="" id="lastlaunchonsystem"></a>**<span data-ttu-id="8bf6d-125">LastLaunchOnSystem</span><span class="sxs-lookup"><span data-stu-id="8bf6d-125">LastLaunchOnSystem</span></span>**  
<span data-ttu-id="8bf6d-126">データ型: **DateTime**</span><span class="sxs-lookup"><span data-stu-id="8bf6d-126">Data type: **DateTime**</span></span>

<span data-ttu-id="8bf6d-127">アクセスの種類: 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="8bf6d-127">Access type: Read-only</span></span>

<span data-ttu-id="8bf6d-128">限定子: なし</span><span class="sxs-lookup"><span data-stu-id="8bf6d-128">Qualifiers: None</span></span>

<span data-ttu-id="8bf6d-129">仮想アプリケーションが起動された最後の日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="8bf6d-129">The last date and time that the virtual application was launched.</span></span>

<a href="" id="globalrunningcount"></a>**<span data-ttu-id="8bf6d-130">GlobalRunningCount</span><span class="sxs-lookup"><span data-stu-id="8bf6d-130">GlobalRunningCount</span></span>**  
<span data-ttu-id="8bf6d-131">データ型: **UInt32**</span><span class="sxs-lookup"><span data-stu-id="8bf6d-131">Data type: **UInt32**</span></span>

<span data-ttu-id="8bf6d-132">アクセスの種類: 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="8bf6d-132">Access type: Read-only</span></span>

<span data-ttu-id="8bf6d-133">限定子: なし</span><span class="sxs-lookup"><span data-stu-id="8bf6d-133">Qualifiers: None</span></span>

<span data-ttu-id="8bf6d-134">直接開始された仮想アプリケーションのインスタンスの数。</span><span class="sxs-lookup"><span data-stu-id="8bf6d-134">A count of the running instances of the virtual application that were started directly.</span></span>

<a href="" id="loading"></a>**<span data-ttu-id="8bf6d-135">読み込み中</span><span class="sxs-lookup"><span data-stu-id="8bf6d-135">Loading</span></span>**  
<span data-ttu-id="8bf6d-136">データ型:**ブール**型</span><span class="sxs-lookup"><span data-stu-id="8bf6d-136">Data type: **Boolean**</span></span>

<span data-ttu-id="8bf6d-137">アクセスの種類: 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="8bf6d-137">Access type: Read-only</span></span>

<span data-ttu-id="8bf6d-138">限定子: なし</span><span class="sxs-lookup"><span data-stu-id="8bf6d-138">Qualifiers: None</span></span>

<span data-ttu-id="8bf6d-139">仮想アプリケーションが開始されている場合は**true** 。それ以外の場合は**false**。</span><span class="sxs-lookup"><span data-stu-id="8bf6d-139">**true** if the virtual application is being started; otherwise **false**.</span></span>

<a href="" id="originalosdpath"></a>**<span data-ttu-id="8bf6d-140">発信経路</span><span class="sxs-lookup"><span data-stu-id="8bf6d-140">OriginalOsdPath</span></span>**  
<span data-ttu-id="8bf6d-141">データ型:**文字列**</span><span class="sxs-lookup"><span data-stu-id="8bf6d-141">Data type: **String**</span></span>

<span data-ttu-id="8bf6d-142">アクセスの種類: 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="8bf6d-142">Access type: Read-only</span></span>

<span data-ttu-id="8bf6d-143">限定子: なし</span><span class="sxs-lookup"><span data-stu-id="8bf6d-143">Qualifiers: None</span></span>

<span data-ttu-id="8bf6d-144">App-v クライアントに登録された OSD ファイルの元のファイルパス。</span><span class="sxs-lookup"><span data-stu-id="8bf6d-144">The original file path of the OSD file that was registered with the App-V Client.</span></span>

<a href="" id="cachedosdpath"></a>**<span data-ttu-id="8bf6d-145">CachedOsdPath</span><span class="sxs-lookup"><span data-stu-id="8bf6d-145">CachedOsdPath</span></span>**  
<span data-ttu-id="8bf6d-146">データ型:**文字列**</span><span class="sxs-lookup"><span data-stu-id="8bf6d-146">Data type: **String**</span></span>

<span data-ttu-id="8bf6d-147">アクセスの種類: 読み取り専用</span><span class="sxs-lookup"><span data-stu-id="8bf6d-147">Access type: Read-only</span></span>

<span data-ttu-id="8bf6d-148">限定子: なし</span><span class="sxs-lookup"><span data-stu-id="8bf6d-148">Qualifiers: None</span></span>

<span data-ttu-id="8bf6d-149">アプリケーションのローカルで OSD ファイルがキャッシュされている場合は、OSD ファイルのファイルパス。</span><span class="sxs-lookup"><span data-stu-id="8bf6d-149">The file path of the OSD file if the App-V Client has cached the OSD file locally.</span></span>

 

 





