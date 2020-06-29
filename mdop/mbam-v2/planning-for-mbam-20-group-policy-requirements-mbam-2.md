---
title: MBAM 2.0 グループ ポリシー要件の計画
description: MBAM 2.0 グループ ポリシー要件の計画
author: dansimp
ms.assetid: f5e19dcb-eb15-4722-bb71-0734b3799eb8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f6092507996fe6f0234178c8b1abae5cea7bf836
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812827"
---
# <span data-ttu-id="4f6b2-103">MBAM 2.0 グループ ポリシー要件の計画</span><span class="sxs-lookup"><span data-stu-id="4f6b2-103">Planning for MBAM 2.0 Group Policy Requirements</span></span>


<span data-ttu-id="4f6b2-104">Microsoft BitLocker の管理と監視 (MBAM) クライアントコンピューターを管理するには、組織でサポートする BitLocker プロテクターの種類を考慮し、適用する対応するグループポリシー設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-104">To manage Microsoft BitLocker Administration and Monitoring (MBAM) client computers, you need to consider the types of BitLocker protectors that you want to support in your organization, and then configure the corresponding Group Policy settings that you want to apply.</span></span> <span data-ttu-id="4f6b2-105">このトピックでは、Microsoft BitLocker の管理と監視を使用して、エンタープライズで BitLocker ドライブ暗号化を管理するときに使用できるグループポリシー設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-105">This topic describes the Group Policy settings that are available for use when you are using Microsoft BitLocker Administration and Monitoring to manage BitLocker Drive Encryption in the enterprise.</span></span>

<span data-ttu-id="4f6b2-106">MBAM は、オペレーティングシステムドライブ用の BitLocker プロテクターとして、トラステッドプラットフォームモジュール (TPM)、TPM + PIN、TPM + USB キー、TPM + PIN + USB キー、パスワード、数字パスワード、データ回復エージェントの各種類をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-106">MBAM supports the following types of BitLocker protectors for operating system drives: Trusted Platform Module (TPM), TPM + PIN, TPM + USB key, and TPM + PIN + USB key, password, numerical password, and Data Recovery Agent.</span></span> <span data-ttu-id="4f6b2-107">パスワードの保護機能がサポートされているのは、Windows To Go デバイスと TPM が搭載されていない Windows 8 デバイスのみです。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-107">The password protector is supported only for Windows To Go devices and for Windows 8 devices that do not have a TPM.</span></span> <span data-ttu-id="4f6b2-108">MBAM は、MBAM をインストールする前にオペレーティングシステムのボリュームが暗号化されている場合にのみ、TPM + USB キーと TPM + PIN + USB キーの保護機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-108">MBAM supports the TPM + USB key and the TPM + PIN + USB key protectors only when the operating system volume is encrypted before MBAM is installed.</span></span>

<span data-ttu-id="4f6b2-109">MBAM は、固定データドライブ用の BitLocker プロテクター (パスワード、自動ロック解除、数字パスワード、データ回復エージェント) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-109">MBAM supports the following types of BitLocker protectors for fixed data drives: password, auto-unlock, numerical password, and Data Recovery Agent.</span></span>

<span data-ttu-id="4f6b2-110">数値パスワードプロテクターはボリューム暗号化の一部として自動的に適用されるため、構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-110">The numeric password protector is applied automatically as part of volume encryption and does not need to be configured.</span></span>

**<span data-ttu-id="4f6b2-111">重要</span><span class="sxs-lookup"><span data-stu-id="4f6b2-111">Important</span></span>**  
<span data-ttu-id="4f6b2-112">既定の Windows BitLocker ドライブ暗号化グループポリシーオブジェクト (GPO) の設定は、MBAM では使われず、有効になっている場合は競合する動作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-112">The default Windows BitLocker drive encryption Group Policy Object (GPO) settings are not used by MBAM and can cause conflicting behavior if they are enabled.</span></span> <span data-ttu-id="4f6b2-113">MBAM を有効にするには、mbam グループポリシーテンプレートをインストールした後でのみ、MBAM グループポリシー設定を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-113">To enable MBAM to manage BitLocker, you must define the MBAM Group Policy settings only after installing the MBAM Group Policy template.</span></span>



<span data-ttu-id="4f6b2-114">拡張されたスタートアップ Pin には、大文字と小文字、数字などの文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-114">Enhanced startup PINs can contain characters, such as uppercase and lowercase letters, and numbers.</span></span> <span data-ttu-id="4f6b2-115">BitLocker とは異なり、MBAM は拡張ピンでの記号とスペースの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-115">Unlike BitLocker, MBAM does not support the use of symbols and spaces for enhanced PINs.</span></span>

<span data-ttu-id="4f6b2-116">グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) の MDOP 技術を実行できるコンピューターに MBAM グループポリシーテンプレートをインストールします。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-116">Install the MBAM Group Policy template on a computer that is capable of running the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) MDOP technology.</span></span> <span data-ttu-id="4f6b2-117">Mbam 機能を有効にする gpo 設定を編集するには、まず、mbam グループポリシーテンプレートをインストールして、該当する gpo を編集するために GPMC または AGPM を開いてから、次の gpo ノードに移動する必要があります。**コンピューター構成** \\ **ポリシー** \\ **管理用テンプレート** \\ **Windows コンポーネント** \\ **MDOP mbam (BitLocker 管理)。**</span><span class="sxs-lookup"><span data-stu-id="4f6b2-117">To edit the GPO settings that enable MBAM functionality, you must first install the MBAM Group Policy template, open the GPMC or AGPM to edit the applicable GPO, and then navigate to the following GPO node: **Computer Configuration**\\**Policies**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management).**</span></span>

<span data-ttu-id="4f6b2-118">MDOP MBAM (BitLocker Management) GPO ノードには、4つのグローバルポリシー設定と4つの子 GPO 設定ノード (クライアント管理、固定ドライブ、オペレーティングシステムドライブ、およびリムーバブルドライブ) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-118">The MDOP MBAM (BitLocker Management) GPO node contains four global policy settings and four child GPO settings nodes: Client Management, Fixed Drive, Operating System Drive, and Removable Drive.</span></span> <span data-ttu-id="4f6b2-119">以下のセクションでは、MBAM GPO ポリシー設定要件の計画に役立つポリシー定義と推奨されるポリシー設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-119">The following sections provide policy definitions and suggested policy settings to assist you in planning for MBAM GPO policy setting requirements.</span></span>

**<span data-ttu-id="4f6b2-120">注</span><span class="sxs-lookup"><span data-stu-id="4f6b2-120">Note</span></span>**  
<span data-ttu-id="4f6b2-121">最低限の推奨される GPO 設定を構成して、MBAM で BitLocker 暗号化を管理できるようにする方法については、「 [mbam 2.0 GPO 設定を編集する方法](how-to-edit-mbam-20-gpo-settings-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-121">For more information about configuring the minimum, recommended GPO settings to enable MBAM to manage BitLocker encryption, see [How to Edit MBAM 2.0 GPO Settings](how-to-edit-mbam-20-gpo-settings-mbam-2.md).</span></span>



## <span data-ttu-id="4f6b2-122">グローバルポリシー定義</span><span class="sxs-lookup"><span data-stu-id="4f6b2-122">Global Policy Definitions</span></span>


<span data-ttu-id="4f6b2-123">このセクションでは、次の GPO ノードで検索される mbam グローバルポリシー定義について説明します。**コンピューター構成** \\ **ポリシー** \\ **管理用テンプレート** \\ **Windows コンポーネント** \\ **MDOP mbam (BitLocker 管理)**。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-123">This section describes MBAM Global policy definitions found at the following GPO node: **Computer Configuration**\\**Policies**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4f6b2-124">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="4f6b2-124">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="4f6b2-125">概要と推奨されるポリシー設定</span><span class="sxs-lookup"><span data-stu-id="4f6b2-125">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4f6b2-126">ドライブの暗号化方法と暗号強度を選ぶ</span><span class="sxs-lookup"><span data-stu-id="4f6b2-126">Choose drive encryption method and cipher strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f6b2-127">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="4f6b2-127">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="4f6b2-128">特定の暗号化方法と暗号強度を使用するように、このポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-128">Configure this policy to use a specific encryption method and cipher strength.</span></span></p>
<p><span data-ttu-id="4f6b2-129">このポリシーが構成されていない場合、BitLocker では、AES 128 ビットとディフューザーの既定の暗号化方法、またはセットアップスクリプトで指定された暗号化メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-129">When this policy is not configured, BitLocker uses the default encryption method of AES 128-bit with Diffuser or the encryption method specified by the setup script.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4f6b2-130">再起動時にメモリの上書きを防止する</span><span class="sxs-lookup"><span data-stu-id="4f6b2-130">Prevent memory overwrite on restart</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f6b2-131">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="4f6b2-131">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="4f6b2-132">このポリシーを構成して、再起動時にメモリ内の BitLocker シークレットを上書きせずに、再起動のパフォーマンスを向上させます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-132">Configure this policy to improve restart performance without overwriting BitLocker secrets in memory on restart.</span></span></p>
<p><span data-ttu-id="4f6b2-133">このポリシーが構成されていない場合、コンピューターを再起動すると、BitLocker シークレットがメモリから削除されます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-133">When this policy is not configured, BitLocker secrets are removed from memory when the computer restarts.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4f6b2-134">スマートカード証明書の使用規則を検証する</span><span class="sxs-lookup"><span data-stu-id="4f6b2-134">Validate smart card certificate usage rule</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f6b2-135">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="4f6b2-135">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="4f6b2-136">スマートカード証明書ベースの BitLocker 保護を使用するように、このポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-136">Configure this policy to use smartcard certificate-based BitLocker protection.</span></span></p>
<p><span data-ttu-id="4f6b2-137">このポリシーが構成されていない場合、証明書の指定には既定のオブジェクト識別子1.3.6.1.4.1.311.67.1.1 が使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-137">When this policy is not configured, a default object identifier 1.3.6.1.4.1.311.67.1.1 is used to specify a certificate.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4f6b2-138">組織固有の識別子を指定する</span><span class="sxs-lookup"><span data-stu-id="4f6b2-138">Provide the unique identifiers for your organization</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f6b2-139">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="4f6b2-139">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="4f6b2-140">証明書ベースのデータ回復エージェントまたは BitLocker To Go リーダーを使用するように、このポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-140">Configure this policy to use a certificate-based data recovery agent or the BitLocker To Go reader.</span></span></p>
<p><span data-ttu-id="4f6b2-141">このポリシーが構成されていない場合、[ <strong> id </strong> ] フィールドは使用されません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-141">When this policy is not configured, the <strong>Identification</strong> field is not used.</span></span></p>
<p><span data-ttu-id="4f6b2-142">会社でより高いセキュリティの測定が必要な場合は、[id] フィールドを構成して、 <strong> </strong> すべての USB デバイスでこのフィールドセットが設定され、このフィールドがこのグループポリシー設定に合わせて調整されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-142">If your company requires higher security measurements, you may want to configure the <strong>Identification</strong> field to make sure that all USB devices have this field set and that they are aligned with this Group Policy setting.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="4f6b2-143">クライアント管理ポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="4f6b2-143">Client Management Policy Definitions</span></span>


<span data-ttu-id="4f6b2-144">このセクションでは、次の GPO ノードで検出された Microsoft BitLocker 管理および監視のクライアント管理ポリシー定義について説明します。**コンピューター構成** \\ **ポリシー** \\ **管理用テンプレート** \\ **Windows コンポーネント** \\ **MDOP mbam (BitLocker 管理)** \\ **クライアントの管理**。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-144">This section describes Client Management policy definitions for Microsoft BitLocker Administration and Monitoring found at the following GPO node: **Computer Configuration**\\**Policies**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)**\\**Client Management**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4f6b2-145">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="4f6b2-145">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="4f6b2-146">概要と推奨されるポリシー設定</span><span class="sxs-lookup"><span data-stu-id="4f6b2-146">Overview and Suggested Policy Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4f6b2-147">MBAM サービスを設定する</span><span class="sxs-lookup"><span data-stu-id="4f6b2-147">Configure MBAM Services</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f6b2-148">推奨される構成: <strong> 有効</span><span class="sxs-lookup"><span data-stu-id="4f6b2-148">Suggested Configuration: <strong>Enabled</span></span></strong></p>
<ul>
<li><p><strong><span data-ttu-id="4f6b2-149">MBAM Recovery and Hardware service endpoint </strong> 。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-149">MBAM Recovery and Hardware service endpoint</strong>.</span></span> <span data-ttu-id="4f6b2-150">MBAM クライアント BitLocker 暗号化管理を有効にするには、この設定を使います。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-150">Use this setting to enable MBAM Client BitLocker encryption management.</span></span> <span data-ttu-id="4f6b2-151">次のようなエンドポイントの場所を入力します。 <strong> http:// </strong><em> &lt; mbam Administration and Monitoring Server Name &gt; </em><strong> : </strong><em> &lt; web サービスは/MBAMRecoveryAndHardwareService/CoreService.svc にバインドされてい &gt; </em><strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-151">Enter an endpoint location that is similar to the following example: <strong>http://</strong><em>&lt;MBAM Administration and Monitoring Server Name&gt;</em><strong>:</strong><em>&lt;port the web service is bound to&gt;</em><strong>/MBAMRecoveryAndHardwareService/CoreService.svc</strong>.</span></span></p></li>
<li><p><strong><span data-ttu-id="4f6b2-152">保存する BitLocker 回復情報を選択し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-152">Select BitLocker recovery information to store</strong>.</span></span> <span data-ttu-id="4f6b2-153">このポリシー設定では、BitLocker 回復情報をバックアップするためのキー回復サービスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-153">This policy setting lets you configure the key recovery service to back up BitLocker recovery information.</span></span> <span data-ttu-id="4f6b2-154">また、コンプライアンスと監査レポートを収集するためのステータスレポートサービスを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-154">It also lets you configure status reporting service for collecting compliance and audit reports.</span></span> <span data-ttu-id="4f6b2-155">ポリシーには、BitLocker によって暗号化されたデータを回復するための管理方法が用意されており、重要な情報がないためにデータの損失を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-155">The policy provides an administrative method of recovering data encrypted by BitLocker to prevent data loss due to the lack of key information.</span></span> <span data-ttu-id="4f6b2-156">状態レポートとキー回復アクティビティは、自動的に、構成済みレポートサーバーの場所に送信されます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-156">Status report and key recovery activity will automatically and silently be sent to the configured report server location.</span></span></p>
<p><span data-ttu-id="4f6b2-157">構成しなかった場合、またはこのポリシー設定を無効にした場合、キーの回復情報は保存されず、ステータスレポートとキーの回復アクティビティはサーバーに報告されません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-157">If you do not configure or if you disable this policy setting, the Key recovery information will not be saved, and status report and key recovery activity will not be reported to server.</span></span> <span data-ttu-id="4f6b2-158">この設定を <strong> [回復パスワードとキーパッケージ] に設定すると、 </strong> 回復パスワードとキーパッケージは、構成済みのキー回復サーバーの場所に自動的にバックアップされます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-158">When this setting is set to <strong>Recovery Password and key package</strong>, the recovery password and key package will be automatically and silently backed up to the configured key recovery server location.</span></span></p></li>
<li><p><strong><span data-ttu-id="4f6b2-159">クライアントチェックの状態の頻度を分単位で入力し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-159">Enter client checking status frequency in minutes</strong>.</span></span> <span data-ttu-id="4f6b2-160">このポリシー設定は、クライアントがクライアントコンピューター上の BitLocker 保護ポリシーと状態を確認する頻度を管理します。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-160">This policy setting manages how frequently the client checks the BitLocker protection policies and status on the client computer.</span></span> <span data-ttu-id="4f6b2-161">このポリシーは、クライアントのコンプライアンスの状態をサーバーに保存する頻度も管理します。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-161">This policy also manages how frequently the client compliance status is saved to the server.</span></span> <span data-ttu-id="4f6b2-162">クライアントは、クライアントコンピューター上の BitLocker 保護ポリシーと状態を確認し、構成された頻度でクライアント回復キーもバックアップします。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-162">The client checks the BitLocker protection policies and status on the client computer and also backs up the client recovery key at the configured frequency.</span></span></p>
<p><span data-ttu-id="4f6b2-163">この頻度は、お客様の会社によって設定された要件に基づいて、コンピューターのコンプライアンスの状態を確認する頻度と、クライアント回復キーをバックアップする頻度に基づいて設定します。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-163">Set this frequency based on the requirement set by your company on how frequently to check the compliance status of the computer, and how frequently to back up the client recovery key.</span></span></p></li>
<li><p><strong><span data-ttu-id="4f6b2-164">MBAM ステータスレポートサービスのエンドポイント </strong> 。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-164">MBAM Status reporting service endpoint</strong>.</span></span> <span data-ttu-id="4f6b2-165">MBAM クライアント BitLocker 暗号化管理を有効にするには、この設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-165">You must configure this setting to enable MBAM Client BitLocker encryption management.</span></span> <span data-ttu-id="4f6b2-166">次のようなエンドポイントの場所を入力します。 <strong> http:// </strong><em> &lt; mbam Administration and Monitoring Server Name &gt; </em><strong> : </strong><em> &lt; web サービスは/MBAMComplianceStatusService/StatusReportingService.svc にバインドされてい &gt; </em><strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-166">Enter an endpoint location that is similar to the following example: <strong>http://</strong><em>&lt;MBAM Administration and Monitoring Server Name&gt;</em><strong>:</strong><em>&lt;port the web service is bound to&gt;</em><strong>/MBAMComplianceStatusService/StatusReportingService.svc</strong>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4f6b2-167">ユーザーの免税ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="4f6b2-167">Configure user exemption policy</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f6b2-168">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="4f6b2-168">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="4f6b2-169">このポリシー設定では、ユーザーに対して BitLocker 暗号化の除外を要求するように指示する、web サイトのアドレス、メールアドレス、または電話番号を構成できます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-169">This policy setting lets you configure a web site address, email address, or phone number that will instruct a user to request an exemption from BitLocker encryption.</span></span></p>
<p><span data-ttu-id="4f6b2-170">このポリシー設定を有効にして、web サイトのアドレス、メールアドレス、または電話番号を指定すると、除外を適用して BitLocker 保護を適用する方法を示すダイアログがユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-170">If you enable this policy setting and provide a web site address, email address, or phone number, users will see a dialog that gives them instructions on how to apply for an exemption from BitLocker protection.</span></span> <span data-ttu-id="4f6b2-171">ユーザーに対して BitLocker 暗号化の適用除外を有効にする方法については、「 <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md)"> ユーザー Bitlocker 暗号化の除外を管理する方法」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-171">For more information about enabling BitLocker encryption exemptions for users, see <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md)">How to Manage User BitLocker Encryption Exemptions</a>.</span></span></p>
<p><span data-ttu-id="4f6b2-172">このポリシー設定を無効にするか、未構成にした場合、除外要求の手順はユーザーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-172">If you either disable or do not configure this policy setting, the exemption request instructions will not be presented to users.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="4f6b2-173">注</span><span class="sxs-lookup"><span data-stu-id="4f6b2-173">Note</span></span></strong><br/><p><span data-ttu-id="4f6b2-174">ユーザーの除外は、コンピューターごとではなく、ユーザーごとに管理されます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-174">User exemption is managed per user, not per computer.</span></span> <span data-ttu-id="4f6b2-175">複数のユーザーが同じコンピューターにログオンしていて、1人のユーザーが除外されていない場合、コンピューターは暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-175">If multiple users log on to the same computer and any one user is not exempt, the computer will be encrypted.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4f6b2-176">カスタマーエクスペリエンス向上プログラムの構成</span><span class="sxs-lookup"><span data-stu-id="4f6b2-176">Configure customer experience improvement program</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f6b2-177">このポリシー設定では、MBAM ユーザーがカスタマーエクスペリエンス向上プログラムに参加する方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-177">This policy setting lets you configure how MBAM users can join the Customer Experience Improvement Program.</span></span> <span data-ttu-id="4f6b2-178">このプログラムでは、コンピューターのハードウェアに関する情報を収集し、ユーザーの作業を中断することなく MBAM を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-178">This program collects information about computer hardware and how users use MBAM without interrupting their work.</span></span> <span data-ttu-id="4f6b2-179">この情報は、Microsoft が改善する MBAM 機能を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-179">The information helps Microsoft to identify which MBAM features to improve.</span></span> <span data-ttu-id="4f6b2-180">Microsoft は、MBAM ユーザを特定したり連絡したりするためにこの情報を使用することはありません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-180">Microsoft will not use this information to identify or contact MBAM users.</span></span></p>
<p><span data-ttu-id="4f6b2-181">このポリシー設定を有効にすると、ユーザーはカスタマーエクスペリエンス向上プログラムに参加できます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-181">If you enable this policy setting, users will be able to join the Customer Experience Improvement Program.</span></span></p>
<p><span data-ttu-id="4f6b2-182">このポリシー設定を無効にすると、ユーザーはカスタマーエクスペリエンス向上プログラムに参加できなくなります。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-182">If you disable this policy setting, users will not be able to join the Customer Experience Improvement Program.</span></span></p>
<p><span data-ttu-id="4f6b2-183">このポリシー設定を構成しない場合、ユーザーにはカスタマーエクスペリエンス向上プログラムに参加するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-183">If you do not configure this policy setting, users will have the option to join the Customer Experience Improvement Program.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="4f6b2-184">固定ドライブのポリシー定義</span><span class="sxs-lookup"><span data-stu-id="4f6b2-184">Fixed Drive Policy Definitions</span></span>


<span data-ttu-id="4f6b2-185">このセクションでは、Microsoft BitLocker の管理と監視に関する、次の GPO ノードで検出される固定ドライブポリシーの定義について説明します。**コンピューター構成** \\ **ポリシー** \\ **管理用テンプレート** \\ **Windows コンポーネント** \\ **MDOP mbam (BitLocker 管理)** \\ **固定ドライブ**。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-185">This section describes Fixed Drive policy definitions for Microsoft BitLocker Administration and Monitoring found at the following GPO node: **Computer Configuration**\\**Policies**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)**\\**Fixed Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4f6b2-186">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="4f6b2-186">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="4f6b2-187">概要と推奨されるポリシー設定</span><span class="sxs-lookup"><span data-stu-id="4f6b2-187">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4f6b2-188">固定データドライブの暗号化設定</span><span class="sxs-lookup"><span data-stu-id="4f6b2-188">Fixed data drive encryption settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f6b2-189">推奨される構成: <strong> 有効</span><span class="sxs-lookup"><span data-stu-id="4f6b2-189">Suggested Configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="4f6b2-190">このポリシー設定を使用すると、固定ドライブを暗号化する必要があるかどうかを管理できます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-190">This policy setting let you manage whether fixed drives must be encrypted.</span></span></p>
<p><span data-ttu-id="4f6b2-191">オペレーティングシステムのボリュームが暗号化される必要がある場合は、[ <strong> 固定データドライブの自動ロックを有効にする] オプションを選択し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-191">If the operating system volume is required to be encrypted, select the <strong>Enable auto-unlock fixed data drive</strong> option.</span></span></p>
<p><span data-ttu-id="4f6b2-192">このポリシーを有効にするとき <strong> </strong> は、固定データドライブの自動ロック解除を許可するか必要としない限り、[固定データドライブのパスワードの使用を構成する] ポリシーを無効にしないでください。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-192">When enabling this policy, you must not disable the <strong>Configure use of password for fixed data drives</strong> policy unless the use of Auto-Unlock for fixed data drives is allowed or required.</span></span></p>
<p><span data-ttu-id="4f6b2-193">固定データドライブの自動ロック解除を使用する必要がある場合は、暗号化されるようにオペレーティングシステムのボリュームを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-193">If you require the use of Auto-Unlock for fixed data drives, you must configure operating system volumes to be encrypted.</span></span></p>
<p><span data-ttu-id="4f6b2-194">このポリシー設定を有効にした場合、ユーザーはすべての固定ドライブを BitLocker で保護する必要があり、ドライブは暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-194">If you enable this policy setting, users are required to put all fixed drives under BitLocker protection, and the drives will be encrypted.</span></span></p>
<p><span data-ttu-id="4f6b2-195">このポリシー設定を構成しない場合、ユーザーは、BitLocker 保護の下に固定ドライブを配置する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-195">If you do not configure this policy setting, users are not required to put fixed drives under BitLocker protection.</span></span> <span data-ttu-id="4f6b2-196">固定データドライブが暗号化された後にこのポリシーを適用すると、MBAM エージェントは暗号化された固定ドライブを暗号化解除します。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-196">If you apply this policy after fixed data drives are encrypted, the MBAM agent decrypts the encrypted fixed drives.</span></span></p>
<p><span data-ttu-id="4f6b2-197">このポリシー設定を無効にした場合、ユーザーは固定データドライブを BitLocker 保護の下に配置することはできません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-197">If you disable this policy setting, users will not be able to put their fixed data drives under BitLocker protection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4f6b2-198">BitLocker で保護されていない固定ドライブへの書き込みアクセスを拒否する</span><span class="sxs-lookup"><span data-stu-id="4f6b2-198">Deny write access to fixed drives not protected by BitLocker</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f6b2-199">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="4f6b2-199">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="4f6b2-200">このポリシー設定は、固定ドライブがコンピューターで書き込み可能であることを確認するために BitLocker の保護が必要かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-200">This policy setting determines whether BitLocker protection is required for fixed drives to be writable on a computer.</span></span> <span data-ttu-id="4f6b2-201">このポリシー設定は、BitLocker を有効にすると適用されます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-201">This policy setting is applied when you turn on BitLocker.</span></span></p>
<p><span data-ttu-id="4f6b2-202">ポリシーが構成されていない場合は、コンピューター上のすべての固定データドライブが読み取りと書き込みのアクセス許可付きでマウントされます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-202">When the policy is not configured, all fixed data drives on the computer are mounted with read and write access.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4f6b2-203">BitLocker で保護された固定ドライブへのアクセスを以前のバージョンの Windows から許可する</span><span class="sxs-lookup"><span data-stu-id="4f6b2-203">Allow access to BitLocker-protected fixed drives from earlier versions of Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f6b2-204">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="4f6b2-204">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="4f6b2-205">このポリシーを有効にすると、Windows Server 2008、Windows Vista、Windows XP、または Windows XP SP2 を実行しているコンピューターで、FAT ファイルシステムの固定ドライブのロックを解除し、表示することができます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-205">Enable this policy to let fixed drives with the FAT file system be unlocked and viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p>
<p><span data-ttu-id="4f6b2-206">ポリシーが有効になっているか、構成されていない場合、FAT ファイルシステムで書式設定された固定ドライブのロックを解除することができ、windows Server 2008、Windows Vista、Windows XP SP3、または Windows XP SP2 を実行しているコンピューターでコンテンツを表示できます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-206">When the policy is enabled or not configured, fixed drives formatted with the FAT file system can be unlocked and their content can be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span> <span data-ttu-id="4f6b2-207">これらのオペレーティングシステムは、BitLocker で保護されたドライブに対する読み取り専用アクセス権を持ちます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-207">These operating systems have read-only access to BitLocker-protected drives.</span></span></p>
<p><span data-ttu-id="4f6b2-208">ポリシーが無効になっている場合、FAT ファイルシステムで書式設定された固定ドライブのロックを解除することはできません。 Windows Server 2008、Windows Vista、Windows XP SP3、または Windows XP SP2 を実行しているコンピューターでは、これらのコンテンツを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-208">When the policy is disabled, fixed drives formatted with the FAT file system cannot be unlocked and their content cannot be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4f6b2-209">固定ドライブのパスワードの使用を構成する</span><span class="sxs-lookup"><span data-stu-id="4f6b2-209">Configure use of password for fixed drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f6b2-210">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="4f6b2-210">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="4f6b2-211">このポリシーを使って、BitLocker で保護された固定データドライブのロックを解除するためにパスワードが必要かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-211">Use this policy to specify whether a password is required to unlock BitLocker-protected fixed data drives.</span></span></p>
<p><span data-ttu-id="4f6b2-212">このポリシー設定を有効にした場合、ユーザーは定義した要件を満たすパスワードを構成できます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-212">If you enable this policy setting, users can configure a password that meets the requirements you define.</span></span> <span data-ttu-id="4f6b2-213">BitLocker では、ドライブで使用できる任意のプロテクターでドライブのロックを解除することができます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-213">BitLocker will allow users to unlock a drive with any of the protectors that are available on the drive.</span></span></p>
<p><span data-ttu-id="4f6b2-214">これらの設定は、ボリュームのロックを解除するときにではなく、BitLocker を有効にするときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-214">These settings are enforced when turning on BitLocker, not when unlocking a volume.</span></span></p>
<p><span data-ttu-id="4f6b2-215">このポリシー設定を無効にした場合、ユーザーはパスワードを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-215">If you disable this policy setting, users are not allowed to use a password.</span></span></p>
<p><span data-ttu-id="4f6b2-216">ポリシーが構成されていない場合、パスワードは既定の設定でサポートされます。パスワードの複雑さの要件は含まれず、8文字しか必要ありません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-216">When the policy is not configured, passwords are supported with the default settings, which do not include password complexity requirements and which require only eight characters.</span></span></p>
<p><span data-ttu-id="4f6b2-217">セキュリティを高めるには、このポリシーを有効にして、[ <strong> 固定データドライブにパスワードを要求する] を選択し </strong> 、[ <strong> パスワードの複雑さを要求する] を選択し </strong> て、必要なパスワードの長さを設定し <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-217">For higher security, enable this policy and select <strong>Require password for fixed data drive</strong>, select <strong>Require password complexity</strong>, and set the desired <strong>minimum password length</strong>.</span></span></p>
<p><span data-ttu-id="4f6b2-218">このポリシー設定を無効にした場合、ユーザーはパスワードを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-218">If you disable this policy setting, users are not allowed to use a password.</span></span></p>
<p><span data-ttu-id="4f6b2-219">このポリシー設定を構成しない場合、パスワードは既定の設定でサポートされます。パスワードの複雑さの要件は含まれません。これには8文字しか必要ありません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-219">If you do not configure this policy setting, passwords will be supported with the default settings, which do not include password complexity requirements and which require only eight characters.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4f6b2-220">BitLocker で保護された固定ドライブの回復方法を選択する</span><span class="sxs-lookup"><span data-stu-id="4f6b2-220">Choose how BitLocker-protected fixed drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f6b2-221">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="4f6b2-221">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="4f6b2-222">BitLocker データ回復エージェントを有効にする、または Active Directory ドメインサービス (AD DS) に BitLocker 回復情報を保存するには、このポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-222">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="4f6b2-223">ポリシーが構成されていない場合、BitLocker データ回復エージェントは許可され、回復情報は AD DS にバックアップされません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-223">When the policy is not configured, the BitLocker data recovery agent is allowed, and recovery information is not backed up to AD DS.</span></span> <span data-ttu-id="4f6b2-224">MBAM は、AD DS にバックアップするための回復情報を必要としません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-224">MBAM does not require recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="4f6b2-225">オペレーティングシステムドライブのポリシー定義</span><span class="sxs-lookup"><span data-stu-id="4f6b2-225">Operating System Drive Policy Definitions</span></span>


<span data-ttu-id="4f6b2-226">このセクションでは、Microsoft BitLocker の管理と監視に使用するオペレーティングシステムドライブのポリシー定義について説明します。**コンピューター構成** \\ **ポリシー** \\ **管理用テンプレート** \\ **Windows コンポーネント** \\ **MDOP mbam (BitLocker 管理)** \\ **オペレーティングシステムドライブ**。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-226">This section describes Operating System Drive policy definitions for Microsoft BitLocker Administration and Monitoring found at the following GPO node: **Computer Configuration**\\**Policies**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)**\\**Operating System Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4f6b2-227">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="4f6b2-227">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="4f6b2-228">概要と推奨されるポリシー設定</span><span class="sxs-lookup"><span data-stu-id="4f6b2-228">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4f6b2-229">オペレーティングシステムドライブの暗号化の設定</span><span class="sxs-lookup"><span data-stu-id="4f6b2-229">Operating system drive encryption settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f6b2-230">推奨される構成: <strong> 有効</span><span class="sxs-lookup"><span data-stu-id="4f6b2-230">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="4f6b2-231">このポリシー設定では、オペレーティングシステムドライブを暗号化する必要があるかどうかを管理できます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-231">This policy setting lets you manage whether the operating system drive must be encrypted.</span></span></p>
<p><span data-ttu-id="4f6b2-232">セキュリティを高めるには、 <strong> </strong> TPM + PIN プロテクターを使って、システム/電源管理/スリープ設定で次のポリシー設定を無効にすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-232">For higher security, consider disabling the following policy settings in <strong>System/Power Management/Sleep Settings</strong> when you enable them with TPM + PIN protector:</span></span></p>
<ul>
<li><p><span data-ttu-id="4f6b2-233">スリープ中 (電源に接続されているとき) にスタンバイ状態 (S1 ~ S3) を許可する</span><span class="sxs-lookup"><span data-stu-id="4f6b2-233">Allow Standby States (S1-S3) When Sleeping (Plugged In)</span></span></p></li>
<li><p><span data-ttu-id="4f6b2-234">スリープ中 (バッテリー) でスタンバイ状態 (S1-S3) を許可する</span><span class="sxs-lookup"><span data-stu-id="4f6b2-234">Allow Standby States (S1-S3) When Sleeping (On Battery)</span></span></p></li>
</ul>
<p><span data-ttu-id="4f6b2-235">Microsoft Windows 8 以降を実行していて、TPM がないコンピューターで BitLocker を使用する場合は、[ <strong> 互換性のある tpm なしで bitlocker を許可する] チェックボックスをオンにし </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-235">If you are running Microsoft Windows 8 or later, and you want to use BitLocker on a computer without a TPM, select the <strong>Allow BitLocker without a compatible TPM</strong> check box.</span></span> <span data-ttu-id="4f6b2-236">このモードでは、起動時にパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-236">In this mode, a password is required for startup.</span></span> <span data-ttu-id="4f6b2-237">パスワードを忘れた場合は、BitLocker の回復オプションのいずれかを使ってドライブにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-237">If you forget the password, you have to use one of the BitLocker recovery options to access the drive.</span></span></p>
<p><span data-ttu-id="4f6b2-238">互換性のある TPM が搭載されたコンピューターでは、2種類の認証方法を使用して、暗号化されたデータの保護を強化できます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-238">On a computer with a compatible TPM, two types of authentication methods can be used at startup to provide added protection for encrypted data.</span></span> <span data-ttu-id="4f6b2-239">コンピューターの起動時には、TPM のみを認証に使うことができます。また、暗証番号 (PIN) の入力を要求することもできます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-239">When the computer starts, it can use only the TPM for authentication, or it can also require the entry of a personal identification number (PIN).</span></span></p>
<p><span data-ttu-id="4f6b2-240">このポリシー設定を有効にした場合、ユーザーは、オペレーティングシステムドライブを [BitLocker 保護] の下に置く必要があり、ドライブは暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-240">If you enable this policy setting, users have to put the operating system drive under BitLocker protection, and the drive will be encrypted.</span></span></p>
<p><span data-ttu-id="4f6b2-241">このポリシーを無効にした場合、ユーザーは、オペレーティングシステムドライブを BitLocker で保護することはできません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-241">If you disable this policy, users will not be able to put the operating system drive under BitLocker protection.</span></span> <span data-ttu-id="4f6b2-242">オペレーティングシステムドライブが暗号化された後にこのポリシーを適用すると、ドライブは暗号化解除されます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-242">If you apply this policy after the operating system drive is encrypted, the drive will be decrypted.</span></span></p>
<p><span data-ttu-id="4f6b2-243">このポリシーを構成しない場合、オペレーティングシステムドライブは、BitLocker による保護の下に配置する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-243">If you do not configure this policy, the operating system drive is not required to be placed under BitLocker protection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4f6b2-244">TPM プラットフォームの検証プロファイルを構成する</span><span class="sxs-lookup"><span data-stu-id="4f6b2-244">Configure TPM platform validation profile</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f6b2-245">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="4f6b2-245">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="4f6b2-246">このポリシー設定では、コンピューター上の TPM セキュリティハードウェアが BitLocker 暗号化キーをセキュリティで保護する方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-246">This policy setting lets you configure how the TPM security hardware on a computer secures the BitLocker encryption key.</span></span> <span data-ttu-id="4f6b2-247">このポリシー設定は、コンピューターに互換性のある TPM が搭載されていない場合、または TPM 保護で BitLocker が既に有効になっている場合は適用されません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-247">This policy setting does not apply if the computer does not have a compatible TPM or if BitLocker has already been turned on with TPM protection.</span></span></p>
<p><span data-ttu-id="4f6b2-248">このポリシー設定が構成されていない場合、TPM では、既定のプラットフォーム検証プロファイルまたはセットアップスクリプトで指定されたプラットフォーム検証プロファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-248">When this policy setting is not configured, the TPM uses the default platform validation profile or the platform validation profile that is specified by the setup script.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4f6b2-249">BitLocker で保護されたオペレーティングシステムドライブの回復方法を選択する</span><span class="sxs-lookup"><span data-stu-id="4f6b2-249">Choose how BitLocker-protected operating system drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f6b2-250">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="4f6b2-250">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="4f6b2-251">BitLocker データ回復エージェントを有効にする、または Active Directory ドメインサービス (AD DS) に BitLocker 回復情報を保存するには、このポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-251">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="4f6b2-252">このポリシーが構成されていない場合、データ回復エージェントは許可され、回復情報は AD DS にバックアップされません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-252">When this policy is not configured, the data recovery agent is allowed, and recovery information is not backed up to AD DS.</span></span></p>
<p><span data-ttu-id="4f6b2-253">MBAM 操作では、AD DS に回復情報をバックアップする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-253">MBAM operation does not require recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="4f6b2-254">リムーバブルドライブのポリシー定義</span><span class="sxs-lookup"><span data-stu-id="4f6b2-254">Removable Drive Policy Definitions</span></span>


<span data-ttu-id="4f6b2-255">このセクションでは、Microsoft BitLocker の管理と監視に使用されるリムーバブルドライブポリシーの定義について説明します。次の GPO ノードで検出されます。**コンピューター構成** \\ **ポリシー** \\ **管理用テンプレート** \\ **Windows コンポーネント** \\ **MDOP mbam (BitLocker 管理)**  \\  **リムーバブルドライブ**。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-255">This section describes Removable Drive Policy definitions for Microsoft BitLocker Administration and Monitoring found at the following GPO node: **Computer Configuration**\\**Policies**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)** \\ **Removable Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4f6b2-256">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="4f6b2-256">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="4f6b2-257">概要と推奨されるポリシー設定</span><span class="sxs-lookup"><span data-stu-id="4f6b2-257">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4f6b2-258">リムーバブルドライブでの BitLocker の使用を制御する</span><span class="sxs-lookup"><span data-stu-id="4f6b2-258">Control use of BitLocker on removable drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f6b2-259">推奨される構成: <strong> 有効</span><span class="sxs-lookup"><span data-stu-id="4f6b2-259">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="4f6b2-260">このポリシーは、リムーバブルデータドライブでの BitLocker の使用を制御します。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-260">This policy controls the use of BitLocker on removable data drives.</span></span></p>
<p><span data-ttu-id="4f6b2-261">[ <strong> リムーバブルデータドライブ上に bitlocker 保護を適用することをユーザーに許可する] オプションを有効にして、 </strong> ユーザーがリムーバブルデータドライブで bitlocker セットアップウィザードを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-261">Enable the <strong>Allow users to apply BitLocker protection on removable data drives</strong> option to allow users to run the BitLocker setup wizard on a removable data drive.</span></span></p>
<p><span data-ttu-id="4f6b2-262"><strong>[リムーバブルデータドライブ上の bitlocker を一時停止して暗号化を解除する] オプションを有効にして、 </strong> ユーザーがドライブから bitlocker ドライブ暗号化を削除できるようにします。または、メンテナンスが実行されている間、暗号化を中断します。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-262">Enable the <strong>Allow users to suspend and decrypt BitLocker on removable data drives</strong> option to allow users to remove BitLocker drive encryption from the drive or to suspend the encryption while maintenance is performed.</span></span></p>
<p><span data-ttu-id="4f6b2-263">このポリシーを有効にして、[ <strong> リムーバブルデータドライブに対する BitLocker 保護の適用を許可する] オプションが選択されている場合 </strong> 、Mbam クライアントは、リムーバブルドライブに関する回復情報を mbam キー回復サーバーに保存し、パスワードが失われた場合にユーザーがドライブを回復できるようにします。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-263">When this policy is enabled and the <strong>Allow users to apply BitLocker protection on removable data drives</strong> option is selected, the MBAM Client saves the recovery information about removable drives to the MBAM key recovery server and allows users to recover the drive if the password is lost.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4f6b2-264">BitLocker で保護されていないリムーバブル ドライブへの書き込みアクセスを拒否する</span><span class="sxs-lookup"><span data-stu-id="4f6b2-264">Deny write access to removable drives not protected by BitLocker</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f6b2-265">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="4f6b2-265">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="4f6b2-266">このポリシーを有効にして、BitLocker で保護されたドライブへの書き込みアクセスのみを許可します。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-266">Enable this policy to allow only write access to BitLocker protected drives.</span></span></p>
<p><span data-ttu-id="4f6b2-267">このポリシーを有効にすると、コンピューター上のすべてのリムーバブルデータドライブは、書き込みアクセスが許可される前に暗号化が必要になります。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-267">When this policy is enabled, all removable data drives on the computer require encryption before write access is allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4f6b2-268">以前のバージョンの Windows から BitLocker で保護されているリムーバブルドライブへのアクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="4f6b2-268">Allow access to BitLocker-protected removable drives from earlier versions of Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f6b2-269">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="4f6b2-269">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="4f6b2-270">このポリシーを有効にすると、FAT ファイルシステムを実行しているコンピューターで、windows Server 2008、Windows Vista、Windows XP、または Windows XP SP2 を実行しているコンピューターで、固定ドライブのロックを解除して表示することができます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-270">Enable this policy to allow fixed drives with the FAT file system to be unlocked and viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p>
<p><span data-ttu-id="4f6b2-271">このポリシーが構成されていない場合は、FAT ファイルシステムで書式設定されたリムーバブルデータドライブは、Windows Server 2008、Windows Vista、Windows XP、SP3、または Windows XP を実行しているコンピューターでロックを解除することができ、そのコンテンツは表示できます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-271">When this policy is not configured, removable data drives formatted with the FAT file system can be unlocked on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2, and their content can be viewed.</span></span> <span data-ttu-id="4f6b2-272">これらのオペレーティングシステムは、BitLocker で保護されたドライブに対する読み取り専用アクセス権を持ちます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-272">These operating systems have read-only access to BitLocker-protected drives.</span></span></p>
<p><span data-ttu-id="4f6b2-273">ポリシーが無効になっている場合、FAT ファイルシステムで書式設定されたリムーバブルドライブのロックを解除することはできません。 Windows Server 2008、Windows Vista、Windows XP SP3、または Windows XP SP2 を実行しているコンピューターでは、これらのコンテンツを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-273">When the policy is disabled, removable drives formatted with the FAT file system cannot be unlocked and their content cannot be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4f6b2-274">リムーバブルデータドライブのパスワードの使用を構成する</span><span class="sxs-lookup"><span data-stu-id="4f6b2-274">Configure use of password for removable data drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f6b2-275">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="4f6b2-275">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="4f6b2-276">このポリシーを有効にして、リムーバブルデータドライブのパスワード保護を構成します。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-276">Enable this policy to configure password protection on removable data drives.</span></span></p>
<p><span data-ttu-id="4f6b2-277">このポリシーが構成されていない場合、パスワードは、パスワードの複雑さの要件を含まず、8文字のみを必要とする既定の設定でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-277">When this policy is not configured, passwords are supported with the default settings, which do not include password complexity requirements and which require only eight characters.</span></span></p>
<p><span data-ttu-id="4f6b2-278">セキュリティを強化するために、このポリシーを有効にして、 <strong> [リムーバブルデータドライブにパスワードを要求する] をオンにし </strong> 、[パスワードの複雑さを要求する] を選択し、推奨される <strong> </strong> <strong> パスワードの最小文字数を設定し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-278">For increased security, you may enable this policy and check <strong>Require password for removable data drive</strong>, select <strong>Require password complexity</strong>, and set the preferred <strong>minimum password length</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4f6b2-279">BitLocker で保護されたリムーバブルドライブの回復方法を選択する</span><span class="sxs-lookup"><span data-stu-id="4f6b2-279">Choose how BitLocker-protected removable drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f6b2-280">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="4f6b2-280">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="4f6b2-281">BitLocker データ回復エージェントを有効にする、または Active Directory ドメインサービス (AD DS) に BitLocker 回復情報を保存するには、このポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-281">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="4f6b2-282">[未構成] に設定すると、 <strong> </strong> データ回復エージェントが許可され、回復情報は AD DS にバックアップされません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-282">When set to <strong>Not Configured</strong>, the data recovery agent is allowed and recovery information is not backed up to AD DS.</span></span></p>
<p><span data-ttu-id="4f6b2-283">MBAM 操作では、AD DS に回復情報をバックアップする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4f6b2-283">MBAM operation does not require recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="4f6b2-284">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4f6b2-284">Related topics</span></span>


[<span data-ttu-id="4f6b2-285">MBAM 2.0 展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="4f6b2-285">MBAM 2.0 Deployment Prerequisites</span></span>](mbam-20-deployment-prerequisites-mbam-2.md)









