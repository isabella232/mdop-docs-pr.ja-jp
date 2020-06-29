---
title: 管理者用コンピューターへの DaRT 7.0 の展開
description: 管理者用コンピューターへの DaRT 7.0 の展開
author: dansimp
ms.assetid: 8baf26aa-b168-463c-810f-a165918b9d9f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 96eda08e28b915e30d88aa57cb19562958848cf4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812690"
---
# <span data-ttu-id="fd291-103">管理者用コンピューターへの DaRT 7.0 の展開</span><span class="sxs-lookup"><span data-stu-id="fd291-103">Deploying DaRT 7.0 to Administrator Computers</span></span>


<span data-ttu-id="fd291-104">Microsoft 診断/回復ツールセット (DaRT) 7 の展開を開始する前に、お使いの環境の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="fd291-104">Before you begin the deployment of Microsoft Diagnostics and Recovery Toolset (DaRT)7, review the requirements for your environment.</span></span> <span data-ttu-id="fd291-105">DaRT をインストールするためのハードウェア要件が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fd291-105">This includes the hardware requirements for installing DaRT.</span></span> <span data-ttu-id="fd291-106">DaRT のハードウェアとソフトウェアの要件の詳細については、「 [dart 7.0 でサポートされている構成](dart-70-supported-configurations-dart-7.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd291-106">For more information about DaRT hardware and software requirements, see [DaRT 7.0 Supported Configurations](dart-70-supported-configurations-dart-7.md).</span></span>

<span data-ttu-id="fd291-107">このセクションのトピックは、環境と展開戦略に基づいて、企業で DaRT を展開するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="fd291-107">The topics in this section can be used to help you deploy DaRT in your enterprise based on your environment and deployment strategy.</span></span>

## <span data-ttu-id="fd291-108">管理者のコンピューターに DaRT 7.0 を展開する</span><span class="sxs-lookup"><span data-stu-id="fd291-108">Deploy DaRT 7.0 to administrator computers</span></span>


<span data-ttu-id="fd291-109">Dart の Windows インストーラファイルを使用して、初めて DaRT リカバリ画像を作成してから、エンドユーザのコンピュータのトラブルシューティングと解決に使用するコンピュータに DaRT をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="fd291-109">You can use the Windows Installer file for DaRT to install DaRT on a computer that you will use to first create the DaRT recovery image and then troubleshoot and fix end-user computers.</span></span> <span data-ttu-id="fd291-110">多くの場合、組織全体で、DaRT の回復イメージを作成するために必要な DaRT の機能のみが管理者のコンピューターにインストールされることがあります。</span><span class="sxs-lookup"><span data-stu-id="fd291-110">Frequently, across an organization, you might install on the administrator computer only the DaRT functionality that you need to create a DaRT recovery image.</span></span> <span data-ttu-id="fd291-111">次に、ヘルプデスク管理者のコンピューターで、DaRT リモート接続ビューアーやクラッシュアナライザーなどの問題のあるコンピューターのトラブルシューティングに必要な DaRT 機能のみをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="fd291-111">Then, on a helpdesk administrator’s computer, you might install only the DaRT functionality that you must have to troubleshoot a problem computer, such as the DaRT Remote Connection Viewer and the Crash Analyzer.</span></span>

<span data-ttu-id="fd291-112">DaRT をインストールするには、Windows インストーラファイルを手動で実行するだけでなく、コマンドプロンプトで DaRT をインストールして、SystemCenterConfigurationManager2012 などのエンタープライズソフトウェア展開システムをサポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fd291-112">In addition to manually running the Windows Installer file to install DaRT, you can also install DaRT at the command prompt to support enterprise software deployment systems such as SystemCenterConfigurationManager2012.</span></span>

[<span data-ttu-id="fd291-113">DaRT 7.0 を展開する方法</span><span class="sxs-lookup"><span data-stu-id="fd291-113">How to Deploy DaRT 7.0</span></span>](how-to-deploy-dart-70.md)

## <span data-ttu-id="fd291-114">DaRT 7.0 を変更、修復、または削除する</span><span class="sxs-lookup"><span data-stu-id="fd291-114">Change, repair, or remove DaRT 7.0</span></span>


<span data-ttu-id="fd291-115">Dart のインストールファイルをダブルクリックして、実行するアクションに対応するボタンをクリックするか、または Windows のコントロールパネルを使用して、DaRT インストールの変更、修復、または削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fd291-115">You can change, repair, or remove the DaRT installation by double-clicking the DaRT installation file and then clicking the button that corresponds to the action that you want to perform or through the Windows Control Panel.</span></span>

[<span data-ttu-id="fd291-116">DaRT 7.0 を変更、修復、削除する方法</span><span class="sxs-lookup"><span data-stu-id="fd291-116">How to Change, Repair, or Remove DaRT 7.0</span></span>](how-to-change-repair-or-remove-dart-70.md)

## <span data-ttu-id="fd291-117">DaRT 7.0 を管理者コンピューターに展開するためのその他のリソース</span><span class="sxs-lookup"><span data-stu-id="fd291-117">Other resources for Deploying the DaRT 7.0 to Administrator Computers</span></span>


-   [<span data-ttu-id="fd291-118">DaRT 7.0 の展開</span><span class="sxs-lookup"><span data-stu-id="fd291-118">Deploying DaRT 7.0</span></span>](deploying-dart-70-new-ia.md)

 

 





