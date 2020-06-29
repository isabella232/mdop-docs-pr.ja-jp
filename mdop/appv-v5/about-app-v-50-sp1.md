---
title: App-V 5.0 SP1 について
description: App-V 5.0 SP1 について
author: dansimp
ms.assetid: 2848a51b-452e-4c70-b465-f6717cfa667f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 82769f9d6ab9114fa8d79470b249eacfc4c9180a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815007"
---
# <span data-ttu-id="84997-103">App-V 5.0 SP1 について</span><span class="sxs-lookup"><span data-stu-id="84997-103">About App-V 5.0 SP1</span></span>


<span data-ttu-id="84997-104">この service pack には、次の変更が含まれています。</span><span class="sxs-lookup"><span data-stu-id="84997-104">This service pack contains the following changes:</span></span>

-   <span data-ttu-id="84997-105">App-v 5.0 sequencer と App-v 5.0 クライアントは、21個の言語をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="84997-105">The App-V 5.0 sequencer and App-V 5.0 client now support twenty-four languages.</span></span> <span data-ttu-id="84997-106">**ボリュームライセンスサービスセンター**を使用して、追加の言語パックをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="84997-106">You can download the additional language packs using the **Volume Licensing Service Center**.</span></span>

-   <span data-ttu-id="84997-107">App-v 5.0 server では、11言語がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="84997-107">The App-V 5.0 server now supports eleven languages.</span></span> <span data-ttu-id="84997-108">**ボリュームライセンスサービスセンター**を使用して、追加の言語パックをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="84997-108">You can download the additional language packs using the **Volume Licensing Service Center**.</span></span>

-   <span data-ttu-id="84997-109">App-V 5.0 ボリュームシャドウコピーサービス (VSS) ライター機能のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="84997-109">Support has been added for the App-V 5.0 Volume Shadow Copy Service (VSS) Writer feature.</span></span>

    <span data-ttu-id="84997-110">**重要** VSS と App-v 5.0 を使用するには、更新されたデータベース名を使用して、次のサーバーレジストリキーの値を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84997-110">**Important** To use VSS and App-V 5.0 you must modify the values for the following server registry keys with the updated database names:</span></span>

    -   <span data-ttu-id="84997-111">管理- **HKEY \ _LOCAL \ _MACHINE**  \\  **SOFTWARE**  \\  **Microsoft**  \\  **AppV**  \\  **Server**  \\  **ManagementService**  \\  **MANAGEMENT \ _DB \ _NAME**</span><span class="sxs-lookup"><span data-stu-id="84997-111">Management - **HKEY\_LOCAL\_MACHINE** \\ **SOFTWARE** \\ **Microsoft** \\ **AppV** \\ **Server** \\ **ManagementService** \\ **MANAGEMENT\_DB\_NAME**</span></span>

    -   <span data-ttu-id="84997-112">レポート- **HKEY \ _LOCAL \ _MACHINE**  \\  **SOFTWARE**  \\  **Microsoft**  \\  **AppV**  \\  **Server**  \\  **reportingservice**  \\  **レポート \ _DB \ _NAME**</span><span class="sxs-lookup"><span data-stu-id="84997-112">Reporting - **HKEY\_LOCAL\_MACHINE** \\ **SOFTWARE** \\ **Microsoft** \\ **AppV** \\ **Server** \\ **ReportingService** \\ **REPORTING\_DB\_NAME**</span></span>

     

## <span data-ttu-id="84997-113">MDOP 技術の入手方法</span><span class="sxs-lookup"><span data-stu-id="84997-113">How to Get MDOP Technologies</span></span>


<span data-ttu-id="84997-114">App-v 5.0 は、Microsoft デスクトップ最適化パック (MDOP) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="84997-114">App-V 5.0 is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="84997-115">MDOP は、Microsoft ソフトウェアアシュアランスの一部です。</span><span class="sxs-lookup"><span data-stu-id="84997-115">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="84997-116">Microsoft ソフトウェアアシュアランスの詳細と MDOP の入手方法については、「 [mdop の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」を参照してください https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="84997-116">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>






## <span data-ttu-id="84997-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="84997-117">Related topics</span></span>


[<span data-ttu-id="84997-118">App-V 5.0 SP1 の新機能</span><span class="sxs-lookup"><span data-stu-id="84997-118">What's new in App-V 5.0 SP1</span></span>](whats-new-in-app-v-50-sp1.md)

[<span data-ttu-id="84997-119">App-V 5.0 SP1 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="84997-119">Release Notes for App-V 5.0 SP1</span></span>](release-notes-for-app-v-50-sp1.md)

 

 





