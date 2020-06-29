---
title: APP-V 5.0 の計画チェックリスト
description: APP-V 5.0 の計画チェックリスト
author: dansimp
ms.assetid: 81d3fa62-3c9e-4de7-a9da-cd13112b0862
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fec4a23c0b1086d32f9c458256e0ece3208bcaee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814818"
---
# <span data-ttu-id="0bbbb-103">APP-V 5.0 の計画チェックリスト</span><span class="sxs-lookup"><span data-stu-id="0bbbb-103">App-V 5.0 Planning Checklist</span></span>


<span data-ttu-id="0bbbb-104">このチェックリストを使用して、Microsoft Application Virtualization (App-v) 5.0 展開用のコンピューティング環境の準備を計画することができます。</span><span class="sxs-lookup"><span data-stu-id="0bbbb-104">This checklist can be used to help you plan for preparing your computing environment for Microsoft Application Virtualization (App-V) 5.0 deployment.</span></span>

<span data-ttu-id="0bbbb-105">**注** このチェックリストは、推奨される手順と、App-v 5.0 の展開を計画する際に考慮する必要のある項目の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="0bbbb-105">**Note** This checklist outlines the recommended steps and a high-level list of items to consider when planning for an App-V 5.0 deployment.</span></span> <span data-ttu-id="0bbbb-106">このチェックリストをスプレッドシートプログラムにコピーして、用途に合わせてカスタマイズすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0bbbb-106">It is recommended that you copy this checklist into a spreadsheet program and customize it for your use.</span></span>

 

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="0bbbb-107">タスク</span><span class="sxs-lookup"><span data-stu-id="0bbbb-107">Task</span></span></th>
<th align="left"><span data-ttu-id="0bbbb-108">参照先</span><span class="sxs-lookup"><span data-stu-id="0bbbb-108">References</span></span></th>
<th align="left"><span data-ttu-id="0bbbb-109">備考</span><span class="sxs-lookup"><span data-stu-id="0bbbb-109">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="0bbbb-110">展開計画を開始する前に、製品についての基本的な理解を得るために、App-v 5.0 に関する概要情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="0bbbb-110">Review the getting started information about App-V 5.0 to gain a basic understanding of the product before beginning deployment planning.</span></span></p></td>
<td align="left"><p><a href="getting-started-with-app-v-50--rtm.md" data-raw-source="[Getting Started with App-V 5.0](getting-started-with-app-v-50--rtm.md)"><span data-ttu-id="0bbbb-111">App-V 5.0 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="0bbbb-111">Getting Started with App-V 5.0</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="0bbbb-112">アプリ-V 5.0 1.0 展開の前提条件を計画し、コンピューティング環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="0bbbb-112">Plan for App-V 5.0 1.0 Deployment Prerequisites and prepare your computing environment.</span></span></p></td>
<td align="left"><p><a href="app-v-50-prerequisites.md" data-raw-source="[App-V 5.0 Prerequisites](app-v-50-prerequisites.md)"><span data-ttu-id="0bbbb-113">App-V 5.0 の前提条件</span><span class="sxs-lookup"><span data-stu-id="0bbbb-113">App-V 5.0 Prerequisites</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="0bbbb-114">App-v 5.0 management server を使用する予定がある場合は、必要な役割を計画します。</span><span class="sxs-lookup"><span data-stu-id="0bbbb-114">If you plan to use the App-V 5.0 management server, plan for the required roles.</span></span></p></td>
<td align="left"><p><a href="planning-for-the-app-v-50-server-deployment.md" data-raw-source="[Planning for the App-V 5.0 Server Deployment](planning-for-the-app-v-50-server-deployment.md)"><span data-ttu-id="0bbbb-115">App-V 5.0 Server の展開計画</span><span class="sxs-lookup"><span data-stu-id="0bbbb-115">Planning for the App-V 5.0 Server Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="0bbbb-116">仮想化されたアプリケーションを作成して実行できるように、App-v 5.0 sequencer とクライアントを計画します。</span><span class="sxs-lookup"><span data-stu-id="0bbbb-116">Plan for the App-V 5.0 sequencer and client so you to create and run virtualized applications.</span></span></p></td>
<td align="left"><p><a href="planning-for-the-app-v-50-sequencer-and-client-deployment.md" data-raw-source="[Planning for the App-V 5.0 Sequencer and Client Deployment](planning-for-the-app-v-50-sequencer-and-client-deployment.md)"><span data-ttu-id="0bbbb-117">App-V 5.0 Sequencer および Client の展開計画</span><span class="sxs-lookup"><span data-stu-id="0bbbb-117">Planning for the App-V 5.0 Sequencer and Client Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="0bbbb-118">該当する場合は、以前のバージョンの App-v から移行するためのオプションと手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="0bbbb-118">If applicable, review the options and steps for migrating from a previous version of App-V.</span></span></p></td>
<td align="left"><p><a href="planning-for-migrating-from-a-previous-version-of-app-v.md" data-raw-source="[Planning for Migrating from a Previous Version of App-V](planning-for-migrating-from-a-previous-version-of-app-v.md)"><span data-ttu-id="0bbbb-119">APP-V の以前のバージョンからの移行計画</span><span class="sxs-lookup"><span data-stu-id="0bbbb-119">Planning for Migrating from a Previous Version of App-V</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="0bbbb-120">共有コンテンツストアモードで使用している App-v 5.0 クライアントの実行を計画します。</span><span class="sxs-lookup"><span data-stu-id="0bbbb-120">Plan for running App-V 5.0 clients using in shared content store mode.</span></span></p></td>
<td align="left"><p><a href="how-to-install-the-app-v-50-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.0 Client for Shared Content Store Mode](how-to-install-the-app-v-50-client-for-shared-content-store-mode.md)"><span data-ttu-id="0bbbb-121">共有コンテンツ ストア モードの App-V 5.0 Client のインストール方法</span><span class="sxs-lookup"><span data-stu-id="0bbbb-121">How to Install the App-V 5.0 Client for Shared Content Store Mode</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="0bbbb-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0bbbb-122">Related topics</span></span>


[<span data-ttu-id="0bbbb-123">App-V 5.0 の計画</span><span class="sxs-lookup"><span data-stu-id="0bbbb-123">Planning for App-V 5.0</span></span>](planning-for-app-v-50-rc.md)

 

 





