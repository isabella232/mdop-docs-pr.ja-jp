---
title: ユーザーの BitLocker 暗号化の除外を管理する方法
description: ユーザーの BitLocker 暗号化の除外を管理する方法
author: dansimp
ms.assetid: 1bfd9d66-6a9a-4d0e-b54a-e5a6627f5ada
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4d5530701fd208d42dc1f6774fac11ee9ca2036b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825074"
---
# <span data-ttu-id="20107-103">ユーザーの BitLocker 暗号化の除外を管理する方法</span><span class="sxs-lookup"><span data-stu-id="20107-103">How to Manage User BitLocker Encryption Exemptions</span></span>


<span data-ttu-id="20107-104">Microsoft BitLocker の管理と監視 (MBAM) を使用すると、ユーザーが必要としないユーザーがいる場合、またはドライブを暗号化しておく必要があるユーザーがいる場合に、除外して BitLocker 保護を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="20107-104">Microsoft BitLocker Administration and Monitoring (MBAM) can be used to manage BitLocker protection by exempting users if there are users who do not need or want their drives encrypted.</span></span>

<span data-ttu-id="20107-105">ユーザーに対して BitLocker 保護を適用除外するには、ユーザーに対して、除外を要求するために使用する連絡先の電話番号、web ページ、または郵送先住所をユーザーに提供するインフラストラクチャを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20107-105">To exempt users from BitLocker protection, an organization will have to create an infrastructure to support exempted users, such as giving the user a contact telephone number, webpage, or mailing address to use to request an exemption.</span></span> <span data-ttu-id="20107-106">また、免除ユーザーは、明示的なユーザーのために特別に作成されたグループポリシーオブジェクトのセキュリティグループに追加される必要があります。</span><span class="sxs-lookup"><span data-stu-id="20107-106">Also, an exempt user will have to be added to a security group for a Group Policy Object that was created specifically for exempted users.</span></span> <span data-ttu-id="20107-107">このセキュリティグループのメンバーがコンピューターにログオンすると、ユーザーのグループポリシー設定により、ユーザーは BitLocker 保護から除外されていることが示されます。</span><span class="sxs-lookup"><span data-stu-id="20107-107">When members of this security group log on to a computer, the user’s Group Policy setting shows that the user is exempted from BitLocker protection.</span></span> <span data-ttu-id="20107-108">ユーザーのグループポリシー設定によってコンピューターのポリシーが上書きされ、コンピューターは BitLocker 暗号化から除外されたままになります。</span><span class="sxs-lookup"><span data-stu-id="20107-108">The user’s Group Policy setting overwrites the computer policy, and the computer will remain exempt from BitLocker encryption.</span></span>

<span data-ttu-id="20107-109">**注** コンピューターが既に BitLocker で保護されている場合は、ユーザーの除外ポリシーには影響ありません。</span><span class="sxs-lookup"><span data-stu-id="20107-109">**Note** If the computer is already BitLocker-protected, the user exemption policy has no effect.</span></span>

 

<span data-ttu-id="20107-110">次の表は、適用除外の設定に基づいて、BitLocker の保護を適用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="20107-110">The following table shows how BitLocker protection is applied based on how exemptions are set.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="20107-111">ユーザーの状態</span><span class="sxs-lookup"><span data-stu-id="20107-111">User Status</span></span></th>
<th align="left"><span data-ttu-id="20107-112">除外されていないコンピューター</span><span class="sxs-lookup"><span data-stu-id="20107-112">Computer Not Exempt</span></span></th>
<th align="left"><span data-ttu-id="20107-113">コンピューターの免税</span><span class="sxs-lookup"><span data-stu-id="20107-113">Computer Exempt</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="20107-114">ユーザーは免税されません</span><span class="sxs-lookup"><span data-stu-id="20107-114">User not exempt</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="20107-115">BitLocker 保護はコンピューターに適用されます</span><span class="sxs-lookup"><span data-stu-id="20107-115">BitLocker protection is enforced on computer</span></span></p></td>
<td align="left"><p><span data-ttu-id="20107-116">BitLocker 保護がコンピューターに適用されない</span><span class="sxs-lookup"><span data-stu-id="20107-116">BitLocker protection is not enforced on computer</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="20107-117">ユーザの除外</span><span class="sxs-lookup"><span data-stu-id="20107-117">User exempt</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="20107-118">BitLocker 保護がコンピューターに適用されない</span><span class="sxs-lookup"><span data-stu-id="20107-118">BitLocker protection is not enforced on computer</span></span></p></td>
<td align="left"><p><span data-ttu-id="20107-119">BitLocker 保護がコンピューターに適用されない</span><span class="sxs-lookup"><span data-stu-id="20107-119">BitLocker protection is not enforced on computer</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="20107-120">ユーザーを BitLocker 暗号化から除外するには</span><span class="sxs-lookup"><span data-stu-id="20107-120">To exempt a user from BitLocker encryption</span></span>**

1.  <span data-ttu-id="20107-121">BitLocker 暗号化要件からユーザーの除外を管理するために使用される ActiveDirectoryDomainServices セキュリティグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="20107-121">Create an ActiveDirectoryDomainServices security group that will be used to manage user exemptions from BitLocker encryption requirements.</span></span>

2.  <span data-ttu-id="20107-122">Microsoft BitLocker の管理と監視のグループポリシーテンプレートを使用して、グループポリシーオブジェクトの設定を作成し、前の手順で作成した Active Directory グループに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="20107-122">Create a Group Policy Object setting by using the Microsoft BitLocker Administration and Monitoring Group Policy template and associate it with the Active Directory group that you created in the previous step.</span></span> <span data-ttu-id="20107-123">ユーザーを適用しないためのポリシー設定は、 **userconfiguration¥管理 Templates\\Windows Components\\MDOP MBAM (BitLocker 管理)** の下にあります。</span><span class="sxs-lookup"><span data-stu-id="20107-123">The policy settings to exempt users can be found under **UserConfiguration\\Administrative Templates\\Windows Components\\MDOP MBAM (BitLocker Management)**.</span></span>

3.  <span data-ttu-id="20107-124">BitLocker を適用除外されたユーザーのセキュリティグループを作成した後、このグループに、除外を要求しているユーザーの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="20107-124">After creating a security group for BitLocker-exempted users, add to this group the names of the users who are requesting an exemption.</span></span> <span data-ttu-id="20107-125">ユーザーが BitLocker によって制御されているコンピューターにログオンすると、MBAM クライアントはユーザーの適用除外ポリシー設定を確認し、ユーザーが BitLocker 除外セキュリティグループの一部であるかどうかに基づいて保護を中断します。</span><span class="sxs-lookup"><span data-stu-id="20107-125">When users log on to a computer controlled by BitLocker, the MBAM client will check the User Exemption Policy setting and will suspend protection based on whether the user is part of the BitLocker exemption security group.</span></span>

    <span data-ttu-id="20107-126">**重要** 共有コンピューターのシナリオでは、ユーザーの例外を使用する場合は特別な考慮事項が必要です。</span><span class="sxs-lookup"><span data-stu-id="20107-126">**Important** Shared computer scenarios require special consideration when using user exemptions.</span></span> <span data-ttu-id="20107-127">非適用ユーザーが適用除外ユーザーと共有しているコンピューターにログオンしている場合、そのコンピューターは暗号化されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="20107-127">If a non-exempt user logs on to a computer shared with an exempt user, the computer may be encrypted.</span></span>

     

**<span data-ttu-id="20107-128">ユーザーが BitLocker 暗号化の除外を要求できるようにするには</span><span class="sxs-lookup"><span data-stu-id="20107-128">To enable users to request an exemption from BitLocker encryption</span></span>**

1.  <span data-ttu-id="20107-129">MBAM ポリシーテンプレートを使用してユーザーの免税ポリシーを構成した場合、ユーザーは MBAM クライアントを通じて BitLocker 保護から除外を要求できます。</span><span class="sxs-lookup"><span data-stu-id="20107-129">If you have configured user exemption policies by using the MBAM policy template, a user can request an exemption from BitLocker protection through the MBAM client.</span></span>

2.  <span data-ttu-id="20107-130">ユーザーが暗号化する必要があるコンピューターにログオンすると、コンピューターが暗号化されていることを知らせる通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="20107-130">When users log on to a computer that is required to be encrypted, they receive a notification that their computer is going to be encrypted.</span></span> <span data-ttu-id="20107-131">[除外を**要求**する] を選択し、**後**で選択して暗号化を延期するか、[**開始**] を選択して BitLocker 暗号化を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="20107-131">They can select **Request Exemption** and postpone the encryption by selecting **Later**, or select **Start** to accept the BitLocker encryption.</span></span>

    <span data-ttu-id="20107-132">**注** [**除外を要求**する] を選択すると、ユーザーの除外ポリシーで設定されている最長時間が経過するまで、BitLocker 保護を延期します。</span><span class="sxs-lookup"><span data-stu-id="20107-132">**Note** Selecting **Request Exemption** postpones the BitLocker protection until the maximum time that is set in the User Exemption Policy.</span></span>

     

3.  <span data-ttu-id="20107-133">ユーザーが [**除外を要求**する] を選択すると、組織の BitLocker 管理グループに連絡するように指示する通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="20107-133">If users select **Request Exemption**, they receive a notification telling them to contact your organization’s BitLocker administration group.</span></span> <span data-ttu-id="20107-134">ユーザーの免税ポリシーを構成する方法に応じて、ユーザーには次の1つ以上の連絡先メソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="20107-134">Depending on how the Configure User Exemption Policy is configured, users are provided with one or more of the following contact methods:</span></span>

    -   <span data-ttu-id="20107-135">電話番号</span><span class="sxs-lookup"><span data-stu-id="20107-135">Phone Number</span></span>

    -   <span data-ttu-id="20107-136">Web ページの URL</span><span class="sxs-lookup"><span data-stu-id="20107-136">Webpage URL</span></span>

    -   <span data-ttu-id="20107-137">郵送先住所</span><span class="sxs-lookup"><span data-stu-id="20107-137">Mailing Address</span></span>

    <span data-ttu-id="20107-138">除外要求を受信した後、MBAM 管理者は、ユーザーを BitLocker の除外された Active Directory グループに追加することが適切であるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="20107-138">After the exemption request is received, the MBAM Administrator can take decide if it is appropriate to add the user to the BitLocker Exemption Active Directory group.</span></span>

    <span data-ttu-id="20107-139">**注** ユーザーが免税要求を送信すると、MBAM エージェントは、ユーザーに対して "一時的に除外" として報告し、次に、設定された日数が経過すると、コンピューターのコンプライアンスを再確認します。</span><span class="sxs-lookup"><span data-stu-id="20107-139">**Note** Once a user submits an exemption request, the MBAM agent reports the user as “temporarily exempt” and then waits a configurable number of days before it checks the computer’s compliance again.</span></span> <span data-ttu-id="20107-140">MBAM 管理者が除外要求を拒否した場合、[除外要求] オプションは無効になり、ユーザーは除外を再度要求することはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="20107-140">If the MBAM administrator rejects the exemption request, the exemption request option is deactivated, which prevents the user from being able to request the exemption again.</span></span>

     

## <span data-ttu-id="20107-141">関連トピック</span><span class="sxs-lookup"><span data-stu-id="20107-141">Related topics</span></span>


[<span data-ttu-id="20107-142">MBAM 2.0 機能の管理</span><span class="sxs-lookup"><span data-stu-id="20107-142">Administering MBAM 2.0 Features</span></span>](administering-mbam-20-features-mbam-2.md)

 

 





