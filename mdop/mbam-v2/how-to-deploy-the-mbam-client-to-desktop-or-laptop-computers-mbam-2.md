---
title: MBAM クライアントをデスクトップまたはノート PC に展開する方法
description: MBAM クライアントをデスクトップまたはノート PC に展開する方法
author: dansimp
ms.assetid: 56744922-bfdd-48f6-ae01-645ff53b64a8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 49340ae970dafc9d263f5564e7981a402da40f19
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813010"
---
# <span data-ttu-id="d802b-103">MBAM クライアントをデスクトップまたはノート PC に展開する方法</span><span class="sxs-lookup"><span data-stu-id="d802b-103">How to Deploy the MBAM Client to Desktop or Laptop Computers</span></span>


<span data-ttu-id="d802b-104">Microsoft BitLocker 管理と監視 (MBAM) クライアントを使うと、管理者は企業内のコンピューター上の BitLocker ドライブ暗号化を強制および監視することができます。</span><span class="sxs-lookup"><span data-stu-id="d802b-104">The Microsoft BitLocker Administration and Monitoring (MBAM) client enables administrators to enforce and monitor BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="d802b-105">Active Directory ドメインサービスや MicrosoftSystemCenterConfigurationManager などの電子ソフトウェア配布システムを使用してクライアントを展開することによって、BitLocker クライアントを組織に統合することができます。</span><span class="sxs-lookup"><span data-stu-id="d802b-105">The BitLocker client can be integrated into an organization by deploying the client through an electronic software distribution system, such as Active Directory Domain Services or MicrosoftSystemCenterConfigurationManager.</span></span>

<span data-ttu-id="d802b-106">**注** Microsoft BitLocker 管理およびクライアントシステム要件の監視については、「 [Mbam 2.0 でサポートされている構成](mbam-20-supported-configurations-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d802b-106">**Note** To review the Microsoft BitLocker Administration and Monitoring Client system requirements, see [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md).</span></span>

 

**<span data-ttu-id="d802b-107">デスクトップまたはラップトップコンピューターに MBAM クライアントを展開するには</span><span class="sxs-lookup"><span data-stu-id="d802b-107">To deploy the MBAM Client to desktop or laptop computers</span></span>**

1.  <span data-ttu-id="d802b-108">MBAM ソフトウェアに付属の MBAM クライアントインストールファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="d802b-108">Locate the MBAM client installation files that are provided with the MBAM software.</span></span>

2.  <span data-ttu-id="d802b-109">Active Directory ドメインサービス、または MicrosoftSystemCenterConfigurationManager などのエンタープライズソフトウェア展開ツールを使用して、Windows インストーラーパッケージをターゲットコンピューターに展開します。</span><span class="sxs-lookup"><span data-stu-id="d802b-109">Use Active Directory Domain Services or an enterprise software deployment tool like MicrosoftSystemCenterConfigurationManager to deploy the Windows Installer package to target computers.</span></span>

3.  <span data-ttu-id="d802b-110">MBAM クライアントインストールファイルを実行するように配布設定またはグループポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="d802b-110">Configure the distribution settings or Group Policy to run the MBAM Client installation file.</span></span> <span data-ttu-id="d802b-111">インストールが正常に完了すると、MBAM クライアントによって、ドメインコントローラーから受信したグループポリシー設定が適用され、BitLocker の暗号化と管理の機能が開始されます。</span><span class="sxs-lookup"><span data-stu-id="d802b-111">After successful installation, the MBAM Client applies the Group Policy settings that are received from a domain controller to begin BitLocker encryption and management functions.</span></span> <span data-ttu-id="d802b-112">MBAM グループポリシー設定の詳細については、「 [mbam 2.0 グループポリシーの要件を計画する](planning-for-mbam-20-group-policy-requirements-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d802b-112">For more information about MBAM group policy settings, see [Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md).</span></span>

    <span data-ttu-id="d802b-113">**重要** MBAM クライアントは、リモートデスクトッププロトコル接続がアクティブな場合は、BitLocker 暗号化アクションを開始しません。</span><span class="sxs-lookup"><span data-stu-id="d802b-113">**Important** The MBAM Client will not start BitLocker encryption actions if a remote desktop protocol connection is active.</span></span> <span data-ttu-id="d802b-114">BitLocker 暗号化を開始する前に、すべてのリモートコンソール接続を閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d802b-114">All remote console connections must be closed before BitLocker encryption will begin.</span></span>

     

## <span data-ttu-id="d802b-115">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d802b-115">Related topics</span></span>


[<span data-ttu-id="d802b-116">MBAM 2.0 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="d802b-116">Deploying the MBAM 2.0 Client</span></span>](deploying-the-mbam-20-client-mbam-2.md)

 

 





