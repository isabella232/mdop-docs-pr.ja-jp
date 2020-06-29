---
title: パッケージのバージョンを無視するように接続グループを構成する方法
description: パッケージのバージョンを無視するように接続グループを構成する方法
author: dansimp
ms.assetid: 6ebc1bff-d190-4f4c-a6da-e09a4cca7874
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b64d1938419aef184c5df667bf71b8157de0450a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813962"
---
# <span data-ttu-id="2580c-103">パッケージのバージョンを無視するように接続グループを構成する方法</span><span class="sxs-lookup"><span data-stu-id="2580c-103">How to Make a Connection Group Ignore the Package Version</span></span>


<span data-ttu-id="2580c-104">Microsoft Application Virtualization (App-v) 5.0 SP3 では、任意のバージョンのパッケージを使用するように接続グループを構成することができます。これにより、パッケージのアップグレードが簡素化され、作成する必要がある接続グループの数が少なくなります。</span><span class="sxs-lookup"><span data-stu-id="2580c-104">Microsoft Application Virtualization (App-V) 5.0 SP3 enables you to configure a connection group to use any version of a package, which simplifies package upgrades and reduces the number of connection groups you need to create.</span></span>

<span data-ttu-id="2580c-105">以前のバージョンの App-v でパッケージをアップグレードするには、接続グループの無効化、接続グループの XML 定義ファイルの変更など、いくつかの手順を実行する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="2580c-105">To upgrade a package in earlier versions of App-V, you had to perform several steps, including disabling the connection group and modifying the connection group’s XML definition file.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2580c-106">タスクの説明 (app-v 5.0 SP3 の場合)</span><span class="sxs-lookup"><span data-stu-id="2580c-106">Task description with App-V 5.0 SP3</span></span></th>
<th align="left"><span data-ttu-id="2580c-107">App-v 5.0 SP3 でタスクを実行する方法</span><span class="sxs-lookup"><span data-stu-id="2580c-107">How to perform the task with App-V 5.0 SP3</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2580c-108">接続グループを構成して、任意のバージョンのパッケージを受け入れることができます。これにより、接続グループを無効にすることなくパッケージをアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="2580c-108">You can configure a connection group to accept any version of a package, which enables you to upgrade the package without having to disable the connection group.</span></span></p>
<p><strong><span data-ttu-id="2580c-109">機能のしくみ:</span><span class="sxs-lookup"><span data-stu-id="2580c-109">How the feature works:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="2580c-110">接続グループが複数のバージョンのパッケージにアクセスできる場合は、最新バージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2580c-110">If the connection group has access to multiple versions of a package, the latest version is used.</span></span></p></li>
<li><p><span data-ttu-id="2580c-111">接続グループに、バージョンが正しくないオプションのパッケージが含まれている場合、そのパッケージは無視され、接続グループの仮想環境の作成がブロックされることはありません。</span><span class="sxs-lookup"><span data-stu-id="2580c-111">If the connection group contains an optional package that has an incorrect version, the package is ignored and won’t block the connection group’s virtual environment from being created.</span></span></p></li>
<li><p><span data-ttu-id="2580c-112">接続グループに、バージョンが正しくないオプションのパッケージが含まれている場合、接続グループの仮想環境を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="2580c-112">If the connection group contains a non-optional package that has an incorrect version, the connection group’s virtual environment cannot be created.</span></span></p></li>
</ul></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2580c-113">メソッド</span><span class="sxs-lookup"><span data-stu-id="2580c-113">Method</span></span></th>
<th align="left"><span data-ttu-id="2580c-114">手順</span><span class="sxs-lookup"><span data-stu-id="2580c-114">Steps</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2580c-115">App-v Server –管理コンソール</span><span class="sxs-lookup"><span data-stu-id="2580c-115">App-V Server – Management Console</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="2580c-116">管理コンソールで、[パッケージ接続グループ] を選択し <strong> </strong> &gt; <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="2580c-116">In the Management Console, select <strong>PACKAGES</strong> &gt; <strong>CONNECTION GROUPS</strong>.</span></span></p></li>
<li><p><span data-ttu-id="2580c-117">接続グループライブラリから適切な接続グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="2580c-117">Select the correct connection group from the Connection Groups library.</span></span></p></li>
<li><p><span data-ttu-id="2580c-118">[ <strong> </strong> 接続されているパッケージ] ウィンドウで [編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2580c-118">Click <strong>EDIT</strong> in the CONNECTED PACKAGES pane.</span></span></p></li>
<li><p><span data-ttu-id="2580c-119"><strong>パッケージ名の横にある [すべてのバージョンを使用する] </strong> チェックボックスをオンにし、[適用] をクリックし <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="2580c-119">Select <strong>Use Any Version</strong> check box next to the package name, and click <strong>Apply</strong>.</span></span></p></li>
</ol>
<p><span data-ttu-id="2580c-120">パッケージの追加またはアップグレードの詳細については、「 <a href="how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md" data-raw-source="[How to Add or Upgrade Packages by Using the Management Console](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)"> 管理コンソールを使用してパッケージを追加またはアップグレードする方法」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="2580c-120">For more about adding or upgrading packages, see <a href="how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md" data-raw-source="[How to Add or Upgrade Packages by Using the Management Console](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)">How to Add or Upgrade Packages by Using the Management Console</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2580c-121">スタンドアロンコンピューター上の app-v クライアント</span><span class="sxs-lookup"><span data-stu-id="2580c-121">App-V Client on a Stand-alone computer</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="2580c-122">接続グループの XML ドキュメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="2580c-122">Create the connection group XML document.</span></span></p></li>
<li><p><span data-ttu-id="2580c-123">パッケージをアップグレードするには、 <strong> パッケージ </strong> タグ属性 <strong> VersionID </strong> をアスタリスク () に設定し <strong>\*</strong> ます。</span><span class="sxs-lookup"><span data-stu-id="2580c-123">For the package to be upgraded, set the <strong>Package</strong> tag attribute <strong>VersionID</strong> to an asterisk (<strong>\*</strong>).</span></span></p></li>
<li><p><span data-ttu-id="2580c-124">次のコマンドレットを使用して、接続グループを追加し、接続グループの XML ドキュメントへのパスを含めます。</span><span class="sxs-lookup"><span data-stu-id="2580c-124">Use the following cmdlet to add the connection group, and include the path to the connection group XML document:</span></span></p>
<p><strong><span data-ttu-id="2580c-125">Add-AppvClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="2580c-125">Add-AppvClientConnectionGroup</span></span></strong></p></li>
<li><p><span data-ttu-id="2580c-126">パッケージをアップグレードする場合は、次のコマンドレットを使用して、古いパッケージを削除し、アップグレードされたパッケージを追加して、アップグレードされたパッケージを公開します。</span><span class="sxs-lookup"><span data-stu-id="2580c-126">When you upgrade a package, use the following cmdlets to remove the old package, add the upgraded package, and publish the upgraded package:</span></span></p>
<ul>
<li><p><span data-ttu-id="2580c-127">RemoveAppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="2580c-127">RemoveAppvClientPackage</span></span></p></li>
<li><p><span data-ttu-id="2580c-128">Add-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="2580c-128">Add-AppvClientPackage</span></span></p></li>
<li><p><span data-ttu-id="2580c-129">公開-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="2580c-129">Publish-AppvClientPackage</span></span></p></li>
</ul></li>
</ol>
<p><span data-ttu-id="2580c-130">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2580c-130">For more information, see:</span></span></p>
<ul>
<li><p><span data-ttu-id="2580c-131">このセクションの XML ファイルの例 ( <strong> オプションのパッケージを含む接続グループの xml ファイル) </strong> : <a href="how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional)"> 接続グループでオプションパッケージを使用する方法</span><span class="sxs-lookup"><span data-stu-id="2580c-131">The example XML file, <strong>Connection group XML file with optional packages</strong>, in this section: <a href="how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional)">How to Use Optional Packages in Connection Groups</span></span></a></p></li>
<li><p><a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md)"><span data-ttu-id="2580c-132">PowerShell を使用してスタンドアロン コンピューターで実行されている App-V 5.0 パッケージを管理する方法</span><span class="sxs-lookup"><span data-stu-id="2580c-132">How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span></a></p></li>
</ul></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="2580c-133">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2580c-133">Related topics</span></span>


[<span data-ttu-id="2580c-134">接続グループの管理</span><span class="sxs-lookup"><span data-stu-id="2580c-134">Managing Connection Groups</span></span>](managing-connection-groups.md)

 

 





