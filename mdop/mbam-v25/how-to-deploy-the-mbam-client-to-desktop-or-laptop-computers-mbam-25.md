---
title: MBAM クライアントをデスクトップまたはノート PC に展開する方法
description: MBAM クライアントをデスクトップまたはノート PC に展開する方法
author: dansimp
ms.assetid: 3a7639e0-468e-4496-8be2-ed29b8e07c53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6b67533a555da4dabec6654ed3f95f91ad8d37bf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824477"
---
# <span data-ttu-id="caf6f-103">MBAM クライアントをデスクトップまたはノート PC に展開する方法</span><span class="sxs-lookup"><span data-stu-id="caf6f-103">How to Deploy the MBAM Client to Desktop or Laptop Computers</span></span>


<span data-ttu-id="caf6f-104">このトピックでは、エンドユーザーのコンピューターに MBAM クライアントを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="caf6f-104">This topic explains how to deploy the MBAM Client to end users’ computers.</span></span> <span data-ttu-id="caf6f-105">MBAM クライアントは、Active Directory ドメインサービスや MicrosoftSystemCenterConfiguration Manager などの電子ソフトウェア配布システムを通じて展開できます。</span><span class="sxs-lookup"><span data-stu-id="caf6f-105">You can deploy the MBAM Client through an electronic software distribution system, such as Active Directory Domain Services or MicrosoftSystemCenterConfiguration Manager.</span></span>

<span data-ttu-id="caf6f-106">Windows 展開の一環として MBAM クライアントを展開する方法については、「 [Windows 展開の一部として MBAM を使用して BitLocker を有効にする方法](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="caf6f-106">To deploy the MBAM Client as part of a Windows deployment, see [How to Enable BitLocker by Using MBAM as Part of a Windows Deployment](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md).</span></span>

<span data-ttu-id="caf6f-107">MBAM クライアントの展開を開始する前に、 [mbam 2.5 でサポートされている構成](mbam-25-supported-configurations.md)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="caf6f-107">Before you start the MBAM Client deployment, review the [MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md).</span></span>

**<span data-ttu-id="caf6f-108">デスクトップまたはラップトップコンピューターに MBAM クライアントを展開するには</span><span class="sxs-lookup"><span data-stu-id="caf6f-108">To deploy the MBAM Client to desktop or laptop computers</span></span>**

1.  <span data-ttu-id="caf6f-109">MBAM ソフトウェアに付属の MBAM クライアントインストールファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="caf6f-109">Locate the MBAM Client installation files that are provided with the MBAM software.</span></span>

2.  <span data-ttu-id="caf6f-110">Active Directory ドメインサービス、または MicrosoftSystemCenterConfiguration Manager などのエンタープライズソフトウェア展開ツールを使用して、Windows インストーラーパッケージをターゲットコンピューターに展開します。</span><span class="sxs-lookup"><span data-stu-id="caf6f-110">Use Active Directory Domain Services or an enterprise software deployment tool like MicrosoftSystemCenterConfiguration Manager to deploy the Windows Installer package to target computers.</span></span>

3.  <span data-ttu-id="caf6f-111">MBAM クライアントインストールファイルを実行するように、配布設定またはグループポリシー設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="caf6f-111">Configure the distribution settings or Group Policy settings to run the MBAM Client installation file.</span></span>

    <span data-ttu-id="caf6f-112">インストールが正常に完了すると、MBAM クライアントは、BitLocker ドライブの暗号化と管理機能を開始するために、ドメインコントローラーから受信したグループポリシー設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="caf6f-112">After successful installation, the MBAM Client applies the Group Policy settings that are received from a domain controller to begin BitLocker Drive Encryption and management functions.</span></span>

    <span data-ttu-id="caf6f-113">**重要** MBAM クライアントは、リモートデスクトッププロトコル接続がアクティブな場合は、BitLocker ドライブ暗号化アクションを開始しません。</span><span class="sxs-lookup"><span data-stu-id="caf6f-113">**Important** The MBAM Client does not start BitLocker Drive Encryption actions if a remote desktop protocol connection is active.</span></span> <span data-ttu-id="caf6f-114">すべてのリモートコンソール接続を閉じる必要があります。ユーザーは、BitLocker ドライブ暗号化が開始される前に、物理コンソールセッションにログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="caf6f-114">All remote console connections must be closed and a user must be logged on to a physical console session before BitLocker Drive Encryption begins.</span></span>

     


## <span data-ttu-id="caf6f-115">関連トピック</span><span class="sxs-lookup"><span data-stu-id="caf6f-115">Related topics</span></span>
[<span data-ttu-id="caf6f-116">MBAM 2.5 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="caf6f-116">Deploying the MBAM 2.5 Client</span></span>](deploying-the-mbam-25-client.md)

[<span data-ttu-id="caf6f-117">MBAM 2.5 クライアントの展開計画</span><span class="sxs-lookup"><span data-stu-id="caf6f-117">Planning for MBAM 2.5 Client Deployment</span></span>](planning-for-mbam-25-client-deployment.md)

 

## <span data-ttu-id="caf6f-118">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="caf6f-118">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="caf6f-119">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="caf6f-119">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="caf6f-120">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="caf6f-120">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





