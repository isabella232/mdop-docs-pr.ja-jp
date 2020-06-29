---
title: MED-V ワークスペースでのプリンターの管理
description: MED-V ワークスペースでのプリンターの管理
author: dansimp
ms.assetid: ba0a65ad-444f-4d18-95eb-8b9fa1a3ffba
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bc7a62075c95e8816a425eff89ffb992f1185d04
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826117"
---
# <span data-ttu-id="d373c-103">MED-V ワークスペースでのプリンターの管理</span><span class="sxs-lookup"><span data-stu-id="d373c-103">Managing Printers on a MED-V Workspace</span></span>


<span data-ttu-id="d373c-104">Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 では、プリンターのリダイレクションは、MED-V 仮想マシンとホストコンピューターの間で一貫した印刷エクスペリエンスを備えたエンドユーザーを提供します。</span><span class="sxs-lookup"><span data-stu-id="d373c-104">In Microsoft Enterprise Desktop Virtualization (MED-V) 2.0, printer redirection provides end users with a consistent printing experience between the MED-V virtual machine and the host computer.</span></span>

<span data-ttu-id="d373c-105">このトピックでは、MED-V ワークスペースで印刷を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d373c-105">This topic provides information about how to manage printing in a MED-V workspace.</span></span>

## <span data-ttu-id="d373c-106">MED-V ワークスペースでのプリンターの管理</span><span class="sxs-lookup"><span data-stu-id="d373c-106">Managing Printers in MED-V Workspaces</span></span>


<span data-ttu-id="d373c-107">ほとんどの場合、MED-V はプリンターリダイレクションを自動的に処理します。</span><span class="sxs-lookup"><span data-stu-id="d373c-107">In most cases, MED-V handles printer redirection automatically.</span></span> <span data-ttu-id="d373c-108">セットアップが完了した後、MED-V は、ホストにインストールされているすべてのネットワークプリンターを特定し、対応するドライバーをネットワークプリントサーバーから取得し、見つかった場合は、MED-V ワークスペースに関連するドライバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d373c-108">After first time setup finishes, MED-V identifies all network printers installed on the host, retrieves the corresponding drivers from the network print server, and if found, installs the relevant drivers in the MED-V workspace.</span></span> <span data-ttu-id="d373c-109">すべてのドライバーが検出されてインストールされると、MED-V は MED-V ワークスペースを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d373c-109">After all drivers are found and installed, MED-V reboots the MED-V workspace.</span></span> <span data-ttu-id="d373c-110">MED-V ワークスペースを再起動した後にのみ、ホストプリンターが存在し、ゲストで利用できるようになります (通常は数分)。</span><span class="sxs-lookup"><span data-stu-id="d373c-110">Only after the MED-V workspace restarts, the host printers are present and available on the guest, typically in a few minutes.</span></span>

<span data-ttu-id="d373c-111">**注** アプリケーションが MED-V ワークスペースで実行されている場合、エンドユーザーは、再起動を続行するか、または後で延期するように求められます。</span><span class="sxs-lookup"><span data-stu-id="d373c-111">**Note** If applications are running on the MED-V workspace, the end user is prompted to let the restart continue or postpone it until later.</span></span> <span data-ttu-id="d373c-112">アプリケーションが実行されていない場合、再起動は自動的に行われ、エンドユーザーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="d373c-112">If no applications are running, the restart is automatic and not shown to the end user.</span></span>

 

<span data-ttu-id="d373c-113">MED-V が再起動されるたびに、ホストに新しいプリンターがインストールされているかどうかを確認し、見つかった場合は、対応するドライバーをネットワークプリントサーバーから取得してゲストにインストールします。</span><span class="sxs-lookup"><span data-stu-id="d373c-113">Every time MED-V is re-started, it checks whether any new printers are installed on the host and, if found, retrieves the corresponding drivers from the network print server and installs them on the guest.</span></span> <span data-ttu-id="d373c-114">MED-V は、初回のセットアップが完了したときと同じように、MED-V ワークスペースを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d373c-114">MED-V then restarts the MED-V workspace just as when first time setup was completed.</span></span>

<span data-ttu-id="d373c-115">**重要** 関連するドライバーがゲストにインストールされた後は、再起動が行われた後はゲストにのみプリンターが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="d373c-115">**Important** After the relevant drivers are installed on the guest, the printers only become visible on the guest after the restart occurs.</span></span>

 

<span data-ttu-id="d373c-116">ドライバーが見つからない場合、またはインストールすることができない場合は、ネットワークプリンターがエンドユーザーに提供されるように、そのドライバーをゲストに手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d373c-116">If at any time a driver cannot be located or installed, it must be manually installed on the guest for the network printer to be available to the end user.</span></span>

<span data-ttu-id="d373c-117">次の一覧では、追加のガイダンスをいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="d373c-117">The following list offers some additional guidance:</span></span>

<span data-ttu-id="d373c-118">**Med-v は、ネットワークプリンターを管理**します。</span><span class="sxs-lookup"><span data-stu-id="d373c-118">**MED-V only manages network printers**.</span></span> <span data-ttu-id="d373c-119">ホストにローカルにインストールされているプリンターのドライバーは、ゲストに自動的にインストールされません。</span><span class="sxs-lookup"><span data-stu-id="d373c-119">Drivers for printers that are installed locally on the host are not automatically installed on the guest.</span></span>

<span data-ttu-id="d373c-120">**Med-v では、プリントサーバー上にある場合にのみプリンタードライバーがインストール**されます。</span><span class="sxs-lookup"><span data-stu-id="d373c-120">**MED-V only installs printer drivers if found on the print server**.</span></span> <span data-ttu-id="d373c-121">見つからない場合は、プリンタードライバーを手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d373c-121">If not found, printer drivers must be manually installed.</span></span>

<span data-ttu-id="d373c-122">**ゲストに手動でインストールされたプリンターには、ホストからアクセスすることはできません**。</span><span class="sxs-lookup"><span data-stu-id="d373c-122">**Printers manually installed on the guest are not accessible to the host**.</span></span> <span data-ttu-id="d373c-123">既定では、MED-V はゲストからホストへのプリンターのリダイレクションのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d373c-123">By default, MED-V only supports printer redirection from the guest to the host.</span></span>

<span data-ttu-id="d373c-124">**警告** プリンターがゲストに手動でインストールされていて、同じプリンターがホストにインストールされている場合、その結果、プリンターはゲストに2回インストールされます。</span><span class="sxs-lookup"><span data-stu-id="d373c-124">**Warning** If a printer is manually installed on the guest, and the same printer is later installed on the host, the result is that the printer is installed two times in the guest.</span></span> <span data-ttu-id="d373c-125">このような状況を回避するために、MED-V のベストプラクティスは、リダイレクトを無効にして、ゲストのプリンターを手動でインストールするか、またはリダイレクトを有効にして、ゲスト上に手動でプリンターをインストールしないようにすることです。</span><span class="sxs-lookup"><span data-stu-id="d373c-125">To avoid this situation, a MED-V best practice is to manage printer redirection in one manner only: either disable redirection and install printers manually on the guest, or enable redirection and do not install printers manually on the guest.</span></span>

 

## <span data-ttu-id="d373c-126">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d373c-126">Related topics</span></span>


[<span data-ttu-id="d373c-127">MED-V ワークスペースの設定を管理する</span><span class="sxs-lookup"><span data-stu-id="d373c-127">Manage MED-V Workspace Settings</span></span>](manage-med-v-workspace-settings.md)

 

 





