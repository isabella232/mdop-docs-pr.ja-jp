---
title: コマンド ラインを使用して MBAM サーバーをインストールする方法
description: コマンド ラインを使用して MBAM サーバーをインストールする方法
author: dansimp
ms.assetid: 6ffc6d41-a793-42c2-b997-95ba47550648
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a689a2df77300300073b2731281004feac87305f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825644"
---
# <span data-ttu-id="aec24-103">コマンド ラインを使用して MBAM サーバーをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="aec24-103">How to Use a Command Line to Install the MBAM Server</span></span>


<span data-ttu-id="aec24-104">コマンドラインを使用して、スタンドアロンまたは構成マネージャーのトポロジで MBAM サーバーをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="aec24-104">You can use a command line to install the MBAM Server with either the Stand-alone or Configuration Manager topology.</span></span> <span data-ttu-id="aec24-105">次のコマンドラインの例は、1つのサーバーに MBAM を展開するためのものであり、テスト環境でのみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aec24-105">The following command line example is for deploying MBAM on a single server, which is an architecture that should be used only in a test environment.</span></span> <span data-ttu-id="aec24-106">複数のサーバーがある運用環境に MBAM を展開する場合は、それに応じてコマンドラインを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aec24-106">You will need to change the command line accordingly when you deploy MBAM to a production environment, which should have multiple servers.</span></span>

## <span data-ttu-id="aec24-107">スタンドアロントポロジで MBAM 2.0 サーバーを展開するためのコマンドライン</span><span class="sxs-lookup"><span data-stu-id="aec24-107">Command Line for Deploying the MBAM2.0 Server with the Stand-alone Topology</span></span>


<span data-ttu-id="aec24-108">次のようなコマンドラインを使用して、MBAM サーバーをスタンドアロントポロジでインストールできます。</span><span class="sxs-lookup"><span data-stu-id="aec24-108">You can use a command line that is similar to the following to install the MBAM Server with the Stand-alone topology.</span></span>

``` syntax
MbamSetup.exe /qb /l*v MaltaServerInstall.log TOPOLOGY=0 I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 ADDLOCAL=KeyDatabase,ReportsDatabase,Reports,AdministrationMonitoringServer,SelfServiceServer,PolicyTemplate,REPORTS_USERACCOUNT=[UserDomain]\[UserName1] REPORTS_USERACCOUNTPW=[UserPwd1] COMPLIDB_SQLINSTANCE=%computername% RECOVERYANDHWDB_SQLINSTANCE=%computername% SRS_INSTANCENAME=%computername% ADMINANDMON_WEBSITE_PORT=83 WEBSITE_PORT=83
```

<span data-ttu-id="aec24-109">次の表では、スタンドアロントポロジで MBAM サーバーを展開するためのコマンドラインパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aec24-109">The following table describes the command line parameters for deploying the MBAM Server with the Stand-alone topology.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="aec24-110">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aec24-110">Parameter</span></span></th>
<th align="left"><span data-ttu-id="aec24-111">パラメーター値</span><span class="sxs-lookup"><span data-stu-id="aec24-111">Parameter Value</span></span></th>
<th align="left"><span data-ttu-id="aec24-112">説明</span><span class="sxs-lookup"><span data-stu-id="aec24-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aec24-113">トポロジ</span><span class="sxs-lookup"><span data-stu-id="aec24-113">TOPOLOGY</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-114">0</span><span class="sxs-lookup"><span data-stu-id="aec24-114">0</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-115">0–スタンドアロントポロジ</span><span class="sxs-lookup"><span data-stu-id="aec24-115">0 – Stand-alone topology</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aec24-116">I_ACCEPT_ENDUSER_LICENSE_AGREEMENT</span><span class="sxs-lookup"><span data-stu-id="aec24-116">I_ACCEPT_ENDUSER_LICENSE_AGREEMENT</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-117">付き</span><span class="sxs-lookup"><span data-stu-id="aec24-117">01</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-118">0–ライセンス agreement1 に同意しない–使用許諾契約に同意してください。</span><span class="sxs-lookup"><span data-stu-id="aec24-118">0 – do not accept the license agreement1 – accept the license agreement</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aec24-119">ADDLOCAL</span><span class="sxs-lookup"><span data-stu-id="aec24-119">ADDLOCAL</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="aec24-120">サーバーにインストールされる機能</span><span class="sxs-lookup"><span data-stu-id="aec24-120">Features to be installed on the Server</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="aec24-121">KeyDatabase</span><span class="sxs-lookup"><span data-stu-id="aec24-121">KeyDatabase</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-122">回復用データベース</span><span class="sxs-lookup"><span data-stu-id="aec24-122">Recovery Database</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="aec24-123">レポートデータベース</span><span class="sxs-lookup"><span data-stu-id="aec24-123">ReportsDatabase</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-124">コンプライアンスと監査レポートデータベース</span><span class="sxs-lookup"><span data-stu-id="aec24-124">Compliance and Audit Reports Database</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="aec24-125">レポート</span><span class="sxs-lookup"><span data-stu-id="aec24-125">Reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-126">コンプライアンスと監査レポート</span><span class="sxs-lookup"><span data-stu-id="aec24-126">Compliance and Audit Reports</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="aec24-127">管理 Monitoringserver</span><span class="sxs-lookup"><span data-stu-id="aec24-127">AdministrationMonitoringServer</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-128">管理と監視の web サイト</span><span class="sxs-lookup"><span data-stu-id="aec24-128">Administration and Monitoring website</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="aec24-129">SelfServiceServer</span><span class="sxs-lookup"><span data-stu-id="aec24-129">SelfServiceServer</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-130">セルフサービスポータル</span><span class="sxs-lookup"><span data-stu-id="aec24-130">Self-Service Portal</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="aec24-131">PolicyTemplate</span><span class="sxs-lookup"><span data-stu-id="aec24-131">PolicyTemplate</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-132">MBAM グループポリシーテンプレート</span><span class="sxs-lookup"><span data-stu-id="aec24-132">MBAM Group Policy template</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aec24-133">REPORTS_USERACCOUNT</span><span class="sxs-lookup"><span data-stu-id="aec24-133">REPORTS_USERACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-134">[UserDomain][UserName1]</span><span class="sxs-lookup"><span data-stu-id="aec24-134">[UserDomain][UserName1]</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-135">コンプライアンスと監査データベースにアクセスする Reporting Services サービスアカウントのドメインとユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="aec24-135">Domain and user account of the Reporting Services service account that will access the Compliance and Audit database</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aec24-136">REPORTS_USERACCOUNTPW</span><span class="sxs-lookup"><span data-stu-id="aec24-136">REPORTS_USERACCOUNTPW</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-137">[UserPwd1]</span><span class="sxs-lookup"><span data-stu-id="aec24-137">[UserPwd1]</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-138">コンプライアンスと監査データベースにアクセスする Reporting Services サービスアカウントのパスワード</span><span class="sxs-lookup"><span data-stu-id="aec24-138">Password of the Reporting Services service account that will access the Compliance and Audit database</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aec24-139">COMPLIDB_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="aec24-139">COMPLIDB_SQLINSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-140">名</span><span class="sxs-lookup"><span data-stu-id="aec24-140">%computername%</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-141">コンプライアンスおよび監査データベースの SQL Server インスタンス名– <strong> % computername% </strong> をコンピューター名で置き換えます</span><span class="sxs-lookup"><span data-stu-id="aec24-141">SQL Server instance name for the Compliance and Audit Database – replace <strong>%computername%</strong> with the computer name</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aec24-142">RECOVERYANDHWDB_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="aec24-142">RECOVERYANDHWDB_SQLINSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-143">名</span><span class="sxs-lookup"><span data-stu-id="aec24-143">%computername%</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-144">回復データベースの SQL Server インスタンス名– <strong> % computername% </strong> をコンピューター名で置き換えます</span><span class="sxs-lookup"><span data-stu-id="aec24-144">SQL Server instance name for the Recovery Database – replace <strong>%computername%</strong> with the computer name</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aec24-145">SRS_INSTANCENAME</span><span class="sxs-lookup"><span data-stu-id="aec24-145">SRS_INSTANCENAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-146">名</span><span class="sxs-lookup"><span data-stu-id="aec24-146">%computername%</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-147">コンプライアンスと監査レポートがインストールされる SQL Server Reporting Server インスタンス– <strong> % computername% </strong> をコンピューター名で置き換えます</span><span class="sxs-lookup"><span data-stu-id="aec24-147">SQL Server Reporting Server instance where the Compliance and Audit reports will be installed – replace <strong>%computername%</strong> with the computer name</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aec24-148">ADMINANDMON_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="aec24-148">ADMINANDMON_WEBSITE_PORT</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-149">83</span><span class="sxs-lookup"><span data-stu-id="aec24-149">83</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-150">管理と監視の web サイトのポート"83" は一例にすぎません</span><span class="sxs-lookup"><span data-stu-id="aec24-150">Port for the Administration and Monitoring website; “83” is only an example</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aec24-151">WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="aec24-151">WEBSITE_PORT</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-152">83</span><span class="sxs-lookup"><span data-stu-id="aec24-152">83</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-153">セルフサービスポータル web サイトのポート。"83" は一例にすぎません</span><span class="sxs-lookup"><span data-stu-id="aec24-153">Port for the Self-Service Portal website; “83” is only an example</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="aec24-154">Configuration Manager トポロジを使用して MBAM 2.0 サーバーを展開するためのコマンドライン</span><span class="sxs-lookup"><span data-stu-id="aec24-154">Command Line for Deploying the MBAM2.0 Server with the Configuration Manager Topology</span></span>


<span data-ttu-id="aec24-155">Configuration Manager トポロジを使用して MBAM サーバーをインストールするには、次のようなコマンドラインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="aec24-155">You can use a command line that is similar to the following to install the MBAM Server with the Configuration Manager topology.</span></span>

``` syntax
MbamSetup.exe /qn /l*v MaltaServerInstall.log I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 TOPOLOGY=1 COMPLIDB_SQLINSTANCE=%computername% RECOVERYANDHWDB_SQLINSTANCE=%computername% SRS_INSTANCENAME=%computername% REPORTS_USERACCOUNT=[UserDomain]\[UserName] REPORTS_USERACCOUNTPW=[UserPwd] ADMINANDMON_WEBSITE_PORT=83 WEBSITE_PORT=83
```

<span data-ttu-id="aec24-156">次の表では、Configuration Manager トポロジを持つ MBAM 2.0 サーバーをインストールするためのコマンドラインパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aec24-156">The following table describes the command line parameters for installing the MBAM2.0 Server with the Configuration Manager topology.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="aec24-157">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aec24-157">Parameter</span></span></th>
<th align="left"><span data-ttu-id="aec24-158">パラメーター値</span><span class="sxs-lookup"><span data-stu-id="aec24-158">Parameter Value</span></span></th>
<th align="left"><span data-ttu-id="aec24-159">説明</span><span class="sxs-lookup"><span data-stu-id="aec24-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aec24-160">トポロジ</span><span class="sxs-lookup"><span data-stu-id="aec24-160">TOPOLOGY</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-161">件</span><span class="sxs-lookup"><span data-stu-id="aec24-161">1</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-162">1– Configuration Manager のトポロジ</span><span class="sxs-lookup"><span data-stu-id="aec24-162">1 – Configuration Manager topology</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aec24-163">I_ACCEPT_ENDUSER_LICENSE_AGREEMENT</span><span class="sxs-lookup"><span data-stu-id="aec24-163">I_ACCEPT_ENDUSER_LICENSE_AGREEMENT</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-164">付き</span><span class="sxs-lookup"><span data-stu-id="aec24-164">01</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-165">0–ライセンス agreement1 に同意しない–使用許諾契約に同意してください。</span><span class="sxs-lookup"><span data-stu-id="aec24-165">0 – do not accept the license agreement1 – accept the license agreement</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aec24-166">COMPLIDB_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="aec24-166">COMPLIDB_SQLINSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-167">名</span><span class="sxs-lookup"><span data-stu-id="aec24-167">%computername%</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-168">監査データベースの SQL Server インスタンス名– <strong> % computername% </strong> をコンピューター名で置き換えます</span><span class="sxs-lookup"><span data-stu-id="aec24-168">SQL Server instance name for the Audit Database – replace <strong>%computername%</strong> with the computer name</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aec24-169">RECOVERYANDHWDB_SQLINSTANCE</span><span class="sxs-lookup"><span data-stu-id="aec24-169">RECOVERYANDHWDB_SQLINSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-170">名</span><span class="sxs-lookup"><span data-stu-id="aec24-170">%computername%</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-171">回復データベースの SQL Server インスタンス名- <strong> % computername% </strong> をコンピューター名で置き換えます</span><span class="sxs-lookup"><span data-stu-id="aec24-171">SQL Server instance name for the Recovery Database - replace <strong>%computername%</strong> with the computer name</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aec24-172">SRS_INSTANCENAME</span><span class="sxs-lookup"><span data-stu-id="aec24-172">SRS_INSTANCENAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-173">名</span><span class="sxs-lookup"><span data-stu-id="aec24-173">%computername%</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-174">監査レポートがインストールされる SQL Server Reporting Server インスタンス–% computername% をコンピューター名で置き換えます</span><span class="sxs-lookup"><span data-stu-id="aec24-174">SQL Server Reporting Server instance where the Audit reports will be installed – replace %computername% with the computer name</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aec24-175">REPORTS_USERACCOUNT</span><span class="sxs-lookup"><span data-stu-id="aec24-175">REPORTS_USERACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-176">[UserDomain][UserName1]</span><span class="sxs-lookup"><span data-stu-id="aec24-176">[UserDomain][UserName1]</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-177">コンプライアンスと監査データベースにアクセスする Reporting Services サービスアカウントのドメインとユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="aec24-177">Domain and user account of the Reporting Services service account that will access the Compliance and Audit database</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aec24-178">REPORTS_USERACCOUNTPW</span><span class="sxs-lookup"><span data-stu-id="aec24-178">REPORTS_USERACCOUNTPW</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-179">[UserPwd1]</span><span class="sxs-lookup"><span data-stu-id="aec24-179">[UserPwd1]</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-180">コンプライアンスと監査データベースにアクセスする Reporting Services サービスアカウントのパスワード</span><span class="sxs-lookup"><span data-stu-id="aec24-180">Password of the Reporting Services service account that will access the Compliance and Audit database</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aec24-181">ADMINANDMON_WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="aec24-181">ADMINANDMON_WEBSITE_PORT</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-182">83</span><span class="sxs-lookup"><span data-stu-id="aec24-182">83</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-183">管理と監視の web サイトのポート"83" は一例にすぎません</span><span class="sxs-lookup"><span data-stu-id="aec24-183">Port for the Administration and Monitoring website; “83” is only an example</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aec24-184">WEBSITE_PORT</span><span class="sxs-lookup"><span data-stu-id="aec24-184">WEBSITE_PORT</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-185">83</span><span class="sxs-lookup"><span data-stu-id="aec24-185">83</span></span></p></td>
<td align="left"><p><span data-ttu-id="aec24-186">セルフサービスポータル web サイトのポート。"83" は一例にすぎません</span><span class="sxs-lookup"><span data-stu-id="aec24-186">Port for the Self-Service Portal website; “83” is only an example</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="aec24-187">関連トピック</span><span class="sxs-lookup"><span data-stu-id="aec24-187">Related topics</span></span>


[<span data-ttu-id="aec24-188">MBAM 2.0 サーバー インフラストラクチャの展開</span><span class="sxs-lookup"><span data-stu-id="aec24-188">Deploying the MBAM 2.0 Server Infrastructure</span></span>](deploying-the-mbam-20-server-infrastructure-mbam-2.md)

 

 





