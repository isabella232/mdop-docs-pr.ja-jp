---
title: PIN またはパスワードの使用
description: PIN またはパスワードの使用
author: dansimp
ms.assetid: 7fe2aef4-d3e0-49c8-877d-7fee13dc5b7b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b8c4b894b8f3e14d2a5cfb39e744fa43874c6753
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823794"
---
# <span data-ttu-id="a5ba6-103">PIN またはパスワードの使用</span><span class="sxs-lookup"><span data-stu-id="a5ba6-103">Using Your PIN or Password</span></span>


<span data-ttu-id="a5ba6-104">BitLocker は、コンピューターに保存されている情報のロックを解除するために暗証番号 (PIN) またはパスワードを要求することによって、コンピューターのセキュリティを保護します。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-104">BitLocker helps secure your computer by requiring a personal identification number (PIN) or password to unlock the information that is stored on your computer.</span></span> <span data-ttu-id="a5ba6-105">PIN またはパスワードの要件は、組織によって設定され、暗号化されているドライブの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-105">The PIN or password requirements are set by your organization and depend on the kind of drive being encrypted.</span></span> <span data-ttu-id="a5ba6-106">暗号化されたドライブ上のデータは、PIN またはパスワードを入力しなくても表示できません。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-106">Data on the encrypted drives cannot be viewed without entering the PIN or password.</span></span> <span data-ttu-id="a5ba6-107">コンピューターのハードウェアに、有効になっているトラステッドプラットフォームモジュール (TPM) が含まれている場合、コンピューターで Windows が起動する前に、TPM チップによって PIN の入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-107">If your computer hardware includes an enabled Trusted Platform Module (TPM), the TPM chip prompts you for your PIN before Windows starts on your computer.</span></span>

## <span data-ttu-id="a5ba6-108">BitLocker PIN とパスワードについて</span><span class="sxs-lookup"><span data-stu-id="a5ba6-108">About Your BitLocker PIN and Passwords</span></span>


<span data-ttu-id="a5ba6-109">会社で、PIN またはパスワードに必要な複雑さを指定します。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-109">Your company specifies the complexity required for your PIN or password.</span></span> <span data-ttu-id="a5ba6-110">PIN またはパスワードに関するこれらの要件については、BitLocker のセットアッププロセスで説明されています。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-110">These requirements for your PIN or password are explained during the BitLocker setup process.</span></span>

<span data-ttu-id="a5ba6-111">パスワードは、オペレーティングシステムが含まれていないコンピューター上のドライブのロックを解除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-111">The password is used to unlock drives on your computer that do not contain the operating system.</span></span> <span data-ttu-id="a5ba6-112">起動時に PIN が要求された後、BitLocker によってパスワードが要求されます。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-112">BitLocker will ask for your password after the PIN is requested during startup.</span></span> <span data-ttu-id="a5ba6-113">コンピューター上の各 BitLocker で保護されたハードディスクには、固有のパスワードが設定されています。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-113">Each BitLocker protected hard disk on your computer has its own unique password.</span></span> <span data-ttu-id="a5ba6-114">BitLocker で保護されたドライブのロックを解除するには、パスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-114">You cannot unlock a BitLocker protected drive until you provide your password.</span></span>

<span data-ttu-id="a5ba6-115">**注** ヘルプデスクで、ドライブのロックが自動的に設定されることがあります。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-115">**Note** Your Help Desk may set drives to unlock automatically.</span></span> <span data-ttu-id="a5ba6-116">これにより、ドライブ上の情報を表示するために PIN またはパスワードを入力する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-116">This eliminates the need to provide a PIN or password to view the information on the drives.</span></span>

 

## <span data-ttu-id="a5ba6-117">PIN またはパスワードを忘れた場合にコンピューターのロックを解除する</span><span class="sxs-lookup"><span data-stu-id="a5ba6-117">Unlocking Your Computer if You Forget Your PIN or Password</span></span>


<span data-ttu-id="a5ba6-118">PIN またはパスワードを忘れた場合は、ヘルプデスクで BitLocker で保護されたドライブのロックを解除することができます。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-118">If you forget your PIN or password, your Help Desk can help you unlock BitLocker protected drives.</span></span> <span data-ttu-id="a5ba6-119">BitLocker で保護されたドライブのロックを解除するには、ヘルプが必要な場合は、ヘルプデスクにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-119">To unlock a drive protected with BitLocker, contact your Help Desk if you need help.</span></span>

**<span data-ttu-id="a5ba6-120">PIN またはパスワードを忘れた場合にコンピューターのロックを解除する方法</span><span class="sxs-lookup"><span data-stu-id="a5ba6-120">How to unlock your computer if you forget your PIN or password</span></span>**

1.  <span data-ttu-id="a5ba6-121">ヘルプデスクに連絡する際には、次の情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-121">When you contact your Help Desk, you will need to provide them with the following information:</span></span>

    -   <span data-ttu-id="a5ba6-122">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="a5ba6-122">Your user name</span></span>

    -   <span data-ttu-id="a5ba6-123">自分のドメイン</span><span class="sxs-lookup"><span data-stu-id="a5ba6-123">Your domain</span></span>

    -   <span data-ttu-id="a5ba6-124">回復キー ID の最初の8桁。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-124">The first eight digits of your recovery key ID.</span></span> <span data-ttu-id="a5ba6-125">これは、PIN またはパスワードを忘れた場合に BitLocker によって表示される32桁のコードです。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-125">This is a 32-digit code that BitLocker will display if you forget your PIN or password.</span></span>

        -   <span data-ttu-id="a5ba6-126">PIN を忘れた場合は、BitLocker 回復コンソールに表示される回復キー ID の最初の8桁を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-126">If you forget your PIN, you will have to enter the first eight digits of the recovery key ID, which will appear in the BitLocker Recovery console.</span></span> <span data-ttu-id="a5ba6-127">BitLocker 回復コンソールは、正しい PIN を入力しなかった場合に表示される Windows の前の画面です。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-127">The BitLocker Recovery console is a pre-Windows screen that will be displayed if you do not enter the correct PIN.</span></span>

        -   <span data-ttu-id="a5ba6-128">パスワードを忘れた場合は、[BitLocker 暗号化オプション] コントロールパネルアプリケーションで回復キー ID を探します。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-128">If you forget your password, look for the recovery key ID in the BitLocker Encryption Options Control Panel application.</span></span> <span data-ttu-id="a5ba6-129">[**ドライブのロック解除**] を選択し、[**パスワードを忘れ**た場合] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-129">Select **Unlock Drive** and then click **I cannot remember my password**.</span></span> <span data-ttu-id="a5ba6-130">BitLocker 暗号化オプションのアプリケーションでは、ヘルプデスクに提供した回復キー ID が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-130">The BitLocker Encryption Options application will then display a recovery key ID that you provide to Help Desk.</span></span>

2.  <span data-ttu-id="a5ba6-131">ヘルプデスクは、必要な情報を受け取ると、電話または電子メール経由で回復キーを提供します。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-131">Once your Help Desk receives the necessary information, it will provide you with a recovery key over the phone or through e-mail.</span></span>

    -   <span data-ttu-id="a5ba6-132">PIN を忘れた場合は、BitLocker 回復コンソールで回復キーを入力して、コンピューターのロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-132">If you forgot your PIN, enter the recovery key in the BitLocker Recovery console to unlock your computer.</span></span>

    -   <span data-ttu-id="a5ba6-133">パスワードを忘れた場合は、以前の回復キー ID が見つかったのと同じ場所に、[BitLocker Encryption Options] コントロールパネルアプリケーションの回復キーを入力します。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-133">If you forgot your password, enter the recovery key in the BitLocker Encryption Options Control Panel application, in the same location where you found the recovery key ID earlier.</span></span> <span data-ttu-id="a5ba6-134">これにより、保護されたハードドライブのロックが解除されます。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-134">This will unlock the protected hard drive.</span></span>

## <span data-ttu-id="a5ba6-135">PIN またはパスワードを変更する</span><span class="sxs-lookup"><span data-stu-id="a5ba6-135">Changing your PIN or Password</span></span>


<span data-ttu-id="a5ba6-136">BitLocker で保護されたドライブのパスワードを変更するには、その前にドライブのロックを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-136">Before you can change the password on a BitLocker protected drive, you must unlock the drive.</span></span> <span data-ttu-id="a5ba6-137">ドライブのロックが解除されていない場合は、[**ドライブのロック解除**] を選択して、現在のパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-137">If the drive is not unlocked, select **Unlock Drive**, and then enter your current password.</span></span> <span data-ttu-id="a5ba6-138">ドライブのロックが解除されたら、[**パスワードの管理**] を選択して、現在のパスワードを変更できます。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-138">As soon as the drive is unlocked, you can select **Manage your Password** to change your current password.</span></span>

**<span data-ttu-id="a5ba6-139">PIN またはパスワードを変更する方法</span><span class="sxs-lookup"><span data-stu-id="a5ba6-139">How to Change your PIN or password</span></span>**

1.  <span data-ttu-id="a5ba6-140">[**スタート**] をクリックし、[**コントロールパネル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-140">Click **Start**, and then select **Control Panel**.</span></span> <span data-ttu-id="a5ba6-141">コントロールパネルが新しいウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-141">Control Panel opens in a new window.</span></span>

2.  <span data-ttu-id="a5ba6-142">[**システムとセキュリティ**] を選択し、[ **BitLocker 暗号化オプション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-142">Select **System and Security**, and then select **BitLocker Encryption Options**.</span></span>

    -   <span data-ttu-id="a5ba6-143">PIN を変更するには、[ **Pin の管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-143">To change your PIN, select **Manage Your PIN**.</span></span> <span data-ttu-id="a5ba6-144">両方のフィールドに新しい PIN を入力し、[ **pin のリセット**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-144">Type your new PIN into both fields and select **Reset PIN**.</span></span>

    -   <span data-ttu-id="a5ba6-145">パスワードを変更するには、[**パスワードの管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-145">To change your password, select **Manage Your Password**.</span></span> <span data-ttu-id="a5ba6-146">両方のフィールドに新しいパスワードを入力して、[**パスワードの再設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5ba6-146">Enter your new password into both fields and select **Reset Password**.</span></span>

 

 





