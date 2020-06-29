---
title: MBAM 1.0 の高可用性
description: MBAM 1.0 の高可用性
author: dansimp
ms.assetid: 5869ecf8-1056-4c32-aecb-838a37e05d39
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 1227967d647cbfbc16967b5936066fd73d2412e2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825364"
---
# <span data-ttu-id="123a0-103">MBAM 1.0 の高可用性</span><span class="sxs-lookup"><span data-stu-id="123a0-103">High Availability for MBAM 1.0</span></span>


<span data-ttu-id="123a0-104">このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) の可用性の高いインストールを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="123a0-104">This topic describes how to configure a highly available installation of Microsoft BitLocker Administration and Monitoring (MBAM).</span></span>

## <span data-ttu-id="123a0-105">MBAM の高可用性シナリオ</span><span class="sxs-lookup"><span data-stu-id="123a0-105">High Availability Scenarios for MBAM</span></span>


<span data-ttu-id="123a0-106">Microsoft BitLocker の管理と監視 (MBAM) は、フォールトトレラントとして設計されています。</span><span class="sxs-lookup"><span data-stu-id="123a0-106">Microsoft BitLocker Administration and Monitoring (MBAM) is designed to be fault-tolerant.</span></span> <span data-ttu-id="123a0-107">サーバーが利用できなくなった場合は、ユーザーに悪影響を与えないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="123a0-107">If a server becomes unavailable, the users should not be negatively affected.</span></span> <span data-ttu-id="123a0-108">たとえば、MBAM エージェントが MBAM web サーバーに接続できない場合、ユーザーに操作の確認を求めるメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="123a0-108">For example, if the MBAM agent cannot connect to the MBAM web server, users should not be prompted for action.</span></span>

<span data-ttu-id="123a0-109">MBAM のインストールを計画する場合は、MBAM サービスの可用性に影響を与える可能性のある次の事項を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="123a0-109">When you plan your MBAM installation, consider the following concerns that can affect the availability of the MBAM service:</span></span>

-   <span data-ttu-id="123a0-110">ドライブの暗号化と回復パスワード–回復パスワードを預託たりできない場合、クライアントコンピューターでは暗号化が開始されません。</span><span class="sxs-lookup"><span data-stu-id="123a0-110">Drive encryption and recovery password – If a recovery password cannot be escrowed, the encryption will not start on the client computer.</span></span>

-   <span data-ttu-id="123a0-111">コンプライアンスステータスデータアップロード–コンプライアンスステータスレポートサービスをホストしているサーバーが利用できない場合は、コンプライアンスデータは最新のままになりません。</span><span class="sxs-lookup"><span data-stu-id="123a0-111">Compliance status data upload – If the server that hosts the compliance status report service is not available, the compliance data will not remain current.</span></span>

-   <span data-ttu-id="123a0-112">ヘルプデスク回復キーアクセス-ヘルプデスクが MBAM データベース情報にアクセスできない場合、ユーザーに回復キーを提供することはできません。</span><span class="sxs-lookup"><span data-stu-id="123a0-112">Help Desk recovery key access - If the Help Desk cannot access MBAM database information, they will be unable to provide recovery keys to users.</span></span>

-   <span data-ttu-id="123a0-113">レポートの可用性–コンプライアンスと監査レポートをホストしているサーバーが使用できない場合、レポートは使用できません。</span><span class="sxs-lookup"><span data-stu-id="123a0-113">Availability of reports – Reports will not be available if the server that hosts the Compliance and Audit Reports is not available.</span></span>

<span data-ttu-id="123a0-114">MBAM 高可用性の主な懸念は、BitLocker キー復元の可用性です。</span><span class="sxs-lookup"><span data-stu-id="123a0-114">The main concern for MBAM high availability is BitLocker key recovery availability.</span></span> <span data-ttu-id="123a0-115">ヘルプデスクが回復キーを提供できない場合、ロックされているユーザーはコンピューターのロックを解除できません。</span><span class="sxs-lookup"><span data-stu-id="123a0-115">If the help desk cannot provide recovery keys, users who are locked out cannot unlock their computers.</span></span> <span data-ttu-id="123a0-116">この問題を回避するには、高可用性を確保するために、冗長な web サーバーとデータベースを実装することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="123a0-116">To avoid this problem, consider implementing redundant web servers and databases to ensure high availability.</span></span>

<span data-ttu-id="123a0-117">MBAM スケーラビリティと高可用性の詳細については、「 [Mbam スケーラビリティーのホワイトペーパー](https://go.microsoft.com/fwlink/p/?LinkId=229025) (」を参照してください https://go.microsoft.com/fwlink/p/?LinkId=229025) 。</span><span class="sxs-lookup"><span data-stu-id="123a0-117">For more information about MBAM scalability and high availability, see the [MBAM Scalability White Paper](https://go.microsoft.com/fwlink/p/?LinkId=229025) (https://go.microsoft.com/fwlink/p/?LinkId=229025).</span></span>

<span data-ttu-id="123a0-118">Microsoft SQL Server の高可用性の一般的なガイダンスについては、「[高可用性](https://go.microsoft.com/fwlink/p/?LinkId=221504)()」を参照してください https://go.microsoft.com/fwlink/p/?LinkId=221504) 。</span><span class="sxs-lookup"><span data-stu-id="123a0-118">For general guidance on high availability for Microsoft SQL Server, see [High Availability](https://go.microsoft.com/fwlink/p/?LinkId=221504) (https://go.microsoft.com/fwlink/p/?LinkId=221504).</span></span>

<span data-ttu-id="123a0-119">Web サーバーの可用性とスケーラビリティに関する一般的なガイダンスについては、「[可用性とスケーラビリティ](https://go.microsoft.com/fwlink/p/?LinkId=221503)(」を参照してください https://go.microsoft.com/fwlink/p/?LinkId=221503) 。</span><span class="sxs-lookup"><span data-stu-id="123a0-119">For general guidance on availability and scalability for web servers, see [Availability and Scalability](https://go.microsoft.com/fwlink/p/?LinkId=221503) (https://go.microsoft.com/fwlink/p/?LinkId=221503).</span></span>

## <span data-ttu-id="123a0-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="123a0-120">Related topics</span></span>


[<span data-ttu-id="123a0-121">MBAM 1.0 の保守</span><span class="sxs-lookup"><span data-stu-id="123a0-121">Maintaining MBAM 1.0</span></span>](maintaining-mbam-10.md)

 

 





