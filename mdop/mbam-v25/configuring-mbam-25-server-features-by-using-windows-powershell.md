---
title: Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成
description: Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成
author: dansimp
ms.assetid: 826429fd-29bb-44be-b47e-5f5c7d20dd1d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: f350a9eb96a20f50644cfdc1965b7f72741a2c29
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822837"
---
# <span data-ttu-id="4ba77-103">Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="4ba77-103">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span>


<span data-ttu-id="4ba77-104">MBAM 2.5 サーバーソフトウェアをインストールしたら、Windows PowerShell コマンドレットまたは MBAM サーバー構成ウィザードを使用して、MBAM 2.5 サーバー機能の構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4ba77-104">After you install the MBAM 2.5 Server software, you can use configure MBAM 2.5 Server features by using Windows PowerShell cmdlets or the MBAM Server Configuration wizard.</span></span> <span data-ttu-id="4ba77-105">このトピックでは、Windows PowerShell コマンドレットを使用して MBAM 2.5 を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-105">This topic describes how to configure MBAM 2.5 by using the Windows PowerShell cmdlets.</span></span> <span data-ttu-id="4ba77-106">代わりにウィザードを使用するには、「 [MBAM 2.5 サーバー機能を構成](configuring-the-mbam-25-server-features.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ba77-106">To use the wizard instead, see [Configuring the MBAM 2.5 Server Features](configuring-the-mbam-25-server-features.md).</span></span>

## <span data-ttu-id="4ba77-107">このトピックの内容は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4ba77-107">In this topic</span></span>


<span data-ttu-id="4ba77-108">このトピックでは、Windows PowerShell を使用して MBAM を構成する方法について次の情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-108">This topic includes the following information about using Windows PowerShell to configure MBAM:</span></span>

-   [<span data-ttu-id="4ba77-109">MBAM 2.5 の Windows PowerShell ヘルプを読み込む方法</span><span class="sxs-lookup"><span data-stu-id="4ba77-109">How to load Windows PowerShell Help for MBAM 2.5</span></span>](#bkmk-load-posh-help)

-   [<span data-ttu-id="4ba77-110">MBAM Windows PowerShell コマンドレットに関するヘルプを表示する方法</span><span class="sxs-lookup"><span data-stu-id="4ba77-110">How to get Help about an MBAM Windows PowerShell cmdlet</span></span>](#bkmk-help-specific-cmdlet)

-   [<span data-ttu-id="4ba77-111">MBAM サーバー構成ウィザードではなく、Windows PowerShell でのみ実行できる構成</span><span class="sxs-lookup"><span data-stu-id="4ba77-111">Configurations that you can do only with Windows PowerShell but not with the MBAM Server Configuration wizard</span></span>](#bkmk-config-only-posh)

-   [<span data-ttu-id="4ba77-112">Windows PowerShell を使用して MBAM Server 機能を構成するための前提条件と要件</span><span class="sxs-lookup"><span data-stu-id="4ba77-112">Prerequisites and requirements for using Windows PowerShell to configure MBAM Server features</span></span>](#bkmk-prereqs-posh-mbamsvr)

-   [<span data-ttu-id="4ba77-113">Windows PowerShell を使用してリモートコンピューターで MBAM を構成する</span><span class="sxs-lookup"><span data-stu-id="4ba77-113">Using Windows PowerShell to configure MBAM on a remote computer</span></span>](#bkmk-remote-config)

-   [<span data-ttu-id="4ba77-114">必要なアカウントと対応する Windows PowerShell コマンドレットのパラメーター</span><span class="sxs-lookup"><span data-stu-id="4ba77-114">Required accounts and corresponding Windows PowerShell cmdlet parameters</span></span>](#bkmk-reqd-posh-accts)

<span data-ttu-id="4ba77-115">MBAM を管理するために使用される**Get Mbambitlockerrecoveryrecoverykey**と**MbamTPMOwnerPassword** Windows powershell コマンドレットについては、「 [Windows powershell を使用して mbam 2.5 を管理する](using-windows-powershell-to-administer-mbam-25.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ba77-115">For information about the **Get-MbamBitLockerRecoveryKey** and **Get-MbamTPMOwnerPassword** Windows PowerShell cmdlets, which are used to administer MBAM, see [Using Windows PowerShell to Administer MBAM 2.5](using-windows-powershell-to-administer-mbam-25.md).</span></span>

## <a href="" id="bkmk-load-posh-help"></a><span data-ttu-id="4ba77-116">MBAM 2.5 の Windows PowerShell ヘルプを読み込む方法</span><span class="sxs-lookup"><span data-stu-id="4ba77-116">How to load Windows PowerShell Help for MBAM 2.5</span></span>


<span data-ttu-id="4ba77-117">TechNet の Windows PowerShell コマンドレットの一覧については、「 [Windows powershell による Microsoft デスクトップ最適化パックオートメーション](https://go.microsoft.com/fwlink/?LinkId=392816)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ba77-117">For a list of the Windows PowerShell cmdlets on TechNet, see [Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=392816).</span></span>

**<span data-ttu-id="4ba77-118">MBAM サーバーソフトウェアをインストールした後に、Windows PowerShell コマンドレットの MBAM 2.5 ヘルプを読み込むには</span><span class="sxs-lookup"><span data-stu-id="4ba77-118">To load the MBAM 2.5 Help for Windows PowerShell cmdlets after installing the MBAM Server software</span></span>**

1.  <span data-ttu-id="4ba77-119">Windows PowerShell または Windows PowerShell Integrated Scripting Environment (ISE) を開きます。</span><span class="sxs-lookup"><span data-stu-id="4ba77-119">Open Windows PowerShell or Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

2.  <span data-ttu-id="4ba77-120">「**更新プログラム-ヘルプ-モジュール Microsoft MBAM」と**入力します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-120">Type **Update-Help –Module Microsoft.MBAM**.</span></span>

## <a href="" id="bkmk-help-specific-cmdlet"></a><span data-ttu-id="4ba77-121">MBAM Windows PowerShell コマンドレットに関するヘルプを表示する方法</span><span class="sxs-lookup"><span data-stu-id="4ba77-121">How to get Help about an MBAM Windows PowerShell cmdlet</span></span>


<span data-ttu-id="4ba77-122">Windows PowerShell for MBAM のヘルプは、次の形式で使用できます。</span><span class="sxs-lookup"><span data-stu-id="4ba77-122">Windows PowerShell Help for MBAM is available in the following formats:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4ba77-123">Windows PowerShell ヘルプの形式</span><span class="sxs-lookup"><span data-stu-id="4ba77-123">Windows PowerShell Help format</span></span></th>
<th align="left"><span data-ttu-id="4ba77-124">詳細情報</span><span class="sxs-lookup"><span data-stu-id="4ba77-124">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4ba77-125">Windows PowerShell コマンドプロンプトで、「 <strong> Get-ヘルプ </strong> &lt; <em> コマンドレット」と入力します。</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="4ba77-125">At a Windows PowerShell command prompt, type <strong>Get-Help</strong> &lt;<em>cmdlet</em>&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="4ba77-126">最新の Windows PowerShell コマンドレットをアップロードするには、前のセクションの手順に従って、MBAM の Windows PowerShell ヘルプを読み込む方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ba77-126">To upload the latest Windows PowerShell cmdlets, follow the instructions in the previous section on how to load Windows PowerShell Help for MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4ba77-127">Web ページとしての TechNet の場合</span><span class="sxs-lookup"><span data-stu-id="4ba77-127">On TechNet as webpages</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393498" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393498">https://go.microsoft.com/fwlink/?LinkId=393498</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4ba77-128">Word の .docx ファイルとしてダウンロードセンターで</span><span class="sxs-lookup"><span data-stu-id="4ba77-128">On the Download Center as a Word .docx file</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393497" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393497">https://go.microsoft.com/fwlink/?LinkId=393497</a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4ba77-129">.Pdf ファイルとしてダウンロードセンターで</span><span class="sxs-lookup"><span data-stu-id="4ba77-129">On the Download Center as a .pdf file</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393499" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393499">https://go.microsoft.com/fwlink/?LinkId=393499</a></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-config-only-posh"></a><span data-ttu-id="4ba77-130">MBAM サーバー構成ウィザードではなく、Windows PowerShell でのみ実行できる構成</span><span class="sxs-lookup"><span data-stu-id="4ba77-130">Configurations that you can do only with Windows PowerShell but not with the MBAM Server Configuration wizard</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4ba77-131">Windows PowerShell を使用してのみ実行できる構成</span><span class="sxs-lookup"><span data-stu-id="4ba77-131">Configurations that you can do only by using Windows PowerShell</span></span></th>
<th align="left"><span data-ttu-id="4ba77-132">詳細</span><span class="sxs-lookup"><span data-stu-id="4ba77-132">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4ba77-133">Web アプリケーションとは別のコンピューターに web サービスをインストールします。</span><span class="sxs-lookup"><span data-stu-id="4ba77-133">Install the web services on a separate computer from the web applications.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4ba77-134">このウィザードを使用するには、web サービスと web アプリケーションを同じコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba77-134">Using the wizard, you must install the web services and web applications on the same computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4ba77-135">すべての Configuration Manager オブジェクトをインストールせずに、個別のレポートサービスポイントでレポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4ba77-135">Enable reports on a separate reporting services point without installing all of the Configuration Manager objects.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4ba77-136">Configuration Manager からすべてのオブジェクトを削除します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-136">Delete all of the objects from Configuration Manager.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4ba77-137">でオブジェクトを削除すると、Configuration Manager からすべてのコンプライアンスデータが削除されます。</span><span class="sxs-lookup"><span data-stu-id="4ba77-137">Deleting the objects in turn deletes all of the compliance data from Configuration Manager.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4ba77-138">データベースのカスタムの接続文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-138">Enter a custom connection string for the databases.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4ba77-139">例: ミラーリングと連携する web アプリケーションを構成するには、 <strong> MbamWebApplication コマンドレットを使用して、 </strong> 接続文字列に適切なフェールオーバーパートナーの構文を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba77-139">Example: To configure the web applications to work with mirroring, you must use the <strong>Enable-MbamWebApplication</strong> cmdlet to specify the appropriate failover partner syntax in the connection string.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4ba77-140">前提条件の確認が失敗した場合でも、検証をスキップして機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-140">Skip validation and configure a feature even though the prerequisite check failed.</span></span></p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="4ba77-141">**注** Windows PowerShell コマンドレットまたは MBAM サーバー構成ウィザードを使用して、MBAM データベースを無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4ba77-141">**Note** You cannot disable the MBAM databases with a Windows PowerShell cmdlet or the MBAM Server Configuration wizard.</span></span> <span data-ttu-id="4ba77-142">コンプライアンスや監査データが誤って削除されるのを防ぐため、データベース管理者はデータベースを手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba77-142">To prevent the accidental removal of your compliance and audit data, database administrators must remove databases manually.</span></span>

 

## <a href="" id="bkmk-prereqs-posh-mbamsvr"></a><span data-ttu-id="4ba77-143">Windows PowerShell を使用して MBAM Server 機能を構成するための前提条件と要件</span><span class="sxs-lookup"><span data-stu-id="4ba77-143">Prerequisites and requirements for using Windows PowerShell to configure MBAM Server features</span></span>


<span data-ttu-id="4ba77-144">構成を開始する前に、次の前提条件を完了します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-144">Before starting the configuration, complete the following prerequisites.</span></span>

**<span data-ttu-id="4ba77-145">アカウントに関連する前提条件</span><span class="sxs-lookup"><span data-stu-id="4ba77-145">Account-related prerequisites</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4ba77-146">受講</span><span class="sxs-lookup"><span data-stu-id="4ba77-146">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="4ba77-147">詳細情報または追加情報</span><span class="sxs-lookup"><span data-stu-id="4ba77-147">Details or additional information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4ba77-148">必要なアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-148">Create the required accounts.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4ba77-149"><strong>このトピックで後述する「必須アカウント」と「対応する Windows PowerShell コマンドレット」のパラメーターを参照してください </strong> 。</span><span class="sxs-lookup"><span data-stu-id="4ba77-149">See section <strong>Required accounts and corresponding Windows PowerShell cmdlet parameters</strong> later in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4ba77-150">Windows PowerShell コマンドレットにパラメーターとして渡すユーザーアカウントとグループは、ドメイン内の有効なアカウントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba77-150">User accounts and groups that you pass as parameters to the Windows PowerShell cmdlets must be valid accounts in the domain.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4ba77-151">ローカルアカウントは使用できません。</span><span class="sxs-lookup"><span data-stu-id="4ba77-151">You cannot use local accounts.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4ba77-152">下位レベルの形式でアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-152">Specify accounts in the down-level format.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4ba77-153">例:</span><span class="sxs-lookup"><span data-stu-id="4ba77-153">Examples:</span></span></p>
<p><span data-ttu-id="4ba77-154">domainNetBiosName\userdomainNetBiosName\group</span><span class="sxs-lookup"><span data-stu-id="4ba77-154">domainNetBiosName\userdomainNetBiosName\group</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="4ba77-155">権限に関連する前提条件</span><span class="sxs-lookup"><span data-stu-id="4ba77-155">Permission-related prerequisites</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4ba77-156">受講</span><span class="sxs-lookup"><span data-stu-id="4ba77-156">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="4ba77-157">詳細情報または追加情報</span><span class="sxs-lookup"><span data-stu-id="4ba77-157">Details or additional information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4ba77-158">MBAM 機能を構成するローカルコンピューターの管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba77-158">You must be an administrator on the local computer where you are configuring the MBAM feature.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4ba77-159">昇格された Windows PowerShell コマンドプロンプトを使用して、すべての Windows PowerShell コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-159">Use an elevated Windows PowerShell command prompt to run all Windows PowerShell cmdlets.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4ba77-160"><strong>Mbamamdatabase </strong> コマンドレットの場合のみ、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4ba77-160">For the <strong>Enable-MbamDatabase</strong> cmdlet only:</span></span></p>
<p><span data-ttu-id="4ba77-161">&quot; &quot; ターゲットの Microsoft SQL Server データベースのインスタンスに対してデータベースの権限を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba77-161">You must have &quot;create any database&quot; permissions on the instance of the target Microsoft SQL Server database.</span></span></p>
<p><span data-ttu-id="4ba77-162">このユーザーアカウントは、MBAM ボリュームシャドウコピーサービス (VSS) ライターを登録するために、ローカル管理者グループまたは Backup Operators グループの一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba77-162">This user account must be a part of the local administrators group or the Backup Operators group to register the MBAM Volume Shadow Copy Service (VSS) Writer.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4ba77-163">既定では、データベース管理者またはシステム管理者が、必要なデータベース権限を作成する必要があり &quot; &quot; ます。</span><span class="sxs-lookup"><span data-stu-id="4ba77-163">By default, the database administrator or system administrator has the required &quot;create any database&quot; permissions.</span></span></p>
<p></p>
<p><span data-ttu-id="4ba77-164">VSS Writer の詳細については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=392814" data-raw-source="[Volume Shadow Copy Service](https://go.microsoft.com/fwlink/?LinkId=392814)"> ボリュームシャドウコピーサービス」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="4ba77-164">For more information about VSS Writer, see <a href="https://go.microsoft.com/fwlink/?LinkId=392814" data-raw-source="[Volume Shadow Copy Service](https://go.microsoft.com/fwlink/?LinkId=392814)">Volume Shadow Copy Service</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4ba77-165"><strong>System Center Configuration Manager の統合 </strong> 機能のみ:</span><span class="sxs-lookup"><span data-stu-id="4ba77-165">For the <strong>System Center Configuration Manager Integration</strong> feature only:</span></span></p>
<p><span data-ttu-id="4ba77-166">この機能を有効にするユーザーは、構成マネージャーで次の権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba77-166">The user who enables this feature must have these rights in Configuration Manager:</span></span></p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4ba77-167">構成マネージャーでの権限の種類</span><span class="sxs-lookup"><span data-stu-id="4ba77-167">Type of rights in Configuration Manager</span></span></th>
<th align="left"><span data-ttu-id="4ba77-168">必要な権利</span><span class="sxs-lookup"><span data-stu-id="4ba77-168">Required rights</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4ba77-169">Configuration Manager サイトの権限:</span><span class="sxs-lookup"><span data-stu-id="4ba77-169">Configuration Manager Site rights:</span></span></p></td>
<td align="left"><p>- <span data-ttu-id="4ba77-170">Read</span><span class="sxs-lookup"><span data-stu-id="4ba77-170">Read</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4ba77-171">Configuration Manager のコレクションの権限:</span><span class="sxs-lookup"><span data-stu-id="4ba77-171">Configuration Manager Collection rights:</span></span></p></td>
<td align="left"><p>- <span data-ttu-id="4ba77-172">作成-削除-読み取り-修正-構成アイテムの展開</span><span class="sxs-lookup"><span data-stu-id="4ba77-172">Create- Delete- Read- Modify- Deploy Configuration Items</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4ba77-173">Configuration Manager 構成アイテムの権限:</span><span class="sxs-lookup"><span data-stu-id="4ba77-173">Configuration Manager Configuration item rights:</span></span></p></td>
<td align="left"><p>- <span data-ttu-id="4ba77-174">作成-削除-読み取り</span><span class="sxs-lookup"><span data-stu-id="4ba77-174">Create- Delete- Read</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p>
<p></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-remote-config"></a><span data-ttu-id="4ba77-175">Windows PowerShell を使用してリモートコンピューターで MBAM を構成する</span><span class="sxs-lookup"><span data-stu-id="4ba77-175">Using Windows PowerShell to configure MBAM on a remote computer</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="4ba77-176">この機能を使用する状況</span><span class="sxs-lookup"><span data-stu-id="4ba77-176">When to use this capability</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4ba77-177">リモートコンピューターで MBAM 2.5 サーバー機能を構成する場合。</span><span class="sxs-lookup"><span data-stu-id="4ba77-177">When you want to configure the MBAM 2.5 Server features on a remote computer.</span></span> <span data-ttu-id="4ba77-178">Windows PowerShell コマンドレットが1台のコンピューターで実行されていて、別のリモートコンピューターで機能を構成している。</span><span class="sxs-lookup"><span data-stu-id="4ba77-178">The Windows PowerShell cmdlets are running on one computer, and you are configuring the features on a different, remote computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="4ba77-179">必要な作業</span><span class="sxs-lookup"><span data-stu-id="4ba77-179">What you have to do</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4ba77-180">Windows PowerShell を使用して、リモートコンピューターで MBAM 2.5 サーバー機能を構成するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba77-180">To use Windows PowerShell to configure MBAM 2.5 Server features on a remote computer, you must:</span></span></p>
<ul>
<li><p><span data-ttu-id="4ba77-181">MBAM 2.5 サーバーソフトウェアがリモートコンピューターにインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-181">Ensure that the MBAM 2.5 Server software has been installed on the remote computer.</span></span></p></li>
<li><p><span data-ttu-id="4ba77-182">資格情報セキュリティサポートプロバイダー (CredSSP) プロトコルを使用して、Windows PowerShell セッションを開きます。</span><span class="sxs-lookup"><span data-stu-id="4ba77-182">Use the Credential Security Support Provider (CredSSP) Protocol to open the Windows PowerShell session.</span></span></p></li>
<li><p><span data-ttu-id="4ba77-183">Windows リモート管理 (WinRM) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="4ba77-183">Enable Windows Remote Management (WinRM).</span></span> <span data-ttu-id="4ba77-184">WinRM を有効にして正しく構成できない場合は、 <strong> </strong> この表に記載されている新しい PSSession コマンドレットでエラーが表示され、問題を解決する方法が示されます。</span><span class="sxs-lookup"><span data-stu-id="4ba77-184">If you fail to enable WinRM and to configure it correctly, the <strong>New-PSSession</strong> cmdlet that is described in this table displays an error and describes how to fix the issue.</span></span> <span data-ttu-id="4ba77-185">WinRM の詳細については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=393064" data-raw-source="[Using Windows Remote Management](https://go.microsoft.com/fwlink/?LinkId=393064)"> Windows リモート管理の使用」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="4ba77-185">For more information about WinRM, see <a href="https://go.microsoft.com/fwlink/?LinkId=393064" data-raw-source="[Using Windows Remote Management](https://go.microsoft.com/fwlink/?LinkId=393064)">Using Windows Remote Management</a>.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="4ba77-186">必要な理由</span><span class="sxs-lookup"><span data-stu-id="4ba77-186">Why you have to do it</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4ba77-187">このプロトコルでは、Windows PowerShell コマンドレットを使用して、ユーザーの管理資格情報を使用して Active Directory ドメインサービスに接続することができます。</span><span class="sxs-lookup"><span data-stu-id="4ba77-187">This protocol enables the Windows PowerShell cmdlets to connect to Active Directory Domain Services by using the user’s administrative credentials.</span></span> <span data-ttu-id="4ba77-188">このプロトコルを使わずに Windows PowerShell セッションを開始すると、検証エラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="4ba77-188">You might get a validation error if you start the Windows PowerShell session without this protocol.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="4ba77-189">CredSSP プロトコルを使用して Windows PowerShell セッションを開始する方法</span><span class="sxs-lookup"><span data-stu-id="4ba77-189">How to start a Windows PowerShell session with the CredSSP protocol</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4ba77-190">Windows PowerShell のプロンプトで、次のコードを入力します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-190">Type the following code at the Windows PowerShell prompt:</span></span></p>
<p><code>$s = New-PSSession -ComputerName xxx -Authentication Credssp -Credential xxx</code></p>
<p><span data-ttu-id="4ba77-191">次のコードに例を示します </span><span class="sxs-lookup"><span data-stu-id="4ba77-191">The following code shows an example.</span></span></p>
<p><code>$session = New-PSSession -ComputerName &lt;MBAM_server_name&gt; -Authentication Credssp -Credential (Get-Credential)</code></p>
<p><code>Enter-PSSession $session</code></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-reqd-posh-accts"></a><span data-ttu-id="4ba77-192">必要なアカウントと対応する Windows PowerShell コマンドレットのパラメーター</span><span class="sxs-lookup"><span data-stu-id="4ba77-192">Required accounts and corresponding Windows PowerShell cmdlet parameters</span></span>


<span data-ttu-id="4ba77-193">次の表では、MBAM 2.5 サーバーの機能を構成するために必要なアカウントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-193">The following table describes the accounts that are required to configure MBAM 2.5 Server features.</span></span> <span data-ttu-id="4ba77-194">また、構成時にアカウントを指定する必要がある、対応する Windows PowerShell コマンドレットとパラメーターも一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="4ba77-194">It also lists the corresponding Windows PowerShell cmdlet and parameter for which you have to specify the account during configuration.</span></span>

<span data-ttu-id="4ba77-195">コマンドレットパラメーターの種類 (ユーザーまたはグループ) 説明を有効にする-MBAMDatabase</span><span class="sxs-lookup"><span data-stu-id="4ba77-195">Cmdlet Parameter Type (User or Group) Description Enable-MBAMDatabase</span></span>

<span data-ttu-id="4ba77-196">AccessAccount</span><span class="sxs-lookup"><span data-stu-id="4ba77-196">AccessAccount</span></span>

<span data-ttu-id="4ba77-197">ユーザーまたはグループ</span><span class="sxs-lookup"><span data-stu-id="4ba77-197">User or Group</span></span>

<span data-ttu-id="4ba77-198">このデータベースの読み取り/書き込みアクセス許可を持つドメインユーザーまたはグループを指定して、web アプリケーションがこのデータベース内のデータやレポートにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="4ba77-198">Specify a domain user or group that has read/write permission to this database to give the web applications access to data and reports in this database.</span></span> <span data-ttu-id="4ba77-199">この値がドメインユーザーの場合は、 **MbamWebApplication**コマンドレットを実行するときに使用される**Webserviceapplicationpoolcredential**パラメーターは、同じユーザーアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba77-199">If the value is a domain user, then the **WebServiceApplicationPoolCredential** parameter that is used when running the **Enable-MbamWebApplication** cmdlet must use the same user account.</span></span> <span data-ttu-id="4ba77-200">値が domain Users グループの場合、 **Webserviceapplicationpoolcredential**パラメーターで使われるドメインアカウントは、このグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba77-200">If the value is a domain Users group, then the domain account that is used by the **WebServiceApplicationPoolCredential** parameter must be a member of this group.</span></span>

<span data-ttu-id="4ba77-201">ReportAccount</span><span class="sxs-lookup"><span data-stu-id="4ba77-201">ReportAccount</span></span>

<span data-ttu-id="4ba77-202">ユーザーまたはグループ</span><span class="sxs-lookup"><span data-stu-id="4ba77-202">User or Group</span></span>

<span data-ttu-id="4ba77-203">このデータベースに読み取り専用のアクセス許可を持つドメインユーザーまたはユーザーグループを指定して、MBAM レポートでコンプライアンスデータと監査データへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-203">Specify a domain user or Users group that has read-only permission to this database to provide the MBAM reports access to the compliance and audit data.</span></span> <span data-ttu-id="4ba77-204">値がドメインユーザーの場合**は、ComplianceAndAuditDBCredential パラメーターコマンドレット**の**ComplianceAndAuditDBCredential**パラメーターに同じユーザーアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba77-204">If the value is a domain user, then the **ComplianceAndAuditDBCredential** parameter of the **Enable-MbamReport** cmdlet must use the same user account.</span></span> <span data-ttu-id="4ba77-205">値が domain Users グループの場合は、 **ComplianceAndAuditDBCredential**パラメーターで使われるドメインアカウントがこのグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba77-205">If the value is a domain Users group, then the domain account that is used by the **ComplianceAndAuditDBCredential** parameter must be a member of this group.</span></span>

<span data-ttu-id="4ba77-206">-MbamReport を有効にする</span><span class="sxs-lookup"><span data-stu-id="4ba77-206">Enable-MbamReport</span></span>

<span data-ttu-id="4ba77-207">ComplianceAndAuditDBCredential</span><span class="sxs-lookup"><span data-stu-id="4ba77-207">ComplianceAndAuditDBCredential</span></span>

<span data-ttu-id="4ba77-208">ユーザー</span><span class="sxs-lookup"><span data-stu-id="4ba77-208">User</span></span>

<span data-ttu-id="4ba77-209">MBAM コンプライアンスおよび監査データベースに接続するためにローカルの SSRS インスタンスで使用される管理資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-209">Specifies the administrative credential that the local SSRS instance uses to connect to the MBAM Compliance and Audit Database.</span></span> <span data-ttu-id="4ba77-210">管理資格情報のドメインユーザーは、 **reportaccount**パラメーターとして使用されるユーザーアカウントと同じである必要があります。これは、 **mbamdatabase**コマンドレットを実行しているときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4ba77-210">The domain user in the administrative credential must be the same as the user account that is used for the **ReportAccount** parameter, which is used while running the **Enable-MbamDatabase** cmdlet.</span></span> <span data-ttu-id="4ba77-211">**Reportaccount**パラメーターで domain Users グループを使用した場合は、このアカウントがそのグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba77-211">If a domain Users group was used with the **ReportAccount** parameter, this account should be a member of that group.</span></span>

<span data-ttu-id="4ba77-212">**重要** 管理資格情報で指定されたアカウントは、セキュリティを強化するためのユーザー権限を制限している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba77-212">**Important** The account specified in the administrative credentials should have limited user rights for improved security.</span></span> <span data-ttu-id="4ba77-213">また、アカウントのパスワードを無期限に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba77-213">Also, the password of the account should be set to not expire.</span></span>

 

<span data-ttu-id="4ba77-214">ReportsReadOnlyAccessGroup</span><span class="sxs-lookup"><span data-stu-id="4ba77-214">ReportsReadOnlyAccessGroup</span></span>

<span data-ttu-id="4ba77-215">Group</span><span class="sxs-lookup"><span data-stu-id="4ba77-215">Group</span></span>

<span data-ttu-id="4ba77-216">レポートの読み取りアクセス許可を持つドメインユーザーグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-216">Specifies the domain user group that has read permissions to the reports.</span></span> <span data-ttu-id="4ba77-217">指定したグループは、 **ReportsReadOnlyAccessGroup** **パラメーターに使用**されているグループと同じグループである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba77-217">The specified group must be the same group that is used for the **ReportsReadOnlyAccessGroup** parameter in the **Enable-MbamWebApplication** cmdlet.</span></span>

<span data-ttu-id="4ba77-218">Enable-MBAMWebApplication</span><span class="sxs-lookup"><span data-stu-id="4ba77-218">Enable-MBAMWebApplication</span></span>

<span data-ttu-id="4ba77-219">Advanced Helpデスク Accessgroup</span><span class="sxs-lookup"><span data-stu-id="4ba77-219">AdvancedHelpdeskAccessGroup</span></span>

<span data-ttu-id="4ba77-220">Group</span><span class="sxs-lookup"><span data-stu-id="4ba77-220">Group</span></span>

<span data-ttu-id="4ba77-221">[レポート] 領域以外の、管理および監視 Web サイトのすべての領域にアクセスできる domain Users グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-221">Specifies the domain Users group that has access to all areas of the Administration and Monitoring Website except the Reports area.</span></span>

<span data-ttu-id="4ba77-222">Helpデスク Accessgroup</span><span class="sxs-lookup"><span data-stu-id="4ba77-222">HelpdeskAccessGroup</span></span>

<span data-ttu-id="4ba77-223">Group</span><span class="sxs-lookup"><span data-stu-id="4ba77-223">Group</span></span>

<span data-ttu-id="4ba77-224">管理と監視の Web サイトの TPM および**ドライブ回復**領域の**管理**にアクセスできる domain Users グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-224">Specifies the domain Users group that has access to the **Manage TPM** and **Drive Recovery** areas of the Administration and Monitoring Website.</span></span>

<span data-ttu-id="4ba77-225">ReportsReadOnlyAccessGroup</span><span class="sxs-lookup"><span data-stu-id="4ba77-225">ReportsReadOnlyAccessGroup</span></span>

<span data-ttu-id="4ba77-226">Group</span><span class="sxs-lookup"><span data-stu-id="4ba77-226">Group</span></span>

<span data-ttu-id="4ba77-227">管理および監視 Web サイトの [**レポート**] 領域に対する読み取りアクセス許可を持つ domain Users グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-227">Specifies the domain Users group that has read permission to the **Reports** area of the Administration and Monitoring Website.</span></span> <span data-ttu-id="4ba77-228">指定したグループ**は、ReportsReadOnlyAccessGroup パラメーターコマンドレット**の**ReportsReadOnlyAccessGroup**パラメーターと同じグループである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba77-228">The specified group must be the same group that is used for the **ReportsReadOnlyAccessGroup** parameter in the **Enable-MbamReport** cmdlet.</span></span>

<span data-ttu-id="4ba77-229">WebServiceApplicationPoolCredential</span><span class="sxs-lookup"><span data-stu-id="4ba77-229">WebServiceApplicationPoolCredential</span></span>

<span data-ttu-id="4ba77-230">ユーザー</span><span class="sxs-lookup"><span data-stu-id="4ba77-230">User</span></span>

<span data-ttu-id="4ba77-231">MBAM web アプリケーションのアプリケーションプールによって使用されるドメインユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-231">Specifies the domain user to be used by the application pool for the MBAM web applications.</span></span> <span data-ttu-id="4ba77-232">これは、 **MbamDatabase**コマンドレットの**accessaccount**パラメーターで指定されているものと同じドメインユーザーアカウントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba77-232">It must be the same domain user account that is specified in the **AccessAccount** parameter of the **Enable-MbamDatabase** cmdlet.</span></span> <span data-ttu-id="4ba77-233">**Enable-MbamDatabase**コマンドレットを実行しているときに、 **accessaccount**パラメーターによって domain Users グループが使用されていた場合、ここで指定されたドメインユーザーはそのグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba77-233">If a domain Users group was used by the **AccessAccount** parameter when running the **Enable-MbamDatabase** cmdlet, the domain user that is specified here must be a member of that group.</span></span> <span data-ttu-id="4ba77-234">管理者の資格情報を指定しない場合は、以前に有効になっていた web アプリケーションで指定された管理資格情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="4ba77-234">If you do not specify the administrative credentials, the administrative credentials that were specified by any previously enabled web application are used.</span></span> <span data-ttu-id="4ba77-235">すべての web アプリケーションで同じアプリケーションプール id が使用されます。</span><span class="sxs-lookup"><span data-stu-id="4ba77-235">All of the web applications use the same application pool identity.</span></span> <span data-ttu-id="4ba77-236">複数回指定すると、最後に指定した値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="4ba77-236">If it is specified multiple times, the most recently specified value is used.</span></span>

<span data-ttu-id="4ba77-237">**重要** セキュリティを向上させるには、管理者の資格情報で指定されているアカウントを制限付きのユーザー権限に設定します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-237">**Important** For improved security, set the account that is specified in the administrative credentials to limited user rights.</span></span> <span data-ttu-id="4ba77-238">また、アカウントのパスワードを無期限に設定します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-238">Also, set the password of the account to never expire.</span></span> <span data-ttu-id="4ba77-239">組み込みの IIS \ _IUSRS アカウント、または**Webserviceapplicationpoolcredential**パラメーターとして使用されているアカウントが、[**認証後にクライアントを偽装**] のローカルセキュリティ設定に追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-239">Ensure that either the built-in IIS\_IUSRS account or the account that is used for the **WebServiceApplicationPoolCredential** parameter has been added to the **Impersonate a client after authentication** local security setting.</span></span>

<span data-ttu-id="4ba77-240">ローカルセキュリティ設定を表示するには、**ローカルセキュリティポリシーエディター**を開き、[**ローカルポリシー** ] ノードを展開し、[**ユーザー権利の割り当て**] ノードを選びます。次に、[**認証後にクライアントを偽装**] グループポリシー設定をダブルクリック**して、** 詳細ウィンドウに表示します。</span><span class="sxs-lookup"><span data-stu-id="4ba77-240">To view the local security setting, open the **Local Security Policy editor**, expand the **Local Policies** node, select the **User Rights Assignment** node, and then double-click the **Impersonate a client after authentication** and **Log on as a batch job** Group Policy settings in the details pane.</span></span>

 

 




## <span data-ttu-id="4ba77-241">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4ba77-241">Related topics</span></span>


[<span data-ttu-id="4ba77-242">MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="4ba77-242">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)

[<span data-ttu-id="4ba77-243">MBAM 2.5 サーバー機能の構成の確認</span><span class="sxs-lookup"><span data-stu-id="4ba77-243">Validating the MBAM 2.5 Server Feature Configuration</span></span>](validating-the-mbam-25-server-feature-configuration.md)

[<span data-ttu-id="4ba77-244">Windows PowerShell を使用した MBAM 2.5 の管理</span><span class="sxs-lookup"><span data-stu-id="4ba77-244">Using Windows PowerShell to Administer MBAM 2.5</span></span>](using-windows-powershell-to-administer-mbam-25.md)

 
## <span data-ttu-id="4ba77-245">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="4ba77-245">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="4ba77-246">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="4ba77-246">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="4ba77-247">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="4ba77-247">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





