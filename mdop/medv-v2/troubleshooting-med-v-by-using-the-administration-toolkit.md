---
title: 管理ツールキットを使用した MED-V のトラブルシューティング
description: 管理ツールキットを使用した MED-V のトラブルシューティング
author: dansimp
ms.assetid: 6c096a1c-b9ce-4ec7-8dfd-5286e3b9a617
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c1eaa493e5603e8a1275a6ff5f189739b168f319
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825374"
---
# <span data-ttu-id="291c0-103">管理ツールキットを使用した MED-V のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="291c0-103">Troubleshooting MED-V by Using the Administration Toolkit</span></span>


<span data-ttu-id="291c0-104">Med-v 管理ツールキットを使って、MED-V ワークスペースの特定の問題のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="291c0-104">Use the MED-V Administration Toolkit to troubleshoot certain problems in a MED-V workspace.</span></span> <span data-ttu-id="291c0-105">MED-V 管理ツールキットを使うと、イベントログのアクセスと構成、MED-V ワークスペースの再起動またはリセット、公開されたアプリケーションの表示、および MED-V ワークスペース内のリダイレクトされた web アドレスの表示を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="291c0-105">The MED-V Administration Toolkit lets you access and configure event logs, restart or reset the MED-V workspace, and view the published applications and redirected web addresses in the MED-V workspace.</span></span> <span data-ttu-id="291c0-106">MED-V 管理ツールキットを使用して、全画面モードで MED-V ワークスペース仮想マシンを開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="291c0-106">You can also use the MED-V Administration Toolkit to open the MED-V workspace virtual machine in full-screen mode.</span></span>

## <span data-ttu-id="291c0-107">MED-V 管理ツールキットを開くには</span><span class="sxs-lookup"><span data-stu-id="291c0-107">To Open the MED-V Administration Toolkit</span></span>


<span data-ttu-id="291c0-108">次の手順を実行して、MED-V 管理ツールキットを開きます。</span><span class="sxs-lookup"><span data-stu-id="291c0-108">Perform the following steps to open the MED-V Administration Toolkit:</span></span>

1.  <span data-ttu-id="291c0-109">トラブルシューティングする MED-V ワークスペースが含まれているホストコンピューターで、コマンドプロンプトウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="291c0-109">On the host computer that contains the MED-V workspace you are troubleshooting, open a Command Prompt window.</span></span>

2.  <span data-ttu-id="291c0-110">% ¥ System のドライブ% \\ プログラムファイル \\ Microsoft Enterprise デスクトップの仮想化を参照します。</span><span class="sxs-lookup"><span data-stu-id="291c0-110">Browse to %systemdrive%\\Program Files\\Microsoft Enterprise Desktop Virtualization.</span></span>

3.  <span data-ttu-id="291c0-111">コマンドプロンプトで、「 **Medvhost/toolkit**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="291c0-111">At the command prompt, type **MedvHost /toolkit**.</span></span>

<span data-ttu-id="291c0-112">MED-V 管理ツールキットが開いたら、ツールキットを使用して、トラブルシューティング中に検出された MED-V ワークスペースの問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="291c0-112">After the MED-V Administration Toolkit opens, you can use the toolkit to help resolve issues in the MED-V workspace found during troubleshooting.</span></span>

## <span data-ttu-id="291c0-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="291c0-113">In this Section</span></span>


<a href="" id="viewing-and-configuring-med-v-logs"></a>[<span data-ttu-id="291c0-114">MED-V ログの表示と構成</span><span class="sxs-lookup"><span data-stu-id="291c0-114">Viewing and Configuring MED-V Logs</span></span>](viewing-and-configuring-med-v-logs.md)  
<span data-ttu-id="291c0-115">MED-V 管理ツールキットを使用して、ホストコンピューターとゲスト仮想マシンでの MED-V イベントログの収集と管理を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="291c0-115">Describes how to use the MED-V Administration Toolkit to collect and manage MED-V event logs in the host computer and the guest virtual machine.</span></span>

<a href="" id="restarting-and-resetting-a-med-v-workspace"></a>[<span data-ttu-id="291c0-116">MED-V ワークスペースの再開とリセット</span><span class="sxs-lookup"><span data-stu-id="291c0-116">Restarting and Resetting a MED-V Workspace</span></span>](restarting-and-resetting-a-med-v-workspace.md)  
<span data-ttu-id="291c0-117">MED-V 管理ツールキットを使用して、MED-V ワークスペースを再起動およびリセットする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="291c0-117">Describes how to restart and reset MED-V workspaces by using the MED-V Administration Toolkit.</span></span>

<a href="" id="viewing-med-v-workspace-configurations"></a>[<span data-ttu-id="291c0-118">MED-V ワークスペースの構成の表示</span><span class="sxs-lookup"><span data-stu-id="291c0-118">Viewing MED-V Workspace Configurations</span></span>](viewing-med-v-workspace-configurations.md)  
<span data-ttu-id="291c0-119">Med-v 管理ツールキットを使って、公開されているアプリケーションと、MED-V ワークスペースのリダイレクトされた web アドレスを表示する方法と、全画面モードで MED-V ワークスペース仮想マシンを開く方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="291c0-119">Describes how to use the MED-V Administration Toolkit to view the published applications and redirected web addresses in a MED-V workspace and how to open the MED-V workspace virtual machine in full-screen mode.</span></span>

## <span data-ttu-id="291c0-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="291c0-120">Related topics</span></span>


[<span data-ttu-id="291c0-121">MED-V のイベント ログ メッセージ</span><span class="sxs-lookup"><span data-stu-id="291c0-121">MED-V Event Log Messages</span></span>](med-v-event-log-messages.md)

[<span data-ttu-id="291c0-122">MED-V のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="291c0-122">Troubleshooting MED-V</span></span>](troubleshooting-med-vmedv2.md)

 

 





