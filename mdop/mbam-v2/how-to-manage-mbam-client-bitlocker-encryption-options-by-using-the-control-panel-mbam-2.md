---
title: コントロール パネルを使用して MBAM クライアントの BitLocker 暗号化オプションを管理する方法
description: コントロール パネルを使用して MBAM クライアントの BitLocker 暗号化オプションを管理する方法
author: dansimp
ms.assetid: e2ff153e-5770-4a12-b79d-cda998b8a8ab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a42901ac9d8a1a3527712f4cf342b5c0ca9ffdfd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825107"
---
# <span data-ttu-id="5e810-103">コントロール パネルを使用して MBAM クライアントの BitLocker 暗号化オプションを管理する方法</span><span class="sxs-lookup"><span data-stu-id="5e810-103">How to Manage MBAM Client BitLocker Encryption Options by Using the Control Panel</span></span>


<span data-ttu-id="5e810-104">Microsoft bitlocker の管理と監視 (MBAM) コントロールパネルアプリケーション (BitLocker 暗号化オプションと呼ばれます) は、Microsoft BitLocker 管理および監視クライアントがインストールされている場合、[**システムとセキュリティ**] の下にあります。</span><span class="sxs-lookup"><span data-stu-id="5e810-104">A Microsoft BitLocker Administration and Monitoring (MBAM) control panel application, called BitLocker Encryption Options, will be available under **System and Security** when the Microsoft BitLocker Administration and Monitoring Client is installed.</span></span> <span data-ttu-id="5e810-105">このカスタムの MBAM コントロールパネルは、追加のコントロールパネルです。</span><span class="sxs-lookup"><span data-stu-id="5e810-105">This custom MBAM control panel is an additional control panel.</span></span> <span data-ttu-id="5e810-106">既定の Windows BitLocker コントロールパネルに代わるものではありません。</span><span class="sxs-lookup"><span data-stu-id="5e810-106">It does not replace the default Windows BitLocker control panel.</span></span> <span data-ttu-id="5e810-107">MBAM コントロールパネルを使用すると、暗号化された固定ドライブとリムーバブルドライブのロックを解除し、PIN またはパスワードを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="5e810-107">The MBAM control panel can be used to unlock encrypted fixed and removable drives, and also manage your PIN or password.</span></span> <span data-ttu-id="5e810-108">MBAM コントロールパネルを有効にする方法については、「 [Windows コントロールパネルで既定の BitLocker 暗号化を非表示にする方法](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e810-108">For more information about enabling the MBAM control panel, see [How to Hide Default BitLocker Encryption in the Windows Control Panel](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel-mbam-2.md).</span></span>

**<span data-ttu-id="5e810-109">MBAM クライアントコントロールパネルを使用するには</span><span class="sxs-lookup"><span data-stu-id="5e810-109">To use the MBAM Client Control Panel</span></span>**

1.  <span data-ttu-id="5e810-110">BitLocker 暗号化オプションを開くには、[**スタート**] をクリックし、[**コントロールパネル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5e810-110">To open BitLocker Encryption Options, click **Start** and then select **Control Panel**.</span></span> <span data-ttu-id="5e810-111">[**コントロールパネル]** が開いたら、[**システムとセキュリティ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5e810-111">When **Control Panel** opens, select **System and Security**.</span></span>

2.  <span data-ttu-id="5e810-112">[ **BitLocker 暗号化オプション**] をダブルクリックして、カスタマイズされた mbam コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5e810-112">Double-click **BitLocker Encryption Options** to open the customized MBAM control panel.</span></span> <span data-ttu-id="5e810-113">コンピューター上のすべてのハードディスクドライブの一覧と、そのパスワードを管理するためのオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5e810-113">You will see a list of all the hard disk drives on the computer and their encryption status, in addition to an option to manage your PIN or passwords.</span></span>

    <span data-ttu-id="5e810-114">コンピューターのハードディスクドライブの一覧を使用して、暗号化の状態の確認、ドライブのロック解除、またはユーザーとコンピューターの適用除外ポリシーが展開されている場合に BitLocker 保護の除外を要求することができます。</span><span class="sxs-lookup"><span data-stu-id="5e810-114">The list of hard disk drives on the computer can be used to verify encryption status, unlock a drive, or request an exemption for BitLocker protection if the User and Computer Exemption policies have been deployed.</span></span>

    <span data-ttu-id="5e810-115">[BitLocker 暗号化オプション] コントロールパネルでは、管理者以外のユーザーが PIN またはパスワードを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="5e810-115">The BitLocker Encryption Options control panel also allows for non-administrator users to manage their PIN or passwords.</span></span> <span data-ttu-id="5e810-116">[ **PIN の管理**] を選ぶと、ユーザーは現在の pin と新しい pin の両方を入力するように求められます (新しい pin の確認に加えて)。</span><span class="sxs-lookup"><span data-stu-id="5e810-116">By selecting **Manage PIN**, users are prompted to enter both a current PIN and a new PIN (in addition to confirming the new PIN).</span></span> <span data-ttu-id="5e810-117">[ **Pin の更新**] を選ぶと、ユーザーが選択した新しい PIN に pin がリセットされます。</span><span class="sxs-lookup"><span data-stu-id="5e810-117">Selecting **Update PIN** will reset the PIN to the new one that the users selected.</span></span>

    <span data-ttu-id="5e810-118">パスワードを管理するには、[**ドライブのロック解除**] を選択し、現在のパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="5e810-118">To manage your password, select **Unlock drive** and enter your current password.</span></span> <span data-ttu-id="5e810-119">ドライブのロックが解除されたら、[**パスワードのリセット**] を選択して、現在のパスワードを変更します。</span><span class="sxs-lookup"><span data-stu-id="5e810-119">As soon as the drive is unlocked, select **Reset Password** to change your current password.</span></span>

## <span data-ttu-id="5e810-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5e810-120">Related topics</span></span>


[<span data-ttu-id="5e810-121">MBAM 2.0 機能の管理</span><span class="sxs-lookup"><span data-stu-id="5e810-121">Administering MBAM 2.0 Features</span></span>](administering-mbam-20-features-mbam-2.md)

 

 





