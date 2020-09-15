---
title: MBAM 2.5 SP1 への修正プログラムの適用
description: MBAM 2.5 SP1 への修正プログラムの適用
ms.author: dansimp
author: dansimp
ms.assetid: ''
ms.reviewer: ''
manager: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 8/30/2018
ms.openlocfilehash: ea564d93a3eec6a46ec7d4c1be0f794abba9c93e
ms.sourcegitcommit: 8ecbf818a6ff2ddafd80b93614c01256484737ad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "11014991"
---
# <span data-ttu-id="e25da-103">MBAM 2.5 SP1 への修正プログラムの適用</span><span class="sxs-lookup"><span data-stu-id="e25da-103">Applying hotfixes on MBAM 2.5 SP1</span></span>
<span data-ttu-id="e25da-104">このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) Server 2.5 SP1 の修正プログラムを適用するためのプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e25da-104">This topic describes the process for applying the hotfixes for Microsoft BitLocker Administration and Monitoring (MBAM) Server 2.5 SP1</span></span>

### <span data-ttu-id="e25da-105">作業を始める前に、Microsoft BitLocker 管理と監視 (MBAM) Server 2.5 SP1 の最新の修正プログラムをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="e25da-105">Before you begin, download the latest hotfix of Microsoft BitLocker Administration and Monitoring (MBAM) Server 2.5 SP1</span></span>
[<span data-ttu-id="e25da-106">デスクトップ最適化パック</span><span class="sxs-lookup"><span data-stu-id="e25da-106">Desktop Optimization Pack</span></span>](https://www.microsoft.com/download/details.aspx?id=57157)

> [!NOTE]
> <span data-ttu-id="e25da-107">修正プログラムのリリースの詳細については、「 [Mbam バージョングラフ](https://docs.microsoft.com/archive/blogs/dubaisec/mbam-version-chart)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e25da-107">For more information about the hotfix releases, see the [MBAM version chart](https://docs.microsoft.com/archive/blogs/dubaisec/mbam-version-chart).</span></span>

#### <span data-ttu-id="e25da-108">既存の MBAM 環境用の MBAM サーバーを更新する手順</span><span class="sxs-lookup"><span data-stu-id="e25da-108">Steps to update the MBAM Server for existing MBAM environment</span></span> 
1. <span data-ttu-id="e25da-109">MBAM サーバー機能を削除します (これを行うには、MBAM Server 構成ツールを開いてから、[機能の削除] を選びます)。</span><span class="sxs-lookup"><span data-stu-id="e25da-109">Remove MBAM server feature (do this by opening the MBAM Server Configuration Tool, then selecting Remove Features).</span></span>
2. <span data-ttu-id="e25da-110">コントロールパネルから MDOP MBAM を削除します。[プログラムと機能] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e25da-110">Remove MDOP MBAM from Control Panel | Programs and Features.</span></span>
3. <span data-ttu-id="e25da-111">MBAM 2.5 SP1 RTM サーバーコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e25da-111">Install MBAM 2.5 SP1 RTM server components.</span></span>
4. <span data-ttu-id="e25da-112">映像 MBAM 2.5 SP1 修正プログラムのロールアップをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e25da-112">Install lastest MBAM 2.5 SP1 hotfix rollup.</span></span>
5. <span data-ttu-id="e25da-113">MBAM Server Configurator を使用して MBAM 機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="e25da-113">Configure MBAM features using MBAM Server Configurator.</span></span>

#### <span data-ttu-id="e25da-114">新しい MBAM 2.5 SP1 サーバーの修正プログラムをインストールする手順</span><span class="sxs-lookup"><span data-stu-id="e25da-114">Steps to install the new MBAM 2.5 SP1 server hotfix</span></span>
<span data-ttu-id="e25da-115">[新しいサーバーインストール](deploying-the-mbam-25-server-infrastructure.md)のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e25da-115">Refer to the document for [new server installation](deploying-the-mbam-25-server-infrastructure.md).</span></span>
