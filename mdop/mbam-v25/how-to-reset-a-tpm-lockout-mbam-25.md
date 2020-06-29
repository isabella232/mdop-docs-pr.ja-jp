---
title: TPM ロックアウトをリセットする方法
description: TPM ロックアウトをリセットする方法
author: dansimp
ms.assetid: dd20a728-c52e-48e6-9f6c-1311c71dee74
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f5aea277e80c54fb01d1a6c00b62f0c617d1ad12
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823324"
---
# <span data-ttu-id="6dff7-103">TPM ロックアウトをリセットする方法</span><span class="sxs-lookup"><span data-stu-id="6dff7-103">How to Reset a TPM Lockout</span></span>


<span data-ttu-id="6dff7-104">このトピックでは、管理と監視の Web サイト (ヘルプデスクとも呼ばれます) を使って TPM ロックアウトをリセットする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6dff7-104">This topic explains how to use the Administration and Monitoring Website (also referred to as the Help Desk) to reset a TPM lockout.</span></span> <span data-ttu-id="6dff7-105">エンドユーザーが誤った PIN を入力した回数が多すぎると、TPM ロックアウトが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6dff7-105">TPM lockouts can occur if an end user enters the incorrect PIN too many times.</span></span> <span data-ttu-id="6dff7-106">TPM のロックが発生する前に、ユーザーが不正な PIN を入力できる回数は、製造元によって異なります。</span><span class="sxs-lookup"><span data-stu-id="6dff7-106">The number of times that a user can enter an incorrect PIN before the TPM locks varies from manufacturer to manufacturer.</span></span>

<span data-ttu-id="6dff7-107">管理と監視の Web サイトの [ **tpm の管理**] 領域から、コンピューター ID と関連付けられたユーザー識別子を提供するときに tpm 所有者のパスワードファイルを提供する、一元管理されたキーの回復データシステムにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6dff7-107">From the **Manage TPM** area of the Administration and Monitoring Website, you can access the centralized Key Recovery data system, which provides a TPM owner password file when you supply a computer ID and associated user identifier.</span></span>

<span data-ttu-id="6dff7-108">管理と監視の Web サイトの [TPM の管理] 領域にアクセスするには、MBAM ヘルプデスクユーザーロールまたは MBAM Advanced のヘルプデスクユーザーの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6dff7-108">To access the Manage TPM area of the Administration and Monitoring Website, you must be assigned the MBAM Helpdesk Users role or the MBAM Advanced Helpdesk Users role.</span></span> <span data-ttu-id="6dff7-109">これらの役割は、管理者が Active Directory で作成するグループです。</span><span class="sxs-lookup"><span data-stu-id="6dff7-109">These roles are groups that administrators create in Active Directory.</span></span> <span data-ttu-id="6dff7-110">これらのグループには任意の名前を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6dff7-110">You can use any name for these groups.</span></span> <span data-ttu-id="6dff7-111">詳細については、「 [MBAM 2.5 のグループとアカウントの計画](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6dff7-111">For more information, see [Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles).</span></span>

<span data-ttu-id="6dff7-112">MBAM と TPM の所有権の詳細については、「 [mbam 2.5 セキュリティに関する考慮事項](mbam-25-security-considerations.md#bkmk-tpm)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6dff7-112">For information about MBAM and TPM ownership, see [MBAM 2.5 Security Considerations](mbam-25-security-considerations.md#bkmk-tpm).</span></span>

**<span data-ttu-id="6dff7-113">TPM ロックアウトをリセットするには</span><span class="sxs-lookup"><span data-stu-id="6dff7-113">To reset a TPM lockout</span></span>**

1.  <span data-ttu-id="6dff7-114">Web ブラウザーを開き、**管理と監視の Web サイト**に移動します。</span><span class="sxs-lookup"><span data-stu-id="6dff7-114">Open a web browser and navigate to the **Administration and Monitoring Website**.</span></span>

2.  <span data-ttu-id="6dff7-115">左側のウィンドウで、[ **tpm の管理**] をクリックし、[ **tpm の管理**] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="6dff7-115">In the left pane, click **Manage TPM** to open the **Manage TPM** page.</span></span>

3.  <span data-ttu-id="6dff7-116">コンピューターの完全修飾ドメイン名とコンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="6dff7-116">Enter the fully qualified domain name for the computer and the computer name.</span></span>

4.  <span data-ttu-id="6dff7-117">エンドユーザーの Windows ログオンドメインとユーザー名を入力して、TPM 所有者パスワードファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="6dff7-117">Enter the end user’s Windows log-on domain and user name to retrieve the TPM owner password file.</span></span>

    <span data-ttu-id="6dff7-118">**注** MBAM Advanced のヘルプデスクユーザーグループの場合、[ユーザードメイン] と [ユーザー ID] フィールドは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="6dff7-118">**Note** If you are in the MBAM Advanced Helpdesk Users group, the user domain and user ID fields are not required.</span></span>

     

5.  <span data-ttu-id="6dff7-119">[ **TPM 所有者パスワードファイルの要求の理由**] ボックスの一覧で、要求の理由を選択し、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dff7-119">From the **Reason for requesting TPM owner password file** list, select a reason for the request, and click **Submit**.</span></span>

    <span data-ttu-id="6dff7-120">MBAM は、次のいずれかの値を返します。</span><span class="sxs-lookup"><span data-stu-id="6dff7-120">MBAM returns one of the following:</span></span>

    -   <span data-ttu-id="6dff7-121">一致する TPM 所有者パスワードファイルが見つからなかった場合のエラーメッセージ</span><span class="sxs-lookup"><span data-stu-id="6dff7-121">An error message if no matching TPM owner password file is found</span></span>

    -   <span data-ttu-id="6dff7-122">送信されたコンピューターの TPM 所有者パスワードファイル</span><span class="sxs-lookup"><span data-stu-id="6dff7-122">The TPM owner password file for the submitted computer</span></span>

    <span data-ttu-id="6dff7-123">TPM 所有者パスワードを取得した後、所有者パスワードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6dff7-123">After the TPM owner password is retrieved, the owner password is displayed.</span></span>

6.  <span data-ttu-id="6dff7-124">パスワードを tpm ファイルに保存するには、[**保存**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6dff7-124">To save the password to a .tpm file, click the **Save** button.</span></span>

7.  <span data-ttu-id="6dff7-125">**管理と監視の Web サイト**の [ **tpm の管理**] 領域で、[ **tpm ロックアウトのリセット**] オプションを選択し、tpm 所有者パスワードファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="6dff7-125">In the **Manage TPM** area of the **Administration and Monitoring Website**, select the **Reset TPM lockout** option and provide the TPM owner password file.</span></span>

    <span data-ttu-id="6dff7-126">TPM ロックアウトがリセットされ、エンドユーザーのアクセスが復元されます。</span><span class="sxs-lookup"><span data-stu-id="6dff7-126">The TPM lockout is reset and the end user’s access is restored.</span></span>

    <span data-ttu-id="6dff7-127">**重要** TPM ハッシュ値または TPM 所有者パスワードファイルにエンドユーザーを指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="6dff7-127">**Important** Do not give the TPM hash value or TPM owner password file to end users.</span></span> <span data-ttu-id="6dff7-128">TPM 情報は変更されないため、ファイルをエンドユーザーに提供すると、セキュリティ上のリスクが生じます。</span><span class="sxs-lookup"><span data-stu-id="6dff7-128">Because the TPM information does not change, giving the file to end users creates a security risk.</span></span>

     



## <span data-ttu-id="6dff7-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6dff7-129">Related topics</span></span>


[<span data-ttu-id="6dff7-130">MBAM 2.5 での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="6dff7-130">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)

 

## <span data-ttu-id="6dff7-131">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="6dff7-131">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="6dff7-132">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="6dff7-132">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="6dff7-133">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="6dff7-133">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





