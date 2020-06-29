---
title: MBAM 2.5 グループ ポリシー テンプレートのコピー
description: MBAM 2.5 グループ ポリシー テンプレートのコピー
author: dansimp
ms.assetid: e526ecec-07ff-435e-bc90-3084b617b84b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/28/2017
ms.openlocfilehash: a3436552256b1632a11037dc94751207cde89d5c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825224"
---
# <span data-ttu-id="2c5ff-103">MBAM 2.5 グループ ポリシー テンプレートのコピー</span><span class="sxs-lookup"><span data-stu-id="2c5ff-103">Copying the MBAM 2.5 Group Policy Templates</span></span>


<span data-ttu-id="2c5ff-104">MBAM クライアントのインストールを展開する前に、「mbam の実装設定を定義する BitLocker ドライブ暗号化」のグループポリシー設定が含まれている MBAM グループポリシーテンプレートをダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c5ff-104">Before deploying the MBAM Client installation, you must download the MBAM Group Policy Templates, which contain Group Policy settings that define MBAM implementation settings for BitLocker Drive Encryption.</span></span> <span data-ttu-id="2c5ff-105">テンプレートをダウンロードした後で、組織全体で実装するグループポリシー設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="2c5ff-105">After downloading the templates, you then set the Group Policy settings to implement across your enterprise.</span></span>

## <span data-ttu-id="2c5ff-106">MDOP グループポリシーテンプレートをダウンロードして展開する</span><span class="sxs-lookup"><span data-stu-id="2c5ff-106">Downloading and deploying the MDOP Group Policy templates</span></span>


<span data-ttu-id="2c5ff-107">MDOP グループポリシーテンプレートは、テクノロジとバージョンごとにグループ化された、自己解凍型の圧縮ファイルからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="2c5ff-107">MDOP Group Policy templates are available for download in a self-extracting, compressed file, grouped by technology and version.</span></span>

**<span data-ttu-id="2c5ff-108">MDOP グループポリシーテンプレートをダウンロードして展開する方法</span><span class="sxs-lookup"><span data-stu-id="2c5ff-108">How to download and deploy the MDOP Group Policy templates</span></span>**

1. <span data-ttu-id="2c5ff-109">[Microsoft デスクトップ最適化パックのグループポリシー管理用テンプレート](https://www.microsoft.com/download/details.aspx?id=55531)から、MDOP グループポリシーテンプレートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="2c5ff-109">Download the MDOP Group Policy templates from [Microsoft Desktop Optimization Pack Group Policy Administrative Templates](https://www.microsoft.com/download/details.aspx?id=55531).</span></span>

2. <span data-ttu-id="2c5ff-110">ダウンロードしたファイルを実行して、テンプレートフォルダーを抽出します。</span><span class="sxs-lookup"><span data-stu-id="2c5ff-110">Run the downloaded file to extract the template folders.</span></span>

   **<span data-ttu-id="2c5ff-111">Warning</span><span class="sxs-lookup"><span data-stu-id="2c5ff-111">Warning</span></span>**  
   <span data-ttu-id="2c5ff-112">テンプレートは、グループポリシー展開ディレクトリに直接抽出しないでください。</span><span class="sxs-lookup"><span data-stu-id="2c5ff-112">Do not extract the templates directly to the Group Policy deployment directory.</span></span> <span data-ttu-id="2c5ff-113">このファイルには、複数の技術とバージョンがバンドルされています。</span><span class="sxs-lookup"><span data-stu-id="2c5ff-113">Multiple technologies and versions are bundled in this file.</span></span>



3. <span data-ttu-id="2c5ff-114">展開されたフォルダーで、テクノロジのバージョンの admx ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="2c5ff-114">In the extracted folder, locate the technology-version .admx file.</span></span> <span data-ttu-id="2c5ff-115">一部の MDOP テクノロジには、複数のグループポリシーオブジェクト (Gpo) のセットがあります。</span><span class="sxs-lookup"><span data-stu-id="2c5ff-115">Certain MDOP technologies have multiple sets of Group Policy Objects (GPOs).</span></span> <span data-ttu-id="2c5ff-116">たとえば、MBAM には、MBAM 管理設定と MBAM ユーザー設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2c5ff-116">For example, MBAM includes MBAM Management settings and MBAM User settings.</span></span>

4. <span data-ttu-id="2c5ff-117">言語によって適切な adml ファイルを見つけます (*つまり、英語*(米国))。</span><span class="sxs-lookup"><span data-stu-id="2c5ff-117">Locate the appropriate .adml file by language-culture (that is, *en* for English-United States).</span></span>

5. <span data-ttu-id="2c5ff-118">Admx ファイルと adml ファイルをポリシー定義フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="2c5ff-118">Copy the .admx and .adml files to a policy definition folder.</span></span> <span data-ttu-id="2c5ff-119">テンプレートの保存場所に応じて、ローカルデバイスまたはドメインの任意のコンピューターからグループポリシー設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="2c5ff-119">Depending on where you store the templates, you can configure Group Policy settings from the local device or from any computer on the domain.</span></span>

   **<span data-ttu-id="2c5ff-120">ローカルファイル。</span><span class="sxs-lookup"><span data-stu-id="2c5ff-120">Local files.</span></span>** <span data-ttu-id="2c5ff-121">ローカルデバイスからグループポリシー設定を構成するには、テンプレートファイルを次の場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="2c5ff-121">To configure Group Policy settings from the local device, copy template files to the following locations:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="2c5ff-122">ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="2c5ff-122">File type</span></span></th>
   <th align="left"><span data-ttu-id="2c5ff-123">ファイルの場所</span><span class="sxs-lookup"><span data-stu-id="2c5ff-123">File location</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="2c5ff-124">グループポリシーテンプレート (admx)</span><span class="sxs-lookup"><span data-stu-id="2c5ff-124">Group Policy template (.admx)</span></span></p></td>
   <td align="left"><p><code>%systemroot%</code><span data-ttu-id="2c5ff-125">&lt;強力な &gt; ポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="2c5ff-125">&lt;strong&gt;policyDefinitions</span></span></strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="2c5ff-126">グループポリシー言語ファイル (adml)</span><span class="sxs-lookup"><span data-stu-id="2c5ff-126">Group Policy language file (.adml)</span></span></p></td>
   <td align="left"><p><code>%systemroot%</code><span data-ttu-id="2c5ff-127">&lt;強力な &gt; ポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="2c5ff-127">&lt;strong&gt;policyDefinitions</span></span></strong><code>[MUIculture]</code></p></td>
   </tr>
   </tbody>
   </table>



~~~
**Domain central store.** To enable Group Policy settings configuration by a Group Policy administrator from any computer on the domain, copy files to the following locations on the domain controller:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">File type</th>
<th align="left">File location</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Group Policy template (.admx)</p></td>
<td align="left"><p><code>%systemroot%</code>\<strong>sysvol\domain\policies\PolicyDefinitions</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Group Policy language file (.adml)</p></td>
<td align="left"><p><code>%systemroot%</code>\<strong>sysvol\domain\policies\PolicyDefinitions\[MUIculture]</strong><code>\[MUIculture]</code></p>
<p>For example, the U.S. English ADML language-specific file will be stored in %systemroot%\sysvol\domain\policies\PolicyDefinitions\en-us.</p></td>
</tr>
</tbody>
</table>
~~~



6. <span data-ttu-id="2c5ff-128">グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) を使用してグループポリシー設定を編集し、MDOP テクノロジのグループポリシー設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="2c5ff-128">Edit the Group Policy settings using Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM) to configure Group Policy settings for the MDOP technology.</span></span> <span data-ttu-id="2c5ff-129">詳細については[、「MBAM 2.5 グループポリシーの設定を編集](editing-the-mbam-25-group-policy-settings.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c5ff-129">See [Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md) for more information.</span></span>

   <span data-ttu-id="2c5ff-130">グループポリシー設定の詳細については、「 [MBAM 2.5 グループポリシーの要件の計画](planning-for-mbam-25-group-policy-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c5ff-130">For descriptions of the Group Policy settings, see [Planning for MBAM 2.5 Group Policy Requirements](planning-for-mbam-25-group-policy-requirements.md).</span></span>


## <span data-ttu-id="2c5ff-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2c5ff-131">Related topics</span></span>


[<span data-ttu-id="2c5ff-132">MBAM 2.5 グループ ポリシー オブジェクトの展開</span><span class="sxs-lookup"><span data-stu-id="2c5ff-132">Deploying MBAM 2.5 Group Policy Objects</span></span>](deploying-mbam-25-group-policy-objects.md)


## <span data-ttu-id="2c5ff-133">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="2c5ff-133">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="2c5ff-134">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="2c5ff-134">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="2c5ff-135">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="2c5ff-135">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>






