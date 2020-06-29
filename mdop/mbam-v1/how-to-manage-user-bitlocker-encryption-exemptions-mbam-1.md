---
title: ユーザーの BitLocker 暗号化の除外を管理する方法
description: ユーザーの BitLocker 暗号化の除外を管理する方法
author: dansimp
ms.assetid: 48d69721-504f-4524-8a04-b9ce213ac9b4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8c3d70558a65c3288174413d6c36cc9c77bc9eaa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812963"
---
# <span data-ttu-id="9c512-103">ユーザーの BitLocker 暗号化の除外を管理する方法</span><span class="sxs-lookup"><span data-stu-id="9c512-103">How to Manage User BitLocker Encryption Exemptions</span></span>


<span data-ttu-id="9c512-104">Microsoft BitLocker の管理と監視 (MBAM) を使って、不要なユーザーまたはドライブを暗号化する必要がないユーザーを除外することで、BitLocker 保護を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="9c512-104">Microsoft BitLocker Administration and Monitoring (MBAM) can be used to manage BitLocker protection by exempting users who do not need or want their drives encrypted.</span></span>

<span data-ttu-id="9c512-105">ユーザーを BitLocker による保護から除外するには、まず、そのような例外をサポートするためのインフラストラクチャを組織で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c512-105">To exempt users from BitLocker protection, an organization must first create an infrastructure to support such exemptions.</span></span> <span data-ttu-id="9c512-106">サポートインフラストラクチャには、除外を要求するための連絡先の電話番号、web ページ、またはメールアドレスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9c512-106">The supporting infrastructure might include a contact telephone number, webpage, or mailing address to request exemption.</span></span> <span data-ttu-id="9c512-107">また、すべての適用除外ユーザーは、特定のユーザーに対して特別に作成されたグループポリシーのセキュリティグループに追加される必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c512-107">Also, any exempt user will have to be added to a security group for Group Policy created specifically for exempted users.</span></span> <span data-ttu-id="9c512-108">このセキュリティグループのメンバーがコンピューターにログオンすると、ユーザーグループポリシーには、ユーザーが BitLocker 保護から除外されていることが示されます。</span><span class="sxs-lookup"><span data-stu-id="9c512-108">When members of this security group log on to a computer, the user Group Policy shows that the user is exempted from BitLocker protection.</span></span> <span data-ttu-id="9c512-109">ユーザーポリシーによってコンピューターのポリシーが上書きされ、コンピューターは BitLocker 暗号化から除外されたままになります。</span><span class="sxs-lookup"><span data-stu-id="9c512-109">The user policy overwrites the computer policy, and the computer will remain exempt from BitLocker encryption.</span></span>

<span data-ttu-id="9c512-110">**注** コンピューターが既に BitLocker で保護されている場合は、ユーザーの除外ポリシーには影響ありません。</span><span class="sxs-lookup"><span data-stu-id="9c512-110">**Note** If the computer is already BitLocker-protected, the user exemption policy has no effect.</span></span>

 

<span data-ttu-id="9c512-111">次の表は、適用除外の設定に基づいて、BitLocker の保護を適用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9c512-111">The following table shows how BitLocker protection is applied based on how exemptions are set.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9c512-112">ユーザーの状態</span><span class="sxs-lookup"><span data-stu-id="9c512-112">User Status</span></span></th>
<th align="left"><span data-ttu-id="9c512-113">除外されていないコンピューター</span><span class="sxs-lookup"><span data-stu-id="9c512-113">Computer Not Exempt</span></span></th>
<th align="left"><span data-ttu-id="9c512-114">コンピューターの免税</span><span class="sxs-lookup"><span data-stu-id="9c512-114">Computer Exempt</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9c512-115">ユーザーは免税されません</span><span class="sxs-lookup"><span data-stu-id="9c512-115">User not exempt</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9c512-116">BitLocker 保護はコンピューターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9c512-116">BitLocker protection is enforced on the computer.</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c512-117">BitLocker 保護はコンピューターに適用されません。</span><span class="sxs-lookup"><span data-stu-id="9c512-117">BitLocker protection is not enforced on the computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="9c512-118">ユーザの除外</span><span class="sxs-lookup"><span data-stu-id="9c512-118">User exempt</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9c512-119">BitLocker 保護はコンピューターに適用されません。</span><span class="sxs-lookup"><span data-stu-id="9c512-119">BitLocker protection is not enforced on the computer.</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c512-120">BitLocker 保護はコンピューターに適用されません。</span><span class="sxs-lookup"><span data-stu-id="9c512-120">BitLocker protection is not enforced on the computer.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="9c512-121">ユーザーを BitLocker 暗号化から除外するには</span><span class="sxs-lookup"><span data-stu-id="9c512-121">To exempt a user from BitLocker Encryption</span></span>**

1.  <span data-ttu-id="9c512-122">ActiveDirectoryDomainServices セキュリティグループを作成して、BitLocker 暗号化からユーザーの除外を管理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9c512-122">Create an ActiveDirectoryDomainServices security group that will be used to manage user exemptions from BitLocker encryption.</span></span>

2.  <span data-ttu-id="9c512-123">MBAM グループポリシーテンプレートを使用して、グループポリシーオブジェクトの設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="9c512-123">Create a Group Policy Object setting by using the MBAM Group Policy template.</span></span> <span data-ttu-id="9c512-124">グループポリシーオブジェクトを、前の手順で作成した Active Directory グループに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="9c512-124">Associate the Group Policy Object with the Active Directory group that you created in the previous step.</span></span> <span data-ttu-id="9c512-125">ユーザーが BitLocker 暗号化の除外を要求できるようにするために必要なポリシー設定の詳細については、「 [MBAM 1.0 グループポリシーの要件を計画](planning-for-mbam-10-group-policy-requirements.md)する」の「ユーザーの免税ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c512-125">For more information about the necessary policy settings to enable users to request exemption from BitLocker encryption, see the Configure User Exemption Policy section in [Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md).</span></span>

3.  <span data-ttu-id="9c512-126">BitLocker を適用除外されたユーザーのセキュリティグループを作成した後、このグループに、除外を要求しているユーザーの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="9c512-126">After creating a security group for BitLocker-exempted users, add to this group the names of the users who are requesting exemption.</span></span> <span data-ttu-id="9c512-127">ユーザーが BitLocker によって制御されているコンピューターにログオンすると、MBAM クライアントはユーザーの免税ポリシー設定を確認し、ユーザーが BitLocker の除外セキュリティグループの一部であるかどうかに基づいて保護を中断します。</span><span class="sxs-lookup"><span data-stu-id="9c512-127">When a user logs on to a computer controlled by BitLocker, the MBAM client will check the User Exemption Policy setting and will suspend protection based on whether the user is part of the BitLocker exemption security group.</span></span>

    <span data-ttu-id="9c512-128">**注** 共有コンピューターのシナリオでは、ユーザーの除外について特に考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c512-128">**Note** Shared computer scenarios require special consideration regarding user exemption.</span></span> <span data-ttu-id="9c512-129">非適用ユーザーが適用除外ユーザーと共有しているコンピューターにログオンしている場合、そのコンピューターは暗号化されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9c512-129">If a non-exempt user logs on to a computer shared with an exempt user, the computer may be encrypted.</span></span>

     

**<span data-ttu-id="9c512-130">ユーザーが BitLocker 暗号化から除外を要求できるようにするには</span><span class="sxs-lookup"><span data-stu-id="9c512-130">To enable users to request exemption from BitLocker Encryption</span></span>**

1.  <span data-ttu-id="9c512-131">MBAM ポリシーテンプレートを使用してユーザーの除外ポリシーを構成した後、ユーザーは MBAM クライアントを介して BitLocker 保護から除外を要求することができます。</span><span class="sxs-lookup"><span data-stu-id="9c512-131">After you have configured user-exemption policies by usingwith the MBAM Policy template, a user can request exemption from BitLocker protection through the MBAM client.</span></span>

2.  <span data-ttu-id="9c512-132">MBAM Hardware Compatibility リストと**互換性**があるとマークされているコンピューターにユーザーがログオンすると、コンピューターが暗号化されていることを知らせる通知がユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c512-132">When a user logs on to a computer that is marked as **Compatible** in the MBAM Hardware Compatibility list, the system presents the user with a notification that the computer is going to be encrypted.</span></span> <span data-ttu-id="9c512-133">ユーザーは [**除外を要求**する] を選択し、**後**で選択して暗号化を延期するか、[**開始**] を選択して BitLocker 暗号化を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="9c512-133">The user can select **Request Exemption** and postpone the encryption by selecting **Later**, or select **Start** to accept the BitLocker encryption.</span></span>

    <span data-ttu-id="9c512-134">**注** [**除外を要求**する] を選択すると、ユーザーの除外ポリシーで設定されている最長時間が経過するまで、BitLocker の保護が延期されます。</span><span class="sxs-lookup"><span data-stu-id="9c512-134">**Note** Selecting **Request Exemption** will postpone the BitLocker protection until the maximum time set in the User Exemption Policy.</span></span>

     

3.  <span data-ttu-id="9c512-135">ユーザーが [**除外の要求**] を選択すると、組織の BitLocker 管理グループに連絡するようにユーザーに通知されます。</span><span class="sxs-lookup"><span data-stu-id="9c512-135">When a user selects **Request Exemption**, the user is notified to contact the organization's BitLocker administration group.</span></span> <span data-ttu-id="9c512-136">ユーザーの免税ポリシーを構成する方法に応じて、ユーザーには次の1つ以上の連絡先メソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9c512-136">Depending on how the Configure User Exemption Policy is configured, users are provided with one or more of the following contact methods:</span></span>

    -   <span data-ttu-id="9c512-137">電話番号</span><span class="sxs-lookup"><span data-stu-id="9c512-137">Phone Number</span></span>

    -   <span data-ttu-id="9c512-138">Web ページの URL</span><span class="sxs-lookup"><span data-stu-id="9c512-138">Webpage URL</span></span>

    -   <span data-ttu-id="9c512-139">郵送先住所</span><span class="sxs-lookup"><span data-stu-id="9c512-139">Mailing Address</span></span>

    <span data-ttu-id="9c512-140">要求の提出後、MBAM 管理者は、BitLocker の除外可能な Active Directory グループにユーザーを追加することが適切であるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="9c512-140">After submittal of the request, the MBAM Administrator can decide if it is appropriate to add the user to the BitLocker Exemption Active Directory group.</span></span>

    <span data-ttu-id="9c512-141">**注** ユーザーの適用除外ポリシーの [延期時間] の有効期限が切れた後は、暗号化ポリシーに適用除外を要求するオプションがユーザーに表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="9c512-141">**Note** Once the postpone time limit from the User Exemption Policy has expired, users will not see the option to request exemption to the encryption policy.</span></span> <span data-ttu-id="9c512-142">この時点で、ユーザーは、BitLocker 保護から適用除外を受け取るために、MBAM 管理者に直接連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c512-142">At this point, users must contact the MBAM administrator directly in order to receive exemption from BitLocker Protection.</span></span>

     

## <span data-ttu-id="9c512-143">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9c512-143">Related topics</span></span>


[<span data-ttu-id="9c512-144">MBAM 1.0 機能の管理</span><span class="sxs-lookup"><span data-stu-id="9c512-144">Administering MBAM 1.0 Features</span></span>](administering-mbam-10-features.md)

 

 





