---
title: APP-V の以前のバージョンからの移行計画
description: APP-V の以前のバージョンからの移行計画
author: dansimp
ms.assetid: d4ca8f09-86fd-456f-8ec2-242ff94ae9a0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 2242f58a29473e116506ec013b94a79d1bb814a6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813474"
---
# <span data-ttu-id="9b8b2-103">APP-V の以前のバージョンからの移行計画</span><span class="sxs-lookup"><span data-stu-id="9b8b2-103">Planning for Migrating from a Previous Version of App-V</span></span>


<span data-ttu-id="9b8b2-104">以前のバージョンの App-v から App-v 5.0 に移行する方法については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-104">Use the following information to plan how to migrate to App-V 5.0 from previous versions of App-V.</span></span>

## <span data-ttu-id="9b8b2-105">移行の要件</span><span class="sxs-lookup"><span data-stu-id="9b8b2-105">Migration requirements</span></span>


<span data-ttu-id="9b8b2-106">アップグレードを開始する前に、次の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-106">Before you start any upgrades, review the following requirements:</span></span>

-   <span data-ttu-id="9b8b2-107">App-v 4.6 SP2 より前のバージョンからアップグレードする場合は、まずバージョンアプリ-V 4.6 SP3 にアップグレードしてから、App-v 5.0 以降にアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-107">If you are upgrading from a version earlier than App-V 4.6 SP2, upgrade to version App-V 4.6 SP3 first before upgrading to App-V 5.0 or later.</span></span> <span data-ttu-id="9b8b2-108">このシナリオでは、最初に App-v クライアントをアップグレードし、次にサーバーコンポーネントをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-108">In this scenario, upgrade the App-V clients first, and then upgrade the server components.</span></span>
<span data-ttu-id="9b8b2-109">**注:** App-v 4.6 は、メインストリームサポートを終了しました。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-109">**Note:** App-V 4.6 has exited Mainstream support.</span></span>

-   <span data-ttu-id="9b8b2-110">App-v 5.0 は、App-v 5.0 を使って作成されたパッケージ、または App-v 5.0 (**appv**) 形式に変換されたパッケージのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-110">App-V 5.0 supports only packages that are created using App-V 5.0, or packages that have been converted to the App-V 5.0 (**.appv**) format.</span></span>

-   <span data-ttu-id="9b8b2-111">App-v 5.0 SP3 のみ: app-v Server を App-v 5.0 SP1 からアップグレードする場合は、手順については、「 [app-v 5.0 SP3 につい](about-app-v-50-sp3.md#bkmk-migrate-to-50sp3)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-111">App-V 5.0 SP3 only: If you are upgrading the App-V Server from App-V 5.0 SP1, see [About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-migrate-to-50sp3) for instructions.</span></span>

## <span data-ttu-id="9b8b2-112">App-v 4.6 を使って app-v 5.0 クライアントを同時に実行する</span><span class="sxs-lookup"><span data-stu-id="9b8b2-112">Running the App-V 5.0 client concurrently with App-V 4.6</span></span>


<span data-ttu-id="9b8b2-113">App-v 5.0 クライアントは、app-v 4.6 SP3 クライアントと同じコンピューターで同時に実行できます。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-113">You can run the App-V 5.0 client concurrently on the same computer with the App-V4.6SP3 client.</span></span>

<span data-ttu-id="9b8b2-114">共存する App-v クライアントを実行する場合は、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-114">When you run coexisting App-V clients, you can:</span></span>

-   <span data-ttu-id="9b8b2-115">両方のクライアントを実行している場合は、App-v 4.6 SP3 パッケージを App-v 5.0 形式に変換し、両方のパッケージを公開します。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-115">Convert an App-V 4.6 SP3 package to the App-V 5.0 format and publish both packages, when you have both clients running.</span></span>

-   <span data-ttu-id="9b8b2-116">変換されたパッケージの移行ポリシーを定義します。これにより、変換された App-v 5.0 パッケージでは、ファイルの種類の関連付けと、App-v 4.6 パッケージのショートカットが想定されます。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-116">Define the migration policy for the converted package, which allows the converted App-V 5.0 package to assume the file type associations and shortcuts from the App-V 4.6 package.</span></span>

### <span data-ttu-id="9b8b2-117">サポートされている共存シナリオ</span><span class="sxs-lookup"><span data-stu-id="9b8b2-117">Supported coexistence scenarios</span></span>

<span data-ttu-id="9b8b2-118">次の表は、サポートされている App-v の共存シナリオを示しています。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-118">The following table shows the supported App-V coexistence scenarios.</span></span> <span data-ttu-id="9b8b2-119">共存クライアントを実行している場合は、特定のリリースの最新の利用可能な更新プログラムをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-119">We recommend that you install the latest available updates of a given release when you are running coexisting clients.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9b8b2-120">App-v 4.6 クライアントの種類</span><span class="sxs-lookup"><span data-stu-id="9b8b2-120">App-V 4.6 client type</span></span></th>
<th align="left"><span data-ttu-id="9b8b2-121">App-v 5.0 クライアントの種類</span><span class="sxs-lookup"><span data-stu-id="9b8b2-121">App-V 5.0 client type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9b8b2-122">App-v 4.6 SP3</span><span class="sxs-lookup"><span data-stu-id="9b8b2-122">App-V 4.6 SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="9b8b2-123">App-v 5.0</span><span class="sxs-lookup"><span data-stu-id="9b8b2-123">App-V 5.0</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9b8b2-124">App-v 4.6 SP3 RDS</span><span class="sxs-lookup"><span data-stu-id="9b8b2-124">App-V 4.6 SP3 RDS</span></span></p></td>
<td align="left"><p><span data-ttu-id="9b8b2-125">App-v 5.0 RDS</span><span class="sxs-lookup"><span data-stu-id="9b8b2-125">App-V 5.0 RDS</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="9b8b2-126">共存クライアントを実行するための要件</span><span class="sxs-lookup"><span data-stu-id="9b8b2-126">Requirements for running coexisting clients</span></span>

<span data-ttu-id="9b8b2-127">共存クライアントを実行するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-127">To run coexisting clients, you must:</span></span>

-   <span data-ttu-id="9b8b2-128">App-v 5.0 クライアントをインストールする前に、app-v 4.6 クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-128">Install the App-V4.6 client before you install the App-V 5.0 client.</span></span>

-   <span data-ttu-id="9b8b2-129">[**移行モードを有効にする**] グループポリシー設定を有効にします。これは、 **app-v** Client の [ &gt; **共存**] ノードにあります。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-129">Enable the **Enable Migration Mode** Group Policy setting, which is in the **App-V** &gt; **Client Coexistence** node.</span></span> <span data-ttu-id="9b8b2-130">Admx テンプレートの展開を取得するには、「 [MDOP グループポリシー (admx) テンプレートをダウンロードして展開する方法](https://technet.microsoft.com/library/dn659707.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-130">To get the deploy the .admx template, see [How to Download and Deploy MDOP Group Policy (.admx) Templates](https://technet.microsoft.com/library/dn659707.aspx).</span></span>

### <span data-ttu-id="9b8b2-131">クライアントのダウンロードとドキュメント</span><span class="sxs-lookup"><span data-stu-id="9b8b2-131">Client downloads and documentation</span></span>

<span data-ttu-id="9b8b2-132">次の表は、リリースに関する TechNet のドキュメントへのリンクを示しています。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-132">The following table provides link to the TechNet documentation about the releases.</span></span> <span data-ttu-id="9b8b2-133">App-v クライアントに関する TechNet ドキュメントは、特に指定がない限り、両方のクライアントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-133">The TechNet documentation about the App-V client applies to both clients, unless stated otherwise.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9b8b2-134">App-v のバージョン</span><span class="sxs-lookup"><span data-stu-id="9b8b2-134">App-V version</span></span></th>
<th align="left"><span data-ttu-id="9b8b2-135">TechNet のドキュメントへのリンク</span><span class="sxs-lookup"><span data-stu-id="9b8b2-135">Link to TechNet documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9b8b2-136">App-v 4.6 SP3</span><span class="sxs-lookup"><span data-stu-id="9b8b2-136">App-V 4.6SP3</span></span></p></td>
<td align="left"><p><a href="https://technet.microsoft.com/library/dn511019.aspx" data-raw-source="[About Microsoft Application Virtualization 4.6 SP3](https://technet.microsoft.com/library/dn511019.aspx)"><span data-ttu-id="9b8b2-137">Microsoft Application Virtualization 4.6 SP3 について</span><span class="sxs-lookup"><span data-stu-id="9b8b2-137">About Microsoft Application Virtualization 4.6 SP3</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9b8b2-138">App-v 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="9b8b2-138">App-V 5.0SP3</span></span></p></td>
<td align="left"><p><a href="about-app-v-50-sp3.md" data-raw-source="[About Microsoft Application Virtualization 5.0 SP3](about-app-v-50-sp3.md)"><span data-ttu-id="9b8b2-139">Microsoft Application Virtualization 5.0 SP3 について</span><span class="sxs-lookup"><span data-stu-id="9b8b2-139">About Microsoft Application Virtualization 5.0 SP3</span></span></a></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="9b8b2-140">App-v 5.0 クライアントの共存を構成する方法の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-140">For more information about how to configure App-V 5.0 client coexistence, see:</span></span>

-   [<span data-ttu-id="9b8b2-141">同じコンピューター上に App-v 4.6 と App-v 5.0 クライアントを展開する方法</span><span class="sxs-lookup"><span data-stu-id="9b8b2-141">How to Deploy the App-V 4.6 and the App-V 5.0 Client on the Same Computer</span></span>](how-to-deploy-the-app-v-46-and-the-app-v--50-client-on-the-same-computer.md)

-   [<span data-ttu-id="9b8b2-142">App-v 5.0 の共存と移行</span><span class="sxs-lookup"><span data-stu-id="9b8b2-142">App-V 5.0 Coexistence and Migration</span></span>](https://technet.microsoft.com/windows/jj835811.aspx)

## <a href="" id="converting--previous-version--packages-using-the-package-converter-"></a><span data-ttu-id="9b8b2-143">パッケージコンバーターを使用した "以前のバージョン" パッケージの変換</span><span class="sxs-lookup"><span data-stu-id="9b8b2-143">Converting “previous-version” packages using the package converter</span></span>


<span data-ttu-id="9b8b2-144">App-v 4.6 SP3 以前のバージョンを使用して作成されたパッケージを App-v 5.0 に移行する前に、次の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-144">Before migrating a package, created using App-V4.6SP3 or earlier, to App-V 5.0, review the following requirements:</span></span>

-   <span data-ttu-id="9b8b2-145">パッケージを**appv**ファイル形式に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-145">You must convert the package to the **.appv** file format.</span></span>

-   <span data-ttu-id="9b8b2-146">パッケージコンバーターは、App-v 4.5 以降を使って作成されたパッケージの直接変換のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-146">The Package Converter supports only the direct conversion of packages that were created by using App-V 4.5 and later.</span></span> <span data-ttu-id="9b8b2-147">以前のバージョンを使用して作成されたパッケージに対してパッケージコンバーターを使用するには、パッケージをアップグレードするために、アプリ-V 4.5 以降の sequencer を使用する必要があります。その後、パッケージの変換を実行できます。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-147">To use the package converter on a package that was created using a previous version, you must use an App-V4.5 or later version of the sequencer to upgrade the package, and then you can perform the package conversion.</span></span>

<span data-ttu-id="9b8b2-148">パッケージコンバーターを使ったパッケージの変換について詳しくは、「[以前のバージョンの app-v で作成されたパッケージを変換する方法](how-to-convert-a-package-created-in-a-previous-version-of-app-v.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-148">For more information about using the package converter to convert a package, see [How to Convert a Package Created in a Previous Version of App-V](how-to-convert-a-package-created-in-a-previous-version-of-app-v.md).</span></span> <span data-ttu-id="9b8b2-149">ファイルを変換した後は、App-v 5.0 クライアントを実行するターゲットコンピューターに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="9b8b2-149">After you convert the file, you can deploy it to target computers that run the App-V 5.0 client.</span></span>






## <span data-ttu-id="9b8b2-150">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9b8b2-150">Related topics</span></span>


[<span data-ttu-id="9b8b2-151">App-V の展開計画</span><span class="sxs-lookup"><span data-stu-id="9b8b2-151">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v.md)

 

 





