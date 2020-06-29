---
title: ヘルプ デスク ポータルを使用する方法
description: ヘルプ デスク ポータルを使用する方法
author: dansimp
ms.assetid: c27f7737-10c8-4164-9de8-57987292c89c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa8813fbe9a7b6980b656ecc673ac4ed618c4cf7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826327"
---
# <span data-ttu-id="d9954-103">ヘルプ デスク ポータルを使用する方法</span><span class="sxs-lookup"><span data-stu-id="d9954-103">How to Use the Help Desk Portal</span></span>


<span data-ttu-id="d9954-104">MBAM 管理と監視の web サイト (ヘルプデスクポータルとも呼ばれます) は、Microsoft BitLocker の管理と監視 (MBAM) サーバーインフラストラクチャの一部としてインストールされている、BitLocker ドライブ暗号化の管理インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="d9954-104">The MBAM Administration and Monitoring website, also referred to as the Help Desk Portal, is an administrative interface to BitLocker drive encryption that is installed as part of the Microsoft BitLocker Administration and Monitoring (MBAM) server infrastructure.</span></span> <span data-ttu-id="d9954-105">以下のセクションでは、この web サイトを使用してレポートを確認し、エンドユーザーのドライブを回復して、エンドユーザーの TPMs を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d9954-105">The following sections describe how you can use this website to review reports, recover end users’ drives, and manage end users’ TPMs.</span></span>

## <a href="" id="bkmk-reports"></a><span data-ttu-id="d9954-106">レポート</span><span class="sxs-lookup"><span data-stu-id="d9954-106">Reports</span></span>


<span data-ttu-id="d9954-107">MBAM は、Active Directory とクライアントコンピューターから情報を収集します。これにより、複数のレポートを実行して、BitLocker の使用状況とコンプライアンスを監視することができます。</span><span class="sxs-lookup"><span data-stu-id="d9954-107">MBAM collects information from Active Directory and client computers, which enables you to run different reports to monitor BitLocker usage and compliance.</span></span> <span data-ttu-id="d9954-108">管理と監視の web サイトの [**レポート**] セクションを使用して、エンタープライズのコンプライアンス、個々のコンピューター、およびキーの回復アクティビティに関するレポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="d9954-108">Using the **Reports** section of the Administration and Monitoring website, you can generate reports on enterprise compliance, individual computers, and key recovery activity.</span></span> <span data-ttu-id="d9954-109">各レポートの説明については、「 [MBAM レポートについ](understanding-mbam-reports-mbam-2.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9954-109">For a description of each report, see [Understanding MBAM Reports](understanding-mbam-reports-mbam-2.md).</span></span>

**<span data-ttu-id="d9954-110">レポートにアクセスするには</span><span class="sxs-lookup"><span data-stu-id="d9954-110">To access reports</span></span>**

1.  <span data-ttu-id="d9954-111">Web ブラウザーを開き、MBAM 管理と監視の web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="d9954-111">Open a web browser and navigate to the MBAM Administration and Monitoring website.</span></span>

2.  <span data-ttu-id="d9954-112">左側のウィンドウで [**レポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9954-112">Select **Reports** in the left pane.</span></span>

3.  <span data-ttu-id="d9954-113">トップメニューバーで、生成するレポートの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="d9954-113">From the top menu bar, select the report type you want to generate.</span></span> <span data-ttu-id="d9954-114">レポートを保存するには、[レポート] メニューバーの [**エクスポート**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9954-114">To save reports, click the **Export** button on the Reports menu bar.</span></span>

<span data-ttu-id="d9954-115">MBAM レポートの実行方法の詳細については、「 [Mbam レポートを生成する方法](how-to-generate-mbam-reports-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9954-115">For additional information about how to run MBAM reports, see [How to Generate MBAM Reports](how-to-generate-mbam-reports-mbam-2.md).</span></span>

## <a href="" id="bkmk-drirec"></a><span data-ttu-id="d9954-116">ドライブの回復</span><span class="sxs-lookup"><span data-stu-id="d9954-116">Drive Recovery</span></span>


<span data-ttu-id="d9954-117">管理と監視の web サイトの**ドライブ回復**機能により、特定の管理者の役割 (ヘルプデスクのユーザーなど) が、Mbam クライアントで収集された回復キーデータにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="d9954-117">The **Drive Recovery** feature of the Administration and Monitoring website allows users with specific administrator roles (for example, Help Desk Users) to access recovery key data that has been collected by the MBAM Client.</span></span> <span data-ttu-id="d9954-118">BitLocker で保護されたドライブにアクセスするには、このデータを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="d9954-118">This data can be used to access a BitLocker-protected drive when BitLocker goes into recovery mode.</span></span> <span data-ttu-id="d9954-119">回復モードのドライブを復元する方法については、「[回復モードでドライブを回復する方法](how-to-recover-a-drive-in-recovery-mode-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9954-119">For instructions on how to recover a drive that is in recovery mode, see [How to Recover a Drive in Recovery Mode](how-to-recover-a-drive-in-recovery-mode-mbam-2.md).</span></span>

<span data-ttu-id="d9954-120">また、移動された、または破損したドライブを復元することもできます。</span><span class="sxs-lookup"><span data-stu-id="d9954-120">You can also recover drives that have been moved or that are corrupted:</span></span>

-   [<span data-ttu-id="d9954-121">移動されたドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="d9954-121">How to Recover a Moved Drive</span></span>](how-to-recover-a-moved-drive-mbam-2.md)

-   [<span data-ttu-id="d9954-122">破損しているドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="d9954-122">How to Recover a Corrupted Drive</span></span>](how-to-recover-a-corrupted-drive-mbam-2.md)

<span data-ttu-id="d9954-123">BitLocker で保護されたドライブを回復する方法の詳細については、「 [MBAM での Bitlocker 管理の実行](performing-bitlocker-management-with-mbam-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9954-123">For additional information about how to recover a BitLocker-protected drive, see [Performing BitLocker Management with MBAM](performing-bitlocker-management-with-mbam-mbam-2.md).</span></span>

## <a href="" id="bkmk-manatpm"></a><span data-ttu-id="d9954-124">TPM を管理する</span><span class="sxs-lookup"><span data-stu-id="d9954-124">Manage TPM</span></span>


<span data-ttu-id="d9954-125">管理および監視 web サイトの TPM の管理機能を使うと、ユーザーに、MBAM クライアントによって収集された TPM データへのアクセス許可 ("MBAM ヘルプデスクユーザー" など) が与えられます。</span><span class="sxs-lookup"><span data-stu-id="d9954-125">The Manage TPM feature of the Administration and Monitoring website gives users with certain administrator roles (for example, “MBAM Helpdesk Users”) access to TPM data that has been collected by the MBAM Client.</span></span> <span data-ttu-id="d9954-126">TPM ロックアウトでは、管理者は管理と監視の web サイトを使って、TPM のロックを解除するために必要なパスワードファイルを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="d9954-126">In a TPM lockout, an administrator can use the Administration and Monitoring website to retrieve the necessary password file to unlock the TPM.</span></span> <span data-ttu-id="d9954-127">Tpm ロックアウト後に TPM をリセットする方法については、「 [Tpm ロックアウトをリセットする方法](how-to-reset-a-tpm-lockout-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9954-127">For instructions on how to reset a TPM after a TPM lockout, see [How to Reset a TPM Lockout](how-to-reset-a-tpm-lockout-mbam-2.md).</span></span>

## <a href="" id="bkmk-helpdesk"></a> <span data-ttu-id="d9954-128">MBAM ヘルプデスクのタスク</span><span class="sxs-lookup"><span data-stu-id="d9954-128">MBAM Help Desk Tasks</span></span>


<span data-ttu-id="d9954-129">管理と監視の web サイトを使用して、BitLocker で保護されたハードウェアの管理、ドライブの回復、レポートの実行など、多くの管理タスクを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d9954-129">You can use the Administration and Monitoring website for many administrative tasks, such as managing BitLocker-protected hardware, recovering drives, and running reports.</span></span> <span data-ttu-id="d9954-130">管理と監視の web サイトの URL は、既定では http:// &lt; *mbamadministration servername*ですが、 &gt; インストールプロセス中にカスタマイズすることはできます。</span><span class="sxs-lookup"><span data-stu-id="d9954-130">By default, the URL for the Administration and Monitoring website is http://&lt;*MBAMAdministrationServername*&gt;, although you can customize it during the installation process.</span></span>

<span data-ttu-id="d9954-131">**注** 管理と監視の web サイトで提供されるさまざまな機能にアクセスするには、ユーザーアカウントに関連付けられた適切なロールを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9954-131">**Note** To access the various features offered by the Administration and Monitoring website, you must have the appropriate roles associated with your user account.</span></span> <span data-ttu-id="d9954-132">ユーザーロールの概要については、「 [MBAM 管理者ロールを管理する方法](how-to-manage-mbam-administrator-roles-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9954-132">For more information about understanding user roles, see [How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-2.md).</span></span>

 

<span data-ttu-id="d9954-133">管理と監視の web サイトを使用して実行できるタスクについては、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9954-133">Use the following links to find information about the tasks that you can perform by using the Administration and Monitoring website:</span></span>

-   [<span data-ttu-id="d9954-134">TPM ロックアウトをリセットする方法</span><span class="sxs-lookup"><span data-stu-id="d9954-134">How to Reset a TPM Lockout</span></span>](how-to-reset-a-tpm-lockout-mbam-2.md)

-   [<span data-ttu-id="d9954-135">回復モードでドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="d9954-135">How to Recover a Drive in Recovery Mode</span></span>](how-to-recover-a-drive-in-recovery-mode-mbam-2.md)

-   [<span data-ttu-id="d9954-136">移動されたドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="d9954-136">How to Recover a Moved Drive</span></span>](how-to-recover-a-moved-drive-mbam-2.md)

-   [<span data-ttu-id="d9954-137">破損しているドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="d9954-137">How to Recover a Corrupted Drive</span></span>](how-to-recover-a-corrupted-drive-mbam-2.md)

-   [<span data-ttu-id="d9954-138">紛失したコンピューターの BitLocker 暗号化の状態を確認する方法</span><span class="sxs-lookup"><span data-stu-id="d9954-138">How to Determine BitLocker Encryption State of Lost Computers</span></span>](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-2.md)

 

 





