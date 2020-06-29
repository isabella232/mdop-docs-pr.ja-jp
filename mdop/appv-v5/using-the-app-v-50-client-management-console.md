---
title: APP-V 5.0 Client 管理コンソールの使用
description: APP-V 5.0 Client 管理コンソールの使用
author: dansimp
ms.assetid: 36398307-57dd-40f3-9d4f-b09f44fd37c3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8541e5bc59334b9074a3940dad7cdf0114205d4c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813259"
---
# <span data-ttu-id="a3537-103">APP-V 5.0 Client 管理コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="a3537-103">Using the App-V 5.0 Client Management Console</span></span>


<span data-ttu-id="a3537-104">このトピックでは、App-v 5.0 クライアントの構成と管理を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3537-104">This topic provides information about how you can configure and manage the App-V 5.0 client.</span></span>

## <span data-ttu-id="a3537-105">App-v 5.0 クライアント構成を変更する</span><span class="sxs-lookup"><span data-stu-id="a3537-105">Modify App-V 5.0 client configuration</span></span>


<span data-ttu-id="a3537-106">App-v 5.0 クライアントには、環境でクライアントを実行する方法を決定するために構成可能な設定が関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="a3537-106">The App-V 5.0 client has associated settings that can be configured to determine how the client will run in your environment.</span></span> <span data-ttu-id="a3537-107">クライアントを実行するコンピューター、または PowerShell またはグループポリシーを使って、これらの設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="a3537-107">You can manage these settings on the computer that runs the client or by using PowerShell or Group Policy.</span></span> <span data-ttu-id="a3537-108">PowerShell またはグループポリシー構成を使用してクライアントを変更する方法の詳細については、「 [Powershell を使用してクライアント構成を変更する方法](how-to-modify-client-configuration-by-using-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3537-108">For more information about how to modify the client using PowerShell or Group Policy configuration see, [How to Modify Client Configuration by Using PowerShell](how-to-modify-client-configuration-by-using-powershell.md).</span></span>

## <a href="" id="the-app-v-5-0-client-management-console-"></a><span data-ttu-id="a3537-109">App-v 5.0 クライアント管理コンソール</span><span class="sxs-lookup"><span data-stu-id="a3537-109">The App-V 5.0 client management console</span></span>


<span data-ttu-id="a3537-110">App-v 5.0 クライアントに関する情報を取得したり、App-v 5.0 クライアント管理コンソールを使用して特定のタスクを実行したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a3537-110">You can obtain information about the App-V 5.0 client or perform specific tasks by using the App-V 5.0 client management console.</span></span> <span data-ttu-id="a3537-111">クライアント管理コンソールで実行できるタスクの多くは、PowerShell を使用して実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="a3537-111">Many of the tasks that you can perform in the client management console you can also perform by using PowerShell.</span></span> <span data-ttu-id="a3537-112">各アクションに関連付けられている PowerShell コマンドレットも、次の表に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3537-112">The associated PowerShell cmdlets for each action are also displayed in the following table.</span></span> <span data-ttu-id="a3537-113">PowerShell の使い方の詳細については、「 [Powershell を使用](administering-app-v-by-using-powershell.md)した App-v の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3537-113">For more information about how to use PowerShell, see [Administering App-V by Using PowerShell](administering-app-v-by-using-powershell.md).</span></span>

<span data-ttu-id="a3537-114">クライアント管理コンソールには、次に示すメインタブがあります。</span><span class="sxs-lookup"><span data-stu-id="a3537-114">The client management console contains the following described main tabs.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a3537-115">タブ</span><span class="sxs-lookup"><span data-stu-id="a3537-115">Tab</span></span></th>
<th align="left"><span data-ttu-id="a3537-116">説明</span><span class="sxs-lookup"><span data-stu-id="a3537-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a3537-117">概要</span><span class="sxs-lookup"><span data-stu-id="a3537-117">Overview</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3537-118">[ <strong> 概要 </strong> ] タブには、次の要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a3537-118">The <strong>Overview</strong> tab contains the following elements:</span></span></p>
<ul>
<li><p><span data-ttu-id="a3537-119">更新-[更新] タイルを使用して、 <strong> </strong> 仮想化されたアプリケーションを更新するか、仮想化された新しいパッケージを受信します。</span><span class="sxs-lookup"><span data-stu-id="a3537-119">Update – Use the <strong>Update</strong> tile to refresh a virtualized application or to receive a new virtualized package.</span></span></p>
<p><span data-ttu-id="a3537-120">最後の更新には、 <strong> </strong> 仮想化されたパッケージの現在のバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3537-120">The <strong>Last Refresh</strong> displays the current version of the virtualized package.</span></span></p></li>
<li><p><span data-ttu-id="a3537-121">すべての仮想アプリケーションをダウンロード- <strong> ダウンロードタイルを使用して、 </strong> 現在のユーザーにプロビジョニングされたすべてのパッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a3537-121">Download all virtual applications – Use the <strong>Download</strong> tile to download all of the packages provisioned to the current user.</span></span></p>
<p><span data-ttu-id="a3537-122">(関連付けられている PowerShell コマンドレット: <strong>Mount-AppvClientPackage </strong> )</span><span class="sxs-lookup"><span data-stu-id="a3537-122">(Associated PowerShell cmdlet: <strong>Mount-AppvClientPackage</strong>)</span></span></p>
<p></p></li>
<li><p><span data-ttu-id="a3537-123">オフライン作業–このタイルを使用して、すべての自動および手動による仮想アプリケーションの更新を許可しません。</span><span class="sxs-lookup"><span data-stu-id="a3537-123">Work Offline – Use this tile to disallow all automatic and manual virtual application updates.</span></span></p>
<p><span data-ttu-id="a3537-124">(関連付けられている PowerShell コマンドレット: <strong>Set-AppvPublishServer – UserRefreshEnabled – GlobalRefreshEnabled </strong></span><span class="sxs-lookup"><span data-stu-id="a3537-124">(Associated PowerShell cmdlet: <strong>Set-AppvPublishServer –UserRefreshEnabled –GlobalRefreshEnabled</strong>)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a3537-125">仮想アプリ</span><span class="sxs-lookup"><span data-stu-id="a3537-125">Virtual Apps</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3537-126">[ <strong> 仮想アプリ </strong> ] タブには、ユーザーに公開されたすべてのパッケージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3537-126">The <strong>VIRTUAL APPS</strong> tab displays all of the packages that have been published to the user.</span></span> <span data-ttu-id="a3537-127">特定のパッケージをクリックすると、そのパッケージに含まれているすべてのアプリケーションを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="a3537-127">You can also click a specific package and see all of the applications that are part of that package.</span></span> <span data-ttu-id="a3537-128">現在使用されているパッケージについての情報と、各パッケージがどの程度コンピューターにダウンロードされているかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3537-128">This displays information about packages that are currently in use and how much of each package has been downloaded to the computer.</span></span> <span data-ttu-id="a3537-129">パッケージのダウンロードを開始および停止することもできます。</span><span class="sxs-lookup"><span data-stu-id="a3537-129">You can also start and stop package downloads.</span></span> <span data-ttu-id="a3537-130">さらに、ユーザーの状態を修復することもできます。</span><span class="sxs-lookup"><span data-stu-id="a3537-130">Additionally, you can repair the user state.</span></span> <span data-ttu-id="a3537-131">修復すると、パッケージに関連付けられているすべてのユーザーデータが削除されます。</span><span class="sxs-lookup"><span data-stu-id="a3537-131">A repair will delete all user data that is associated with a package.</span></span></p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a3537-132">アプリ接続グループ</span><span class="sxs-lookup"><span data-stu-id="a3537-132">App Connection Groups</span></span></p></td>
<td align="left"><p><span data-ttu-id="a3537-133">[ <strong> アプリ接続グループ </strong> ] タブには、現在のユーザーが利用できるすべての接続グループが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3537-133">The <strong>APP CONNECTION GROUPS</strong> tab displays all of the connection groups that are available to the current user.</span></span> <span data-ttu-id="a3537-134">特定の接続グループをクリックすると、選択したグループに含まれるすべてのパッケージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3537-134">Click a specific connection group to see all of the packages that are part of the selected group.</span></span> <span data-ttu-id="a3537-135">既に使用されている接続グループと、コンピューターにダウンロードされた接続グループの内容に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3537-135">This displays information about connection groups that are already in use and how much of the connection group contents have been downloaded to the computer.</span></span> <span data-ttu-id="a3537-136">さらに、接続グループのダウンロードを開始して停止することもできます。</span><span class="sxs-lookup"><span data-stu-id="a3537-136">Additionally, you can start and stop connection group downloads.</span></span> <span data-ttu-id="a3537-137">このセクションを使って修復を開始できます。</span><span class="sxs-lookup"><span data-stu-id="a3537-137">You can use this section to initiate a repair.</span></span> <span data-ttu-id="a3537-138">修復すると、接続グループに関連付けられているユーザーの状態がすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="a3537-138">A repair will remove all of the user state that is associated a connection group.</span></span></p>
<p><span data-ttu-id="a3537-139">(関連付けられている PowerShell コマンドレット: ダウンロード- <strong>Mount-AppvClientConnectionGroup </strong> 。</span><span class="sxs-lookup"><span data-stu-id="a3537-139">(Associated PowerShell cmdlets: Download - <strong>Mount-AppvClientConnectionGroup</strong>.</span></span> <span data-ttu-id="a3537-140">修復- <strong> AppvClientConnectionGroup </strong> )</span><span class="sxs-lookup"><span data-stu-id="a3537-140">Repair -<strong>AppvClientConnectionGroup</strong>.)</span></span></p>
<p></p></td>
</tr>
</tbody>
</table>

 

[<span data-ttu-id="a3537-141">Client 管理コンソールにアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="a3537-141">How to Access the Client Management Console</span></span>](how-to-access-the-client-management-console.md)

[<span data-ttu-id="a3537-142">公開サーバーからパッケージと接続グループの更新を受信するように Client を構成する方法</span><span class="sxs-lookup"><span data-stu-id="a3537-142">How to Configure the Client to Receive Package and Connection Groups Updates From the Publishing Server</span></span>](how-to-configure-the-client-to-receive-package-and-connection-groups-updates-from-the-publishing-server-beta.md)






## <span data-ttu-id="a3537-143">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a3537-143">Related topics</span></span>


[<span data-ttu-id="a3537-144">APP-V 5.0 の操作</span><span class="sxs-lookup"><span data-stu-id="a3537-144">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





