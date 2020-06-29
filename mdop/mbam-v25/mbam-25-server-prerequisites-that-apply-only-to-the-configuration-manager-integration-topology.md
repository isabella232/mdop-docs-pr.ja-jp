---
title: Configuration Manager 統合トポロジのみに適用される MBAM 2.5 サーバー前提条件
description: Configuration Manager 統合トポロジのみに適用される MBAM 2.5 サーバー前提条件
author: dansimp
ms.assetid: 74180d8d-7b0f-460f-b301-53595cde8381
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dd9b89e1a1383997d6ebc92f8e034fbf2945823f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812563"
---
# <span data-ttu-id="42be6-103">Configuration Manager 統合トポロジのみに適用される MBAM 2.5 サーバー前提条件</span><span class="sxs-lookup"><span data-stu-id="42be6-103">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</span></span>


<span data-ttu-id="42be6-104">System Center Configuration Manager の統合機能を使用して Microsoft BitLocker 管理および監視 (MBAM) 2.5 をインストールしている場合は、このトピックで説明されている前提条件と、[スタンドアロンおよび Configuration manager の統合トポロジに関する Mbam 2.5 サーバーの前提条件](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)に加えて、このトピックで説明する前提条件を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42be6-104">If you are installing Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 by using the System Center Configuration Manager Integration feature, you must complete the prerequisites described in this topic, in addition to those in [MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md).</span></span> <span data-ttu-id="42be6-105">また、構成マネージャーの統合トポロジに必要な .mof ファイルを作成または変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42be6-105">You must also create or modify .mof files that are needed for the Configuration Manager Integration topology.</span></span>

## <span data-ttu-id="42be6-106">Configuration Manager 統合機能の前提条件</span><span class="sxs-lookup"><span data-stu-id="42be6-106">Prerequisites for the Configuration Manager Integration Feature</span></span>


<span data-ttu-id="42be6-107">System Center Configuration Manager の統合トポロジで MBAM を構成する場合は、構成マネージャーに必要なその他の前提条件を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42be6-107">If you are configuring MBAM with the System Center Configuration Manager Integration topology, you must complete additional prerequisites that are required for Configuration Manager.</span></span>

[<span data-ttu-id="42be6-108">Configuration Manager 統合機能の前提条件</span><span class="sxs-lookup"><span data-stu-id="42be6-108">Prerequisites for the Configuration Manager Integration Feature</span></span>](prerequisites-for-the-configuration-manager-integration-feature.md)

## <span data-ttu-id="42be6-109">構成の .mof ファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="42be6-109">Edit the Configuration.mof file</span></span>


<span data-ttu-id="42be6-110">MBAM Configuration Manager レポートでクライアントコンピューターが BitLocker のコンプライアンスの詳細を報告できるようにするには、SystemCenter2012 ConfigurationManager と Microsoft System Center Configuration Manager 2007 用の構成の .mof ファイルを編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42be6-110">To enable the client computers to report BitLocker compliance details through the MBAM Configuration Manager Reports, you have to edit the Configuration.mof file for SystemCenter2012 ConfigurationManager and Microsoft System Center Configuration Manager 2007.</span></span>

[<span data-ttu-id="42be6-111">Configuration.mof ファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="42be6-111">Edit the Configuration.mof File</span></span>](edit-the-configurationmof-file-mbam-25.md)

## <a href="" id="create-or-edit-the-sms-def-mof-file"></a><span data-ttu-id="42be6-112">Sms \ _def ファイルを作成または編集する</span><span class="sxs-lookup"><span data-stu-id="42be6-112">Create or edit the Sms\_def.mof file</span></span>


<span data-ttu-id="42be6-113">MBAM Configuration Manager のレポートでクライアントコンピューターが BitLocker の準拠の詳細を報告できるようにするには、Sms \ _def .mof ファイルを作成または編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42be6-113">To enable the client computers to report BitLocker compliance details in the MBAM Configuration Manager Reports, you have to create or edit the Sms\_def.mof file.</span></span> <span data-ttu-id="42be6-114">SystemCenter2012 ConfigurationManager を使用している場合は、ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42be6-114">If you are using SystemCenter2012 ConfigurationManager, you must create the file.</span></span> <span data-ttu-id="42be6-115">Configuration Manager 2007 では、ファイルが既に存在するため、既存のファイルを編集することはできますが、上書きする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="42be6-115">In Configuration Manager 2007, the file already exists, so you need to edit, but not overwrite, the existing file.</span></span>

[<span data-ttu-id="42be6-116">Sms \ _def ファイルを作成または編集する</span><span class="sxs-lookup"><span data-stu-id="42be6-116">Create or Edit the Sms\_def.mof File</span></span>](create-or-edit-the-sms-defmof-file-mbam-25.md)


## <span data-ttu-id="42be6-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="42be6-117">Related topics</span></span>


[<span data-ttu-id="42be6-118">MBAM 2.5 に対応する環境の準備</span><span class="sxs-lookup"><span data-stu-id="42be6-118">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)

[<span data-ttu-id="42be6-119">MBAM 2.5 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="42be6-119">MBAM 2.5 Supported Configurations</span></span>](mbam-25-supported-configurations.md)

[<span data-ttu-id="42be6-120">MBAM 2.5 の展開計画</span><span class="sxs-lookup"><span data-stu-id="42be6-120">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

 

 
## <span data-ttu-id="42be6-121">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="42be6-121">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="42be6-122">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="42be6-122">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="42be6-123">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="42be6-123">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




