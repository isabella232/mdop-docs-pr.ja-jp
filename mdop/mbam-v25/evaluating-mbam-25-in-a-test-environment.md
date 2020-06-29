---
title: テスト環境での MBAM 2.5 の評価
description: テスト環境での MBAM 2.5 の評価
author: dansimp
ms.assetid: 72959b7a-e55f-4797-91b3-5be23c8c2844
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0d7ba8a62f5ddecf85fe56e04fc16a6bae374ba9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823154"
---
# <span data-ttu-id="8ead2-103">テスト環境での MBAM 2.5 の評価</span><span class="sxs-lookup"><span data-stu-id="8ead2-103">Evaluating MBAM 2.5 in a Test Environment</span></span>


<span data-ttu-id="8ead2-104">このトピックでは、単体または System Center Configuration Manager の統合トポロジで、Microsoft BitLocker の管理と監視 (MBAM) 2.5 を評価するためにテスト環境をセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-104">This topic describes how you can set up a test environment to evaluate Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 in the Stand-alone or System Center Configuration Manager Integration topology.</span></span>

## <span data-ttu-id="8ead2-105">スタンドアロントポロジを使用して MBAM 2.5 を評価する</span><span class="sxs-lookup"><span data-stu-id="8ead2-105">Evaluating MBAM 2.5 by using the Stand-alone topology</span></span>


<span data-ttu-id="8ead2-106">スタンドアロントポロジを使用して MBAM を評価するには、次の表の情報を使用して MBAM サーバーソフトウェアをインストールし、テスト環境で MBAM サーバー機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-106">To evaluate MBAM by using the Stand-alone topology, use the information in the following tables to install the MBAM Server software, and then configure the MBAM Server features in your test environment.</span></span>

**<span data-ttu-id="8ead2-107">スタンドアロントポロジを使用して MBAM 2.5 を評価するには</span><span class="sxs-lookup"><span data-stu-id="8ead2-107">To evaluate MBAM 2.5 by using the Stand-alone topology</span></span>**

1. <span data-ttu-id="8ead2-108">MBAM をインストールする前に、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8ead2-108">Before installing MBAM, do the following:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="8ead2-109">タスク</span><span class="sxs-lookup"><span data-stu-id="8ead2-109">Task</span></span></th>
   <th align="left"><span data-ttu-id="8ead2-110">手順を表示する場所</span><span class="sxs-lookup"><span data-stu-id="8ead2-110">Where to get instructions</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="8ead2-111">すべての必須ソフトウェアがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-111">Ensure that you have installed all of the prerequisite software.</span></span></p></td>
   <td align="left"><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="8ead2-112">スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件</span><span class="sxs-lookup"><span data-stu-id="8ead2-112">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="8ead2-113">必要なハードウェア、RAM、その他の仕様を確認します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-113">Check the required hardware, RAM, and other specifications.</span></span></p></td>
   <td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="8ead2-114">MBAM 2.5 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="8ead2-114">MBAM 2.5 Supported Configurations</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="8ead2-115">コマンドレットを使用して MBAM を構成する場合は、Windows PowerShell を使用するための前提条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-115">Review the prerequisites for using Windows PowerShell if you plan to use the cmdlets to configure MBAM.</span></span></p></td>
   <td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"><span data-ttu-id="8ead2-116">Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="8ead2-116">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="8ead2-117">MBAM サーバーソフトウェアをインストールし、必要な機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-117">Install the MBAM Server software, and then configure the features you want.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="8ead2-118">タスク</span><span class="sxs-lookup"><span data-stu-id="8ead2-118">Task</span></span></th>
   <th align="left"><span data-ttu-id="8ead2-119">手順を表示する場所</span><span class="sxs-lookup"><span data-stu-id="8ead2-119">Where to get instructions</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="8ead2-120">Mbam サーバー機能を構成する各サーバーに MBAM サーバーソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8ead2-120">Install the MBAM Server software on each server where you want to configure an MBAM Server feature.</span></span></p></td>
   <td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="8ead2-121">MBAM 2.5 サーバー ソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="8ead2-121">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="8ead2-122">コンプライアンスデータベースと監査データベース、および回復データベースを構成します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-122">Configure the Compliance and Audit Database and the Recovery Database.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)"><span data-ttu-id="8ead2-123">MBAM 2.5 データベースを構成する方法</span><span class="sxs-lookup"><span data-stu-id="8ead2-123">How to Configure the MBAM 2.5 Databases</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="8ead2-124">レポート機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-124">Configure the Reports feature.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)"><span data-ttu-id="8ead2-125">MBAM 2.5 レポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="8ead2-125">How to Configure the MBAM 2.5 Reports</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="8ead2-126">Web アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-126">Configure the web applications.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)"><span data-ttu-id="8ead2-127">MBAM 2.5 Web アプリケーションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="8ead2-127">How to Configure the MBAM 2.5 Web Applications</span></span></a></p></td>
   </tr>
   </tbody>
   </table>



3. <span data-ttu-id="8ead2-128">クライアントコンピューターで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8ead2-128">On a client computer, do the following:</span></span>

   1.  <span data-ttu-id="8ead2-129">クライアントコンピューターに MBAM クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8ead2-129">Install the MBAM Client on a client computer.</span></span>

   2.  <span data-ttu-id="8ead2-130">コンピューターに MBAM グループポリシーオブジェクト (Gpo) を適用します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-130">Apply the MBAM Group Policy Objects (GPOs) to the computer.</span></span>

   3.  <span data-ttu-id="8ead2-131">次のレジストリキーを設定して、MBAM クライアントで、一定の間隔ですばやく起動するように強制します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-131">Set the following registry keys to force the MBAM Client to wake up faster and at regular intervals:</span></span>

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement
       "ClientWakeupFrequency"=dword:00000001
       "StatusReportingFrequency"=dword:00000001
       ```

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM]
       "NoStartupDelay"=dword:00000001
       ```

       **<span data-ttu-id="8ead2-132">注</span><span class="sxs-lookup"><span data-stu-id="8ead2-132">Note</span></span>**  
       <span data-ttu-id="8ead2-133">これらのキーは、MBAM クライアントを毎分起動するため、テスト環境でのみ使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8ead2-133">Because these keys wake up the MBAM Client every minute, we recommend that you use these registry key settings only in a test environment.</span></span>



   4.  <span data-ttu-id="8ead2-134">**BitLocker 管理クライアントサービス**を再起動します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-134">Restart the **BitLocker Management Client Service**.</span></span>

## <span data-ttu-id="8ead2-135">System Center 2012 Configuration Manager の統合トポロジを使用した MBAM 2.5 の評価</span><span class="sxs-lookup"><span data-stu-id="8ead2-135">Evaluating MBAM 2.5 by using the System Center 2012 Configuration Manager Integration topology</span></span>


<span data-ttu-id="8ead2-136">Configuration Manager の統合トポロジを使用して MBAM を評価するには、次の表の情報を使用して MBAM サーバーソフトウェアをインストールし、テスト環境で MBAM サーバー機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-136">To evaluate MBAM by using the Configuration Manager Integration topology, use the information in the following tables to install the MBAM Server software, and then configure the MBAM Server features in your test environment.</span></span> <span data-ttu-id="8ead2-137">クライアントコンピューターに MBAM クライアントをインストールした後、MBAM クライアントでコンピューターの状態を [MBAM] にすばやく報告させる追加の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-137">After installing the MBAM Client on a client computer, you will complete additional steps to force the MBAM Client to report the computer’s status to MBAM more quickly.</span></span>

**<span data-ttu-id="8ead2-138">System Center 2012 Configuration Manager の統合トポロジを使用して MBAM 2.5 を評価するには</span><span class="sxs-lookup"><span data-stu-id="8ead2-138">To evaluate MBAM 2.5 by using the System Center 2012 Configuration Manager Integration topology</span></span>**

1. <span data-ttu-id="8ead2-139">MBAM をインストールする前に、必須ソフトウェアとサポートされている構成を確認してください。</span><span class="sxs-lookup"><span data-stu-id="8ead2-139">Before installing MBAM, review the prerequisite software and supported configuration.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="8ead2-140">タスク</span><span class="sxs-lookup"><span data-stu-id="8ead2-140">Task</span></span></th>
   <th align="left"><span data-ttu-id="8ead2-141">手順を表示する場所</span><span class="sxs-lookup"><span data-stu-id="8ead2-141">Where to get instructions</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="8ead2-142">すべての必須ソフトウェアがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-142">Ensure that you have installed all of the prerequisite software.</span></span></p></td>
   <td align="left"><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="8ead2-143">スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件</span><span class="sxs-lookup"><span data-stu-id="8ead2-143">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p>
   <p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="8ead2-144">Configuration Manager 統合トポロジのみに適用される MBAM 2.5 サーバー前提条件</span><span class="sxs-lookup"><span data-stu-id="8ead2-144">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="8ead2-145">必要なハードウェア、RAM、その他の仕様を確認します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-145">Check the required hardware, RAM, and other specifications.</span></span></p></td>
   <td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="8ead2-146">MBAM 2.5 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="8ead2-146">MBAM 2.5 Supported Configurations</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="8ead2-147">コマンドレットを使用して MBAM を構成する場合は、Windows PowerShell を使用するための前提条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-147">Review the prerequisites for using Windows PowerShell if you plan to use the cmdlets to configure MBAM.</span></span></p></td>
   <td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"><span data-ttu-id="8ead2-148">Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="8ead2-148">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="8ead2-149">.Mof ファイルを作成または編集します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-149">Create or edit the .mof files.</span></span></p></td>
   <td align="left"><p><a href="edit-the-configurationmof-file-mbam-25.md" data-raw-source="[Edit the Configuration.mof File](edit-the-configurationmof-file-mbam-25.md)"><span data-ttu-id="8ead2-150">Configuration.mof ファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="8ead2-150">Edit the Configuration.mof File</span></span></a></p>
   <p><a href="create-or-edit-the-sms-defmof-file-mbam-25.md" data-raw-source="[Create or Edit the Sms_def.mof File](create-or-edit-the-sms-defmof-file-mbam-25.md)"><span data-ttu-id="8ead2-151">Sms_def.mof ファイルを作成または編集する</span><span class="sxs-lookup"><span data-stu-id="8ead2-151">Create or Edit the Sms_def.mof File</span></span></a></p></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="8ead2-152">MBAM サーバーソフトウェアをインストールし、必要な機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-152">Install the MBAM Server software, and then configure the features you want.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="8ead2-153">タスク</span><span class="sxs-lookup"><span data-stu-id="8ead2-153">Task</span></span></th>
   <th align="left"><span data-ttu-id="8ead2-154">手順を表示する場所</span><span class="sxs-lookup"><span data-stu-id="8ead2-154">Where to get instructions</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="8ead2-155">Mbam サーバー機能を構成する各サーバーに MBAM サーバーソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8ead2-155">Install the MBAM Server software on each server where you want to configure an MBAM Server feature.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="8ead2-156">注</span><span class="sxs-lookup"><span data-stu-id="8ead2-156">Note</span></span></strong><br/><p><span data-ttu-id="8ead2-157">Windows PowerShell またはエクスポートされたデータ層アプリケーション (DAC) パッケージを使用して、リモートの SQL Server コンピューターにデータベースをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="8ead2-157">You can install the databases to a remote SQL Server computer by using Windows PowerShell or an exported data-tier application (DAC) package.</span></span> <span data-ttu-id="8ead2-158">DAC パッケージの詳細については、「 <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)"> データ層アプリケーション」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="8ead2-158">For more information about DAC packages, see <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)">Data-tier Applications</a>.</span></span></p>
   </div>
   <div>

   </div></td>
   <td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="8ead2-159">MBAM 2.5 サーバー ソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="8ead2-159">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="8ead2-160">コンプライアンスデータベースと監査データベース、および回復データベースを構成します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-160">Configure the Compliance and Audit Database and the Recovery Database.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)"><span data-ttu-id="8ead2-161">MBAM 2.5 データベースを構成する方法</span><span class="sxs-lookup"><span data-stu-id="8ead2-161">How to Configure the MBAM 2.5 Databases</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="8ead2-162">レポート機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-162">Configure the Reports feature.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)"><span data-ttu-id="8ead2-163">MBAM 2.5 レポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="8ead2-163">How to Configure the MBAM 2.5 Reports</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="8ead2-164">Web アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-164">Configure the web applications.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)"><span data-ttu-id="8ead2-165">MBAM 2.5 Web アプリケーションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="8ead2-165">How to Configure the MBAM 2.5 Web Applications</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="8ead2-166">Configuration Manager オブジェクトをインストールするように System Center Configuration Manager を構成します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-166">Configure the System Center Configuration Manager to install the Configuration Manager objects.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md" data-raw-source="[How to Configure the MBAM 2.5 System Center Configuration Manager Integration](how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md)"><span data-ttu-id="8ead2-167">MBAM 2.5 System Center Configuration Manager 統合を構成する方法</span><span class="sxs-lookup"><span data-stu-id="8ead2-167">How to Configure the MBAM 2.5 System Center Configuration Manager Integration</span></span></a></p></td>
   </tr>
   </tbody>
   </table>



3. <span data-ttu-id="8ead2-168">クライアントコンピューターで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8ead2-168">On a client computer, do the following:</span></span>

   1.  <span data-ttu-id="8ead2-169">MBAM クライアントと Configuration Manager クライアントをクライアントコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="8ead2-169">Install the MBAM Client and the Configuration Manager Client on a client computer.</span></span>

   2.  <span data-ttu-id="8ead2-170">MBAM グループポリシーオブジェクトをコンピューターに適用します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-170">Apply the MBAM Group Policy Objects to the computer.</span></span>

   3.  <span data-ttu-id="8ead2-171">次のレジストリキーを設定して、MBAM クライアントで、一定の間隔ですばやく起動するように強制します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-171">Set the following registry keys to force the MBAM Client to wake up faster and at regular intervals:</span></span>

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement
       "ClientWakeupFrequency"=dword:00000001
       "StatusReportingFrequency"=dword:00000001
       ```

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM]
       "NoStartupDelay"=dword:00000001
       ```

       **<span data-ttu-id="8ead2-172">注</span><span class="sxs-lookup"><span data-stu-id="8ead2-172">Note</span></span>**  
       <span data-ttu-id="8ead2-173">これらのキーは、MBAM クライアントを毎分起動するため、テスト環境でのみ使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8ead2-173">Because these keys wake up the MBAM Client every minute, we recommend that you use these registry key settings only in a test environment.</span></span>



   4.  <span data-ttu-id="8ead2-174">**BitLocker 管理クライアントサービス**を再起動します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-174">Restart the **BitLocker Management Client Service**.</span></span>

   5.  <span data-ttu-id="8ead2-175">コントロールパネルで [**構成マネージャー**] を開き、[**操作**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ead2-175">In Control Panel, open **Configuration Manager**, and then click the **Actions** tab.</span></span>

   6.  <span data-ttu-id="8ead2-176">[**ハードウェアインベントリサイクル**] を選択し、[**今すぐ実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ead2-176">Select **Hardware Inventory Cycle**, and then click **Run Now**.</span></span> <span data-ttu-id="8ead2-177">この手順では、.mof ファイルにインポートした新しいクラスを使ってハードウェアインベントリを実行し、そのデータを Configuration Manager サーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-177">This step runs the hardware inventory by using the new classes that you imported to your .mof files, and then sends the data to the Configuration Manager server.</span></span>

   7.  <span data-ttu-id="8ead2-178">[**コンピューターポリシーの取得 & 評価サイクル**] を選択し、[**今すぐ実行**] をクリックして、そのクライアントコンピューターに関連するグループポリシーオブジェクトを適用します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-178">Select **Machine Policy Retrieval & Evaluation Cycle**, and then click **Run Now** to apply the Group Policy Objects that are relevant to that client computer.</span></span>



4. <span data-ttu-id="8ead2-179">Configuration Manager コンソールで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8ead2-179">In the Configuration Manager console, do the following:</span></span>

   1.  <span data-ttu-id="8ead2-180">ナビゲーションウィンドウで、[ **Mbam サポートされているコンピューター**] を右クリックし、[**メンバーシップの更新**] をクリックし、[**はい**] をクリックして、クライアントコンピューターがそのメンバーシップを直ちに報告するように強制します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-180">In the navigation pane, right-click **MBAM Supported Computers**, click **Update Membership**, and then click **Yes** to force the client computer to report its membership immediately.</span></span>

   2.  <span data-ttu-id="8ead2-181">ナビゲーションウィンドウで、[ **Mbam サポートされているコンピューター** ] をクリックして、クライアントコンピューターがコレクションに表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-181">In the navigation pane, click **MBAM Supported Computers** to verify that the client computer appears in the collection.</span></span>

5. <span data-ttu-id="8ead2-182">クライアントコンピューターのコントロールパネルで、もう一度**Configuration Manager**を開き、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8ead2-182">On the client computer, in Control Panel, reopen **Configuration Manager** again, and do the following:</span></span>

   1.  <span data-ttu-id="8ead2-183">[**操作**] タブをクリックし、[マシンポリシーの取得] を再実行して、**評価サイクル &** します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-183">Click the **Actions** tab, and then rerun **Machine Policy Retrieval & Evaluation Cycle**.</span></span>

   2.  <span data-ttu-id="8ead2-184">[**構成**] タブをクリックして、BitLocker ベースラインを選択し、[**評価**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ead2-184">Click the **Configurations** tab, select the BitLocker baseline, and then click **Evaluate**.</span></span>

6. <span data-ttu-id="8ead2-185">Configuration Manager コンソールで、[エンタープライズコンプライアンスレポート] にクライアントコンピューターが表示されていることを確認します。次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8ead2-185">In the Configuration Manager console, verify that the client computer appears on the Enterprise Compliance Report: as follows:</span></span>

   1.  <span data-ttu-id="8ead2-186">ナビゲーションウィンドウで、[**監視**] ワークスペースを選択します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-186">In the navigation pane, select the **Monitoring** workspace.</span></span>

   2.  <span data-ttu-id="8ead2-187">コンソールツリーで、[**概要** &gt; **レポート** &gt; **レポート** &gt; **mbam**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-187">In the console tree, expand **Overview** &gt; **Reporting** &gt; **Reports** &gt; **MBAM**.</span></span>

   3.  <span data-ttu-id="8ead2-188">レポートを表示する言語を表すフォルダーを選択し、[結果] ウィンドウでレポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-188">Select the folder that represents the language in which you want to view reports, and then select the report in the results pane.</span></span>

## <span data-ttu-id="8ead2-189">System Center Configuration Manager 2007 の統合トポロジを使用して MBAM 2.5 を評価する</span><span class="sxs-lookup"><span data-stu-id="8ead2-189">Evaluating MBAM 2.5 by using the System Center Configuration Manager 2007 Integration topology</span></span>


<span data-ttu-id="8ead2-190">Configuration Manager の統合トポロジを使用して MBAM を評価するには、同じ手順に従って、実稼働環境での使用時に、テスト環境に MBAM をインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-190">To evaluate MBAM by using the Configuration Manager Integration topology, follow the same steps to install and configure MBAM in your test environment as you use in a production environment.</span></span> <span data-ttu-id="8ead2-191">クライアントコンピューターに MBAM クライアントをインストールした後は、このトピックの追加の手順を実行して、MBAM クライアントがコンピューターの状態を MBAM に簡単に報告できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8ead2-191">After installing the MBAM Client on a client computer, complete the additional steps in this topic to enable the MBAM Client to start reporting the computer’s status to MBAM more quickly.</span></span>

**<span data-ttu-id="8ead2-192">Configuration Manager 2007 統合トポロジを使用して MBAM を評価するには</span><span class="sxs-lookup"><span data-stu-id="8ead2-192">To evaluate MBAM by using the Configuration Manager 2007 Integration topology</span></span>**

1. <span data-ttu-id="8ead2-193">MBAM をインストールする前に、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8ead2-193">Before you install MBAM, do the following:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="8ead2-194">タスク</span><span class="sxs-lookup"><span data-stu-id="8ead2-194">Task</span></span></th>
   <th align="left"><span data-ttu-id="8ead2-195">手順を表示する場所</span><span class="sxs-lookup"><span data-stu-id="8ead2-195">Where to get instructions</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="8ead2-196">すべての必須ソフトウェアがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-196">Ensure that you have installed all of the prerequisite software.</span></span></p></td>
   <td align="left"><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="8ead2-197">スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件</span><span class="sxs-lookup"><span data-stu-id="8ead2-197">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p>
   <p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="8ead2-198">Configuration Manager 統合トポロジのみに適用される MBAM 2.5 サーバー前提条件</span><span class="sxs-lookup"><span data-stu-id="8ead2-198">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="8ead2-199">必要なハードウェア、RAM、その他の仕様を確認します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-199">Check the required hardware, RAM, and other specifications.</span></span></p></td>
   <td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="8ead2-200">MBAM 2.5 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="8ead2-200">MBAM 2.5 Supported Configurations</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="8ead2-201">.Mof ファイルを作成または編集します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-201">Create or edit the .mof files.</span></span></p></td>
   <td align="left"><p><a href="edit-the-configurationmof-file-mbam-25.md" data-raw-source="[Edit the Configuration.mof File](edit-the-configurationmof-file-mbam-25.md)"><span data-ttu-id="8ead2-202">Configuration.mof ファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="8ead2-202">Edit the Configuration.mof File</span></span></a></p>
   <p><a href="create-or-edit-the-sms-defmof-file-mbam-25.md" data-raw-source="[Create or Edit the Sms_def.mof File](create-or-edit-the-sms-defmof-file-mbam-25.md)"><span data-ttu-id="8ead2-203">Sms_def.mof ファイルを作成または編集する</span><span class="sxs-lookup"><span data-stu-id="8ead2-203">Create or Edit the Sms_def.mof File</span></span></a></p></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="8ead2-204">MBAM サーバーソフトウェアをインストールし、必要な機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-204">Install the MBAM Server software, and then configure the features you want.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="8ead2-205">タスク</span><span class="sxs-lookup"><span data-stu-id="8ead2-205">Task</span></span></th>
   <th align="left"><span data-ttu-id="8ead2-206">手順を表示する場所</span><span class="sxs-lookup"><span data-stu-id="8ead2-206">Where to get instructions</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="8ead2-207">Mbam サーバー機能を構成する各サーバーに MBAM サーバーソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8ead2-207">Install the MBAM Server software on each server where you want to configure an MBAM Server feature.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="8ead2-208">注</span><span class="sxs-lookup"><span data-stu-id="8ead2-208">Note</span></span></strong><br/><p><span data-ttu-id="8ead2-209">Windows PowerShell またはエクスポートされたデータ層アプリケーション (DAC) パッケージを使用して、リモートの SQL Server コンピューターにデータベースをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="8ead2-209">You can install the databases to a remote SQL Server computer by using Windows PowerShell or an exported data-tier application (DAC) package.</span></span> <span data-ttu-id="8ead2-210">DAC パッケージの詳細については、「 <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)"> データ層アプリケーション」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="8ead2-210">For more information about DAC packages, see <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)">Data-tier Applications</a>.</span></span></p>
   </div>
   <div>

   </div></td>
   <td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="8ead2-211">MBAM 2.5 サーバー ソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="8ead2-211">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="8ead2-212">コンプライアンスデータベースと監査データベース、および回復データベースを構成します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-212">Configure the Compliance and Audit Database and the Recovery Database.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)"><span data-ttu-id="8ead2-213">MBAM 2.5 データベースを構成する方法</span><span class="sxs-lookup"><span data-stu-id="8ead2-213">How to Configure the MBAM 2.5 Databases</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="8ead2-214">レポート機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-214">Configure the Reports feature.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)"><span data-ttu-id="8ead2-215">MBAM 2.5 レポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="8ead2-215">How to Configure the MBAM 2.5 Reports</span></span></a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="8ead2-216">Web アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-216">Configure the web applications.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)"><span data-ttu-id="8ead2-217">MBAM 2.5 Web アプリケーションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="8ead2-217">How to Configure the MBAM 2.5 Web Applications</span></span></a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="8ead2-218">Configuration Manager オブジェクトをインストールするように System Center Configuration Manager を構成します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-218">Configure the System Center Configuration Manager to install the Configuration Manager objects.</span></span></p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md" data-raw-source="[How to Configure the MBAM 2.5 System Center Configuration Manager Integration](how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md)"><span data-ttu-id="8ead2-219">MBAM 2.5 System Center Configuration Manager 統合を構成する方法</span><span class="sxs-lookup"><span data-stu-id="8ead2-219">How to Configure the MBAM 2.5 System Center Configuration Manager Integration</span></span></a></p></td>
   </tr>
   </tbody>
   </table>



3. <span data-ttu-id="8ead2-220">クライアントコンピューターで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8ead2-220">On a client computer, do the following:</span></span>

   1.  <span data-ttu-id="8ead2-221">クライアントコンピューターに MBAM クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8ead2-221">Install the MBAM Client on a client computer.</span></span>

   2.  <span data-ttu-id="8ead2-222">MBAM グループポリシーオブジェクトをコンピューターに適用します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-222">Apply the MBAM Group Policy Objects to the computer.</span></span>

   3.  <span data-ttu-id="8ead2-223">次のレジストリキーを設定して、MBAM クライアントがより迅速に、またはより迅速にスリープ状態になるようにします。</span><span class="sxs-lookup"><span data-stu-id="8ead2-223">Set the following registry keys to force the MBAM Client to wake up more quickly and at faster intervals:</span></span>

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement
       "ClientWakeupFrequency"=dword:00000001
       "StatusReportingFrequency"=dword:00000001
       ```

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM]
       "NoStartupDelay"=dword:00000001
       ```

       **<span data-ttu-id="8ead2-224">注</span><span class="sxs-lookup"><span data-stu-id="8ead2-224">Note</span></span>**  
       <span data-ttu-id="8ead2-225">これらのキーは、MBAM クライアントを1分間隔でウェイクアップするため、評価環境でのみ使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8ead2-225">Because these keys wake up the MBAM Client every minute, we recommend that you use these registry key settings only in an evaluation environment.</span></span>



   4.  <span data-ttu-id="8ead2-226">**BitLocker 管理クライアントサービス**を再起動します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-226">Restart the **BitLocker Management Client Service**.</span></span>

   5.  <span data-ttu-id="8ead2-227">コントロールパネルで [**構成マネージャー**] を開き、[**操作**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ead2-227">In Control Panel, open **Configuration Manager**, and then click the **Actions** tab.</span></span>

   6.  <span data-ttu-id="8ead2-228">[**コンピューターポリシーの取得 & 評価サイクル**] を選択し、[**今すぐ実行**] をクリックして、そのクライアントコンピューターに関連するグループポリシーオブジェクトを適用します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-228">Select **Machine Policy Retrieval & Evaluation Cycle**, and then click **Run Now** to apply the Group Policy Objects that are relevant to that client computer.</span></span>

   7.  <span data-ttu-id="8ead2-229">[**ハードウェアインベントリサイクル**] を選択し、[**今すぐ実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ead2-229">Select **Hardware Inventory Cycle**, and then click **Run Now**.</span></span> <span data-ttu-id="8ead2-230">この手順では、.mof ファイルにインポートした新しいクラスを使ってハードウェアインベントリを実行し、そのデータを Configuration Manager サーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-230">This step runs the hardware inventory by using the new classes that you imported to your .mof files and then sends the data to the Configuration Manager server.</span></span>

4. <span data-ttu-id="8ead2-231">Configuration Manager コンソールで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8ead2-231">In the Configuration Manager console, do the following:</span></span>

   1.  <span data-ttu-id="8ead2-232">ナビゲーションウィンドウで、[ **Mbam サポートされているコンピューター**] を右クリックし、[**メンバーシップの更新**] をクリックし、[**はい**] をクリックして、クライアントコンピューターがそのメンバーシップを直ちに報告するように強制します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-232">In the navigation pane, right-click **MBAM Supported Computers**, click **Update Membership**, and then click **Yes** to force the client computer to report its membership immediately.</span></span>

   2.  <span data-ttu-id="8ead2-233">ナビゲーションウィンドウで、[ **Mbam サポートされているコンピューター** ] をクリックして、クライアントコンピューターがコレクションに表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-233">In the navigation pane, click **MBAM Supported Computers** to verify that the client computer appears in the collection.</span></span>

5. <span data-ttu-id="8ead2-234">クライアントコンピューターのコントロールパネルで、もう一度**Configuration Manager**を開き、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8ead2-234">On the client computer, in Control Panel, reopen **Configuration Manager** again, and do the following:</span></span>

   1.  <span data-ttu-id="8ead2-235">[**操作**] タブをクリックし、[マシンポリシーの取得] を再実行して、**評価サイクル &** します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-235">Click the **Actions** tab, and then rerun **Machine Policy Retrieval & Evaluation Cycle**.</span></span>

   2.  <span data-ttu-id="8ead2-236">[**構成**] タブをクリックして、BitLocker ベースラインを選択し、[**評価**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ead2-236">Click the **Configurations** tab, select the BitLocker baseline, and click **Evaluate**.</span></span>

6. <span data-ttu-id="8ead2-237">Configuration Manager コンソールで、次のように、[エンタープライズコンプライアンス] レポートにクライアントコンピューターが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-237">In the Configuration Manager console, verify that the client computer appears on the Enterprise Compliance Report, as follows</span></span>

   1.  <span data-ttu-id="8ead2-238">ナビゲーションウィンドウで、[**コンピューター管理**] &gt; **レポート** &gt; **サービス** &gt; \*\* &lt; サーバー名 &gt; mbam\*\*を展開します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-238">In the navigation pane, expand **Computer Management** &gt; **Reporting** &gt; **Reporting Services** &gt; **&lt;server name&gt;MBAM**.</span></span>

   2.  <span data-ttu-id="8ead2-239">**Mbam**ノードで、レポートを表示する言語を表すフォルダーを選択し、[結果] ウィンドウからレポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="8ead2-239">Within the **MBAM** node, select the folder that represents the language in which you want to view reports, and then select the report from the results pane.</span></span>


## <span data-ttu-id="8ead2-240">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8ead2-240">Related topics</span></span>


[<span data-ttu-id="8ead2-241">MBAM 2.5 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="8ead2-241">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)


## <span data-ttu-id="8ead2-242">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="8ead2-242">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="8ead2-243">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="8ead2-243">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="8ead2-244">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="8ead2-244">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>





