---
title: PowerShell を使用してスタンドアロン コンピューターで接続グループを管理する方法
description: PowerShell を使用してスタンドアロン コンピューターで接続グループを管理する方法
author: dansimp
ms.assetid: b73ae74d-8a6f-4bb3-b1f2-0067c7bd5212
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 32dd4f9c5ad1ba4ae9e25246d5ec52a6363ef303
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813923"
---
# <span data-ttu-id="8c43f-103">PowerShell を使用してスタンドアロン コンピューターで接続グループを管理する方法</span><span class="sxs-lookup"><span data-stu-id="8c43f-103">How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell</span></span>


<span data-ttu-id="8c43f-104">App-v 接続グループでは、すべての仮想アプリケーションを1つの仮想環境内のパッケージの定義済みセットとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="8c43f-104">An App-V connection group allows you to run all the virtual applications as a defined set of packages in a single virtual environment.</span></span> <span data-ttu-id="8c43f-105">たとえば、個別のパッケージを使用してアプリケーションとそのプラグインを仮想化して、1つの接続グループで実行することができます。</span><span class="sxs-lookup"><span data-stu-id="8c43f-105">For example, you can virtualize an application and its plug-ins by using separate packages, but run them together in a single connection group.</span></span>

<span data-ttu-id="8c43f-106">接続グループの XML ファイルは、App-v クライアントをインストールしたコンピューターで実行される接続グループを定義します。</span><span class="sxs-lookup"><span data-stu-id="8c43f-106">A connection group XML file defines the connection group that runs on the computer where you’ve installed the App-V client.</span></span> <span data-ttu-id="8c43f-107">接続グループの XML ファイルとその構成方法については、「[接続グループファイルについ](about-the-connection-group-file.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c43f-107">For information about the connection group XML file and how to configure it, see [About the Connection Group File](about-the-connection-group-file.md).</span></span>

<span data-ttu-id="8c43f-108">このトピックでは、次の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="8c43f-108">This topic explains the following procedures:</span></span>

-   [<span data-ttu-id="8c43f-109">接続グループに App-v パッケージを追加して発行するには</span><span class="sxs-lookup"><span data-stu-id="8c43f-109">To add and publish the App-V packages in the connection group</span></span>](#bkmk-add-pub-pkgs-in-cg)

-   [<span data-ttu-id="8c43f-110">App-v クライアントで接続グループを追加して有効にするには</span><span class="sxs-lookup"><span data-stu-id="8c43f-110">To add and enable the connection group on the App-V client</span></span>](#bkmk-add-enable-cg-on-clt)

-   [<span data-ttu-id="8c43f-111">特定のユーザーに対して接続グループを有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="8c43f-111">To enable or disable a connection group for a specific user</span></span>](#bkmk-enable-cg-for-user-poshtopic)

-   [<span data-ttu-id="8c43f-112">管理者のみが接続グループを有効にできるようにするには</span><span class="sxs-lookup"><span data-stu-id="8c43f-112">To allow only administrators to enable connection groups</span></span>](#bkmk-admin-only-posh-topic-cg)

<a href="" id="bkmk-add-pub-pkgs-in-cg"></a>**<span data-ttu-id="8c43f-113">接続グループに App-v パッケージを追加して発行するには</span><span class="sxs-lookup"><span data-stu-id="8c43f-113">To add and publish the App-V packages in the connection group</span></span>**

1.  <span data-ttu-id="8c43f-114">App-v クライアントを実行しているコンピューターに app-v 5.0 パッケージを追加して発行するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="8c43f-114">To add and publish the App-V 5.0 packages to the computer running the App-V client, type the following command:</span></span>

    <span data-ttu-id="8c43f-115">Add-AppvClientPackage – path c:\\tmpstore\\quartfin.appv |公開-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="8c43f-115">Add-AppvClientPackage –path c:\\tmpstore\\quartfin.appv | Publish-AppvClientPackage</span></span>

2.  <span data-ttu-id="8c43f-116">接続グループ内の各パッケージについて、**手順 1**を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="8c43f-116">Repeat **step 1** of this procedure for each package in the connection group.</span></span>

<a href="" id="bkmk-add-enable-cg-on-clt"></a>**<span data-ttu-id="8c43f-117">App-v クライアントで接続グループを追加して有効にするには</span><span class="sxs-lookup"><span data-stu-id="8c43f-117">To add and enable the connection group on the App-V client</span></span>**

1.  <span data-ttu-id="8c43f-118">次のコマンドを入力して、接続グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="8c43f-118">Add the connection group by typing the following command:</span></span>

    <span data-ttu-id="8c43f-119">Add-AppvClientConnectionGroup – path c:\\tmpstore\\financ.xml</span><span class="sxs-lookup"><span data-stu-id="8c43f-119">Add-AppvClientConnectionGroup –path c:\\tmpstore\\financ.xml</span></span>

2.  <span data-ttu-id="8c43f-120">次のコマンドを入力して、接続グループを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8c43f-120">Enable the connection group by typing the following command:</span></span>

    <span data-ttu-id="8c43f-121">Enable-AppvClientConnectionGroup – name "財務アプリケーション"</span><span class="sxs-lookup"><span data-stu-id="8c43f-121">Enable-AppvClientConnectionGroup –name “Financial Applications”</span></span>

    <span data-ttu-id="8c43f-122">メンバーパッケージ内の仮想アプリケーションがターゲットコンピューターで実行されると、接続グループの仮想環境内で実行され、接続グループ内の他のパッケージ内のすべての仮想アプリケーションで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8c43f-122">When any virtual applications that are in the member packages are run on the target computer, they will run inside the connection group’s virtual environment and will be available to all the virtual applications in the other packages in the connection group.</span></span>

<a href="" id="bkmk-enable-cg-for-user-poshtopic"></a>**<span data-ttu-id="8c43f-123">特定のユーザーに対して接続グループを有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="8c43f-123">To enable or disable a connection group for a specific user</span></span>**

1.  <span data-ttu-id="8c43f-124">パラメーターの説明と要件を確認します。</span><span class="sxs-lookup"><span data-stu-id="8c43f-124">Review the parameter description and requirements:</span></span>

    -   <span data-ttu-id="8c43f-125">このパラメーターを使用すると、管理者は特定のユーザーに対して接続グループを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="8c43f-125">The parameter enables an administrator to enable or disable a connection group for a specific user.</span></span>

    -   <span data-ttu-id="8c43f-126">このパラメーターを使用するには、App-v 5.0 SP2 ホットフィックスパッケージ5以降を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c43f-126">You must use App-V 5.0 SP2 Hotfix Package 5 or later to use this parameter.</span></span>

    -   <span data-ttu-id="8c43f-127">このコマンドレットは、ユーザーまたは管理者セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="8c43f-127">You can run this cmdlet from the user or administrator session.</span></span>

    -   <span data-ttu-id="8c43f-128">パラメーターを使用するには、管理者の資格情報を使ってログインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c43f-128">You must be logged in with administrative credentials to use the parameter.</span></span>

    -   <span data-ttu-id="8c43f-129">エンドユーザーはログインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c43f-129">The end user must be logged in.</span></span>

    -   <span data-ttu-id="8c43f-130">エンドユーザーのセキュリティ識別子 (SID) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c43f-130">You must provide the end user’s security identifier (SID).</span></span>

2.  <span data-ttu-id="8c43f-131">次のコマンドレットを使用して、オプションの [ **usersid]** パラメーターを追加します。ここで、 **-UserSID**はエンドユーザーのセキュリティ識別子 (SID) を表します。</span><span class="sxs-lookup"><span data-stu-id="8c43f-131">Use the following cmdlets, and add the optional **–UserSID** parameter, where **-UserSID** represents the end user’s security identifier (SID):</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="8c43f-132">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="8c43f-132">Cmdlet</span></span></th>
    <th align="left"><span data-ttu-id="8c43f-133">例</span><span class="sxs-lookup"><span data-stu-id="8c43f-133">Examples</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="8c43f-134">Enable-AppVClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="8c43f-134">Enable-AppVClientConnectionGroup</span></span></p></td>
    <td align="left"><p><span data-ttu-id="8c43f-135">Enable-AppVClientConnectionGroup "ConnectionGroupA"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</span><span class="sxs-lookup"><span data-stu-id="8c43f-135">Enable-AppVClientConnectionGroup “ConnectionGroupA” -UserSID S-1-2-34-56789012-3456789012-345678901-2345</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="8c43f-136">Disable-AppVClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="8c43f-136">Disable -AppVClientConnectionGroup</span></span></p></td>
    <td align="left"><p><span data-ttu-id="8c43f-137">Disable-AppVClientConnectionGroup "ConnectionGroupA"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</span><span class="sxs-lookup"><span data-stu-id="8c43f-137">Disable -AppVClientConnectionGroup “ConnectionGroupA” -UserSID S-1-2-34-56789012-3456789012-345678901-2345</span></span></p></td>
    </tr>
    </tbody>
    </table>

<a href="" id="bkmk-admin-only-posh-topic-cg"></a>**<span data-ttu-id="8c43f-138">管理者のみが接続グループを有効にできるようにするには</span><span class="sxs-lookup"><span data-stu-id="8c43f-138">To allow only administrators to enable connection groups</span></span>**

1.  <span data-ttu-id="8c43f-139">このコマンドレットを使用するための説明と要件を確認します。</span><span class="sxs-lookup"><span data-stu-id="8c43f-139">Review the description and requirement for using this cmdlet:</span></span>

    -   <span data-ttu-id="8c43f-140">このコマンドレットとパラメーターを使用して、管理者 (エンドユーザーではない) だけが接続グループを有効または無効にできるように、App-v クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="8c43f-140">Use this cmdlet and parameter to configure the App-V client to allow only administrators (not end users) to enable or disable connection groups.</span></span>

    -   <span data-ttu-id="8c43f-141">このコマンドレットを使用するには、少なくとも App-v 5.0 SP3 を使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c43f-141">You must be using at least App-V 5.0 SP3 to use this cmdlet.</span></span>

2.  <span data-ttu-id="8c43f-142">次のコマンドレットとパラメーターを実行します。</span><span class="sxs-lookup"><span data-stu-id="8c43f-142">Run the following cmdlet and parameter:</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="8c43f-143">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="8c43f-143">Cmdlet</span></span></th>
    <th align="left"><span data-ttu-id="8c43f-144">パラメーターと値</span><span class="sxs-lookup"><span data-stu-id="8c43f-144">Parameter and values</span></span></th>
    <th align="left"><span data-ttu-id="8c43f-145">例</span><span class="sxs-lookup"><span data-stu-id="8c43f-145">Example</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="8c43f-146">Set-AppvClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="8c43f-146">Set-AppvClientConfiguration</span></span></p></td>
    <td align="left"><p><span data-ttu-id="8c43f-147">– RequirePublishAsAdmin</span><span class="sxs-lookup"><span data-stu-id="8c43f-147">–RequirePublishAsAdmin</span></span></p>
    <ul>
    <li><p><span data-ttu-id="8c43f-148">0-偽</span><span class="sxs-lookup"><span data-stu-id="8c43f-148">0 - False</span></span></p></li>
    <li><p><span data-ttu-id="8c43f-149">1-True</span><span class="sxs-lookup"><span data-stu-id="8c43f-149">1 - True</span></span></p></li>
    </ul></td>
    <td align="left"><p><span data-ttu-id="8c43f-150">Set-AppvClientConfiguration – RequirePublishAsAdmin1</span><span class="sxs-lookup"><span data-stu-id="8c43f-150">Set-AppvClientConfiguration –RequirePublishAsAdmin1</span></span></p></td>
    </tr>
    </tbody>
    </table>

    <span data-ttu-id="8c43f-151">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="8c43f-151">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="8c43f-152">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="8c43f-152">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="8c43f-153">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="8c43f-153">Got an App-V issue?</span></span>** <span data-ttu-id="8c43f-154">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="8c43f-154">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="8c43f-155">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8c43f-155">Related topics</span></span>


[<span data-ttu-id="8c43f-156">APP-V 5.0 の操作</span><span class="sxs-lookup"><span data-stu-id="8c43f-156">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

[<span data-ttu-id="8c43f-157">PowerShell を使用した App-V の管理</span><span class="sxs-lookup"><span data-stu-id="8c43f-157">Administering App-V by Using PowerShell</span></span>](administering-app-v-by-using-powershell.md)

 

 





