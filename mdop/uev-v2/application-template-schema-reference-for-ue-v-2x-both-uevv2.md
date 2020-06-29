---
title: UE-V 2 .x のアプリケーションテンプレートスキーマリファレンス
description: UE-V 2 .x のアプリケーションテンプレートスキーマリファレンス
author: dansimp
ms.assetid: be8735a5-6a3e-4b1f-ba14-2a3bc3e5a8b6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 03ff6eabae68f07c23d5977f901e6a90e292c6ac
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827407"
---
# <span data-ttu-id="9464b-103">UE-V 2 .x のアプリケーションテンプレートスキーマリファレンス</span><span class="sxs-lookup"><span data-stu-id="9464b-103">Application Template Schema Reference for UE-V 2.x</span></span>


<span data-ttu-id="9464b-104">Microsoft User Experience Virtualization (UE-V) 2.0、2.1、および 2.1 SP1 では、XML 設定の場所テンプレートを使用して、UE-V でキャプチャおよび適用されるデスクトップアプリケーションの設定と Windows 設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="9464b-104">Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 use XML settings location templates to define the desktop application settings and Windows settings that are captured and applied by UE-V.</span></span> <span data-ttu-id="9464b-105">UE-V には、既定の設定場所テンプレートのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9464b-105">UE-V includes a set of default settings location templates.</span></span> <span data-ttu-id="9464b-106">また、UE-V Generator を使用して、カスタム設定の場所テンプレートを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="9464b-106">You can also create custom settings location templates with the UE-V Generator.</span></span>

<span data-ttu-id="9464b-107">高度なユーザーは、設定場所テンプレートの XML ファイルをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="9464b-107">An advanced user can customize the XML file for a settings location template.</span></span> <span data-ttu-id="9464b-108">このトピックでは、UE-V 2.1 (SP1) と2.0 の設定の場所テンプレートの XML 構造について詳しく説明し、これらのファイルを編集するためのガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="9464b-108">This topic details the XML structure of the UE-V 2.1 (SP1) and 2.0 settings location templates and provides guidance for editing these files.</span></span>

## <span data-ttu-id="9464b-109">UE-V 2.1 および 2.1 SP1 アプリケーションテンプレートスキーマリファレンス</span><span class="sxs-lookup"><span data-stu-id="9464b-109">UE-V 2.1 and 2.1 SP1 Application Template Schema Reference</span></span>


<span data-ttu-id="9464b-110">このセクションでは、UE-V 2.1 および 2.1 SP1 設定の場所テンプレートの XML 構造について詳しく説明し、このファイルを編集するためのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="9464b-110">This section details the XML structure of the UE-V 2.1 and 2.1 SP1 settings location template and provides guidance for editing this file.</span></span>

### <span data-ttu-id="9464b-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9464b-111">In This Section</span></span>

-   [<span data-ttu-id="9464b-112">XML 宣言とエンコード属性</span><span class="sxs-lookup"><span data-stu-id="9464b-112">XML Declaration and Encoding Attribute</span></span>](#xml21)

-   [<span data-ttu-id="9464b-113">名前空間とルート要素</span><span class="sxs-lookup"><span data-stu-id="9464b-113">Namespace and Root Element</span></span>](#namespace21)

-   [<span data-ttu-id="9464b-114">データ型</span><span class="sxs-lookup"><span data-stu-id="9464b-114">Data types</span></span>](#data21)

-   [<span data-ttu-id="9464b-115">Name 要素</span><span class="sxs-lookup"><span data-stu-id="9464b-115">Name Element</span></span>](#name21)

-   [<span data-ttu-id="9464b-116">ID 要素</span><span class="sxs-lookup"><span data-stu-id="9464b-116">ID Element</span></span>](#id21)

-   [<span data-ttu-id="9464b-117">Version 要素</span><span class="sxs-lookup"><span data-stu-id="9464b-117">Version Element</span></span>](#version21)

-   [<span data-ttu-id="9464b-118">作成要素</span><span class="sxs-lookup"><span data-stu-id="9464b-118">Author Element</span></span>](#author21)

-   [<span data-ttu-id="9464b-119">プロセスとプロセス要素</span><span class="sxs-lookup"><span data-stu-id="9464b-119">Processes and Process Element</span></span>](#processes21)

-   [<span data-ttu-id="9464b-120">Application 要素</span><span class="sxs-lookup"><span data-stu-id="9464b-120">Application Element</span></span>](#application21)

-   [<span data-ttu-id="9464b-121">共通要素</span><span class="sxs-lookup"><span data-stu-id="9464b-121">Common Element</span></span>](#common21)

-   [<span data-ttu-id="9464b-122">SettingsLocationTemplate 要素</span><span class="sxs-lookup"><span data-stu-id="9464b-122">SettingsLocationTemplate Element</span></span>](#settingslocationtemplate21)

-   [<span data-ttu-id="9464b-123">付録: SettingsLocationTemplate .xsd</span><span class="sxs-lookup"><span data-stu-id="9464b-123">Appendix: SettingsLocationTemplate.xsd</span></span>](#appendix21)

### <a href="" id="xml21"></a><span data-ttu-id="9464b-124">XML 宣言とエンコード属性</span><span class="sxs-lookup"><span data-stu-id="9464b-124">XML Declaration and Encoding Attribute</span></span>

**<span data-ttu-id="9464b-125">必須: True</span><span class="sxs-lookup"><span data-stu-id="9464b-125">Mandatory: True</span></span>**

**<span data-ttu-id="9464b-126">種類: 文字列</span><span class="sxs-lookup"><span data-stu-id="9464b-126">Type: String</span></span>**

<span data-ttu-id="9464b-127">XML 宣言では、XML バージョン1.0 属性 ( &lt; ? XML バージョン = "1.0") を指定する必要があり &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="9464b-127">The XML declaration must specify the XML version 1.0 attribute (&lt;?xml version="1.0"&gt;).</span></span> <span data-ttu-id="9464b-128">UE-V Generator によって作成された設定場所テンプレートは、UTF-8 エンコードで保存されます。ただし、エンコードは明示的に指定されません。</span><span class="sxs-lookup"><span data-stu-id="9464b-128">Settings location templates created by the UE-V Generator are saved in UTF-8 encoding, although the encoding is not explicitly specified.</span></span> <span data-ttu-id="9464b-129">ベストプラクティスとして、この要素に encoding = "UTF-8" 属性を含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9464b-129">We recommend that you include the encoding="UTF-8" attribute in this element as a best practice.</span></span> <span data-ttu-id="9464b-130">製品に含まれているすべてのテンプレートにもこのタグが指定されています (Virtualization\\Templates では、Microsoft User Experience のドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="9464b-130">All templates included with the product specify this tag as well (see the documents in %ProgramFiles%\\Microsoft User Experience Virtualization\\Templates for reference).</span></span> <span data-ttu-id="9464b-131">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9464b-131">For example:</span></span>

`<?xml version="1.0" encoding="UTF-8"?>`

### <a href="" id="namespace21"></a><span data-ttu-id="9464b-132">名前空間とルート要素</span><span class="sxs-lookup"><span data-stu-id="9464b-132">Namespace and Root Element</span></span>

**<span data-ttu-id="9464b-133">必須: True</span><span class="sxs-lookup"><span data-stu-id="9464b-133">Mandatory: True</span></span>**

**<span data-ttu-id="9464b-134">種類: 文字列</span><span class="sxs-lookup"><span data-stu-id="9464b-134">Type: String</span></span>**

<span data-ttu-id="9464b-135">UE-V は、 https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate すべてのアプリケーションの名前空間を使います。</span><span class="sxs-lookup"><span data-stu-id="9464b-135">UE-V uses the https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate namespace for all applications.</span></span> <span data-ttu-id="9464b-136">SettingsLocationTemplate はルート要素であり、他のすべての要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9464b-136">SettingsLocationTemplate is the root element and contains all other elements.</span></span> <span data-ttu-id="9464b-137">このタグを使用して、すべてのテンプレートの参照設定の場所テンプレート:</span><span class="sxs-lookup"><span data-stu-id="9464b-137">Reference SettingsLocationTemplate in all templates using this tag:</span></span>

`<SettingsLocationTemplate xmlns='https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate'>`

### <a href="" id="data21"></a><span data-ttu-id="9464b-138">データ型</span><span class="sxs-lookup"><span data-stu-id="9464b-138">Data types</span></span>

<span data-ttu-id="9464b-139">UE-V アプリケーションテンプレートスキーマのデータ型を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9464b-139">These are the data types for the UE-V application template schema.</span></span>

<a href="" id="guid"></a><span data-ttu-id="9464b-140">**GUID**GUID は、標準のグローバル一意識別子の正規表現として "\ \ {\ [a-z-9 \]- {8} \ [a-fa-9 \]-\ [-] {4} [A-z-f0-9 \]-\ [a------ {4} {4} \]-\ [a- {12} ---------\]</span><span class="sxs-lookup"><span data-stu-id="9464b-140">**GUID** GUID describes a standard globally unique identifier regular expression in the form "\\{\[a-fA-F0-9\]{8}-\[a-fA-F0-9\]{4}-\[a-fA-F0-9\]{4}-\[a-fA-F0-9\]{4}-\[a-fA-F0-9\]{12}\\}".</span></span> <span data-ttu-id="9464b-141">これは、既知のフォルダーの書式を確認するために、filesetting¥ root¥ knownfolder 要素で使われます。</span><span class="sxs-lookup"><span data-stu-id="9464b-141">This is used in the Filesetting\\Root\\KnownFolder element to verify the formatting of well-known folders.</span></span>

<a href="" id="filenamestring"></a><span data-ttu-id="9464b-142">**FilenameString**FilenameString は、監視されるプロセスのファイル名を指します。</span><span class="sxs-lookup"><span data-stu-id="9464b-142">**FilenameString** FilenameString refers to the file name of a process to be monitored.</span></span> <span data-ttu-id="9464b-143">この値は、regex \ [^ \ \ \ \ \ \ \ \ \ \* \ \ | \ \ \ \* \ \ | &lt; &gt; ) で制限されています。/: \] + (つまり、バックスラッシュ文字、アスタリスクまたは疑問符のワイルドカード文字、パイプ文字、不等号、スラッシュ、またはコロン文字) が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-143">Its values are restricted by the regex \[^\\\\\\?\\\*\\|&lt;&gt;/:\]+, (that is, they may not contain backslash characters, asterisk or question mark wild-card characters, the pipe character, the greater than or less than sign, forward slash, or colon characters).</span></span>

<a href="" id="idstring"></a><span data-ttu-id="9464b-144">**Idstring**IDString は、アプリケーション要素の ID 値、SettingsLocationTemplate、共通要素を参照します (共通の設定を共有するアプリケーションスイートを記述するために使用されます)。</span><span class="sxs-lookup"><span data-stu-id="9464b-144">**IDString** IDString refers to the ID value of Application elements, SettingsLocationTemplate, and Common elements (used to describe application suites that share common settings).</span></span> <span data-ttu-id="9464b-145">FilenameString と同じ regex で制限されています (\ [^] \ \ \ \ \ \ \ \ \* \ \ | \ \ \ \* \ \ | &lt; &gt; )/:\]+).</span><span class="sxs-lookup"><span data-stu-id="9464b-145">It is restricted by the same regex as FilenameString (\[^\\\\\\?\\\*\\|&lt;&gt;/:\]+).</span></span>

<a href="" id="templateversion"></a><span data-ttu-id="9464b-146">**テンプレートのバージョン**TemplateVersion は、設定場所テンプレートのリビジョンを記述するために使用される整数値です。</span><span class="sxs-lookup"><span data-stu-id="9464b-146">**TemplateVersion** TemplateVersion is an integer value used to describe the revision of the settings location template.</span></span> <span data-ttu-id="9464b-147">この値の範囲は 0 ~ 2147483647 です。</span><span class="sxs-lookup"><span data-stu-id="9464b-147">Its value may range from 0 to 2147483647.</span></span>

<a href="" id="empty"></a><span data-ttu-id="9464b-148">**空**Empty は null 値を参照します。</span><span class="sxs-lookup"><span data-stu-id="9464b-148">**Empty** Empty refers to a null value.</span></span> <span data-ttu-id="9464b-149">これは、監視するプロセスがないことを示すために、Process\\ shellprocess で使われます。</span><span class="sxs-lookup"><span data-stu-id="9464b-149">This is used in Process\\ShellProcess to indicate that there is no process to monitor.</span></span> <span data-ttu-id="9464b-150">この値は、どのアプリケーションテンプレートでも使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="9464b-150">This value should not be used in any application templates.</span></span>

<a href="" id="author"></a><span data-ttu-id="9464b-151">**作成者**作成者データ型は、テンプレートの作成者を識別する複雑な型です。</span><span class="sxs-lookup"><span data-stu-id="9464b-151">**Author** The Author data type is a complex type that identifies the author of a template.</span></span> <span data-ttu-id="9464b-152">これには、**名前**と**メール**という2つの子要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9464b-152">It contains two child elements: **Name** and **Email**.</span></span> <span data-ttu-id="9464b-153">Author データ型では、Email 要素が省略可能である間、Name 要素は必須です。</span><span class="sxs-lookup"><span data-stu-id="9464b-153">Within the Author data type, the Name element is mandatory while the Email element is optional.</span></span> <span data-ttu-id="9464b-154">この型については、SettingsLocationTemplate 要素の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="9464b-154">This type is described in more detail under the SettingsLocationTemplate element.</span></span>

<a href="" id="range"></a><span data-ttu-id="9464b-155">**範囲**Range は、**最小値**と**最大値**の2つの子要素で構成される integer クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="9464b-155">**Range** Range defines an integer class consisting of two child elements: **Minimum** and **Maximum**.</span></span> <span data-ttu-id="9464b-156">このデータ型は、ProcessVersion データ型に実装されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-156">This data type is implemented in the ProcessVersion data type.</span></span> <span data-ttu-id="9464b-157">指定する場合は、最小値と最大値の両方が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-157">If specified, both Minimum and Maximum values must be included.</span></span>

<a href="" id="processversion"></a><span data-ttu-id="9464b-158">**Processversion**ProcessVersion は、4つの子要素を持つ型 ( **Major**、 **Minor**、 **Build**、および**Patch**) を定義します。</span><span class="sxs-lookup"><span data-stu-id="9464b-158">**ProcessVersion** ProcessVersion defines a type with four child elements: **Major**, **Minor**, **Build**, and **Patch**.</span></span> <span data-ttu-id="9464b-159">このデータ型は、プロセス要素によって ProductVersion と FileVersion 値を設定するために使われます。</span><span class="sxs-lookup"><span data-stu-id="9464b-159">This data type is used by the Process element to populate its ProductVersion and FileVersion values.</span></span> <span data-ttu-id="9464b-160">この型のデータは、範囲値です。</span><span class="sxs-lookup"><span data-stu-id="9464b-160">The data for this type is a Range value.</span></span> <span data-ttu-id="9464b-161">主要な子要素は必須であり、他の要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9464b-161">The Major child element is mandatory and the others are optional.</span></span>

<a href="" id="architecture"></a><span data-ttu-id="9464b-162">**アーキテクチャ**アーキテクチャでは、 **Win32**と**Win64**の2つの値を列挙します。</span><span class="sxs-lookup"><span data-stu-id="9464b-162">**Architecture** Architecture enumerates two possible values: **Win32** and **Win64**.</span></span> <span data-ttu-id="9464b-163">これらの値は、プロセスアーキテクチャを指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-163">These values are used to specify process architecture.</span></span>

<a href="" id="process"></a><span data-ttu-id="9464b-164">**プロセス**プロセスデータ型は、UE-V で監視されるプロセスを記述するために使用されるコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="9464b-164">**Process** The Process data type is a container used to describe processes to be monitored by UE-V.</span></span> <span data-ttu-id="9464b-165">これには、**ファイル名**、**アーキテクチャ**、**商品名**、 **filedescription**、 **productversion**、 **FileVersion**という6つの子要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9464b-165">It contains six child elements: **Filename**, **Architecture**, **ProductName**, **FileDescription**, **ProductVersion**, and **FileVersion**.</span></span> <span data-ttu-id="9464b-166">この表では、各要素のデータ型について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="9464b-166">This table details each element’s respective data type:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9464b-167">要素</span><span class="sxs-lookup"><span data-stu-id="9464b-167">Element</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="9464b-168">データ型</span><span class="sxs-lookup"><span data-stu-id="9464b-168">Data Type</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="9464b-169">Mandatory</span><span class="sxs-lookup"><span data-stu-id="9464b-169">Mandatory</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-170">ル</span><span class="sxs-lookup"><span data-stu-id="9464b-170">Filename</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-171">FilenameString</span><span class="sxs-lookup"><span data-stu-id="9464b-171">FilenameString</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-172">True</span><span class="sxs-lookup"><span data-stu-id="9464b-172">True</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-173">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="9464b-173">Architecture</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-174">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="9464b-174">Architecture</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-175">False</span><span class="sxs-lookup"><span data-stu-id="9464b-175">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-176">ProductName</span><span class="sxs-lookup"><span data-stu-id="9464b-176">ProductName</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-177">String</span><span class="sxs-lookup"><span data-stu-id="9464b-177">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-178">False</span><span class="sxs-lookup"><span data-stu-id="9464b-178">False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-179">ファイルの説明</span><span class="sxs-lookup"><span data-stu-id="9464b-179">FileDescription</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-180">String</span><span class="sxs-lookup"><span data-stu-id="9464b-180">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-181">False</span><span class="sxs-lookup"><span data-stu-id="9464b-181">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-182">ProductVersion</span><span class="sxs-lookup"><span data-stu-id="9464b-182">ProductVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-183">ProcessVersion</span><span class="sxs-lookup"><span data-stu-id="9464b-183">ProcessVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-184">False</span><span class="sxs-lookup"><span data-stu-id="9464b-184">False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-185">FileVersion</span><span class="sxs-lookup"><span data-stu-id="9464b-185">FileVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-186">ProcessVersion</span><span class="sxs-lookup"><span data-stu-id="9464b-186">ProcessVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-187">False</span><span class="sxs-lookup"><span data-stu-id="9464b-187">False</span></span></p></td>
</tr>
</tbody>
</table>

 

<a href="" id="processes"></a><span data-ttu-id="9464b-188">**プロセス**プロセスデータ型は、1つ以上のプロセス要素のコレクションのコンテナーを表します。</span><span class="sxs-lookup"><span data-stu-id="9464b-188">**Processes** The Processes data type represents a container for a collection of one or more Process elements.</span></span> <span data-ttu-id="9464b-189">次の2つの子要素がプロセスシーケンスの種類でサポートされています。**プロセス**と**shellprocess**。</span><span class="sxs-lookup"><span data-stu-id="9464b-189">Two child elements are supported in the Processes sequence type: **Process** and **ShellProcess**.</span></span> <span data-ttu-id="9464b-190">プロセスは、Process 型の要素であり、ShellProcess はデータ型が空であることを示します。</span><span class="sxs-lookup"><span data-stu-id="9464b-190">Process is an element of type Process and ShellProcess is of data type Empty.</span></span> <span data-ttu-id="9464b-191">シーケンスで少なくとも1つの項目を識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-191">At least one item must be identified in the sequence.</span></span>

<a href="" id="path"></a><span data-ttu-id="9464b-192">**Path**Path は、レジストリとファイルのパスを参照するために、RegistrySetting と FileSetting で消費されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-192">**Path** Path is consumed by RegistrySetting and FileSetting to refer to registry and file paths.</span></span> <span data-ttu-id="9464b-193">この要素は、 **Recursive**と**DeleteIfNotFound**の2つのオプション属性をサポートします。</span><span class="sxs-lookup"><span data-stu-id="9464b-193">This element supports two optional attributes: **Recursive** and **DeleteIfNotFound**.</span></span> <span data-ttu-id="9464b-194">どちらの値も default = "False" に設定されています。</span><span class="sxs-lookup"><span data-stu-id="9464b-194">Both values are set to default=”False”.</span></span>

<span data-ttu-id="9464b-195">Recursive は、パスとすべてのサブフォルダーがファイル設定に含まれていること、またはすべての子レジストリキーがレジストリ設定に含まれていることを示します。</span><span class="sxs-lookup"><span data-stu-id="9464b-195">Recursive indicates that the path and all subfolders are included for file settings or that all child registry keys are included for registry settings.</span></span> <span data-ttu-id="9464b-196">どちらの場合も、キャプチャされたデータには、現在のレベルのすべての項目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9464b-196">In both cases, all items at the current level are included in the data captured.</span></span> <span data-ttu-id="9464b-197">FileSettings オブジェクトの場合、指定したフォルダー内のすべてのファイルは、UE-V によってキャプチャされるデータに含まれますが、フォルダーは含まれません。</span><span class="sxs-lookup"><span data-stu-id="9464b-197">For a FileSettings object, all files within the specified folder are included in the data captured by UE-V but folders are not included.</span></span> <span data-ttu-id="9464b-198">レジストリパスの場合、現在のパスにあるすべての値がキャプチャされますが、子レジストリキーはキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="9464b-198">For registry paths, all values in the current path are captured but child registry keys are not captured.</span></span> <span data-ttu-id="9464b-199">どちらの場合も、大量のデータセットまたは多数の項目をキャプチャしないように注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-199">In both cases, care should be taken to avoid capturing large data sets or large numbers of items.</span></span>

<span data-ttu-id="9464b-200">DeleteIfNotFound 属性は、ユーザー設定の記憶域のパスデータから設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="9464b-200">The DeleteIfNotFound attribute removes the setting from the user’s settings storage path data.</span></span> <span data-ttu-id="9464b-201">これは、パッケージからこれらの設定を削除すると、設定の記憶域パスファイルサーバーに大量のディスク領域が保存される可能性がある場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="9464b-201">This may be desirable in cases where removing these settings from the package will save a large amount of disk space on the settings storage path file server.</span></span>

<a href="" id="filemask"></a><span data-ttu-id="9464b-202">**Filemask**FileMask Path で定義されているフォルダーに対して、特定の種類のファイルのみを指定します。</span><span class="sxs-lookup"><span data-stu-id="9464b-202">**FileMask** FileMask specifies only certain file types for the folder that is defined by Path.</span></span> <span data-ttu-id="9464b-203">たとえば、Path `C:\users\username\files` とファイルが含まれている可能性があり `*.txt` ます。テキストファイルのみを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="9464b-203">For example, Path might be `C:\users\username\files` and FileMask could be `*.txt` to include only text files.</span></span>

<a href="" id="registrysetting"></a><span data-ttu-id="9464b-204">**Registrysetting**RegistrySetting は、レジストリキーと値のコンテナーと、UE-V エージェントの一部に関連する目的の動作を表します。</span><span class="sxs-lookup"><span data-stu-id="9464b-204">**RegistrySetting** RegistrySetting represents a container for registry keys and values and the associated desired behavior on the part of the UE-V Agent.</span></span> <span data-ttu-id="9464b-205">4つの子要素は、 **path**、 **Name**、 **Exclude**、および値の**パス**と**名前**のシーケンスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-205">Four child elements are defined within this type: **Path**, **Name**, **Exclude**, and a sequence of the values **Path** and **Name**.</span></span>

<a href="" id="filesetting"></a><span data-ttu-id="9464b-206">**Filesetting**FileSetting には、ファイルとファイルのパスに関連付けられたパラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9464b-206">**FileSetting** FileSetting contains parameters associated with files and files paths.</span></span> <span data-ttu-id="9464b-207">4つの子要素 (**ルート**、 **Path**、 **filemask**、**除外**) が定義されています。</span><span class="sxs-lookup"><span data-stu-id="9464b-207">Four child elements are defined: **Root**, **Path**, **FileMask**, and **Exclude**.</span></span> <span data-ttu-id="9464b-208">Root は必須で、他のオプションは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9464b-208">Root is mandatory and the others are optional.</span></span>

<a href="" id="settings"></a><span data-ttu-id="9464b-209">**設定**設定は、特定のテンプレートに適用されるすべての設定のコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="9464b-209">**Settings** Settings is a container for all the settings that apply to a particular template.</span></span> <span data-ttu-id="9464b-210">これには、前に説明したレジストリ、File、SystemParameter、および CustomAction の各設定のインスタンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9464b-210">It contains instances of the Registry, File, SystemParameter, and CustomAction settings described earlier.</span></span> <span data-ttu-id="9464b-211">さらに、次の子要素も含めることができます。これには、次のような動作があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-211">In addition, it can also contain the following child elements with behaviors described:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9464b-212">要素</span><span class="sxs-lookup"><span data-stu-id="9464b-212">Element</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="9464b-213">説明</span><span class="sxs-lookup"><span data-stu-id="9464b-213">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-214">非同期</span><span class="sxs-lookup"><span data-stu-id="9464b-214">Asynchronous</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-215">非同期設定パッケージは、アプリケーションの起動をブロックせずに適用されるため、設定が適用されている間、アプリケーションは実行を開始できます。</span><span class="sxs-lookup"><span data-stu-id="9464b-215">Asynchronous settings packages are applied without blocking the application startup so that the application start proceeds while the settings are still being applied.</span></span> <span data-ttu-id="9464b-216">これは、SystemParameterSetting など、API を通じて非同期的に適用できる設定に役立ち <code>get/set</code> ます。</span><span class="sxs-lookup"><span data-stu-id="9464b-216">This is useful for settings that can be applied asynchronously, such as those <code>get/set</code> through an API, like SystemParameterSetting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-217">PreventOverlappingSynchronization</span><span class="sxs-lookup"><span data-stu-id="9464b-217">PreventOverlappingSynchronization</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-218">既定では、UE-V は、テンプレートを使用するアプリケーションの最後のインスタンスが閉じられている場合にのみ、アプリケーションの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="9464b-218">By default, UE-V only saves settings for an application when the last instance of an application using the template is closed.</span></span> <span data-ttu-id="9464b-219">この要素が "false" に設定されている場合、アプリケーションの他のインスタンスが実行されている場合でも、UE-V は設定をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="9464b-219">When this element is set to ‘false’, UE-V exports the settings even if other instances of an application are running.</span></span> <span data-ttu-id="9464b-220">適したテンプレート– UE-V に同梱されている共通要素セクションが含まれている場合は、このフラグを使って共有設定をアプリケーションの終了時に常にエクスポートし、最後のインスタンスが閉じられるまでは、アプリケーション固有の設定がエクスポートされないようにします。</span><span class="sxs-lookup"><span data-stu-id="9464b-220">Suited templates – those that include a Common element section– that are shipped with UE-V use this flag to enable shared settings to always export on application close, while preventing application-specific settings from exporting until the last instance is closed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-221">Always Applysettings</span><span class="sxs-lookup"><span data-stu-id="9464b-221">AlwaysApplySettings</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-222">(2.1 で導入されました)</span><span class="sxs-lookup"><span data-stu-id="9464b-222">(introduced in 2.1)</span></span></p>
<p><span data-ttu-id="9464b-223">このパラメーターを指定すると、パッケージとアプリケーションの現在の状態の違いがない場合でも、インポートした設定パッケージが強制的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-223">This parameter forces an imported settings package to be applied even if there are no differences between the package and the current state of the application.</span></span> <span data-ttu-id="9464b-224">このパラメーターは、設定のインポート速度が遅くなる可能性があるため、特別な場合にのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="9464b-224">This parameter should be used only in special cases since it can slow down settings import.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="name21"></a><span data-ttu-id="9464b-225">Name 要素</span><span class="sxs-lookup"><span data-stu-id="9464b-225">Name Element</span></span>

**<span data-ttu-id="9464b-226">必須: True</span><span class="sxs-lookup"><span data-stu-id="9464b-226">Mandatory: True</span></span>**

**<span data-ttu-id="9464b-227">種類: 文字列</span><span class="sxs-lookup"><span data-stu-id="9464b-227">Type: String</span></span>**

<span data-ttu-id="9464b-228">[名前] 設定場所テンプレートの一意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9464b-228">Name specifies a unique name for the settings location template.</span></span> <span data-ttu-id="9464b-229">これは、WMI、PowerShell、イベントビューアー、デバッグログでテンプレートを参照するときに表示するために使われます。</span><span class="sxs-lookup"><span data-stu-id="9464b-229">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="9464b-230">一般的に、バージョン情報を参照することは避けてください。これは、ProductVersion 要素から objected することができます。</span><span class="sxs-lookup"><span data-stu-id="9464b-230">In general, avoid referencing version information, as this can be objected from the ProductVersion element.</span></span> <span data-ttu-id="9464b-231">たとえば、ではなく、を指定し `<Name>My Application</Name>` `<Name>My Application 1.1</Name>` ます。</span><span class="sxs-lookup"><span data-stu-id="9464b-231">For example, specify `<Name>My Application</Name>` rather than `<Name>My Application 1.1</Name>`.</span></span>

<span data-ttu-id="9464b-232">**注** UE-V は外部の Dtd を参照しないため、設定場所テンプレートで名前付きエンティティを使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="9464b-232">**Note** UE-V does not reference external DTDs, so it is not possible to use named entities in a settings location template.</span></span> <span data-ttu-id="9464b-233">たとえば、登録されて &reg; いる商標記号®の参照には使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="9464b-233">For example, do not use &reg; to refer to the registered trade mark sign ®.</span></span> <span data-ttu-id="9464b-234">代わりに、このような種類の特殊文字 (®文字の & \ #174 など) を含める場合は、標準の番号付き参照を使います。</span><span class="sxs-lookup"><span data-stu-id="9464b-234">Instead, use canonical numbered references to include these types of special characters, for example, &\#174 for the ® character.</span></span> <span data-ttu-id="9464b-235">この規則は、このドキュメント内のすべての文字列値に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-235">This rule applies to all string values in this document.</span></span>

<span data-ttu-id="9464b-236"><http://www.w3.org/TR/xhtml1/dtds.html>文字エンティティの完全な一覧については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9464b-236">See <http://www.w3.org/TR/xhtml1/dtds.html> for a complete list of character entities.</span></span> <span data-ttu-id="9464b-237">UTF-8 でエンコードされたドキュメントには、Unicode 文字が直接含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-237">UTF-8-encoded documents may include the Unicode characters directly.</span></span> <span data-ttu-id="9464b-238">UE-V Generator を使用してテンプレートを保存すると、文字エンティティが自動的に Unicode 表現に変換されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-238">Saving templates through the UE-V Generator converts character entities to their Unicode representations automatically.</span></span>

 

### <a href="" id="id21"></a><span data-ttu-id="9464b-239">ID 要素</span><span class="sxs-lookup"><span data-stu-id="9464b-239">ID Element</span></span>

**<span data-ttu-id="9464b-240">必須: True</span><span class="sxs-lookup"><span data-stu-id="9464b-240">Mandatory: True</span></span>**

**<span data-ttu-id="9464b-241">種類: 文字列</span><span class="sxs-lookup"><span data-stu-id="9464b-241">Type: String</span></span>**

<span data-ttu-id="9464b-242">ID は、特定のテンプレートの一意の識別子を入力します。</span><span class="sxs-lookup"><span data-stu-id="9464b-242">ID populates a unique identifier for a particular template.</span></span> <span data-ttu-id="9464b-243">このタグは、UE-V Agent が実行時にテンプレートを参照するために使用するプライマリ識別子になります (たとえば、Get-UevTemplate と Get-UevTemplateProgram PowerShell コマンドレットの出力を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="9464b-243">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime (for example, see the output of the Get-UevTemplate and Get-UevTemplateProgram PowerShell cmdlets).</span></span> <span data-ttu-id="9464b-244">慣例により、このタグにはスペースを含めないでください。これによってスクリプトが簡素化されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-244">By convention, this tag should not contain any spaces, which simplifies scripting.</span></span> <span data-ttu-id="9464b-245">この要素には、やなどのテンプレートを簡単に識別できるように、アプリのバージョン番号を指定する必要があり `<ID>MicrosoftCalculator6</ID>` `<ID>MicrosoftOffice2010Win64</ID>` ます。</span><span class="sxs-lookup"><span data-stu-id="9464b-245">Version numbers of applications should be specified in this element to allow for easy identification of the template, such as `<ID>MicrosoftCalculator6</ID>` or `<ID>MicrosoftOffice2010Win64</ID>`.</span></span>

### <a href="" id="version21"></a><span data-ttu-id="9464b-246">Version 要素</span><span class="sxs-lookup"><span data-stu-id="9464b-246">Version Element</span></span>

**<span data-ttu-id="9464b-247">必須: True</span><span class="sxs-lookup"><span data-stu-id="9464b-247">Mandatory: True</span></span>**

**<span data-ttu-id="9464b-248">種類: Integer</span><span class="sxs-lookup"><span data-stu-id="9464b-248">Type: Integer</span></span>**

**<span data-ttu-id="9464b-249">最小値: 0</span><span class="sxs-lookup"><span data-stu-id="9464b-249">Minimum Value: 0</span></span>**

**<span data-ttu-id="9464b-250">最大値: 2147483647</span><span class="sxs-lookup"><span data-stu-id="9464b-250">Maximum Value: 2147483647</span></span>**

<span data-ttu-id="9464b-251">[バージョン] は、変更の管理追跡用の設定場所テンプレートのバージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="9464b-251">Version identifies the version of the settings location template for administrative tracking of changes.</span></span> <span data-ttu-id="9464b-252">UE-V Generator は、テンプレートが保存されるたびに、この数値を1つずつ自動的にインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="9464b-252">The UE-V Generator automatically increments this number by one each time the template is saved.</span></span> <span data-ttu-id="9464b-253">このフィールドは整数である必要があることに注意してください。小数点以下の値 `<Version>2.5</Version>` は使用できません。</span><span class="sxs-lookup"><span data-stu-id="9464b-253">Notice that this field must be a whole number integer; fractional values, such as `<Version>2.5</Version>` are not allowed.</span></span>

<span data-ttu-id="9464b-254">**ヒント:** XML コメントタグを使用して、バージョンの変更に関するメモを保存でき `<!-- -->` ます。たとえば、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9464b-254">**Hint:** You can save notes about version changes using XML comment tags `<!-- -->`, for example:</span></span>

```xml
  <!--
     Version History

     Version 1 Jul 05, 2012 Initial template created by Generator - Denise@Contoso.com
     Version 2 Jul 31, 2012 Added support for app.exe v2.1.3 - Mark@Contoso.com
     Version 3 Jan 01, 2013 Added font settings support - Mark@Contoso.com
     Version 4 Jan 31, 2013 Added support for plugin settings - Tony@Contoso.com
   -->
  <Version>4</Version>
```

<span data-ttu-id="9464b-255">**重要** この値は、次のような場合に、既存のテンプレートに新しいバージョンのテンプレートを適用する必要があるかどうかを確認するために照会されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-255">**Important** This value is queried to determine if a new version of a template should be applied to an existing template in these instances:</span></span>

-   <span data-ttu-id="9464b-256">スケジュールされたテンプレートの自動更新タスクの実行時</span><span class="sxs-lookup"><span data-stu-id="9464b-256">When the scheduled Template Auto Update task executes</span></span>

-   <span data-ttu-id="9464b-257">更新プログラム UevTemplate PowerShell コマンドレットが実行されるとき</span><span class="sxs-lookup"><span data-stu-id="9464b-257">When the Update-UevTemplate PowerShell cmdlet is executed</span></span>

-   <span data-ttu-id="9464b-258">WMI 経由で microsoft\\uev: SettingsLocationTemplate Update メソッドが呼び出された場合</span><span class="sxs-lookup"><span data-stu-id="9464b-258">When the microsoft\\uev:SettingsLocationTemplate Update method is called through WMI</span></span>

 

### <a href="" id="author21"></a><span data-ttu-id="9464b-259">作成要素</span><span class="sxs-lookup"><span data-stu-id="9464b-259">Author Element</span></span>

**<span data-ttu-id="9464b-260">必須: False</span><span class="sxs-lookup"><span data-stu-id="9464b-260">Mandatory: False</span></span>**

**<span data-ttu-id="9464b-261">種類: 文字列</span><span class="sxs-lookup"><span data-stu-id="9464b-261">Type: String</span></span>**

<span data-ttu-id="9464b-262">[作成者] は、設定場所テンプレートの作成者を指定します。</span><span class="sxs-lookup"><span data-stu-id="9464b-262">Author identifies the creator of the settings location template.</span></span> <span data-ttu-id="9464b-263">2つのオプションの子要素がサポートされています。**名前**と**メール**</span><span class="sxs-lookup"><span data-stu-id="9464b-263">Two optional child elements are supported: **Name** and **Email**.</span></span> <span data-ttu-id="9464b-264">どちらの属性も省略可能ですが、メールの子要素が指定されている場合は、Name 要素と共に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-264">Both attributes are optional, but, if the Email child element is specified, it must be accompanied by the Name element.</span></span> <span data-ttu-id="9464b-265">[Author] は、設定場所テンプレートの連絡先の完全な名前を示し、メールは作成者のメールアドレスを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-265">Author refers to the full name of the contact for the settings location template, and email should refer to an email address for the author.</span></span> <span data-ttu-id="9464b-266">この情報は、一般に公開されるテンプレート ( [Ue-v テンプレートギャラリー](https://gallery.technet.microsoft.com/site/search?f%5B0%5D.Type=RootCategory&f%5B0%5D.Value=UE-V)など) に含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9464b-266">We recommend that you include this information in templates published publicly, for example, on the [UE-V Template Gallery](https://gallery.technet.microsoft.com/site/search?f%5B0%5D.Type=RootCategory&f%5B0%5D.Value=UE-V).</span></span>

### <a href="" id="processes21"></a><span data-ttu-id="9464b-267">プロセスとプロセス要素</span><span class="sxs-lookup"><span data-stu-id="9464b-267">Processes and Process Element</span></span>

**<span data-ttu-id="9464b-268">必須: True</span><span class="sxs-lookup"><span data-stu-id="9464b-268">Mandatory: True</span></span>**

**<span data-ttu-id="9464b-269">Type: Element</span><span class="sxs-lookup"><span data-stu-id="9464b-269">Type: Element</span></span>**

<span data-ttu-id="9464b-270">プロセスには、少なくとも1つの要素が含まれます。これには、 `<Process>` **ファイル名**、**アーキテクチャ**、**商品名**、 **filedescription**、 **productversion**、 **FileVersion**という子要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9464b-270">Processes contains at least one `<Process>` element, which in turn contains the following child elements: **Filename**, **Architecture**, **ProductName**, **FileDescription**, **ProductVersion**, and **FileVersion**.</span></span> <span data-ttu-id="9464b-271">ファイル名の子要素は必須であり、他の項目は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9464b-271">The Filename child element is mandatory and the others are optional.</span></span> <span data-ttu-id="9464b-272">完全に入力された要素には、次の例のようなタグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9464b-272">A fully populated element contains tags similar to this example:</span></span>

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <Architecture>Win64</Architecture>
  <ProductName> MyApplication </ProductName>
  <FileDescription>MyApplication.exe</FileDescription>
  <ProductVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </FileVersion>
</Process>
```

### <span data-ttu-id="9464b-273">ル</span><span class="sxs-lookup"><span data-stu-id="9464b-273">Filename</span></span>

**<span data-ttu-id="9464b-274">必須: True</span><span class="sxs-lookup"><span data-stu-id="9464b-274">Mandatory: True</span></span>**

**<span data-ttu-id="9464b-275">種類: 文字列</span><span class="sxs-lookup"><span data-stu-id="9464b-275">Type: String</span></span>**

<span data-ttu-id="9464b-276">Filename は、ファイルシステムに表示される実行可能ファイルの実際のファイル名を指します。</span><span class="sxs-lookup"><span data-stu-id="9464b-276">Filename refers to the actual file name of the executable as it appears in the file system.</span></span> <span data-ttu-id="9464b-277">この要素は、テンプレートがプロセスに適用されるかどうかを評価するために UE-V が使う主要な条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="9464b-277">This element specifies the primary criterion that UE-V uses to evaluate whether a template applies to a process or not.</span></span> <span data-ttu-id="9464b-278">この要素は、設定場所テンプレート XML で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-278">This element must be specified in the settings location template XML.</span></span>

<span data-ttu-id="9464b-279">有効なファイル名は、正規表現 \ [^] \ \ \ \ \ \ \ \* \ \ | \ \ \ \* \ \ | &lt; &gt;/: \] +、つまり、バックスラッシュ文字、アスタリスクまたは疑問符のワイルドカード文字、パイプ文字、不等号、スラッシュ、またはコロン (\ \?) が含まれていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-279">Valid filenames must not match the regular expression \[^\\\\\\?\\\*\\|&lt;&gt;/:\]+, that is, they may not contain backslash characters, asterisk or question mark wild-card characters, the pipe character, the greater than or less than sign, forward slash, or colon (the \\ ?</span></span> <span data-ttu-id="9464b-280">\* |&lt; &gt; /または: 文字)。</span><span class="sxs-lookup"><span data-stu-id="9464b-280">\* | &lt; &gt; / or : characters.).</span></span>

<span data-ttu-id="9464b-281">**ヒント:** この regex に対して文字列をテストするには、PowerShell コマンドウィンドウを使って、実行可能ファイルの名前を**ファイル**名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="9464b-281">**Hint:** To test a string against this regex, use a PowerShell command window and substitute your executable’s name for **YourFileName**:</span></span>

`"YourFileName.exe" -match  "[\\\?\*\|<>/:]+"`

<span data-ttu-id="9464b-282">値が**True**の場合は、文字列に不正な文字が含まれていることを示します。</span><span class="sxs-lookup"><span data-stu-id="9464b-282">A value of **True** indicates that the string contains illegal characters.</span></span> <span data-ttu-id="9464b-283">次に、不正な値の例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="9464b-283">Here are some examples of illegal values:</span></span>

-   <span data-ttu-id="9464b-284">\\\\server\\share\\program.exe</span><span class="sxs-lookup"><span data-stu-id="9464b-284">\\\\server\\share\\program.exe</span></span>

-   <span data-ttu-id="9464b-285">プログラム \ \* .exe</span><span class="sxs-lookup"><span data-stu-id="9464b-285">Program\*.exe</span></span>

-   <span data-ttu-id="9464b-286">Pro? ram.exe</span><span class="sxs-lookup"><span data-stu-id="9464b-286">Pro?ram.exe</span></span>

-   <span data-ttu-id="9464b-287">プログラム &lt; 1 &gt; . .exe</span><span class="sxs-lookup"><span data-stu-id="9464b-287">Program&lt;1&gt;.exe</span></span>

<span data-ttu-id="9464b-288">**注** UE-V Generator は、指定された文字より大きい文字と小さい文字をそれぞれエンコードし &gt; &lt; ます。</span><span class="sxs-lookup"><span data-stu-id="9464b-288">**Note** The UE-V Generator encodes the greater than and less than characters as &gt; and &lt; respectively.</span></span>

 

<span data-ttu-id="9464b-289">まれに、ファイル名の値に .exe 拡張子が含まれているとは限りませんが、値の一部として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-289">In rare circumstances, the FileName value will not necessarily include the .exe extension, but it should be specified as part of the value.</span></span> <span data-ttu-id="9464b-290">たとえば、 `<Filename>MyApplictication.exe</Filename>` の代わりにを指定する必要があり `<Filename>MyApplictication</Filename>` ます。</span><span class="sxs-lookup"><span data-stu-id="9464b-290">For example, `<Filename>MyApplictication.exe</Filename>` should be specified instead of `<Filename>MyApplictication</Filename>`.</span></span> <span data-ttu-id="9464b-291">実行可能ファイルの実際の名前が "MyApplication.exe" の場合、2番目の例では、テンプレートはプロセスに適用されません。</span><span class="sxs-lookup"><span data-stu-id="9464b-291">The second example will not apply the template to the process if the actual name of the executable file is “MyApplication.exe”.</span></span>

### <span data-ttu-id="9464b-292">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="9464b-292">Architecture</span></span>

**<span data-ttu-id="9464b-293">必須: False</span><span class="sxs-lookup"><span data-stu-id="9464b-293">Mandatory: False</span></span>**

**<span data-ttu-id="9464b-294">Type: Architecture (文字列)</span><span class="sxs-lookup"><span data-stu-id="9464b-294">Type: Architecture (String)</span></span>**

<span data-ttu-id="9464b-295">アーキテクチャとは、ターゲットの実行可能ファイルがコンパイルされたプロセッサアーキテクチャを指します。</span><span class="sxs-lookup"><span data-stu-id="9464b-295">Architecture refers to the processor architecture for which the target executable was compiled.</span></span> <span data-ttu-id="9464b-296">有効な値は、32ビットアプリケーションまたは64ビットアプリケーション用の Win64 の Win32 です。</span><span class="sxs-lookup"><span data-stu-id="9464b-296">Valid values are Win32 for 32-bit applications or Win64 for 64-bit applications.</span></span> <span data-ttu-id="9464b-297">存在する場合、このタグは、設定場所テンプレートを特定のアプリケーションアーキテクチャに適用することを制限します。</span><span class="sxs-lookup"><span data-stu-id="9464b-297">If present, this tag limits the applicability of the settings location template to a particular application architecture.</span></span> <span data-ttu-id="9464b-298">この例については、UE-V に含まれる% programfiles% ¥ Microsoft User Experience Virtualization\\templates\\ MicrosoftOffice2010Win32.xml と MicrosoftOffice2010Win64.xml ファイルを比較します。</span><span class="sxs-lookup"><span data-stu-id="9464b-298">For an example of this, compare the %ProgramFiles%\\Microsoft User Experience Virtualization\\templates\\ MicrosoftOffice2010Win32.xml and MicrosoftOffice2010Win64.xml files included with UE-V.</span></span> <span data-ttu-id="9464b-299">これは、異なるバージョンの実行可能ファイル間で相対パスが変更された場合、またはプロセッサアーキテクチャを切り替えるときに設定が追加または削除された場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9464b-299">This is useful when relative paths change between different versions of an executable or if settings have been added or removed when moving from one processor architecture to another.</span></span>

<span data-ttu-id="9464b-300">この要素が存在しない場合、設定場所テンプレートはプロセスのアーキテクチャを無視し、ファイル名とその他の属性が適用されている場合、32と64ビットの両方のプロセスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-300">If this element is absent, the settings location template ignores the process’ architecture and applies to both 32 and 64-bit processes if the file name and other attributes apply.</span></span>

<span data-ttu-id="9464b-301">**注** UE-V は、このバージョンの ARM プロセッサをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9464b-301">**Note** UE-V does not support ARM processors in this version.</span></span>

 

### <span data-ttu-id="9464b-302">ProductName</span><span class="sxs-lookup"><span data-stu-id="9464b-302">ProductName</span></span>

**<span data-ttu-id="9464b-303">必須: False</span><span class="sxs-lookup"><span data-stu-id="9464b-303">Mandatory: False</span></span>**

**<span data-ttu-id="9464b-304">種類: 文字列</span><span class="sxs-lookup"><span data-stu-id="9464b-304">Type: String</span></span>**

<span data-ttu-id="9464b-305">ProductName は、管理目的またはレポート用に製品を識別するために使用されるオプションの要素です。</span><span class="sxs-lookup"><span data-stu-id="9464b-305">ProductName is an optional element used to identify a product for administrative purposes or reporting.</span></span> <span data-ttu-id="9464b-306">ProductName はファイル名とは異なり、その値に対する正規表現の制限はありません。</span><span class="sxs-lookup"><span data-stu-id="9464b-306">ProductName differs from Filename in that there are no regular expression restrictions on its value.</span></span> <span data-ttu-id="9464b-307">これにより、実行可能ファイル名が明確でない可能性のあるプロセスの説明をより簡単に理解できます。</span><span class="sxs-lookup"><span data-stu-id="9464b-307">This allows for more easily understood descriptions of a process where the executable name may not be obvious.</span></span> <span data-ttu-id="9464b-308">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9464b-308">For example:</span></span>

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <ProductName>My Application 6.x by Contoso.com</ProductName>
  <ProductVersion>
    <Major Minimum="6" Maximum="6" />
  </ProductVersion>
</Process>
```

### <span data-ttu-id="9464b-309">ファイルの説明</span><span class="sxs-lookup"><span data-stu-id="9464b-309">FileDescription</span></span>

**<span data-ttu-id="9464b-310">必須: False</span><span class="sxs-lookup"><span data-stu-id="9464b-310">Mandatory: False</span></span>**

**<span data-ttu-id="9464b-311">種類: 文字列</span><span class="sxs-lookup"><span data-stu-id="9464b-311">Type: String</span></span>**

<span data-ttu-id="9464b-312">FileDescription は、実行可能ファイルの管理の説明を可能にするオプションのタグです。</span><span class="sxs-lookup"><span data-stu-id="9464b-312">FileDescription is an optional tag that allows for an administrative description of the executable file.</span></span> <span data-ttu-id="9464b-313">これは無料のテキストフィールドであり、実行可能ファイルの機能を識別する必要があるソフトウェアパッケージ内の複数の実行可能ファイルを区別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9464b-313">This is a free text field and can be useful in distinguishing multiple executables within a software package where there is a need to identify the function of the executable.</span></span>

<span data-ttu-id="9464b-314">たとえば、次に示すように、適したアプリケーションでは、2つの実行可能ファイル (MyApplication.exe と MyApplicationHelper.exe) の機能についての通知を表示すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-314">For example, in a suited application, it might be useful to provide reminders about the function of two executables (MyApplication.exe and MyApplicationHelper.exe), as shown here:</span></span>

```xml
<Processes>
  <Process>
    <Filename>MyApplication.exe</Filename>
    <FileDescription>My Application Main Engine</ FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
  <Process>
    <Filename>MyApplicationHelper.exe</Filename>
    <FileDescription>My Application Background Process Executable</FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
</Processes>
```

### <span data-ttu-id="9464b-315">ProductVersion</span><span class="sxs-lookup"><span data-stu-id="9464b-315">ProductVersion</span></span>

**<span data-ttu-id="9464b-316">必須: False</span><span class="sxs-lookup"><span data-stu-id="9464b-316">Mandatory: False</span></span>**

**<span data-ttu-id="9464b-317">種類: 文字列</span><span class="sxs-lookup"><span data-stu-id="9464b-317">Type: String</span></span>**

<span data-ttu-id="9464b-318">ProductVersion は、ファイルのメジャーバージョンとマイナー製品バージョン、およびビルドとパッチレベルを指します。</span><span class="sxs-lookup"><span data-stu-id="9464b-318">ProductVersion refers to the major and minor product versions of a file, as well as a build and patch level.</span></span> <span data-ttu-id="9464b-319">ProductVersion は省略可能な要素ですが、指定する場合は、少なくとも主要な子要素が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-319">ProductVersion is an optional element, but if specified, it must contain at least the Major child element.</span></span> <span data-ttu-id="9464b-320">この値は、最小値の "X" 最大値 = "Y" (X と Y は整数) の範囲を表す必要があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-320">The value must express a range in the form Minimum="X" Maximum="Y" where X and Y are integers.</span></span> <span data-ttu-id="9464b-321">最小値と最大値は同じにすることができます。</span><span class="sxs-lookup"><span data-stu-id="9464b-321">The Minimum and Maximum values can be identical.</span></span>

<span data-ttu-id="9464b-322">製品とファイルのバージョンの要素が指定されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-322">The product and file version elements may be left unspecified.</span></span> <span data-ttu-id="9464b-323">これにより、テンプレートは "バージョンに依存しない" という意味になります。つまり、指定した実行可能ファイルのすべてのバージョンにテンプレートが適用されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-323">Doing so makes the template “version agnostic”, meaning that the template will apply to all versions of the specified executable.</span></span>

**<span data-ttu-id="9464b-324">例 1:</span><span class="sxs-lookup"><span data-stu-id="9464b-324">Example 1:</span></span>**

<span data-ttu-id="9464b-325">製品バージョン: 1.0 は、UE-V Generator で指定されている次の XML を生成します。</span><span class="sxs-lookup"><span data-stu-id="9464b-325">Product version: 1.0 specified in the UE-V Generator produces the following XML:</span></span>

```xml
<ProductVersion>
  <Major Minimum="1" Maximum="1" />
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

**<span data-ttu-id="9464b-326">例 2:</span><span class="sxs-lookup"><span data-stu-id="9464b-326">Example 2:</span></span>**

<span data-ttu-id="9464b-327">ファイルバージョン: UE-V Generator で指定された5.0.2.1000 は、次の XML を生成します。</span><span class="sxs-lookup"><span data-stu-id="9464b-327">File version: 5.0.2.1000 specified in the UE-V Generator produces the following XML:</span></span>

```xml
<FileVersion>
  <Major Minimum="5" Maximum="5" />
  <Minor Minimum="0" Maximum="0" />
  <Build Minimum="2" Maximum="2" />
  <Patch Minimum="1000" Maximum="1000" />
</FileVersion>
```

**<span data-ttu-id="9464b-328">間違った例1–不完全な範囲:</span><span class="sxs-lookup"><span data-stu-id="9464b-328">Incorrect Example 1 – incomplete range:</span></span>**

<span data-ttu-id="9464b-329">最小属性のみが存在します。</span><span class="sxs-lookup"><span data-stu-id="9464b-329">Only the Minimum attribute is present.</span></span> <span data-ttu-id="9464b-330">範囲には最大値も含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-330">Maximum must be included in a range as well.</span></span>

```xml
<ProductVersion>
  <Major Minimum="2" />
</ProductVersion>
```

**<span data-ttu-id="9464b-331">間違った例2–主要要素のない Minor:</span><span class="sxs-lookup"><span data-stu-id="9464b-331">Incorrect Example 2 – Minor specified without Major element:</span></span>**

<span data-ttu-id="9464b-332">Minor 要素のみが存在します。</span><span class="sxs-lookup"><span data-stu-id="9464b-332">Only the Minor element is present.</span></span> <span data-ttu-id="9464b-333">メジャーも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-333">Major must be included as well.</span></span>

```xml
<ProductVersion>
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

### <span data-ttu-id="9464b-334">FileVersion</span><span class="sxs-lookup"><span data-stu-id="9464b-334">FileVersion</span></span>

**<span data-ttu-id="9464b-335">必須: False</span><span class="sxs-lookup"><span data-stu-id="9464b-335">Mandatory: False</span></span>**

**<span data-ttu-id="9464b-336">種類: 文字列</span><span class="sxs-lookup"><span data-stu-id="9464b-336">Type: String</span></span>**

<span data-ttu-id="9464b-337">FileVersion は、公開されたアプリケーションのリリースバージョンと、コンポーネント実行可能ファイルの内部ビルドの詳細を区別します。</span><span class="sxs-lookup"><span data-stu-id="9464b-337">FileVersion differentiates between the release version of a published application and the internal build details of a component executable.</span></span> <span data-ttu-id="9464b-338">ほとんどの商用アプリケーションでは、これらの番号は同じです。</span><span class="sxs-lookup"><span data-stu-id="9464b-338">For the majority of commercial applications, these numbers are identical.</span></span> <span data-ttu-id="9464b-339">実際には、ファイルの製品バージョンはファイルの一般的なバージョン id を示していますが、ファイルバージョンはファイルの特定のビルドを示します (修正プログラムや更新プログラムの場合など)。</span><span class="sxs-lookup"><span data-stu-id="9464b-339">Where they vary, the product version of a file indicates a generic version identification of a file, while file version indicates a specific build of a file (as in the case of a hotfix or update).</span></span> <span data-ttu-id="9464b-340">これにより、検出ロジックを壊すことなくファイルを一意に識別できます。</span><span class="sxs-lookup"><span data-stu-id="9464b-340">This uniquely identifies files without breaking detection logic.</span></span>

<span data-ttu-id="9464b-341">特定の実行可能ファイルの製品バージョンとファイルバージョンを確認するには、Windows エクスプローラーでファイルを右クリックし、[プロパティ] を選択して、[詳細] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9464b-341">To determine the product version and file version of a particular executable, right-click on the file in Windows Explorer, select Properties, then click on the Details tab.</span></span>

<span data-ttu-id="9464b-342">アプリケーションの FileVersion 要素を含めることで、細かい微調整による検出ロジックを行うことができますが、ほとんどのアプリケーションには必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9464b-342">Including a FileVersion element for an application allows for more granular fine-tuning detection logic, but is not necessary for most applications.</span></span> <span data-ttu-id="9464b-343">ProductVersion 要素の設定が最初にチェックされ、次に FileVersion がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="9464b-343">The ProductVersion element settings are checked first, and then FileVersion is checked.</span></span> <span data-ttu-id="9464b-344">より限定的な設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-344">The more restrictive setting will apply.</span></span>

<span data-ttu-id="9464b-345">FileVersion の子要素と構文規則は、ProductVersion バージョンと同じです。</span><span class="sxs-lookup"><span data-stu-id="9464b-345">The child elements and syntax rules for FileVersion are identical to those of ProductVersion.</span></span>

```xml
<Process>
  <Filename>MSACCESS.EXE</Filename>
  <Architecture>Win32</Architecture>
  <ProductVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </FileVersion>
</Process>
```

### <a href="" id="application21"></a><span data-ttu-id="9464b-346">Application 要素</span><span class="sxs-lookup"><span data-stu-id="9464b-346">Application Element</span></span>

<span data-ttu-id="9464b-347">アプリケーションは、特定のアプリケーションに適用される設定のコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="9464b-347">Application is a container for settings that apply to a particular application.</span></span> <span data-ttu-id="9464b-348">これは、次のフィールド/型のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="9464b-348">It is a collection of the following fields/types.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9464b-349">フィールド/型</span><span class="sxs-lookup"><span data-stu-id="9464b-349">Field/Type</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="9464b-350">説明</span><span class="sxs-lookup"><span data-stu-id="9464b-350">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-351">Name (名前)</span><span class="sxs-lookup"><span data-stu-id="9464b-351">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-352">設定場所テンプレートの一意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9464b-352">Specifies a unique name for the settings location template.</span></span> <span data-ttu-id="9464b-353">これは、WMI、PowerShell、イベントビューアー、デバッグログでテンプレートを参照するときに表示するために使われます。</span><span class="sxs-lookup"><span data-stu-id="9464b-353">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="9464b-354">詳細については、「名前」を参照してください <a href="#name21" data-raw-source="[Name](#name21)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="9464b-354">For more information, see <a href="#name21" data-raw-source="[Name](#name21)">Name</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-355">ID</span><span class="sxs-lookup"><span data-stu-id="9464b-355">ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-356">特定のテンプレートの一意の識別子を設定します。</span><span class="sxs-lookup"><span data-stu-id="9464b-356">Populates a unique identifier for a particular template.</span></span> <span data-ttu-id="9464b-357">このタグは、UE-V Agent が実行時にテンプレートを参照するために使用するプライマリ識別子になります。</span><span class="sxs-lookup"><span data-stu-id="9464b-357">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime.</span></span> <span data-ttu-id="9464b-358">詳細については、「ID」を参照してください <a href="#id21" data-raw-source="[ID](#id21)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="9464b-358">For more information, see <a href="#id21" data-raw-source="[ID](#id21)">ID</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-359">説明</span><span class="sxs-lookup"><span data-stu-id="9464b-359">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-360">テンプレートの説明 (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="9464b-360">An optional description of the template.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-361">LocalizedNames</span><span class="sxs-lookup"><span data-stu-id="9464b-361">LocalizedNames</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-362">UI に表示されるオプションの名前。言語ロケールによってローカライズされます。</span><span class="sxs-lookup"><span data-stu-id="9464b-362">An optional name displayed in the UI, localized by a language locale.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-363">LocalizedDescriptions</span><span class="sxs-lookup"><span data-stu-id="9464b-363">LocalizedDescriptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-364">言語ロケールによってローカライズされた省略可能なテンプレートの説明です。</span><span class="sxs-lookup"><span data-stu-id="9464b-364">An optional template description localized by a language locale.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-365">バージョン</span><span class="sxs-lookup"><span data-stu-id="9464b-365">Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-366">変更の管理追跡用の設定場所テンプレートのバージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="9464b-366">Identifies the version of the settings location template for administrative tracking of changes.</span></span> <span data-ttu-id="9464b-367">詳細については、「バージョン」を参照してください <a href="#version21" data-raw-source="[Version](#version21)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="9464b-367">For more information, see <a href="#version21" data-raw-source="[Version](#version21)">Version</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-368">DeferToMSAccount</span><span class="sxs-lookup"><span data-stu-id="9464b-368">DeferToMSAccount</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-369">このテンプレートが Microsoft アカウントと組み合わせて有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="9464b-369">Controls whether this template is enabled in conjunction with a Microsoft account or not.</span></span> <span data-ttu-id="9464b-370">コンピューター上のユーザーに対して MSA の同期が有効になっている場合、このテンプレートは自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="9464b-370">If MSA syncing is enabled for a user on a machine, then this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-371">DeferToOffice365</span><span class="sxs-lookup"><span data-stu-id="9464b-371">DeferToOffice365</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-372">MSA の場合と同様に、このテンプレートを Office365 と組み合わせて有効にするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="9464b-372">Similar to MSA, this controls whether this template is enabled in conjunction with Office365.</span></span> <span data-ttu-id="9464b-373">設定の同期に Office 365 が使用されている場合、このテンプレートは自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="9464b-373">If Office 365 is being used to sync settings, this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-374">FixedProfile (2.1 で導入)</span><span class="sxs-lookup"><span data-stu-id="9464b-374">FixedProfile (Introduced in 2.1)</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-375">このテンプレートは、この要素内で指定されたプロファイルにのみ関連付けることができます。また、WMI または PowerShell を使用して変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="9464b-375">Specifies that this template can only be associated with the profile specified within this element, and cannot be changed via WMI or PowerShell.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-376">プロセス</span><span class="sxs-lookup"><span data-stu-id="9464b-376">Processes</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-377">1つ以上のプロセス要素のコレクションのコンテナー。</span><span class="sxs-lookup"><span data-stu-id="9464b-377">A container for a collection of one or more Process elements.</span></span> <span data-ttu-id="9464b-378">詳細については、「プロセス」を参照してください <a href="#processes21" data-raw-source="[Processes](#processes21)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="9464b-378">For more information, see <a href="#processes21" data-raw-source="[Processes](#processes21)">Processes</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-379">設定</span><span class="sxs-lookup"><span data-stu-id="9464b-379">Settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-380">特定のテンプレートに適用されるすべての設定のコンテナー。</span><span class="sxs-lookup"><span data-stu-id="9464b-380">A container for all the settings that apply to a particular template.</span></span> <span data-ttu-id="9464b-381">これには、Registry、File、SystemParameter、および CustomAction の各設定のインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9464b-381">It contains instances of the Registry, File, SystemParameter, and CustomAction settings.</span></span> <span data-ttu-id="9464b-382">詳細については、「 <strong> </strong> データ型の設定」を参照してください <a href="#data21" data-raw-source="[Data types](#data21)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="9464b-382">For more information, see <strong>Settings</strong> in <a href="#data21" data-raw-source="[Data types](#data21)">Data types</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="common21"></a><span data-ttu-id="9464b-383">共通要素</span><span class="sxs-lookup"><span data-stu-id="9464b-383">Common Element</span></span>

<span data-ttu-id="9464b-384">Common は Application 要素と似ていますが、常に、2つ以上のアプリケーション要素に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="9464b-384">Common is similar to an Application element, but it is always associated with two or more Application elements.</span></span> <span data-ttu-id="9464b-385">共通セクションは、これらのアプリケーションインスタンス間で共有される一連の設定を表します。</span><span class="sxs-lookup"><span data-stu-id="9464b-385">The Common section represents the set of settings that are shared between those Application instances.</span></span> <span data-ttu-id="9464b-386">これは、次のフィールド/型のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="9464b-386">It is a collection of the following fields/types.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9464b-387">フィールド/型</span><span class="sxs-lookup"><span data-stu-id="9464b-387">Field/Type</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="9464b-388">説明</span><span class="sxs-lookup"><span data-stu-id="9464b-388">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-389">Name (名前)</span><span class="sxs-lookup"><span data-stu-id="9464b-389">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-390">設定場所テンプレートの一意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9464b-390">Specifies a unique name for the settings location template.</span></span> <span data-ttu-id="9464b-391">これは、WMI、PowerShell、イベントビューアー、デバッグログでテンプレートを参照するときに表示するために使われます。</span><span class="sxs-lookup"><span data-stu-id="9464b-391">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="9464b-392">詳細については、「名前」を参照してください <a href="#name21" data-raw-source="[Name](#name21)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="9464b-392">For more information, see <a href="#name21" data-raw-source="[Name](#name21)">Name</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-393">ID</span><span class="sxs-lookup"><span data-stu-id="9464b-393">ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-394">特定のテンプレートの一意の識別子を設定します。</span><span class="sxs-lookup"><span data-stu-id="9464b-394">Populates a unique identifier for a particular template.</span></span> <span data-ttu-id="9464b-395">このタグは、UE-V Agent が実行時にテンプレートを参照するために使用するプライマリ識別子になります。</span><span class="sxs-lookup"><span data-stu-id="9464b-395">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime.</span></span> <span data-ttu-id="9464b-396">詳細については、「ID」を参照してください <a href="#id21" data-raw-source="[ID](#id21)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="9464b-396">For more information, see <a href="#id21" data-raw-source="[ID](#id21)">ID</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-397">説明</span><span class="sxs-lookup"><span data-stu-id="9464b-397">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-398">テンプレートの説明 (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="9464b-398">An optional description of the template.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-399">LocalizedNames</span><span class="sxs-lookup"><span data-stu-id="9464b-399">LocalizedNames</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-400">UI に表示されるオプションの名前。言語ロケールによってローカライズされます。</span><span class="sxs-lookup"><span data-stu-id="9464b-400">An optional name displayed in the UI, localized by a language locale.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-401">LocalizedDescriptions</span><span class="sxs-lookup"><span data-stu-id="9464b-401">LocalizedDescriptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-402">言語ロケールによってローカライズされた省略可能なテンプレートの説明です。</span><span class="sxs-lookup"><span data-stu-id="9464b-402">An optional template description localized by a language locale.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-403">バージョン</span><span class="sxs-lookup"><span data-stu-id="9464b-403">Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-404">変更の管理追跡用の設定場所テンプレートのバージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="9464b-404">Identifies the version of the settings location template for administrative tracking of changes.</span></span> <span data-ttu-id="9464b-405">詳細については、「バージョン」を参照してください <a href="#version21" data-raw-source="[Version](#version21)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="9464b-405">For more information, see <a href="#version21" data-raw-source="[Version](#version21)">Version</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-406">DeferToMSAccount</span><span class="sxs-lookup"><span data-stu-id="9464b-406">DeferToMSAccount</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-407">このテンプレートが Microsoft アカウントと組み合わせて有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="9464b-407">Controls whether this template is enabled in conjunction with a Microsoft account or not.</span></span> <span data-ttu-id="9464b-408">コンピューター上のユーザーに対して MSA の同期が有効になっている場合、このテンプレートは自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="9464b-408">If MSA syncing is enabled for a user on a machine, then this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-409">DeferToOffice365</span><span class="sxs-lookup"><span data-stu-id="9464b-409">DeferToOffice365</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-410">MSA の場合と同様に、このテンプレートを Office365 と組み合わせて有効にするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="9464b-410">Similar to MSA, this controls whether this template is enabled in conjunction with Office365.</span></span> <span data-ttu-id="9464b-411">設定の同期に Office 365 が使用されている場合、このテンプレートは自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="9464b-411">If Office 365 is being used to sync settings, this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-412">FixedProfile (2.1 で導入)</span><span class="sxs-lookup"><span data-stu-id="9464b-412">FixedProfile (Introduced in 2.1)</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-413">このテンプレートは、この要素内で指定されたプロファイルにのみ関連付けることができます。また、WMI または PowerShell を使用して変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="9464b-413">Specifies that this template can only be associated with the profile specified within this element, and cannot be changed via WMI or PowerShell.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-414">設定</span><span class="sxs-lookup"><span data-stu-id="9464b-414">Settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-415">特定のテンプレートに適用されるすべての設定のコンテナー。</span><span class="sxs-lookup"><span data-stu-id="9464b-415">A container for all the settings that apply to a particular template.</span></span> <span data-ttu-id="9464b-416">これには、Registry、File、SystemParameter、および CustomAction の各設定のインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9464b-416">It contains instances of the Registry, File, SystemParameter, and CustomAction settings.</span></span> <span data-ttu-id="9464b-417">詳細については、「 <strong> </strong> データ型の設定」を参照してください <a href="#data21" data-raw-source="[Data types](#data21)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="9464b-417">For more information, see <strong>Settings</strong> in <a href="#data21" data-raw-source="[Data types](#data21)">Data types</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="settingslocationtemplate21"></a><span data-ttu-id="9464b-418">SettingsLocationTemplate 要素</span><span class="sxs-lookup"><span data-stu-id="9464b-418">SettingsLocationTemplate Element</span></span>

<span data-ttu-id="9464b-419">この要素は、1つのアプリケーションまたは一連のアプリケーションの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="9464b-419">This element defines the settings for a single application or a suite of applications.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9464b-420">フィールド/型</span><span class="sxs-lookup"><span data-stu-id="9464b-420">Field/Type</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="9464b-421">説明</span><span class="sxs-lookup"><span data-stu-id="9464b-421">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-422">Name (名前)</span><span class="sxs-lookup"><span data-stu-id="9464b-422">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-423">設定場所テンプレートの一意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9464b-423">Specifies a unique name for the settings location template.</span></span> <span data-ttu-id="9464b-424">これは、WMI、PowerShell、イベントビューアー、デバッグログでテンプレートを参照するときに表示するために使われます。</span><span class="sxs-lookup"><span data-stu-id="9464b-424">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="9464b-425">詳細については、「名前」を参照してください <a href="#name21" data-raw-source="[Name](#name21)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="9464b-425">For more information, see <a href="#name21" data-raw-source="[Name](#name21)">Name</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-426">ID</span><span class="sxs-lookup"><span data-stu-id="9464b-426">ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-427">特定のテンプレートの一意の識別子を設定します。</span><span class="sxs-lookup"><span data-stu-id="9464b-427">Populates a unique identifier for a particular template.</span></span> <span data-ttu-id="9464b-428">このタグは、UE-V Agent が実行時にテンプレートを参照するために使用するプライマリ識別子になります。</span><span class="sxs-lookup"><span data-stu-id="9464b-428">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime.</span></span> <span data-ttu-id="9464b-429">詳細については、「ID」を参照してください <a href="#id21" data-raw-source="[ID](#id21)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="9464b-429">For more information, see <a href="#id21" data-raw-source="[ID](#id21)">ID</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-430">説明</span><span class="sxs-lookup"><span data-stu-id="9464b-430">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-431">テンプレートの説明 (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="9464b-431">An optional description of the template.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-432">LocalizedNames</span><span class="sxs-lookup"><span data-stu-id="9464b-432">LocalizedNames</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-433">UI に表示されるオプションの名前。言語ロケールによってローカライズされます。</span><span class="sxs-lookup"><span data-stu-id="9464b-433">An optional name displayed in the UI, localized by a language locale.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-434">LocalizedDescriptions</span><span class="sxs-lookup"><span data-stu-id="9464b-434">LocalizedDescriptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-435">言語ロケールによってローカライズされた省略可能なテンプレートの説明です。</span><span class="sxs-lookup"><span data-stu-id="9464b-435">An optional template description localized by a language locale.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="appendix21"></a><span data-ttu-id="9464b-436">付録: SettingsLocationTemplate .xsd</span><span class="sxs-lookup"><span data-stu-id="9464b-436">Appendix: SettingsLocationTemplate.xsd</span></span>

<span data-ttu-id="9464b-437">次に示すのは、要素、子要素、属性、パラメーターが表示された SettingsLocationTemplate です。</span><span class="sxs-lookup"><span data-stu-id="9464b-437">Here is the SettingsLocationTemplate.xsd file showing its elements, child elements, attributes, and parameters:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="UevSettingsLocationTemplate"
  targetNamespace="https://schemas.microsoft.com/UserExperienceVirtualization/2013A/SettingsLocationTemplate"
  elementFormDefault="qualified"
  xmlns="https://schemas.microsoft.com/UserExperienceVirtualization/2013A/SettingsLocationTemplate"
  xmlns:mstns="https://schemas.microsoft.com/UserExperienceVirtualization/2013A/SettingsLocationTemplate"
  xmlns:xs="http://www.w3.org/2001/XMLSchema">

    <xs:simpleType name="Guid">
        <xs:restriction base="xs:string">
            <xs:pattern value="\{[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{12}\}" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="FilenameString">
        <xs:restriction base="xs:string">
            <xs:pattern value="[^\\\?\*\|&lt;&gt;/:]+" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="IDString">
        <xs:restriction base="xs:string">
            <xs:pattern value="[^\\\?\*\|&lt;&gt;/:.]+" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="CompositeIDString">
        <xs:restriction base="xs:string">
            <xs:pattern value="[^\\\?\*\|&lt;&gt;/:.]+([.][^\\\?\*\|&lt;&gt;/:.]+)?" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="TemplateVersion">
        <xs:restriction base="xs:integer">
            <xs:minInclusive value="0" />
            <xs:maxInclusive value="2147483647" />
        </xs:restriction>
    </xs:simpleType>

    <xs:complexType name="Empty">
        <xs:sequence/>
    </xs:complexType>

    <xs:complexType name="LocalizedString">
        <xs:simpleContent>
            <xs:extension base="xs:string">
                <xs:attribute name="Locale" type="xs:string" use="required"/>
            </xs:extension>
        </xs:simpleContent>
    </xs:complexType>

    <xs:complexType name="LocalizedName">
        <xs:sequence>
            <xs:element name="Name" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="LocalizedDescription">
        <xs:sequence>
            <xs:element name="Description" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="ReplacedTemplates">
      <xs:sequence>
        <xs:element name="ID" type="CompositeIDString" minOccurs="1" maxOccurs="unbounded" />
    </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Author">
        <xs:all>
            <xs:element name="Name" type="xs:string" minOccurs="1" />
            <xs:element name="Email" type="xs:string" minOccurs="0" />
        </xs:all>
    </xs:complexType>

    <xs:complexType name="Range">
        <xs:attribute name="Minimum" type="xs:integer" use="required"/>
        <xs:attribute name="Maximum" type="xs:integer" use="required"/>
    </xs:complexType>

    <xs:complexType name="ProcessVersion">
        <xs:sequence>
            <xs:element name="Major" type="Range" minOccurs="1" />
            <xs:element name="Minor" type="Range" minOccurs="0" />
            <xs:element name="Build" type="Range" minOccurs="0" />
            <xs:element name="Patch" type="Range" minOccurs="0" />
        </xs:sequence>
    </xs:complexType>

    <xs:simpleType name="Architecture">
        <xs:restriction base="xs:string">
            <xs:enumeration value="Win32"/>
            <xs:enumeration value="Win64"/>
        </xs:restriction>
    </xs:simpleType>

    <xs:complexType name="Process">
        <xs:sequence>
            <xs:element name="Filename" type="FilenameString" minOccurs="1" />
            <xs:element name="Architecture" type="Architecture" minOccurs="0" />
            <xs:element name="ProductName" type="xs:string" minOccurs="0" />
            <xs:element name="FileDescription" type="xs:string" minOccurs="0" />
            <xs:element name="ProductVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
            <xs:element name="FileVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Processes">
        <xs:sequence>
            <xs:choice minOccurs="1">
                <xs:element name="Process" type="Process" />
                <xs:element name="ShellProcess" type="Empty" />
            </xs:choice>
            <xs:element name="Process" type="Process" minOccurs="0" maxOccurs="unbounded" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Path">
        <xs:simpleContent>
            <xs:extension base="xs:string">
                <xs:attribute name="Recursive" type="xs:boolean" default="false"/>
                <xs:attribute name="DeleteIfNotFound" type="xs:boolean" default="false"/>
            </xs:extension>
        </xs:simpleContent>
    </xs:complexType>

    <xs:complexType name="RegistrySetting">
        <xs:sequence>
            <xs:element name="Path" type="Path" />
            <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
            <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                    <xs:sequence>
                        <xs:element name="Path" type="Path" minOccurs="0" />
                        <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
                    </xs:sequence>
                </xs:complexType>
            </xs:element>
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="FileSetting">
        <xs:sequence>

            <xs:element name="Root">
                <xs:complexType>
                    <xs:choice>
                        <xs:element name="KnownFolder" type="Guid" />
                        <xs:element name="RegistryEntry" type="xs:string" />
                        <xs:element name="EnvironmentVariable" type="xs:string" />
                    </xs:choice>
                </xs:complexType>
            </xs:element>

            <xs:element name="Path" minOccurs="0" type="Path" />
            <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded"/>

            <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                    <xs:sequence>
                        <xs:element name="Path" type="Path" minOccurs="0" />
                        <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
                    </xs:sequence>
                </xs:complexType>
            </xs:element>

        </xs:sequence>
    </xs:complexType>

    <xs:simpleType name="CustomActionSetting">
        <xs:restriction base="xs:anyURI"/>
    </xs:simpleType>

    <xs:simpleType name="SystemParameterSetting">
        <xs:restriction base="xs:string">

            <!-- Accessibility parameters -->
            <xs:enumeration value="AccessTimeout"/>
            <xs:enumeration value="AudioDescription"/>
            <xs:enumeration value="ClientAreaAnimation"/>
            <xs:enumeration value="DisableOverlappedContent"/>
            <xs:enumeration value="FilterKeys"/>
            <xs:enumeration value="FocusBorderHeight"/>
            <xs:enumeration value="FocusBorderWidth"/>
            <xs:enumeration value="HighContrast"/>
            <xs:enumeration value="MessageDuration"/>
            <xs:enumeration value="MouseClickLock"/>
            <xs:enumeration value="MouseClickLockTime"/>
            <xs:enumeration value="MouseKeys"/>
            <xs:enumeration value="MouseSonar"/>
            <xs:enumeration value="MouseVanish"/>
            <xs:enumeration value="ScreenReader"/>
            <xs:enumeration value="ShowSounds"/>
            <xs:enumeration value="SoundSentry"/>
            <xs:enumeration value="StickyKeys"/>
            <xs:enumeration value="ToggleKeys"/>

            <!-- Input parameters -->
            <xs:enumeration value="Beep"/>
            <xs:enumeration value="BlockSendInputResets"/>
            <xs:enumeration value="DefaultInputLang"/>
            <xs:enumeration value="DoubleClickTime"/>
            <xs:enumeration value="DoubleClkHeight"/>
            <xs:enumeration value="DoubleClkWidth"/>
            <xs:enumeration value="KeyboardCues"/>
            <xs:enumeration value="KeyboardDelay"/>
            <xs:enumeration value="KeyboardPref"/>
            <xs:enumeration value="KeyboardSpeed"/>
            <xs:enumeration value="Mouse"/>
            <xs:enumeration value="MouseButtonSwap"/>
            <xs:enumeration value="MouseHoverHeight"/>
            <xs:enumeration value="MouseHoverTime"/>
            <xs:enumeration value="MouseHoverWidth"/>
            <xs:enumeration value="MouseSpeed"/>
            <xs:enumeration value="MouseTrails"/>
            <xs:enumeration value="SnapToDefButton"/>
            <xs:enumeration value="WheelScrollChars"/>
            <xs:enumeration value="WheelScrollLines"/>

            <!-- Desktop parameters (limited subset) -->
            <xs:enumeration value="DeskWallpaper"/>
            <xs:enumeration value="DesktopColor"/>

        </xs:restriction>
    </xs:simpleType>

    <xs:complexType name="Settings">
        <xs:sequence>
            <xs:element name="Asynchronous" type="xs:boolean" minOccurs="0" />
            <xs:element name="PreventOverlappingSynchronization" type="xs:boolean" minOccurs="0" />
            <xs:element name="AlwaysApplySettings" type="xs:boolean" minOccurs="0" />
            <xs:choice minOccurs="0" maxOccurs="unbounded">
                <xs:element name="Registry" type="RegistrySetting" />
                <xs:element name="File" type="FileSetting" />
                <xs:element name="SystemParameter" type="SystemParameterSetting" />
                <xs:element name="CustomAction" type="CustomActionSetting" />
            </xs:choice>
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Common">
        <xs:sequence>
            <xs:element name="Name" type="xs:string" />
            <xs:element name="ID" type="IDString" />
            <xs:element name="ReplacedTemplates" type="ReplacedTemplates" minOccurs="0" />
            <xs:element name="Description" type="xs:string" minOccurs="0" />
            <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
            <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
            <xs:element name="Version" type="xs:integer" />
            <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
            <xs:element name="DeferToOffice365" type="Empty" minOccurs="0" />
            <xs:element name="Settings" type="Settings" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Application">
        <xs:sequence>
            <xs:element name="Name" type="xs:string" />
            <xs:element name="ID" type="IDString" />
            <xs:element name="ReplacedTemplates" type="ReplacedTemplates" minOccurs="0" />
            <xs:element name="Description" type="xs:string" minOccurs="0" />
            <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
            <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
            <xs:element name="Version" type="xs:integer" />
            <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
            <xs:element name="DeferToOffice365" type="Empty" minOccurs="0" />
            <xs:element name="Processes" type="Processes" />
            <xs:element name="Settings" type="Settings" />
        </xs:sequence>
    </xs:complexType>


    <xs:element name="SettingsLocationTemplate">
        <xs:complexType>
            <xs:sequence>

                <xs:element name="Name" type="xs:string" />
                <xs:element name="ID" type="IDString" />
                <xs:element name="Description" type="xs:string" minOccurs="0" />
                <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
                <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />

                <xs:choice>

                    <!-- Single application -->
                    <xs:sequence>
                        <xs:element name="ReplacedTemplates" type="ReplacedTemplates" minOccurs="0" />
                        <xs:element name="Version" type="TemplateVersion" />
                        <xs:element name="Author" type="Author" minOccurs="0" />
                        <xs:element name="FixedProfile" type="xs:string"  minOccurs="0" />
                        <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
                        <xs:element name="DeferToOffice365" type="Empty" minOccurs="0" />
                        <xs:element name="Processes" type="Processes" />
                        <xs:element name="Settings" type="Settings" />
                    </xs:sequence>

                    <!-- Suite of applications -->
                    <xs:sequence>
                        <xs:element name="ManageSuiteOnly" type="xs:boolean" minOccurs="0" />
                        <xs:element name="Author" type="Author" minOccurs="0" />
                        <xs:element name="FixedProfile" type="xs:string"  minOccurs="0" />
                        <xs:element name="Common" type="Common" />
                        <xs:element name="Application" type="Application" minOccurs="2" maxOccurs="unbounded" />
                    </xs:sequence>

                </xs:choice>

            </xs:sequence>
        </xs:complexType>
    </xs:element>
    <!-- SettingsLocationTemplate -->

</xs:schema>
```

## <span data-ttu-id="9464b-438">UE-V 2.0 アプリケーションテンプレートのスキーマリファレンス</span><span class="sxs-lookup"><span data-stu-id="9464b-438">UE-V 2.0 Application Template Schema Reference</span></span>


<span data-ttu-id="9464b-439">このセクションでは、UE-V 2.0 設定の場所テンプレートの XML 構造について詳しく説明し、このファイルの編集に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="9464b-439">This section details the XML structure of the UE-V 2.0 settings location template and provides guidance for editing this file.</span></span>

### <span data-ttu-id="9464b-440">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9464b-440">In This Section</span></span>

-   [<span data-ttu-id="9464b-441">XML 宣言とエンコード属性</span><span class="sxs-lookup"><span data-stu-id="9464b-441">XML Declaration and Encoding Attribute</span></span>](#xml)

-   [<span data-ttu-id="9464b-442">名前空間とルート要素</span><span class="sxs-lookup"><span data-stu-id="9464b-442">Namespace and Root Element</span></span>](#namespace)

-   [<span data-ttu-id="9464b-443">データ型</span><span class="sxs-lookup"><span data-stu-id="9464b-443">Data types</span></span>](#data)

-   [<span data-ttu-id="9464b-444">Name 要素</span><span class="sxs-lookup"><span data-stu-id="9464b-444">Name Element</span></span>](#name)

-   [<span data-ttu-id="9464b-445">ID 要素</span><span class="sxs-lookup"><span data-stu-id="9464b-445">ID Element</span></span>](#id)

-   [<span data-ttu-id="9464b-446">Version 要素</span><span class="sxs-lookup"><span data-stu-id="9464b-446">Version Element</span></span>](#version)

-   [<span data-ttu-id="9464b-447">作成要素</span><span class="sxs-lookup"><span data-stu-id="9464b-447">Author Element</span></span>](#author)

-   [<span data-ttu-id="9464b-448">プロセスとプロセス要素</span><span class="sxs-lookup"><span data-stu-id="9464b-448">Processes and Process Element</span></span>](#processes)

-   [<span data-ttu-id="9464b-449">Application 要素</span><span class="sxs-lookup"><span data-stu-id="9464b-449">Application Element</span></span>](#application)

-   [<span data-ttu-id="9464b-450">共通要素</span><span class="sxs-lookup"><span data-stu-id="9464b-450">Common Element</span></span>](#common)

-   [<span data-ttu-id="9464b-451">SettingsLocationTemplate 要素</span><span class="sxs-lookup"><span data-stu-id="9464b-451">SettingsLocationTemplate Element</span></span>](#settingslocationtemplate)

-   [<span data-ttu-id="9464b-452">付録: SettingsLocationTemplate .xsd</span><span class="sxs-lookup"><span data-stu-id="9464b-452">Appendix: SettingsLocationTemplate.xsd</span></span>](#appendix)

### <a href="" id="xml"></a><span data-ttu-id="9464b-453">XML 宣言とエンコード属性</span><span class="sxs-lookup"><span data-stu-id="9464b-453">XML Declaration and Encoding Attribute</span></span>

**<span data-ttu-id="9464b-454">必須: True</span><span class="sxs-lookup"><span data-stu-id="9464b-454">Mandatory: True</span></span>**

**<span data-ttu-id="9464b-455">種類: 文字列</span><span class="sxs-lookup"><span data-stu-id="9464b-455">Type: String</span></span>**

<span data-ttu-id="9464b-456">XML 宣言では、XML バージョン1.0 属性 ( &lt; ? XML バージョン = "1.0") を指定する必要があり &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="9464b-456">The XML declaration must specify the XML version 1.0 attribute (&lt;?xml version="1.0"&gt;).</span></span> <span data-ttu-id="9464b-457">UE-V Generator によって作成された設定場所テンプレートは、UTF-8 エンコードで保存されます。ただし、エンコードは明示的に指定されません。</span><span class="sxs-lookup"><span data-stu-id="9464b-457">Settings location templates created by the UE-V Generator are saved in UTF-8 encoding, although the encoding is not explicitly specified.</span></span> <span data-ttu-id="9464b-458">ベストプラクティスとして、この要素に encoding = "UTF-8" 属性を含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9464b-458">We recommend that you include the encoding="UTF-8" attribute in this element as a best practice.</span></span> <span data-ttu-id="9464b-459">製品に含まれているすべてのテンプレートにもこのタグが指定されています (Virtualization\\Templates では、Microsoft User Experience のドキュメントを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="9464b-459">All templates included with the product specify this tag as well (see the documents in %ProgramFiles%\\Microsoft User Experience Virtualization\\Templates for reference).</span></span> <span data-ttu-id="9464b-460">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9464b-460">For example:</span></span>

`<?xml version="1.0" encoding="UTF-8"?>`

### <a href="" id="namespace"></a><span data-ttu-id="9464b-461">名前空間とルート要素</span><span class="sxs-lookup"><span data-stu-id="9464b-461">Namespace and Root Element</span></span>

**<span data-ttu-id="9464b-462">必須: True</span><span class="sxs-lookup"><span data-stu-id="9464b-462">Mandatory: True</span></span>**

**<span data-ttu-id="9464b-463">種類: 文字列</span><span class="sxs-lookup"><span data-stu-id="9464b-463">Type: String</span></span>**

<span data-ttu-id="9464b-464">UE-V は、 https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate すべてのアプリケーションの名前空間を使います。</span><span class="sxs-lookup"><span data-stu-id="9464b-464">UE-V uses the https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate namespace for all applications.</span></span> <span data-ttu-id="9464b-465">SettingsLocationTemplate はルート要素であり、他のすべての要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9464b-465">SettingsLocationTemplate is the root element and contains all other elements.</span></span> <span data-ttu-id="9464b-466">このタグを使用して、すべてのテンプレートの参照設定の場所テンプレート:</span><span class="sxs-lookup"><span data-stu-id="9464b-466">Reference SettingsLocationTemplate in all templates using this tag:</span></span>

`<SettingsLocationTemplate xmlns='https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate'>`

### <a href="" id="data"></a><span data-ttu-id="9464b-467">データ型</span><span class="sxs-lookup"><span data-stu-id="9464b-467">Data types</span></span>

<span data-ttu-id="9464b-468">UE-V アプリケーションテンプレートスキーマのデータ型を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9464b-468">These are the data types for the UE-V application template schema.</span></span>

<a href="" id="guid"></a><span data-ttu-id="9464b-469">**GUID**GUID は、標準のグローバル一意識別子の正規表現として "\ \ {\ [a-z-9 \]- {8} \ [a-fa-9 \]-\ [-] {4} [A-z-f0-9 \]-\ [a------ {4} {4} \]-\ [a- {12} ---------\]</span><span class="sxs-lookup"><span data-stu-id="9464b-469">**GUID** GUID describes a standard globally unique identifier regular expression in the form "\\{\[a-fA-F0-9\]{8}-\[a-fA-F0-9\]{4}-\[a-fA-F0-9\]{4}-\[a-fA-F0-9\]{4}-\[a-fA-F0-9\]{12}\\}".</span></span> <span data-ttu-id="9464b-470">これは、既知のフォルダーの書式を確認するために、filesetting¥ root¥ knownfolder 要素で使われます。</span><span class="sxs-lookup"><span data-stu-id="9464b-470">This is used in the Filesetting\\Root\\KnownFolder element to verify the formatting of well-known folders.</span></span>

<a href="" id="filenamestring"></a><span data-ttu-id="9464b-471">**FilenameString**FilenameString は、監視されるプロセスのファイル名を指します。</span><span class="sxs-lookup"><span data-stu-id="9464b-471">**FilenameString** FilenameString refers to the file name of a process to be monitored.</span></span> <span data-ttu-id="9464b-472">この値は、regex \ [^ \ \ \ \ \ \ \ \ \ \* \ \ | \ \ \ \* \ \ | &lt; &gt; ) で制限されています。/: \] + (つまり、バックスラッシュ文字、アスタリスクまたは疑問符のワイルドカード文字、パイプ文字、不等号、スラッシュ、またはコロン文字) が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-472">Its values are restricted by the regex \[^\\\\\\?\\\*\\|&lt;&gt;/:\]+, (that is, they may not contain backslash characters, asterisk or question mark wild-card characters, the pipe character, the greater than or less than sign, forward slash, or colon characters).</span></span>

<a href="" id="idstring"></a><span data-ttu-id="9464b-473">**Idstring**IDString は、アプリケーション要素の ID 値、SettingsLocationTemplate、共通要素を参照します (共通の設定を共有するアプリケーションスイートを記述するために使用されます)。</span><span class="sxs-lookup"><span data-stu-id="9464b-473">**IDString** IDString refers to the ID value of Application elements, SettingsLocationTemplate, and Common elements (used to describe application suites that share common settings).</span></span> <span data-ttu-id="9464b-474">FilenameString と同じ regex で制限されています (\ [^] \ \ \ \ \ \ \ \ \* \ \ | \ \ \ \* \ \ | &lt; &gt; )/:\]+).</span><span class="sxs-lookup"><span data-stu-id="9464b-474">It is restricted by the same regex as FilenameString (\[^\\\\\\?\\\*\\|&lt;&gt;/:\]+).</span></span>

<a href="" id="templateversion"></a><span data-ttu-id="9464b-475">**テンプレートのバージョン**TemplateVersion は、設定場所テンプレートのリビジョンを記述するために使用される整数値です。</span><span class="sxs-lookup"><span data-stu-id="9464b-475">**TemplateVersion** TemplateVersion is an integer value used to describe the revision of the settings location template.</span></span> <span data-ttu-id="9464b-476">この値の範囲は 0 ~ 2147483647 です。</span><span class="sxs-lookup"><span data-stu-id="9464b-476">Its value may range from 0 to 2147483647.</span></span>

<a href="" id="empty"></a><span data-ttu-id="9464b-477">**空**Empty は null 値を参照します。</span><span class="sxs-lookup"><span data-stu-id="9464b-477">**Empty** Empty refers to a null value.</span></span> <span data-ttu-id="9464b-478">これは、監視するプロセスがないことを示すために、Process\\ shellprocess で使われます。</span><span class="sxs-lookup"><span data-stu-id="9464b-478">This is used in Process\\ShellProcess to indicate that there is no process to monitor.</span></span> <span data-ttu-id="9464b-479">この値は、どのアプリケーションテンプレートでも使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="9464b-479">This value should not be used in any application templates.</span></span>

<a href="" id="author"></a><span data-ttu-id="9464b-480">**作成者**作成者データ型は、テンプレートの作成者を識別する複雑な型です。</span><span class="sxs-lookup"><span data-stu-id="9464b-480">**Author** The Author data type is a complex type that identifies the author of a template.</span></span> <span data-ttu-id="9464b-481">これには、**名前**と**メール**という2つの子要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9464b-481">It contains two child elements: **Name** and **Email**.</span></span> <span data-ttu-id="9464b-482">Author データ型では、Email 要素が省略可能である間、Name 要素は必須です。</span><span class="sxs-lookup"><span data-stu-id="9464b-482">Within the Author data type, the Name element is mandatory while the Email element is optional.</span></span> <span data-ttu-id="9464b-483">この型については、SettingsLocationTemplate 要素の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="9464b-483">This type is described in more detail under the SettingsLocationTemplate element.</span></span>

<a href="" id="range"></a><span data-ttu-id="9464b-484">**範囲**Range は、**最小値**と**最大値**の2つの子要素で構成される integer クラスを定義します。</span><span class="sxs-lookup"><span data-stu-id="9464b-484">**Range** Range defines an integer class consisting of two child elements: **Minimum** and **Maximum**.</span></span> <span data-ttu-id="9464b-485">このデータ型は、ProcessVersion データ型に実装されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-485">This data type is implemented in the ProcessVersion data type.</span></span> <span data-ttu-id="9464b-486">指定する場合は、最小値と最大値の両方が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-486">If specified, both Minimum and Maximum values must be included.</span></span>

<a href="" id="processversion"></a><span data-ttu-id="9464b-487">**Processversion**ProcessVersion は、4つの子要素を持つ型 ( **Major**、 **Minor**、 **Build**、および**Patch**) を定義します。</span><span class="sxs-lookup"><span data-stu-id="9464b-487">**ProcessVersion** ProcessVersion defines a type with four child elements: **Major**, **Minor**, **Build**, and **Patch**.</span></span> <span data-ttu-id="9464b-488">このデータ型は、プロセス要素によって ProductVersion と FileVersion 値を設定するために使われます。</span><span class="sxs-lookup"><span data-stu-id="9464b-488">This data type is used by the Process element to populate its ProductVersion and FileVersion values.</span></span> <span data-ttu-id="9464b-489">この型のデータは、範囲値です。</span><span class="sxs-lookup"><span data-stu-id="9464b-489">The data for this type is a Range value.</span></span> <span data-ttu-id="9464b-490">主要な子要素は必須であり、他の要素は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9464b-490">The Major child element is mandatory and the others are optional.</span></span>

<a href="" id="architecture"></a><span data-ttu-id="9464b-491">**アーキテクチャ**アーキテクチャでは、 **Win32**と**Win64**の2つの値を列挙します。</span><span class="sxs-lookup"><span data-stu-id="9464b-491">**Architecture** Architecture enumerates two possible values: **Win32** and **Win64**.</span></span> <span data-ttu-id="9464b-492">これらの値は、プロセスアーキテクチャを指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-492">These values are used to specify process architecture.</span></span>

<a href="" id="process"></a><span data-ttu-id="9464b-493">**プロセス**プロセスデータ型は、UE-V で監視されるプロセスを記述するために使用されるコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="9464b-493">**Process** The Process data type is a container used to describe processes to be monitored by UE-V.</span></span> <span data-ttu-id="9464b-494">これには、**ファイル名**、**アーキテクチャ**、**商品名**、 **filedescription**、 **productversion**、 **FileVersion**という6つの子要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9464b-494">It contains six child elements: **Filename**, **Architecture**, **ProductName**, **FileDescription**, **ProductVersion**, and **FileVersion**.</span></span> <span data-ttu-id="9464b-495">この表では、各要素のデータ型について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="9464b-495">This table details each element’s respective data type:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9464b-496">要素</span><span class="sxs-lookup"><span data-stu-id="9464b-496">Element</span></span></th>
<th align="left"><span data-ttu-id="9464b-497">データ型</span><span class="sxs-lookup"><span data-stu-id="9464b-497">Data Type</span></span></th>
<th align="left"><span data-ttu-id="9464b-498">Mandatory</span><span class="sxs-lookup"><span data-stu-id="9464b-498">Mandatory</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-499">ル</span><span class="sxs-lookup"><span data-stu-id="9464b-499">Filename</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-500">FilenameString</span><span class="sxs-lookup"><span data-stu-id="9464b-500">FilenameString</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-501">True</span><span class="sxs-lookup"><span data-stu-id="9464b-501">True</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-502">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="9464b-502">Architecture</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-503">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="9464b-503">Architecture</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-504">False</span><span class="sxs-lookup"><span data-stu-id="9464b-504">False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-505">ProductName</span><span class="sxs-lookup"><span data-stu-id="9464b-505">ProductName</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-506">String</span><span class="sxs-lookup"><span data-stu-id="9464b-506">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-507">False</span><span class="sxs-lookup"><span data-stu-id="9464b-507">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-508">ファイルの説明</span><span class="sxs-lookup"><span data-stu-id="9464b-508">FileDescription</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-509">String</span><span class="sxs-lookup"><span data-stu-id="9464b-509">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-510">False</span><span class="sxs-lookup"><span data-stu-id="9464b-510">False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-511">ProductVersion</span><span class="sxs-lookup"><span data-stu-id="9464b-511">ProductVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-512">ProcessVersion</span><span class="sxs-lookup"><span data-stu-id="9464b-512">ProcessVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-513">False</span><span class="sxs-lookup"><span data-stu-id="9464b-513">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-514">FileVersion</span><span class="sxs-lookup"><span data-stu-id="9464b-514">FileVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-515">ProcessVersion</span><span class="sxs-lookup"><span data-stu-id="9464b-515">ProcessVersion</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-516">False</span><span class="sxs-lookup"><span data-stu-id="9464b-516">False</span></span></p></td>
</tr>
</tbody>
</table>

 

<a href="" id="processes"></a><span data-ttu-id="9464b-517">**プロセス**プロセスデータ型は、1つ以上のプロセス要素のコレクションのコンテナーを表します。</span><span class="sxs-lookup"><span data-stu-id="9464b-517">**Processes** The Processes data type represents a container for a collection of one or more Process elements.</span></span> <span data-ttu-id="9464b-518">次の2つの子要素がプロセスシーケンスの種類でサポートされています。**プロセス**と**shellprocess**。</span><span class="sxs-lookup"><span data-stu-id="9464b-518">Two child elements are supported in the Processes sequence type: **Process** and **ShellProcess**.</span></span> <span data-ttu-id="9464b-519">プロセスは、Process 型の要素であり、ShellProcess はデータ型が空であることを示します。</span><span class="sxs-lookup"><span data-stu-id="9464b-519">Process is an element of type Process and ShellProcess is of data type Empty.</span></span> <span data-ttu-id="9464b-520">シーケンスで少なくとも1つの項目を識別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-520">At least one item must be identified in the sequence.</span></span>

<a href="" id="path"></a><span data-ttu-id="9464b-521">**Path**Path は、レジストリとファイルのパスを参照するために、RegistrySetting と FileSetting で消費されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-521">**Path** Path is consumed by RegistrySetting and FileSetting to refer to registry and file paths.</span></span> <span data-ttu-id="9464b-522">この要素は、 **Recursive**と**DeleteIfNotFound**の2つのオプション属性をサポートします。</span><span class="sxs-lookup"><span data-stu-id="9464b-522">This element supports two optional attributes: **Recursive** and **DeleteIfNotFound**.</span></span> <span data-ttu-id="9464b-523">どちらの値も default = "False" に設定されています。</span><span class="sxs-lookup"><span data-stu-id="9464b-523">Both values are set to default=”False”.</span></span>

<span data-ttu-id="9464b-524">Recursive は、パスとすべてのサブフォルダーがファイル設定に含まれていること、またはすべての子レジストリキーがレジストリ設定に含まれていることを示します。</span><span class="sxs-lookup"><span data-stu-id="9464b-524">Recursive indicates that the path and all subfolders are included for file settings or that all child registry keys are included for registry settings.</span></span> <span data-ttu-id="9464b-525">どちらの場合も、キャプチャされたデータには、現在のレベルのすべての項目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9464b-525">In both cases, all items at the current level are included in the data captured.</span></span> <span data-ttu-id="9464b-526">FileSettings オブジェクトの場合、指定したフォルダー内のすべてのファイルは、UE-V によってキャプチャされるデータに含まれますが、フォルダーは含まれません。</span><span class="sxs-lookup"><span data-stu-id="9464b-526">For a FileSettings object, all files within the specified folder are included in the data captured by UE-V but folders are not included.</span></span> <span data-ttu-id="9464b-527">レジストリパスの場合、現在のパスにあるすべての値がキャプチャされますが、子レジストリキーはキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="9464b-527">For registry paths, all values in the current path are captured but child registry keys are not captured.</span></span> <span data-ttu-id="9464b-528">どちらの場合も、大量のデータセットまたは多数の項目をキャプチャしないように注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-528">In both cases, care should be taken to avoid capturing large data sets or large numbers of items.</span></span>

<span data-ttu-id="9464b-529">DeleteIfNotFound 属性は、ユーザー設定の記憶域のパスデータから設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="9464b-529">The DeleteIfNotFound attribute removes the setting from the user’s settings storage path data.</span></span> <span data-ttu-id="9464b-530">これは、パッケージからこれらの設定を削除すると、設定の記憶域パスファイルサーバーに大量のディスク領域が保存される可能性がある場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="9464b-530">This may be desirable in cases where removing these settings from the package will save a large amount of disk space on the settings storage path file server.</span></span>

<a href="" id="filemask"></a><span data-ttu-id="9464b-531">**Filemask**FileMask Path で定義されているフォルダーに対して、特定の種類のファイルのみを指定します。</span><span class="sxs-lookup"><span data-stu-id="9464b-531">**FileMask** FileMask specifies only certain file types for the folder that is defined by Path.</span></span> <span data-ttu-id="9464b-532">たとえば、Path `C:\users\username\files` とファイルが含まれている可能性があり `*.txt` ます。テキストファイルのみを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="9464b-532">For example, Path might be `C:\users\username\files` and FileMask could be `*.txt` to include only text files.</span></span>

<a href="" id="registrysetting"></a><span data-ttu-id="9464b-533">**Registrysetting**RegistrySetting は、レジストリキーと値のコンテナーと、UE-V エージェントの一部に関連する目的の動作を表します。</span><span class="sxs-lookup"><span data-stu-id="9464b-533">**RegistrySetting** RegistrySetting represents a container for registry keys and values and the associated desired behavior on the part of the UE-V Agent.</span></span> <span data-ttu-id="9464b-534">4つの子要素は、 **path**、 **Name**、 **Exclude**、および値の**パス**と**名前**のシーケンスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-534">Four child elements are defined within this type: **Path**, **Name**, **Exclude**, and a sequence of the values **Path** and **Name**.</span></span>

<a href="" id="filesetting"></a><span data-ttu-id="9464b-535">**Filesetting**FileSetting には、ファイルとファイルのパスに関連付けられたパラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9464b-535">**FileSetting** FileSetting contains parameters associated with files and files paths.</span></span> <span data-ttu-id="9464b-536">4つの子要素 (**ルート**、 **Path**、 **filemask**、**除外**) が定義されています。</span><span class="sxs-lookup"><span data-stu-id="9464b-536">Four child elements are defined: **Root**, **Path**, **FileMask**, and **Exclude**.</span></span> <span data-ttu-id="9464b-537">Root は必須で、他のオプションは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9464b-537">Root is mandatory and the others are optional.</span></span>

<a href="" id="settings"></a><span data-ttu-id="9464b-538">**設定**設定は、特定のテンプレートに適用されるすべての設定のコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="9464b-538">**Settings** Settings is a container for all the settings that apply to a particular template.</span></span> <span data-ttu-id="9464b-539">これには、前に説明したレジストリ、File、SystemParameter、および CustomAction の各設定のインスタンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9464b-539">It contains instances of the Registry, File, SystemParameter, and CustomAction settings described earlier.</span></span> <span data-ttu-id="9464b-540">さらに、次の子要素も含めることができます。これには、次のような動作があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-540">In addition, it can also contain the following child elements with behaviors described:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9464b-541">要素</span><span class="sxs-lookup"><span data-stu-id="9464b-541">Element</span></span></th>
<th align="left"><span data-ttu-id="9464b-542">説明</span><span class="sxs-lookup"><span data-stu-id="9464b-542">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-543">非同期</span><span class="sxs-lookup"><span data-stu-id="9464b-543">Asynchronous</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-544">非同期設定パッケージは、アプリケーションの起動をブロックせずに適用されるため、設定が適用されている間、アプリケーションは実行を開始できます。</span><span class="sxs-lookup"><span data-stu-id="9464b-544">Asynchronous settings packages are applied without blocking the application startup so that the application start proceeds while the settings are still being applied.</span></span> <span data-ttu-id="9464b-545">これは、SystemParameterSetting など、API を通じて非同期的に適用できる設定に役立ち <code>get/set</code> ます。</span><span class="sxs-lookup"><span data-stu-id="9464b-545">This is useful for settings that can be applied asynchronously, such as those <code>get/set</code> through an API, like SystemParameterSetting.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-546">PreventOverlappingSynchronization</span><span class="sxs-lookup"><span data-stu-id="9464b-546">PreventOverlappingSynchronization</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-547">既定では、UE-V は、テンプレートを使用するアプリケーションの最後のインスタンスが閉じられている場合にのみ、アプリケーションの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="9464b-547">By default, UE-V only saves settings for an application when the last instance of an application using the template is closed.</span></span> <span data-ttu-id="9464b-548">この要素が "false" に設定されている場合、アプリケーションの他のインスタンスが実行されている場合でも、UE-V は設定をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="9464b-548">When this element is set to ‘false’, UE-V exports the settings even if other instances of an application are running.</span></span> <span data-ttu-id="9464b-549">適したテンプレート– UE-V に同梱されている共通要素セクションが含まれている場合は、このフラグを使って共有設定をアプリケーションの終了時に常にエクスポートし、最後のインスタンスが閉じられるまでは、アプリケーション固有の設定がエクスポートされないようにします。</span><span class="sxs-lookup"><span data-stu-id="9464b-549">Suited templates – those that include a Common element section– that are shipped with UE-V use this flag to enable shared settings to always export on application close, while preventing application-specific settings from exporting until the last instance is closed.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="name"></a><span data-ttu-id="9464b-550">Name 要素</span><span class="sxs-lookup"><span data-stu-id="9464b-550">Name Element</span></span>

**<span data-ttu-id="9464b-551">必須: True</span><span class="sxs-lookup"><span data-stu-id="9464b-551">Mandatory: True</span></span>**

**<span data-ttu-id="9464b-552">種類: 文字列</span><span class="sxs-lookup"><span data-stu-id="9464b-552">Type: String</span></span>**

<span data-ttu-id="9464b-553">[名前] 設定場所テンプレートの一意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9464b-553">Name specifies a unique name for the settings location template.</span></span> <span data-ttu-id="9464b-554">これは、WMI、PowerShell、イベントビューアー、デバッグログでテンプレートを参照するときに表示するために使われます。</span><span class="sxs-lookup"><span data-stu-id="9464b-554">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="9464b-555">一般的に、バージョン情報を参照することは避けてください。これは、ProductVersion 要素から objected することができます。</span><span class="sxs-lookup"><span data-stu-id="9464b-555">In general, avoid referencing version information, as this can be objected from the ProductVersion element.</span></span> <span data-ttu-id="9464b-556">たとえば、ではなく、を指定し `<Name>My Application</Name>` `<Name>My Application 1.1</Name>` ます。</span><span class="sxs-lookup"><span data-stu-id="9464b-556">For example, specify `<Name>My Application</Name>` rather than `<Name>My Application 1.1</Name>`.</span></span>

<span data-ttu-id="9464b-557">**注** UE-V は外部の Dtd を参照しないため、設定場所テンプレートで名前付きエンティティを使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="9464b-557">**Note** UE-V does not reference external DTDs, so it is not possible to use named entities in a settings location template.</span></span> <span data-ttu-id="9464b-558">たとえば、登録されて &reg; いる商標記号®の参照には使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="9464b-558">For example, do not use &reg; to refer to the registered trade mark sign ®.</span></span> <span data-ttu-id="9464b-559">代わりに、このような種類の特殊文字 (®文字の & \ #174 など) を含める場合は、標準の番号付き参照を使います。</span><span class="sxs-lookup"><span data-stu-id="9464b-559">Instead, use canonical numbered references to include these types of special characters, for example, &\#174 for the ® character.</span></span> <span data-ttu-id="9464b-560">この規則は、このドキュメント内のすべての文字列値に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-560">This rule applies to all string values in this document.</span></span>

<span data-ttu-id="9464b-561"><http://www.w3.org/TR/xhtml1/dtds.html>文字エンティティの完全な一覧については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9464b-561">See <http://www.w3.org/TR/xhtml1/dtds.html> for a complete list of character entities.</span></span> <span data-ttu-id="9464b-562">UTF-8 でエンコードされたドキュメントには、Unicode 文字が直接含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-562">UTF-8-encoded documents may include the Unicode characters directly.</span></span> <span data-ttu-id="9464b-563">UE-V Generator を使用してテンプレートを保存すると、文字エンティティが自動的に Unicode 表現に変換されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-563">Saving templates through the UE-V Generator converts character entities to their Unicode representations automatically.</span></span>

 

### <a href="" id="id"></a><span data-ttu-id="9464b-564">ID 要素</span><span class="sxs-lookup"><span data-stu-id="9464b-564">ID Element</span></span>

**<span data-ttu-id="9464b-565">必須: True</span><span class="sxs-lookup"><span data-stu-id="9464b-565">Mandatory: True</span></span>**

**<span data-ttu-id="9464b-566">種類: 文字列</span><span class="sxs-lookup"><span data-stu-id="9464b-566">Type: String</span></span>**

<span data-ttu-id="9464b-567">ID は、特定のテンプレートの一意の識別子を入力します。</span><span class="sxs-lookup"><span data-stu-id="9464b-567">ID populates a unique identifier for a particular template.</span></span> <span data-ttu-id="9464b-568">このタグは、UE-V Agent が実行時にテンプレートを参照するために使用するプライマリ識別子になります (たとえば、Get-UevTemplate と Get-UevTemplateProgram PowerShell コマンドレットの出力を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="9464b-568">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime (for example, see the output of the Get-UevTemplate and Get-UevTemplateProgram PowerShell cmdlets).</span></span> <span data-ttu-id="9464b-569">慣例により、このタグにはスペースを含めないでください。これによってスクリプトが簡素化されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-569">By convention, this tag should not contain any spaces, which simplifies scripting.</span></span> <span data-ttu-id="9464b-570">この要素には、やなどのテンプレートを簡単に識別できるように、アプリのバージョン番号を指定する必要があり `<ID>MicrosoftCalculator6</ID>` `<ID>MicrosoftOffice2010Win64</ID>` ます。</span><span class="sxs-lookup"><span data-stu-id="9464b-570">Version numbers of applications should be specified in this element to allow for easy identification of the template, such as `<ID>MicrosoftCalculator6</ID>` or `<ID>MicrosoftOffice2010Win64</ID>`.</span></span>

### <a href="" id="version"></a><span data-ttu-id="9464b-571">Version 要素</span><span class="sxs-lookup"><span data-stu-id="9464b-571">Version Element</span></span>

**<span data-ttu-id="9464b-572">必須: True</span><span class="sxs-lookup"><span data-stu-id="9464b-572">Mandatory: True</span></span>**

**<span data-ttu-id="9464b-573">種類: Integer</span><span class="sxs-lookup"><span data-stu-id="9464b-573">Type: Integer</span></span>**

**<span data-ttu-id="9464b-574">最小値: 0</span><span class="sxs-lookup"><span data-stu-id="9464b-574">Minimum Value: 0</span></span>**

**<span data-ttu-id="9464b-575">最大値: 2147483647</span><span class="sxs-lookup"><span data-stu-id="9464b-575">Maximum Value: 2147483647</span></span>**

<span data-ttu-id="9464b-576">[バージョン] は、変更の管理追跡用の設定場所テンプレートのバージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="9464b-576">Version identifies the version of the settings location template for administrative tracking of changes.</span></span> <span data-ttu-id="9464b-577">UE-V Generator は、テンプレートが保存されるたびに、この数値を1つずつ自動的にインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="9464b-577">The UE-V Generator automatically increments this number by one each time the template is saved.</span></span> <span data-ttu-id="9464b-578">このフィールドは整数である必要があることに注意してください。小数点以下の値 `<Version>2.5</Version>` は使用できません。</span><span class="sxs-lookup"><span data-stu-id="9464b-578">Notice that this field must be a whole number integer; fractional values, such as `<Version>2.5</Version>` are not allowed.</span></span>

<span data-ttu-id="9464b-579">**ヒント:** XML コメントタグを使用して、バージョンの変更に関するメモを保存でき `<!-- -->` ます。たとえば、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9464b-579">**Hint:** You can save notes about version changes using XML comment tags `<!-- -->`, for example:</span></span>

```xml
<!--
    Version History

    Version 1 Jul 05, 2012 Initial template created by Generator - Denise@Contoso.com
    Version 2 Jul 31, 2012 Added support for app.exe v2.1.3 - Mark@Contoso.com
    Version 3 Jan 01, 2013 Added font settings support - Mark@Contoso.com
    Version 4 Jan 31, 2013 Added support for plugin settings - Tony@Contoso.com
  -->
<Version>4</Version>
```

<span data-ttu-id="9464b-580">**重要** この値は、次のような場合に、既存のテンプレートに新しいバージョンのテンプレートを適用する必要があるかどうかを確認するために照会されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-580">**Important** This value is queried to determine if a new version of a template should be applied to an existing template in these instances:</span></span>

-   <span data-ttu-id="9464b-581">スケジュールされたテンプレートの自動更新タスクの実行時</span><span class="sxs-lookup"><span data-stu-id="9464b-581">When the scheduled Template Auto Update task executes</span></span>

-   <span data-ttu-id="9464b-582">更新プログラム UevTemplate PowerShell コマンドレットが実行されるとき</span><span class="sxs-lookup"><span data-stu-id="9464b-582">When the Update-UevTemplate PowerShell cmdlet is executed</span></span>

-   <span data-ttu-id="9464b-583">WMI 経由で microsoft\\uev: SettingsLocationTemplate Update メソッドが呼び出された場合</span><span class="sxs-lookup"><span data-stu-id="9464b-583">When the microsoft\\uev:SettingsLocationTemplate Update method is called through WMI</span></span>

 

### <a href="" id="author"></a><span data-ttu-id="9464b-584">作成要素</span><span class="sxs-lookup"><span data-stu-id="9464b-584">Author Element</span></span>

**<span data-ttu-id="9464b-585">必須: False</span><span class="sxs-lookup"><span data-stu-id="9464b-585">Mandatory: False</span></span>**

**<span data-ttu-id="9464b-586">種類: 文字列</span><span class="sxs-lookup"><span data-stu-id="9464b-586">Type: String</span></span>**

<span data-ttu-id="9464b-587">[作成者] は、設定場所テンプレートの作成者を指定します。</span><span class="sxs-lookup"><span data-stu-id="9464b-587">Author identifies the creator of the settings location template.</span></span> <span data-ttu-id="9464b-588">2つのオプションの子要素がサポートされています。**名前**と**メール**</span><span class="sxs-lookup"><span data-stu-id="9464b-588">Two optional child elements are supported: **Name** and **Email**.</span></span> <span data-ttu-id="9464b-589">どちらの属性も省略可能ですが、メールの子要素が指定されている場合は、Name 要素と共に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-589">Both attributes are optional, but, if the Email child element is specified, it must be accompanied by the Name element.</span></span> <span data-ttu-id="9464b-590">[Author] は、設定場所テンプレートの連絡先の完全な名前を示し、メールは作成者のメールアドレスを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-590">Author refers to the full name of the contact for the settings location template, and email should refer to an email address for the author.</span></span> <span data-ttu-id="9464b-591">この情報は、一般に公開されるテンプレート ( [Ue-v テンプレートギャラリー](https://gallery.technet.microsoft.com/site/search?f%5B0%5D.Type=RootCategory&f%5B0%5D.Value=UE-V)など) に含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9464b-591">We recommend that you include this information in templates published publicly, for example, on the [UE-V Template Gallery](https://gallery.technet.microsoft.com/site/search?f%5B0%5D.Type=RootCategory&f%5B0%5D.Value=UE-V).</span></span>

### <a href="" id="processes"></a><span data-ttu-id="9464b-592">プロセスとプロセス要素</span><span class="sxs-lookup"><span data-stu-id="9464b-592">Processes and Process Element</span></span>

**<span data-ttu-id="9464b-593">必須: True</span><span class="sxs-lookup"><span data-stu-id="9464b-593">Mandatory: True</span></span>**

**<span data-ttu-id="9464b-594">Type: Element</span><span class="sxs-lookup"><span data-stu-id="9464b-594">Type: Element</span></span>**

<span data-ttu-id="9464b-595">プロセスには、少なくとも1つの要素が含まれます。これには、 `<Process>` **ファイル名**、**アーキテクチャ**、**商品名**、 **filedescription**、 **productversion**、 **FileVersion**という子要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9464b-595">Processes contains at least one `<Process>` element, which in turn contains the following child elements: **Filename**, **Architecture**, **ProductName**, **FileDescription**, **ProductVersion**, and **FileVersion**.</span></span> <span data-ttu-id="9464b-596">ファイル名の子要素は必須であり、他の項目は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="9464b-596">The Filename child element is mandatory and the others are optional.</span></span> <span data-ttu-id="9464b-597">完全に入力された要素には、次の例のようなタグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9464b-597">A fully populated element contains tags similar to this example:</span></span>

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <Architecture>Win64</Architecture>
  <ProductName> MyApplication </ProductName>
  <FileDescription>MyApplication.exe</FileDescription>
  <ProductVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </FileVersion>
</Process>
```

### <span data-ttu-id="9464b-598">ル</span><span class="sxs-lookup"><span data-stu-id="9464b-598">Filename</span></span>

**<span data-ttu-id="9464b-599">必須: True</span><span class="sxs-lookup"><span data-stu-id="9464b-599">Mandatory: True</span></span>**

**<span data-ttu-id="9464b-600">種類: 文字列</span><span class="sxs-lookup"><span data-stu-id="9464b-600">Type: String</span></span>**

<span data-ttu-id="9464b-601">Filename は、ファイルシステムに表示される実行可能ファイルの実際のファイル名を指します。</span><span class="sxs-lookup"><span data-stu-id="9464b-601">Filename refers to the actual file name of the executable as it appears in the file system.</span></span> <span data-ttu-id="9464b-602">この要素は、テンプレートがプロセスに適用されるかどうかを評価するために UE-V が使う主要な条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="9464b-602">This element specifies the primary criterion that UE-V uses to evaluate whether a template applies to a process or not.</span></span> <span data-ttu-id="9464b-603">この要素は、設定場所テンプレート XML で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-603">This element must be specified in the settings location template XML.</span></span>

<span data-ttu-id="9464b-604">有効なファイル名は、正規表現 \ [^] \ \ \ \ \ \ \ \* \ \ | \ \ \ \* \ \ | &lt; &gt;/: \] +、つまり、バックスラッシュ文字、アスタリスクまたは疑問符のワイルドカード文字、パイプ文字、不等号、スラッシュ、またはコロン (\ \?) が含まれていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-604">Valid filenames must not match the regular expression \[^\\\\\\?\\\*\\|&lt;&gt;/:\]+, that is, they may not contain backslash characters, asterisk or question mark wild-card characters, the pipe character, the greater than or less than sign, forward slash, or colon (the \\ ?</span></span> <span data-ttu-id="9464b-605">\* |&lt; &gt; /または: 文字)。</span><span class="sxs-lookup"><span data-stu-id="9464b-605">\* | &lt; &gt; / or : characters.).</span></span>

<span data-ttu-id="9464b-606">**ヒント:** この regex に対して文字列をテストするには、PowerShell コマンドウィンドウを使って、実行可能ファイルの名前を**ファイル**名に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="9464b-606">**Hint:** To test a string against this regex, use a PowerShell command window and substitute your executable’s name for **YourFileName**:</span></span>

`"YourFileName.exe" -match  "[\\\?\*\|<>/:]+"`

<span data-ttu-id="9464b-607">値が**True**の場合は、文字列に不正な文字が含まれていることを示します。</span><span class="sxs-lookup"><span data-stu-id="9464b-607">A value of **True** indicates that the string contains illegal characters.</span></span> <span data-ttu-id="9464b-608">次に、不正な値の例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="9464b-608">Here are some examples of illegal values:</span></span>

-   <span data-ttu-id="9464b-609">\\\\server\\share\\program.exe</span><span class="sxs-lookup"><span data-stu-id="9464b-609">\\\\server\\share\\program.exe</span></span>

-   <span data-ttu-id="9464b-610">プログラム \ \* .exe</span><span class="sxs-lookup"><span data-stu-id="9464b-610">Program\*.exe</span></span>

-   <span data-ttu-id="9464b-611">Pro? ram.exe</span><span class="sxs-lookup"><span data-stu-id="9464b-611">Pro?ram.exe</span></span>

-   <span data-ttu-id="9464b-612">プログラム &lt; 1 &gt; . .exe</span><span class="sxs-lookup"><span data-stu-id="9464b-612">Program&lt;1&gt;.exe</span></span>

<span data-ttu-id="9464b-613">**注** UE-V Generator は、指定された文字より大きい文字と小さい文字をそれぞれエンコードし &gt; &lt; ます。</span><span class="sxs-lookup"><span data-stu-id="9464b-613">**Note** The UE-V Generator encodes the greater than and less than characters as &gt; and &lt; respectively.</span></span>

 

<span data-ttu-id="9464b-614">まれに、ファイル名の値に .exe 拡張子が含まれているとは限りませんが、値の一部として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-614">In rare circumstances, the FileName value will not necessarily include the .exe extension, but it should be specified as part of the value.</span></span> <span data-ttu-id="9464b-615">たとえば、 `<Filename>MyApplictication.exe</Filename>` の代わりにを指定する必要があり `<Filename>MyApplictication</Filename>` ます。</span><span class="sxs-lookup"><span data-stu-id="9464b-615">For example, `<Filename>MyApplictication.exe</Filename>` should be specified instead of `<Filename>MyApplictication</Filename>`.</span></span> <span data-ttu-id="9464b-616">実行可能ファイルの実際の名前が "MyApplication.exe" の場合、2番目の例では、テンプレートはプロセスに適用されません。</span><span class="sxs-lookup"><span data-stu-id="9464b-616">The second example will not apply the template to the process if the actual name of the executable file is “MyApplication.exe”.</span></span>

### <span data-ttu-id="9464b-617">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="9464b-617">Architecture</span></span>

**<span data-ttu-id="9464b-618">必須: False</span><span class="sxs-lookup"><span data-stu-id="9464b-618">Mandatory: False</span></span>**

**<span data-ttu-id="9464b-619">Type: Architecture (文字列)</span><span class="sxs-lookup"><span data-stu-id="9464b-619">Type: Architecture (String)</span></span>**

<span data-ttu-id="9464b-620">アーキテクチャとは、ターゲットの実行可能ファイルがコンパイルされたプロセッサアーキテクチャを指します。</span><span class="sxs-lookup"><span data-stu-id="9464b-620">Architecture refers to the processor architecture for which the target executable was compiled.</span></span> <span data-ttu-id="9464b-621">有効な値は、32ビットアプリケーションまたは64ビットアプリケーション用の Win64 の Win32 です。</span><span class="sxs-lookup"><span data-stu-id="9464b-621">Valid values are Win32 for 32-bit applications or Win64 for 64-bit applications.</span></span> <span data-ttu-id="9464b-622">存在する場合、このタグは、設定場所テンプレートを特定のアプリケーションアーキテクチャに適用することを制限します。</span><span class="sxs-lookup"><span data-stu-id="9464b-622">If present, this tag limits the applicability of the settings location template to a particular application architecture.</span></span> <span data-ttu-id="9464b-623">この例については、UE-V に含まれる% programfiles% ¥ Microsoft User Experience Virtualization\\templates\\ MicrosoftOffice2010Win32.xml と MicrosoftOffice2010Win64.xml ファイルを比較します。</span><span class="sxs-lookup"><span data-stu-id="9464b-623">For an example of this, compare the %ProgramFiles%\\Microsoft User Experience Virtualization\\templates\\ MicrosoftOffice2010Win32.xml and MicrosoftOffice2010Win64.xml files included with UE-V.</span></span> <span data-ttu-id="9464b-624">これは、異なるバージョンの実行可能ファイル間で相対パスが変更された場合、またはプロセッサアーキテクチャを切り替えるときに設定が追加または削除された場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9464b-624">This is useful when relative paths change between different versions of an executable or if settings have been added or removed when moving from one processor architecture to another.</span></span>

<span data-ttu-id="9464b-625">この要素が存在しない場合、設定場所テンプレートはプロセスのアーキテクチャを無視し、ファイル名とその他の属性が適用されている場合、32と64ビットの両方のプロセスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-625">If this element is absent, the settings location template ignores the process’ architecture and applies to both 32 and 64-bit processes if the file name and other attributes apply.</span></span>

<span data-ttu-id="9464b-626">**注** UE-V は、このバージョンの ARM プロセッサをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9464b-626">**Note** UE-V does not support ARM processors in this version.</span></span>

 

### <span data-ttu-id="9464b-627">ProductName</span><span class="sxs-lookup"><span data-stu-id="9464b-627">ProductName</span></span>

**<span data-ttu-id="9464b-628">必須: False</span><span class="sxs-lookup"><span data-stu-id="9464b-628">Mandatory: False</span></span>**

**<span data-ttu-id="9464b-629">種類: 文字列</span><span class="sxs-lookup"><span data-stu-id="9464b-629">Type: String</span></span>**

<span data-ttu-id="9464b-630">ProductName は、管理目的またはレポート用に製品を識別するために使用されるオプションの要素です。</span><span class="sxs-lookup"><span data-stu-id="9464b-630">ProductName is an optional element used to identify a product for administrative purposes or reporting.</span></span> <span data-ttu-id="9464b-631">ProductName はファイル名とは異なり、その値に対する正規表現の制限はありません。</span><span class="sxs-lookup"><span data-stu-id="9464b-631">ProductName differs from Filename in that there are no regular expression restrictions on its value.</span></span> <span data-ttu-id="9464b-632">これにより、実行可能ファイル名が明確でない可能性のあるプロセスの説明をより簡単に理解できます。</span><span class="sxs-lookup"><span data-stu-id="9464b-632">This allows for more easily understood descriptions of a process where the executable name may not be obvious.</span></span> <span data-ttu-id="9464b-633">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9464b-633">For example:</span></span>

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <ProductName>My Application 6.x by Contoso.com</ProductName>
  <ProductVersion>
    <Major Minimum="6" Maximum="6" />
  </ProductVersion>
</Process>
```

### <span data-ttu-id="9464b-634">ファイルの説明</span><span class="sxs-lookup"><span data-stu-id="9464b-634">FileDescription</span></span>

**<span data-ttu-id="9464b-635">必須: False</span><span class="sxs-lookup"><span data-stu-id="9464b-635">Mandatory: False</span></span>**

**<span data-ttu-id="9464b-636">種類: 文字列</span><span class="sxs-lookup"><span data-stu-id="9464b-636">Type: String</span></span>**

<span data-ttu-id="9464b-637">FileDescription は、実行可能ファイルの管理の説明を可能にするオプションのタグです。</span><span class="sxs-lookup"><span data-stu-id="9464b-637">FileDescription is an optional tag that allows for an administrative description of the executable file.</span></span> <span data-ttu-id="9464b-638">これは無料のテキストフィールドであり、実行可能ファイルの機能を識別する必要があるソフトウェアパッケージ内の複数の実行可能ファイルを区別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9464b-638">This is a free text field and can be useful in distinguishing multiple executables within a software package where there is a need to identify the function of the executable.</span></span>

<span data-ttu-id="9464b-639">たとえば、次に示すように、適したアプリケーションでは、2つの実行可能ファイル (MyApplication.exe と MyApplicationHelper.exe) の機能についての通知を表示すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-639">For example, in a suited application, it might be useful to provide reminders about the function of two executables (MyApplication.exe and MyApplicationHelper.exe), as shown here:</span></span>

```xml
<Processes>
  <Process>
    <Filename>MyApplication.exe</Filename>
    <FileDescription>My Application Main Engine</ FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
  <Process>
    <Filename>MyApplicationHelper.exe</Filename>
    <FileDescription>My Application Background Process Executable</FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
</Processes>
```

### <span data-ttu-id="9464b-640">ProductVersion</span><span class="sxs-lookup"><span data-stu-id="9464b-640">ProductVersion</span></span>

**<span data-ttu-id="9464b-641">必須: False</span><span class="sxs-lookup"><span data-stu-id="9464b-641">Mandatory: False</span></span>**

**<span data-ttu-id="9464b-642">種類: 文字列</span><span class="sxs-lookup"><span data-stu-id="9464b-642">Type: String</span></span>**

<span data-ttu-id="9464b-643">ProductVersion は、ファイルのメジャーバージョンとマイナー製品バージョン、およびビルドとパッチレベルを指します。</span><span class="sxs-lookup"><span data-stu-id="9464b-643">ProductVersion refers to the major and minor product versions of a file, as well as a build and patch level.</span></span> <span data-ttu-id="9464b-644">ProductVersion は省略可能な要素ですが、指定する場合は、少なくとも主要な子要素が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-644">ProductVersion is an optional element, but if specified, it must contain at least the Major child element.</span></span> <span data-ttu-id="9464b-645">この値は、最小値の "X" 最大値 = "Y" (X と Y は整数) の範囲を表す必要があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-645">The value must express a range in the form Minimum="X" Maximum="Y" where X and Y are integers.</span></span> <span data-ttu-id="9464b-646">最小値と最大値は同じにすることができます。</span><span class="sxs-lookup"><span data-stu-id="9464b-646">The Minimum and Maximum values can be identical.</span></span>

<span data-ttu-id="9464b-647">製品とファイルのバージョンの要素が指定されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-647">The product and file version elements may be left unspecified.</span></span> <span data-ttu-id="9464b-648">これにより、テンプレートは "バージョンに依存しない" という意味になります。つまり、指定した実行可能ファイルのすべてのバージョンにテンプレートが適用されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-648">Doing so makes the template “version agnostic”, meaning that the template will apply to all versions of the specified executable.</span></span>

**<span data-ttu-id="9464b-649">例 1:</span><span class="sxs-lookup"><span data-stu-id="9464b-649">Example 1:</span></span>**

<span data-ttu-id="9464b-650">製品バージョン: 1.0 は、UE-V Generator で指定されている次の XML を生成します。</span><span class="sxs-lookup"><span data-stu-id="9464b-650">Product version: 1.0 specified in the UE-V Generator produces the following XML:</span></span>

```xml
<ProductVersion>
  <Major Minimum="1" Maximum="1" />
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

**<span data-ttu-id="9464b-651">例 2:</span><span class="sxs-lookup"><span data-stu-id="9464b-651">Example 2:</span></span>**

<span data-ttu-id="9464b-652">ファイルバージョン: UE-V Generator で指定された5.0.2.1000 は、次の XML を生成します。</span><span class="sxs-lookup"><span data-stu-id="9464b-652">File version: 5.0.2.1000 specified in the UE-V Generator produces the following XML:</span></span>

```xml
<FileVersion>
  <Major Minimum="5" Maximum="5" />
  <Minor Minimum="0" Maximum="0" />
  <Build Minimum="2" Maximum="2" />
  <Patch Minimum="1000" Maximum="1000" />
</FileVersion>
```

**<span data-ttu-id="9464b-653">間違った例1–不完全な範囲:</span><span class="sxs-lookup"><span data-stu-id="9464b-653">Incorrect Example 1 – incomplete range:</span></span>**

<span data-ttu-id="9464b-654">最小属性のみが存在します。</span><span class="sxs-lookup"><span data-stu-id="9464b-654">Only the Minimum attribute is present.</span></span> <span data-ttu-id="9464b-655">範囲には最大値も含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-655">Maximum must be included in a range as well.</span></span>

```xml
<ProductVersion>
  <Major Minimum="2" />
</ProductVersion>
```

**<span data-ttu-id="9464b-656">間違った例2–主要要素のない Minor:</span><span class="sxs-lookup"><span data-stu-id="9464b-656">Incorrect Example 2 – Minor specified without Major element:</span></span>**

<span data-ttu-id="9464b-657">Minor 要素のみが存在します。</span><span class="sxs-lookup"><span data-stu-id="9464b-657">Only the Minor element is present.</span></span> <span data-ttu-id="9464b-658">メジャーも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9464b-658">Major must be included as well.</span></span>

```xml
<ProductVersion>
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

### <span data-ttu-id="9464b-659">FileVersion</span><span class="sxs-lookup"><span data-stu-id="9464b-659">FileVersion</span></span>

**<span data-ttu-id="9464b-660">必須: False</span><span class="sxs-lookup"><span data-stu-id="9464b-660">Mandatory: False</span></span>**

**<span data-ttu-id="9464b-661">種類: 文字列</span><span class="sxs-lookup"><span data-stu-id="9464b-661">Type: String</span></span>**

<span data-ttu-id="9464b-662">FileVersion は、公開されたアプリケーションのリリースバージョンと、コンポーネント実行可能ファイルの内部ビルドの詳細を区別します。</span><span class="sxs-lookup"><span data-stu-id="9464b-662">FileVersion differentiates between the release version of a published application and the internal build details of a component executable.</span></span> <span data-ttu-id="9464b-663">ほとんどの商用アプリケーションでは、これらの番号は同じです。</span><span class="sxs-lookup"><span data-stu-id="9464b-663">For the majority of commercial applications, these numbers are identical.</span></span> <span data-ttu-id="9464b-664">実際には、ファイルの製品バージョンはファイルの一般的なバージョン id を示していますが、ファイルバージョンはファイルの特定のビルドを示します (修正プログラムや更新プログラムの場合など)。</span><span class="sxs-lookup"><span data-stu-id="9464b-664">Where they vary, the product version of a file indicates a generic version identification of a file, while file version indicates a specific build of a file (as in the case of a hotfix or update).</span></span> <span data-ttu-id="9464b-665">これにより、検出ロジックを壊すことなくファイルを一意に識別できます。</span><span class="sxs-lookup"><span data-stu-id="9464b-665">This uniquely identifies files without breaking detection logic.</span></span>

<span data-ttu-id="9464b-666">特定の実行可能ファイルの製品バージョンとファイルバージョンを確認するには、Windows エクスプローラーでファイルを右クリックし、[プロパティ] を選択して、[詳細] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9464b-666">To determine the product version and file version of a particular executable, right-click on the file in Windows Explorer, select Properties, then click on the Details tab.</span></span>

<span data-ttu-id="9464b-667">アプリケーションの FileVersion 要素を含めることで、細かい微調整による検出ロジックを行うことができますが、ほとんどのアプリケーションには必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9464b-667">Including a FileVersion element for an application allows for more granular fine-tuning detection logic, but is not necessary for most applications.</span></span> <span data-ttu-id="9464b-668">ProductVersion 要素の設定が最初にチェックされ、次に FileVersion がチェックされます。</span><span class="sxs-lookup"><span data-stu-id="9464b-668">The ProductVersion element settings are checked first, and then FileVersion is checked.</span></span> <span data-ttu-id="9464b-669">より限定的な設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="9464b-669">The more restrictive setting will apply.</span></span>

<span data-ttu-id="9464b-670">FileVersion の子要素と構文規則は、ProductVersion バージョンと同じです。</span><span class="sxs-lookup"><span data-stu-id="9464b-670">The child elements and syntax rules for FileVersion are identical to those of ProductVersion.</span></span>

```xml
<Process>
  <Filename>MSACCESS.EXE</Filename>
  <Architecture>Win32</Architecture>
  <ProductVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </FileVersion>
</Process>
```

### <a href="" id="application"></a><span data-ttu-id="9464b-671">Application 要素</span><span class="sxs-lookup"><span data-stu-id="9464b-671">Application Element</span></span>

<span data-ttu-id="9464b-672">アプリケーションは、特定のアプリケーションに適用される設定のコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="9464b-672">Application is a container for settings that apply to a particular application.</span></span> <span data-ttu-id="9464b-673">これは、次のフィールド/型のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="9464b-673">It is a collection of the following fields/types.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9464b-674">フィールド/型</span><span class="sxs-lookup"><span data-stu-id="9464b-674">Field/Type</span></span></th>
<th align="left"><span data-ttu-id="9464b-675">説明</span><span class="sxs-lookup"><span data-stu-id="9464b-675">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-676">Name (名前)</span><span class="sxs-lookup"><span data-stu-id="9464b-676">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-677">設定場所テンプレートの一意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9464b-677">Specifies a unique name for the settings location template.</span></span> <span data-ttu-id="9464b-678">これは、WMI、PowerShell、イベントビューアー、デバッグログでテンプレートを参照するときに表示するために使われます。</span><span class="sxs-lookup"><span data-stu-id="9464b-678">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="9464b-679">詳細については、「名前」を参照してください <a href="#name" data-raw-source="[Name](#name)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="9464b-679">For more information, see <a href="#name" data-raw-source="[Name](#name)">Name</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-680">ID</span><span class="sxs-lookup"><span data-stu-id="9464b-680">ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-681">特定のテンプレートの一意の識別子を設定します。</span><span class="sxs-lookup"><span data-stu-id="9464b-681">Populates a unique identifier for a particular template.</span></span> <span data-ttu-id="9464b-682">このタグは、UE-V Agent が実行時にテンプレートを参照するために使用するプライマリ識別子になります。</span><span class="sxs-lookup"><span data-stu-id="9464b-682">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime.</span></span> <span data-ttu-id="9464b-683">詳細については、「ID」を参照してください <a href="#id" data-raw-source="[ID](#id)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="9464b-683">For more information, see <a href="#id" data-raw-source="[ID](#id)">ID</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-684">説明</span><span class="sxs-lookup"><span data-stu-id="9464b-684">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-685">テンプレートの説明 (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="9464b-685">An optional description of the template.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-686">LocalizedNames</span><span class="sxs-lookup"><span data-stu-id="9464b-686">LocalizedNames</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-687">UI に表示されるオプションの名前。言語ロケールによってローカライズされます。</span><span class="sxs-lookup"><span data-stu-id="9464b-687">An optional name displayed in the UI, localized by a language locale.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-688">LocalizedDescriptions</span><span class="sxs-lookup"><span data-stu-id="9464b-688">LocalizedDescriptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-689">言語ロケールによってローカライズされた省略可能なテンプレートの説明です。</span><span class="sxs-lookup"><span data-stu-id="9464b-689">An optional template description localized by a language locale.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-690">バージョン</span><span class="sxs-lookup"><span data-stu-id="9464b-690">Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-691">変更の管理追跡用の設定場所テンプレートのバージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="9464b-691">Identifies the version of the settings location template for administrative tracking of changes.</span></span> <span data-ttu-id="9464b-692">詳細については、「バージョン」を参照してください <a href="#version" data-raw-source="[Version](#version)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="9464b-692">For more information, see <a href="#version" data-raw-source="[Version](#version)">Version</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-693">DeferToMSAccount</span><span class="sxs-lookup"><span data-stu-id="9464b-693">DeferToMSAccount</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-694">このテンプレートが Microsoft アカウントと組み合わせて有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="9464b-694">Controls whether this template is enabled in conjunction with a Microsoft account or not.</span></span> <span data-ttu-id="9464b-695">コンピューター上のユーザーに対して MSA の同期が有効になっている場合、このテンプレートは自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="9464b-695">If MSA syncing is enabled for a user on a machine, then this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-696">DeferToOffice365</span><span class="sxs-lookup"><span data-stu-id="9464b-696">DeferToOffice365</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-697">MSA の場合と同様に、このテンプレートを Office365 と組み合わせて有効にするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="9464b-697">Similar to MSA, this controls whether this template is enabled in conjunction with Office365.</span></span> <span data-ttu-id="9464b-698">設定の同期に Office 365 が使用されている場合、このテンプレートは自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="9464b-698">If Office 365 is being used to sync settings, this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-699">プロセス</span><span class="sxs-lookup"><span data-stu-id="9464b-699">Processes</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-700">1つ以上のプロセス要素のコレクションのコンテナー。</span><span class="sxs-lookup"><span data-stu-id="9464b-700">A container for a collection of one or more Process elements.</span></span> <span data-ttu-id="9464b-701">詳細については、「プロセス」を参照してください <a href="#processes" data-raw-source="[Processes](#processes)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="9464b-701">For more information, see <a href="#processes" data-raw-source="[Processes](#processes)">Processes</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-702">設定</span><span class="sxs-lookup"><span data-stu-id="9464b-702">Settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-703">特定のテンプレートに適用されるすべての設定のコンテナー。</span><span class="sxs-lookup"><span data-stu-id="9464b-703">A container for all the settings that apply to a particular template.</span></span> <span data-ttu-id="9464b-704">これには、Registry、File、SystemParameter、および CustomAction の各設定のインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9464b-704">It contains instances of the Registry, File, SystemParameter, and CustomAction settings.</span></span> <span data-ttu-id="9464b-705">詳細については、「 <strong> </strong> データ型の設定」を参照してください <a href="#data" data-raw-source="[Data types](#data)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="9464b-705">For more information, see <strong>Settings</strong> in <a href="#data" data-raw-source="[Data types](#data)">Data types</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="common"></a><span data-ttu-id="9464b-706">共通要素</span><span class="sxs-lookup"><span data-stu-id="9464b-706">Common Element</span></span>

<span data-ttu-id="9464b-707">Common は Application 要素と似ていますが、常に、2つ以上のアプリケーション要素に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="9464b-707">Common is similar to an Application element, but it is always associated with two or more Application elements.</span></span> <span data-ttu-id="9464b-708">共通セクションは、これらのアプリケーションインスタンス間で共有される一連の設定を表します。</span><span class="sxs-lookup"><span data-stu-id="9464b-708">The Common section represents the set of settings that are shared between those Application instances.</span></span> <span data-ttu-id="9464b-709">これは、次のフィールド/型のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="9464b-709">It is a collection of the following fields/types.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9464b-710">フィールド/型</span><span class="sxs-lookup"><span data-stu-id="9464b-710">Field/Type</span></span></th>
<th align="left"><span data-ttu-id="9464b-711">説明</span><span class="sxs-lookup"><span data-stu-id="9464b-711">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-712">Name (名前)</span><span class="sxs-lookup"><span data-stu-id="9464b-712">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-713">設定場所テンプレートの一意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9464b-713">Specifies a unique name for the settings location template.</span></span> <span data-ttu-id="9464b-714">これは、WMI、PowerShell、イベントビューアー、デバッグログでテンプレートを参照するときに表示するために使われます。</span><span class="sxs-lookup"><span data-stu-id="9464b-714">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="9464b-715">詳細については、「名前」を参照してください <a href="#name" data-raw-source="[Name](#name)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="9464b-715">For more information, see <a href="#name" data-raw-source="[Name](#name)">Name</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-716">ID</span><span class="sxs-lookup"><span data-stu-id="9464b-716">ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-717">特定のテンプレートの一意の識別子を設定します。</span><span class="sxs-lookup"><span data-stu-id="9464b-717">Populates a unique identifier for a particular template.</span></span> <span data-ttu-id="9464b-718">このタグは、UE-V Agent が実行時にテンプレートを参照するために使用するプライマリ識別子になります。</span><span class="sxs-lookup"><span data-stu-id="9464b-718">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime.</span></span> <span data-ttu-id="9464b-719">詳細については、「ID」を参照してください <a href="#id" data-raw-source="[ID](#id)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="9464b-719">For more information, see <a href="#id" data-raw-source="[ID](#id)">ID</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-720">説明</span><span class="sxs-lookup"><span data-stu-id="9464b-720">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-721">テンプレートの説明 (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="9464b-721">An optional description of the template.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-722">LocalizedNames</span><span class="sxs-lookup"><span data-stu-id="9464b-722">LocalizedNames</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-723">UI に表示されるオプションの名前。言語ロケールによってローカライズされます。</span><span class="sxs-lookup"><span data-stu-id="9464b-723">An optional name displayed in the UI, localized by a language locale.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-724">LocalizedDescriptions</span><span class="sxs-lookup"><span data-stu-id="9464b-724">LocalizedDescriptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-725">言語ロケールによってローカライズされた省略可能なテンプレートの説明です。</span><span class="sxs-lookup"><span data-stu-id="9464b-725">An optional template description localized by a language locale.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-726">バージョン</span><span class="sxs-lookup"><span data-stu-id="9464b-726">Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-727">変更の管理追跡用の設定場所テンプレートのバージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="9464b-727">Identifies the version of the settings location template for administrative tracking of changes.</span></span> <span data-ttu-id="9464b-728">詳細については、「バージョン」を参照してください <a href="#version" data-raw-source="[Version](#version)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="9464b-728">For more information, see <a href="#version" data-raw-source="[Version](#version)">Version</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-729">DeferToMSAccount</span><span class="sxs-lookup"><span data-stu-id="9464b-729">DeferToMSAccount</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-730">このテンプレートが Microsoft アカウントと組み合わせて有効になっているかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="9464b-730">Controls whether this template is enabled in conjunction with a Microsoft account or not.</span></span> <span data-ttu-id="9464b-731">コンピューター上のユーザーに対して MSA の同期が有効になっている場合、このテンプレートは自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="9464b-731">If MSA syncing is enabled for a user on a machine, then this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-732">DeferToOffice365</span><span class="sxs-lookup"><span data-stu-id="9464b-732">DeferToOffice365</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-733">MSA の場合と同様に、このテンプレートを Office365 と組み合わせて有効にするかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="9464b-733">Similar to MSA, this controls whether this template is enabled in conjunction with Office365.</span></span> <span data-ttu-id="9464b-734">設定の同期に Office 365 が使用されている場合、このテンプレートは自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="9464b-734">If Office 365 is being used to sync settings, this template will automatically be disabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-735">設定</span><span class="sxs-lookup"><span data-stu-id="9464b-735">Settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-736">特定のテンプレートに適用されるすべての設定のコンテナー。</span><span class="sxs-lookup"><span data-stu-id="9464b-736">A container for all the settings that apply to a particular template.</span></span> <span data-ttu-id="9464b-737">これには、Registry、File、SystemParameter、および CustomAction の各設定のインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9464b-737">It contains instances of the Registry, File, SystemParameter, and CustomAction settings.</span></span> <span data-ttu-id="9464b-738">詳細については、「 <strong> </strong> データ型の設定」を参照してください <a href="#data" data-raw-source="[Data types](#data)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="9464b-738">For more information, see <strong>Settings</strong> in <a href="#data" data-raw-source="[Data types](#data)">Data types</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="settingslocationtemplate"></a><span data-ttu-id="9464b-739">SettingsLocationTemplate 要素</span><span class="sxs-lookup"><span data-stu-id="9464b-739">SettingsLocationTemplate Element</span></span>

<span data-ttu-id="9464b-740">この要素は、1つのアプリケーションまたは一連のアプリケーションの設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="9464b-740">This element defines the settings for a single application or a suite of applications.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9464b-741">フィールド/型</span><span class="sxs-lookup"><span data-stu-id="9464b-741">Field/Type</span></span></th>
<th align="left"><span data-ttu-id="9464b-742">説明</span><span class="sxs-lookup"><span data-stu-id="9464b-742">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-743">Name (名前)</span><span class="sxs-lookup"><span data-stu-id="9464b-743">Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-744">設定場所テンプレートの一意の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9464b-744">Specifies a unique name for the settings location template.</span></span> <span data-ttu-id="9464b-745">これは、WMI、PowerShell、イベントビューアー、デバッグログでテンプレートを参照するときに表示するために使われます。</span><span class="sxs-lookup"><span data-stu-id="9464b-745">This is used for display purposes when referencing the template in WMI, PowerShell, Event Viewer and debug logs.</span></span> <span data-ttu-id="9464b-746">詳細については、「名前」を参照してください <a href="#name" data-raw-source="[Name](#name)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="9464b-746">For more information, see <a href="#name" data-raw-source="[Name](#name)">Name</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-747">ID</span><span class="sxs-lookup"><span data-stu-id="9464b-747">ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-748">特定のテンプレートの一意の識別子を設定します。</span><span class="sxs-lookup"><span data-stu-id="9464b-748">Populates a unique identifier for a particular template.</span></span> <span data-ttu-id="9464b-749">このタグは、UE-V Agent が実行時にテンプレートを参照するために使用するプライマリ識別子になります。</span><span class="sxs-lookup"><span data-stu-id="9464b-749">This tag becomes the primary identifier that the UE-V Agent uses to reference the template at runtime.</span></span> <span data-ttu-id="9464b-750">詳細については、「ID」を参照してください <a href="#id" data-raw-source="[ID](#id)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="9464b-750">For more information, see <a href="#id" data-raw-source="[ID](#id)">ID</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-751">説明</span><span class="sxs-lookup"><span data-stu-id="9464b-751">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-752">テンプレートの説明 (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="9464b-752">An optional description of the template.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9464b-753">LocalizedNames</span><span class="sxs-lookup"><span data-stu-id="9464b-753">LocalizedNames</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-754">UI に表示されるオプションの名前。言語ロケールによってローカライズされます。</span><span class="sxs-lookup"><span data-stu-id="9464b-754">An optional name displayed in the UI, localized by a language locale.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9464b-755">LocalizedDescriptions</span><span class="sxs-lookup"><span data-stu-id="9464b-755">LocalizedDescriptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="9464b-756">言語ロケールによってローカライズされた省略可能なテンプレートの説明です。</span><span class="sxs-lookup"><span data-stu-id="9464b-756">An optional template description localized by a language locale.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="appendix"></a><span data-ttu-id="9464b-757">付録: SettingsLocationTemplate .xsd</span><span class="sxs-lookup"><span data-stu-id="9464b-757">Appendix: SettingsLocationTemplate.xsd</span></span>

<span data-ttu-id="9464b-758">次に示すのは、要素、子要素、属性、パラメーターが表示された SettingsLocationTemplate です。</span><span class="sxs-lookup"><span data-stu-id="9464b-758">Here is the SettingsLocationTemplate.xsd file showing its elements, child elements, attributes, and parameters:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="UevSettingsLocationTemplate"
  targetNamespace="https://schemas.microsoft.com/UserExperienceVirtualization/2013/SettingsLocationTemplate"
  elementFormDefault="qualified"
  xmlns="https://schemas.microsoft.com/UserExperienceVirtualization/2013/SettingsLocationTemplate"
  xmlns:mstns="https://schemas.microsoft.com/UserExperienceVirtualization/2013/SettingsLocationTemplate"
  xmlns:xs="http://www.w3.org/2001/XMLSchema">

  <xs:simpleType name="Guid">
    <xs:restriction base="xs:string">
      <xs:pattern value="\{[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{12}\}" />
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="FilenameString">
    <xs:restriction base="xs:string">
      <xs:pattern value="[^\\\?\*\|&lt;&gt;/:]+" />
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="IDString">
    <xs:restriction base="xs:string">
      <xs:pattern value="[^\\\?\*\|&lt;&gt;/:.]+" />
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="TemplateVersion">
    <xs:restriction base="xs:integer">
      <xs:minInclusive value="0" />
      <xs:maxInclusive value="2147483647" />
    </xs:restriction>
  </xs:simpleType>

  <xs:complexType name="Empty">
    <xs:sequence/>
  </xs:complexType>

  <xs:complexType name="LocalizedString">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="Locale" type="xs:string" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>

  <xs:complexType name="LocalizedName">
    <xs:sequence>
      <xs:element name="Name" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="LocalizedDescription">
    <xs:sequence>
      <xs:element name="Description" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Author">
    <xs:all>
      <xs:element name="Name" type="xs:string" minOccurs="1" />
      <xs:element name="Email" type="xs:string" minOccurs="0" />
    </xs:all>
  </xs:complexType>

  <xs:complexType name="Range">
    <xs:attribute name="Minimum" type="xs:integer" use="required"/>
    <xs:attribute name="Maximum" type="xs:integer" use="required"/>
  </xs:complexType>

  <xs:complexType name="ProcessVersion">
    <xs:sequence>
      <xs:element name="Major" type="Range" minOccurs="1" />
      <xs:element name="Minor" type="Range" minOccurs="0" />
      <xs:element name="Build" type="Range" minOccurs="0" />
      <xs:element name="Patch" type="Range" minOccurs="0" />
    </xs:sequence>
  </xs:complexType>

  <xs:simpleType name="Architecture">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Win32"/>
      <xs:enumeration value="Win64"/>
    </xs:restriction>
  </xs:simpleType>

  <xs:complexType name="Process">
    <xs:sequence>
      <xs:element name="Filename" type="FilenameString" minOccurs="1" />
      <xs:element name="Architecture" type="Architecture" minOccurs="0" />
      <xs:element name="ProductName" type="xs:string" minOccurs="0" />
      <xs:element name="FileDescription" type="xs:string" minOccurs="0" />
      <xs:element name="ProductVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
      <xs:element name="FileVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Processes">
    <xs:sequence>
      <xs:choice minOccurs="1">
        <xs:element name="Process" type="Process" />
        <xs:element name="ShellProcess" type="Empty" />
      </xs:choice>
      <xs:element name="Process" type="Process" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Path">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="Recursive" type="xs:boolean" default="false"/>
        <xs:attribute name="DeleteIfNotFound" type="xs:boolean" default="false"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>

  <xs:complexType name="RegistrySetting">
    <xs:sequence>
      <xs:element name="Path" type="Path" />
      <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
      <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
        <xs:complexType>
          <xs:sequence>
            <xs:element name="Path" type="Path" minOccurs="0" />
            <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
          </xs:sequence>
        </xs:complexType>
      </xs:element>
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="FileSetting">
    <xs:sequence>

      <xs:element name="Root">
        <xs:complexType>
          <xs:choice>
            <xs:element name="KnownFolder" type="Guid" />
            <xs:element name="RegistryEntry" type="xs:string" />
            <xs:element name="EnvironmentVariable" type="xs:string" />
          </xs:choice>
        </xs:complexType>
      </xs:element>

      <xs:element name="Path" minOccurs="0" type="Path" />
      <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded"/>

      <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
        <xs:complexType>
          <xs:sequence>
            <xs:element name="Path" type="Path" minOccurs="0" />
            <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
          </xs:sequence>
        </xs:complexType>
      </xs:element>

    </xs:sequence>
  </xs:complexType>

  <xs:simpleType name="SystemParameterSetting">
    <xs:restriction base="xs:string">

      <!-- Accessibility parameters -->
      <xs:enumeration value="AccessTimeout"/>
      <xs:enumeration value="AudioDescription"/>
      <xs:enumeration value="ClientAreaAnimation"/>
      <xs:enumeration value="DisableOverlappedContent"/>
      <xs:enumeration value="FilterKeys"/>
      <xs:enumeration value="FocusBorderHeight"/>
      <xs:enumeration value="FocusBorderWidth"/>
      <xs:enumeration value="HighContrast"/>
      <xs:enumeration value="MessageDuration"/>
      <xs:enumeration value="MouseClickLock"/>
      <xs:enumeration value="MouseClickLockTime"/>
      <xs:enumeration value="MouseKeys"/>
      <xs:enumeration value="MouseSonar"/>
      <xs:enumeration value="MouseVanish"/>
      <xs:enumeration value="ScreenReader"/>
      <xs:enumeration value="ShowSounds"/>
      <xs:enumeration value="SoundSentry"/>
      <xs:enumeration value="StickyKeys"/>
      <xs:enumeration value="ToggleKeys"/>

      <!-- Input parameters -->
      <xs:enumeration value="Beep"/>
      <xs:enumeration value="BlockSendInputResets"/>
      <xs:enumeration value="DefaultInputLang"/>
      <xs:enumeration value="DoubleClickTime"/>
      <xs:enumeration value="DoubleClkHeight"/>
      <xs:enumeration value="DoubleClkWidth"/>
      <xs:enumeration value="KeyboardCues"/>
      <xs:enumeration value="KeyboardDelay"/>
      <xs:enumeration value="KeyboardPref"/>
      <xs:enumeration value="KeyboardSpeed"/>
      <xs:enumeration value="Mouse"/>
      <xs:enumeration value="MouseButtonSwap"/>
      <xs:enumeration value="MouseHoverHeight"/>
      <xs:enumeration value="MouseHoverTime"/>
      <xs:enumeration value="MouseHoverWidth"/>
      <xs:enumeration value="MouseSpeed"/>
      <xs:enumeration value="MouseTrails"/>
      <xs:enumeration value="SnapToDefButton"/>
      <xs:enumeration value="WheelScrollChars"/>
      <xs:enumeration value="WheelScrollLines"/>

      <!-- Desktop parameters (limited subset) -->
      <xs:enumeration value="DeskWallpaper"/>
      <xs:enumeration value="DesktopColor"/>

    </xs:restriction>
  </xs:simpleType>

  <xs:complexType name="Settings">
    <xs:sequence>
      <xs:element name="Asynchronous" type="xs:boolean" minOccurs="0" />
      <xs:element name="PreventOverlappingSynchronization" type="xs:boolean" minOccurs="0" />
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Registry" type="RegistrySetting" />
        <xs:element name="File" type="FileSetting" />
        <xs:element name="SystemParameter" type="SystemParameterSetting" />
      </xs:choice>
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Common">
    <xs:sequence>
      <xs:element name="Name" type="xs:string" />
      <xs:element name="ID" type="IDString" />
      <xs:element name="Description" type="xs:string" minOccurs="0" />
      <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
      <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
      <xs:element name="Version" type="xs:integer" />
      <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
      <xs:element name="Settings" type="Settings" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Application">
    <xs:sequence>
      <xs:element name="Name" type="xs:string" />
      <xs:element name="ID" type="IDString" />
      <xs:element name="Description" type="xs:string" minOccurs="0" />
      <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
      <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
      <xs:element name="Version" type="xs:integer" />
      <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
      <xs:element name="Processes" type="Processes" />
      <xs:element name="Settings" type="Settings" />
    </xs:sequence>
  </xs:complexType>


  <xs:element name="SettingsLocationTemplate">
    <xs:complexType>
      <xs:sequence>

        <xs:element name="Name" type="xs:string" />
        <xs:element name="ID" type="IDString" />
        <xs:element name="Description" type="xs:string" minOccurs="0" />
        <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
        <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />

        <xs:choice>

          <!-- Single application -->
          <xs:sequence>
            <xs:element name="Version" type="TemplateVersion" />
            <xs:element name="Author" type="Author" minOccurs="0" />
            <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
            <xs:element name="Processes" type="Processes" />
            <xs:element name="Settings" type="Settings" />
          </xs:sequence>

          <!-- Suite of applications -->
          <xs:sequence>
            <xs:element name="ManageSuiteOnly" type="xs:boolean" minOccurs="0" />
            <xs:element name="Author" type="Author" minOccurs="0" />
            <xs:element name="Common" type="Common" />
            <xs:element name="Application" type="Application" minOccurs="2" maxOccurs="unbounded" />
          </xs:sequence>

        </xs:choice>

      </xs:sequence>
    </xs:complexType>
  </xs:element>
  <!-- SettingsLocationTemplate -->

</xs:schema>
```






## <span data-ttu-id="9464b-759">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9464b-759">Related topics</span></span>


[<span data-ttu-id="9464b-760">カスタム ue-v (ue-v) テンプレートと UE-V Generator を使って作業する</span><span class="sxs-lookup"><span data-stu-id="9464b-760">Working with Custom UE-V 2.x Templates and the UE-V 2.x Generator</span></span>](working-with-custom-ue-v-2x-templates-and-the-ue-v-2x-generator-new-uevv2.md)

[<span data-ttu-id="9464b-761">UE-V 2.x のテクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="9464b-761">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)

 

 





