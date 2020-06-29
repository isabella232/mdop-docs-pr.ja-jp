---
title: 回復モードでドライブを回復する方法
description: 回復モードでドライブを回復する方法
author: dansimp
ms.assetid: 09d27e4b-57fa-47c7-a004-8b876a49f27e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c1151ffe7453eb8d07d2aa6dcb4c41f6b3efe6de
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812954"
---
# <span data-ttu-id="ddb45-103">回復モードでドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="ddb45-103">How to Recover a Drive in Recovery Mode</span></span>


<span data-ttu-id="ddb45-104">Microsoft BitLocker の管理と監視 (MBAM) には、暗号化されたドライブの回復機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ddb45-104">Microsoft BitLocker Administration and Monitoring (MBAM) includes Encrypted Drive Recovery features.</span></span> <span data-ttu-id="ddb45-105">これらの機能により、BitLocker によってそのボリュームが回復モードになったときに、BitLocker で保護されたボリュームへのアクセスに必要なツールのキャプチャと保存が可能になります。</span><span class="sxs-lookup"><span data-stu-id="ddb45-105">These features ensure the capture and storage of data and availability of tools that are required to access a BitLocker-protected volume when BitLocker puts that volume into recovery mode.</span></span> <span data-ttu-id="ddb45-106">BitLocker で保護されたボリュームは、PIN またはパスワードを紛失または忘れた場合、または信頼されているモジュールプラットフォーム (TPM) チップがコンピューターの BIOS またはスタートアップファイルへの変更を検出した場合に回復モードになります。</span><span class="sxs-lookup"><span data-stu-id="ddb45-106">A BitLocker-protected volume goes into recovery mode when a PIN or password is lost or forgotten, or when the Trusted Module Platform (TPM) chip detects a change to the computer's BIOS or startup files.</span></span>

<span data-ttu-id="ddb45-107">回復パスワード ID と関連付けられたユーザー識別子が指定されているときに回復パスワードを提供できる中央キー回復データシステムにアクセスするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="ddb45-107">Use this procedure to access the centralized Key Recovery data system that can provide a recovery password when a recovery password ID and associated user identifier are supplied.</span></span>

<span data-ttu-id="ddb45-108">**重要** MBAM は、単一使用の回復キーを生成します。</span><span class="sxs-lookup"><span data-stu-id="ddb45-108">**Important** MBAM generates single-use recovery keys.</span></span> <span data-ttu-id="ddb45-109">この制限の下では、回復キーは1回だけ使用でき、その後は無効になります。</span><span class="sxs-lookup"><span data-stu-id="ddb45-109">Under this limitation, a recovery key can be used only once and then it is no longer valid.</span></span> <span data-ttu-id="ddb45-110">回復パスワードの1回の使用は、オペレーティングシステムドライブと固定ドライブに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ddb45-110">The single use of a recovery password is automatically applied to operating system drives and fixed drives.</span></span> <span data-ttu-id="ddb45-111">リムーバブルドライブでは、ドライブが取り外されたときに単一の使用が適用され、グループポリシーの設定がアクティブになっているコンピューターで、リムーバブルドライブを管理します。</span><span class="sxs-lookup"><span data-stu-id="ddb45-111">On removable drives, the single use is applied when the drive is removed and then re-inserted and unlocked on a computer that has the group policy settings activated to manage removable drives.</span></span>

 

**<span data-ttu-id="ddb45-112">回復モードでドライブを回復するには</span><span class="sxs-lookup"><span data-stu-id="ddb45-112">To recover a drive in Recovery Mode</span></span>**

1.  <span data-ttu-id="ddb45-113">MBAM web サイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="ddb45-113">Open the MBAM website.</span></span>

2.  <span data-ttu-id="ddb45-114">ナビゲーションウィンドウで、[**ドライブの回復**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb45-114">In the navigation pane, click **Drive Recovery**.</span></span> <span data-ttu-id="ddb45-115">[**暗号化されたドライブへのアクセスを回復する**web ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="ddb45-115">The **Recover access to an encrypted drive** webpage opens.</span></span>

3.  <span data-ttu-id="ddb45-116">ユーザーの Windows ログオンドメインとユーザー名、および回復キー ID の最初の8桁を入力して、一致する回復キーの候補の一覧を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ddb45-116">Enter the user's Windows Logon domain and user name and the first eight digits of the recovery key ID, to receive a list of possible matching recovery keys.</span></span> <span data-ttu-id="ddb45-117">または、完全な回復キーを受け取るには、回復キーの ID 全体を入力します。</span><span class="sxs-lookup"><span data-stu-id="ddb45-117">Alternatively, enter the entire recovery key ID to receive the exact recovery key.</span></span> <span data-ttu-id="ddb45-118">[**ドライブロック解除の理由**] ドロップダウンリストから定義済みのオプションのいずれかを選択し、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb45-118">Select one of the predefined options in the **Reason for Drive Unlock** drop-down list, and then click **Submit**.</span></span>

    <span data-ttu-id="ddb45-119">**注** MBAM Advanced ヘルプデスクユーザーの場合、ユーザードメインとユーザー ID のエントリは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ddb45-119">**Note** If you are an MBAM Advanced Helpdesk User, the user domain and user ID entries are not required.</span></span>

     

4.  <span data-ttu-id="ddb45-120">MBAM は、次の値を返します。</span><span class="sxs-lookup"><span data-stu-id="ddb45-120">MBAM returns the following:</span></span>

    1.  <span data-ttu-id="ddb45-121">一致する回復パスワードが見つからなかった場合のエラーメッセージ</span><span class="sxs-lookup"><span data-stu-id="ddb45-121">An error message if no matching recovery password is found</span></span>

    2.  <span data-ttu-id="ddb45-122">ユーザーが複数の一致する回復パスワードを持っている場合、一致する可能性がある複数の一致</span><span class="sxs-lookup"><span data-stu-id="ddb45-122">Multiple possible matches if the user has multiple matching recovery passwords</span></span>

    3.  <span data-ttu-id="ddb45-123">送信されたユーザーの回復パスワードと回復パッケージ</span><span class="sxs-lookup"><span data-stu-id="ddb45-123">The recovery password and recovery package for the submitted user</span></span>

        <span data-ttu-id="ddb45-124">**注** 破損したドライブを回復する場合、回復パッケージオプションは、回復を試みるために必要な重要な情報を BitLocker に提供します。</span><span class="sxs-lookup"><span data-stu-id="ddb45-124">**Note** If you are recovering a damaged drive, the recovery package option provides BitLocker with the critical information necessary to attempt the recovery.</span></span>

         

5.  <span data-ttu-id="ddb45-125">回復パスワードと回復パッケージを取得した後、回復パスワードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ddb45-125">After the recovery password and recovery package are retrieved, the recovery password is displayed.</span></span> <span data-ttu-id="ddb45-126">パスワードをコピーするには、[**キーのコピー**] をクリックして、回復パスワードをメールまたはその他の一時記憶域のテキストファイルに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="ddb45-126">To copy the password, click **Copy Key**, and then paste the recovery password into an email or other text file for temporary storage.</span></span> <span data-ttu-id="ddb45-127">または、回復パスワードをファイルに保存するには、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb45-127">Or, to save the recovery password to a file, click **Save**.</span></span>

6.  <span data-ttu-id="ddb45-128">ユーザーが回復パスワードをシステムに入力するか、回復パッケージを使用すると、ドライブのロックが解除されます。</span><span class="sxs-lookup"><span data-stu-id="ddb45-128">When the user types the recovery password into the system or uses the recovery package, the drive is unlocked.</span></span>

## <span data-ttu-id="ddb45-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ddb45-129">Related topics</span></span>


[<span data-ttu-id="ddb45-130">MBAM での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="ddb45-130">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam.md)

 

 





