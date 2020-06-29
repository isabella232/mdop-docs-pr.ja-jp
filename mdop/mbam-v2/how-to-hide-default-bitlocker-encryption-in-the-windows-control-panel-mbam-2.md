---
title: Windows コントロール パネルで既定の BitLocker 暗号化を非表示にする方法
description: Windows コントロール パネルで既定の BitLocker 暗号化を非表示にする方法
author: dansimp
ms.assetid: 6674aa51-2b5d-4e4a-8b43-2cc18d008285
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: eda8fafbd7b3ebf414520354eba6def2e97f6237
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824084"
---
# <span data-ttu-id="78606-103">Windows コントロール パネルで既定の BitLocker 暗号化を非表示にする方法</span><span class="sxs-lookup"><span data-stu-id="78606-103">How to Hide Default BitLocker Encryption in the Windows Control Panel</span></span>


<span data-ttu-id="78606-104">Microsoft BitLocker の管理と監視 (MBAM) では、Microsoft BitLocker の管理および監視クライアントコンピューター (BitLocker 暗号化オプション) 向けにカスタマイズされたコントロールパネルを提供しています。</span><span class="sxs-lookup"><span data-stu-id="78606-104">Microsoft BitLocker Administration and Monitoring (MBAM) offers a customized control panel for Microsoft BitLocker Administration and Monitoring client computers, called BitLocker Encryption Options.</span></span> <span data-ttu-id="78606-105">このカスタマイズされたコントロールパネルは、BitLocker ドライブ暗号化と呼ばれる、既定の Windows BitLocker コントロールパネルを置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="78606-105">This customized control panel can replace the default Windows BitLocker control panel, which is called BitLocker Drive Encryption.</span></span> <span data-ttu-id="78606-106">コントロールパネルの [システムとセキュリティ] の下にあるカスタマイズされたコントロールパネルを使用すると、ユーザーは PIN とパスワードを管理したり、ドライブのロックを解除したり、管理者がドライブの暗号化を解除したり、BitLocker ドライブの暗号化を停止または再開したりするためのインターフェイスを非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="78606-106">The customized control panel, which is in Control Panel under System and Security, enables users to manage their PIN and passwords and to unlock drives, and hides the interface that enables administrators to decrypt a drive or to suspend or resume BitLocker drive encryption.</span></span>

**<span data-ttu-id="78606-107">Windows のコントロールパネルで既定の BitLocker ドライブ暗号化を非表示にするには</span><span class="sxs-lookup"><span data-stu-id="78606-107">To hide default BitLocker drive encryption in Windows Control Panel</span></span>**

1.  <span data-ttu-id="78606-108">グループポリシー管理コンソール (GPMC)、高度なグループポリシー管理 (AGPM)、または、BitLocker グループポリシーコンピューターのローカルグループポリシーエディターで、[ユーザーの**構成**] を参照します。</span><span class="sxs-lookup"><span data-stu-id="78606-108">In the Group Policy Management Console (GPMC), the Advanced Group Policy Management (AGPM), or the Local Group Policy Editor on the BitLocker Group Policies computer, browse to **User configuration**.</span></span>

2.  <span data-ttu-id="78606-109">次に、[**ポリシー**] をクリックし、[**管理用テンプレート**] を選択して、[**コントロールパネル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78606-109">Next, click **Policies**, select **Administrative Templates**, and then click **Control Panel**.</span></span>

3.  <span data-ttu-id="78606-110">[**詳細**] ウィンドウで、[**指定したコントロールパネルの項目を非表示**にする] をダブルクリックし、[**有効**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="78606-110">Double-click **Hide specified Control Panel items** in the **Details** pane, and then select **Enabled**.</span></span>

4.  <span data-ttu-id="78606-111">[**表示**] をクリックし、[**追加**] をクリックして、「Microsoft」と入力します **。**</span><span class="sxs-lookup"><span data-stu-id="78606-111">Click **Show**, click **Add**, and then type **Microsoft.BitLockerDriveEncryption**.</span></span> <span data-ttu-id="78606-112">このポリシーでは、Windows の [コントロールパネル] から既定の Windows BitLocker 管理ツールを非表示にします。コントロールパネルで、ユーザーは [システムとセキュリティ] の下にある更新された MBAM BitLocker 暗号化オプションツールを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="78606-112">This policy hides the default Windows BitLocker Management tool from the Windows Control Panel and, in Control Panel, lets the user open the updated MBAM BitLocker Encryption Options tool under System and Security.</span></span>

## <span data-ttu-id="78606-113">関連トピック</span><span class="sxs-lookup"><span data-stu-id="78606-113">Related topics</span></span>


[<span data-ttu-id="78606-114">MBAM 2.0 グループ ポリシー オブジェクトの展開</span><span class="sxs-lookup"><span data-stu-id="78606-114">Deploying MBAM 2.0 Group Policy Objects</span></span>](deploying-mbam-20-group-policy-objects-mbam-2.md)

 

 





