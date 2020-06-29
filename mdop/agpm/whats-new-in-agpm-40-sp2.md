---
title: AGPM 4.0 SP2 の新機能
description: AGPM 4.0 SP2 の新機能
author: dansimp
ms.assetid: 5c0dcab4-f27d-4153-8b8e-b280b080be51
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 56369207780cf0795f16eda91f249a26270c4b47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818147"
---
# <span data-ttu-id="df385-103">AGPM 4.0 SP2 の新機能</span><span class="sxs-lookup"><span data-stu-id="df385-103">What's New in AGPM 4.0 SP2</span></span>


<span data-ttu-id="df385-104">このコンテンツでは、Microsoft Advanced グループポリシー管理 (AGPM) 4.0 Service Pack2 (SP2) の拡張機能とサポートされる構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="df385-104">This content describes enhancements and supported configurations for Microsoft Advanced Group Policy Management (AGPM)4.0 Service Pack2 (SP2).</span></span> <span data-ttu-id="df385-105">このコンテンツと他の AGPM ドキュメントの間に違いがある場合は、このコンテンツには権限があることを考慮して、他のドキュメントを置き換えることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="df385-105">If there is a difference between this content and other AGPM documentation, consider this content authoritative and assume that it supersedes the other documentation.</span></span>

## <a href="" id="what-s-new"></a><span data-ttu-id="df385-106">新機能</span><span class="sxs-lookup"><span data-stu-id="df385-106">What’s new</span></span>


<span data-ttu-id="df385-107">AGPM 4.0 SP2 では、次の機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="df385-107">AGPM4.0 SP2 supports the following features and functionality.</span></span>

### <span data-ttu-id="df385-108">Windows 8.1 および Windows Server2012 R2 のサポート</span><span class="sxs-lookup"><span data-stu-id="df385-108">Support for Windows8.1 and Windows Server2012 R2</span></span>

<span data-ttu-id="df385-109">AGPM 4.0 SP2 では、Windows 8.1 および Windows Server2012 R2 オペレーティングシステムのサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="df385-109">AGPM4.0 SP2 adds support for the Windows8.1 and Windows Server2012 R2 operating systems.</span></span>

### <span data-ttu-id="df385-110">クライアント側の新しい拡張子と変更された機能</span><span class="sxs-lookup"><span data-stu-id="df385-110">New and changed client-side extensions</span></span>

<span data-ttu-id="df385-111">Windows 8.1 で新しいポリシー設定をサポートするために、AGPM のためにグループポリシークライアント側の拡張機能が追加または変更されています。</span><span class="sxs-lookup"><span data-stu-id="df385-111">Group Policy client-side extensions have been added or changed for AGPM to support new policy settings in Windows8.1.</span></span> <span data-ttu-id="df385-112">これらのポリシー設定を使用すると、グループポリシー管理者は、2つのグループポリシーオブジェクト (Gpo) またはテンプレートの間で変更される特定のポリシー設定を管理および追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="df385-112">These policy settings enable Group Policy administrators to manage and track Windows8.1–specific policy settings that change between two Group Policy Objects (GPOs) or templates.</span></span> <span data-ttu-id="df385-113">クライアント側の拡張機能を表示するには、AGPM クライアントで利用できる設定と差分レポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="df385-113">To view your client-side extensions, use the settings and difference reports that are available in the AGPM Client.</span></span>

<span data-ttu-id="df385-114">新しい、または変更されたグループポリシークライアント側拡張機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df385-114">The new and changed Group Policy client-side extensions are:</span></span>

-   <span data-ttu-id="df385-115">**ワークフォルダーの設定を指定**します。</span><span class="sxs-lookup"><span data-stu-id="df385-115">**Specify Work Folders settings**.</span></span> <span data-ttu-id="df385-116">このポリシー設定を有効にすると、IT 管理者はワークフォルダーを自動的に作成するように構成することができます。</span><span class="sxs-lookup"><span data-stu-id="df385-116">If you enable this policy setting, IT administrators can configure Work Folders to be created automatically.</span></span> <span data-ttu-id="df385-117">ワークフォルダー機能を使用すると、エンドユーザーは Windows デスクトップデバイスから他のデバイスにファイルを同期することができます。</span><span class="sxs-lookup"><span data-stu-id="df385-117">The Work Folders feature enables end users to synchronize files from their Windows desktop devices to their other devices.</span></span> <span data-ttu-id="df385-118">このポリシー設定を使用して、エンドユーザーのデバイスに同期関係を作成し、ユーザーの作業フォルダーを格納するファイルサーバーの識別方法を構成します。</span><span class="sxs-lookup"><span data-stu-id="df385-118">Use this policy setting to create the synchronization relationship on an end user’s devices and to configure how to identify the file server that stores the user’s Work Folders.</span></span> <span data-ttu-id="df385-119">[**自動プロビジョン**] チェックボックスをオンにすると、ユーザー入力なしで同期パートナーシップが作成され、ユーザーのデバイスへの同期が自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="df385-119">If you select the **Auto provision synchronization** check box, the synchronization partnership will be created without user input, and data will automatically start synchronizing to the user’s device.</span></span> <span data-ttu-id="df385-120">[**自動プロビジョン同期**] チェックボックスをオンにしない場合、ユーザーは入力を提供して同期を開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df385-120">If you do not select the **Auto provision synchronization** check box, users must provide input to start the synchronization.</span></span>

-   <span data-ttu-id="df385-121">**すべてのユーザーに対して自動セットアップを強制**します。</span><span class="sxs-lookup"><span data-stu-id="df385-121">**Force automatic setup for all users**.</span></span> <span data-ttu-id="df385-122">このポリシー設定を有効にした場合、IT 管理者は、エンドユーザーからの入力を必要とせずに、エンドユーザーのデバイスにワークフォルダーのパートナーシップを自動的に作成するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="df385-122">If you enable this policy setting, IT administrators can determine whether to create the Work Folders partnership automatically on end-user devices without input from end users.</span></span> <span data-ttu-id="df385-123">このポリシー設定を有効にした場合、同期は、[**ワークフォルダー設定の指定**] ポリシー設定の構成に従って設定されます。</span><span class="sxs-lookup"><span data-stu-id="df385-123">If you enable this policy setting, the synchronization will be set up according to how you configure the **Specify Work Folders settings** policy setting.</span></span> <span data-ttu-id="df385-124">[**自動セットアップをすべてのユーザーに強制**する] ポリシー設定を [**無効**] または [**未構成**] に設定した場合は、[**自動プロビジョニング**] オプションの設定方法に応じ**て、ワーク**フォルダーのパートナーシップが設定されます。</span><span class="sxs-lookup"><span data-stu-id="df385-124">If you set the **Force automatic setup for all users** policy setting to **Disabled** or **Not configured**, the Work Folders partnership will be configured according to how you set the **Automatic Provisioning** option in the **Specify Work Folders settings** policy setting.</span></span>

<span data-ttu-id="df385-125">ワークフォルダー機能の詳細については、「[ワークフォルダーの概要](https://go.microsoft.com/fwlink/?LinkId=330444)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df385-125">For more information about the Work Folders feature, see [Work Folders Overview](https://go.microsoft.com/fwlink/?LinkId=330444).</span></span>

### <span data-ttu-id="df385-126">顧客のフィードバックと修正プログラムのロールアップ</span><span class="sxs-lookup"><span data-stu-id="df385-126">Customer feedback and hotfix rollup</span></span>

<span data-ttu-id="df385-127">AGPM 4.0 SP2 には、AGPM 4.0 Service Pack1 (SP1) 以降で検出された問題に対処するための修正プログラムのロールアップが含まれています。</span><span class="sxs-lookup"><span data-stu-id="df385-127">AGPM4.0 SP2 includes a rollup of hotfixes to address issues found since the AGPM4.0 Service Pack1 (SP1) release.</span></span> <span data-ttu-id="df385-128">AGPM 4.0 SP2 には、Microsoft Advanced Group Policy Management 4.0 SP1 Hotfix1 を含む最新の修正プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="df385-128">AGPM4.0 SP2 contains the latest fixes up to and including Microsoft Advanced Group Policy Management4.0 SP1 Hotfix1.</span></span> <span data-ttu-id="df385-129">詳細については、サポート技術情報の記事[2873472](https://go.microsoft.com/fwlink/?LinkId=325400)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df385-129">For more information, see Knowledge Base article [2873472](https://go.microsoft.com/fwlink/?LinkId=325400)).</span></span>

### <span data-ttu-id="df385-130">設定と差分レポートの新しいグループポリシーの拡張機能</span><span class="sxs-lookup"><span data-stu-id="df385-130">New Group Policy extensions in settings and difference reports</span></span>

<span data-ttu-id="df385-131">[設定] と [差分] レポートに新しいグループポリシー拡張機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="df385-131">The new Group Policy extensions have been added to the settings and difference reports.</span></span>

### <span data-ttu-id="df385-132">インストーラーの変更とサポート</span><span class="sxs-lookup"><span data-stu-id="df385-132">Installer changes and support</span></span>

<span data-ttu-id="df385-133">AGPM 4.0 SP2 インストーラーの変更とサポートは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df385-133">The changes and support for the AGPM4.0 SP2 installer are:</span></span>

-   <span data-ttu-id="df385-134">Windows 8 または Windows Server 2012 オペレーティングシステムまたはそれ以降のオペレーティングシステムに AGPM 4.0 SP2 をインストールした場合、AGPM インストーラーは、必要な必須ソフトウェア (グループポリシー管理コンソール (GPMC) と Microsoft .NET Framework 3.5) がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="df385-134">If you install AGPM4.0 SP2 on the Windows 8 or Windows Server 2012 operating system or later operating systems, the AGPM installer verifies that the required prerequisite software (the Group Policy Management Console (GPMC) and the Microsoft .NET Framework3.5) is installed.</span></span> <span data-ttu-id="df385-135">この必須ソフトウェアがインストールされていない場合は、AGPM 4.0 SP2 インストールがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="df385-135">If this prerequisite software is not installed, the AGPM4.0 SP2 installation is blocked.</span></span>

-   <span data-ttu-id="df385-136">AGPM サーバーをインストールすると、WCF のアクティブ化、非 HTTP アクティベーション、Windows プロセスのアクティブ化サービスが自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="df385-136">When you install the AGPM Server, WCF Activation, Non-HTTP Activation, and Windows Process Activation Service are automatically enabled.</span></span>

-   <span data-ttu-id="df385-137">Windows Vista クライアントオペレーティングシステム以降のオペレーティングシステムでは、AGPM 4.0 SP2 をインストールする前に、使用しているオペレーティングシステムに対応したバージョンのリモートシステム管理ツールをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="df385-137">On the WindowsVista client operating system and later operating systems, download the appropriate version of the Remote System Administration Tools for your operating system before you install AGPM4.0 SP2.</span></span>

-   <span data-ttu-id="df385-138">AGPM 4.0 SP2 は、サポートされている以前のオペレーティングシステムとの下位互換性をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="df385-138">AGPM4.0 SP2 supports backward compatibility with older supported operating systems.</span></span>

### <span data-ttu-id="df385-139">指定した構成パラメーターを指定せずに AGPM 4.0 SP2 にアップグレードする機能</span><span class="sxs-lookup"><span data-stu-id="df385-139">Ability to upgrade to AGPM4.0 SP2 without reentering configuration parameters</span></span>

<span data-ttu-id="df385-140">次の表に示すように、AGPM クライアントまたは AGPM サーバーを AGPM 4.0 SP2 にアップグレードすることができます。この場合は、次の表に示すように、agpm 4.0 以降の構成パラメーターを再入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df385-140">You can upgrade the AGPM Client or AGPM Server to AGPM4.0 SP2 without being prompted to reenter configuration parameters (called the Smart Upgrade) only from AGPM4.0 onward, as shown in the following table.</span></span> <span data-ttu-id="df385-141">表に示すように、他のバージョンの AGPM から AGPM 4.0 SP2 にアップグレードする場合は、従来のアップグレードを使用する必要があります。これには、構成パラメーターを再入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df385-141">If you are upgrading to AGPM4.0 SP2 from other versions of AGPM, as shown in the table, you must use the Classic Upgrade, which requires you to reenter the configuration parameters.</span></span> <span data-ttu-id="df385-142">AGPM の各バージョンは特定のオペレーティングシステムに関連付けられているため、「[インストールする agpm のバージョンを選択](https://go.microsoft.com/fwlink/?LinkId=254350)する」を参照して、agpm をアップグレードする前に、適切なオペレーティングシステムにアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="df385-142">Because each version of AGPM is associated with a particular operating system, see [Choosing Which Version of AGPM to Install](https://go.microsoft.com/fwlink/?LinkId=254350) and make sure that you upgrade your operating system as appropriate before you upgrade AGPM.</span></span>

**<span data-ttu-id="df385-143">AGPM 4.0 SP2 でサポートされているアップグレード</span><span class="sxs-lookup"><span data-stu-id="df385-143">AGPM 4.0 SP2 supported upgrades</span></span>**

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="df385-144">アップグレードできる AGPM バージョン</span><span class="sxs-lookup"><span data-stu-id="df385-144">AGPM version from which you can upgrade</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="df385-145">2.5</span><span class="sxs-lookup"><span data-stu-id="df385-145">2.5</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="df385-146">3.0</span><span class="sxs-lookup"><span data-stu-id="df385-146">3.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="df385-147">4.0</span><span class="sxs-lookup"><span data-stu-id="df385-147">4.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="df385-148">4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="df385-148">4.0 SP1</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="df385-149">4.0 SP2</span><span class="sxs-lookup"><span data-stu-id="df385-149">4.0 SP2</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="df385-150">2.5</span><span class="sxs-lookup"><span data-stu-id="df385-150">2.5</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-151">該当なし</span><span class="sxs-lookup"><span data-stu-id="df385-151">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-152">従来のアップグレード</span><span class="sxs-lookup"><span data-stu-id="df385-152">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-153">従来のアップグレード</span><span class="sxs-lookup"><span data-stu-id="df385-153">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-154">インストールがブロックされている</span><span class="sxs-lookup"><span data-stu-id="df385-154">Installation is blocked</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-155">インストールがブロックされている</span><span class="sxs-lookup"><span data-stu-id="df385-155">Installation is blocked</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="df385-156">3.0</span><span class="sxs-lookup"><span data-stu-id="df385-156">3.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-157">該当なし</span><span class="sxs-lookup"><span data-stu-id="df385-157">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-158">該当なし</span><span class="sxs-lookup"><span data-stu-id="df385-158">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-159">従来のアップグレード</span><span class="sxs-lookup"><span data-stu-id="df385-159">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-160">インストールがブロックされている</span><span class="sxs-lookup"><span data-stu-id="df385-160">Installation is blocked</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-161">インストールがブロックされている</span><span class="sxs-lookup"><span data-stu-id="df385-161">Installation is blocked</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="df385-162">4.0</span><span class="sxs-lookup"><span data-stu-id="df385-162">4.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-163">該当なし</span><span class="sxs-lookup"><span data-stu-id="df385-163">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-164">該当なし</span><span class="sxs-lookup"><span data-stu-id="df385-164">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-165">該当なし</span><span class="sxs-lookup"><span data-stu-id="df385-165">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-166">スマートアップグレード</span><span class="sxs-lookup"><span data-stu-id="df385-166">Smart Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-167">スマートアップグレード</span><span class="sxs-lookup"><span data-stu-id="df385-167">Smart Upgrade</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="df385-168">4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="df385-168">4.0 SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-169">該当なし</span><span class="sxs-lookup"><span data-stu-id="df385-169">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-170">該当なし</span><span class="sxs-lookup"><span data-stu-id="df385-170">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-171">該当なし</span><span class="sxs-lookup"><span data-stu-id="df385-171">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-172">該当なし</span><span class="sxs-lookup"><span data-stu-id="df385-172">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-173">スマートアップグレード</span><span class="sxs-lookup"><span data-stu-id="df385-173">Smart Upgrade</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="df385-174">サポートされている構成</span><span class="sxs-lookup"><span data-stu-id="df385-174">Supported configurations</span></span>


<span data-ttu-id="df385-175">AGPM 4.0 SP2 では、次の表に示す構成がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="df385-175">AGPM4.0 SP2 supports the configurations in the following table.</span></span> <span data-ttu-id="df385-176">AGPM では混合構成がサポートされていますが、windows 8.1 と windows Server2012 R2、windows 8、windows Server 2012 など、同じオペレーティングシステム行で AGPM クライアントと AGPM サーバーを実行することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="df385-176">Although AGPM supports mixed configurations, we strongly recommend that you run the AGPM Client and AGPM Server on the same operating system line—for example, Windows8.1 with Windows Server2012 R2, Windows 8 with Windows Server 2012, and so on.</span></span>

**<span data-ttu-id="df385-177">AGPM 4.0 SP2 でサポートされているオペレーティングシステムとポリシー設定</span><span class="sxs-lookup"><span data-stu-id="df385-177">AGPM4.0 SP2 supported operating systems and policy settings</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="df385-178">AGPM サーバーでサポートされている構成</span><span class="sxs-lookup"><span data-stu-id="df385-178">Supported configurations for the AGPM Server</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="df385-179">AGPM クライアントでサポートされている構成</span><span class="sxs-lookup"><span data-stu-id="df385-179">Supported configurations for the AGPM Client</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="df385-180">AGPM のサポート</span><span class="sxs-lookup"><span data-stu-id="df385-180">AGPM Support</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="df385-181">Windows Server2012 R2 または Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="df385-181">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-182">Windows Server2012 R2 または Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="df385-182">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-183">サポートされています</span><span class="sxs-lookup"><span data-stu-id="df385-183">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="df385-184">Windows Server2012 R2、Windows Server 2012、Windows 8.1、または Windows 8</span><span class="sxs-lookup"><span data-stu-id="df385-184">Windows Server2012 R2, Windows Server 2012, Windows8.1, or Windows 8</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-185">Windows Server 2012 または Windows 8</span><span class="sxs-lookup"><span data-stu-id="df385-185">Windows Server 2012 or Windows 8</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-186">サポートされますが、Windows 8.1 でのみ存在するポリシー設定や設定項目は編集できません。</span><span class="sxs-lookup"><span data-stu-id="df385-186">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="df385-187">Windows Server2008R2 または Windows7</span><span class="sxs-lookup"><span data-stu-id="df385-187">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-188">Windows Server2008R2 または Windows7</span><span class="sxs-lookup"><span data-stu-id="df385-188">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-189">サポートされますが、Windows 8.1 または Windows 8 でのみ存在するポリシー設定や設定項目は編集できません。</span><span class="sxs-lookup"><span data-stu-id="df385-189">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1 or Windows 8</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="df385-190">Windows Server 2012、Windows Server2008R2、Windows 8、または Windows7</span><span class="sxs-lookup"><span data-stu-id="df385-190">Windows Server 2012, Windows Server2008R2, Windows 8, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-191">Windows Server2008 または Windows Vista Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="df385-191">Windows Server2008 or WindowsVista with Service Pack 1 (SP1)</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-192">サポートされますが、windows Server2012 R2、Windows Server 2012、Windows Server2008R2、windows 8.1、Windows 8、または Windows7 でのみ存在するポリシー設定や環境設定項目は編集できません。</span><span class="sxs-lookup"><span data-stu-id="df385-192">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, Windows 8, or Windows7</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="df385-193">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="df385-193">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-194">Windows Server 2012、Windows Server2008R2、Windows 8、または Windows7</span><span class="sxs-lookup"><span data-stu-id="df385-194">Windows Server 2012, Windows Server2008R2, Windows 8, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-195">サポートされていないアプリ</span><span class="sxs-lookup"><span data-stu-id="df385-195">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="df385-196">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="df385-196">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-197">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="df385-197">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="df385-198">サポートされますが、windows Server2012 R2、Windows Server 2012、Windows Server2008R2、windows 8.1、Windows 8、または Windows7 でのみ存在するポリシー設定または設定項目をレポートまたは編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="df385-198">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, Windows 8, or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="df385-199">AGPM 4.0 SP2 をインストールするための前提条件</span><span class="sxs-lookup"><span data-stu-id="df385-199">Prerequisites for installing AGPM4.0 SP2</span></span>


<span data-ttu-id="df385-200">次の表では、リモートサーバー管理ツールで .NET Framework 3.5 または GPMC が見つからない場合の Windows 8.1 の AGPM 4.0 SP2 クライアントとサーバーインストーラーの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="df385-200">The following table describes the behavior of AGPM4.0 SP2 Client and Server installers on Windows8.1 when the .NET Framework3.5 or the GPMC in the Remote Server Administration Tools is missing.</span></span>

**<span data-ttu-id="df385-201">AGPM クライアント</span><span class="sxs-lookup"><span data-stu-id="df385-201">AGPM Client</span></span>**

**<span data-ttu-id="df385-202">AGPM サーバー</span><span class="sxs-lookup"><span data-stu-id="df385-202">AGPM Server</span></span>**

**<span data-ttu-id="df385-203">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="df385-203">Operating system</span></span>**

**<span data-ttu-id="df385-204">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="df385-204">.NET Framework</span></span>**

**<span data-ttu-id="df385-205">リモート サーバー管理ツール</span><span class="sxs-lookup"><span data-stu-id="df385-205">Remote Server Administration Tools</span></span>**

**<span data-ttu-id="df385-206">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="df385-206">.NET Framework</span></span>**

**<span data-ttu-id="df385-207">リモート サーバー管理ツール</span><span class="sxs-lookup"><span data-stu-id="df385-207">Remote Server Administration Tools</span></span>**

**<span data-ttu-id="df385-208">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="df385-208">Windows8.1</span></span>**

<span data-ttu-id="df385-209">.NET Framework 3.5 が有効になっていない場合、またはインストールされていない場合、インストーラーはインストールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="df385-209">If the .NET Framework3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="df385-210">GPMC が有効になっていないか、インストールされていない場合は、インストーラーによってインストールがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="df385-210">If the GPMC is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="df385-211">.NET Framework 3.5 が有効になっていない場合、またはインストールされていない場合、インストーラーはインストールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="df385-211">If the .NET Framework3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="df385-212">GPMC が有効になっていないか、インストールされていない場合は、インストーラーによってインストールがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="df385-212">If the GPMC is not enabled or installed, the installer blocks the installation.</span></span>

**<span data-ttu-id="df385-213">Windows Server2012 R2</span><span class="sxs-lookup"><span data-stu-id="df385-213">Windows Server2012 R2</span></span>**

<span data-ttu-id="df385-214">.NET Framework 3.5 が有効になっていない場合、またはインストールされていない場合、インストーラーはインストールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="df385-214">If the .NET Framework3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="df385-215">GPMC が有効になっていない場合は、インストール中にインストーラーによって有効になります。</span><span class="sxs-lookup"><span data-stu-id="df385-215">If the GPMC is not enabled, the installer enables it during the installation.</span></span>

<span data-ttu-id="df385-216">.NET Framework 3.5 が有効になっていない場合、またはインストールされていない場合、インストーラーはインストールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="df385-216">If the .NET Framework3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="df385-217">GPMC が有効になっていない場合は、インストール中にインストーラーによって有効になります。</span><span class="sxs-lookup"><span data-stu-id="df385-217">If the GPMC is not enabled, the installer enables it during the installation.</span></span>

 

## <span data-ttu-id="df385-218">MDOP 技術の入手方法</span><span class="sxs-lookup"><span data-stu-id="df385-218">How to Get MDOP Technologies</span></span>


<span data-ttu-id="df385-219">AGPM 4.0 SP2 は、Microsoft デスクトップ最適化パック (MDOP) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="df385-219">AGPM 4.0 SP2 is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="df385-220">MDOP は、Microsoft ソフトウェアアシュアランスの一部です。</span><span class="sxs-lookup"><span data-stu-id="df385-220">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="df385-221">Microsoft ソフトウェアアシュアランスの詳細と MDOP の入手方法については、「 [mdop の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」を参照してください https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="df385-221">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="df385-222">関連トピック</span><span class="sxs-lookup"><span data-stu-id="df385-222">Related topics</span></span>


[<span data-ttu-id="df385-223">高度なグループ ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="df385-223">Advanced Group Policy Management</span></span>](index.md)

[<span data-ttu-id="df385-224">Microsoft Advanced Group Policy Management (AGPM) 4.0 SP2 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="df385-224">Release Notes for Microsoft Advanced Group Policy Management 4.0 SP2</span></span>](release-notes-for-microsoft-advanced-group-policy-management-40-sp2.md)

[<span data-ttu-id="df385-225">インストールする AGPM のバージョンの選択</span><span class="sxs-lookup"><span data-stu-id="df385-225">Choosing Which Version of AGPM to Install</span></span>](choosing-which-version-of-agpm-to-install.md)

 

 





