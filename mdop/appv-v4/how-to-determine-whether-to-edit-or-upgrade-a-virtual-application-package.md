---
title: 仮想アプリケーション パッケージを編集またはアップグレードするかを決定する方法
description: 仮想アプリケーション パッケージを編集またはアップグレードするかを決定する方法
author: dansimp
ms.assetid: 33dd5332-6802-46e0-9748-43fcc8f80aa3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b256a4927231613b6f2e688b5951adf57c9cb89a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817504"
---
# <span data-ttu-id="266dd-103">仮想アプリケーション パッケージを編集またはアップグレードするかを決定する方法</span><span class="sxs-lookup"><span data-stu-id="266dd-103">How to Determine Whether to Edit or Upgrade a Virtual Application Package</span></span>


<span data-ttu-id="266dd-104">次の表は、仮想アプリケーションパッケージを編集用に開くことができるかどうかを判断するのに役立ちます。新しいバージョンのパッケージを作成する必要がある場合、またはどちらかのオプションを使用できるかどうかを確認するには、App-v Sequencer を使います。</span><span class="sxs-lookup"><span data-stu-id="266dd-104">Use the following table to help determine whether a virtual application package can be opened for edit, whether you need to create a new version of the package, or whether either option is available, using the App-V Sequencer.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="266dd-105">操作</span><span class="sxs-lookup"><span data-stu-id="266dd-105">Action</span></span></th>
<th align="left"><span data-ttu-id="266dd-106">編集用に開く</span><span class="sxs-lookup"><span data-stu-id="266dd-106">Open for edit</span></span></th>
<th align="left"><span data-ttu-id="266dd-107">アップグレードのために開く</span><span class="sxs-lookup"><span data-stu-id="266dd-107">Open for upgrade</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="266dd-108">パッケージのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="266dd-108">View package properties.</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-109">あり</span><span class="sxs-lookup"><span data-stu-id="266dd-109">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-110">要</span><span class="sxs-lookup"><span data-stu-id="266dd-110">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="266dd-111">パッケージの変更履歴を表示します。</span><span class="sxs-lookup"><span data-stu-id="266dd-111">View package change history.</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-112">あり</span><span class="sxs-lookup"><span data-stu-id="266dd-112">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-113">要</span><span class="sxs-lookup"><span data-stu-id="266dd-113">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="266dd-114">関連付けられたパッケージファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="266dd-114">View associated package files.</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-115">あり</span><span class="sxs-lookup"><span data-stu-id="266dd-115">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-116">要</span><span class="sxs-lookup"><span data-stu-id="266dd-116">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="266dd-117">レジストリ設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="266dd-117">Edit registry settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-118">あり</span><span class="sxs-lookup"><span data-stu-id="266dd-118">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-119">要</span><span class="sxs-lookup"><span data-stu-id="266dd-119">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="266dd-120">追加のパッケージ設定を確認します (オペレーティングシステムのファイルプロパティを除く)。</span><span class="sxs-lookup"><span data-stu-id="266dd-120">Review additional package settings (except operating system file properties).</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-121">あり</span><span class="sxs-lookup"><span data-stu-id="266dd-121">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-122">要</span><span class="sxs-lookup"><span data-stu-id="266dd-122">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="266dd-123">関連付けられた Windows インストーラー (MSI) を作成します。</span><span class="sxs-lookup"><span data-stu-id="266dd-123">Create associated Windows Installer (MSI).</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-124">あり</span><span class="sxs-lookup"><span data-stu-id="266dd-124">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-125">要</span><span class="sxs-lookup"><span data-stu-id="266dd-125">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="266dd-126">OSD ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="266dd-126">Modify OSD file.</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-127">あり</span><span class="sxs-lookup"><span data-stu-id="266dd-127">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-128">要</span><span class="sxs-lookup"><span data-stu-id="266dd-128">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="266dd-129">パッケージの圧縮と圧縮解除を行います。</span><span class="sxs-lookup"><span data-stu-id="266dd-129">Compress and uncompress package.</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-130">あり</span><span class="sxs-lookup"><span data-stu-id="266dd-130">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-131">要</span><span class="sxs-lookup"><span data-stu-id="266dd-131">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="266dd-132">ファイルの種類の関連付けを追加します。</span><span class="sxs-lookup"><span data-stu-id="266dd-132">Add file type associations.</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-133">あり</span><span class="sxs-lookup"><span data-stu-id="266dd-133">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-134">要</span><span class="sxs-lookup"><span data-stu-id="266dd-134">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="266dd-135">ショートカットの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="266dd-135">Rename shortcuts.</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-136">あり</span><span class="sxs-lookup"><span data-stu-id="266dd-136">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-137">要</span><span class="sxs-lookup"><span data-stu-id="266dd-137">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="266dd-138">仮想化されたレジストリキーの状態 (上書き/マージ) を設定します。</span><span class="sxs-lookup"><span data-stu-id="266dd-138">Set virtualized registry key state (override / merge).</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-139">あり</span><span class="sxs-lookup"><span data-stu-id="266dd-139">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-140">要</span><span class="sxs-lookup"><span data-stu-id="266dd-140">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="266dd-141">仮想化されたフォルダーの状態を設定します。</span><span class="sxs-lookup"><span data-stu-id="266dd-141">Set virtualized folder state.</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-142">あり</span><span class="sxs-lookup"><span data-stu-id="266dd-142">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-143">要</span><span class="sxs-lookup"><span data-stu-id="266dd-143">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="266dd-144">仮想ファイルシステムのマッピングを編集します。</span><span class="sxs-lookup"><span data-stu-id="266dd-144">Edit virtual file system mappings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-145">あり</span><span class="sxs-lookup"><span data-stu-id="266dd-145">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-146">要</span><span class="sxs-lookup"><span data-stu-id="266dd-146">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="266dd-147">パッケージの関連するすべてのオペレーティングシステムファイルプロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="266dd-147">Review all associated operating system file properties for a package.</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-148">なし</span><span class="sxs-lookup"><span data-stu-id="266dd-148">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-149">あり</span><span class="sxs-lookup"><span data-stu-id="266dd-149">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="266dd-150">その他のサービスを追加します。</span><span class="sxs-lookup"><span data-stu-id="266dd-150">Add additional services.</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-151">なし</span><span class="sxs-lookup"><span data-stu-id="266dd-151">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-152">あり</span><span class="sxs-lookup"><span data-stu-id="266dd-152">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="266dd-153">その他のファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="266dd-153">Add additional files.</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-154">なし</span><span class="sxs-lookup"><span data-stu-id="266dd-154">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-155">あり</span><span class="sxs-lookup"><span data-stu-id="266dd-155">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="266dd-156">関連するセキュリティ記述子を収集して構成します。</span><span class="sxs-lookup"><span data-stu-id="266dd-156">Collect and configure associated security descriptors.</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-157">なし</span><span class="sxs-lookup"><span data-stu-id="266dd-157">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-158">あり</span><span class="sxs-lookup"><span data-stu-id="266dd-158">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="266dd-159">セキュリティ更新プログラムを適用するか、新しいバージョンにアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="266dd-159">Apply security updates or upgrade to a new version.</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-160">なし</span><span class="sxs-lookup"><span data-stu-id="266dd-160">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-161">あり</span><span class="sxs-lookup"><span data-stu-id="266dd-161">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="266dd-162">その他のアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="266dd-162">Add an additional application.</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-163">なし</span><span class="sxs-lookup"><span data-stu-id="266dd-163">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-164">あり</span><span class="sxs-lookup"><span data-stu-id="266dd-164">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="266dd-165">アプリケーションを開く必要がある更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="266dd-165">Apply updates that require the application to open.</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-166">なし</span><span class="sxs-lookup"><span data-stu-id="266dd-166">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-167">あり</span><span class="sxs-lookup"><span data-stu-id="266dd-167">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="266dd-168">コンピューターを再起動する必要がある更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="266dd-168">Apply updates that require the computer to restart.</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-169">なし</span><span class="sxs-lookup"><span data-stu-id="266dd-169">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="266dd-170">○</span><span class="sxs-lookup"><span data-stu-id="266dd-170">Yes</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="266dd-171">関連トピック</span><span class="sxs-lookup"><span data-stu-id="266dd-171">Related topics</span></span>


[<span data-ttu-id="266dd-172">既存の仮想アプリケーションを編集する方法</span><span class="sxs-lookup"><span data-stu-id="266dd-172">How to Edit an Existing Virtual Application</span></span>](how-to-edit-an-existing-virtual-application.md)

[<span data-ttu-id="266dd-173">既存の仮想アプリケーションをアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="266dd-173">How to Upgrade an Existing Virtual Application</span></span>](how-to-upgrade-an-existing-virtual-application.md)

 

 





