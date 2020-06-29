---
title: MBAM 2.0 の高可用性
description: MBAM 2.0 の高可用性
author: dansimp
ms.assetid: 244ee013-9e2a-48d2-b842-4e10594fd74f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6482a099d96aee731f81368b8b787325e592c453
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824727"
---
# <span data-ttu-id="0aa02-103">MBAM 2.0 の高可用性</span><span class="sxs-lookup"><span data-stu-id="0aa02-103">High Availability for MBAM 2.0</span></span>


<span data-ttu-id="0aa02-104">このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) の高可用性インストールに関する基本情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="0aa02-104">This topic provides basic information about a highly available installation of Microsoft BitLocker Administration and Monitoring (MBAM).</span></span> <span data-ttu-id="0aa02-105">このバージョンの MBAM では、高可用性シナリオが完全にはサポートされていないため、ここでは説明しません。</span><span class="sxs-lookup"><span data-stu-id="0aa02-105">High-availability scenarios are not fully supported in this version of MBAM, so they are not described here.</span></span> <span data-ttu-id="0aa02-106">関連するブログとフォーラムを検索することをお勧めします。ここでは、ユーザーが環境内で MBAM の高可用性を正しく設定した方法を説明しています。</span><span class="sxs-lookup"><span data-stu-id="0aa02-106">It is recommended that you search related blogs and forums, where users describe how they have successfully configured high availability for MBAM in their environments.</span></span>

## <span data-ttu-id="0aa02-107">MBAM の高可用性シナリオ</span><span class="sxs-lookup"><span data-stu-id="0aa02-107">High Availability Scenarios for MBAM</span></span>


<span data-ttu-id="0aa02-108">Microsoft BitLocker の管理と監視は、フォールトトレラントとして設計されています。</span><span class="sxs-lookup"><span data-stu-id="0aa02-108">Microsoft BitLocker Administration and Monitoring is designed to be fault-tolerant.</span></span> <span data-ttu-id="0aa02-109">サーバーが利用できなくなった場合、ユーザーは悪影響を受けないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="0aa02-109">If a server becomes unavailable, users should not be negatively affected.</span></span> <span data-ttu-id="0aa02-110">たとえば、MBAM エージェントが MBAM web サーバーに接続できない場合、ユーザーに操作の確認を求めるメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="0aa02-110">For example, if the MBAM agent cannot connect to the MBAM web server, users should not be prompted for action.</span></span>

<span data-ttu-id="0aa02-111">MBAM のインストールを計画する場合は、次の項目を考慮してください。これは、MBAM サービスの可用性に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0aa02-111">When you plan your MBAM installation, consider the following items, which can affect the availability of the MBAM service:</span></span>

-   <span data-ttu-id="0aa02-112">ドライブの暗号化と回復パスワード–回復パスワードを預託たりできない場合、クライアントコンピューターでは暗号化は開始されません。</span><span class="sxs-lookup"><span data-stu-id="0aa02-112">Drive encryption and recovery password – If a recovery password cannot be escrowed, the encryption does not start on the client computer.</span></span>

-   <span data-ttu-id="0aa02-113">コンプライアンスステータスデータアップロード–コンプライアンスステータスレポートサービスをホストしているサーバーが利用できない場合、コンプライアンスデータは最新のままになりません。</span><span class="sxs-lookup"><span data-stu-id="0aa02-113">Compliance status data upload – If the server that hosts the compliance status report service is not available, the compliance data does not remain current.</span></span>

-   <span data-ttu-id="0aa02-114">ヘルプデスクの回復キーアクセス-ヘルプデスクが MBAM データベース情報にアクセスできない場合、ヘルプデスクはユーザーに回復キーを提供できません。</span><span class="sxs-lookup"><span data-stu-id="0aa02-114">Help Desk recovery key access - If the Help Desk cannot access MBAM database information, the Help Desk cannot provide recovery keys to users.</span></span>

-   <span data-ttu-id="0aa02-115">レポートの可用性–コンプライアンスレポートおよび監査レポートをホストしているサーバーが利用できない場合、レポートは使用できません。</span><span class="sxs-lookup"><span data-stu-id="0aa02-115">Availability of reports –If the server that hosts the Compliance and Audit Reports is not available, reports will not be available.</span></span>

## <a href="" id="how-the-mbam-backup-uses-the-volume-shadow-copy-service--vss--"></a><span data-ttu-id="0aa02-116">MBAM バックアップがボリュームシャドウコピーサービス (VSS) を使用する方法</span><span class="sxs-lookup"><span data-stu-id="0aa02-116">How the MBAM Backup Uses the Volume Shadow Copy Service (VSS)</span></span>


<span data-ttu-id="0aa02-117">MBAM 2.0 は、Microsoft BitLocker 管理および管理ライターと呼ばれるボリュームシャドウコピーサービス (VSS) ライターを提供します。これにより、コンプライアンスと監査データベースおよび回復データベースのバックアップが容易になります。</span><span class="sxs-lookup"><span data-stu-id="0aa02-117">MBAM2.0 provides a Volume Shadow Copy Service (VSS) writer, called the Microsoft BitLocker Administration and Management Writer, which facilitates the backup of the Compliance and Audit Database and the Recovery Database.</span></span>

<span data-ttu-id="0aa02-118">MBAM Server Windows Installer は、MBAM VSS ライターを登録します。</span><span class="sxs-lookup"><span data-stu-id="0aa02-118">The MBAM Server Windows Installer registers the MBAM VSS Writer.</span></span> <span data-ttu-id="0aa02-119">VSS ライター登録中にエラーが発生すると、MBAM サーバーのインストールがロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="0aa02-119">Any failure during the VSS writer registration causes the MBAM Server installation to roll back.</span></span> <span data-ttu-id="0aa02-120">コンプライアンスと監査データベースと回復データベースが異なるサーバーにインストールされているトポロジでは、MBAM VSS Writer の個別のインスタンスが各サーバーに登録されます。</span><span class="sxs-lookup"><span data-stu-id="0aa02-120">In a topology where the Compliance and Audit Database and the Recovery Database are installed on different servers, a separate instance of MBAM VSS Writer is registered on each server.</span></span> <span data-ttu-id="0aa02-121">MBAM VSS Writer は、SQL Server VSS Writer に依存しています。</span><span class="sxs-lookup"><span data-stu-id="0aa02-121">The MBAM VSS Writer is dependent on the SQL Server VSS Writer.</span></span> <span data-ttu-id="0aa02-122">SQL Server VSS Writer は、Microsoft SQL Server インストールの一部として登録されています。</span><span class="sxs-lookup"><span data-stu-id="0aa02-122">The SQL Server VSS Writer is registered as part of the Microsoft SQL Server installation.</span></span> <span data-ttu-id="0aa02-123">VSS ライターを使用してバックアップを実行するすべてのバックアップテクノロジは、MBAM VSS ライターを検出できます。</span><span class="sxs-lookup"><span data-stu-id="0aa02-123">Any backup technology that uses VSS writers to perform backup can discover the MBAM VSS Writer.</span></span>

## <span data-ttu-id="0aa02-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0aa02-124">Related topics</span></span>


[<span data-ttu-id="0aa02-125">MBAM 2.0 の保守</span><span class="sxs-lookup"><span data-stu-id="0aa02-125">Maintaining MBAM 2.0</span></span>](maintaining-mbam-20-mbam-2.md)

 

 





