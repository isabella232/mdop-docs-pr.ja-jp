---
title: 破損しているドライブを回復する方法
description: 破損しているドライブを回復する方法
author: dansimp
ms.assetid: 715491ae-69c0-4fae-ad3f-3bd19a0db2f2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 545ff5c7e6bea29d5f89cce1cf18212b7d0e2870
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812946"
---
# <span data-ttu-id="116d5-103">破損しているドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="116d5-103">How to Recover a Corrupted Drive</span></span>


<span data-ttu-id="116d5-104">BitLocker によって保護されている破損したドライブを回復するために、Microsoft BitLocker 管理および監視 (MBAM) ヘルプデスクユーザーは回復キーパッケージファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="116d5-104">To recover a corrupted drive that has been protected by BitLocker, a Microsoft BitLocker Administration and Monitoring (MBAM) help desk user must create a recovery key package file.</span></span> <span data-ttu-id="116d5-105">このパッケージファイルは、破損したドライブが含まれているコンピューターにコピーして、ドライブの回復に使用することができます。</span><span class="sxs-lookup"><span data-stu-id="116d5-105">This package file can be copied to the computer that contains the corrupted drive and then used to recover the drive.</span></span> <span data-ttu-id="116d5-106">これを実現するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="116d5-106">To accomplish this, use the following procedure.</span></span>

**<span data-ttu-id="116d5-107">破損したドライブを回復するには</span><span class="sxs-lookup"><span data-stu-id="116d5-107">To Recover a Corrupted Drive</span></span>**

1.  <span data-ttu-id="116d5-108">MBAM 管理 web サイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="116d5-108">Open the MBAM administration website.</span></span>

2.  <span data-ttu-id="116d5-109">ナビゲーションウィンドウから [**ドライブの回復**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="116d5-109">Select **Drive Recovery** from the navigation pane.</span></span> <span data-ttu-id="116d5-110">ユーザーのドメイン名とユーザー名、ドライブのロックを解除する理由、およびユーザーの回復パスワード ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="116d5-110">Enter the user’s domain name and user name, the reason for unlocking the drive, and the user’s recovery password ID.</span></span>

    <span data-ttu-id="116d5-111">**注** ヘルプデスク管理者ロールのメンバーである場合は、ユーザーのドメイン名またはユーザー名を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="116d5-111">**Note** If you are a member of the Help Desk Administrators role, you do not have to enter the user’s domain name or user name.</span></span>

     

3.  <span data-ttu-id="116d5-112">**[送信]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="116d5-112">Click **Submit**.</span></span> <span data-ttu-id="116d5-113">回復キーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="116d5-113">The recovery key will be displayed.</span></span>

4.  <span data-ttu-id="116d5-114">[**保存**] をクリックし、[**回復キーパッケージ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="116d5-114">Click **Save**, and then select **Recovery Key Package**.</span></span> <span data-ttu-id="116d5-115">回復キーパッケージはコンピューター上に作成されます。</span><span class="sxs-lookup"><span data-stu-id="116d5-115">The recovery key package will be created on your computer.</span></span>

5.  <span data-ttu-id="116d5-116">破損したドライブがあるコンピューターに回復キーパッケージをコピーします。</span><span class="sxs-lookup"><span data-stu-id="116d5-116">Copy the recovery key package to the computer that has the corrupted drive.</span></span>

6.  <span data-ttu-id="116d5-117">管理者特権でコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="116d5-117">Open an elevated command prompt.</span></span> <span data-ttu-id="116d5-118">この操作を行うには、[**スタート**] をクリックし `cmd` 、[**プログラムとファイルの検索**] ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="116d5-118">To do this, click **Start** and type `cmd` in the **Search programs and files** box.</span></span> <span data-ttu-id="116d5-119">検索結果の一覧で**cmd.exe**を右クリックし、[**管理者として実行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="116d5-119">In the search results list, right-click **cmd.exe** and select **Run as Administrator**.</span></span>

7.  <span data-ttu-id="116d5-120">コマンドプロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="116d5-120">At the command prompt, type the following:</span></span>

    `repair-bde <fixed drive> <corrupted drive> -kp <location of keypackage> -rp <recovery password>`

    <span data-ttu-id="116d5-121">**注** コマンドの &lt; 固定ドライブの場合は &gt; 、破損したドライブ上のデータと同等またはそれ以上の空き領域がある利用可能な記憶域デバイスを指定します。</span><span class="sxs-lookup"><span data-stu-id="116d5-121">**Note** For the &lt;fixed drive&gt; in the command, specify an available storage device that has free space equal to or larger than the data on the corrupted drive.</span></span> <span data-ttu-id="116d5-122">破損したドライブ上のデータが回復され、指定された固定ドライブに移動されます。</span><span class="sxs-lookup"><span data-stu-id="116d5-122">Data on the corrupted drive is recovered and moved to the specified fixed drive.</span></span>

     

## <span data-ttu-id="116d5-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="116d5-123">Related topics</span></span>


[<span data-ttu-id="116d5-124">MBAM での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="116d5-124">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam.md)

 

 





