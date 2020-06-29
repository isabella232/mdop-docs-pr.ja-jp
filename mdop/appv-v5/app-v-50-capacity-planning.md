---
title: App-V 5.0 容量計画
description: App-V 5.0 容量計画
author: dansimp
ms.assetid: 56f48b00-cd91-4280-9481-5372a0e2e792
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9e828457a286f6f686c227a935828679514d87ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814851"
---
# <span data-ttu-id="8037b-103">App-V 5.0 容量計画</span><span class="sxs-lookup"><span data-stu-id="8037b-103">App-V 5.0 Capacity Planning</span></span>


<span data-ttu-id="8037b-104">以下の推奨事項をベースラインとして使用して、組織の App-v 5.0 インフラストラクチャに適したキャパシティ計画情報を決定することができます。</span><span class="sxs-lookup"><span data-stu-id="8037b-104">The following recommendations can be used as a baseline to help determine capacity planning information that is appropriate to your organization’s App-V 5.0 infrastructure.</span></span>

<span data-ttu-id="8037b-105">**重要** このセクションの情報は、アプリ-V 5.0 の展開を計画するための一般的なガイドとしてのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="8037b-105">**Important** Use the information in this section only as a general guide for planning your App-V 5.0 deployment.</span></span> <span data-ttu-id="8037b-106">システム容量の要件は、ハードウェアとアプリケーション環境の具体的な詳細によって異なります。</span><span class="sxs-lookup"><span data-stu-id="8037b-106">Your system capacity requirements will depend on the specific details of your hardware and application environment.</span></span> <span data-ttu-id="8037b-107">また、このドキュメントに示されているパフォーマンス数値は例であり、結果は異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8037b-107">Additionally, the performance numbers displayed in this document are examples and your results may vary.</span></span>

 

## <span data-ttu-id="8037b-108">プロジェクトのスコープを決定する</span><span class="sxs-lookup"><span data-stu-id="8037b-108">Determine the Project Scope</span></span>


<span data-ttu-id="8037b-109">App-v 5.0 インフラストラクチャを設計する前に、プロジェクトのスコープを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8037b-109">Before you design the App-V 5.0 infrastructure, you must determine the project’s scope.</span></span> <span data-ttu-id="8037b-110">スコープは、どのアプリケーションを実質的に使用できるか、またターゲットユーザーとその場所を特定するかを決定することで構成されます。</span><span class="sxs-lookup"><span data-stu-id="8037b-110">The scope consists of determining which applications will be available virtually and to also identify the target users, and their locations.</span></span> <span data-ttu-id="8037b-111">この情報は、実装する必要がある App-v 5.0 インフラストラクチャの種類を決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8037b-111">This information will help determine what type of App-V 5.0 infrastructure should be implemented.</span></span> <span data-ttu-id="8037b-112">プロジェクトの範囲に関する決定は、組織の特定のニーズに基づいて行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8037b-112">Decisions about the scope of the project must be based on the specific needs of your organization.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8037b-113">タスク</span><span class="sxs-lookup"><span data-stu-id="8037b-113">Task</span></span></th>
<th align="left"><span data-ttu-id="8037b-114">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8037b-114">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8037b-115">アプリケーションの範囲を決定する</span><span class="sxs-lookup"><span data-stu-id="8037b-115">Determine Application Scope</span></span></p></td>
<td align="left"><p><span data-ttu-id="8037b-116">仮想化するアプリケーションによっては、App-v 5.0 インフラストラクチャはさまざまな方法で設定できます。</span><span class="sxs-lookup"><span data-stu-id="8037b-116">Depending on the applications to be virtualized, the App-V 5.0 infrastructure can be set up in different ways.</span></span> <span data-ttu-id="8037b-117">最初のタスクは、仮想化するアプリケーションを定義することです。</span><span class="sxs-lookup"><span data-stu-id="8037b-117">The first task is to define what applications you want to virtualize.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8037b-118">場所の範囲を決定する</span><span class="sxs-lookup"><span data-stu-id="8037b-118">Determine Location Scope</span></span></p></td>
<td align="left"><p><span data-ttu-id="8037b-119">場所の範囲は、仮想化されたアプリケーションを実行する予定の物理的な場所 (たとえば、企業全体または特定の地理的な場所) を指します。</span><span class="sxs-lookup"><span data-stu-id="8037b-119">Location scope refers to the physical locations (for example, enterprise-wide or a specific geographic location) where you plan to run the virtualized applications.</span></span> <span data-ttu-id="8037b-120">仮想アプリケーションを実行するユーザー人口 (単一の部署など) を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="8037b-120">It can also refer to the user population (for example, a single department) who will run the virtual applications.</span></span> <span data-ttu-id="8037b-121">接続パスと、仮想化されたアプリケーションを使用しているユーザーの数および WAN のリンク速度を使用しているユーザーの数について、利用可能な帯域幅を含むネットワークマップを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8037b-121">You should obtain a network map that includes the connection paths as well as available bandwidth to each location and the number of users using virtualized applications and the WAN link speed.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="8037b-122">必要な App-v 5.0 インフラストラクチャを決定する</span><span class="sxs-lookup"><span data-stu-id="8037b-122">Determine Which App-V 5.0 Infrastructure is Required</span></span>


<span data-ttu-id="8037b-123">**重要** 次の2つのモデルでは、仮想アプリケーションを実行する予定のコンピューターに App-v 5.0 クライアントがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8037b-123">**Important** Both of the following models require the App-V 5.0 client to be installed on the computer where you plan to run virtual applications.</span></span>

<span data-ttu-id="8037b-124">また、Microsoft Systems Center Configuration Manager などの電子ソフトウェア配布 (ESD) ソリューションを使用して、App-v 5.0 環境を管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="8037b-124">You can also manage your App-V 5.0 environment using an Electronic Software Distribution (ESD) solution such as Microsoft Systems Center Configuration Manager.</span></span> <span data-ttu-id="8037b-125">詳細については、「[電子ソフトウェア配布 (ESD) を使用した app-v 5.0 パッケージの展開](deploying-app-v-50-packages-by-using-electronic-software-distribution--esd-.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8037b-125">For more information see [Deploying App-V 5.0 Packages by Using Electronic Software Distribution (ESD)](deploying-app-v-50-packages-by-using-electronic-software-distribution--esd-.md).</span></span>

 

-   <span data-ttu-id="8037b-126">**スタンド**アロンモデル-スタンドアロンモデルでは、ストリームを使わずに配布するために仮想アプリケーションを Windows Installer 対応にすることができます。</span><span class="sxs-lookup"><span data-stu-id="8037b-126">**Standalone Model** - The standalone model allows virtual applications to be Windows Installer-enabled for distribution without streaming.</span></span> <span data-ttu-id="8037b-127">スタンドアロンモードの App V 5.0 は、sequencer とクライアントで構成されます。追加のコンポーネントは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8037b-127">App-V 5.0 in Standalone Mode consists of the sequencer and the client; no additional components are required.</span></span> <span data-ttu-id="8037b-128">アプリケーションは、シーケンスと呼ばれるプロセスを使用して仮想化の準備を行います。</span><span class="sxs-lookup"><span data-stu-id="8037b-128">Applications are prepared for virtualization using a process called sequencing.</span></span> <span data-ttu-id="8037b-129">詳細については、「 [app-v 5.0 Sequencer とクライアント展開の計画](planning-for-the-app-v-50-sequencer-and-client-deployment.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8037b-129">For more information see, [Planning for the App-V 5.0 Sequencer and Client Deployment](planning-for-the-app-v-50-sequencer-and-client-deployment.md).</span></span> <span data-ttu-id="8037b-130">単体モデルは、次のシナリオでお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8037b-130">The stand-alone model is recommended for the following scenarios:</span></span>

    -   <span data-ttu-id="8037b-131">App-v 5.0 インフラストラクチャに接続できないリモートユーザーが切断されている。</span><span class="sxs-lookup"><span data-stu-id="8037b-131">With disconnected remote users who cannot connect to the App-V 5.0 infrastructure.</span></span>

    -   <span data-ttu-id="8037b-132">Configuration Manager 2012 などのソフトウェア管理システムを実行している場合。</span><span class="sxs-lookup"><span data-stu-id="8037b-132">When you are running a software management system, such as Configuration Manager 2012.</span></span>

    -   <span data-ttu-id="8037b-133">ネットワーク帯域幅の制限により、電子ソフトウェアの配布が禁止されている場合。</span><span class="sxs-lookup"><span data-stu-id="8037b-133">When network bandwidth limitations inhibit electronic software distribution.</span></span>

-   <span data-ttu-id="8037b-134">**完全**なインフラストラクチャモデル-完全なインフラストラクチャモデルでは、ソフトウェアの配布、管理、レポート機能が提供されます。また、ネットワーク経由のアプリケーションのストリーミングも含まれます。</span><span class="sxs-lookup"><span data-stu-id="8037b-134">**Full Infrastructure Model** - The full infrastructure model provides for software distribution, management, and reporting capabilities; it also includes the streaming of applications across the network.</span></span> <span data-ttu-id="8037b-135">App-v 5.0 の完全なインフラストラクチャモデルは、1つ以上の App-v 5.0 management サーバーで構成されます。</span><span class="sxs-lookup"><span data-stu-id="8037b-135">The App-V 5.0 Full Infrastructure Model consists of one or more App-V 5.0 management servers.</span></span> <span data-ttu-id="8037b-136">管理サーバーを使用して、アプリケーションをすべてのクライアントに公開することができます。</span><span class="sxs-lookup"><span data-stu-id="8037b-136">The Management Server can be used to publish applications to all clients.</span></span> <span data-ttu-id="8037b-137">公開プロセスでは、仮想アプリケーションのアイコンとショートカットがターゲットコンピューターに配置されます。</span><span class="sxs-lookup"><span data-stu-id="8037b-137">The publishing process places the virtual application icons and shortcuts on the target computer.</span></span> <span data-ttu-id="8037b-138">また、ローカルユーザーにアプリケーションをストリームすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8037b-138">It can also stream applications to local users.</span></span> <span data-ttu-id="8037b-139">管理サーバーのインストールの詳細については、「 [app-v 5.0 サーバー展開の計画](planning-for-the-app-v-50-server-deployment.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8037b-139">For more information about installing the management server see, [Planning for the App-V 5.0 Server Deployment](planning-for-the-app-v-50-server-deployment.md).</span></span> <span data-ttu-id="8037b-140">次のシナリオでは、完全なインフラストラクチャモデルをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8037b-140">The full infrastructure model is recommended for the following scenarios:</span></span>

    <span data-ttu-id="8037b-141">**重要** アプリ-V 5.0 の完全なインフラストラクチャモデルでは、構成データを保存するために Microsoft SQL Server が必要です。</span><span class="sxs-lookup"><span data-stu-id="8037b-141">**Important** The App-V 5.0 full infrastructure model requires Microsoft SQL Server to store configuration data.</span></span> <span data-ttu-id="8037b-142">詳細については[、「app-v 5.0 でサポートされている構成](app-v-50-supported-configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8037b-142">For more information see [App-V 5.0 Supported Configurations](app-v-50-supported-configurations.md).</span></span>

     

    -   <span data-ttu-id="8037b-143">管理サーバーを使用して、アプリケーションをターゲットコンピューターに発行する場合。</span><span class="sxs-lookup"><span data-stu-id="8037b-143">When you want to use the Management Server to publish the application to target computers.</span></span>

    -   <span data-ttu-id="8037b-144">ターゲットコンピューターへのアプリケーションの迅速なプロビジョニング。</span><span class="sxs-lookup"><span data-stu-id="8037b-144">For rapid provisioning of applications to target computers.</span></span>

    -   <span data-ttu-id="8037b-145">App-v 5.0 レポートを使用する場合。</span><span class="sxs-lookup"><span data-stu-id="8037b-145">When you want to use App-V 5.0 reporting.</span></span>

## <span data-ttu-id="8037b-146">エンドツーエンドサーバーのサイズ変更のガイダンス</span><span class="sxs-lookup"><span data-stu-id="8037b-146">End-to-end Server Sizing Guidance</span></span>


<span data-ttu-id="8037b-147">以下のセクションでは、エンドツーエンドの App-v 5.0 のサイズと計画について説明します。</span><span class="sxs-lookup"><span data-stu-id="8037b-147">The following section provides information about end-to-end App-V 5.0 sizing and planning.</span></span> <span data-ttu-id="8037b-148">詳細については、後続のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8037b-148">For more specific information, refer to the subsequent sections.</span></span>

<span data-ttu-id="8037b-149">**注** クライアントでのラウンドトリップの応答時間は、アプリ-V 5.0 クライアントを実行しているコンピューターが、発行サーバーから正常な通知を受信するまでにかかった時間です。</span><span class="sxs-lookup"><span data-stu-id="8037b-149">**Note** Round trip response time on the client is the time taken by the computer running the App-V 5.0 client to receive a successful notification from the publishing server.</span></span> <span data-ttu-id="8037b-150">発行サーバーのラウンドトリップ応答時間は、発行サーバーを実行しているコンピューターが管理サーバーから正常なパッケージメタデータ更新を受信するまでの時間です。</span><span class="sxs-lookup"><span data-stu-id="8037b-150">Round trip response time on the publishing server is the time taken by the computer running the publishing server to receive a successful package metadata update from the management server.</span></span>

 

-   <span data-ttu-id="8037b-151">2万クライアントは、1つのパブリッシングサーバーをターゲットとして、適切なラウンドトリップ時間でパッケージの更新を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="8037b-151">20,000 clients can target a single publishing server to obtain the package refreshes in an acceptable round trip time.</span></span> <span data-ttu-id="8037b-152">( &lt; 3 秒)</span><span class="sxs-lookup"><span data-stu-id="8037b-152">(&lt;3 seconds)</span></span>

-   <span data-ttu-id="8037b-153">1つの管理サーバーでは、許容可能なラウンドトリップ時間内のパッケージのメタデータの更新について、最大50の発行サーバーをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="8037b-153">A single management server can support up to 50 publishing servers for package metadata refreshes in an acceptable round trip time.</span></span> <span data-ttu-id="8037b-154">( &lt; 5 秒)</span><span class="sxs-lookup"><span data-stu-id="8037b-154">(&lt;5 seconds)</span></span>

## <a href="" id="---------app-v-5-0-management-server-capacity-planning-recommendations"></a> <span data-ttu-id="8037b-155">App-v 5.0 Management Server キャパシティ計画の推奨事項</span><span class="sxs-lookup"><span data-stu-id="8037b-155">App-V 5.0 Management Server Capacity Planning Recommendations</span></span>


<span data-ttu-id="8037b-156">App-v 5.0 公開サーバーでは、パッケージの更新要求とパッケージ更新の応答に管理サーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="8037b-156">The App-V 5.0 publishing servers require the management server for package refresh requests and package refresh responses.</span></span> <span data-ttu-id="8037b-157">その後、管理サーバーはその情報を管理データベースに送信して情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="8037b-157">The management server then sends the information to the management database to retrieve information.</span></span> <span data-ttu-id="8037b-158">App-v 5.0 management server でサポートされている構成の詳細については[、「app-v 5.0 でサポートされている構成](app-v-50-supported-configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8037b-158">For more information about App-V 5.0 management server supported configurations see [App-V 5.0 Supported Configurations](app-v-50-supported-configurations.md).</span></span>

<span data-ttu-id="8037b-159">**注** App-v 5.0 公開サーバーの既定の更新時刻は、10分です。</span><span class="sxs-lookup"><span data-stu-id="8037b-159">**Note** The default refresh time on the App-V 5.0 publishing server is ten minutes.</span></span>

 

<span data-ttu-id="8037b-160">複数の同時発行サーバーから1つの管理サーバーに連絡してパッケージのメタデータを更新すると、次の3つの要因が、発行サーバーのラウンドトリップ応答時間に影響します。</span><span class="sxs-lookup"><span data-stu-id="8037b-160">When multiple simultaneous publishing servers contact a single management server for package metadata refreshes, the following three factors influence the round trip response time on the publishing server:</span></span>

1.  <span data-ttu-id="8037b-161">同時要求を行っている発行サーバーの数です。</span><span class="sxs-lookup"><span data-stu-id="8037b-161">Number of publishing servers making simultaneous requests.</span></span>

2.  <span data-ttu-id="8037b-162">管理サーバーで構成されている接続グループの数。</span><span class="sxs-lookup"><span data-stu-id="8037b-162">Number of connection groups configured on the management server.</span></span>

3.  <span data-ttu-id="8037b-163">管理サーバーで構成されているアクセスグループの数。</span><span class="sxs-lookup"><span data-stu-id="8037b-163">Number of access groups configured on the management server.</span></span>

<span data-ttu-id="8037b-164">次の表は、往復時間に影響を与える各要素についての詳細を示しています。</span><span class="sxs-lookup"><span data-stu-id="8037b-164">The following table displays more information about each factor that impacts round trip time.</span></span>

<span data-ttu-id="8037b-165">**注** ラウンドトリップの応答時間は、管理サーバーから正常にパッケージのメタデータ更新を受信するために、App-v 5.0 発行サーバーを実行しているコンピューターによって行われた時間です。</span><span class="sxs-lookup"><span data-stu-id="8037b-165">**Note** Round trip response time is the time taken by the computer running the App-V 5.0 publishing server to receive a successful package metadata update from the management server.</span></span>

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8037b-166">ラウンドトリップの応答時間に影響を与える要因</span><span class="sxs-lookup"><span data-stu-id="8037b-166">Factors impacting round trip response time</span></span></th>
<th align="left"><span data-ttu-id="8037b-167">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8037b-167">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8037b-168">パッケージのメタデータの更新を同時に要求する発行サーバーの数です。</span><span class="sxs-lookup"><span data-stu-id="8037b-168">The number of publishing servers simultaneously requesting package metadata refreshes.</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-169">1つの管理サーバーは、同時に公開するために、最大320の発行サーバーに応答できます。</span><span class="sxs-lookup"><span data-stu-id="8037b-169">A single management server can respond to up to 320 publishing servers requesting publishing metadata simultaneously.</span></span></p></li>
<li><p><span data-ttu-id="8037b-170">320 pub サーバーのラウンドトリップ応答時間は、最大40秒です。</span><span class="sxs-lookup"><span data-stu-id="8037b-170">Round trip response time for 320 pub servers is ~40 seconds.</span></span></p></li>
<li><p><span data-ttu-id="8037b-171">&lt;50 パブリッシングサーバーでメタデータを同時に要求する場合、ラウンドトリップの応答時間は &lt; 5 秒です。</span><span class="sxs-lookup"><span data-stu-id="8037b-171">For &lt;50 publishing servers requesting metadata simultaneously, the round trip response time is &lt;5 seconds.</span></span></p></li>
<li><p><span data-ttu-id="8037b-172">50から320発行サーバーへの応答時間は直線的に増加します (約 2x)。</span><span class="sxs-lookup"><span data-stu-id="8037b-172">From 50 to 320 publishing servers, the response time increases linearly (approximately 2x).</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8037b-173">管理サーバーで構成されている接続グループの数。</span><span class="sxs-lookup"><span data-stu-id="8037b-173">The number of connection groups configured on the management server.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-174">最大100の接続グループについては、パブリッシングサーバーのラウンドトリップ応答時間に大幅な変更はありません。</span><span class="sxs-lookup"><span data-stu-id="8037b-174">For up to 100 connection groups, there is no significant change in the round trip response time on the publishing server.</span></span></p></li>
<li><p><span data-ttu-id="8037b-175">100-400 接続グループの場合、ラウンドトリップ応答時間のわずかな線形増加が発生します。</span><span class="sxs-lookup"><span data-stu-id="8037b-175">For 100 - 400 connection groups, there is a minor linear increase in the round trip response time.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8037b-176">管理サーバーで構成されているアクセスグループの数。</span><span class="sxs-lookup"><span data-stu-id="8037b-176">The number of access groups configured on the management server.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-177">最大40のアクセスグループについては、パブリッシングサーバーのラウンドトリップ応答時間が直線的 (約3倍) 増加しています。</span><span class="sxs-lookup"><span data-stu-id="8037b-177">For up to 40 access groups, there is a linear (approximately 3x) increase in the round trip response time on the publishing server.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="8037b-178">次の表は、前の各要素のサンプル値を示しています。</span><span class="sxs-lookup"><span data-stu-id="8037b-178">The following table displays sample values for each of the previous factors.</span></span> <span data-ttu-id="8037b-179">各バリエーションで、120パッケージは、app-v 5.0 management サーバーから更新されます。</span><span class="sxs-lookup"><span data-stu-id="8037b-179">In each variation, 120 packages are refreshed from the App-V 5.0management server.</span></span>

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8037b-180">シナリオ</span><span class="sxs-lookup"><span data-stu-id="8037b-180">Scenario</span></span></th>
<th align="left"><span data-ttu-id="8037b-181">バリエーション</span><span class="sxs-lookup"><span data-stu-id="8037b-181">Variation</span></span></th>
<th align="left"><span data-ttu-id="8037b-182">接続グループの数</span><span class="sxs-lookup"><span data-stu-id="8037b-182">Number of connection groups</span></span></th>
<th align="left"><span data-ttu-id="8037b-183">アクセスグループの数</span><span class="sxs-lookup"><span data-stu-id="8037b-183">Number of access groups</span></span></th>
<th align="left"><span data-ttu-id="8037b-184">発行サーバーの数</span><span class="sxs-lookup"><span data-stu-id="8037b-184">Number of publishing servers</span></span></th>
<th align="left"><span data-ttu-id="8037b-185">ネットワーク接続の種類発行サーバー/管理サーバー</span><span class="sxs-lookup"><span data-stu-id="8037b-185">Network connection type publishing server / management server</span></span></th>
<th align="left"><span data-ttu-id="8037b-186">パブリッシングサーバーのラウンドトリップ応答時間 (秒単位)</span><span class="sxs-lookup"><span data-stu-id="8037b-186">Round trip response time on the publishing server (in seconds)</span></span></th>
<th align="left"><span data-ttu-id="8037b-187">管理サーバーの CPU 使用率</span><span class="sxs-lookup"><span data-stu-id="8037b-187">CPU utilization on management server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8037b-188">サーバーを公開して、メタデータを公開するために管理サーバーに同時に接続します。</span><span class="sxs-lookup"><span data-stu-id="8037b-188">Publishing servers simultaneously contacting management server for publishing metadata.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8037b-189">発行サーバーの数</span><span class="sxs-lookup"><span data-stu-id="8037b-189">Number of publishing servers</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-190">0</span><span class="sxs-lookup"><span data-stu-id="8037b-190">0</span></span></p></li>
<li><p><span data-ttu-id="8037b-191">0</span><span class="sxs-lookup"><span data-stu-id="8037b-191">0</span></span></p></li>
<li><p><span data-ttu-id="8037b-192">0</span><span class="sxs-lookup"><span data-stu-id="8037b-192">0</span></span></p></li>
<li><p><span data-ttu-id="8037b-193">0</span><span class="sxs-lookup"><span data-stu-id="8037b-193">0</span></span></p></li>
<li><p><span data-ttu-id="8037b-194">0</span><span class="sxs-lookup"><span data-stu-id="8037b-194">0</span></span></p></li>
<li><p><span data-ttu-id="8037b-195">0</span><span class="sxs-lookup"><span data-stu-id="8037b-195">0</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-196">件</span><span class="sxs-lookup"><span data-stu-id="8037b-196">1</span></span></p></li>
<li><p><span data-ttu-id="8037b-197">件</span><span class="sxs-lookup"><span data-stu-id="8037b-197">1</span></span></p></li>
<li><p><span data-ttu-id="8037b-198">件</span><span class="sxs-lookup"><span data-stu-id="8037b-198">1</span></span></p></li>
<li><p><span data-ttu-id="8037b-199">件</span><span class="sxs-lookup"><span data-stu-id="8037b-199">1</span></span></p></li>
<li><p><span data-ttu-id="8037b-200">件</span><span class="sxs-lookup"><span data-stu-id="8037b-200">1</span></span></p></li>
<li><p><span data-ttu-id="8037b-201">件</span><span class="sxs-lookup"><span data-stu-id="8037b-201">1</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-202">50</span><span class="sxs-lookup"><span data-stu-id="8037b-202">50</span></span></p></li>
<li><p><span data-ttu-id="8037b-203">100</span><span class="sxs-lookup"><span data-stu-id="8037b-203">100</span></span></p></li>
<li><p><span data-ttu-id="8037b-204">200</span><span class="sxs-lookup"><span data-stu-id="8037b-204">200</span></span></p></li>
<li><p><span data-ttu-id="8037b-205">300</span><span class="sxs-lookup"><span data-stu-id="8037b-205">300</span></span></p></li>
<li><p><span data-ttu-id="8037b-206">315</span><span class="sxs-lookup"><span data-stu-id="8037b-206">315</span></span></p></li>
<li><p><span data-ttu-id="8037b-207">320</span><span class="sxs-lookup"><span data-stu-id="8037b-207">320</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-208">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-208">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-209">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-209">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-210">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-210">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-211">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-211">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-212">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-212">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-213">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-213">LAN</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-214">個</span><span class="sxs-lookup"><span data-stu-id="8037b-214">5</span></span></p></li>
<li><p><span data-ttu-id="8037b-215">常用</span><span class="sxs-lookup"><span data-stu-id="8037b-215">10</span></span></p></li>
<li><p><span data-ttu-id="8037b-216">#</span><span class="sxs-lookup"><span data-stu-id="8037b-216">19</span></span></p></li>
<li><p><span data-ttu-id="8037b-217">32</span><span class="sxs-lookup"><span data-stu-id="8037b-217">32</span></span></p></li>
<li><p><span data-ttu-id="8037b-218">求める</span><span class="sxs-lookup"><span data-stu-id="8037b-218">30</span></span></p></li>
<li><p><span data-ttu-id="8037b-219">37</span><span class="sxs-lookup"><span data-stu-id="8037b-219">37</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-220">17</span><span class="sxs-lookup"><span data-stu-id="8037b-220">17</span></span></p></li>
<li><p><span data-ttu-id="8037b-221">17</span><span class="sxs-lookup"><span data-stu-id="8037b-221">17</span></span></p></li>
<li><p><span data-ttu-id="8037b-222">17</span><span class="sxs-lookup"><span data-stu-id="8037b-222">17</span></span></p></li>
<li><p><span data-ttu-id="8037b-223">マート</span><span class="sxs-lookup"><span data-stu-id="8037b-223">15</span></span></p></li>
<li><p><span data-ttu-id="8037b-224">17</span><span class="sxs-lookup"><span data-stu-id="8037b-224">17</span></span></p></li>
<li><p><span data-ttu-id="8037b-225">マート</span><span class="sxs-lookup"><span data-stu-id="8037b-225">15</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8037b-226">発行メタデータに接続グループが含まれている</span><span class="sxs-lookup"><span data-stu-id="8037b-226">Publishing metadata contains connection groups</span></span></p></td>
<td align="left"><p><span data-ttu-id="8037b-227">接続グループの数</span><span class="sxs-lookup"><span data-stu-id="8037b-227">Number of connection groups</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-228">常用</span><span class="sxs-lookup"><span data-stu-id="8037b-228">10</span></span></p></li>
<li><p><span data-ttu-id="8037b-229">50</span><span class="sxs-lookup"><span data-stu-id="8037b-229">50</span></span></p></li>
<li><p><span data-ttu-id="8037b-230">100</span><span class="sxs-lookup"><span data-stu-id="8037b-230">100</span></span></p></li>
<li><p><span data-ttu-id="8037b-231">150</span><span class="sxs-lookup"><span data-stu-id="8037b-231">150</span></span></p></li>
<li><p><span data-ttu-id="8037b-232">300</span><span class="sxs-lookup"><span data-stu-id="8037b-232">300</span></span></p></li>
<li><p><span data-ttu-id="8037b-233">400</span><span class="sxs-lookup"><span data-stu-id="8037b-233">400</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-234">件</span><span class="sxs-lookup"><span data-stu-id="8037b-234">1</span></span></p></li>
<li><p><span data-ttu-id="8037b-235">件</span><span class="sxs-lookup"><span data-stu-id="8037b-235">1</span></span></p></li>
<li><p><span data-ttu-id="8037b-236">件</span><span class="sxs-lookup"><span data-stu-id="8037b-236">1</span></span></p></li>
<li><p><span data-ttu-id="8037b-237">件</span><span class="sxs-lookup"><span data-stu-id="8037b-237">1</span></span></p></li>
<li><p><span data-ttu-id="8037b-238">件</span><span class="sxs-lookup"><span data-stu-id="8037b-238">1</span></span></p></li>
<li><p><span data-ttu-id="8037b-239">件</span><span class="sxs-lookup"><span data-stu-id="8037b-239">1</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-240">100</span><span class="sxs-lookup"><span data-stu-id="8037b-240">100</span></span></p></li>
<li><p><span data-ttu-id="8037b-241">100</span><span class="sxs-lookup"><span data-stu-id="8037b-241">100</span></span></p></li>
<li><p><span data-ttu-id="8037b-242">100</span><span class="sxs-lookup"><span data-stu-id="8037b-242">100</span></span></p></li>
<li><p><span data-ttu-id="8037b-243">100</span><span class="sxs-lookup"><span data-stu-id="8037b-243">100</span></span></p></li>
<li><p><span data-ttu-id="8037b-244">100</span><span class="sxs-lookup"><span data-stu-id="8037b-244">100</span></span></p></li>
<li><p><span data-ttu-id="8037b-245">100</span><span class="sxs-lookup"><span data-stu-id="8037b-245">100</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-246">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-246">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-247">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-247">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-248">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-248">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-249">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-249">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-250">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-250">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-251">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-251">LAN</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-252">常用</span><span class="sxs-lookup"><span data-stu-id="8037b-252">10</span></span></p></li>
<li><p><span data-ttu-id="8037b-253">折り</span><span class="sxs-lookup"><span data-stu-id="8037b-253">11</span></span></p></li>
<li><p><span data-ttu-id="8037b-254">折り</span><span class="sxs-lookup"><span data-stu-id="8037b-254">11</span></span></p></li>
<li><p><span data-ttu-id="8037b-255">16</span><span class="sxs-lookup"><span data-stu-id="8037b-255">16</span></span></p></li>
<li><p><span data-ttu-id="8037b-256">22</span><span class="sxs-lookup"><span data-stu-id="8037b-256">22</span></span></p></li>
<li><p><span data-ttu-id="8037b-257">50</span><span class="sxs-lookup"><span data-stu-id="8037b-257">25</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-258">17</span><span class="sxs-lookup"><span data-stu-id="8037b-258">17</span></span></p></li>
<li><p><span data-ttu-id="8037b-259">#</span><span class="sxs-lookup"><span data-stu-id="8037b-259">19</span></span></p></li>
<li><p><span data-ttu-id="8037b-260">22</span><span class="sxs-lookup"><span data-stu-id="8037b-260">22</span></span></p></li>
<li><p><span data-ttu-id="8037b-261">#</span><span class="sxs-lookup"><span data-stu-id="8037b-261">19</span></span></p></li>
<li><p><span data-ttu-id="8037b-262">超える</span><span class="sxs-lookup"><span data-stu-id="8037b-262">20</span></span></p></li>
<li><p><span data-ttu-id="8037b-263">超える</span><span class="sxs-lookup"><span data-stu-id="8037b-263">20</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8037b-264">公開メタデータにアクセスグループが含まれている</span><span class="sxs-lookup"><span data-stu-id="8037b-264">Publishing metadata contains access groups</span></span></p></td>
<td align="left"><p><span data-ttu-id="8037b-265">アクセスグループの数</span><span class="sxs-lookup"><span data-stu-id="8037b-265">Number of access groups</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-266">0</span><span class="sxs-lookup"><span data-stu-id="8037b-266">0</span></span></p></li>
<li><p><span data-ttu-id="8037b-267">0</span><span class="sxs-lookup"><span data-stu-id="8037b-267">0</span></span></p></li>
<li><p><span data-ttu-id="8037b-268">0</span><span class="sxs-lookup"><span data-stu-id="8037b-268">0</span></span></p></li>
<li><p><span data-ttu-id="8037b-269">0</span><span class="sxs-lookup"><span data-stu-id="8037b-269">0</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-270">件</span><span class="sxs-lookup"><span data-stu-id="8037b-270">1</span></span></p></li>
<li><p><span data-ttu-id="8037b-271">常用</span><span class="sxs-lookup"><span data-stu-id="8037b-271">10</span></span></p></li>
<li><p><span data-ttu-id="8037b-272">超える</span><span class="sxs-lookup"><span data-stu-id="8037b-272">20</span></span></p></li>
<li><p><span data-ttu-id="8037b-273">40</span><span class="sxs-lookup"><span data-stu-id="8037b-273">40</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-274">100</span><span class="sxs-lookup"><span data-stu-id="8037b-274">100</span></span></p></li>
<li><p><span data-ttu-id="8037b-275">100</span><span class="sxs-lookup"><span data-stu-id="8037b-275">100</span></span></p></li>
<li><p><span data-ttu-id="8037b-276">100</span><span class="sxs-lookup"><span data-stu-id="8037b-276">100</span></span></p></li>
<li><p><span data-ttu-id="8037b-277">100</span><span class="sxs-lookup"><span data-stu-id="8037b-277">100</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-278">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-278">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-279">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-279">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-280">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-280">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-281">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-281">LAN</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-282">常用</span><span class="sxs-lookup"><span data-stu-id="8037b-282">10</span></span></p></li>
<li><p><span data-ttu-id="8037b-283">43</span><span class="sxs-lookup"><span data-stu-id="8037b-283">43</span></span></p></li>
<li><p><span data-ttu-id="8037b-284">153</span><span class="sxs-lookup"><span data-stu-id="8037b-284">153</span></span></p></li>
<li><p><span data-ttu-id="8037b-285">535</span><span class="sxs-lookup"><span data-stu-id="8037b-285">535</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-286">17</span><span class="sxs-lookup"><span data-stu-id="8037b-286">17</span></span></p></li>
<li><p><span data-ttu-id="8037b-287">#</span><span class="sxs-lookup"><span data-stu-id="8037b-287">26</span></span></p></li>
<li><p><span data-ttu-id="8037b-288">24</span><span class="sxs-lookup"><span data-stu-id="8037b-288">24</span></span></p></li>
<li><p><span data-ttu-id="8037b-289">24</span><span class="sxs-lookup"><span data-stu-id="8037b-289">24</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="8037b-290">管理サーバーを実行しているコンピューターの CPU 使用率は、ターゲットに設定されている発行サーバーの数に関係なく、約25% になります。</span><span class="sxs-lookup"><span data-stu-id="8037b-290">The CPU utilization of the computer running the management server is around 25% irrespective of the number of publishing servers targeting it.</span></span> <span data-ttu-id="8037b-291">Microsoft SQL Server データベーストランザクション/sec、バッチ要求/秒、およびユーザー接続は、発行サーバーの数に関係なく同一になります。</span><span class="sxs-lookup"><span data-stu-id="8037b-291">The Microsoft SQL Server database transactions/sec, batch requests/sec and user connections are identical irrespective of the number of publishing servers.</span></span> <span data-ttu-id="8037b-292">たとえば、トランザクション/sec は ~ 30、バッチ要求 ~ 200、ユーザーは ~ 6 を接続します。</span><span class="sxs-lookup"><span data-stu-id="8037b-292">For example: Transactions/sec is ~30, batch requests ~200, and user connects ~6.</span></span>

<span data-ttu-id="8037b-293">地理的に分散した展開を使用している場合、管理サーバー & 発行サーバーは、それらの間の低速リンクネットワークを利用します。発行サーバーのラウンドトリップ応答時間は、 &lt; 1 つの管理サーバーで同時に100を要求する場合でも、許容時間制限 (5 秒) になります。</span><span class="sxs-lookup"><span data-stu-id="8037b-293">Using a geographically distributed deployment, where the management server & publishing servers utilize a slow link network between them, the round trip response time on the publishing servers is within acceptable time limits (&lt;5 seconds), even for 100 simultaneous requests on a single management server.</span></span>

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8037b-294">シナリオ</span><span class="sxs-lookup"><span data-stu-id="8037b-294">Scenario</span></span></th>
<th align="left"><span data-ttu-id="8037b-295">バリエーション</span><span class="sxs-lookup"><span data-stu-id="8037b-295">Variation</span></span></th>
<th align="left"><span data-ttu-id="8037b-296">接続グループの数</span><span class="sxs-lookup"><span data-stu-id="8037b-296">Number of connection groups</span></span></th>
<th align="left"><span data-ttu-id="8037b-297">アクセスグループの数</span><span class="sxs-lookup"><span data-stu-id="8037b-297">Number of access groups</span></span></th>
<th align="left"><span data-ttu-id="8037b-298">発行サーバーの数</span><span class="sxs-lookup"><span data-stu-id="8037b-298">Number of publishing servers</span></span></th>
<th align="left"><span data-ttu-id="8037b-299">ネットワーク接続の種類発行サーバー/管理サーバー</span><span class="sxs-lookup"><span data-stu-id="8037b-299">Network connection type publishing server / management server</span></span></th>
<th align="left"><span data-ttu-id="8037b-300">パブリッシングサーバーのラウンドトリップ応答時間 (秒単位)</span><span class="sxs-lookup"><span data-stu-id="8037b-300">Round trip response time on the publishing server (in seconds)</span></span></th>
<th align="left"><span data-ttu-id="8037b-301">管理サーバーの CPU 使用率</span><span class="sxs-lookup"><span data-stu-id="8037b-301">CPU utilization on management server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8037b-302">発行サーバーと管理サーバーの間のネットワーク接続</span><span class="sxs-lookup"><span data-stu-id="8037b-302">Network connection between the publishing server and management server</span></span></p></td>
<td align="left"><p><span data-ttu-id="8037b-303">1.5 Mbps 低速リンクネットワーク</span><span class="sxs-lookup"><span data-stu-id="8037b-303">1.5 Mbps Slow link Network</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-304">0</span><span class="sxs-lookup"><span data-stu-id="8037b-304">0</span></span></p></li>
<li><p><span data-ttu-id="8037b-305">0</span><span class="sxs-lookup"><span data-stu-id="8037b-305">0</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-306">件</span><span class="sxs-lookup"><span data-stu-id="8037b-306">1</span></span></p></li>
<li><p><span data-ttu-id="8037b-307">件</span><span class="sxs-lookup"><span data-stu-id="8037b-307">1</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-308">50</span><span class="sxs-lookup"><span data-stu-id="8037b-308">50</span></span></p></li>
<li><p><span data-ttu-id="8037b-309">100</span><span class="sxs-lookup"><span data-stu-id="8037b-309">100</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-310">1.5 mbps ケーブルの DSL</span><span class="sxs-lookup"><span data-stu-id="8037b-310">1.5Mbps Cable DSL</span></span></p></li>
<li><p><span data-ttu-id="8037b-311">1.5 mbps ケーブルの DSL</span><span class="sxs-lookup"><span data-stu-id="8037b-311">1.5Mbps Cable DSL</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-312">4d</span><span class="sxs-lookup"><span data-stu-id="8037b-312">4</span></span></p></li>
<li><p><span data-ttu-id="8037b-313">個</span><span class="sxs-lookup"><span data-stu-id="8037b-313">5</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-314">件</span><span class="sxs-lookup"><span data-stu-id="8037b-314">1</span></span></p></li>
<li><p><span data-ttu-id="8037b-315">両面</span><span class="sxs-lookup"><span data-stu-id="8037b-315">2</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8037b-316">発行サーバーと管理サーバーの間のネットワーク接続</span><span class="sxs-lookup"><span data-stu-id="8037b-316">Network connection between the publishing server and management server</span></span></p></td>
<td align="left"><p><span data-ttu-id="8037b-317">LAN/WIFI ネットワーク</span><span class="sxs-lookup"><span data-stu-id="8037b-317">LAN / WIFI Network</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-318">0</span><span class="sxs-lookup"><span data-stu-id="8037b-318">0</span></span></p></li>
<li><p><span data-ttu-id="8037b-319">0</span><span class="sxs-lookup"><span data-stu-id="8037b-319">0</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-320">件</span><span class="sxs-lookup"><span data-stu-id="8037b-320">1</span></span></p></li>
<li><p><span data-ttu-id="8037b-321">件</span><span class="sxs-lookup"><span data-stu-id="8037b-321">1</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-322">100</span><span class="sxs-lookup"><span data-stu-id="8037b-322">100</span></span></p></li>
<li><p><span data-ttu-id="8037b-323">200</span><span class="sxs-lookup"><span data-stu-id="8037b-323">200</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-324">Wifi</span><span class="sxs-lookup"><span data-stu-id="8037b-324">Wifi</span></span></p></li>
<li><p><span data-ttu-id="8037b-325">Wifi</span><span class="sxs-lookup"><span data-stu-id="8037b-325">Wifi</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-326">折り</span><span class="sxs-lookup"><span data-stu-id="8037b-326">11</span></span></p></li>
<li><p><span data-ttu-id="8037b-327">超える</span><span class="sxs-lookup"><span data-stu-id="8037b-327">20</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-328">マート</span><span class="sxs-lookup"><span data-stu-id="8037b-328">15</span></span></p></li>
<li><p><span data-ttu-id="8037b-329">17</span><span class="sxs-lookup"><span data-stu-id="8037b-329">17</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="8037b-330">管理サーバーと発行サーバーが低速リンクネットワークまたは高速ネットワーク経由で接続されているかどうかにかかわらず、管理サーバーは約15000パッケージ更新要求を30分で処理できます。</span><span class="sxs-lookup"><span data-stu-id="8037b-330">Whether the management server and publishing servers are connected over a slow link network, or a high speed network, the management server can handle approximately 15,000 package refresh requests in 30 minutes.</span></span>

## <a href="" id="---------app-v-5-0-reporting-server-capacity-planning-recommendations"></a> <span data-ttu-id="8037b-331">App-v 5.0 レポートサーバーキャパシティ計画の推奨事項</span><span class="sxs-lookup"><span data-stu-id="8037b-331">App-V 5.0 Reporting Server Capacity Planning Recommendations</span></span>


<span data-ttu-id="8037b-332">App-v 5.0 クライアントは、レポートデータをレポートサーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="8037b-332">App-V 5.0 clients send reporting data to the reporting server.</span></span> <span data-ttu-id="8037b-333">その後、レポートサーバーでは、Microsoft SQL Server データベースに情報が記録され、App-v 5.0 クライアントを実行しているコンピューターに正常に通知が返されます。</span><span class="sxs-lookup"><span data-stu-id="8037b-333">The reporting server then records the information in the Microsoft SQL Server database and returns a successful notification back to the computer running App-V 5.0 client.</span></span> <span data-ttu-id="8037b-334">App-v 5.0 Reporting Server でサポートされている構成の詳細については[、「app-v 5.0 でサポートされている構成](app-v-50-supported-configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8037b-334">For more information about App-V 5.0 Reporting Server supported configurations see [App-V 5.0 Supported Configurations](app-v-50-supported-configurations.md).</span></span>

<span data-ttu-id="8037b-335">**注** ラウンドトリップの応答時間は、レポート情報をレポートサーバーに送信して、レポートサーバーから正常に通知を受信するために、App-v 5.0 クライアントを実行しているコンピューターにかかる時間です。</span><span class="sxs-lookup"><span data-stu-id="8037b-335">**Note** Round trip response time is the time taken by the computer running the App-V 5.0 client to send the reporting information to the reporting server and receive a successful notification from the reporting server.</span></span>

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8037b-336">シナリオ</span><span class="sxs-lookup"><span data-stu-id="8037b-336">Scenario</span></span></th>
<th align="left"><span data-ttu-id="8037b-337">まとめ</span><span class="sxs-lookup"><span data-stu-id="8037b-337">Summary</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8037b-338">複数の App-v 5.0 クライアントは、レポート情報を同時にレポートサーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="8037b-338">Multiple App-V 5.0 clients send reporting information to the reporting server simultaneously.</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-339">レポートサーバーからのラウンドトリップ応答時間は、500クライアントでは2.6 秒です。</span><span class="sxs-lookup"><span data-stu-id="8037b-339">Round trip response time from the reporting server is 2.6 seconds for 500 clients.</span></span></p></li>
<li><p><span data-ttu-id="8037b-340">レポートサーバーからのラウンドトリップ応答時間は、1000クライアントでは5.65 秒です。</span><span class="sxs-lookup"><span data-stu-id="8037b-340">Round trip response time from the reporting server is 5.65 seconds for 1000 clients.</span></span></p></li>
<li><p><span data-ttu-id="8037b-341">ラウンドトリップの応答時間は、クライアント数に応じて直線的に増加します。</span><span class="sxs-lookup"><span data-stu-id="8037b-341">Round trip response time increases linearly depending on number of clients.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8037b-342">レポートサーバーによって処理された1秒あたりの要求数。</span><span class="sxs-lookup"><span data-stu-id="8037b-342">Requests per second processed by the reporting server.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-343">1つのレポートサーバーと1つのデータベースは、1秒あたり最大139要求を処理できます。</span><span class="sxs-lookup"><span data-stu-id="8037b-343">A single reporting server and a single database, can process a maximum of 139 requests per second.</span></span> <span data-ttu-id="8037b-344">平均は121要求数/秒です。</span><span class="sxs-lookup"><span data-stu-id="8037b-344">The average is 121 requests/second.</span></span></p></li>
<li><p><span data-ttu-id="8037b-345">同じ Microsoft SQL Server データベースにレポートされた2つのレポートサーバーを使用する場合、average requests/秒は1つのレポートサーバー = ~ 127 に似ていますが、最大278要求数は1秒です。</span><span class="sxs-lookup"><span data-stu-id="8037b-345">Using two reporting servers reporting to the same Microsoft SQL Server database, the average requests/second is similar to a single reporting server = ~127, with a max of 278 requests/second.</span></span></p></li>
<li><p><span data-ttu-id="8037b-346">1つのレポートサーバーで、500の同時接続とアクティブな接続を処理できます。</span><span class="sxs-lookup"><span data-stu-id="8037b-346">A single reporting server can process 500 concurrent/active connections.</span></span></p></li>
<li><p><span data-ttu-id="8037b-347">1つのレポートサーバーで、最大1500の同時接続を処理できます。</span><span class="sxs-lookup"><span data-stu-id="8037b-347">A single reporting server can process a maximum 1500 concurrent connections.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8037b-348">レポートデータベース。</span><span class="sxs-lookup"><span data-stu-id="8037b-348">Reporting Database.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-349">Microsoft SQL Server を実行しているコンピューターのロックの競合は、要求/秒の制限要素です。</span><span class="sxs-lookup"><span data-stu-id="8037b-349">Lock contention on the computer running Microsoft SQL Server is the limiting factor for requests/second.</span></span></p></li>
<li><p><span data-ttu-id="8037b-350">スループットと応答時間はデータベースのサイズに依存しません。</span><span class="sxs-lookup"><span data-stu-id="8037b-350">Throughput and response time are independent of database size.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="8037b-351">**ランダム遅延の計算**:</span><span class="sxs-lookup"><span data-stu-id="8037b-351">**Calculating random delay**:</span></span>

<span data-ttu-id="8037b-352">ランダムな遅延は、レポートサーバーに送信されるデータの最大遅延 (分単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="8037b-352">The random delay specifies the maximum delay (in minutes) for data to be sent to the reporting server.</span></span> <span data-ttu-id="8037b-353">スケジュールされたタスクが開始されると、クライアントは**0**と**ReportingRandomDelay**の間のランダムな遅延を生成し、データを送信する前に指定された期間待機します。</span><span class="sxs-lookup"><span data-stu-id="8037b-353">When the scheduled task is started, the client generates a random delay between **0** and **ReportingRandomDelay** and will wait the specified duration before sending data.</span></span>

<span data-ttu-id="8037b-354">ランダム遅延 = 4 \ \* クライアント数/秒あたりの平均要求数。</span><span class="sxs-lookup"><span data-stu-id="8037b-354">Random delay = 4 \* number of clients / average requests per second.</span></span>

<span data-ttu-id="8037b-355">例: 500 クライアントで、1秒あたりの120要求があった場合、ランダム遅延は、4 \ \* 500/120 = ~ 17 分です。</span><span class="sxs-lookup"><span data-stu-id="8037b-355">Example: For 500 clients, with 120 requests per second, the Random delay is, 4 \* 500 / 120 = ~17 minutes.</span></span>

## <a href="" id="---------app-v-5-0-publishing-server-capacity-planning-recommendations"></a> <span data-ttu-id="8037b-356">App-v 5.0 発行サーバーのキャパシティ計画に関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="8037b-356">App-V 5.0 Publishing Server Capacity Planning Recommendations</span></span>


<span data-ttu-id="8037b-357">App-v 5.0 クライアントを実行しているコンピューターは、app-v 5.0 発行サーバーに接続して、公開更新要求を送信し、応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="8037b-357">Computers running the App-V 5.0 client connect to the App-V 5.0 publishing server to send a publishing refresh request and to receive a response.</span></span> <span data-ttu-id="8037b-358">ラウンドトリップの応答時間は、App-v 5.0 クライアントを実行しているコンピューターで測定されます。</span><span class="sxs-lookup"><span data-stu-id="8037b-358">Round trip response time is measured on the computer running the App-V 5.0 client.</span></span> <span data-ttu-id="8037b-359">プロセッサ時間は発行サーバーで測定されます。</span><span class="sxs-lookup"><span data-stu-id="8037b-359">Processor time is measured on the publishing server.</span></span> <span data-ttu-id="8037b-360">App-v 5.0 Publishing Server でサポートされている構成の詳細については[、「app-v 5.0 でサポートされている構成](app-v-50-supported-configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8037b-360">For more information about App-V 5.0 Publishing Server supported configurations see [App-V 5.0 Supported Configurations](app-v-50-supported-configurations.md).</span></span>

<span data-ttu-id="8037b-361">**重要** 次の一覧は、App-v 5.0 発行サーバーのセットアップ時に考慮する主な要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="8037b-361">**Important** The following list displays the main factors to consider when setting up the App-V 5.0 publishing server:</span></span>

-   <span data-ttu-id="8037b-362">1つのパブリッシングサーバーに同時に接続しているクライアントの数。</span><span class="sxs-lookup"><span data-stu-id="8037b-362">The number of clients connecting simultaneously to a single publishing server.</span></span>

-   <span data-ttu-id="8037b-363">各更新のパッケージ数。</span><span class="sxs-lookup"><span data-stu-id="8037b-363">The number of packages in each refresh.</span></span>

-   <span data-ttu-id="8037b-364">クライアントと App-v 5.0 発行サーバーとの間の環境で利用可能なネットワーク帯域幅。</span><span class="sxs-lookup"><span data-stu-id="8037b-364">The available network bandwidth in your environment between the client and the App-V 5.0 publishing server.</span></span>

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8037b-365">シナリオ</span><span class="sxs-lookup"><span data-stu-id="8037b-365">Scenario</span></span></th>
<th align="left"><span data-ttu-id="8037b-366">まとめ</span><span class="sxs-lookup"><span data-stu-id="8037b-366">Summary</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8037b-367">複数の App-v 5.0 クライアントは、1つのパブリッシングサーバーに同時に接続します。</span><span class="sxs-lookup"><span data-stu-id="8037b-367">Multiple App-V 5.0 clients connect to a single publishing server simultaneously.</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-368">デュアルコアプロセッサを実行している発行サーバーでは、ほとんどの5000クライアントで同時に更新を要求することができます。</span><span class="sxs-lookup"><span data-stu-id="8037b-368">A publishing server running dual core processors can respond to at most 5000 clients requesting a refresh simultaneously.</span></span></p></li>
<li><p><span data-ttu-id="8037b-369">5000-10000 クライアントの場合、発行サーバーに最低限の4コアが必要です。</span><span class="sxs-lookup"><span data-stu-id="8037b-369">For 5000-10000 clients, the publishing server requires a minimum quad core.</span></span></p></li>
<li><p><span data-ttu-id="8037b-370">10000-20000 クライアントの場合、応答時間をより効率的にするために、発行サーバーには2つのクワッドコアが必要です。</span><span class="sxs-lookup"><span data-stu-id="8037b-370">For 10000-20000 clients, the publishing server should have dual quad cores for more efficient response times.</span></span></p></li>
<li><p><span data-ttu-id="8037b-371">4コアの発行サーバーは、3秒以内に最大1万パッケージを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="8037b-371">A publishing server with a quad core can refresh up to 10000 packages within 3 seconds.</span></span> <span data-ttu-id="8037b-372">(1万の同時クライアントのサポート)</span><span class="sxs-lookup"><span data-stu-id="8037b-372">(Supporting 10000 simultaneous clients)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8037b-373">各更新のパッケージ数。</span><span class="sxs-lookup"><span data-stu-id="8037b-373">Number of packages in each refresh.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-374">パッケージの数を増やすと 40% (最大1000パッケージ) の応答時間が増加します。</span><span class="sxs-lookup"><span data-stu-id="8037b-374">Increasing number of packages will increase response time by ~40% (up to 1000 packages).</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8037b-375">App-v 5.0 クライアントと発行サーバー間のネットワーク。</span><span class="sxs-lookup"><span data-stu-id="8037b-375">Network between the App-V 5.0 client and the publishing server.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-376">低速ネットワーク (1.5 Mbps の帯域幅) では、LAN と比較した場合の応答時間が97% 増加しています (最大1000ユーザー)。</span><span class="sxs-lookup"><span data-stu-id="8037b-376">Across a slow network (1.5 Mbps bandwidth), there is a 97% increase in response time compared to LAN (up to 1000 users).</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="8037b-377">**注** 発行サーバーの CPU 使用率は、同時要求を処理する必要がある時間間隔内に常に高くなり &gt; ます (ほとんどの場合、90% です)。</span><span class="sxs-lookup"><span data-stu-id="8037b-377">**Note** The publishing server CPU usage is always high during the time interval when it has to process simultaneous requests (&gt;90% in most cases).</span></span> <span data-ttu-id="8037b-378">発行サーバーは、1秒で1500クライアント要求を処理できます。</span><span class="sxs-lookup"><span data-stu-id="8037b-378">The publishing server can handle ~1500 client requests in 1 second.</span></span>

 

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8037b-379">シナリオ</span><span class="sxs-lookup"><span data-stu-id="8037b-379">Scenario</span></span></th>
<th align="left"><span data-ttu-id="8037b-380">バリエーション</span><span class="sxs-lookup"><span data-stu-id="8037b-380">Variation</span></span></th>
<th align="left"><span data-ttu-id="8037b-381">App-v 5.0 クライアントの数</span><span class="sxs-lookup"><span data-stu-id="8037b-381">Number of App-V 5.0 clients</span></span></th>
<th align="left"><span data-ttu-id="8037b-382">パッケージ数</span><span class="sxs-lookup"><span data-stu-id="8037b-382">Number of packages</span></span></th>
<th align="left"><span data-ttu-id="8037b-383">パブリッシングサーバー上のプロセッサ構成</span><span class="sxs-lookup"><span data-stu-id="8037b-383">Processor configuration on the publishing server</span></span></th>
<th align="left"><span data-ttu-id="8037b-384">ネットワーク接続の種類発行サーバー/App-v 5.0 クライアント</span><span class="sxs-lookup"><span data-stu-id="8037b-384">Network connection type publishing server / App-V 5.0 client</span></span></th>
<th align="left"><span data-ttu-id="8037b-385">App-v 5.0 クライアントでのラウンドトリップ時間 (秒単位)</span><span class="sxs-lookup"><span data-stu-id="8037b-385">Round trip time on the App-V 5.0 client (in seconds)</span></span></th>
<th align="left"><span data-ttu-id="8037b-386">パブリッシングサーバーの CPU 使用率 (%)</span><span class="sxs-lookup"><span data-stu-id="8037b-386">CPU utilization on publishing server (in %)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8037b-387">App-v 5.0 クライアントは、発行の更新要求 &amp; を受信し、120パッケージを含む各要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="8037b-387">App-V 5.0 client sends publishing refresh request &amp; receives response, each request containing 120 packages</span></span></p></td>
<td align="left"><p><span data-ttu-id="8037b-388">クライアント数</span><span class="sxs-lookup"><span data-stu-id="8037b-388">Number of clients</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-389">100</span><span class="sxs-lookup"><span data-stu-id="8037b-389">100</span></span></p></li>
<li><p><span data-ttu-id="8037b-390">1000</span><span class="sxs-lookup"><span data-stu-id="8037b-390">1000</span></span></p></li>
<li><p><span data-ttu-id="8037b-391">5000</span><span class="sxs-lookup"><span data-stu-id="8037b-391">5000</span></span></p></li>
<li><p><span data-ttu-id="8037b-392">1万</span><span class="sxs-lookup"><span data-stu-id="8037b-392">10000</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-393">120</span><span class="sxs-lookup"><span data-stu-id="8037b-393">120</span></span></p></li>
<li><p><span data-ttu-id="8037b-394">120</span><span class="sxs-lookup"><span data-stu-id="8037b-394">120</span></span></p></li>
<li><p><span data-ttu-id="8037b-395">120</span><span class="sxs-lookup"><span data-stu-id="8037b-395">120</span></span></p></li>
<li><p><span data-ttu-id="8037b-396">120</span><span class="sxs-lookup"><span data-stu-id="8037b-396">120</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-397">デュアルコア</span><span class="sxs-lookup"><span data-stu-id="8037b-397">Dual Core</span></span></p></li>
<li><p><span data-ttu-id="8037b-398">デュアルコア</span><span class="sxs-lookup"><span data-stu-id="8037b-398">Dual Core</span></span></p></li>
<li><p><span data-ttu-id="8037b-399">クアッドコア</span><span class="sxs-lookup"><span data-stu-id="8037b-399">Quad Core</span></span></p></li>
<li><p><span data-ttu-id="8037b-400">クアッドコア</span><span class="sxs-lookup"><span data-stu-id="8037b-400">Quad Core</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-401">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-401">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-402">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-402">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-403">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-403">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-404">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-404">LAN</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-405">件</span><span class="sxs-lookup"><span data-stu-id="8037b-405">1</span></span></p></li>
<li><p><span data-ttu-id="8037b-406">両面</span><span class="sxs-lookup"><span data-stu-id="8037b-406">2</span></span></p></li>
<li><p><span data-ttu-id="8037b-407">両面</span><span class="sxs-lookup"><span data-stu-id="8037b-407">2</span></span></p></li>
<li><p><span data-ttu-id="8037b-408">-</span><span class="sxs-lookup"><span data-stu-id="8037b-408">3</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-409">100</span><span class="sxs-lookup"><span data-stu-id="8037b-409">100</span></span></p></li>
<li><p><span data-ttu-id="8037b-410">99</span><span class="sxs-lookup"><span data-stu-id="8037b-410">99</span></span></p></li>
<li><p><span data-ttu-id="8037b-411">89</span><span class="sxs-lookup"><span data-stu-id="8037b-411">89</span></span></p></li>
<li><p><span data-ttu-id="8037b-412">77</span><span class="sxs-lookup"><span data-stu-id="8037b-412">77</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8037b-413">更新ごとに複数のパッケージ</span><span class="sxs-lookup"><span data-stu-id="8037b-413">Multiple packages in each refresh</span></span></p></td>
<td align="left"><p><span data-ttu-id="8037b-414">パッケージ数</span><span class="sxs-lookup"><span data-stu-id="8037b-414">Number of packages</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-415">1000</span><span class="sxs-lookup"><span data-stu-id="8037b-415">1000</span></span></p></li>
<li><p><span data-ttu-id="8037b-416">1000</span><span class="sxs-lookup"><span data-stu-id="8037b-416">1000</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-417">500</span><span class="sxs-lookup"><span data-stu-id="8037b-417">500</span></span></p></li>
<li><p><span data-ttu-id="8037b-418">1000</span><span class="sxs-lookup"><span data-stu-id="8037b-418">1000</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-419">クアッドコア</span><span class="sxs-lookup"><span data-stu-id="8037b-419">Quad Core</span></span></p></li>
<li><p><span data-ttu-id="8037b-420">クアッドコア</span><span class="sxs-lookup"><span data-stu-id="8037b-420">Quad Core</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-421">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-421">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-422">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-422">LAN</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-423">両面</span><span class="sxs-lookup"><span data-stu-id="8037b-423">2</span></span></p></li>
<li><p><span data-ttu-id="8037b-424">-</span><span class="sxs-lookup"><span data-stu-id="8037b-424">3</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-425">92</span><span class="sxs-lookup"><span data-stu-id="8037b-425">92</span></span></p></li>
<li><p><span data-ttu-id="8037b-426">91</span><span class="sxs-lookup"><span data-stu-id="8037b-426">91</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8037b-427">クライアントと発行サーバー間のネットワーク</span><span class="sxs-lookup"><span data-stu-id="8037b-427">Network between client and publishing server</span></span></p></td>
<td align="left"><p><span data-ttu-id="8037b-428">1.5 Mbps 低速リンクネットワーク</span><span class="sxs-lookup"><span data-stu-id="8037b-428">1.5 Mbps Slow link network</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-429">100</span><span class="sxs-lookup"><span data-stu-id="8037b-429">100</span></span></p></li>
<li><p><span data-ttu-id="8037b-430">500</span><span class="sxs-lookup"><span data-stu-id="8037b-430">500</span></span></p></li>
<li><p><span data-ttu-id="8037b-431">1000</span><span class="sxs-lookup"><span data-stu-id="8037b-431">1000</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-432">120</span><span class="sxs-lookup"><span data-stu-id="8037b-432">120</span></span></p></li>
<li><p><span data-ttu-id="8037b-433">120</span><span class="sxs-lookup"><span data-stu-id="8037b-433">120</span></span></p></li>
<li><p><span data-ttu-id="8037b-434">120</span><span class="sxs-lookup"><span data-stu-id="8037b-434">120</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-435">クアッドコア</span><span class="sxs-lookup"><span data-stu-id="8037b-435">Quad Core</span></span></p></li>
<li><p><span data-ttu-id="8037b-436">クアッドコア</span><span class="sxs-lookup"><span data-stu-id="8037b-436">Quad Core</span></span></p></li>
<li><p><span data-ttu-id="8037b-437">クアッドコア</span><span class="sxs-lookup"><span data-stu-id="8037b-437">Quad Core</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-438">1.5 Mbps の大陸内ネットワーク</span><span class="sxs-lookup"><span data-stu-id="8037b-438">1.5 Mbps Intra-Continental Network</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-439">-</span><span class="sxs-lookup"><span data-stu-id="8037b-439">3</span></span></p></li>
<li><p><span data-ttu-id="8037b-440">10 (0.2% の故障率)</span><span class="sxs-lookup"><span data-stu-id="8037b-440">10 (with 0.2% failure rate)</span></span></p></li>
<li><p><span data-ttu-id="8037b-441">17 (1% の故障率)</span><span class="sxs-lookup"><span data-stu-id="8037b-441">17 (with 1% failure rate)</span></span></p></li>
</ul></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="---------app-v-5-0-streaming-capacity-planning-recommendations"></a> <span data-ttu-id="8037b-442">App-v 5.0 ストリーミングキャパシティ計画の推奨事項</span><span class="sxs-lookup"><span data-stu-id="8037b-442">App-V 5.0 Streaming Capacity Planning Recommendations</span></span>


<span data-ttu-id="8037b-443">App-v 5.0 クライアントを実行しているコンピューターは、ストリーミングサーバーから仮想アプリケーションパッケージをストリームします。</span><span class="sxs-lookup"><span data-stu-id="8037b-443">Computers running the App-V 5.0 client stream the virtual application package from the streaming server.</span></span> <span data-ttu-id="8037b-444">ラウンドトリップの応答時間は、App-v 5.0 クライアントを実行しているコンピューターで測定され、パッケージ全体をストリーミングするのにかかった時間です。</span><span class="sxs-lookup"><span data-stu-id="8037b-444">Round trip response time is measured on the computer running the App-V 5.0 client, and is the time taken to stream the entire package.</span></span>

<span data-ttu-id="8037b-445">**重要** 次のリストは、App-v 5.0 ストリーミングサーバーのセットアップ時に考慮する主な要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="8037b-445">**Important** The following list identifies the main factors to consider when setting up the App-V 5.0 streaming server:</span></span>

-   <span data-ttu-id="8037b-446">1つのストリーミングサーバーから同時にアプリケーションパッケージをストリーミングするクライアントの数です。</span><span class="sxs-lookup"><span data-stu-id="8037b-446">The number of clients streaming application packages simultaneously from a single streaming server.</span></span>

-   <span data-ttu-id="8037b-447">ストリーミングされるパッケージのサイズ。</span><span class="sxs-lookup"><span data-stu-id="8037b-447">The size of the package being streamed.</span></span>

-   <span data-ttu-id="8037b-448">クライアントとストリーミングサーバー間の環境で利用可能なネットワーク帯域幅。</span><span class="sxs-lookup"><span data-stu-id="8037b-448">The available network bandwidth in your environment between the client and the streaming server.</span></span>

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8037b-449">シナリオ</span><span class="sxs-lookup"><span data-stu-id="8037b-449">Scenario</span></span></th>
<th align="left"><span data-ttu-id="8037b-450">まとめ</span><span class="sxs-lookup"><span data-stu-id="8037b-450">Summary</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8037b-451">複数の App-v 5.0 クライアントは、単一のストリーミングサーバーからアプリケーションを同時にストリーミングします。</span><span class="sxs-lookup"><span data-stu-id="8037b-451">Multiple App-V 5.0 clients stream applications from a single streaming server simultaneously.</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-452">同じサーバーから同時にストリーミングしているクライアントの数が増加すると、パッケージのダウンロード/ストリーミング時間との間に線形関係があります。</span><span class="sxs-lookup"><span data-stu-id="8037b-452">If the number of clients simultaneously streaming from the same server increases, there is a linear relationship with the package download/streaming time.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8037b-453">ストリーミングされるパッケージのサイズ。</span><span class="sxs-lookup"><span data-stu-id="8037b-453">Size of the package being streamed.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-454">パッケージサイズは、サイズが 1 GB の大きなパッケージのストリーミング/ダウンロード時間に大きな影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="8037b-454">The package size has a significant impact on the streaming/download time only for larger packages with a size ~ 1GB.</span></span> <span data-ttu-id="8037b-455">3 MB から 100 MB までのパッケージサイズの場合、ストリーミングの時間範囲は20秒から100秒までで、100の同時クライアントがあります。</span><span class="sxs-lookup"><span data-stu-id="8037b-455">For package sizes ranging from 3 MB to 100 MB, the streaming time ranges from 20 seconds to 100 seconds, with 100 simultaneous clients.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8037b-456">App-v 5.0 クライアントとストリーミングサーバー間のネットワーク。</span><span class="sxs-lookup"><span data-stu-id="8037b-456">Network between the App-V 5.0 client and the streaming server.</span></span></p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-457">低速ネットワーク (1.5 Mbps の帯域幅) では、LAN と比較した場合の応答時間が70-80% 増加しています (最大100ユーザー)。</span><span class="sxs-lookup"><span data-stu-id="8037b-457">Across a slow network (1.5 Mbps bandwidth), there is a 70-80% increase in response time compared to LAN (up to 100 users).</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="8037b-458">次の表は、前の一覧の各要素のサンプル値を示しています。</span><span class="sxs-lookup"><span data-stu-id="8037b-458">The following table displays sample values for each of the factors in the previous list:</span></span>

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8037b-459">シナリオ</span><span class="sxs-lookup"><span data-stu-id="8037b-459">Scenario</span></span></th>
<th align="left"><span data-ttu-id="8037b-460">バリエーション</span><span class="sxs-lookup"><span data-stu-id="8037b-460">Variation</span></span></th>
<th align="left"><span data-ttu-id="8037b-461">App-v 5.0 クライアントの数</span><span class="sxs-lookup"><span data-stu-id="8037b-461">Number of App-V 5.0 clients</span></span></th>
<th align="left"><span data-ttu-id="8037b-462">各パッケージのサイズ</span><span class="sxs-lookup"><span data-stu-id="8037b-462">Size of each package</span></span></th>
<th align="left"><span data-ttu-id="8037b-463">ネットワーク接続の種類のストリーミングサーバー/App-v 5.0 クライアント</span><span class="sxs-lookup"><span data-stu-id="8037b-463">Network connection type streaming server / App-V 5.0 client</span></span></th>
<th align="left"><span data-ttu-id="8037b-464">App-v 5.0 クライアントでのラウンドトリップ時間 (秒単位)</span><span class="sxs-lookup"><span data-stu-id="8037b-464">Round trip time on the App-V 5.0 client (in seconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8037b-465">複数の App-v 5.0 クライアントが、ストリーミングサーバーから仮想アプリケーションパッケージをストリーミングします。</span><span class="sxs-lookup"><span data-stu-id="8037b-465">Multiple App-V 5.0 clients streaming virtual application packages from a streaming server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8037b-466">クライアント数。</span><span class="sxs-lookup"><span data-stu-id="8037b-466">Number of clients.</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-467">100</span><span class="sxs-lookup"><span data-stu-id="8037b-467">100</span></span></p></li>
<li><p><span data-ttu-id="8037b-468">200</span><span class="sxs-lookup"><span data-stu-id="8037b-468">200</span></span></p></li>
<li><p><span data-ttu-id="8037b-469">1000</span><span class="sxs-lookup"><span data-stu-id="8037b-469">1000</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="8037b-470">100</span><span class="sxs-lookup"><span data-stu-id="8037b-470">100</span></span></p></li>
<li><p><span data-ttu-id="8037b-471">200</span><span class="sxs-lookup"><span data-stu-id="8037b-471">200</span></span></p></li>
<li><p><span data-ttu-id="8037b-472">1000</span><span class="sxs-lookup"><span data-stu-id="8037b-472">1000</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-473">3.5 MB</span><span class="sxs-lookup"><span data-stu-id="8037b-473">3.5 MB</span></span></p></li>
<li><p><span data-ttu-id="8037b-474">3.5 MB</span><span class="sxs-lookup"><span data-stu-id="8037b-474">3.5 MB</span></span></p></li>
<li><p><span data-ttu-id="8037b-475">3.5 MB</span><span class="sxs-lookup"><span data-stu-id="8037b-475">3.5 MB</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="8037b-476">5 MB</span><span class="sxs-lookup"><span data-stu-id="8037b-476">5 MB</span></span></p></li>
<li><p><span data-ttu-id="8037b-477">5 MB</span><span class="sxs-lookup"><span data-stu-id="8037b-477">5 MB</span></span></p></li>
<li><p><span data-ttu-id="8037b-478">5 MB</span><span class="sxs-lookup"><span data-stu-id="8037b-478">5 MB</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-479">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-479">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-480">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-480">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-481">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-481">LAN</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="8037b-482">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-482">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-483">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-483">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-484">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-484">LAN</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-485">29</span><span class="sxs-lookup"><span data-stu-id="8037b-485">29</span></span></p></li>
<li><p><span data-ttu-id="8037b-486">39</span><span class="sxs-lookup"><span data-stu-id="8037b-486">39</span></span></p></li>
<li><p><span data-ttu-id="8037b-487">391</span><span class="sxs-lookup"><span data-stu-id="8037b-487">391</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="8037b-488">35</span><span class="sxs-lookup"><span data-stu-id="8037b-488">35</span></span></p></li>
<li><p><span data-ttu-id="8037b-489">68</span><span class="sxs-lookup"><span data-stu-id="8037b-489">68</span></span></p></li>
<li><p><span data-ttu-id="8037b-490">461</span><span class="sxs-lookup"><span data-stu-id="8037b-490">461</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8037b-491">ストリーミングされる各パッケージのサイズ。</span><span class="sxs-lookup"><span data-stu-id="8037b-491">Size of each package being streamed.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8037b-492">各パッケージのサイズ。</span><span class="sxs-lookup"><span data-stu-id="8037b-492">Size of each package.</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-493">100</span><span class="sxs-lookup"><span data-stu-id="8037b-493">100</span></span></p></li>
<li><p><span data-ttu-id="8037b-494">200</span><span class="sxs-lookup"><span data-stu-id="8037b-494">200</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="8037b-495">100</span><span class="sxs-lookup"><span data-stu-id="8037b-495">100</span></span></p></li>
<li><p><span data-ttu-id="8037b-496">200</span><span class="sxs-lookup"><span data-stu-id="8037b-496">200</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-497">21 MB</span><span class="sxs-lookup"><span data-stu-id="8037b-497">21 MB</span></span></p></li>
<li><p><span data-ttu-id="8037b-498">21 MB</span><span class="sxs-lookup"><span data-stu-id="8037b-498">21 MB</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="8037b-499">109</span><span class="sxs-lookup"><span data-stu-id="8037b-499">109</span></span></p></li>
<li><p><span data-ttu-id="8037b-500">109</span><span class="sxs-lookup"><span data-stu-id="8037b-500">109</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-501">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-501">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-502">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-502">LAN</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="8037b-503">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-503">LAN</span></span></p></li>
<li><p><span data-ttu-id="8037b-504">LAN</span><span class="sxs-lookup"><span data-stu-id="8037b-504">LAN</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<p><span data-ttu-id="8037b-505">33</span><span class="sxs-lookup"><span data-stu-id="8037b-505">33</span></span></p>
<p><span data-ttu-id="8037b-506">83</span><span class="sxs-lookup"><span data-stu-id="8037b-506">83</span></span></p>
<p></p>
<p><span data-ttu-id="8037b-507">100</span><span class="sxs-lookup"><span data-stu-id="8037b-507">100</span></span></p>
<p><span data-ttu-id="8037b-508">160</span><span class="sxs-lookup"><span data-stu-id="8037b-508">160</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8037b-509">クライアントと App-v 5.0 ストリーミングサーバー間のネットワーク接続。</span><span class="sxs-lookup"><span data-stu-id="8037b-509">Network connection between client and App-V 5.0 streaming server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8037b-510">1.5 Mbps 低速リンクネットワーク。</span><span class="sxs-lookup"><span data-stu-id="8037b-510">1.5 Mbps Slow link network.</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-511">100</span><span class="sxs-lookup"><span data-stu-id="8037b-511">100</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="8037b-512">100</span><span class="sxs-lookup"><span data-stu-id="8037b-512">100</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-513">3.5 MB</span><span class="sxs-lookup"><span data-stu-id="8037b-513">3.5 MB</span></span></p></li>
<li><p></p></li>
<li><p><span data-ttu-id="8037b-514">5 MB</span><span class="sxs-lookup"><span data-stu-id="8037b-514">5 MB</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="8037b-515">1.5 Mbps の大陸内ネットワーク</span><span class="sxs-lookup"><span data-stu-id="8037b-515">1.5 Mbps Intra-Continental Network</span></span></p></li>
</ul></td>
<td align="left"><p></p>
<p><span data-ttu-id="8037b-516">102</span><span class="sxs-lookup"><span data-stu-id="8037b-516">102</span></span></p>
<p></p>
<p><span data-ttu-id="8037b-517">121</span><span class="sxs-lookup"><span data-stu-id="8037b-517">121</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="8037b-518">各 App-v 5.0 ストリーミングサーバーは、仮想化されたアプリケーションを同時にストリーミングする少なくとも200クライアントを処理できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8037b-518">Each App-V 5.0 streaming server should be able to handle a minimum of 200 clients concurrently streaming virtualized applications.</span></span>

<span data-ttu-id="8037b-519">**注** ストリームにかかる実際の時間は、主に、同時にストリーミングしているクライアント数、パッケージ数、パッケージサイズ、サーバーのネットワークアクティビティ、ネットワークの状態によって決まります。</span><span class="sxs-lookup"><span data-stu-id="8037b-519">**Note** The actual time to it will take to stream is determined primarily by the number of clients streaming simultaneously, number of packages, package size, the server’s network activity, and network conditions.</span></span>

 

<span data-ttu-id="8037b-520">たとえば、平均ユーザーは 100 MB のパッケージを2分未満でストリーミングできます。これは、100の同時クライアントがサーバーからストリーミングしている場合です。</span><span class="sxs-lookup"><span data-stu-id="8037b-520">For example, an average user can stream a 100 MB package in less than 2 minutes, when 100 simultaneous clients are streaming from the server.</span></span> <span data-ttu-id="8037b-521">ただし、サイズが 1 GB のパッケージは、最大30分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="8037b-521">However, a package of size 1 GB could take up to 30 minutes.</span></span> <span data-ttu-id="8037b-522">ほとんどの実際の環境では、ストリーミング需要は一律配布されていません。必要なストリーミングサーバの数を正しくサイズ指定するために、お客様の環境に存在するおおよそのピークストリーミング要件を理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="8037b-522">In most real world environments streaming demand is not uniformly distributed, you will need to understand the approximate peak streaming requirements present in your environment in order to properly size the number of required streaming servers.</span></span>

<span data-ttu-id="8037b-523">アプリケーションを事前にキャッシュしておくと、ストリーミングサーバーがサポートできるクライアントの数が大きくなり、ピークストリーミングの要件が小さくなります。</span><span class="sxs-lookup"><span data-stu-id="8037b-523">The number of clients a streaming server can support can be significantly increased and the peak streaming requirements reduced if you pre-cache your applications.</span></span> <span data-ttu-id="8037b-524">オンデマンドストリーミング配信とストリーム最適化されたパッケージを使用して、ストリーミングサーバーがサポートできるクライアントの数を増やすこともできます。</span><span class="sxs-lookup"><span data-stu-id="8037b-524">You can also increase the number of clients a streaming server can support by using on-demand streaming delivery and stream optimized packages.</span></span>

## <span data-ttu-id="8037b-525">App-v 5.0 サーバーロールの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="8037b-525">Combining App-V 5.0 Server Roles</span></span>


<span data-ttu-id="8037b-526">割引のスケーリングとフォールトトレランスの要件: Active Directory への接続がある場所に必要なサーバーの最小数は1です。</span><span class="sxs-lookup"><span data-stu-id="8037b-526">Discounting scaling and fault-tolerance requirements, the minimum number of servers needed for a location with connectivity to Active Directory is one.</span></span> <span data-ttu-id="8037b-527">このサーバーは、管理サーバー、管理サーバーサービス、Microsoft SQL Server の役割をホストします。</span><span class="sxs-lookup"><span data-stu-id="8037b-527">This server will host the management server, management server service, and Microsoft SQL Server roles.</span></span> <span data-ttu-id="8037b-528">したがって、サーバーの役割は、互いに競合しないため、任意の組み合わせで配置することができます。</span><span class="sxs-lookup"><span data-stu-id="8037b-528">Server roles, therefore, can be arranged in any desired combination since they do not conflict with one another.</span></span>

<span data-ttu-id="8037b-529">スケーリング要件を無視すると、フォールトトレラントな実装を提供するために必要なサーバーの最小数は4です。</span><span class="sxs-lookup"><span data-stu-id="8037b-529">Ignoring scaling requirements, the minimum number of servers necessary to provide a fault-tolerant implementation is four.</span></span> <span data-ttu-id="8037b-530">管理サーバーと Microsoft SQL Server の役割は、フォールトトレラント構成に配置されています。</span><span class="sxs-lookup"><span data-stu-id="8037b-530">The management server, and Microsoft SQL Server roles support being placed in fault-tolerant configurations.</span></span> <span data-ttu-id="8037b-531">管理サーバーサービスは、いずれのロールとも組み合わせることができますが、単一点障害のままです。</span><span class="sxs-lookup"><span data-stu-id="8037b-531">The management server service can be combined with any of the roles, but remains a single point of failure.</span></span>

<span data-ttu-id="8037b-532">フォールトトレランスの戦略とテクノロジはいくつでも提供されていますが、特定のサービスに適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="8037b-532">Although there are a number of fault-tolerance strategies and technologies available, not all are applicable to a given service.</span></span> <span data-ttu-id="8037b-533">さらに、App-v 5.0 ロールが結合されている場合、非互換性のために一部のフォールトトレランスオプションが適用されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="8037b-533">Additionally, if App-V 5.0 roles are combined, certain fault-tolerance options may no longer apply due to incompatibilities.</span></span>






## <span data-ttu-id="8037b-534">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8037b-534">Related topics</span></span>


[<span data-ttu-id="8037b-535">App-V 5.0 でサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="8037b-535">App-V 5.0 Supported Configurations</span></span>](app-v-50-supported-configurations.md)

[<span data-ttu-id="8037b-536">App-V 5.0 の高可用性の計画</span><span class="sxs-lookup"><span data-stu-id="8037b-536">Planning for High Availability with App-V 5.0</span></span>](planning-for-high-availability-with-app-v-50.md)

[<span data-ttu-id="8037b-537">App-V の展開計画</span><span class="sxs-lookup"><span data-stu-id="8037b-537">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v.md)

 

 





