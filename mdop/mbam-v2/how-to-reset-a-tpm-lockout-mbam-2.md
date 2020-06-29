---
title: TPM ロックアウトをリセットする方法
description: TPM ロックアウトをリセットする方法
author: dansimp
ms.assetid: 20719ab2-18ae-4d3b-989a-539341909816
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6453473ec09c2033346c7e464c08dbfdfe046d47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825054"
---
# <span data-ttu-id="9d628-103">TPM ロックアウトをリセットする方法</span><span class="sxs-lookup"><span data-stu-id="9d628-103">How to Reset a TPM Lockout</span></span>


<span data-ttu-id="9d628-104">Microsoft BitLocker の管理と監視 (MBAM) の暗号化されたドライブの回復機能には、データのキャプチャとストレージ、およびトラステッドプラットフォームモジュール (TPM) を管理するために必要なツールの可用性が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9d628-104">The Encrypted Drive Recovery feature of Microsoft BitLocker Administration and Monitoring (MBAM) encompasses both the capture and storage of data and the availability for tools that are needed to manage the Trusted Platform Module (TPM).</span></span> <span data-ttu-id="9d628-105">このトピックでは、管理と監視の web サイトで中央キー回復データシステムにアクセスする方法について説明します。これにより、コンピューター ID と関連付けられているユーザー識別子が指定されたときに TPM 所有者パスワードファイルを提供できます。</span><span class="sxs-lookup"><span data-stu-id="9d628-105">This topic covers how to access the centralized Key Recovery data system in the Administration and Monitoring website, which can provide a TPM owner password file when a computer ID and associated user identifier are supplied.</span></span>

<span data-ttu-id="9d628-106">TPM ロックアウトは、ユーザーが誤った PIN を入力した回数が何度も超えた場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9d628-106">A TPM lockout can occur if a user enters the incorrect PIN too many times.</span></span> <span data-ttu-id="9d628-107">TPM のロックが発生する前に、ユーザーが不正な PIN を入力できる回数は、製造元によって異なります。</span><span class="sxs-lookup"><span data-stu-id="9d628-107">The number of times that a user can enter an incorrect PIN before the TPM locks varies from manufacturer to manufacturer.</span></span>

<span data-ttu-id="9d628-108">MBAM が TPM を所有している場合にのみ、TPM ロックアウトをリセットできます。</span><span class="sxs-lookup"><span data-stu-id="9d628-108">You can reset a TPM lockout only if MBAM owns the TPM.</span></span>

**<span data-ttu-id="9d628-109">TPM ロックアウトをリセットするには</span><span class="sxs-lookup"><span data-stu-id="9d628-109">To reset a TPM lockout</span></span>**

1.  <span data-ttu-id="9d628-110">Web ブラウザーを開き、管理と監視の web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="9d628-110">Open a web browser and navigate to the Administration and Monitoring website.</span></span>

2.  <span data-ttu-id="9d628-111">左側のナビゲーションウィンドウで、[ **tpm の管理**] を選択し、[ **tpm の管理**] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="9d628-111">In the left navigation pane, select **Manage TPM** to open the **Manage TPM** page.</span></span>

3.  <span data-ttu-id="9d628-112">コンピューターとコンピューター名の完全修飾ドメイン名を入力し、ユーザーの Windows ログオンドメインとユーザーのユーザー名を入力して、TPM 所有者パスワードファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="9d628-112">Enter the fully qualified domain name for the computer and the computer name, and enter the user’s Windows logon domain and the user’s user name to retrieve the TPM owner password file.</span></span>

4.  <span data-ttu-id="9d628-113">[ **TPM 所有者パスワードファイルの要求の理由**] ボックスの一覧で、要求の理由を選択し、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d628-113">From the **Reason for requesting TPM owner password file** list, select a reason for the request, and click **Submit**.</span></span>

    <span data-ttu-id="9d628-114">MBAM は、次のいずれかの値を返します。</span><span class="sxs-lookup"><span data-stu-id="9d628-114">MBAM returns one of the following:</span></span>

    -   <span data-ttu-id="9d628-115">一致する TPM 所有者パスワードファイルが見つからなかった場合のエラーメッセージ</span><span class="sxs-lookup"><span data-stu-id="9d628-115">An error message, if no matching TPM owner password file is found</span></span>

    -   <span data-ttu-id="9d628-116">送信されたコンピューターの TPM 所有者パスワードファイル</span><span class="sxs-lookup"><span data-stu-id="9d628-116">The TPM owner password file for the submitted computer</span></span>

    **<span data-ttu-id="9d628-117">注</span><span class="sxs-lookup"><span data-stu-id="9d628-117">Note</span></span>**  
    <span data-ttu-id="9d628-118">上級のヘルプデスクユーザーの場合、[ユーザードメイン] と [ユーザー ID] フィールドは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="9d628-118">If you are an Advanced Helpdesk user, the user domain and user ID fields are not required.</span></span>



~~~
After the TPM owner password is retrieved, the owner password is displayed.
~~~

5. <span data-ttu-id="9d628-119">パスワードを tpm ファイルに保存するには、[**保存**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d628-119">To save the password to a .tpm file, click the **Save** button.</span></span>

   <span data-ttu-id="9d628-120">ユーザーは TPM 管理コンソールを実行し、[ **tpm ロックアウトのリセット**] オプションを選択し、tpm のロックアウトをリセットする tpm 所有者パスワードファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d628-120">The user will run the TPM management console, select the **Reset TPM lockout** option, and provide the TPM owner password file to reset the TPM lockout.</span></span>

   **<span data-ttu-id="9d628-121">重要</span><span class="sxs-lookup"><span data-stu-id="9d628-121">Important</span></span>**  
   <span data-ttu-id="9d628-122">ヘルプデスク管理者は、TPM ハッシュ値または TPM 所有者パスワードファイルをエンドユーザーに提供しないようにします。</span><span class="sxs-lookup"><span data-stu-id="9d628-122">Help Desk administrators should not give the TPM hash value or TPM owner password file to end users.</span></span> <span data-ttu-id="9d628-123">TPM 情報は変更されないため、ファイルがエンドユーザーに提供されている場合は、セキュリティ上のリスクを招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9d628-123">The TPM information does not change, so it could pose a security risk if the file is given to end users.</span></span>



## <span data-ttu-id="9d628-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9d628-124">Related topics</span></span>


[<span data-ttu-id="9d628-125">MBAM での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="9d628-125">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam-mbam-2.md)









