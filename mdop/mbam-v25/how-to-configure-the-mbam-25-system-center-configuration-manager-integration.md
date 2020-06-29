---
title: MBAM 2.5 System Center Configuration Manager 統合を構成する方法
description: MBAM 2.5 System Center Configuration Manager 統合を構成する方法
author: dansimp
ms.assetid: 2b8a4c13-1dad-41e8-89ac-6889c5f7e051
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7c6fb0a0b06399baf1dc6493a40d17e76a51741f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812443"
---
# <span data-ttu-id="44fb0-103">MBAM 2.5 System Center Configuration Manager 統合を構成する方法</span><span class="sxs-lookup"><span data-stu-id="44fb0-103">How to Configure the MBAM 2.5 System Center Configuration Manager Integration</span></span>


<span data-ttu-id="44fb0-104">このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) を構成して、MBAM を Configuration Manager と統合する System Center Configuration Manager 統合トポロジを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="44fb0-104">This topic explains how to configure Microsoft BitLocker Administration and Monitoring (MBAM) to use the System Center Configuration Manager Integration topology, which integrates MBAM with Configuration Manager.</span></span>

<span data-ttu-id="44fb0-105">以下を使用して Configuration Manager の統合を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="44fb0-105">The instructions explain how to configure Configuration Manager Integration by using:</span></span>

-   <span data-ttu-id="44fb0-106">Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="44fb0-106">A Windows PowerShell cmdlet</span></span>

-   <span data-ttu-id="44fb0-107">MBAM サーバー構成ウィザード</span><span class="sxs-lookup"><span data-stu-id="44fb0-107">The MBAM Server Configuration wizard</span></span>

<span data-ttu-id="44fb0-108">手順は、 [MBAM 2.5 の高レベルアーキテクチャ](high-level-architecture-for-mbam-25.md)の推奨アーキテクチャに基づいています。</span><span class="sxs-lookup"><span data-stu-id="44fb0-108">The instructions are based on the recommended architecture in [High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md).</span></span>

**<span data-ttu-id="44fb0-109">構成を開始する前に、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="44fb0-109">Before you start the configuration:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="44fb0-110">ステップ</span><span class="sxs-lookup"><span data-stu-id="44fb0-110">Step</span></span></th>
<th align="left"><span data-ttu-id="44fb0-111">手順を表示する場所</span><span class="sxs-lookup"><span data-stu-id="44fb0-111">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="44fb0-112">MBAM の推奨アーキテクチャを確認します。</span><span class="sxs-lookup"><span data-stu-id="44fb0-112">Review the recommended architecture for MBAM.</span></span></p></td>
<td align="left"><p><a href="high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md" data-raw-source="[High-Level Architecture of MBAM 2.5 with Configuration Manager Integration Topology](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)"><span data-ttu-id="44fb0-113">Configuration Manager 統合トポロジを使用した MBAM 2.5 のアーキテクチャ概要</span><span class="sxs-lookup"><span data-stu-id="44fb0-113">High-Level Architecture of MBAM 2.5 with Configuration Manager Integration Topology</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="44fb0-114">MBAM のサポートされている構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="44fb0-114">Review the supported configurations for MBAM.</span></span></p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="44fb0-115">MBAM 2.5 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="44fb0-115">MBAM 2.5 Supported Configurations</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="44fb0-116">各サーバーに必要な前提条件を完了します。</span><span class="sxs-lookup"><span data-stu-id="44fb0-116">Complete the required prerequisites on each server.</span></span></p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="44fb0-117">スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件</span><span class="sxs-lookup"><span data-stu-id="44fb0-117">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="44fb0-118">Configuration Manager 統合トポロジのみに適用される MBAM 2.5 サーバー前提条件</span><span class="sxs-lookup"><span data-stu-id="44fb0-118">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</span></span></a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="44fb0-119">Mbam サーバー機能を構成する各サーバーに MBAM サーバーソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="44fb0-119">Install the MBAM Server software on each server where you will configure an MBAM Server feature.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="44fb0-120">注</span><span class="sxs-lookup"><span data-stu-id="44fb0-120">Note</span></span></strong><br/><p><span data-ttu-id="44fb0-121">このトポロジでは、MBAM サーバーソフトウェアをインストールするコンピューターに Configuration Manager コンソールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="44fb0-121">For this topology, you must install the Configuration Manager console on the computer where you are installing the MBAM Server software.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="44fb0-122">MBAM 2.5 サーバー ソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="44fb0-122">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="44fb0-123">Windows PowerShell の前提条件を確認します (Windows PowerShell コマンドレットを使用して MBAM を構成する場合にのみ該当します)。</span><span class="sxs-lookup"><span data-stu-id="44fb0-123">Review Windows PowerShell prerequisites (applicable only if you are going to use Windows PowerShell cmdlets to configure MBAM).</span></span></p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"><span data-ttu-id="44fb0-124">Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="44fb0-124">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="44fb0-125">Windows PowerShell を使用して Configuration Manager の統合を構成するには</span><span class="sxs-lookup"><span data-stu-id="44fb0-125">To configure Configuration Manager Integration by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="44fb0-126">構成を開始する前に、「Windows PowerShell を使用して Windows PowerShell を使用するための前提条件を確認する」を参照して、 [MBAM 2.5 Server の機能を構成](configuring-mbam-25-server-features-by-using-windows-powershell.md)するを参照してください。</span><span class="sxs-lookup"><span data-stu-id="44fb0-126">Before you start the configuration, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md) to review the prerequisites for using Windows PowerShell.</span></span>

2.  <span data-ttu-id="44fb0-127">**MbamCMIntegration** Windows PowerShell コマンドレットを使用して、レポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="44fb0-127">Use the **Enable-MbamCMIntegration** Windows PowerShell cmdlet to configure the Reports.</span></span> <span data-ttu-id="44fb0-128">このコマンドレットに関する情報を取得するには、「 **MbamCMIntegration**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="44fb0-128">To get information about this cmdlet, type **Get-Help Enable-MbamCMIntegration**.</span></span>

**<span data-ttu-id="44fb0-129">ウィザードを使用して System Center Configuration Manager の統合を構成するには</span><span class="sxs-lookup"><span data-stu-id="44fb0-129">To configure the System Center Configuration Manager Integration by using the wizard</span></span>**

1.  <span data-ttu-id="44fb0-130">System Center Configuration Manager の統合機能を構成するサーバーで、MBAM サーバー構成ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="44fb0-130">On the server where you want to configure the System Center Configuration Manager Integration feature, start the MBAM Server Configuration wizard.</span></span> <span data-ttu-id="44fb0-131">[**スタート**] メニューから [ **Mbam Server 構成**] を選択して、ウィザードを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="44fb0-131">You can select **MBAM Server Configuration** from the **Start** menu to open the wizard.</span></span>

2.  <span data-ttu-id="44fb0-132">[**新しい機能の追加**] をクリックし、[ **System Center Configuration Manager の統合**] を選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44fb0-132">Click **Add New Features**, select **System Center Configuration Manager Integration**, and then click **Next**.</span></span>

    <span data-ttu-id="44fb0-133">このウィザードは、構成マネージャーの統合に関するすべての前提条件が満たされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="44fb0-133">The wizard checks that all prerequisites for the Configuration Manager Integration have been met.</span></span>

3.  <span data-ttu-id="44fb0-134">前提条件の確認が正常に完了したら、[**次へ**] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="44fb0-134">If the prerequisite check is successful, click **Next** to continue.</span></span> <span data-ttu-id="44fb0-135">それ以外の場合は、不足している前提条件を解決し、[**前提条件の確認] をもう一度**クリックします。</span><span class="sxs-lookup"><span data-stu-id="44fb0-135">Otherwise, resolve any missing prerequisites, and then click **Check prerequisites again**.</span></span>

4.  <span data-ttu-id="44fb0-136">ウィザードでフィールドの値を入力するには、次の説明を使用します。</span><span class="sxs-lookup"><span data-stu-id="44fb0-136">Use the following descriptions to enter the field values in the wizard:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="44fb0-137">フィールド</span><span class="sxs-lookup"><span data-stu-id="44fb0-137">Field</span></span></th>
    <th align="left"><span data-ttu-id="44fb0-138">説明</span><span class="sxs-lookup"><span data-stu-id="44fb0-138">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="44fb0-139">SQL Server Reporting Services サーバー</span><span class="sxs-lookup"><span data-stu-id="44fb0-139">SQL Server Reporting Services server</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="44fb0-140">レポートサービスポイントの役割を持つサーバーの完全修飾ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="44fb0-140">Fully qualified domain name (FQDN) of the server with the Reporting Service point role.</span></span> <span data-ttu-id="44fb0-141">MBAM Configuration Manager レポートが展開されるサーバーです。</span><span class="sxs-lookup"><span data-stu-id="44fb0-141">This is the server to which the MBAM Configuration Manager Reports are deployed.</span></span></p>
    <p><span data-ttu-id="44fb0-142">サーバーを指定しない場合、Configuration Manager レポートはローカルサーバーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="44fb0-142">If you don’t specify a server, the Configuration Manager Reports will be deployed to the local server.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="44fb0-143">SQL Server Reporting Services インスタンス</span><span class="sxs-lookup"><span data-stu-id="44fb0-143">SQL Server Reporting Services instance</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="44fb0-144">Configuration Manager レポートが展開される SQL Server Reporting Services (SSRS) インスタンスの名前です。</span><span class="sxs-lookup"><span data-stu-id="44fb0-144">Name of the SQL Server Reporting Services (SSRS) instance where the Configuration Manager Reports are deployed.</span></span></p>
    <p><span data-ttu-id="44fb0-145">インスタンスを指定しない場合、Configuration Manager レポートは既定の SSRS インスタンス名に展開されます。</span><span class="sxs-lookup"><span data-stu-id="44fb0-145">If you don’t specify an instance, the Configuration Manager Reports will be deployed to the default SSRS instance name.</span></span> <span data-ttu-id="44fb0-146">サーバーで System Center 2012 構成マネージャーがインストールされている場合、入力した値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="44fb0-146">The value you enter is ignored if the server has System Center 2012 Configuration Manager installed.</span></span></p></td>
    </tr>
    </tbody>
    </table>



5.  <span data-ttu-id="44fb0-147">[**概要**] ページで、追加される機能を確認します。</span><span class="sxs-lookup"><span data-stu-id="44fb0-147">On the **Summary** page, review the features that will be added.</span></span>

    **<span data-ttu-id="44fb0-148">注</span><span class="sxs-lookup"><span data-stu-id="44fb0-148">Note</span></span>**  
    <span data-ttu-id="44fb0-149">作成したエントリの Windows PowerShell スクリプトを作成するには、[ **PowerShell スクリプトのエクスポート**] をクリックし、スクリプトを保存します。</span><span class="sxs-lookup"><span data-stu-id="44fb0-149">To create a Windows PowerShell script of the entries you just made, click **Export PowerShell Script** and save the script.</span></span>



6.  <span data-ttu-id="44fb0-150">[**追加**] をクリックして Configuration Manager の統合機能をサーバーに追加し、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44fb0-150">Click **Add** to add the Configuration Manager Integration feature to the server, and then click **Close**.</span></span>



## <span data-ttu-id="44fb0-151">関連トピック</span><span class="sxs-lookup"><span data-stu-id="44fb0-151">Related topics</span></span>


[<span data-ttu-id="44fb0-152">MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="44fb0-152">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)

[<span data-ttu-id="44fb0-153">MBAM 2.5 サーバー機能の構成の確認</span><span class="sxs-lookup"><span data-stu-id="44fb0-153">Validating the MBAM 2.5 Server Feature Configuration</span></span>](validating-the-mbam-25-server-feature-configuration.md)


## <span data-ttu-id="44fb0-154">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="44fb0-154">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="44fb0-155">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="44fb0-155">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="44fb0-156">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="44fb0-156">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>






