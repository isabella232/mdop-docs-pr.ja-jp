---
title: MBAM 1.0 の保守
description: MBAM 1.0 の保守
author: dansimp
ms.assetid: 02ffb093-c364-4837-bbe8-23d4c09fbd3d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7eecef4e82680b08fde1b1bef88487a6fc156fe4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825774"
---
# <span data-ttu-id="94445-103">MBAM 1.0 の保守</span><span class="sxs-lookup"><span data-stu-id="94445-103">Maintaining MBAM 1.0</span></span>


<span data-ttu-id="94445-104">必要な計画がすべて完了して、Microsoft BitLocker の管理と監視 (MBAM) を展開した後、MBAM を高可用性の方法で実行し、エンタープライズの BitLocker 暗号化操作の管理に使用します。</span><span class="sxs-lookup"><span data-stu-id="94445-104">After you complete all the necessary planning and then deploy Microsoft BitLocker Administration and Monitoring (MBAM), you can configure MBAM to run in a highly available fashion while using it to manage enterprise BitLocker encryption operations.</span></span> <span data-ttu-id="94445-105">このセクションの情報では、MBAM の高可用性オプションについて説明し、必要に応じて MBAM サーバー機能を移動する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="94445-105">The information in this section describes high availability options for MBAM, as well as how to move MBAM Server features if necessary.</span></span>

## <span data-ttu-id="94445-106">MBAM 管理パック</span><span class="sxs-lookup"><span data-stu-id="94445-106">MBAM Management Pack</span></span>


<span data-ttu-id="94445-107">MBAM 用の MicrosoftSystemCenterOperationsManager 管理パックは、Microsoft ダウンロードセンターからダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="94445-107">The MicrosoftSystemCenterOperationsManager Management Pack for MBAM is available for download from the Microsoft Download Center.</span></span>

<span data-ttu-id="94445-108">この管理パックは、web サービスとデータベース間の接続、web サイトとそのサービスの管理 web サービスとの間の通信など、サーバー側インフラストラクチャでの重要な操作を監視します。</span><span class="sxs-lookup"><span data-stu-id="94445-108">This management pack monitors the critical interactions in the server-side infrastructure, such as the connections between the web services and databases and the operational calls between websites and their supportive web service.</span></span> <span data-ttu-id="94445-109">また、デスクトップクライアントとその受信 web サービスエンドポイントの間の要求もアップロードします。</span><span class="sxs-lookup"><span data-stu-id="94445-109">It also uploads the requests between desktop clients and their respective receiving web service endpoints.</span></span>

[<span data-ttu-id="94445-110">Microsoft BitLocker 管理パックと監視管理パック</span><span class="sxs-lookup"><span data-stu-id="94445-110">Microsoft BitLocker Administration And Monitoring Management Pack</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=258390)

## <span data-ttu-id="94445-111">MBAM 1.0 の高可用性を確保する</span><span class="sxs-lookup"><span data-stu-id="94445-111">Ensure high availability for MBAM 1.0</span></span>


<span data-ttu-id="94445-112">MBAM はフォールトトレラントとして設計されています。</span><span class="sxs-lookup"><span data-stu-id="94445-112">MBAM is designed to be fault-tolerant.</span></span> <span data-ttu-id="94445-113">サーバーが利用できなくなった場合は、ユーザーに悪影響を与えないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="94445-113">If a server becomes unavailable, the users should not be negatively affected.</span></span> <span data-ttu-id="94445-114">このセクションの情報は、高可用性の MBAM インストールを構成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="94445-114">The information in this section can be used to configure a highly available MBAM installation.</span></span>

[<span data-ttu-id="94445-115">MBAM 1.0 の高可用性</span><span class="sxs-lookup"><span data-stu-id="94445-115">High Availability for MBAM 1.0</span></span>](high-availability-for-mbam-10.md)

## <span data-ttu-id="94445-116">MBAM 1.0 機能を別のサーバーに移動する</span><span class="sxs-lookup"><span data-stu-id="94445-116">Move MBAM 1.0 features to another server</span></span>


<span data-ttu-id="94445-117">MBAM サーバー機能をサーバーコンピューター間で移動する必要がある場合は、特定の順序と必須の手順を実行して、生産性やデータの損失を回避する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94445-117">When you need to move an MBAM Server feature from one server computer to another, there is a specific order and required steps that you should follow to avoid loss of productivity or data.</span></span> <span data-ttu-id="94445-118">このセクションでは、1つまたは複数の MBAM サーバー機能を別のコンピューターに移動するために実行する必要のある手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="94445-118">This section describes the steps that you should take to move one or more MBAM Server features to a different computer.</span></span>

[<span data-ttu-id="94445-119">MBAM 1.0 機能を別のコンピューターに移動する方法</span><span class="sxs-lookup"><span data-stu-id="94445-119">How to Move MBAM 1.0 Features to Another Computer</span></span>](how-to-move-mbam-10-features-to-another-computer.md)

## <span data-ttu-id="94445-120">MBAM を管理するためのその他のリソース</span><span class="sxs-lookup"><span data-stu-id="94445-120">Other resources for maintaining MBAM</span></span>


[<span data-ttu-id="94445-121">MBAM 1.0 の操作</span><span class="sxs-lookup"><span data-stu-id="94445-121">Operations for MBAM 1.0</span></span>](operations-for-mbam-10.md)

 

 





