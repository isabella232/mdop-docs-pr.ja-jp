---
title: App-V 5.0 SP3 について
description: App-V 5.0 SP3 について
author: dansimp
ms.assetid: 67b5268b-edc1-4027-98b0-b3937dd70a6b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: bc72f3f72c2b06470287dfe4ba3ed22abcc6068b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814974"
---
# <span data-ttu-id="e416e-103">App-V 5.0 SP3 について</span><span class="sxs-lookup"><span data-stu-id="e416e-103">About App-V 5.0 SP3</span></span>


<span data-ttu-id="e416e-104">Microsoft Application Virtualization (App-v) 5.0 SP3 に適用される重大な変更に関する情報を確認するには、次のセクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="e416e-104">Use the following sections to review information about significant changes that apply to Microsoft Application Virtualization (App-V) 5.0 SP3:</span></span>

-   [<span data-ttu-id="e416e-105">App-v 5.0 SP3 ソフトウェアの前提条件とサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="e416e-105">App-V 5.0 SP3 software prerequisites and supported configurations</span></span>](#bkmk-sp3-prereq-configs)

-   [<span data-ttu-id="e416e-106">App-v 5.0 SP3 への移行</span><span class="sxs-lookup"><span data-stu-id="e416e-106">Migrating to App-V 5.0 SP3</span></span>](#bkmk-migrate-to-50sp3)

-   [<span data-ttu-id="e416e-107">手動で作成された接続グループの xml ファイルには、スキーマの更新が必要</span><span class="sxs-lookup"><span data-stu-id="e416e-107">Manually created connection group xml file requires update to schema</span></span>](#bkmk-update-schema-cg)

-   [<span data-ttu-id="e416e-108">接続グループの改善</span><span class="sxs-lookup"><span data-stu-id="e416e-108">Improvements to connection groups</span></span>](#bkmk-cg-improvements)

-   [<span data-ttu-id="e416e-109">管理者は、特定のユーザーに対してパッケージの発行と発行の取り消しを行うことができます</span><span class="sxs-lookup"><span data-stu-id="e416e-109">Administrators can publish and unpublish packages for a specific user</span></span>](#bkmk-usersid-pub-pkgs-specf-user)

-   [<span data-ttu-id="e416e-110">管理者のみがパッケージの発行と発行を解除できるようにする</span><span class="sxs-lookup"><span data-stu-id="e416e-110">Enable only administrators to publish and unpublish packages</span></span>](#bkmk-admins-only-pub-unpub-pkgs)

-   [<span data-ttu-id="e416e-111">RunVirtual registry key は、ユーザーに公開されているパッケージをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e416e-111">RunVirtual registry key supports packages that are published to the user</span></span>](#bkmk-runvirtual-reg-key)

-   [<span data-ttu-id="e416e-112">新しい PowerShell コマンドレットと更新可能なコマンドレットのヘルプ</span><span class="sxs-lookup"><span data-stu-id="e416e-112">New PowerShell cmdlets and updateable cmdlet help</span></span>](#bkmk-posh-cmdlets-help)

-   [<span data-ttu-id="e416e-113">プライマリ仮想アプリケーションディレクトリ (PVAD) は非表示になっていますが、オンにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e416e-113">Primary virtual application directory (PVAD) is hidden but can be turned on</span></span>](#bkmk-pvad-hidden)

-   [<span data-ttu-id="e416e-114">App-v の公開メタデータを表示するには、ClientVersion が必要です</span><span class="sxs-lookup"><span data-stu-id="e416e-114">ClientVersion is required to view App-V publishing metadata</span></span>](#bkmk-pub-metadata-clientversion)

-   [<span data-ttu-id="e416e-115">App-v のイベントログが統合されている</span><span class="sxs-lookup"><span data-stu-id="e416e-115">App-V event logs have been consolidated</span></span>](#bkmk-event-logs-moved)

## <a href="" id="bkmk-sp3-prereq-configs"></a><span data-ttu-id="e416e-116">App-v 5.0 SP3 ソフトウェアの前提条件とサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="e416e-116">App-V 5.0 SP3 software prerequisites and supported configurations</span></span>


<span data-ttu-id="e416e-117">アプリ-V 5.0 SP3 ソフトウェアの前提条件とサポートされる構成については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e416e-117">See the following links for the App-V 5.0 SP3 software prerequisites and supported configurations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e416e-118">前提条件とサポートされる構成へのリンク</span><span class="sxs-lookup"><span data-stu-id="e416e-118">Links to prerequisites and supported configurations</span></span></th>
<th align="left"><span data-ttu-id="e416e-119">説明</span><span class="sxs-lookup"><span data-stu-id="e416e-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="app-v-50-sp3-prerequisites.md" data-raw-source="[App-V 5.0 SP3 Prerequisites](app-v-50-sp3-prerequisites.md)"><span data-ttu-id="e416e-120">APP-V 5.0 SP3 の前提条件</span><span class="sxs-lookup"><span data-stu-id="e416e-120">App-V 5.0 SP3 Prerequisites</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="e416e-121">App-v 5.0 SP3 のインストールを開始する前にインストールする必要がある必須ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="e416e-121">Prerequisite software that you must install before starting the App-V 5.0 SP3 installation</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="app-v-50-sp3-supported-configurations.md" data-raw-source="[App-V 5.0 SP3 Supported Configurations](app-v-50-sp3-supported-configurations.md)"><span data-ttu-id="e416e-122">App-V 5.0 SP3 でサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="e416e-122">App-V 5.0 SP3 Supported Configurations</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="e416e-123">App-v Server、Sequencer、およびクライアントコンポーネントのサポートされているオペレーティングシステムとハードウェアの要件</span><span class="sxs-lookup"><span data-stu-id="e416e-123">Supported operating systems and hardware requirements for the App-V Server, Sequencer, and Client components</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-migrate-to-50sp3"></a><span data-ttu-id="e416e-124">App-v 5.0 SP3 への移行</span><span class="sxs-lookup"><span data-stu-id="e416e-124">Migrating to App-V 5.0 SP3</span></span>


<span data-ttu-id="e416e-125">以前のバージョンから App-v 5.0 SP3 にアップグレードするには、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="e416e-125">Use the following information to upgrade to App-V 5.0 SP3 from earlier versions.</span></span>

### <span data-ttu-id="e416e-126">アップグレードを開始する前に</span><span class="sxs-lookup"><span data-stu-id="e416e-126">Before you start the upgrade</span></span>

<span data-ttu-id="e416e-127">アップグレードを開始する前に、次の情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="e416e-127">Review the following information before you start the upgrade:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e416e-128">アップグレード前に確認する項目</span><span class="sxs-lookup"><span data-stu-id="e416e-128">Items to review before upgrading</span></span></th>
<th align="left"><span data-ttu-id="e416e-129">説明</span><span class="sxs-lookup"><span data-stu-id="e416e-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-130">アップグレードするコンポーネント</span><span class="sxs-lookup"><span data-stu-id="e416e-130">Components to upgrade</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="e416e-131">App-v Server</span><span class="sxs-lookup"><span data-stu-id="e416e-131">App-V Server</span></span></p></li>
<li><p><span data-ttu-id="e416e-132">Sequencer (シーケンサー)</span><span class="sxs-lookup"><span data-stu-id="e416e-132">Sequencer</span></span></p></li>
<li><p><span data-ttu-id="e416e-133">App-v client または App-v リモートデスクトップサービス (RDS) クライアント</span><span class="sxs-lookup"><span data-stu-id="e416e-133">App-V client or App-V Remote Desktop Services (RDS) client</span></span></p></li>
<li><p><span data-ttu-id="e416e-134">接続グループ</span><span class="sxs-lookup"><span data-stu-id="e416e-134">Connection groups</span></span></p></li>
</ol>
<div class="alert">
<strong><span data-ttu-id="e416e-135">注</span><span class="sxs-lookup"><span data-stu-id="e416e-135">Note</span></span></strong><br/><p><span data-ttu-id="e416e-136">App-v クライアントユーザーインターフェイスを使用するには、 <a href="https://www.microsoft.com/download/details.aspx?id=41186" data-raw-source="[Microsoft Application Virtualization 5.0 Client UI Application](https://www.microsoft.com/download/details.aspx?id=41186)"> Microsoft Application Virtualization 5.0 クライアント UI アプリケーションから既存のバージョンをダウンロードし </a> ます。</span><span class="sxs-lookup"><span data-stu-id="e416e-136">To use the App-V client user interface, download the existing version from <a href="https://www.microsoft.com/download/details.aspx?id=41186" data-raw-source="[Microsoft Application Virtualization 5.0 Client UI Application](https://www.microsoft.com/download/details.aspx?id=41186)">Microsoft Application Virtualization 5.0 Client UI Application</a>.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-137">アプリからのアップグレード-V 4. x</span><span class="sxs-lookup"><span data-stu-id="e416e-137">Upgrading from App-V 4.x</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-138">まず、App-V 5.0 にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e416e-138">You must first upgrade to App-V 5.0.</span></span> <span data-ttu-id="e416e-139">アプリ-V 5.0 SP3 からアプリに直接アップグレードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e416e-139">You cannot upgrade directly from App-V 4.x to App-V 5.0 SP3.</span></span></p>
<p><span data-ttu-id="e416e-140">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e416e-140">For more information, see:</span></span></p>
<ul>
<li><p><a href="about-app-v-50.md" data-raw-source="[About App-V 5.0](about-app-v-50.md)"><span data-ttu-id="e416e-141">App-V 5.0 について</span><span class="sxs-lookup"><span data-stu-id="e416e-141">About App-V 5.0</span></span></a> </p></li>
<li><p><a href="planning-for-migrating-from-a-previous-version-of-app-v.md" data-raw-source="[Planning for Migrating from a Previous Version of App-V](planning-for-migrating-from-a-previous-version-of-app-v.md)"><span data-ttu-id="e416e-142">APP-V の以前のバージョンからの移行計画</span><span class="sxs-lookup"><span data-stu-id="e416e-142">Planning for Migrating from a Previous Version of App-V</span></span></a></p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-143">App-v 5.0 以降からのアップグレード</span><span class="sxs-lookup"><span data-stu-id="e416e-143">Upgrading from App-V 5.0 or later</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-144">以下のいずれかのバージョンから直接 App-v 5.0 SP3 にアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="e416e-144">You can upgrade to App-V 5.0 SP3 directly from any of the following versions:</span></span></p>
<ul>
<li><p><span data-ttu-id="e416e-145">App-v 5.0</span><span class="sxs-lookup"><span data-stu-id="e416e-145">App-V 5.0</span></span></p></li>
<li><p><span data-ttu-id="e416e-146">App-v 5.0 SP1</span><span class="sxs-lookup"><span data-stu-id="e416e-146">App-V 5.0 SP1</span></span></p></li>
<li><p><span data-ttu-id="e416e-147">App-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="e416e-147">App-V 5.0 SP2</span></span></p></li>
</ul>
<p><span data-ttu-id="e416e-148">App-v 5.0 SP3 にアップグレードするには、この記事の残りのセクションの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e416e-148">To upgrade to App-V 5.0 SP3, follow the steps in the remaining sections of this article.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-149">アップグレードした後でパッケージと接続グループに必要な変更を加える</span><span class="sxs-lookup"><span data-stu-id="e416e-149">Required changes to packages and connection groups after upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-150">なし。</span><span class="sxs-lookup"><span data-stu-id="e416e-150">None.</span></span> <span data-ttu-id="e416e-151">パッケージと接続グループは、現時点でも引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="e416e-151">Packages and connection groups will continue to work as they currently do.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-steps-upgrd-infrastruc"></a><span data-ttu-id="e416e-152">App-v インフラストラクチャのアップグレード手順</span><span class="sxs-lookup"><span data-stu-id="e416e-152">Steps to upgrade the App-V infrastructure</span></span>

<span data-ttu-id="e416e-153">次の手順を実行して、app-v インフラストラクチャの各コンポーネントを App-v 5.0 SP3 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="e416e-153">Complete the following steps to upgrade each component of the App-V infrastructure to App-V 5.0 SP3.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e416e-154">ステップ</span><span class="sxs-lookup"><span data-stu-id="e416e-154">Step</span></span></th>
<th align="left"><span data-ttu-id="e416e-155">詳細情報</span><span class="sxs-lookup"><span data-stu-id="e416e-155">For more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-156">手順 1: App-v Server をアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="e416e-156">Step 1: Upgrade the App-V Server.</span></span></p>
<p><span data-ttu-id="e416e-157">App-v Server を使っていない場合は、この手順をスキップして次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="e416e-157">If you are not using the App-V Server, skip this step and go to the next step.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="e416e-158">注</span><span class="sxs-lookup"><span data-stu-id="e416e-158">Note</span></span></strong><br/><p><span data-ttu-id="e416e-159">App-v 5.0 SP3 クライアントは、app-v 5.0 SP1 サーバーと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="e416e-159">The App-V 5.0 SP3 client is compatible with the App-V 5.0 SP1 Server.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="e416e-160">次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="e416e-160">Follow these steps:</span></span></p>
<ol>
<li><p><span data-ttu-id="e416e-161">App-v <a href="release-notes-for-app-v-50-sp3.md" data-raw-source="[Release Notes for App-V 5.0 SP3](release-notes-for-app-v-50-sp3.md)"> </a> Server のインストールに影響する可能性のある問題については、「APP-V 5.0 SP3 のリリースノート」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e416e-161">Review the <a href="release-notes-for-app-v-50-sp3.md" data-raw-source="[Release Notes for App-V 5.0 SP3](release-notes-for-app-v-50-sp3.md)">Release Notes for App-V 5.0 SP3</a> for issues that may affect the App-V Server installation.</span></span></p></li>
<li><p><span data-ttu-id="e416e-162">管理データベースやレポートデータベースのアップグレードに使用する方法に応じて、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e416e-162">Do one of the following, depending on the method you are using to upgrade the Management database and/or Reporting database:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e416e-163">データベースのアップグレード方法</span><span class="sxs-lookup"><span data-stu-id="e416e-163">Database upgrade method</span></span></th>
<th align="left"><span data-ttu-id="e416e-164">ステップ</span><span class="sxs-lookup"><span data-stu-id="e416e-164">Step</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-165">Windows インストーラー</span><span class="sxs-lookup"><span data-stu-id="e416e-165">Windows Installer</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-166">この手順をスキップして、「App-v Server をアップグレードする場合」の手順3に進みます。</span><span class="sxs-lookup"><span data-stu-id="e416e-166">Skip this step and go to step 3, “If you are upgrading the App-V Server...”</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-167">SQL スクリプト</span><span class="sxs-lookup"><span data-stu-id="e416e-167">SQL scripts</span></span></p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e416e-168">管理データベース</span><span class="sxs-lookup"><span data-stu-id="e416e-168">Management database</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e416e-169">インストールまたはアップグレードするには、「 <a href="https://support.microsoft.com/kb/3031340" data-raw-source="[SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail](https://support.microsoft.com/kb/3031340)"> office スクリプトをインストールまたは5.0 アップグレードする」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="e416e-169">To install or upgrade, see <a href="https://support.microsoft.com/kb/3031340" data-raw-source="[SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail](https://support.microsoft.com/kb/3031340)">SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e416e-170">レポートデータベース</span><span class="sxs-lookup"><span data-stu-id="e416e-170">Reporting database</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e416e-171"><a href="how-to-deploy-the-app-v-databases-by-using-sql-scripts.md" data-raw-source="[How to Deploy the App-V Databases by Using SQL Scripts](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md)">「SQL スクリプトを使用して App-v データベースを展開する方法」の手順に従い </a> ます。</span><span class="sxs-lookup"><span data-stu-id="e416e-171">Follow the steps in <a href="how-to-deploy-the-app-v-databases-by-using-sql-scripts.md" data-raw-source="[How to Deploy the App-V Databases by Using SQL Scripts](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md)">How to Deploy the App-V Databases by Using SQL Scripts</a>.</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>
<p> </p></li>
<li><p><span data-ttu-id="e416e-172">App-v Server を App-v 5.0 SP1 修正プログラムパッケージ3以降でアップグレードする場合は、「 <a href="#bkmk-check-reg-key-svr" data-raw-source="[Check registry keys after installing the App-V 5.0 SP3 Server](#bkmk-check-reg-key-svr)"> app-v 5.0 SP3 サーバーをインストールした後でレジストリキーを確認する」の手順を実行し </a> ます。</span><span class="sxs-lookup"><span data-stu-id="e416e-172">If you are upgrading the App-V Server from App-V 5.0 SP1 Hotfix Package 3 or later, complete the steps in section <a href="#bkmk-check-reg-key-svr" data-raw-source="[Check registry keys after installing the App-V 5.0 SP3 Server](#bkmk-check-reg-key-svr)">Check registry keys after installing the App-V 5.0 SP3 Server</a>.</span></span></p></li>
<li><p><span data-ttu-id="e416e-173">「 <a href="how-to-deploy-the-app-v-50-server-50sp3.md" data-raw-source="[How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)"> App-v 5.0 サーバーを展開する方法」の手順に従い </a> ます。</span><span class="sxs-lookup"><span data-stu-id="e416e-173">Follow the steps in <a href="how-to-deploy-the-app-v-50-server-50sp3.md" data-raw-source="[How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)">How to Deploy the App-V 5.0 Server</a>.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-174">手順 2: App-v Sequencer をアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="e416e-174">Step 2: Upgrade the App-V Sequencer.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-175"><a href="how-to-install-the-sequencer-beta-gb18030.md" data-raw-source="[How to Install the Sequencer](how-to-install-the-sequencer-beta-gb18030.md)">Sequencer をインストールする方法について説明し </a> ます。</span><span class="sxs-lookup"><span data-stu-id="e416e-175">See <a href="how-to-install-the-sequencer-beta-gb18030.md" data-raw-source="[How to Install the Sequencer](how-to-install-the-sequencer-beta-gb18030.md)">How to Install the Sequencer</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-176">手順 3: App-v クライアントまたは App-v RDS クライアントをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="e416e-176">Step 3: Upgrade the App-V client or App-V RDS client.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-177">「 <a href="how-to-deploy-the-app-v-client-gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md)"> App-v クライアントを展開する方法」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="e416e-177">See <a href="how-to-deploy-the-app-v-client-gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md)">How to Deploy the App-V Client</a>.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-check-reg-key-svr"></a><span data-ttu-id="e416e-178">App-v 5.0 SP3 サーバーをインストールする前にレジストリキーを確認する</span><span class="sxs-lookup"><span data-stu-id="e416e-178">Check registry keys before installing the App-V 5.0 SP3 Server</span></span>

<span data-ttu-id="e416e-179">これは、前の表の手順3です。</span><span class="sxs-lookup"><span data-stu-id="e416e-179">This is step 3 from the previous table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e416e-180">この手順が必要な場合</span><span class="sxs-lookup"><span data-stu-id="e416e-180">When this step is required</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e416e-181">.Msp ファイルを使用してインストールした後続の修正プログラムパッケージを使用して、App-v SP1 からアップグレードしようとしています。</span><span class="sxs-lookup"><span data-stu-id="e416e-181">You are upgrading from App-V SP1 with any subsequent Hotfix Packages that you installed by using an .msp file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e416e-182">この手順を実行する必要があるコンポーネント</span><span class="sxs-lookup"><span data-stu-id="e416e-182">Which components require that you do this step</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e416e-183">アップグレードしている App-v Server コンポーネントのみ</span><span class="sxs-lookup"><span data-stu-id="e416e-183">Only the App-V Server components that you are upgrading.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e416e-184">この手順を実行する必要がある場合</span><span class="sxs-lookup"><span data-stu-id="e416e-184">When you need to do this step</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e416e-185">App-v Server を app-v 5.0 SP3 にアップグレードする前に</span><span class="sxs-lookup"><span data-stu-id="e416e-185">Before you upgrade the App-V Server to App-V 5.0 SP3</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e416e-186">必要な作業</span><span class="sxs-lookup"><span data-stu-id="e416e-186">What you need to do</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e416e-187">次の表の情報を使用して、[ <code>HKLM\Software\Microsoft\AppV\Server</code> 元のサーバーインストールで指定した値を使用して、各レジストリキーの値を更新します] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e416e-187">Using the information in the following tables, update each registry key value under <code>HKLM\Software\Microsoft\AppV\Server</code> with the value that you provided in your original server installation.</span></span> <span data-ttu-id="e416e-188">この手順を完了すると、App-v SP1 の修正プログラムパッケージをインストールしたときに削除された可能性があるレジストリ値が復元されます。</span><span class="sxs-lookup"><span data-stu-id="e416e-188">Completing this step restores registry values that may have been removed when App-V SP1 Hotfix Packages were installed.</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="e416e-189">ManagementDatabase キー</span><span class="sxs-lookup"><span data-stu-id="e416e-189">ManagementDatabase key</span></span>**

<span data-ttu-id="e416e-190">管理データベースをインストールする場合は、次のレジストリキーをに設定 `HKLM\Software\Microsoft\AppV\Server\ManagementDatabase` します。</span><span class="sxs-lookup"><span data-stu-id="e416e-190">If you are installing the Management database, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ManagementDatabase`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e416e-191">キー名</span><span class="sxs-lookup"><span data-stu-id="e416e-191">Key name</span></span></th>
<th align="left"><span data-ttu-id="e416e-192">説明</span><span class="sxs-lookup"><span data-stu-id="e416e-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-193">IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="e416e-193">IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-194">ローカル以外の管理データベースにアクセスするためにパブリックアクセスアカウントが必要かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="e416e-194">Describes whether a public access account is required to access non-local management databases.</span></span> <span data-ttu-id="e416e-195">値が必要な場合は、"1" に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e416e-195">Value is set to “1” if it is required.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-196">MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e416e-196">MANAGEMENT_DB_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-197">管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="e416e-197">Name of the Management database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-198">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e416e-198">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-199">読み取り (パブリック) 管理データベースへのアクセスに使用するアカウント。</span><span class="sxs-lookup"><span data-stu-id="e416e-199">Account used for read (public) access to the Management database.</span></span></p>
<p><span data-ttu-id="e416e-200">"1" に設定されているときに使われ <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> ます。</span><span class="sxs-lookup"><span data-stu-id="e416e-200">Used when <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-201">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="e416e-201">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-202">管理データベースへの読み取り (パブリック) アクセスに使用されるアカウントのセキュリティ識別子 (SID)。</span><span class="sxs-lookup"><span data-stu-id="e416e-202">Secure identifier (SID) of the account used for read (public) access to the Management database.</span></span></p>
<p><span data-ttu-id="e416e-203">"1" に設定されているときに使われ <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> ます。</span><span class="sxs-lookup"><span data-stu-id="e416e-203">Used when <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-204">MANAGEMENT_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="e416e-204">MANAGEMENT_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-205">管理データベースの SQL Server インスタンス。</span><span class="sxs-lookup"><span data-stu-id="e416e-205">SQL Server instance for the Management database.</span></span></p>
<p><span data-ttu-id="e416e-206">この値が空白の場合、既定のデータベースインスタンスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e416e-206">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-207">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e416e-207">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-208">管理データベースへの書き込み (管理者) アクセスのために使用されるアカウント。</span><span class="sxs-lookup"><span data-stu-id="e416e-208">Account used for write (administrator) access to the Management database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-209">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="e416e-209">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-210">管理データベースへの書き込み (管理者) アクセスのために使用されるアカウントのセキュリティ識別子 (SID)。</span><span class="sxs-lookup"><span data-stu-id="e416e-210">Secure identifier (SID) of the account used for write (administrator) access to the Management database.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-211">MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e416e-211">MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-212">管理サーバーのリモートコンピューターアカウント (ドメイン \ アカウント)。</span><span class="sxs-lookup"><span data-stu-id="e416e-212">Management server remote computer account (domain\account).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-213">MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e416e-213">MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-214">管理サーバー (ドメイン \ アカウント) のインストール管理者ログイン。</span><span class="sxs-lookup"><span data-stu-id="e416e-214">Installation administrator login for the Management server (domain\account).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-215">MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="e416e-215">MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-216">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e416e-216">Valid values are:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="e416e-217">1 </strong> –管理サービスはローカルコンピューターにあります。つまり、MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT は空白です。</span><span class="sxs-lookup"><span data-stu-id="e416e-217">1</strong> – the Management service is on the local computer, that is, MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT is blank.</span></span></p></li>
<li><p><strong><span data-ttu-id="e416e-218">0 </strong> - 管理サービスは、ローカルコンピューターとは別のコンピューターにあります。</span><span class="sxs-lookup"><span data-stu-id="e416e-218">0</strong> - the Management service is on a different computer from the local computer.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="e416e-219">ManagementService キー</span><span class="sxs-lookup"><span data-stu-id="e416e-219">ManagementService key</span></span>**

<span data-ttu-id="e416e-220">管理サーバーをインストールする場合は、次のレジストリキーをに設定 `HKLM\Software\Microsoft\AppV\Server\ManagementService` します。</span><span class="sxs-lookup"><span data-stu-id="e416e-220">If you are installing the Management server, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ManagementService`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e416e-221">キー名</span><span class="sxs-lookup"><span data-stu-id="e416e-221">Key name</span></span></th>
<th align="left"><span data-ttu-id="e416e-222">説明</span><span class="sxs-lookup"><span data-stu-id="e416e-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-223">MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e416e-223">MANAGEMENT_ADMINACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-224">Active Directory ドメインサービス (AD DS) グループまたは、App-v (ドメイン \ アカウント) を管理する権限が与えられているアカウント。</span><span class="sxs-lookup"><span data-stu-id="e416e-224">Active Directory Domain Services (AD DS) group or account that is authorized to manage App-V (domain\account).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-225">MANAGEMENT_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="e416e-225">MANAGEMENT_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-226">管理データベースを含む SQL server インスタンス。</span><span class="sxs-lookup"><span data-stu-id="e416e-226">SQL server instance that contains the Management database.</span></span></p>
<p><span data-ttu-id="e416e-227">この値が空白の場合、既定のデータベースインスタンスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e416e-227">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-228">MANAGEMENT_DB_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="e416e-228">MANAGEMENT_DB_SQL_SERVER_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-229">管理データベースのあるリモート SQL server の名前。</span><span class="sxs-lookup"><span data-stu-id="e416e-229">Name of the remote SQL server with the Management database.</span></span></p>
<p><span data-ttu-id="e416e-230">この値が空白の場合は、ローカルコンピューターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e416e-230">If the value is blank, the local computer is used.</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="e416e-231">ReportingDatabase キー</span><span class="sxs-lookup"><span data-stu-id="e416e-231">ReportingDatabase key</span></span>**

<span data-ttu-id="e416e-232">レポートデータベースをインストールする場合は、次のレジストリキーをに設定 `HKLM\Software\Microsoft\AppV\Server\ReportingDatabase` します。</span><span class="sxs-lookup"><span data-stu-id="e416e-232">If you are installing the Reporting database, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ReportingDatabase`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e416e-233">キー名</span><span class="sxs-lookup"><span data-stu-id="e416e-233">Key name</span></span></th>
<th align="left"><span data-ttu-id="e416e-234">説明</span><span class="sxs-lookup"><span data-stu-id="e416e-234">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-235">IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="e416e-235">IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-236">ローカル以外のレポートデータベースにアクセスするためにパブリックアクセスアカウントが必要かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="e416e-236">Describes whether a public access account is required to access non-local reporting databases.</span></span> <span data-ttu-id="e416e-237">値が必要な場合は、"1" に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e416e-237">Value is set to “1” if it is required.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-238">REPORTING_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="e416e-238">REPORTING_DB_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-239">レポートデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="e416e-239">Name of the Reporting database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-240">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e416e-240">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-241">レポートデータベースへの読み取り (パブリック) アクセスに使用されるアカウント。</span><span class="sxs-lookup"><span data-stu-id="e416e-241">Account used for read (public) access to the Reporting database.</span></span></p>
<p><span data-ttu-id="e416e-242">"1" に設定されているときに使われ <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> ます。</span><span class="sxs-lookup"><span data-stu-id="e416e-242">Used when <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-243">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="e416e-243">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-244">レポートデータベースへの読み取り (パブリック) アクセスに使用されるアカウントのセキュリティ識別子 (SID)。</span><span class="sxs-lookup"><span data-stu-id="e416e-244">Secure identifier (SID) of the account used for read (public) access to the Reporting database.</span></span></p>
<p><span data-ttu-id="e416e-245">"1" に設定されているときに使われ <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> ます。</span><span class="sxs-lookup"><span data-stu-id="e416e-245">Used when <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-246">REPORTING_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="e416e-246">REPORTING_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-247">レポートデータベースの SQL Server インスタンス。</span><span class="sxs-lookup"><span data-stu-id="e416e-247">SQL Server instance for the Reporting database.</span></span></p>
<p><span data-ttu-id="e416e-248">この値が空白の場合、既定のデータベースインスタンスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e416e-248">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-249">REPORTING_DB_WRITE_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e416e-249">REPORTING_DB_WRITE_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-250">REPORTING_DB_WRITE_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="e416e-250">REPORTING_DB_WRITE_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-251">REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e416e-251">REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-252">レポートサーバーのリモートコンピューターアカウント (ドメイン \ アカウント)。</span><span class="sxs-lookup"><span data-stu-id="e416e-252">Reporting server remote computer account (domain\account).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-253">REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="e416e-253">REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-254">[Reporting server (ドメイン \ アカウント)] のインストール管理者としてログインします。</span><span class="sxs-lookup"><span data-stu-id="e416e-254">Installation administrator login for the Reporting server (domain\account).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-255">REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="e416e-255">REPORTING_SERVER_MACHINE_USE_LOCAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-256">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e416e-256">Valid values are:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="e416e-257">1 </strong> –レポートサービスはローカルコンピューターにあります。つまり、REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT は空白です。</span><span class="sxs-lookup"><span data-stu-id="e416e-257">1</strong> – the Reporting service is on the local computer, that is, REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT is blank.</span></span></p></li>
<li><p><strong><span data-ttu-id="e416e-258">0 </strong> - レポートサービスは、ローカルコンピューターの別のコンピューターにあります。</span><span class="sxs-lookup"><span data-stu-id="e416e-258">0</strong> - the Reporting service is on a different computer from the local computer.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="e416e-259">ReportingService キー</span><span class="sxs-lookup"><span data-stu-id="e416e-259">ReportingService key</span></span>**

<span data-ttu-id="e416e-260">レポートサーバーをインストールする場合は、次のレジストリキーをに設定 `HKLM\Software\Microsoft\AppV\Server\ReportingService` します。</span><span class="sxs-lookup"><span data-stu-id="e416e-260">If you are installing the Reporting server, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ReportingService`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e416e-261">キー名</span><span class="sxs-lookup"><span data-stu-id="e416e-261">Key name</span></span></th>
<th align="left"><span data-ttu-id="e416e-262">説明</span><span class="sxs-lookup"><span data-stu-id="e416e-262">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-263">REPORTING_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="e416e-263">REPORTING_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-264">レポートデータベースの SQL Server インスタンス。</span><span class="sxs-lookup"><span data-stu-id="e416e-264">SQL Server instance for the Reporting database.</span></span></p>
<p><span data-ttu-id="e416e-265">この値が空白の場合、既定のデータベースインスタンスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e416e-265">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-266">REPORTING_DB_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="e416e-266">REPORTING_DB_SQL_SERVER_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-267">レポートデータベースのあるリモート SQL server の名前。</span><span class="sxs-lookup"><span data-stu-id="e416e-267">Name of the remote SQL server with the Reporting database.</span></span></p>
<p><span data-ttu-id="e416e-268">この値が空白の場合は、ローカルコンピューターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e416e-268">If the value is blank, the local computer is used.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-update-schema-cg"></a><span data-ttu-id="e416e-269">手動で作成された接続グループの xml ファイルには、スキーマの更新が必要</span><span class="sxs-lookup"><span data-stu-id="e416e-269">Manually created connection group xml file requires update to schema</span></span>


<span data-ttu-id="e416e-270">接続グループの XML ファイルを手動で作成していて、新しい "オプションパッケージ" を使い、強化された[接続グループ](#bkmk-cg-improvements)の機能を使用したい場合は、XML ファイルで次のスキーマを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e416e-270">If you are manually creating the connection group XML file, and want to use the new “optional packages” and “use any version” features that are described in [Improvements to connection groups](#bkmk-cg-improvements), you must specify the following schema in the XML file:</span></span>

`xmlns="http://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup"`

<span data-ttu-id="e416e-271">詳細については、「[接続グループファイルについ](about-the-connection-group-file.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e416e-271">For examples and more information, see [About the Connection Group File](about-the-connection-group-file.md).</span></span>

## <a href="" id="bkmk-cg-improvements"></a><span data-ttu-id="e416e-272">接続グループの改善</span><span class="sxs-lookup"><span data-stu-id="e416e-272">Improvements to connection groups</span></span>


<span data-ttu-id="e416e-273">アプリ-V 5.0 SP3 で追加されたオプションのパッケージやその他の改善によって、接続グループをより簡単に管理できます。</span><span class="sxs-lookup"><span data-stu-id="e416e-273">You can manage connection groups more easily by using optional packages and other improvements that have been added in App-V 5.0 SP3.</span></span> <span data-ttu-id="e416e-274">次の表は、新しい接続グループ機能を使用して実行できるタスクと、各タスクに関する詳細情報へのリンクをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="e416e-274">The following table summarizes the tasks that you can perform by using the new connection group features, and links to more detailed information about each task.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e416e-275">タスク/機能</span><span class="sxs-lookup"><span data-stu-id="e416e-275">Task/feature</span></span></th>
<th align="left"><span data-ttu-id="e416e-276">説明</span><span class="sxs-lookup"><span data-stu-id="e416e-276">Description</span></span></th>
<th align="left"><span data-ttu-id="e416e-277">詳細情報へのリンク</span><span class="sxs-lookup"><span data-stu-id="e416e-277">Links to more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-278">接続グループにオプションのパッケージを含めることを有効にする</span><span class="sxs-lookup"><span data-stu-id="e416e-278">Enable a connection group to include optional packages</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-279">接続グループにオプションのパッケージを含めることで、ユーザーが資格を持つアプリケーションに基づいて、接続グループの仮想環境に含めるアプリケーションを動的に決定することができます。</span><span class="sxs-lookup"><span data-stu-id="e416e-279">Including optional packages in a connection group enables you to dynamically determine which applications will be included in the connection group’s virtual environment, based on the applications that users are entitled to.</span></span></p>
<p><span data-ttu-id="e416e-280">複数の接続グループを管理する必要はありません。同じ接続グループでオプションとオプション以外のパッケージを混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="e416e-280">You don’t need to manage as many connection groups because you can mix optional and non-optional packages in the same connection group.</span></span> <span data-ttu-id="e416e-281">パッケージを混在させることで、ユーザーは共通のパッケージを1つしか持っていない場合でも、異なるグループのユーザーが同じ接続グループを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e416e-281">Mixing packages allows different groups of users to use the same connection group, even though users might have only one package in common.</span></span></p>
<p><strong><span data-ttu-id="e416e-282">例 </strong> : すべてのユーザーに対して Microsoft Office でパッケージを有効にすることはできますが、異なる Office プラグインを含むさまざまなオプションパッケージをユーザーの異なるサブセットに対して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e416e-282">Example</strong>: You can enable a package with Microsoft Office for all users, but enable different optional packages, which contain different Office plug-ins, to different subsets of users.</span></span></p></td>
<td align="left"><p><a href="how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional)"><span data-ttu-id="e416e-283">接続グループでオプション パッケージを使用する方法</span><span class="sxs-lookup"><span data-stu-id="e416e-283">How to Use Optional Packages in Connection Groups</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-284">接続グループを変更せずに、省略可能なパッケージを非公開にする、または削除する</span><span class="sxs-lookup"><span data-stu-id="e416e-284">Unpublish or delete an optional package without changing the connection group</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-285">接続グループに含まれているオプションのパッケージを公開または削除するか、非公開にして再公開します。これは、App-v クライアントで接続グループを無効にするか、再び有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e416e-285">Unpublish or delete, or unpublish and republish an optional package, which is in a connection group, without having to disable or re-enable the connection group on the App-V client.</span></span></p></td>
<td align="left"><p><a href="how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional)"><span data-ttu-id="e416e-286">接続グループでオプション パッケージを使用する方法</span><span class="sxs-lookup"><span data-stu-id="e416e-286">How to Use Optional Packages in Connection Groups</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-287">ユーザーに公開されたパッケージとグローバルに公開されたパッケージを含む接続グループを公開する</span><span class="sxs-lookup"><span data-stu-id="e416e-287">Publish connection groups that contain user-published and globally published packages</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-288">ユーザーが公開した、またはグローバルに公開されたパッケージを含む、ユーザーに公開された接続グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="e416e-288">Create a user-published connection group that contains user-published and globally published packages.</span></span></p></td>
<td align="left"><p><a href="how-to-create-a-connection-group-with-user-published-and-globally-published-packages.md" data-raw-source="[How to Create a Connection Group with User-Published and Globally Published Packages](how-to-create-a-connection-group-with-user-published-and-globally-published-packages.md)"><span data-ttu-id="e416e-289">ユーザー単位で公開されるパッケージとグローバルに公開されるパッケージを含む接続グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="e416e-289">How to Create a Connection Group with User-Published and Globally Published Packages</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-290">パッケージバージョンを無視するように接続グループを設定する</span><span class="sxs-lookup"><span data-stu-id="e416e-290">Make a connection group ignore the package version</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-291">接続グループを構成して、任意のバージョンのパッケージを受け入れるようにします。これにより、接続グループを無効にすることなくパッケージをアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="e416e-291">Configure a connection group to accept any version of a package, which enables you to upgrade a package without having to disable the connection group.</span></span> <span data-ttu-id="e416e-292">また、接続グループに正しくないバージョンのオプションのパッケージが含まれている場合は、パッケージは無視され、接続グループの仮想環境の作成がブロックされることはありません。</span><span class="sxs-lookup"><span data-stu-id="e416e-292">In addition, if there is an optional package with an incorrect version in the connection group, the package is ignored and won’t block the connection group’s virtual environment from being created.</span></span></p></td>
<td align="left"><p><a href="how-to-make-a-connection-group-ignore-the-package-version.md" data-raw-source="[How to Make a Connection Group Ignore the Package Version](how-to-make-a-connection-group-ignore-the-package-version.md)"><span data-ttu-id="e416e-293">パッケージのバージョンを無視するように接続グループを構成する方法</span><span class="sxs-lookup"><span data-stu-id="e416e-293">How to Make a Connection Group Ignore the Package Version</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-294">エンドユーザーの発行機能を制限する</span><span class="sxs-lookup"><span data-stu-id="e416e-294">Limit end users’ publishing capabilities</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-295">(エンドユーザーではなく) 管理者のみがパッケージを公開し、接続グループを有効にすることを許可します。</span><span class="sxs-lookup"><span data-stu-id="e416e-295">Enable only administrators (not end users) to publish packages and to enable connection groups.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-296">接続グループの詳細については、「 <a href="how-to-allow-only-administrators-to-enable-connection-groups.md" data-raw-source="[How to Allow Only Administrators to Enable Connection Groups](how-to-allow-only-administrators-to-enable-connection-groups.md)"> 管理者のみが接続グループを有効にできるようにする方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e416e-296">For information about connection groups, see <a href="how-to-allow-only-administrators-to-enable-connection-groups.md" data-raw-source="[How to Allow Only Administrators to Enable Connection Groups](how-to-allow-only-administrators-to-enable-connection-groups.md)">How to Allow Only Administrators to Enable Connection Groups</span></span></a></p>
<p><span data-ttu-id="e416e-297">パッケージの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e416e-297">For information about packages, see the following articles:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e416e-298">メソッド</span><span class="sxs-lookup"><span data-stu-id="e416e-298">Method</span></span></th>
<th align="left"><span data-ttu-id="e416e-299">詳細情報へのリンク</span><span class="sxs-lookup"><span data-stu-id="e416e-299">Link to more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-300">管理コンソール</span><span class="sxs-lookup"><span data-stu-id="e416e-300">Management console</span></span></p></td>
<td align="left"><p><a href="how-to-publish-a-package-by-using-the-management-console-50.md" data-raw-source="[How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-50.md)"><span data-ttu-id="e416e-301">管理コンソールを使用してパッケージを公開する方法</span><span class="sxs-lookup"><span data-stu-id="e416e-301">How to Publish a Package by Using the Management Console</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-302">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e416e-302">PowerShell</span></span></p></td>
<td align="left"><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admin-only-posh-topic-cg" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admin-only-posh-topic-cg)"><span data-ttu-id="e416e-303">PowerShell を使用してスタンドアロン コンピューターで接続グループを管理する方法</span><span class="sxs-lookup"><span data-stu-id="e416e-303">How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-304">サードパーティの電子ソフトウェア配信システム</span><span class="sxs-lookup"><span data-stu-id="e416e-304">Third-party electronic software delivery system</span></span></p></td>
<td align="left"><p><a href="how-to-enable-only-administrators-to-publish-packages-by-using-an-esd.md" data-raw-source="[How to Enable Only Administrators to Publish Packages by Using an ESD](how-to-enable-only-administrators-to-publish-packages-by-using-an-esd.md)"><span data-ttu-id="e416e-305">ESD を使用して管理者のみが公開パッケージを有効にできるようにする方法</span><span class="sxs-lookup"><span data-stu-id="e416e-305">How to Enable Only Administrators to Publish Packages by Using an ESD</span></span></a></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-306">特定のユーザーの接続グループを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="e416e-306">Enable or disable a connection group for a specific user</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-307">管理者は、 <strong> </strong> 次のコマンドレットを使用してオプション– UserSID パラメーターを使用して、特定のユーザーの接続グループを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e416e-307">Administrators can enable or disable a connection group for a specific user by using the optional <strong>–UserSID</strong> parameter with the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="e416e-308">Enable-AppVClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="e416e-308">Enable-AppVClientConnectionGroup</span></span></p></li>
<li><p><span data-ttu-id="e416e-309">Disable-AppVClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="e416e-309">Disable-AppVClientConnectionGroup</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-enable-cg-for-user-poshtopic" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-enable-cg-for-user-poshtopic)"><span data-ttu-id="e416e-310">PowerShell を使用してスタンドアロン コンピューターで接続グループを管理する方法</span><span class="sxs-lookup"><span data-stu-id="e416e-310">How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-311">同一のパッケージパスを接続グループ内の1つの仮想ディレクトリにマージする</span><span class="sxs-lookup"><span data-stu-id="e416e-311">Merging identical package paths into one virtual directory in connection groups</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-312">接続グループ内の2つ以上のパッケージに同一のディレクトリパスが含まれている場合、そのパスは接続グループの仮想環境内の1つの仮想ディレクトリにマージされます。</span><span class="sxs-lookup"><span data-stu-id="e416e-312">If two or more packages in a connection group contain identical directory paths, the paths are merged into a single virtual directory inside the connection group virtual environment.</span></span></p>
<p><span data-ttu-id="e416e-313">このパスの結合によって、1つのパッケージに含まれるアプリケーションが、別のパッケージに含まれているファイルにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="e416e-313">This merging of paths allows an application in one package to access files that are in a different package.</span></span></p></td>
<td align="left"><p><a href="about-the-connection-group-virtual-environment.md#bkmk-merged-root-ve-exp" data-raw-source="[About the Connection Group Virtual Environment](about-the-connection-group-virtual-environment.md#bkmk-merged-root-ve-exp)"><span data-ttu-id="e416e-314">接続グループの仮想環境について</span><span class="sxs-lookup"><span data-stu-id="e416e-314">About the Connection Group Virtual Environment</span></span></a></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-usersid-pub-pkgs-specf-user"></a><span data-ttu-id="e416e-315">管理者は、特定のユーザーに対してパッケージの発行と発行の取り消しを行うことができます</span><span class="sxs-lookup"><span data-stu-id="e416e-315">Administrators can publish and unpublish packages for a specific user</span></span>


<span data-ttu-id="e416e-316">管理者は、次のコマンドレットを使用して、特定のユーザーに対してパッケージを公開または非公開にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e416e-316">Administrators can use the following cmdlets to publish or unpublish packages for a specific user.</span></span> <span data-ttu-id="e416e-317">コマンドレットを使うには、 **– UserSID**パラメーターに続けてユーザーのセキュリティ識別子 (SID) を入力します。</span><span class="sxs-lookup"><span data-stu-id="e416e-317">To use the cmdlets, enter the **–UserSID** parameter, followed by the user’s security identifier (SID).</span></span> <span data-ttu-id="e416e-318">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e416e-318">For more information, see:</span></span>

-   [<span data-ttu-id="e416e-319">PowerShell を使用してスタンドアロン コンピューターで実行されている App-V 5.0 パッケージを管理する方法</span><span class="sxs-lookup"><span data-stu-id="e416e-319">How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span>](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-pub-pkg-a-user-standalone-posh)

-   [<span data-ttu-id="e416e-320">PowerShell を使用してスタンドアロン コンピューターで実行されている App-V 5.0 パッケージを管理する方法</span><span class="sxs-lookup"><span data-stu-id="e416e-320">How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span>](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-unpub-pkg-specfc-use)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e416e-321">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="e416e-321">Cmdlet</span></span></th>
<th align="left"><span data-ttu-id="e416e-322">例</span><span class="sxs-lookup"><span data-stu-id="e416e-322">Examples</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-323">公開-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="e416e-323">Publish-AppvClientPackage</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-324">Publish-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</span><span class="sxs-lookup"><span data-stu-id="e416e-324">Publish-AppvClientPackage “ContosoApplication” -UserSID S-1-2-34-56789012-3456789012-345678901-2345</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-325">未発行-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="e416e-325">Unpublish-AppvClientPackage</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-326">未発行-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</span><span class="sxs-lookup"><span data-stu-id="e416e-326">Unpublish-AppvClientPackage “ContosoApplication” -UserSID S-1-2-34-56789012-3456789012-345678901-2345</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-admins-only-pub-unpub-pkgs"></a><span data-ttu-id="e416e-327">管理者のみがパッケージの発行と発行を解除できるようにする</span><span class="sxs-lookup"><span data-stu-id="e416e-327">Enable only administrators to publish and unpublish packages</span></span>


<span data-ttu-id="e416e-328">次のいずれかの方法を使用して、管理者 (エンドユーザーではなく) だけがパッケージの発行と公開解除を行うことができるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e416e-328">You can enable only administrators (not end users) to publish and unpublish packages by using one of the following methods:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e416e-329">メソッド</span><span class="sxs-lookup"><span data-stu-id="e416e-329">Method</span></span></th>
<th align="left"><span data-ttu-id="e416e-330">詳細情報</span><span class="sxs-lookup"><span data-stu-id="e416e-330">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-331">グループ ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="e416e-331">Group Policy setting</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-332">次のグループポリシーオブジェクトノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="e416e-332">Navigate to the following Group Policy Object node:</span></span></p>
<p><strong><span data-ttu-id="e416e-333">コンピューター構成 &gt; ポリシー &gt; 管理用テンプレート &gt; System &gt; App-V の &gt; 公開 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="e416e-333">Computer Configuration &gt; Policies &gt; Administrative Templates &gt; System &gt; App-V &gt; Publishing</strong>.</span></span></p>
<p><span data-ttu-id="e416e-334">[ <strong> 管理者として発行する] グループポリシーの設定を有効にし </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="e416e-334">Enable the <strong>Require publish as administrator</strong> Group Policy setting.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-335">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e416e-335">PowerShell</span></span></p></td>
<td align="left"><p><a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs)"><span data-ttu-id="e416e-336">PowerShell を使用してスタンドアロン コンピューターで実行されている App-V 5.0 パッケージを管理する方法</span><span class="sxs-lookup"><span data-stu-id="e416e-336">How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span></a></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-runvirtual-reg-key"></a><span data-ttu-id="e416e-337">RunVirtual registry key は、ユーザーに公開されているパッケージをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e416e-337">RunVirtual registry key supports packages that are published to the user</span></span>


<span data-ttu-id="e416e-338">App-v 5.0 SP3 は、ユーザーによって公開されたパッケージ内の仮想化されたアプリケーションとの**Runvirtual** registry キーの使用をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e416e-338">App-V 5.0 SP3 adds support for using the **RunVirtual** registry key with virtualized applications that are in user-published packages.</span></span> <span data-ttu-id="e416e-339">**Runvirtual** registry キーを使うと、ローカルにインストールされたアプリケーションを仮想環境に、または app-v を使って仮想化されたアプリケーションと共に実行できます。</span><span class="sxs-lookup"><span data-stu-id="e416e-339">The **RunVirtual** registry key lets you run a locally installed application in a virtual environment, along with applications that have been virtualized by using App-V.</span></span>

<span data-ttu-id="e416e-340">以前は、App-v パッケージで仮想化されたアプリケーションをグローバルに公開する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="e416e-340">Previously, the virtualized applications in App-V packages had to be published globally.</span></span> <span data-ttu-id="e416e-341">**Runvirtual**について詳しくは、仮想化されたアプリケーションの仮想環境でローカルにインストールされたアプリケーションを実行するその他の方法については、「[仮想環境内でローカルにインストールされたアプリケーションを仮想化](running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md)されたアプリケーションで実行する」をご覧ください</span><span class="sxs-lookup"><span data-stu-id="e416e-341">For more about **RunVirtual** and about other methods of running locally installed applications in a virtual environment with virtualized applications, see [Running a Locally Installed Application Inside a Virtual Environment with Virtualized Applications](running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md).</span></span>

## <a href="" id="bkmk-posh-cmdlets-help"></a><span data-ttu-id="e416e-342">新しい PowerShell コマンドレットと更新可能なコマンドレットのヘルプ</span><span class="sxs-lookup"><span data-stu-id="e416e-342">New PowerShell cmdlets and updateable cmdlet help</span></span>


<span data-ttu-id="e416e-343">新しい PowerShell コマンドレットと更新可能なコマンドレットのヘルプは、App-v 5.0 SP3 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="e416e-343">New PowerShell cmdlets and updateable cmdlet help are included in App-V 5.0 SP3.</span></span> <span data-ttu-id="e416e-344">コマンドレットモジュールをダウンロードするには、「 [PowerShell コマンドレットを読み込み、コマンドレットのヘルプを取得する方法](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md#bkmk-load-cmdlets)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e416e-344">To download the cmdlet modules, see [How to Load the PowerShell Cmdlets and Get Cmdlet Help](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md#bkmk-load-cmdlets).</span></span>

### <span data-ttu-id="e416e-345">新しいアプリ-V 5.0 SP3 サーバー PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="e416e-345">New App-V 5.0 SP3 Server PowerShell cmdlets</span></span>

<span data-ttu-id="e416e-346">接続グループを管理できるように、App-v Server 用の新しい Windows PowerShell コマンドレットが追加されました。</span><span class="sxs-lookup"><span data-stu-id="e416e-346">New Windows PowerShell cmdlets for the App-V Server have been added to help you manage connection groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e416e-347">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="e416e-347">Cmdlet</span></span></th>
<th align="left"><span data-ttu-id="e416e-348">説明</span><span class="sxs-lookup"><span data-stu-id="e416e-348">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-349">Add-AppvServerConnectionGroupPackage</span><span class="sxs-lookup"><span data-stu-id="e416e-349">Add-AppvServerConnectionGroupPackage</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-350">接続グループ&#39;s パッケージリストの末尾にパッケージを追加して、パッケージをオプションとして、または接続グループ内のバージョンなしで構成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e416e-350">Appends a package to the end of a connection group&#39;s package list and enables you to configure the package as optional and/or with no version within the connection group.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-351">Set-AppvServerConnectionGroupPackage</span><span class="sxs-lookup"><span data-stu-id="e416e-351">Set-AppvServerConnectionGroupPackage</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-352">オプションであるかどうかなど、接続グループパッケージの詳細を編集できます。</span><span class="sxs-lookup"><span data-stu-id="e416e-352">Enables you to edit details about the connection group package, such as whether it is optional.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-353">Remove-AppvServerConnectionGroupPackage</span><span class="sxs-lookup"><span data-stu-id="e416e-353">Remove-AppvServerConnectionGroupPackage</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-354">接続グループからパッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="e416e-354">Removes a package from a connection group.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-get-cmdlet-help"></a><span data-ttu-id="e416e-355">PowerShell コマンドレットのヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="e416e-355">Getting help for the PowerShell cmdlets</span></span>

<span data-ttu-id="e416e-356">コマンドレットのヘルプは、次の形式で利用できます。</span><span class="sxs-lookup"><span data-stu-id="e416e-356">Cmdlet help is available in the following formats:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e416e-357">形式</span><span class="sxs-lookup"><span data-stu-id="e416e-357">Format</span></span></th>
<th align="left"><span data-ttu-id="e416e-358">説明</span><span class="sxs-lookup"><span data-stu-id="e416e-358">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-359">ダウンロード可能なモジュールとして</span><span class="sxs-lookup"><span data-stu-id="e416e-359">As a downloadable module</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-360">コマンドレットモジュールをダウンロードした後に最新のヘルプを表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e416e-360">To get the latest help after downloading the cmdlet module:</span></span></p>
<ol>
<li><p><span data-ttu-id="e416e-361">Windows PowerShell または Windows PowerShell Integrated Scripting Environment (ISE) を開きます。</span><span class="sxs-lookup"><span data-stu-id="e416e-361">Open Windows PowerShell or Windows PowerShell Integrated Scripting Environment (ISE).</span></span></p></li>
<li><p><span data-ttu-id="e416e-362">次のいずれかのコマンドを入力して、目的のモジュールのコマンドレットを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="e416e-362">Type one of the following commands to load the cmdlets for the module you want:</span></span></p></li>
</ol>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e416e-363">App-v コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e416e-363">App-V component</span></span></th>
<th align="left"><span data-ttu-id="e416e-364">入力するコマンド</span><span class="sxs-lookup"><span data-stu-id="e416e-364">Command to type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-365">App-v Server</span><span class="sxs-lookup"><span data-stu-id="e416e-365">App-V Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-366">更新-ヘルプ-モジュール AppvServer</span><span class="sxs-lookup"><span data-stu-id="e416e-366">Update-Help-Module AppvServer</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-367">App-v Sequencer</span><span class="sxs-lookup"><span data-stu-id="e416e-367">App-V Sequencer</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-368">更新-ヘルプ-モジュール AppvSequencer</span><span class="sxs-lookup"><span data-stu-id="e416e-368">Update-Help-Module AppvSequencer</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-369">App-v クライアント</span><span class="sxs-lookup"><span data-stu-id="e416e-369">App-V client</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-370">更新-ヘルプ-モジュール AppvClient</span><span class="sxs-lookup"><span data-stu-id="e416e-370">Update-Help-Module AppvClient</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-371">Web ページとしての TechNet の場合</span><span class="sxs-lookup"><span data-stu-id="e416e-371">On TechNet as web pages</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-372">「 <a href="https://technet.microsoft.com/library/dn520245.aspx" data-raw-source="[Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://technet.microsoft.com/library/dn520245.aspx)"> Windows PowerShell での Microsoft デスクトップ最適化パックオートメーション」の下の [App-V] ノードを参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="e416e-372">See the App-V node under <a href="https://technet.microsoft.com/library/dn520245.aspx" data-raw-source="[Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://technet.microsoft.com/library/dn520245.aspx)">Microsoft Desktop Optimization Pack Automation with Windows PowerShell</a>.</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="e416e-373">詳細については、「 [PowerShell コマンドレットを読み込み、コマンドレットのヘルプを取得する方法](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e416e-373">For more information, see [How to Load the PowerShell Cmdlets and Get Cmdlet Help](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md).</span></span>

## <a href="" id="bkmk-pvad-hidden"></a><span data-ttu-id="e416e-374">プライマリ仮想アプリケーションディレクトリ (PVAD) は非表示になっていますが、オンにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e416e-374">Primary virtual application directory (PVAD) is hidden but can be turned on</span></span>


<span data-ttu-id="e416e-375">プライマリ仮想アプリケーションディレクトリ (PVAD) は、App-v 5.0 SP3 では非表示になっていますが、次のいずれかの方法を使用して再びオンにし、表示することができます。</span><span class="sxs-lookup"><span data-stu-id="e416e-375">The primary virtual application directory (PVAD) is hidden in App-V 5.0 SP3, but you can turn it back on and make it visible by using one of the following methods:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e416e-376">メソッド</span><span class="sxs-lookup"><span data-stu-id="e416e-376">Method</span></span></th>
<th align="left"><span data-ttu-id="e416e-377">手順</span><span class="sxs-lookup"><span data-stu-id="e416e-377">Steps</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e416e-378">コマンドラインパラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="e416e-378">Use a command line parameter</span></span></p></td>
<td align="left"><p><span data-ttu-id="e416e-379"><strong>– Enablepvadcontrol </strong> パラメーターをSequencer.exeに渡し <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="e416e-379">Pass the <strong>–EnablePVADControl</strong> parameter to the <strong>Sequencer.exe</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e416e-380">レジストリサブキーを作成する</span><span class="sxs-lookup"><span data-stu-id="e416e-380">Create a registry subkey</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="e416e-381">レジストリエディターで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e416e-381">In the Registry Editor, navigate to:</span></span> <code>HKLM\SOFTWARE\Microsoft\AppV\Sequencer\Compatibility</code></p>
<div class="alert">
<strong><span data-ttu-id="e416e-382">注</span><span class="sxs-lookup"><span data-stu-id="e416e-382">Note</span></span></strong><br/><p><span data-ttu-id="e416e-383">サブキーが存在しない場合は <code>Compatibility</code> 、作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e416e-383">If the <code>Compatibility</code> subkey doesn’t exist, you must create it.</span></span></p>
</div>
<div>

</div></li>
<li><p><span data-ttu-id="e416e-384">Enablepvadcontrol という名前の DWORD 値を作成 <strong> </strong> し、値を1に設定し <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="e416e-384">Create a DWORD Value named <strong>EnablePVADControl</strong>, and set the value to <strong>1</strong>.</span></span></p>
<p><span data-ttu-id="e416e-385">値が0の場合は、 <strong> </strong> pvad が非表示になることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e416e-385">A value of <strong>0</strong> means that PVAD is hidden.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>



<span data-ttu-id="e416e-386">**PVAD の詳細:** Sequencer を使ってパッケージを作成する場合は、パッケージの任意のインストールパスを入力できます。</span><span class="sxs-lookup"><span data-stu-id="e416e-386">**More about PVAD:** When you use the Sequencer to create a package, you can enter any installation path for the package.</span></span> <span data-ttu-id="e416e-387">以前のバージョンの App-v では、アプリケーションのプライマリ仮想アプリケーションディレクトリ (PVAD) をパスとして指定する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="e416e-387">In past versions of App-V, you were required to specify the primary virtual application directory (PVAD) of the application as the path.</span></span> <span data-ttu-id="e416e-388">PVAD は、通常は、App-v を使っていない場合に、ローカルコンピューターにアプリケーションをインストールするディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="e416e-388">PVAD is the directory to which you would typically install an application on your local computer if you weren’t using App-V.</span></span> <span data-ttu-id="e416e-389">たとえば、コンピューターに Office をインストールする場合は、通常、PVAD は c/1/1 (Microsoft office¥) となります。</span><span class="sxs-lookup"><span data-stu-id="e416e-389">For example, if you were installing Office on a computer, the PVAD typically would be C:\\Program Files\\Microsoft Office\\.</span></span>

## <a href="" id="bkmk-pub-metadata-clientversion"></a><span data-ttu-id="e416e-390">App-v の公開メタデータを表示するには、ClientVersion が必要です</span><span class="sxs-lookup"><span data-stu-id="e416e-390">ClientVersion is required to view App-V publishing metadata</span></span>


<span data-ttu-id="e416e-391">App-v 5.0 SP3 では、メタデータのために App-v パブリッシングサーバーにクエリを実行するときに、アドレスに次の値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e416e-391">In App-V 5.0 SP3, you must provide the following values in the address when you query the App-V Publishing server for metadata:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e416e-392">値</span><span class="sxs-lookup"><span data-stu-id="e416e-392">Value</span></span></th>
<th align="left"><span data-ttu-id="e416e-393">追加情報</span><span class="sxs-lookup"><span data-stu-id="e416e-393">Additional details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e416e-394">ClientVersion</span><span class="sxs-lookup"><span data-stu-id="e416e-394">ClientVersion</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e416e-395">クエリから clientversion パラメーターを省略した場合、 <strong> </strong> メタデータには新しいアプリ-V 5.0 SP3 機能は含まれません。</span><span class="sxs-lookup"><span data-stu-id="e416e-395">If you omit the <strong>ClientVersion</strong> parameter from the query, the metadata excludes the new App-V 5.0 SP3 features.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e416e-396">ClientOS</span><span class="sxs-lookup"><span data-stu-id="e416e-396">ClientOS</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e416e-397">この値を指定する必要があるのは、パッケージの順序を指定するときに特定のクライアントオペレーティングシステムを選択する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="e416e-397">You have to provide this value only if you select specific client operating systems when you sequence the package.</span></span> <span data-ttu-id="e416e-398">既定の (すべてのオペレーティングシステム) を選択した場合は、この値をクエリで指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="e416e-398">If you select the default (all operating systems), do not specify this value in the query.</span></span></p>
<p><span data-ttu-id="e416e-399"><strong>クエリから clientos パラメーターを省略した場合 </strong> 、任意のオペレーティングシステムをサポートするように指定されたパッケージのみがメタデータに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e416e-399">If you omit the <strong>ClientOS</strong> parameter from the query, only the packages that were sequenced to support any operating system appear in the metadata.</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="e416e-400">このクエリの構文と例については、「 [App-v Server 発行メタデータを表示](viewing-app-v-server-publishing-metadata.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e416e-400">For syntax and examples of this query, see [Viewing App-V Server Publishing Metadata](viewing-app-v-server-publishing-metadata.md).</span></span>

## <a href="" id="bkmk-event-logs-moved"></a><span data-ttu-id="e416e-401">App-v のイベントログが統合されている</span><span class="sxs-lookup"><span data-stu-id="e416e-401">App-V event logs have been consolidated</span></span>


<span data-ttu-id="e416e-402">次のイベントログは、以前は**アプリケーションとサービスログ、microsoft/appv/app-v &lt; コンポーネント &gt; **に置かれていましたが、**アプリケーションとサービスログ、Microsoft/appv/servicelog**に移動されました。</span><span class="sxs-lookup"><span data-stu-id="e416e-402">The following event logs, previously located at **Applications and Services Logs/Microsoft/AppV/&lt;App-V component&gt;**, have been moved to **Applications and Services Logs/Microsoft/AppV/ServiceLog**.</span></span>

<span data-ttu-id="e416e-403">ログを表示するには**View** 、 &gt; イベントビューアーアプリケーションで、[**分析ログとデバッグログ**の表示] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e416e-403">To view the logs, select **View** &gt; **Show Analytic and Debug Logs** in the Event Viewer application.</span></span>

<span data-ttu-id="e416e-404">クライアント-カタログクライアント統合クライアント-オーケストレーションクライアント-VFSC FilesystemMetadataLibrary ManifestLibrary-スクリプトクライアント-サービスクライアント-Vemgr Client-ManifestLibrary Policy Library サブシステム-AppPath サブシステム-Com サブシステム– fta</span><span class="sxs-lookup"><span data-stu-id="e416e-404">Client-Catalog Client-Integration Client-Orchestration Client-PackageConfig Client-Scripting Client-Service Client-Vemgr Client-VFSC FilesystemMetadataLibrary ManifestLibrary PolicyLibrary Subsystems-ActiveX Subsystems-AppPath Subsystems-Com Subsystems-fta</span></span>

## <span data-ttu-id="e416e-405">MDOP 技術の入手方法</span><span class="sxs-lookup"><span data-stu-id="e416e-405">How to Get MDOP Technologies</span></span>


<span data-ttu-id="e416e-406">App-v は、Microsoft デスクトップ最適化パック (MDOP) の一部です。</span><span class="sxs-lookup"><span data-stu-id="e416e-406">App-V is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="e416e-407">MDOP は、Microsoft ソフトウェアアシュアランスの一部です。</span><span class="sxs-lookup"><span data-stu-id="e416e-407">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="e416e-408">Microsoft ソフトウェアアシュアランスと MDOP の入手の詳細については、「 [mdop の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e416e-408">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>






## <span data-ttu-id="e416e-409">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e416e-409">Related topics</span></span>


[<span data-ttu-id="e416e-410">App-V 5.0 SP3 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="e416e-410">Release Notes for App-V 5.0 SP3</span></span>](release-notes-for-app-v-50-sp3.md)









