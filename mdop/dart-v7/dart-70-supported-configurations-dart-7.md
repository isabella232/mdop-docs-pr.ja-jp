---
title: DaRT 7.0 でサポートされる構成
description: DaRT 7.0 でサポートされる構成
author: dansimp
ms.assetid: e9ee87b0-3254-4625-b178-17b2f5b8f8c8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4b074a061c402f86769e42d873e0119ac54080c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812691"
---
# <span data-ttu-id="28191-103">DaRT 7.0 でサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="28191-103">DaRT 7.0 Supported Configurations</span></span>


<span data-ttu-id="28191-104">お客様の環境は、Microsoft Diagnostics and Recovery ツールセット (DaRT) 7 をインストールして実行できるように、ここで説明した構成要件を満たしている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="28191-104">Your environment may already meet the configuration requirements provided here so that you can install and run Microsoft Diagnostics and Recovery Toolset (DaRT)7.</span></span> <span data-ttu-id="28191-105">次のような回復イメージとディスク領域の要件があります。</span><span class="sxs-lookup"><span data-stu-id="28191-105">These include the following recovery image and disk space requirements.</span></span>

## <span data-ttu-id="28191-106">DaRT 7 の回復イメージの要件</span><span class="sxs-lookup"><span data-stu-id="28191-106">DaRT 7 Recovery Image Requirements</span></span>


<span data-ttu-id="28191-107">クロスプラットフォームの回復イメージの作成はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="28191-107">No cross-platform recovery image creation is supported.</span></span> <span data-ttu-id="28191-108">次の表は、エンタープライズで作成して展開する必要がある回復イメージの種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="28191-108">The following table specifies the kind of recovery image that you should create and deploy in your enterprise:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="28191-109">プラットフォームと DaRT のバージョン</span><span class="sxs-lookup"><span data-stu-id="28191-109">Platform and DaRT Version</span></span></th>
<th align="left"><span data-ttu-id="28191-110">回復イメージの要件</span><span class="sxs-lookup"><span data-stu-id="28191-110">Recovery Image Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="28191-111">64ビット DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="28191-111">64-Bit DaRT 7.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="28191-112">64ビット DaRT 回復イメージを作成して使用します。</span><span class="sxs-lookup"><span data-stu-id="28191-112">Create and use a 64-Bit DaRT recovery image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="28191-113">32ビット DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="28191-113">32-Bit DaRT 7.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="28191-114">32ビット DaRT 回復イメージを作成して使用します。</span><span class="sxs-lookup"><span data-stu-id="28191-114">Create and use a 32-Bit DaRT recovery image.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="28191-115">DaRT 7 のエンドユーザコンピューターの要件</span><span class="sxs-lookup"><span data-stu-id="28191-115">DaRT 7 End-user Computer Requirements</span></span>


<span data-ttu-id="28191-116">DaRT の [**診断/回復ツールセット**] ウィンドウでは、次のオペレーティングシステムのいずれかを dart で利用可能なシステムメモリ容量と共に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28191-116">The **Diagnostics and Recovery Toolset** window in DaRT requires that the destination computer use one of the following operating systems together with the specified amount of system memory available for DaRT:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="28191-117">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="28191-117">Operating System</span></span></th>
<th align="left"><span data-ttu-id="28191-118">DaRT のシステム要件</span><span class="sxs-lookup"><span data-stu-id="28191-118">System Requirements for DaRT</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="28191-119">Windows7 64 ビット (2GB)</span><span class="sxs-lookup"><span data-stu-id="28191-119">Windows7 64-Bit (2GB)</span></span></p></td>
<td align="left"><p><span data-ttu-id="28191-120">2.5 GB のシステムメモリ</span><span class="sxs-lookup"><span data-stu-id="28191-120">2.5GB of system memory</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="28191-121">Windows7 32 ビット (1 GB)</span><span class="sxs-lookup"><span data-stu-id="28191-121">Windows7 32-Bit (1GB)</span></span></p></td>
<td align="left"><p><span data-ttu-id="28191-122">1.5 GB のシステムメモリ</span><span class="sxs-lookup"><span data-stu-id="28191-122">1.5GB of system memory</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="28191-123">Windows Server2008R2 (512MB)</span><span class="sxs-lookup"><span data-stu-id="28191-123">Windows Server2008R2 (512MB)</span></span></p></td>
<td align="left"><p><span data-ttu-id="28191-124">1 GB のシステムメモリ</span><span class="sxs-lookup"><span data-stu-id="28191-124">1GB of system memory</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="28191-125">DaRT には、以下の最低限のハードウェア要件もあります。</span><span class="sxs-lookup"><span data-stu-id="28191-125">DaRT also has the following minimal hardware requirements:</span></span>

-   <span data-ttu-id="28191-126">CD または DVD ドライブまたは USB ポート</span><span class="sxs-lookup"><span data-stu-id="28191-126">A CD or DVD drive or a USB port</span></span>

    <span data-ttu-id="28191-127">これは、CD、DVD、または USB を使用して企業内で DaRT を展開する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="28191-127">This is required if you are deploying DaRT in your enterprise by using a CD, DVD, or USB.</span></span>

-   <span data-ttu-id="28191-128">CD または DVD、USB フラッシュドライブ、またはリモートまたは回復パーティションからコンピューターを起動するための BIOS のサポート</span><span class="sxs-lookup"><span data-stu-id="28191-128">BIOS support for starting the computer from a CD or DVD, a USB flash drive, or from a remote or recovery partition</span></span>

## <span data-ttu-id="28191-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="28191-129">Related topics</span></span>


[<span data-ttu-id="28191-130">DaRT 7.0 の展開計画</span><span class="sxs-lookup"><span data-stu-id="28191-130">Planning to Deploy DaRT 7.0</span></span>](planning-to-deploy-dart-70.md)

 

 





