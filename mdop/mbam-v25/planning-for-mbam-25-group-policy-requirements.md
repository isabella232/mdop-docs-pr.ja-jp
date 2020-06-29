---
title: MBAM 2.5 グループ ポリシー要件の計画
description: MBAM 2.5 グループ ポリシー要件の計画
author: dansimp
ms.assetid: 82d545dc-3fbf-4b46-b62f-47fe178a7c44
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4beeb9f88f16e7d48d145861c398a90fa29f3491
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823767"
---
# <span data-ttu-id="93111-103">MBAM 2.5 グループ ポリシー要件の計画</span><span class="sxs-lookup"><span data-stu-id="93111-103">Planning for MBAM 2.5 Group Policy Requirements</span></span>


<span data-ttu-id="93111-104">以下の情報を使用して、組織内で Microsoft BitLocker 管理および監視 (MBAM) クライアントコンピューターを管理するために使用できる BitLocker プロテクターの種類を決定してください。</span><span class="sxs-lookup"><span data-stu-id="93111-104">Use the following information to determine the types of BitLocker protectors that you can use to manage the Microsoft BitLocker Administration and Monitoring (MBAM) client computers in your enterprise.</span></span>

## <span data-ttu-id="93111-105">MBAM でサポートされている BitLocker プロテクターの種類</span><span class="sxs-lookup"><span data-stu-id="93111-105">Types of BitLocker protectors that MBAM supports</span></span>


<span data-ttu-id="93111-106">MBAM は、次の種類の BitLocker プロテクターをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="93111-106">MBAM supports the following types of BitLocker protectors.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="93111-107">ドライブまたはボリュームの種類</span><span class="sxs-lookup"><span data-stu-id="93111-107">Type of drive or volume</span></span></th>
<th align="left"><span data-ttu-id="93111-108">サポートされている BitLocker プロテクター</span><span class="sxs-lookup"><span data-stu-id="93111-108">Supported BitLocker protectors</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93111-109">オペレーティングシステムボリューム</span><span class="sxs-lookup"><span data-stu-id="93111-109">Operating system volumes</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="93111-110">トラステッド プラットフォーム モジュール (TPM)</span><span class="sxs-lookup"><span data-stu-id="93111-110">Trusted Platform Module (TPM)</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="93111-111">TPM + PIN</span><span class="sxs-lookup"><span data-stu-id="93111-111">TPM + PIN</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="93111-112">TPM + USB キー </strong> – MBAM をインストールする前にオペレーティングシステムのボリュームが暗号化されている場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="93111-112">TPM + USB key</strong> – supported only when the operating system volume is encrypted before MBAM is installed</span></span></p></li>
<li><p><strong><span data-ttu-id="93111-113">TPM + PIN + USB キーは </strong> - 、mbam をインストールする前にオペレーティングシステムのボリュームが暗号化されている場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="93111-113">TPM + PIN + USB key</strong> - supported only when the operating system volume is encrypted before MBAM is installed</span></span></p></li>
<li><p><strong><span data-ttu-id="93111-114">パスワードは </strong> - 、Windows to Go デバイス、固定データドライブ、windows 8、windows 8.1、TPM を搭載していない windows 10 デバイスでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="93111-114">Password</strong> - supported only for Windows To Go devices, fixed data drives, and Windows 8, Windows 8.1, and Windows 10 devices that do not have a TPM</span></span></p></li>
<li><p><strong><span data-ttu-id="93111-115">数値パスワードは </strong> - ボリューム暗号化の一部として自動的に適用され、Windows 7 で FIPS モードを除き、構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="93111-115">Numerical password</strong> - applied automatically as part of volume encryption and does not need to be configured except in FIPS mode on Windows 7</span></span></p></li>
<li><p><strong><span data-ttu-id="93111-116">データ回復エージェント (DRA)</span><span class="sxs-lookup"><span data-stu-id="93111-116">Data recovery agent (DRA)</span></span></strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93111-117">固定データドライブ</span><span class="sxs-lookup"><span data-stu-id="93111-117">Fixed data drives</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="93111-118">パスワード</span><span class="sxs-lookup"><span data-stu-id="93111-118">Password</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="93111-119">自動ロック解除</span><span class="sxs-lookup"><span data-stu-id="93111-119">Auto-unlock</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="93111-120">数値パスワードは </strong> - ボリューム暗号化の一部として自動的に適用され、Windows 7 で FIPS モードを除き、構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="93111-120">Numerical password</strong> - applied automatically as part of volume encryption and does not need to be configured except in FIPS mode on Windows 7</span></span></p></li>
<li><p><strong><span data-ttu-id="93111-121">データ回復エージェント (DRA)</span><span class="sxs-lookup"><span data-stu-id="93111-121">Data recovery agent (DRA)</span></span></strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93111-122">リムーバブルドライブ</span><span class="sxs-lookup"><span data-stu-id="93111-122">Removable drives</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="93111-123">パスワード</span><span class="sxs-lookup"><span data-stu-id="93111-123">Password</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="93111-124">自動ロック解除</span><span class="sxs-lookup"><span data-stu-id="93111-124">Auto-unlock</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="93111-125">数値パスワードは </strong> - ボリューム暗号化の一部として自動的に適用され、構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="93111-125">Numerical password</strong> - applied automatically as part of volume encryption and does not need to be configured</span></span></p></li>
<li><p><strong><span data-ttu-id="93111-126">データ回復エージェント (DRA)</span><span class="sxs-lookup"><span data-stu-id="93111-126">Data recovery agent (DRA)</span></span></strong></p></li>
</ul></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="93111-127">使用済みスペース暗号化の BitLocker ポリシーのサポート</span><span class="sxs-lookup"><span data-stu-id="93111-127">Support for the Used Space Encryption BitLocker policy</span></span>

<span data-ttu-id="93111-128">MBAM 2.5 SP1 では、BitLocker グループポリシーによって使用されるスペースの暗号化を有効にすると、MBAM クライアントによって受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="93111-128">In MBAM 2.5 SP1, if you enable Used Space Encryption via BitLocker Group policy, the MBAM Client honors it.</span></span>

<span data-ttu-id="93111-129">このグループポリシー設定は、**オペレーティングシステムドライブでの [ドライブの暗号化の種類の強制**] と呼ばれ、次の GPO ノードにあります。**コンピューターの構成** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **BitLocker ドライブ暗号化** &gt; **オペレーティングシステムドライブ**。</span><span class="sxs-lookup"><span data-stu-id="93111-129">This Group Policy setting is called **Enforce drive encryption type on operating system drives** and is located in the following GPO node: **Computer Configuration** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **BitLocker Drive Encryption** &gt; **Operating System Drives**.</span></span> <span data-ttu-id="93111-130">このポリシーを有効にして、**使用領域のみの暗号化**として暗号化の種類を選択した場合、mbam ではポリシーが優先され、BitLocker はボリュームで使用されているディスク領域のみを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="93111-130">If you enable this policy and select the encryption type as **Used Space Only encryption**, MBAM will honor the policy and BitLocker will only encrypt disk space that is used on the volume.</span></span>

## <span data-ttu-id="93111-131">MBAM グループポリシーテンプレートを取得して設定を編集する方法</span><span class="sxs-lookup"><span data-stu-id="93111-131">How to get the MBAM Group Policy Templates and edit the settings</span></span>


<span data-ttu-id="93111-132">MBAM グループポリシー設定を構成する準備ができたら、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="93111-132">When you are ready to configure the MBAM Group Policy settings you want, do the following:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="93111-133">手順</span><span class="sxs-lookup"><span data-stu-id="93111-133">Steps to follow</span></span></th>
<th align="left"><span data-ttu-id="93111-134">手順を表示する場所</span><span class="sxs-lookup"><span data-stu-id="93111-134">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93111-135"><a href="https://go.microsoft.com/fwlink/p/?LinkId=393941" data-raw-source="[How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941)">MDOP グループポリシー (admx) テンプレートの取得方法から MBAM グループポリシーテンプレートをコピー </a> し、グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) を実行できるコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="93111-135">Copy the MBAM Group Policy Templates from <a href="https://go.microsoft.com/fwlink/p/?LinkId=393941" data-raw-source="[How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941)">How to Get MDOP Group Policy (.admx) Templates</a> and install them on a computer that is capable of running the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span></p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)"><span data-ttu-id="93111-136">MBAM 2.5 グループ ポリシー テンプレートのコピー</span><span class="sxs-lookup"><span data-stu-id="93111-136">Copying the MBAM 2.5 Group Policy Templates</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93111-137">エンタープライズで使用するグループポリシー設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="93111-137">Configure the Group Policy settings that you want to use in your enterprise.</span></span></p></td>
<td align="left"><p><a href="editing-the-mbam-25-group-policy-settings.md" data-raw-source="[Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md)"><span data-ttu-id="93111-138">MBAM 2.5 グループ ポリシー設定の編集</span><span class="sxs-lookup"><span data-stu-id="93111-138">Editing the MBAM 2.5 Group Policy Settings</span></span></a></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="93111-139">MBAM グループポリシー設定の説明</span><span class="sxs-lookup"><span data-stu-id="93111-139">Descriptions of the MBAM Group Policy settings</span></span>


<span data-ttu-id="93111-140">**MDOP MBAM (BitLocker Management)** gpo ノードには、4つのグローバルポリシー設定と4つの子 GPO ノード (**クライアント管理**、**固定ドライブ**、**オペレーティングシステムドライブ**、および**リムーバブルドライブ**) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="93111-140">The **MDOP MBAM (BitLocker Management)** GPO node contains four global policy settings and four child GPO nodes: **Client Management**, **Fixed Drive**, **Operating System Drive**, and **Removable Drive**.</span></span> <span data-ttu-id="93111-141">以下のセクションでは、MBAM グループポリシー設定の設定と提案について説明します。</span><span class="sxs-lookup"><span data-stu-id="93111-141">The following sections describe and suggest settings for the MBAM Group Policy settings.</span></span>

**<span data-ttu-id="93111-142">重要</span><span class="sxs-lookup"><span data-stu-id="93111-142">Important</span></span>**  
<span data-ttu-id="93111-143">**BitLocker ドライブ暗号化**ノードのグループポリシー設定を変更しないようにします。または、mbam が正しく動作しません。</span><span class="sxs-lookup"><span data-stu-id="93111-143">Do not change the Group Policy settings in the **BitLocker Drive Encryption** node, or MBAM will not work correctly.</span></span> <span data-ttu-id="93111-144">MBAM は、 **MDOP mbam (BitLocker Management)** ノードの設定を構成するときに、このノードの設定を自動的に構成します。</span><span class="sxs-lookup"><span data-stu-id="93111-144">MBAM automatically configures the settings in this node for you when you configure the settings in the **MDOP MBAM (BitLocker Management)** node.</span></span>



### <span data-ttu-id="93111-145">グローバルグループポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="93111-145">Global Group Policy definitions</span></span>

<span data-ttu-id="93111-146">以下のセクションでは、mbam グローバルグループポリシー定義について説明します。**コンピューター構成** &gt; **ポリシー** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **MDOP mbam (BitLocker 管理)**。</span><span class="sxs-lookup"><span data-stu-id="93111-146">This section describes MBAM Global Group Policy definitions at the following GPO node: **Computer Configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="93111-147">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="93111-147">Policy name</span></span></th>
<th align="left"><span data-ttu-id="93111-148">概要と推奨されるグループポリシー設定</span><span class="sxs-lookup"><span data-stu-id="93111-148">Overview and suggested Group Policy settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93111-149">ドライブの暗号化方法と暗号強度を選ぶ</span><span class="sxs-lookup"><span data-stu-id="93111-149">Choose drive encryption method and cipher strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-150">推奨される構成: <strong> 有効</span><span class="sxs-lookup"><span data-stu-id="93111-150">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="93111-151">特定の暗号化方法と暗号強度を使用するように、このポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="93111-151">Configure this policy to use a specific encryption method and cipher strength.</span></span></p>
<p><span data-ttu-id="93111-152">このポリシーが構成されていない場合、BitLocker では、ディフューザー付き AES 128 ビットという既定の暗号化方法が使用されます。</span><span class="sxs-lookup"><span data-stu-id="93111-152">When this policy is not configured, BitLocker uses the default encryption method: AES 128-bit with Diffuser.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="93111-153">注</span><span class="sxs-lookup"><span data-stu-id="93111-153">Note</span></span></strong><br/><p><span data-ttu-id="93111-154">BitLocker コンピューターのコンプライアンスレポートの問題が発生すると &quot; &quot; 、既定値を使用している場合でも、暗号強度に対して [不明] と表示されます。</span><span class="sxs-lookup"><span data-stu-id="93111-154">An issue with the BitLocker Computer Compliance report causes it to display &quot;unknown&quot; for the cipher strength, even if you are using the default value.</span></span> <span data-ttu-id="93111-155">この問題を回避するには、この設定を有効にして暗号強度の値を設定してください。</span><span class="sxs-lookup"><span data-stu-id="93111-155">To work around this issue, make sure you enable this setting and set a value for cipher strength.</span></span></p>
</div>
<div>

</div>
<ul>
<li><p><span data-ttu-id="93111-156">AES 128 ビットディフューザー付き AES – Windows 7 のみ</span><span class="sxs-lookup"><span data-stu-id="93111-156">AES 128-bit with Diffuser – for Windows 7 only</span></span></p></li>
<li><p><span data-ttu-id="93111-157">Windows 8、Windows 8.1、Windows 10 用の AES 128</span><span class="sxs-lookup"><span data-stu-id="93111-157">AES 128 for Windows 8, Windows 8.1, and Windows 10</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93111-158">再起動時にメモリの上書きを防止する</span><span class="sxs-lookup"><span data-stu-id="93111-158">Prevent memory overwrite on restart</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-159">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="93111-159">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="93111-160">このポリシーを構成して、再起動時にメモリ内の BitLocker シークレットを上書きせずに、再起動のパフォーマンスを向上させます。</span><span class="sxs-lookup"><span data-stu-id="93111-160">Configure this policy to improve restart performance without overwriting BitLocker secrets in memory on restart.</span></span></p>
<p><span data-ttu-id="93111-161">このポリシーが構成されていない場合、コンピューターを再起動すると、BitLocker シークレットがメモリから削除されます。</span><span class="sxs-lookup"><span data-stu-id="93111-161">When this policy is not configured, BitLocker secrets are removed from memory when the computer restarts.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93111-162">スマートカード証明書の使用規則を検証する</span><span class="sxs-lookup"><span data-stu-id="93111-162">Validate smart card certificate usage rule</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-163">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="93111-163">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="93111-164">スマートカード証明書ベースの BitLocker 保護を使用するように、このポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="93111-164">Configure this policy to use smartcard certificate-based BitLocker protection.</span></span></p>
<p><span data-ttu-id="93111-165">このポリシーが構成されていない場合は、既定のオブジェクト識別子1.3.6.1.4.1.311.67.1.1 が証明書の指定に使用されます。</span><span class="sxs-lookup"><span data-stu-id="93111-165">When this policy is not configured, the default object identifier 1.3.6.1.4.1.311.67.1.1 is used to specify a certificate.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93111-166">組織固有の識別子を指定する</span><span class="sxs-lookup"><span data-stu-id="93111-166">Provide the unique identifiers for your organization</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-167">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="93111-167">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="93111-168">証明書ベースのデータ回復エージェントまたは BitLocker To Go リーダーを使用するように、このポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="93111-168">Configure this policy to use a certificate-based data recovery agent or the BitLocker To Go reader.</span></span></p>
<p><span data-ttu-id="93111-169">このポリシーが構成されていない場合、[ <strong> id </strong> ] フィールドは使用されません。</span><span class="sxs-lookup"><span data-stu-id="93111-169">When this policy is not configured, the <strong>Identification</strong> field is not used.</span></span></p>
<p><span data-ttu-id="93111-170">会社でより高いセキュリティの測定が必要な場合は、[id] フィールドを構成して、 <strong> </strong> すべての USB デバイスでこのフィールドセットが設定され、このフィールドがこのグループポリシー設定に合わせて調整されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="93111-170">If your company requires higher security measurements, you can configure the <strong>Identification</strong> field to make sure that all USB devices have this field set and that they are aligned with this Group Policy setting.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="93111-171">クライアント管理グループポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="93111-171">Client Management Group Policy definitions</span></span>

<span data-ttu-id="93111-172">以下のセクションでは、mbam のクライアント管理ポリシー定義について説明します。**コンピューター構成** &gt; **ポリシー** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **MDOP mbam (BitLocker 管理)** &gt; **クライアントの管理**。</span><span class="sxs-lookup"><span data-stu-id="93111-172">This section describes Client Management policy definitions for MBAM at the following GPO node: **Computer Configuration** &gt; **Policies** &gt;**Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)** &gt; **Client Management**.</span></span>

<span data-ttu-id="93111-173">次の表に示すように、スタンドアロンおよび System Center Configuration Manager の統合トポロジに対して同じグループポリシー設定を設定することができます。構成マネージャーの統合トポロジを使用している場合は、「 **Mbam service &gt; Mbam Status reporting service Endpoint の構成**」の設定を無効にします。</span><span class="sxs-lookup"><span data-stu-id="93111-173">You can set the same Group Policy settings for the Stand-alone and System Center Configuration Manager Integration topologies, with one exception: Disable the **Configure MBAM Services &gt; MBAM Status reporting service endpoint** setting if you are using the Configuration Manager Integration topology, as indicated in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="93111-174">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="93111-174">Policy name</span></span></th>
<th align="left"><span data-ttu-id="93111-175">概要と推奨されるグループポリシー設定</span><span class="sxs-lookup"><span data-stu-id="93111-175">Overview and suggested Group Policy settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93111-176">MBAM サービスを設定する</span><span class="sxs-lookup"><span data-stu-id="93111-176">Configure MBAM Services</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-177">推奨される構成: <strong> 有効</span><span class="sxs-lookup"><span data-stu-id="93111-177">Suggested configuration: <strong>Enabled</span></span></strong></p>
<ul>
<li><p><strong><span data-ttu-id="93111-178">MBAM Recovery and Hardware service endpoint </strong> 。</span><span class="sxs-lookup"><span data-stu-id="93111-178">MBAM Recovery and Hardware service endpoint</strong>.</span></span> <span data-ttu-id="93111-179">MBAM クライアント BitLocker 暗号化管理を有効にするには、この設定を使います。</span><span class="sxs-lookup"><span data-stu-id="93111-179">Use this setting to enable MBAM Client BitLocker encryption management.</span></span> <span data-ttu-id="93111-180">次の例のようなエンドポイントの場所を入力します。 <strong> http (s)// </strong><em> &lt; mbam 管理と監視サーバー名 &gt; </em><strong> : </strong><em> &lt; web サービスが/MBAMRecoveryAndHardwareService/CoreService.svc にバインドさ &gt; </em><strong> </strong> れているポート。</span><span class="sxs-lookup"><span data-stu-id="93111-180">Enter an endpoint location that is similar to the following example: <strong>http(s)://</strong><em>&lt;MBAM Administration and Monitoring Server Name&gt;</em><strong>:</strong><em>&lt;the port the web service is bound to&gt;</em><strong>/MBAMRecoveryAndHardwareService/CoreService.svc</strong>.</span></span></p></li>
<li><p><strong><span data-ttu-id="93111-181">保存する BitLocker 回復情報を選択し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="93111-181">Select BitLocker recovery information to store</strong>.</span></span> <span data-ttu-id="93111-182">このポリシー設定では、BitLocker 回復情報をバックアップするためのキー回復サービスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="93111-182">This policy setting lets you configure the key recovery service to back up BitLocker recovery information.</span></span> <span data-ttu-id="93111-183">また、レポートを収集するためのステータスレポートサービスを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="93111-183">It also lets you configure a status reporting service for collecting reports.</span></span> <span data-ttu-id="93111-184">ポリシーには、BitLocker によって暗号化されたデータを回復するための管理方法が用意されており、重要な情報がないためにデータの損失を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="93111-184">The policy provides an administrative method of recovering data encrypted by BitLocker to prevent data loss due to the lack of key information.</span></span> <span data-ttu-id="93111-185">状態レポートとキー回復アクティビティは、自動的に、構成されたレポートサーバーの場所に自動的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="93111-185">The status report and key recovery activity are automatically and silently sent to the configured report server location.</span></span></p>
<p><span data-ttu-id="93111-186">このポリシー設定を構成しなかった場合、または無効にした場合、キーの回復情報は保存されず、状態レポートとキー回復操作はサーバーに報告されません。</span><span class="sxs-lookup"><span data-stu-id="93111-186">If you do not configure this policy setting or if you disable it, the key recovery information is not saved, and the status report and key recovery activity are not reported to the server.</span></span> <span data-ttu-id="93111-187">この設定が <strong> [回復パスワードとキーパッケージ] に設定されている場合 </strong> 、回復パスワードとキーパッケージは自動的に、構成されたキー回復サーバーの場所に自動的にバックアップされます。</span><span class="sxs-lookup"><span data-stu-id="93111-187">When this setting is set to <strong>Recovery Password and key package</strong>, the recovery password and key package are automatically and silently backed up to the configured key recovery server location.</span></span></p></li>
<li><p><strong><span data-ttu-id="93111-188">クライアントチェックの状態の頻度を分単位で入力し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="93111-188">Enter client checking status frequency in minutes</strong>.</span></span> <span data-ttu-id="93111-189">このポリシー設定は、クライアントがクライアントコンピューター上の BitLocker 保護ポリシーと状態を確認する頻度を管理します。</span><span class="sxs-lookup"><span data-stu-id="93111-189">This policy setting manages how frequently the client checks the BitLocker protection policies and status on the client computer.</span></span> <span data-ttu-id="93111-190">このポリシーは、クライアントのコンプライアンスの状態をサーバーに保存する頻度も管理します。</span><span class="sxs-lookup"><span data-stu-id="93111-190">This policy also manages how frequently the client compliance status is saved to the server.</span></span> <span data-ttu-id="93111-191">クライアントは、クライアントコンピューター上の BitLocker 保護ポリシーと状態を確認し、構成された頻度でクライアント回復キーもバックアップします。</span><span class="sxs-lookup"><span data-stu-id="93111-191">The client checks the BitLocker protection policies and status on the client computer and also backs up the client recovery key at the configured frequency.</span></span></p>
<p><span data-ttu-id="93111-192">この頻度は、お客様の会社によって設定された要件に基づいて、コンピューターのコンプライアンスの状態と、クライアント回復キーをバックアップする頻度に基づいて設定します。</span><span class="sxs-lookup"><span data-stu-id="93111-192">Set this frequency based on the requirement set by your company on how frequently to check the compliance status of the computer and how frequently to back up the client recovery key.</span></span></p></li>
<li><p><strong><span data-ttu-id="93111-193">MBAM Status reporting service エンドポイント:</span><span class="sxs-lookup"><span data-stu-id="93111-193">MBAM Status reporting service endpoint:</span></span></strong></p>
<p><strong><span data-ttu-id="93111-194">スタンドアロンのトポロジの MBAM の場合 </strong> : Mbam クライアント BitLocker 暗号化管理を有効にするには、この設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93111-194">For MBAM in a Stand-alone topology</strong>: You must configure this setting to enable MBAM Client BitLocker encryption management.</span></span></p>
<p><span data-ttu-id="93111-195">次の例のようなエンドポイントの場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="93111-195">Enter an endpoint location that is similar to the following example:</span></span></p>
<p><strong><span data-ttu-id="93111-196">http (s)/ </strong><em> &lt; mbam 管理と監視サーバー名 &gt; </em><strong> : </strong><em> &lt; web サービスが/MBAMComplianceStatusService/StatusReportingService.svc にバインドされているポート &gt; </em><strong></span><span class="sxs-lookup"><span data-stu-id="93111-196">http(s)://</strong><em>&lt;MBAM Administration and Monitoring Server Name&gt;</em><strong>:</strong><em>&lt;the port the web service is bound to&gt;</em><strong>/MBAMComplianceStatusService/StatusReportingService.svc</span></span></strong></p>
<p><strong><span data-ttu-id="93111-197">Configuration Manager の統合トポロジの MBAM の場合 </strong> : この設定を無効にします。</span><span class="sxs-lookup"><span data-stu-id="93111-197">For MBAM in the Configuration Manager Integration topology</strong>: Disable this setting.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93111-198">ユーザーの免税ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="93111-198">Configure user exemption policy</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-199">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="93111-199">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="93111-200">このポリシー設定では、ユーザーに対して BitLocker 暗号化の除外を要求するように指示する web サイトアドレス、メールアドレス、または電話番号を構成できます。</span><span class="sxs-lookup"><span data-stu-id="93111-200">This policy setting lets you configure a website address, email address, or phone number that instructs a user to request an exemption from BitLocker encryption.</span></span></p>
<p><span data-ttu-id="93111-201">このポリシー設定を有効にして、web サイトのアドレス、メールアドレス、または電話番号を指定すると、除外を適用して BitLocker 保護を適用する方法の手順を示すダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="93111-201">If you enable this policy setting and provide a website address, email address, or phone number, users see a dialog box with instructions on how to apply for an exemption from BitLocker protection.</span></span> <span data-ttu-id="93111-202">ユーザーに対して BitLocker 暗号化の適用除外を有効にする方法については、「 <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-25.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-25.md)"> ユーザー Bitlocker 暗号化の除外を管理する方法」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="93111-202">For more information about enabling BitLocker encryption exemptions for users, see <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-25.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-25.md)">How to Manage User BitLocker Encryption Exemptions</a>.</span></span></p>
<p><span data-ttu-id="93111-203">このポリシー設定を無効にするか、未構成にした場合、除外要求の手順はユーザーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="93111-203">If you either disable or do not configure this policy setting, the exemption request instructions are not displayed to users.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="93111-204">注</span><span class="sxs-lookup"><span data-stu-id="93111-204">Note</span></span></strong><br/><p><span data-ttu-id="93111-205">ユーザーの除外は、コンピューターごとではなく、ユーザーごとに管理されます。</span><span class="sxs-lookup"><span data-stu-id="93111-205">User exemption is managed per user, not per computer.</span></span> <span data-ttu-id="93111-206">複数のユーザーが同じコンピューターにログオンしていて、1人のユーザーが除外されていない場合、コンピューターは暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="93111-206">If multiple users log on to the same computer and any one user is not exempt, the computer is encrypted.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93111-207">カスタマーエクスペリエンス向上プログラムの構成</span><span class="sxs-lookup"><span data-stu-id="93111-207">Configure customer experience improvement program</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-208">推奨される構成: <strong> 有効</span><span class="sxs-lookup"><span data-stu-id="93111-208">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="93111-209">このポリシー設定では、MBAM ユーザーがカスタマーエクスペリエンス向上プログラムに参加する方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="93111-209">This policy setting lets you configure how MBAM users can join the Customer Experience Improvement Program.</span></span> <span data-ttu-id="93111-210">このプログラムでは、コンピューターのハードウェアに関する情報を収集し、ユーザーの作業を中断することなく MBAM を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="93111-210">This program collects information about computer hardware and how users use MBAM without interrupting their work.</span></span> <span data-ttu-id="93111-211">この情報は、Microsoft が改善する MBAM 機能を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="93111-211">The information helps Microsoft to identify which MBAM features to improve.</span></span> <span data-ttu-id="93111-212">Microsoft は、MBAM ユーザーを特定したり連絡したりするためにこの情報を使用することはありません。</span><span class="sxs-lookup"><span data-stu-id="93111-212">Microsoft does not use this information to identify or contact MBAM users.</span></span></p>
<p><span data-ttu-id="93111-213">このポリシー設定を有効にした場合、ユーザーはカスタマーエクスペリエンス向上プログラムに参加できます。</span><span class="sxs-lookup"><span data-stu-id="93111-213">If you enable this policy setting, users can join the Customer Experience Improvement Program.</span></span></p>
<p><span data-ttu-id="93111-214">このポリシー設定を無効にすると、ユーザーはカスタマーエクスペリエンス向上プログラムに参加できなくなります。</span><span class="sxs-lookup"><span data-stu-id="93111-214">If you disable this policy setting, users cannot join the Customer Experience Improvement Program.</span></span></p>
<p><span data-ttu-id="93111-215">このポリシー設定を構成しない場合、ユーザーはカスタマーエクスペリエンス向上プログラムに参加するためのオプションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="93111-215">If you do not configure this policy setting, users have the option to join the Customer Experience Improvement Program.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93111-216">セキュリティポリシーのリンクの URL を指定する</span><span class="sxs-lookup"><span data-stu-id="93111-216">Provide the URL for the Security Policy link</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-217">推奨される構成: <strong> 有効</span><span class="sxs-lookup"><span data-stu-id="93111-217">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="93111-218">このポリシー設定を使用して、エンドユーザーに "会社セキュリティポリシー" という名前のリンクとして表示される URL を指定し &quot; ます。 &quot;このリンクは、会社の内部セキュリティポリシーを指し、暗号化要件に関する情報をエンドユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="93111-218">Use this policy setting to specify a URL that is displayed to end users as a link named &quot;Company Security Policy.&quot; The link points to your company’s internal security policy and provides end users with information about encryption requirements.</span></span> <span data-ttu-id="93111-219">このリンクは、ユーザーが MBAM によってドライブを暗号化するように求められた場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="93111-219">The link appears when users are prompted by MBAM to encrypt a drive.</span></span></p>
<p><span data-ttu-id="93111-220">このポリシー設定を有効にした場合は、セキュリティポリシーのリンクの URL を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="93111-220">If you enable this policy setting, you can configure the URL for the Security Policy link.</span></span></p>
<p><span data-ttu-id="93111-221">このポリシー設定を無効にした場合、または構成しなかった場合、[セキュリティポリシー] リンクはユーザーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="93111-221">If you disable or do not configure this policy setting, the Security Policy link is not displayed to users.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="93111-222">固定ドライブのグループポリシー定義</span><span class="sxs-lookup"><span data-stu-id="93111-222">Fixed Drive Group Policy definitions</span></span>

<span data-ttu-id="93111-223">このセクションでは、Microsoft BitLocker の管理と監視を行うための、次の GPO ノードでの固定ドライブポリシー定義について説明します。**コンピューター構成** &gt; **ポリシー** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **MDOP mbam (BitLocker 管理)** &gt; **固定ドライブ**。</span><span class="sxs-lookup"><span data-stu-id="93111-223">This section describes Fixed Drive policy definitions for Microsoft BitLocker Administration and Monitoring at the following GPO node: **Computer Configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)** &gt; **Fixed Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="93111-224">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="93111-224">Policy name</span></span></th>
<th align="left"><span data-ttu-id="93111-225">概要と推奨されるグループポリシー設定</span><span class="sxs-lookup"><span data-stu-id="93111-225">Overview and suggested Group Policy settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93111-226">固定データドライブの暗号化設定</span><span class="sxs-lookup"><span data-stu-id="93111-226">Fixed data drive encryption settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-227">推奨される構成: <strong> 有効</span><span class="sxs-lookup"><span data-stu-id="93111-227">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="93111-228">このポリシー設定では、固定データドライブを暗号化する必要があるかどうかを管理できます。</span><span class="sxs-lookup"><span data-stu-id="93111-228">This policy setting lets you manage whether fixed data drives must be encrypted.</span></span></p>
<p><span data-ttu-id="93111-229">オペレーティングシステムのボリュームが暗号化されている必要がある場合は、[ <strong> 固定データドライブを自動ロック解除する] をクリックし </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="93111-229">If the operating system volume is required to be encrypted, click <strong>Enable auto-unlock fixed data drive</strong>.</span></span></p>
<p><span data-ttu-id="93111-230">このポリシーを有効にする場合は、 <strong> </strong> 固定データドライブの自動ロック解除を有効にするか、または要求しない限り、固定データドライブのパスワードの使用を構成しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="93111-230">When you enable this policy, you must not disable the <strong>Configure use of password for fixed data drives</strong> policy unless you are enabling or requiring the use of auto-unlock for fixed data drives.</span></span></p>
<p><span data-ttu-id="93111-231">固定データドライブの自動ロック解除を使用する必要がある場合は、暗号化されるようにオペレーティングシステムのボリュームを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93111-231">If you have to use auto-unlock for fixed data drives, you must configure operating system volumes to be encrypted.</span></span></p>
<p><span data-ttu-id="93111-232">このポリシー設定を有効にした場合、ユーザーはすべての固定データドライブを BitLocker 保護の下に置く必要があり、データドライブは暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="93111-232">If you enable this policy setting, users are required to put all fixed data drives under BitLocker protection, and the data drives are then encrypted.</span></span></p>
<p><span data-ttu-id="93111-233">このポリシー設定を構成しない場合、ユーザーは、固定データドライブを BitLocker による保護の対象として配置する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="93111-233">If you do not configure this policy setting, users are not required to put fixed data drives under BitLocker protection.</span></span> <span data-ttu-id="93111-234">固定データドライブが暗号化された後にこのポリシーを適用すると、MBAM エージェントは暗号化された固定データドライブを解読します。</span><span class="sxs-lookup"><span data-stu-id="93111-234">If you apply this policy after fixed data drives are encrypted, the MBAM agent decrypts the encrypted fixed data drives.</span></span></p>
<p><span data-ttu-id="93111-235">このポリシー設定を無効にした場合、ユーザーは固定データドライブを BitLocker 保護下に配置することはできません。</span><span class="sxs-lookup"><span data-stu-id="93111-235">If you disable this policy setting, users cannot put their fixed data drives under BitLocker protection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93111-236">BitLocker で保護されていない固定ドライブへの書き込みアクセスを拒否する</span><span class="sxs-lookup"><span data-stu-id="93111-236">Deny write access to fixed drives not protected by BitLocker</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-237">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="93111-237">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="93111-238">このポリシー設定は、固定データドライブをコンピューター上で書き込み可能にするために BitLocker の保護が必要かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="93111-238">This policy setting determines whether BitLocker protection is required for fixed data drives to be writable on a computer.</span></span> <span data-ttu-id="93111-239">このポリシー設定は、BitLocker を有効にすると適用されます。</span><span class="sxs-lookup"><span data-stu-id="93111-239">This policy setting is applied when you turn on BitLocker.</span></span></p>
<p><span data-ttu-id="93111-240">ポリシーが構成されていない場合、コンピューター上のすべての固定データドライブは読み取り/書き込みアクセス許可を使用してマウントされます。</span><span class="sxs-lookup"><span data-stu-id="93111-240">When the policy is not configured, all fixed data drives on the computer are mounted with read/write permission.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93111-241">BitLocker で保護された固定ドライブへのアクセスを以前のバージョンの Windows から許可する</span><span class="sxs-lookup"><span data-stu-id="93111-241">Allow access to BitLocker-protected fixed drives from earlier versions of Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-242">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="93111-242">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="93111-243">このポリシーを有効にすると、Windows Server 2008、Windows Vista、Windows XP、または Windows XP SP2 を実行しているコンピューターで、FAT ファイルシステムで固定されたドライブのロックを解除し、表示することができます。</span><span class="sxs-lookup"><span data-stu-id="93111-243">Enable this policy so that fixed drives with the FAT file system can be unlocked and viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p>
<p><span data-ttu-id="93111-244">ポリシーが有効になっているか、構成されていない場合は、FAT ファイルシステムで書式設定された固定ドライブのロックを解除することができ、windows Server 2008、Windows Vista、Windows XP SP3、または Windows XP SP2 を実行しているコンピューターでそれらのコンテンツを表示できます。</span><span class="sxs-lookup"><span data-stu-id="93111-244">When the policy is enabled or not configured, fixed drives that are formatted with the FAT file system can be unlocked and their content can be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span> <span data-ttu-id="93111-245">これらのオペレーティングシステムは、BitLocker で保護されたドライブに対して読み取り専用のアクセス許可を持っています。</span><span class="sxs-lookup"><span data-stu-id="93111-245">These operating systems have read-only permission to BitLocker-protected drives.</span></span></p>
<p><span data-ttu-id="93111-246">ポリシーが無効になっている場合、FAT ファイルシステムでフォーマットされている固定ドライブのロックを解除することはできません。 Windows Server 2008、Windows Vista、Windows XP SP3、または Windows XP SP2 を実行しているコンピューターでは、これらのコンテンツを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="93111-246">When the policy is disabled, fixed drives that are formatted with the FAT file system cannot be unlocked and their content cannot be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93111-247">固定ドライブのパスワードの使用を構成する</span><span class="sxs-lookup"><span data-stu-id="93111-247">Configure use of password for fixed drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-248">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="93111-248">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="93111-249">このポリシーを使って、BitLocker で保護された固定データドライブのロックを解除するためにパスワードが必要かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="93111-249">Use this policy to specify whether a password is required to unlock BitLocker-protected fixed data drives.</span></span></p>
<p><span data-ttu-id="93111-250">このポリシー設定を有効にした場合、ユーザーは定義した要件を満たすパスワードを構成できます。</span><span class="sxs-lookup"><span data-stu-id="93111-250">If you enable this policy setting, users can configure a password that meets the requirements that you define.</span></span> <span data-ttu-id="93111-251">BitLocker を使用すると、ユーザーはドライブで利用可能な任意のプロテクターでドライブのロックを解除することができます。</span><span class="sxs-lookup"><span data-stu-id="93111-251">BitLocker enables users to unlock a drive with any of the protectors that are available on the drive.</span></span></p>
<p><span data-ttu-id="93111-252">これらの設定は、ボリュームのロックを解除しても、BitLocker を有効にするときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="93111-252">These settings are enforced when you turn on BitLocker, not when you unlock a volume.</span></span></p>
<p><span data-ttu-id="93111-253">このポリシー設定を無効にした場合、ユーザーはパスワードを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="93111-253">If you disable this policy setting, users are not allowed to use a password.</span></span></p>
<p><span data-ttu-id="93111-254">ポリシーが構成されていない場合、パスワードは既定の設定でサポートされます。パスワードの複雑さの要件は含まれず、8文字しか必要ありません。</span><span class="sxs-lookup"><span data-stu-id="93111-254">When the policy is not configured, passwords are supported with the default settings, which do not include password complexity requirements and which require only eight characters.</span></span></p>
<p><span data-ttu-id="93111-255">セキュリティを高めるには、このポリシーを有効にして、[ <strong> 固定データドライブにパスワードを要求する] を選び </strong> 、[パスワードの複雑さを要求する] をクリックして、 <strong> </strong> <strong> 必要なパスワードの最小の長さを設定し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="93111-255">For higher security, enable this policy, and then select <strong>Require password for fixed data drive</strong>, click <strong>Require password complexity</strong>, and set the <strong>minimum password length</strong> that you want.</span></span></p>
<p><span data-ttu-id="93111-256">このポリシー設定を無効にした場合、ユーザーはパスワードを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="93111-256">If you disable this policy setting, users are not allowed to use a password.</span></span></p>
<p><span data-ttu-id="93111-257">このポリシー設定を構成しない場合、パスワードは既定の設定でサポートされます。これにはパスワードの複雑さの要件は含まれず、8文字しか必要ありません。</span><span class="sxs-lookup"><span data-stu-id="93111-257">If you do not configure this policy setting, passwords are supported with the default settings, which do not include password complexity requirements and which require only eight characters.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93111-258">BitLocker で保護された固定ドライブの回復方法を選択する</span><span class="sxs-lookup"><span data-stu-id="93111-258">Choose how BitLocker-protected fixed drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-259">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="93111-259">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="93111-260">BitLocker データ回復エージェントを有効にする、または Active Directory ドメインサービス (AD DS) に BitLocker 回復情報を保存するには、このポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="93111-260">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="93111-261">ポリシーが構成されていない場合、BitLocker データ回復エージェントは許可され、回復情報は AD DS にバックアップされません。</span><span class="sxs-lookup"><span data-stu-id="93111-261">When the policy is not configured, the BitLocker data recovery agent is allowed, and recovery information is not backed up to AD DS.</span></span> <span data-ttu-id="93111-262">MBAM は、AD DS にバックアップするための回復情報を必要としません。</span><span class="sxs-lookup"><span data-stu-id="93111-262">MBAM does not require recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93111-263">暗号化ポリシーの適用設定</span><span class="sxs-lookup"><span data-stu-id="93111-263">Encryption Policy Enforcement Settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-264">推奨される構成: <strong> 有効</span><span class="sxs-lookup"><span data-stu-id="93111-264">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="93111-265">このポリシー設定を使用して、MBAM ポリシーへの準拠を強制されるまで固定データドライブが準拠していない日数を構成します。</span><span class="sxs-lookup"><span data-stu-id="93111-265">Use this policy setting to configure the number of days that fixed data drives can remain noncompliant until they are forced to comply with MBAM policies.</span></span> <span data-ttu-id="93111-266">ユーザーは、猶予期間後に、必要な操作を延期したり、除外を要求したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="93111-266">Users cannot postpone the required action or request an exemption from it after the grace period.</span></span> <span data-ttu-id="93111-267">猶予期間は、固定データドライブが準拠していないと判断された場合に始まります。</span><span class="sxs-lookup"><span data-stu-id="93111-267">The grace period starts when the fixed data drive is determined to be noncompliant.</span></span> <span data-ttu-id="93111-268">ただし、固定データドライブポリシーは、オペレーティングシステムドライブに準拠するまでは適用されません。</span><span class="sxs-lookup"><span data-stu-id="93111-268">However, the fixed data drive policy is not enforced until the operating system drive is compliant.</span></span></p>
<p><span data-ttu-id="93111-269">猶予期間の経過後も固定データドライブが準拠していない場合、ユーザーには、除外を延期または要求するオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="93111-269">If the grace period expires and the fixed data drive is still not compliant, users do not have the option to postpone or to request an exemption.</span></span> <span data-ttu-id="93111-270">暗号化プロセスでユーザーの入力が必要な場合は、ユーザーが必要な情報を提供するまで閉じることができないダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="93111-270">If the encryption process requires user input, a dialog box appears that users cannot close until they provide the required information.</span></span></p>
<p><span data-ttu-id="93111-271">「0」と入力して <strong> </strong> 、 <strong> </strong> オペレーティングシステムドライブの猶予期間が終了した直後に暗号化処理が開始されるように、[固定ドライブの猶予期間 (分単位) を構成します。</span><span class="sxs-lookup"><span data-stu-id="93111-271">Enter <strong>0</strong> in the <strong>Configure the number of noncompliance grace period days for fixed drives</strong> to force the encryption process to begin immediately after the grace period expires for the operating system drive.</span></span></p>
<p><span data-ttu-id="93111-272">この設定を無効にした場合、または構成しなかった場合、ユーザーは MBAM ポリシーに準拠することは強制されません。</span><span class="sxs-lookup"><span data-stu-id="93111-272">If you disable or do not configure this setting, users are not forced to comply with MBAM policies.</span></span></p>
<p><span data-ttu-id="93111-273">プロテクターを追加するためにユーザーの操作が必要ない場合は、猶予期間が終了した後にバックグラウンドで暗号化が開始されます。</span><span class="sxs-lookup"><span data-stu-id="93111-273">If no user interaction is required to add a protector, encryption begins in the background after the grace period expires.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="93111-274">オペレーティングシステムドライブのグループポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="93111-274">Operating System Drive Group Policy definitions</span></span>

<span data-ttu-id="93111-275">このセクションでは、Microsoft BitLocker の管理と監視に使用するオペレーティングシステムドライブのポリシー定義を次の GPO ノードで説明します。**コンピューター構成** &gt; **ポリシー** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **MDOP mbam (BitLocker 管理)** &gt; **オペレーティングシステムドライブ**。</span><span class="sxs-lookup"><span data-stu-id="93111-275">This section describes Operating System Drive policy definitions for Microsoft BitLocker Administration and Monitoring at the following GPO node: **Computer Configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)** &gt; **Operating System Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="93111-276">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="93111-276">Policy name</span></span></th>
<th align="left"><span data-ttu-id="93111-277">概要と推奨されるグループポリシー設定</span><span class="sxs-lookup"><span data-stu-id="93111-277">Overview and suggested Group Policy settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93111-278">オペレーティングシステムドライブの暗号化の設定</span><span class="sxs-lookup"><span data-stu-id="93111-278">Operating system drive encryption settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-279">推奨される構成: <strong> 有効</span><span class="sxs-lookup"><span data-stu-id="93111-279">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="93111-280">このポリシー設定では、オペレーティングシステムドライブを暗号化する必要があるかどうかを管理できます。</span><span class="sxs-lookup"><span data-stu-id="93111-280">This policy setting lets you manage whether the operating system drive must be encrypted.</span></span></p>
<p><span data-ttu-id="93111-281">セキュリティを高めるには、 <strong> </strong> &gt; <strong> </strong> &gt; <strong> </strong> TPM + PIN プロテクターを使って、システムの電源管理のスリープ設定で次のポリシー設定を無効にすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="93111-281">For higher security, consider disabling the following policy settings in <strong>System</strong> &gt; <strong>Power Management</strong> &gt; <strong>Sleep Settings</strong> when you enable them with TPM + PIN protector:</span></span></p>
<ul>
<li><p><span data-ttu-id="93111-282">スリープ中 (電源に接続されているとき) にスタンバイ状態 (S1 ~ S3) を許可する</span><span class="sxs-lookup"><span data-stu-id="93111-282">Allow Standby States (S1-S3) When Sleeping (Plugged In)</span></span></p></li>
<li><p><span data-ttu-id="93111-283">スリープ中 (バッテリー) でスタンバイ状態 (S1-S3) を許可する</span><span class="sxs-lookup"><span data-stu-id="93111-283">Allow Standby States (S1-S3) When Sleeping (On Battery)</span></span></p></li>
</ul>
<p><span data-ttu-id="93111-284">Microsoft Windows 8 以降を実行していて、TPM がないコンピューターで BitLocker を使用する場合は、[ <strong> 互換性のある tpm なしで bitlocker を許可する] チェックボックスをオンにし </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="93111-284">If you are running Microsoft Windows 8 or later, and you want to use BitLocker on a computer without a TPM, select the <strong>Allow BitLocker without a compatible TPM</strong> check box.</span></span> <span data-ttu-id="93111-285">このモードでは、起動時にパスワードを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93111-285">In this mode, a password is required for startup.</span></span> <span data-ttu-id="93111-286">パスワードを忘れた場合は、BitLocker の回復オプションのいずれかを使ってドライブにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="93111-286">If you forget the password, you have to use one of the BitLocker recovery options to access the drive.</span></span></p>
<p><span data-ttu-id="93111-287">互換性のある TPM が搭載されたコンピューターでは、2種類の認証方法を使用して、暗号化されたデータの保護を強化できます。</span><span class="sxs-lookup"><span data-stu-id="93111-287">On a computer with a compatible TPM, two types of authentication methods can be used at startup to provide added protection for encrypted data.</span></span> <span data-ttu-id="93111-288">コンピューターの起動時には、TPM のみを認証に使うことができます。また、暗証番号 (PIN) の入力を要求することもできます。</span><span class="sxs-lookup"><span data-stu-id="93111-288">When the computer starts, it can use only the TPM for authentication, or it can also require the entry of a personal identification number (PIN).</span></span></p>
<p><span data-ttu-id="93111-289">このポリシー設定を有効にした場合、ユーザーは、オペレーティングシステムドライブを [BitLocker 保護] の下に置く必要があり、ドライブは暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="93111-289">If you enable this policy setting, users have to put the operating system drive under BitLocker protection, and the drive is then encrypted.</span></span></p>
<p><span data-ttu-id="93111-290">このポリシーを無効にした場合、ユーザーは、オペレーティングシステムドライブを BitLocker で保護することはできません。</span><span class="sxs-lookup"><span data-stu-id="93111-290">If you disable this policy, users cannot put the operating system drive under BitLocker protection.</span></span> <span data-ttu-id="93111-291">オペレーティングシステムドライブが暗号化された後にこのポリシーを適用すると、ドライブは暗号化解除されます。</span><span class="sxs-lookup"><span data-stu-id="93111-291">If you apply this policy after the operating system drive is encrypted, the drive is then decrypted.</span></span></p>
<p><span data-ttu-id="93111-292">このポリシーを構成しない場合、オペレーティングシステムドライブは、BitLocker による保護の下に配置する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="93111-292">If you do not configure this policy, the operating system drive is not required to be placed under BitLocker protection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93111-293">スタートアップの拡張 Pin を許可する</span><span class="sxs-lookup"><span data-stu-id="93111-293">Allow enhanced PINs for startup</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-294">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="93111-294">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="93111-295">このポリシー設定を使用して、強化されたスタートアップ Pin が BitLocker と共に使用されるかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="93111-295">Use this policy setting to configure whether enhanced startup PINs are used with BitLocker.</span></span> <span data-ttu-id="93111-296">拡張されたスタートアップ Pin では、大文字と小文字、記号、数字、スペースなどの文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="93111-296">Enhanced startup PINs permit the use of characters including uppercase and lowercase letters, symbols, numbers, and spaces.</span></span> <span data-ttu-id="93111-297">このポリシー設定は、BitLocker を有効にすると適用されます。</span><span class="sxs-lookup"><span data-stu-id="93111-297">This policy setting is applied when you turn on BitLocker.</span></span></p>
<p><span data-ttu-id="93111-298">このポリシー設定を有効にすると、すべての新しい BitLocker スタートアップ Pin が設定され、エンドユーザーは拡張 Pin を作成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="93111-298">If you enable this policy setting, all new BitLocker startup PINs set will enable end user to create enhanced PINs.</span></span> <span data-ttu-id="93111-299">ただし、プレブート環境では、すべてのコンピューターで拡張ピンがサポートされているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="93111-299">However, not all computers can support enhanced PINs in the pre-boot environment.</span></span> <span data-ttu-id="93111-300">使用を有効にする前に、管理者がこの機能に対応しているかどうかを評価することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="93111-300">We strongly recommend that administrators evaluate whether their systems are compatible with this feature before enabling its use.</span></span></p>
<p><span data-ttu-id="93111-301"><strong> </strong> プレブート環境に入力できる文字数を制限するコンピューターとの互換性を向上させるには、[ASCII のみの pin を使用する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="93111-301">Select the <strong>Require ASCII-only PINs</strong> check box to help make enhanced PINs more compatible with computers that limit the type or number of characters that can be entered in the pre-boot environment.</span></span></p>
<p><span data-ttu-id="93111-302">このポリシー設定を無効にした場合、または構成しなかった場合は、強化された Pin は使用されません。</span><span class="sxs-lookup"><span data-stu-id="93111-302">If you disable or do not configure this policy setting, enhanced PINs are not used.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93111-303">BitLocker で保護されたオペレーティングシステムドライブの回復方法を選択する</span><span class="sxs-lookup"><span data-stu-id="93111-303">Choose how BitLocker-protected operating system drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-304">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="93111-304">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="93111-305">BitLocker データ回復エージェントを有効にする、または Active Directory ドメインサービス (AD DS) に BitLocker 回復情報を保存するには、このポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="93111-305">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="93111-306">このポリシーが構成されていない場合、データ回復エージェントは許可され、回復情報は AD DS にバックアップされません。</span><span class="sxs-lookup"><span data-stu-id="93111-306">When this policy is not configured, the data recovery agent is allowed, and recovery information is not backed up to AD DS.</span></span></p>
<p><span data-ttu-id="93111-307">MBAM 操作では、AD DS に回復情報をバックアップする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="93111-307">MBAM operation does not require recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93111-308">オペレーティングシステムドライブのパスワードの使用を構成する</span><span class="sxs-lookup"><span data-stu-id="93111-308">Configure use of passwords for operating system drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-309">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="93111-309">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="93111-310">BitLocker で保護されたオペレーティングシステムドライブのロックを解除するために使用するパスワードの制約を設定するには、このポリシー設定を使います。</span><span class="sxs-lookup"><span data-stu-id="93111-310">Use this policy setting to set the constraints for passwords that are used to unlock BitLocker-protected operating system drives.</span></span> <span data-ttu-id="93111-311">オペレーティングシステムドライブで TPM 以外のプロテクターが許可されている場合は、パスワードのプロビジョニング、パスワードの複雑さの要件の適用、パスワードの最小文字数の構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="93111-311">If non-TPM protectors are allowed on operating system drives, you can provision a password, enforce complexity requirements on the password, and configure a minimum length for the password.</span></span> <span data-ttu-id="93111-312">複雑さの要件の設定を有効にするには、[コンピューターの構成] の &quot; &quot; [Windows 設定] の [アカウントポリシー] のパスワードポリシーにある複雑さの要件を満たすように、グループポリシーの設定を有効にする必要があり &gt; &gt; &gt; &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="93111-312">For the complexity requirement setting to be effective, you must also enable the Group Policy setting &quot;Password must meet complexity requirements&quot; located in Computer Configuration &gt; Windows Settings &gt; Security Settings &gt; Account Policies &gt; Password Policy.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="93111-313">注</span><span class="sxs-lookup"><span data-stu-id="93111-313">Note</span></span></strong><br/><p><span data-ttu-id="93111-314">これらの設定は、ボリュームのロックを解除しても、BitLocker を有効にするときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="93111-314">These settings are enforced when you turn on BitLocker, not when you unlock a volume.</span></span> <span data-ttu-id="93111-315">BitLocker では、ドライブで利用できる任意のプロテクターでドライブのロックを解除することができます。</span><span class="sxs-lookup"><span data-stu-id="93111-315">BitLocker lets you unlock a drive with any of the protectors that are available on the drive.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="93111-316">このポリシー設定を有効にした場合、ユーザーは定義した要件を満たすパスワードを構成できます。</span><span class="sxs-lookup"><span data-stu-id="93111-316">If you enable this policy setting, users can configure a password that meets the requirements that you define.</span></span> <span data-ttu-id="93111-317">パスワードに複雑さの要件を適用するには、[パスワードの複雑さを要求する] をクリックし <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="93111-317">To enforce complexity requirements on the password, click <strong>Require password complexity</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93111-318">BIOS ベースのファームウェア構成の TPM プラットフォーム検証プロファイルを構成する</span><span class="sxs-lookup"><span data-stu-id="93111-318">Configure TPM platform validation profile for BIOS-based firmware configurations</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-319">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="93111-319">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="93111-320">このポリシー設定では、コンピューター&#39;s のトラステッドプラットフォームモジュール (TPM) セキュリティハードウェアが BitLocker 暗号化キーをセキュリティで保護する方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="93111-320">This policy setting allows you to configure how the computer&#39;s Trusted Platform Module (TPM) security hardware secures the BitLocker encryption key.</span></span> <span data-ttu-id="93111-321">このポリシー設定は、コンピューターに互換性のある TPM が搭載されていない場合、または TPM 保護で BitLocker が既に有効になっている場合は適用されません。</span><span class="sxs-lookup"><span data-stu-id="93111-321">This policy setting does not apply if the computer does not have a compatible TPM or if BitLocker has already been turned on with TPM protection.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="93111-322">重要</span><span class="sxs-lookup"><span data-stu-id="93111-322">Important</span></span></strong><br/><p><span data-ttu-id="93111-323">このグループポリシー設定は、BIOS 構成のコンピューター、または、互換性サービスモジュール (CSM) が有効になっている UEFI ファームウェアを使用しているコンピューターにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="93111-323">This Group Policy setting applies only to computers with BIOS configurations or to computers with UEFI firmware with a Compatibility Service Module (CSM) enabled.</span></span> <span data-ttu-id="93111-324">ネイティブの UEFI ファームウェア構成を使用するコンピューターは、異なる値をプラットフォーム構成レジスタ (Pcr) に保存します。</span><span class="sxs-lookup"><span data-stu-id="93111-324">Computers that use a native UEFI firmware configuration store different values into the Platform Configuration Registers (PCRs).</span></span> <span data-ttu-id="93111-325">ネイティブの uefi &quot; ファームウェア構成用に tpm プラットフォーム検証プロファイルを構成 &quot; するグループポリシー設定を使用して、ネイティブの uefi ファームウェアを使用するコンピューターの tpm PCR プロファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="93111-325">Use the &quot;Configure TPM platform validation profile for native UEFI firmware configurations&quot; Group Policy setting to configure the TPM PCR profile for computers that use native UEFI firmware.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="93111-326">BitLocker を有効にする前にこのポリシー設定を有効にした場合は、BitLocker で暗号化されたオペレーティングシステムドライブへのアクセスをロック解除する前に、TPM が検証するブートコンポーネントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="93111-326">If you enable this policy setting before you turn on BitLocker, you can configure the boot components that the TPM validates before you unlock access to the BitLocker-encrypted operating system drive.</span></span> <span data-ttu-id="93111-327">BitLocker の保護が有効になっている間に、これらのコンポーネントのいずれかが変更された場合、TPM は暗号化キーを解放してドライブのロックを解除します。代わりに、コンピューターは BitLocker 回復コンソールを表示し、回復パスワードまたは回復キーを指定してドライブのロックを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93111-327">If any of these components change while BitLocker protection is in effect, the TPM does not release the encryption key to unlock the drive and the computer instead displays the BitLocker Recovery console and requires that you provide either the recovery password or recovery key to unlock the drive.</span></span></p>
<p><span data-ttu-id="93111-328">このポリシー設定を無効にするか、未構成にした場合、BitLocker では、既定のプラットフォーム検証プロファイルまたはセットアップスクリプトで指定されたプラットフォーム検証プロファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="93111-328">If you disable or do not configure this policy setting, BitLocker uses the default platform validation profile or the platform validation profile that is specified by the Setup script.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93111-329">TPM プラットフォームの検証プロファイルを構成する</span><span class="sxs-lookup"><span data-stu-id="93111-329">Configure TPM platform validation profile</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-330">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="93111-330">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="93111-331">このポリシー設定では、コンピューター&#39;s のトラステッドプラットフォームモジュール (TPM) セキュリティハードウェアが BitLocker 暗号化キーをセキュリティで保護する方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="93111-331">This policy setting enables you to configure how the computer&#39;s Trusted Platform Module (TPM) security hardware secures the BitLocker encryption key.</span></span> <span data-ttu-id="93111-332">このポリシー設定は、コンピューターに互換性のある TPM が搭載されていない場合、または TPM 保護で BitLocker が既に有効になっている場合は適用されません。</span><span class="sxs-lookup"><span data-stu-id="93111-332">This policy setting does not apply if the computer does not have a compatible TPM or if BitLocker has already been turned on with TPM protection.</span></span></p>
<p><span data-ttu-id="93111-333">BitLocker を有効にする前にこのポリシー設定を有効にした場合は、BitLocker で暗号化されたオペレーティングシステムドライブへのアクセスをロック解除する前に、TPM が検証するブートコンポーネントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="93111-333">If you enable this policy setting before you turn on BitLocker, you can configure the boot components that the TPM validates before you unlock access to the BitLocker-encrypted operating system drive.</span></span> <span data-ttu-id="93111-334">BitLocker の保護が有効になっている間に、これらのコンポーネントのいずれかが変更された場合、TPM は暗号化キーを解放してドライブのロックを解除します。代わりに、コンピューターは BitLocker 回復コンソールを表示し、回復パスワードまたは回復キーを指定してドライブのロックを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93111-334">If any of these components change while BitLocker protection is in effect, the TPM does not release the encryption key to unlock the drive and the computer instead displays the BitLocker Recovery console and requires that you provide either the recovery password or recovery key to unlock the drive.</span></span></p>
<p><span data-ttu-id="93111-335">このポリシー設定を無効にするか、未構成にした場合、BitLocker では、既定のプラットフォーム検証プロファイルまたはセットアップスクリプトで指定されたプラットフォーム検証プロファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="93111-335">If you disable or do not configure this policy setting, BitLocker uses the default platform validation profile or the platform validation profile that is specified by the setup script.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93111-336">ネイティブの UEFI ファームウェア構成の TPM プラットフォーム検証プロファイルを構成する</span><span class="sxs-lookup"><span data-stu-id="93111-336">Configure TPM platform validation profile for native UEFI firmware configurations</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-337">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="93111-337">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="93111-338">このポリシー設定では、コンピューター&#39;s のトラステッドプラットフォームモジュール (TPM) セキュリティハードウェアが BitLocker 暗号化キーをセキュリティで保護する方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="93111-338">This policy setting allows you to configure how the computer&#39;s Trusted Platform Module (TPM) security hardware secures the BitLocker encryption key.</span></span> <span data-ttu-id="93111-339">このポリシー設定は、コンピューターに互換性のある TPM が搭載されていない場合、または TPM 保護で BitLocker が既に有効になっている場合は適用されません。</span><span class="sxs-lookup"><span data-stu-id="93111-339">This policy setting does not apply if the computer does not have a compatible TPM or if BitLocker has already been turned on with TPM protection.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="93111-340">重要</span><span class="sxs-lookup"><span data-stu-id="93111-340">Important</span></span></strong><br/><p><span data-ttu-id="93111-341">このグループポリシー設定は、ネイティブの UEFI ファームウェア構成を使用しているコンピューターにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="93111-341">This Group Policy setting applies only to computers with a native UEFI firmware configuration.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="93111-342">BitLocker を有効にする前にこのポリシー設定を有効にした場合は、BitLocker で暗号化されたオペレーティングシステムドライブへのアクセスをロック解除する前に TPM が検証するブートコンポーネントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="93111-342">If you enable this policy setting before you turn on BitLocker, you can configure the boot components that the TPM validates before unlocking access to the BitLocker-encrypted operating system drive.</span></span> <span data-ttu-id="93111-343">BitLocker の保護が有効になっている間に、これらのコンポーネントのいずれかが変更された場合、TPM は暗号化キーを解放してドライブのロックを解除します。代わりに、コンピューターは BitLocker 回復コンソールを表示し、回復パスワードまたは回復キーを指定してドライブのロックを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93111-343">If any of these components change while BitLocker protection is in effect, the TPM does not release the encryption key to unlock the drive and the computer instead displays the BitLocker Recovery console and requires that you provide either the recovery password or recovery key to unlock the drive.</span></span></p>
<p><span data-ttu-id="93111-344">このポリシー設定を無効にするか、未構成にした場合、BitLocker では、既定のプラットフォーム検証プロファイルまたはセットアップスクリプトで指定されたプラットフォーム検証プロファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="93111-344">If you disable or do not configure this policy setting, BitLocker uses the default platform validation profile or the platform validation profile that is specified by the setup script.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93111-345">BitLocker の回復後にプラットフォームの検証データを再設定する</span><span class="sxs-lookup"><span data-stu-id="93111-345">Reset platform validation data after BitLocker recovery</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-346">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="93111-346">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="93111-347">このポリシー設定を使用して、BitLocker の回復後に Windows を起動したときに、プラットフォームの検証データを更新するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="93111-347">Use this policy setting to control whether platform validation data is refreshed when Windows is started after BitLocker recovery.</span></span></p>
<p><span data-ttu-id="93111-348">このポリシー設定を有効にした場合、BitLocker の回復後に Windows を起動すると、プラットフォームの検証データが更新されます。</span><span class="sxs-lookup"><span data-stu-id="93111-348">If you enable this policy setting, platform validation data are refreshed when Windows is started after BitLocker recovery.</span></span> <span data-ttu-id="93111-349">このポリシー設定を無効にした場合、BitLocker の回復後に Windows を起動すると、プラットフォームの検証データは更新されません。</span><span class="sxs-lookup"><span data-stu-id="93111-349">If you disable this policy setting, platform validation data are not refreshed when Windows is started after BitLocker recovery.</span></span> <span data-ttu-id="93111-350">このポリシー設定を構成しない場合、BitLocker の回復後に Windows を起動すると、プラットフォームの検証データが更新されます。</span><span class="sxs-lookup"><span data-stu-id="93111-350">If you do not configure this policy setting, platform validation data are refreshed when Windows is started after BitLocker recovery.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93111-351">強化されたブート構成データの入力規則プロファイルを使用する</span><span class="sxs-lookup"><span data-stu-id="93111-351">Use enhanced Boot Configuration Data validation profile</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-352">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="93111-352">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="93111-353">このポリシー設定では、プラットフォームの検証中に確認する特定のブート構成データ (BCD) 設定を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="93111-353">This policy setting allows you to choose specific Boot Configuration Data (BCD) settings to verify during platform validation.</span></span></p>
<p><span data-ttu-id="93111-354">このポリシー設定を有効にした場合、その他の設定を追加したり、既定の設定を削除したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="93111-354">If you enable this policy setting, you can add additional settings, remove the default settings, or both.</span></span> <span data-ttu-id="93111-355">このポリシー設定を無効にすると、Windows 7 で使用される既定の BCD プロファイルと同じように、コンピューターは BCD プロファイルに戻ります。</span><span class="sxs-lookup"><span data-stu-id="93111-355">If you disable this policy setting, the computer reverts to a BCD profile similar to the default BCD profile that is used by Windows 7.</span></span> <span data-ttu-id="93111-356">このポリシー設定を構成しない場合、コンピューターは既定の Windows BCD 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="93111-356">If you do not configure this policy setting, the computer verifies the default Windows BCD settings.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="93111-357">注</span><span class="sxs-lookup"><span data-stu-id="93111-357">Note</span></span></strong><br/><p><span data-ttu-id="93111-358">保護されたブート構成データ (BCD) 整合性検証のために BitLocker がセキュリティで保護されたブート構成データ (BCD) を使用している場合、[整合性を検証するためにセキュアブートを許可する] ポリシーで定義されているように、[強化された &quot; &quot; &quot; ブート構成データの入力規則] &quot;</span><span class="sxs-lookup"><span data-stu-id="93111-358">When BitLocker uses Secure Boot for platform and Boot Configuration Data (BCD) integrity validation, as defined by the &quot;Allow Secure Boot for integrity validation&quot; policy, the &quot;Use enhanced Boot Configuration Data validation profile&quot; policy is ignored.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="93111-359">ブートデバッグを制御する設定 (0x16000010) は常に検証され、指定されたフィールドに含まれている場合は効果がありません。</span><span class="sxs-lookup"><span data-stu-id="93111-359">The setting that controls boot debugging (0x16000010) is always validated and has no effect if it is included in the provided fields.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93111-360">暗号化ポリシーの適用設定</span><span class="sxs-lookup"><span data-stu-id="93111-360">Encryption Policy Enforcement Settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-361">推奨される構成: <strong> 有効</span><span class="sxs-lookup"><span data-stu-id="93111-361">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="93111-362">このポリシー設定を使用して、ユーザーがオペレーティングシステムドライブの MBAM ポリシーに準拠して延期できる日数を構成します。</span><span class="sxs-lookup"><span data-stu-id="93111-362">Use this policy setting to configure the number of days that users can postpone complying with MBAM policies for their operating system drive.</span></span> <span data-ttu-id="93111-363">猶予期間は、オペレーティングシステムが最初に準拠していないと検出されたときに始まります。</span><span class="sxs-lookup"><span data-stu-id="93111-363">The grace period begins when the operating system is first detected as noncompliant.</span></span> <span data-ttu-id="93111-364">この猶予期間の期限が切れた後は、ユーザーは必要な操作を延期したり、除外を要求したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="93111-364">After this grace period expires, users cannot postpone the required action or request an exemption from it.</span></span></p>
<p><span data-ttu-id="93111-365">暗号化プロセスでユーザーの入力が必要な場合は、ユーザーが必要な情報を提供するまで閉じることができないダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="93111-365">If the encryption process requires user input, a dialog box appears that users cannot close until they provide the required information.</span></span></p>
<p><span data-ttu-id="93111-366">この設定を無効にした場合、または構成しなかった場合、ユーザーは MBAM ポリシーに準拠することは強制されません。</span><span class="sxs-lookup"><span data-stu-id="93111-366">If you disable or do not configure this setting, users are not forced to comply with MBAM policies.</span></span></p>
<p><span data-ttu-id="93111-367">プロテクターを追加するためにユーザーの操作が必要ない場合は、猶予期間が終了した後にバックグラウンドで暗号化が開始されます。</span><span class="sxs-lookup"><span data-stu-id="93111-367">If no user interaction is required to add a protector, encryption begins in the background after the grace period expires.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93111-368">プレブート回復メッセージと URL を構成する</span><span class="sxs-lookup"><span data-stu-id="93111-368">Configure pre-boot recovery message and URL</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-369">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="93111-369">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="93111-370">このポリシー設定を有効にして、カスタム回復メッセージを構成するか、OS ドライブがロックされているときにプレブートの BitLocker 回復画面に表示される URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="93111-370">Enable this policy setting to configure a custom recovery message or to specify a URL that is then displayed on the pre-boot BitLocker recovery screen when the OS drive is locked.</span></span> <span data-ttu-id="93111-371">この設定は、Windows 10 を実行しているクライアントコンピューターでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="93111-371">This setting is only available on client computers running Windows 10.</span></span></p>
<p><span data-ttu-id="93111-372">このポリシーが有効になっている場合は、プレブート回復メッセージに対して次のいずれかのオプションを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="93111-372">When this policy is enabled, you can select one of these options for the pre-boot recovery message:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="93111-373">[カスタム回復メッセージを使う] </strong> : プレブートの BitLocker 回復画面にカスタムメッセージを含めるには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="93111-373">Use custom recovery message</strong>: Select this option to include a custom message in the pre-boot BitLocker recovery screen.</span></span> <span data-ttu-id="93111-374">[ <strong> カスタム回復メッセージ] オプション </strong> ボックスに、表示するメッセージを入力します。</span><span class="sxs-lookup"><span data-stu-id="93111-374">In the <strong>Custom recovery message option</strong> box, type the message that you want displayed.</span></span> <span data-ttu-id="93111-375">回復 URL も指定する場合は、カスタム回復メッセージの一部として含めます。</span><span class="sxs-lookup"><span data-stu-id="93111-375">If you also want to specify a recovery URL, include it as part of your custom recovery message.</span></span></p></li>
<li><p><strong><span data-ttu-id="93111-376">[カスタム回復 URL を使用する] </strong> : プレブートの BitLocker 回復画面に表示される既定の URL を置き換えるには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="93111-376">Use custom recovery URL</strong>: Select this option to replace the default URL that is displayed in the pre-boot BitLocker recovery screen.</span></span> <span data-ttu-id="93111-377">[ <strong> カスタム回復 url] オプション </strong> ボックスに、表示する url を入力します。</span><span class="sxs-lookup"><span data-stu-id="93111-377">In the <strong>Custom recovery URL option</strong> box, type the URL that you want displayed.</span></span></p></li>
<li><p><strong><span data-ttu-id="93111-378">[既定の回復メッセージと URL を使用 </strong> する]: 既定の bitlocker 回復メッセージと url をプレブートの bitlocker 回復画面に表示するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="93111-378">Use default recovery message and URL</strong>: Select this option to display the default BitLocker recovery message and URL in the pre-boot BitLocker recovery screen.</span></span> <span data-ttu-id="93111-379">以前にカスタム回復メッセージまたは URL を構成していて、既定のメッセージに戻す場合は、このポリシーを有効にして、[ <strong> 既定の回復メッセージと URL を使用する] オプションを選択する必要があり </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="93111-379">If you previously configured a custom recovery message or URL and want to revert to the default message, you must enable this policy and select the <strong>Use default recovery message and URL</strong> option.</span></span></p></li>
</ul>
<div class="alert">
<strong><span data-ttu-id="93111-380">注</span><span class="sxs-lookup"><span data-stu-id="93111-380">Note</span></span></strong><br/><p><span data-ttu-id="93111-381">プリブートでは、すべての文字と言語がサポートされるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="93111-381">Not all characters and languages are supported in pre-boot.</span></span> <span data-ttu-id="93111-382">カスタムメッセージまたは URL に使用した文字が、プレブートの BitLocker 回復画面で正しく表示されることをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="93111-382">We recommend that you test that the characters you use for the custom message or URL appear correctly on the pre-boot BitLocker recovery screen.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="93111-383">リムーバブルドライブのグループポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="93111-383">Removable Drive Group Policy definitions</span></span>

<span data-ttu-id="93111-384">このセクションでは、Microsoft BitLocker の管理と監視を行うためのリムーバブルドライブのグループポリシー定義について説明します。**コンピューター構成** &gt; **ポリシー** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **MDOP mbam (BitLocker 管理)** &gt; **リムーバブルドライブ**。</span><span class="sxs-lookup"><span data-stu-id="93111-384">This section describes Removable Drive Group Policy definitions for Microsoft BitLocker Administration and Monitoring at the following GPO node: **Computer Configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)** &gt; **Removable Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="93111-385">ポリシー名</span><span class="sxs-lookup"><span data-stu-id="93111-385">Policy name</span></span></th>
<th align="left"><span data-ttu-id="93111-386">概要と推奨されるグループポリシー設定</span><span class="sxs-lookup"><span data-stu-id="93111-386">Overview and suggested Group Policy settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93111-387">リムーバブルドライブでの BitLocker の使用を制御する</span><span class="sxs-lookup"><span data-stu-id="93111-387">Control use of BitLocker on removable drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-388">推奨される構成: <strong> 有効</span><span class="sxs-lookup"><span data-stu-id="93111-388">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="93111-389">このポリシーは、リムーバブルデータドライブでの BitLocker の使用を制御します。</span><span class="sxs-lookup"><span data-stu-id="93111-389">This policy controls the use of BitLocker on removable data drives.</span></span></p>
<p><span data-ttu-id="93111-390">[ <strong> ユーザーがリムーバブルデータドライブに bitlocker 保護を適用することを許可する] をクリックして </strong> 、ユーザーがリムーバブルデータドライブで bitlocker セットアップウィザードを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="93111-390">Click <strong>Allow users to apply BitLocker protection on removable data drives</strong> to allow users to run the BitLocker setup wizard on a removable data drive.</span></span></p>
<p><span data-ttu-id="93111-391">[ <strong> ユーザーがリムーバブルデータドライブ上の bitlocker を一時停止して暗号化を解除することを許可する] をクリックして </strong> 、ユーザーが bitlocker ドライブ暗号化をドライブから削除するか、メンテナンスが実行されているときに暗号化を中断できるようにします。</span><span class="sxs-lookup"><span data-stu-id="93111-391">Click <strong>Allow users to suspend and decrypt BitLocker on removable data drives</strong> to enable users to remove BitLocker drive encryption from the drive or to suspend the encryption while maintenance is performed.</span></span></p>
<p><span data-ttu-id="93111-392">このポリシーが有効になっている場合、[ <strong> ユーザーにリムーバブルデータドライブへの BitLocker 保護の適用を許可する] をクリックすると、 </strong> Mbam クライアントがリムーバブルドライブに関する回復情報を mbam key recovery サーバーに保存し、パスワードが失われた場合にユーザーがドライブを回復できるようにします。</span><span class="sxs-lookup"><span data-stu-id="93111-392">When this policy is enabled, and you click <strong>Allow users to apply BitLocker protection on removable data drives</strong>, the MBAM Client saves the recovery information about removable drives to the MBAM key recovery server and allows users to recover the drive if the password is lost.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93111-393">BitLocker で保護されていないリムーバブル ドライブへの書き込みアクセスを拒否する</span><span class="sxs-lookup"><span data-stu-id="93111-393">Deny write access to removable drives not protected by BitLocker</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-394">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="93111-394">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="93111-395">このポリシーを有効にして、BitLocker で保護されたドライブに対する書き込みアクセス許可のみを許可します。</span><span class="sxs-lookup"><span data-stu-id="93111-395">Enable this policy to allow only write permission to BitLocker-protected drives.</span></span></p>
<p><span data-ttu-id="93111-396">このポリシーを有効にすると、コンピューター上のすべてのリムーバブルデータドライブは、書き込み権限が許可される前に暗号化が必要になります。</span><span class="sxs-lookup"><span data-stu-id="93111-396">When this policy is enabled, all removable data drives on the computer require encryption before write permission is allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93111-397">以前のバージョンの Windows から BitLocker で保護されているリムーバブルドライブへのアクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="93111-397">Allow access to BitLocker-protected removable drives from earlier versions of Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-398">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="93111-398">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="93111-399">このポリシーを有効にすると、FAT ファイルシステムを実行しているコンピューターで、windows Server 2008、Windows Vista、Windows XP、または Windows XP SP2 を実行しているコンピューターで、固定ドライブのロックを解除して表示することができます。</span><span class="sxs-lookup"><span data-stu-id="93111-399">Enable this policy to allow fixed drives with the FAT file system to be unlocked and viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p>
<p><span data-ttu-id="93111-400">このポリシーが構成されていない場合、FAT ファイルシステムで書式設定されたリムーバブルドライブは、Windows Server 2008、Windows Vista、Windows XP (SP3)、または Windows XP SP2 を実行しているコンピューターではロック解除でき、そのコンテンツは表示できます。</span><span class="sxs-lookup"><span data-stu-id="93111-400">When this policy is not configured, removable drives that are formatted with the FAT file system can be unlocked on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2, and their content can be viewed.</span></span> <span data-ttu-id="93111-401">これらのオペレーティングシステムは、BitLocker で保護されたドライブに対して読み取り専用のアクセス許可を持っています。</span><span class="sxs-lookup"><span data-stu-id="93111-401">These operating systems have read-only permission to BitLocker-protected drives.</span></span></p>
<p><span data-ttu-id="93111-402">ポリシーが無効になっている場合、FAT ファイルシステムで書式設定されたリムーバブルドライブのロックを解除することはできません。 Windows Server 2008、Windows Vista、Windows XP SP3、または Windows XP SP2 を実行しているコンピューターでは、これらのコンテンツを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="93111-402">When the policy is disabled, removable drives formatted with the FAT file system cannot be unlocked and their content cannot be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93111-403">リムーバブルデータドライブのパスワードの使用を構成する</span><span class="sxs-lookup"><span data-stu-id="93111-403">Configure use of password for removable data drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-404">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="93111-404">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="93111-405">このポリシーを有効にして、リムーバブルデータドライブのパスワード保護を構成します。</span><span class="sxs-lookup"><span data-stu-id="93111-405">Enable this policy to configure password protection on removable data drives.</span></span></p>
<p><span data-ttu-id="93111-406">このポリシーが構成されていない場合、パスワードは、パスワードの複雑さの要件を含まず、8文字のみを必要とする既定の設定でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="93111-406">When this policy is not configured, passwords are supported with the default settings, which do not include password complexity requirements and which require only eight characters.</span></span></p>
<p><span data-ttu-id="93111-407">セキュリティ強化のために、このポリシーを有効にして <strong> 、[リムーバブルデータドライブにパスワードを要求する] を選び </strong> 、[パスワードの複雑さを要求する] をクリックし、 <strong> </strong> 推奨される <strong> パスワードの最小文字数を設定 </strong> することができます。</span><span class="sxs-lookup"><span data-stu-id="93111-407">For increased security, you can enable this policy and select <strong>Require password for removable data drive</strong>, click <strong>Require password complexity</strong>, and set the preferred <strong>minimum password length</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93111-408">BitLocker で保護されたリムーバブルドライブの回復方法を選択する</span><span class="sxs-lookup"><span data-stu-id="93111-408">Choose how BitLocker-protected removable drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="93111-409">推奨される構成: <strong> 未構成</span><span class="sxs-lookup"><span data-stu-id="93111-409">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="93111-410">BitLocker データ回復エージェントを有効にする、または Active Directory ドメインサービス (AD DS) に BitLocker 回復情報を保存するには、このポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="93111-410">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="93111-411">[未構成] に設定すると、 <strong> </strong> データ回復エージェントが許可され、回復情報は AD DS にバックアップされません。</span><span class="sxs-lookup"><span data-stu-id="93111-411">When set to <strong>Not Configured</strong>, the data recovery agent is allowed, and recovery information is not backed up to AD DS.</span></span></p>
<p><span data-ttu-id="93111-412">MBAM 操作では、AD DS に回復情報をバックアップする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="93111-412">MBAM operation does not require recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
</tbody>
</table>




## <span data-ttu-id="93111-413">関連トピック</span><span class="sxs-lookup"><span data-stu-id="93111-413">Related topics</span></span>


[<span data-ttu-id="93111-414">MBAM 2.5 に対応する環境の準備</span><span class="sxs-lookup"><span data-stu-id="93111-414">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)

[<span data-ttu-id="93111-415">MBAM 2.5 展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="93111-415">MBAM 2.5 Deployment Prerequisites</span></span>](mbam-25-deployment-prerequisites.md)


## <span data-ttu-id="93111-416">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="93111-416">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="93111-417">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="93111-417">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="93111-418">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="93111-418">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>






