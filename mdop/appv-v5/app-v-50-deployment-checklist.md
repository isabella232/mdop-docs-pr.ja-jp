---
title: APP-V 5.0 の展開チェックリスト
description: APP-V 5.0 の展開チェックリスト
author: dansimp
ms.assetid: d6d93152-82b4-4b02-8b11-ed21d3331f00
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3f213271a6d4b90961846b49553c07f1eb6e4c03
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814843"
---
# <span data-ttu-id="7e477-103">APP-V 5.0 の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="7e477-103">App-V 5.0 Deployment Checklist</span></span>


<span data-ttu-id="7e477-104">このチェックリストは、Microsoft Application Virtualization (App-v) 5.0 の展開時に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7e477-104">This checklist can be used to help you during Microsoft Application Virtualization (App-V) 5.0 deployment.</span></span>

**<span data-ttu-id="7e477-105">注</span><span class="sxs-lookup"><span data-stu-id="7e477-105">Note</span></span>**  
<span data-ttu-id="7e477-106">このチェックリストは、推奨される手順と、App-v 5.0 機能の展開時に考慮する必要がある項目の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="7e477-106">This checklist outlines the recommended steps and a high-level list of items to consider when deploying App-V 5.0 features.</span></span> <span data-ttu-id="7e477-107">このチェックリストをスプレッドシートプログラムにコピーして、用途に合わせてカスタマイズすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7e477-107">It is recommended that you copy this checklist into a spreadsheet program and customize it for your use.</span></span>



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
<th align="left"><span data-ttu-id="7e477-108">タスク</span><span class="sxs-lookup"><span data-stu-id="7e477-108">Task</span></span></th>
<th align="left"><span data-ttu-id="7e477-109">参照先</span><span class="sxs-lookup"><span data-stu-id="7e477-109">References</span></span></th>
<th align="left"><span data-ttu-id="7e477-110">備考</span><span class="sxs-lookup"><span data-stu-id="7e477-110">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="7e477-111">計画フェーズを完了して、App-v 5.0 展開用のコンピューティング環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="7e477-111">Complete the planning phase to prepare the computing environment for App-V 5.0 deployment.</span></span></p></td>
<td align="left"><p><a href="app-v-50-planning-checklist.md" data-raw-source="[App-V 5.0 Planning Checklist](app-v-50-planning-checklist.md)"><span data-ttu-id="7e477-112">APP-V 5.0 の計画チェックリスト</span><span class="sxs-lookup"><span data-stu-id="7e477-112">App-V 5.0 Planning Checklist</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="7e477-113">App-v 5.0 でサポートされている構成情報を確認して、選択したクライアントおよびサーバーコンピューターが、app-v 5.0 機能のインストールでサポートされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7e477-113">Review the App-V 5.0 supported configurations information to make sure selected client and server computers are supported for App-V 5.0 feature installation.</span></span></p></td>
<td align="left"><p><a href="app-v-50-supported-configurations.md" data-raw-source="[App-V 5.0 Supported Configurations](app-v-50-supported-configurations.md)"><span data-ttu-id="7e477-114">App-V 5.0 でサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="7e477-114">App-V 5.0 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="7e477-115">App-v 5.0 セットアップを実行して、環境に必要な App-v 5.0 機能を展開します。</span><span class="sxs-lookup"><span data-stu-id="7e477-115">Run App-V 5.0 Setup to deploy the required App-V 5.0 features for your environment.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="7e477-116">注</span><span class="sxs-lookup"><span data-stu-id="7e477-116">Note</span></span></strong><br/><p><span data-ttu-id="7e477-117">インストール時に作成されたサーバーの名前と、関連付けられている URL を追跡します。</span><span class="sxs-lookup"><span data-stu-id="7e477-117">Keep track of the names of the servers and associated URL’s created during installation.</span></span> <span data-ttu-id="7e477-118">この情報は、インストールプロセス全体で使用されます。</span><span class="sxs-lookup"><span data-stu-id="7e477-118">This information will be used throughout the installation process.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p></p>
<ul>
<li><p><a href="how-to-install-the-sequencer-beta-gb18030.md" data-raw-source="[How to Install the Sequencer](how-to-install-the-sequencer-beta-gb18030.md)"><span data-ttu-id="7e477-119">Sequencer をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="7e477-119">How to Install the Sequencer</span></span></a></p></li>
<li><p><a href="how-to-deploy-the-app-v-client-gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md)"><span data-ttu-id="7e477-120">APP-V Client を展開する方法</span><span class="sxs-lookup"><span data-stu-id="7e477-120">How to Deploy the App-V Client</span></span></a></p></li>
<li><p><a href="how-to-deploy-the-app-v-50-server-50sp3.md" data-raw-source="[How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)"><span data-ttu-id="7e477-121">App-V 5.0 Server を展開する方法</span><span class="sxs-lookup"><span data-stu-id="7e477-121">How to Deploy the App-V 5.0 Server</span></span></a></p></li>
</ul></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>








## <span data-ttu-id="7e477-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7e477-122">Related topics</span></span>


[<span data-ttu-id="7e477-123">APP-V 5.0 の展開</span><span class="sxs-lookup"><span data-stu-id="7e477-123">Deploying App-V 5.0</span></span>](deploying-app-v-50.md)









