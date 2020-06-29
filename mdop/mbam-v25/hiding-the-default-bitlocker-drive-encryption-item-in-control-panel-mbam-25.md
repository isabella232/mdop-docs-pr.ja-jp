---
title: コントロール パネルの既定の BitLocker ドライブ暗号化項目を非表示にする
description: コントロール パネルの既定の BitLocker ドライブ暗号化項目を非表示にする
author: dansimp
ms.assetid: 6e2a9a02-a809-43a1-80a3-1b03c7192c89
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: af395928ca8934bfea4eeb848bbd4ee377987293
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823097"
---
# <span data-ttu-id="13e8b-103">コントロール パネルの既定の BitLocker ドライブ暗号化項目を非表示にする</span><span class="sxs-lookup"><span data-stu-id="13e8b-103">Hiding the Default BitLocker Drive Encryption Item in Control Panel</span></span>


<span data-ttu-id="13e8b-104">このトピックでは、Windows オペレーティングシステムの一部としてコントロールパネルに既定で表示される、 **BitLocker ドライブ暗号化**コントロールパネルの項目を非表示にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="13e8b-104">This topic describes how to hide the **BitLocker Drive Encryption** Control Panel item, which appears by default on Control Panel as part of the Windows operating system.</span></span>

<span data-ttu-id="13e8b-105">**注** Microsoft BitLocker の管理と監視 (MBAM) [ **Bitlocker 暗号化オプション**] という追加のカスタムコントロールパネル項目を作成します。これにより、エンドユーザーは PIN とパスワードを管理し、bitlocker をドライブに対して有効にし、暗号化を確認できます。</span><span class="sxs-lookup"><span data-stu-id="13e8b-105">**Note** Microsoft BitLocker Administration and Monitoring (MBAM) creates an additional, custom Control Panel item, called **BitLocker Encryption Options**, which enables end users to manage their PIN and password, turn on BitLocker for a drive, and check encryption.</span></span>

 

<span data-ttu-id="13e8b-106">詳細については[、「コントロールパネルの Bitlocker 暗号化オプションと Bitlocker ドライブ暗号化項目](understanding-the-bitlocker-encryption-options-and-bitlocker-drive-encryption-items-in-control-panel.md)について」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13e8b-106">See [Understanding the BitLocker Encryption Options and BitLocker Drive Encryption Items in Control Panel](understanding-the-bitlocker-encryption-options-and-bitlocker-drive-encryption-items-in-control-panel.md) to read about:</span></span>

-   <span data-ttu-id="13e8b-107">MBAM と既定のコントロールパネルアイテムの相違点</span><span class="sxs-lookup"><span data-stu-id="13e8b-107">Differences between the MBAM and the default Control Panel items</span></span>

-   <span data-ttu-id="13e8b-108">Windows エクスプローラーでドライブを右クリックすると表示される BitLocker ショートカットメニューを**管理**する</span><span class="sxs-lookup"><span data-stu-id="13e8b-108">**Manage BitLocker** shortcut menu that appears when you right-click a drive in Windows Explorer</span></span>

<span data-ttu-id="13e8b-109">**重要** **BitLocker ドライブ暗号化**ノードのグループポリシー設定は変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="13e8b-109">**Important** Do not change the Group Policy settings in the **BitLocker Drive Encryption** node.</span></span> <span data-ttu-id="13e8b-110">この場合、MBAM は正しく動作しません。</span><span class="sxs-lookup"><span data-stu-id="13e8b-110">If you do, MBAM will not work correctly.</span></span> <span data-ttu-id="13e8b-111">[ **MDOP mbam (BitLocker Management)** ] ノードでグループポリシー設定を構成すると、mbam が自動的に**bitlocker ドライブ暗号化**設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="13e8b-111">When you configure the Group Policy settings in the **MDOP MBAM (BitLocker Management)** node, MBAM automatically configures the **BitLocker Drive Encryption** settings for you.</span></span>

 

**<span data-ttu-id="13e8b-112">コントロールパネルの既定の BitLocker ドライブ暗号化項目を非表示にするには</span><span class="sxs-lookup"><span data-stu-id="13e8b-112">To hide the default BitLocker Drive Encryption item in Control Panel</span></span>**

1.  <span data-ttu-id="13e8b-113">グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理で、**ユーザー構成** &gt; **ポリシー**の &gt; **管理用テンプレート**の [ &gt; **コントロールパネル]** を参照します。</span><span class="sxs-lookup"><span data-stu-id="13e8b-113">In the Group Policy Management Console (GPMC) or in Advanced Group Policy Management, browse to **User configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Control Panel**.</span></span>

2.  <span data-ttu-id="13e8b-114">**詳細**ウィンドウで、[**指定したコントロールパネルの項目を非表示**にする] をダブルクリックし、[**有効**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13e8b-114">In the **Details** pane, double-click **Hide specified Control Panel items**, and then click **Enabled**.</span></span>

3.  <span data-ttu-id="13e8b-115">[**表示**] をクリックし、[**追加**] をクリックして、「Microsoft」と入力します **。**</span><span class="sxs-lookup"><span data-stu-id="13e8b-115">Click **Show**, click **Add**, and then type **Microsoft.BitLockerDriveEncryption**.</span></span>



## <span data-ttu-id="13e8b-116">関連トピック</span><span class="sxs-lookup"><span data-stu-id="13e8b-116">Related topics</span></span>


[<span data-ttu-id="13e8b-117">コントロール パネルの [BitLocker 暗号化のオプション] 項目と [BitLocker ドライブ暗号化] 項目について</span><span class="sxs-lookup"><span data-stu-id="13e8b-117">Understanding the BitLocker Encryption Options and BitLocker Drive Encryption Items in Control Panel</span></span>](understanding-the-bitlocker-encryption-options-and-bitlocker-drive-encryption-items-in-control-panel.md)

[<span data-ttu-id="13e8b-118">MBAM 2.5 グループ ポリシー オブジェクトの展開</span><span class="sxs-lookup"><span data-stu-id="13e8b-118">Deploying MBAM 2.5 Group Policy Objects</span></span>](deploying-mbam-25-group-policy-objects.md)

 

## <span data-ttu-id="13e8b-119">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="13e8b-119">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="13e8b-120">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="13e8b-120">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="13e8b-121">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="13e8b-121">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





