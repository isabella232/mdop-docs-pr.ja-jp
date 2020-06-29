---
title: APP-V 5.1 の展開チェックリスト
description: APP-V 5.1 の展開チェックリスト
author: dansimp
ms.assetid: 44bed85a-e4f5-49d7-a308-a2b681f76372
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0864335e505996a3ea379b09de6a1aaa7fbe1676
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814771"
---
# <span data-ttu-id="851e6-103">APP-V 5.1 の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="851e6-103">App-V 5.1 Deployment Checklist</span></span>


<span data-ttu-id="851e6-104">このチェックリストは、Microsoft Application Virtualization (App-v) 5.1 の展開時に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="851e6-104">This checklist can be used to help you during Microsoft Application Virtualization (App-V) 5.1 deployment.</span></span>

**<span data-ttu-id="851e6-105">注</span><span class="sxs-lookup"><span data-stu-id="851e6-105">Note</span></span>**  
<span data-ttu-id="851e6-106">このチェックリストは、推奨される手順と、App-v 5.1 機能の展開時に考慮する必要がある項目の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="851e6-106">This checklist outlines the recommended steps and a high-level list of items to consider when deploying App-V 5.1 features.</span></span> <span data-ttu-id="851e6-107">このチェックリストをスプレッドシートプログラムにコピーして、用途に合わせてカスタマイズすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="851e6-107">It is recommended that you copy this checklist into a spreadsheet program and customize it for your use.</span></span>



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
<th align="left"><span data-ttu-id="851e6-108">タスク</span><span class="sxs-lookup"><span data-stu-id="851e6-108">Task</span></span></th>
<th align="left"><span data-ttu-id="851e6-109">参照先</span><span class="sxs-lookup"><span data-stu-id="851e6-109">References</span></span></th>
<th align="left"><span data-ttu-id="851e6-110">備考</span><span class="sxs-lookup"><span data-stu-id="851e6-110">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="851e6-111">計画フェーズを完了して、App-v 5.1 展開用のコンピューティング環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="851e6-111">Complete the planning phase to prepare the computing environment for App-V 5.1 deployment.</span></span></p></td>
<td align="left"><p><a href="app-v-51-planning-checklist.md" data-raw-source="[App-V 5.1 Planning Checklist](app-v-51-planning-checklist.md)"><span data-ttu-id="851e6-112">APP-V 5.1 の計画チェックリスト</span><span class="sxs-lookup"><span data-stu-id="851e6-112">App-V 5.1 Planning Checklist</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="851e6-113">App-v 5.1 でサポートされている構成情報を確認して、選択したクライアントおよびサーバーコンピューターが、app-v 5.1 機能のインストールでサポートされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="851e6-113">Review the App-V 5.1 supported configurations information to make sure selected client and server computers are supported for App-V 5.1 feature installation.</span></span></p></td>
<td align="left"><p><a href="app-v-51-supported-configurations.md" data-raw-source="[App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md)"><span data-ttu-id="851e6-114">App-V 5.1 でサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="851e6-114">App-V 5.1 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="851e6-115">App-v 5.1 セットアップを実行して、環境に必要な App-v 5.1 機能を展開します。</span><span class="sxs-lookup"><span data-stu-id="851e6-115">Run App-V 5.1 Setup to deploy the required App-V 5.1 features for your environment.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="851e6-116">注</span><span class="sxs-lookup"><span data-stu-id="851e6-116">Note</span></span></strong><br/><p><span data-ttu-id="851e6-117">インストール時に作成されたサーバーの名前と、関連付けられている URL を追跡します。</span><span class="sxs-lookup"><span data-stu-id="851e6-117">Keep track of the names of the servers and associated URL’s created during installation.</span></span> <span data-ttu-id="851e6-118">この情報は、インストールプロセス全体で使用されます。</span><span class="sxs-lookup"><span data-stu-id="851e6-118">This information will be used throughout the installation process.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p></p>
<ul>
<li><p><a href="how-to-install-the-sequencer-51beta-gb18030.md" data-raw-source="[How to Install the Sequencer](how-to-install-the-sequencer-51beta-gb18030.md)"><span data-ttu-id="851e6-119">Sequencer をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="851e6-119">How to Install the Sequencer</span></span></a></p></li>
<li><p><a href="how-to-deploy-the-app-v-client-51gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-51gb18030.md)"><span data-ttu-id="851e6-120">APP-V Client を展開する方法</span><span class="sxs-lookup"><span data-stu-id="851e6-120">How to Deploy the App-V Client</span></span></a></p></li>
<li><p><a href="how-to-deploy-the-app-v-51-server.md" data-raw-source="[How to Deploy the App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md)"><span data-ttu-id="851e6-121">App-V 5.1 Server を展開する方法</span><span class="sxs-lookup"><span data-stu-id="851e6-121">How to Deploy the App-V 5.1 Server</span></span></a></p></li>
</ul></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>








## <span data-ttu-id="851e6-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="851e6-122">Related topics</span></span>


[<span data-ttu-id="851e6-123">APP-V 5.1 の展開</span><span class="sxs-lookup"><span data-stu-id="851e6-123">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)









