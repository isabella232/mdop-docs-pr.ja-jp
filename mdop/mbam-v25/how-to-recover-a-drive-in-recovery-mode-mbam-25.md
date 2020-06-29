---
title: 回復モードでドライブを回復する方法
description: 回復モードでドライブを回復する方法
author: dansimp
ms.assetid: e126eaf8-9ae7-40fe-a28e-dbd78d26859e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d15f33f461e60fceeed3acbce3a0c82b02b56f98
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823367"
---
# <span data-ttu-id="c9511-103">回復モードでドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="c9511-103">How to Recover a Drive in Recovery Mode</span></span>


<span data-ttu-id="c9511-104">このトピックでは、管理と監視の Web サイト (ヘルプデスクとも呼ばれます) を使用して、BitLocker で保護されたドライブが回復モードになった場合にエンドユーザーに提供する回復パスワードを取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c9511-104">This topic explains how to use the Administration and Monitoring Website (also referred to as the Help Desk) to get a recovery password to give to end users if their BitLocker-protected drive goes into recovery mode.</span></span> <span data-ttu-id="c9511-105">ユーザーが PIN またはパスワードを紛失または忘れた場合や、信頼済みモジュールプラットフォーム (TPM) チップによってコンピューターの BIOS またはスタートアップファイルの変更が検出された場合、ドライブは回復モードになります。</span><span class="sxs-lookup"><span data-stu-id="c9511-105">Drives go into recovery mode if users lose or forget their PIN or password or if the Trusted Module Platform (TPM) chip detects changes to the BIOS or startup files of a computer.</span></span>

<span data-ttu-id="c9511-106">回復パスワードを取得するには、管理と監視の Web サイトの [**ドライブの回復**] 領域を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9511-106">To get a recovery password, use the **Drive Recovery** area of the Administration and Monitoring Website.</span></span> <span data-ttu-id="c9511-107">この web サイトの領域にアクセスするには、MBAM ヘルプデスクユーザーロールまたは MBAM Advanced ヘルプデスクユーザーの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9511-107">You must be assigned the MBAM Helpdesk Users role or the MBAM Advanced Helpdesk Users role to access this area of the website.</span></span>

**<span data-ttu-id="c9511-108">注</span><span class="sxs-lookup"><span data-stu-id="c9511-108">Note</span></span>**  
<span data-ttu-id="c9511-109">これらの役割は、作成時に異なる名前を指定した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c9511-109">You may have given these roles different names when you created them.</span></span> <span data-ttu-id="c9511-110">詳細については、「 [MBAM 2.5 のグループとアカウントの計画](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9511-110">For more information, see [Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles).</span></span>



**<span data-ttu-id="c9511-111">重要</span><span class="sxs-lookup"><span data-stu-id="c9511-111">Important</span></span>**  
<span data-ttu-id="c9511-112">回復パスワードは1回の使用後に有効期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="c9511-112">Recovery passwords expire after a single use.</span></span> <span data-ttu-id="c9511-113">オペレーティングシステムドライブと固定データドライブでは、単一使用ルールが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c9511-113">On operating system drives and fixed data drives, the single-use rule is applied automatically.</span></span> <span data-ttu-id="c9511-114">リムーバブルドライブの場合は、ドライブが取り外され、グループポリシー設定がアクティブになっているコンピューターで、リムーバブルドライブを管理するために、ドライブが適用されます。</span><span class="sxs-lookup"><span data-stu-id="c9511-114">On removable drives, it is applied when the drive is removed and then reinserted and unlocked on a computer that has Group Policy settings activated to manage removable drives.</span></span>



**<span data-ttu-id="c9511-115">回復モードでドライブを回復するには</span><span class="sxs-lookup"><span data-stu-id="c9511-115">To recover a drive in recovery mode</span></span>**

1.  <span data-ttu-id="c9511-116">Web ブラウザーを開き、**管理と監視の Web サイト**に移動します。</span><span class="sxs-lookup"><span data-stu-id="c9511-116">Open a web browser and navigate to the **Administration and Monitoring Website**.</span></span>

2.  <span data-ttu-id="c9511-117">左側のウィンドウで、[**ドライブの回復**] を選択して、[**暗号化されたドライブへのアクセスを回復**する] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="c9511-117">In the left pane, select **Drive Recovery** to open the **Recover access to an encrypted drive** page.</span></span>

3.  <span data-ttu-id="c9511-118">回復情報を表示するには、エンドユーザーの Windows ログオンドメインとユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="c9511-118">Enter the end user’s Windows log-on domain and user name to view recovery information.</span></span>

    **<span data-ttu-id="c9511-119">注</span><span class="sxs-lookup"><span data-stu-id="c9511-119">Note</span></span>**  
    <span data-ttu-id="c9511-120">MBAM Advanced のヘルプデスクユーザーグループの場合、[ユーザードメイン] と [ユーザー ID] フィールドは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="c9511-120">If you are in the MBAM Advanced Helpdesk Users group, the user domain and user ID fields are not required.</span></span>



4.  <span data-ttu-id="c9511-121">回復キー ID の最初の8桁を入力して、一致する可能性のある回復キーの一覧を表示するか、完全な回復キーを取得するために回復キー ID 全体を入力します。</span><span class="sxs-lookup"><span data-stu-id="c9511-121">Enter the first eight digits of the recovery key ID to see a list of possible matching recovery keys, or enter the entire recovery key ID to get the exact recovery key.</span></span>

5.  <span data-ttu-id="c9511-122">[**ドライブのロック解除の理由**] ボックスの一覧で、定義済みのオプションのいずれかを選び、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9511-122">From the **Reason for Drive Unlock** list, select one of the predefined options, and then click **Submit**.</span></span>

    <span data-ttu-id="c9511-123">MBAM は、次の値を返します。</span><span class="sxs-lookup"><span data-stu-id="c9511-123">MBAM returns the following:</span></span>

    -   <span data-ttu-id="c9511-124">一致する回復パスワードが見つからなかった場合のエラーメッセージ</span><span class="sxs-lookup"><span data-stu-id="c9511-124">An error message if no matching recovery password is found</span></span>

    -   <span data-ttu-id="c9511-125">ユーザーが複数の一致する回復パスワードを持っている場合、一致する可能性がある複数の一致</span><span class="sxs-lookup"><span data-stu-id="c9511-125">Multiple possible matches if the user has multiple matching recovery passwords</span></span>

    -   <span data-ttu-id="c9511-126">送信されたユーザーの回復パスワードと回復パッケージ</span><span class="sxs-lookup"><span data-stu-id="c9511-126">The recovery password and recovery package for the submitted user</span></span>

        **<span data-ttu-id="c9511-127">注</span><span class="sxs-lookup"><span data-stu-id="c9511-127">Note</span></span>**  
        <span data-ttu-id="c9511-128">破損したドライブを回復する場合、[回復パッケージ] オプションでは、ドライブを復元するために必要な重要な情報を BitLocker に提供します。</span><span class="sxs-lookup"><span data-stu-id="c9511-128">If you are recovering a damaged drive, the recovery package option provides BitLocker with critical information that it needs to recover the drive.</span></span>



~~~
After the recovery password and recovery package are retrieved, the recovery password is displayed.
~~~

6. <span data-ttu-id="c9511-129">パスワードをコピーするには、[**キーのコピー**] をクリックし、メールメッセージに回復パスワードを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c9511-129">To copy the password, click **Copy Key**, and then paste the recovery password into an email message.</span></span> <span data-ttu-id="c9511-130">または、[**保存**] をクリックして回復パスワードをファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="c9511-130">Alternatively, click **Save** to save the recovery password to a file.</span></span>

   <span data-ttu-id="c9511-131">ユーザーが回復パスワードをシステムに入力するか、回復パッケージを使用すると、ドライブのロックが解除されます。</span><span class="sxs-lookup"><span data-stu-id="c9511-131">When the user types the recovery password into the system or uses the recovery package, the drive is unlocked.</span></span>



## <span data-ttu-id="c9511-132">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c9511-132">Related topics</span></span>


[<span data-ttu-id="c9511-133">MBAM 2.5 での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="c9511-133">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)



## <span data-ttu-id="c9511-134">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="c9511-134">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="c9511-135">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="c9511-135">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="c9511-136">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="c9511-136">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





