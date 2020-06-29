---
title: コントロール パネルを使用して MBAM クライアントの BitLocker 暗号化オプションを管理する方法
description: コントロール パネルを使用して MBAM クライアントの BitLocker 暗号化オプションを管理する方法
author: dansimp
ms.assetid: c08077e1-5529-468f-9370-c3b33fc258f3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 271147d0e5581f6ce49fe0b46aa83dae6ae4556b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812955"
---
# <span data-ttu-id="a2b4e-103">コントロール パネルを使用して MBAM クライアントの BitLocker 暗号化オプションを管理する方法</span><span class="sxs-lookup"><span data-stu-id="a2b4e-103">How to Manage MBAM Client BitLocker Encryption Options by Using the Control Panel</span></span>


<span data-ttu-id="a2b4e-104">BitLocker 暗号化オプションと呼ばれる Microsoft BitLocker の管理と監視 (MBAM) コントロールパネルアプリケーションは、MBAM クライアントがインストールされている場合、[**システムとセキュリティ**] の下にあります。</span><span class="sxs-lookup"><span data-stu-id="a2b4e-104">A Microsoft BitLocker Administration and Monitoring (MBAM) control panel application, called BitLocker Encryption Options, will be available under **System and Security** when the MBAM Client is installed.</span></span> <span data-ttu-id="a2b4e-105">このカスタマイズされた MBAM コントロールパネルは、既定の Windows BitLocker コントロールパネルに置き換わります。</span><span class="sxs-lookup"><span data-stu-id="a2b4e-105">This customized MBAM control panel replaces the default Windows BitLocker control panel.</span></span> <span data-ttu-id="a2b4e-106">MBAM コントロールパネルでは、暗号化されたドライブ (固定およびリムーバブル) のロックを解除することができます。また、PIN やパスワードの管理にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a2b4e-106">The MBAM control panel enables you to unlock encrypted drives (fixed and removable), and also helps you manage your PIN or password.</span></span> <span data-ttu-id="a2b4e-107">MBAM コントロールパネルを有効にする方法については、「 [Windows コントロールパネルで既定の BitLocker 暗号化を非表示にする方法](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2b4e-107">For more information about enabling the MBAM control panel, see [How to Hide Default BitLocker Encryption in The Windows Control Panel](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel.md).</span></span>

<span data-ttu-id="a2b4e-108">**注** BitLocker クライアントの場合、管理者と運用ログファイルはイベントビューアーにあります。 [**アプリケーションとサービス**] では、  /  **Microsoft**  /  **Windows**の  /  **bitlockermanagement**がログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="a2b4e-108">**Note** For the BitLocker client, the Admin and Operational log files are located in Event Viewer, under **Application and Services Logs** / **Microsoft** / **Windows** / **BitLockerManagement**.</span></span>

 

**<span data-ttu-id="a2b4e-109">MBAM クライアントコントロールパネルを使用するには</span><span class="sxs-lookup"><span data-stu-id="a2b4e-109">To use the MBAM Client Control Panel</span></span>**

1.  <span data-ttu-id="a2b4e-110">BitLocker 暗号化オプションを開くには、[**スタート**] をクリックし、[**コントロールパネル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a2b4e-110">To open BitLocker Encryption Options, click **Start**, and then select **Control Panel**.</span></span> <span data-ttu-id="a2b4e-111">[**コントロールパネル]** が開いたら、[**システムとセキュリティ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a2b4e-111">When **Control Panel** opens, select **System and Security**.</span></span>

2.  <span data-ttu-id="a2b4e-112">[ **BitLocker 暗号化オプション**] をダブルクリックして、カスタマイズされた mbam コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="a2b4e-112">Double-click **BitLocker Encryption Options** to open the customized MBAM control panel.</span></span> <span data-ttu-id="a2b4e-113">コンピューター上のすべてのハードディスクドライブの一覧と、その暗号化状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2b4e-113">You will see a list of all the hard disk drives on the computer and their encryption status.</span></span> <span data-ttu-id="a2b4e-114">PIN またはパスワードを管理するためのオプションも表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2b4e-114">You will also see an option to manage your PIN or passwords.</span></span>

3.  <span data-ttu-id="a2b4e-115">コンピューターのハードディスクドライブの一覧を使用して、暗号化状態の確認、ドライブのロック解除、またはユーザーとコンピューターの除外ポリシーが展開されている場合は、BitLocker 保護の除外を要求します。</span><span class="sxs-lookup"><span data-stu-id="a2b4e-115">Use the list of hard disk drives on the computer to verify the encryption status, unlock a drive, or request an exemption for BitLocker protection if the User and Computer Exemption policies have been deployed.</span></span>

4.  <span data-ttu-id="a2b4e-116">管理者以外は、[BitLocker 暗号化オプション] コントロールパネルを使用して Pin またはパスワードを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="a2b4e-116">Non-administrators can use the BitLocker Encryption Options control panel to manage PINs or passwords.</span></span> <span data-ttu-id="a2b4e-117">ユーザーは、[ **pin の管理]** を選ぶことができます。次に、現在の pin と新しい pin の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="a2b4e-117">A user can select **Manage PIN,** and then enter both a current PIN and a new PIN.</span></span> <span data-ttu-id="a2b4e-118">また、ユーザーは新しい PIN を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="a2b4e-118">Users can also confirm their new PIN.</span></span> <span data-ttu-id="a2b4e-119">**UPDATE pin**関数は、ユーザーが選択した新しい PIN に pin をリセットします。</span><span class="sxs-lookup"><span data-stu-id="a2b4e-119">The **Update PIN** function will reset the PIN to the new one that the user selects.</span></span>

5.  <span data-ttu-id="a2b4e-120">パスワードを管理するには、[**ドライブのロック解除**] を選択し、現在のパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="a2b4e-120">To manage your password, select **Unlock drive** and enter your current password.</span></span> <span data-ttu-id="a2b4e-121">ドライブのロックが解除されたら、[**パスワードのリセット**] を選択して、現在のパスワードを変更します。</span><span class="sxs-lookup"><span data-stu-id="a2b4e-121">As soon as the drive is unlocked, select **Reset Password** to change your current password.</span></span>

## <span data-ttu-id="a2b4e-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a2b4e-122">Related topics</span></span>


[<span data-ttu-id="a2b4e-123">MBAM 1.0 機能の管理</span><span class="sxs-lookup"><span data-stu-id="a2b4e-123">Administering MBAM 1.0 Features</span></span>](administering-mbam-10-features.md)

 

 





