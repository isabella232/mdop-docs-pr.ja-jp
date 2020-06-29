---
title: MDOP グループ ポリシー (.admx) テンプレートをダウンロードして展開する方法
description: MDOP グループ ポリシー (.admx) テンプレートをダウンロードして展開する方法
author: dansimp
ms.assetid: fdb64505-6c66-4fdf-ad74-a6a161191e3f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/15/2018
ms.openlocfilehash: 5bc5f8d536c113ccbc0a1931e6c7e4ed3c7a9a37
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826917"
---
# <span data-ttu-id="89117-103">MDOP グループ ポリシー (.admx) テンプレートをダウンロードして展開する方法</span><span class="sxs-lookup"><span data-stu-id="89117-103">How to Download and Deploy MDOP Group Policy (.admx) Templates</span></span>


<span data-ttu-id="89117-104">グループポリシーテンプレート、admx、adml ファイルを使用して、特定の Microsoft デスクトップ最適化パック (MDOP) テクノロジ (たとえば、アプリ-V、UE-V、または MBAM など) の機能設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="89117-104">You can manage the feature settings of certain Microsoft Desktop Optimization Pack (MDOP) technologies (for example, App-V, UE-V, or MBAM) by using Group Policy templates, the .admx and .adml files.</span></span> <span data-ttu-id="89117-105">MDOP グループポリシーテンプレートは、テクノロジとバージョンごとにグループ化された、自己解凍型の圧縮ファイルからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="89117-105">MDOP Group Policy templates are available for download in a self-extracting, compressed file, grouped by technology and version.</span></span>

## <span data-ttu-id="89117-106">MDOP グループポリシーテンプレート</span><span class="sxs-lookup"><span data-stu-id="89117-106">MDOP Group Policy templates</span></span>

**<span data-ttu-id="89117-107">MDOP グループポリシーテンプレートをダウンロードして展開する方法</span><span class="sxs-lookup"><span data-stu-id="89117-107">How to download and deploy the MDOP Group Policy templates</span></span>**

1. <span data-ttu-id="89117-108">最新の[MDOP グループポリシーテンプレート](https://www.microsoft.com/download/details.aspx?id=55531)をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="89117-108">Download the latest [MDOP Group Policy templates](https://www.microsoft.com/download/details.aspx?id=55531)</span></span> 

2. <span data-ttu-id="89117-109">実行して、ダウンロードした .cab ファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="89117-109">Expand the downloaded .cab file by running</span></span> `expand <download_folder>\MDOP_ADMX_Templates.cab -F:* <destination_folder>`

   **<span data-ttu-id="89117-110">Warning</span><span class="sxs-lookup"><span data-stu-id="89117-110">Warning</span></span>**  
   <span data-ttu-id="89117-111">テンプレートは、グループポリシー展開ディレクトリに直接抽出しないでください。</span><span class="sxs-lookup"><span data-stu-id="89117-111">Do not extract the templates directly to the Group Policy deployment directory.</span></span> <span data-ttu-id="89117-112">このファイルには、複数の技術とバージョンがバンドルされています。</span><span class="sxs-lookup"><span data-stu-id="89117-112">Multiple technologies and versions are bundled in this file.</span></span>

3. <span data-ttu-id="89117-113">展開されたフォルダーで、テクノロジのバージョンの admx ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="89117-113">In the extracted folder, locate the technology-version .admx file.</span></span> <span data-ttu-id="89117-114">一部の MDOP テクノロジには、複数のグループポリシーオブジェクト (Gpo) のセットがあります。</span><span class="sxs-lookup"><span data-stu-id="89117-114">Certain MDOP technologies have multiple sets of Group Policy Objects (GPOs).</span></span> <span data-ttu-id="89117-115">たとえば、MBAM には、MBAM 管理設定と MBAM ユーザー設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="89117-115">For example, MBAM includes MBAM Management settings and MBAM User settings.</span></span>

4. <span data-ttu-id="89117-116">言語によって適切な adml ファイルを見つけます (つまり、英語 (米国) の場合は*en-us* )。</span><span class="sxs-lookup"><span data-stu-id="89117-116">Locate the appropriate .adml file by language-culture (that is, *en-us* for English-United States).</span></span>

5. <span data-ttu-id="89117-117">Admx ファイルと adml ファイルをポリシー定義フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="89117-117">Copy the .admx and .adml files to a policy definition folder.</span></span> <span data-ttu-id="89117-118">テンプレートの保存場所に応じて、ローカルデバイスまたはドメインの任意のコンピューターからグループポリシー設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="89117-118">Depending on where you store the templates, you can configure Group Policy settings from the local device or from any computer on the domain.</span></span>

   - <span data-ttu-id="89117-119">**ローカルファイル:** ローカルデバイスからグループポリシー設定を構成するには、テンプレートファイルを次の場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="89117-119">**Local files:** To configure Group Policy settings from the local device, copy template files to the following locations:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="89117-120">ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="89117-120">File type</span></span></th>
   <th align="left"><span data-ttu-id="89117-121">ファイルの場所</span><span class="sxs-lookup"><span data-stu-id="89117-121">File location</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="89117-122">グループポリシーテンプレート (admx)</span><span class="sxs-lookup"><span data-stu-id="89117-122">Group Policy template (.admx)</span></span></p></td>
   <td align="left"><p><code>%systemroot%</code><span data-ttu-id="89117-123">&lt;強力な &gt; ポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="89117-123">&lt;strong&gt;policyDefinitions</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="89117-124">グループポリシー言語ファイル (adml)</span><span class="sxs-lookup"><span data-stu-id="89117-124">Group Policy language file (.adml)</span></span></p></td>
   <td align="left"><p><code>%systemroot%</code><span data-ttu-id="89117-125">&lt;強力な &gt; ポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="89117-125">&lt;strong&gt;policyDefinitions</span></span></strong><code>[MUIculture]</code></p></td>
   </tr>
   </tbody>
   </table>

   - <span data-ttu-id="89117-126">**Domain central store:** グループポリシーの設定をグループポリシーの管理者がドメインの任意のコンピューターから有効にするには、ドメインコントローラーの次の場所にファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="89117-126">**Domain central store:** To enable Group Policy settings configuration by a Group Policy administrator from any computer on the domain, copy files to the following locations on the domain controller:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="89117-127">ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="89117-127">File type</span></span></th>
   <th align="left"><span data-ttu-id="89117-128">ファイルの場所</span><span class="sxs-lookup"><span data-stu-id="89117-128">File location</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="89117-129">グループポリシーテンプレート (admx)</span><span class="sxs-lookup"><span data-stu-id="89117-129">Group Policy template (.admx)</span></span></p></td>
   <td align="left"><p><code>%systemroot%</code><span data-ttu-id="89117-130">&lt;強力な &gt; sysvol\domain\policies\PolicyDefinitions</span><span class="sxs-lookup"><span data-stu-id="89117-130">&lt;strong&gt;sysvol\domain\policies\PolicyDefinitions</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="89117-131">グループポリシー言語ファイル (adml)</span><span class="sxs-lookup"><span data-stu-id="89117-131">Group Policy language file (.adml)</span></span></p></td>
   <td align="left"><p><code>%systemroot%</code><span data-ttu-id="89117-132">&lt;強力な &gt; sysvol\domain\policies\PolicyDefinitions [MUIculture]</span><span class="sxs-lookup"><span data-stu-id="89117-132">&lt;strong&gt;sysvol\domain\policies\PolicyDefinitions[MUIculture]</span></span></strong><code>[MUIculture]</code></p>
   <p><span data-ttu-id="89117-133">たとえば、米国英語 ADML の言語固有のファイルは、%systemroot%\sysvol\domain\policies\PolicyDefinitions\en-us. に保存されます。</span><span class="sxs-lookup"><span data-stu-id="89117-133">For example, the U.S. English ADML language-specific file will be stored in %systemroot%\sysvol\domain\policies\PolicyDefinitions\en-us.</span></span></p></td>
   </tr>
   </tbody>
   </table>

6. <span data-ttu-id="89117-134">グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) を使用してグループポリシー設定を編集し、MDOP テクノロジのグループポリシー設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="89117-134">Edit the Group Policy settings using Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM) to configure Group Policy settings for the MDOP technology.</span></span>

### <span data-ttu-id="89117-135">技術別の MDOP グループポリシー</span><span class="sxs-lookup"><span data-stu-id="89117-135">MDOP Group Policy by technology</span></span>

<span data-ttu-id="89117-136">サポートされている MDOP グループポリシーの詳細については、技術に関する具体的なドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="89117-136">For more information about supported MDOP Group Policy, see the specific documentation for the technology.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="89117-137">MDOP 技術</span><span class="sxs-lookup"><span data-stu-id="89117-137">MDOP Technology</span></span></th>
<th align="left"><span data-ttu-id="89117-138">バージョンバンドル</span><span class="sxs-lookup"><span data-stu-id="89117-138">Version bundles</span></span></th>
<th align="left"><span data-ttu-id="89117-139">備考</span><span class="sxs-lookup"><span data-stu-id="89117-139">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="89117-140">Application Virtualization (APP-V)</span><span class="sxs-lookup"><span data-stu-id="89117-140">Application Virtualization (App-V)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="89117-141">App-v 5.0 および App-v 5.0 Service Pack</span><span class="sxs-lookup"><span data-stu-id="89117-141">App-V 5.0 and App-V 5.0 Service Packs</span></span></p></td>
<td align="left"><p><a href="../appv-v5/how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md" data-raw-source="[How to Modify App-V 5.0 Client Configuration Using the ADMX Template and Group Policy](../appv-v5/how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md)"><span data-ttu-id="89117-142">ADMX テンプレートとグループ ポリシーを使用して App-V 5.0 Client 構成を変更する方法</span><span class="sxs-lookup"><span data-stu-id="89117-142">How to Modify App-V 5.0 Client Configuration Using the ADMX Template and Group Policy</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="89117-143">User Experience Virtualization (UE-V)</span><span class="sxs-lookup"><span data-stu-id="89117-143">User Experience Virtualization (UE-V)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="89117-144">UE-V 2.0 および UE-V 2.1</span><span class="sxs-lookup"><span data-stu-id="89117-144">UE-V 2.0 and UE-V 2.1</span></span></p></td>
<td align="left"><p><a href="../uev-v2/configuring-ue-v-2x-with-group-policy-objects-both-uevv2.md" data-raw-source="[Configuring UE-V 2.x with Group Policy Objects](../uev-v2/configuring-ue-v-2x-with-group-policy-objects-both-uevv2.md)"><span data-ttu-id="89117-145">グループポリシーオブジェクトを使用して UE-V 2. x を構成する</span><span class="sxs-lookup"><span data-stu-id="89117-145">Configuring UE-V 2.x with Group Policy Objects</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="89117-146">UE-V 1.0 (1.0 SP1 を含む)</span><span class="sxs-lookup"><span data-stu-id="89117-146">UE-V 1.0 including 1.0 SP1</span></span></p></td>
<td align="left"><p><a href="../uev-v1/configuring-ue-v-with-group-policy-objects.md" data-raw-source="[Configuring UE-V with Group Policy Objects](../uev-v1/configuring-ue-v-with-group-policy-objects.md)"><span data-ttu-id="89117-147">グループ ポリシー オブジェクトを使用した UE-V の構成</span><span class="sxs-lookup"><span data-stu-id="89117-147">Configuring UE-V with Group Policy Objects</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="89117-148">Microsoft BitLocker Administration and Monitoring (MBAM)</span><span class="sxs-lookup"><span data-stu-id="89117-148">Microsoft BitLocker Administration and Monitoring (MBAM)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="89117-149">MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="89117-149">MBAM 2.5</span></span></p></td>
<td align="left"><p><a href="../mbam-v25/planning-for-mbam-25-group-policy-requirements.md" data-raw-source="[Planning for MBAM 2.5 Group Policy Requirements](../mbam-v25/planning-for-mbam-25-group-policy-requirements.md)"><span data-ttu-id="89117-150">MBAM 2.5 グループ ポリシー要件の計画</span><span class="sxs-lookup"><span data-stu-id="89117-150">Planning for MBAM 2.5 Group Policy Requirements</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="89117-151">MBAM 2.0 (2.0 SP1 を含む)</span><span class="sxs-lookup"><span data-stu-id="89117-151">MBAM 2.0 including 2.0 SP1</span></span></p></td>
<td align="left"><p><a href="../mbam-v2/planning-for-mbam-20-group-policy-requirements-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Group Policy Requirements](../mbam-v2/planning-for-mbam-20-group-policy-requirements-mbam-2.md)"><span data-ttu-id="89117-152">MBAM 2.0 グループ ポリシー要件の計画</span><span class="sxs-lookup"><span data-stu-id="89117-152">Planning for MBAM 2.0 Group Policy Requirements</span></span></a></p>
<p><a href="../mbam-v2/deploying-mbam-20-group-policy-objects-mbam-2.md" data-raw-source="[Deploying MBAM 2.0 Group Policy Objects](../mbam-v2/deploying-mbam-20-group-policy-objects-mbam-2.md)"><span data-ttu-id="89117-153">MBAM 2.0 グループ ポリシー オブジェクトの展開</span><span class="sxs-lookup"><span data-stu-id="89117-153">Deploying MBAM 2.0 Group Policy Objects</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="89117-154">MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="89117-154">MBAM 1.0</span></span></p></td>
<td align="left"><p><a href="../mbam-v1/how-to-edit-mbam-10-gpo-settings.md" data-raw-source="[How to Edit MBAM 1.0 GPO Settings](../mbam-v1/how-to-edit-mbam-10-gpo-settings.md)"><span data-ttu-id="89117-155">MBAM 1.0 GPO 設定を編集する方法</span><span class="sxs-lookup"><span data-stu-id="89117-155">How to Edit MBAM 1.0 GPO Settings</span></span></a></p></td>
</tr>
</tbody>
</table>

 

 

 





