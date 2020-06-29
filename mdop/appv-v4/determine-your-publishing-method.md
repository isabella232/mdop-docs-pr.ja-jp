---
title: 公開方法の選択
description: 公開方法の選択
author: dansimp
ms.assetid: 1f2d0d39-5d65-457a-b826-4f45b00c8c85
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9a6b19b12c28ab67e3250909cb32ddb8419f399a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821677"
---
# <span data-ttu-id="39eac-103">公開方法の選択</span><span class="sxs-lookup"><span data-stu-id="39eac-103">Determine Your Publishing Method</span></span>


<span data-ttu-id="39eac-104">Application Virtualization Sequencer を使用してアプリケーションをシーケンスした後は、そのアプリケーションをユーザーに*公開*する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39eac-104">After you sequence an application by using the Application Virtualization Sequencer, you need to *publish* that application to your users.</span></span> <span data-ttu-id="39eac-105">アプリケーションの公開は、アイコン、パッケージ定義情報、およびアプリケーションの仮想化クライアントがインストールされている各コンピューターへのコンテンツソースの場所の配信で構成されます。</span><span class="sxs-lookup"><span data-stu-id="39eac-105">Publishing the application consists of delivering the icons, package definition information, and content source location to each computer where the Application Virtualization Client has been installed.</span></span> <span data-ttu-id="39eac-106">次の表では、電子ソフトウェア配布 (ESD) システムを使用してアプリケーションの仮想化を展開するときにサポートされる発行方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="39eac-106">The following table describes publishing methods that are supported when you deploy Application Virtualization by using an electronic software distribution (ESD) system.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="39eac-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="39eac-107">Method</span></span></th>
<th align="left"><span data-ttu-id="39eac-108">長所</span><span class="sxs-lookup"><span data-stu-id="39eac-108">Advantages</span></span></th>
<th align="left"><span data-ttu-id="39eac-109">短所</span><span class="sxs-lookup"><span data-stu-id="39eac-109">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="39eac-110">シーケンス中に Windows インストーラーファイルを生成し、スタンドアロンソリューションとして作成します。</span><span class="sxs-lookup"><span data-stu-id="39eac-110">Generate a Windows Installer file during sequencing, as a stand-alone solution.</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="39eac-111">簡単に使うことができます。</span><span class="sxs-lookup"><span data-stu-id="39eac-111">Very simple to use.</span></span></p></li>
<li><p><span data-ttu-id="39eac-112">パッケージは各コンピューター上のキャッシュにローカルに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="39eac-112">Package loaded into cache locally on each computer.</span></span></p></li>
<li><p><span data-ttu-id="39eac-113">ユーザーに表示されるアイコン。</span><span class="sxs-lookup"><span data-stu-id="39eac-113">Icons displayed to user.</span></span></p></li>
<li><p><span data-ttu-id="39eac-114">従来のソフトウェア展開と似ています。</span><span class="sxs-lookup"><span data-stu-id="39eac-114">Similar to traditional software deployment.</span></span></p></li>
<li><p><span data-ttu-id="39eac-115">ストリーミングサーバは不要。</span><span class="sxs-lookup"><span data-stu-id="39eac-115">No need for streaming servers.</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="39eac-116">コンピューター上のパッケージコンテンツの場所を柔軟に指定することはできません。すべてのコンピューター上の同じ場所にあります。</span><span class="sxs-lookup"><span data-stu-id="39eac-116">No flexibility in location of package contents on computers—same location on all computers.</span></span></p></li>
<li><p><span data-ttu-id="39eac-117">アプリケーションを削除するには、[プログラムの追加と削除] を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39eac-117">Must use only Add/Remove Programs or msiexec to remove applications.</span></span></p></li>
<li><p><span data-ttu-id="39eac-118">パッケージの更新に必要な新しいバージョンの削除と置き換え。</span><span class="sxs-lookup"><span data-stu-id="39eac-118">Removal and replacement with new version required for package updating.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="39eac-119">シーケンス中に、MODE、LOAD、OVERRIDEURL コマンドラインプロパティとパッケージマニフェストと共に使用される Windows インストーラーファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="39eac-119">Generate a Windows Installer file during sequencing, used with MODE, LOAD, and OVERRIDEURL command-line properties and the package manifest.</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="39eac-120">使いやすく、柔軟性が向上しました。</span><span class="sxs-lookup"><span data-stu-id="39eac-120">Simple to use but with added flexibility.</span></span></p></li>
<li><p><span data-ttu-id="39eac-121">ユーザーに表示されるアイコン。</span><span class="sxs-lookup"><span data-stu-id="39eac-121">Icons displayed to user.</span></span></p></li>
<li><p><span data-ttu-id="39eac-122">アプリケーションを含む SFT ファイルをストリーミングソースの場所に配置し、クライアントがその場所を使用するように構成することができます。</span><span class="sxs-lookup"><span data-stu-id="39eac-122">SFT file containing the applications can be placed on a streaming source location, with clients configured to use that location.</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="39eac-123">限定された柔軟性: パッケージコンテンツの場所のみを実行時に制御できます。</span><span class="sxs-lookup"><span data-stu-id="39eac-123">Limited flexibility—only the location of the package content can be controlled at run time.</span></span></p></li>
<li><p><span data-ttu-id="39eac-124">アプリケーションを削除するには、[プログラムの追加と削除] を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39eac-124">Must use only Add/Remove Programs or msiexec to remove the application.</span></span></p></li>
<li><p><span data-ttu-id="39eac-125">ストリーミングサーバーを使用しない限り、パッケージの更新に必要な新しいバージョンの削除と置き換え。</span><span class="sxs-lookup"><span data-stu-id="39eac-125">Removal and replacement with new version required for package updating, unless using streaming server.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="39eac-126">SFTMIME コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="39eac-126">Run SFTMIME commands.</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="39eac-127">完全な柔軟性—すべてのパッケージ管理機能を完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="39eac-127">Complete flexibility—full control of all package management functions.</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="39eac-128">ESD システムで使用するためにコマンドをスクリプト化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39eac-128">Commands must be scripted for use with the ESD system.</span></span></p></li>
<li><p><span data-ttu-id="39eac-129">コマンドは、各コンピューターで正しい順序で実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="39eac-129">Commands must be run on each computer in correct sequence.</span></span></p></li>
<li><p><span data-ttu-id="39eac-130">コマンド言語と慎重な計画について詳しく理解している。</span><span class="sxs-lookup"><span data-stu-id="39eac-130">Detailed understanding of command language and careful planning required.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="39eac-131">これらの発行方法の使い方については、「[クライアントで仮想アプリケーションを公開する方法](how-to-publish-a-virtual-application-on-the-client.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39eac-131">For more information about using these publishing methods, see [How to Publish a Virtual Application on the Client](how-to-publish-a-virtual-application-on-the-client.md).</span></span>

## <span data-ttu-id="39eac-132">関連トピック</span><span class="sxs-lookup"><span data-stu-id="39eac-132">Related topics</span></span>


[<span data-ttu-id="39eac-133">ストリーミング方法の選択</span><span class="sxs-lookup"><span data-stu-id="39eac-133">Determine Your Streaming Method</span></span>](determine-your-streaming-method.md)

[<span data-ttu-id="39eac-134">電子ソフトウェア配布ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="39eac-134">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="39eac-135">電子ソフトウェア配布ベースのシナリオ概要</span><span class="sxs-lookup"><span data-stu-id="39eac-135">Electronic Software Distribution-Based Scenario Overview</span></span>](electronic-software-distribution-based-scenario-overview.md)

[<span data-ttu-id="39eac-136">クライアントで仮想アプリケーションを公開する方法</span><span class="sxs-lookup"><span data-stu-id="39eac-136">How to Publish a Virtual Application on the Client</span></span>](how-to-publish-a-virtual-application-on-the-client.md)

[<span data-ttu-id="39eac-137">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="39eac-137">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





