---
title: MBAM 1.0 グループ ポリシー要件の計画
description: MBAM 1.0 グループ ポリシー要件の計画
author: dansimp
ms.assetid: 0fc9c509-7850-4a8e-bb82-b949025bcb02
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f5061748107dc1d00baa41188b8cf240ec187317
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812435"
---
# <span data-ttu-id="2f9ed-103">MBAM 1.0 グループ ポリシー要件の計画</span><span class="sxs-lookup"><span data-stu-id="2f9ed-103">Planning for MBAM 1.0 Group Policy Requirements</span></span>


<span data-ttu-id="2f9ed-104">Microsoft BitLocker 管理および監視 (MBAM) クライアント管理では、カスタムグループポリシー設定を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-104">Microsoft BitLocker Administration and Monitoring (MBAM) Client management requires custom Group Policy settings to be applied.</span></span> <span data-ttu-id="2f9ed-105">このトピックでは、MBAM を使って企業の BitLocker ドライブ暗号化を管理する場合に、グループポリシーオブジェクト (GPO) に使用できるポリシーオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-105">This topic describes the available policy options for Group Policy Object (GPO) when you use MBAM to manage BitLocker Drive Encryption in the enterprise.</span></span>

**<span data-ttu-id="2f9ed-106">重要</span><span class="sxs-lookup"><span data-stu-id="2f9ed-106">Important</span></span>**  
<span data-ttu-id="2f9ed-107">MBAM は、Windows BitLocker ドライブ暗号化の既定の GPO 設定を使いません。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-107">MBAM does not use the default GPO settings for Windows BitLocker drive encryption.</span></span> <span data-ttu-id="2f9ed-108">既定の設定が有効になっている場合、競合する動作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-108">If the default settings are enabled, they can cause conflicting behavior.</span></span> <span data-ttu-id="2f9ed-109">MBAM を有効にするには、MBAM グループポリシーテンプレートをインストールした後で、GPO ポリシー設定を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-109">To enable MBAM to manage BitLocker, you must define the GPO policy settings after you install the MBAM Group Policy Template.</span></span>



<span data-ttu-id="2f9ed-110">MBAM グループポリシーテンプレートをインストールした後、MBAM がエンタープライズ BitLocker 暗号化を管理できるようにする、使用可能なカスタム MBAM GPO ポリシー設定を表示して変更することができます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-110">After you install the MBAM Group Policy template, you can view and modify the available custom MBAM GPO policy settings that enable MBAM to manage the enterprise BitLocker encryption.</span></span> <span data-ttu-id="2f9ed-111">MBAM グループポリシーテンプレートは、グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) の MDOP 技術を実行できるコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-111">The MBAM Group Policy template must be installed on a computer that is capable of running the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) MDOP technology.</span></span> <span data-ttu-id="2f9ed-112">次に、該当する gpo を編集するには、GPMC または AGPM を開き、次の gpo ノードに移動します。**コンピューターの構成** \\ **管理用テンプレート** \\ **Windows コンポーネント** \\ **MDOP mbam (BitLocker 管理)**。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-112">Next, to edit the applicable GPO, open the GPMC or AGPM, and then navigate to the following GPO node: **Computer Configuration**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)**.</span></span>

<span data-ttu-id="2f9ed-113">MDOP MBAM (BitLocker Management) GPO ノードには、4つのグローバルポリシー設定と4つの子 GPO 設定ノードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-113">The MDOP MBAM (BitLocker Management) GPO node contains four global policy settings and four child GPO setting nodes, respectively.</span></span> <span data-ttu-id="2f9ed-114">4つの GPO グローバルポリシー設定は、クライアント管理、固定ドライブ、オペレーティングシステムドライブ、およびリムーバブルドライブです。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-114">The four GPO global policy settings are: Client Management, Fixed Drive, Operating System Drive, and Removable Drive.</span></span> <span data-ttu-id="2f9ed-115">以下のセクションでは、MBAM GPO ポリシー設定要件の計画に役立つポリシー定義と推奨されるポリシー設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-115">The following sections provide policy definitions and suggested policy settings to help you plan for the MBAM GPO policy setting requirements.</span></span>

**<span data-ttu-id="2f9ed-116">注</span><span class="sxs-lookup"><span data-stu-id="2f9ed-116">Note</span></span>**  
<span data-ttu-id="2f9ed-117">BitLocker 暗号化の管理を可能にする GPO の推奨設定の最小値の構成の詳細については、「 [mbam 1.0 GPO 設定を編集する方法](how-to-edit-mbam-10-gpo-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-117">For more information about configuring the minimum suggested GPO settings to enable MBAM to manage BitLocker encryption, see [How to Edit MBAM 1.0 GPO Settings](how-to-edit-mbam-10-gpo-settings.md).</span></span>



## <span data-ttu-id="2f9ed-118">グローバルポリシー定義</span><span class="sxs-lookup"><span data-stu-id="2f9ed-118">Global policy definitions</span></span>


<span data-ttu-id="2f9ed-119">このセクションでは、mbam グローバルポリシー定義について説明します。これは、**コンピューター構成** \\ **管理用テンプレート** \\ **Windows コンポーネント**の \\ **MDOP mbam (BitLocker 管理)** が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-119">This section describes the MBAM Global policy definitions, which can be found at the following GPO node: **Computer Configuration**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2f9ed-120">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="2f9ed-120">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="2f9ed-121">概要と推奨されるポリシー設定</span><span class="sxs-lookup"><span data-stu-id="2f9ed-121">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2f9ed-122">ドライブの暗号化方法と暗号強度を選ぶ</span><span class="sxs-lookup"><span data-stu-id="2f9ed-122">Choose drive encryption method and cipher strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f9ed-123">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="2f9ed-123">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="2f9ed-124">特定の暗号化方法と暗号強度を使用するように、このポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-124">Configure this policy to use a specific encryption method and cipher strength.</span></span></p>
<p><span data-ttu-id="2f9ed-125">このポリシーが構成されていない場合、BitLocker では、AES 128 ビットとディフューザーの既定の暗号化方法、またはセットアップスクリプトで指定された暗号化メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-125">When this policy is not configured, BitLocker uses the default encryption method of AES 128-bit with Diffuser or the encryption method specified by the setup script.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2f9ed-126">再起動時にメモリの上書きを防止する</span><span class="sxs-lookup"><span data-stu-id="2f9ed-126">Prevent memory overwrite on restart</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f9ed-127">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="2f9ed-127">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="2f9ed-128">このポリシーを構成して、再起動時にメモリ内の BitLocker シークレットを上書きせずに、再起動のパフォーマンスを向上させます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-128">Configure this policy to improve restart performance without overwriting BitLocker secrets in memory on restart.</span></span></p>
<p><span data-ttu-id="2f9ed-129">このポリシーが構成されていない場合、コンピューターを再起動すると、BitLocker シークレットがメモリから削除されます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-129">When this policy is not configured, BitLocker secrets are removed from memory when the computer restarts.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2f9ed-130">スマートカード証明書の使用規則を検証する</span><span class="sxs-lookup"><span data-stu-id="2f9ed-130">Validate smart card certificate usage rule</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f9ed-131">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="2f9ed-131">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="2f9ed-132">スマートカード証明書ベースの BitLocker 保護を使用するように、このポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-132">Configure this policy to use smartcard certificate-based BitLocker protection.</span></span></p>
<p><span data-ttu-id="2f9ed-133">このポリシーが構成されていない場合、証明書の指定には既定のオブジェクト識別子1.3.6.1.4.1.311.67.1.1 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-133">When this policy is not configured, a default object identifier 1.3.6.1.4.1.311.67.1.1 is used to specify a certificate.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2f9ed-134">組織固有の識別子を指定する</span><span class="sxs-lookup"><span data-stu-id="2f9ed-134">Provide the unique identifiers for your organization</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f9ed-135">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="2f9ed-135">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="2f9ed-136">証明書ベースのデータ回復エージェントまたは BitLocker To Go リーダーを使用するように、このポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-136">Configure this policy to use a certificate-based data recovery agent or the BitLocker To Go reader.</span></span></p>
<p><span data-ttu-id="2f9ed-137">このポリシーが構成されていない場合、[ <strong> id </strong> ] フィールドは使用されません。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-137">When this policy is not configured, the <strong>Identification</strong> field is not used.</span></span></p>
<p><span data-ttu-id="2f9ed-138">会社でより高いセキュリティの測定が必要な場合は、[id] フィールドを構成して、 <strong> </strong> すべての USB デバイスでこのフィールドセットが設定され、このフィールドがこのグループポリシー設定に合わせて調整されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-138">If your company requires higher security measurements, you may want to configure the <strong>Identification</strong> field to make sure that all USB devices have this field set and that they are aligned with this Group Policy setting.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="2f9ed-139">クライアント管理ポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="2f9ed-139">Client Management policy definitions</span></span>


<span data-ttu-id="2f9ed-140">このセクションでは、mbam のクライアント管理ポリシー定義について説明します。**コンピューター構成** \\ **管理用テンプレート** \\ **Windows コンポーネント** \\ **MDOP mbam (BitLocker 管理)**  \\  **クライアント管理**。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-140">This section describes the Client Management policy definitions for MBAM, found at the following GPO node: **Computer Configuration**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)** \\ **Client Management**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2f9ed-141">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="2f9ed-141">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="2f9ed-142">概要と推奨されるポリシー設定</span><span class="sxs-lookup"><span data-stu-id="2f9ed-142">Overview and Suggested Policy Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2f9ed-143">MBAM サービスを設定する</span><span class="sxs-lookup"><span data-stu-id="2f9ed-143">Configure MBAM Services</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f9ed-144">推奨される構成: <strong> 有効</span><span class="sxs-lookup"><span data-stu-id="2f9ed-144">Suggested Configuration: <strong>Enabled</span></span></strong></p>
<ul>
<li><p><strong><span data-ttu-id="2f9ed-145">MBAM Recovery and Hardware service endpoint </strong> 。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-145">MBAM Recovery and Hardware service endpoint</strong>.</span></span> <span data-ttu-id="2f9ed-146">これは、MBAM クライアント BitLocker 暗号化管理を有効にするために構成する必要がある最初のポリシー設定です。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-146">This is the first policy setting that you must configure to enable the MBAM Client BitLocker encryption management.</span></span> <span data-ttu-id="2f9ed-147">この設定では、次の例のようなエンドポイントの場所を入力します。 <strong> http:// </strong><em> &lt; mbam 管理と監視サーバー名 &gt; </em><strong> : </strong><em> &lt; web サービスは/MBAMRecoveryAndHardwareService/CoreService.svc にバインドされてい &gt; </em><strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-147">For this setting, enter the endpoint location similar to the following example: <strong>http://</strong><em>&lt;MBAM Administration and Monitoring Server Name&gt;</em><strong>:</strong><em>&lt;port the web service is bound to&gt;</em><strong>/MBAMRecoveryAndHardwareService/CoreService.svc</strong>.</span></span></p></li>
<li><p><strong><span data-ttu-id="2f9ed-148">保存する BitLocker 回復情報を選択し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-148">Select BitLocker recovery information to store</strong>.</span></span> <span data-ttu-id="2f9ed-149">このポリシー設定では、BitLocker 回復情報をバックアップするためのキー回復サービスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-149">This policy setting lets you configure the key recovery service to back up the BitLocker recovery information.</span></span> <span data-ttu-id="2f9ed-150">また、コンプライアンスと監査レポートを収集するためのステータスレポートサービスを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-150">It also lets you configure the status reporting service for collecting compliance and audit reports.</span></span> <span data-ttu-id="2f9ed-151">このポリシーには、重要な情報がないためにデータの損失を防ぐために、BitLocker によって暗号化されたデータを回復する管理方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-151">The policy provides an administrative method of recovering data encrypted by BitLocker to help prevent data loss due to the lack of key information.</span></span> <span data-ttu-id="2f9ed-152">状態レポートとキー回復アクティビティは、自動的に、構成済みレポートサーバーの場所に送信されます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-152">Status report and key recovery activity will automatically and silently be sent to the configured report server location.</span></span></p>
<p><span data-ttu-id="2f9ed-153">構成しなかった場合、またはこのポリシー設定を無効にした場合、キーの回復情報は保存されず、ステータスレポートとキーの回復アクティビティはサーバーに報告されません。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-153">If you do not configure or if you disable this policy setting, the key recovery information will not be saved, and status report and key recovery activity will not be reported to server.</span></span> <span data-ttu-id="2f9ed-154">この設定を <strong> [回復パスワードとキーパッケージ] に設定すると、 </strong> 回復パスワードとキーパッケージは、構成済みのキー回復サーバーの場所に自動的にバックアップされます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-154">When this setting is set to <strong>Recovery Password and key package</strong>, the recovery password and key package will be automatically and silently backed up to the configured key recovery server location.</span></span></p></li>
<li><p><strong><span data-ttu-id="2f9ed-155">クライアントチェックの状態の頻度を分単位で入力し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-155">Enter the client checking status frequency in minutes</strong>.</span></span> <span data-ttu-id="2f9ed-156">このポリシー設定は、クライアントが BitLocker 保護ポリシーとクライアントコンピューターの状態を確認する頻度を管理します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-156">This policy setting manages how frequently the client checks the BitLocker protection policies and the status on the client computer.</span></span> <span data-ttu-id="2f9ed-157">このポリシーは、クライアントのコンプライアンスの状態をサーバーに保存する頻度も管理します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-157">This policy also manages how frequently the client compliance status is saved to the server.</span></span> <span data-ttu-id="2f9ed-158">クライアントは、クライアントコンピューター上の BitLocker 保護ポリシーと状態を確認し、構成された頻度でクライアント回復キーもバックアップします。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-158">The client checks the BitLocker protection policies and status on the client computer, and it also backs up the client recovery key at the configured frequency.</span></span></p>
<p><span data-ttu-id="2f9ed-159">コンピューターのコンプライアンスの状態を確認する頻度と、クライアント回復キーをバックアップする頻度について、会社が確立した要件に基づいてこの頻度を設定します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-159">Set this frequency based on the requirement established by your company on how frequently to check the compliance status of the computer, and how frequently to back up the client recovery key.</span></span></p></li>
<li><p><strong><span data-ttu-id="2f9ed-160">MBAM ステータスレポートサービスのエンドポイント </strong> 。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-160">MBAM Status reporting service endpoint</strong>.</span></span> <span data-ttu-id="2f9ed-161">これは、MBAM クライアント BitLocker 暗号化の管理を有効にするために構成する必要がある2番目のポリシー設定です。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-161">This is the second policy setting that you must configure to enable MBAM Client BitLocker encryption management.</span></span> <span data-ttu-id="2f9ed-162">この設定では、次の例を使用して、エンドポイントの場所を入力します。 <strong> http:// </strong><em> &lt; mbam 管理と監視サーバー名 &gt; </em><strong> : </strong><em> &lt; web サービスが/MBAMComplianceStatusService/StatusReportingService. にバインドされ &gt; </em><strong> ている</span><span class="sxs-lookup"><span data-stu-id="2f9ed-162">For this setting, enter the endpoint location by using the following example: <strong>http://</strong><em>&lt;MBAM Administration and Monitoring Server Name&gt;</em><strong>:</strong><em>&lt;port the web service is bound to&gt;</em><strong>/MBAMComplianceStatusService/StatusReportingService.</span></span> <span data-ttu-id="2f9ed-163">svc </strong> 。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-163">svc</strong>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2f9ed-164">ハードウェアの互換性のチェックを許可する</span><span class="sxs-lookup"><span data-stu-id="2f9ed-164">Allow hardware compatibility checking</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f9ed-165">推奨される構成: <strong> 有効</span><span class="sxs-lookup"><span data-stu-id="2f9ed-165">Suggested Configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="2f9ed-166">このポリシー設定では、MBAM クライアントコンピューターのドライブで BitLocker の保護を有効にする前に、ハードウェア互換性の確認を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-166">This policy setting lets you manage the verification of hardware compatibility before you enable BitLocker protection on drives of MBAM client computers.</span></span></p>
<p><span data-ttu-id="2f9ed-167">エンタープライズに、トラステッドプラットフォームモジュール (TPM) をサポートしていない旧式のコンピューターハードウェアまたはコンピューターがある場合は、このポリシーオプションを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-167">You should enable this policy option if your enterprise has older computer hardware or computers that do not support Trusted Platform Module (TPM).</span></span> <span data-ttu-id="2f9ed-168">これらの条件のいずれかが true の場合は、ハードウェア互換性の確認を有効にして、MBAM が BitLocker をサポートするコンピューターモデルにのみ適用されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-168">If either of these criteria is true, enable the hardware compatibility verification to make sure that MBAM is applied only to computer models that support BitLocker.</span></span> <span data-ttu-id="2f9ed-169">組織内のすべてのコンピューターで BitLocker がサポートされている場合、ハードウェアの互換性を展開する必要はありません。また、このポリシーを [未構成] に設定することもでき <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-169">If all computers in your organization support BitLocker, you do not have to deploy the Hardware Compatibility, and you can set this policy to <strong>Not Configured</strong>.</span></span></p>
<p><span data-ttu-id="2f9ed-170">このポリシー設定を有効にした場合、コンピューターのモデルは24時間ごとに1回、ハードウェア互換性リストに対して検証されます。これにより、ポリシーによって、コンピュータードライブの BitLocker の保護が有効になります。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-170">If you enable this policy setting, the model of the computer is validated against the hardware compatibility list once every 24 hours, before the policy enables BitLocker protection on a computer drive.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="2f9ed-171">注</span><span class="sxs-lookup"><span data-stu-id="2f9ed-171">Note</span></span></strong><br/><p><span data-ttu-id="2f9ed-172">このポリシー設定を有効にする前に、mbam <strong> </strong> サービスの構成オプションで Mbam 回復とハードウェアサービスのエンドポイントの設定が構成されていることを確認してください <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-172">Before enabling this policy setting, make sure that you have configured the <strong>MBAM Recovery and Hardware service endpoint</strong> setting in the <strong>Configure MBAM Services</strong> policy options.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="2f9ed-173">このポリシー設定を無効にした場合、または構成しなかった場合、コンピューターモデルはハードウェア互換性リストに対して検証されません。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-173">If you either disable or do not configure this policy setting, the computer model is not validated against the hardware compatibility list.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2f9ed-174">ユーザーの免税ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="2f9ed-174">Configure user exemption policy</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f9ed-175">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="2f9ed-175">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="2f9ed-176">このポリシー設定では、ユーザーに対して BitLocker 暗号化の除外を要求するように指示する、web サイトのアドレス、メールアドレス、または電話番号を構成できます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-176">This policy setting lets you configure a web site address, email address, or phone number that will instruct a user to request an exemption from BitLocker encryption.</span></span></p>
<p><span data-ttu-id="2f9ed-177">このポリシー設定を有効にして、web サイトのアドレス、メールアドレス、または電話番号を指定すると、除外を適用して BitLocker 保護を適用する方法の手順を示すダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-177">If you enable this policy setting and provide a web site address, email address, or phone number, users will see a dialog with instructions on how to apply for an exemption from BitLocker protection.</span></span> <span data-ttu-id="2f9ed-178">ユーザーに対して BitLocker 暗号化の除外を有効にする方法の詳細については、「 <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md)"> ユーザー Bitlocker 暗号化の除外を管理する方法」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-178">For more information about how to enable BitLocker encryption exemptions for users, see <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md)">How to Manage User BitLocker Encryption Exemptions</a>.</span></span></p>
<p><span data-ttu-id="2f9ed-179">このポリシー設定を無効にするか、未構成にした場合、除外要求に適用するための手順はユーザーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-179">If you either disable or do not configure this policy setting, the instructions about how to apply for an exemption request will not be presented to users.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="2f9ed-180">注</span><span class="sxs-lookup"><span data-stu-id="2f9ed-180">Note</span></span></strong><br/><p><span data-ttu-id="2f9ed-181">ユーザーの除外は、コンピューターごとではなく、ユーザーごとに管理されます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-181">User exemption is managed per user, not per computer.</span></span> <span data-ttu-id="2f9ed-182">複数のユーザーが同じコンピューターにログオンしていて、1人のユーザーが除外されていない場合、コンピューターは暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-182">If multiple users log on to the same computer and one user is not exempt, the computer will be encrypted.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="2f9ed-183">固定ドライブのポリシー定義</span><span class="sxs-lookup"><span data-stu-id="2f9ed-183">Fixed Drive policy definitions</span></span>


<span data-ttu-id="2f9ed-184">このセクションでは、mbam の固定ドライブポリシー定義について説明します。これは、次の GPO ノードで確認できます。**コンピューター構成** \\ **管理用テンプレート** \\ **Windows コンポーネント** \\ **MDOP mbam (BitLocker 管理)**  \\  **固定ドライブ**。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-184">This section describes the Fixed Drive policy definitions for MBAM, which can be found at the following GPO node: **Computer Configuration**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)** \\ **Fixed Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2f9ed-185">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="2f9ed-185">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="2f9ed-186">概要と推奨されるポリシー設定</span><span class="sxs-lookup"><span data-stu-id="2f9ed-186">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2f9ed-187">固定データドライブの暗号化設定</span><span class="sxs-lookup"><span data-stu-id="2f9ed-187">Fixed data drive encryption settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f9ed-188">推奨される構成: 有効にして、 <strong> </strong> <strong> </strong> オペレーティングシステムのボリュームが暗号化されている必要がある場合は、[固定データドライブの自動ロック解除を行う] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-188">Suggested Configuration: <strong>Enabled</strong>, and select the <strong>Enable auto-unlock fixed data drive</strong> check box if the operating system volume is required to be encrypted.</span></span></p>
<p><span data-ttu-id="2f9ed-189">このポリシー設定では、固定ドライブを暗号化するかどうかを管理できます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-189">This policy setting lets you manage whether or not to encrypt the fixed drives.</span></span></p>
<p><span data-ttu-id="2f9ed-190">このポリシーを有効にする場合は、[ <strong> 固定データドライブのパスワードの使用を構成する] ポリシーを無効にしないでください </strong> 。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-190">When you enable this policy, do not disable the <strong>Configure use of password for fixed data drives</strong> policy.</span></span></p>
<p><span data-ttu-id="2f9ed-191">[ <strong> 固定データドライブの自動ロック解除を行う] チェックボックスがオンになっている場合は、 </strong> オペレーティングシステムのボリュームが暗号化されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-191">If the <strong>Enable auto-unlock fixed data drive</strong> check box is selected, the operating system volume must be encrypted.</span></span></p>
<p><span data-ttu-id="2f9ed-192">このポリシー設定を有効にした場合、ユーザーはすべての固定ドライブを BitLocker 保護下に置き、ドライブを暗号化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-192">If you enable this policy setting, users are required to put all fixed drives under BitLocker protection, which will encrypt the drives.</span></span></p>
<p><span data-ttu-id="2f9ed-193">このポリシーを構成していない場合、またはこのポリシーを無効にした場合、ユーザーは BitLocker 保護の下に固定ドライブを配置する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-193">If you do not configure this policy or if you disable this policy, users are not required to put fixed drives under BitLocker protection.</span></span></p>
<p><span data-ttu-id="2f9ed-194">このポリシーを無効にすると、MBAM エージェントは暗号化された固定ドライブを暗号化解除します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-194">If you disable this policy, the MBAM agent decrypts any encrypted fixed drives.</span></span></p>
<p><span data-ttu-id="2f9ed-195">オペレーティングシステムのボリュームを暗号化する必要がない場合は、[ <strong> 固定データドライブの自動ロックを有効にする] チェックボックスをオフにし </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-195">If encrypting the operating system volume is not required, clear the <strong>Enable auto-unlock fixed data drive</strong> check box.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2f9ed-196">BitLocker で保護されていない固定ドライブに対する "書き込み" アクセス許可を拒否する</span><span class="sxs-lookup"><span data-stu-id="2f9ed-196">Deny “write” permission to fixed drives that are not protected by BitLocker</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f9ed-197">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="2f9ed-197">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="2f9ed-198">このポリシー設定は、書き込み可能なコンピューター上の固定ドライブに対して BitLocker 保護が必要かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-198">This policy setting determines if BitLocker protection is required for fixed drives on a computer so that they are writable.</span></span> <span data-ttu-id="2f9ed-199">このポリシー設定は、BitLocker を有効にすると適用されます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-199">This policy setting is applied when you turn on BitLocker.</span></span></p>
<p><span data-ttu-id="2f9ed-200">ポリシーが構成されていない場合、コンピューター上のすべての固定ドライブは読み取り/書き込みアクセス許可を使用してマウントされます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-200">When the policy is not configured, all fixed drives on the computer are mounted with read/write permissions.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2f9ed-201">BitLocker で保護された固定ドライブへのアクセスを以前のバージョンの Windows から許可する</span><span class="sxs-lookup"><span data-stu-id="2f9ed-201">Allow access to BitLocker-protected fixed drives from earlier versions of Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f9ed-202">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="2f9ed-202">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="2f9ed-203">このポリシーを有効にすると、Windows Server 2008、Windows Vista、Windows XP SP3、または Windows XP SP2 を実行しているコンピューター上で、ファイルアロケーションテーブル (FAT) ファイルシステムでフォーマットされた固定ドライブのロックを解除して表示することができます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-203">Enable this policy to unlock and view the fixed drives that are formatted with the file allocation table (FAT) file system on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p>
<p><span data-ttu-id="2f9ed-204">これらのオペレーティングシステムは、BitLocker で保護されたドライブに対して読み取り専用のアクセス許可を持っています。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-204">These operating systems have read-only permissions to BitLocker-protected drives.</span></span></p>
<p><span data-ttu-id="2f9ed-205">ポリシーが無効になっている場合、FAT ファイルシステムで書式設定された固定ドライブのロックを解除することはできません。 Windows Server 2008、Windows Vista、Windows XP SP3、または Windows XP SP2 を実行しているコンピューターでは、これらのコンテンツを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-205">When the policy is disabled, fixed drives formatted with the FAT file system cannot be unlocked and their content cannot be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2f9ed-206">固定ドライブのパスワードの使用を構成する</span><span class="sxs-lookup"><span data-stu-id="2f9ed-206">Configure use of password for fixed drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f9ed-207">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="2f9ed-207">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="2f9ed-208">このポリシーを有効にして、固定ドライブのパスワード保護を構成します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-208">Enable this policy to configure password protection on fixed drives.</span></span></p>
<p><span data-ttu-id="2f9ed-209">ポリシーが構成されていない場合は、パスワードの複雑さの要件を含まず、8文字のみを必要とする既定の設定でパスワードがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-209">When the policy is not configured, passwords will be supported with the default settings, which do not include password complexity requirements and require only eight characters.</span></span></p>
<p><span data-ttu-id="2f9ed-210">セキュリティを高めるには、このポリシーを有効にして、[ <strong> 固定データドライブにパスワードを要求する] を選択し </strong> 、[ <strong> パスワードの複雑さを要求する] を選択し </strong> て、必要なパスワードの長さを設定し <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-210">For higher security, enable this policy and select <strong>Require password for fixed data drive</strong>, select <strong>Require password complexity</strong>, and set the desired <strong>minimum password length</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2f9ed-211">BitLocker で保護された固定ドライブの回復方法を選択する</span><span class="sxs-lookup"><span data-stu-id="2f9ed-211">Choose how BitLocker-protected fixed drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f9ed-212">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="2f9ed-212">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="2f9ed-213">BitLocker データ回復エージェントを有効にする、または Active Directory ドメインサービス (AD DS) に BitLocker 回復情報を保存するには、このポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-213">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="2f9ed-214">このポリシーが構成されていない場合、BitLocker データ回復エージェントは許可され、回復情報は AD DS にバックアップされません。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-214">When this policy is not configured, the BitLocker data recovery agent is allowed, and recovery information is not backed up to AD DS.</span></span> <span data-ttu-id="2f9ed-215">MBAM は、AD DS に回復情報をバックアップする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-215">MBAM does not require the recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="2f9ed-216">オペレーティングシステムドライブのポリシー定義</span><span class="sxs-lookup"><span data-stu-id="2f9ed-216">Operating System Drive policy definitions</span></span>


<span data-ttu-id="2f9ed-217">このセクションでは、mbam のオペレーティングシステムドライブのポリシー定義について説明します。**コンピューター構成** \\ **管理用テンプレート** \\ **Windows コンポーネント** \\ **MDOP mbam (BitLocker 管理)**  \\  **オペレーティングシステムドライブ**。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-217">This section describes the Operating System Drive policy definitions for MBAM, found at the following GPO node: **Computer Configuration**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)** \\ **Operating System Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2f9ed-218">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="2f9ed-218">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="2f9ed-219">概要と推奨されるポリシー設定</span><span class="sxs-lookup"><span data-stu-id="2f9ed-219">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2f9ed-220">オペレーティングシステムドライブの暗号化の設定</span><span class="sxs-lookup"><span data-stu-id="2f9ed-220">Operating system drive encryption settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f9ed-221">推奨される構成: <strong> 有効</span><span class="sxs-lookup"><span data-stu-id="2f9ed-221">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="2f9ed-222">このポリシー設定は、オペレーティングシステムのドライブが暗号化されるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-222">This policy setting determines if the operating system drive will be encrypted.</span></span></p>
<p><span data-ttu-id="2f9ed-223">このポリシーを構成して、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-223">Configure this policy to do the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2f9ed-224">オペレーティングシステムドライブに対して BitLocker 保護を適用します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-224">Enforce BitLocker protection for the operating system drive.</span></span></p></li>
<li><p><span data-ttu-id="2f9ed-225">PIN の使用を構成して、オペレーティングシステムの保護にトラステッドプラットフォームモジュール (TPM) PIN を使用します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-225">Configure PIN usage to use a Trusted Platform Module (TPM) PIN for operating system protection.</span></span></p></li>
<li><p><span data-ttu-id="2f9ed-226">拡張起動 Pin を構成して、大文字、小文字、数字などの文字を許可します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-226">Configure enhanced startup PINs to permit characters such as uppercase and lowercase letters, and numbers.</span></span> <span data-ttu-id="2f9ed-227">MBAM は、拡張ピンでの記号とスペースの使用をサポートしていません。ただし、BitLocker では記号とスペースがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-227">MBAM does not support the use of symbols and spaces for enhanced PINs, even though BitLocker supports symbols and spaces.</span></span></p></li>
</ul>
<p><span data-ttu-id="2f9ed-228">このポリシー設定を有効にした場合、ユーザーは BitLocker を使用してオペレーティングシステムドライブをセキュリティで保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-228">If you enable this policy setting, users are required to secure the operating system drive by using BitLocker.</span></span></p>
<p><span data-ttu-id="2f9ed-229">構成しない場合、または設定を無効にした場合、ユーザーは BitLocker を使用してオペレーティングシステムドライブを保護する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-229">If you do not configure or if you disable the setting, users are not required to secure the operating system drive by using BitLocker.</span></span></p>
<p><span data-ttu-id="2f9ed-230">このポリシーを無効にすると、MBAM エージェントは暗号化されたオペレーティングシステムボリュームを暗号化解除します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-230">If you disable this policy, the MBAM agent decrypts the operating system volume if it is encrypted.</span></span></p>
<p><span data-ttu-id="2f9ed-231">有効になっている場合、このポリシー設定では、ユーザーは BitLocker 保護を使用してオペレーティングシステムをセキュリティで保護する必要があり、ドライブは暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-231">When it is enabled, this policy setting requires users to secure the operating system by using BitLocker protection, and the drive is encrypted.</span></span> <span data-ttu-id="2f9ed-232">暗号化の要件に基づいて、オペレーティングシステムドライブの保護方法を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-232">Based on your encryption requirements, you may select the method of protection for the operating system drive.</span></span></p>
<p><span data-ttu-id="2f9ed-233">セキュリティ要件を高くするには、TPM + PIN を使用し、拡張 Pin を許可して、PIN の最小の長さを8文字に設定します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-233">For higher security requirements, use TPM + PIN, allow enhanced PINs, and set the minimum PIN length to eight characters.</span></span></p>
<p><span data-ttu-id="2f9ed-234">TPM + PIN プロテクターでこのポリシーが有効になっている場合は、 <strong> システムの </strong>  /  <strong> Power Management の </strong>  /  <strong> スリープ設定 </strong> で次のポリシーを無効にすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-234">When this policy is enabled with the TPM + PIN protector, you can consider disabling the following policies under <strong>System</strong> / <strong>Power Management</strong> / <strong>Sleep Settings</strong>:</span></span></p>
<ul>
<li><p><span data-ttu-id="2f9ed-235">スリープ中 (電源に接続されているとき) にスタンバイ状態 (S1 ~ S3) を許可する</span><span class="sxs-lookup"><span data-stu-id="2f9ed-235">Allow Standby States (S1-S3) When Sleeping (Plugged In)</span></span></p></li>
<li><p><span data-ttu-id="2f9ed-236">スリープ中 (バッテリー) でスタンバイ状態 (S1-S3) を許可する</span><span class="sxs-lookup"><span data-stu-id="2f9ed-236">Allow Standby States (S1-S3) When Sleeping (On Battery)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2f9ed-237">TPM プラットフォームの検証プロファイルを構成する</span><span class="sxs-lookup"><span data-stu-id="2f9ed-237">Configure TPM platform validation profile</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f9ed-238">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="2f9ed-238">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="2f9ed-239">このポリシー設定では、コンピューター上の TPM セキュリティハードウェアが BitLocker 暗号化キーをセキュリティで保護する方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-239">This policy setting lets you configure how the TPM security hardware on a computer secures the BitLocker encryption key.</span></span> <span data-ttu-id="2f9ed-240">このポリシー設定は、コンピューターに互換性のある TPM が搭載されていない場合、または BitLocker で TPM 保護が有効になっている場合は適用されません。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-240">This policy setting does not apply if the computer does not have a compatible TPM or if BitLocker already has TPM protection enabled.</span></span></p>
<p><span data-ttu-id="2f9ed-241">このポリシーが構成されていない場合、TPM では、既定のプラットフォーム検証プロファイルまたはセットアップスクリプトで指定されたプラットフォームの検証プロファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-241">When this policy is not configured, the TPM uses the default platform validation profile or the platform validation profile specified by the setup script.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2f9ed-242">BitLocker で保護されたオペレーティングシステムドライブの回復方法を選択する</span><span class="sxs-lookup"><span data-stu-id="2f9ed-242">Choose how to recover BitLocker-protected operating system drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f9ed-243">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="2f9ed-243">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="2f9ed-244">BitLocker データ回復エージェントを有効にする、または Active Directory ドメインサービス (AD DS) に BitLocker 回復情報を保存するには、このポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-244">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="2f9ed-245">このポリシーが構成されていない場合、データ回復エージェントは許可され、回復情報は AD DS にバックアップされません。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-245">When this policy is not configured, the data recovery agent is allowed, and the recovery information is not backed up to AD DS.</span></span></p>
<p><span data-ttu-id="2f9ed-246">MBAM 操作では、回復情報を AD DS にバックアップする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-246">MBAM operation does not require the recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="2f9ed-247">リムーバブルドライブのポリシー定義</span><span class="sxs-lookup"><span data-stu-id="2f9ed-247">Removable Drive policy definitions</span></span>


<span data-ttu-id="2f9ed-248">このセクションでは、mbam のリムーバブルドライブポリシー定義について説明します。**コンピューター構成** \\ **管理用テンプレート** \\ **Windows コンポーネント** \\ **MDOP mbam (BitLocker 管理)**  \\  **リムーバブルドライブ**。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-248">This section describes the Removable Drive Policy definitions for MBAM, found at the following GPO node: **Computer Configuration**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)** \\ **Removable Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2f9ed-249">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="2f9ed-249">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="2f9ed-250">概要と推奨されるポリシー設定</span><span class="sxs-lookup"><span data-stu-id="2f9ed-250">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2f9ed-251">リムーバブルドライブでの BitLocker の使用を制御する</span><span class="sxs-lookup"><span data-stu-id="2f9ed-251">Control the use of BitLocker on removable drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f9ed-252">推奨される構成: <strong> 有効</span><span class="sxs-lookup"><span data-stu-id="2f9ed-252">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="2f9ed-253">このポリシーは、リムーバブルデータドライブでの BitLocker の使用を制御します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-253">This policy controls the use of BitLocker on removable data drives.</span></span></p>
<p><span data-ttu-id="2f9ed-254">[ <strong> リムーバブルデータドライブに対して bitlocker 保護を適用することをユーザーに許可する </strong> ] オプションを有効にして、ユーザーがリムーバブルデータドライブで bitlocker セットアップウィザードを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-254">Enable the <strong>Allow users to apply BitLocker protection on removable data drives</strong> option, to allow users to run the BitLocker setup wizard on a removable data drive.</span></span></p>
<p><span data-ttu-id="2f9ed-255"><strong>[リムーバブルデータドライブ上の bitlocker を一時停止して暗号化を解除する] オプションを有効にして、 </strong> ユーザーがドライブから bitlocker ドライブ暗号化を削除できるようにします。または、メンテナンスが実行されている間、暗号化を中断します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-255">Enable the <strong>Allow users to suspend and decrypt BitLocker on removable data drives</strong> option to allow users to remove BitLocker drive encryption from the drive or to suspend the encryption while maintenance is performed.</span></span></p>
<p><span data-ttu-id="2f9ed-256">このポリシーを有効にして、[ <strong> ユーザーにリムーバブルデータドライブへの BitLocker 保護の適用を許可する] オプションが選択されている場合 </strong> 、Mbam クライアントは、リムーバブルドライブに関する回復情報を mbam キー回復サーバーに保存し、パスワードが失われた場合にユーザーがドライブを回復できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-256">When this policy is enabled and the <strong>Allow users to apply BitLocker protection on removable data drives</strong> option is selected, the MBAM Client saves the recovery information about removable drives to the MBAM key recovery server, and it allows users to recover the drive if the password is lost.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2f9ed-257">BitLocker で保護されていないリムーバブルドライブに対する "書き込み" アクセス許可を拒否する</span><span class="sxs-lookup"><span data-stu-id="2f9ed-257">Deny the “write” permissions to removable drives that are not protected by BitLocker</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f9ed-258">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="2f9ed-258">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="2f9ed-259">このポリシーを有効にして、BitLocker で保護されたドライブへの書き込み専用アクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-259">Enable this policy to allow write-only permissions to BitLocker protected drives.</span></span></p>
<p><span data-ttu-id="2f9ed-260">このポリシーを有効にすると、コンピューター上のすべてのリムーバブルデータドライブは、書き込み権限が許可される前に暗号化が必要になります。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-260">When this policy is enabled, all removable data drives on the computer require encryption before write permissions are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2f9ed-261">以前のバージョンの Windows から BitLocker で保護されているリムーバブルドライブへのアクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="2f9ed-261">Allow access to BitLocker-protected removable drives from earlier versions of Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f9ed-262">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="2f9ed-262">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="2f9ed-263">このポリシーを有効にすると、Windows Server 2008、Windows Vista、Windows XP SP3、または Windows XP SP2 を実行しているコンピューター上で、(FAT) ファイルシステムでフォーマットされている固定ドライブをロック解除して表示することができます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-263">Enable this policy to unlock and view the fixed drives that are formatted with the (FAT) file system on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p>
<p><span data-ttu-id="2f9ed-264">これらのオペレーティングシステムは、BitLocker で保護されたドライブに対して読み取り専用のアクセス許可を持っています。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-264">These operating systems have read-only permissions to BitLocker-protected drives.</span></span></p>
<p><span data-ttu-id="2f9ed-265">ポリシーが無効になっている場合、FAT ファイルシステムで書式設定されたリムーバブルドライブのロックを解除することはできません。 Windows Server 2008、Windows Vista、Windows XP SP3、または Windows XP SP2 を実行しているコンピューターでは、これらのコンテンツを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-265">When the policy is disabled, removable drives formatted with the FAT file system cannot be unlocked and their content cannot be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2f9ed-266">リムーバブルデータドライブのパスワードを使用するように構成する</span><span class="sxs-lookup"><span data-stu-id="2f9ed-266">Configure the use of password for removable data drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f9ed-267">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="2f9ed-267">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="2f9ed-268">このポリシーを有効にして、リムーバブルデータドライブのパスワード保護を構成します。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-268">Enable this policy to configure password protection on removable data drives.</span></span></p>
<p><span data-ttu-id="2f9ed-269">このポリシーが構成されていない場合は、パスワードの複雑さの要件が含まれておらず、8文字のみを必要とする既定の設定でパスワードがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-269">When this policy is not configured, passwords are supported with the default settings, which do not include password complexity requirements and require only eight characters.</span></span></p>
<p><span data-ttu-id="2f9ed-270">セキュリティ強化のために、このポリシーを有効にして、[リムーバブルデータドライブにパスワードを要求する] を選択し、[パスワードの複雑さを要求する] を選択して、[パスワード <strong> </strong> <strong> </strong> の最小文字数] を設定し <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-270">For increased security, you can enable this policy and select <strong>Require password for removable data drive</strong>, select <strong>Require password complexity</strong>, and then set the preferred <strong>minimum password length</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2f9ed-271">BitLocker で保護されたリムーバブルドライブの回復方法を選択する</span><span class="sxs-lookup"><span data-stu-id="2f9ed-271">Choose how BitLocker-protected removable drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f9ed-272">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="2f9ed-272">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="2f9ed-273">このポリシーを構成して、BitLocker データ回復エージェントを有効にしたり、Active Directory ドメインサービス (AD DS) に BitLocker 回復情報を保存したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-273">You can configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="2f9ed-274">ポリシーが未構成に設定されている場合 <strong> </strong> 、データ回復エージェントは許可され、回復情報は AD DS にバックアップされません。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-274">When the policy is set to <strong>Not Configured</strong>, the data recovery agent is allowed and recovery information is not backed up to AD DS.</span></span></p>
<p><span data-ttu-id="2f9ed-275">MBAM 操作では、回復情報を AD DS にバックアップする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2f9ed-275">MBAM operation does not require the recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="2f9ed-276">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2f9ed-276">Related topics</span></span>


[<span data-ttu-id="2f9ed-277">MBAM 1.0 に対応する環境の準備</span><span class="sxs-lookup"><span data-stu-id="2f9ed-277">Preparing your Environment for MBAM 1.0</span></span>](preparing-your-environment-for-mbam-10.md)









