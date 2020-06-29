---
title: 接続グループ ファイルについて
description: 接続グループ ファイルについて
author: dansimp
ms.assetid: 1f4df515-f5f6-4b58-91a8-c71598cb3ea4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 31ef9dc9c4465ed8f261b73518348c05ceb78d15
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814930"
---
# <span data-ttu-id="778ea-103">接続グループ ファイルについて</span><span class="sxs-lookup"><span data-stu-id="778ea-103">About the Connection Group File</span></span>


**<span data-ttu-id="778ea-104">このトピックの内容は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="778ea-104">In this topic:</span></span>**

-   [<span data-ttu-id="778ea-105">接続グループファイルの目的と場所</span><span class="sxs-lookup"><span data-stu-id="778ea-105">Connection group file purpose and location</span></span>](#bkmk-cg-purpose-loc)

-   [<span data-ttu-id="778ea-106">接続グループの XML ファイルの構造</span><span class="sxs-lookup"><span data-stu-id="778ea-106">Structure of the connection group XML file</span></span>](#bkmk-define-cg-5-0sp3)

-   [<span data-ttu-id="778ea-107">接続グループ内のパッケージの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="778ea-107">Configuring the priority of packages in a connection group</span></span>](#bkmk-config-pkg-priority-incg)

-   [<span data-ttu-id="778ea-108">サポートされている仮想アプリケーション接続構成</span><span class="sxs-lookup"><span data-stu-id="778ea-108">Supported virtual application connection configurations</span></span>](#bkmk-va-conn-configs)

## <a href="" id="bkmk-cg-purpose-loc"></a><span data-ttu-id="778ea-109">接続グループファイルの目的と場所</span><span class="sxs-lookup"><span data-stu-id="778ea-109">Connection group file purpose and location</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="778ea-110">接続グループの目的</span><span class="sxs-lookup"><span data-stu-id="778ea-110">Connection group purpose</span></span></p></td>
<td align="left"><p><span data-ttu-id="778ea-111">接続グループは、パッケージをグループ化して、それらのパッケージ内のアプリケーションが相互に対話できる仮想環境を作成できるようにするアプリ V の機能です。</span><span class="sxs-lookup"><span data-stu-id="778ea-111">A connection group is an App-V feature that enables you to group packages together to create a virtual environment in which the applications in those packages can interact with each other.</span></span></p>
<p><span data-ttu-id="778ea-112">例: Microsoft Office でプラグインを使用する場合。</span><span class="sxs-lookup"><span data-stu-id="778ea-112">Example: You want to use plug-ins with Microsoft Office.</span></span> <span data-ttu-id="778ea-113">プラグインを含むパッケージを作成して、Office を含む別のパッケージを作成し、両方のパッケージを接続グループに追加して、これらのプラグインを使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="778ea-113">You can create a package that contains the plug-ins, and create another package that contains Office, and then add both packages to a connection group to enable Office to use those plug-ins.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="778ea-114">接続グループファイルのしくみ</span><span class="sxs-lookup"><span data-stu-id="778ea-114">How the connection group file works</span></span></p></td>
<td align="left"><p><span data-ttu-id="778ea-115">App-v 5.1 接続グループファイルを適用すると、ファイルで列挙されるパッケージは、実行時に1つの仮想環境に結合されます。</span><span class="sxs-lookup"><span data-stu-id="778ea-115">When you apply an App-V 5.1 connection group file, the packages that are enumerated in the file will be combined at runtime into a single virtual environment.</span></span> <span data-ttu-id="778ea-116">Microsoft Application Virtualization (App-v) 5.1 接続グループファイルを使用して、既存のアプリ-V 5.1 接続グループを構成します。</span><span class="sxs-lookup"><span data-stu-id="778ea-116">Use the Microsoft Application Virtualization (App-V) 5.1 connection group file to configure existing App-V 5.1 connection groups.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="778ea-117">ファイルパスの例</span><span class="sxs-lookup"><span data-stu-id="778ea-117">Example file path</span></span></p></td>
<td align="left"><p><span data-ttu-id="778ea-118">%APPDATA%\Microsoft\AppV\Client\Catalog\PackageGroups {6CCC7575-162E-4152-9407-ED411DA138F4} {4D1E16E1-8EF8-41ED D5-8910a8524d96}。</span><span class="sxs-lookup"><span data-stu-id="778ea-118">%APPDATA%\Microsoft\AppV\Client\Catalog\PackageGroups{6CCC7575-162E-4152-9407-ED411DA138F4}{4D1E16E1-8EF8-41ED-92D5-8910A8527F96}.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-define-cg-5-0sp3"></a><span data-ttu-id="778ea-119">接続グループの XML ファイルの構造</span><span class="sxs-lookup"><span data-stu-id="778ea-119">Structure of the connection group XML file</span></span>


**<span data-ttu-id="778ea-120">このセクションの内容:</span><span class="sxs-lookup"><span data-stu-id="778ea-120">In this section:</span></span>**

-   [<span data-ttu-id="778ea-121">接続グループを定義するパラメーター</span><span class="sxs-lookup"><span data-stu-id="778ea-121">Parameters that define the connection group</span></span>](#bkmk-params-define-cg)

-   [<span data-ttu-id="778ea-122">接続グループ内のパッケージを定義するパラメーター</span><span class="sxs-lookup"><span data-stu-id="778ea-122">Parameters that define the packages in the connection group</span></span>](#bkmk-params-define-pkgs-incg)

-   [<span data-ttu-id="778ea-123">App-v の例: 接続グループの XML ファイル</span><span class="sxs-lookup"><span data-stu-id="778ea-123">App-V example connection group XML file</span></span>](#bkmk-50sp3-exp-cg-xml)

-   [<span data-ttu-id="778ea-124">App-v 5.0 ~ app-v 5.0 SP2 のサンプル接続グループの XML ファイル</span><span class="sxs-lookup"><span data-stu-id="778ea-124">App-V 5.0 through App-V 5.0 SP2 example connection group XML file</span></span>](#bkmk-50thru50sp2-exp-cg-xm)

### <a href="" id="bkmk-params-define-cg"></a><span data-ttu-id="778ea-125">接続グループを定義するパラメーター</span><span class="sxs-lookup"><span data-stu-id="778ea-125">Parameters that define the connection group</span></span>

<span data-ttu-id="778ea-126">次の表では、パッケージではなく、接続グループ自体を定義する XML ファイルのパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="778ea-126">The following table describes the parameters in the XML file that define the connection group itself, not the packages.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="778ea-127">フィールド</span><span class="sxs-lookup"><span data-stu-id="778ea-127">Field</span></span></th>
<th align="left"><span data-ttu-id="778ea-128">説明</span><span class="sxs-lookup"><span data-stu-id="778ea-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="778ea-129">スキーマ名</span><span class="sxs-lookup"><span data-stu-id="778ea-129">Schema name</span></span></p></td>
<td align="left"><p><span data-ttu-id="778ea-130">スキーマの名前。</span><span class="sxs-lookup"><span data-stu-id="778ea-130">Name of the schema.</span></span></p>
<p><strong><span data-ttu-id="778ea-131"></strong>この表で説明されている新しい "optional packages" と "use any" 機能を使用する場合は、この XML ファイルで次のスキーマを指定する必要があります。5.0</span><span class="sxs-lookup"><span data-stu-id="778ea-131">Applicable starting in App-V 5.0 SP3</strong>: If you want to use the new “optional packages” and “use any version” features that are described in this table, you must specify the following schema in the XML file:</span></span></p>
<p><code>xmlns=&quot;<a href="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot" data-raw-source="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot">https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&quot</a>;</code></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="778ea-132">AppConnectionGroupId</span><span class="sxs-lookup"><span data-stu-id="778ea-132">AppConnectionGroupId</span></span></p></td>
<td align="left"><p><span data-ttu-id="778ea-133">この接続グループの一意の GUID 識別子。</span><span class="sxs-lookup"><span data-stu-id="778ea-133">Unique GUID identifier for this connection group.</span></span> <span data-ttu-id="778ea-134">接続グループの状態は、この識別子に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="778ea-134">The connection group state is associated with this identifier.</span></span> <span data-ttu-id="778ea-135">この識別子は、接続グループを作成するときにのみ指定します。</span><span class="sxs-lookup"><span data-stu-id="778ea-135">Specify this identifier only when you create the connection group.</span></span></p>
<p><span data-ttu-id="778ea-136">新しい GUID を作成するには、次のように入力 <strong>[Guid]::NewGuid()</strong> します。</span><span class="sxs-lookup"><span data-stu-id="778ea-136">You can create a new GUID by typing: <strong>[Guid]::NewGuid()</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="778ea-137">VersionId</span><span class="sxs-lookup"><span data-stu-id="778ea-137">VersionId</span></span></p></td>
<td align="left"><p><span data-ttu-id="778ea-138">このバージョンの接続グループのバージョン GUID 識別子。</span><span class="sxs-lookup"><span data-stu-id="778ea-138">Version GUID identifier for this version of the connection group.</span></span></p>
<p><span data-ttu-id="778ea-139">接続グループを更新する場合 (たとえば、新しいパッケージを追加または更新する場合) は、新しいバージョンを反映するようにバージョン GUID を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="778ea-139">When you update a connection group (for example, by adding or updating a new package), you must update the version GUID to reflect the new version.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="778ea-140">DisplayName</span><span class="sxs-lookup"><span data-stu-id="778ea-140">DisplayName</span></span></p></td>
<td align="left"><p><span data-ttu-id="778ea-141">接続グループの表示名。</span><span class="sxs-lookup"><span data-stu-id="778ea-141">Display name of the connection group.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="778ea-142">Priority</span><span class="sxs-lookup"><span data-stu-id="778ea-142">Priority</span></span></p></td>
<td align="left"><p><span data-ttu-id="778ea-143">接続グループのオプションの priority フィールド。</span><span class="sxs-lookup"><span data-stu-id="778ea-143">Optional priority field for the connection group.</span></span></p>
<p><strong><span data-ttu-id="778ea-144">"0" </strong> - は、最も優先度の高い値を示します。</span><span class="sxs-lookup"><span data-stu-id="778ea-144">“0”</strong> - indicates the highest priority.</span></span></p>
<p><span data-ttu-id="778ea-145">優先度は必須ですが、構成されていない場合は、使用する正しい接続グループが判断できないため、パッケージは失敗します。</span><span class="sxs-lookup"><span data-stu-id="778ea-145">If a priority is required, but has not been configured, the package will fail because the correct connection group to use cannot be determined.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-params-define-pkgs-incg"></a><span data-ttu-id="778ea-146">接続グループ内のパッケージを定義するパラメーター</span><span class="sxs-lookup"><span data-stu-id="778ea-146">Parameters that define the packages in the connection group</span></span>

<span data-ttu-id="778ea-147">接続グループ &lt; の &gt; XML ファイルの [パッケージ] セクションで、次の表に示すように、各パッケージの一意のパッケージ識別子とバージョン識別子を指定して、接続グループにメンバーパッケージを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="778ea-147">In the &lt;Packages&gt; section of the connection group XML file, you list the member packages in the connection group by specifying each package’s unique package identifier and version identifier, as described in the following table.</span></span> <span data-ttu-id="778ea-148">一覧の最初のパッケージの優先順位が最も高くなります。</span><span class="sxs-lookup"><span data-stu-id="778ea-148">The first package in the list has the highest precedence.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="778ea-149">フィールド</span><span class="sxs-lookup"><span data-stu-id="778ea-149">Field</span></span></th>
<th align="left"><span data-ttu-id="778ea-150">説明</span><span class="sxs-lookup"><span data-stu-id="778ea-150">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="778ea-151">PackageId</span><span class="sxs-lookup"><span data-stu-id="778ea-151">PackageId</span></span></p></td>
<td align="left"><p><span data-ttu-id="778ea-152">このパッケージの一意の GUID 識別子。</span><span class="sxs-lookup"><span data-stu-id="778ea-152">Unique GUID identifier for this package.</span></span> <span data-ttu-id="778ea-153">この GUID は、パッケージの新しいバージョンが公開されたときには変更されません。</span><span class="sxs-lookup"><span data-stu-id="778ea-153">This GUID doesn’t change when newer versions of the package are published.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="778ea-154">VersionId</span><span class="sxs-lookup"><span data-stu-id="778ea-154">VersionId</span></span></p></td>
<td align="left"><p><span data-ttu-id="778ea-155">パッケージのバージョンを表す一意の GUID 識別子。</span><span class="sxs-lookup"><span data-stu-id="778ea-155">Unique GUID identifier for the version of the package.</span></span></p>
<p><strong><span data-ttu-id="778ea-156">App-v 5.0 SP3 での開始に適用 </strong> される機能: <strong> パッケージバージョンに "\*" を指定した場合 </strong> 、利用可能な最新のパッケージバージョンの GUID が動的に挿入されます。</span><span class="sxs-lookup"><span data-stu-id="778ea-156">Applicable starting in App-V 5.0 SP3</strong>: If you specify <strong>“\*”</strong> for the package version, the GUID of the latest available package version is dynamically inserted.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="778ea-157">IsOptional</span><span class="sxs-lookup"><span data-stu-id="778ea-157">IsOptional</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="778ea-158">App-V 5.0 SP3 </strong> : パラメーターを使用すると、接続グループ内でパッケージをオプションにすることができます。</span><span class="sxs-lookup"><span data-stu-id="778ea-158">Applicable starting in App-V 5.0 SP3</strong>: Parameter that enables you to make a package optional within the connection group.</span></span> <span data-ttu-id="778ea-159">有効なエントリは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="778ea-159">Valid entries are:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="778ea-160">"true" </strong> –パッケージは接続グループでオプションです</span><span class="sxs-lookup"><span data-stu-id="778ea-160">“true”</strong> – package is optional in the connection group</span></span></p></li>
<li><p><strong><span data-ttu-id="778ea-161">"false" </strong> –パッケージは接続グループで必要</span><span class="sxs-lookup"><span data-stu-id="778ea-161">“false”</strong> – package is required in the connection group</span></span></p></li>
</ul>
<p><span data-ttu-id="778ea-162"><a href="how-to-use-optional-packages-in-connection-groups51.md" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups51.md)">接続グループでオプションパッケージを使用する方法について説明し </a> ます。</span><span class="sxs-lookup"><span data-stu-id="778ea-162">See <a href="how-to-use-optional-packages-in-connection-groups51.md" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups51.md)">How to Use Optional Packages in Connection Groups</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-50sp3-exp-cg-xml"></a><span data-ttu-id="778ea-163">App-v の例: 接続グループの XML ファイル</span><span class="sxs-lookup"><span data-stu-id="778ea-163">App-V example connection group XML file</span></span>

<span data-ttu-id="778ea-164">次の例の接続グループ XML ファイルは、前の表のフィールドの例を示しています。また、アプリ-V 5.0 SP3 で開始される新しいアイテムを強調表示しています。</span><span class="sxs-lookup"><span data-stu-id="778ea-164">The following example connection group XML file shows examples of the fields in the previous tables and highlights the items that are new starting in App-V 5.0 SP3.</span></span>

```XML
<?xml version="1.0" encoding="UTF-16">
<appv:AppConnectionGroup 
  xmlns="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup"
  xmlns:appv="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup"  
  AppConnectionGroupId="61BE9B14-D2B4-41CE-A6E3-A1B658DE7000"
  VersionId="E6B6AA57-F2A7-49C9-ADF8-F2B5B3C8A42F"
  Priority="0"  
  DisplayName="Sample Connection Group">
  <appv:Packages>    
    <appv:Package
      PackageId="1DC709C8-309F-4AB4-BD47-F75926D04276"
      VersionId="*"
      IsOptional="true"    
    />
    <appv:Package
      PackageId="04220DCA-EE77-42BE-A9F5-96FD8E8593F2"
      VersionId="E15EFFE9-043D-4C01-BC52-AD2BD1E8BAFA"
      IsOptional="false"    
    />  
  </appv:Packages>
</appv:AppConnectionGroup>
```

### <a href="" id="bkmk-50thru50sp2-exp-cg-xm"></a><span data-ttu-id="778ea-165">App-v 5.0 ~ app-v 5.0 SP2 のサンプル接続グループの XML ファイル</span><span class="sxs-lookup"><span data-stu-id="778ea-165">App-V 5.0 through App-V 5.0 SP2 example connection group XML file</span></span>

<span data-ttu-id="778ea-166">次の例の接続グループ XML ファイルは、app-v 5.0 SP2 経由で app-v 5.0 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="778ea-166">The following example connection group XML file applies to App-V 5.0 through App-V 5.0 SP2.</span></span> <span data-ttu-id="778ea-167">前の表のフィールドの例を示していますが、上記で説明した変更は、App-v 5.0 SP3 では除外されています。</span><span class="sxs-lookup"><span data-stu-id="778ea-167">It shows examples of the fields in the previous table, but it excludes the changes described above for App-V 5.0 SP3.</span></span>

```XML
<?xml version="1.0" encoding="UTF-16">
<appv:AppConnectionGroup
  xmlns="https://schemas.microsoft.com/appv/2010/virtualapplicationconnectiongroup"
  xmlns:appv="https://schemas.microsoft.com/appv/2010/virtualapplicationconnectiongroup"
  AppConnectionGroupId="61BE9B14-D2B4-41CE-A6E3-A1B658DE7000"
  VersionId="E6B6AA57-F2A7-49C9-ADF8-F2B5B3C8A42F"
  Priority="0"
  DisplayName="Sample Connection Group">
  <appv:Packages>
    <appv:Package
      PackageId="1DC709C8-309F-4AB4-BD47-F75926D04276"
      VersionId="C7DF4F63-5288-439C-ACEF-EF06BF401EC5"
    />
    <appv:Package
     PackageId="04220DCA-EE77-42BE-A9F5-96FD8E8593F2"
     VersionId="E15EFFE9-043D-4C01-BC52-AD2BD1E8BAFA"
   />
 </appv:Packages>
<appv:AppConnectionGroup>
```

## <a href="" id="bkmk-config-pkg-priority-incg"></a><span data-ttu-id="778ea-168">接続グループ内のパッケージの優先度を設定する</span><span class="sxs-lookup"><span data-stu-id="778ea-168">Configuring the priority of packages in a connection group</span></span>


<span data-ttu-id="778ea-169">パッケージの優先順位は、パッケージの一覧順序で構成されます。</span><span class="sxs-lookup"><span data-stu-id="778ea-169">Package precedence is configured using the package list order.</span></span> <span data-ttu-id="778ea-170">ドキュメント内の最初のパッケージの優先順位が最も高くなります。</span><span class="sxs-lookup"><span data-stu-id="778ea-170">The first package in the document has the highest precedence.</span></span> <span data-ttu-id="778ea-171">リスト内の後続のパッケージの優先度が降順になります。</span><span class="sxs-lookup"><span data-stu-id="778ea-171">Subsequent packages in the list have descending priority.</span></span>

<span data-ttu-id="778ea-172">パッケージの優先順位は、仮想環境の初期化中に、それ以外の不可避リソースの競合を解決するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="778ea-172">Package precedence is the resolution for otherwise inevitable resource collisions during virtual environment initialization.</span></span> <span data-ttu-id="778ea-173">たとえば、同じ仮想環境で開かれている2つのパッケージが同じレジストリ DWORD 値を定義している場合、最も優先順位の高いパッケージでは、設定されている値が決定されます。</span><span class="sxs-lookup"><span data-stu-id="778ea-173">For example, if two packages that are opening in the same virtual environment define the same registry DWORD value, the package with the highest precedence determines the value that is set.</span></span>

<span data-ttu-id="778ea-174">次の方法を使用して、接続グループファイルを使用して各接続グループを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="778ea-174">You can use the connection group file to configure each connection group by using the following methods:</span></span>

-   <span data-ttu-id="778ea-175">接続グループの実行時の優先順位を指定します。</span><span class="sxs-lookup"><span data-stu-id="778ea-175">Specify runtime priorities for connection groups.</span></span> <span data-ttu-id="778ea-176">App-v 管理コンソールを使用して優先順位を編集するには、接続グループをクリックし、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="778ea-176">To edit priority by using the App-V Management Console, click the connection group and then click **Edit**.</span></span>

    <span data-ttu-id="778ea-177">**注** 優先度は、パッケージが複数の接続グループに関連付けられている場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="778ea-177">**Note** Priority is required only if the package is associated with more than one connection group.</span></span>

     

-   <span data-ttu-id="778ea-178">接続グループ内でパッケージの優先順位を指定します。</span><span class="sxs-lookup"><span data-stu-id="778ea-178">Specify package precedence within the connection group.</span></span>

<span data-ttu-id="778ea-179">[優先度] フィールドは、実行中の仮想アプリケーションがネイティブのアプリケーション要求 (Microsoft Windows エクスプローラーなど) から開始されるときに必要です。</span><span class="sxs-lookup"><span data-stu-id="778ea-179">The priority field is required when a running virtual application initiates from a native application request, for example, Microsoft Windows Explorer.</span></span> <span data-ttu-id="778ea-180">App-v クライアントは、優先順位を使って、アプリケーションが実行する必要がある接続グループの仮想環境を決定します。</span><span class="sxs-lookup"><span data-stu-id="778ea-180">The App-V client uses the priority to determine which connection group virtual environment the application should run in.</span></span> <span data-ttu-id="778ea-181">この状況は、仮想アプリケーションが複数の接続グループに含まれている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="778ea-181">This situation occurs if a virtual application is part of multiple connection groups.</span></span>

<span data-ttu-id="778ea-182">仮想アプリケーションを別の仮想アプリケーションで開いた場合、元の仮想アプリケーションの仮想環境が使用されます。</span><span class="sxs-lookup"><span data-stu-id="778ea-182">If a virtual application is opened using another virtual application the virtual environment of the original virtual application will be used.</span></span> <span data-ttu-id="778ea-183">この場合、[優先度] フィールドは使用されません。</span><span class="sxs-lookup"><span data-stu-id="778ea-183">The priority field is not used in this case.</span></span>

**<span data-ttu-id="778ea-184">例:</span><span class="sxs-lookup"><span data-stu-id="778ea-184">Example:</span></span>**

<span data-ttu-id="778ea-185">仮想アプリケーション Microsoft Outlook は、仮想環境**XYZ**で実行されています。</span><span class="sxs-lookup"><span data-stu-id="778ea-185">The virtual application Microsoft Outlook is running in virtual environment **XYZ**.</span></span> <span data-ttu-id="778ea-186">添付されている Microsoft word 文書を開くと、仮想環境**XYZ**で、microsoft word に関連付けられている接続グループまたは実行時の優先順位に関係なく、仮想化されたバージョンの microsoft word が開きます。</span><span class="sxs-lookup"><span data-stu-id="778ea-186">When you open an attached Microsoft Word document, a virtualized version Microsoft Word opens in the virtual environment **XYZ**, regardless of the virtualized Microsoft Word’s associated connection groups or runtime priorities.</span></span>

## <a href="" id="bkmk-va-conn-configs"></a><span data-ttu-id="778ea-187">サポートされている仮想アプリケーション接続構成</span><span class="sxs-lookup"><span data-stu-id="778ea-187">Supported virtual application connection configurations</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="778ea-188">構成</span><span class="sxs-lookup"><span data-stu-id="778ea-188">Configuration</span></span></th>
<th align="left"><span data-ttu-id="778ea-189">シナリオ例</span><span class="sxs-lookup"><span data-stu-id="778ea-189">Example scenario</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="778ea-190">を.</span><span class="sxs-lookup"><span data-stu-id="778ea-190">An.</span></span> <span data-ttu-id="778ea-191">exe ファイルとプラグイン (.dll)</span><span class="sxs-lookup"><span data-stu-id="778ea-191">exe file and plug-in (.dll)</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="778ea-192">Microsoft Office をすべてのユーザーに配布しますが、ユーザーのサブセットのみに Microsoft Excel プラグインを配布します。</span><span class="sxs-lookup"><span data-stu-id="778ea-192">You want to distribute Microsoft Office to all users, but distribute a Microsoft Excel plug-in to only a subset of users.</span></span></p></li>
<li><p><span data-ttu-id="778ea-193">適切なユーザーの接続グループを有効にします。</span><span class="sxs-lookup"><span data-stu-id="778ea-193">Enable the connection group for the appropriate users.</span></span></p></li>
<li><p><span data-ttu-id="778ea-194">必要に応じて各パッケージを個別に更新します。</span><span class="sxs-lookup"><span data-stu-id="778ea-194">Update each package individually as required.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="778ea-195">を.</span><span class="sxs-lookup"><span data-stu-id="778ea-195">An.</span></span> <span data-ttu-id="778ea-196">exe ファイルとミドルウェアアプリケーション</span><span class="sxs-lookup"><span data-stu-id="778ea-196">exe file and a middleware application</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="778ea-197">アプリケーションにはミドルウェアアプリケーションが必要です。または、すべてが同じミドルウェアランタイムバージョンに依存している複数のアプリケーションが必要です。</span><span class="sxs-lookup"><span data-stu-id="778ea-197">You have an application requires a middleware application, or several applications that all depend on the same middleware runtime version.</span></span></p></li>
<li><p><span data-ttu-id="778ea-198">1つまたは複数のアプリケーションが必要なすべてのコンピューターは、アプリケーションとミドルウェアアプリケーションのランタイムとの接続グループを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="778ea-198">All computers that require one or more of the applications receive the connection groups with the application and middleware application runtime.</span></span></p></li>
<li><p><span data-ttu-id="778ea-199">必要に応じて、複数のミドルウェアアプリケーションを1つの接続グループにまとめることができます。</span><span class="sxs-lookup"><span data-stu-id="778ea-199">You can optionally combine multiple middleware applications into a single connection group.</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="778ea-200">例</span><span class="sxs-lookup"><span data-stu-id="778ea-200">Example</span></span></th>
<th align="left"><span data-ttu-id="778ea-201">説明の例</span><span class="sxs-lookup"><span data-stu-id="778ea-201">Example description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="778ea-202">財務部門の仮想アプリケーション接続グループ</span><span class="sxs-lookup"><span data-stu-id="778ea-202">Virtual application connection group for the financial division</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="778ea-203">ミドルウェアアプリケーション1</span><span class="sxs-lookup"><span data-stu-id="778ea-203">Middleware application 1</span></span></p></li>
<li><p><span data-ttu-id="778ea-204">ミドルウェアアプリケーション2</span><span class="sxs-lookup"><span data-stu-id="778ea-204">Middleware application 2</span></span></p></li>
<li><p><span data-ttu-id="778ea-205">ミドルウェアアプリケーション3</span><span class="sxs-lookup"><span data-stu-id="778ea-205">Middleware application 3</span></span></p></li>
<li><p><span data-ttu-id="778ea-206">ミドルウェアアプリケーションランタイム</span><span class="sxs-lookup"><span data-stu-id="778ea-206">Middleware application runtime</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="778ea-207">人事部の仮想アプリケーション接続グループ</span><span class="sxs-lookup"><span data-stu-id="778ea-207">Virtual application connection group for HR division</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="778ea-208">ミドルウェアアプリケーション5</span><span class="sxs-lookup"><span data-stu-id="778ea-208">Middleware application 5</span></span></p></li>
<li><p><span data-ttu-id="778ea-209">ミドルウェアアプリケーション6</span><span class="sxs-lookup"><span data-stu-id="778ea-209">Middleware application 6</span></span></p></li>
<li><p><span data-ttu-id="778ea-210">ミドルウェアアプリケーションランタイム</span><span class="sxs-lookup"><span data-stu-id="778ea-210">Middleware application runtime</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>
<p> </p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="778ea-211">を.</span><span class="sxs-lookup"><span data-stu-id="778ea-211">An.</span></span> <span data-ttu-id="778ea-212">exe ファイルと .exe ファイル</span><span class="sxs-lookup"><span data-stu-id="778ea-212">exe file and an .exe file</span></span></p></td>
<td align="left"><p><span data-ttu-id="778ea-213">別のアプリケーションに依存するアプリケーションを使用していて、運用効率、ライセンスの制限、またはロールアウトのタイムラインのために、パッケージを分離させたい。</span><span class="sxs-lookup"><span data-stu-id="778ea-213">You have an application that relies on another application, and you want to keep the packages separate for operational efficiencies, licensing restrictions, or rollout timelines.</span></span></p>
<p><strong><span data-ttu-id="778ea-214">例:</span><span class="sxs-lookup"><span data-stu-id="778ea-214">Example:</span></span></strong></p>
<p><span data-ttu-id="778ea-215">Microsoft Lync 2010 を展開する場合は、次の3つのパッケージを使用できます。</span><span class="sxs-lookup"><span data-stu-id="778ea-215">If you are deploying Microsoft Lync 2010, you can use three packages:</span></span></p>
<ul>
<li><p><span data-ttu-id="778ea-216">Microsoft 表紙</span><span class="sxs-lookup"><span data-stu-id="778ea-216">Microsoft Office2010</span></span></p></li>
<li><p><span data-ttu-id="778ea-217">Microsoft Communicator2007</span><span class="sxs-lookup"><span data-stu-id="778ea-217">Microsoft Communicator2007</span></span></p></li>
<li><p><span data-ttu-id="778ea-218">Microsoft Lync2010</span><span class="sxs-lookup"><span data-stu-id="778ea-218">Microsoft Lync2010</span></span></p></li>
</ul>
<p><span data-ttu-id="778ea-219">次の接続グループを使用して展開を管理できます。</span><span class="sxs-lookup"><span data-stu-id="778ea-219">You can manage the deployment using the following connection groups:</span></span></p>
<ul>
<li><p><span data-ttu-id="778ea-220">Microsoft 表紙と Microsoft Communicator2007</span><span class="sxs-lookup"><span data-stu-id="778ea-220">Microsoft Office2010 and Microsoft Communicator2007</span></span></p></li>
<li><p><span data-ttu-id="778ea-221">Microsoft 表紙と Microsoft Lync2010</span><span class="sxs-lookup"><span data-stu-id="778ea-221">Microsoft Office2010 and Microsoft Lync2010</span></span></p></li>
</ul>
<p><span data-ttu-id="778ea-222">展開が完了したら、新しい Microsoft 表紙 + Microsoft Lync2010 パッケージを1つ作成するか、別のパッケージとして保持して維持し、接続グループを使用して展開することができます。</span><span class="sxs-lookup"><span data-stu-id="778ea-222">When the deployment has completed, you can either create a single new Microsoft Office2010 + Microsoft Lync2010 package, or keep and maintain them as separate packages and deploy them by using a connection group.</span></span></p></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="778ea-223">関連トピック</span><span class="sxs-lookup"><span data-stu-id="778ea-223">Related topics</span></span>


[<span data-ttu-id="778ea-224">接続グループの管理</span><span class="sxs-lookup"><span data-stu-id="778ea-224">Managing Connection Groups</span></span>](managing-connection-groups51.md)

 

 





