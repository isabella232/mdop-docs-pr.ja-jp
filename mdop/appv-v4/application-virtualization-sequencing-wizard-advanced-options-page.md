---
title: Application Virtualization のシーケンスウィザードの [詳細オプション] ページ
description: Application Virtualization のシーケンスウィザードの [詳細オプション] ページ
author: dansimp
ms.assetid: 2c4c5d95-d55e-463d-a851-8486f6a724f2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 716fa27852f1cadfebec31a267ce1b9b581b8ff7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819597"
---
# <span data-ttu-id="e06a8-103">Application Virtualization のシーケンスウィザードの [詳細オプション] ページ</span><span class="sxs-lookup"><span data-stu-id="e06a8-103">Application Virtualization Sequencing Wizard Advanced Options Page</span></span>


<span data-ttu-id="e06a8-104">Application Virtualization (App-v) シーケンスウィザードの **[詳細オプション**] ページを使用して、インストールするアプリケーションの詳細オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="e06a8-104">Use the **Advanced Options** page of the Application Virtualization (App-V) Sequencing Wizard to specify advanced options for the application to be installed.</span></span> <span data-ttu-id="e06a8-105">このページには、次の表に示す要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e06a8-105">The page contains the elements described in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e06a8-106">名前</span><span class="sxs-lookup"><span data-stu-id="e06a8-106">Name</span></span></th>
<th align="left"><span data-ttu-id="e06a8-107">説明</span><span class="sxs-lookup"><span data-stu-id="e06a8-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e06a8-108">ブロックサイズ</span><span class="sxs-lookup"><span data-stu-id="e06a8-108">Block Size</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e06a8-109">ネットワーク経由でストリーミングしたときに、SFT ファイルが分割されるブロックのサイズを指定する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="e06a8-109">Use to specify the size of blocks that the SFT file will be divided into when streamed across a network.</span></span> <span data-ttu-id="e06a8-110">すべてのブロックは指定したサイズと等しくなります。ただし、最後のブロックが指定よりも小さくなっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e06a8-110">All blocks equal the specified size; however, the last block might be smaller than specified.</span></span> <span data-ttu-id="e06a8-111">次のいずれかの値を選びます。</span><span class="sxs-lookup"><span data-stu-id="e06a8-111">Select one of the following values:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="e06a8-112">4 KB</span><span class="sxs-lookup"><span data-stu-id="e06a8-112">4 KB</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="e06a8-113">16 KB</span><span class="sxs-lookup"><span data-stu-id="e06a8-113">16 KB</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="e06a8-114">32 KB</span><span class="sxs-lookup"><span data-stu-id="e06a8-114">32 KB</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="e06a8-115">64 KB</span><span class="sxs-lookup"><span data-stu-id="e06a8-115">64 KB</span></span></strong></p></li>
</ul>
<div class="alert">
<strong><span data-ttu-id="e06a8-116">注</span><span class="sxs-lookup"><span data-stu-id="e06a8-116">Note</span></span></strong><br/><p><span data-ttu-id="e06a8-117">ブロックサイズを選択するときは、SFT ファイルのサイズとネットワーク帯域幅を考慮します。</span><span class="sxs-lookup"><span data-stu-id="e06a8-117">When you select a block size, consider the size of the SFT file and your network bandwidth.</span></span> <span data-ttu-id="e06a8-118">ブロックサイズが小さいファイルは、ネットワーク上でのストリーミングには時間がかかりますが、帯域幅の消費が少なくなります。</span><span class="sxs-lookup"><span data-stu-id="e06a8-118">A file with a smaller block size takes longer to stream over the network but is less bandwidth-intensive.</span></span> <span data-ttu-id="e06a8-119">ブロックサイズが大きいファイルは、より速くストリーミングされる可能性がありますが、より多くのネットワーク帯域幅を使用します。</span><span class="sxs-lookup"><span data-stu-id="e06a8-119">Files with larger block sizes might stream faster, but they use more network bandwidth.</span></span> <span data-ttu-id="e06a8-120">実験を通じて、ネットワーク上のストリーミングアプリケーションに最適なブロックサイズを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="e06a8-120">Through experimentation, you can discover the optimum block size for streaming applications on your network.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e06a8-121">監視中に Microsoft Update を有効にする</span><span class="sxs-lookup"><span data-stu-id="e06a8-121">Enable Microsoft Update During Monitoring</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e06a8-122">シーケンスウィザード&#39;s 監視段階での Microsoft 更新プログラムのインストールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e06a8-122">Enables installation of Microsoft Updates during the Sequencing Wizard&#39;s monitoring phase.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e06a8-123">Dll を再配置する</span><span class="sxs-lookup"><span data-stu-id="e06a8-123">Rebase DLLs</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e06a8-124">サポートされているダイナミックリンクライブラリを、RAM 内の連続した領域にマッピングし、メモリを節約し、パフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="e06a8-124">Enables remapping of supported dynamic-link libraries to a contiguous space in RAM, saving memory and improving performance.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e06a8-125">戻る</span><span class="sxs-lookup"><span data-stu-id="e06a8-125">Back</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e06a8-126">シーケンスウィザード&#39;s の前のページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e06a8-126">Accesses the Sequencing Wizard&#39;s previous page.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e06a8-127">Next</span><span class="sxs-lookup"><span data-stu-id="e06a8-127">Next</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e06a8-128">シーケンスウィザード&#39;s の次のページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e06a8-128">Accesses the Sequencing Wizard&#39;s next page.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e06a8-129">Cancel</span><span class="sxs-lookup"><span data-stu-id="e06a8-129">Cancel</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e06a8-130">シーケンスウィザードの操作を終了します。</span><span class="sxs-lookup"><span data-stu-id="e06a8-130">Terminates operation of the Sequencing Wizard.</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="e06a8-131">\ [テンプレートトークンの値 \]</span><span class="sxs-lookup"><span data-stu-id="e06a8-131">\[Template Token Value\]</span></span>

<span data-ttu-id="e06a8-132">[App-v シーケンスウィザード] の **[詳細オプション**] ページを使用して、順序を設定するアプリケーションの詳細オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="e06a8-132">Use the **Advanced Options** page of the App-V Sequencing Wizard to specify advanced options for the application you are sequencing.</span></span> <span data-ttu-id="e06a8-133">このページには、次の表に示す要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e06a8-133">This page contains the elements described in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e06a8-134">名前</span><span class="sxs-lookup"><span data-stu-id="e06a8-134">Name</span></span></th>
<th align="left"><span data-ttu-id="e06a8-135">説明</span><span class="sxs-lookup"><span data-stu-id="e06a8-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e06a8-136">監視中に Microsoft Update を実行することを許可する</span><span class="sxs-lookup"><span data-stu-id="e06a8-136">Allow Microsoft Update to run during monitoring</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e06a8-137">アプリケーションシーケンスの監視フェーズ中にソフトウェアの更新をアプリケーションに適用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="e06a8-137">Specifies whether software updates will be applied to the application during the monitoring phase of application sequencing.</span></span> <span data-ttu-id="e06a8-138">このオプションは、アプリケーションのインストールを正常に完了するために更新プログラムが必要な場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e06a8-138">This option is helpful if updates are required to successfully complete the application installation.</span></span> <span data-ttu-id="e06a8-139">既定では、このオプションは選択されていません。</span><span class="sxs-lookup"><span data-stu-id="e06a8-139">This option is not selected by default.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e06a8-140">Dll を再配置する</span><span class="sxs-lookup"><span data-stu-id="e06a8-140">Rebase Dlls</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e06a8-141">サポートされているダイナミックリンクライブラリの、RAM 内の連続した領域への再マッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e06a8-141">Enables remapping of supported dynamic-link libraries to a contiguous space in RAM.</span></span> <span data-ttu-id="e06a8-142">このオプションを選ぶと、メモリの管理やアプリケーションのパフォーマンスの向上に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e06a8-142">Selecting this option can help manage memory and improve application performance.</span></span> <span data-ttu-id="e06a8-143">既定では、このオプションは選択されていません。</span><span class="sxs-lookup"><span data-stu-id="e06a8-143">This option is not selected by default.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e06a8-144">戻る</span><span class="sxs-lookup"><span data-stu-id="e06a8-144">Back</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e06a8-145">ウィザードの前のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e06a8-145">Goes to the previous page of the wizard.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e06a8-146">Next</span><span class="sxs-lookup"><span data-stu-id="e06a8-146">Next</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e06a8-147">ウィザードの次のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e06a8-147">Goes to the next page of the wizard.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e06a8-148">Cancel</span><span class="sxs-lookup"><span data-stu-id="e06a8-148">Cancel</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e06a8-149">設定を破棄してウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="e06a8-149">Discards the settings and exits the wizard.</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="e06a8-150">\ [テンプレートトークンの値 \]</span><span class="sxs-lookup"><span data-stu-id="e06a8-150">\[Template Token Value\]</span></span>

## <span data-ttu-id="e06a8-151">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e06a8-151">Related topics</span></span>


[<span data-ttu-id="e06a8-152">シーケンス ウィザード</span><span class="sxs-lookup"><span data-stu-id="e06a8-152">Sequencing Wizard</span></span>](sequencing-wizard.md)









