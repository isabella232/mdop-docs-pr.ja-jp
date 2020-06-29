---
title: MED-V 2.0 の更新
description: MED-V 2.0 の更新
author: dansimp
ms.assetid: beea2f54-42d7-4a17-98e0-d243a8562265
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 62e8987ec511783422b8dd336dd4f3be2008c9b2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823734"
---
# <span data-ttu-id="55983-103">MED-V 2.0 の更新</span><span class="sxs-lookup"><span data-stu-id="55983-103">Updating MED-V 2.0</span></span>


<span data-ttu-id="55983-104">Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 に適切なセキュリティ更新プログラムを適用して、システムのセキュリティを強化します。</span><span class="sxs-lookup"><span data-stu-id="55983-104">Help secure your system by applying the appropriate security updates for Microsoft Enterprise Desktop Virtualization (MED-V) 2.0.</span></span>

## <span data-ttu-id="55983-105">MED-V の更新</span><span class="sxs-lookup"><span data-stu-id="55983-105">Updating MED-V</span></span>


<span data-ttu-id="55983-106">MED-V は、エンドユーザーが、または電子的なソフトウェア配布システムを使用してサイレントモードで更新することができます。</span><span class="sxs-lookup"><span data-stu-id="55983-106">You can update MED-V interactively, by the end user, or silently by using an electronic software distribution system.</span></span> <span data-ttu-id="55983-107">MED-V Host agent をインストールすると、MED-V Host Agent がアップグレードされ、必要に応じて MED-V ワークスペースが更新されます。</span><span class="sxs-lookup"><span data-stu-id="55983-107">Installation of the MED-V Host Agent upgrades the MED-V Host Agent and then updates the MED-V workspace if required.</span></span> <span data-ttu-id="55983-108">MED-V ホストエージェントとゲストエージェントの同期が維持されます。MED-V Host Agent が更新されているときに、アプリケーションが MED-V ワークスペースから実行されている場合は、更新を完了するためにホストコンピューターの再起動が必要になります。</span><span class="sxs-lookup"><span data-stu-id="55983-108">The MED-V Host Agent and Guest Agent keep in sync. If applications are running from the MED-V workspace while the MED-V Host Agent is being updated, a restart of the host computer is required to complete the update.</span></span> <span data-ttu-id="55983-109">アプリケーションが実行されていない場合、MED-V は自動的に再開され、ホストコンピューターの再起動なしでアップグレードが完了します。</span><span class="sxs-lookup"><span data-stu-id="55983-109">If no applications are running, MED-V is restarted automatically and the upgrade is completed without a restart of the host computer.</span></span>

<span data-ttu-id="55983-110">電子ソフトウェア配布システムを使用して MED-V を更新する場合は、再起動の動作を制御できます。</span><span class="sxs-lookup"><span data-stu-id="55983-110">If you are updating MED-V by using an electronic software distribution system, you can control the restart behavior.</span></span> <span data-ttu-id="55983-111">これを行うには、MED-V\_HostAgent\_Setup.exe をインストールするときに、コマンドプロンプトで **「REBOOT = "ReallySuppress"** 」と入力して、再起動を抑制します。</span><span class="sxs-lookup"><span data-stu-id="55983-111">To do this, suppress the restart by typing **REBOOT=”ReallySuppress”** at the command prompt when installing MED-V\_HostAgent\_Setup.exe.</span></span> <span data-ttu-id="55983-112">次に、3010のリターンコード (再起動が必要であることを示すシグナル) を取得するように電子ソフトウェア配布システムを構成し、[再起動の設定] 動作を実行します。</span><span class="sxs-lookup"><span data-stu-id="55983-112">Then, configure the electronic software distribution system to capture the 3010 return code (which signals that a restart is required) and perform the set restart behavior.</span></span>

## <span data-ttu-id="55983-113">関連トピック</span><span class="sxs-lookup"><span data-stu-id="55983-113">Related topics</span></span>


[<span data-ttu-id="55983-114">MED-V テクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="55983-114">Technical Reference for MED-V</span></span>](technical-reference-for-med-v.md)

 

 





