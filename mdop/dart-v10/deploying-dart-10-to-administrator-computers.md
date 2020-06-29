---
title: 管理者用コンピューターへの DaRT 10 の展開
description: 管理者用コンピューターへの DaRT 10 の展開
author: dansimp
ms.assetid: c1981cbe-10f8-41f6-8989-bcc9d57a2aa8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 020ffab3239c5e56b3505f468035cf5007baf9e2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813131"
---
# <span data-ttu-id="1ba08-103">管理者用コンピューターへの DaRT 10 の展開</span><span class="sxs-lookup"><span data-stu-id="1ba08-103">Deploying DaRT 10 to Administrator Computers</span></span>


<span data-ttu-id="1ba08-104">Microsoft 診断/回復ツールセット (DaRT) 10 の展開を開始する前に、お使いの環境の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="1ba08-104">Before you begin the deployment of Microsoft Diagnostics and Recovery Toolset (DaRT) 10, review the requirements for your environment.</span></span> <span data-ttu-id="1ba08-105">DaRT 10 をインストールするためのハードウェア要件が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1ba08-105">This includes the hardware requirements for installing DaRT 10.</span></span> <span data-ttu-id="1ba08-106">DaRT のハードウェアとソフトウェアの要件の詳細については、「 [dart 10 のサポートされる構成](dart-10-supported-configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ba08-106">For more information about DaRT hardware and software requirements, see [DaRT 10 Supported Configurations](dart-10-supported-configurations.md).</span></span>

<span data-ttu-id="1ba08-107">このセクションのトピックは、環境と展開戦略に基づいて、企業で DaRT を展開するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="1ba08-107">The topics in this section can be used to help you deploy DaRT in your enterprise based on your environment and deployment strategy.</span></span>

## <span data-ttu-id="1ba08-108">DaRT 10 の展開</span><span class="sxs-lookup"><span data-stu-id="1ba08-108">Deploy DaRT 10</span></span>


<span data-ttu-id="1ba08-109">Dart の Windows インストーラファイルを使用して、初めて DaRT リカバリ画像を作成してから、エンドユーザのコンピュータのトラブルシューティングと解決に使用するコンピュータに DaRT をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="1ba08-109">You can use the Windows Installer file for DaRT to install DaRT on a computer that you will use to first create the DaRT recovery image and then troubleshoot and fix end-user computers.</span></span> <span data-ttu-id="1ba08-110">多くの場合、組織全体で、DaRT の回復イメージを作成するために必要な DaRT の機能のみが管理者のコンピューターにインストールされることがあります。</span><span class="sxs-lookup"><span data-stu-id="1ba08-110">Frequently, across an organization, you might install on the administrator computer only the DaRT functionality that you need to create a DaRT recovery image.</span></span> <span data-ttu-id="1ba08-111">次に、ヘルプデスク管理者のコンピューターで、DaRT リモート接続ビューアーやクラッシュアナライザーなどの問題のあるコンピューターのトラブルシューティングに必要な DaRT 機能のみをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="1ba08-111">Then, on a help desk administrator’s computer, you might install only the DaRT functionality that you must have to troubleshoot a problem computer, such as the DaRT Remote Connection Viewer and the Crash Analyzer.</span></span>

<span data-ttu-id="1ba08-112">DaRT をインストールするには、Windows インストーラファイルを手動で実行するだけでなく、コマンドプロンプトで DaRT をインストールして、SystemCenterConfigurationManager2012 などのエンタープライズソフトウェア展開システムをサポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1ba08-112">In addition to manually running the Windows Installer file to install DaRT, you can also install DaRT at the command prompt to support enterprise software deployment systems such as SystemCenterConfigurationManager2012.</span></span>

[<span data-ttu-id="1ba08-113">DaRT 10 を展開する方法</span><span class="sxs-lookup"><span data-stu-id="1ba08-113">How to Deploy DaRT 10</span></span>](how-to-deploy-dart-10.md)

## <span data-ttu-id="1ba08-114">DaRT 10 を変更、修復、または削除する</span><span class="sxs-lookup"><span data-stu-id="1ba08-114">Change, repair, or remove DaRT 10</span></span>


<span data-ttu-id="1ba08-115">Dart のインストールファイルをダブルクリックして、実行するアクションに対応するボタンをクリックするか、または Windows のコントロールパネルを使用して、DaRT インストールの変更、修復、または削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1ba08-115">You can change, repair, or remove the DaRT installation by double-clicking the DaRT installation file and then clicking the button that corresponds to the action that you want to perform or through the Windows Control Panel.</span></span>

[<span data-ttu-id="1ba08-116">DaRT 10 を変更、修復、削除する方法</span><span class="sxs-lookup"><span data-stu-id="1ba08-116">How to Change, Repair, or Remove DaRT 10</span></span>](how-to-change-repair-or-remove-dart-10.md)

## <span data-ttu-id="1ba08-117">DaRT 10 の入手方法</span><span class="sxs-lookup"><span data-stu-id="1ba08-117">How to get DaRT 10</span></span>


<span data-ttu-id="1ba08-118">DaRT ソフトウェアの入手方法については、「 [MDOP の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1ba08-118">To get the DaRT software, see [How to Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="1ba08-119">DaRT 10 を管理者コンピューターに展開するためのその他のリソース</span><span class="sxs-lookup"><span data-stu-id="1ba08-119">Other resources for deploying DaRT 10 to administrator computers</span></span>


[<span data-ttu-id="1ba08-120">DaRT 10 の展開</span><span class="sxs-lookup"><span data-stu-id="1ba08-120">Deploying DaRT 10</span></span>](deploying-dart-10.md)

 

 





