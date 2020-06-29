---
title: ユーザー単位で公開されるパッケージとグローバルに公開されるパッケージを含む接続グループを作成する方法
description: ユーザー単位で公開されるパッケージとグローバルに公開されるパッケージを含む接続グループを作成する方法
author: dansimp
ms.assetid: 82f7ea7f-7b14-4506-8940-fdcd6c3e117f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: c98981180133881909db17d19cb42771f94bd66a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814354"
---
# <span data-ttu-id="07cf2-103">ユーザー単位で公開されるパッケージとグローバルに公開されるパッケージを含む接続グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="07cf2-103">How to Create a Connection Group with User-Published and Globally Published Packages</span></span>
<span data-ttu-id="07cf2-104">次のいずれかの方法を使用して、ユーザーに公開されたパッケージとグローバルに公開されたパッケージの両方を含む、ユーザーの権利を持つ接続グループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="07cf2-104">You can create user-entitled connection groups that contain both user-published and globally published packages, using either of the following methods:</span></span>

-   [<span data-ttu-id="07cf2-105">PowerShell コマンドレットを使用してユーザーのタイトルの接続グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="07cf2-105">How to use PowerShell cmdlets to create the user-entitled connection groups</span></span>](#bkmk-posh-userentitled-cg)

-   [<span data-ttu-id="07cf2-106">App-v Server を使用してユーザーのタイトルの接続グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="07cf2-106">How to use the App-V Server to create the user-entitled connection groups</span></span>](#bkmk-appvserver-userentitled-cg)

**<span data-ttu-id="07cf2-107">始める前に知っておくべきこと:</span><span class="sxs-lookup"><span data-stu-id="07cf2-107">What to know before you start:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="07cf2-108">サポートされていないシナリオと潜在的な問題</span><span class="sxs-lookup"><span data-stu-id="07cf2-108">Unsupported scenarios and potential issues</span></span></th>
<th align="left"><span data-ttu-id="07cf2-109">結果</span><span class="sxs-lookup"><span data-stu-id="07cf2-109">Result</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="07cf2-110">グローバルタイトルの接続グループには、ユーザーに公開されたパッケージを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="07cf2-110">You cannot include user-published packages in globally entitled connection groups.</span></span></p></td>
<td align="left"><p><span data-ttu-id="07cf2-111">接続グループは失敗します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-111">The connection group will fail.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="07cf2-112">パッケージをグローバルに公開して、そのパッケージを省略可能な状態にしていないユーザー公開接続グループを作成した場合でも、別の接続グループでパッケージを使用している <strong> 場合でも、 &lt; &gt; </strong> パッケージの発行を取り下げるために、パッケージの発行を停止することができます。</span><span class="sxs-lookup"><span data-stu-id="07cf2-112">If you publish a package globally and then create a user-published connection group in which you’ve made that package non-optional, you can still run <strong>Unpublish-AppvClientPackage &lt;package&gt; -global</strong> to unpublish the package, even when that package is being used in another connection group.</span></span></p></td>
<td align="left"><p><span data-ttu-id="07cf2-113">他の接続グループがそのパッケージを使用している場合、そのパッケージはこれらの接続グループで失敗します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-113">If any other connection groups are using that package, the package will fail in those connection groups.</span></span></p>
<p><span data-ttu-id="07cf2-114">別の接続グループで使用されているオプション以外のパッケージを誤って非公開にしないようにするには、省略可能なパッケージ以外の接続グループを追跡することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="07cf2-114">To avoid inadvertently unpublishing a non-optional package that is being used in another connection group, we recommend that you track the connection groups in which you’ve used a non-optional package.</span></span></p></td>
</tr>
</tbody>
</table>

 
<a href="" id="bkmk-posh-userentitled-cg"></a>**<span data-ttu-id="07cf2-115">PowerShell コマンドレットを使用してユーザーのタイトルの接続グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="07cf2-115">How to use PowerShell cmdlets to create user-entitled connection groups</span></span>**

1.  <span data-ttu-id="07cf2-116">次のコマンドを使用して、パッケージを追加して公開します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-116">Add and publish packages by using the following commands:</span></span>

    **<span data-ttu-id="07cf2-117">AppvClientPackage Package1 \ _AppV \ _file \ _Path</span><span class="sxs-lookup"><span data-stu-id="07cf2-117">Add-AppvClientPackage Package1\_AppV\_file\_Path</span></span>**

    **<span data-ttu-id="07cf2-118">Add-AppvClientPackage Package2 \ _AppV \ _file \ _Path</span><span class="sxs-lookup"><span data-stu-id="07cf2-118">Add-AppvClientPackage Package2\_AppV\_file\_Path</span></span>**

    **<span data-ttu-id="07cf2-119">Publish-AppvClientPackage-PackageId Package1 \ _ID-VersionId Package1 \ _Version ID-グローバル</span><span class="sxs-lookup"><span data-stu-id="07cf2-119">Publish-AppvClientPackage -PackageId Package1\_ID-VersionId Package1\_Version ID -Global</span></span>**

    **<span data-ttu-id="07cf2-120">Publish-AppvClientPackage-PackageId Package2 \ _ID-VersionIdPackage2 \ _ID</span><span class="sxs-lookup"><span data-stu-id="07cf2-120">Publish-AppvClientPackage -PackageId Package2\_ID -VersionIdPackage2\_ID</span></span>**

2.  <span data-ttu-id="07cf2-121">接続グループの XML ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-121">Create the connection group XML file.</span></span> <span data-ttu-id="07cf2-122">詳細については、「[接続グループファイルについ](about-the-connection-group-file.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07cf2-122">For more information, see [About the Connection Group File](about-the-connection-group-file.md).</span></span>

3.  <span data-ttu-id="07cf2-123">次のコマンドを使用して、接続グループを追加して公開します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-123">Add and publish the connection group by using the following commands:</span></span>

    **<span data-ttu-id="07cf2-124">AppvClientConnectionGroup 接続 \ _Group \ _XML \ _file \ _Path</span><span class="sxs-lookup"><span data-stu-id="07cf2-124">Add-AppvClientConnectionGroup Connection\_Group\_XML\_file\_Path</span></span>**

    **<span data-ttu-id="07cf2-125">Enable-AppvClientConnectionGroup-GroupId CG \ _Group \ _ID-VersionId CG \ _Version \ _ID</span><span class="sxs-lookup"><span data-stu-id="07cf2-125">Enable-AppvClientConnectionGroup -GroupId CG\_Group\_ID-VersionId CG\_Version\_ID</span></span>**

<a href="" id="bkmk-appvserver-userentitled-cg"></a>**<span data-ttu-id="07cf2-126">App-v Server を使用して、ユーザーのタイトルの接続グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="07cf2-126">How to use the App-V Server to create user-entitled connection groups</span></span>**

1.  <span data-ttu-id="07cf2-127">App-v 5.0 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="07cf2-127">Open the App-V 5.0 Management Console.</span></span>

2.  <span data-ttu-id="07cf2-128">[「管理コンソールを使用してパッケージを公開する方法](how-to-publish-a-package-by-using-the-management-console-50.md)」の指示に従って、グローバルとユーザーにパッケージを公開します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-128">Follow the instructions in [How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-50.md) to publish packages globally and to the user.</span></span>

3.  <span data-ttu-id="07cf2-129">「接続グループを[作成](how-to-create-a-connection-group.md)して接続グループを作成する方法」の指示に従って、ユーザーに公開されたパッケージとグローバルに公開されたパッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-129">Follow the instructions in [How to Create a Connection Group](how-to-create-a-connection-group.md) to create the connection group, and add the user-published and globally published packages.</span></span>

    <span data-ttu-id="07cf2-130">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="07cf2-130">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="07cf2-131">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="07cf2-131">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="07cf2-132">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="07cf2-132">Got an App-V issue?</span></span>** <span data-ttu-id="07cf2-133">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-133">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="07cf2-134">関連トピック</span><span class="sxs-lookup"><span data-stu-id="07cf2-134">Related topics</span></span>


[<span data-ttu-id="07cf2-135">接続グループの管理</span><span class="sxs-lookup"><span data-stu-id="07cf2-135">Managing Connection Groups</span></span>](managing-connection-groups.md)

[<span data-ttu-id="07cf2-136">接続グループでオプション パッケージを使用する方法</span><span class="sxs-lookup"><span data-stu-id="07cf2-136">How to Use Optional Packages in Connection Groups</span></span>](how-to-use-optional-packages-in-connection-groups.md)

 

 





