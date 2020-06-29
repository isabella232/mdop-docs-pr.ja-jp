---
title: 管理コンソールを使用した APP-V 5.0 仮想アプリケーションの管理
description: 管理コンソールを使用した APP-V 5.0 仮想アプリケーションの管理
author: dansimp
ms.assetid: e9280dbd-782b-493a-b495-daab25247795
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 10/03/2016
ms.openlocfilehash: 7a71f7c0fd82f8ef9d1efd5b978591b6838a648a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814867"
---
# <span data-ttu-id="77ea1-103">管理コンソールを使用した APP-V 5.0 仮想アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="77ea1-103">Administering App-V 5.0 Virtual Applications by Using the Management Console</span></span>


<span data-ttu-id="77ea1-104">Microsoft Application Virtualization (App-v) 5.0 management server を使って、環境内のパッケージ、接続グループ、およびパッケージアクセスを管理します。</span><span class="sxs-lookup"><span data-stu-id="77ea1-104">Use the Microsoft Application Virtualization (App-V) 5.0 management server to manage packages, connection groups, and package access in your environment.</span></span> <span data-ttu-id="77ea1-105">サーバーは、アプリケーションアイコン、ショートカット、ファイルの種類の関連付けを、App-v 5.0 クライアントを実行する承認済みコンピューターに公開します。</span><span class="sxs-lookup"><span data-stu-id="77ea1-105">The server publishes application icons, shortcuts, and file type associations to authorized computers that run the App-V 5.0 client.</span></span> <span data-ttu-id="77ea1-106">1つまたは複数の管理サーバーは、通常、構成およびパッケージ情報用の共通データストアを共有します。</span><span class="sxs-lookup"><span data-stu-id="77ea1-106">One or more management servers typically share a common data store for configuration and package information.</span></span>

<span data-ttu-id="77ea1-107">管理サーバーは Active Directory ドメインサービス (AD DS) グループを使用して、ユーザーの承認を管理し、データベースとデータストアを管理するための SQL Server がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="77ea1-107">The management server uses Active Directory Domain Services (AD DS) groups to manage user authorization and has SQL Server installed to manage the database and data store.</span></span>

<span data-ttu-id="77ea1-108">管理サーバーではアプリケーションがオンデマンドでエンドユーザーにストリーミング配信されるため、これらのサーバーは、信頼性の高い高帯域幅の Lan を備えたシステム構成に最適です。</span><span class="sxs-lookup"><span data-stu-id="77ea1-108">Because the management servers stream applications to end users on demand, these servers are ideally suited for system configurations that have reliable, high-bandwidth LANs.</span></span> <span data-ttu-id="77ea1-109">管理サーバーは、次のコンポーネントで構成されています。</span><span class="sxs-lookup"><span data-stu-id="77ea1-109">The management server consists of the following components:</span></span>

-   <span data-ttu-id="77ea1-110">管理サーバー-管理サーバーを使用して、パッケージと接続グループを管理します。</span><span class="sxs-lookup"><span data-stu-id="77ea1-110">Management Server – Use the management server to manage packages and connection groups.</span></span>

-   <span data-ttu-id="77ea1-111">発行サーバー–公開サーバーを使用して、App-v 5.0 クライアントを実行しているコンピューターにパッケージを展開します。</span><span class="sxs-lookup"><span data-stu-id="77ea1-111">Publishing Server – Use the publishing server to deploy packages to computers that run the App-V 5.0 client.</span></span>

-   <span data-ttu-id="77ea1-112">管理データベース-管理データベースを使用して、パッケージアクセスを管理し、サーバーの同期を管理サーバーと公開します。</span><span class="sxs-lookup"><span data-stu-id="77ea1-112">Management Database - Use the management database to manage the package access and to publish the server’s synchronization with the management server.</span></span>

## <span data-ttu-id="77ea1-113">管理コンソールのタスク</span><span class="sxs-lookup"><span data-stu-id="77ea1-113">Management Console tasks</span></span>


<span data-ttu-id="77ea1-114">App-v 5.0 管理コンソールで実行できる一般的なタスクは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="77ea1-114">The most common tasks that you can perform with the App-V 5.0 Management console are:</span></span>

-   [<span data-ttu-id="77ea1-115">管理コンソールに接続する方法</span><span class="sxs-lookup"><span data-stu-id="77ea1-115">How to Connect to the Management Console</span></span>](how-to-connect-to-the-management-console-beta.md)

-   [<span data-ttu-id="77ea1-116">管理コンソールを使用してパッケージを追加またはアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="77ea1-116">How to Add or Upgrade Packages by Using the Management Console</span></span>](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)

-   [<span data-ttu-id="77ea1-117">管理コンソールを使用してパッケージへのアクセスを構成する方法</span><span class="sxs-lookup"><span data-stu-id="77ea1-117">How to Configure Access to Packages by Using the Management Console</span></span>](how-to-configure-access-to-packages-by-using-the-management-console-50.md)

-   [<span data-ttu-id="77ea1-118">管理コンソールを使用してパッケージを公開する方法</span><span class="sxs-lookup"><span data-stu-id="77ea1-118">How to Publish a Package by Using the Management Console</span></span>](how-to-publish-a-package-by-using-the-management-console-50.md)

-   [<span data-ttu-id="77ea1-119">管理コンソールでパッケージを削除する方法</span><span class="sxs-lookup"><span data-stu-id="77ea1-119">How to Delete a Package in the Management Console</span></span>](how-to-delete-a-package-in-the-management-console-beta.md)

-   [<span data-ttu-id="77ea1-120">管理コンソールを使用して管理者を追加または削除する方法</span><span class="sxs-lookup"><span data-stu-id="77ea1-120">How to Add or Remove an Administrator by Using the Management Console</span></span>](how-to-add-or-remove-an-administrator-by-using-the-management-console.md)

-   [<span data-ttu-id="77ea1-121">管理コンソールを使用して公開サーバーを登録および登録解除する方法</span><span class="sxs-lookup"><span data-stu-id="77ea1-121">How to Register and Unregister a Publishing Server by Using the Management Console</span></span>](how-to-register-and-unregister-a-publishing-server-by-using-the-management-console.md)

-   [<span data-ttu-id="77ea1-122">APP-V 5.0 管理コンソールを使用してカスタム構成ファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="77ea1-122">How to Create a Custom Configuration File by Using the App-V 5.0 Management Console</span></span>](how-to-create-a-custom-configuration-file-by-using-the-app-v-50-management-console.md)

-   [<span data-ttu-id="77ea1-123">管理コンソールを使用してアクセス権限と構成を別のバージョンのパッケージに転送する方法</span><span class="sxs-lookup"><span data-stu-id="77ea1-123">How to Transfer Access and Configurations to Another Version of a Package by Using the Management Console</span></span>](how-to-transfer-access-and-configurations-to-another-version-of-a-package-by-using-the-management-console.md)

-   [<span data-ttu-id="77ea1-124">管理コンソールを使用して特定の AD グループの仮想アプリケーションの拡張機能をカスタマイズする方法</span><span class="sxs-lookup"><span data-stu-id="77ea1-124">How to Customize Virtual Applications Extensions for a Specific AD Group by Using the Management Console</span></span>](how-to-customize-virtual-applications-extensions-for-a-specific-ad-group-by-using-the-management-console.md)

-   [<span data-ttu-id="77ea1-125">管理コンソールでアプリケーションと既定の仮想アプリケーションの拡張機能を構成する</span><span class="sxs-lookup"><span data-stu-id="77ea1-125">Configure Applications and Default Virtual Application Extensions in Management Console</span></span>](configure-applications-and-default-virtual-application-extensions-in-management-console.md)

<span data-ttu-id="77ea1-126">App-v 5.0 管理コンソールの主な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="77ea1-126">The main elements of the App-V 5.0 Management Console are:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="77ea1-127">[管理コンソール] タブ</span><span class="sxs-lookup"><span data-stu-id="77ea1-127">Management Console tab</span></span></th>
<th align="left"><span data-ttu-id="77ea1-128">説明</span><span class="sxs-lookup"><span data-stu-id="77ea1-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="77ea1-129">概要</span><span class="sxs-lookup"><span data-stu-id="77ea1-129">Overview</span></span></p></td>
<td align="left"><p></p>
<ul>
<li><p><strong><span data-ttu-id="77ea1-130">App-v </strong> - 5.0 sequencer の使用に関する一般的な情報を確認するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="77ea1-130">App-V Sequencer</strong> - Select this option to review general information about using the App-V 5.0 sequencer.</span></span></p></li>
<li><p><strong><span data-ttu-id="77ea1-131">[アプリケーションパッケージライブラリ </strong> ]: <strong> 管理コンソールの [パッケージ] ページを開くには、このオプションを選択し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="77ea1-131">Application Packages Library</strong> – Select this option to open the <strong>PACKAGES</strong> page of the Management Console.</span></span> <span data-ttu-id="77ea1-132">このページを使用して、サーバーに追加されたパッケージを確認します。</span><span class="sxs-lookup"><span data-stu-id="77ea1-132">Use this page to review packages that have been added to the server.</span></span> <span data-ttu-id="77ea1-133">また、接続グループを管理することも、パッケージを追加またはアップグレードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="77ea1-133">You can also manage the connection groups, as well as add or upgrade packages.</span></span></p></li>
<li><p><strong><span data-ttu-id="77ea1-134"></strong>[サーバー]: <strong> 管理コンソールの [サーバー] ページを開くには、このオプションを選択し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="77ea1-134">SERVERS</strong> – Select this option to open the <strong>SERVERS</strong> page of the Management Console.</span></span> <span data-ttu-id="77ea1-135">このページを使用して、App-v 5.0 インフラストラクチャに登録されているサーバーの一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="77ea1-135">Use this page to review the list of servers that have been registered with your App-V 5.0 infrastructure.</span></span></p></li>
<li><p><strong><span data-ttu-id="77ea1-136">クライアント </strong> – app-v 5.0 クライアントに関する一般的な情報を確認するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="77ea1-136">CLIENTS</strong> – Select this option to review general information about App-V 5.0 clients.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="77ea1-137">[パッケージ] タブ</span><span class="sxs-lookup"><span data-stu-id="77ea1-137">Packages tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="77ea1-138">パッケージ <strong> </strong> を追加またはアップグレードするには、[パッケージ] タブを使います。</span><span class="sxs-lookup"><span data-stu-id="77ea1-138">Use the <strong>PACKAGES</strong> tab to add or upgrade packages.</span></span> <span data-ttu-id="77ea1-139">[接続グループ] をクリックして、接続グループを管理することもでき <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="77ea1-139">You can also manage connection groups by clicking <strong>CONNECTION GROUPS</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="77ea1-140">[サーバー] タブ</span><span class="sxs-lookup"><span data-stu-id="77ea1-140">Servers tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="77ea1-141">[ <strong> サーバー </strong> ] タブを使って、新しいサーバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="77ea1-141">Use the <strong>SERVERS</strong> tab to register a new server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="77ea1-142">[管理者] タブ</span><span class="sxs-lookup"><span data-stu-id="77ea1-142">Administrators tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="77ea1-143">[ <strong> 管理者 </strong> ] タブを使用して、app-v 5.0 環境で管理者を登録、追加、または削除します。</span><span class="sxs-lookup"><span data-stu-id="77ea1-143">Use the <strong>ADMINISTRATORS</strong> tab to register, add, or remove administrators in your App-V 5.0 environment.</span></span></p></td>
</tr>
</tbody>
</table>

 






## <a href="" id="other-resources-for-this-app-v-5-0-deployment-"></a><span data-ttu-id="77ea1-144">この App-v 5.0 の展開に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="77ea1-144">Other resources for this App-V 5.0 deployment</span></span>


-   [<span data-ttu-id="77ea1-145">Microsoft Application Virtualization 5.0 管理者ガイド</span><span class="sxs-lookup"><span data-stu-id="77ea1-145">Microsoft Application Virtualization 5.0 Administrator's Guide</span></span>](microsoft-application-virtualization-50-administrators-guide.md)

-   [<span data-ttu-id="77ea1-146">APP-V 5.0 の操作</span><span class="sxs-lookup"><span data-stu-id="77ea1-146">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





