---
title: App-V 5.1 について
description: App-V 5.1 について
author: dansimp
ms.assetid: 35bc9908-d502-4a9c-873f-8ee17b6d9d74
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4f2404dcd431b32f5d9a4ae7c49f1e376979e04e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814947"
---
# <span data-ttu-id="db443-103">App-V 5.1 について</span><span class="sxs-lookup"><span data-stu-id="db443-103">About App-V 5.1</span></span>


<span data-ttu-id="db443-104">Application Virtualization (App-v) 5.1 に適用される重大な変更に関する情報を確認するには、次のセクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="db443-104">Use the following sections to review information about significant changes that apply to Application Virtualization (App-V) 5.1:</span></span>

[<span data-ttu-id="db443-105">App-v 5.1 ソフトウェアの前提条件とサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="db443-105">App-V 5.1 software prerequisites and supported configurations</span></span>](#bkmk-51-prereq-configs)

[<span data-ttu-id="db443-106">App への移行-V 5.1</span><span class="sxs-lookup"><span data-stu-id="db443-106">Migrating to App-V 5.1</span></span>](#bkmk-migrate-to-51)

[<span data-ttu-id="db443-107">App-v 5.1 の新機能</span><span class="sxs-lookup"><span data-stu-id="db443-107">What’s New in App-V 5.1</span></span>](#bkmk-whatsnew)

[<span data-ttu-id="db443-108">Windows 10 での app-v のサポート</span><span class="sxs-lookup"><span data-stu-id="db443-108">App-V support for Windows 10</span></span>](#bkmk-win10support)

[<span data-ttu-id="db443-109">App-v 管理コンソールの変更</span><span class="sxs-lookup"><span data-stu-id="db443-109">App-V Management Console Changes</span></span>](#bkmk-mgmtconsole)

[<span data-ttu-id="db443-110">Sequencer の機能強化</span><span class="sxs-lookup"><span data-stu-id="db443-110">Sequencer Improvements</span></span>](#bkmk-seqimprove)

[<span data-ttu-id="db443-111">パッケージコンバーターの改善</span><span class="sxs-lookup"><span data-stu-id="db443-111">Improvements to Package Converter</span></span>](#bkmk-pkgconvimprove)

[<span data-ttu-id="db443-112">1つのイベントトリガーでの複数のスクリプトのサポート</span><span class="sxs-lookup"><span data-stu-id="db443-112">Support for multiple scripts on a single event trigger</span></span>](#bkmk-supmultscripts)

[<span data-ttu-id="db443-113">インストールフォルダーへのハードコーディングされたパスは、仮想ファイルシステムのルートにリダイレクトされます</span><span class="sxs-lookup"><span data-stu-id="db443-113">Hardcoded path to installation folder is redirected to virtual file system root</span></span>](#bkmk-hardcodepath)

## <a href="" id="bkmk-51-prereq-configs"></a><span data-ttu-id="db443-114">App-v 5.1 ソフトウェアの前提条件とサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="db443-114">App-V 5.1 software prerequisites and supported configurations</span></span>


<span data-ttu-id="db443-115">App-V 5.1 ソフトウェアの前提条件とサポートされる構成については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="db443-115">See the following links for the App-V 5.1 software prerequisites and supported configurations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="db443-116">前提条件とサポートされる構成へのリンク</span><span class="sxs-lookup"><span data-stu-id="db443-116">Links to prerequisites and supported configurations</span></span></th>
<th align="left"><span data-ttu-id="db443-117">説明</span><span class="sxs-lookup"><span data-stu-id="db443-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="app-v-51-prerequisites.md" data-raw-source="[App-V 5.1 Prerequisites](app-v-51-prerequisites.md)"><span data-ttu-id="db443-118">App-V 5.1 の前提条件</span><span class="sxs-lookup"><span data-stu-id="db443-118">App-V 5.1 Prerequisites</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="db443-119">App-v 5.1 のインストールを開始する前にインストールする必要がある必須ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="db443-119">Prerequisite software that you must install before starting the App-V 5.1 installation</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="app-v-51-supported-configurations.md" data-raw-source="[App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md)"><span data-ttu-id="db443-120">App-V 5.1 でサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="db443-120">App-V 5.1 Supported Configurations</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="db443-121">App-v Server、Sequencer、およびクライアントコンポーネントのサポートされているオペレーティングシステムとハードウェアの要件</span><span class="sxs-lookup"><span data-stu-id="db443-121">Supported operating systems and hardware requirements for the App-V Server, Sequencer, and Client components</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="db443-122">**Configuration Manager を app-v と共に使用する場合のサポート:** App-v 5.1 は System Center 2012 R2 Configuration Manager SP1 をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="db443-122">**Support for using Configuration Manager with App-V:** App-V 5.1 supports System Center 2012 R2 Configuration Manager SP1.</span></span> <span data-ttu-id="db443-123">構成マネージャーと構成マネージャーとのアプリの統合については、「 [Configuration manager とのアプリの統合の計画](https://technet.microsoft.com/library/jj822982.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="db443-123">See [Planning for App-V Integration with Configuration Manager](https://technet.microsoft.com/library/jj822982.aspx) for information about integrating your App-V environment with Configuration Manager and Configuration Manager.</span></span>

## <a href="" id="bkmk-migrate-to-51"></a><span data-ttu-id="db443-124">App への移行-V 5.1</span><span class="sxs-lookup"><span data-stu-id="db443-124">Migrating to App-V 5.1</span></span>


<span data-ttu-id="db443-125">以前のバージョンから App-v 5.1 にアップグレードするには、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="db443-125">Use the following information to upgrade to App-V 5.1 from earlier versions.</span></span> <span data-ttu-id="db443-126">詳細について[は、「以前のバージョンから app-v 5.1 に移行する](migrating-to-app-v-51-from-a-previous-version.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db443-126">See [Migrating to App-V 5.1 from a Previous Version](migrating-to-app-v-51-from-a-previous-version.md) for more information.</span></span>

### <span data-ttu-id="db443-127">アップグレードを開始する前に</span><span class="sxs-lookup"><span data-stu-id="db443-127">Before you start the upgrade</span></span>

<span data-ttu-id="db443-128">アップグレードを開始する前に、次の情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="db443-128">Review the following information before you start the upgrade:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="db443-129">アップグレード前に確認する項目</span><span class="sxs-lookup"><span data-stu-id="db443-129">Items to review before upgrading</span></span></th>
<th align="left"><span data-ttu-id="db443-130">説明</span><span class="sxs-lookup"><span data-stu-id="db443-130">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="db443-131">アップグレードするコンポーネント (任意の順序)</span><span class="sxs-lookup"><span data-stu-id="db443-131">Components to upgrade, in any order</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="db443-132">App-v Server</span><span class="sxs-lookup"><span data-stu-id="db443-132">App-V Server</span></span></p></li>
<li><p><span data-ttu-id="db443-133">Sequencer (シーケンサー)</span><span class="sxs-lookup"><span data-stu-id="db443-133">Sequencer</span></span></p></li>
<li><p><span data-ttu-id="db443-134">App-v Client または App-v リモートデスクトップサービス (RDS) クライアント</span><span class="sxs-lookup"><span data-stu-id="db443-134">App-V Client or App-V Remote Desktop Services (RDS) Client</span></span></p></li>
</ol>
<div class="alert">
<strong><span data-ttu-id="db443-135">注</span><span class="sxs-lookup"><span data-stu-id="db443-135">Note</span></span></strong><br/><p><span data-ttu-id="db443-136">App-v 5.0 SP2 より前に、クライアント管理ユーザーインターフェイス (UI) は、App-v クライアントのインストールで提供されていました。</span><span class="sxs-lookup"><span data-stu-id="db443-136">Prior to App-V 5.0 SP2, the Client Management User Interface (UI) was provided with the App-V Client installation.</span></span> <span data-ttu-id="db443-137">App-v 5.0 SP2 インストール (以降) の場合は、 <a href="https://www.microsoft.com/download/details.aspx?id=41186" data-raw-source="[Application Virtualization 5.0 Client UI Application](https://www.microsoft.com/download/details.aspx?id=41186)"> Application Virtualization 5.0 クライアント UI アプリケーションからダウンロードして、クライアント管理 UI を使用でき </a> ます。</span><span class="sxs-lookup"><span data-stu-id="db443-137">For App-V 5.0 SP2 installations (or later), you can use the Client Management UI by downloading from <a href="https://www.microsoft.com/download/details.aspx?id=41186" data-raw-source="[Application Virtualization 5.0 Client UI Application](https://www.microsoft.com/download/details.aspx?id=41186)">Application Virtualization 5.0 Client UI Application</a>.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="db443-138">アプリからのアップグレード-V 4. x</span><span class="sxs-lookup"><span data-stu-id="db443-138">Upgrading from App-V 4.x</span></span></p></td>
<td align="left"><p><span data-ttu-id="db443-139">まず、App-V 5.0 にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="db443-139">You must first upgrade to App-V 5.0.</span></span> <span data-ttu-id="db443-140">App-v から app-v 5.1 に直接アップグレードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="db443-140">You cannot upgrade directly from App-V 4.x to App-V 5.1.</span></span> <span data-ttu-id="db443-141">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db443-141">For more information, see:</span></span></p>
<ul>
<li><p><span data-ttu-id="db443-142"><a href="about-app-v-50.md" data-raw-source="[About App-V 5.0](about-app-v-50.md)">アプリ-v 5.0 についての「app-v 4.6 と app-v 5.0 の違い」</span><span class="sxs-lookup"><span data-stu-id="db443-142">“Differences between App-V 4.6 and App-V 5.0” in <a href="about-app-v-50.md" data-raw-source="[About App-V 5.0](about-app-v-50.md)">About App-V 5.0</span></span></a></p></li>
<li><p><a href="planning-for-migrating-from-a-previous-version-of-app-v.md" data-raw-source="[Planning for Migrating from a Previous Version of App-V](planning-for-migrating-from-a-previous-version-of-app-v.md)"><span data-ttu-id="db443-143">APP-V の以前のバージョンからの移行計画</span><span class="sxs-lookup"><span data-stu-id="db443-143">Planning for Migrating from a Previous Version of App-V</span></span></a></p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="db443-144">App-v 5.0 以降からのアップグレード</span><span class="sxs-lookup"><span data-stu-id="db443-144">Upgrading from App-V 5.0 or later</span></span></p></td>
<td align="left"><p><span data-ttu-id="db443-145">以下のいずれかのバージョンから直接 App-v 5.1 にアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="db443-145">You can upgrade to App-V 5.1 directly from any of the following versions:</span></span></p>
<ul>
<li><p><span data-ttu-id="db443-146">App-v 5.0</span><span class="sxs-lookup"><span data-stu-id="db443-146">App-V 5.0</span></span></p></li>
<li><p><span data-ttu-id="db443-147">App-v 5.0 SP1</span><span class="sxs-lookup"><span data-stu-id="db443-147">App-V 5.0 SP1</span></span></p></li>
<li><p><span data-ttu-id="db443-148">App-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="db443-148">App-V 5.0 SP2</span></span></p></li>
<li><p><span data-ttu-id="db443-149">App-v 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="db443-149">App-V 5.0 SP3</span></span></p></li>
</ul>
<p><span data-ttu-id="db443-150">App-v 5.1 にアップグレードするには、このトピックの残りのセクションの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="db443-150">To upgrade to App-V 5.1, follow the steps in the remaining sections of this topic.</span></span></p>
<p><span data-ttu-id="db443-151">パッケージと接続グループは、現在の場合と同様に、引き続き App-v 5.1 で動作します。</span><span class="sxs-lookup"><span data-stu-id="db443-151">Packages and connection groups will continue to work with App-V 5.1 as they currently do.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-steps-upgrd-infrastruc"></a><span data-ttu-id="db443-152">App-v インフラストラクチャのアップグレード手順</span><span class="sxs-lookup"><span data-stu-id="db443-152">Steps to upgrade the App-V infrastructure</span></span>

<span data-ttu-id="db443-153">次の手順を実行して、app-v インフラストラクチャの各コンポーネントを App-v 5.1 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="db443-153">Complete the following steps to upgrade each component of the App-V infrastructure to App-V 5.1.</span></span> <span data-ttu-id="db443-154">次の順序は提案にすぎません。コンポーネントのアップグレードは任意の順序で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="db443-154">The following order is only a suggestion; you may upgrade components in any order.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="db443-155">ステップ</span><span class="sxs-lookup"><span data-stu-id="db443-155">Step</span></span></th>
<th align="left"><span data-ttu-id="db443-156">詳細情報</span><span class="sxs-lookup"><span data-stu-id="db443-156">For more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="db443-157">手順 1: App-v Server をアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="db443-157">Step 1: Upgrade the App-V Server.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="db443-158">注</span><span class="sxs-lookup"><span data-stu-id="db443-158">Note</span></span></strong><br/><p><span data-ttu-id="db443-159">App-v Server を使っていない場合は、この手順をスキップして次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="db443-159">If you are not using the App-V Server, skip this step and go to the next step.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="db443-160">次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="db443-160">Follow these steps:</span></span></p>
<ol>
<li><p><span data-ttu-id="db443-161">管理データベースやレポートデータベースのアップグレードに使用する方法に応じて、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="db443-161">Do one of the following, depending on the method you are using to upgrade the Management database and/or Reporting database:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="db443-162">データベースのアップグレード方法</span><span class="sxs-lookup"><span data-stu-id="db443-162">Database upgrade method</span></span></th>
<th align="left"><span data-ttu-id="db443-163">ステップ</span><span class="sxs-lookup"><span data-stu-id="db443-163">Step</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="db443-164">Windows インストーラー</span><span class="sxs-lookup"><span data-stu-id="db443-164">Windows Installer</span></span></p></td>
<td align="left"><p><span data-ttu-id="db443-165">この手順をスキップして、「App-v Server をアップグレードする場合」の手順2に進みます。</span><span class="sxs-lookup"><span data-stu-id="db443-165">Skip this step and go to step 2, “If you are upgrading the App-V Server...”</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="db443-166">SQL スクリプト</span><span class="sxs-lookup"><span data-stu-id="db443-166">SQL scripts</span></span></p></td>
<td align="left"><p><span data-ttu-id="db443-167"><a href="how-to-deploy-the-app-v-databases-by-using-sql-scripts.md" data-raw-source="[How to Deploy the App-V Databases by Using SQL Scripts](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md)">「SQL スクリプトを使用して App-v データベースを展開する方法」の手順に従い </a> ます。</span><span class="sxs-lookup"><span data-stu-id="db443-167">Follow the steps in <a href="how-to-deploy-the-app-v-databases-by-using-sql-scripts.md" data-raw-source="[How to Deploy the App-V Databases by Using SQL Scripts](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md)">How to Deploy the App-V Databases by Using SQL Scripts</a>.</span></span></p></td>
</tr>
</tbody>
</table>
<li><p><span data-ttu-id="db443-168">App-v Server を App-v 5.0 SP1 修正プログラムパッケージ3以降でアップグレードする場合は、「 <a href="check-reg-key-svr.md" data-raw-source="[Check registry keys after installing the App-V 5.0 SP3 Server](check-reg-key-svr.md)"> app-v 5.0 SP3 サーバーをインストールした後でレジストリキーを確認する」の手順を実行し </a> ます。</span><span class="sxs-lookup"><span data-stu-id="db443-168">If you are upgrading the App-V Server from App-V 5.0 SP1 Hotfix Package 3 or later, complete the steps in section <a href="check-reg-key-svr.md" data-raw-source="[Check registry keys after installing the App-V 5.0 SP3 Server](check-reg-key-svr.md)">Check registry keys after installing the App-V 5.0 SP3 Server</a>.</span></span></p></li>
<li><p><span data-ttu-id="db443-169">「 <a href="how-to-deploy-the-app-v-51-server.md" data-raw-source="[How to Deploy the App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md)"> App-v 5.1 サーバーを展開する方法」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="db443-169">Follow the steps in <a href="how-to-deploy-the-app-v-51-server.md" data-raw-source="[How to Deploy the App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md)">How to Deploy the App-V 5.1 Server</span></span></a></p></li>
<p> </p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="db443-170">手順 2: App-v Sequencer をアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="db443-170">Step 2: Upgrade the App-V Sequencer.</span></span></p></td>
<td align="left"><p><span data-ttu-id="db443-171"><a href="how-to-install-the-sequencer-beta-gb18030.md" data-raw-source="[How to Install the Sequencer](how-to-install-the-sequencer-beta-gb18030.md)">Sequencer をインストールする方法について説明し </a> ます。</span><span class="sxs-lookup"><span data-stu-id="db443-171">See <a href="how-to-install-the-sequencer-beta-gb18030.md" data-raw-source="[How to Install the Sequencer](how-to-install-the-sequencer-beta-gb18030.md)">How to Install the Sequencer</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="db443-172">手順 3: App-v クライアントまたは App-v RDS クライアントをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="db443-172">Step 3: Upgrade the App-V Client or App-V RDS Client.</span></span></p></td>
<td align="left"><p><span data-ttu-id="db443-173">「 <a href="how-to-deploy-the-app-v-client-gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md)"> App-v クライアントを展開する方法」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="db443-173">See <a href="how-to-deploy-the-app-v-client-gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md)">How to Deploy the App-V Client</a>.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="db443-174">以前のバージョンの App-v を使用して作成されたパッケージの変換</span><span class="sxs-lookup"><span data-stu-id="db443-174">Converting packages created using a prior version of App-V</span></span>

<span data-ttu-id="db443-175">Package converter ユーティリティーを使って、app-v 5.0 のバージョンを使って作成された仮想アプリケーションパッケージをアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="db443-175">Use the package converter utility to upgrade virtual application packages created using versions of App-V prior to App-V 5.0.</span></span> <span data-ttu-id="db443-176">パッケージコンバーターは、PowerShell を使用してパッケージを変換し、変換が必要なパッケージが多い場合は、プロセスの自動化に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="db443-176">The package converter uses PowerShell to convert packages and can help automate the process if you have many packages that require conversion.</span></span>

**<span data-ttu-id="db443-177">注</span><span class="sxs-lookup"><span data-stu-id="db443-177">Note</span></span>**  
<span data-ttu-id="db443-178">App-v 5.1 パッケージは、app-v 5.0 パッケージとまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="db443-178">App-V 5.1 packages are exactly the same as App-V 5.0 packages.</span></span> <span data-ttu-id="db443-179">バージョン間のパッケージ形式は変更されていないため、App-v 5.0 パッケージを App-v 5.1 パッケージに変換する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="db443-179">There has been no change in the package format between the versions and so there is no need to convert App-V 5.0 packages to App-V 5.1 packages.</span></span>



## <a href="" id="bkmk-whatsnew"></a><span data-ttu-id="db443-180">App-v 5.1 の新機能</span><span class="sxs-lookup"><span data-stu-id="db443-180">What’s New in App-V 5.1</span></span>


<span data-ttu-id="db443-181">これらのセクションは、既に App-v に精通していて、App-v 5.1 で何が変更されているかを確認したいユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="db443-181">These sections are for users who are already familiar with App-V and want to know what has changed in App-V 5.1.</span></span> <span data-ttu-id="db443-182">まだ App-v に精通していない場合は、まず「 [app-v 5.1 の計画](planning-for-app-v-51.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db443-182">If you are not already familiar with App-V, you should start by reading [Planning for App-V 5.1](planning-for-app-v-51.md).</span></span>

### <a href="" id="bkmk-win10support"></a><span data-ttu-id="db443-183">Windows 10 での app-v のサポート</span><span class="sxs-lookup"><span data-stu-id="db443-183">App-V support for Windows 10</span></span>

<span data-ttu-id="db443-184">次の表は、Windows 10 の App-v のサポートを示しています。</span><span class="sxs-lookup"><span data-stu-id="db443-184">The following table lists the Windows 10 support for App-V.</span></span> <span data-ttu-id="db443-185">Windows 10 は、アプリ-v 5.1 より前のバージョンではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="db443-185">Windows 10 is not supported in versions of App-V prior to App-V 5.1.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="db443-186">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="db443-186">Component</span></span></th>
<th align="left"><span data-ttu-id="db443-187">App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="db443-187">App-V 5.1</span></span></th>
<th align="left"><span data-ttu-id="db443-188">App-v 5.0</span><span class="sxs-lookup"><span data-stu-id="db443-188">App-V 5.0</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="db443-189">App-v クライアント</span><span class="sxs-lookup"><span data-stu-id="db443-189">App-V Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="db443-190">あり</span><span class="sxs-lookup"><span data-stu-id="db443-190">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="db443-191">なし</span><span class="sxs-lookup"><span data-stu-id="db443-191">No</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="db443-192">App-v RDS クライアント</span><span class="sxs-lookup"><span data-stu-id="db443-192">App-V RDS Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="db443-193">あり</span><span class="sxs-lookup"><span data-stu-id="db443-193">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="db443-194">なし</span><span class="sxs-lookup"><span data-stu-id="db443-194">No</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="db443-195">App-v Sequencer</span><span class="sxs-lookup"><span data-stu-id="db443-195">App-V Sequencer</span></span></p></td>
<td align="left"><p><span data-ttu-id="db443-196">あり</span><span class="sxs-lookup"><span data-stu-id="db443-196">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="db443-197">なし</span><span class="sxs-lookup"><span data-stu-id="db443-197">No</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-mgmtconsole"></a><span data-ttu-id="db443-198">App-v 管理コンソールの変更</span><span class="sxs-lookup"><span data-stu-id="db443-198">App-V Management Console Changes</span></span>

<span data-ttu-id="db443-199">このセクションでは、App-v 管理コンソールの現在の機能と以前の機能を比較します。</span><span class="sxs-lookup"><span data-stu-id="db443-199">This section compares the App-V Management Console’s current and previous functionality.</span></span>

### <span data-ttu-id="db443-200">Silverlight は必要なくなりました</span><span class="sxs-lookup"><span data-stu-id="db443-200">Silverlight is no longer required</span></span>

<span data-ttu-id="db443-201">管理コンソールの UI には Silverlight は不要です。</span><span class="sxs-lookup"><span data-stu-id="db443-201">The Management Console UI no longer requires Silverlight.</span></span> <span data-ttu-id="db443-202">5.1 管理コンソールは、HTML5 と Javascript で構築されています。</span><span class="sxs-lookup"><span data-stu-id="db443-202">The 5.1 Management Console is built on HTML5 and Javascript.</span></span>

### <span data-ttu-id="db443-203">通知とメッセージが個別にダイアログボックスに表示される</span><span class="sxs-lookup"><span data-stu-id="db443-203">Notifications and messages are displayed individually in a dialog box</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="db443-204">アプリの新バージョン-V 5.1</span><span class="sxs-lookup"><span data-stu-id="db443-204">New in App-V 5.1</span></span></th>
<th align="left"><span data-ttu-id="db443-205">App-v 5.1 より前</span><span class="sxs-lookup"><span data-stu-id="db443-205">Prior to App-V 5.1</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="db443-206">メッセージ数:</span><span class="sxs-lookup"><span data-stu-id="db443-206">Number of messages indicator:</span></span></strong></p>
<p><span data-ttu-id="db443-207">App-v 管理コンソールのタイトルバーで、表示待ちのメッセージの数を示すフラグアイコンの横に数字が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="db443-207">On the title bar of the App-V Management Console, a number is now displayed next to a flag icon to indicate the number of messages that are waiting to be read.</span></span></p></td>
<td align="left"><p><span data-ttu-id="db443-208">一度に1つのメッセージまたはエラーしか表示されず、表示されたメッセージの数を確認できませんでした。</span><span class="sxs-lookup"><span data-stu-id="db443-208">You could see only one message or error at a time, and you were unable to determine how many messages there were.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="db443-209">メッセージの外観:</span><span class="sxs-lookup"><span data-stu-id="db443-209">Message appearance:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="db443-210">ユーザー入力が必要なメッセージは、表示されている現在のページの上部に表示される別のダイアログボックスに表示されます。このダイアログボックスを閉じる前に返信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db443-210">Messages that require user input appear in a separate dialog box that displays on top of the current page that you were viewing, and require a response before you can dismiss them.</span></span></p></li>
<li><p><span data-ttu-id="db443-211">メッセージとエラーがリストに表示され、その下に1つが表示されます。</span><span class="sxs-lookup"><span data-stu-id="db443-211">Messages and errors appear in a list, with one beneath the other.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="db443-212">一度に1つのメッセージまたはエラーしか表示できません。</span><span class="sxs-lookup"><span data-stu-id="db443-212">You could see only one message or error at a time.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="db443-213">メッセージを消す:</span><span class="sxs-lookup"><span data-stu-id="db443-213">Dismissing messages:</span></span></strong></p>
<p><span data-ttu-id="db443-214">すべての <strong> メッセージとエラーを一度に無視するには、[すべて消去 </strong> ] リンクを使います。または、一度に1つずつ閉じます。</span><span class="sxs-lookup"><span data-stu-id="db443-214">Use the <strong>Dismiss All</strong> link to dismiss all messages and errors at one time, or dismiss them one at a time.</span></span></p></td>
<td align="left"><p><span data-ttu-id="db443-215">一度に1つのメッセージとエラーを消すことができます。</span><span class="sxs-lookup"><span data-stu-id="db443-215">You could dismiss messages and errors only one at a time.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="db443-216">本体のページが別の Url になりました</span><span class="sxs-lookup"><span data-stu-id="db443-216">Console pages are now separate URLs</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="db443-217">アプリの新バージョン-V 5.1</span><span class="sxs-lookup"><span data-stu-id="db443-217">New in App-V 5.1</span></span></th>
<th align="left"><span data-ttu-id="db443-218">App-v 5.1 より前</span><span class="sxs-lookup"><span data-stu-id="db443-218">Prior to App-V 5.1</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="db443-219">本体の各ページには異なる URL があります。これにより、特定のページをブックマークして、後ですばやくアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="db443-219">Each page in the console has a different URL, which enables you to bookmark specific pages for quick access in the future.</span></span></p>
<p><span data-ttu-id="db443-220">一部の Url に表示される番号は、特定のパッケージを示します。</span><span class="sxs-lookup"><span data-stu-id="db443-220">The number that appears in some URLs indicates the specific package.</span></span> <span data-ttu-id="db443-221">これらの番号は一意です。</span><span class="sxs-lookup"><span data-stu-id="db443-221">These numbers are unique.</span></span></p></td>
<td align="left"><p><span data-ttu-id="db443-222">すべてのコンソールページは、同じ URL 経由でアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="db443-222">All console pages are accessed through the same URL.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="db443-223">[新規]、[別の接続グループ] ページ、および [メニュー] オプション</span><span class="sxs-lookup"><span data-stu-id="db443-223">New, separate CONNECTION GROUPS page and menu option</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="db443-224">アプリの新バージョン-V 5.1</span><span class="sxs-lookup"><span data-stu-id="db443-224">New in App-V 5.1</span></span></th>
<th align="left"><span data-ttu-id="db443-225">App-v 5.1 より前</span><span class="sxs-lookup"><span data-stu-id="db443-225">Prior to App-V 5.1</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="db443-226">[接続グループ] ページは、[パッケージ] ページと同じレベルで、メインメニューの一部になります。</span><span class="sxs-lookup"><span data-stu-id="db443-226">The CONNECTION GROUPS page is now part of the main menu, at the same level as the PACKAGES page.</span></span></p></td>
<td align="left"><p><span data-ttu-id="db443-227">[接続グループ] ページを開くには、[パッケージ] ページ内を移動します。</span><span class="sxs-lookup"><span data-stu-id="db443-227">To open the CONNECTION GROUPS page, you navigate through the PACKAGES page.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="db443-228">パッケージのメニューオプションが変更されました</span><span class="sxs-lookup"><span data-stu-id="db443-228">Menu options for packages have changed</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="db443-229">アプリの新バージョン-V 5.1</span><span class="sxs-lookup"><span data-stu-id="db443-229">New in App-V 5.1</span></span></th>
<th align="left"><span data-ttu-id="db443-230">App-v 5.1 より前</span><span class="sxs-lookup"><span data-stu-id="db443-230">Prior to App-V 5.1</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="db443-231">[パッケージ] ページの下部に表示される [現在のオプション] ボタンは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="db443-231">The following options are now buttons that appear at the bottom of the PACKAGES page:</span></span></p>
<ul>
<li><p><span data-ttu-id="db443-232">追加またはアップグレード</span><span class="sxs-lookup"><span data-stu-id="db443-232">Add or Upgrade</span></span></p></li>
<li><p><span data-ttu-id="db443-233">公開</span><span class="sxs-lookup"><span data-stu-id="db443-233">Publish</span></span></p></li>
<li><p><span data-ttu-id="db443-234">発行</span><span class="sxs-lookup"><span data-stu-id="db443-234">Unpublish</span></span></p></li>
<li><p><span data-ttu-id="db443-235">Delete</span><span class="sxs-lookup"><span data-stu-id="db443-235">Delete</span></span></p></li>
</ul>
<p><span data-ttu-id="db443-236">次のオプションは、パッケージを右クリックしてドロップダウンコンテキストメニューを開くときにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="db443-236">The following options will still appear when you right-click a package to open the drop-down context menu:</span></span></p>
<ul>
<li><p><span data-ttu-id="db443-237">公開</span><span class="sxs-lookup"><span data-stu-id="db443-237">Publish</span></span></p></li>
<li><p><span data-ttu-id="db443-238">発行</span><span class="sxs-lookup"><span data-stu-id="db443-238">Unpublish</span></span></p></li>
<li><p><span data-ttu-id="db443-239">広告アクセスの編集</span><span class="sxs-lookup"><span data-stu-id="db443-239">Edit AD Access</span></span></p></li>
<li><p><span data-ttu-id="db443-240">展開構成を編集する</span><span class="sxs-lookup"><span data-stu-id="db443-240">Edit Deployment Config</span></span></p></li>
<li><p><span data-ttu-id="db443-241">展開構成を転送...</span><span class="sxs-lookup"><span data-stu-id="db443-241">Transfer deployment configuration from…</span></span></p></li>
<li><p><span data-ttu-id="db443-242">アクセスと構成を転送する...</span><span class="sxs-lookup"><span data-stu-id="db443-242">Transfer access and configuration from…</span></span></p></li>
<li><p><span data-ttu-id="db443-243">Delete</span><span class="sxs-lookup"><span data-stu-id="db443-243">Delete</span></span></p></li>
</ul>
<p><span data-ttu-id="db443-244">[削除] をクリックして <strong> </strong> パッケージを削除すると、ダイアログボックスが開き、パッケージを削除するかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="db443-244">When you click <strong>Delete</strong> to remove a package, a dialog box opens and asks you to confirm that you want to delete the package.</span></span></p></td>
<td align="left"><p><span data-ttu-id="db443-245">[ <strong> 追加] または [アップグレード] オプションは、[ </strong> パッケージ] ページの右上のボタンです。</span><span class="sxs-lookup"><span data-stu-id="db443-245">The <strong>Add or Upgrade</strong> option was a button at the top right of the PACKAGES page.</span></span></p>
<p><span data-ttu-id="db443-246">[ <strong> 発行 </strong> ]、[非公開]、および [削除] オプションは、[ <strong> </strong> <strong> </strong> パッケージ] 一覧でパッケージ名を右クリックした場合にのみ使用できました。</span><span class="sxs-lookup"><span data-stu-id="db443-246">The <strong>Publish</strong>, <strong>Unpublish</strong>, and <strong>Delete</strong> options were available only if you right-clicked a package name in the packages list.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="db443-247">次のパッケージ操作は、各パッケージの [パッケージの詳細] ページのボタンになります。</span><span class="sxs-lookup"><span data-stu-id="db443-247">The following package operations are now buttons on the package details page for each package:</span></span></p>
<ul>
<li><p><span data-ttu-id="db443-248">転送 (ドロップダウンメニューには、次のオプションがあります)。</span><span class="sxs-lookup"><span data-stu-id="db443-248">Transfer (drop-down menu with the following options):</span></span></p>
<ul>
<li><p><span data-ttu-id="db443-249">展開構成を転送...</span><span class="sxs-lookup"><span data-stu-id="db443-249">Transfer deployment configuration from…</span></span></p></li>
<li><p><span data-ttu-id="db443-250">アクセスと構成を転送する...</span><span class="sxs-lookup"><span data-stu-id="db443-250">Transfer access and configuration from…</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="db443-251">編集 (接続グループと広告アクセス)</span><span class="sxs-lookup"><span data-stu-id="db443-251">Edit (connection groups and AD Access)</span></span></p></li>
<li><p><span data-ttu-id="db443-252">発行</span><span class="sxs-lookup"><span data-stu-id="db443-252">Unpublish</span></span></p></li>
<li><p><span data-ttu-id="db443-253">Delete</span><span class="sxs-lookup"><span data-stu-id="db443-253">Delete</span></span></p></li>
<li><p><span data-ttu-id="db443-254">既定の構成を編集する</span><span class="sxs-lookup"><span data-stu-id="db443-254">Edit Default Configuration</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="db443-255">これらのパッケージオプションは、[パッケージ] 一覧でパッケージ名を右クリックした場合にのみ使用できました。</span><span class="sxs-lookup"><span data-stu-id="db443-255">These package options were available only if you right-clicked a package name in the packages list.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="db443-256">左側のウィンドウのアイコンに新しい色とテキストが設定されている</span><span class="sxs-lookup"><span data-stu-id="db443-256">Icons in left pane have new colors and text</span></span>

<span data-ttu-id="db443-257">左側のウィンドウのアイコンの色が変更され、テキストが追加され、アイコンが他の Microsoft 製品と一貫性が保たれます。</span><span class="sxs-lookup"><span data-stu-id="db443-257">The colors of the icons in the left pane have been changed, and text added, to make the icons consistent with other Microsoft products.</span></span>

### <span data-ttu-id="db443-258">概要ページが削除されました</span><span class="sxs-lookup"><span data-stu-id="db443-258">Overview page has been removed</span></span>

<span data-ttu-id="db443-259">管理コンソールの左側のウィンドウで、[概要] メニューオプションとそれに関連する概要ページが削除されました。</span><span class="sxs-lookup"><span data-stu-id="db443-259">In the left pane of the Management Console, the OVERVIEW menu option and its associated OVERVIEW page have been removed.</span></span>

### <a href="" id="bkmk-seqimprove"></a><span data-ttu-id="db443-260">Sequencer の機能強化</span><span class="sxs-lookup"><span data-stu-id="db443-260">Sequencer Improvements</span></span>

<span data-ttu-id="db443-261">App-v 5.1 Sequencer のパッケージエディターには、次のような改善が加えられました。</span><span class="sxs-lookup"><span data-stu-id="db443-261">The following improvements have been made to the package editor in the App-V 5.1 Sequencer.</span></span>

### <span data-ttu-id="db443-262">マニフェストファイルをインポートおよびエクスポートする</span><span class="sxs-lookup"><span data-stu-id="db443-262">Import and export the manifest file</span></span>

<span data-ttu-id="db443-263">AppxManifest.xml ファイルをインポートしてエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="db443-263">You can import and export the AppxManifest.xml file.</span></span> <span data-ttu-id="db443-264">マニフェストファイルをエクスポートするには、[**詳細設定**] タブを選択し、[マニフェストファイル] ボックスで [**エクスポート**] をクリックします。マニフェストファイルに変更を加えることができます。たとえば、シェルの拡張機能の削除やファイルの種類の関連付けの編集などです。</span><span class="sxs-lookup"><span data-stu-id="db443-264">To export the manifest file, select the **Advanced** tab and in the Manifest File box, click **Export...**. You can make changes to the manifest file, such as removing shell extensions or editing file type associations.</span></span>

<span data-ttu-id="db443-265">変更を加えたら、[**インポート**] をクリックし、編集したファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="db443-265">After you make your changes, click **Import...** and select the file you edited.</span></span> <span data-ttu-id="db443-266">再びインポートした後、マニフェストファイルはパッケージエディター内ですぐに更新されます。</span><span class="sxs-lookup"><span data-stu-id="db443-266">After you successfully import it back in, the manifest file is immediately updated within the package editor.</span></span>

**<span data-ttu-id="db443-267">注意</span><span class="sxs-lookup"><span data-stu-id="db443-267">Caution</span></span>**  
<span data-ttu-id="db443-268">ファイルをインポートすると、その変更は XML スキーマに対して検証されます。</span><span class="sxs-lookup"><span data-stu-id="db443-268">When you import the file, your changes are validated against the XML schema.</span></span> <span data-ttu-id="db443-269">ファイルが有効でない場合は、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="db443-269">If the file is not valid, you will receive an error.</span></span> <span data-ttu-id="db443-270">XML スキーマに対して検証されたファイルをインポートすることはできますが、その他の理由でまだ実行できない場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="db443-270">Be aware that it is possible to import a file that is validated against the XML schema, but that might still fail to run for other reasons.</span></span>



### <span data-ttu-id="db443-271">Windows 10 からオペレーティングシステムの一覧への追加</span><span class="sxs-lookup"><span data-stu-id="db443-271">Addition of Windows 10 to operating systems list</span></span>

<span data-ttu-id="db443-272">[展開] タブで、Windows 10 32 ビットと Windows 10-64 ビットがパッケージのシーケンスを行うことができるオペレーティングシステムの一覧に追加されています。</span><span class="sxs-lookup"><span data-stu-id="db443-272">In the Deployment tab, Windows 10 32-bit and Windows 10-64 bit have been added to the list of operating systems for which you can sequence a package.</span></span> <span data-ttu-id="db443-273">**任意のオペレーティングシステム**を選択した場合は、シーケンス処理されたパッケージでサポートされるオペレーティングシステムの間に Windows 10 が自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="db443-273">If you select **Any Operating System**, Windows 10 is automatically included among the operating systems that the sequenced package will support.</span></span>

### <span data-ttu-id="db443-274">仮想レジストリエディターの下部に現在のパスが表示される</span><span class="sxs-lookup"><span data-stu-id="db443-274">Current path displays at bottom of virtual registry editor</span></span>

<span data-ttu-id="db443-275">[仮想レジストリ] タブでは、現在選択されているキーを確認できるように、仮想レジストリエディターの下部にパスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="db443-275">In the Virtual Registry tab, the path now displays at the bottom of the virtual registry editor, which enables you to determine the currently selected key.</span></span> <span data-ttu-id="db443-276">以前は、現在選択されているキーを見つけるためにレジストリツリーをスクロールする必要がありました。</span><span class="sxs-lookup"><span data-stu-id="db443-276">Previously, you had to scroll through the registry tree to find the currently selected key.</span></span>

### <a href="" id="combined--find-and-replace--dialog-box-and-shortcut-keys-added-in-virtual-registry-editor"></a><span data-ttu-id="db443-277">[検索と置換] ダイアログボックスと、仮想レジストリエディターに追加されたショートカットキーの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="db443-277">Combined “find and replace” dialog box and shortcut keys added in virtual registry editor</span></span>

<span data-ttu-id="db443-278">仮想レジストリエディターでは、検索オプション (Ctrl + F) のショートカットキーが追加され、[検索] と [置換] のタスクを結合したダイアログボックスが追加され、値とデータの検索と置換を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="db443-278">In the virtual registry editor, shortcut keys have been added for the Find option (Ctrl+F), and a dialog box that combines the “find” and “replace” tasks has been added to enable you to find and replace values and data.</span></span> <span data-ttu-id="db443-279">この結合ダイアログボックスにアクセスするには、キーを選択し、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="db443-279">To access this combined dialog box, select a key and do one of the following:</span></span>

-   <span data-ttu-id="db443-280">Ctrl キーを押し**ながら H**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="db443-280">Press **Ctrl+H**</span></span>

-   <span data-ttu-id="db443-281">キーを右クリックし、[**置換**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="db443-281">Right-click a key and select **Replace**.</span></span>

-   <span data-ttu-id="db443-282">[ **View** &gt; **Virtual Registry** &gt; **Replace**の表示] を選択します。</span><span class="sxs-lookup"><span data-stu-id="db443-282">Select **View** &gt; **Virtual Registry** &gt; **Replace**.</span></span>

<span data-ttu-id="db443-283">以前は、[置換] ダイアログボックスは存在しませんでした。手動で変更を行う必要がありました。</span><span class="sxs-lookup"><span data-stu-id="db443-283">Previously, the “Replace” dialog box did not exist, and you had to make changes manually.</span></span>

### <span data-ttu-id="db443-284">レジストリキーとパッケージファイルの名前を正常に変更する</span><span class="sxs-lookup"><span data-stu-id="db443-284">Rename registry keys and package files successfully</span></span>

<span data-ttu-id="db443-285">Sequencer の問題が発生しなくても、仮想レジストリキーとファイルの名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="db443-285">You can rename virtual registry keys and files without experiencing Sequencer issues.</span></span> <span data-ttu-id="db443-286">以前は、キーの名前を変更しようとした場合、Sequencer は動作を停止しました。</span><span class="sxs-lookup"><span data-stu-id="db443-286">Previously, the Sequencer stopped working if you tried to rename a key.</span></span>

### <span data-ttu-id="db443-287">仮想レジストリキーのインポートとエクスポート</span><span class="sxs-lookup"><span data-stu-id="db443-287">Import and export virtual registry keys</span></span>

<span data-ttu-id="db443-288">仮想レジストリキーのインポートとエクスポートを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="db443-288">You can import and export virtual registry keys.</span></span> <span data-ttu-id="db443-289">キーをインポートするには、キーをインポートするノードを右クリックし、インポートするキーに移動して、[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db443-289">To import a key, right-click the node under which to import the key, navigate to the key you want to import, and then click **Import**.</span></span> <span data-ttu-id="db443-290">キーをエクスポートするには、キーを右クリックし、[**エクスポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="db443-290">To export a key, right-click the key and select **Export**.</span></span>

### <span data-ttu-id="db443-291">仮想ファイルシステムにディレクトリをインポートする</span><span class="sxs-lookup"><span data-stu-id="db443-291">Import a directory into the virtual file system</span></span>

<span data-ttu-id="db443-292">ディレクトリを VFS にインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="db443-292">You can import a directory into the VFS.</span></span> <span data-ttu-id="db443-293">ディレクトリをインポートするには、[**パッケージファイル**] タブをクリック**View**し、[ &gt; **仮想ファイルシステム** &gt; の**インポートディレクトリ**の表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db443-293">To import a directory, click the **Package Files** tab, and then click **View** &gt; **Virtual File System** &gt; **Import Directory**.</span></span> <span data-ttu-id="db443-294">既に VFS に登録されているファイルを含むディレクトリをインポートしようとすると、インポートが失敗し、説明メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="db443-294">If you try to import a directory that contains files that are already in the VFS, the import fails, and an explanatory message is displayed.</span></span> <span data-ttu-id="db443-295">App-v 5.1 より前のバージョンでは、ディレクトリをインポートできませんでした。</span><span class="sxs-lookup"><span data-stu-id="db443-295">Prior to App-V 5.1, you could not import directories.</span></span>

### <span data-ttu-id="db443-296">VFS ファイルを削除してパッケージに追加し直すことなくインポートまたはエクスポートする</span><span class="sxs-lookup"><span data-stu-id="db443-296">Import or export a VFS file without having to delete and then add it back to the package</span></span>

<span data-ttu-id="db443-297">ファイルを削除することなく、VFS からファイルをインポートまたはエクスポートして、ファイルをパッケージに戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="db443-297">You can import files to or export files from the VFS without having to delete the file and then add it back to the package.</span></span> <span data-ttu-id="db443-298">たとえば、この機能を使って、変更ログをローカルドライブにエクスポートし、外部エディターを使用してファイルを編集してから、ファイルを VFS に再インポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="db443-298">For example, you might use this feature to export a change log to a local drive, edit the file using an external editor, and then re-import the file into the VFS.</span></span>

<span data-ttu-id="db443-299">ファイルをエクスポートするには、[**パッケージファイル**] タブを選択し、VFS 内のファイルを右クリックして [**エクスポート**] をクリックし、編集を行うことができるエクスポート場所を選びます。</span><span class="sxs-lookup"><span data-stu-id="db443-299">To export a file, select the **Package Files** tab, right-click the file in the VFS, click **Export**, and choose an export location from which you can make your edits.</span></span>

<span data-ttu-id="db443-300">ファイルをインポートするには、[**パッケージファイル**] タブを選択し、エクスポートしたファイルを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="db443-300">To import a file, select the **Package Files** tab and right-click the file that you had exported.</span></span> <span data-ttu-id="db443-301">編集したファイルを参照し、[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db443-301">Browse to the file that you edited, and then click **Import**.</span></span> <span data-ttu-id="db443-302">インポートされたファイルによって、既存のファイルが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="db443-302">The imported file will overwrite the existing file.</span></span>

<span data-ttu-id="db443-303">ファイルをインポートした後、[**ファイル**の保存] をクリックしてパッケージを保存する必要があり &gt; **Save**ます。</span><span class="sxs-lookup"><span data-stu-id="db443-303">After you import a file, you must save the package by clicking **File** &gt; **Save**.</span></span>

### <span data-ttu-id="db443-304">パッケージファイルの追加のメニューが移動されました</span><span class="sxs-lookup"><span data-stu-id="db443-304">Menu for adding a package file has moved</span></span>

<span data-ttu-id="db443-305">パッケージファイルを追加するためのメニューオプションが移動されました。</span><span class="sxs-lookup"><span data-stu-id="db443-305">The menu option for adding a package file has been moved.</span></span> <span data-ttu-id="db443-306">[追加] オプションを見つけるには、[**パッケージファイル**] タブを選択し、[ **View** &gt; **仮想ファイルシステム**の表示] をクリックし &gt; **Add File**ます。</span><span class="sxs-lookup"><span data-stu-id="db443-306">To find the Add option, select the **Package Files** tab, then click **View** &gt; **Virtual File System** &gt; **Add File**.</span></span> <span data-ttu-id="db443-307">以前は、[VFS] ノードの下にあるフォルダーを右クリックし、[**ファイルの追加**] を選択しました。</span><span class="sxs-lookup"><span data-stu-id="db443-307">Previously, you right-clicked a folder under the VFS node, and chose **Add File**.</span></span>

### <span data-ttu-id="db443-308">仮想レジストリノードによって、既定でマシンとユーザーのハイブが拡張される</span><span class="sxs-lookup"><span data-stu-id="db443-308">Virtual registry node expands MACHINE and USER hives by default</span></span>

<span data-ttu-id="db443-309">仮想レジストリを開くと、コンピューターとユーザーのハイブがトップレベルのレジストリノードの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="db443-309">When you open the virtual registry, the MACHINE and USER hives are shown below the top-level REGISTRY node.</span></span> <span data-ttu-id="db443-310">以前は、[REGISTRY] ノードを展開して、その下にあるハイブを表示する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="db443-310">Previously, you had to expand the REGISTRY node to show the hives beneath.</span></span>

### <span data-ttu-id="db443-311">Browser Helper オブジェクトを有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="db443-311">Enable or disable Browser Helper Objects</span></span>

<span data-ttu-id="db443-312">ブラウザーヘルパーオブジェクトを有効または無効にするには、Sequencer のユーザーインターフェイスの [詳細設定] タブで、[ブラウザーヘルパーオブジェクトを有効にする] チェックボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="db443-312">You can enable or disable Browser Helper Objects by selecting a new check box, Enable Browser Helper Objects, on the Advanced tab of the Sequencer user interface.</span></span> <span data-ttu-id="db443-313">Browser Helper オブジェクトの場合:</span><span class="sxs-lookup"><span data-stu-id="db443-313">If Browser Helper Objects:</span></span>

-   <span data-ttu-id="db443-314">パッケージ内に存在し、有効になっている場合は、既定でチェックボックスがオンになっています。</span><span class="sxs-lookup"><span data-stu-id="db443-314">Exist in the package and are enabled, the check box is selected by default.</span></span>

-   <span data-ttu-id="db443-315">パッケージ内に存在し、無効になっている場合、このチェックボックスは既定でオフになっています。</span><span class="sxs-lookup"><span data-stu-id="db443-315">Exist in the package and are disabled, the check box is clear by default.</span></span>

-   <span data-ttu-id="db443-316">パッケージ内に存在し、1つ以上の有効な状態と1つ以上の無効な場合は、チェックボックスは既定で [不確定] に設定されます。</span><span class="sxs-lookup"><span data-stu-id="db443-316">Exist in the package, with one or more enabled and one or more disabled, the check box is set to indeterminate by default.</span></span>

-   <span data-ttu-id="db443-317">パッケージには存在しません。このチェックボックスは無効です。</span><span class="sxs-lookup"><span data-stu-id="db443-317">Do not exist in the package, the check box is disabled.</span></span>

### <a href="" id="bkmk-pkgconvimprove"></a><span data-ttu-id="db443-318">パッケージコンバーターの改善</span><span class="sxs-lookup"><span data-stu-id="db443-318">Improvements to Package Converter</span></span>

<span data-ttu-id="db443-319">これで、パッケージコンバーターを使用して、スクリプトを含む App-v 4.6 パッケージ、ソースからのレジストリ情報とスクリプトをパッケージコンバーター出力に含めることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="db443-319">You can now use the package converter to convert App-V 4.6 packages that contain scripts, and registry information and scripts from source .osd files are now included in package converter output.</span></span>

<span data-ttu-id="db443-320">例を含む詳細については、「[以前のバージョンからの app-v 5.1 への移行](migrating-to-app-v-51-from-a-previous-version.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db443-320">For more information including examples, see [Migrating to App-V 5.1 from a Previous Version](migrating-to-app-v-51-from-a-previous-version.md).</span></span>

### <a href="" id="bkmk-supmultscripts"></a><span data-ttu-id="db443-321">1つのイベントトリガーでの複数のスクリプトのサポート</span><span class="sxs-lookup"><span data-stu-id="db443-321">Support for multiple scripts on a single event trigger</span></span>

<span data-ttu-id="db443-322">App-v 5.1 は、app-v パッケージの1つのイベントトリガーで複数のスクリプトを使うことをサポートしています。これには、アプリ-V 4.6 から App-v 5.0 以降に変換するパッケージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="db443-322">App-V 5.1 supports the use of multiple scripts on a single event trigger for App-V packages, including packages that you are converting from App-V 4.6 to App-V 5.0 or later.</span></span> <span data-ttu-id="db443-323">複数のスクリプトを使用できるようにするために、App-v 5.1 は、ScriptRunner.exe という名前のスクリプト起動アプリケーションを使用します。このアプリケーションは、App-v クライアントのインストールの一部としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="db443-323">To enable the use of multiple scripts, App-V 5.1 uses a script launcher application, named ScriptRunner.exe, which is installed as part of the App-V client installation.</span></span>

<span data-ttu-id="db443-324">イベントトリガーの一覧やスクリプトを実行できるコンテキストなどの詳細については、「 [app-v 5.1 の動的構成について](about-app-v-51-dynamic-configuration.md)」のスクリプトセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="db443-324">For more information, including a list of event triggers and the context under which scripts can be run, see the Scripts section in [About App-V 5.1 Dynamic Configuration](about-app-v-51-dynamic-configuration.md).</span></span>

### <a href="" id="bkmk-hardcodepath"></a><span data-ttu-id="db443-325">インストールフォルダーへのハードコーディングされたパスは、仮想ファイルシステムのルートにリダイレクトされます</span><span class="sxs-lookup"><span data-stu-id="db443-325">Hardcoded path to installation folder is redirected to virtual file system root</span></span>

<span data-ttu-id="db443-326">パッケージを App-v 4.6 から5.1 に変換する場合、App-v 5.1 パッケージは、4.6 パッケージを作成するときに必要だったハードコードされたドライブにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="db443-326">When you convert packages from App-V 4.6 to 5.1, the App-V 5.1 package can access the hardcoded drive that you were required to use when you created 4.6 packages.</span></span> <span data-ttu-id="db443-327">ドライブ文字は、4.6 の優先順位のコンピューターでインストールドライブとして選択したドライブになります。</span><span class="sxs-lookup"><span data-stu-id="db443-327">The drive letter will be the drive you selected as the installation drive on the 4.6 sequencing machine.</span></span> <span data-ttu-id="db443-328">(既定のドライブ文字は Q:\\.)</span><span class="sxs-lookup"><span data-stu-id="db443-328">(The default drive letter is Q:\\.)</span></span>

<span data-ttu-id="db443-329">以前は、4.6 ルートフォルダーは認識されず、App-v 5.0 パッケージによってアクセスできませんでした。</span><span class="sxs-lookup"><span data-stu-id="db443-329">Previously, the 4.6 root folder was not recognized and could not be accessed by App-V 5.0 packages.</span></span> <span data-ttu-id="db443-330">App-v 5.1 パッケージでは、完全なパスを使用してハードコーディングされたファイルにアクセスしたり、プログラムによってアプリ-V 4.6 のインストールルートでファイルを列挙したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="db443-330">App-V 5.1 packages can access hardcoded files by their full path or can programmatically enumerate files under the App-V 4.6 installation root.</span></span>

<span data-ttu-id="db443-331">**技術的な詳細:** App-v 5.1 パッケージコンバーターによって、Filesystem 要素の FilesystemMetadata.xml ファイルに、App-v 4.6 インストールルートフォルダーと短いフォルダー名が保存されます。</span><span class="sxs-lookup"><span data-stu-id="db443-331">**Technical Details:** The App-V 5.1 package converter will save the App-V 4.6 installation root folder and short folder names in the FilesystemMetadata.xml file in the Filesystem element.</span></span> <span data-ttu-id="db443-332">App-v 5.1 クライアントで仮想プロセスが作成されると、アプリ-V 4.6 インストールルートから仮想ファイルシステムのルートへの要求がマップされます。</span><span class="sxs-lookup"><span data-stu-id="db443-332">When the App-V 5.1 client creates the virtual process, it will map requests from the App-V 4.6 installation root to the virtual file system root.</span></span>

## <span data-ttu-id="db443-333">MDOP 技術の入手方法</span><span class="sxs-lookup"><span data-stu-id="db443-333">How to Get MDOP Technologies</span></span>


<span data-ttu-id="db443-334">App-v は、Microsoft デスクトップ最適化パック (MDOP) の一部です。</span><span class="sxs-lookup"><span data-stu-id="db443-334">App-V is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="db443-335">MDOP は、Microsoft ソフトウェアアシュアランスの一部です。</span><span class="sxs-lookup"><span data-stu-id="db443-335">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="db443-336">Microsoft ソフトウェアアシュアランスと MDOP の入手の詳細については、「 [mdop の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db443-336">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>






## <span data-ttu-id="db443-337">関連トピック</span><span class="sxs-lookup"><span data-stu-id="db443-337">Related topics</span></span>


[<span data-ttu-id="db443-338">App-V 5.1 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="db443-338">Release Notes for App-V 5.1</span></span>](release-notes-for-app-v-51.md)









