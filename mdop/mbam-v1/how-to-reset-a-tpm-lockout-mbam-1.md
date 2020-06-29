---
title: TPM ロックアウトをリセットする方法
description: TPM ロックアウトをリセットする方法
author: dansimp
ms.assetid: 91ec6666-1ae2-4e76-9459-ad65c405f639
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dde77a12e97d050777dac15d4106124ec111b3cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812922"
---
# <span data-ttu-id="fccd3-103">TPM ロックアウトをリセットする方法</span><span class="sxs-lookup"><span data-stu-id="fccd3-103">How to Reset a TPM Lockout</span></span>


<span data-ttu-id="fccd3-104">Microsoft BitLocker の管理と監視 (MBAM) の暗号化されたドライブの回復機能には、データのキャプチャとストレージ、およびトラステッドプラットフォームモジュール (TPM) を管理するために必要なツールの可用性が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fccd3-104">The Encrypted Drive Recovery feature of Microsoft BitLocker Administration and Monitoring (MBAM) encompasses both the capture and storage of data and the availability for tools that are required to manage the Trusted Platform Module (TPM).</span></span> <span data-ttu-id="fccd3-105">このトピックでは、ビット \ _admmon \ _tlanextref 管理 web サイトで中央キー回復データシステムにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fccd3-105">This topic covers how to access the centralized Key Recovery data system in the bit\_admmon\_tlanextref administration website.</span></span> <span data-ttu-id="fccd3-106">キー回復データシステムでは、コンピューターの id と関連付けられているユーザー識別子が指定されている場合、TPM 所有者パスワードファイルを提供できます。</span><span class="sxs-lookup"><span data-stu-id="fccd3-106">The Key Recovery data system can provide a TPM owner password file when the computer identity and the associated user identifier are supplied.</span></span>

<span data-ttu-id="fccd3-107">TPM ロックアウトは、ユーザーが誤った PIN を何度も入力した場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fccd3-107">A TPM lockout can occur if a user enters an incorrect PIN too many times.</span></span> <span data-ttu-id="fccd3-108">TPM ロックアウトの前に、ユーザーが間違った PIN を入力できる回数は、コンピューターの製造元の仕様に基づいています。</span><span class="sxs-lookup"><span data-stu-id="fccd3-108">The number of times that a user can enter an incorrect PIN before the TPM lockout is based on the computer manufacturer's specification.</span></span>

**<span data-ttu-id="fccd3-109">TPM ロックアウトをリセットするには</span><span class="sxs-lookup"><span data-stu-id="fccd3-109">To reset a TPM lockout</span></span>**

1.  <span data-ttu-id="fccd3-110">MBAM 管理 web サイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="fccd3-110">Open the MBAM administration website.</span></span>

2.  <span data-ttu-id="fccd3-111">ナビゲーションウィンドウで、[ **TPM の管理**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fccd3-111">In the navigation pane, select **Manage TPM**.</span></span> <span data-ttu-id="fccd3-112">[TPM の**管理**] ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="fccd3-112">This opens the **Manage TPM** page.</span></span>

3.  <span data-ttu-id="fccd3-113">コンピューターとコンピューター名の完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="fccd3-113">Enter the fully qualified domain name (FQDN) for the computer and the computer name.</span></span> <span data-ttu-id="fccd3-114">ユーザーの Windows ログオンドメインとユーザーのユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="fccd3-114">Enter the user’s Windows Logon domain and the user’s user name.</span></span> <span data-ttu-id="fccd3-115">[ **TPM 所有者パスワードファイルの要求の理由**] ドロップダウンメニューで、定義済みのオプションのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="fccd3-115">Select one of the predefined options in the **Reason for requesting TPM owner password file** drop-down menu.</span></span> <span data-ttu-id="fccd3-116">**[送信]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fccd3-116">Click **Submit**.</span></span>

4.  <span data-ttu-id="fccd3-117">MBAM は、次のいずれかを返します。</span><span class="sxs-lookup"><span data-stu-id="fccd3-117">MBAM will return one of the following:</span></span>

    -   <span data-ttu-id="fccd3-118">一致する TPM 所有者パスワードファイルが見つからなかった場合のエラーメッセージ</span><span class="sxs-lookup"><span data-stu-id="fccd3-118">An error message if no matching TPM owner password file is found</span></span>

    -   <span data-ttu-id="fccd3-119">送信されたコンピューターの TPM 所有者パスワードファイル</span><span class="sxs-lookup"><span data-stu-id="fccd3-119">The TPM owner password file for the submitted computer</span></span>

    <span data-ttu-id="fccd3-120">**注** 上級のヘルプデスクユーザーの場合、[ユーザードメイン] と [ユーザー ID] フィールドは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="fccd3-120">**Note** If you are an Advanced Helpdesk User, the user domain and user ID fields are not required.</span></span>

     

5.  <span data-ttu-id="fccd3-121">取得すると、所有者パスワードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fccd3-121">Upon retrieval, the owner password is displayed.</span></span> <span data-ttu-id="fccd3-122">このパスワードを tpm ファイルに保存するには、[**保存**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fccd3-122">To save this password to a .tpm file, click the **Save** button.</span></span>

6.  <span data-ttu-id="fccd3-123">ユーザーは、TPM 管理コンソールを実行し、[ **tpm ロックアウトのリセット**] オプションを選択し、tpm のロックアウトをリセットする tpm 所有者パスワードファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="fccd3-123">The user will run the TPM management console and select the **Reset TPM lockout** option and provide the TPM owner password file to reset the TPM lockout.</span></span>

## <span data-ttu-id="fccd3-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fccd3-124">Related topics</span></span>


[<span data-ttu-id="fccd3-125">MBAM での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="fccd3-125">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam.md)

 

 





