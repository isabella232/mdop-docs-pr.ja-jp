---
title: Windows コントロール パネルで既定の BitLocker 暗号化を非表示にする方法
description: Windows コントロール パネルで既定の BitLocker 暗号化を非表示にする方法
author: dansimp
ms.assetid: c8503743-220c-497c-9785-e2feeca484d6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 67a61763e556f8c3b93825220dbbd61a14b7d6f4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824507"
---
# <span data-ttu-id="fff89-103">Windows コントロール パネルで既定の BitLocker 暗号化を非表示にする方法</span><span class="sxs-lookup"><span data-stu-id="fff89-103">How to Hide Default BitLocker Encryption in The Windows Control Panel</span></span>


<span data-ttu-id="fff89-104">Microsoft BitLocker の管理と監視 (MBAM) は、「BitLocker 暗号化オプション」と呼ばれる MBAM クライアントコンピューター用にカスタマイズされたコントロールパネルを提供します。</span><span class="sxs-lookup"><span data-stu-id="fff89-104">Microsoft BitLocker Administration and Monitoring (MBAM) offers a customized control panel for MBAM client computers that is named called BitLocker Encryption Options.</span></span> <span data-ttu-id="fff89-105">このカスタマイズされたコントロールパネルでは、BitLocker ドライブ暗号化という名前の既定の Windows BitLocker コントロールパネルを置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="fff89-105">This customized control panel can replace the default Windows BitLocker control panel that is named BitLocker Drive Encryption.</span></span> <span data-ttu-id="fff89-106">Windows コントロールパネルの [システムとセキュリティ] の下にある [BitLocker 暗号化オプション] コントロールパネルを使用すると、ユーザーは PIN とパスワードを管理したり、ドライブのロックを解除したり、管理者がドライブの暗号化を解除したり、BitLocker 暗号化を停止または再開したりするためのインターフェイスを非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fff89-106">The BitLocker Encryption Options control panel, located under System and Security in the Windows control panel, enables users to manage their PIN and passwords, unlock drives, and hides the interface that allows administrators to decrypt a drive or to suspend or resume BitLocker encryption.</span></span>

**<span data-ttu-id="fff89-107">Windows の [コントロールパネル] で既定の BitLocker 暗号化を非表示にするには</span><span class="sxs-lookup"><span data-stu-id="fff89-107">To hide default BitLocker Encryption in the Windows Control Panel</span></span>**

1.  <span data-ttu-id="fff89-108">グループポリシー管理コンソール (GPMC)、高度なグループポリシー管理 (AGPM)、または、BitLocker グループポリシーコンピューターのローカルグループポリシーエディターを使用して、**ユーザーの構成**を参照します。</span><span class="sxs-lookup"><span data-stu-id="fff89-108">Browse to **User configuration** by using the Group Policy Management Console (GPMC), the Advanced Group Policy Management (AGPM), or the Local Group Policy Editor on the BitLocker Group Policies computer.</span></span>

2.  <span data-ttu-id="fff89-109">[**ポリシー**] をクリックし、[**管理用テンプレート**] をクリックして、[**コントロールパネル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fff89-109">Click **Policies**, select **Administrative Templates**, and then click **Control Panel**.</span></span>

3.  <span data-ttu-id="fff89-110">**詳細**ウィンドウで、[**指定したコントロールパネルの項目を非表示**にする] をダブルクリックし、[**有効**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fff89-110">In the **Details** pane, double-click **Hide specified Control Panel items**, and then select **Enabled**.</span></span>

4.  <span data-ttu-id="fff89-111">[**表示**] をクリックし、 **[追加] をクリック**して、「Microsoft」と入力します。</span><span class="sxs-lookup"><span data-stu-id="fff89-111">Click **Show**, **click Add…**, and then type Microsoft.BitLockerDriveEncryption.</span></span> <span data-ttu-id="fff89-112">このポリシーでは、windows の [コントロールパネル] から既定の Windows BitLocker 管理ツールを非表示にし、ユーザーが Windows のコントロールパネルから更新された MBAM BitLocker 暗号化オプションツールを開くことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="fff89-112">This policy hides the default Windows BitLocker Management tool from the Windows Control Panel and allows the user to open the updated MBAM BitLocker Encryption Options tool from the Windows Control Panel.</span></span>

## <span data-ttu-id="fff89-113">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fff89-113">Related topics</span></span>


[<span data-ttu-id="fff89-114">MBAM 1.0 グループ ポリシー オブジェクトの展開</span><span class="sxs-lookup"><span data-stu-id="fff89-114">Deploying MBAM 1.0 Group Policy Objects</span></span>](deploying-mbam-10-group-policy-objects.md)

 

 





