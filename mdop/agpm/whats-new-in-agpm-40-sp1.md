---
title: AGPM 4.0 SP1 の新機能
description: AGPM 4.0 SP1 の新機能
author: dansimp
ms.assetid: c6a3d94a-13c3-44e6-a466-c3011879999e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: eca1ee4a1c2eb943a25246dc31b127eaf72ff5fc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818154"
---
# <span data-ttu-id="8421e-103">AGPM 4.0 SP1 の新機能</span><span class="sxs-lookup"><span data-stu-id="8421e-103">What's New in AGPM 4.0 SP1</span></span>


<span data-ttu-id="8421e-104">この "最新情報" のコンテンツでは、Microsoft Advanced グループポリシー管理 (AGPM) 4.0 SP1 の拡張機能とサポートされる構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="8421e-104">This “What’s New” content describes enhancements and supported configurations for Microsoft Advanced Group Policy Management (AGPM) 4.0 SP1.</span></span> <span data-ttu-id="8421e-105">このコンテンツと他の AGPM ドキュメントの間に違いがある場合、このコンテンツは、権限があると見なされ、この製品に含まれているコンテンツを置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="8421e-105">If there is a difference between this content and other AGPM documentation, this content should be considered authoritative and should supersede the content included with this product.</span></span>

## <a href="" id="what-s-new"></a><span data-ttu-id="8421e-106">新機能</span><span class="sxs-lookup"><span data-stu-id="8421e-106">What’s new</span></span>


<span data-ttu-id="8421e-107">AGPM 4.0 SP1 では、次の機能強化がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8421e-107">AGPM 4.0 SP1 supports the following enhancements:</span></span>

### <span data-ttu-id="8421e-108">クライアント側の新しい拡張子と変更された機能</span><span class="sxs-lookup"><span data-stu-id="8421e-108">New and changed client-side extensions</span></span>

<span data-ttu-id="8421e-109">Windows 8 および Windows Server 2012 で新しいグループポリシーをサポートするために、AGPM のためにグループポリシークライアント側の拡張機能 (CSEs) が追加または変更されています。</span><span class="sxs-lookup"><span data-stu-id="8421e-109">Group Policy client-side extensions (CSEs) have been added or changed for AGPM to support new Group Policies in Windows 8 and Windows Server 2012.</span></span> <span data-ttu-id="8421e-110">これらのグループポリシーを使用すると、グループポリシー管理者は、2つのグループポリシーオブジェクト (Gpo) とテンプレートの間で変更される Windows 8 固有のグループポリシー設定を管理および追跡することができます。</span><span class="sxs-lookup"><span data-stu-id="8421e-110">These group policies enable Group Policy administrators to manage and track Windows 8-specific Group Policy settings that change between two Group Policy Objects (GPOs) or templates.</span></span> <span data-ttu-id="8421e-111">また、Windows 8 固有の設定を使用してカスタム Gpo を作成し、Gpo をテンプレートとして構成して保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="8421e-111">You can also create custom GPOs, with Windows 8-specific settings, and configure and save the GPOs as a template.</span></span> <span data-ttu-id="8421e-112">CSEs を表示するには、AGPM 4.0 SP1 クライアントで利用可能な設定と差分レポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="8421e-112">To view your CSEs, use the settings and difference reports that are available in the AGPM 4.0 SP1 client.</span></span>

<span data-ttu-id="8421e-113">新しい、または変更されたグループポリシークライアント側拡張機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8421e-113">The new and changed Group Policy client-side extensions are:</span></span>

-   <span data-ttu-id="8421e-114">**集約型アクセスポリシー:** グループポリシー管理者が、[ファイルサーバー] などのグループポリシーサーバーに対して集約型アクセスポリシーを指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8421e-114">**Central Access Policy:** Enables Group Policy administrators to specify Central Access Policies on Group Policy servers, for example, file servers.</span></span> <span data-ttu-id="8421e-115">集約型アクセスポリシーは、GPO 項目によって指定され、ポリシーのターゲットに適用され、リソースの集中アクセスと制御を容易にするための承認ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="8421e-115">Central Access Policy is an authorization policy that is specified by a GPO item and applied to policy targets to facilitate centralized access and control of resources.</span></span> <span data-ttu-id="8421e-116">これらの中央アクセスポリシーは、Active Directory 内のグループポリシークライアントコンピューターで構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8421e-116">These Central Access Policies must be configured on a Group Policy client computer from within Active Directory.</span></span> <span data-ttu-id="8421e-117">グループポリシーは、適用する必要があるコンピューターに対して、適用可能な集約型アクセスポリシーの知識を配布します。</span><span class="sxs-lookup"><span data-stu-id="8421e-117">A Group Policy distributes the knowledge of an applicable Central Access Policy to the computers that have to enforce it.</span></span>

-   <span data-ttu-id="8421e-118">**名前解決ポリシーの変更:** グループポリシー管理者が dns クライアントコンピューター上の DNS セキュリティと DirectAccess の設定を構成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8421e-118">**Name Resolution Policy changes:** Enables Group Policy administrators to configure settings for DNS security and DirectAccess on DNS client computers.</span></span> <span data-ttu-id="8421e-119">標準 DNS サーバー設定とエンコード設定を構成するための新しいタブが追加されました。</span><span class="sxs-lookup"><span data-stu-id="8421e-119">New tabs for configuring Generic DNS Server settings and Encoding settings have been added.</span></span>

-   <span data-ttu-id="8421e-120">**グループポリシーの基本設定の変更:** Windows 8 用に追加された Internet Explorer 10 設定の構成と管理のサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="8421e-120">**Group Policy Preference changes:** Adds support for the configuration and management of Internet Explorer 10 settings that were added for Windows 8.</span></span>

-   <span data-ttu-id="8421e-121">**リモートアプリケーションとデスクトップ接続:** グループポリシー管理者は、リモートアプリケーションとデスクトップ接続に使用する既定の接続 URL を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="8421e-121">**Remote Application and Desktop Connections:** Lets Group Policy administrators specify the default connection URL that is used for Remote Application and Desktop Connections.</span></span>

-   <span data-ttu-id="8421e-122">**Windows To Go スタートアップオプション:** グループポリシー管理者は、Windows to Go ワークスペースを含む USB デバイスが接続されている場合に、コンピューターが Windows を起動するかどうかを構成できます。</span><span class="sxs-lookup"><span data-stu-id="8421e-122">**Windows To Go Startup Options:** Lets Group Policy administrators configure whether the computer will boot to Windows To Go if a USB device that contains a Windows To Go workspace is connected.</span></span>

-   <span data-ttu-id="8421e-123">**Windows To Go Hibernate のオプション:** グループポリシー管理者は、コンピューターが Windows To Go ワークスペースから開始されたときに、コンピューターが休止状態のスリープ状態 (S4) を使用できるかどうかを構成できます。</span><span class="sxs-lookup"><span data-stu-id="8421e-123">**Windows To Go Hibernate Options:** Lets Group Policy administrators configure whether a computer can use the hibernation sleep state (S4) when the computer is started from a Windows To Go workspace.</span></span>

### <span data-ttu-id="8421e-124">顧客のフィードバックと修正プログラムのロールアップ</span><span class="sxs-lookup"><span data-stu-id="8421e-124">Customer feedback and hotfix rollup</span></span>

<span data-ttu-id="8421e-125">AGPM 4.0 SP1 には、AGPM 4.0 リリース以降で検出された問題に対処するための修正プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8421e-125">AGPM 4.0 SP1 includes a rollup of fixes to address issues found since the AGPM 4.0 release.</span></span> <span data-ttu-id="8421e-126">AGPM 4.0 SP1 には、Microsoft Advanced Group Policy Management 4.0 Hotfix 1 までの最新の修正プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8421e-126">AGPM 4.0 SP1 contains the latest fixes up to and including Microsoft Advanced Group Policy Management 4.0 Hotfix 1.</span></span>

### <span data-ttu-id="8421e-127">設定と差分レポートで、新しいグループポリシーの拡張機能が表示される</span><span class="sxs-lookup"><span data-stu-id="8421e-127">Settings and difference reports show new Group Policy extensions</span></span>

<span data-ttu-id="8421e-128">[設定] と [差分] レポートに新しいグループポリシー拡張機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="8421e-128">The new Group Policy extensions have been added to the settings and difference reports.</span></span>

### <span data-ttu-id="8421e-129">インストーラーの変更とサポート</span><span class="sxs-lookup"><span data-stu-id="8421e-129">Installer changes and support</span></span>

<span data-ttu-id="8421e-130">AGPM 4.0 SP1 インストーラーの変更とサポートは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8421e-130">The changes and support for the AGPM 4.0 SP1 installer are:</span></span>

-   <span data-ttu-id="8421e-131">Windows 8 または Windows Server 2012 で AGPM 4.0 SP1 をインストールする場合、AGPM インストーラーは、必須の必須ソフトウェア (グループポリシー管理コンソールと .NET 3.5 フレームワーク) がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8421e-131">If you install AGPM 4.0 SP1 on Windows 8 or Windows Server 2012, the AGPM installer verifies that the required prerequisite software (Group Policy Management Console and the .NET 3.5 Framework) is installed.</span></span> <span data-ttu-id="8421e-132">これらの前提条件がインストールされていない場合、AGPM 4.0 SP1 のインストールはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="8421e-132">If these prerequisites are not installed, the AGPM 4.0 SP1 installation is blocked.</span></span>

-   <span data-ttu-id="8421e-133">AGPM 4.0 SP1 をインストールすると、WCF のアクティブ化、非 HTTP アクティベーション、Windows プロセスのアクティブ化サービスが自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="8421e-133">When you install AGPM 4.0 SP1, WCF Activation, Non-HTTP Activation, and Windows Process Activation Service are automatically enabled.</span></span>

-   <span data-ttu-id="8421e-134">Windows Vista、Windows 7、Windows 8 クライアントオペレーティングシステムでは、AGPM 4.0 SP1 をインストールする前に、使用しているオペレーティングシステム用の適切なバージョンのリモートシステム管理ツールキットをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8421e-134">On Windows Vista, Windows 7, and Windows 8 client operating systems, download the appropriate version of the Remote System Administration Toolkit for your operating system before you install AGPM 4.0 SP1.</span></span>

-   <span data-ttu-id="8421e-135">サポートされている以前のオペレーティングシステムとの下位互換性がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8421e-135">Backward compatibility with older supported operating systems is supported.</span></span>

### <span data-ttu-id="8421e-136">構成パラメーターを再入力せずに、AGPM 4.0 SP1 にアップグレードまたは更新する機能</span><span class="sxs-lookup"><span data-stu-id="8421e-136">Ability to upgrade or update to AGPM 4.0 SP1 without re-entering configuration parameters</span></span>

<span data-ttu-id="8421e-137">次の表に示すように、AGPM クライアントまたはサーバーは、AGPM 4.0 からのみ agpm 4.0 SP1 にアップグレードできます ("スマートアップグレード" と呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="8421e-137">You can upgrade the AGPM client or server to AGPM 4.0 SP1 only from AGPM 4.0 without being prompted to re-enter configuration parameters (called “Smart Upgrade”), as shown in the following table.</span></span> <span data-ttu-id="8421e-138">表に示されているように、他のバージョンの AGPM から AGPM 4.0 SP1 にアップグレードする場合は、構成パラメーターを再入力する必要がある "クラシックアップグレード" を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8421e-138">If you are upgrading to AGPM 4.0 SP1 from other versions of AGPM, as shown in the table, you must use the “Classic Upgrade,” which requires you to re-enter the configuration parameters.</span></span> <span data-ttu-id="8421e-139">AGPM の各バージョンは特定のオペレーティングシステムに関連付けられているため、[インストールする agpm のバージョンを選択](https://go.microsoft.com/fwlink/?LinkId=254350)する方法を参照して、アップグレードを実行する前に、必要に応じてオペレーティングシステムをアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="8421e-139">Since each version of AGPM is associated with a particular operating system, refer to [Choosing Which Version of AGPM to Install](https://go.microsoft.com/fwlink/?LinkId=254350), and be sure to upgrade your operating system as appropriate before performing an upgrade.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8421e-140">アップグレードできる AGPM バージョン</span><span class="sxs-lookup"><span data-stu-id="8421e-140">AGPM Version From Which You Can Upgrade</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="8421e-141">2.5</span><span class="sxs-lookup"><span data-stu-id="8421e-141">2.5</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="8421e-142">3.0</span><span class="sxs-lookup"><span data-stu-id="8421e-142">3.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="8421e-143">4.0</span><span class="sxs-lookup"><span data-stu-id="8421e-143">4.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="8421e-144">4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="8421e-144">4.0 SP1</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8421e-145">2.5</span><span class="sxs-lookup"><span data-stu-id="8421e-145">2.5</span></span></p></td>
<td align="left"><p><span data-ttu-id="8421e-146">適用不可能</span><span class="sxs-lookup"><span data-stu-id="8421e-146">Not Applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="8421e-147">従来のアップグレード</span><span class="sxs-lookup"><span data-stu-id="8421e-147">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="8421e-148">従来のアップグレード</span><span class="sxs-lookup"><span data-stu-id="8421e-148">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="8421e-149">インストールがブロックされている</span><span class="sxs-lookup"><span data-stu-id="8421e-149">Installation is blocked</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8421e-150">3.0</span><span class="sxs-lookup"><span data-stu-id="8421e-150">3.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="8421e-151">適用不可能</span><span class="sxs-lookup"><span data-stu-id="8421e-151">Not Applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="8421e-152">適用不可能</span><span class="sxs-lookup"><span data-stu-id="8421e-152">Not Applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="8421e-153">従来のアップグレード</span><span class="sxs-lookup"><span data-stu-id="8421e-153">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="8421e-154">インストールがブロックされている</span><span class="sxs-lookup"><span data-stu-id="8421e-154">Installation is blocked</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8421e-155">4.0</span><span class="sxs-lookup"><span data-stu-id="8421e-155">4.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="8421e-156">適用不可能</span><span class="sxs-lookup"><span data-stu-id="8421e-156">Not Applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="8421e-157">適用不可能</span><span class="sxs-lookup"><span data-stu-id="8421e-157">Not Applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="8421e-158">適用不可能</span><span class="sxs-lookup"><span data-stu-id="8421e-158">Not Applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="8421e-159">スマートアップグレード</span><span class="sxs-lookup"><span data-stu-id="8421e-159">Smart Upgrade</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="8421e-160">サポートされている構成</span><span class="sxs-lookup"><span data-stu-id="8421e-160">Supported configurations</span></span>


<span data-ttu-id="8421e-161">AGPM では、次の表に示す構成がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8421e-161">AGPM supports the configurations in the following table.</span></span> <span data-ttu-id="8421e-162">AGPM では混合構成がサポートされていますが、AGPM クライアントとサーバーは同じオペレーティングシステムファミリで実行することを強くお勧めします。たとえば、windows 8 では windows Server 2012、windows 7 は windows Server 2008 R2 などです。</span><span class="sxs-lookup"><span data-stu-id="8421e-162">Although AGPM supports mixed configurations, it is strongly recommended that you run the AGPM client and server on the same operating system family, for example, Windows 8 with Windows Server 2012, Windows 7 with Windows Server 2008 R2, and so on.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8421e-163">AGPM 4.0 SP1 サーバーでサポートされている構成</span><span class="sxs-lookup"><span data-stu-id="8421e-163">Supported Configurations for AGPM 4.0 SP1 Server</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="8421e-164">AGPM 4.0 SP1 クライアントでサポートされている構成</span><span class="sxs-lookup"><span data-stu-id="8421e-164">Supported Configurations for AGPM 4.0 SP1 Client</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="8421e-165">AGPM 4.0 SP1 のサポート</span><span class="sxs-lookup"><span data-stu-id="8421e-165">AGPM 4.0 SP1 Support</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8421e-166">Windows 8 または Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="8421e-166">Windows 8 or Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="8421e-167">Windows 8 または Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="8421e-167">Windows 8 or Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="8421e-168">サポートされています</span><span class="sxs-lookup"><span data-stu-id="8421e-168">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8421e-169">Windows Server 2008 R2 または Windows 7</span><span class="sxs-lookup"><span data-stu-id="8421e-169">Windows Server 2008 R2 or Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="8421e-170">Windows Server 2008 R2 または Windows 7</span><span class="sxs-lookup"><span data-stu-id="8421e-170">Windows Server 2008 R2 or Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="8421e-171">サポートされますが、Windows 8 にのみ存在するポリシー設定や設定項目は編集できません。</span><span class="sxs-lookup"><span data-stu-id="8421e-171">Supported, but cannot edit policy settings or preference items that exist only in Windows 8</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8421e-172">Windows Server 2008 R2 または windows 7 または windows 8 または windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="8421e-172">Windows Server 2008 R2 or Windows 7 or Windows 8 or Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="8421e-173">Windows Server 2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="8421e-173">Windows Server 2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="8421e-174">サポートされますが、Windows Server 2008 R2 または Windows 7 または windows 8 でのみ存在するポリシー設定や基本設定項目は編集できません。</span><span class="sxs-lookup"><span data-stu-id="8421e-174">Supported, but cannot edit policy settings or preference items that exist only in Windows Server 2008 R2 or Windows 7 or Windows 8.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8421e-175">Windows Server 2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="8421e-175">Windows Server 2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="8421e-176">Windows Server 2008 R2 または windows 7 または windows 8 または windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="8421e-176">Windows Server 2008 R2 or Windows 7 or Windows 8 or Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="8421e-177">サポートされています</span><span class="sxs-lookup"><span data-stu-id="8421e-177">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8421e-178">Windows Server 2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="8421e-178">Windows Server 2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="8421e-179">Windows Server 2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="8421e-179">Windows Server 2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="8421e-180">サポートされますが、Windows Server 2008 R2 または Windows 7 または windows 8 でのみ存在するポリシー設定または設定項目を報告または編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="8421e-180">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server 2008 R2 or Windows 7 or Windows 8</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="8421e-181">AGPM 4.0 SP1 をインストールするための前提条件</span><span class="sxs-lookup"><span data-stu-id="8421e-181">Prerequisites for installing AGPM 4.0 SP1</span></span>


<span data-ttu-id="8421e-182">次の表では、.NET 3.5 またはリモートサーバー管理ツール (RSAT) 内のグループポリシー管理コンソールが見つからない場合の、AGPM 4.0 SP1 クライアントとサーバーインストーラーでの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="8421e-182">The following table describes the behavior on Windows 8 of AGPM 4.0 SP1 client and server installers when .NET 3.5 or the Group Policy Management Console in the Remote Server Administration Tools (RSAT) is missing.</span></span>

**<span data-ttu-id="8421e-183">AGPM クライアント 4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="8421e-183">AGPM Client 4.0 SP1</span></span>**

**<span data-ttu-id="8421e-184">AGPM サーバー 4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="8421e-184">AGPM Server 4.0 SP1</span></span>**

**<span data-ttu-id="8421e-185">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="8421e-185">Operating System</span></span>**

**<span data-ttu-id="8421e-186">.NET</span><span class="sxs-lookup"><span data-stu-id="8421e-186">.NET</span></span>**

**<span data-ttu-id="8421e-187">RSAT</span><span class="sxs-lookup"><span data-stu-id="8421e-187">RSAT</span></span>**

**<span data-ttu-id="8421e-188">.NET</span><span class="sxs-lookup"><span data-stu-id="8421e-188">.NET</span></span>**

**<span data-ttu-id="8421e-189">RSAT</span><span class="sxs-lookup"><span data-stu-id="8421e-189">RSAT</span></span>**

**<span data-ttu-id="8421e-190">Windows 8</span><span class="sxs-lookup"><span data-stu-id="8421e-190">Windows 8</span></span>**

<span data-ttu-id="8421e-191">.NET 3.5 が有効になっていない場合、またはインストールされていない場合、インストーラーはインストールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="8421e-191">If .NET 3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="8421e-192">GPMC が有効になっていないか、システムにインストールされていない場合は、インストーラーによってインストールがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="8421e-192">If GPMC is not enabled or installed on the system, the installer blocks the installation.</span></span>

<span data-ttu-id="8421e-193">.NET 3.5 が有効になっていない場合、またはインストールされていない場合、インストーラーはインストールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="8421e-193">If .NET 3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="8421e-194">GPMC が有効になっていないか、システムにインストールされていない場合は、インストーラーによってインストールがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="8421e-194">If GPMC is not enabled or installed on the system, the installer blocks the installation.</span></span>

**<span data-ttu-id="8421e-195">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="8421e-195">Windows Server 2012</span></span>**

<span data-ttu-id="8421e-196">.NET 3.5 が有効になっていない場合、またはインストールされていない場合、インストーラーはインストールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="8421e-196">If .NET 3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="8421e-197">GPMC が有効になっていない場合は、インストール中にインストーラーによって有効になります。</span><span class="sxs-lookup"><span data-stu-id="8421e-197">If GPMC is not enabled, the installer enables it during the installation.</span></span>

<span data-ttu-id="8421e-198">.NET 3.5 が有効になっていない場合、またはインストールされていない場合、インストーラーはインストールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="8421e-198">If .NET 3.5 is not enabled or installed, the installer blocks the installation.</span></span>

<span data-ttu-id="8421e-199">GPMC が有効になっていない場合は、インストール中にインストーラーによって有効になります。</span><span class="sxs-lookup"><span data-stu-id="8421e-199">If GPMC is not enabled, the installer enables it during the installation.</span></span>

 

## <span data-ttu-id="8421e-200">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8421e-200">Related topics</span></span>


[<span data-ttu-id="8421e-201">高度なグループ ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="8421e-201">Advanced Group Policy Management</span></span>](index.md)

[<span data-ttu-id="8421e-202">Microsoft Advanced Group Policy Management (AGPM) 4.0 SP1 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="8421e-202">Release Notes for Microsoft Advanced Group Policy Management 4.0 SP1</span></span>](release-notes-for-microsoft-advanced-group-policy-management-40-sp1.md)

 

 





