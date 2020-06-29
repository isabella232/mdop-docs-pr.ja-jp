---
title: コンピューターの BitLocker 暗号化の除外を管理する方法
description: コンピューターの BitLocker 暗号化の除外を管理する方法
author: dansimp
ms.assetid: d4400a0d-b36b-4cf5-a294-1f53ec47f9ee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 51b93061468508900eaee7fce8a7827e2db61d19
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825677"
---
# <span data-ttu-id="4da49-103">コンピューターの BitLocker 暗号化の除外を管理する方法</span><span class="sxs-lookup"><span data-stu-id="4da49-103">How to Manage Computer BitLocker Encryption Exemptions</span></span>


<span data-ttu-id="4da49-104">Microsoft BitLocker の管理と監視 (MBAM) を使用して、BitLocker 保護から特定のコンピューターを除外することができます。</span><span class="sxs-lookup"><span data-stu-id="4da49-104">Microsoft BitLocker Administration and Monitoring (MBAM) can be used to exempt certain computers from BitLocker protection.</span></span> <span data-ttu-id="4da49-105">たとえば、組織では、コンピューターごとに BitLocker の除外を制御することができます。</span><span class="sxs-lookup"><span data-stu-id="4da49-105">For example, an organization may decide to control BitLocker exemption on a computer-by-computer basis.</span></span>

<span data-ttu-id="4da49-106">コンピューターを BitLocker 暗号化から除外するには、コンピューターベースの BitLocker 保護規則を回避するために、ActiveDirectoryDomainServices のセキュリティグループにコンピューターを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4da49-106">To exempt a computer from BitLocker encryption, you must add the computer to a security group in ActiveDirectoryDomainServices in order to bypass any computer-based BitLocker protection rules.</span></span>

<span data-ttu-id="4da49-107">**注** コンピューターが既に BitLocker で保護されている場合は、コンピューターの除外ポリシーには影響ありません。</span><span class="sxs-lookup"><span data-stu-id="4da49-107">**Note** If the computer is already BitLocker-protected, the computer exemption policy has no effect.</span></span>

 

**<span data-ttu-id="4da49-108">BitLocker 暗号化からコンピューターを除外するには</span><span class="sxs-lookup"><span data-stu-id="4da49-108">To exempt a computer from BitLocker encryption</span></span>**

1.  <span data-ttu-id="4da49-109">ActiveDirectoryDomainServices のセキュリティグループに適用除外するコンピューターアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="4da49-109">Add the computer account that you want to be exempted to a security group in ActiveDirectoryDomainServices.</span></span> <span data-ttu-id="4da49-110">これにより、コンピューターベースの BitLocker 保護規則をすべてバイパスすることができます。</span><span class="sxs-lookup"><span data-stu-id="4da49-110">This allows you to bypass any computer-based BitLocker protection rules.</span></span>

2.  <span data-ttu-id="4da49-111">MBAM グループポリシーテンプレートを使用してグループポリシーオブジェクトを作成し、前の手順で作成した Active Directory グループにグループポリシーオブジェクトを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="4da49-111">Create a Group Policy Object by using the MBAM Group Policy template, then associate the Group Policy Object with the Active Directory group that you created in the previous step.</span></span> <span data-ttu-id="4da49-112">必要なグループポリシーオブジェクトの作成について詳しくは、「 [MBAM 1.0 グループポリシーオブジェクトの展開](deploying-mbam-10-group-policy-objects.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4da49-112">For more information about creating the necessary Group Policy Objects, see [Deploying MBAM 1.0 Group Policy Objects](deploying-mbam-10-group-policy-objects.md).</span></span>

3.  <span data-ttu-id="4da49-113">除外されたコンピューターが起動すると、MBAM クライアントはコンピューターの適用除外ポリシー設定を確認し、コンピューターが BitLocker の除外セキュリティグループの一部であるかどうかに基づいて保護を中断します。</span><span class="sxs-lookup"><span data-stu-id="4da49-113">When an exempted computer starts, the MBAM client checks the Computer Exemption Policy setting and suspends protection based on whether the computer is part of the BitLocker exemption security group.</span></span>

## <span data-ttu-id="4da49-114">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4da49-114">Related topics</span></span>


[<span data-ttu-id="4da49-115">MBAM 1.0 機能の管理</span><span class="sxs-lookup"><span data-stu-id="4da49-115">Administering MBAM 1.0 Features</span></span>](administering-mbam-10-features.md)

 

 





