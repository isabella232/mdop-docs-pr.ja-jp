---
title: MBAM 2.5 のセキュリティに関する考慮事項
description: MBAM 2.5 のセキュリティに関する考慮事項
author: dansimp
ms.assetid: f6613c63-b32b-45fb-a6e8-673d6dae7d16
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/23/2017
ms.openlocfilehash: 86a756ab6f983fa1f22de6835b5993e1215d1dbe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826837"
---
# <span data-ttu-id="112ff-103">MBAM 2.5 のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="112ff-103">MBAM 2.5 Security Considerations</span></span>


<span data-ttu-id="112ff-104">このトピックには、Microsoft BitLocker の管理と監視 (MBAM) をセキュリティで保護する方法に関する次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="112ff-104">This topic contains the following information about how to secure Microsoft BitLocker Administration and Monitoring (MBAM):</span></span>

-   [<span data-ttu-id="112ff-105">MBAM を構成して TPM をエスクローし、所有者の認証パスワードを保存する</span><span class="sxs-lookup"><span data-stu-id="112ff-105">Configure MBAM to escrow the TPM and store OwnerAuth passwords</span></span>](#bkmk-tpm)

-   [<span data-ttu-id="112ff-106">ロックアウト後に TPM を自動的にロック解除するように MBAM を設定する</span><span class="sxs-lookup"><span data-stu-id="112ff-106">Configure MBAM to automatically unlock the TPM after a lockout</span></span>](#bkmk-autounlock)

-   [<span data-ttu-id="112ff-107">SQL Server への接続をセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="112ff-107">Secure connections to SQL Server</span></span>](#bkmk-secure-databases)

-   [<span data-ttu-id="112ff-108">アカウントとグループを作成する</span><span class="sxs-lookup"><span data-stu-id="112ff-108">Create accounts and groups</span></span>](#bkmk-accts-groups)

-   [<span data-ttu-id="112ff-109">MBAM ログファイルを使用する</span><span class="sxs-lookup"><span data-stu-id="112ff-109">Use MBAM log files</span></span>](#bkmk-logfiles)

-   [<span data-ttu-id="112ff-110">MBAM データベースの確認に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="112ff-110">Review MBAM database TDE considerations</span></span>](#bkmk-tde)

-   [<span data-ttu-id="112ff-111">一般的なセキュリティの考慮事項を理解する</span><span class="sxs-lookup"><span data-stu-id="112ff-111">Understand general security considerations</span></span>](#bkmk-general-security)

## <a href="" id="bkmk-tpm"></a><span data-ttu-id="112ff-112">MBAM を構成して TPM をエスクローし、所有者の認証パスワードを保存する</span><span class="sxs-lookup"><span data-stu-id="112ff-112">Configure MBAM to escrow the TPM and store OwnerAuth passwords</span></span>

<span data-ttu-id="112ff-113">**注**Windows 10 バージョン1607以降では、Windows のみが TPM の所有権を取得できます。</span><span class="sxs-lookup"><span data-stu-id="112ff-113">**Note** For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="112ff-114">さらに、TPM をプロビジョニングするときに、Windows によって TPM 所有者のパスワードは保持されません。</span><span class="sxs-lookup"><span data-stu-id="112ff-114">In addition, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="112ff-115">詳細については、 [TPM 所有者パスワード](https://docs.microsoft.com/windows/security/information-protection/tpm/change-the-tpm-owner-password)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="112ff-115">See [TPM owner password](https://docs.microsoft.com/windows/security/information-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

<span data-ttu-id="112ff-116">構成によっては、信頼されたプラットフォームモジュール (TPM) は特定の状況でロックされます。たとえば、パスワードが多すぎる場合や、一定の期間ロックされている場合などがあります。</span><span class="sxs-lookup"><span data-stu-id="112ff-116">Depending on its configuration, the Trusted Platform Module (TPM) will lock itself in certain situations ─ such as when too many incorrect passwords are entered ─ and can remain locked for a period of time.</span></span> <span data-ttu-id="112ff-117">TPM のロックアウト中は、BitLocker で暗号化キーにアクセスしてロック解除または暗号化解除の操作を実行することはできません。ユーザーは、オペレーティングシステムドライブにアクセスするために BitLocker 回復キーを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="112ff-117">During TPM lockout, BitLocker cannot access the encryption keys to perform unlock or decryption operations, requiring the user to enter their BitLocker recovery key to access the operating system drive.</span></span> <span data-ttu-id="112ff-118">TPM ロックアウトをリセットするには、TPM OwnerAuth パスワードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="112ff-118">To reset TPM lockout, you must provide the TPM OwnerAuth password.</span></span>

<span data-ttu-id="112ff-119">MBAM は、tpm を所有している場合、またはパスワードを escrows 場合は、MBAM データベースに TPM OwnerAuth パスワードを保存できます。</span><span class="sxs-lookup"><span data-stu-id="112ff-119">MBAM can store the TPM OwnerAuth password in the MBAM database if it owns the TPM or if it escrows the password.</span></span> <span data-ttu-id="112ff-120">所有者認証パスワードは、TPM ロックアウトから回復する必要がある場合に、管理と監視の Web サイトで簡単にアクセスできます。ロックアウトが自動的に解決されるのを待つ必要はありません。</span><span class="sxs-lookup"><span data-stu-id="112ff-120">OwnerAuth passwords are then easily accessible on the Administration and Monitoring Website when you must recover from a TPM lockout, eliminating the need to wait for the lockout to resolve on its own.</span></span>

### <span data-ttu-id="112ff-121">Windows 8 以上の Escrowing TPM OwnerAuth</span><span class="sxs-lookup"><span data-stu-id="112ff-121">Escrowing TPM OwnerAuth in Windows 8 and higher</span></span>

<span data-ttu-id="112ff-122">**注**Windows 10 バージョン1607以降では、Windows のみが TPM の所有権を取得できます。</span><span class="sxs-lookup"><span data-stu-id="112ff-122">**Note** For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="112ff-123">Addiiton では、TPM のプロビジョニング時に Windows は TPM 所有者パスワードを保持しません。</span><span class="sxs-lookup"><span data-stu-id="112ff-123">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="112ff-124">詳細については、 [TPM 所有者パスワード](https://docs.microsoft.com/windows/security/information-protection/tpm/change-the-tpm-owner-password)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="112ff-124">See [TPM owner password](https://docs.microsoft.com/windows/security/information-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

<span data-ttu-id="112ff-125">Windows 8 以上の場合、MBAM は、ownerauth がローカルコンピューターで利用可能であれば、OwnerAuth パスワードを保存するために TPM を所有している必要がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="112ff-125">In Windows 8 or higher, MBAM no longer must own the TPM to store the OwnerAuth password, as long as the OwnerAuth is available on the local machine.</span></span>

<span data-ttu-id="112ff-126">MBAM からエスクローを有効にし、TPM OwnerAuth パスワードを保存するには、これらのグループポリシー設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="112ff-126">To enable MBAM to escrow and then store TPM OwnerAuth passwords, you must configure these Group Policy settings.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="112ff-127">グループポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="112ff-127">Group Policy Setting</span></span></th>
<th align="left"><span data-ttu-id="112ff-128">構成</span><span class="sxs-lookup"><span data-stu-id="112ff-128">Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="112ff-129">Active Directory ドメインサービスへの TPM バックアップを有効にする</span><span class="sxs-lookup"><span data-stu-id="112ff-129">Turn on TPM backup to Active Directory Domain Services</span></span></p></td>
<td align="left"><p><span data-ttu-id="112ff-130">Disabled または未構成</span><span class="sxs-lookup"><span data-stu-id="112ff-130">Disabled or Not Configured</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="112ff-131">オペレーティングシステムで利用できる TPM 所有者認証情報のレベルを構成する</span><span class="sxs-lookup"><span data-stu-id="112ff-131">Configure the level of TPM owner authorization information available to the operating system</span></span></p></td>
<td align="left"><p><span data-ttu-id="112ff-132">委任/なしまたは未構成</span><span class="sxs-lookup"><span data-stu-id="112ff-132">Delegated/None or Not Configured</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="112ff-133">これらのグループポリシー設定の場所は、**コンピューター構成**の &gt; **管理用テンプレート** &gt; **システム**の &gt; **信頼できるプラットフォームモジュールサービス**です。</span><span class="sxs-lookup"><span data-stu-id="112ff-133">The location of these Group Policy settings is **Computer Configuration** &gt; **Administrative Templates** &gt; **System** &gt; **Trusted Platform Module Services**.</span></span>

<span data-ttu-id="112ff-134">**注** MBAM がこれらの設定で正常に escrows した場合、Windows はローカルで OwnerAuth を削除します。</span><span class="sxs-lookup"><span data-stu-id="112ff-134">**Note** Windows removes the OwnerAuth locally after MBAM successfully escrows it with these settings.</span></span>

 

### <span data-ttu-id="112ff-135">Windows 7 の Escrowing TPM OwnerAuth</span><span class="sxs-lookup"><span data-stu-id="112ff-135">Escrowing TPM OwnerAuth in Windows 7</span></span>

<span data-ttu-id="112ff-136">Windows 7 では、mbam データベースの TPM OwnerAuth 情報を自動的に設定するために、MBAM は TPM を所有している必要があります。</span><span class="sxs-lookup"><span data-stu-id="112ff-136">In Windows 7, MBAM must own the TPM to automatically escrow TPM OwnerAuth information in the MBAM database.</span></span> <span data-ttu-id="112ff-137">MBAM が TPM を所有していない場合は、MBAM Active Directory (AD) データインポートコマンドレットを使用して、Active Directory から MBAM データベースに TPM OwnerAuth をコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="112ff-137">If MBAM does not own the TPM, you must use the MBAM Active Directory (AD) Data Import cmdlets to copy TPM OwnerAuth from Active Directory into the MBAM database.</span></span>

### <span data-ttu-id="112ff-138">MBAM Active Directory データのインポートコマンドレット</span><span class="sxs-lookup"><span data-stu-id="112ff-138">MBAM Active Directory Data Import cmdlets</span></span>

<span data-ttu-id="112ff-139">MBAM Active Directory データのインポートコマンドレットを使用して、Active Directory に保存されている回復キーパッケージと OwnerAuth パスワードを取得できます。</span><span class="sxs-lookup"><span data-stu-id="112ff-139">The MBAM Active Directory Data Import cmdlets let you retrieve recovery key packages and OwnerAuth passwords that are stored in Active Directory.</span></span>

<span data-ttu-id="112ff-140">MBAM 2.5 SP1 サーバーには、既定で MBAM データベースを作成するための4つの PowerShell コマンドレットが付属しており、ボリューム回復と、TPM 所有者の情報は Active Directory に保存されています。</span><span class="sxs-lookup"><span data-stu-id="112ff-140">The MBAM 2.5 SP1 server ships with four PowerShell cmdlets that pre-populate MBAM databases with the Volume recovery and TPM owner information stored in Active Directory.</span></span>

<span data-ttu-id="112ff-141">ボリューム回復キーとパッケージの場合:</span><span class="sxs-lookup"><span data-stu-id="112ff-141">For Volume Recovery keys and packages:</span></span>

-   <span data-ttu-id="112ff-142">読み取り-ADRecoveryInformation</span><span class="sxs-lookup"><span data-stu-id="112ff-142">Read-ADRecoveryInformation</span></span>

-   <span data-ttu-id="112ff-143">書き込み用の MbamRecoveryInformation</span><span class="sxs-lookup"><span data-stu-id="112ff-143">Write-MbamRecoveryInformation</span></span>

<span data-ttu-id="112ff-144">TPM 所有者情報:</span><span class="sxs-lookup"><span data-stu-id="112ff-144">For TPM Owner Information:</span></span>

-   <span data-ttu-id="112ff-145">読み取り-ADTpmInformation</span><span class="sxs-lookup"><span data-stu-id="112ff-145">Read-ADTpmInformation</span></span>

-   <span data-ttu-id="112ff-146">書き込み-MbamTpmInformation</span><span class="sxs-lookup"><span data-stu-id="112ff-146">Write-MbamTpmInformation</span></span>

<span data-ttu-id="112ff-147">ユーザーをコンピューターに関連付けるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="112ff-147">For Associating Users to Computers:</span></span>

-   <span data-ttu-id="112ff-148">書き込み用の MbamComputerUser</span><span class="sxs-lookup"><span data-stu-id="112ff-148">Write-MbamComputerUser</span></span>

<span data-ttu-id="112ff-149">Read-AD \ \* コマンドレットは Active Directory から情報を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="112ff-149">The Read-AD\* cmdlets read information from Active Directory.</span></span> <span data-ttu-id="112ff-150">書き込み用の Mbam \ \* コマンドレットは、MBAM データベースにデータをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="112ff-150">The Write-Mbam\* cmdlets push the data into the MBAM databases.</span></span> <span data-ttu-id="112ff-151">構文、パラメーター、例など、これらのコマンドレットの詳細については、「 [Microsoft Bitlocker 管理と監視の2.5 のコマンドレットリファレンス](https://technet.microsoft.com/library/dn459018.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="112ff-151">See [Cmdlet Reference for Microsoft Bitlocker Administration and Monitoring 2.5](https://technet.microsoft.com/library/dn459018.aspx) for detailed information about these cmdlets, including syntax, parameters, and examples.</span></span>

<span data-ttu-id="112ff-152">**ユーザー間の関連付けを作成する:** MBAM Active Directory データインポートコマンドレットは、Active Directory から情報を収集し、MBAM データベースにデータを挿入します。</span><span class="sxs-lookup"><span data-stu-id="112ff-152">**Create user-to-computer associations:** The MBAM Active Directory Data Import cmdlets gather information from Active Directory and insert the data into MBAM database.</span></span> <span data-ttu-id="112ff-153">ただし、ユーザーはユーザーをボリュームに関連付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="112ff-153">However, they do not associate users to volumes.</span></span> <span data-ttu-id="112ff-154">Add-ComputerUser.ps1 PowerShell スクリプトをダウンロードしてユーザー間の関連付けを作成することができます。これにより、ユーザーは管理と監視の Web サイトを通じて、またはセルフサービスポータルを使用して、コンピューターにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="112ff-154">You can download the Add-ComputerUser.ps1 PowerShell script to create user-to-machine associations, which let users regain access to a computer through the Administration and Monitoring Website or by using the Self-Service Portal for recovery.</span></span> <span data-ttu-id="112ff-155">Add-ComputerUser.ps1 スクリプトは、Active Directory (AD) の [**管理者**] 属性、ad のオブジェクト所有者、またはカスタム CSV ファイルからデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="112ff-155">The Add-ComputerUser.ps1 script gathers data from the **Managed By** attribute in Active Directory (AD), the object owner in AD, or from a custom CSV file.</span></span> <span data-ttu-id="112ff-156">次に、スクリプトは検出されたユーザーを回復情報パイプラインオブジェクトに追加します。これは、データを回復用データベースに挿入するために、MbamRecoveryInformation に渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="112ff-156">The script then adds the discovered users to the recovery information pipeline object, which must be passed to Write-MbamRecoveryInformation to insert the data into the recovery database.</span></span>

<span data-ttu-id="112ff-157">[Microsoft ダウンロードセンター](https://go.microsoft.com/fwlink/?LinkId=613122)から Add-ComputerUser.ps1 PowerShell スクリプトをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="112ff-157">Download the Add-ComputerUser.ps1 PowerShell script from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=613122).</span></span>

<span data-ttu-id="112ff-158">スクリプトのヘルプを表示するには、コマンドレットとスクリプトの使い方の例など、**ヘルプ Add-ComputerUser.ps1**を指定します。</span><span class="sxs-lookup"><span data-stu-id="112ff-158">You can specify **help Add-ComputerUser.ps1** to get help for the script, including examples of how to use the cmdlets and the script.</span></span>

<span data-ttu-id="112ff-159">MBAM サーバーをインストールした後に、ユーザーとコンピューターの関連付けを作成するには、MbamComputerUser PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="112ff-159">To create user-to-computer associations after you have installed the MBAM server, use the Write-MbamComputerUser PowerShell cmdlet.</span></span> <span data-ttu-id="112ff-160">このコマンドレットでは、Add-ComputerUser.ps1 PowerShell スクリプトと同様に、セルフサービスポータルを使用して、指定されたコンピューターの TPM OwnerAuth information またはボリューム回復パスワードを取得できるユーザーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="112ff-160">Similar to the Add-ComputerUser.ps1 PowerShell script, this cmdlet lets you specify users that can use the Self-Service Portal to get TPM OwnerAuth information or volume recovery passwords for the specified computer.</span></span>

<span data-ttu-id="112ff-161">**注** MBAM エージェントは、コンピューターがサーバーへのレポートを開始するときに、ユーザーとコンピューターの関連付けを上書きします。</span><span class="sxs-lookup"><span data-stu-id="112ff-161">**Note** The MBAM agent will override user-to-computer associations when that computer begins reporting up to the server.</span></span>

 

<span data-ttu-id="112ff-162">**前提条件:** 読み取り専用 \ \* コマンドレットは、ドメイン管理者などの高い権限を持つユーザーアカウントとして実行されるか、または情報への読み取りアクセス権が付与されたカスタムセキュリティグループのアカウントとして実行される場合にのみ、広告から情報を取得できます (推奨)。</span><span class="sxs-lookup"><span data-stu-id="112ff-162">**Prerequisites:** The Read-AD\* cmdlets can retrieve information from AD only if they are either run as a highly privileged user account, such as a Domain Administrator, or run as an account in a custom security group granted read access to the information (recommended).</span></span>

<span data-ttu-id="112ff-163">[BitLocker ドライブ暗号化操作ガイド: AD DS を使用して暗号化さ](https://technet.microsoft.com/library/cc771778(WS.10).aspx)れたボリュームを回復すると、広告情報に対する読み取りアクセス権を持つカスタムセキュリティグループ (または複数のグループ) の作成に関する詳細が提供されます。</span><span class="sxs-lookup"><span data-stu-id="112ff-163">[BitLocker Drive Encryption Operations Guide: Recovering Encrypted Volumes with AD DS](https://technet.microsoft.com/library/cc771778(WS.10).aspx) provides details about creating a custom security group (or multiple groups) with read access to the AD information.</span></span>

<span data-ttu-id="112ff-164">**Mbam Recovery と Hardware Web サービスの書き込みアクセス許可:** 書き込み用の Mbam \ \* コマンドレットは、MBAM 回復とハードウェアサービスの URL を受け取り、回復または TPM 情報の公開に使用します。</span><span class="sxs-lookup"><span data-stu-id="112ff-164">**MBAM Recovery and Hardware Web Service Write Permissions:** The Write-Mbam\* cmdlets accept the URL of the MBAM Recovery and Hardware Service, used to publish the recovery or TPM information.</span></span> <span data-ttu-id="112ff-165">通常、MBAM Recovery およびハードウェアサービスと通信できるのは、ドメインコンピューターサービスアカウントだけです。</span><span class="sxs-lookup"><span data-stu-id="112ff-165">Typically, only a domain computer service account can communicate with the MBAM Recovery and Hardware Service.</span></span> <span data-ttu-id="112ff-166">MBAM 2.5 SP1 では、DataMigrationAccessGroup というセキュリティグループを使用して、MBAM 回復とハードウェアサービスを構成することができます。これにより、メンバーは、ドメインコンピューターサービスアカウントのチェックを省略できます。</span><span class="sxs-lookup"><span data-stu-id="112ff-166">In MBAM 2.5 SP1, you can configure the MBAM Recovery and Hardware Service with a security group called DataMigrationAccessGroup whose members are allowed to bypass the domain computer service account check.</span></span> <span data-ttu-id="112ff-167">書き込み用の Mbam \ \* コマンドレットは、この構成されたグループに属しているユーザーとして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="112ff-167">The Write-Mbam\* cmdlets must be run as a user belonging to this configured group.</span></span> <span data-ttu-id="112ff-168">(または、構成されたグループ内の個別のユーザーの資格情報を、Mbam \ \* コマンドレットの-Credential パラメーターを使って指定できます)。</span><span class="sxs-lookup"><span data-stu-id="112ff-168">(Alternatively, the credentials of an individual user in the configured group can be specified by using the –Credential parameter in the Write-Mbam\* cmdlets.)</span></span>

<span data-ttu-id="112ff-169">以下のいずれかの方法で、このセキュリティグループの名前を使用して、MBAM Recovery とハードウェアサービスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="112ff-169">You can configure the MBAM Recovery and Hardware Service with the name of this security group in one of these ways:</span></span>

-   <span data-ttu-id="112ff-170">DataMigrationAccessGroup パラメーターを使用して、セキュリティグループ (個別) の名前を Enable-MbamWebApplication – AgentService Powershell コマンドレットに指定します。</span><span class="sxs-lookup"><span data-stu-id="112ff-170">Provide the name of the security group (or individual) in the -DataMigrationAccessGroup parameter of the Enable-MbamWebApplication –AgentService Powershell cmdlet.</span></span>

-   <span data-ttu-id="112ff-171">MBAM 回復とハードウェアサービスがインストールされた後にグループを構成するには、 &lt; inetpub &gt; ¥ Microsoft Bitlocker Management solution¥ Recovery and hardware Service\ \ フォルダーの web.config ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="112ff-171">Configure the group after the MBAM Recovery and Hardware Service has been installed by editing the web.config file in the &lt;inetpub&gt;\\Microsoft Bitlocker Management Solution\\Recovery and Hardware Service\\ folder.</span></span>

    ```xml
    <add key="DataMigrationUsersGroupName" value="<groupName>|<empty>" />
    ```

    <span data-ttu-id="112ff-172">ここ &lt; &gt; で、GroupName は Active Directory からのデータ移行を許可するために使用されるドメインとグループ名 (または個々のユーザー) に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="112ff-172">where &lt;groupName&gt; is replaced with the domain and the group name (or the individual user) that will be used to allow data migration from Active Directory.</span></span>

-   <span data-ttu-id="112ff-173">この appSetting を編集するには、IIS Manager の構成エディターを使用します。</span><span class="sxs-lookup"><span data-stu-id="112ff-173">Use the Configuration Editor in IIS Manager to edit this appSetting.</span></span>

<span data-ttu-id="112ff-174">次の例では、ADRecoveryInformation グループとデータ移行ユーザーグループの両方のメンバーとして実行すると、mbam.contoso.com サーバー上で実行されている MBAM 回復とハードウェアサービスを使って、contoso.com ドメインのワークステーション組織単位 (OU) のコンピューターからボリューム回復情報を取得して、MBAM に書き込みます。</span><span class="sxs-lookup"><span data-stu-id="112ff-174">In the following example, the command, when run as a member of both the ADRecoveryInformation group and the Data Migration Users group, will pull the volume recovery information from computers in the WORKSTATIONS organizational unit (OU) in the contoso.com domain and write them to MBAM by using the MBAM Recovery and Hardware Service running on the mbam.contoso.com server.</span></span>

``` syntax
PS C:\> Read-ADRecoveryInformation -Server contoso.com -SearchBase "OU=WORKSTATIONS,DC=CONTOSO,DC=COM" | Write-MbamRecoveryInformation -RecoveryServiceEndPoint "https://mbam.contoso.com/MBAMRecoveryAndHardwareService/CoreService.svc"
```

<span data-ttu-id="112ff-175">**読み取り-AD \ \* コマンドレット**は、回復または TPM 情報を照会する Active Directory ホスティングサーバーコンピューターの名前または IP アドレスを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="112ff-175">**Read-AD\* cmdlets** accept the name or IP address of an Active Directory hosting server machine to query for recovery or TPM information.</span></span> <span data-ttu-id="112ff-176">コンピューターオブジェクトが SearchBase パラメーターの値として存在する広告コンテナーの識別名を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="112ff-176">We recommend providing the distinguished names of the AD containers in which the computer object resides as the value of the SearchBase parameter.</span></span> <span data-ttu-id="112ff-177">複数の Ou にわたってコンピューターが保存されている場合、コマンドレットでパイプライン入力を受け入れて、各コンテナーについて1回実行することができます。</span><span class="sxs-lookup"><span data-stu-id="112ff-177">If computers are stored across several OUs, the cmdlets can accept pipeline input to run once for each container.</span></span> <span data-ttu-id="112ff-178">広告コンテナーの識別名は、OU = マシン、DC = contoso、DC = com と同様に表示されます。</span><span class="sxs-lookup"><span data-stu-id="112ff-178">The distinguished name of an AD container will look similar to OU=Machines,DC=contoso,DC=com.</span></span> <span data-ttu-id="112ff-179">特定のコンテナーを対象とした検索を実行すると、次の利点が得られます。</span><span class="sxs-lookup"><span data-stu-id="112ff-179">Performing a search targeted to specific containers provides the following benefits:</span></span>

-   <span data-ttu-id="112ff-180">コンピューターオブジェクトの大規模な広告データセットを照会するときのタイムアウトのリスクを軽減します。</span><span class="sxs-lookup"><span data-stu-id="112ff-180">Reduces the risk of timeout while querying a large AD dataset for computer objects.</span></span>

-   <span data-ttu-id="112ff-181">データセンターサーバーまたはバックアップが必要とされていない可能性があるその他のクラスを含む Ou は省略できます。</span><span class="sxs-lookup"><span data-stu-id="112ff-181">Can omit OUs containing datacenter servers or other classes of computers for which the backup might not be desired or necessary.</span></span>

<span data-ttu-id="112ff-182">別の方法として、指定した検索ベースまたはドメイン全体の下にあるすべてのコンテナーでコンピューターオブジェクトを検索するために、オプションの検索ベースを指定するか、または省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="112ff-182">Another option is to provide the –Recurse flag with or without the optional SearchBase to search for computer objects across all containers under the specified SearchBase or the entire domain respectively.</span></span> <span data-ttu-id="112ff-183">-再帰フラグを使う場合は、-MaxPageSize パラメーターを使って、クエリを処理するために必要なローカルメモリとリモートメモリの量を制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="112ff-183">When you use the -Recurse flag, you can also use the -MaxPageSize parameter to control the amount of local and remote memory required to service the query.</span></span>

<span data-ttu-id="112ff-184">これらのコマンドレットは、型 PsObject のパイプラインオブジェクトに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="112ff-184">These cmdlets write to the pipeline objects of type PsObject.</span></span> <span data-ttu-id="112ff-185">各 PsObject インスタンスには、関連付けられたコンピューター名、タイムスタンプ、およびその他の情報を MBAM データストアに公開するために必要なその他の情報を含む、1つのボリューム回復キーまたは TPM 所有者の文字列が含まれています。</span><span class="sxs-lookup"><span data-stu-id="112ff-185">Each PsObject instance contains a single volume recovery key or TPM owner string with its associated computer name, timestamp, and other information required to publish it to the MBAM data store.</span></span>

<span data-ttu-id="112ff-186">**書き込み用の Mbam \ \* コマンドレット**は、プロパティ名によってパイプラインから回復情報パラメーターの値を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="112ff-186">**Write-Mbam\* cmdlets** accept recovery information parameter values from the pipeline by property name.</span></span> <span data-ttu-id="112ff-187">これにより、書き込み用の Mbam \ \* コマンドレットは、Read-AD \ \* コマンドレットのパイプライン出力を受け入れることができます (たとえば、contoso.com-Server の–再帰 |書き込み-MbamRecoveryInformation – RecoveryServiceEndpoint mbam.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="112ff-187">This allows the Write-Mbam\* cmdlets to accept the pipeline output of the Read-AD\* cmdlets (for example, Read-ADRecoveryInformation –Server contoso.com –Recurse | Write-MbamRecoveryInformation –RecoveryServiceEndpoint mbam.contoso.com).</span></span>

<span data-ttu-id="112ff-188">書き込み用の**Mbam \ \* コマンドレット**には、フォールトトレランス、詳細なログ、および WhatIf と Confirm の環境設定のオプションを提供するオプションのパラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="112ff-188">The **Write-Mbam\* cmdlets** include optional parameters that provide options for fault tolerance, verbose logging, and preferences for WhatIf and Confirm.</span></span>

<span data-ttu-id="112ff-189">**書き込み用の Mbam \ \* コマンドレット**には、 **DateTime**オブジェクトの値を含むオプションの*Time*パラメーターも含まれています。</span><span class="sxs-lookup"><span data-stu-id="112ff-189">The **Write-Mbam\* cmdlets** also include an optional *Time* parameter whose value is a **DateTime** object.</span></span> <span data-ttu-id="112ff-190">このオブジェクトには*Kind* `Local` 、、、またはに設定できる Kind 属性が含まれてい `UTC` `Unspecified` ます。</span><span class="sxs-lookup"><span data-stu-id="112ff-190">This object includes a *Kind* attribute that can be set to `Local`, `UTC`, or `Unspecified`.</span></span> <span data-ttu-id="112ff-191">Active Directory から取得したデータから*time*パラメーターを設定すると、時刻は UTC に変換され、この*Kind*属性は自動的にに設定され `UTC` ます。</span><span class="sxs-lookup"><span data-stu-id="112ff-191">When the *Time* parameter is populated from data taken from the Active Directory, the time is converted to UTC and this *Kind* attribute is set automatically to `UTC`.</span></span> <span data-ttu-id="112ff-192">ただし、別のソース (テキストファイルなど) を使用して*Time*パラメーターを設定する場合は、 *Kind*属性を適切な値に明示的に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="112ff-192">However, when populating the *Time* parameter using another source, such as a text file, you must explicitly set the *Kind* attribute to its appropriate value.</span></span>

<span data-ttu-id="112ff-193">**注** 読み取り-AD \ \* コマンドレットには、コンピューターユーザーを表すユーザーアカウントを検出する機能はありません。</span><span class="sxs-lookup"><span data-stu-id="112ff-193">**Note** The Read-AD\* cmdlets do not have the ability to discover the user accounts that represent the computer users.</span></span> <span data-ttu-id="112ff-194">ユーザーアカウントの関連付けは、次の場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="112ff-194">User account associations are needed for the following:</span></span>

-   <span data-ttu-id="112ff-195">セルフサービスポータルを使用してボリュームパスワード/パッケージを復元するユーザー</span><span class="sxs-lookup"><span data-stu-id="112ff-195">Users to recover volume passwords/packages by using the Self-Service portal</span></span>

-   <span data-ttu-id="112ff-196">インストール時に定義された MBAM Advanced ヘルプデスクのユーザーセキュリティグループに含まれていないユーザー、他のユーザーの代理として回復する</span><span class="sxs-lookup"><span data-stu-id="112ff-196">Users who are not in the MBAM Advanced Helpdesk Users security group as defined during installation, recovering on behalf of other users</span></span>

 

## <a href="" id="bkmk-autounlock"></a><span data-ttu-id="112ff-197">ロックアウト後に TPM を自動的にロック解除するように MBAM を設定する</span><span class="sxs-lookup"><span data-stu-id="112ff-197">Configure MBAM to automatically unlock the TPM after a lockout</span></span>


<span data-ttu-id="112ff-198">MBAM 2.5 SP1 を構成すると、ロックアウトの場合に TPM が自動的にロックされます。</span><span class="sxs-lookup"><span data-stu-id="112ff-198">You can configure MBAM 2.5 SP1 to automatically unlock the TPM in case of a lockout.</span></span> <span data-ttu-id="112ff-199">TPM のロックアウト自動リセットが有効になっている場合、MBAM は、ユーザーがロックされていることを検出し、MBAM データベースから OwnerAuth パスワードを取得して、ユーザーの TPM を自動的にロック解除します。</span><span class="sxs-lookup"><span data-stu-id="112ff-199">If TPM lockout auto reset is enabled, MBAM can detect that a user is locked out and then get the OwnerAuth password from the MBAM database to automatically unlock the TPM for the user.</span></span> <span data-ttu-id="112ff-200">TPM のロックアウト自動リセットは、そのコンピューターの OS の回復キーがセルフサービスポータルまたは管理/監視 Web サイトを使用して取得された場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="112ff-200">TPM lockout auto reset is only available if the OS recovery key for that computer was retrieved by using the Self Service Portal or the Administration and Monitoring Website.</span></span>

<span data-ttu-id="112ff-201">**重要** TPM ロックアウトの自動リセットを有効にするには、この機能をサーバー側とクライアント側のグループポリシーの両方で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="112ff-201">**Important** To enable TPM lockout auto reset, you must configure this feature on both the server side and in Group Policy on the client side.</span></span>

 

-   <span data-ttu-id="112ff-202">クライアント側で tpm ロックアウトの自動リセットを有効にするには、グループポリシー設定を構成します。**コンピューターの構成** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **MDOP mbam** &gt; **クライアント管理**</span><span class="sxs-lookup"><span data-stu-id="112ff-202">To enable TPM lockout auto reset on the client side, configure the Group Policy setting "Configure TPM lockout auto reset" located at **Computer Configuration** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM** &gt; **Client Management**.</span></span>

-   <span data-ttu-id="112ff-203">サーバー側で TPM ロックアウトの自動リセットを有効にするには、セットアップ時に MBAM サーバー構成ウィザードで [TPM ロックアウトの自動リセットを有効にする] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="112ff-203">To enable TPM lockout auto reset on the server side, you can check "Enable TPM lockout auto reset" in the MBAM Server Configuration wizard during setup.</span></span>

    <span data-ttu-id="112ff-204">また、「-TPM ロックアウト自動リセット」スイッチを指定して、エージェントサービス web コンポーネントを有効にすることで、PowerShell で TPM ロックアウトの自動リセットを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="112ff-204">You can also enable TPM lockout auto reset in PowerShell by specifying the "-TPM lockout auto reset" switch while enabling the agent service web component.</span></span>

<span data-ttu-id="112ff-205">ユーザーがセルフサービスポータルまたは管理と監視の Web サイトから取得した BitLocker 回復キーを入力した後、MBAM エージェントは、TPM がロックされているかどうかを確認します。ロックアウトされている場合は、MBAM データベースからコンピューターの TPM OwnerAuth を取得しようとします。</span><span class="sxs-lookup"><span data-stu-id="112ff-205">After a user enters the BitLocker recovery key they obtained from the Self Service Portal or the Administration and Monitoring Website, the MBAM agent will determine if the TPM is locked out. If it is locked out, it will attempt to retrieve the TPM OwnerAuth for the computer from the MBAM database.</span></span> <span data-ttu-id="112ff-206">TPM OwnerAuth が正常に取得された場合は、TPM のロックを解除するために使われます。</span><span class="sxs-lookup"><span data-stu-id="112ff-206">If the TPM OwnerAuth is successfully retrieved, it will be used to unlock the TPM.</span></span> <span data-ttu-id="112ff-207">Tpm のロックを解除すると、tpm が完全に機能し、ユーザーは TPM ロックアウト後の再起動中に回復パスワードの入力を強制されません。</span><span class="sxs-lookup"><span data-stu-id="112ff-207">Unlocking the TPM makes the TPM fully functional and the user will not be forced to enter the recovery password during subsequent reboots from a TPM lockout.</span></span>

<span data-ttu-id="112ff-208">TPM のロックアウトの自動リセットは、既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="112ff-208">TPM lockout auto reset is disabled by default.</span></span>

<span data-ttu-id="112ff-209">**注** TPM のロックアウト自動リセットは、TPM バージョン1.2 を実行しているコンピューターでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="112ff-209">**Note** TPM lockout auto reset is only supported on computers running TPM version 1.2.</span></span> <span data-ttu-id="112ff-210">TPM 2.0 には、組み込みのロックアウト自動リセット機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="112ff-210">TPM 2.0 provides built-in lockout auto reset functionality.</span></span>

 

<span data-ttu-id="112ff-211">**回復監査レポート**には、TPM ロックアウト自動リセットに関連するイベントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="112ff-211">**The Recovery Audit Report** includes events related to TPM lockout auto reset.</span></span> <span data-ttu-id="112ff-212">MBAM クライアントから要求された場合、TPM OwnerAuth パスワードを取得するために、イベントがログに記録され、回復を示します。</span><span class="sxs-lookup"><span data-stu-id="112ff-212">If a request is made from the MBAM client to retrieve a TPM OwnerAuth password, an event is logged to indicate recovery.</span></span> <span data-ttu-id="112ff-213">監査エントリには、次のイベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="112ff-213">Audit entries will include the following events:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="112ff-214">記録</span><span class="sxs-lookup"><span data-stu-id="112ff-214">Entry</span></span></th>
<th align="left"><span data-ttu-id="112ff-215">値</span><span class="sxs-lookup"><span data-stu-id="112ff-215">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="112ff-216">監査要求ソース</span><span class="sxs-lookup"><span data-stu-id="112ff-216">Audit Request Source</span></span></p></td>
<td align="left"><p><span data-ttu-id="112ff-217">エージェント TPM のロック解除</span><span class="sxs-lookup"><span data-stu-id="112ff-217">Agent TPM unlock</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="112ff-218">キーの種類</span><span class="sxs-lookup"><span data-stu-id="112ff-218">Key Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="112ff-219">TPM パスワードハッシュ</span><span class="sxs-lookup"><span data-stu-id="112ff-219">TPM Password Hash</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="112ff-220">理由の説明</span><span class="sxs-lookup"><span data-stu-id="112ff-220">Reason Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="112ff-221">TPM リセット</span><span class="sxs-lookup"><span data-stu-id="112ff-221">TPM Reset</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-secure-databases"></a><span data-ttu-id="112ff-222">SQL Server への接続をセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="112ff-222">Secure connections to SQL Server</span></span>


<span data-ttu-id="112ff-223">MBAM では、sql Server は、SQL Server Reporting Services と、管理および監視 web サイトとセルフサービスポータル用の web サービスと通信します。</span><span class="sxs-lookup"><span data-stu-id="112ff-223">In MBAM, SQL Server communicates with SQL Server Reporting Services and with the web services for the Administration and Monitoring Website and Self-Service Portal.</span></span> <span data-ttu-id="112ff-224">SQL Server との通信をセキュリティで保護することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="112ff-224">We recommend that you secure the communication with SQL Server.</span></span> <span data-ttu-id="112ff-225">詳細については、「 [SQL Server への接続の暗号化](https://technet.microsoft.com/library/ms189067.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="112ff-225">For more information, see [Encrypting Connections to SQL Server](https://technet.microsoft.com/library/ms189067.aspx).</span></span>

<span data-ttu-id="112ff-226">MBAM web サイトのセキュリティ保護の詳細については、「 [Mbam Web サイトをセキュリティで保護する方法を計画する](planning-how-to-secure-the-mbam-websites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="112ff-226">For more information about securing the MBAM websites, see [Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md).</span></span>

## <a href="" id="bkmk-accts-groups"></a><span data-ttu-id="112ff-227">アカウントとグループを作成する</span><span class="sxs-lookup"><span data-stu-id="112ff-227">Create accounts and groups</span></span>


<span data-ttu-id="112ff-228">ユーザーアカウントを管理するためのベストプラクティスは、ドメイングローバルグループを作成し、ユーザーアカウントを追加することです。</span><span class="sxs-lookup"><span data-stu-id="112ff-228">The best practice for managing user accounts is to create domain global groups and add user accounts to them.</span></span> <span data-ttu-id="112ff-229">推奨されるアカウントとグループの説明については、「 [MBAM 2.5 グループとアカウントの計画](planning-for-mbam-25-groups-and-accounts.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="112ff-229">For a description of the recommended accounts and groups, see [Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md).</span></span>

## <a href="" id="bkmk-logfiles"></a><span data-ttu-id="112ff-230">MBAM ログファイルを使用する</span><span class="sxs-lookup"><span data-stu-id="112ff-230">Use MBAM log files</span></span>


<span data-ttu-id="112ff-231">このセクションでは、MBAM Server および MBAM クライアントログファイルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="112ff-231">This section describes the MBAM Server and MBAM Client log files.</span></span>

**<span data-ttu-id="112ff-232">MBAM サーバーセットアップログファイル</span><span class="sxs-lookup"><span data-stu-id="112ff-232">MBAM Server Setup log files</span></span>**

<span data-ttu-id="112ff-233">MBAM のインストール中に、 **MBAMServerSetup.exe**ファイルによって、ユーザーの **% temp%** フォルダーに次のログファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="112ff-233">The **MBAMServerSetup.exe** file generates the following log files in the user’s **%temp%** folder during the MBAM installation:</span></span>

-   **<span data-ttu-id="112ff-234">Microsoft \ _BitLocker \ _Administration \ _and \ _Monitoring \ _ &lt; # &gt; .log</span><span class="sxs-lookup"><span data-stu-id="112ff-234">Microsoft\_BitLocker\_Administration\_and\_Monitoring\_&lt;14 numbers&gt;.log</span></span>**

    <span data-ttu-id="112ff-235">MBAM セットアップおよび MBAM サーバー機能の構成中に実行されたアクションをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="112ff-235">Logs the actions taken during the MBAM setup and the MBAM Server feature configuration.</span></span>

-   **<span data-ttu-id="112ff-236">Microsoft \ _BitLocker \ _Administration \ _and \ _Monitoring \ _ &lt; 14 \ _numbers &gt;\_0\_MBAMServer.msi</span><span class="sxs-lookup"><span data-stu-id="112ff-236">Microsoft\_BitLocker\_Administration\_and\_Monitoring\_&lt;14\_numbers&gt;\_0\_MBAMServer.msi.log</span></span>**

    <span data-ttu-id="112ff-237">インストール中に実行される追加のアクションを記録します。</span><span class="sxs-lookup"><span data-stu-id="112ff-237">Logs additional action taken during installation.</span></span>

**<span data-ttu-id="112ff-238">MBAM サーバー構成ログファイル</span><span class="sxs-lookup"><span data-stu-id="112ff-238">MBAM Server Configuration log files</span></span>**

-   **<span data-ttu-id="112ff-239">アプリケーションとサービスログ/Microsoft Windows/MBAM-セットアップ</span><span class="sxs-lookup"><span data-stu-id="112ff-239">Applications and Services Logs/Microsoft Windows/MBAM-Setup</span></span>**

    <span data-ttu-id="112ff-240">Windows Powershell コマンドレットまたは MBAM サーバー構成ウィザードを使っているときに、MBAM サーバー機能を構成するときに発生するエラーをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="112ff-240">Logs the errors that occur when you are using Windows Powershell cmdlets or the MBAM Server Configuration wizard to configure the MBAM Server features.</span></span>

**<span data-ttu-id="112ff-241">MBAM クライアントのセットアップログファイル</span><span class="sxs-lookup"><span data-stu-id="112ff-241">MBAM Client setup log files</span></span>**

-   **<span data-ttu-id="112ff-242">MSI &lt; 5 ランダム文字 &gt; ログ</span><span class="sxs-lookup"><span data-stu-id="112ff-242">MSI&lt;five random characters&gt;.log</span></span>**

    <span data-ttu-id="112ff-243">MBAM クライアントのインストール中に実行されたアクションをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="112ff-243">Logs the actions taken during the MBAM Client installation.</span></span>

**<span data-ttu-id="112ff-244">MBAM-Web ログファイル</span><span class="sxs-lookup"><span data-stu-id="112ff-244">MBAM-Web log files</span></span>**

-   <span data-ttu-id="112ff-245">Web ポータルとサービスからのアクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="112ff-245">Shows activity from the web portals and services.</span></span>

## <a href="" id="bkmk-tde"></a><span data-ttu-id="112ff-246">MBAM データベースの確認に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="112ff-246">Review MBAM database TDE considerations</span></span>


<span data-ttu-id="112ff-247">SQL Server で使用できる透過データ暗号化 (TDE) 機能は、MBAM データベース機能をホストするデータベースインスタンスのオプションのインストールです。</span><span class="sxs-lookup"><span data-stu-id="112ff-247">The transparent data encryption (TDE) feature that is available in SQL Server is an optional installation for the database instances that will host the MBAM database features.</span></span>

<span data-ttu-id="112ff-248">TDE では、リアルタイムの完全なデータベースレベルの暗号化を実行できます。</span><span class="sxs-lookup"><span data-stu-id="112ff-248">With TDE, you can perform real-time, full database-level encryption.</span></span> <span data-ttu-id="112ff-249">TDE は、法令遵守または企業データセキュリティ標準に準拠するために、一括暗号化に最適な選択肢です。</span><span class="sxs-lookup"><span data-stu-id="112ff-249">TDE is the optimal choice for bulk encryption to meet regulatory compliance or corporate data security standards.</span></span> <span data-ttu-id="112ff-250">TDE はファイルレベルで動作します。これは、暗号化ファイルシステム (EFS) と BitLocker ドライブ暗号化の2つの Windows 機能に似ています。</span><span class="sxs-lookup"><span data-stu-id="112ff-250">TDE works at the file level, which is similar to two Windows features: the Encrypting File System (EFS) and BitLocker Drive Encryption.</span></span> <span data-ttu-id="112ff-251">どちらの機能も、ハードドライブ上のデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="112ff-251">Both features also encrypt data on the hard drive.</span></span> <span data-ttu-id="112ff-252">TDE では、セルレベルの暗号化、EFS、または BitLocker は置き換えられません。</span><span class="sxs-lookup"><span data-stu-id="112ff-252">TDE does not replace cell-level encryption, EFS, or BitLocker.</span></span>

<span data-ttu-id="112ff-253">データベースで TDE を有効にすると、すべてのバックアップが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="112ff-253">When TDE is enabled on a database, all backups are encrypted.</span></span> <span data-ttu-id="112ff-254">そのため、データベース暗号化キーを保護するために使用された証明書がバックアップされ、データベースのバックアップと維持されるように、特別な注意を払う必要があります。</span><span class="sxs-lookup"><span data-stu-id="112ff-254">Thus, special care must be taken to ensure that the certificate that was used to protect the database encryption key is backed up and maintained with the database backup.</span></span> <span data-ttu-id="112ff-255">この証明書 (または証明書) が失われると、データを読み取ることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="112ff-255">If this certificate (or certificates) is lost, the data will be unreadable.</span></span>

<span data-ttu-id="112ff-256">データベースを使用して証明書をバックアップします。</span><span class="sxs-lookup"><span data-stu-id="112ff-256">Back up the certificate with the database.</span></span> <span data-ttu-id="112ff-257">各証明書のバックアップには、2つのファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="112ff-257">Each certificate backup should have two files.</span></span> <span data-ttu-id="112ff-258">これらのファイルはどちらもアーカイブする必要があります。</span><span class="sxs-lookup"><span data-stu-id="112ff-258">Both of these files should be archived.</span></span> <span data-ttu-id="112ff-259">セキュリティのために、データベースバックアップファイルとは別にバックアップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="112ff-259">Ideally for security, they should be backed up separately from the database backup file.</span></span> <span data-ttu-id="112ff-260">または、拡張キー管理 (EKM) 機能の使用を検討してください (「拡張キー管理」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="112ff-260">You can alternatively consider using the extensible key management (EKM) feature (see Extensible Key Management) for storage and maintenance of keys that are used for TDE.</span></span>

<span data-ttu-id="112ff-261">MBAM データベースインスタンスの TDE を有効にする方法の例については、「[透過データ暗号化 (tde) の概要](https://technet.microsoft.com/library/bb934049.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="112ff-261">For an example of how to enable TDE for MBAM database instances, see [Understanding Transparent Data Encryption (TDE)](https://technet.microsoft.com/library/bb934049.aspx).</span></span>

## <a href="" id="bkmk-general-security"></a><span data-ttu-id="112ff-262">一般的なセキュリティの考慮事項を理解する</span><span class="sxs-lookup"><span data-stu-id="112ff-262">Understand general security considerations</span></span>


**<span data-ttu-id="112ff-263">セキュリティのリスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="112ff-263">Understand the security risks.</span></span>** <span data-ttu-id="112ff-264">Microsoft BitLocker の管理と監視を使用するときに最も重大なリスクは、BitLocker ドライブの暗号化を再構成し、MBAM クライアントで BitLocker 暗号化キーデータを取得できる承認されていないユーザーによって、その機能が侵害される可能性があるということです。</span><span class="sxs-lookup"><span data-stu-id="112ff-264">The most serious risk when you use Microsoft BitLocker Administration and Monitoring is that its functionality could be compromised by an unauthorized user who could then reconfigure BitLocker Drive Encryption and gain BitLocker encryption key data on MBAM Clients.</span></span> <span data-ttu-id="112ff-265">ただし、サービス拒否攻撃のために MBAM 機能が短期間で失われても、メールやネットワーク通信の損失、または電源の損失など、通常、重大な影響はありません。</span><span class="sxs-lookup"><span data-stu-id="112ff-265">However, the loss of MBAM functionality for a short period of time, due to a denial-of-service attack, does not generally have a catastrophic impact, unlike, for example, losing e-mail or network communications, or power.</span></span>

<span data-ttu-id="112ff-266">**コンピューターを物理的に保護**します。</span><span class="sxs-lookup"><span data-stu-id="112ff-266">**Physically secure your computers**.</span></span> <span data-ttu-id="112ff-267">物理的なセキュリティがない場合は、セキュリティは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="112ff-267">There is no security without physical security.</span></span> <span data-ttu-id="112ff-268">MBAM サーバーに物理的にアクセスできる攻撃者は、クライアントベース全体を攻撃するためにそれを使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="112ff-268">An attacker who gets physical access to an MBAM Server could potentially use it to attack the entire client base.</span></span> <span data-ttu-id="112ff-269">すべての潜在的な物理的な攻撃は、高リスクと見なされ、適切に軽減する必要があります。</span><span class="sxs-lookup"><span data-stu-id="112ff-269">All potential physical attacks must be considered high risk and mitigated appropriately.</span></span> <span data-ttu-id="112ff-270">MBAM サーバは、アクセスを制御できる安全なサーバールームに保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="112ff-270">MBAM Servers should be stored in a secure server room with controlled access.</span></span> <span data-ttu-id="112ff-271">オペレーティングシステムによってコンピューターがロックされている場合、またはセキュアなスクリーンセーバーを使用している場合は、管理者が物理的に存在しない場合は、これらのコンピューターをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="112ff-271">Secure these computers when administrators are not physically present by having the operating system lock the computer, or by using a secured screen saver.</span></span>

<span data-ttu-id="112ff-272">**すべてのコンピューターに最新のセキュリティ更新プログラムを適用**します。</span><span class="sxs-lookup"><span data-stu-id="112ff-272">**Apply the most recent security updates to all computers**.</span></span> <span data-ttu-id="112ff-273">セキュリティの更新プログラムについて最新情報を入手するには、[セキュリティ TechCenter](https://go.microsoft.com/fwlink/?LinkId=28819)のセキュリティ通知サービスをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="112ff-273">Stay informed about new updates for Windows operating systems, SQL Server, and MBAM by subscribing to the Security Notification service at the [Security TechCenter](https://go.microsoft.com/fwlink/?LinkId=28819).</span></span>

<span data-ttu-id="112ff-274">**強力なパスワードを使用するか、語句を渡し**ます。</span><span class="sxs-lookup"><span data-stu-id="112ff-274">**Use strong passwords or pass phrases**.</span></span> <span data-ttu-id="112ff-275">すべての MBAM 管理者アカウントには、常に15文字以上の強力なパスワードを使用してください。</span><span class="sxs-lookup"><span data-stu-id="112ff-275">Always use strong passwords with 15 or more characters for all MBAM administrator accounts.</span></span> <span data-ttu-id="112ff-276">空のパスワードは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="112ff-276">Never use blank passwords.</span></span> <span data-ttu-id="112ff-277">パスワードの概念の詳細については、「[パスワードポリシー](https://technet.microsoft.com/library/hh994572.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="112ff-277">For more information about password concepts, see [Password Policy](https://technet.microsoft.com/library/hh994572.aspx).</span></span>



## <span data-ttu-id="112ff-278">関連トピック</span><span class="sxs-lookup"><span data-stu-id="112ff-278">Related topics</span></span>


[<span data-ttu-id="112ff-279">MBAM 2.5 の展開計画</span><span class="sxs-lookup"><span data-stu-id="112ff-279">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

 
## <span data-ttu-id="112ff-280">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="112ff-280">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="112ff-281">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="112ff-281">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="112ff-282">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="112ff-282">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





