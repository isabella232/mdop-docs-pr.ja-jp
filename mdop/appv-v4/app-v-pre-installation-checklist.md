---
title: APP-V インストール前のチェックリスト
description: APP-V インストール前のチェックリスト
author: dansimp
ms.assetid: 3af609b1-2c09-4edb-b083-b913b6d5e8c4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 70e71d3dea02daeadedb4cff78c58302ac743dda
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819787"
---
# <span data-ttu-id="6fc6f-103">APP-V インストール前のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="6fc6f-103">App-V Pre-Installation Checklist</span></span>


<span data-ttu-id="6fc6f-104">次のチェックリストは、考慮する項目の概要と、Microsoft Application Virtualization (App-v) サーバーをインストールする前に実行する必要がある手順の概要を示すものです。</span><span class="sxs-lookup"><span data-stu-id="6fc6f-104">The following checklist is intended to provide a high-level list of items to consider and outlines the steps you should take before you install the Microsoft Application Virtualization (App-V) servers.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6fc6f-105">ステップ</span><span class="sxs-lookup"><span data-stu-id="6fc6f-105">Step</span></span></th>
<th align="left"><span data-ttu-id="6fc6f-106">リファレンス</span><span class="sxs-lookup"><span data-stu-id="6fc6f-106">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6fc6f-107">使用しているコンピューティング環境が、App-v に必要なサポートされている構成を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6fc6f-107">Ensure your computing environment meets the supported configurations required for App-V.</span></span></p></td>
<td align="left"><p><a href="application-virtualization-deployment-requirements.md" data-raw-source="[Application Virtualization Deployment Requirements](application-virtualization-deployment-requirements.md)"><span data-ttu-id="6fc6f-108">Application Virtualization の展開要件</span><span class="sxs-lookup"><span data-stu-id="6fc6f-108">Application Virtualization Deployment Requirements</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6fc6f-109">必要な Active Directory グループとアカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="6fc6f-109">Configure the necessary Active Directory groups and accounts.</span></span></p></td>
<td align="left"><p><a href="configuring-prerequisite-groups-in-active-directory-for-app-v.md" data-raw-source="[Configuring Prerequisite Groups in Active Directory for App-V](configuring-prerequisite-groups-in-active-directory-for-app-v.md)"><span data-ttu-id="6fc6f-110">App-V 用に Active Directory の前提条件グループを構成する</span><span class="sxs-lookup"><span data-stu-id="6fc6f-110">Configuring Prerequisite Groups in Active Directory for App-V</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6fc6f-111">IIS を実行しているサーバーのインターネットインフォメーションサービス (IIS) 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="6fc6f-111">Configure the Internet Information Services (IIS) settings on the server that is running IIS.</span></span></p></td>
<td align="left"><p><a href="how-to-configure-windows-server-2008-for-app-v-management-servers.md" data-raw-source="[How to Configure Windows Server 2008 for App-V Management Servers](how-to-configure-windows-server-2008-for-app-v-management-servers.md)"><span data-ttu-id="6fc6f-112">App-V Management Server 用に Windows Server 2008 を構成する方法</span><span class="sxs-lookup"><span data-stu-id="6fc6f-112">How to Configure Windows Server 2008 for App-V Management Servers</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6fc6f-113">IIS を実行しているサーバーが委任に対して信頼されるように構成します。</span><span class="sxs-lookup"><span data-stu-id="6fc6f-113">Configure the server that is running IIS to be trusted for delegation.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="6fc6f-114">注</span><span class="sxs-lookup"><span data-stu-id="6fc6f-114">Note</span></span></strong><br/><p><span data-ttu-id="6fc6f-115">これは、分散システムアーキテクチャを使用して App-v Management Server をインストールする場合にのみ必要です。つまり、App-v 管理コンソール、管理 Web サービス、およびデータベースをさまざまなコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="6fc6f-115">This is required only if you are installing the App-V Management Server by using a distributed system architecture, that is, if you install the App-V Management Console, the Management Web Service, and the database on different computers.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="how-to-configure-the-server-to-be-trusted-for-delegation.md" data-raw-source="[How to Configure the Server to be Trusted for Delegation](how-to-configure-the-server-to-be-trusted-for-delegation.md)"><span data-ttu-id="6fc6f-116">サーバーを委任に対して信頼されるように構成する方法</span><span class="sxs-lookup"><span data-stu-id="6fc6f-116">How to Configure the Server to be Trusted for Delegation</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6fc6f-117">Microsoft SQL Server 2008 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="6fc6f-117">Install Microsoft SQL Server 2008.</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=181924" data-raw-source="[Install SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=181924)"><span data-ttu-id="6fc6f-118">SQL Server 2008 </a> ( <a href="https://go.microsoft.com/fwlink/?LinkId=181924" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=181924"> https://go.microsoft.com/fwlink/?LinkId=181924 </a> ) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="6fc6f-118">Install SQL Server 2008</a> (<a href="https://go.microsoft.com/fwlink/?LinkId=181924" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=181924">https://go.microsoft.com/fwlink/?LinkId=181924</a>).</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="6fc6f-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6fc6f-119">Related topics</span></span>


[<span data-ttu-id="6fc6f-120">Application Virtualization の展開およびアップグレードのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="6fc6f-120">Application Virtualization Deployment and Upgrade Checklists</span></span>](application-virtualization-deployment-and-upgrade-checklists.md)

[<span data-ttu-id="6fc6f-121">App-V インストールのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="6fc6f-121">App-V Installation Checklist</span></span>](app-v-installation-checklist.md)









