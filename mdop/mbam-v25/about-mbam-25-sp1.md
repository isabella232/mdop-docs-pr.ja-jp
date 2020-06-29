---
title: MBAM 2.5 SP1 の概要
description: MBAM 2.5 SP1 の概要
author: dansimp
ms.assetid: 6f12e605-44e6-4646-9c20-aee89c8ff0b7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 09/27/2016
ms.openlocfilehash: 41e47e1561629c00d30b45ad2dcd94f37753af5b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823784"
---
# <span data-ttu-id="389b8-103">MBAM 2.5 SP1 の概要</span><span class="sxs-lookup"><span data-stu-id="389b8-103">About MBAM 2.5 SP1</span></span>


<span data-ttu-id="389b8-104">MBAM 2.5 SP1 には、BitLocker ドライブ暗号化用の簡素化された管理インターフェイスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="389b8-104">MBAM 2.5 SP1 provides a simplified administrative interface for BitLocker Drive Encryption.</span></span> <span data-ttu-id="389b8-105">BitLocker は、紛失または盗難になったコンピューターのデータ盗難またはデータ漏洩に対する保護を強化します。</span><span class="sxs-lookup"><span data-stu-id="389b8-105">BitLocker offers enhanced protection against data theft or data exposure for computers that are lost or stolen.</span></span> <span data-ttu-id="389b8-106">BitLocker は、Windows オペレーティングシステムとドライブに保存されているすべてのデータを暗号化し、データドライブを構成します。</span><span class="sxs-lookup"><span data-stu-id="389b8-106">BitLocker encrypts all data that is stored on the Windows operating system and drives and configured data drives.</span></span>

## <span data-ttu-id="389b8-107">MBAM の概要</span><span class="sxs-lookup"><span data-stu-id="389b8-107">Overview of MBAM</span></span>


<span data-ttu-id="389b8-108">MBAM 2.5 SP1 には、次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="389b8-108">MBAM 2.5 SP1 has the following features:</span></span>

-   <span data-ttu-id="389b8-109">管理者は、企業全体のクライアント コンピューター上のボリュームを暗号化するプロセスを自動化できます。</span><span class="sxs-lookup"><span data-stu-id="389b8-109">Enables administrators to automate the process of encrypting volumes on client computers across the enterprise.</span></span>

-   <span data-ttu-id="389b8-110">セキュリティ担当者は、個々のコンピューターまたは企業全体の準拠状態をすばやく判断できます。</span><span class="sxs-lookup"><span data-stu-id="389b8-110">Enables security officers to quickly determine the compliance state of individual computers or even of the enterprise itself.</span></span>

-   <span data-ttu-id="389b8-111">Microsoft System Center Configuration Manager により、一元的なレポートおよびハードウェア管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="389b8-111">Provides centralized reporting and hardware management with Microsoft System Center Configuration Manager.</span></span>

-   <span data-ttu-id="389b8-112">ヘルプデスクの作業負荷を減らし、BitLocker PIN と回復キー要求を使ってエンドユーザーを支援します。</span><span class="sxs-lookup"><span data-stu-id="389b8-112">Reduces the workload on the Help Desk to assist end users with BitLocker PIN and recovery key requests.</span></span>

-   <span data-ttu-id="389b8-113">エンド ユーザーは、セルフ サービス ポータルを使って、暗号化されたデバイスを自分で回復できます。</span><span class="sxs-lookup"><span data-stu-id="389b8-113">Enables end users to recover encrypted devices independently by using the Self-Service Portal.</span></span>

-   <span data-ttu-id="389b8-114">セキュリティ責任者が、重要な情報を回復するためのアクセスを簡単に監査できるようにします。</span><span class="sxs-lookup"><span data-stu-id="389b8-114">Enables security officers to easily audit access to recover key information.</span></span>

-   <span data-ttu-id="389b8-115">企業データの保護を保証することにより、Windows Enterprise ユーザーがどこにいても作業を継続できるようにします。</span><span class="sxs-lookup"><span data-stu-id="389b8-115">Empowers Windows Enterprise users to continue working anywhere with the assurance that their corporate data is protected.</span></span>

<span data-ttu-id="389b8-116">MBAM は、企業に対して設定した BitLocker 暗号化ポリシーオプションを適用し、それらのポリシーでクライアントコンピューターのコンプライアンスを監視し、企業および個人のコンピューターの暗号化状態に関するレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="389b8-116">MBAM enforces the BitLocker encryption policy options that you set for your enterprise, monitors the compliance of client computers with those policies, and reports on the encryption status of the enterprise’s and individual’s computers.</span></span> <span data-ttu-id="389b8-117">また、ユーザーが PIN やパスワードを忘れた場合や、BIOS またはブートレコードが変更された場合は、MBAM を使用して回復キーの情報にアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="389b8-117">In addition, MBAM lets you access the recovery key information when users forget their PIN or password, or when their BIOS or boot records change.</span></span>

<span data-ttu-id="389b8-118">次のグループは、BitLocker を管理するために MBAM を使用することに関心を持っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="389b8-118">The following groups might be interested in using MBAM to manage BitLocker:</span></span>

-   <span data-ttu-id="389b8-119">管理者、IT セキュリティの専門家、および機密データが承認されずに公開されないように責任を持つコンプライアンス責任者</span><span class="sxs-lookup"><span data-stu-id="389b8-119">Administrators, IT security professionals, and compliance officers who are responsible for ensuring that confidential data is not disclosed without authorization</span></span>

-   <span data-ttu-id="389b8-120">リモートまたは支店でコンピューターのセキュリティを担当する管理者</span><span class="sxs-lookup"><span data-stu-id="389b8-120">Administrators who are responsible for computer security in remote or branch offices</span></span>

-   <span data-ttu-id="389b8-121">Windows を実行しているクライアントコンピューターに責任を持つ管理者</span><span class="sxs-lookup"><span data-stu-id="389b8-121">Administrators who are responsible for client computers that are running Windows</span></span>

<span data-ttu-id="389b8-122">**注** この MBAM 文書では、BitLocker について詳しくは説明していません。</span><span class="sxs-lookup"><span data-stu-id="389b8-122">**Note** BitLocker is not explained in detail in this MBAM documentation.</span></span> <span data-ttu-id="389b8-123">詳細については、「 [BitLocker ドライブの暗号化の概要](https://go.microsoft.com/fwlink/p/?LinkId=225013)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="389b8-123">For more information, see [BitLocker Drive Encryption Overview](https://go.microsoft.com/fwlink/p/?LinkId=225013).</span></span>

 

## <a href="" id="what-s-new-in-mbam-2-5-sp1"></a><span data-ttu-id="389b8-124">MBAM 2.5 SP1 の新機能</span><span class="sxs-lookup"><span data-stu-id="389b8-124">What’s new in MBAM 2.5 SP1</span></span>


<span data-ttu-id="389b8-125">このセクションでは、MBAM 2.5 SP1 の新機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="389b8-125">This section describes the new features in MBAM 2.5 SP1.</span></span>

### <span data-ttu-id="389b8-126">MBAM 2.5 SP1 クライアントで新しくサポートされる言語</span><span class="sxs-lookup"><span data-stu-id="389b8-126">Newly Supported Languages for the MBAM 2.5 SP1 Client</span></span>

<span data-ttu-id="389b8-127">以下の追加言語は、MBAM クライアント用の MBAM 2.5 SP1 でサポートされるようになりました (セルフサービスポータルを含む)。</span><span class="sxs-lookup"><span data-stu-id="389b8-127">The following additional languages are now supported in MBAM 2.5 SP1 for the MBAM Client only, including the Self-Service Portal:</span></span>

<span data-ttu-id="389b8-128">チェコ語 (チェコ共和国) .cs-CZ</span><span class="sxs-lookup"><span data-stu-id="389b8-128">Czech (Czech Republic) cs-CZ</span></span>

<span data-ttu-id="389b8-129">デンマーク語 (デンマーク) da-DK</span><span class="sxs-lookup"><span data-stu-id="389b8-129">Danish (Denmark) da-DK</span></span>

<span data-ttu-id="389b8-130">オランダ語 (オランダ) nl-NL</span><span class="sxs-lookup"><span data-stu-id="389b8-130">Dutch (Netherlands) nl-NL</span></span>

<span data-ttu-id="389b8-131">フィンランド語 (フィンランド) fi</span><span class="sxs-lookup"><span data-stu-id="389b8-131">Finnish (Finland) fi-FI</span></span>

<span data-ttu-id="389b8-132">ギリシャ語 (ギリシャ) el-GR</span><span class="sxs-lookup"><span data-stu-id="389b8-132">Greek (Greece) el-GR</span></span>

<span data-ttu-id="389b8-133">ハンガリー語 (ハンガリー) hu-HU</span><span class="sxs-lookup"><span data-stu-id="389b8-133">Hungarian (Hungary) hu-HU</span></span>

<span data-ttu-id="389b8-134">ノルウェー語、ブークモール (ノルウェー) nb-いいえ</span><span class="sxs-lookup"><span data-stu-id="389b8-134">Norwegian, Bokmål (Norway) nb-NO</span></span>

<span data-ttu-id="389b8-135">ポーランド語 (ポーランド) pl-PL</span><span class="sxs-lookup"><span data-stu-id="389b8-135">Polish (Poland) pl-PL</span></span>

<span data-ttu-id="389b8-136">ポルトガル語 (ポルトガル) の pt-PT</span><span class="sxs-lookup"><span data-stu-id="389b8-136">Portuguese (Portugal) pt-PT</span></span>

<span data-ttu-id="389b8-137">スロバキア語 (スロバキア) sk-SK</span><span class="sxs-lookup"><span data-stu-id="389b8-137">Slovak (Slovakia) sk-SK</span></span>

<span data-ttu-id="389b8-138">スロベニア語 (スロベニア) sl-SI</span><span class="sxs-lookup"><span data-stu-id="389b8-138">Slovenian (Slovenia) sl-SI</span></span>

<span data-ttu-id="389b8-139">スウェーデン語 (スウェーデン) sv-SE</span><span class="sxs-lookup"><span data-stu-id="389b8-139">Swedish (Sweden) sv-SE</span></span>

<span data-ttu-id="389b8-140">トルコ語 (トルコ) tr-TR</span><span class="sxs-lookup"><span data-stu-id="389b8-140">Turkish (Turkey) tr-TR</span></span>

<span data-ttu-id="389b8-141">MBAM 2.5 および MBAM 2.5 SP1 でのクライアントとサーバーでサポートされているすべての言語の一覧については、「 [mbam 2.5 サポートされる構成](mbam-25-supported-configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="389b8-141">For a list of all languages supported for client and server in MBAM 2.5 and MBAM 2.5 SP1, see [MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md).</span></span>

### <span data-ttu-id="389b8-142">Windows 10 のサポート</span><span class="sxs-lookup"><span data-stu-id="389b8-142">Support for Windows 10</span></span>

<span data-ttu-id="389b8-143">MBAM 2.5 SP1 は、以前のバージョンの MBAM でサポートされているものと同じソフトウェアに加えて、Windows 10 および Windows Server 2016 のサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="389b8-143">MBAM 2.5 SP1 adds support for Windows 10 and Windows Server 2016, in addition to the same software that is supported in earlier versions of MBAM.</span></span>

<span data-ttu-id="389b8-144">Windows 10 は、MBAM 2.5 と MBAM 2.5 SP1 の両方でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="389b8-144">Windows 10 is supported in both MBAM 2.5 and MBAM 2.5 SP1.</span></span>

### <span data-ttu-id="389b8-145">Microsoft SQL Server 2014 SP1 のサポート</span><span class="sxs-lookup"><span data-stu-id="389b8-145">Support for Microsoft SQL Server 2014 SP1</span></span>

<span data-ttu-id="389b8-146">MBAM 2.5 SP1 は、以前のバージョンの MBAM でサポートされているものと同じソフトウェアに加えて、Microsoft SQL Server 2014 SP1 のサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="389b8-146">MBAM 2.5 SP1 adds support for Microsoft SQL Server 2014 SP1, in addition to the same software that is supported in earlier versions of MBAM.</span></span>

### <span data-ttu-id="389b8-147">MBAM は別の MSI で出荷されなくなりました</span><span class="sxs-lookup"><span data-stu-id="389b8-147">MBAM no longer ships with separate MSI</span></span>

<span data-ttu-id="389b8-148">MBAM 2.5 SP1 以降、MBAM 製品には別の MSI が含まれなくなりました。</span><span class="sxs-lookup"><span data-stu-id="389b8-148">Beginning in MBAM 2.5 SP1, a separate MSI is no longer included with the MBAM product.</span></span> <span data-ttu-id="389b8-149">ただし、製品に含まれている実行可能ファイル (.exe) から MSI を抽出することはできます。</span><span class="sxs-lookup"><span data-stu-id="389b8-149">However, you can extract the MSI from the executable file (.exe) that is included with the product.</span></span>

### <span data-ttu-id="389b8-150">MBAM は、TPM を所有していない場合に、所有権の認証パスワードを使うことができます</span><span class="sxs-lookup"><span data-stu-id="389b8-150">MBAM can escrow OwnerAuth passwords without owning the TPM</span></span>

<span data-ttu-id="389b8-151">以前は、MBAM が TPM を所有していなかった場合、TPM OwnerAuth を MBAM データベースに預託たりすることはできませんでした。</span><span class="sxs-lookup"><span data-stu-id="389b8-151">Previously, if MBAM did not own the TPM, the TPM OwnerAuth could not be escrowed to the MBAM database.</span></span> <span data-ttu-id="389b8-152">TPM を所有し、パスワードを保存するために MBAM を構成するには、TPM の自動プロビジョニングを無効にし、クライアントコンピューター上の TPM をクリアする必要がありました。</span><span class="sxs-lookup"><span data-stu-id="389b8-152">To configure MBAM to own the TPM and to store the passwords, you had to disable TPM auto-provisioning and clear the TPM on the client computer.</span></span>

<span data-ttu-id="389b8-153">Windows 8 以上では、MBAM 2.5 SP1 では、TPM を所有していない場合でも OwnerAuth パスワードをエスクローすることができます。</span><span class="sxs-lookup"><span data-stu-id="389b8-153">In Windows 8 and higher, MBAM 2.5 SP1 can now escrow the OwnerAuth passwords without owning the TPM.</span></span> <span data-ttu-id="389b8-154">サービスの起動時に、MBAM は、TPM が既に所有されているかどうかを確認して、その場合はオペレーティングシステムからパスワードを要求します。</span><span class="sxs-lookup"><span data-stu-id="389b8-154">During service startup, MBAM queries to see if the TPM is already owned and if so, it requests the passwords from the operating system.</span></span> <span data-ttu-id="389b8-155">パスワードは、MBAM データベースに預託たりされます。</span><span class="sxs-lookup"><span data-stu-id="389b8-155">The passwords are then escrowed to the MBAM database.</span></span> <span data-ttu-id="389b8-156">また、OwnerAuth がローカルで削除されないように、グループポリシーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="389b8-156">In addition, Group Policy must be set to prevent the OwnerAuth from being deleted locally.</span></span>

<span data-ttu-id="389b8-157">Windows 7 では、mbam データベースの TPM OwnerAuth 情報を自動的に設定するために、MBAM は TPM を所有している必要があります。</span><span class="sxs-lookup"><span data-stu-id="389b8-157">In Windows 7, MBAM must own the TPM to automatically escrow TPM OwnerAuth information in the MBAM database.</span></span> <span data-ttu-id="389b8-158">MBAM が、tpm と Active Directory (AD) のバックアップを所有していない場合は、グループポリシーを使用して tpm の active **directory (ad) データをインポート**するためのコマンドレットを使用して、AD から mbam データベースに Tpm ownerauth をコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="389b8-158">If MBAM does not own the TPM and Active Directory (AD) backup of the TPM is configured through Group Policy, you must use the **MBAM Active Directory (AD) Data Import cmdlets** to copy TPM OwnerAuth from AD into the MBAM database.</span></span> <span data-ttu-id="389b8-159">これは、MBAM データベースに事前設定された5つの新しい PowerShell コマンドレットであり、ボリューム回復と、Active Directory に保存されている TPM 所有者情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="389b8-159">These are five new PowerShell cmdlets that pre-populate MBAM databases with the Volume recovery and TPM owner information stored in Active Directory.</span></span>

<span data-ttu-id="389b8-160">詳細については、「 [Mbam 2.5 セキュリティに関する考慮事項](mbam-25-security-considerations.md#bkmk-tpm)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="389b8-160">For more information, see [MBAM 2.5 Security Considerations](mbam-25-security-considerations.md#bkmk-tpm).</span></span>

### <span data-ttu-id="389b8-161">MBAM はロックアウト後に TPM を自動的にロック解除する</span><span class="sxs-lookup"><span data-stu-id="389b8-161">MBAM can automatically unlock the TPM after a lockout</span></span>

<span data-ttu-id="389b8-162">TPM 1.2 を実行しているコンピューターでは、ロックアウトの場合に TPM を自動的にロック解除するように MBAM を構成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="389b8-162">On computers running TPM 1.2, you can now configure MBAM to automatically unlock the TPM in case of a lockout.</span></span> <span data-ttu-id="389b8-163">TPM のロックアウト自動リセット機能が有効になっている場合、MBAM は、ユーザーがロックされていることを検出し、MBAM データベースから OwnerAuth パスワードを取得して、ユーザーの TPM を自動的にロック解除します。</span><span class="sxs-lookup"><span data-stu-id="389b8-163">If the TPM lockout auto reset feature is enabled, MBAM can detect that a user is locked out and then get the OwnerAuth password from the MBAM database to automatically unlock the TPM for the user.</span></span>

<span data-ttu-id="389b8-164">この機能は、サーバー側とクライアント側のグループポリシーの両方で有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="389b8-164">This feature must be enabled on both the server side and in Group Policy on the client side.</span></span> <span data-ttu-id="389b8-165">詳細については、「 [Mbam 2.5 セキュリティに関する考慮事項](mbam-25-security-considerations.md#bkmk-autounlock)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="389b8-165">For more information, see [MBAM 2.5 Security Considerations](mbam-25-security-considerations.md#bkmk-autounlock).</span></span>

### <span data-ttu-id="389b8-166">FIPS に準拠した BitLocker 数値パスワード保護機能のサポート</span><span class="sxs-lookup"><span data-stu-id="389b8-166">Support for FIPS-compliant BitLocker numerical password protectors</span></span>

<span data-ttu-id="389b8-167">MBAM 2.5 では、Windows 8.1 オペレーティングシステムを実行しているデバイスで連邦情報処理規格 (FIPS) に準拠した BitLocker 回復キーのサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="389b8-167">In MBAM2.5, support was added for Federal Information Processing Standard (FIPS)-compliant BitLocker recovery keys on devices running the Windows 8.1 operating system.</span></span> <span data-ttu-id="389b8-168">ただし、windows は Windows 7 で FIPS 準拠の回復キーを実装していません。</span><span class="sxs-lookup"><span data-stu-id="389b8-168">However, Windows did not implement FIPS-compliant recovery keys in Windows 7.</span></span> <span data-ttu-id="389b8-169">そのため、Windows 7 デバイスと Windows 8 デバイスでは、回復用のデータ回復エージェント (DRA) プロテクターが必要です。</span><span class="sxs-lookup"><span data-stu-id="389b8-169">Therefore, Windows 7 and Windows 8 devices still required a Data Recovery Agent (DRA) protector for recovery.</span></span>

<span data-ttu-id="389b8-170">Windows チームでは、backported FIPS 対応の回復キーがホットフィックスと共にあり、MBAM 2.5 SP1 でもサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="389b8-170">The Windows team has backported FIPS-compliant recovery keys with a hotfix, and MBAM 2.5 SP1 has added support for them as well.</span></span>

<span data-ttu-id="389b8-171">**注** Windows8 オペレーティングシステムを実行しているクライアントコンピューターには、修正プログラムがその OS に backported れていないため、引き続き DRA プロテクターが必要です。</span><span class="sxs-lookup"><span data-stu-id="389b8-171">**Note** Client computers that are running the Windows8 operating system still require a DRA protector since the hotfix was not backported to that OS.</span></span> <span data-ttu-id="389b8-172">Windows 7 および Windows 8 コンピューター用の BitLocker ホットフィックスをダウンロードしてインストールするには、「 [bitlocker の管理と2.5 監視を行うための修正プログラムパッケージ 2](https://support.microsoft.com/kb/3015477) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="389b8-172">See [Hotfix Package 2 for BitLocker Administration and Monitoring 2.5](https://support.microsoft.com/kb/3015477) to download and install the BitLocker hotfix for Windows 7 and Windows 8 computers.</span></span> <span data-ttu-id="389b8-173">DRA の詳細については、「 [BitLocker でデータ回復エージェントを使用する](https://go.microsoft.com/fwlink/?LinkId=393557)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="389b8-173">For information about DRA, see [Using Data Recovery Agents with BitLocker](https://go.microsoft.com/fwlink/?LinkId=393557).</span></span>

 

<span data-ttu-id="389b8-174">組織で FIPS のコンプライアンスを有効にするには、連邦情報処理標準 (FIPS) のグループポリシー設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="389b8-174">To enable FIPS compliance in your organization, you must configure the Federal Information Processing Standard (FIPS) Group Policy settings.</span></span> <span data-ttu-id="389b8-175">構成手順については、「 [BitLocker グループポリシーの設定](https://go.microsoft.com/fwlink/?LinkId=393560)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="389b8-175">For configuration instructions, see [BitLocker Group Policy Settings](https://go.microsoft.com/fwlink/?LinkId=393560).</span></span>

### <span data-ttu-id="389b8-176">新しいグループポリシー設定でプレブート回復メッセージと URL をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="389b8-176">Customize pre-boot recovery message and URL with new Group Policy setting</span></span>

<span data-ttu-id="389b8-177">新しいグループポリシー設定で、**プレブート回復メッセージと url を構成**すると、カスタム回復メッセージを構成するか、OS ドライブがロックされているときにプレブート BitLocker 回復画面に表示される URL を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="389b8-177">A new Group Policy setting, **Configure pre-boot recovery message and URL**, lets you configure a custom recovery message or specify a URL that is then displayed on the pre-boot BitLocker recovery screen when the OS drive is locked.</span></span> <span data-ttu-id="389b8-178">この設定は、Windows 10 を実行しているクライアントコンピューターでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="389b8-178">This setting is only available on client computers running Windows 10.</span></span>

<span data-ttu-id="389b8-179">このポリシー設定を有効にした場合、プレブート回復メッセージに対して次のいずれかのオプションを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="389b8-179">If you enable this policy setting, you can you can select one of these options for the pre-boot recovery message:</span></span>

-   <span data-ttu-id="389b8-180">[**カスタム回復メッセージを使う**]: プレブートの BitLocker 回復画面にカスタムメッセージを含めるには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="389b8-180">**Use custom recovery message**: Select this option to include a custom message in the pre-boot BitLocker recovery screen.</span></span>

-   <span data-ttu-id="389b8-181">[**カスタム回復 URL を使用**する]: プレブートの BitLocker 回復画面に表示される既定の URL を置き換えるには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="389b8-181">**Use custom recovery URL**: Select this option to replace the default URL that is displayed in the pre-boot BitLocker recovery screen.</span></span>

-   <span data-ttu-id="389b8-182">[**既定の回復メッセージと Url を使用**する]: 既定の bitlocker 回復メッセージと url をプレブートの bitlocker 回復画面に表示するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="389b8-182">**Use default recovery message and URL**: Select this option to display the default BitLocker recovery message and URL in the pre-boot BitLocker recovery screen.</span></span> <span data-ttu-id="389b8-183">以前にカスタム回復メッセージまたは URL を構成していて、既定のメッセージに戻す場合は、このポリシーを有効にして、このオプションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="389b8-183">If you previously configured a custom recovery message or URL and want to revert to the default message, you must enable this policy and select this option.</span></span>

<span data-ttu-id="389b8-184">新しいグループポリシーの設定は、次の GPO ノードにあります。**コンピューター構成** &gt; **ポリシー** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **MDOP mbam (BitLocker 管理)** &gt; **オペレーティングシステムドライブ**。</span><span class="sxs-lookup"><span data-stu-id="389b8-184">The new Group Policy setting is located in the following GPO node: **Computer Configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)** &gt; **Operating System Drive**.</span></span> <span data-ttu-id="389b8-185">詳細については、「 [MBAM 2.5 グループポリシーの要件の計画](planning-for-mbam-25-group-policy-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="389b8-185">For more information, see [Planning for MBAM 2.5 Group Policy Requirements](planning-for-mbam-25-group-policy-requirements.md).</span></span>

### <span data-ttu-id="389b8-186">MBAM 使用領域の暗号化のサポートが追加されました</span><span class="sxs-lookup"><span data-stu-id="389b8-186">MBAM added support for Used Space Encryption</span></span>

<span data-ttu-id="389b8-187">MBAM 2.5 SP1 では、BitLocker グループポリシーによって使用されるスペースの暗号化を有効にすると、MBAM クライアントによって受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="389b8-187">In MBAM 2.5 SP1, if you enable Used Space Encryption via BitLocker Group Policy, the MBAM Client honors it.</span></span>

<span data-ttu-id="389b8-188">このグループポリシー設定は、**オペレーティングシステムドライブでの [ドライブの暗号化の種類の強制**] と呼ばれ、次の GPO ノードにあります。**コンピューターの構成** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **BitLocker ドライブ暗号化** &gt; **オペレーティングシステムドライブ**。</span><span class="sxs-lookup"><span data-stu-id="389b8-188">This Group Policy setting is called **Enforce drive encryption type on operating system drives** and is located in the following GPO node: **Computer Configuration** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **BitLocker Drive Encryption** &gt; **Operating System Drives**.</span></span> <span data-ttu-id="389b8-189">このポリシーを有効にして、**使用領域のみの暗号化**として暗号化の種類を選択した場合、mbam ではポリシーが優先され、BitLocker はボリュームで使用されているディスク領域のみを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="389b8-189">If you enable this policy and select the encryption type as **Used Space Only encryption**, MBAM will honor the policy and BitLocker will only encrypt disk space that is used on the volume.</span></span>

<span data-ttu-id="389b8-190">詳細については、「 [MBAM 2.5 グループポリシーの要件の計画](planning-for-mbam-25-group-policy-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="389b8-190">For more information, see [Planning for MBAM 2.5 Group Policy Requirements](planning-for-mbam-25-group-policy-requirements.md).</span></span>

### <span data-ttu-id="389b8-191">暗号化されたハードドライブ向け MBAM クライアントのサポート</span><span class="sxs-lookup"><span data-stu-id="389b8-191">MBAM Client support for Encrypted Hard Drives</span></span>

<span data-ttu-id="389b8-192">MBAM は、Opal と IEEE 1667 標準の TCG 仕様要件を満たす、暗号化されたハードドライブ上の BitLocker をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="389b8-192">MBAM supports BitLocker on Encrypted Hard Drives that meet TCG specification requirements for Opal as well as IEEE 1667 standards.</span></span> <span data-ttu-id="389b8-193">これらのデバイスで BitLocker が有効になっている場合は、暗号化されたドライブでキーを生成し、管理機能を実行します。</span><span class="sxs-lookup"><span data-stu-id="389b8-193">When BitLocker is enabled on these devices, it will generate keys and perform management functions on the encrypted drive.</span></span> <span data-ttu-id="389b8-194">詳細については、「[暗号化されたハードドライブ](https://technet.microsoft.com/library/hh831627.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="389b8-194">See [Encrypted Hard Drive](https://technet.microsoft.com/library/hh831627.aspx) for more information.</span></span>

### <span data-ttu-id="389b8-195">Spn の登録時に委任構成が不要になった</span><span class="sxs-lookup"><span data-stu-id="389b8-195">Delegation configuration no longer required when registering SPNs</span></span>

<span data-ttu-id="389b8-196">アプリケーションプールアカウントに登録する Spn の制約付き委任を構成するための要件は、MBAM 2.5 SP1 では必要なくなりました。</span><span class="sxs-lookup"><span data-stu-id="389b8-196">The requirement to configure constrained delegation for SPNs that you register for the application pool account is no longer necessary in MBAM 2.5 SP1.</span></span> <span data-ttu-id="389b8-197">ただし、まだ MBAM 2.5 の要件となっています。</span><span class="sxs-lookup"><span data-stu-id="389b8-197">However, it is still a requirement for MBAM 2.5.</span></span>

### <span data-ttu-id="389b8-198">Windows 展開の一部として MBAM を使用して BitLocker を有効にする</span><span class="sxs-lookup"><span data-stu-id="389b8-198">Enable BitLocker using MBAM as Part of a Windows Deployment</span></span>

<span data-ttu-id="389b8-199">MBAM 2.5 SP1 では、PowerShell スクリプトを使って、MBAM サーバーに対して BitLocker ドライブ暗号化とエスクローの回復キーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="389b8-199">In MBAM 2.5 SP1, you can use a PowerShell script to configure BitLocker drive encryption and escrow recovery keys to the MBAM Server.</span></span>

<span data-ttu-id="389b8-200">詳細については、「 [Windows 展開の一部として MBAM を使用して BitLocker を有効にする方法](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="389b8-200">For more information, see [How to Enable BitLocker by Using MBAM as Part of a Windows Deployment](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md)</span></span>

### <span data-ttu-id="389b8-201">セルフサービスポータルは、PowerShell または SSP カスタマイズウィザードを使用してカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="389b8-201">Self-Service Portal can be customized by using either PowerShell or the SSP customization wizard</span></span>

<span data-ttu-id="389b8-202">MBAM 2.5 SP1 の場合、セルフサービスポータルは、カスタマイズウィザードと PowerShell を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="389b8-202">As of MBAM 2.5 SP1, the Self-Service Portal can be configured by using the customization wizard as well as by using PowerShell.</span></span> <span data-ttu-id="389b8-203">[MBAM 2.5 Web アプリケーションを構成する方法に](how-to-configure-the-mbam-25-web-applications.md)ついて説明します。</span><span class="sxs-lookup"><span data-stu-id="389b8-203">See [How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md).</span></span>

### <span data-ttu-id="389b8-204">Web ブラウザーが管理者として意図せずに動作しなくなった</span><span class="sxs-lookup"><span data-stu-id="389b8-204">Web browser no longer unintentionally runs as administrator</span></span>

<span data-ttu-id="389b8-205">MBAM 2.5 の問題により、サーバー構成ツールのヘルプリンクが表示され、ブラウザーウィンドウが管理者権限で開くようになりました。</span><span class="sxs-lookup"><span data-stu-id="389b8-205">An issue in MBAM 2.5 caused help links in the Server Configuration tool to cause browser windows to open with administrator rights.</span></span> <span data-ttu-id="389b8-206">この問題は、MBAM 2.5 SP1 で修正されています。</span><span class="sxs-lookup"><span data-stu-id="389b8-206">This issue is fixed in MBAM 2.5 SP1.</span></span>

### <span data-ttu-id="389b8-207">CDN にアクセスできない場合は、JavaScript ファイルをダウンロードしてセルフサービスポータルを構成する必要がなくなりました</span><span class="sxs-lookup"><span data-stu-id="389b8-207">No longer need to download the JavaScript files to configure the Self-Service Portal when the CDN is inaccessible</span></span>

<span data-ttu-id="389b8-208">MBAM 2.5 およびそれ以前のバージョンでは、セルフサービスポータルにアクセスしているクライアントがインターネットにアクセスできなかった場合に、セルフサービスポータルの構成に使用される jQuery ファイルを事前に CDN からダウンロードする必要がありました。</span><span class="sxs-lookup"><span data-stu-id="389b8-208">In MBAM 2.5 and earlier, the jQuery files used for configuration of the Self-Service Portal had to be downloaded from the CDN in advance if clients accessing the Self-Service Portal did not have internet access.</span></span> <span data-ttu-id="389b8-209">MBAM 2.5 SP1 では、すべての JavaScript ファイルが製品に含まれているため、ダウンロードする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="389b8-209">In MBAM 2.5 SP1, all JavaScript files are included in the product, so downloading them is unnecessary.</span></span>

### <span data-ttu-id="389b8-210">レポートは、レポートビルダー3.0 で開くことができます。</span><span class="sxs-lookup"><span data-stu-id="389b8-210">Reports can be opened in Report Builder 3.0</span></span>

<span data-ttu-id="389b8-211">MBAM 2.5 SP1 では、レポートは最新のレポート定義言語スキーマに更新されているため、ユーザーはレポート3.0 ビルダーのレポートを開いてカスタマイズし、レポートファイルを破損せずにすぐに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="389b8-211">In MBAM 2.5 SP1, the reports have been updated to the latest report definition language schema, allowing users to open and customize the reports in Report Builder 3.0 and save them immediately without corrupting the report file.</span></span>

### <span data-ttu-id="389b8-212">新しい PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="389b8-212">New PowerShell cmdlets</span></span>

<span data-ttu-id="389b8-213">MBAM 2.5 SP1 用の新しい PowerShell コマンドレットを使用すると、データベース、レポート、web アプリケーションなどのさまざまな MBAM 機能を構成して管理できます。</span><span class="sxs-lookup"><span data-stu-id="389b8-213">New PowerShell cmdlets for MBAM 2.5 SP1 enable you to configure and manage different MBAM features, including databases, reports, and web applications.</span></span> <span data-ttu-id="389b8-214">各機能には対応する PowerShell コマンドレットがあり、機能を有効または無効にしたり、機能に関する情報を取得したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="389b8-214">Each feature has a corresponding PowerShell cmdlet that you can use to enable or disable features, or to get information about the feature.</span></span>

<span data-ttu-id="389b8-215">MBAM 2.5 SP1 には、次のコマンドレットが実装されています。</span><span class="sxs-lookup"><span data-stu-id="389b8-215">The following cmdlets have been implemented for MBAM 2.5 SP1:</span></span>

-   <span data-ttu-id="389b8-216">書き込み-MbamTpmInformation</span><span class="sxs-lookup"><span data-stu-id="389b8-216">Write-MbamTpmInformation</span></span>

-   <span data-ttu-id="389b8-217">書き込み用の MbamRecoveryInformation</span><span class="sxs-lookup"><span data-stu-id="389b8-217">Write-MbamRecoveryInformation</span></span>

-   <span data-ttu-id="389b8-218">読み取り-ADTpmInformation</span><span class="sxs-lookup"><span data-stu-id="389b8-218">Read-ADTpmInformation</span></span>

-   <span data-ttu-id="389b8-219">読み取り-ADRecoveryInformation</span><span class="sxs-lookup"><span data-stu-id="389b8-219">Read-ADRecoveryInformation</span></span>

-   <span data-ttu-id="389b8-220">書き込み用の MbamComputerUser</span><span class="sxs-lookup"><span data-stu-id="389b8-220">Write-MbamComputerUser</span></span>

<span data-ttu-id="389b8-221">MBAM 2.5 SP1 の Enable-MbamWebApplication およびテスト用の MbamWebApplication コマンドレットには、次のパラメーターが実装されています。</span><span class="sxs-lookup"><span data-stu-id="389b8-221">The following parameters have been implemented in the Enable-MbamWebApplication and Test-MbamWebApplication cmdlets for MBAM 2.5 SP1:</span></span>

-   <span data-ttu-id="389b8-222">DataMigrationAccessGroup</span><span class="sxs-lookup"><span data-stu-id="389b8-222">DataMigrationAccessGroup</span></span>

-   <span data-ttu-id="389b8-223">TpmAutoUnlock</span><span class="sxs-lookup"><span data-stu-id="389b8-223">TpmAutoUnlock</span></span>

<span data-ttu-id="389b8-224">コマンドレットの詳細については、「 [Mbam 2.5 セキュリティに関する考慮事項](mbam-25-security-considerations.md)」および「 [Microsoft Bitlocker 管理と監視コマンドレットのヘルプ](https://technet.microsoft.com/library/dn720418.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="389b8-224">For information about the cmdlets, see [MBAM 2.5 Security Considerations](mbam-25-security-considerations.md) and [Microsoft Bitlocker Administration and Monitoring Cmdlet Help](https://technet.microsoft.com/library/dn720418.aspx).</span></span>

### <span data-ttu-id="389b8-225">MBAM エージェントでプレゼンテーションモードが検出される</span><span class="sxs-lookup"><span data-stu-id="389b8-225">MBAM agent detects presentation mode</span></span>

<span data-ttu-id="389b8-226">MBAM エージェントは、コンピューターがプレゼンテーションモードになっているときに、その時点で MBAM UI が呼び出されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="389b8-226">The MBAM agent can detect when the computer is in presentation mode and avoid invoking the MBAM UI at that time.</span></span>

### <span data-ttu-id="389b8-227">MBAM エージェントサービスが遅延開始を使用するように構成されるようになりました</span><span class="sxs-lookup"><span data-stu-id="389b8-227">MBAM agent service now configured to use delayed start</span></span>

<span data-ttu-id="389b8-228">インストール後、サービスは、遅延開始を使用するように MBAM エージェントサービスを設定し、Windows を起動するのにかかる時間を減らします。</span><span class="sxs-lookup"><span data-stu-id="389b8-228">After installation, the service will now set the MBAM agent service to use delayed start, decreasing the amount of time it takes to start Windows.</span></span>

### <span data-ttu-id="389b8-229">ロックされた固定データボリュームは、コンプライアンスとして報告する</span><span class="sxs-lookup"><span data-stu-id="389b8-229">Locked Fixed Data volumes now report as Compliant</span></span>

<span data-ttu-id="389b8-230">"ロックされた固定データ" ボリュームのコンプライアンス計算ロジックは、ボリュームを "準拠" として報告するように変更されましたが、プロテクターの状態と暗号化の状態は "不明" で、コンプライアンスの状態は "ボリュームはロックされています" という情報になります。</span><span class="sxs-lookup"><span data-stu-id="389b8-230">The compliance calculation logic for "Locked Fixed Data" volumes has been changed to report the volumes as "Compliant," but with a Protector State and Encryption State of "Unknown" and with a Compliance Status Detail of "Volume is locked".</span></span> <span data-ttu-id="389b8-231">以前は、ロックされているボリュームは、"非準拠"、プロテクターの状態が "暗号化"、暗号化の状態が "不明"、暗号化状態の詳細に "不明なエラー" と報告されました。</span><span class="sxs-lookup"><span data-stu-id="389b8-231">Previously, locked volumes were reported as “Non-Compliant”, a Protector State of "Encrypted", an Encryption State of "Unknown", and a Compliance Status Detail of "An unknown error".</span></span>


## <span data-ttu-id="389b8-232">MDOP 技術の入手方法</span><span class="sxs-lookup"><span data-stu-id="389b8-232">How to Get MDOP Technologies</span></span>


<span data-ttu-id="389b8-233">MBAM は Microsoft デスクトップ最適化パック (MDOP) の一部です。</span><span class="sxs-lookup"><span data-stu-id="389b8-233">MBAM is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="389b8-234">MDOP は、Microsoft ソフトウェアアシュアランスプログラムに含まれています。</span><span class="sxs-lookup"><span data-stu-id="389b8-234">MDOP is part of the Microsoft Software Assurance program.</span></span> <span data-ttu-id="389b8-235">Microsoft ソフトウェアアシュアランスプログラムと MDOP の入手方法の詳細については、「 [mdop の入手](https://go.microsoft.com/fwlink/?LinkId=322049)方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="389b8-235">For more information about the Microsoft Software Assurance program and how to acquire the MDOP, see [How Do I Get MDOP?](https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="389b8-236">MBAM 2.5 SP1 リリースノート</span><span class="sxs-lookup"><span data-stu-id="389b8-236">MBAM 2.5 SP1 Release Notes</span></span>


<span data-ttu-id="389b8-237">このドキュメントに記載されていない詳細および最新ニュースについては、「 [MBAM 2.5 SP1 のリリースノート](release-notes-for-mbam-25-sp1.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="389b8-237">For more information and late-breaking news that is not included in this documentation, see [Release Notes for MBAM 2.5 SP1](release-notes-for-mbam-25-sp1.md).</span></span>

## <span data-ttu-id="389b8-238">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="389b8-238">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="389b8-239">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="389b8-239">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="389b8-240">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="389b8-240">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>

## <span data-ttu-id="389b8-241">関連トピック</span><span class="sxs-lookup"><span data-stu-id="389b8-241">Related topics</span></span>


[<span data-ttu-id="389b8-242">Microsoft BitLocker Administration and Monitoring 2.5</span><span class="sxs-lookup"><span data-stu-id="389b8-242">Microsoft BitLocker Administration and Monitoring 2.5</span></span>](index.md)

[<span data-ttu-id="389b8-243">MBAM 2.5 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="389b8-243">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)

 

 





