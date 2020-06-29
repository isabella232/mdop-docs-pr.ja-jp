---
title: エンド ユーザーが BitLocker を管理するための支援
description: エンド ユーザーが BitLocker を管理するための支援
author: dansimp
ms.assetid: 47776fb3-2d94-4970-b687-c35ec3dd6c64
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 26ef2bc33a75ff7773b75807ab0e10e5aa67b109
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824777"
---
# <span data-ttu-id="99de6-103">エンド ユーザーが BitLocker を管理するための支援</span><span class="sxs-lookup"><span data-stu-id="99de6-103">Helping End Users Manage BitLocker</span></span>


<span data-ttu-id="99de6-104">紛失または盗難されたコンピューターのコンテンツは、不正アクセスの対象となります。これにより、ユーザーと会社の両方にセキュリティ上のリスクが生じます。</span><span class="sxs-lookup"><span data-stu-id="99de6-104">Content on a lost or stolen computer is vulnerable to unauthorized access, which can present a security risk to both people and companies.</span></span> <span data-ttu-id="99de6-105">Microsoft BitLocker の管理と監視 (MBAM) では、悪意のあるユーザーから機密データを保護するために、コンピューターをロックすることによって、許可されていないアクセスを防止するために BitLocker を使用します。</span><span class="sxs-lookup"><span data-stu-id="99de6-105">Microsoft BitLocker Administration and Monitoring (MBAM) uses BitLocker to help prevent unauthorized access by locking your computer to help protect sensitive data from malicious users.</span></span>

## <span data-ttu-id="99de6-106">BitLocker とは</span><span class="sxs-lookup"><span data-stu-id="99de6-106">What is BitLocker?</span></span>


<span data-ttu-id="99de6-107">BitLocker ドライブ暗号化は、ドライブを暗号化することによって、オペレーティングシステムドライブ、データドライブ、およびリムーバブルドライブ (USB サムドライブなど) に対する保護を提供できます。</span><span class="sxs-lookup"><span data-stu-id="99de6-107">BitLocker Drive Encryption can provide protection for operating system drives, data drives, and removable drives (such as a USB thumb drive) by encrypting the drives.</span></span> <span data-ttu-id="99de6-108">BitLocker の構成によっては、暗号化されたドライブに保存されている情報のロックを解除するために、ユーザーがキー (パスワードまたは PIN) を入力する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="99de6-108">Depending on how BitLocker is configured, users may have to provide a key (a password or PIN) to unlock the information that is stored on the encrypted drives.</span></span>

<span data-ttu-id="99de6-109">BitLocker で暗号化されたドライブに新しいファイルを追加すると、BitLocker はそれらを自動的に暗号化します。</span><span class="sxs-lookup"><span data-stu-id="99de6-109">When you add new files to a drive that is encrypted with BitLocker, BitLocker encrypts them automatically.</span></span> <span data-ttu-id="99de6-110">ファイルは暗号化されたドライブに保存されている場合にのみ、暗号化されたままになります。</span><span class="sxs-lookup"><span data-stu-id="99de6-110">Files remain encrypted only while they are stored in the encrypted drive.</span></span> <span data-ttu-id="99de6-111">別のドライブまたはコンピューターにコピーされたファイルは、解読されます。</span><span class="sxs-lookup"><span data-stu-id="99de6-111">Files that are copied to another drive or computer are decrypted.</span></span> <span data-ttu-id="99de6-112">ネットワーク経由などの他のユーザーとファイルを共有している場合、これらのファイルは暗号化されたドライブに格納されている間は暗号化されますが、認証されたユーザーは通常どおりアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="99de6-112">If you share files with other users, such as through a network, these files are encrypted while stored on the encrypted drive, but they can be accessed normally by authorized users.</span></span>

<span data-ttu-id="99de6-113">オペレーティングシステムドライブを暗号化すると、起動時に BitLocker がチェックされ、セキュリティ上のリスクを表す可能性がある条件 (たとえば、BIOS への変更やスタートアップファイルへの変更など) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="99de6-113">If you encrypt the operating system drive, BitLocker checks the computer during startup for any conditions that could represent a security risk (for example, a change to the BIOS or changes to any startup files).</span></span> <span data-ttu-id="99de6-114">潜在的なセキュリティリスクが検出されると、BitLocker はオペレーティングシステムドライブをロックし、ロックを解除するために特別な BitLocker 回復キーを必要とします。</span><span class="sxs-lookup"><span data-stu-id="99de6-114">If a potential security risk is detected, BitLocker will lock the operating system drive and require a special BitLocker recovery key to unlock it.</span></span> <span data-ttu-id="99de6-115">初めて BitLocker を有効にするときは、必ずこの回復キーを作成してください。</span><span class="sxs-lookup"><span data-stu-id="99de6-115">Make sure that you create this recovery key when you turn on BitLocker for the first time.</span></span> <span data-ttu-id="99de6-116">そうしないと、ファイルへのアクセスが完全に失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="99de6-116">Otherwise, you could permanently lose access to your files.</span></span>

<span data-ttu-id="99de6-117">データドライブ (固定またはリムーバブル) を暗号化する場合は、パスワードまたはスマートカードを使用して暗号化されたドライブのロックを解除するか、コンピューターにログオンしたときに自動的にロックを解除するようにドライブを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="99de6-117">If you encrypt data drives (fixed or removable), you can unlock an encrypted drive with a password or a smart card, or set the drive to automatically unlock when you log on to the computer.</span></span>

<span data-ttu-id="99de6-118">BitLocker では、パスワードと Pin に加えて、多くの新しいコンピューターで提供されているトラステッドプラットフォームモジュール (TPM) チップを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="99de6-118">In addition to passwords and PINs, BitLocker can use the Trusted Platform Module (TPM) chip that is provided in many newer computers.</span></span> <span data-ttu-id="99de6-119">TPM チップは、BitLocker によってオペレーティングシステムドライブのロックが解除される前に、コンピューターが改ざんされていないことを確認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="99de6-119">The TPM chip is used to ensure that your computer has not been tampered with before BitLocker will unlock the operating system drive.</span></span> <span data-ttu-id="99de6-120">暗号化処理中に、TPM チップを有効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="99de6-120">During the encryption process, you may have to enable the TPM chip.</span></span> <span data-ttu-id="99de6-121">コンピューターの起動時に、BitLocker によって TPM にドライブへのキーが要求され、ロックが解除されます。</span><span class="sxs-lookup"><span data-stu-id="99de6-121">When you start your computer, BitLocker asks the TPM for the keys to the drive and unlocks it.</span></span> <span data-ttu-id="99de6-122">TPM チップを有効にするには、コンピューターを再起動してから、コンピューターソフトウェアの Windows レイヤーの前にある BIOS で設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99de6-122">To enable the TPM chip, you will have to restart your computer and then change a setting in the BIOS, a pre-Windows layer of your computer software.</span></span> <span data-ttu-id="99de6-123">TPM の詳細については、「[コンピューターの Tpm チップについ](about-the-computer-tpm-chip.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99de6-123">For more information about the TPM, see [About the Computer TPM Chip](about-the-computer-tpm-chip.md).</span></span>

<span data-ttu-id="99de6-124">コンピューターが BitLocker によって保護されると、コンピューターが休止状態または起動を開始するたびに PIN またはパスワードの入力が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="99de6-124">Once your computer is protected by BitLocker, you may have to enter a PIN or password every time that the computer wakes from hibernation or starts.</span></span> <span data-ttu-id="99de6-125">PIN またはパスワードを忘れてしまった場合は、会社や組織のヘルプデスクにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="99de6-125">The Help Desk for your company or organization can help if you ever forget your PIN or password.</span></span>

<span data-ttu-id="99de6-126">BitLocker を一時的にオフにするには、一時的に無効にするか、ドライブの暗号化を解除します。</span><span class="sxs-lookup"><span data-stu-id="99de6-126">You can turn off BitLocker, either temporarily, by suspending it, or permanently, by decrypting the drive.</span></span>

<span data-ttu-id="99de6-127">**注** BitLocker では、個々のファイルだけでなくドライブ全体が暗号化されるため、ドライブ間で機密データを移動するときには注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="99de6-127">**Note** Because BitLocker encrypts the whole drive and not just the individual files themselves, be careful when you move sensitive data between drives.</span></span> <span data-ttu-id="99de6-128">BitLocker で保護されたドライブから暗号化されていないドライブにファイルを移動すると、ファイルは暗号化されなくなります。</span><span class="sxs-lookup"><span data-stu-id="99de6-128">If you move a file from a BitLocker-protected drive to a nonencrypted drive, the file will no longer be encrypted.</span></span>

 

## <span data-ttu-id="99de6-129">BitLocker 暗号化オプションアプリケーションについて</span><span class="sxs-lookup"><span data-stu-id="99de6-129">About the BitLocker Encryption Options Application</span></span>


<span data-ttu-id="99de6-130">コンピューターのハードディスクドライブのロックを解除し、PIN とパスワードを管理するには、次の手順に従って、Windows コントロールパネルの BitLocker 暗号化オプションアプリケーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="99de6-130">To unlock hard disk drives on your computer and to manage your PIN and passwords, use the BitLocker Encryption Options application in the Windows Control Panel by following the procedure outlined here.</span></span> <span data-ttu-id="99de6-131">パスワードを入力して保護されたドライブのロックを解除し、このアプリケーションを使用して、接続されているドライブの BitLocker 状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="99de6-131">You can enter passwords to unlock protected drives and can check the BitLocker status of attached drives by using this application.</span></span>

**<span data-ttu-id="99de6-132">BitLocker 暗号化オプションアプリケーションを開くには</span><span class="sxs-lookup"><span data-stu-id="99de6-132">To open the BitLocker Encryption Options application</span></span>**

1.  <span data-ttu-id="99de6-133">[**スタート**] をクリックし、[**コントロールパネル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99de6-133">Click **Start**, and select **Control Panel**.</span></span> <span data-ttu-id="99de6-134">コントロールパネルが新しいウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="99de6-134">The Control Panel opens in a new window.</span></span>

2.  <span data-ttu-id="99de6-135">**コントロールパネル**で、[**システムとセキュリティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="99de6-135">In **Control Panel**, select **System and Security**.</span></span>

3.  <span data-ttu-id="99de6-136">[ **Bitlocker 暗号化オプション**] を選択して、Bitlocker 暗号化オプションアプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="99de6-136">Select **BitLocker Encryption Options** to open the BitLocker Encryption Options application.</span></span>

    <span data-ttu-id="99de6-137">使用可能なオプションの説明については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="99de6-137">For a description of the available options, see the following section.</span></span>

## <span data-ttu-id="99de6-138">BitLocker 暗号化オプションアプリケーションのオプション</span><span class="sxs-lookup"><span data-stu-id="99de6-138">Options on the BitLocker Encryption Options Application</span></span>


<span data-ttu-id="99de6-139">コントロールパネルの [BitLocker Encryption Options] アプリケーションを使用すると、コンピューターを保護するために BitLocker によって使用される PIN とパスワードを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="99de6-139">The BitLocker Encryption Options application on Control Panel lets you manage your PIN and passwords, which BitLocker uses to protect your computer.</span></span>

**<span data-ttu-id="99de6-140">BitLocker ドライブ暗号化–固定ディスクドライブ:</span><span class="sxs-lookup"><span data-stu-id="99de6-140">BitLocker Drive Encryption – Fixed Disk Drives:</span></span>**

<span data-ttu-id="99de6-141">このセクションでは、コンピューターに接続されているハードディスクドライブと、その現在の BitLocker 暗号化の状態に関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="99de6-141">In this section, you can view information about hard disk drives connected to your computer and their current BitLocker Encryption status.</span></span>

-   <span data-ttu-id="99de6-142">**Pin を管理**する-BitLocker によって使用される pin を変更して、オペレーティングシステムドライブのロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="99de6-142">**Manage your PIN** - changes the PIN used by BitLocker to unlock your operating system drive.</span></span>

-   <span data-ttu-id="99de6-143">**パスワードの管理**-BitLocker で使用されるパスワードを変更して、他の内部ドライブのロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="99de6-143">**Manage your password** - changes the password that is used by BitLocker to unlock your other internal drives.</span></span>

**<span data-ttu-id="99de6-144">BitLocker ドライブ暗号化-外部ドライブ:</span><span class="sxs-lookup"><span data-stu-id="99de6-144">BitLocker Drive Encryption - External Drives:</span></span>**

<span data-ttu-id="99de6-145">このセクションでは、コンピューターに接続されている外部ドライブ (USB サムドライブなど) と、その現在の BitLocker 暗号化の状態に関する情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="99de6-145">In this section, you can view information about external drives (such as a USB thumb drive) connected to your computer, and their current BitLocker encryption status.</span></span>

-   <span data-ttu-id="99de6-146">**パスワードの管理**-BitLocker で使用されるパスワードを変更して、他の内部ドライブのロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="99de6-146">**Manage your password** - changes the password that is used by BitLocker to unlock your other internal drives.</span></span>

**<span data-ttu-id="99de6-147">オプション</span><span class="sxs-lookup"><span data-stu-id="99de6-147">Advanced:</span></span>**

-   <span data-ttu-id="99de6-148">**Tpm 管理**-別のウィンドウで tpm 管理ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="99de6-148">**TPM Administration** - opens the TPM Administration tool in a separate window.</span></span> <span data-ttu-id="99de6-149">ここから、一般的な TPM タスクを構成し、TPM チップセットに関する情報を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="99de6-149">From here you can configure common TPM tasks and obtain information about the TPM chipset.</span></span> <span data-ttu-id="99de6-150">このツールにアクセスするには、コンピューターの管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="99de6-150">You must have administrative permissions on your computer to access this tool.</span></span>

-   <span data-ttu-id="99de6-151">**ディスクの管理**-ディスク管理ツールを開きます。</span><span class="sxs-lookup"><span data-stu-id="99de6-151">**Disk Management** -open the Disk Management tool.</span></span> <span data-ttu-id="99de6-152">ここでは、コンピューターに接続されているすべてのハードドライブの情報を表示して、パーティションとドライブのオプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="99de6-152">From here you can view the information for all hard drives connected to the computer and configure partitions and drive options.</span></span> <span data-ttu-id="99de6-153">このツールにアクセスするには、コンピューターの管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="99de6-153">You must have administrative rights on your computer to access this tool.</span></span>

 

 





