---
title: App-V インストールのチェックリスト
description: App-V インストールのチェックリスト
author: dansimp
ms.assetid: b17efaab-cd6d-4c30-beb7-c6e7c9c87657
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4d6d83ac465a7e48dd35bd2fe966c3c51be24c96
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819814"
---
# <span data-ttu-id="769ac-103">App-V インストールのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="769ac-103">App-V Installation Checklist</span></span>


<span data-ttu-id="769ac-104">次のチェックリストは、考慮する項目の概要と、Microsoft Application Virtualization (App-v) サーバーをインストールするために必要な手順の概要を示すものです。</span><span class="sxs-lookup"><span data-stu-id="769ac-104">The following checklist is intended to provide a high-level list of items to consider and outlines the steps you should take to install the Microsoft Application Virtualization (App-V) servers.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="769ac-105">ステップ</span><span class="sxs-lookup"><span data-stu-id="769ac-105">Step</span></span></th>
<th align="left"><span data-ttu-id="769ac-106">リファレンス</span><span class="sxs-lookup"><span data-stu-id="769ac-106">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="769ac-107">App-v Management Server をインストールします。</span><span class="sxs-lookup"><span data-stu-id="769ac-107">Install the App-V Management Server.</span></span> <span data-ttu-id="769ac-108">管理 Web サービス、管理コンソール、またはデータストアをさまざまなサーバーにインストールする場合は、カスタムインストールオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="769ac-108">If you are installing the Management Web Service, Management Console, or the Data Store on different servers, you can use the custom installation option.</span></span></p></td>
<td align="left"><p><a href="how-to-install-application-virtualization-management-server.md" data-raw-source="[How to Install Application Virtualization Management Server](how-to-install-application-virtualization-management-server.md)"><span data-ttu-id="769ac-109">Application Virtualization Management Server をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="769ac-109">How to Install Application Virtualization Management Server</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="769ac-110">App-v 管理 Web サービスをインストールします。</span><span class="sxs-lookup"><span data-stu-id="769ac-110">Install the App-V Management Web Service.</span></span> <span data-ttu-id="769ac-111">(省略可能)</span><span class="sxs-lookup"><span data-stu-id="769ac-111">(Optional ¹)</span></span></p></td>
<td align="left"><p><a href="how-to-install-the-management-web-service.md" data-raw-source="[How to Install the Management Web Service](how-to-install-the-management-web-service.md)"><span data-ttu-id="769ac-112">Management Web Service をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="769ac-112">How to Install the Management Web Service</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="769ac-113">App-v 管理コンソールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="769ac-113">Install the App-V Management Console.</span></span> <span data-ttu-id="769ac-114">(省略可能)</span><span class="sxs-lookup"><span data-stu-id="769ac-114">(Optional ¹)</span></span></p></td>
<td align="left"><p><a href="how-to-install-the-management-console.md" data-raw-source="[How to Install the Management Console](how-to-install-the-management-console.md)"><span data-ttu-id="769ac-115">Management Console をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="769ac-115">How to Install the Management Console</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="769ac-116">App-v データストアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="769ac-116">Install the App-V Data Store.</span></span> <span data-ttu-id="769ac-117">(省略可能)</span><span class="sxs-lookup"><span data-stu-id="769ac-117">(Optional ¹)</span></span></p></td>
<td align="left"><p><a href="how-to-install-a-database.md" data-raw-source="[How to Install a Database](how-to-install-a-database.md)"><span data-ttu-id="769ac-118">データベースをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="769ac-118">How to Install a Database</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="769ac-119">App-v クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="769ac-119">Install the App-V client.</span></span></p></td>
<td align="left"><p><a href="how-to-manually-install-the-application-virtualization-client.md" data-raw-source="[How to Manually Install the Application Virtualization Client](how-to-manually-install-the-application-virtualization-client.md)"><span data-ttu-id="769ac-120">Application Virtualization Client を手動でインストールする方法</span><span class="sxs-lookup"><span data-stu-id="769ac-120">How to Manually Install the Application Virtualization Client</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="769ac-121">App-v Sequencer をインストールします。</span><span class="sxs-lookup"><span data-stu-id="769ac-121">Install the App-V Sequencer.</span></span></p></td>
<td align="left"><p><a href="how-to-install-the-application-virtualization-sequencer.md" data-raw-source="[How to Install the Application Virtualization Sequencer](how-to-install-the-application-virtualization-sequencer.md)"><span data-ttu-id="769ac-122">Application Virtualization Sequencer をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="769ac-122">How to Install the Application Virtualization Sequencer</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="769ac-123">App-v ストリーミングサーバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="769ac-123">Install the App-V Streaming Server.</span></span> <span data-ttu-id="769ac-124">(これはオプションであり、ストリーミングサーバーをインストールしている場合にのみ必要です)。</span><span class="sxs-lookup"><span data-stu-id="769ac-124">(This is optional and required only if you are installing the Streaming Server).</span></span></p></td>
<td align="left"><p><a href="how-to-install-the-application-virtualization-streaming-server.md" data-raw-source="[How to Install the Application Virtualization Streaming Server](how-to-install-the-application-virtualization-streaming-server.md)"><span data-ttu-id="769ac-125">Application Virtualization Streaming Server をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="769ac-125">How to Install the Application Virtualization Streaming Server</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="769ac-126">アプリケーションをユーザーのコンピューターにストリーミングするために使用されるサーバー上に、コンテンツディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="769ac-126">Create Content directories on the servers that will be used for streaming applications to users’ computers.</span></span></p></td>
<td align="left"><p><a href="how-to-configure-the-application-virtualization-management-servers.md" data-raw-source="[How to Configure the Application Virtualization Management Servers](how-to-configure-the-application-virtualization-management-servers.md)"><span data-ttu-id="769ac-127">Application Virtualization Management Server を構成する方法</span><span class="sxs-lookup"><span data-stu-id="769ac-127">How to Configure the Application Virtualization Management Servers</span></span></a></p>
<p><a href="how-to-configure-the-application-virtualization-streaming-servers.md" data-raw-source="[How to Configure the Application Virtualization Streaming Servers](how-to-configure-the-application-virtualization-streaming-servers.md)"><span data-ttu-id="769ac-128">Application Virtualization Streaming Server を構成する方法</span><span class="sxs-lookup"><span data-stu-id="769ac-128">How to Configure the Application Virtualization Streaming Servers</span></span></a></p>
<p><a href="how-to-configure-the-server-for-iis.md" data-raw-source="[How to Configure the Server for IIS](how-to-configure-the-server-for-iis.md)"><span data-ttu-id="769ac-129">IIS のサーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="769ac-129">How to Configure the Server for IIS</span></span></a></p>
<p><a href="how-to-configure-the-file-server.md" data-raw-source="[How to Configure the File Server](how-to-configure-the-file-server.md)"><span data-ttu-id="769ac-130">ファイル サーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="769ac-130">How to Configure the File Server</span></span></a></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="769ac-131">¹この情報が必要になるのは、App-v Management Web Service、管理コンソール、またはデータストアを別のコンピューターにインストールする場合のみです。</span><span class="sxs-lookup"><span data-stu-id="769ac-131">¹ This is required only if you are installing the App-V Management Web Service, Management Console, or the Data Store on a different computer.</span></span>

## <span data-ttu-id="769ac-132">関連トピック</span><span class="sxs-lookup"><span data-stu-id="769ac-132">Related topics</span></span>


[<span data-ttu-id="769ac-133">Application Virtualization の展開およびアップグレードのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="769ac-133">Application Virtualization Deployment and Upgrade Checklists</span></span>](application-virtualization-deployment-and-upgrade-checklists.md)

[<span data-ttu-id="769ac-134">App-V インストール後のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="769ac-134">App-V Postinstallation Checklist</span></span>](app-v-postinstallation-checklist.md)

 

 





