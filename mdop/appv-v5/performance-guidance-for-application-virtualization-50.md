---
title: Application Virtualization 5.0 に関するパフォーマンス ガイダンス
description: Application Virtualization 5.0 に関するパフォーマンス ガイダンス
author: dansimp
ms.assetid: 6b3a3255-b957-4b9b-8bfc-a93fe8438a81
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 3b0f5ef07935fc34adce772e7b2fff85a12b01dc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813538"
---
# <span data-ttu-id="2e742-103">Application Virtualization 5.0 に関するパフォーマンス ガイダンス</span><span class="sxs-lookup"><span data-stu-id="2e742-103">Performance Guidance for Application Virtualization 5.0</span></span>


<span data-ttu-id="2e742-104">最適なパフォーマンスを得るために App-v 5.0 を構成する方法、仮想アプリパッケージを最適化する方法、および RDS と VDI を使用してユーザーエクスペリエンスを向上させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2e742-104">Learn how to configure App-V 5.0 for optimal performance, optimize virtual app packages, and provide a better user experience with RDS and VDI.</span></span>

<span data-ttu-id="2e742-105">複数の方法を実装することで、エンドユーザーエクスペリエンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="2e742-105">Implementing multiple methods can help you improve the end-user experience.</span></span> <span data-ttu-id="2e742-106">ただし、環境によっては、すべてのメソッドがサポートされないことがあります。</span><span class="sxs-lookup"><span data-stu-id="2e742-106">However, your environment may not support all methods.</span></span>

<span data-ttu-id="2e742-107">このドキュメントを読む前に、次の情報を読んで理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-107">You should read and understand the following information before reading this document.</span></span>

-   [<span data-ttu-id="2e742-108">Microsoft Application Virtualization 5.0 管理者ガイド</span><span class="sxs-lookup"><span data-stu-id="2e742-108">Microsoft Application Virtualization 5.0 Administrator's Guide</span></span>](microsoft-application-virtualization-50-administrators-guide.md)

-   [<span data-ttu-id="2e742-109">App-v 5 SP2 アプリケーションのパブリッシングとクライアントの対話式操作</span><span class="sxs-lookup"><span data-stu-id="2e742-109">App-V 5 SP2 Application Publishing and Client Interaction</span></span>](https://go.microsoft.com/fwlink/?LinkId=395206)

-   [<span data-ttu-id="2e742-110">Microsoft Application Virtualization 5.0 シーケンスガイド</span><span class="sxs-lookup"><span data-stu-id="2e742-110">Microsoft Application Virtualization 5.0 Sequencing Guide</span></span>](https://go.microsoft.com/fwlink/?LinkId=269953)

**<span data-ttu-id="2e742-111">注</span><span class="sxs-lookup"><span data-stu-id="2e742-111">Note</span></span>**  
<span data-ttu-id="2e742-112">このドキュメントで使用されている用語によっては、外部のソースとコンテキストによって意味が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-112">Some terms used in this document may have different meanings depending on external source and context.</span></span> <span data-ttu-id="2e742-113">このドキュメントで使用される用語の詳細については、 **\\** このドキュメントの「 [Application Virtualization のパフォーマンスに関するガイドライン](#bkmk-terms1)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e742-113">For more information about terms used in this document followed by an asterisk **\\**\* review the [Application Virtualization Performance Guidance Terminology](#bkmk-terms1) section of this document.</span></span>



<span data-ttu-id="2e742-114">最後に、このドキュメントでは、App-v 5.0 クライアントを実行しているコンピューターと最適なパフォーマンスを得るための環境を構成するための情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="2e742-114">Finally, this document will provide you with the information to configure the computer running App-V 5.0 client and the environment for optimal performance.</span></span> <span data-ttu-id="2e742-115">Sequencer を使用してパフォーマンスの仮想アプリケーションパッケージを最適化し、ユーザーエクスペリエンスの仮想化 (UE-V) またはその他のユーザー環境管理テクノロジを使用して、リモートデスクトップサービス (RDS) と非永続的仮想デスクトップインフラストラクチャ (VDI) の両方で、最適なユーザー5.0 エクスペリエンスを提供する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2e742-115">Optimize your virtual application packages for performance using the sequencer, and to understand how to use User Experience Virtualization (UE-V) or other user environment management technologies to provide the optimal user experience with App-V 5.0 in both Remote Desktop Services (RDS) and non-persistent virtual desktop infrastructure (VDI).</span></span>

<span data-ttu-id="2e742-116">環境に関連する情報を特定するには、各セクションの簡単な概要と適用性のチェックリストを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-116">To help determine what information is relevant to your environment you should review each section’s brief overview and applicability checklist.</span></span>

## <a href="" id="---------app-v-5-0-in-stateful--non-persistent-deployments"></a> <span data-ttu-id="2e742-117">ステートフルな展開 (非永続的な展開) での app-v 5.0</span><span class="sxs-lookup"><span data-stu-id="2e742-117">App-V 5.0 in stateful\* non-persistent deployments</span></span>


<span data-ttu-id="2e742-118">このセクションでは、ログイン後にすべての仮想アプリケーションにユーザーがアクセスできるようにするために役立つ方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2e742-118">This section provides information about an approach that helps ensure a user will have access to all virtual applications within seconds after logging in.</span></span> <span data-ttu-id="2e742-119">これを実現するには、長時間実行されることが多いアプリ-V 5.0 公開の更新に固有のアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="2e742-119">This is achieved by uniquely addressing the often long-running App-V 5.0 publishing refresh.</span></span> <span data-ttu-id="2e742-120">アプローチの基礎となるのは、最も迅速な公開の更新です。実際に何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2e742-120">As you will discover the basis of the approach, the fastest publishing refresh, is one that doesn’t have to actually do anything.</span></span> <span data-ttu-id="2e742-121">多くの条件を満たし、最適なユーザーエクスペリエンスを提供するための手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-121">A number of conditions must be met and steps followed to provide the optimal user experience.</span></span>

<span data-ttu-id="2e742-122">詳細については、次のセクションの情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e742-122">Use the information in the following section for more information:</span></span>

<span data-ttu-id="2e742-123">[使用シナリオ](#bkmk-us): 2 つのシナリオをレビューするときには、これらは非常によいアプローチであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2e742-123">[Usage Scenarios](#bkmk-us) - As you review the two scenarios, keep in mind that these are the approach extremes.</span></span> <span data-ttu-id="2e742-124">使用要件に基づいて、次の手順をユーザーや仮想アプリケーションパッケージのサブセットに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="2e742-124">Based on your usage requirements, you may choose to apply these steps to a subset of users and/or virtual applications packages.</span></span>

-   <span data-ttu-id="2e742-125">パフォーマンスの最適化–最適なエクスペリエンスを提供するために、基本イメージには、アプリの V 仮想アプリケーションパッケージの一部が含まれていることが想定されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-125">Optimized for Performance – To provide the optimal experience, you can expect the base image to include some of the App-V virtual application package.</span></span> <span data-ttu-id="2e742-126">その他の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="2e742-126">This and other requirements are discussed.</span></span>

-   <span data-ttu-id="2e742-127">ストレージに最適化されています。記憶域への影響を懸念している場合は、このシナリオに従うことで問題解決に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2e742-127">Optimized for Storage – If you are concerned with the storage impact, following this scenario will help address those concerns.</span></span>

[<span data-ttu-id="2e742-128">環境の準備</span><span class="sxs-lookup"><span data-stu-id="2e742-128">Preparing your Environment</span></span>](#bkmk-pe)

-   <span data-ttu-id="2e742-129">基本イメージを準備するための手順: 非永続的な VDI または RDSH 環境のどちらでも、この方法を有効にするためには、基本イメージの手順をいくつか実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-129">Steps to Prepare the Base Image – Whether in a non-persistent VDI or RDSH environment, only a few steps must be completed in the base image to enable this approach.</span></span>

-   <span data-ttu-id="2e742-130">Ue-v のアプローチには、ユーザープロファイル管理 (UPM) ソリューションとして ue-v 2.0 を使用します。この方法の基盤は、いくつかのレジストリとファイルの場所だけのコンテンツを保持する UEM ソリューションの機能です。</span><span class="sxs-lookup"><span data-stu-id="2e742-130">Use UE-V 2.0 as the User Profile Management (UPM) solution for the App-V approach – the cornerstone of this approach is the ability of a UEM solution to persist the contents of just a few registry and file locations.</span></span> <span data-ttu-id="2e742-131">これらの場所は、ユーザーインテグレーション \ \* を構成します。</span><span class="sxs-lookup"><span data-stu-id="2e742-131">These locations constitute the user integrations\*.</span></span> <span data-ttu-id="2e742-132">UPM ソリューションの固有の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="2e742-132">Be sure to review the specific requirements for the UPM solution.</span></span>

[<span data-ttu-id="2e742-133">ユーザーエクスペリエンスのウォークスルー</span><span class="sxs-lookup"><span data-stu-id="2e742-133">User Experience Walk-through</span></span>](#bkmk-uewt)

-   <span data-ttu-id="2e742-134">詳細については、この後の「アプリ-V および UE-V の操作」と「ユーザーが必要とする期待」の順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="2e742-134">Walk-through – This is a step-by-step walk-through of the App-V and UE-V operations and the expectations users should have.</span></span>

-   <span data-ttu-id="2e742-135">[結果]-予期される結果が示されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-135">Outcome – This describes the expected results.</span></span>

[<span data-ttu-id="2e742-136">パッケージのライフサイクルへの影響</span><span class="sxs-lookup"><span data-stu-id="2e742-136">Impact to Package Lifecycle</span></span>](#bkmk-plc)

[<span data-ttu-id="2e742-137">パフォーマンスの最適化/チューニングを通じて VDI のエクスペリエンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="2e742-137">Enhancing the VDI Experience through Performance Optimization/Tuning</span></span>](#bkmk-evdi)

### <a href="" id="applicability-checklist-"></a><span data-ttu-id="2e742-138">適用のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="2e742-138">Applicability Checklist</span></span>

<span data-ttu-id="2e742-139">展開環境</span><span class="sxs-lookup"><span data-stu-id="2e742-139">Deployment Environment</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="2e742-140">非永続的な VDI または RDSH。</span><span class="sxs-lookup"><span data-stu-id="2e742-140">Non-Persistent VDI or RDSH.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="2e742-141">ユーザーエクスペリエンスの仮想化 (UE-V)、その他の UPM ソリューション、またはユーザープロファイルディスク (UPD)。</span><span class="sxs-lookup"><span data-stu-id="2e742-141">User Experience Virtualization (UE-V), other UPM solutions or User Profile Disks (UPD).</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="2e742-142">期待される構成</span><span class="sxs-lookup"><span data-stu-id="2e742-142">Expected Configuration</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="2e742-143">User Experience Virtualization (UE-V) では、App-v のユーザー状態テンプレートが有効またはユーザープロファイル管理 (UPM) ソフトウェアが使用されています。</span><span class="sxs-lookup"><span data-stu-id="2e742-143">User Experience Virtualization (UE-V) with the App-V user state template enabled or User Profile Management (UPM) software.</span></span> <span data-ttu-id="2e742-144">非 UE-V UPM ソフトウェアは、ログインまたはプロセス/アプリケーションの開始とログオフのトリガーに対応している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-144">Non-UE-V UPM software must be capable of triggering on Login or Process/Application Start and Logoff.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="2e742-145">App-v 共有コンテンツストア (SCS) が構成されているか、構成することができます。</span><span class="sxs-lookup"><span data-stu-id="2e742-145">App-V Shared Content Store (SCS) is configured or can be configured.</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="2e742-146">IT 管理</span><span class="sxs-lookup"><span data-stu-id="2e742-146">IT Administration</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="2e742-147">最適なパフォーマンスを確保するために、または管理者がさまざまなユーザーグループの複数の画像を管理する必要がある場合は、管理者が VM ベースイメージを定期的に更新する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-147">Admin may need to update the VM base image regularly to ensure optimal performance or Admin may need to manage multiple images for different user groups.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-us"></a><span data-ttu-id="2e742-148">使用シナリオ</span><span class="sxs-lookup"><span data-stu-id="2e742-148">Usage Scenario</span></span>

<span data-ttu-id="2e742-149">2つのシナリオを確認したら、これらの方法は非常に極端なものであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2e742-149">As you review the two scenarios, keep in mind that these approach the extremes.</span></span> <span data-ttu-id="2e742-150">使用要件に基づいて、これらの手順は、ユーザーのサブセット、仮想アプリケーションパッケージ、またはその両方に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="2e742-150">Based on your usage requirements, you may choose to apply these steps to a subset of users, virtual application packages, or both.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2e742-151">パフォーマンスを最適化</span><span class="sxs-lookup"><span data-stu-id="2e742-151">Optimized for Performance</span></span></th>
<th align="left"><span data-ttu-id="2e742-152">ストレージに最適化されている</span><span class="sxs-lookup"><span data-stu-id="2e742-152">Optimized for Storage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2e742-153">最適なユーザーエクスペリエンスを提供するために、この手法では、UPM ソリューションの機能を活用し、追加のイメージの準備を行う必要があります。また、追加の画像管理のオーバーヘッドが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-153">To provide the most optimal user experience, this approach leverages the capabilities of a UPM solution and requires additional image preparation and can incur some additional image management overhead.</span></span></p>
<p><span data-ttu-id="2e742-154">次に、ステートフル非永続的展開でのさまざまなパフォーマンスの改善について説明します。</span><span class="sxs-lookup"><span data-stu-id="2e742-154">The following describes many performance improvements in stateful non-persistent deployments.</span></span> <span data-ttu-id="2e742-155">詳細については、 <strong> </strong> <strong> </strong> <strong> このドキュメントの「関連項目」セクションの「公開のパフォーマンスと5.0 参照用にパッケージを最適化する」のシーケンス手順を参照してください </strong> 。</span><span class="sxs-lookup"><span data-stu-id="2e742-155">For more information, see the <strong>Sequencing Steps to Optimize Packages for Publishing Performance</strong> and reference to <strong>App-V 5.0 Sequencing Guide</strong> in the <strong>See Also section of this document</strong>.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e742-156">前のシナリオの一般的な期待値は、ここにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-156">The general expectations of the previous scenario still apply here.</span></span> <span data-ttu-id="2e742-157">ただし、VM イメージは通常、非常に高コストのアレイに保存されることに注意してください。アプローチに若干の変更が加えられました。</span><span class="sxs-lookup"><span data-stu-id="2e742-157">However, keep in mind that VM images are typically stored in very costly arrays; a slight alteration has been made to the approach.</span></span> <span data-ttu-id="2e742-158">ベースイメージ内のユーザーによって対象化された仮想アプリケーションパッケージを事前に構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="2e742-158">Do not pre-configure user-targeted virtual application packages in the base image.</span></span></p>
<p><span data-ttu-id="2e742-159">この変更による影響については、このドキュメントの「ユーザーエクスペリエンスのチュートリアル」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e742-159">The impact of this alteration is detailed in the User Experience Walkthrough section of this document.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-pe"></a><span data-ttu-id="2e742-160">環境の準備</span><span class="sxs-lookup"><span data-stu-id="2e742-160">Preparing your Environment</span></span>

<span data-ttu-id="2e742-161">次の表は、基本イメージと UE-V またはその他の UPM ソリューションを準備するために必要な手順を示しています。</span><span class="sxs-lookup"><span data-stu-id="2e742-161">The following table displays the required steps to prepare the base image and the UE-V or another UPM solution for the approach.</span></span>

**<span data-ttu-id="2e742-162">基本イメージを準備する</span><span class="sxs-lookup"><span data-stu-id="2e742-162">Prepare the Base Image</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2e742-163">パフォーマンスを最適化</span><span class="sxs-lookup"><span data-stu-id="2e742-163">Optimized for Performance</span></span></th>
<th align="left"><span data-ttu-id="2e742-164">ストレージに最適化されている</span><span class="sxs-lookup"><span data-stu-id="2e742-164">Optimized for Storage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="2e742-165">Application Virtualization 5.0 SP2 クライアントバージョンのクライアント用の修正プログラムパッケージ4をインストールします。</span><span class="sxs-lookup"><span data-stu-id="2e742-165">Install the Hotfix Package 4 for Application Virtualization 5.0 SP2 client version of the client.</span></span></p></li>
<li><p><span data-ttu-id="2e742-166">UE-V をインストールして、UE-V のテンプレートギャラリーから App-v の設定テンプレートをダウンロードします。次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e742-166">Install UE-V and download the App-V Settings Template from the UE-V template Gallery, see the following steps.</span></span></p></li>
<li><p><span data-ttu-id="2e742-167">共有コンテンツストア (SCS) モードを構成します。</span><span class="sxs-lookup"><span data-stu-id="2e742-167">Configure for Shared Content Store (SCS) mode.</span></span> <span data-ttu-id="2e742-168">詳細については <a href="how-to-install-the-app-v-50-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.0 Client for Shared Content Store Mode](how-to-install-the-app-v-50-client-for-shared-content-store-mode.md)"> 、「共有コンテンツストアモード用の app-v 5.0 クライアントをインストールする方法」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="2e742-168">For more information see <a href="how-to-install-the-app-v-50-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.0 Client for Shared Content Store Mode](how-to-install-the-app-v-50-client-for-shared-content-store-mode.md)">How to Install the App-V 5.0 Client for Shared Content Store Mode</a>.</span></span></p></li>
<li><p><span data-ttu-id="2e742-169">ログインレジストリの DWORD でのユーザーの統合の保持を構成します。</span><span class="sxs-lookup"><span data-stu-id="2e742-169">Configure Preserve User Integrations on Login Registry DWORD.</span></span></p></li>
<li><p><span data-ttu-id="2e742-170">すべてのユーザーとグローバルなパッケージを事前構成するたとえば、 <strong> AppvClientPackage を追加 </strong> します。</span><span class="sxs-lookup"><span data-stu-id="2e742-170">Pre-configure all user- and global-targeted packages for example, <strong>Add-AppvClientPackage</strong>.</span></span></p></li>
<li><p><span data-ttu-id="2e742-171">すべてのユーザーとグローバルな接続グループを事前構成し <strong> ます。たとえば、AppvClientConnectionGroup を追加し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="2e742-171">Pre-configure all user- and global-targeted connection groups for example, <strong>Add-AppvClientConnectionGroup</strong>.</span></span></p></li>
<li><p><span data-ttu-id="2e742-172">グローバルターゲットパッケージをすべて事前に発行します。</span><span class="sxs-lookup"><span data-stu-id="2e742-172">Pre-publish all global-targeted packages.</span></span></p>
<p></p>
<p><span data-ttu-id="2e742-173">一方</span><span class="sxs-lookup"><span data-stu-id="2e742-173">Alternatively,</span></span></p>
<ul>
<li><p><span data-ttu-id="2e742-174">グローバル発行/更新を実行します。</span><span class="sxs-lookup"><span data-stu-id="2e742-174">Perform a global publishing/refresh.</span></span></p></li>
<li><p><span data-ttu-id="2e742-175">ユーザーの発行/更新を実行します。</span><span class="sxs-lookup"><span data-stu-id="2e742-175">Perform a user publishing/refresh.</span></span></p></li>
<li><p><span data-ttu-id="2e742-176">すべてのユーザー対象パッケージを公開解除します。</span><span class="sxs-lookup"><span data-stu-id="2e742-176">Un-publish all user-targeted packages.</span></span></p></li>
<li><p><span data-ttu-id="2e742-177">次のユーザー仮想ファイルシステム (VFS) エントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="2e742-177">Delete the following user-Virtual File System (VFS) entries.</span></span></p></li>
</ul>
<p><code>AppData\Local\Microsoft\AppV\Client\VFS</code></p>
<p><code>AppData\Roaming\Microsoft\AppV\Client\VFS</code></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="2e742-178">Application Virtualization 5.0 SP2 クライアントバージョンのクライアント用の修正プログラムパッケージ4をインストールします。</span><span class="sxs-lookup"><span data-stu-id="2e742-178">Install the Hotfix Package 4 for Application Virtualization 5.0 SP2 client version of the client.</span></span></p></li>
<li><p><span data-ttu-id="2e742-179">UE-V をインストールして、UE-V のテンプレートギャラリーから App-v の設定テンプレートをダウンロードします。次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e742-179">Install UE-V and download the App-V Settings Template from the UE-V template Gallery, see the following steps.</span></span></p></li>
<li><p><span data-ttu-id="2e742-180">共有コンテンツストア (SCS) モードを構成します。</span><span class="sxs-lookup"><span data-stu-id="2e742-180">Configure for Shared Content Store (SCS) mode.</span></span> <span data-ttu-id="2e742-181">詳細については <a href="how-to-install-the-app-v-50-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.0 Client for Shared Content Store Mode](how-to-install-the-app-v-50-client-for-shared-content-store-mode.md)"> 、「共有コンテンツストアモード用の app-v 5.0 クライアントをインストールする方法」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="2e742-181">For more information see <a href="how-to-install-the-app-v-50-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.0 Client for Shared Content Store Mode](how-to-install-the-app-v-50-client-for-shared-content-store-mode.md)">How to Install the App-V 5.0 Client for Shared Content Store Mode</a>.</span></span></p></li>
<li><p><span data-ttu-id="2e742-182">ログインレジストリの DWORD でのユーザーの統合の保持を構成します。</span><span class="sxs-lookup"><span data-stu-id="2e742-182">Configure Preserve User Integrations on Login Registry DWORD.</span></span></p></li>
<li><p><span data-ttu-id="2e742-183">すべてのグローバル対象パッケージを事前構成し <strong> ます。たとえば、AppvClientPackage を追加 </strong> します。</span><span class="sxs-lookup"><span data-stu-id="2e742-183">Pre-configure all global-targeted packages for example, <strong>Add-AppvClientPackage</strong>.</span></span></p></li>
<li><p><span data-ttu-id="2e742-184">すべてのグローバルターゲット接続グループを事前に構成するたとえば、 <strong> AppvClientConnectionGroup を追加 </strong> します。</span><span class="sxs-lookup"><span data-stu-id="2e742-184">Pre-configure all global-targeted connection groups for example, <strong>Add-AppvClientConnectionGroup</strong>.</span></span></p></li>
<li><p><span data-ttu-id="2e742-185">グローバルターゲットパッケージをすべて事前に発行します。</span><span class="sxs-lookup"><span data-stu-id="2e742-185">Pre-publish all global-targeted packages.</span></span></p>
<p></p></li>
</ul></td>
</tr>
</tbody>
</table>



<span data-ttu-id="2e742-186">**構成**-重要な App-v クライアントの構成と、その他のコンテキストと使い方については、次の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="2e742-186">**Configurations** - For critical App-V Client configurations and for a little more context and how-to, review the following information:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2e742-187">構成設定</span><span class="sxs-lookup"><span data-stu-id="2e742-187">Configuration Setting</span></span></th>
<th align="left"><span data-ttu-id="2e742-188">この機能について</span><span class="sxs-lookup"><span data-stu-id="2e742-188">What does this do?</span></span></th>
<th align="left"><span data-ttu-id="2e742-189">使い方を教えてください。</span><span class="sxs-lookup"><span data-stu-id="2e742-189">How should I use it?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2e742-190">共有コンテンツストア (SCS) モード</span><span class="sxs-lookup"><span data-stu-id="2e742-190">Shared Content Store (SCS) Mode</span></span></p>
<ul>
<li><p><span data-ttu-id="2e742-191"><strong>AppvClientConfiguration </strong> – <strong> sharedcontentstoremode を使って PowerShell で構成でき </strong> ます。または</span><span class="sxs-lookup"><span data-stu-id="2e742-191">Configurable in PowerShell using <strong>Set- AppvClientConfiguration</strong> –<strong>SharedContentStoreMode</strong>, or</span></span></p></li>
<li><p><span data-ttu-id="2e742-192">App-v 5.0 クライアントのインストール中。</span><span class="sxs-lookup"><span data-stu-id="2e742-192">During installation of the App-V 5.0 client.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="2e742-193">共有コンテンツストアを実行している場合、発行データはハードディスク上で管理されます。その他の仮想アプリケーションアセットは、メモリ (RAM) で管理されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-193">When running the shared content store only publishing data is maintained on hard disk; other virtual application assets are maintained in memory (RAM).</span></span></p>
<p><span data-ttu-id="2e742-194">これにより、ローカル記憶域を節約し、ディスク i/o を1秒あたり少なく (IOPS) 減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="2e742-194">This helps to conserve local storage and minimize disk I/O per second (IOPS).</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e742-195">これは、App-v クライアントエンドポイントと SCS コンテンツサーバーである SAN の間で待機時間の短い接続が利用できる場合にお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2e742-195">This is recommended when low-latency connections are available between the App-V Client endpoint and the SCS content server, SAN.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2e742-196">PreserveUserIntegrationsOnLogin</span><span class="sxs-lookup"><span data-stu-id="2e742-196">PreserveUserIntegrationsOnLogin</span></span></p>
<ul>
<li><p><span data-ttu-id="2e742-197">[ <strong> HKEY_LOCAL_MACHINE </strong>  \  <strong> ソフトウェア </strong>  \  <strong> Microsoft </strong>  \  <strong> AppV </strong>  \  <strong> クライアント </strong>  \  <strong> </strong> との統合] の下のレジストリで構成します。</span><span class="sxs-lookup"><span data-stu-id="2e742-197">Configure in the Registry under <strong>HKEY_LOCAL_MACHINE</strong> \ <strong>Software</strong> \ <strong>Microsoft</strong> \ <strong>AppV</strong> \ <strong>Client</strong> \ <strong>Integration</strong>.</span></span></p></li>
<li><p><span data-ttu-id="2e742-198">値1の DWORD 値 PreserveUserIntegrationsOnLogin を作成し <strong> </strong> <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="2e742-198">Create the DWORD value <strong>PreserveUserIntegrationsOnLogin</strong> with a value of <strong>1</strong>.</span></span></p></li>
<li><p><span data-ttu-id="2e742-199">App-v クライアントサービスを再起動するか、App-v クライアントを実行しているコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="2e742-199">Restart the App-V client service or restart the computer running the App-V Client.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="2e742-200">特定のパッケージをまだ構成していない場合 (AppvClientPackage)、この設定が構成されていない場合 <strong> </strong> 、app-v クライアントは永続的なユーザー統合による統合を解除し、その後 \* に再統合 \* します。</span><span class="sxs-lookup"><span data-stu-id="2e742-200">If you have not pre-configured (<strong>Add-AppvClientPackage</strong>) a specific package and this setting is not configured, the App-V Client will de-integrate\* the persisted user integrations, then re-integrate\*.</span></span></p>
<p><span data-ttu-id="2e742-201">上記の条件を満たしているすべてのパッケージについて、発行/更新の際に、効率的に2回作業が行われます。</span><span class="sxs-lookup"><span data-stu-id="2e742-201">For every package that meets the above conditions, effectively twice the work will be done during publishing/refresh.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e742-202">ベースイメージで利用可能なすべてのユーザーパッケージを事前に構成する予定がない場合は、この設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="2e742-202">If you don’t plan to pre-configure every available user package in the base image, use this setting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2e742-203">MaxConcurrentPublishingRefresh</span><span class="sxs-lookup"><span data-stu-id="2e742-203">MaxConcurrentPublishingRefresh</span></span></p>
<ul>
<li><p><span data-ttu-id="2e742-204">「Microsoft AppV 強力なクライアントの公開 HKEY_LOCAL_MACHINE」のレジストリで構成 <strong> </strong> &lt; &gt; </strong>  \  <strong> </strong>  \  <strong> </strong> &lt; &gt; </strong>  \  <strong> </strong> します。</span><span class="sxs-lookup"><span data-stu-id="2e742-204">Configure in the Registry under <strong>HKEY_LOCAL_MACHINE</strong> &lt;strong&gt;Software</strong> \ <strong>Microsoft</strong> \ <strong>AppV</strong> &lt;strong&gt;Client</strong> \ <strong>Publishing</strong>.</span></span></p></li>
<li><p><span data-ttu-id="2e742-205"><strong> </strong> 同時発行の更新の最大数に応じて DWORD 値 MaxConcurrentPublishingrefresh を作成します。</span><span class="sxs-lookup"><span data-stu-id="2e742-205">Create the DWORD value <strong>MaxConcurrentPublishingrefresh</strong> with the desired maximum number of concurrent publishing refreshes.</span></span></p></li>
<li><p><span data-ttu-id="2e742-206">App-v クライアントサービスとコンピューターを再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2e742-206">The App-V client service and computer do not need to be restarted.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="2e742-207">この設定は、同時に公開の更新/同期を実行できるユーザーの数を決定します。</span><span class="sxs-lookup"><span data-stu-id="2e742-207">This setting determines the number of users that can perform a publishing refresh/sync at the same time.</span></span> <span data-ttu-id="2e742-208">既定の設定では、制限はありません。</span><span class="sxs-lookup"><span data-stu-id="2e742-208">The default setting is no limit.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e742-209">同時発行の更新数を制限すると、コンピューターのパフォーマンスに影響を与える可能性のある CPU 使用量が過度に消費されることを回避できます。</span><span class="sxs-lookup"><span data-stu-id="2e742-209">Limiting the number of concurrent publishing refreshes prevents excessive CPU usage that could impact computer performance.</span></span> <span data-ttu-id="2e742-210">この制限は、複数のユーザーが同じコンピューターに一度にログインして、発行更新同期を実行できる RDS 環境でお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2e742-210">This limit is recommended in an RDS environment, where multiple users can log in to the same computer at the same time and perform a publishing refresh sync.</span></span></p>
<p><span data-ttu-id="2e742-211">同時発行の更新しきい値に達した場合は、新しいアプリケーションを公開し、ログイン後にエンドユーザーがそれらのアプリを使用できるようにするために、一定の時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="2e742-211">If the concurrent publishing refresh threshold is reached, the time required to publish new applications and make them available to end users after they log in could take an indeterminate amount of time.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="2e742-212">App-v のアプローチ用に UE-V ソリューションを構成する</span><span class="sxs-lookup"><span data-stu-id="2e742-212">Configure UE-V solution for App-V Approach</span></span>

<span data-ttu-id="2e742-213">Microsoft User Experience Virtualization (UE-V) を使用して、特定のユーザーのアプリケーション設定と Windows オペレーティングシステムの設定をキャプチャし、一元管理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2e742-213">We recommend using Microsoft User Experience Virtualization (UE-V) to capture and centralize application settings and Windows operating system settings for a specific user.</span></span> <span data-ttu-id="2e742-214">これらの設定は、デスクトップコンピューター、ノート pc、仮想デスクトップインフラストラクチャ (VDI) セッションなど、ユーザーによってアクセスされるさまざまなコンピューターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-214">These settings are then applied to the different computers that are accessed by the user, including desktop computers, laptop computers, and virtual desktop infrastructure (VDI) sessions.</span></span> <span data-ttu-id="2e742-215">UE-V は、RDS と VDI のシナリオに最適化されています。</span><span class="sxs-lookup"><span data-stu-id="2e742-215">UE-V is optimized for RDS and VDI scenarios.</span></span>

<span data-ttu-id="2e742-216">詳細については、「[ユーザーエクスペリエンスの仮想化の概要 2.0](https://technet.microsoft.com/library/dn458936.aspx) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e742-216">For more information see [Getting Started With User Experience Virtualization 2.0](https://technet.microsoft.com/library/dn458936.aspx)</span></span>

<span data-ttu-id="2e742-217">基本的に必要なことは、UE-V クライアントをインストールし、 [Microsoft User Experience Virtualization (ue-v) テンプレートギャラリー](https://gallery.technet.microsoft.com/Authored-UE-V-Settings-bb442a33)から次の microsoft 作成された app-v 設定テンプレートをダウンロードすることです。</span><span class="sxs-lookup"><span data-stu-id="2e742-217">In essence all that is required is to install the UE-V client and download the following Microsoft authored App-V settings template from the [Microsoft User Experience Virtualization (UE-V) template gallery](https://gallery.technet.microsoft.com/Authored-UE-V-Settings-bb442a33).</span></span> <span data-ttu-id="2e742-218">テンプレートを登録します。</span><span class="sxs-lookup"><span data-stu-id="2e742-218">Register the template.</span></span> <span data-ttu-id="2e742-219">UE-V テンプレートの詳細については、「UE-V 固有のリソース」を参照してください。これにより、[テンプレートを取得して登録することが](https://technet.microsoft.com/library/dn458936.aspx)できます。</span><span class="sxs-lookup"><span data-stu-id="2e742-219">For more information around UE-V templates see [The UE-V specific resource for acquiring and registering the template](https://technet.microsoft.com/library/dn458936.aspx).</span></span>

**<span data-ttu-id="2e742-220">注</span><span class="sxs-lookup"><span data-stu-id="2e742-220">Note</span></span>**  
<span data-ttu-id="2e742-221">追加の構成手順を実行しなくても、Microsoft User Environment Virtualization (UE-V) では、ターゲットコンピューター上の [スタート] メニューのショートカット (.lnk ファイル) を同期することはできません。</span><span class="sxs-lookup"><span data-stu-id="2e742-221">Without performing an additional configuration step, the Microsoft User Environment Virtualization (UE-V) will not be able to synchronize the Start menu shortcuts (.lnk files) on the target computer.</span></span> <span data-ttu-id="2e742-222">.Lnk ファイルの種類は、既定では除外されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-222">The .lnk file type is excluded by default.</span></span>

<span data-ttu-id="2e742-223">UE-V は、RDS および VDI シナリオの除外リストから .lnk ファイルの種類を削除することのみをサポートします。ここでは、すべてのユーザーのデバイスが同じ場所にインストールされ、すべての .lnk ファイルがすべてのユーザーのデバイスで有効になります。</span><span class="sxs-lookup"><span data-stu-id="2e742-223">UE-V will only support removing the .lnk file type from the exclusion list in the RDS and VDI scenarios, where every user’s device will have the same set of applications installed to the same location and every .lnk file is valid for all the users’ devices.</span></span> <span data-ttu-id="2e742-224">たとえば、現在、UE-V は、次の2つのシナリオをサポートしていません。そのため、すべてのデバイスではなく、ショートカットが有効になります。</span><span class="sxs-lookup"><span data-stu-id="2e742-224">For example, UE-V would not currently support the following 2 scenarios, because the net result will be that the shortcut will be valid on one but not all devices.</span></span>

-   <span data-ttu-id="2e742-225">.Lnk ファイルが有効になっているデバイスにユーザーがアプリケーションをインストールしていて、同じネイティブアプリケーションが別のデバイスにインストールされている場合は、.lnk ファイルが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="2e742-225">If a user has an application installed on one device with .lnk files enabled and the same native application installed on another device to a different installation root with .lnk files enabled.</span></span>

-   <span data-ttu-id="2e742-226">ユーザーが1つのデバイスにアプリケーションをインストールしていて、.lnk ファイルが有効になっていない場合。</span><span class="sxs-lookup"><span data-stu-id="2e742-226">If a user has an application installed on one device but not another with .lnk files enabled.</span></span>



**<span data-ttu-id="2e742-227">重要</span><span class="sxs-lookup"><span data-stu-id="2e742-227">Important</span></span>**  
<span data-ttu-id="2e742-228">このトピックでは、レジストリエディターを使用して Windows レジストリを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2e742-228">This topic describes how to change the Windows registry by using Registry Editor.</span></span> <span data-ttu-id="2e742-229">Windows レジストリを誤って変更した場合、Windows の再インストールが必要になる可能性のある重大な問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-229">If you change the Windows registry incorrectly, you can cause serious problems that might require you to reinstall Windows.</span></span> <span data-ttu-id="2e742-230">レジストリを変更する前に、レジストリファイル (system.dat とユーザー) のバックアップコピーを作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-230">You should make a backup copy of the registry files (System.dat and User.dat) before you change the registry.</span></span> <span data-ttu-id="2e742-231">Microsoft は、レジストリを変更したときに発生する可能性のある問題を解決できないことを保証できません。</span><span class="sxs-lookup"><span data-stu-id="2e742-231">Microsoft cannot guarantee that the problems that might occur when you change the registry can be resolved.</span></span> <span data-ttu-id="2e742-232">レジストリは、自分の責任において変更してください。</span><span class="sxs-lookup"><span data-stu-id="2e742-232">Change the registry at your own risk.</span></span>



<span data-ttu-id="2e742-233">Microsoft Registry Editor (regedit.exe) を使用して、ExcludedFileTypes の [ **HKEY \ _LOCAL \ _MACHINE**  \\  **Software**  \\  **Microsoft**  \\  **UEV**  \\  **Agent**  \\  **Configuration**  \\  **ExcludedFileTypes**に移動し、除外するファイルの種類から .lnk を削除し**ます**。</span><span class="sxs-lookup"><span data-stu-id="2e742-233">Using the Microsoft Registry Editor (regedit.exe), navigate to **HKEY\_LOCAL\_MACHINE** \\ **Software** \\ **Microsoft** \\ **UEV** \\ **Agent** \\ **Configuration** \\ **ExcludedFileTypes** and remove **.lnk** from the excluded file types.</span></span>

**<span data-ttu-id="2e742-234">他のユーザープロファイル管理 (UPM) ソリューションを App-v のアプローチとして構成する</span><span class="sxs-lookup"><span data-stu-id="2e742-234">Configure other User Profile Management (UPM) solution for App-V Approach</span></span>**

<span data-ttu-id="2e742-235">ステートフル環境で期待されるのは、UPM ソリューションが実装されていて、セッション間およびログイン間でのユーザーデータの常設をサポートできるということです。</span><span class="sxs-lookup"><span data-stu-id="2e742-235">The expectation in a stateful environment is that a UPM solution is implemented and can support persistence of user data across sessions and between logins.</span></span>

<span data-ttu-id="2e742-236">UPM ソリューションの要件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2e742-236">The requirements for the UPM solution are as follows.</span></span>

<span data-ttu-id="2e742-237">最適化されたログインエクスペリエンスを有効にするには (たとえば、ユーザーの App-v 5.0 の方法)、ソリューションが次の機能をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-237">To enable an optimized login experience, for example the App-V 5.0 approach for the user, the solution must be capable of:</span></span>

-   <span data-ttu-id="2e742-238">ユーザープロファイル/ペルソナの一部として、次のユーザーの統合を保持します。</span><span class="sxs-lookup"><span data-stu-id="2e742-238">Persisting the below user integrations as part of the user profile/persona.</span></span>

-   <span data-ttu-id="2e742-239">Login (または application start) でユーザープロファイル同期をトリガーすると、公開/更新の開始前にすべてのユーザー統合が適用されることを保証できます。</span><span class="sxs-lookup"><span data-stu-id="2e742-239">Triggering a user profile sync on login (or application start), which can guarantee that all user integrations are applied before publishing/refresh begin, or,</span></span>

-   <span data-ttu-id="2e742-240">ユーザープロファイルディスク (UPD) またはユーザー統合を含む類似技術の接続とデタッチ。</span><span class="sxs-lookup"><span data-stu-id="2e742-240">Attaching and detaching a user profile disk (UPD) or similar technology that contains the user integrations.</span></span>

-   <span data-ttu-id="2e742-241">セッションがログオフされる前に、ユーザー統合を構成する場所への変更をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="2e742-241">Capturing changes to the locations, which constitute the user integrations, prior to session logoff.</span></span>

<span data-ttu-id="2e742-242">公開サーバー (**AppvPublishingServer**) を追加するときに app-v 5.0 を使用すると、ログオン時や指定した更新間隔の後など、同期を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="2e742-242">With App-V 5.0 when you add a publishing server (**Add-AppvPublishingServer**) you can configure synchronization, for example refresh during log on and/or after a specified refresh interval.</span></span> <span data-ttu-id="2e742-243">どちらの場合も、スケジュールされたタスクが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-243">In both cases a scheduled task is created.</span></span>

<span data-ttu-id="2e742-244">以前のバージョンの App-v 5.0 では、ユーザーとグローバル更新を開始する VBScript を使用して、両方のスケジュールされたタスクが構成されていました。</span><span class="sxs-lookup"><span data-stu-id="2e742-244">In previous versions of App-V 5.0, both scheduled tasks were configured using a VBScript that would initiate the user and global refresh.</span></span> <span data-ttu-id="2e742-245">アプリケーションの仮想化 5.0 SP2 の修正プログラムパッケージ4を使用すると、ログオン時にユーザーの更新が**SyncAppvPublishingServer.exe**によって開始されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-245">With Hotfix Package 4 for Application Virtualization 5.0 SP2 the user refresh on log on is initiated by **SyncAppvPublishingServer.exe**.</span></span> <span data-ttu-id="2e742-246">この変更は、UPM ソリューションにトリガープロセスを提供するために導入されました。</span><span class="sxs-lookup"><span data-stu-id="2e742-246">This change was introduced to provide UPM solutions a trigger process.</span></span> <span data-ttu-id="2e742-247">このプロセスでは、UPM ソリューションがユーザー統合を適用できるように、発行/更新が遅延されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-247">This process will delay the publish /refresh to allow the UPM solution to apply the user integrations.</span></span> <span data-ttu-id="2e742-248">公開/更新が完了すると終了します。</span><span class="sxs-lookup"><span data-stu-id="2e742-248">It will exit once the publishing/refresh is complete.</span></span>

**<span data-ttu-id="2e742-249">ユーザーの統合</span><span class="sxs-lookup"><span data-stu-id="2e742-249">User Integrations</span></span>**

<span data-ttu-id="2e742-250">Registry – HKEY \ _CURRENT \ _USER</span><span class="sxs-lookup"><span data-stu-id="2e742-250">Registry – HKEY\_CURRENT\_USER</span></span>

-   <span data-ttu-id="2e742-251">Path-ソフトウェア \\ クラス</span><span class="sxs-lookup"><span data-stu-id="2e742-251">Path - Software\\Classes</span></span>

    <span data-ttu-id="2e742-252">除外: Local Settings、ActivatableClasses、AppX \ \*</span><span class="sxs-lookup"><span data-stu-id="2e742-252">Exclude: Local Settings, ActivatableClasses, AppX\*</span></span>

-   <span data-ttu-id="2e742-253">Path-ソフトウェア \ microsoft AppV</span><span class="sxs-lookup"><span data-stu-id="2e742-253">Path - Software\\Microsoft\\AppV</span></span>

-   <span data-ttu-id="2e742-254">パス-Software\\Microsoft\\Windows\\CurrentVersion\\App のパス</span><span class="sxs-lookup"><span data-stu-id="2e742-254">Path- Software\\Microsoft\\Windows\\CurrentVersion\\App Paths</span></span>

**<span data-ttu-id="2e742-255">ファイルの場所</span><span class="sxs-lookup"><span data-stu-id="2e742-255">File Locations</span></span>**

-   <span data-ttu-id="2e742-256">ルート– "環境変数" APPDATA</span><span class="sxs-lookup"><span data-stu-id="2e742-256">Root – “Environment Variable” APPDATA</span></span>

    <span data-ttu-id="2e742-257">Path – Microsoft\\AppV\\Client\\Catalog</span><span class="sxs-lookup"><span data-stu-id="2e742-257">Path – Microsoft\\AppV\\Client\\Catalog</span></span>

-   <span data-ttu-id="2e742-258">ルート– "環境変数" APPDATA</span><span class="sxs-lookup"><span data-stu-id="2e742-258">Root – “Environment Variable” APPDATA</span></span>

    <span data-ttu-id="2e742-259">Path – Microsoft\\AppV\\Client\\Integration</span><span class="sxs-lookup"><span data-stu-id="2e742-259">Path – Microsoft\\AppV\\Client\\Integration</span></span>

-   <span data-ttu-id="2e742-260">ルート– "環境変数" APPDATA</span><span class="sxs-lookup"><span data-stu-id="2e742-260">Root – “Environment Variable” APPDATA</span></span>

    <span data-ttu-id="2e742-261">Path-Microsoft\\Windows\\Start menu¥プログラム</span><span class="sxs-lookup"><span data-stu-id="2e742-261">Path - Microsoft\\Windows\\Start Menu\\Programs</span></span>

-   <span data-ttu-id="2e742-262">(すべてのデスクトップショートカット、仮想と非仮想) を保持するには</span><span class="sxs-lookup"><span data-stu-id="2e742-262">(To persist all desktop shortcuts, virtual and non-virtual)</span></span>

    <span data-ttu-id="2e742-263">ルート-"KnownFolder" {B4BFCC3A-DB2C-424C-B029-7FE99A87C641} FileMask-\ \* .lnk</span><span class="sxs-lookup"><span data-stu-id="2e742-263">Root - “KnownFolder” {B4BFCC3A-DB2C-424C-B029-7FE99A87C641}FileMask - \*.lnk</span></span>

**<span data-ttu-id="2e742-264">Microsoft User Experience Virtualization (UE-V)</span><span class="sxs-lookup"><span data-stu-id="2e742-264">Microsoft User Experience Virtualization (UE-V)</span></span>**

<span data-ttu-id="2e742-265">さらに、Microsoft User Experience Virtualization (UE-V) を使用して、特定のユーザーのアプリケーション設定と Windows オペレーティングシステムの設定をキャプチャして一元管理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2e742-265">Additionally, we recommend using Microsoft User Experience Virtualization (UE-V) to capture and centralize application settings and Windows operating system settings for a specific user.</span></span> <span data-ttu-id="2e742-266">これらの設定は、デスクトップコンピューター、ノート pc、仮想デスクトップインフラストラクチャ (VDI) セッションなど、ユーザーによってアクセスされるさまざまなコンピューターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-266">These settings are then applied to the different computers that are accessed by the user, including desktop computers, laptop computers, and virtual desktop infrastructure (VDI) sessions.</span></span>

<span data-ttu-id="2e742-267">詳細については、「[ユーザーエクスペリエンスの仮想化1.0 の概要](https://technet.microsoft.com/library/jj680015.aspx)」および「 [Ue-v のテンプレートギャラリーを使用した設定場所テンプレートの共有](https://technet.microsoft.com/library/jj679972.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e742-267">For more information see [Getting Started With User Experience Virtualization 1.0](https://technet.microsoft.com/library/jj680015.aspx) and [Sharing Settings Location Templates with the UE-V Template Gallery](https://technet.microsoft.com/library/jj679972.aspx).</span></span>

### <a href="" id="bkmk-uewt"></a><span data-ttu-id="2e742-268">ユーザーエクスペリエンスのウォークスルー</span><span class="sxs-lookup"><span data-stu-id="2e742-268">User Experience Walk-through</span></span>

<span data-ttu-id="2e742-269">ここでは、App-v および UPM の操作と、ユーザーが求める期待を段階的に説明します。</span><span class="sxs-lookup"><span data-stu-id="2e742-269">This following is a step-by-step walk-through of the App-V and UPM operations and the expectations users should expect.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2e742-270">パフォーマンスを最適化</span><span class="sxs-lookup"><span data-stu-id="2e742-270">Optimized for Performance</span></span></th>
<th align="left"><span data-ttu-id="2e742-271">ストレージに最適化されている</span><span class="sxs-lookup"><span data-stu-id="2e742-271">Optimized for Storage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2e742-272">VDI/RDSH 環境でこの方法を実装した後、最初のログイン時に、</span><span class="sxs-lookup"><span data-stu-id="2e742-272">After implementing this approach in the VDI/RDSH environment, on first login,</span></span></p>
<ul>
<li><p><span data-ttu-id="2e742-273">実行ユーザーによる公開/更新が開始されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-273">(Operation) A user-publishing/refresh is initiated.</span></span> <span data-ttu-id="2e742-274">求めユーザーが初めて仮想アプリケーションを公開した場合 (永続的でない場合など) は、通常の公開/更新時間になります。</span><span class="sxs-lookup"><span data-stu-id="2e742-274">(Expectation) If this is the first time a user has published virtual applications (e.g. non-persistent), this will take the usual duration of a publishing/refresh.</span></span></p></li>
<li><p><span data-ttu-id="2e742-275">実行公開/更新後、UPM ソリューションによってユーザーの統合がキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="2e742-275">(Operation) After the publishing/refresh, the UPM solution captures the user integrations.</span></span> <span data-ttu-id="2e742-276">求めUPM ソリューションがどのように構成されているかによって、これはログオフプロセスの一部として発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="2e742-276">(Expectation) Depending on how the UPM solution is configured, this may occur as part of the logoff process.</span></span> <span data-ttu-id="2e742-277">これにより、ユーザーの状態を維持する場合と同様のオーバーヘッドが発生します。</span><span class="sxs-lookup"><span data-stu-id="2e742-277">This will incur the same/similar overhead as persisting the user state.</span></span></p></li>
</ul>
<p><span data-ttu-id="2e742-278">後続のログイン時:</span><span class="sxs-lookup"><span data-stu-id="2e742-278">On subsequent logins:</span></span></p>
<ul>
<li><p><span data-ttu-id="2e742-279">実行UPM ソリューションは、公開/更新の前にユーザー統合をシステムに適用します。</span><span class="sxs-lookup"><span data-stu-id="2e742-279">(Operation) UPM solution applies the user integrations to the system prior to publishing/refresh.</span></span></p>
<p><span data-ttu-id="2e742-280">求めデスクトップまたは [スタート] メニューにショートカットが表示されます。この機能は、すぐに動作します。</span><span class="sxs-lookup"><span data-stu-id="2e742-280">(Expectation) There will be shortcuts present on the desktop, or in the start menu, which work immediately.</span></span> <span data-ttu-id="2e742-281">公開/更新が完了すると (パッケージの資格の変更)、一部の機能が消える場合があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-281">When the publishing/refresh completes (i.e., package entitlements change), some may go away.</span></span></p></li>
<li><p><span data-ttu-id="2e742-282">実行公開/更新では、ユーザーパッケージの利用資格の変更について、公開および公開操作が処理されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-282">(Operation) Publishing/refresh will process un-publish and publish operations for changes in user package entitlements.</span></span> <span data-ttu-id="2e742-283">求め権利の変更がない場合、publishing1 は秒単位で完了します。</span><span class="sxs-lookup"><span data-stu-id="2e742-283">(Expectation) If there are no entitlement changes, publishing1 will complete in seconds.</span></span> <span data-ttu-id="2e742-284">そうしないと、仮想アプリケーションの数と複雑さ \* に関係なく発行/更新が増加します。</span><span class="sxs-lookup"><span data-stu-id="2e742-284">Otherwise, the publishing/refresh will increase relative to the number and complexity\* of virtual applications</span></span></p></li>
<li><p><span data-ttu-id="2e742-285">実行UPM ソリューションは、ログオフ時にもう一度ユーザーの統合をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="2e742-285">(Operation) UPM solution will capture user integrations again at logoff.</span></span> <span data-ttu-id="2e742-286">求め前と同じです。</span><span class="sxs-lookup"><span data-stu-id="2e742-286">(Expectation) Same as previous.</span></span></p></li>
</ul>
<p><span data-ttu-id="2e742-287">¹発行操作 (AppVClientPackage) では、 <strong> </strong> ユーザーカタログにエントリが追加され、ユーザーに資格がマッピングされ、ローカルストアが識別され、統合手順が完了して終了します。</span><span class="sxs-lookup"><span data-stu-id="2e742-287">¹ The publishing operation (<strong>Publish-AppVClientPackage</strong>) adds entries to the user catalog, maps entitlement to the user, identifies the local store, and finishes by completing any integration steps.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e742-288">VDI/RDSH 環境でこの方法を実装した後、最初のログイン時に、</span><span class="sxs-lookup"><span data-stu-id="2e742-288">After implementing this approach in the VDI/RDSH environment, on first login,</span></span></p>
<ul>
<li><p><span data-ttu-id="2e742-289">実行ユーザーによる公開/更新が開始されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-289">(Operation) A user-publishing/refresh is initiated.</span></span> <span data-ttu-id="2e742-290">求め</span><span class="sxs-lookup"><span data-stu-id="2e742-290">(Expectation)</span></span></p>
<ul>
<li><p><span data-ttu-id="2e742-291">ユーザーが初めて仮想アプリケーションを公開した場合 (永続的でない場合など) は、通常の公開/更新の期間がかかります。</span><span class="sxs-lookup"><span data-stu-id="2e742-291">If this is the first time a user has published virtual applications (e.g., non-persistent), this will take the usual duration of a publishing/refresh.</span></span></p></li>
<li><p><span data-ttu-id="2e742-292">最初と後のログインは、パッケージ (追加/更新) を事前に構成することによって影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="2e742-292">First and subsequent logins will be impacted by pre-configuring of packages (add/refresh).</span></span></p>
<p></p></li>
</ul></li>
<li><p><span data-ttu-id="2e742-293">実行公開/更新後、UPM ソリューションによってユーザーの統合がキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="2e742-293">(Operation) After the publishing/refresh, the UPM solution captures the user integrations.</span></span> <span data-ttu-id="2e742-294">求めUPM ソリューションがどのように構成されているかによって、これはログオフプロセスの一部として発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="2e742-294">(Expectation) Depending on how the UPM solution is configured, this may occur as part of the logoff process.</span></span> <span data-ttu-id="2e742-295">これにより、ユーザーの状態を維持する場合と同様のオーバーヘッドが発生します。</span><span class="sxs-lookup"><span data-stu-id="2e742-295">This will incur the same/similar overhead as persisting the user state</span></span></p></li>
</ul>
<p><span data-ttu-id="2e742-296">後続のログイン時:</span><span class="sxs-lookup"><span data-stu-id="2e742-296">On subsequent logins:</span></span></p>
<ul>
<li><p><span data-ttu-id="2e742-297">実行UPM ソリューションは、公開/更新の前にユーザー統合をシステムに適用します。</span><span class="sxs-lookup"><span data-stu-id="2e742-297">(Operation) UPM solution applies the user integrations to the system prior to publishing/refresh.</span></span></p></li>
<li><p><span data-ttu-id="2e742-298">実行追加/更新では、ユーザーのすべてのターゲットアプリケーションを事前に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-298">(Operation) Add/refresh must pre-configure all user targeted applications.</span></span> <span data-ttu-id="2e742-299">求め</span><span class="sxs-lookup"><span data-stu-id="2e742-299">(Expectation)</span></span></p>
<ul>
<li><p><span data-ttu-id="2e742-300">これにより、アプリケーションの可用性が大幅に向上することがあります (10 秒の順序で)。</span><span class="sxs-lookup"><span data-stu-id="2e742-300">This may increase the time to application availability significantly (on the order of 10’s of seconds).</span></span></p></li>
<li><p><span data-ttu-id="2e742-301">これにより、仮想アプリケーションの数と複雑さ \* に基づいて、公開の更新時間が増加します。</span><span class="sxs-lookup"><span data-stu-id="2e742-301">This will increase the publishing refresh time relative to the number and complexity\* of virtual applications.</span></span></p>
<p></p></li>
</ul></li>
<li><p><span data-ttu-id="2e742-302">実行公開/更新では、ユーザーパッケージの利用資格の変更について、公開および公開操作が処理されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-302">(Operation) Publishing/refresh will process un-publish and publish operations for changes to user package entitlements.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2e742-303">成功</span><span class="sxs-lookup"><span data-stu-id="2e742-303">Outcome</span></span></th>
<th align="left"><span data-ttu-id="2e742-304">成功</span><span class="sxs-lookup"><span data-stu-id="2e742-304">Outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="2e742-305">ユーザー統合は完全に保持されるため、たとえば、パブリッシング/refresh の統合などの機能はありません。</span><span class="sxs-lookup"><span data-stu-id="2e742-305">Because the user integrations are entirely preserved, there will be no work for example, integration for the publishing/refresh to complete.</span></span> <span data-ttu-id="2e742-306">すべての仮想アプリケーションは、ログインしてから数秒以内で利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="2e742-306">All virtual applications will be available within seconds of login.</span></span></p></li>
<li><p><span data-ttu-id="2e742-307">公開/更新では、エクスペリエンスに影響を与える仮想アプリケーションのユーザーに対する変更を処理します。</span><span class="sxs-lookup"><span data-stu-id="2e742-307">The publishing/refresh will process changes to the users entitled virtual applications which impacts the experience.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="2e742-308">追加/更新では、すべての仮想アプリケーションを仮想マシンに再構成する必要があるため、すべてのログインでの公開の更新時間は延長されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-308">Because the add/refresh must re-configure all the virtual applications to the VM, the publishing refresh time on every login will be extended.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-plc"></a><span data-ttu-id="2e742-309">パッケージライフサイクルへの影響</span><span class="sxs-lookup"><span data-stu-id="2e742-309">Impact to Package Life Cycle</span></span>

<span data-ttu-id="2e742-310">パッケージのアップグレードは、パッケージのライフサイクルにおいて非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="2e742-310">Upgrading a package is a crucial aspect of the package lifecycle.</span></span> <span data-ttu-id="2e742-311">ユーザーが適切にアップグレードされた (公開) またはダウングレードされた (公開されていない) 仮想アプリケーションパッケージにアクセスできることを保証するために、これらの変更を反映するように基本イメージを更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2e742-311">To help guarantee users have access to the appropriate upgraded (published) or downgraded (un-published) virtual application packages, it is recommended you update the base image to reflect these changes.</span></span> <span data-ttu-id="2e742-312">次のセクションをレビューする理由について説明します。</span><span class="sxs-lookup"><span data-stu-id="2e742-312">To understand why review the following section:</span></span>

<span data-ttu-id="2e742-313">App-v 5.0 SP2 では、保留状態の概念が導入されました。</span><span class="sxs-lookup"><span data-stu-id="2e742-313">App-V 5.0 SP2 introduced the concept of pending states.</span></span> <span data-ttu-id="2e742-314">かつては</span><span class="sxs-lookup"><span data-stu-id="2e742-314">In the past,</span></span>

-   <span data-ttu-id="2e742-315">管理者が権限を変更した場合、またはパッケージの新しいバージョン (アップグレード済み) を作成した場合、またはパッケージが使用されていた公開/更新時に、発行取り消し操作や公開操作が失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="2e742-315">If an administrator changed entitlements or created a new version of a package (upgraded) and during a publishing/refresh that package was in-use, the un-publish or publish operation, respectively, would fail.</span></span>

-   <span data-ttu-id="2e742-316">これで、パッケージが使用中の場合、操作は保留されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-316">Now, if a package is in-use the operation will be pended.</span></span> <span data-ttu-id="2e742-317">公開/公開保留の操作は、サービスの再開時に処理されるか、または公開または非公開の別のコマンドが発行された場合に処理されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-317">The un-publish and publish-pend operations will be processed on service restart or if another publish or un-publish command is issued.</span></span> <span data-ttu-id="2e742-318">後者の場合、仮想アプリケーションが使用されている場合は、仮想アプリケーションは保留状態のままになります。</span><span class="sxs-lookup"><span data-stu-id="2e742-318">In the latter case, if the virtual application is in-use otherwise, the virtual application will remain in a pending state.</span></span> <span data-ttu-id="2e742-319">グローバルに公開されたパッケージの場合、再起動 (またはサービスの再起動) が必要になることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="2e742-319">For globally published packages, a restart (or service restart) often needed.</span></span>

<span data-ttu-id="2e742-320">非永続的な環境では、保留中の操作が処理される可能性は低くなります。</span><span class="sxs-lookup"><span data-stu-id="2e742-320">In a non-persistent environment, it is unlikely these pended operations will be processed.</span></span> <span data-ttu-id="2e742-321">タスクなどの保留中の操作は、[ **HKEY] \ _CURRENT \ _USER**  \\  **Software**  \\  **Microsoft**  \\  **AppV**  \\  **Client**  \\  **pendingtasks**] の下にキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="2e742-321">The pended operations, for example tasks are captured under **HKEY\_CURRENT\_USER** \\ **Software** \\ **Microsoft** \\ **AppV** \\ **Client** \\ **PendingTasks**.</span></span> <span data-ttu-id="2e742-322">この場所は UPM ソリューションによって保持されますが、ログオン前に環境に適用されていない場合は処理されません。</span><span class="sxs-lookup"><span data-stu-id="2e742-322">Although this location is persisted by the UPM solution, if it is not applied to the environment prior to log on, it will not be processed.</span></span>

### <a href="" id="bkmk-evdi"></a><span data-ttu-id="2e742-323">パフォーマンス最適化のチューニングを通じて VDI のエクスペリエンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="2e742-323">Enhancing the VDI Experience through Performance Optimization Tuning</span></span>

<span data-ttu-id="2e742-324">以下のセクションでは、パフォーマンスを向上させるために環境を最適化するときに役立つ可能性がある Microsoft のドキュメントとダウンロードに関する情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="2e742-324">The following section contains lists with information about Microsoft documentation and downloads that may be useful when optimizing your environment for performance.</span></span>

**<span data-ttu-id="2e742-325">.NET NGEN ブログとスクリプト (強くお勧めします)</span><span class="sxs-lookup"><span data-stu-id="2e742-325">.NET NGEN Blog and Script (Highly Recommended)</span></span>**

<span data-ttu-id="2e742-326">NGEN テクノロジについて</span><span class="sxs-lookup"><span data-stu-id="2e742-326">About NGEN technology</span></span>

-   [<span data-ttu-id="2e742-327">NGEN 最適化の速度を向上させる方法</span><span class="sxs-lookup"><span data-stu-id="2e742-327">How to speed up NGEN optimization</span></span>](https://blogs.msdn.com/b/dotnet/archive/2013/08/06/wondering-why-mscorsvw-exe-has-high-cpu-usage-you-can-speed-it-up.aspx)

-   [<span data-ttu-id="2e742-328">スクリプト</span><span class="sxs-lookup"><span data-stu-id="2e742-328">Script</span></span>](https://aka.ms/DrainNGenQueue)

**<span data-ttu-id="2e742-329">Windows サーバーおよびサーバーの役割</span><span class="sxs-lookup"><span data-stu-id="2e742-329">Windows Server and Server Roles</span></span>**

<span data-ttu-id="2e742-330">のサーバーパフォーマンスのチューニングガイドライン</span><span class="sxs-lookup"><span data-stu-id="2e742-330">Server Performance Tuning Guidelines for</span></span>

-   [<span data-ttu-id="2e742-331">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="2e742-331">Microsoft Windows Server 2012 R2</span></span>](https://msdn.microsoft.com/library/windows/hardware/dn529133.aspx)

-   [<span data-ttu-id="2e742-332">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="2e742-332">Microsoft Windows Server 2012</span></span>](https://download.microsoft.com/download/0/0/B/00BE76AF-D340-4759-8ECD-C80BC53B6231/performance-tuning-guidelines-windows-server-2012.docx)

-   [<span data-ttu-id="2e742-333">Microsoft Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="2e742-333">Microsoft Windows Server 2008 R2</span></span>](https://download.microsoft.com/download/6/B/2/6B2EBD3A-302E-4553-AC00-9885BBF31E21/Perf-tun-srv-R2.docx)

**<span data-ttu-id="2e742-334">サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="2e742-334">Server Roles</span></span>**

-   [<span data-ttu-id="2e742-335">リモートデスクトップ仮想化ホスト</span><span class="sxs-lookup"><span data-stu-id="2e742-335">Remote Desktop Virtualization Host</span></span>](https://msdn.microsoft.com/library/windows/hardware/dn567643.aspx)

-   [<span data-ttu-id="2e742-336">リモートデスクトップセッションホスト</span><span class="sxs-lookup"><span data-stu-id="2e742-336">Remote Desktop Session Host</span></span>](https://msdn.microsoft.com/library/windows/hardware/dn567648.aspx)

-   [<span data-ttu-id="2e742-337">IIS の関連度: App-v の管理、公開、レポート Web サービス</span><span class="sxs-lookup"><span data-stu-id="2e742-337">IIS Relevance: App-V Management, Publishing, Reporting Web Services</span></span>](https://msdn.microsoft.com/library/windows/hardware/dn567678.aspx)

-   [<span data-ttu-id="2e742-338">ファイルサーバー (SMB) の関連度: アプリ V のコンテンツストレージと SCS モードでの配信に使用されている場合</span><span class="sxs-lookup"><span data-stu-id="2e742-338">File Server (SMB) Relevance: If used for App-V Content Storage and Delivery in SCS Mode</span></span>](https://technet.microsoft.com/library/jj134210.aspx)

**<span data-ttu-id="2e742-339">Windows クライアント (ゲスト OS) のパフォーマンスのチューニングガイダンス</span><span class="sxs-lookup"><span data-stu-id="2e742-339">Windows Client (Guest OS) Performance Tuning Guidance</span></span>**

-   [<span data-ttu-id="2e742-340">Microsoft Windows 7</span><span class="sxs-lookup"><span data-stu-id="2e742-340">Microsoft Windows 7</span></span>](https://download.microsoft.com/download/E/5/7/E5783D68-160B-4366-8387-114FC3E45EB4/Performance Tuning Guidelines for Windows 7 Desktop Virtualization v1.9.docx)

-   [<span data-ttu-id="2e742-341">最適化スクリプト: (Microsoft サポートによって提供されます)</span><span class="sxs-lookup"><span data-stu-id="2e742-341">Optimization Script: (Provided by Microsoft Support)</span></span>](https://blogs.technet.com/b/jeff_stokes/archive/2012/10/15/the-microsoft-premier-field-engineer-pfe-view-on-virtual-desktop-vdi-density.aspx)

-   [<span data-ttu-id="2e742-342">Microsoft Windows 8</span><span class="sxs-lookup"><span data-stu-id="2e742-342">Microsoft Windows 8</span></span>](https://download.microsoft.com/download/6/0/1/601D7797-A063-4FA7-A2E5-74519B57C2B4/Windows_8_VDI_Image_Client_Tuning_Guide.pdf)

-   [<span data-ttu-id="2e742-343">最適化スクリプト: (Microsoft サポートによって提供されます)</span><span class="sxs-lookup"><span data-stu-id="2e742-343">Optimization Script: (Provided by Microsoft Support)</span></span>](https://blogs.technet.com/b/jeff_stokes/archive/2013/04/09/hot-off-the-presses-get-it-now-the-windows-8-vdi-optimization-script-courtesy-of-pfe.aspx)

## <span data-ttu-id="2e742-344">公開のパフォーマンスのためにパッケージを最適化するためのシーケンス手順</span><span class="sxs-lookup"><span data-stu-id="2e742-344">Sequencing Steps to Optimize Packages for Publishing Performance</span></span>


<span data-ttu-id="2e742-345">App-v 5.0 と App-v 5.0 SP2 では、それぞれのリリースで重要な価値を提供しています。</span><span class="sxs-lookup"><span data-stu-id="2e742-345">App-V 5.0 and App-V 5.0 SP2 provide significant value in their respective releases.</span></span> <span data-ttu-id="2e742-346">新しいシナリオや新しい顧客の展開シナリオを可能にするいくつかの機能があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-346">Several features facilitate new scenarios or enabled new customer deployment scenarios.</span></span> <span data-ttu-id="2e742-347">以下の機能は、発行操作と起動操作のパフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-347">These following features can impact the performance of the publishing and launch operations.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2e742-348">ステップ</span><span class="sxs-lookup"><span data-stu-id="2e742-348">Step</span></span></th>
<th align="left"><span data-ttu-id="2e742-349">考慮事項</span><span class="sxs-lookup"><span data-stu-id="2e742-349">Consideration</span></span></th>
<th align="left"><span data-ttu-id="2e742-350">メリット</span><span class="sxs-lookup"><span data-stu-id="2e742-350">Benefits</span></span></th>
<th align="left"><span data-ttu-id="2e742-351">オフ</span><span class="sxs-lookup"><span data-stu-id="2e742-351">Tradeoffs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2e742-352">機能ブロック 1 (FB1、プライマリ FB とも呼ばれます) がありません</span><span class="sxs-lookup"><span data-stu-id="2e742-352">No Feature Block 1 (FB1, also known as Primary FB)</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e742-353">FB1 なしは、アプリがすぐに起動し、ストリームフォールトを発生させることを意味します (アプリケーションはファイル、DLL を要求し、起動時にネットワーク経由でプルダウンする必要があります)。ネットワークの制限事項がある場合は、FB1 は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2e742-353">No FB1 means the application will launch immediately and stream fault (application requires file, DLL and must pull down over the network) during launch.If there are network limitations, FB1 will:</span></span></p>
<ul>
<li><p><span data-ttu-id="2e742-354">初めてアプリケーションを起動するときに使用されるストリームフォールトとネットワーク帯域幅の数を減らします。</span><span class="sxs-lookup"><span data-stu-id="2e742-354">Reduce the number of stream faults and network bandwidth used when you launch an application for the first time.</span></span></p></li>
<li><p><span data-ttu-id="2e742-355">FB1 全体がストリーミングされるまで、起動を遅らせます。</span><span class="sxs-lookup"><span data-stu-id="2e742-355">Delay launch until the entire FB1 has been streamed.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="2e742-356">ストリームの障害が発生すると、起動時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-356">Stream faulting decreases the launch time.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e742-357">FB1 が構成されている仮想アプリケーションパッケージは、再順序付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-357">Virtual application packages with FB1 configured will need to be re-sequenced.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="2e742-358">FB1 を削除する</span><span class="sxs-lookup"><span data-stu-id="2e742-358">Removing FB1</span></span>

<span data-ttu-id="2e742-359">FB1 を削除しても、元のアプリケーションインストーラーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="2e742-359">Removing FB1 does not require the original application installer.</span></span> <span data-ttu-id="2e742-360">次の手順を完了したら、sequencer を実行しているコンピューターをクリーンなスナップショットに戻すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2e742-360">After completing the following steps, it is suggested that you revert the computer running the sequencer to a clean snapshot.</span></span>

<span data-ttu-id="2e742-361">**SEQUENCER UI** -新しい仮想アプリケーションパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="2e742-361">**Sequencer UI** - Create a New Virtual Application Package.</span></span>

1.  <span data-ttu-id="2e742-362">シーケンスの手順を完了して、ストリーミングをカスタマイズし &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="2e742-362">Complete the sequencing steps up to Customize -&gt; Streaming.</span></span>

2.  <span data-ttu-id="2e742-363">ストリーミング手順では、[**低速または信頼性の低いネットワーク経由の展開用にパッケージを最適化する**] を選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="2e742-363">At the Streaming step, do not select **Optimize the package for deployment over slow or unreliable network**.</span></span>

3.  <span data-ttu-id="2e742-364">必要に応じて、[**ターゲット OS**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="2e742-364">If desired, move on to **Target OS**.</span></span>

**<span data-ttu-id="2e742-365">既存の仮想アプリケーションパッケージを変更する</span><span class="sxs-lookup"><span data-stu-id="2e742-365">Modify an Existing Virtual Application Package</span></span>**

1.  <span data-ttu-id="2e742-366">シーケンス手順を完了してストリーミングを行います。</span><span class="sxs-lookup"><span data-stu-id="2e742-366">Complete the sequencing steps up to Streaming.</span></span>

2.  <span data-ttu-id="2e742-367">[パッケージを**低速または信頼性の低いネットワーク経由で展開するために最適化**する] を選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="2e742-367">Do not select **Optimize the package for deployment over a slow or unreliable network**.</span></span>

3.  <span data-ttu-id="2e742-368">「**パッケージの作成**」に移動します。</span><span class="sxs-lookup"><span data-stu-id="2e742-368">Move to **Create Package**.</span></span>

<span data-ttu-id="2e742-369">**PowerShell** -既存の仮想アプリケーションパッケージを更新します。</span><span class="sxs-lookup"><span data-stu-id="2e742-369">**PowerShell** - Update an Existing Virtual Application Package.</span></span>

1.  <span data-ttu-id="2e742-370">管理者特権の PowerShell セッションを開きます。</span><span class="sxs-lookup"><span data-stu-id="2e742-370">Open an elevated PowerShell session.</span></span>

2.  <span data-ttu-id="2e742-371">インポート-モジュール**appvsequencer**。</span><span class="sxs-lookup"><span data-stu-id="2e742-371">Import-module **appvsequencer**.</span></span>

3.  <span data-ttu-id="2e742-372">**更新-AppvSequencerPackage**  - **AppvPackageFilePath**</span><span class="sxs-lookup"><span data-stu-id="2e742-372">**Update-AppvSequencerPackage** - **AppvPackageFilePath**</span></span>

    <span data-ttu-id="2e742-373">"C:\\Packages\\MyPackage.appv"-インストーラ</span><span class="sxs-lookup"><span data-stu-id="2e742-373">"C:\\Packages\\MyPackage.appv" -Installer</span></span>

    <span data-ttu-id="2e742-374">"C:\\PackageInstall\\PackageUpgrade.exe empty.exe"-OutputPath</span><span class="sxs-lookup"><span data-stu-id="2e742-374">"C:\\PackageInstall\\PackageUpgrade.exe empty.exe" -OutputPath</span></span>

    <span data-ttu-id="2e742-375">"C:\\UpgradedPackages"</span><span class="sxs-lookup"><span data-stu-id="2e742-375">"C:\\UpgradedPackages"</span></span>

    **<span data-ttu-id="2e742-376">注</span><span class="sxs-lookup"><span data-stu-id="2e742-376">Note</span></span>**  
    <span data-ttu-id="2e742-377">このコマンドレットを実行するには、実行可能ファイル (.exe) またはバッチファイル (.bat) が必要です。</span><span class="sxs-lookup"><span data-stu-id="2e742-377">This cmdlet requires an executable (.exe) or batch file (.bat).</span></span> <span data-ttu-id="2e742-378">空の (何もしない) 実行可能ファイルまたはバッチファイルを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-378">You must provide an empty (does nothing) executable or batch file.</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2e742-379">ステップ</span><span class="sxs-lookup"><span data-stu-id="2e742-379">Step</span></span></th>
<th align="left"><span data-ttu-id="2e742-380">考慮事項</span><span class="sxs-lookup"><span data-stu-id="2e742-380">Considerations</span></span></th>
<th align="left"><span data-ttu-id="2e742-381">メリット</span><span class="sxs-lookup"><span data-stu-id="2e742-381">Benefits</span></span></th>
<th align="left"><span data-ttu-id="2e742-382">オフ</span><span class="sxs-lookup"><span data-stu-id="2e742-382">Tradeoffs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2e742-383">公開時に SXS はインストールされません (インストール前の SxS アセンブリ)</span><span class="sxs-lookup"><span data-stu-id="2e742-383">No SXS Install at Publish (Pre-Install SxS assemblies)</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e742-384">仮想アプリケーションパッケージの順序を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2e742-384">Virtual Application packages do not need to be re-sequenced.</span></span> <span data-ttu-id="2e742-385">SxS アセンブリは仮想アプリケーションパッケージに残しておくことができます。</span><span class="sxs-lookup"><span data-stu-id="2e742-385">SxS Assemblies can remain in the virtual application package.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e742-386">SxS アセンブリの依存関係は、公開時にはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="2e742-386">The SxS Assembly dependencies will not install at publishing time.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e742-387">SxS アセンブリの依存関係が事前にインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-387">SxS Assembly dependencies must be pre-installed.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="2e742-388">Sequencer での新しい仮想アプリケーションパッケージの作成</span><span class="sxs-lookup"><span data-stu-id="2e742-388">Creating a new virtual application package on the sequencer</span></span>

<span data-ttu-id="2e742-389">Sequencer の監視中に、プログラムのインストールの一部として SxS アセンブリ (VC + + ランタイムなど) がインストールされている場合、SxS アセンブリは自動的に検出され、パッケージに含まれます。</span><span class="sxs-lookup"><span data-stu-id="2e742-389">If, during sequencer monitoring, an SxS Assembly (such as a VC++ Runtime) is installed as part of an application’s installation, SxS Assembly will be automatically detected and included in the package.</span></span> <span data-ttu-id="2e742-390">管理者に通知され、SxS アセンブリを除外するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-390">The administrator will be notified and will have the option to exclude the SxS Assembly.</span></span>

<span data-ttu-id="2e742-391">**クライアント側**:</span><span class="sxs-lookup"><span data-stu-id="2e742-391">**Client Side**:</span></span>

<span data-ttu-id="2e742-392">仮想アプリケーションパッケージを公開する場合、必要な SxS の依存関係が既にインストールされているかどうかが、App-v 5.0 SP2 クライアントによって検出されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-392">When publishing a virtual application package, the App-V 5.0 SP2 Client will detect if a required SxS dependency is already installed.</span></span> <span data-ttu-id="2e742-393">この依存関係がコンピューターで利用できず、パッケージに含まれている場合は、従来の Windows インストーラー (.**msi**) SxS アセンブリのインストールが開始されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-393">If the dependency is unavailable on the computer and it is included in the package, a traditional Windows Installer (.**msi**) installation of the SxS assembly will be initiated.</span></span> <span data-ttu-id="2e742-394">前に説明したように、クライアントを実行しているコンピューターに依存関係をインストールするだけで、Windows Installer (.msi) のインストールが行われないようにします。</span><span class="sxs-lookup"><span data-stu-id="2e742-394">As previously documented, simply install the dependency on the computer running the client to ensure that the Windows Installer (.msi) installation will not occur.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2e742-395">ステップ</span><span class="sxs-lookup"><span data-stu-id="2e742-395">Step</span></span></th>
<th align="left"><span data-ttu-id="2e742-396">考慮事項</span><span class="sxs-lookup"><span data-stu-id="2e742-396">Considerations</span></span></th>
<th align="left"><span data-ttu-id="2e742-397">メリット</span><span class="sxs-lookup"><span data-stu-id="2e742-397">Benefits</span></span></th>
<th align="left"><span data-ttu-id="2e742-398">オフ</span><span class="sxs-lookup"><span data-stu-id="2e742-398">Tradeoffs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2e742-399">動的構成ファイルを選択的に使用する</span><span class="sxs-lookup"><span data-stu-id="2e742-399">Selectively Employ Dynamic Configuration files</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e742-400">App-v 5.0 クライアントは、これらの動的構成ファイルを解析して処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-400">The App-V 5.0 client must parse and process these Dynamic Configuration files.</span></span></p>
<p><span data-ttu-id="2e742-401">ファイルのサイズと複雑さ (スクリプトの実行、VREG の包含/除外) について認識している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-401">Be conscious of size and complexity (script execution, VREG inclusions/exclusions) of the file.</span></span></p>
<p><span data-ttu-id="2e742-402">多くの仮想アプリケーションパッケージには、ユーザーまたはコンピューター固有の動的構成ファイルが既に含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-402">Numerous virtual application packages may already have User- or computer–specific dynamic configurations files.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e742-403">これらのファイルが選択されているかどうかによって、公開時間が向上します。</span><span class="sxs-lookup"><span data-stu-id="2e742-403">Publishing times will improve if these files are used selectively or not at all.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e742-404">仮想アプリケーションパッケージは、個別に再構成する必要があります。または、App-v server 管理コンソールを使用して、関連付けられた動的構成ファイルを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-404">Virtual application packages would need to be reconfigured individually or via the App-V server management console to remove associated Dynamic Configuration files.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="2e742-405">Powershell を使用した動的構成の無効化</span><span class="sxs-lookup"><span data-stu-id="2e742-405">Disabling a Dynamic Configuration using Powershell</span></span>

-   <span data-ttu-id="2e742-406">既に公開されているパッケージ `Set-AppVClientPackage –Name Myapp –Path c:\Packages\Apps\MyApp.appv` の場合は、</span><span class="sxs-lookup"><span data-stu-id="2e742-406">For already published packages, you can use `Set-AppVClientPackage –Name Myapp –Path c:\Packages\Apps\MyApp.appv` without</span></span>

    <span data-ttu-id="2e742-407">**-Dynamicdeploymentconfiguration**パラメーター</span><span class="sxs-lookup"><span data-stu-id="2e742-407">**-DynamicDeploymentConfiguration** parameter</span></span>

-   <span data-ttu-id="2e742-408">同様に、を使って新しいパッケージを追加する場合は、 `Add-AppVClientPackage –Path c:\Packages\Apps\MyApp.appv`</span><span class="sxs-lookup"><span data-stu-id="2e742-408">Similarly, when adding new packages using `Add-AppVClientPackage –Path c:\Packages\Apps\MyApp.appv`, do not use the</span></span>

    <span data-ttu-id="2e742-409">**-Dynamicdeploymentconfiguration**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="2e742-409">**-DynamicDeploymentConfiguration** parameter.</span></span>

<span data-ttu-id="2e742-410">動的な構成を適用する方法については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e742-410">For documentation on How to Apply a Dynamic Configuration, see:</span></span>

-   [<span data-ttu-id="2e742-411">PowerShell を使用してユーザー構成ファイルを適用する方法</span><span class="sxs-lookup"><span data-stu-id="2e742-411">How to Apply the User Configuration File by Using PowerShell</span></span>](how-to-apply-the-user-configuration-file-by-using-powershell.md)

-   [<span data-ttu-id="2e742-412">PowerShell を使用して展開構成ファイルを適用する方法</span><span class="sxs-lookup"><span data-stu-id="2e742-412">How to Apply the Deployment Configuration File by Using PowerShell</span></span>](how-to-apply-the-deployment-configuration-file-by-using-powershell.md)

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2e742-413">ステップ</span><span class="sxs-lookup"><span data-stu-id="2e742-413">Step</span></span></th>
<th align="left"><span data-ttu-id="2e742-414">考慮事項</span><span class="sxs-lookup"><span data-stu-id="2e742-414">Considerations</span></span></th>
<th align="left"><span data-ttu-id="2e742-415">メリット</span><span class="sxs-lookup"><span data-stu-id="2e742-415">Benefits</span></span></th>
<th align="left"><span data-ttu-id="2e742-416">オフ</span><span class="sxs-lookup"><span data-stu-id="2e742-416">Tradeoffs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2e742-417">パッケージのライフサイクル中の同期スクリプト実行のアカウント。</span><span class="sxs-lookup"><span data-stu-id="2e742-417">Account for Synchronous Script Execution during Package Lifecycle.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e742-418">スクリプトの資料がパッケージに埋め込まれている場合、Add (Powershell) の速度が大幅に低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="2e742-418">If script collateral is embedded in the package, Add (Powershell) may be significantly slower.</span></span></p>
<p><span data-ttu-id="2e742-419">仮想アプリケーションの起動時 (StartVirtualEnvironment、StartProcess)、または Add + Publish の間にスクリプトを実行すると、このようなライフサイクル操作の1つ以上で、認識されるパフォーマンスに影響します。</span><span class="sxs-lookup"><span data-stu-id="2e742-419">Running of scripts during virtual application launch (StartVirtualEnvironment, StartProcess) and/or Add+Publish will impact the perceived performance during one or more of these lifecycle operations.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e742-420">非同期 (非ブロッキング) スクリプトを使用すると、ライフサイクルの操作が効率的に完了します。</span><span class="sxs-lookup"><span data-stu-id="2e742-420">Use of Asynchronous (Non-Blocking) Scripts will ensure that the lifecycle operations complete efficiently.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e742-421">この手順には、関連付けられた動的構成ファイルを持ち、同期されている参照と実行を行う埋め込みスクリプトの資料を含む、すべての仮想アプリケーションパッケージについての実用的な知識が必要です。</span><span class="sxs-lookup"><span data-stu-id="2e742-421">This step requires working knowledge of all virtual application packages with embedded script collateral, which have associated dynamic configurations files and which reference and run scripts synchronously.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2e742-422">パッケージから余分な仮想フォントを削除します。</span><span class="sxs-lookup"><span data-stu-id="2e742-422">Remove Extraneous Virtual Fonts from Package.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e742-423">App-v 製品チームによって調査されたアプリケーションの大半は、少数のフォント (通常は20未満) を含んでいました。</span><span class="sxs-lookup"><span data-stu-id="2e742-423">The majority of applications investigated by the App-V product team contained a small number of fonts, typically fewer than 20.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e742-424">仮想フォントは、公開の更新のパフォーマンスに影響します。</span><span class="sxs-lookup"><span data-stu-id="2e742-424">Virtual Fonts impact publishing refresh performance.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e742-425">目的のフォントは、ネイティブで有効またはインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e742-425">Desired fonts will need to be enabled/installed natively.</span></span> <span data-ttu-id="2e742-426">手順については、「フォントをインストールまたはアンインストールする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e742-426">For instructions, see Install or uninstall fonts.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="2e742-427">パッケージ内に存在する仮想フォントを確認する</span><span class="sxs-lookup"><span data-stu-id="2e742-427">Determining what virtual fonts exist in the package</span></span>

-   <span data-ttu-id="2e742-428">パッケージのコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2e742-428">Make a copy of the package.</span></span>

-   <span data-ttu-id="2e742-429">パッケージ \ _copy を Package\_copy.zip に名前変更する</span><span class="sxs-lookup"><span data-stu-id="2e742-429">Rename Package\_copy.appv to Package\_copy.zip</span></span>

-   <span data-ttu-id="2e742-430">AppxManifest.xml を開き、次の内容を探します。</span><span class="sxs-lookup"><span data-stu-id="2e742-430">Open AppxManifest.xml and locate the following:</span></span>

    <span data-ttu-id="2e742-431">&lt;appv: 拡張機能カテゴリ = "AppV. Fonts"&gt;</span><span class="sxs-lookup"><span data-stu-id="2e742-431">&lt;appv:Extension Category="AppV.Fonts"&gt;</span></span>

    <span data-ttu-id="2e742-432">&lt;appv: フォント&gt;</span><span class="sxs-lookup"><span data-stu-id="2e742-432">&lt;appv:Fonts&gt;</span></span>

    <span data-ttu-id="2e742-433">&lt;appv: Font Path = "\ [{Fonts} \] \\private\\CalibriL.ttf" DelayLoad = "true" &gt; &lt; /Appv: font&gt;</span><span class="sxs-lookup"><span data-stu-id="2e742-433">&lt;appv:Font Path="\[{Fonts}\]\\private\\CalibriL.ttf" DelayLoad="true"&gt;&lt;/appv:Font&gt;</span></span>

    **<span data-ttu-id="2e742-434">注</span><span class="sxs-lookup"><span data-stu-id="2e742-434">Note</span></span>**  
    <span data-ttu-id="2e742-435">**Delayload**としてマークされているフォントがある場合は、最初の起動に影響しません。</span><span class="sxs-lookup"><span data-stu-id="2e742-435">If there are fonts marked as **DelayLoad**, those will not impact first launch.</span></span>



~~~
&lt;/appv:Fonts&gt;
~~~

### <span data-ttu-id="2e742-436">パッケージから仮想フォントを除外する</span><span class="sxs-lookup"><span data-stu-id="2e742-436">Excluding virtual fonts from the package</span></span>

<span data-ttu-id="2e742-437">ユーザーのスコープに最適な動的構成ファイルを使用します。コンピューター上のすべてのユーザーに対する展開構成、特定のユーザーまたはユーザー向けのユーザー構成。</span><span class="sxs-lookup"><span data-stu-id="2e742-437">Use the dynamic configuration file that best suits the user scope – deployment configuration for all users on computer, user configuration for specific user or users.</span></span>

-   <span data-ttu-id="2e742-438">展開またはユーザー構成でフォントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="2e742-438">Disable fonts with the deployment or user configuration.</span></span>

<span data-ttu-id="2e742-439">フォント</span><span class="sxs-lookup"><span data-stu-id="2e742-439">Fonts</span></span>

--&gt;

<span data-ttu-id="2e742-440">&lt;フォント有効 = "false"/&gt;</span><span class="sxs-lookup"><span data-stu-id="2e742-440">&lt;Fonts Enabled="false" /&gt;</span></span>

<span data-ttu-id="2e742-441">&lt;!--</span><span class="sxs-lookup"><span data-stu-id="2e742-441">&lt;!--</span></span>

## <a href="" id="bkmk-terms1"></a> <span data-ttu-id="2e742-442">App-v 5.0 のパフォーマンスガイダンスの用語</span><span class="sxs-lookup"><span data-stu-id="2e742-442">App-V 5.0 Performance Guidance Terminology</span></span>


<span data-ttu-id="2e742-443">次の用語は、App-v 5.0 パフォーマンスの最適化に関する概念とアクションを記述するときに使われます。</span><span class="sxs-lookup"><span data-stu-id="2e742-443">The following terms are used when describing concepts and actions related to App-V 5.0 performance optimization.</span></span>

-   <span data-ttu-id="2e742-444">**複雑さ**–事前構成 (**AppvClientPackage**) または統合 (**Publish-AppvClientPackage**) の実行中にパフォーマンスに影響を与える可能性のある1つ以上のパッケージの特性を指します。</span><span class="sxs-lookup"><span data-stu-id="2e742-444">**Complexity** – Refers to the one or more package characteristics that may impact performance during pre-configure (**Add-AppvClientPackage**) or integration (**Publish-AppvClientPackage**).</span></span> <span data-ttu-id="2e742-445">特性の例としては、マニフェストのサイズ、仮想フォントの数、ファイルの数などがあります。</span><span class="sxs-lookup"><span data-stu-id="2e742-445">Some example characteristics are: manifest size, number of virtual fonts, number of files.</span></span>

-   <span data-ttu-id="2e742-446">**統合の解除**–ユーザー統合を削除します</span><span class="sxs-lookup"><span data-stu-id="2e742-446">**De-Integrate** – Removes the user integrations</span></span>

-   <span data-ttu-id="2e742-447">**再統合**–ユーザー統合を適用します。</span><span class="sxs-lookup"><span data-stu-id="2e742-447">**Re-Integrate** – Applies the user integrations.</span></span>

-   <span data-ttu-id="2e742-448">**非永続的なプール**–仮想環境がログインするたびに実行されるコンピューターを作成します。</span><span class="sxs-lookup"><span data-stu-id="2e742-448">**Non-Persistent, Pooled** – Creates a computer running a virtual environment each time they log in.</span></span>

-   <span data-ttu-id="2e742-449">**永続的なパーソナル**–すべてのログインで同じ仮想環境を実行しているコンピューター。</span><span class="sxs-lookup"><span data-stu-id="2e742-449">**Persistent, Personal** – A computer running a virtual environment that remains the same for every login.</span></span>

-   <span data-ttu-id="2e742-450">**ステートフル**-このドキュメントでは、ユーザーの統合がセッション間で保持され、ユーザー環境管理テクノロジが永続的でない RDSH または VDI と併用されていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2e742-450">**Stateful** - For this document, implies that user integrations are persisted between sessions and a user environment management technology is used in conjunction with non-persistent RDSH or VDI.</span></span>

-   <span data-ttu-id="2e742-451">**ステートレス**–セッション間でユーザーの状態が保持されないシナリオを表します。</span><span class="sxs-lookup"><span data-stu-id="2e742-451">**Stateless** – Represents a scenario when no user state is persisted between sessions.</span></span>

-   <span data-ttu-id="2e742-452">**トリガー** – (またはネイティブアクショントリガー)。</span><span class="sxs-lookup"><span data-stu-id="2e742-452">**Trigger** – (or Native Action Triggers).</span></span> <span data-ttu-id="2e742-453">UPM では、これらの種類のトリガーを使って、監視または同期操作を開始します。</span><span class="sxs-lookup"><span data-stu-id="2e742-453">UPM uses these types of triggers to initiate monitoring or synchronization operations.</span></span>

-   <span data-ttu-id="2e742-454">**ユーザーエクスペリエンス**-app-v 5.0 のコンテキストでは、ユーザーエクスペリエンス quantitatively は次の部分の合計です。</span><span class="sxs-lookup"><span data-stu-id="2e742-454">**User Experience** - In the context of App-V 5.0, the user experience, quantitatively, is the sum of the following parts:</span></span>

    -   <span data-ttu-id="2e742-455">ユーザーがログインを開始した時点から、ユーザーがデスクトップを操作できる場合。</span><span class="sxs-lookup"><span data-stu-id="2e742-455">From the point that users initiate a log-in to when they are able to manipulate the desktop.</span></span>

    -   <span data-ttu-id="2e742-456">App-v 5.0 full server インフラストラクチャを使用しているときに、デスクトップが対話できるポイント (PowerShell 用語では、同期) が開始されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-456">From the point where the desktop can be interacted with to the point a publishing refresh begins (in PowerShell terms, sync) when using the App-V 5.0 full server infrastructure.</span></span> <span data-ttu-id="2e742-457">スタンドアロンインスタンスでは、 **AppVClientPackage**と**Publish AppVClientPackage Powershell**コマンドが開始されたときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="2e742-457">In standalone instances, it is when the **Add-AppVClientPackage** and **Publish-AppVClientPackage Powershell** commands are initiated.</span></span>

    -   <span data-ttu-id="2e742-458">公開の更新の開始から完了まで。</span><span class="sxs-lookup"><span data-stu-id="2e742-458">From start to completion of the publishing refresh.</span></span> <span data-ttu-id="2e742-459">スタンドアロンインスタンスの場合、これは最初に最後に公開された仮想アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="2e742-459">In standalone instances, this is the first to last virtual application published.</span></span>

    -   <span data-ttu-id="2e742-460">仮想アプリケーションをショートカットから起動できる場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="2e742-460">From the point where the virtual application is available to launch from a shortcut.</span></span> <span data-ttu-id="2e742-461">または、ファイルの種類の関連付けが登録されている時点から、指定された仮想アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="2e742-461">Alternatively, it is from the point at which the file type association is registered and will launch a specified virtual application.</span></span>

-   <span data-ttu-id="2e742-462">**ユーザープロファイル管理**–環境に関連付けられているユーザーコンポーネントを管理するための制御された構造のアプローチです。</span><span class="sxs-lookup"><span data-stu-id="2e742-462">**User Profile Management** – The controlled and structured approach to managing user components associated with the environment.</span></span> <span data-ttu-id="2e742-463">たとえば、ユーザープロファイル、基本設定とポリシーの管理、アプリケーションコントロール、アプリケーションの展開などです。</span><span class="sxs-lookup"><span data-stu-id="2e742-463">For example, user profiles, preference and policy management, application control and application deployment.</span></span> <span data-ttu-id="2e742-464">スクリプトまたはサードパーティのソリューションを使用して、必要に応じて環境を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="2e742-464">You can use scripting or third-party solutions configure the environment as needed.</span></span>






## <span data-ttu-id="2e742-465">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2e742-465">Related topics</span></span>


[<span data-ttu-id="2e742-466">Microsoft Application Virtualization 5.0 管理者ガイド</span><span class="sxs-lookup"><span data-stu-id="2e742-466">Microsoft Application Virtualization 5.0 Administrator's Guide</span></span>](microsoft-application-virtualization-50-administrators-guide.md)









