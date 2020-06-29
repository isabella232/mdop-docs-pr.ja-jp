---
title: MBAM 2.5 Web アプリケーションを構成する方法
description: MBAM 2.5 Web アプリケーションを構成する方法
author: dansimp
ms.assetid: 909bf2d3-028c-4ac1-9247-171532a1eeae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0336d24f51167a00c8565ccd081f4bc5dfb2c4cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824497"
---
# <span data-ttu-id="ed5a5-103">MBAM 2.5 Web アプリケーションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="ed5a5-103">How to Configure the MBAM 2.5 Web Applications</span></span>


<span data-ttu-id="ed5a5-104">このトピックでは、次のいずれかの方法を使用して、 [mbam 2.5 の推奨される高レベルアーキテクチャ](high-level-architecture-for-mbam-25.md)用に Microsoft BitLocker 管理および監視 (mbam) 2.5 web アプリケーションを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-104">This topic explains how to configure the Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 web applications for the recommended [High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md) by using one of the following methods:</span></span>

-   <span data-ttu-id="ed5a5-105">Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="ed5a5-105">A Windows PowerShell cmdlet</span></span>

-   <span data-ttu-id="ed5a5-106">MBAM サーバー構成ウィザード</span><span class="sxs-lookup"><span data-stu-id="ed5a5-106">The MBAM Server Configuration wizard</span></span>

<span data-ttu-id="ed5a5-107">Web アプリケーションは、次の web サイトと対応する web サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-107">The web applications comprise the following websites and their corresponding web services:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ed5a5-108">Web サイト</span><span class="sxs-lookup"><span data-stu-id="ed5a5-108">Website</span></span></th>
<th align="left"><span data-ttu-id="ed5a5-109">説明</span><span class="sxs-lookup"><span data-stu-id="ed5a5-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ed5a5-110">管理と監視の Web サイト</span><span class="sxs-lookup"><span data-stu-id="ed5a5-110">Administration and Monitoring Website</span></span></p></td>
<td align="left"><p><span data-ttu-id="ed5a5-111">指定したユーザーが自分の PIN またはパスワードを忘れた場合に、エンドユーザーが自分のコンピューターを回復するのに役立つ web サイト</span><span class="sxs-lookup"><span data-stu-id="ed5a5-111">Website where specified users can view reports and help end users recover their computers when they forget their PIN or password</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ed5a5-112">セルフサービスポータル</span><span class="sxs-lookup"><span data-stu-id="ed5a5-112">Self-Service Portal</span></span></p></td>
<td align="left"><p><span data-ttu-id="ed5a5-113">エンドユーザーが PIN またはパスワードを忘れた場合に、自分のコンピューターにアクセスできる個別の web サイト</span><span class="sxs-lookup"><span data-stu-id="ed5a5-113">Website that end users can access to independently regain access to their computers if they forget their PIN or password</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="ed5a5-114">構成を開始する前に、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-114">Before you start the configuration:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ed5a5-115">ステップ</span><span class="sxs-lookup"><span data-stu-id="ed5a5-115">Step</span></span></th>
<th align="left"><span data-ttu-id="ed5a5-116">手順を表示する場所</span><span class="sxs-lookup"><span data-stu-id="ed5a5-116">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ed5a5-117">MBAM の推奨アーキテクチャを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-117">Review the recommended architecture for MBAM.</span></span></p></td>
<td align="left"><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)"><span data-ttu-id="ed5a5-118">MBAM 2.5 のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="ed5a5-118">High-Level Architecture for MBAM 2.5</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ed5a5-119">MBAM のサポートされている構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-119">Review the supported configurations for MBAM.</span></span></p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="ed5a5-120">MBAM 2.5 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="ed5a5-120">MBAM 2.5 Supported Configurations</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ed5a5-121">各サーバーに必要な前提条件を完了します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-121">Complete the required prerequisites on each server.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ed5a5-122">注</span><span class="sxs-lookup"><span data-stu-id="ed5a5-122">Note</span></span></strong><br/><p><span data-ttu-id="ed5a5-123">管理と監視の Web サイトを構成する前に、Secure Sockets Layer (SSL) を使用するように SQL ServerReporting Services (SSRS) を構成していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-123">Ensure that you configure SQL ServerReporting Services (SSRS) to use the Secure Sockets Layer (SSL) before you configure the Administration and Monitoring Website.</span></span> <span data-ttu-id="ed5a5-124">それ以外の場合は、レポート機能で HTTPS の代わりに HTTP が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-124">Otherwise, the Reports feature will use HTTP instead of HTTPS.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="ed5a5-125">スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件</span><span class="sxs-lookup"><span data-stu-id="ed5a5-125">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="ed5a5-126">MBAM 2.5 Server の前提条件構成マネージャーの統合トポロジにのみ適用されます </a> (該当する場合)。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-126">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</a> (if applicable)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ed5a5-127">Web サイトのアプリケーションプールアカウントのサービスプリンシパル名 (Spn) を登録します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-127">Register service principal names (SPNs) for the application pool account for the websites.</span></span> <span data-ttu-id="ed5a5-128">この手順を実行する必要があるのは、Active Directory ドメインサービス (AD DS) で管理ドメインの権限を持っていない場合のみです。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-128">You need to do this step only if you do not have administrative domain rights in Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="ed5a5-129">AD DS でこれらの権限がある場合は、MBAM によって Spn が作成されます。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-129">If you do have these rights in AD DS, MBAM will create the SPNs for you.</span></span></p></td>
<td align="left"><p><a href="planning-how-to-secure-the-mbam-websites.md#bkmk-regvirtualspn" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md#bkmk-regvirtualspn)"><span data-ttu-id="ed5a5-130">MBAM Web サイトをセキュリティで保護する方法の計画</span><span class="sxs-lookup"><span data-stu-id="ed5a5-130">Planning How to Secure the MBAM Websites</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ed5a5-131">Mbam サーバー機能を構成する各サーバーに MBAM サーバーソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-131">Install the MBAM Server software on each server where you will configure an MBAM Server feature.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ed5a5-132">注</span><span class="sxs-lookup"><span data-stu-id="ed5a5-132">Note</span></span></strong><br/><p><span data-ttu-id="ed5a5-133">あるサーバーと web サービスの両方に web サイトをインストールしようとしている場合、その web サイトを構成するには、 <strong> MbamWebApplication の Windows PowerShell コマンドレットを使用する必要があり </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-133">If you plan to install the websites on one server and the web services on another, you will be able to configure them only by using the <strong>Enable-MbamWebApplication</strong> Windows PowerShell cmdlet.</span></span> <span data-ttu-id="ed5a5-134">MBAM サーバーの構成ウィザードでは、これらの項目を個別のサーバーで構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-134">The MBAM Server Configuration wizard does not support configuring these items on separate servers.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="ed5a5-135">MBAM 2.5 サーバー ソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="ed5a5-135">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ed5a5-136">コマンドレットを使用して MBAM Server 機能を構成する場合は、Windows PowerShell を使用するための前提条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-136">Review the prerequisites for using Windows PowerShell if you plan to use cmdlets to configure MBAM Server features.</span></span></p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"><span data-ttu-id="ed5a5-137">Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="ed5a5-137">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="ed5a5-138">Windows PowerShell を使用して web アプリケーションを構成するには</span><span class="sxs-lookup"><span data-stu-id="ed5a5-138">To configure the web applications by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="ed5a5-139">構成を開始する前に、「Windows PowerShell を使用して Windows PowerShell を使用するための前提条件を確認する」を参照して、 [MBAM 2.5 Server の機能を構成](configuring-mbam-25-server-features-by-using-windows-powershell.md)するを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-139">Before you start the configuration, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md) to review the prerequisites for using Windows PowerShell.</span></span>

2.  <span data-ttu-id="ed5a5-140">Windows PowerShell を使用して web アプリケーションを構成するには、 **MbamWebApplication**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-140">Use the **Enable-MbamWebApplication** cmdlet to configure the web applications using Windows PowerShell.</span></span> <span data-ttu-id="ed5a5-141">このコマンドレットに関する情報を取得するには、「 **get-ヘルプの有効化-MbamWebApplication**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-141">To get information about this cmdlet, type **Get-Help Enable-MbamWebApplication**.</span></span>

**<span data-ttu-id="ed5a5-142">ウィザードを使用してすべての web アプリケーションの設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="ed5a5-142">To configure the settings for all web applications using the wizard</span></span>**

1. <span data-ttu-id="ed5a5-143">Web アプリケーションを構成するサーバーで、MBAM サーバー構成ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-143">On the server where you want to configure the web applications, start the MBAM Server Configuration wizard.</span></span> <span data-ttu-id="ed5a5-144">[**スタート**] メニューから [ **Mbam Server 構成**] を選択して、ウィザードを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-144">You can select **MBAM Server Configuration** from the **Start** menu to open the wizard.</span></span>

2. <span data-ttu-id="ed5a5-145">[**新しい機能の追加**] をクリックし、[**管理/監視 web サイト**] と [**セルフサービスポータル**] を選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-145">Click **Add New Features**, select **Administration and Monitoring Website** and **Self-Service Portal**, and then click **Next**.</span></span> <span data-ttu-id="ed5a5-146">Web アプリケーションのすべての前提条件が満たされていることがウィザードによってチェックされます。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-146">The wizard checks that all prerequisites for the web applications have been met.</span></span>

3. <span data-ttu-id="ed5a5-147">前提条件の確認が正常に完了したら、[**次へ**] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-147">If the prerequisite check is successful, click **Next** to continue.</span></span> <span data-ttu-id="ed5a5-148">それ以外の場合は、不足している前提条件を解決し、[**前提条件の確認] をもう一度**クリックします。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-148">Otherwise, resolve any missing prerequisites, and then click **Check prerequisites again**.</span></span>

4. <span data-ttu-id="ed5a5-149">ウィザードでフィールドの値を入力するには、次の説明を使用します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-149">Use the following descriptions to enter the field values in the wizard.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><strong><span data-ttu-id="ed5a5-150">フィールド</span><span class="sxs-lookup"><span data-stu-id="ed5a5-150">Field</span></span></strong></th>
   <th align="left"><span data-ttu-id="ed5a5-151">説明</span><span class="sxs-lookup"><span data-stu-id="ed5a5-151">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="ed5a5-152">セキュリティ証明書</span><span class="sxs-lookup"><span data-stu-id="ed5a5-152">Security certificate</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="ed5a5-153">以前に作成した証明書を選択して、web サービスと、web サイトを構成しているサーバー間の通信を暗号化することもできます。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-153">Select a previously created certificate to optionally encrypt the communication between the web services and the server on which you are configuring the websites.</span></span> <span data-ttu-id="ed5a5-154">[証明書を使用しない] を選択した場合 <strong> </strong> 、web 通信がセキュリティで保護されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-154">If you choose <strong>Do not use a certificate</strong>, your web communication may not be secure.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="ed5a5-155">ホスト名</span><span class="sxs-lookup"><span data-stu-id="ed5a5-155">Host name</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="ed5a5-156">Web サイトを構成するホストコンピューターの名前。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-156">Name of the host computer where you are configuring the websites.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="ed5a5-157">インストールパス</span><span class="sxs-lookup"><span data-stu-id="ed5a5-157">Installation path</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="ed5a5-158">Web サイトをインストールするパス。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-158">Path where you are installing the websites.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="ed5a5-159">Port</span><span class="sxs-lookup"><span data-stu-id="ed5a5-159">Port</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="ed5a5-160">Web サイトとサービスの通信に使用するポート番号。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-160">Port number to use for website and service communication.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="ed5a5-161">注</span><span class="sxs-lookup"><span data-stu-id="ed5a5-161">Note</span></span></strong><br/><p><span data-ttu-id="ed5a5-162">指定したポートを介した通信を有効にするには、ファイアウォールの例外を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-162">You must set a firewall exception to enable communication through the specified port.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="ed5a5-163">Web サービスアプリケーションプールのドメインアカウントとパスワード</span><span class="sxs-lookup"><span data-stu-id="ed5a5-163">Web service application pool domain account and password</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="ed5a5-164">Web サービスアプリケーションプールのドメインユーザーアカウントとパスワード。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-164">Domain user account and password for the web service application pool.</span></span></p>
   <p><span data-ttu-id="ed5a5-165">[ <strong> データベースの構成] ページの [読み取り/書き込み権限ドメインユーザーまたはグループ] フィールドにユーザー名を入力した場合は、 </strong> <strong> </strong> このフィールドに同じ値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-165">If you enter a user name in the <strong>Read/write access domain user or group</strong> field on the <strong>Configure Databases</strong> page, you must enter that same value in this field.</span></span></p>
   <p><span data-ttu-id="ed5a5-166">[ <strong> データベースの構成] ページの [読み取り/書き込みアクセスドメインユーザーまたはグループ] フィールドにグループ名を入力した場合 </strong> <strong> </strong> 、このフィールドに入力する値は、そのグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-166">If you enter a group name in the <strong>Read/write access domain user or group</strong> field on the <strong>Configure Databases</strong> page, the value you enter in this field must be a member of that group.</span></span></p>
   <p><span data-ttu-id="ed5a5-167">資格情報を指定しない場合、以前に有効になっていた web アプリケーションに指定された資格情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-167">If you do not specify credentials, the credentials that were specified for any previously enabled web application will be used.</span></span> <span data-ttu-id="ed5a5-168">すべての web アプリケーションは、同じアプリケーションプールの資格情報を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-168">All web applications must use the same application pool credentials.</span></span> <span data-ttu-id="ed5a5-169">Web アプリケーションごとに異なる資格情報を指定すると、最後に指定された値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-169">If you specify different credentials for different web applications, the most recently specified value will be used.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="ed5a5-170">重要</span><span class="sxs-lookup"><span data-stu-id="ed5a5-170">Important</span></span></strong><br/><p><span data-ttu-id="ed5a5-171">セキュリティを向上させるには、資格情報で指定されているアカウントに、制限付きのユーザー権限を設定します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-171">For improved security, set the account that is specified in the credentials to have limited user rights.</span></span> <span data-ttu-id="ed5a5-172">また、アカウントのパスワードを無期限に設定します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-172">Also, set the password of the account to never expire.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



5. <span data-ttu-id="ed5a5-173">組み込みの IIS \ _IUSRS アカウントまたはアプリケーションプールアカウントが、[**認証後にクライアントを偽装**する] および **[バッチジョブ**のローカルセキュリティ設定] に追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-173">Verify that the built-in IIS\_IUSRS account or the application pool account has been added to the **Impersonate a client after authentication** and the **Log on as a batch job** local security settings.</span></span>

   <span data-ttu-id="ed5a5-174">ローカルセキュリティ設定に追加されているかどうかを確認するには、**ローカルセキュリティポリシーエディター**を開き、[**ローカルポリシー** ] ノードを展開し、[**ユーザー権利の割り当て**] ノードをクリックして、右側のウィンドウで [**認証後にクライアントを偽装**し、**バッチジョブとしてログオンする**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-174">To check whether it has been added to the local security settings, open the **Local Security Policy editor**, expand the **Local Policies** node, click the **User Rights Assignment** node, and double-click **Impersonate a client after authentication** and **Log on as a batch job** policies in the right pane.</span></span>

**<span data-ttu-id="ed5a5-175">ウィザードを使用してデータベースの接続情報を構成するには</span><span class="sxs-lookup"><span data-stu-id="ed5a5-175">To configure connection information for the databases by using the wizard</span></span>**

1.  <span data-ttu-id="ed5a5-176">次のフィールドの説明を使用して、コンプライアンスと監査データベース用にウィザードの接続情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-176">Use the following field descriptions to configure the connection information in the wizard for the Compliance and Audit Database.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="ed5a5-177">フィールド</span><span class="sxs-lookup"><span data-stu-id="ed5a5-177">Field</span></span></th>
    <th align="left"><span data-ttu-id="ed5a5-178">説明</span><span class="sxs-lookup"><span data-stu-id="ed5a5-178">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="ed5a5-179">SQL Server 名</span><span class="sxs-lookup"><span data-stu-id="ed5a5-179">SQL Server name</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="ed5a5-180">コンプライアンスと監査データベースが構成されているサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-180">Name of the server where the Compliance and Audit Database is configured.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="ed5a5-181">SQL Server データベースインスタンス</span><span class="sxs-lookup"><span data-stu-id="ed5a5-181">SQL Server database instance</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="ed5a5-182">コンプライアンスと監査データベースが構成されている SQL Server インスタンスの名前。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-182">SQL Server instance name where the Compliance and Audit Database is configured.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="ed5a5-183">データベース名</span><span class="sxs-lookup"><span data-stu-id="ed5a5-183">Database name</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="ed5a5-184">コンプライアンスおよび監査データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-184">Name of the Compliance and Audit Database.</span></span></p></td>
    </tr>
    </tbody>
    </table>



2.  <span data-ttu-id="ed5a5-185">次のフィールドの説明を使用して、回復データベースのウィザードで接続情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-185">Use the following field descriptions to configure the connection information in the wizard for the Recovery Database.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="ed5a5-186">フィールド</span><span class="sxs-lookup"><span data-stu-id="ed5a5-186">Field</span></span></th>
    <th align="left"><span data-ttu-id="ed5a5-187">説明</span><span class="sxs-lookup"><span data-stu-id="ed5a5-187">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="ed5a5-188">SQL Server 名</span><span class="sxs-lookup"><span data-stu-id="ed5a5-188">SQL Server name</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="ed5a5-189">回復データベースが構成されているサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-189">Name of the server where the Recovery Database is configured.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="ed5a5-190">SQL Server データベースインスタンス</span><span class="sxs-lookup"><span data-stu-id="ed5a5-190">SQL Server database instance</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="ed5a5-191">回復データベースが構成されている SQL Server インスタンスの名前。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-191">SQL Server instance name where the Recovery Database is configured.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="ed5a5-192">データベース名</span><span class="sxs-lookup"><span data-stu-id="ed5a5-192">Database name</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="ed5a5-193">回復データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-193">Name of the Recovery Database.</span></span></p></td>
    </tr>
    </tbody>
    </table>



**<span data-ttu-id="ed5a5-194">ウィザードを使用して web アプリケーションを構成するには</span><span class="sxs-lookup"><span data-stu-id="ed5a5-194">To configure the web applications by using the wizard</span></span>**

1. <span data-ttu-id="ed5a5-195">次の説明を使用して、管理と監視の Web サイトを構成するためのウィザードのフィールド値を入力します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-195">Use the following descriptions to enter the field values in the wizard to configure the Administration and Monitoring Website.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="ed5a5-196">フィールド</span><span class="sxs-lookup"><span data-stu-id="ed5a5-196">Field</span></span></th>
   <th align="left"><span data-ttu-id="ed5a5-197">説明</span><span class="sxs-lookup"><span data-stu-id="ed5a5-197">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="ed5a5-198">高度なヘルプデスクの役割ドメイングループ</span><span class="sxs-lookup"><span data-stu-id="ed5a5-198">Advanced Helpdesk role domain group</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="ed5a5-199">メンバーが [レポート] 領域以外の管理および監視 Web サイトのすべての領域にアクセスできるドメインユーザーグループ。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-199">Domain user group whose members have access to all areas of the Administration and Monitoring Website except the Reports area.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="ed5a5-200">ヘルプデスクの役割ドメイングループ</span><span class="sxs-lookup"><span data-stu-id="ed5a5-200">Helpdesk role domain group</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="ed5a5-201"><strong> </strong> <strong> </strong> 管理と監視 web サイトの TPM およびドライブの回復領域にアクセスできるメンバーのドメインユーザーグループ。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-201">Domain user group whose members have access to the <strong>Manage TPM</strong> and <strong>Drive Recovery</strong> areas of the Administration and Monitoring Website.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="ed5a5-202">System Center Configuration Manager の統合を使用する</span><span class="sxs-lookup"><span data-stu-id="ed5a5-202">Use System Center Configuration Manager Integration</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="ed5a5-203">Configuration Manager の統合トポロジで MBAM を構成する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-203">Select this check box if you are configuring MBAM with the Configuration Manager Integration topology.</span></span> <span data-ttu-id="ed5a5-204">このチェックボックスをオンにすると、管理と監視の Web サイトではなく、構成マネージャーに表示される回復監査レポートを除くすべてのレポートが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-204">Selecting this check box makes all reports, except the Recovery Audit report, appear in Configuration Manager instead of in the Administration and Monitoring Website.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="ed5a5-205">レポート役割のドメイングループ</span><span class="sxs-lookup"><span data-stu-id="ed5a5-205">Reporting role domain group</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="ed5a5-206">管理と監視の Web サイトの [レポート] 領域に対する読み取り専用アクセス権を持つメンバーのドメインユーザーグループ。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-206">Domain user group whose members have read-only access to the Reports area of the Administration and Monitoring Website.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="ed5a5-207">SQL Server Reporting Services の URL</span><span class="sxs-lookup"><span data-stu-id="ed5a5-207">SQL Server Reporting Services URL</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="ed5a5-208">MBAM レポートが構成されている SSRS サーバーの URL です。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-208">URL for the SSRS server where the MBAM Reports are configured.</span></span></p>
   <p><span data-ttu-id="ed5a5-209">レポート Url の例:</span><span class="sxs-lookup"><span data-stu-id="ed5a5-209">Examples of report URLs:</span></span></p>
   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="ed5a5-210">ホスト名の種類</span><span class="sxs-lookup"><span data-stu-id="ed5a5-210">Type of host name</span></span></th>
   <th align="left"><span data-ttu-id="ed5a5-211">例</span><span class="sxs-lookup"><span data-stu-id="ed5a5-211">Example</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="ed5a5-212">完全修飾ドメイン名の例</span><span class="sxs-lookup"><span data-stu-id="ed5a5-212">Example with a fully qualified domain name</span></span></p></td>
   <td align="left"><p><a href="https://MyReportServer.Contoso.com/ReportServer" data-raw-source="https://MyReportServer.Contoso.com/ReportServer">https://MyReportServer.Contoso.com/ReportServer</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="ed5a5-213">カスタムホスト名を使用した例</span><span class="sxs-lookup"><span data-stu-id="ed5a5-213">Example with a custom host name</span></span></p></td>
   <td align="left"><p><a href="https://MyReportServer/ReportServer" data-raw-source="https://MyReportServer/ReportServer">https://MyReportServer/ReportServer</a></p></td>
   </tr>
   </tbody>
   </table>
   <p> </p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="ed5a5-214">仮想ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="ed5a5-214">Virtual directory</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="ed5a5-215">管理と監視の Web サイトの仮想ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-215">Virtual directory of the Administration and Monitoring Website.</span></span> <span data-ttu-id="ed5a5-216">この名前は、サーバー上の web サイトの物理ディレクトリに対応し、web サイトのホスト名に追加されます。たとえば、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-216">This name corresponds to the website’s physical directory on the server and is appended to the website’s host name, for example:</span></span></p>
   <p><span data-ttu-id="ed5a5-217">http (s)// &lt; <em> hostname </em> &gt; : &lt; <em> port/ </em> &gt; helpデスク/</span><span class="sxs-lookup"><span data-stu-id="ed5a5-217">http(s)://&lt;<em>hostname</em>&gt;:&lt;<em>port</em>&gt;/HelpDesk/</span></span></p>
   <p><span data-ttu-id="ed5a5-218">仮想ディレクトリを指定しない場合は、値の <strong> ヘルプデスク </strong> が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-218">If you do not specify a virtual directory, the value <strong>HelpDesk</strong> will be used.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="ed5a5-219">データ移行役割ドメイングループ </strong> (オプション)</span><span class="sxs-lookup"><span data-stu-id="ed5a5-219">Data Migration role domain group</strong> (optional)</span></span></p></td>
   <td align="left"><p><span data-ttu-id="ed5a5-220">メンバーが書き込み用の Mbam \* Information コマンドレットを使用して、このエンドポイントを介して回復情報を書くためのアクセス権を持つドメインユーザーグループ。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-220">Domain user group whose members have access to use the Write-Mbam\*Information Cmdlets to write recovery information via this endpoint.</span></span></p></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="ed5a5-221">次の説明を使用して、セルフサービスポータルを構成するためのウィザードのフィールド値を入力します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-221">Use the following description to enter the field values in the wizard to configure the Self-Service Portal.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="ed5a5-222">フィールド</span><span class="sxs-lookup"><span data-stu-id="ed5a5-222">Field</span></span></th>
   <th align="left"><span data-ttu-id="ed5a5-223">説明</span><span class="sxs-lookup"><span data-stu-id="ed5a5-223">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="ed5a5-224">仮想ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="ed5a5-224">Virtual directory</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="ed5a5-225">Web アプリケーションの仮想ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-225">Virtual directory of the web application.</span></span> <span data-ttu-id="ed5a5-226">この名前は、サーバー上の web サイトの物理ディレクトリに対応し、web サイトのホスト名に追加されます。たとえば、次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-226">This name corresponds to the website’s physical directory on the server, and is appended to the website’s host name, for example:</span></span></p>
   <p><span data-ttu-id="ed5a5-227">http (s):// &lt; <em> hostname </em> &gt; : &lt; <em> port </em> &gt; /selfservice/</span><span class="sxs-lookup"><span data-stu-id="ed5a5-227">http(s)://&lt;<em>hostname</em>&gt;:&lt;<em>port</em>&gt;/SelfService/</span></span></p>
   <p><span data-ttu-id="ed5a5-228">仮想ディレクトリを指定しない場合は、値 <strong> selfservice </strong> が使用されます。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-228">If you do not specify a virtual directory, the value <strong>SelfService</strong> will be used.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="ed5a5-229">会社名</span><span class="sxs-lookup"><span data-stu-id="ed5a5-229">Company name</span></span></p></td>
   <td align="left"><p><span data-ttu-id="ed5a5-230">セルフサービスポータルの会社名を指定します。たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-230">Specify a company name for the Self-Service Portal, for example:</span></span></p>
   <p><span data-ttu-id="ed5a5-231">Contoso IT</span><span class="sxs-lookup"><span data-stu-id="ed5a5-231">Contoso IT</span></span></p>
   <p><span data-ttu-id="ed5a5-232">この会社名は、すべてのセルフサービスポータルユーザーによって表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-232">This company name is viewed by all Self-Service Portal users.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="ed5a5-233">ヘルプデスクの URL テキスト</span><span class="sxs-lookup"><span data-stu-id="ed5a5-233">Helpdesk URL text</span></span></p></td>
   <td align="left"><p><span data-ttu-id="ed5a5-234">組織のヘルプデスクの web サイトにユーザーを誘導するテキストステートメントを指定します。たとえば、次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-234">Specify a text statement that directs users to your organization's Helpdesk website, for example:</span></span></p>
   <p><span data-ttu-id="ed5a5-235">ヘルプデスクまたは IT 部門に問い合わせる</span><span class="sxs-lookup"><span data-stu-id="ed5a5-235">Contact Helpdesk or IT department</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="ed5a5-236">ヘルプデスクの URL</span><span class="sxs-lookup"><span data-stu-id="ed5a5-236">Helpdesk URL</span></span></p></td>
   <td align="left"><p><span data-ttu-id="ed5a5-237">組織のヘルプデスクの web サイトの URL を指定します。例:</span><span class="sxs-lookup"><span data-stu-id="ed5a5-237">Specify the URL for your organization's Helpdesk website, for example:</span></span></p>
   <p><span data-ttu-id="ed5a5-238">http (s)/会社 &lt; <em> ヘルプの url</em>&gt;/</span><span class="sxs-lookup"><span data-stu-id="ed5a5-238">http(s)://&lt;<em>companyHelpdeskURL</em>&gt;/</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="ed5a5-239">お知らせのテキストファイル</span><span class="sxs-lookup"><span data-stu-id="ed5a5-239">Notice text file</span></span></p></td>
   <td align="left"><p><span data-ttu-id="ed5a5-240">セルフサービスポータルのランディングページで、ユーザーに表示する通知が含まれているファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-240">Select a file that contains the notice you want displayed to users on the Self-Service Portal landing page.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="ed5a5-241">ユーザーに通知テキストを表示しない</span><span class="sxs-lookup"><span data-stu-id="ed5a5-241">Do not display notice text to users</span></span></p></td>
   <td align="left"><p><span data-ttu-id="ed5a5-242">通知テキストがユーザーに表示されないように指定するには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-242">Select this check box to specify that the notice text is not displayed to users.</span></span></p></td>
   </tr>
   </tbody>
   </table>



3. <span data-ttu-id="ed5a5-243">入力が完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-243">When you finish your entries, click **Next**.</span></span>

   <span data-ttu-id="ed5a5-244">Web アプリケーションのすべての前提条件が満たされていることがウィザードによってチェックされます。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-244">The wizard checks that all prerequisites for the web applications have been met.</span></span>

4. <span data-ttu-id="ed5a5-245">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-245">Click **Next** to continue.</span></span>

5. <span data-ttu-id="ed5a5-246">[**概要**] ページで、追加される機能を確認します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-246">On the **Summary** page, review the features that will be added.</span></span>

   **<span data-ttu-id="ed5a5-247">注</span><span class="sxs-lookup"><span data-stu-id="ed5a5-247">Note</span></span>**  
   <span data-ttu-id="ed5a5-248">作成したエントリ用に Windows PowerShell スクリプトを作成するには、[ **PowerShell スクリプトのエクスポート**] をクリックし、スクリプトを保存します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-248">To create a Windows PowerShell script for the entries you made, click **Export PowerShell Script** and save the script.</span></span>



6. <span data-ttu-id="ed5a5-249">[**追加**] をクリックして web アプリケーションをサーバーに追加し、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-249">Click **Add** to add the web applications to the server, and then click **Close**.</span></span>

   <span data-ttu-id="ed5a5-250">ユーザー設定の通知テキスト、会社名、詳細情報へのポインターなどを追加してセルフサービスポータルをカスタマイズする方法については、「[組織のためのセルフサービスポータルのカスタマイズ](customizing-the-self-service-portal-for-your-organization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-250">To customize the Self-Service Portal by adding custom notice text, your company name, pointers to more information, and so on, see [Customizing the Self-Service Portal for Your Organization](customizing-the-self-service-portal-for-your-organization.md).</span></span>

**<span data-ttu-id="ed5a5-251">クライアントコンピューターが CDN にアクセスできない場合にセルフサービスポータルを構成するには</span><span class="sxs-lookup"><span data-stu-id="ed5a5-251">To configure the Self-Service Portal if client computers cannot access the CDN</span></span>**

1.  <span data-ttu-id="ed5a5-252">Microsoft BitLocker 管理および監視 (MBAM) 2.5 SP1 を実行しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-252">Determine whether you are running Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1.</span></span> <span data-ttu-id="ed5a5-253">その場合は、何も行いません。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-253">If so, do nothing.</span></span> <span data-ttu-id="ed5a5-254">セルフサービスポータルの構成が完了しました。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-254">Your Self-Service Portal configuration is complete.</span></span>

    **<span data-ttu-id="ed5a5-255">注</span><span class="sxs-lookup"><span data-stu-id="ed5a5-255">Note</span></span>**  
    <span data-ttu-id="ed5a5-256">Microsoft BitLocker 管理と監視 (MBAM) 2.5 SP1 は、セットアップで JavaScript ファイルをインストールするため、Microsoft Ajax コンテンツ配信ネットワークに接続しなくても、セルフサービスポータルを構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-256">Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1 installs the JavaScript files in setup, and so does not need to be connected to the Microsoft Ajax Content Delivery Network in order to configure the Self-Service Portal.</span></span> <span data-ttu-id="ed5a5-257">次の手順は、SP1 より前のバージョンの Microsoft BitLocker 管理および監視 (MBAM) 2.5 を使用している場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-257">The following steps are necessary only if you are using a version of Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 previous to SP1.</span></span>



2.  <span data-ttu-id="ed5a5-258">クライアントコンピューターが Microsoft Ajax コンテンツ配信ネットワーク (CDN) にアクセスできるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-258">Determine if your client computers have access to the Microsoft Ajax Content Delivery Network (CDN).</span></span>

    <span data-ttu-id="ed5a5-259">CDN は、特定の JavaScript ファイルに必要なアクセス権をセルフサービスポータルに提供します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-259">The CDN gives the Self-Service Portal the access it requires to certain JavaScript files.</span></span> <span data-ttu-id="ed5a5-260">クライアントコンピューターが CDN にアクセスできないときにセルフサービスポータルを構成しないと、会社名とエンドユーザーがサインインしたアカウントは表示されません。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-260">If you don’t configure the Self-Service Portal when client computers cannot access the CDN, only the company name and the account under which the end user signed in will be displayed.</span></span> <span data-ttu-id="ed5a5-261">エラーメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-261">No error message will be shown.</span></span>

3.  <span data-ttu-id="ed5a5-262">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-262">Do one of the following:</span></span>

    -   <span data-ttu-id="ed5a5-263">クライアントコンピューターで CDN にアクセスできる場合は、何も行いません。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-263">If your client computers have access to the CDN, do nothing.</span></span> <span data-ttu-id="ed5a5-264">セルフサービスポータルの構成が完了しました。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-264">Your Self-Service Portal configuration is complete.</span></span>

    -   <span data-ttu-id="ed5a5-265">クライアントコンピューターが CDN にアクセスできない場合は、[クライアントコンピューターが Microsoft コンテンツ配信ネットワークにアクセスできないときに、セルフサービスポータルを構成する](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-265">If your client computers do not have access to the CDN, complete the steps in [How to Configure the Self-Service Portal When Client Computers Cannot Access the Microsoft Content Delivery Network](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md).</span></span>


## <span data-ttu-id="ed5a5-266">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ed5a5-266">Related topics</span></span>


[<span data-ttu-id="ed5a5-267">サーバーのイベント ログ</span><span class="sxs-lookup"><span data-stu-id="ed5a5-267">Server Event Logs</span></span>](server-event-logs.md)

[<span data-ttu-id="ed5a5-268">MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="ed5a5-268">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)

[<span data-ttu-id="ed5a5-269">クライアント コンピューターが Microsoft Content Delivery Network にアクセスできない場合にセルフサービス ポータルを構成する方法</span><span class="sxs-lookup"><span data-stu-id="ed5a5-269">How to Configure the Self-Service Portal When Client Computers Cannot Access the Microsoft Content Delivery Network</span></span>](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)

[<span data-ttu-id="ed5a5-270">組織のセルフサービス ポータルのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="ed5a5-270">Customizing the Self-Service Portal for Your Organization</span></span>](customizing-the-self-service-portal-for-your-organization.md)

[<span data-ttu-id="ed5a5-271">MBAM 2.5 サーバー機能の構成の確認</span><span class="sxs-lookup"><span data-stu-id="ed5a5-271">Validating the MBAM 2.5 Server Feature Configuration</span></span>](validating-the-mbam-25-server-feature-configuration.md)



## <span data-ttu-id="ed5a5-272">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-272">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="ed5a5-273">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-273">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="ed5a5-274">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="ed5a5-274">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





