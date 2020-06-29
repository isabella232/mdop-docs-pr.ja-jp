---
title: 破損しているドライブを回復する方法
description: 破損しているドライブを回復する方法
author: dansimp
ms.assetid: b0457a00-f72e-4ad8-ab3b-7701851ca87e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5bbd4c2a1f5ef3fde78a9f72c1f77ccb0cdea377
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822874"
---
# <span data-ttu-id="36362-103">破損しているドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="36362-103">How to Recover a Corrupted Drive</span></span>


<span data-ttu-id="36362-104">BitLocker によって保護されている破損したドライブを回復するには、Microsoft BitLocker 管理および監視 (MBAM) ヘルプデスクユーザーは回復キーパッケージファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36362-104">To recover a corrupted drive protected by BitLocker, a Microsoft BitLocker Administration and Monitoring (MBAM) Help Desk user will need to create a recovery key package file.</span></span> <span data-ttu-id="36362-105">このパッケージファイルは、破損したドライブが含まれているコンピューターにコピーして、ドライブの回復に使用することができます。</span><span class="sxs-lookup"><span data-stu-id="36362-105">This package file can then be copied to the computer that contains the corrupted drive, and then used to recover the drive.</span></span> <span data-ttu-id="36362-106">この操作を実行するために必要な手順については、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="36362-106">Use the following procedure for the steps needed to do this.</span></span>

<span data-ttu-id="36362-107">**重要** データが失われる可能性を回避するために、次の手順を完了する前に、"修復-bde" のヘルプを読み、コマンドの使い方を明確に理解しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="36362-107">**Important** To avoid a potential loss of data, it is strongly recommended that you read the “repair-bde” help and clearly understand how to use the command before completing the following instructions.</span></span>

 

**<span data-ttu-id="36362-108">破損したドライブを回復するには</span><span class="sxs-lookup"><span data-stu-id="36362-108">To recover a corrupted drive</span></span>**

1.  <span data-ttu-id="36362-109">破損したドライブを復元するために必要な回復キーパッケージを作成するには、web ブラウザーを起動して、MBAM 管理と監視 web サイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="36362-109">To create the recovery key package necessary to recover a corrupted drive, start a web browser and open the MBAM Administration and Monitoring website.</span></span>

2.  <span data-ttu-id="36362-110">左側のナビゲーションウィンドウから [**ドライブの回復**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="36362-110">Select **Drive Recovery** from the left navigation pane.</span></span> <span data-ttu-id="36362-111">ユーザーのドメイン名、ユーザー名、ドライブのロックを解除する理由、ユーザーの回復パスワード ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="36362-111">Enter the user’s domain name, user name, reason for unlocking the drive, and the user’s recovery password ID.</span></span>

    <span data-ttu-id="36362-112">**注** ヘルプデスク管理者ロールのメンバーである場合は、ユーザーのドメイン名またはユーザー名を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="36362-112">**Note** If you are a member of the Help Desk Administrators role, you do not have to enter the user’s domain name or user name.</span></span>

     

3.  <span data-ttu-id="36362-113">**[送信]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="36362-113">Click **Submit**.</span></span> <span data-ttu-id="36362-114">回復キーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="36362-114">The recovery key will be displayed.</span></span>

4.  <span data-ttu-id="36362-115">[**保存**] をクリックし、[**回復キーパッケージ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36362-115">Click **Save**, and then select **Recovery Key Package**.</span></span> <span data-ttu-id="36362-116">回復キーパッケージはコンピューター上に作成されます。</span><span class="sxs-lookup"><span data-stu-id="36362-116">The recovery key package will be created on your computer.</span></span>

5.  <span data-ttu-id="36362-117">破損したドライブがあるコンピューターに回復キーパッケージをコピーします。</span><span class="sxs-lookup"><span data-stu-id="36362-117">Copy the recovery key package to the computer that has the corrupted drive.</span></span>

6.  <span data-ttu-id="36362-118">管理者特権でコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="36362-118">Open an elevated command prompt.</span></span> <span data-ttu-id="36362-119">この操作を行うには、[**スタート**] をクリックし `cmd` 、[**プログラムとファイルの検索] ボックス**に入力します。</span><span class="sxs-lookup"><span data-stu-id="36362-119">To do this, click **Start** and type `cmd` in the **Search programs and files box**.</span></span> <span data-ttu-id="36362-120">**cmd.exe**を右クリックし、[**管理者として実行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36362-120">Right-click **cmd.exe** and select **Run as Administrator**.</span></span>

7.  <span data-ttu-id="36362-121">コマンドプロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="36362-121">At the command prompt, type the following:</span></span>

    `repair-bde <corrupted drive> <fixed drive> -kp <location of keypackage> -rp <recovery password>`

    <span data-ttu-id="36362-122">**注** &lt;破損した &gt; ドライブ上のデータと同サイズ以上の空き領域がある、使用可能なハードディスクドライブに固定ドライブを置きます。</span><span class="sxs-lookup"><span data-stu-id="36362-122">**Note** Replace &lt;fixed drive&gt; with an available hard disk drive that has free space equal to or larger than the data on the corrupted drive.</span></span> <span data-ttu-id="36362-123">破損したドライブ上のデータが回復され、指定されたハードディスクドライブに移動されます。</span><span class="sxs-lookup"><span data-stu-id="36362-123">Data on the corrupted drive is recovered and moved to the specified hard disk drive.</span></span>

     

## <span data-ttu-id="36362-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="36362-124">Related topics</span></span>


[<span data-ttu-id="36362-125">MBAM での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="36362-125">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





