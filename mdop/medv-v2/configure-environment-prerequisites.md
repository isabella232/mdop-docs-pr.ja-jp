---
title: 環境の前提条件を構成する
description: 環境の前提条件を構成する
author: dansimp
ms.assetid: 7379e8e5-1cb2-4b8e-8acc-5c04e26f8c91
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8d6fc3b81f6dafbe709dd904b9fba6124d2f6b6a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826447"
---
# <span data-ttu-id="ba73e-103">環境の前提条件を構成する</span><span class="sxs-lookup"><span data-stu-id="ba73e-103">Configure Environment Prerequisites</span></span>


<span data-ttu-id="ba73e-104">Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 を展開して実行するには、環境が以下の最低限の前提条件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba73e-104">Before you can deploy and run Microsoft Enterprise Desktop Virtualization (MED-V) 2.0, you must ensure that your environment meets the following minimum prerequisites.</span></span>

**<span data-ttu-id="ba73e-105">Windows 7</span><span class="sxs-lookup"><span data-stu-id="ba73e-105">Windows 7</span></span>**

<span data-ttu-id="ba73e-106">MED-V Host Agent と MED-V ワークスペースパッケージャーは、Windows 7 以降でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ba73e-106">The MED-V Host Agent and the MED-V Workspace Packager are only supported in Windows 7 or newer.</span></span>

**<span data-ttu-id="ba73e-107">Windows XP SP3</span><span class="sxs-lookup"><span data-stu-id="ba73e-107">Windows XP SP3</span></span>**

<span data-ttu-id="ba73e-108">MED-V ゲストエージェントは、Windows XP SP3 でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ba73e-108">The MED-V Guest Agent is only supported in Windows XP SP3.</span></span>

**<span data-ttu-id="ba73e-109">.NET Framework 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="ba73e-109">.NET Framework 3.5 SP1</span></span>**

<span data-ttu-id="ba73e-110">MED-V ホストとゲストエージェント、および MED-V ワークスペースパッケージャーには、Microsoft .NET Framework 3.5 SP1 が必要です。</span><span class="sxs-lookup"><span data-stu-id="ba73e-110">The MED-V Host and Guest agents and the MED-V Workspace Packager require the Microsoft .NET Framework 3.5 SP1.</span></span>

<span data-ttu-id="ba73e-111">**重要** また、更新[KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) () をインストールする必要があり https://go.microsoft.com/fwlink/?LinkId=204950) ます。これは、いくつかの既知のアプリケーション互換性の問題に対応しています。</span><span class="sxs-lookup"><span data-stu-id="ba73e-111">**Important** You must also install the update [KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) (https://go.microsoft.com/fwlink/?LinkId=204950), which addresses several known application compatibility issues.</span></span>

 

<span data-ttu-id="ba73e-112">**注** .NET Framework 3.5 SP1 と更新 KB959209 を手動でインストールして、MED-V で使用するために準備する Windows 仮想 PC イメージにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba73e-112">**Note** You must manually install the .NET Framework 3.5 SP1 and the update KB959209 into the Windows Virtual PC image that you prepare for use with MED-V.</span></span> <span data-ttu-id="ba73e-113">ただし、既定では、ホストコンピューターに Windows 7 をインストールすると、Microsoft .NET Framework 3.5 SP1 と更新プログラムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ba73e-113">However, by default, the Microsoft .NET Framework 3.5 SP1 and the update are included when you install Windows 7 on the host computer.</span></span>

 

**<span data-ttu-id="ba73e-114">Active Directory インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="ba73e-114">An Active Directory Infrastructure</span></span>**

<span data-ttu-id="ba73e-115">グループポリシーは、Active Directory 環境でのオペレーティングシステム、アプリケーション、ユーザーの設定の一元管理と構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="ba73e-115">Group Policy provides the centralized management and configuration of operating systems, applications, and users' settings in an Active Directory environment.</span></span>

## <span data-ttu-id="ba73e-116">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ba73e-116">Related topics</span></span>


[<span data-ttu-id="ba73e-117">インストールの前提条件を構成する</span><span class="sxs-lookup"><span data-stu-id="ba73e-117">Configure Installation Prerequisites</span></span>](configure-installation-prerequisites.md)

[<span data-ttu-id="ba73e-118">アーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="ba73e-118">High-Level Architecture</span></span>](high-level-architecturemedv2.md)

[<span data-ttu-id="ba73e-119">MED-V 2.0 でサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="ba73e-119">MED-V 2.0 Supported Configurations</span></span>](med-v-20-supported-configurations.md)

 

 





