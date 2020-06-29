---
title: APP-V サーバーの公開メタデータの表示
description: APP-V サーバーの公開メタデータの表示
author: dansimp
ms.assetid: d5fa9eb5-647c-478d-8a4d-0ecda018bce6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 97c59301678280febe23b8061c08033a88ae49c7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813234"
---
# <span data-ttu-id="cab64-103">APP-V サーバーの公開メタデータの表示</span><span class="sxs-lookup"><span data-stu-id="cab64-103">Viewing App-V Server Publishing Metadata</span></span>


<span data-ttu-id="cab64-104">公開に関連する問題を解決するために役立つ公開メタデータを表示するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="cab64-104">Use this procedure to view publishing metadata, which can help you resolve publishing-related issues.</span></span> <span data-ttu-id="cab64-105">この手順を使用するには、App-v Management server を使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="cab64-105">You must be using the App-V Management server to use this procedure.</span></span>

<span data-ttu-id="cab64-106">この記事には、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cab64-106">This article contains the following information:</span></span>

-   [<span data-ttu-id="cab64-107">公開メタデータを表示するための app-v 5.1 の要件</span><span class="sxs-lookup"><span data-stu-id="cab64-107">App-V 5.1 requirements for viewing publishing metadata</span></span>](#bkmk-51-reqs-pub-meta)

-   [<span data-ttu-id="cab64-108">公開メタデータの表示に使う構文</span><span class="sxs-lookup"><span data-stu-id="cab64-108">Syntax to use for viewing publishing metadata</span></span>](#bkmk-syntax-view-pub-meta)

-   [<span data-ttu-id="cab64-109">クライアントのオペレーティングシステムとバージョンのクエリ値</span><span class="sxs-lookup"><span data-stu-id="cab64-109">Query values for client operating system and version</span></span>](#bkmk-values-query-pub-meta)

-   [<span data-ttu-id="cab64-110">発行メタデータの定義</span><span class="sxs-lookup"><span data-stu-id="cab64-110">Definition of publishing metadata</span></span>](#bkmk-whatis-pub-metadata)

## <a href="" id="bkmk-51-reqs-pub-meta"></a><span data-ttu-id="cab64-111">公開メタデータを表示するための app-v 5.1 の要件</span><span class="sxs-lookup"><span data-stu-id="cab64-111">App-V 5.1 requirements for viewing publishing metadata</span></span>


<span data-ttu-id="cab64-112">App-v 5.1 では、メタデータのために App-v パブリッシングサーバーにクエリを実行するときに、アドレスに次の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cab64-112">In App-V 5.1, you must provide the following values in the address when you query the App-V Publishing server for metadata:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cab64-113">値</span><span class="sxs-lookup"><span data-stu-id="cab64-113">Value</span></span></th>
<th align="left"><span data-ttu-id="cab64-114">追加情報</span><span class="sxs-lookup"><span data-stu-id="cab64-114">Additional details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="cab64-115">ClientVersion</span><span class="sxs-lookup"><span data-stu-id="cab64-115">ClientVersion</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="cab64-116"><strong>クエリから clientversion パラメーターを省略した場合 </strong> 、メタデータには、APP-V 5.0 SP3 で新しく追加された機能が除外されます。</span><span class="sxs-lookup"><span data-stu-id="cab64-116">If you omit the <strong>ClientVersion</strong> parameter from the query, the metadata excludes the features that were new in App-V 5.0 SP3.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="cab64-117">ClientOS</span><span class="sxs-lookup"><span data-stu-id="cab64-117">ClientOS</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="cab64-118">この値を指定する必要があるのは、パッケージの順序を指定するときに特定のクライアントオペレーティングシステムを選択する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="cab64-118">You have to provide this value only if you select specific client operating systems when you sequence the package.</span></span> <span data-ttu-id="cab64-119">既定の (すべてのオペレーティングシステム) を選択した場合は、この値をクエリで指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="cab64-119">If you select the default (all operating systems), do not specify this value in the query.</span></span></p>
<p><span data-ttu-id="cab64-120"><strong>クエリから clientos パラメーターを省略した場合 </strong> 、任意のオペレーティングシステムをサポートするように指定されたパッケージのみがメタデータに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cab64-120">If you omit the <strong>ClientOS</strong> parameter from the query, only the packages that were sequenced to support any operating system appear in the metadata.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-syntax-view-pub-meta"></a><span data-ttu-id="cab64-121">公開メタデータを表示するためのクエリ構文</span><span class="sxs-lookup"><span data-stu-id="cab64-121">Query syntax for viewing publishing metadata</span></span>


<span data-ttu-id="cab64-122">次の表は、構文とクエリの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="cab64-122">The following table provides the syntax and query examples.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cab64-123">App-v のバージョン</span><span class="sxs-lookup"><span data-stu-id="cab64-123">Version of App-V</span></span></th>
<th align="left"><span data-ttu-id="cab64-124">クエリ構文</span><span class="sxs-lookup"><span data-stu-id="cab64-124">Query syntax</span></span></th>
<th align="left"><span data-ttu-id="cab64-125">パラメーターの説明</span><span class="sxs-lookup"><span data-stu-id="cab64-125">Parameter descriptions</span></span></th>
<th align="left"><span data-ttu-id="cab64-126">例</span><span class="sxs-lookup"><span data-stu-id="cab64-126">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cab64-127">App-v 5.0 SP3 およびアプリ-V 5.1</span><span class="sxs-lookup"><span data-stu-id="cab64-127">App-V 5.0 SP3 and App-V 5.1</span></span></p></td>
<td align="left"><p><code>http://&lt;PubServer&gt;:&lt;Publishing Port#&gt;/?ClientVersion=&lt;AppvClientVersion&gt;&amp;ClientOS=&lt;OSStringValue&gt;</code></p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cab64-128">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cab64-128">Parameter</span></span></th>
<th align="left"><span data-ttu-id="cab64-129">説明</span><span class="sxs-lookup"><span data-stu-id="cab64-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cab64-130">&lt;PubServer&gt;</span><span class="sxs-lookup"><span data-stu-id="cab64-130">&lt;PubServer&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-131">App-v 発行サーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="cab64-131">Name of the App-V Publishing server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cab64-132">&lt;公開ポート#&gt;</span><span class="sxs-lookup"><span data-stu-id="cab64-132">&lt;Publishing Port#&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-133">発行サーバーの構成時に定義した App-v 発行サーバーへのポート。</span><span class="sxs-lookup"><span data-stu-id="cab64-133">Port to the App-V Publishing server, which you defined when you configured the Publishing server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cab64-134">ClientVersion = &lt; AppvClientVersion&gt;</span><span class="sxs-lookup"><span data-stu-id="cab64-134">ClientVersion=&lt;AppvClientVersion&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-135">App-v クライアントのバージョン。</span><span class="sxs-lookup"><span data-stu-id="cab64-135">Version of the App-V client.</span></span> <span data-ttu-id="cab64-136">使用する適切な値については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cab64-136">Refer to the following table for the correct value to use.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cab64-137">ClientOS = &lt; osstringvalue&gt;</span><span class="sxs-lookup"><span data-stu-id="cab64-137">ClientOS=&lt;OSStringValue&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-138">App-v クライアントを実行しているコンピューターのオペレーティングシステム。</span><span class="sxs-lookup"><span data-stu-id="cab64-138">Operating system of the computer that is running the App-V client.</span></span> <span data-ttu-id="cab64-139">使用する適切な値については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cab64-139">Refer to the following table for the correct value to use.</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p>
<p><span data-ttu-id="cab64-140">公開サーバーの名前とポート番号 (http:// &lt; pubserver &gt; : &lt; publishing port #) を app-v クライアントから取得するには &gt; 、 <strong> APPVPUBLISHINGSERVER PowerShell コマンドレットの URL 構成を確認し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="cab64-140">To get the name of the Publishing server and the port number (http://&lt;PubServer&gt;:&lt;Publishing Port#&gt;) from the App-V Client, look at the URL configuration of the <strong>Get-AppvPublishingServer</strong> PowerShell cmdlet.</span></span></p></td>
<td align="left"><p><code><a href="http://pubsvr01:2718/?clientversion=5.0.10066.0&amp;clientos=WindowsClient_6.2_x64" data-raw-source="http://pubsvr01:2718/?clientversion=5.0.10066.0&amp;amp;clientos=WindowsClient_6.2_x64">http://pubsvr01:2718/?clientversion=5.0.10066.0&amp;clientos=WindowsClient_6.2_x64</a></code></p>
<p><span data-ttu-id="cab64-141">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="cab64-141">In the example:</span></span></p>
<ul>
<li><p><span data-ttu-id="cab64-142">"Pubsvr01" という名前の Windows Server 2012 R2 は、発行サービスをホストします。</span><span class="sxs-lookup"><span data-stu-id="cab64-142">A Windows Server 2012 R2 named “pubsvr01” hosts the Publishing service.</span></span></p></li>
<li><p><span data-ttu-id="cab64-143">Windows クライアントは Windows 8.1 64 ビットです。</span><span class="sxs-lookup"><span data-stu-id="cab64-143">The Windows client is Windows 8.1 64-bit.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cab64-144">App-V 5.0 ~ app-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="cab64-144">App-V 5.0 through App-V 5.0 SP2</span></span></p></td>
<td align="left"><p><code>http://&lt;PubServer&gt;:&lt;Publishing Port#&gt;/ </code></p>
<div class="alert">
<strong><span data-ttu-id="cab64-145">注</span><span class="sxs-lookup"><span data-stu-id="cab64-145">Note</span></span></strong><br/><p><strong><span data-ttu-id="cab64-146">ClientVersion </strong> と <strong> clientos </strong> は、app-v 5.0 SP3 および app-v 5.1 でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="cab64-146">ClientVersion</strong> and <strong>ClientOS</strong> are supported only in App-V 5.0 SP3 and App-V 5.1.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="cab64-147">App-v 5.0 SP3 および App-v 5.1 の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cab64-147">See the information for App-V 5.0 SP3 and App-V 5.1.</span></span></p></td>
<td align="left"><p><code><a href="http://pubsvr01:2718" data-raw-source="http://pubsvr01:2718">http://pubsvr01:2718</a></code></p>
<p><span data-ttu-id="cab64-148">この例では、"pubsvr01" という名前の Windows Server 2012 R2 は、管理サービスと発行サービスをホストしています。</span><span class="sxs-lookup"><span data-stu-id="cab64-148">In the example, A Windows Server 2012 R2 named “pubsvr01” hosts the Management and Publishing services.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-values-query-pub-meta"></a><span data-ttu-id="cab64-149">クライアントのオペレーティングシステムとバージョンのクエリ値</span><span class="sxs-lookup"><span data-stu-id="cab64-149">Query values for client operating system and version</span></span>


<span data-ttu-id="cab64-150">公開メタデータクエリで、使用しているクライアントのオペレーティングシステムとバージョンに対応する文字列値を入力します。</span><span class="sxs-lookup"><span data-stu-id="cab64-150">In your publishing metadata query, enter the string values that correspond to the client operating system and version that you’re using.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cab64-151">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="cab64-151">Operating system</span></span></th>
<th align="left"><span data-ttu-id="cab64-152">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="cab64-152">Architecture</span></span></th>
<th align="left"><span data-ttu-id="cab64-153">操作文字列文字列値</span><span class="sxs-lookup"><span data-stu-id="cab64-153">Operating string string value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cab64-154">Windows 10</span><span class="sxs-lookup"><span data-stu-id="cab64-154">Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-155">64 ビット</span><span class="sxs-lookup"><span data-stu-id="cab64-155">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-156">WindowsClient_10 0_x64</span><span class="sxs-lookup"><span data-stu-id="cab64-156">WindowsClient_10.0_x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cab64-157">Windows 10</span><span class="sxs-lookup"><span data-stu-id="cab64-157">Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-158">32 ビット</span><span class="sxs-lookup"><span data-stu-id="cab64-158">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-159">WindowsClient_10 0_x86</span><span class="sxs-lookup"><span data-stu-id="cab64-159">WindowsClient_10.0_x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cab64-160">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="cab64-160">Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-161">64 ビット</span><span class="sxs-lookup"><span data-stu-id="cab64-161">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-162">WindowsClient_6 2_x64</span><span class="sxs-lookup"><span data-stu-id="cab64-162">WindowsClient_6.2_x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cab64-163">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="cab64-163">Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-164">32 ビット</span><span class="sxs-lookup"><span data-stu-id="cab64-164">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-165">WindowsClient_6 2_x86</span><span class="sxs-lookup"><span data-stu-id="cab64-165">WindowsClient_6.2_x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cab64-166">Windows 8</span><span class="sxs-lookup"><span data-stu-id="cab64-166">Windows 8</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-167">64 ビット</span><span class="sxs-lookup"><span data-stu-id="cab64-167">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-168">WindowsClient_6 2_x64</span><span class="sxs-lookup"><span data-stu-id="cab64-168">WindowsClient_6.2_x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cab64-169">Windows 8</span><span class="sxs-lookup"><span data-stu-id="cab64-169">Windows 8</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-170">32 ビット</span><span class="sxs-lookup"><span data-stu-id="cab64-170">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-171">WindowsClient_6 2_x86</span><span class="sxs-lookup"><span data-stu-id="cab64-171">WindowsClient_6.2_x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cab64-172">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="cab64-172">Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-173">64 ビット</span><span class="sxs-lookup"><span data-stu-id="cab64-173">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-174">WindowsServer_6 2_x64</span><span class="sxs-lookup"><span data-stu-id="cab64-174">WindowsServer_6.2_x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cab64-175">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="cab64-175">Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-176">32 ビット</span><span class="sxs-lookup"><span data-stu-id="cab64-176">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-177">WindowsServer_6 2_x86</span><span class="sxs-lookup"><span data-stu-id="cab64-177">WindowsServer_6.2_x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cab64-178">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="cab64-178">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-179">64 ビット</span><span class="sxs-lookup"><span data-stu-id="cab64-179">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-180">WindowsServer_6 2_x64</span><span class="sxs-lookup"><span data-stu-id="cab64-180">WindowsServer_6.2_x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cab64-181">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="cab64-181">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-182">32 ビット</span><span class="sxs-lookup"><span data-stu-id="cab64-182">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-183">WindowsServer_6 2_x86</span><span class="sxs-lookup"><span data-stu-id="cab64-183">WindowsServer_6.2_x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cab64-184">Windows 7</span><span class="sxs-lookup"><span data-stu-id="cab64-184">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-185">64 ビット</span><span class="sxs-lookup"><span data-stu-id="cab64-185">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-186">WindowsClient_6 1_x64</span><span class="sxs-lookup"><span data-stu-id="cab64-186">WindowsClient_6.1_x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cab64-187">Windows 7</span><span class="sxs-lookup"><span data-stu-id="cab64-187">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-188">32 ビット</span><span class="sxs-lookup"><span data-stu-id="cab64-188">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-189">WindowsClient_6 1_x86</span><span class="sxs-lookup"><span data-stu-id="cab64-189">WindowsClient_6.1_x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cab64-190">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="cab64-190">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-191">64 ビット</span><span class="sxs-lookup"><span data-stu-id="cab64-191">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-192">WindowsServer_6 1_x64</span><span class="sxs-lookup"><span data-stu-id="cab64-192">WindowsServer_6.1_x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cab64-193">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="cab64-193">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-194">32 ビット</span><span class="sxs-lookup"><span data-stu-id="cab64-194">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="cab64-195">WindowsServer_6 1_x86</span><span class="sxs-lookup"><span data-stu-id="cab64-195">WindowsServer_6.1_x86</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-whatis-pub-metadata"></a><span data-ttu-id="cab64-196">発行メタデータの定義</span><span class="sxs-lookup"><span data-stu-id="cab64-196">Definition of publishing metadata</span></span>


<span data-ttu-id="cab64-197">App-v クライアントを実行しているコンピューターにパッケージが公開されると、そのコンピューターにメタデータが送信され、どのパッケージと接続グループが公開されているかが示されます。</span><span class="sxs-lookup"><span data-stu-id="cab64-197">When packages are published to a computer that is running the App-V client, metadata is sent to that computer indicating which packages and connection groups are being published.</span></span> <span data-ttu-id="cab64-198">App-v クライアントでは、次の2つの個別の要求が行われます。</span><span class="sxs-lookup"><span data-stu-id="cab64-198">The App-V Client makes two separate requests for the following:</span></span>

-   <span data-ttu-id="cab64-199">クライアントコンピューターに付属しているパッケージと接続グループ。</span><span class="sxs-lookup"><span data-stu-id="cab64-199">Packages and connection groups that are entitled to the client computer.</span></span>

-   <span data-ttu-id="cab64-200">現在のユーザーに与えられているパッケージと接続グループ。</span><span class="sxs-lookup"><span data-stu-id="cab64-200">Packages and connection groups that are entitled to the current user.</span></span>

<span data-ttu-id="cab64-201">発行サーバーは、管理サーバーと通信して、要求者が利用できるパッケージと接続グループを決定します。</span><span class="sxs-lookup"><span data-stu-id="cab64-201">The Publishing server communicates with the Management server to determine which packages and connection groups are available to the requester.</span></span> <span data-ttu-id="cab64-202">メタデータを生成するには、発行サーバーが管理サーバーに登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cab64-202">The Publishing server must be registered with the Management server in order for the metadata to be generated.</span></span>

<span data-ttu-id="cab64-203">インターネットブラウザーでは、特定のユーザーまたはコンピューターのコンテキストに含まれるクエリを使用して、各要求のメタデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="cab64-203">You can view the metadata for each request in an Internet browser by using a query that is in the context of the specific user or computer.</span></span>






## <span data-ttu-id="cab64-204">関連トピック</span><span class="sxs-lookup"><span data-stu-id="cab64-204">Related topics</span></span>


[<span data-ttu-id="cab64-205">App-V 5.1 テクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="cab64-205">Technical Reference for App-V 5.1</span></span>](technical-reference-for-app-v-51.md)









