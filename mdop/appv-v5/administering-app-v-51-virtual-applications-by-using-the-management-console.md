---
title: 管理コンソールを使用した APP-V 5.1 仮想アプリケーションの管理
description: 管理コンソールを使用した APP-V 5.1 仮想アプリケーションの管理
author: dansimp
ms.assetid: a4d078aa-ec54-4fa4-9463-bfb3b971d724
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 63ec965519bedef08b09c961dc5d1c90e1d8d694
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814866"
---
# <span data-ttu-id="7857b-103">管理コンソールを使用した APP-V 5.1 仮想アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="7857b-103">Administering App-V 5.1 Virtual Applications by Using the Management Console</span></span>


<span data-ttu-id="7857b-104">Microsoft Application Virtualization (App-v) 5.1 management server を使って、環境内のパッケージ、接続グループ、およびパッケージアクセスを管理します。</span><span class="sxs-lookup"><span data-stu-id="7857b-104">Use the Microsoft Application Virtualization (App-V) 5.1 management server to manage packages, connection groups, and package access in your environment.</span></span> <span data-ttu-id="7857b-105">サーバーは、アプリケーションアイコン、ショートカット、ファイルの種類の関連付けを、App-v 5.1 クライアントを実行する承認済みコンピューターに公開します。</span><span class="sxs-lookup"><span data-stu-id="7857b-105">The server publishes application icons, shortcuts, and file type associations to authorized computers that run the App-V 5.1 client.</span></span> <span data-ttu-id="7857b-106">1つまたは複数の管理サーバーは、通常、構成およびパッケージ情報用の共通データストアを共有します。</span><span class="sxs-lookup"><span data-stu-id="7857b-106">One or more management servers typically share a common data store for configuration and package information.</span></span>

<span data-ttu-id="7857b-107">管理サーバーは Active Directory ドメインサービス (AD DS) グループを使用して、ユーザーの承認を管理し、データベースとデータストアを管理するための SQL Server がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="7857b-107">The management server uses Active Directory Domain Services (AD DS) groups to manage user authorization and has SQL Server installed to manage the database and data store.</span></span>

<span data-ttu-id="7857b-108">管理サーバーではアプリケーションがオンデマンドでエンドユーザーにストリーミング配信されるため、これらのサーバーは、信頼性の高い高帯域幅の Lan を備えたシステム構成に最適です。</span><span class="sxs-lookup"><span data-stu-id="7857b-108">Because the management servers stream applications to end users on demand, these servers are ideally suited for system configurations that have reliable, high-bandwidth LANs.</span></span> <span data-ttu-id="7857b-109">管理サーバーは、次のコンポーネントで構成されています。</span><span class="sxs-lookup"><span data-stu-id="7857b-109">The management server consists of the following components:</span></span>

-   <span data-ttu-id="7857b-110">管理サーバー-管理サーバーを使用して、パッケージと接続グループを管理します。</span><span class="sxs-lookup"><span data-stu-id="7857b-110">Management Server – Use the management server to manage packages and connection groups.</span></span>

-   <span data-ttu-id="7857b-111">発行サーバー–公開サーバーを使用して、App-v 5.1 クライアントを実行しているコンピューターにパッケージを展開します。</span><span class="sxs-lookup"><span data-stu-id="7857b-111">Publishing Server – Use the publishing server to deploy packages to computers that run the App-V 5.1 client.</span></span>

-   <span data-ttu-id="7857b-112">管理データベース-管理データベースを使用して、パッケージアクセスを管理し、サーバーの同期を管理サーバーと公開します。</span><span class="sxs-lookup"><span data-stu-id="7857b-112">Management Database - Use the management database to manage the package access and to publish the server’s synchronization with the management server.</span></span>

## <span data-ttu-id="7857b-113">管理コンソールのタスク</span><span class="sxs-lookup"><span data-stu-id="7857b-113">Management Console tasks</span></span>


<span data-ttu-id="7857b-114">App-v 5.1 管理コンソールで実行できる一般的なタスクは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7857b-114">The most common tasks that you can perform with the App-V 5.1 Management console are:</span></span>

-   [<span data-ttu-id="7857b-115">管理コンソールに接続する方法</span><span class="sxs-lookup"><span data-stu-id="7857b-115">How to Connect to the Management Console</span></span>](how-to-connect-to-the-management-console-51.md)

-   [<span data-ttu-id="7857b-116">管理コンソールを使用してパッケージを追加またはアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="7857b-116">How to Add or Upgrade Packages by Using the Management Console</span></span>](how-to-add-or-upgrade-packages-by-using-the-management-console-51-gb18030.md)

-   [<span data-ttu-id="7857b-117">管理コンソールを使用してパッケージへのアクセスを構成する方法</span><span class="sxs-lookup"><span data-stu-id="7857b-117">How to Configure Access to Packages by Using the Management Console</span></span>](how-to-configure-access-to-packages-by-using-the-management-console-51.md)

-   [<span data-ttu-id="7857b-118">管理コンソールを使用してパッケージを公開する方法</span><span class="sxs-lookup"><span data-stu-id="7857b-118">How to Publish a Package by Using the Management Console</span></span>](how-to-publish-a-package-by-using-the-management-console-51.md)

-   [<span data-ttu-id="7857b-119">管理コンソールでパッケージを削除する方法</span><span class="sxs-lookup"><span data-stu-id="7857b-119">How to Delete a Package in the Management Console</span></span>](how-to-delete-a-package-in-the-management-console-51.md)

-   [<span data-ttu-id="7857b-120">管理コンソールを使用して管理者を追加または削除する方法</span><span class="sxs-lookup"><span data-stu-id="7857b-120">How to Add or Remove an Administrator by Using the Management Console</span></span>](how-to-add-or-remove-an-administrator-by-using-the-management-console51.md)

-   [<span data-ttu-id="7857b-121">管理コンソールを使用して公開サーバーを登録および登録解除する方法</span><span class="sxs-lookup"><span data-stu-id="7857b-121">How to Register and Unregister a Publishing Server by Using the Management Console</span></span>](how-to-register-and-unregister-a-publishing-server-by-using-the-management-console51.md)

-   [<span data-ttu-id="7857b-122">APP-V 5.1 管理コンソールを使用してカスタム構成ファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="7857b-122">How to Create a Custom Configuration File by Using the App-V 5.1 Management Console</span></span>](how-to-create-a-custom-configuration-file-by-using-the-app-v-51-management-console.md)

-   [<span data-ttu-id="7857b-123">管理コンソールを使用してアクセス権限と構成を別のバージョンのパッケージに転送する方法</span><span class="sxs-lookup"><span data-stu-id="7857b-123">How to Transfer Access and Configurations to Another Version of a Package by Using the Management Console</span></span>](how-to-transfer-access-and-configurations-to-another-version-of-a-package-by-using-the-management-console51.md)

-   [<span data-ttu-id="7857b-124">管理コンソールを使用して特定の AD グループの仮想アプリケーションの拡張機能をカスタマイズする方法</span><span class="sxs-lookup"><span data-stu-id="7857b-124">How to Customize Virtual Applications Extensions for a Specific AD Group by Using the Management Console</span></span>](how-to-customize-virtual-applications-extensions-for-a-specific-ad-group-by-using-the-management-console51.md)

-   [<span data-ttu-id="7857b-125">管理コンソールを使用してアプリケーションと既定の仮想アプリケーション拡張機能を表示して構成する方法</span><span class="sxs-lookup"><span data-stu-id="7857b-125">How to View and Configure Applications and Default Virtual Application Extensions by Using the Management Console</span></span>](how-to-view-and-configure-applications-and-default-virtual-application-extensions-by-using-the-management-console-beta.md)

<span data-ttu-id="7857b-126">App-v 5.1 管理コンソールの主な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7857b-126">The main elements of the App-V 5.1 Management Console are:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7857b-127">[管理コンソール] タブ</span><span class="sxs-lookup"><span data-stu-id="7857b-127">Management Console tab</span></span></th>
<th align="left"><span data-ttu-id="7857b-128">説明</span><span class="sxs-lookup"><span data-stu-id="7857b-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7857b-129">[パッケージ] タブ</span><span class="sxs-lookup"><span data-stu-id="7857b-129">Packages tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="7857b-130">パッケージ <strong> </strong> を追加またはアップグレードするには、[パッケージ] タブを使います。</span><span class="sxs-lookup"><span data-stu-id="7857b-130">Use the <strong>PACKAGES</strong> tab to add or upgrade packages.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7857b-131">[接続グループ] タブ</span><span class="sxs-lookup"><span data-stu-id="7857b-131">Connection Groups tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="7857b-132">[ <strong> 接続グループ] タブを使用して、 </strong> 接続グループを管理します。</span><span class="sxs-lookup"><span data-stu-id="7857b-132">Use the <strong>CONNECTION GROUPS</strong> tab to manage connection groups.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7857b-133">[サーバー] タブ</span><span class="sxs-lookup"><span data-stu-id="7857b-133">Servers tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="7857b-134">[ <strong> サーバー </strong> ] タブを使って、新しいサーバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="7857b-134">Use the <strong>SERVERS</strong> tab to register a new server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7857b-135">[管理者] タブ</span><span class="sxs-lookup"><span data-stu-id="7857b-135">Administrators tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="7857b-136">[ <strong> 管理者 </strong> ] タブを使用して、app-v 5.1 環境で管理者を登録、追加、または削除します。</span><span class="sxs-lookup"><span data-stu-id="7857b-136">Use the <strong>ADMINISTRATORS</strong> tab to register, add, or remove administrators in your App-V 5.1 environment.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="7857b-137">**重要** Web 管理コンソールを開くブラウザーで JavaScript を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7857b-137">**Important** JavaScript must be enabled on the browser that opens the Web Management Console.</span></span>

 






## <a href="" id="other-resources-for-this-app-v-5-1-deployment-"></a><span data-ttu-id="7857b-138">この App-v 5.1 の展開に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="7857b-138">Other resources for this App-V 5.1 deployment</span></span>


-   [<span data-ttu-id="7857b-139">Microsoft Application Virtualization 5.1 管理者ガイド</span><span class="sxs-lookup"><span data-stu-id="7857b-139">Microsoft Application Virtualization 5.1 Administrator's Guide</span></span>](microsoft-application-virtualization-51-administrators-guide.md)

-   [<span data-ttu-id="7857b-140">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="7857b-140">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





