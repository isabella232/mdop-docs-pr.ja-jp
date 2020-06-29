---
title: 管理者用コンピューターへの DaRT 8.0 の展開
description: 管理者用コンピューターへの DaRT 8.0 の展開
author: dansimp
ms.assetid: f918ead8-742e-464a-8bf6-1fcedde66cae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0ab001f612f2257ecbd77c39319cc99c17d36197
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824124"
---
# <span data-ttu-id="2eef4-103">管理者用コンピューターへの DaRT 8.0 の展開</span><span class="sxs-lookup"><span data-stu-id="2eef4-103">Deploying DaRT 8.0 to Administrator Computers</span></span>


<span data-ttu-id="2eef4-104">Microsoft 診断/回復ツールセット (DaRT) 8.0 の展開を開始する前に、お使いの環境の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="2eef4-104">Before you begin the deployment of Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0, review the requirements for your environment.</span></span> <span data-ttu-id="2eef4-105">DaRT 8.0 をインストールするためのハードウェア要件が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2eef4-105">This includes the hardware requirements for installing DaRT 8.0.</span></span> <span data-ttu-id="2eef4-106">DaRT のハードウェアとソフトウェアの要件の詳細については、「 [dart 8.0 でサポートされている構成](dart-80-supported-configurations-dart-8.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2eef4-106">For more information about DaRT hardware and software requirements, see [DaRT 8.0 Supported Configurations](dart-80-supported-configurations-dart-8.md).</span></span>

<span data-ttu-id="2eef4-107">このセクションのトピックは、環境と展開戦略に基づいて、企業で DaRT を展開するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="2eef4-107">The topics in this section can be used to help you deploy DaRT in your enterprise based on your environment and deployment strategy.</span></span>

## <span data-ttu-id="2eef4-108">DaRT 8.0 の展開</span><span class="sxs-lookup"><span data-stu-id="2eef4-108">Deploy DaRT 8.0</span></span>


<span data-ttu-id="2eef4-109">Dart の Windows インストーラファイルを使用して、初めて DaRT リカバリ画像を作成してから、エンドユーザのコンピュータのトラブルシューティングと解決に使用するコンピュータに DaRT をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="2eef4-109">You can use the Windows Installer file for DaRT to install DaRT on a computer that you will use to first create the DaRT recovery image and then troubleshoot and fix end-user computers.</span></span> <span data-ttu-id="2eef4-110">多くの場合、組織全体で、DaRT の回復イメージを作成するために必要な DaRT の機能のみが管理者のコンピューターにインストールされることがあります。</span><span class="sxs-lookup"><span data-stu-id="2eef4-110">Frequently, across an organization, you might install on the administrator computer only the DaRT functionality that you need to create a DaRT recovery image.</span></span> <span data-ttu-id="2eef4-111">次に、ヘルプデスク管理者のコンピューターで、DaRT リモート接続ビューアーやクラッシュアナライザーなどの問題のあるコンピューターのトラブルシューティングに必要な DaRT 機能のみをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="2eef4-111">Then, on a help desk administrator’s computer, you might install only the DaRT functionality that you must have to troubleshoot a problem computer, such as the DaRT Remote Connection Viewer and the Crash Analyzer.</span></span>

<span data-ttu-id="2eef4-112">DaRT をインストールするには、Windows インストーラファイルを手動で実行するだけでなく、コマンドプロンプトで DaRT をインストールして、SystemCenterConfigurationManager2012 などのエンタープライズソフトウェア展開システムをサポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2eef4-112">In addition to manually running the Windows Installer file to install DaRT, you can also install DaRT at the command prompt to support enterprise software deployment systems such as SystemCenterConfigurationManager2012.</span></span>

[<span data-ttu-id="2eef4-113">DaRT 8.0 を展開する方法</span><span class="sxs-lookup"><span data-stu-id="2eef4-113">How to Deploy DaRT 8.0</span></span>](how-to-deploy-dart-80-dart-8.md)

## <span data-ttu-id="2eef4-114">DaRT 8.0 を変更、修復、または削除する</span><span class="sxs-lookup"><span data-stu-id="2eef4-114">Change, repair, or remove DaRT 8.0</span></span>


<span data-ttu-id="2eef4-115">Dart のインストールファイルをダブルクリックして、実行するアクションに対応するボタンをクリックするか、または Windows のコントロールパネルを使用して、DaRT インストールの変更、修復、または削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2eef4-115">You can change, repair, or remove the DaRT installation by double-clicking the DaRT installation file and then clicking the button that corresponds to the action that you want to perform or through the Windows Control Panel.</span></span>

[<span data-ttu-id="2eef4-116">DaRT 8.0 を変更、修復、削除する方法</span><span class="sxs-lookup"><span data-stu-id="2eef4-116">How to Change, Repair, or Remove DaRT 8.0</span></span>](how-to-change-repair-or-remove-dart-80-dart-8.md)

## <span data-ttu-id="2eef4-117">DaRT 8.0 の入手方法</span><span class="sxs-lookup"><span data-stu-id="2eef4-117">How to get DaRT 8.0</span></span>


<span data-ttu-id="2eef4-118">DaRT ソフトウェアの入手方法については、「 [MDOP の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2eef4-118">To get the DaRT software, see [How to Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="2eef4-119">DaRT 8.0 を管理者コンピューターに展開するためのその他のリソース</span><span class="sxs-lookup"><span data-stu-id="2eef4-119">Other resources for deploying the DaRT 8.0 to administrator computers</span></span>


[<span data-ttu-id="2eef4-120">DaRT 8.0 の展開</span><span class="sxs-lookup"><span data-stu-id="2eef4-120">Deploying DaRT 8.0</span></span>](deploying-dart-80-dart-8.md)

 

 





