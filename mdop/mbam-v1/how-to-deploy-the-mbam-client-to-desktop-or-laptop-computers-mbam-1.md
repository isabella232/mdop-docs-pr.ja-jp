---
title: MBAM クライアントをデスクトップまたはノート PC に展開する方法
description: MBAM クライアントをデスクトップまたはノート PC に展開する方法
author: dansimp
ms.assetid: f32927a2-4c05-4da8-acca-1108d1dfdb7e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ce4f8597cc182c037983a89efd60c5ef935712ce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825544"
---
# <span data-ttu-id="db380-103">MBAM クライアントをデスクトップまたはノート PC に展開する方法</span><span class="sxs-lookup"><span data-stu-id="db380-103">How to Deploy the MBAM Client to Desktop or Laptop Computers</span></span>


<span data-ttu-id="db380-104">Microsoft BitLocker 管理と監視 (MBAM) クライアントを使うと、管理者は企業内のコンピューター上の BitLocker ドライブ暗号化を強制および監視することができます。</span><span class="sxs-lookup"><span data-stu-id="db380-104">The Microsoft BitLocker Administration and Monitoring (MBAM) Client enables administrators to enforce and monitor BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="db380-105">MBAM クライアントは、Active Directory ドメインサービスなどのツール、または MicrosoftSystemCenter2012 ConfigurationManager などのエンタープライズソフトウェア展開ツールなどのツールを使用してクライアントを展開することで、組織に統合することができます。</span><span class="sxs-lookup"><span data-stu-id="db380-105">The MBAM Client can be integrated into an organization by deploying the client through tools, such as Active Directory Domain Services or an enterprise software deployment tool such as MicrosoftSystemCenter2012 ConfigurationManager.</span></span>

<span data-ttu-id="db380-106">**注** MBAM クライアントシステム要件を確認するには、「 [mbam 1.0 でサポートされている構成](mbam-10-supported-configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db380-106">**Note** To review the MBAM Client system requirements, see [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

 

**<span data-ttu-id="db380-107">デスクトップまたはラップトップコンピューターに MBAM クライアントを展開するには</span><span class="sxs-lookup"><span data-stu-id="db380-107">To deploy the MBAM Client to desktop or laptop computers</span></span>**

1.  <span data-ttu-id="db380-108">MBAM ソフトウェアに付属の MBAM クライアントインストールファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="db380-108">Locate the MBAM Client installation files that are provided with the MBAM software.</span></span>

2.  <span data-ttu-id="db380-109">Active Directory ドメインサービス、または MicrosoftSystemCenter2012 ConfigurationManager などのエンタープライズソフトウェア展開ツールを使用して、ターゲットコンピューターに Windows インストーラーパッケージを展開します。</span><span class="sxs-lookup"><span data-stu-id="db380-109">Deploy the Windows Installer package to target computers by using Active Directory Domain Services or an enterprise software deployment tool, such as MicrosoftSystemCenter2012 ConfigurationManager.</span></span>

    <span data-ttu-id="db380-110">**注** グループポリシーを使って Windows インストーラーパッケージを展開しないでください。</span><span class="sxs-lookup"><span data-stu-id="db380-110">**Note** You should not use Group Policy to deploy the Windows Installer package.</span></span>

     

3.  <span data-ttu-id="db380-111">MBAM クライアントインストールファイルを実行するように配布設定またはグループポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="db380-111">Configure the distribution settings or Group Policy to run the MBAM Client installation file.</span></span> <span data-ttu-id="db380-112">インストールが正常に完了すると、MBAM クライアントによって、ドメインコントローラーから受信したグループポリシー設定が適用され、BitLocker の暗号化と管理の機能が開始されます。</span><span class="sxs-lookup"><span data-stu-id="db380-112">After successful installation, the MBAM Client applies the Group Policy settings that are received from a domain controller to begin BitLocker encryption and management functions.</span></span> <span data-ttu-id="db380-113">MBAM グループポリシー設定の詳細については、「 [mbam 1.0 グループポリシーの要件を計画する](planning-for-mbam-10-group-policy-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db380-113">For more information about MBAM Group Policy settings, see [Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md).</span></span>

    <span data-ttu-id="db380-114">**重要** MBAM クライアントは、リモートデスクトッププロトコル接続がアクティブな場合は、BitLocker 暗号化アクションを開始しません。</span><span class="sxs-lookup"><span data-stu-id="db380-114">**Important** The MBAM Client will not start BitLocker encryption actions if a remote desktop protocol connection is active.</span></span> <span data-ttu-id="db380-115">BitLocker 暗号化を開始する前に、すべてのリモートコンソール接続を閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="db380-115">All remote console connections must be closed before BitLocker encryption will begin.</span></span>

     

## <span data-ttu-id="db380-116">関連トピック</span><span class="sxs-lookup"><span data-stu-id="db380-116">Related topics</span></span>


[<span data-ttu-id="db380-117">MBAM 1.0 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="db380-117">Deploying the MBAM 1.0 Client</span></span>](deploying-the-mbam-10-client.md)

 

 





