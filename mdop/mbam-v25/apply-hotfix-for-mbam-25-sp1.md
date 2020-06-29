---
title: MBAM 2.5 SP1 への修正プログラムの適用
description: MBAM 2.5 SP1 への修正プログラムの適用
ms.author: ppriya-msft
author: dansimp
ms.assetid: ''
ms.reviewer: ''
manager: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 8/30/2018
ms.openlocfilehash: 71f840ce4d57a0698289128f92b9d760ca14ddfc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824187"
---
# <span data-ttu-id="43c40-103">MBAM 2.5 SP1 への修正プログラムの適用</span><span class="sxs-lookup"><span data-stu-id="43c40-103">Applying hotfixes on MBAM 2.5 SP1</span></span>
<span data-ttu-id="43c40-104">このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) Server 2.5 SP1 の修正プログラムを適用するためのプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="43c40-104">This topic describes the process for applying the hotfixes for Microsoft BitLocker Administration and Monitoring (MBAM) Server 2.5 SP1</span></span>

### <span data-ttu-id="43c40-105">作業を始める前に、Microsoft BitLocker 管理と監視 (MBAM) Server 2.5 SP1 の最新の修正プログラムをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="43c40-105">Before you begin, download the latest hotfix of Microsoft BitLocker Administration and Monitoring (MBAM) Server 2.5 SP1</span></span>
[<span data-ttu-id="43c40-106">デスクトップ最適化パック</span><span class="sxs-lookup"><span data-stu-id="43c40-106">Desktop Optimization Pack</span></span>](https://www.microsoft.com/download/details.aspx?id=57157)

> [!NOTE]
> <span data-ttu-id="43c40-107">修正プログラムのリリースの詳細については、「 [Mbam バージョングラフ](https://docs.microsoft.com/archive/blogs/dubaisec/mbam-version-chart)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43c40-107">For more information about the hotfix releases, see the [MBAM version chart](https://docs.microsoft.com/archive/blogs/dubaisec/mbam-version-chart).</span></span>

#### <span data-ttu-id="43c40-108">既存の MBAM 環境用の MBAM サーバーを更新する手順</span><span class="sxs-lookup"><span data-stu-id="43c40-108">Steps to update the MBAM Server for existing MBAM environment</span></span> 
1. <span data-ttu-id="43c40-109">MBAM サーバー機能を削除します (これを行うには、MBAM Server 構成ツールを開いてから、[機能の削除] を選びます)。</span><span class="sxs-lookup"><span data-stu-id="43c40-109">Remove MBAM server feature (do this by opening the MBAM Server Configuration Tool, then selecting Remove Features).</span></span>
2. <span data-ttu-id="43c40-110">コントロールパネルから MDOP MBAM を削除します。[プログラムと機能] を選びます。</span><span class="sxs-lookup"><span data-stu-id="43c40-110">Remove MDOP MBAM from Control Panel | Programs and Features.</span></span>
3. <span data-ttu-id="43c40-111">MBAM 2.5 SP1 RTM サーバーコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="43c40-111">Install MBAM 2.5 SP1 RTM server components.</span></span>
4. <span data-ttu-id="43c40-112">映像 MBAM 2.5 SP1 修正プログラムのロールアップをインストールします。</span><span class="sxs-lookup"><span data-stu-id="43c40-112">Install lastest MBAM 2.5 SP1 hotfix rollup.</span></span>
5. <span data-ttu-id="43c40-113">MBAM Server Configurator を使用して MBAM 機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="43c40-113">Configure MBAM features using MBAM Server Configurator.</span></span>

#### <span data-ttu-id="43c40-114">新しい MBAM 2.5 SP1 サーバーの修正プログラムをインストールする手順</span><span class="sxs-lookup"><span data-stu-id="43c40-114">Steps to install the new MBAM 2.5 SP1 server hotfix</span></span>
<span data-ttu-id="43c40-115">[新しいサーバーインストール](deploying-the-mbam-25-server-infrastructure.md)のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="43c40-115">Refer to the document for [new server installation](deploying-the-mbam-25-server-infrastructure.md).</span></span>
