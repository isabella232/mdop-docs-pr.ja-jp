---
title: 以前のバージョンからの移行計画
description: 以前のバージョンからの移行計画
author: dansimp
ms.assetid: 62967bf1-542f-41b0-838f-c62f3430ac73
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9b239e09da06270b30b401151cf12e817e2cf8d4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815927"
---
# <span data-ttu-id="19850-103">以前のバージョンからの移行計画</span><span class="sxs-lookup"><span data-stu-id="19850-103">Planning for Migration from Previous Versions</span></span>


<span data-ttu-id="19850-104">Microsoft Application Virtualization 4.5 以降のバージョンにアップグレードする前に、4.1 より前のバージョンをバージョン4.1 にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="19850-104">Before attempting to upgrade to Microsoft Application Virtualization4.5 or later versions, any version prior to4.1 must be upgraded to version4.1.</span></span> <span data-ttu-id="19850-105">まずクライアントをアップグレードし、次にサーバーコンポーネントをアップグレードすることを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19850-105">You should plan to upgrade your clients first, and then upgrade the server components.</span></span> <span data-ttu-id="19850-106">4.5 にアップグレードされているクライアントは、まだアップグレードされていないアプリケーション仮想化サーバーで動作し続けます。</span><span class="sxs-lookup"><span data-stu-id="19850-106">Clients that have been upgraded to4.5 will continue to work with Application Virtualization servers that have not yet been upgraded.</span></span> <span data-ttu-id="19850-107">以前のバージョンのクライアントは、4.5 にアップグレードされたサーバーではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="19850-107">Earlier versions of the client are not supported on servers that have been upgraded to4.5.</span></span> <span data-ttu-id="19850-108">システムコンポーネントのアップグレードの詳細については、「 [Application Virtualization の展開とアップグレードに関する考慮事項](application-virtualization-deployment-and-upgrade-considerations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19850-108">For more information about upgrading the system components, see [Application Virtualization Deployment and Upgrade Considerations](application-virtualization-deployment-and-upgrade-considerations.md).</span></span>

<span data-ttu-id="19850-109">移行を成功させるためには、Application Virtualization システムコンポーネントを次の順序でアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="19850-109">To help ensure a successful migration, the Application Virtualization system components should be upgraded in the following order:</span></span>

1.  **<span data-ttu-id="19850-110">Microsoft Application Virtualization クライアント。</span><span class="sxs-lookup"><span data-stu-id="19850-110">Microsoft Application Virtualization Clients.</span></span>** <span data-ttu-id="19850-111">詳細なアップグレード手順については、「 [Application Virtualization クライアントをアップグレードする方法](how-to-upgrade-the-application-virtualization-client.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19850-111">For step-by-step upgrade instructions, see [How to Upgrade the Application Virtualization Client](how-to-upgrade-the-application-virtualization-client.md).</span></span>

2.  **<span data-ttu-id="19850-112">Microsoft Application Virtualization サーバーとデータベース。</span><span class="sxs-lookup"><span data-stu-id="19850-112">Microsoft Application Virtualization Servers and Database.</span></span>** <span data-ttu-id="19850-113">詳細なアップグレード手順については、「[サーバーとシステムコンポーネントをアップグレードする方法](how-to-upgrade-the-servers-and-system-components.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19850-113">For step-by-step upgrade instructions, see [How to Upgrade the Servers and System Components](how-to-upgrade-the-servers-and-system-components.md).</span></span>

    <span data-ttu-id="19850-114">**注** Application Virtualization データベースへのサーバー共有アクセス権が複数ある場合は、データベースのアップグレード中に、それらのすべてのサーバーをオフラインにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="19850-114">**Note** If you have more than one server sharing access to the Application Virtualization database, all those servers must be taken offline while the database is being upgraded.</span></span> <span data-ttu-id="19850-115">データベースのアップグレードについては、通常のビジネス慣行に従う必要がありますが、最初にテストサーバーでデータベースのバックアップコピーを使用してデータベースのアップグレードをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="19850-115">You should follow your normal business practices for the database upgrade, but it is highly advisable that you test the database upgrade by using a backup copy of the database first on a test server.</span></span> <span data-ttu-id="19850-116">次に、最初のアップグレード用にいずれかのサーバーを選択する必要があります。これにより、データベーススキーマがアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="19850-116">Then, you should select one of the servers for the first upgrade, which will upgrade the database schema.</span></span> <span data-ttu-id="19850-117">運用データベースのアップグレードが正常に完了したら、他のサーバーをアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="19850-117">After the production database has been successfully upgraded, you can upgrade the other servers.</span></span>

     

3.  **<span data-ttu-id="19850-118">Microsoft Application Virtualization Management Web サービス。</span><span class="sxs-lookup"><span data-stu-id="19850-118">Microsoft Application Virtualization Management Web Service.</span></span>** <span data-ttu-id="19850-119">この手順は、管理 Web サービスが別のサーバー上にある場合にのみ適用されます。この場合、Web サービスをアップグレードするためにサーバーインストーラープログラムを別のサーバー上で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19850-119">This step applies only if the Management Web Service is on a separate server, which would require that you run the server installer program on that separate server to upgrade the Web service.</span></span> <span data-ttu-id="19850-120">それ以外の場合は、前のサーバーアップグレード手順によって、自動的に管理 Web サービスがアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="19850-120">Otherwise, the previous server upgrade step will automatically upgrade the Management Web Service.</span></span>

4.  **<span data-ttu-id="19850-121">Microsoft Application Virtualization 管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="19850-121">Microsoft Application Virtualization Management Console.</span></span>** <span data-ttu-id="19850-122">この手順は、管理コンソールが別のコンピューターにある場合にのみ適用されます。そのため、コンソールをアップグレードするには、別のコンピューターでサーバーインストーラープログラムを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19850-122">This step applies only if the Management Console is on a separate computer, which would require that you run the server installer program on that separate computer to upgrade the console.</span></span> <span data-ttu-id="19850-123">それ以外の場合は、前のサーバーアップグレード手順によって管理コンソールがアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="19850-123">Otherwise, the previous server upgrade step will upgrade the Management Console.</span></span>

5.  **<span data-ttu-id="19850-124">Microsoft Application Virtualization Sequencer。</span><span class="sxs-lookup"><span data-stu-id="19850-124">Microsoft Application Virtualization Sequencer.</span></span>** <span data-ttu-id="19850-125">詳細な手順については、「 [Application Virtualization Sequencer をインストールする方法](how-to-install-the-application-virtualization-sequencer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19850-125">For step-by-step instructions, see [How to Install the Application Virtualization Sequencer](how-to-install-the-application-virtualization-sequencer.md).</span></span> <span data-ttu-id="19850-126">バージョン4.2 でシーケンスされた仮想アプリケーションパッケージは、バージョン4.5 での使用のために順序を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="19850-126">Any virtual application packages sequenced in version4.2 will not have to be re-sequenced for use with version4.5.</span></span> <span data-ttu-id="19850-127">ただし、既定のアクセス制御リスト (Acl) を適用したり、Windows インストーラーファイルを生成したりする場合は、仮想パッケージを Microsoft Application Virtualization 4.5 形式にアップグレードすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="19850-127">However, you should consider upgrading the virtual packages to the Microsoft Application Virtualization4.5 format if you would like to apply default access control lists (ACLs) or generate a Windows Installer file.</span></span> <span data-ttu-id="19850-128">これは単純なプロセスであり、既存の仮想アプリケーションパッケージを開いて、4.5 Sequencer として保存するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="19850-128">This is a simple process and requires only that the existing virtual application package be opened and saved with the4.5 Sequencer.</span></span> <span data-ttu-id="19850-129">これは、Application Virtualization Sequencer コマンドラインインターフェイスを使用して自動化できます。</span><span class="sxs-lookup"><span data-stu-id="19850-129">This can be automated by using the Application Virtualization Sequencer command-line interface.</span></span>

## <a href="" id="app-v-4-6-client-package-support-"></a><span data-ttu-id="19850-130">App-v 4.6 クライアントパッケージのサポート</span><span class="sxs-lookup"><span data-stu-id="19850-130">App-V4.6 Client Package Support</span></span>


<span data-ttu-id="19850-131">以前のバージョンの App-v で作成されたパッケージを、app-v 4.6 クライアントに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="19850-131">You can deploy packages created in previous versions of App-V to App-V4.6 Clients.</span></span> <span data-ttu-id="19850-132">ただし、適切なオペレーティングシステムとチップアーキテクチャの情報が含まれるように、関連する **.osd**ファイルを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19850-132">However, you must modify the associated **.osd** file so that it includes the appropriate operating system and chip architecture information.</span></span> <span data-ttu-id="19850-133">次の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="19850-133">Use the following values.</span></span>

<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="19850-134">OS 値</span><span class="sxs-lookup"><span data-stu-id="19850-134">OS Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="19850-135">&lt;OS 値 = "Win2003TS"/&gt;</span><span class="sxs-lookup"><span data-stu-id="19850-135">&lt;OS VALUE=”Win2003TS”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="19850-136">&lt;OS 値 = "Win2003TS64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="19850-136">&lt;OS VALUE=”Win2003TS64”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="19850-137">&lt;OS 値 = "Win2008TS"/&gt;</span><span class="sxs-lookup"><span data-stu-id="19850-137">&lt;OS VALUE=”Win2008TS”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="19850-138">&lt;OS 値 = "Win2008TS64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="19850-138">&lt;OS VALUE=”Win2008TS64”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="19850-139">&lt;OS 値 = "Win2008R2TS64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="19850-139">&lt;OS VALUE=”Win2008R2TS64”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="19850-140">&lt;OS 値 = "Win7"/&gt;</span><span class="sxs-lookup"><span data-stu-id="19850-140">&lt;OS VALUE=”Win7”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="19850-141">&lt;OS 値 = "Win764"/&gt;</span><span class="sxs-lookup"><span data-stu-id="19850-141">&lt;OS VALUE=”Win764”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="19850-142">&lt;OS 値 = "WinVista"/&gt;</span><span class="sxs-lookup"><span data-stu-id="19850-142">&lt;OS VALUE=”WinVista”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="19850-143">&lt;OS 値 = "WinVista64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="19850-143">&lt;OS VALUE=”WinVista64”/&gt;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="19850-144">&lt;OS 値 = "WinXP"/&gt;</span><span class="sxs-lookup"><span data-stu-id="19850-144">&lt;OS VALUE=”WinXP”/&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="19850-145">&lt;OS 値 = "WinXP64"/&gt;</span><span class="sxs-lookup"><span data-stu-id="19850-145">&lt;OS VALUE=”WinXP64”/&gt;</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="19850-146">新しく作成された32ビットパッケージを実行するには、アプリを実行するコンピューターで、32ビットのオペレーティングシステムを実行しているコンピューター (app-v 4.6 Sequencer がインストールされているコンピューター) でアプリケーションをシーケンスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="19850-146">To run a newly created 32-bit package, you must sequence the application on a computer running a 32-bit operating system with the App-V4.6 Sequencer installed.</span></span> <span data-ttu-id="19850-147">アプリケーションをシーケンスした後、Sequencer コンソールで [**展開**] タブを選択し、必要に応じて、適切なオペレーティングシステムとチップアーキテクチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="19850-147">After you have sequenced the application, in the Sequencer console, select the **Deployment** tab and then specify the appropriate operating system and chip architecture as required.</span></span>

<span data-ttu-id="19850-148">**重要** 64ビットオペレーティングシステムを実行しているコンピューターでシーケンスされたアプリケーションは、64ビットオペレーティングシステムを実行しているコンピューターに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19850-148">**Important** Applications sequenced on a computer running a 64-bit operating system must be deployed to computers running a 64-bit operating system.</span></span> <span data-ttu-id="19850-149">App-v 4.6 Sequencer を使用して作成された新しい32ビットパッケージは、app-v 4.5 クライアントを実行しているコンピューターでは実行されません。</span><span class="sxs-lookup"><span data-stu-id="19850-149">New 32-bit packages created by using the App-V4.6 Sequencer will not run on computers running the App-V 4.5 Client.</span></span>

 

<span data-ttu-id="19850-150">新しい64ビットパッケージを App-v 4.6 クライアントで実行するには、App-v 4.6 Sequencer を実行しているコンピューターで、64ビットオペレーティングシステムを実行しているコンピューターにアプリケーションをシーケンスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="19850-150">To run new 64-bit packages on the App-V4.6 Client, you must sequence the application on a computer running the App-V4.6 Sequencer and that is running a 64-bit operating system.</span></span> <span data-ttu-id="19850-151">アプリケーションをシーケンスした後、Sequencer コンソールで [**展開**] タブを選択し、必要に応じて、適切なオペレーティングシステムとチップアーキテクチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="19850-151">After you have sequenced the application, in the Sequencer console, select the **Deployment** tab and then specify the appropriate operating system and chip architecture as required.</span></span>

<span data-ttu-id="19850-152">次の表は、さまざまなバージョンの Sequencer を使用して作成されたパッケージを実行するクライアントバージョンを示しています。</span><span class="sxs-lookup"><span data-stu-id="19850-152">The following table lists which client versions will run packages created by using the various versions of the Sequencer.</span></span>

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="19850-153">App-v 4.2 Sequencer を使用したシーケンス</span><span class="sxs-lookup"><span data-stu-id="19850-153">Sequenced by using the App-V 4.2 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="19850-154">App-v 4.5 Sequencer を使用したシーケンス</span><span class="sxs-lookup"><span data-stu-id="19850-154">Sequenced by using the App-V 4.5 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="19850-155">32ビット版のアプリを使ったシーケンス (V 4.6 Sequencer)</span><span class="sxs-lookup"><span data-stu-id="19850-155">Sequenced by using the 32-bit App-V 4.6 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="19850-156">64ビット版のアプリを使ったシーケンス (V 4.6 Sequencer)</span><span class="sxs-lookup"><span data-stu-id="19850-156">Sequenced by using the 64-bit App-V 4.6 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="19850-157">32ビット版のアプリを使ったシーケンス-V 4.6 SP1 Sequencer</span><span class="sxs-lookup"><span data-stu-id="19850-157">Sequenced by using the 32-bit App-V 4.6 SP1 Sequencer</span></span></th>
<th align="left"><span data-ttu-id="19850-158">64ビット版のアプリを使ったシーケンス-V 4.6 SP1 Sequencer</span><span class="sxs-lookup"><span data-stu-id="19850-158">Sequenced by using the 64-bit App-V 4.6 SP1 Sequencer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="19850-159">4.2 クライアント</span><span class="sxs-lookup"><span data-stu-id="19850-159">4.2 Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-160">あり</span><span class="sxs-lookup"><span data-stu-id="19850-160">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-161">×</span><span class="sxs-lookup"><span data-stu-id="19850-161">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-162">なし</span><span class="sxs-lookup"><span data-stu-id="19850-162">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-163">なし</span><span class="sxs-lookup"><span data-stu-id="19850-163">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-164">なし</span><span class="sxs-lookup"><span data-stu-id="19850-164">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-165">なし</span><span class="sxs-lookup"><span data-stu-id="19850-165">No</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="19850-166">4.5 クライアント¹</span><span class="sxs-lookup"><span data-stu-id="19850-166">4.5 Client ¹</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-167">あり</span><span class="sxs-lookup"><span data-stu-id="19850-167">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-168">可</span><span class="sxs-lookup"><span data-stu-id="19850-168">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-169">×</span><span class="sxs-lookup"><span data-stu-id="19850-169">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-170">なし</span><span class="sxs-lookup"><span data-stu-id="19850-170">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-171">なし</span><span class="sxs-lookup"><span data-stu-id="19850-171">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-172">なし</span><span class="sxs-lookup"><span data-stu-id="19850-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="19850-173">4.6 クライアント (32 ビット)</span><span class="sxs-lookup"><span data-stu-id="19850-173">4.6 Client (32-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-174">あり</span><span class="sxs-lookup"><span data-stu-id="19850-174">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-175">要</span><span class="sxs-lookup"><span data-stu-id="19850-175">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-176">可</span><span class="sxs-lookup"><span data-stu-id="19850-176">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-177">未対応</span><span class="sxs-lookup"><span data-stu-id="19850-177">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-178">あり</span><span class="sxs-lookup"><span data-stu-id="19850-178">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-179">×</span><span class="sxs-lookup"><span data-stu-id="19850-179">No</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="19850-180">4.6 クライアント (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="19850-180">4.6 Client (64-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-181">あり</span><span class="sxs-lookup"><span data-stu-id="19850-181">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-182">要</span><span class="sxs-lookup"><span data-stu-id="19850-182">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-183">要</span><span class="sxs-lookup"><span data-stu-id="19850-183">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-184">要</span><span class="sxs-lookup"><span data-stu-id="19850-184">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-185">要</span><span class="sxs-lookup"><span data-stu-id="19850-185">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-186">要</span><span class="sxs-lookup"><span data-stu-id="19850-186">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="19850-187">4.6 SP1 クライアント</span><span class="sxs-lookup"><span data-stu-id="19850-187">4.6 SP1 Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-188">あり</span><span class="sxs-lookup"><span data-stu-id="19850-188">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-189">要</span><span class="sxs-lookup"><span data-stu-id="19850-189">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-190">可</span><span class="sxs-lookup"><span data-stu-id="19850-190">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-191">未対応</span><span class="sxs-lookup"><span data-stu-id="19850-191">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-192">あり</span><span class="sxs-lookup"><span data-stu-id="19850-192">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-193">×</span><span class="sxs-lookup"><span data-stu-id="19850-193">No</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="19850-194">4.6 SP1 クライアント (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="19850-194">4.6 SP1 Client (64-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-195">あり</span><span class="sxs-lookup"><span data-stu-id="19850-195">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-196">要</span><span class="sxs-lookup"><span data-stu-id="19850-196">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-197">要</span><span class="sxs-lookup"><span data-stu-id="19850-197">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-198">要</span><span class="sxs-lookup"><span data-stu-id="19850-198">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-199">要</span><span class="sxs-lookup"><span data-stu-id="19850-199">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="19850-200">要</span><span class="sxs-lookup"><span data-stu-id="19850-200">Yes</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="19850-201">¹アプリ-v 4.5、app-v 4.5 CU1、および App-v 4.5 SP1 を含む、すべてのバージョンの App-v 4.5 クライアントに適用されます。</span><span class="sxs-lookup"><span data-stu-id="19850-201">¹Applies to all versions of the App-V4.5 Client, including App-V4.5, App-V4.5CU1 and App-V4.5 SP1.</span></span>

## <span data-ttu-id="19850-202">その他の移行に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="19850-202">Additional Migration Considerations</span></span>


<span data-ttu-id="19850-203">App-v 4.5 Sequencer の機能の1つは、Microsoft Endpoint Configuration Manager などの電子ソフトウェア配布 (ESD) システムとの仮想アプリケーションパッケージの相互運用性の制御ポイントとして、Windows Installer ファイル (.msi) を作成する機能です。</span><span class="sxs-lookup"><span data-stu-id="19850-203">One of the features of the App-V4.5 Sequencer is the ability to create Windows Installer files (.msi) as control points for virtual application package interoperability with electronic software distribution (ESD) systems such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="19850-204">以前に4.5 にアップグレードされた、アプリの仮想化用の .msi ツールを使用して作成された Windows Installer ファイルは、4.5 クライアントにはインストールできませんが、その後も4.5 にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="19850-204">Previous Windows Installer files created with the .msi tool for Application Virtualization that were installed on a App-V4.1 or4.2 Client that is subsequently upgraded to4.5 continue to work, although they cannot be installed on the4.5 Client.</span></span> <span data-ttu-id="19850-205">ただし、4.5 Sequencer でアップグレードしない限り、削除またはアップグレードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="19850-205">However, they cannot be removed or upgraded unless they are upgraded in the4.5 Sequencer.</span></span> <span data-ttu-id="19850-206">元の4.5 仮想アプリケーションパッケージは、4.5 Sequencer で開いてから、Windows Installer ファイルとして保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19850-206">The original pre-4.5 virtual application package would need to be opened in the4.5 Sequencer and then saved as a Windows Installer File.</span></span>

<span data-ttu-id="19850-207">**注** App-v 4.2 クライアントが既に4.5 にアップグレードされている場合は、スクリプトを使用して、4.5 クライアント上の4.2 パッケージを保存し、それらを管理できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="19850-207">**Note** If the App-V4.2 Client has already been upgraded to4.5, it is possible to use script as a workaround to preserve the4.2 packages on4.5 clients and allow them to be managed.</span></span> <span data-ttu-id="19850-208">このスクリプトでは、msvcp71.dll と msvcr71.dll の2つのファイルを App-v のインストールフォルダーにコピーし、レジストリキー \ [HKEY \ _LOCAL \ _MACHINE ¥¥のレジストリキーの値を設定する必要があります (例:</span><span class="sxs-lookup"><span data-stu-id="19850-208">This script must copy two files, msvcp71.dll and msvcr71.dll, to the App-V installation folder and set the following registry key values under the registry key \[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\]:</span></span>

<span data-ttu-id="19850-209">"ClientVersion" = "4.2.1.20"</span><span class="sxs-lookup"><span data-stu-id="19850-209">"ClientVersion"="4.2.1.20"</span></span>

<span data-ttu-id="19850-210">"GlobalDataDirectory" = "C:\\\\Documents and Settings\\\\All Users\\\\Documents\\\\" (グローバルに書き込み可能な場所)</span><span class="sxs-lookup"><span data-stu-id="19850-210">"GlobalDataDirectory"="C:\\\\Documents and Settings\\\\All Users\\\\Documents\\\\" (a globally writeable location)</span></span>

 

<span data-ttu-id="19850-211">App-v 4.5 Sequencer によって生成された Windows Installer ファイルは、App-v 4.6 クライアントで実行しようとすると、"このパッケージは Microsoft Application Virtualization Client 4.5 以降を必要とします" というエラーメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="19850-211">Windows Installer files generated by the App-V 4.5 Sequencer display the error message "This package requires Microsoft Application Virtualization Client 4.5 or later" when you try to run them on an App-V 4.6 Client.</span></span> <span data-ttu-id="19850-212">App-v 4.5 SP1 Sequencer または App-v 4.6 Sequencer のいずれかを使用して、古いパッケージを開き、パッケージ用の新しい .msi を生成します。</span><span class="sxs-lookup"><span data-stu-id="19850-212">Open the old package with either the App-V 4.5 SP1 Sequencer or the App-V 4.6 Sequencer and generate a new .msi for the package.</span></span>

<span data-ttu-id="19850-213">作成および保存された4.2 レポートは、サーバーが4.5 にアップグレードされると上書きされます。</span><span class="sxs-lookup"><span data-stu-id="19850-213">Any4.2 reports that were created and saved will be overwritten when the server is upgraded to4.5.</span></span> <span data-ttu-id="19850-214">これらのレポートを保持する必要がある場合は、サーバー上の SoftGrid 管理コンソールフォルダーにある SftMMC ファイルのバックアップコピーを保存し、そのコピーを使用してアップグレード中にインストールされた新しい SftMMC を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="19850-214">If you need to keep these reports, you must save a backup copy of the SftMMC.msc file located in the SoftGrid Management Console folder on the server and use that copy to replace the new SftMMC.msc that is installed during the upgrade.</span></span>

<span data-ttu-id="19850-215">以前のバージョンからのアップグレードの詳細については、「 [Microsoft Application Virtualization 4.5 へのアップグレード](https://go.microsoft.com/fwlink/?LinkId=120358)に関する FAQ (」を参照してください https://go.microsoft.com/fwlink/?LinkId=120358) 。</span><span class="sxs-lookup"><span data-stu-id="19850-215">For additional information about upgrading from previous versions, see [Upgrading to Microsoft Application Virtualization 4.5 FAQ](https://go.microsoft.com/fwlink/?LinkId=120358) (https://go.microsoft.com/fwlink/?LinkId=120358).</span></span>

## <span data-ttu-id="19850-216">関連トピック</span><span class="sxs-lookup"><span data-stu-id="19850-216">Related topics</span></span>


[<span data-ttu-id="19850-217">Application Virtualization システムの展開計画</span><span class="sxs-lookup"><span data-stu-id="19850-217">Planning for Application Virtualization System Deployment</span></span>](planning-for-application-virtualization-system-deployment.md)

 

 





