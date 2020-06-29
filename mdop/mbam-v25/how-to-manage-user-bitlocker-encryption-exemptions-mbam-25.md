---
title: ユーザーの BitLocker 暗号化の除外を管理する方法
description: ユーザーの BitLocker 暗号化の除外を管理する方法
author: dansimp
ms.assetid: f582ab82-5bb5-4cd3-ad7c-483240533cf9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c4224a0fb6d905c2362659efe7cf05e16756f7c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826794"
---
# <span data-ttu-id="52175-103">ユーザーの BitLocker 暗号化の除外を管理する方法</span><span class="sxs-lookup"><span data-stu-id="52175-103">How to Manage User BitLocker Encryption Exemptions</span></span>


<span data-ttu-id="52175-104">Microsoft BitLocker の管理と監視 (MBAM) を使うと、BitLocker ドライブ暗号化の要件からユーザーを除外できます。</span><span class="sxs-lookup"><span data-stu-id="52175-104">Microsoft BitLocker Administration and Monitoring (MBAM) enables you to exempt users from BitLocker Drive Encryption requirements.</span></span>

<span data-ttu-id="52175-105">ユーザーによる BitLocker 保護の適用を解除するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="52175-105">To exempt users from BitLocker protection, you have to:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="52175-106">タスク</span><span class="sxs-lookup"><span data-stu-id="52175-106">Task</span></span></th>
<th align="left"><span data-ttu-id="52175-107">詳細</span><span class="sxs-lookup"><span data-stu-id="52175-107">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="52175-108">除外されたユーザーをサポートするインフラストラクチャを作成します。</span><span class="sxs-lookup"><span data-stu-id="52175-108">Create an infrastructure to support exempted users.</span></span></p></td>
<td align="left"><p><span data-ttu-id="52175-109">このインフラストラクチャの例として、除外を要求するために使用できる連絡先の電話番号、web ページ、または住所をユーザーに提供することがあります。</span><span class="sxs-lookup"><span data-stu-id="52175-109">Examples of this infrastructure include providing users with a contact telephone number, webpage, or mailing address that they can use to request an exemption.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="52175-110">除外されたユーザーに対して特別に構成されているグループポリシーオブジェクトのセキュリティグループに、除外されたユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="52175-110">Add the exempted user to a security group for a Group Policy Object that is configured specifically for exempted users.</span></span></p></td>
<td align="left"><p><span data-ttu-id="52175-111">このセキュリティグループのメンバーがコンピューターにサインインすると、ユーザーのグループポリシー設定によって、ユーザーの BitLocker 保護が exempts されます。</span><span class="sxs-lookup"><span data-stu-id="52175-111">When members of this security group sign in to a computer, the user’s Group Policy setting exempts the user from BitLocker protection.</span></span> <span data-ttu-id="52175-112">ユーザーのグループポリシー設定によってコンピューターのポリシーが上書きされ、コンピューターは BitLocker 暗号化から除外されたままになります。</span><span class="sxs-lookup"><span data-stu-id="52175-112">The user’s Group Policy setting overwrites the computer policy, and the computer will remain exempt from BitLocker encryption.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="52175-113">注</span><span class="sxs-lookup"><span data-stu-id="52175-113">Note</span></span></strong><br/><p><span data-ttu-id="52175-114">コンピューターが既に BitLocker で保護されており、ユーザーが除外されている場合、MBAM は暗号化ポリシーを適用しません。</span><span class="sxs-lookup"><span data-stu-id="52175-114">MBAM does not enact the encryption policy if the computer is already BitLocker-protected and the user is exempted.</span></span> <span data-ttu-id="52175-115">ただし、暗号化ポリシーから除外されていない別のユーザーがコンピューターにサインインすると、暗号化が行われます。</span><span class="sxs-lookup"><span data-stu-id="52175-115">However, if another user who is not exempt from the encryption policy signs in to the computer, encryption will take place.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



<span data-ttu-id="52175-116">次の手順では、ユーザーが MBAM クライアントまたは組織が使用しているプロセスから、BitLocker ドライブ暗号化の除外プロセスから除外を要求したときの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="52175-116">The following steps describe what occurs when end users request an exemption from the BitLocker Drive Encryption exemption process through the MBAM Client or through whatever process your organization uses.</span></span> <span data-ttu-id="52175-117">MBAM グループポリシー設定を構成する必要があります。これにより、エンドユーザーは BitLocker ドライブ暗号化の除外を要求できるようになります。</span><span class="sxs-lookup"><span data-stu-id="52175-117">You must configure MBAM Group Policy settings to allow end users to request an exemption from BitLocker Drive Encryption.</span></span>

1.  <span data-ttu-id="52175-118">エンドユーザーが暗号化する必要があるコンピューターにサインインすると、コンピューターが暗号化されていることを知らせる通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="52175-118">When end users sign in to a computer that is required to be encrypted, they receive a notification that their computer is going to be encrypted.</span></span> <span data-ttu-id="52175-119">[除外の**要求**] を選択し、[**延期**] を選択して暗号化を延期するか、[**暗号化の開始**] を選択して BitLocker の暗号化を承認することができます。</span><span class="sxs-lookup"><span data-stu-id="52175-119">They can select **Request Exemption** and postpone the encryption by selecting **Postpone**, or they can select **Start Encryption** to accept the BitLocker encryption.</span></span>

    **<span data-ttu-id="52175-120">注</span><span class="sxs-lookup"><span data-stu-id="52175-120">Note</span></span>**  
    <span data-ttu-id="52175-121">[**除外を要求**する] を選択すると、ユーザーの除外ポリシーで設定されている最長時間が経過するまで、BitLocker 保護を延期します。</span><span class="sxs-lookup"><span data-stu-id="52175-121">Selecting **Request Exemption** postpones the BitLocker protection until the maximum time that is set in the User Exemption Policy.</span></span>



2.  <span data-ttu-id="52175-122">エンドユーザーが [**除外を要求**する] を選択すると、組織の BitLocker 管理グループに連絡するように指示する通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="52175-122">If end users select **Request Exemption**, they receive a notification telling them to contact the organization’s BitLocker administration group.</span></span> <span data-ttu-id="52175-123">**ユーザーの免税ポリシーを構成**する方法に応じて、ユーザーには次の1つ以上の連絡先メソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="52175-123">Depending on how the **Configure User Exemption Policy** is configured, users are provided with one or more of the following contact methods:</span></span>

    -   <span data-ttu-id="52175-124">電話番号</span><span class="sxs-lookup"><span data-stu-id="52175-124">Phone number</span></span>

    -   <span data-ttu-id="52175-125">Web ページの URL</span><span class="sxs-lookup"><span data-stu-id="52175-125">Webpage URL</span></span>

    -   <span data-ttu-id="52175-126">郵送先住所</span><span class="sxs-lookup"><span data-stu-id="52175-126">Mailing address</span></span>

3.  <span data-ttu-id="52175-127">除外要求を受信した後、MBAM 管理者は、BitLocker の例外の除外 Active Directory ドメインサービス (AD DS) グループにユーザーを追加するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="52175-127">After the exemption request is received, the MBAM administrator decides whether to add the user to the BitLocker Exemption Active Directory Domain Services (AD DS) group.</span></span>

4.  <span data-ttu-id="52175-128">エンドユーザーが免税要求を送信した後、MBAM クライアントはユーザーを "一時的に除外" として報告します。</span><span class="sxs-lookup"><span data-stu-id="52175-128">After an end user submits an exemption request, the MBAM Client reports the user as “Temporarily exempt.”</span></span> <span data-ttu-id="52175-129">クライアントは、コンピューターのコンプライアンスをもう一度確認する前に、管理者が設定した日数だけ待機します。</span><span class="sxs-lookup"><span data-stu-id="52175-129">The Client then waits a specified number of days, which IT administrators configure, before it checks the computer’s compliance again.</span></span> <span data-ttu-id="52175-130">MBAM 管理者が除外要求を拒否した場合、[除外要求] オプションが無効になり、ユーザーは除外を再度要求することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="52175-130">If the MBAM administrator rejects the exemption request, the exemption request option is deactivated, which prevents the user from requesting the exemption again.</span></span>

<span data-ttu-id="52175-131">Microsoft BitLocker の管理と監視 (MBAM) を使うと、BitLocker ドライブ暗号化の要件からユーザーを除外できます。</span><span class="sxs-lookup"><span data-stu-id="52175-131">Microsoft BitLocker Administration and Monitoring (MBAM) enables you to exempt users from BitLocker Drive Encryption requirements.</span></span>

<span data-ttu-id="52175-132">ユーザーによる BitLocker 保護の適用を解除するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="52175-132">To exempt users from BitLocker protection, you have to:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="52175-133">タスク</span><span class="sxs-lookup"><span data-stu-id="52175-133">Task</span></span></th>
<th align="left"><span data-ttu-id="52175-134">詳細</span><span class="sxs-lookup"><span data-stu-id="52175-134">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="52175-135">除外されたユーザーをサポートするインフラストラクチャを作成します。</span><span class="sxs-lookup"><span data-stu-id="52175-135">Create an infrastructure to support exempted users.</span></span></p></td>
<td align="left"><p><span data-ttu-id="52175-136">このインフラストラクチャの例として、除外を要求するために使用できる連絡先の電話番号、web ページ、または住所をユーザーに提供することがあります。</span><span class="sxs-lookup"><span data-stu-id="52175-136">Examples of this infrastructure include providing users with a contact telephone number, webpage, or mailing address that they can use to request an exemption.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="52175-137">除外されたユーザーに対して特別に構成されているグループポリシーオブジェクトのセキュリティグループに、除外されたユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="52175-137">Add the exempted user to a security group for a Group Policy Object that is configured specifically for exempted users.</span></span></p></td>
<td align="left"><p><span data-ttu-id="52175-138">このセキュリティグループのメンバーがコンピューターにサインインすると、ユーザーのグループポリシー設定によって、ユーザーの BitLocker 保護が exempts されます。</span><span class="sxs-lookup"><span data-stu-id="52175-138">When members of this security group sign in to a computer, the user’s Group Policy setting exempts the user from BitLocker protection.</span></span> <span data-ttu-id="52175-139">ユーザーのグループポリシー設定によってコンピューターのポリシーが上書きされ、コンピューターは BitLocker 暗号化から除外されたままになります。</span><span class="sxs-lookup"><span data-stu-id="52175-139">The user’s Group Policy setting overwrites the computer policy, and the computer will remain exempt from BitLocker encryption.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="52175-140">注</span><span class="sxs-lookup"><span data-stu-id="52175-140">Note</span></span></strong><br/><p><span data-ttu-id="52175-141">コンピューターが既に BitLocker で保護されている場合は、ユーザーの除外ポリシーには影響ありません。</span><span class="sxs-lookup"><span data-stu-id="52175-141">If the computer is already BitLocker-protected, the User Exemption Policy has no effect.</span></span> <span data-ttu-id="52175-142">さらに、暗号化ポリシーから除外されていないコンピューターに別のユーザーがサインインすると、暗号化が行われます。</span><span class="sxs-lookup"><span data-stu-id="52175-142">In addition, if another user signs in to a computer that is not exempt from the encryption policy, encryption will take place.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



<span data-ttu-id="52175-143">次の手順では、ユーザーが MBAM クライアントまたは組織が使用しているプロセスから、BitLocker ドライブ暗号化の除外プロセスから除外を要求したときの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="52175-143">The following steps describe what occurs when end users request an exemption from the BitLocker Drive Encryption exemption process through the MBAM Client or through whatever process your organization uses.</span></span> <span data-ttu-id="52175-144">MBAM グループポリシー設定を構成する必要があります。これにより、エンドユーザーは BitLocker ドライブ暗号化の除外を要求できるようになります。</span><span class="sxs-lookup"><span data-stu-id="52175-144">You must configure MBAM Group Policy settings to allow end users to request an exemption from BitLocker Drive Encryption.</span></span>

1.  <span data-ttu-id="52175-145">エンドユーザーが暗号化する必要があるコンピューターにサインインすると、コンピューターが暗号化されていることを知らせる通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="52175-145">When end users sign in to a computer that is required to be encrypted, they receive a notification that their computer is going to be encrypted.</span></span> <span data-ttu-id="52175-146">[除外の**要求**] を選択し、[**延期**] を選択して暗号化を延期するか、[**暗号化の開始**] を選択して BitLocker の暗号化を承認することができます。</span><span class="sxs-lookup"><span data-stu-id="52175-146">They can select **Request Exemption** and postpone the encryption by selecting **Postpone**, or they can select **Start Encryption** to accept the BitLocker encryption.</span></span>

    **<span data-ttu-id="52175-147">注</span><span class="sxs-lookup"><span data-stu-id="52175-147">Note</span></span>**  
    <span data-ttu-id="52175-148">[**除外を要求**する] を選択すると、ユーザーの除外ポリシーで設定されている最長時間が経過するまで、BitLocker 保護を延期します。</span><span class="sxs-lookup"><span data-stu-id="52175-148">Selecting **Request Exemption** postpones the BitLocker protection until the maximum time that is set in the User Exemption Policy.</span></span>



2.  <span data-ttu-id="52175-149">エンドユーザーが [**除外を要求**する] を選択すると、組織の BitLocker 管理グループに連絡するように指示する通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="52175-149">If end users select **Request Exemption**, they receive a notification telling them to contact the organization’s BitLocker administration group.</span></span> <span data-ttu-id="52175-150">**ユーザーの免税ポリシーを構成**する方法に応じて、ユーザーには次の1つ以上の連絡先メソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="52175-150">Depending on how the **Configure User Exemption Policy** is configured, users are provided with one or more of the following contact methods:</span></span>

    -   <span data-ttu-id="52175-151">電話番号</span><span class="sxs-lookup"><span data-stu-id="52175-151">Phone number</span></span>

    -   <span data-ttu-id="52175-152">Web ページの URL</span><span class="sxs-lookup"><span data-stu-id="52175-152">Webpage URL</span></span>

    -   <span data-ttu-id="52175-153">郵送先住所</span><span class="sxs-lookup"><span data-stu-id="52175-153">Mailing address</span></span>

3.  <span data-ttu-id="52175-154">除外要求を受信した後、MBAM 管理者は、BitLocker の例外の除外 Active Directory ドメインサービス (AD DS) グループにユーザーを追加するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="52175-154">After the exemption request is received, the MBAM administrator decides whether to add the user to the BitLocker Exemption Active Directory Domain Services (AD DS) group.</span></span>

4.  <span data-ttu-id="52175-155">エンドユーザーが免税要求を送信した後、MBAM クライアントはユーザーを "一時的に除外" として報告します。</span><span class="sxs-lookup"><span data-stu-id="52175-155">After an end user submits an exemption request, the MBAM Client reports the user as “Temporarily exempt.”</span></span> <span data-ttu-id="52175-156">クライアントは、コンピューターのコンプライアンスをもう一度確認する前に、管理者が設定した日数だけ待機します。</span><span class="sxs-lookup"><span data-stu-id="52175-156">The Client then waits a specified number of days, which IT administrators configure, before it checks the computer’s compliance again.</span></span> <span data-ttu-id="52175-157">MBAM 管理者が除外要求を拒否した場合、[除外要求] オプションが無効になり、ユーザーは除外を再度要求することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="52175-157">If the MBAM administrator rejects the exemption request, the exemption request option is deactivated, which prevents the user from requesting the exemption again.</span></span>

**<span data-ttu-id="52175-158">BitLocker ドライブ暗号化をユーザーに適用するには</span><span class="sxs-lookup"><span data-stu-id="52175-158">To exempt a user from BitLocker Drive Encryption</span></span>**

1.  <span data-ttu-id="52175-159">BitLocker 暗号化要件からユーザーの除外を管理するために使用される AD DS セキュリティグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="52175-159">Create an AD DS security group that will be used to manage user exemptions from BitLocker encryption requirements.</span></span>

2.  <span data-ttu-id="52175-160">Microsoft BitLocker の管理と監視のグループポリシーテンプレートを使用して、グループポリシーオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="52175-160">Create a Group Policy Object by using the Microsoft BitLocker Administration and Monitoring Group Policy Templates.</span></span>

3.  <span data-ttu-id="52175-161">グループポリシーオブジェクトを、前の手順で作成した AD DS グループに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="52175-161">Associate the Group Policy Object with the AD DS group that you created in the previous step.</span></span> <span data-ttu-id="52175-162">ユーザーを適用するポリシー設定は、次の場所にあります。 **userconfiguration** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **MDOP mbam (BitLocker 管理)**。</span><span class="sxs-lookup"><span data-stu-id="52175-162">The policy settings to exempt users are located at: **UserConfiguration** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)**.</span></span>

4.  <span data-ttu-id="52175-163">BitLocker の適用除外ユーザー用に作成したセキュリティグループに対して、除外を要求しているユーザーの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="52175-163">To the security group you created for BitLocker exempted users, add the names of the users who are requesting an exemption.</span></span>

    <span data-ttu-id="52175-164">ユーザーが BitLocker によって制御されているコンピューターにサインインすると、MBAM クライアントはユーザーの適用除外ポリシー設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="52175-164">When a user signs in to a computer controlled by BitLocker, the MBAM Client checks the User Exemption Policy setting.</span></span> <span data-ttu-id="52175-165">コンピューターが既に暗号化されている場合、BitLocker の保護は中断されません。</span><span class="sxs-lookup"><span data-stu-id="52175-165">If the computer is already encrypted, BitLocker protection is not suspended.</span></span> <span data-ttu-id="52175-166">コンピューターが暗号化されていない場合、MBAM はユーザーに暗号化を求めるメッセージを表示しません。</span><span class="sxs-lookup"><span data-stu-id="52175-166">If the computer is not encrypted, MBAM does not prompt the user to encrypt.</span></span>

    **<span data-ttu-id="52175-167">重要</span><span class="sxs-lookup"><span data-stu-id="52175-167">Important</span></span>**  
    <span data-ttu-id="52175-168">共有コンピューターのシナリオでは、BitLocker ユーザーの除外を使用している場合は特別な考慮事項が必要です。</span><span class="sxs-lookup"><span data-stu-id="52175-168">Shared computer scenarios require special consideration when you are using BitLocker user exemptions.</span></span> <span data-ttu-id="52175-169">非適用ユーザーが、適用除外ユーザーと共有されているコンピューターにサインインした場合、そのコンピューターは暗号化されることがあります。</span><span class="sxs-lookup"><span data-stu-id="52175-169">If a non-exempt user signs in to a computer that is shared with an exempt user, the computer may be encrypted.</span></span>




## <span data-ttu-id="52175-170">関連トピック</span><span class="sxs-lookup"><span data-stu-id="52175-170">Related topics</span></span>


[<span data-ttu-id="52175-171">MBAM 2.5 機能の管理</span><span class="sxs-lookup"><span data-stu-id="52175-171">Administering MBAM 2.5 Features</span></span>](administering-mbam-25-features.md)

[<span data-ttu-id="52175-172">MBAM 2.5 グループ ポリシー要件の計画</span><span class="sxs-lookup"><span data-stu-id="52175-172">Planning for MBAM 2.5 Group Policy Requirements</span></span>](planning-for-mbam-25-group-policy-requirements.md)




## <span data-ttu-id="52175-173">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="52175-173">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="52175-174">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="52175-174">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="52175-175">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="52175-175">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




