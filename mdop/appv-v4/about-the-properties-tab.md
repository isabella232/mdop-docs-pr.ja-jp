---
title: '[プロパティ] タブについて'
description: '[プロパティ] タブについて'
author: dansimp
ms.assetid: a6cf6f51-3778-4c8d-9632-3af4005775d2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4b2d6c3e01dde48fdd6701984f66610ea0333b74
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819924"
---
# <span data-ttu-id="7e673-103">[プロパティ] タブについて</span><span class="sxs-lookup"><span data-stu-id="7e673-103">About the Properties Tab</span></span>


<span data-ttu-id="7e673-104">[**プロパティ**] タブを使用して、シーケンスされたアプリケーションパッケージに関する基本的な統計情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="7e673-104">Use the **Properties** tab to view basic statistical information about a sequenced application package.</span></span> <span data-ttu-id="7e673-105">この情報は、特に記載がない限り、自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="7e673-105">The information is automatically generated unless otherwise noted.</span></span> <span data-ttu-id="7e673-106">このタブには、次の要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7e673-106">This tab contains the following elements.</span></span>

## <span data-ttu-id="7e673-107">パッケージ情報</span><span class="sxs-lookup"><span data-stu-id="7e673-107">Package Information</span></span>


<a href="" id="package-name"></a>**<span data-ttu-id="7e673-108">パッケージ名</span><span class="sxs-lookup"><span data-stu-id="7e673-108">Package Name</span></span>**  
<span data-ttu-id="7e673-109">1つまたは複数のアプリケーションが含まれている可能性のあるシーケンス付きのアプリケーションパッケージで使用される単一の名前。たとえば、Microsoft Office を使用して、同じ仮想環境で実行される Microsoft Word と Microsoft Excel アプリケーションを含むシーケンス形式のアプリケーションパッケージにラベルを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="7e673-109">The single name used for a sequenced application package that might contain one or more applications—for example, Microsoft Office could be used to label a sequenced application package that contains Microsoft Word and Microsoft Excel applications that run in the same virtual environment.</span></span>

<a href="" id="comments"></a>**<span data-ttu-id="7e673-110">コメント</span><span class="sxs-lookup"><span data-stu-id="7e673-110">Comments</span></span>**  
<span data-ttu-id="7e673-111">Open Software Descriptor (OSD) file ABSTRACT 要素に表示されるソフトウェアパッケージの短い説明を表示します。</span><span class="sxs-lookup"><span data-stu-id="7e673-111">Displays a short description of the software package that will appear in the Open Software Descriptor (OSD) file ABSTRACT element.</span></span> <span data-ttu-id="7e673-112">この項目は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="7e673-112">This item is optional.</span></span>

<a href="" id="package-version"></a>**<span data-ttu-id="7e673-113">パッケージバージョン</span><span class="sxs-lookup"><span data-stu-id="7e673-113">Package Version</span></span>**  
<span data-ttu-id="7e673-114">順序付けされたアプリケーションパッケージのバージョン。</span><span class="sxs-lookup"><span data-stu-id="7e673-114">The sequenced application package version.</span></span>

<a href="" id="package-guid"></a>**<span data-ttu-id="7e673-115">パッケージ GUID</span><span class="sxs-lookup"><span data-stu-id="7e673-115">Package GUID</span></span>**  
<span data-ttu-id="7e673-116">シーケンス付きのアプリケーションパッケージに自動的に割り当てられたグローバル一意識別子 (GUID) は、シーケンス付きのアプリケーションパッケージがストリーミングされているコンピューターで実行されている可能性のある他のシーケンスされたアプリケーションパッケージと区別するために自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="7e673-116">The globally unique identifier (GUID) automatically assigned to the sequenced application package to distinguish it from other sequenced application packages that might be running on the computer to which a sequenced application package is streamed.</span></span>

<a href="" id="package-version-guid"></a>**<span data-ttu-id="7e673-117">パッケージバージョン GUID</span><span class="sxs-lookup"><span data-stu-id="7e673-117">Package Version GUID</span></span>**  
<span data-ttu-id="7e673-118">順序付けされたアプリケーションパッケージのバージョン GUID。</span><span class="sxs-lookup"><span data-stu-id="7e673-118">The sequenced application package version GUID.</span></span>

<a href="" id="root-directory"></a>**<span data-ttu-id="7e673-119">ルートディレクトリ</span><span class="sxs-lookup"><span data-stu-id="7e673-119">Root Directory</span></span>**  
<span data-ttu-id="7e673-120">シーケンス処理を行っているアプリケーションパッケージのファイルがインストールされているディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="7e673-120">The directory on the sequencing computer in which files for the sequenced application package are installed.</span></span> <span data-ttu-id="7e673-121">このディレクトリは、シーケンスされたアプリケーションパッケージをストリーミングするコンピューター上にも作成されます。</span><span class="sxs-lookup"><span data-stu-id="7e673-121">This directory is also created on the computer to which a sequenced application package will be streamed.</span></span> <span data-ttu-id="7e673-122">下位互換性を確保することをお勧めします。これは、Q:\\MyApp.1\\. などの Q ドライブのルートにある8.3 形式のディレクトリ名にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7e673-122">It is recommended for backwards compatibility that this be an 8.3 format directory name at the root of the Q drive, such as Q:\\MyApp.1\\.</span></span>

<a href="" id="created"></a>**<span data-ttu-id="7e673-123">Created</span><span class="sxs-lookup"><span data-stu-id="7e673-123">Created</span></span>**  
<span data-ttu-id="7e673-124">シーケンス付きのアプリケーションパッケージが作成された日付と時刻です。</span><span class="sxs-lookup"><span data-stu-id="7e673-124">The date and time the sequenced application package was created.</span></span>

<a href="" id="modified"></a>**<span data-ttu-id="7e673-125">変更</span><span class="sxs-lookup"><span data-stu-id="7e673-125">Modified</span></span>**  
<span data-ttu-id="7e673-126">シーケンス付きのアプリケーションパッケージが最後に変更された日付と時刻です。</span><span class="sxs-lookup"><span data-stu-id="7e673-126">The date and time the sequenced application package was last modified.</span></span>

<a href="" id="package-size"></a>**<span data-ttu-id="7e673-127">パッケージサイズ</span><span class="sxs-lookup"><span data-stu-id="7e673-127">Package Size</span></span>**  
<span data-ttu-id="7e673-128">パッケージのサイズ (mb 単位) です。</span><span class="sxs-lookup"><span data-stu-id="7e673-128">The size of the package in megabytes.</span></span>

<a href="" id="launch-size"></a>**<span data-ttu-id="7e673-129">起動サイズ</span><span class="sxs-lookup"><span data-stu-id="7e673-129">Launch Size</span></span>**  
<span data-ttu-id="7e673-130">アプリケーションを起動するために必要な SFT ファイルの部分のサイズ (mb 単位) です。</span><span class="sxs-lookup"><span data-stu-id="7e673-130">The size in megabytes of the portion of the SFT file that is required to start the application.</span></span>

## <span data-ttu-id="7e673-131">シーケンスパラメーター</span><span class="sxs-lookup"><span data-stu-id="7e673-131">Sequencing Parameters</span></span>


<a href="" id="block-size"></a>**<span data-ttu-id="7e673-132">ブロックサイズ</span><span class="sxs-lookup"><span data-stu-id="7e673-132">Block Size</span></span>**  
<span data-ttu-id="7e673-133">ネットワーク経由でストリーミングするために、SFT ファイルが分割されるプライマリ機能ブロックとセカンダリ機能ブロックのサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="7e673-133">Specifies the size of the primary and secondary feature blocks into which the SFT file is divided for streaming across a network.</span></span> <span data-ttu-id="7e673-134">すべてのブロックは指定したサイズと等しくなります。ただし、最後のブロックが指定よりも小さくなっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7e673-134">All blocks equal the specified size; however, the last block might be smaller than specified.</span></span> <span data-ttu-id="7e673-135">次のいずれかの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e673-135">You will see one of the following values:</span></span>

-   <span data-ttu-id="7e673-136">4 KB</span><span class="sxs-lookup"><span data-stu-id="7e673-136">4 KB</span></span>

-   <span data-ttu-id="7e673-137">16 KB</span><span class="sxs-lookup"><span data-stu-id="7e673-137">16 KB</span></span>

-   <span data-ttu-id="7e673-138">32 KB</span><span class="sxs-lookup"><span data-stu-id="7e673-138">32 KB</span></span>

-   <span data-ttu-id="7e673-139">64 KB</span><span class="sxs-lookup"><span data-stu-id="7e673-139">64 KB</span></span>

<span data-ttu-id="7e673-140">**注** 最初のパッケージを作成した後は、ブロックサイズの値は変更できません。</span><span class="sxs-lookup"><span data-stu-id="7e673-140">**Note** After the initial package has been created, the block size value is not changeable.</span></span>

 

## <span data-ttu-id="7e673-141">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7e673-141">Related topics</span></span>


[<span data-ttu-id="7e673-142">パッケージのプロパティを変更する方法</span><span class="sxs-lookup"><span data-stu-id="7e673-142">How to Change Package Properties</span></span>](how-to-change-package-properties.md)

[<span data-ttu-id="7e673-143">Sequencer Console</span><span class="sxs-lookup"><span data-stu-id="7e673-143">Sequencer Console</span></span>](sequencer-console.md)

 

 





