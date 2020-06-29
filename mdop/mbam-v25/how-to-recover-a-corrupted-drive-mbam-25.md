---
title: 破損しているドライブを回復する方法
description: 破損しているドライブを回復する方法
author: dansimp
ms.assetid: fa5b846b-dda6-4ae4-bf6c-39e4f1d8aa00
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fd9fd8a65d57cbfe965197fa26b57319ee046784
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822554"
---
# <span data-ttu-id="9a4ad-103">破損しているドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="9a4ad-103">How to Recover a Corrupted Drive</span></span>


<span data-ttu-id="9a4ad-104">この手順は、BitLocker で保護されている破損したドライブを回復するために、管理と監視の Web サイト (ヘルプデスクとも呼ばれます) と共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-104">You can use this procedure with the Administration and Monitoring Website (also referred to as the Help Desk) Website to recover a corrupted drive that is protected by BitLocker.</span></span> <span data-ttu-id="9a4ad-105">これを行うには、次の表で説明されているタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-105">To do this, you will complete the tasks outlined in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9a4ad-106">タスク</span><span class="sxs-lookup"><span data-stu-id="9a4ad-106">Task</span></span></th>
<th align="left"><span data-ttu-id="9a4ad-107">詳細と詳細情報</span><span class="sxs-lookup"><span data-stu-id="9a4ad-107">Details and more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9a4ad-108"><strong> </strong> 管理と監視の web サイトのドライブ回復領域にアクセスして、回復キーパッケージファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-108">Create a recovery key package file by accessing the <strong>Drive Recovery</strong> area of the Administration and Monitoring Website.</span></span></p></td>
<td align="left"><p><span data-ttu-id="9a4ad-109">[ドライブ回復] 領域にアクセスするには、 <strong> </strong> Mbam ヘルプデスクユーザーロールまたは Mbam Advanced ヘルプデスクユーザーの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-109">To access the <strong>Drive Recovery</strong> area, you must be assigned the MBAM Helpdesk Users role or the MBAM Advanced Helpdesk Users role.</span></span> <span data-ttu-id="9a4ad-110">これらの役割は、作成時に異なる名前を指定した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-110">You may have given these roles different names when you created them.</span></span> <span data-ttu-id="9a4ad-111">詳細については、「 <a href="planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles" data-raw-source="[Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)"> MBAM 2.5 のグループとアカウントの計画」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-111">For more information, see <a href="planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles" data-raw-source="[Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)">Planning for MBAM 2.5 Groups and Accounts</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9a4ad-112">破損したドライブが含まれているコンピューターにパッケージファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-112">Copy the package file to the computer that contains the corrupted drive.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9a4ad-113">このコマンドを使用し <code>repair-bde</code> て回復プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-113">Use the <code>repair-bde</code> command to complete the recovery process.</span></span></p></td>
<td align="left"><p><span data-ttu-id="9a4ad-114">データが失われる可能性を回避するには、 <a href="https://go.microsoft.com/fwlink/?LinkId=393567" data-raw-source="[Manage-bde](https://go.microsoft.com/fwlink/?LinkId=393567)"> 使用前に manage-bde コマンドを確認することを強くお勧めし </a> ます。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-114">To avoid a potential loss of data, it is strongly recommended that you review the <a href="https://go.microsoft.com/fwlink/?LinkId=393567" data-raw-source="[Manage-bde](https://go.microsoft.com/fwlink/?LinkId=393567)">Manage-bde</a> command before using it.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="9a4ad-115">破損したドライブを回復するには</span><span class="sxs-lookup"><span data-stu-id="9a4ad-115">To recover a corrupted drive</span></span>**

1.  <span data-ttu-id="9a4ad-116">Web ブラウザーを開き、**管理と監視の Web サイト**に移動します。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-116">Open a web browser and navigate to the **Administration and Monitoring Website**.</span></span>

2.  <span data-ttu-id="9a4ad-117">左側のウィンドウで、[**ドライブの回復**] を選択して、[**暗号化されたドライブへのアクセスを回復**する] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-117">In the left pane, select **Drive Recovery** to open the **Recover access to an encrypted drive** page.</span></span>

3.  <span data-ttu-id="9a4ad-118">エンドユーザーの Windows ログオンドメインとユーザー名、ドライブのロックを解除する理由、およびエンドユーザーの回復パスワード ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-118">Enter the end user’s Windows log-on domain and user name, the reason for unlocking the drive, and the end user’s recovery password ID.</span></span>

    <span data-ttu-id="9a4ad-119">**注** 上級のヘルプデスクユーザーアクセスグループのメンバーである場合は、ユーザーのドメイン名またはユーザー名を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-119">**Note** If you are a member of the Advanced Helpdesk Users access group, you do not have to enter the user’s domain name or user name.</span></span>

     

4.  <span data-ttu-id="9a4ad-120">**[送信]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-120">Click **Submit**.</span></span> <span data-ttu-id="9a4ad-121">回復キーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-121">The recovery key will be displayed.</span></span>

5.  <span data-ttu-id="9a4ad-122">[**保存**] をクリックし、[**回復キーパッケージ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-122">Click **Save**, and then select **Recovery Key Package**.</span></span> <span data-ttu-id="9a4ad-123">回復キーパッケージはコンピューター上に作成されます。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-123">The recovery key package will be created on your computer.</span></span>

6.  <span data-ttu-id="9a4ad-124">破損したドライブがあるコンピューターに回復キーパッケージをコピーします。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-124">Copy the recovery key package to the computer that has the corrupted drive.</span></span>

7.  <span data-ttu-id="9a4ad-125">管理者特権でコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-125">Open an elevated command prompt.</span></span> <span data-ttu-id="9a4ad-126">この操作を行うには、[**スタート**] をクリックし `cmd` 、[**プログラムとファイルの検索**] テキストボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-126">To do this, click **Start** and type `cmd` in the **Search programs and files** text box.</span></span> <span data-ttu-id="9a4ad-127">[ **cmd.exe**] を右クリックし、[**管理者として実行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-127">Right-click **cmd.exe**, and select **Run as Administrator**.</span></span>

8.  <span data-ttu-id="9a4ad-128">コマンドプロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-128">At the command prompt, type the following:</span></span>

    `repair-bde <corrupted drive> <fixed drive> -kp <location of keypackage> -rp <recovery password>`

    <span data-ttu-id="9a4ad-129">**注** 破損した &lt; ドライブ上のデータと同サイズ以上の空き領域がある、使用可能なハードディスクドライブに*固定ドライブ*を置き &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-129">**Note** Replace &lt;*fixed drive*&gt; with an available hard disk drive that has free space equal to or larger than the data on the corrupted drive.</span></span> <span data-ttu-id="9a4ad-130">破損したドライブ上のデータが回復され、指定されたハードディスクドライブに移動されます。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-130">Data on the corrupted drive is recovered and moved to the specified hard disk drive.</span></span>

     


## <span data-ttu-id="9a4ad-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9a4ad-131">Related topics</span></span>


[<span data-ttu-id="9a4ad-132">MBAM 2.5 での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="9a4ad-132">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)

 
## <span data-ttu-id="9a4ad-133">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-133">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="9a4ad-134">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-134">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="9a4ad-135">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="9a4ad-135">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





