---
title: 以前のバージョンから APP-V 5.1 への移行
description: 以前のバージョンから APP-V 5.1 への移行
author: dansimp
ms.assetid: e7ee0edc-7544-4c0a-aaca-d922a33bc1bb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7fb6ddbfed4f6fd1ae9613d2ee86361a51918a65
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813554"
---
# <span data-ttu-id="6e956-103">以前のバージョンから APP-V 5.1 への移行</span><span class="sxs-lookup"><span data-stu-id="6e956-103">Migrating to App-V 5.1 from a Previous Version</span></span>


<span data-ttu-id="6e956-104">Microsoft Application Virtualization (App-v) 5.1 を使用すると、既存のアプリ-V 4.6 または App-v 5.0 インフラストラクチャを、より柔軟かつ統合化され、より簡単に5.1 管理することができます。</span><span class="sxs-lookup"><span data-stu-id="6e956-104">With Microsoft Application Virtualization (App-V) 5.1, you can migrate your existing App-V 4.6 or App-V 5.0 infrastructure to the more flexible, integrated, and easier to manage App-V 5.1 infrastructure.</span></span>
<span data-ttu-id="6e956-105">ただし、App-v から app-v 5.1 に直接移行することはできません。最初に App-v 5.0 に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e956-105">However, you cannot migrate directly from App-V 4.x to App-V 5.1, you must migrate to App-V 5.0 first.</span></span> <span data-ttu-id="6e956-106">App-v から app-v への移行の詳細については、「[以前のバージョンから移行](migrating-from-a-previous-version-app-v-50.md)5.0 する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e956-106">For more information on migrating from App-V 4.x to App-V 5.0, see [Migrating from a Previous Version](migrating-from-a-previous-version-app-v-50.md)</span></span>  

<span data-ttu-id="6e956-107">**注** App-v 5.1 パッケージは、app-v 5.0 パッケージとまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="6e956-107">**Note** App-V 5.1 packages are exactly the same as App-V 5.0 packages.</span></span> <span data-ttu-id="6e956-108">バージョン間のパッケージ形式は変更されていないため、App-v 5.0 パッケージを App-v 5.1 パッケージに変換する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6e956-108">There has been no change in the package format between the versions and therefore, there is no need to convert App-V 5.0 packages to App-V 5.1 packages.</span></span>

<span data-ttu-id="6e956-109">App-v 4.6 と App-v 5.1 の違いの詳細については、「 [app-v 5.0 について](about-app-v-50.md)」の「app-v **4.6 と app-v 5.0」セクション**を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e956-109">For more information about the differences between App-V 4.6 and App-V 5.1, see the **Differences between App-V 4.6 and App-V 5.0 section** of [About App-V 5.0](about-app-v-50.md).</span></span>

 

## <a href="" id="bkmk-pkgconvimprove"></a><span data-ttu-id="6e956-110">App-v 5.1 パッケージコンバーターの改善</span><span class="sxs-lookup"><span data-stu-id="6e956-110">Improvements to the App-V 5.1 Package Converter</span></span>


<span data-ttu-id="6e956-111">これで、パッケージコンバーターを使用して、スクリプトを含む App-v 4.6 パッケージ、ソースからのレジストリ情報とスクリプトをパッケージコンバーター出力に含めることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6e956-111">You can now use the package converter to convert App-V 4.6 packages that contain scripts, and registry information and scripts from source .osd files are now included in package converter output.</span></span>

<span data-ttu-id="6e956-112">また、この `–OSDsToIncludeInPackage` パラメーターをコマンドレットと共に使用して、 `ConvertFrom-AppvLegacyPackage` どの .osd ファイルの情報が変換され、新しいパッケージ内に配置されるかを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e956-112">You can also use the `–OSDsToIncludeInPackage` parameter with the `ConvertFrom-AppvLegacyPackage` cmdlet to specify which .osd files’ information is converted and placed within the new package.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6e956-113">アプリの新バージョン-V 5.1</span><span class="sxs-lookup"><span data-stu-id="6e956-113">New in App-V 5.1</span></span></th>
<th align="left"><span data-ttu-id="6e956-114">App-v 5.1 より前</span><span class="sxs-lookup"><span data-stu-id="6e956-114">Prior to App-V 5.1</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e956-115">新しい .xml ファイルは、パッケージに関連付けられている .osd ファイルに対応して作成されます。これらのファイルには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6e956-115">New .xml files are created corresponding to the .osd files associated with a package; these files include the following information:</span></span></p>
<ul>
<li><p><span data-ttu-id="6e956-116">環境変数</span><span class="sxs-lookup"><span data-stu-id="6e956-116">environment variables</span></span></p></li>
<li><p><span data-ttu-id="6e956-117">ショートカット</span><span class="sxs-lookup"><span data-stu-id="6e956-117">shortcuts</span></span></p></li>
<li><p><span data-ttu-id="6e956-118">ファイルの種類の関連付け</span><span class="sxs-lookup"><span data-stu-id="6e956-118">file type associations</span></span></p></li>
<li><p><span data-ttu-id="6e956-119">レジストリ情報</span><span class="sxs-lookup"><span data-stu-id="6e956-119">registry information</span></span></p></li>
<li><p><span data-ttu-id="6e956-120">スクリプト</span><span class="sxs-lookup"><span data-stu-id="6e956-120">scripts</span></span></p></li>
</ul>
<p><span data-ttu-id="6e956-121">ソースディレクトリの .osd ファイルのサブセットから、パラメーターを使ってパッケージに情報を追加することができるようになりました <code>-OSDsToIncludeInPackage</code> 。</span><span class="sxs-lookup"><span data-stu-id="6e956-121">You can now choose to add information from a subset of the .osd files in the source directory to the package using the <code>-OSDsToIncludeInPackage</code> parameter.</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e956-122">パッケージに関連付けられている .osd ファイルに含まれているレジストリ情報とスクリプトは、パッケージコンバーター出力に含まれていませんでした。</span><span class="sxs-lookup"><span data-stu-id="6e956-122">Registry information and scripts included in .osd files associated with a package were not included in package converter output.</span></span></p>
<p><span data-ttu-id="6e956-123">パッケージコンバーターは、新しいパッケージに、ソースディレクトリ内のすべての .osd ファイルからの情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="6e956-123">The package converter would populate the new package with information from all of the .osd files in the source directory.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="6e956-124">変換ステートメントの例</span><span class="sxs-lookup"><span data-stu-id="6e956-124">Example conversion statement</span></span>

<span data-ttu-id="6e956-125">新しいプロセスについて理解するには、次のパッケージコンバータステートメントの例を確認し `ConvertFrom-AppvLegacyPackage` ます。</span><span class="sxs-lookup"><span data-stu-id="6e956-125">To understand the new process, review the following example `ConvertFrom-AppvLegacyPackage` package converter statement.</span></span>

**<span data-ttu-id="6e956-126">ソースディレクトリ (\\\\OldPkgStore\\ContosoApp) には、次のものが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e956-126">If the source directory (\\\\OldPkgStore\\ContosoApp) includes the following:</span></span>**

-   <span data-ttu-id="6e956-127">ContosoApp</span><span class="sxs-lookup"><span data-stu-id="6e956-127">ContosoApp.sft</span></span>

-   <span data-ttu-id="6e956-128">ContosoApp.msi</span><span class="sxs-lookup"><span data-stu-id="6e956-128">ContosoApp.msi</span></span>

-   <span data-ttu-id="6e956-129">ContosoApp.sprj</span><span class="sxs-lookup"><span data-stu-id="6e956-129">ContosoApp.sprj</span></span>

-   <span data-ttu-id="6e956-130">ContosoApp\_manifest.xml</span><span class="sxs-lookup"><span data-stu-id="6e956-130">ContosoApp\_manifest.xml</span></span>

-   <span data-ttu-id="6e956-131">X. osd</span><span class="sxs-lookup"><span data-stu-id="6e956-131">X.osd</span></span>

-   <span data-ttu-id="6e956-132">Y .osd</span><span class="sxs-lookup"><span data-stu-id="6e956-132">Y.osd</span></span>

-   <span data-ttu-id="6e956-133">Z-.osd</span><span class="sxs-lookup"><span data-stu-id="6e956-133">Z.osd</span></span>

**<span data-ttu-id="6e956-134">このコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6e956-134">And you run this command:</span></span>**

``` syntax
ConvertFrom-AppvLegacyPackage –SourcePath \\OldPkgStore\ContosoApp\ 
-DestinationPath \\NewPkgStore\ContosoApp\
-OSDsToIncludeInPackage X.osd,Y.osd
```

**<span data-ttu-id="6e956-135">以下は、移行先ディレクトリ (\\\\NewPkgStore\\ContosoApp) で作成されます。</span><span class="sxs-lookup"><span data-stu-id="6e956-135">The following is created in the destination directory (\\\\NewPkgStore\\ContosoApp):</span></span>**

-   <span data-ttu-id="6e956-136">ContosoApp</span><span class="sxs-lookup"><span data-stu-id="6e956-136">ContosoApp.appv</span></span>

-   <span data-ttu-id="6e956-137">ContosoApp.msi</span><span class="sxs-lookup"><span data-stu-id="6e956-137">ContosoApp.msi</span></span>

-   <span data-ttu-id="6e956-138">ContosoApp\_DeploymentConfig.xml</span><span class="sxs-lookup"><span data-stu-id="6e956-138">ContosoApp\_DeploymentConfig.xml</span></span>

-   <span data-ttu-id="6e956-139">ContosoApp\_UserConfig.xml</span><span class="sxs-lookup"><span data-stu-id="6e956-139">ContosoApp\_UserConfig.xml</span></span>

-   <span data-ttu-id="6e956-140">X\_Config.xml</span><span class="sxs-lookup"><span data-stu-id="6e956-140">X\_Config.xml</span></span>

-   <span data-ttu-id="6e956-141">Y\_Config.xml</span><span class="sxs-lookup"><span data-stu-id="6e956-141">Y\_Config.xml</span></span>

-   <span data-ttu-id="6e956-142">Z\_Config.xml</span><span class="sxs-lookup"><span data-stu-id="6e956-142">Z\_Config.xml</span></span>

**<span data-ttu-id="6e956-143">上の例では、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6e956-143">In the above example:</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6e956-144">これらのソースディレクトリファイル...</span><span class="sxs-lookup"><span data-stu-id="6e956-144">These Source directory files…</span></span></th>
<th align="left"><span data-ttu-id="6e956-145">...は、次の宛先ディレクトリファイルに変換されます...</span><span class="sxs-lookup"><span data-stu-id="6e956-145">…are converted to these Destination directory files…</span></span></th>
<th align="left"><span data-ttu-id="6e956-146">...これらのアイテムは</span><span class="sxs-lookup"><span data-stu-id="6e956-146">…and will contain these items</span></span></th>
<th align="left"><span data-ttu-id="6e956-147">説明</span><span class="sxs-lookup"><span data-stu-id="6e956-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><ul>
<li><p><span data-ttu-id="6e956-148">X. osd</span><span class="sxs-lookup"><span data-stu-id="6e956-148">X.osd</span></span></p></li>
<li><p><span data-ttu-id="6e956-149">Y .osd</span><span class="sxs-lookup"><span data-stu-id="6e956-149">Y.osd</span></span></p></li>
<li><p><span data-ttu-id="6e956-150">Z-.osd</span><span class="sxs-lookup"><span data-stu-id="6e956-150">Z.osd</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="6e956-151">X_Config.xml</span><span class="sxs-lookup"><span data-stu-id="6e956-151">X_Config.xml</span></span></p></li>
<li><p><span data-ttu-id="6e956-152">Y_Config.xml</span><span class="sxs-lookup"><span data-stu-id="6e956-152">Y_Config.xml</span></span></p></li>
<li><p><span data-ttu-id="6e956-153">Z_Config.xml</span><span class="sxs-lookup"><span data-stu-id="6e956-153">Z_Config.xml</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="6e956-154">環境変数</span><span class="sxs-lookup"><span data-stu-id="6e956-154">Environment variables</span></span></p></li>
<li><p><span data-ttu-id="6e956-155">ショートカット</span><span class="sxs-lookup"><span data-stu-id="6e956-155">Shortcuts</span></span></p></li>
<li><p><span data-ttu-id="6e956-156">ファイルの種類の関連付け</span><span class="sxs-lookup"><span data-stu-id="6e956-156">File type associations</span></span></p></li>
<li><p><span data-ttu-id="6e956-157">レジストリ情報</span><span class="sxs-lookup"><span data-stu-id="6e956-157">Registry information</span></span></p></li>
<li><p><span data-ttu-id="6e956-158">スクリプト</span><span class="sxs-lookup"><span data-stu-id="6e956-158">Scripts</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="6e956-159">各 .osd ファイルは、ここに記載されている項目を含む、個別の .xml ファイルに変換されます。これらのファイルは、ここに記載されているアプリ-V 5.1 展開構成形式になっています。</span><span class="sxs-lookup"><span data-stu-id="6e956-159">Each .osd file is converted to a separate, corresponding .xml file that contains the items listed here in App-V 5.1 deployment configuration format.</span></span> <span data-ttu-id="6e956-160">これらの項目は、必要に応じて、これらの .xml ファイルからコピーし、展開構成またはユーザー構成ファイルに配置することができます。</span><span class="sxs-lookup"><span data-stu-id="6e956-160">These items can then be copied from these .xml files and placed in the deployment configuration or user configuration files as desired.</span></span></p>
<p><span data-ttu-id="6e956-161">この例には、ソースディレクトリの3つの .osd ファイルに対応する3つの .xml ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="6e956-161">In this example, there are three .xml files, corresponding with the three .osd files in the source directory.</span></span> <span data-ttu-id="6e956-162">各 .xml ファイルには、環境変数、ショートカット、ファイルの種類の関連付け、レジストリ情報、スクリプトが含まれており、対応する .osd ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e956-162">Each .xml file contains the environment variables, shortcuts, file type associations, registry information, and scripts in its corresponding .osd file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><ul>
<li><p><span data-ttu-id="6e956-163">X. osd</span><span class="sxs-lookup"><span data-stu-id="6e956-163">X.osd</span></span></p></li>
<li><p><span data-ttu-id="6e956-164">Y .osd</span><span class="sxs-lookup"><span data-stu-id="6e956-164">Y.osd</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="6e956-165">ContosoApp</span><span class="sxs-lookup"><span data-stu-id="6e956-165">ContosoApp.appv</span></span></p></li>
<li><p><span data-ttu-id="6e956-166">ContosoApp_DeploymentConfig.xml</span><span class="sxs-lookup"><span data-stu-id="6e956-166">ContosoApp_DeploymentConfig.xml</span></span></p></li>
<li><p><span data-ttu-id="6e956-167">ContosoApp_UserConfig.xml</span><span class="sxs-lookup"><span data-stu-id="6e956-167">ContosoApp_UserConfig.xml</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="6e956-168">環境変数</span><span class="sxs-lookup"><span data-stu-id="6e956-168">Environment variables</span></span></p></li>
<li><p><span data-ttu-id="6e956-169">ショートカット</span><span class="sxs-lookup"><span data-stu-id="6e956-169">Shortcuts</span></span></p></li>
<li><p><span data-ttu-id="6e956-170">ファイルの種類の関連付け</span><span class="sxs-lookup"><span data-stu-id="6e956-170">File type associations</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="6e956-171">パラメーターで指定された .osd ファイルからの情報 <code>-OSDsToIncludeInPackage</code> が変換され、パッケージ内に配置されます。</span><span class="sxs-lookup"><span data-stu-id="6e956-171">The information from the .osd files specified in the <code>-OSDsToIncludeInPackage</code> parameter are converted and placed inside the package.</span></span> <span data-ttu-id="6e956-172">次に、コンバーターは展開構成ファイルとユーザー構成ファイルにパッケージの内容を設定します。これは、新しいパッケージの順序付けの場合と同様です。</span><span class="sxs-lookup"><span data-stu-id="6e956-172">The converter then populates the deployment configuration file and the user configuration file with the contents of the package, just as App-V Sequencer does when sequencing a new package.</span></span></p>
<p><span data-ttu-id="6e956-173">この例では、環境変数、ショートカット、およびファイルの種類の関連付けが X. .osd と Y パッケージに含まれており、これらの情報の一部も展開構成ファイルとユーザー構成ファイルに含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e956-173">In this example, environment variables, shortcuts, and file type associations included in X.osd and Y.osd were converted and placed in the App-V package, and some of this information was also included in the deployment configuration and user configuration files.</span></span> <span data-ttu-id="6e956-174">X. osd と Y はパラメーターの引数として指定されているために使われます <code>-OSDsToIncludeInPackage</code> 。</span><span class="sxs-lookup"><span data-stu-id="6e956-174">X.osd and Y.osd were used because they were included as arguments to the <code>-OSDsToIncludeInPackage</code> parameter.</span></span> <span data-ttu-id="6e956-175">このパッケージには、これらの引数の1つとして含まれていないため、Z-index からの情報はパッケージに含まれていませんでした。</span><span class="sxs-lookup"><span data-stu-id="6e956-175">No information from Z.osd was included in the package, because it was not included as one of these arguments.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="6e956-176">以前のバージョンの App-v を使用して作成されたパッケージの変換</span><span class="sxs-lookup"><span data-stu-id="6e956-176">Converting packages created using a prior version of App-V</span></span>


<span data-ttu-id="6e956-177">Package converter ユーティリティーを使って、app-v 5.0 のバージョンを使って作成された仮想アプリケーションパッケージをアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="6e956-177">Use the package converter utility to upgrade virtual application packages created using versions of App-V prior to App-V 5.0.</span></span> <span data-ttu-id="6e956-178">パッケージコンバーターは、PowerShell を使用してパッケージを変換し、変換が必要なパッケージが多い場合は、プロセスの自動化に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6e956-178">The package converter uses PowerShell to convert packages and can help automate the process if you have many packages that require conversion.</span></span>

<span data-ttu-id="6e956-179">**重要** 既存のパッケージを変換した後は、パッケージを展開する前にパッケージをテストして、変換処理が正常に完了したことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e956-179">**Important** After you convert an existing package you should test the package prior to deploying the package to ensure the conversion process was successful.</span></span>

 

**<span data-ttu-id="6e956-180">既存のパッケージを変換する前に知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="6e956-180">What to know before you convert existing packages</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6e956-181">問題</span><span class="sxs-lookup"><span data-stu-id="6e956-181">Issue</span></span></th>
<th align="left"><span data-ttu-id="6e956-182">回避策</span><span class="sxs-lookup"><span data-stu-id="6e956-182">Workaround</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e956-183">変換後、DSC を使用する仮想パッケージはリンクされません。</span><span class="sxs-lookup"><span data-stu-id="6e956-183">Virtual packages using DSC are not linked after conversion.</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e956-184">接続グループを使ってパッケージをリンクします。</span><span class="sxs-lookup"><span data-stu-id="6e956-184">Link the packages using connection groups.</span></span> <span data-ttu-id="6e956-185">「 <a href="managing-connection-groups51.md" data-raw-source="[Managing Connection Groups](managing-connection-groups51.md)"> 接続グループの管理」をご覧ください </a> 。</span><span class="sxs-lookup"><span data-stu-id="6e956-185">See <a href="managing-connection-groups51.md" data-raw-source="[Managing Connection Groups](managing-connection-groups51.md)">Managing Connection Groups</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6e956-186">変換中に環境変数の競合が検出されます。</span><span class="sxs-lookup"><span data-stu-id="6e956-186">Environment variable conflicts are detected during conversion.</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e956-187">関連付けられている .osd ファイル内の競合を解決 <strong> </strong> します。</span><span class="sxs-lookup"><span data-stu-id="6e956-187">Resolve any conflicts in the associated <strong>.osd</strong> file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e956-188">変換中にハードコーディングされたパスが検出されます。</span><span class="sxs-lookup"><span data-stu-id="6e956-188">Hard-coded paths are detected during conversion.</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e956-189">ハードコーディングされたパスは正しく変換されにくくなります。</span><span class="sxs-lookup"><span data-stu-id="6e956-189">Hard-coded paths are difficult to convert correctly.</span></span> <span data-ttu-id="6e956-190">パッケージコンバーターは、ハードコーディングされたパスを含むファイルを含むパッケージを検出して返します。</span><span class="sxs-lookup"><span data-stu-id="6e956-190">The package converter will detect and return packages with files that contain hard-coded paths.</span></span> <span data-ttu-id="6e956-191">ハードコーディングされたパスでファイルを表示し、パッケージにファイルが必要かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="6e956-191">View the file with the hard-coded path, and determine whether the package requires the file.</span></span> <span data-ttu-id="6e956-192">その場合は、パッケージの順序を再確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e956-192">If so, it is recommended to re-sequence the package.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="6e956-193">パッケージを変換するときに、エラーが発生したファイルまたはショートカットを確認します。</span><span class="sxs-lookup"><span data-stu-id="6e956-193">When converting a package check for failing files or shortcuts.</span></span> <span data-ttu-id="6e956-194">App-V 4.6 パッケージでアイテムを見つけます。</span><span class="sxs-lookup"><span data-stu-id="6e956-194">Locate the item in App-V 4.6 package.</span></span> <span data-ttu-id="6e956-195">ハードコードされたパスである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e956-195">It could possibly be a hard-coded path.</span></span> <span data-ttu-id="6e956-196">パスを変換します。</span><span class="sxs-lookup"><span data-stu-id="6e956-196">Convert the path.</span></span>

<span data-ttu-id="6e956-197">**注** 機能を活用する必要がある重要なアプリケーションやアプリケーションを変換するには、App-v 5.1 sequencer を使うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e956-197">**Note** It is recommended that you use the App-V 5.1 sequencer for converting critical applications or applications that need to take advantage of features.</span></span> <span data-ttu-id="6e956-198">「 [App-v 5.1 を使って新しいアプリケーションを順序付けする方法](how-to-sequence-a-new-application-with-app-v-51-beta-gb18030.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e956-198">See, [How to Sequence a New Application with App-V 5.1](how-to-sequence-a-new-application-with-app-v-51-beta-gb18030.md).</span></span>

<span data-ttu-id="6e956-199">変換後に変換されたパッケージが開かない場合は、App-v 5.1 sequencer を使用してアプリケーションを再シーケンスすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e956-199">If a converted package does not open after you convert it, it is also recommended that you re-sequence the application using the App-V 5.1 sequencer.</span></span>

 

[<span data-ttu-id="6e956-200">以前のバージョンの APP-V で作成されたパッケージを変換する方法</span><span class="sxs-lookup"><span data-stu-id="6e956-200">How to Convert a Package Created in a Previous Version of App-V</span></span>](how-to-convert-a-package-created-in-a-previous-version-of-app-v51.md)

## <span data-ttu-id="6e956-201">クライアントの移行</span><span class="sxs-lookup"><span data-stu-id="6e956-201">Migrating Clients</span></span>


<span data-ttu-id="6e956-202">次の表は、クライアントをアップグレードするための推奨される方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6e956-202">The following table displays the recommended method for upgrading clients.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6e956-203">タスク</span><span class="sxs-lookup"><span data-stu-id="6e956-203">Task</span></span></th>
<th align="left"><span data-ttu-id="6e956-204">詳細情報</span><span class="sxs-lookup"><span data-stu-id="6e956-204">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e956-205">環境を最新バージョンの App-v にアップグレードする-V 4.6</span><span class="sxs-lookup"><span data-stu-id="6e956-205">Upgrade your environment to the latest version of App-V4.6</span></span></p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)"><span data-ttu-id="6e956-206">アプリケーションの仮想化の展開とアップグレードに関する考慮事項 </a> 。</span><span class="sxs-lookup"><span data-stu-id="6e956-206">Application Virtualization Deployment and Upgrade Considerations</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6e956-207">共存を有効にした App-v 5.1 クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6e956-207">Install the App-V 5.1 client with co-existence enabled.</span></span></p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md" data-raw-source="[How to Deploy the App-V 4.6 and the App-V 5.1 Client on the Same Computer](how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md)"><span data-ttu-id="6e956-208">同じコンピューターに app-v 4.6 と App-v 5.1 クライアントを展開する方法を説明 </a> します。</span><span class="sxs-lookup"><span data-stu-id="6e956-208">How to Deploy the App-V 4.6 and the App-V 5.1 Client on the Same Computer</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e956-209">アプリ-V 5.1 パッケージのシーケンスとロールアウト。</span><span class="sxs-lookup"><span data-stu-id="6e956-209">Sequence and roll out App-V 5.1 packages.</span></span> <span data-ttu-id="6e956-210">必要に応じて、App-v 4.6 パッケージの発行を取り消します。</span><span class="sxs-lookup"><span data-stu-id="6e956-210">As needed, unpublish App-V 4.6 packages.</span></span></p></td>
<td align="left"><p><a href="how-to-sequence-a-new-application-with-app-v-51-beta-gb18030.md" data-raw-source="[How to Sequence a New Application with App-V 5.1](how-to-sequence-a-new-application-with-app-v-51-beta-gb18030.md)"><span data-ttu-id="6e956-211">App-V 5.1 を使って新しいアプリケーションをシーケンスする方法について説明 </a> します。</span><span class="sxs-lookup"><span data-stu-id="6e956-211">How to Sequence a New Application with App-V 5.1</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="6e956-212">**重要** 共存モードを使用するには、最新バージョンの App-v を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e956-212">**Important** You must be running the latest version of App-V4.6 to use coexistence mode.</span></span> <span data-ttu-id="6e956-213">さらに、パッケージをシーケンス処理するときには、 **[ユーザーの\*\*\*\*構成] セクションに**ある [管理権限] 設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e956-213">Additionally, when you sequence a package, you must configure the Managing Authority setting, which is in the **User Configuration** is located in the **User Configuration** section.</span></span>

 

## <span data-ttu-id="6e956-214">App-v 5.1 Server の完全なインフラストラクチャを移行する</span><span class="sxs-lookup"><span data-stu-id="6e956-214">Migrating the App-V 5.1 Server Full Infrastructure</span></span>


<span data-ttu-id="6e956-215">完全な App-v 5.1 インフラストラクチャにアップグレードする直接的な方法はありません。</span><span class="sxs-lookup"><span data-stu-id="6e956-215">There is no direct method to upgrade to a full App-V 5.1 infrastructure.</span></span> <span data-ttu-id="6e956-216">App-v server のアップグレードについては、次のセクションの情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e956-216">Use the information in the following section for information about upgrading the App-V server.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6e956-217">タスク</span><span class="sxs-lookup"><span data-stu-id="6e956-217">Task</span></span></th>
<th align="left"><span data-ttu-id="6e956-218">詳細情報</span><span class="sxs-lookup"><span data-stu-id="6e956-218">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e956-219">環境を最新バージョンの App-v 4.6 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="6e956-219">Upgrade your environment to the latest version of App-V4.6.</span></span></p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)"><span data-ttu-id="6e956-220">アプリケーションの仮想化の展開とアップグレードに関する考慮事項 </a> 。</span><span class="sxs-lookup"><span data-stu-id="6e956-220">Application Virtualization Deployment and Upgrade Considerations</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6e956-221">クライアントの App-v 5.1 バージョンを展開します。</span><span class="sxs-lookup"><span data-stu-id="6e956-221">Deploy App-V 5.1 version of the client.</span></span></p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-client-51gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-51gb18030.md)"><span data-ttu-id="6e956-222">App-v クライアントを展開する方法を説明 </a> します。</span><span class="sxs-lookup"><span data-stu-id="6e956-222">How to Deploy the App-V Client</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e956-223">App-v 5.1 server をインストールします。</span><span class="sxs-lookup"><span data-stu-id="6e956-223">Install App-V 5.1 server.</span></span></p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-51-server.md" data-raw-source="[How to Deploy the App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md)"><span data-ttu-id="6e956-224">App-v 5.1 サーバーを展開する方法について説明 </a> します。</span><span class="sxs-lookup"><span data-stu-id="6e956-224">How to Deploy the App-V 5.1 Server</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6e956-225">既存のパッケージを移行します。</span><span class="sxs-lookup"><span data-stu-id="6e956-225">Migrate existing packages.</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e956-226"><strong>この記事の「以前のバージョンの app-v を使用して作成されたパッケージの変換」を参照してください </strong> 。</span><span class="sxs-lookup"><span data-stu-id="6e956-226">See the <strong>Converting packages created using a prior version of App-V</strong> section of this article.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="6e956-227">その他の移行タスク</span><span class="sxs-lookup"><span data-stu-id="6e956-227">Additional Migration tasks</span></span>


<span data-ttu-id="6e956-228">また、エンドポイントの再構成や、App-v 5.1 クライアントを実行しているコンピューター上で以前のバージョンを使用して作成されたパッケージの開くなど、追加の移行タスクを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e956-228">You can also perform additional migration tasks such as reconfiguring end points as well as opening a package created using a prior version on a computer running the App-V 5.1 client.</span></span> <span data-ttu-id="6e956-229">次のリンクでは、これらのタスクを実行する方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="6e956-229">The following links provide more information about performing these tasks.</span></span>

[<span data-ttu-id="6e956-230">特定のコンピューター上の全ユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.1 パッケージに移行する方法</span><span class="sxs-lookup"><span data-stu-id="6e956-230">How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.1 Package for All Users on a Specific Computer</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-51-package-for-all-users-on-a-specific-computer.md)

[<span data-ttu-id="6e956-231">特定のユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.1 パッケージに移行する方法</span><span class="sxs-lookup"><span data-stu-id="6e956-231">How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.1 for a Specific User</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-51-for-a-specific-user.md)

[<span data-ttu-id="6e956-232">特定のコンピューター上の全ユーザーの拡張ポイントを App-V 5.1 パッケージから App-V 4.6 パッケージに戻す方法</span><span class="sxs-lookup"><span data-stu-id="6e956-232">How to Revert Extension Points from an App-V 5.1 Package to an App-V 4.6 Package For All Users on a Specific Computer</span></span>](how-to-revert-extension-points-from-an-app-v-51-package-to-an-app-v-46-package-for-all-users-on-a-specific-computer.md)

[<span data-ttu-id="6e956-233">特定のユーザーの拡張ポイントを App-V 5.1 パッケージから App-V 4.6 パッケージに戻す方法</span><span class="sxs-lookup"><span data-stu-id="6e956-233">How to Revert Extension Points From an App-V 5.1 Package to an App-V 4.6 Package for a Specific User</span></span>](how-to-revert-extension-points-from-an-app-v-51-package-to-an-app-v-46-package-for-a-specific-user.md)







## <span data-ttu-id="6e956-234">App-v の移行タスクを実行するためのその他のリソース</span><span class="sxs-lookup"><span data-stu-id="6e956-234">Other resources for performing App-V migration tasks</span></span>


[<span data-ttu-id="6e956-235">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="6e956-235">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

[<span data-ttu-id="6e956-236">簡素化された Microsoft App-V 5.1 Management Server のアップグレード手順</span><span class="sxs-lookup"><span data-stu-id="6e956-236">A simplified Microsoft App-V 5.1 Management Server upgrade procedure</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=786330)

 

 





