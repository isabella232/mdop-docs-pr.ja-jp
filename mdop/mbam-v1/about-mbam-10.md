---
title: MBAM 1.0 の概要
description: MBAM 1.0 の概要
author: dansimp
ms.assetid: 99254aaa-2b30-4b2e-8365-0d4b67a89a0c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: f8cae83bb9c8d756d57766cbcf9a90febf53f54a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824104"
---
# <span data-ttu-id="3036b-103">MBAM 1.0 の概要</span><span class="sxs-lookup"><span data-stu-id="3036b-103">About MBAM 1.0</span></span>


<span data-ttu-id="3036b-104">Microsoft BitLocker の管理と監視 (MBAM) は、BitLocker ドライブ暗号化のための簡素化された管理インターフェイスを提供します。また、紛失したり盗まれたりしたコンピューターのデータ盗難またはデータ漏洩に対する保護を強化します。</span><span class="sxs-lookup"><span data-stu-id="3036b-104">Microsoft BitLocker Administration and Monitoring (MBAM) provides a simplified administrative interface to BitLocker drive encryption and offers enhanced protection against data theft or data exposure for computers that are lost or stolen.</span></span> <span data-ttu-id="3036b-105">BitLocker は、Windows オペレーティングシステムボリュームに保存されているすべてのデータを暗号化します。このデータボリュームには、Windows オペレーティングシステム、休止状態ファイル、ページングファイル、アプリケーション、アプリケーションで使用されるデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3036b-105">BitLocker encrypts all data that is stored on the Windows operating system volume and configured data volumes, which includes the Windows operating system, hibernation and paging files, applications, and the data that is used by applications.</span></span>

<span data-ttu-id="3036b-106">Microsoft BitLocker の管理と監視を使用して、組織に適した BitLocker 暗号化ポリシーオプションを選択して、これらのポリシーに対するクライアントのコンプライアンスを監視し、企業と個々のコンピューターの両方の暗号化の状態を報告することができます。</span><span class="sxs-lookup"><span data-stu-id="3036b-106">With Microsoft BitLocker Administration and Monitoring, you can select the BitLocker encryption policy options that are appropriate for your enterprise so that you can monitor the client compliance with those policies and then report the encryption status of both the enterprise and individual computers.</span></span> <span data-ttu-id="3036b-107">さらに、ユーザーが PIN またはパスワードを忘れた場合や、BIOS またはブートレコードが変更された場合に、回復キーの情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3036b-107">In addition, you can access recovery key information when users forget their PIN or password or when their BIOS or boot record changes.</span></span>

<span data-ttu-id="3036b-108">**注** このガイドでは、BitLocker について詳しくは説明していません。</span><span class="sxs-lookup"><span data-stu-id="3036b-108">**Note** BitLocker is not covered in detail in this guide.</span></span> <span data-ttu-id="3036b-109">BitLocker の概要については、「 [Bitlocker ドライブ暗号化の概要](https://go.microsoft.com/fwlink/p/?LinkId=225013)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3036b-109">For an overview of BitLocker, see [BitLocker Drive Encryption Overview](https://go.microsoft.com/fwlink/p/?LinkId=225013).</span></span>

 

<span data-ttu-id="3036b-110">次のグループは、BitLocker を管理するために MBAM を使用することに関心を持っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3036b-110">The following groups might be interested in using MBAM to manage BitLocker:</span></span>

-   <span data-ttu-id="3036b-111">承認されていない機密データが公開されないようにする必要がある管理者、IT セキュリティの専門家、コンプライアンス責任者</span><span class="sxs-lookup"><span data-stu-id="3036b-111">Administrators, IT security professionals, and compliance officers who are tasked with ensuring that confidential data is not disclosed without authorization</span></span>

-   <span data-ttu-id="3036b-112">リモートまたは支店のコンピューターをセキュリティで保護する責任を負う管理者</span><span class="sxs-lookup"><span data-stu-id="3036b-112">Administrators who are responsible for securing computers in remote or branch offices</span></span>

-   <span data-ttu-id="3036b-113">モバイルのサーバーまたは Windows クライアントコンピューターに責任を持つ管理者</span><span class="sxs-lookup"><span data-stu-id="3036b-113">Administrators who are responsible for servers or Windows client computers that are mobile</span></span>

-   <span data-ttu-id="3036b-114">機密データを含むサーバーの使用停止を担当する管理者</span><span class="sxs-lookup"><span data-stu-id="3036b-114">Administrators who are responsible for decommissioning servers that contain confidential data</span></span>

## <span data-ttu-id="3036b-115">MBAM 1.0 リリースノート</span><span class="sxs-lookup"><span data-stu-id="3036b-115">MBAM 1.0 Release Notes</span></span>


<span data-ttu-id="3036b-116">詳細と最新の更新については、「 [MBAM 1.0 のリリースノート](release-notes-for-mbam-10.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3036b-116">For more information and for latest updates, see [Release Notes for MBAM 1.0](release-notes-for-mbam-10.md).</span></span>

## <span data-ttu-id="3036b-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3036b-117">Related topics</span></span>


[<span data-ttu-id="3036b-118">MBAM 1.0 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="3036b-118">Getting Started with MBAM 1.0</span></span>](getting-started-with-mbam-10.md)

 

 





