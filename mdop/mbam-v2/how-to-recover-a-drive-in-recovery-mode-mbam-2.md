---
title: 回復モードでドライブを回復する方法
description: 回復モードでドライブを回復する方法
author: dansimp
ms.assetid: 8b792bc8-b671-4345-9d37-0208db3e5b03
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7d5ce509599d0eb800a71360e3be9d0fa3b33f4f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825057"
---
# <span data-ttu-id="34b8e-103">回復モードでドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="34b8e-103">How to Recover a Drive in Recovery Mode</span></span>


<span data-ttu-id="34b8e-104">Microsoft BitLocker の管理と監視 (MBAM) の暗号化されたドライブ回復機能を使用すると、BitLocker で保護されたボリュームにアクセスするために必要なデータと可用性をキャプチャして保存することができます。 BitLocker は回復モードになります。</span><span class="sxs-lookup"><span data-stu-id="34b8e-104">The encrypted drive recovery features of Microsoft BitLocker Administration and Monitoring (MBAM) ensure the capture and storage of data and availability of tools required to access a BitLocker-protected volume when BitLocker goes into recovery mode.</span></span> <span data-ttu-id="34b8e-105">BitLocker で保護されたボリュームは、PIN またはパスワードを紛失または忘れた場合、またはコンピューターの BIOS または起動ファイルの変更を信頼されたモジュールプラットフォーム (TPM) チップが検出した場合に、回復モードになります。</span><span class="sxs-lookup"><span data-stu-id="34b8e-105">A BitLocker-protected volume goes into recovery mode when a PIN or password is lost or forgotten, or when the Trusted Module Platform (TPM) chip detects changes to the BIOS or startup files of a computer.</span></span>

<span data-ttu-id="34b8e-106">この手順を使用して一元的なキー回復データシステムにアクセスします。これにより、回復パスワード ID と関連付けられたユーザー識別子が指定されている場合に回復パスワードを提供できます。</span><span class="sxs-lookup"><span data-stu-id="34b8e-106">Use this procedure to access the centralized key recovery data system, which can provide a recovery password if a recovery password ID and associated user identifier are supplied.</span></span>

**<span data-ttu-id="34b8e-107">重要</span><span class="sxs-lookup"><span data-stu-id="34b8e-107">Important</span></span>**  
<span data-ttu-id="34b8e-108">Microsoft BitLocker の管理と監視では、使用時に期限切れになる単一使用の回復キーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="34b8e-108">Microsoft BitLocker Administration and Monitoring uses single-use recovery keys that expire upon use.</span></span> <span data-ttu-id="34b8e-109">回復パスワードの1回の使用は、オペレーティングシステムドライブと固定ドライブに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="34b8e-109">The single use of a recovery password is automatically applied to operating system drives and fixed drives.</span></span> <span data-ttu-id="34b8e-110">リムーバブルドライブの場合は、ドライブが取り外されたときに適用され、グループポリシー設定がアクティブになっているコンピューターで、リムーバブルドライブを管理するために再挿入とロック解除を行います。</span><span class="sxs-lookup"><span data-stu-id="34b8e-110">On removable drives, it is applied when the drive is removed and then re-inserted and unlocked on a computer that has Group Policy settings activated to manage removable drives.</span></span>



**<span data-ttu-id="34b8e-111">回復モードでドライブを回復するには</span><span class="sxs-lookup"><span data-stu-id="34b8e-111">To recover a drive in recovery mode</span></span>**

1.  <span data-ttu-id="34b8e-112">Web ブラウザーを開き、管理と監視の web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="34b8e-112">Open a web browser and navigate to the Administration and Monitoring website.</span></span>

2.  <span data-ttu-id="34b8e-113">ナビゲーションウィンドウで、[**ドライブの回復**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34b8e-113">In the navigation pane, click **Drive Recovery**.</span></span> <span data-ttu-id="34b8e-114">[暗号化されたドライブへのアクセスを回復する] web ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="34b8e-114">The “Recover access to an encrypted drive” webpage opens.</span></span>

3.  <span data-ttu-id="34b8e-115">回復情報を表示するユーザーの Windows ログオンドメインとユーザー名を入力して、一致する回復キーの一覧、または回復キー id 全体を取得し、正確な回復キーを受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="34b8e-115">Enter the Windows Logon domain and user name of the user to view recovery information and the first eight digits of the recovery key ID to receive a list of possible matching recovery keys or the entire recovery key ID to receive the exact recovery key.</span></span>

4.  <span data-ttu-id="34b8e-116">[**ドライブのロックを解除する理由**] ボックスの一覧からいずれかの定義済みオプションを選び、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="34b8e-116">Select one of the predefined options from the **Reason for Drive Unlock** list, and then click **Submit**.</span></span>

    **<span data-ttu-id="34b8e-117">注</span><span class="sxs-lookup"><span data-stu-id="34b8e-117">Note</span></span>**  
    <span data-ttu-id="34b8e-118">MBAM Advanced ヘルプデスクユーザーの場合、ユーザードメインとユーザー ID のエントリは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="34b8e-118">If you are an MBAM Advanced Helpdesk user, the user domain and user ID entries are not required.</span></span>



~~~
MBAM returns the following:

-   An error message if no matching recovery password is found

-   Multiple possible matches if the user has multiple matching recovery passwords

-   The recovery password and recovery package for the submitted user

    **Note**  
    If you are recovering a damaged drive, the recovery package option provides BitLocker with critical information that it needs to recover the drive.



After the recovery password and recovery package are retrieved, the recovery password is displayed.
~~~

5. <span data-ttu-id="34b8e-119">パスワードをコピーするには、[**キーのコピー**] をクリックし、メールメッセージに回復パスワードを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="34b8e-119">To copy the password, click **Copy Key**, and then paste the recovery password into an email message.</span></span> <span data-ttu-id="34b8e-120">または、[**保存**] をクリックして回復パスワードをファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="34b8e-120">Alternatively, click **Save** to save the recovery password to a file.</span></span>

   <span data-ttu-id="34b8e-121">ユーザーが回復パスワードをシステムに入力するか、回復パッケージを使用すると、ドライブのロックが解除されます。</span><span class="sxs-lookup"><span data-stu-id="34b8e-121">When the user types the recovery password into the system or uses the recovery package, the drive is unlocked.</span></span>

## <span data-ttu-id="34b8e-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="34b8e-122">Related topics</span></span>


[<span data-ttu-id="34b8e-123">MBAM での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="34b8e-123">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam-mbam-2.md)









