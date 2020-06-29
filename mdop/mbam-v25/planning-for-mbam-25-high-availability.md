---
title: MBAM 2.5 の高可用性のための計画
description: MBAM 2.5 の高可用性のための計画
author: dansimp
ms.assetid: 1e29b30c-33f1-4a52-9442-8c1391f0049c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 20c304f669cfe9e1484be47dea1b9fcc917aea2c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826944"
---
# <span data-ttu-id="fb76b-103">MBAM 2.5 の高可用性のための計画</span><span class="sxs-lookup"><span data-stu-id="fb76b-103">Planning for MBAM 2.5 High Availability</span></span>


<span data-ttu-id="fb76b-104">Microsoft BitLocker の管理と監視 (MBAM) では、次のセクションで説明されている1つ以上のテクノロジを使用することで、高可用性を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="fb76b-104">Microsoft BitLocker Administration and Monitoring (MBAM) can maintain high availability through use of one or more of the following technologies, which are described in the following sections:</span></span>

-   [<span data-ttu-id="fb76b-105">SQL Server AlwaysOn 可用性グループ</span><span class="sxs-lookup"><span data-stu-id="fb76b-105">SQL Server AlwaysOn availability groups</span></span>](#bkmk-alwayson)

-   [<span data-ttu-id="fb76b-106">Microsoft SQL Server クラスタリング</span><span class="sxs-lookup"><span data-stu-id="fb76b-106">Microsoft SQL Server clustering</span></span>](#bkmk-sql-clustering)

-   [<span data-ttu-id="fb76b-107">IIS ネットワーク負荷分散</span><span class="sxs-lookup"><span data-stu-id="fb76b-107">IIS Network Load Balancing</span></span>](#bkmk-load-balance)

-   [<span data-ttu-id="fb76b-108">SQL Server でのデータベースのミラーリング</span><span class="sxs-lookup"><span data-stu-id="fb76b-108">Database mirroring in SQL Server</span></span>](#bkmk-db-mirroring)

-   [<span data-ttu-id="fb76b-109">ボリュームシャドウコピーサービス (VSS) を使用した MBAM データベースのバックアップ</span><span class="sxs-lookup"><span data-stu-id="fb76b-109">Backing up MBAM databases by using the Volume Shadow Copy Service (VSS)</span></span>](#bkmk-vss)

<span data-ttu-id="fb76b-110">次のセクションの情報を使用して、MBAM を高可用性構成で展開するためのオプションについて理解してください。</span><span class="sxs-lookup"><span data-stu-id="fb76b-110">Use the information in the following sections to help you understand the options to deploy MBAM in a highly available configuration.</span></span>

## <a href="" id="bkmk-alwayson"></a><span data-ttu-id="fb76b-111">SQL Server AlwaysOn 可用性グループのサポート</span><span class="sxs-lookup"><span data-stu-id="fb76b-111">Support for SQL Server AlwaysOn availability groups</span></span>


<span data-ttu-id="fb76b-112">MBAM は、Microsoft SQL Server のデータベースの可用性グループの構成と管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fb76b-112">MBAM enables you to configure and manage availability groups for the databases in Microsoft SQL Server.</span></span> <span data-ttu-id="fb76b-113">MBAM の可用性グループは、コンプライアンスと監査データベース、および回復データベースが個別ではなく互いにフェイルオーバーするフェールオーバー環境をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fb76b-113">An availability group for MBAM supports a failover environment where the Compliance and Audit Database and the Recovery Database fail over together rather than separately.</span></span>

<span data-ttu-id="fb76b-114">可用性グループでは、一連の読み取り/書き込みプライマリデータベースと、対応するセカンダリデータベースのセットがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="fb76b-114">An availability group supports a set of read/write primary databases and one to four sets of corresponding secondary databases.</span></span> <span data-ttu-id="fb76b-115">必要に応じて、セカンダリデータベースは読み取り専用のアクセス許可、一部のバックアップ操作、またはその両方で使用できます。</span><span class="sxs-lookup"><span data-stu-id="fb76b-115">Optionally, secondary databases can be made available for read-only permission, some backup operations, or for both.</span></span>

<span data-ttu-id="fb76b-116">可用性グループの設定方法について詳しくは、「 [AlwaysOn 可用性グループ](https://go.microsoft.com/fwlink/?LinkId=393277)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fb76b-116">For information about how to set up availability groups, see [AlwaysOn Availability Groups](https://go.microsoft.com/fwlink/?LinkId=393277).</span></span>

## <a href="" id="bkmk-sql-clustering"></a><span data-ttu-id="fb76b-117">Microsoft SQL Server クラスタリング</span><span class="sxs-lookup"><span data-stu-id="fb76b-117">Microsoft SQL Server clustering</span></span>


<span data-ttu-id="fb76b-118">MBAM 2.5 コンプライアンスと監査データベース、および SQL Server クラスターを実行しているコンピューター上の回復データベースは、実行できます。</span><span class="sxs-lookup"><span data-stu-id="fb76b-118">You can run the MBAM 2.5 Compliance and Audit Database and the Recovery Database on computers that are running SQL Server clusters.</span></span>

## <a href="" id="bkmk-load-balance"></a><span data-ttu-id="fb76b-119">IIS ネットワーク負荷分散</span><span class="sxs-lookup"><span data-stu-id="fb76b-119">IIS Network Load Balancing</span></span>


<span data-ttu-id="fb76b-120">ネットワーク負荷分散を使って、管理と監視の Web サイト (ヘルプデスクとも呼ばれます)、セルフサービスポータル、およびインターネットインフォメーションサービス (IIS) を介して展開された web サービスを実行しているコンピューター向けに、可用性の高い環境を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="fb76b-120">You can use Network Load Balancing to configure a highly available environment for computers that are running the Administration and Monitoring Website (also known as Help Desk), the Self-Service Portal, and the web services, which are deployed through Internet Information Services (IIS).</span></span>

### <span data-ttu-id="fb76b-121">前提条件</span><span class="sxs-lookup"><span data-stu-id="fb76b-121">Prerequisites</span></span>

<span data-ttu-id="fb76b-122">ロードバランシングを構成する前に、次の前提条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fb76b-122">Before configuring load balancing, ensure that you have met the following prerequisites:</span></span>

-   <span data-ttu-id="fb76b-123">ロードバランサーを使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb76b-123">A load balancer must be available.</span></span> <span data-ttu-id="fb76b-124">ロードバランサーは、Microsoft または別の会社から使うことができます。</span><span class="sxs-lookup"><span data-stu-id="fb76b-124">You can use load balancers from Microsoft or another company.</span></span> <span data-ttu-id="fb76b-125">Microsoft ロードバランサー技術の詳細については、「 [IIS サーバーで Web ファームを構築する](https://go.microsoft.com/fwlink/?LinkId=393326)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb76b-125">For more information about Microsoft load balancer technology, see [Build a Web Farm with IIS Servers](https://go.microsoft.com/fwlink/?LinkId=393326).</span></span>

-   <span data-ttu-id="fb76b-126">少なくとも2台のサーバーが IIS を実行しており、ASP.NET MVC 4 を含む、web 機能をサポートするためのすべての MBAM 前提条件を満たしている。</span><span class="sxs-lookup"><span data-stu-id="fb76b-126">At least two servers are running IIS and have met all of the MBAM prerequisites to support its web features, including ASP.NET MVC 4.</span></span>

-   <span data-ttu-id="fb76b-127">MBAM データベースおよびレポートはサーバー上で実行されています。</span><span class="sxs-lookup"><span data-stu-id="fb76b-127">MBAM databases and reports are running on a server.</span></span>

### <a href="" id="-------------mbam-specific-changes-that-are-required-to-enable-load-balancing"></a> <span data-ttu-id="fb76b-128">ロードバランシングを有効にするために必要な MBAM 固有の変更</span><span class="sxs-lookup"><span data-stu-id="fb76b-128">MBAM-specific changes that are required to enable Load Balancing</span></span>

<span data-ttu-id="fb76b-129">次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="fb76b-129">Complete the following tasks:</span></span>

1.  <span data-ttu-id="fb76b-130">Web アプリケーションプールに使用しているドメインアカウントの下に、仮想ホスト名のサービスプリンシパル名 (SPN) を登録します。</span><span class="sxs-lookup"><span data-stu-id="fb76b-130">Register a Service Principal Name (SPN) for the virtual host name under the domain account that you are using for the web application pools.</span></span> <span data-ttu-id="fb76b-131">たとえば、仮想ホスト名が mbamvirtual.contoso.com で、web アプリケーションプールに使用されているドメインアカウントが contoso\\mbamapppooluser の場合は、次のコマンドで SPN を適切に登録します。</span><span class="sxs-lookup"><span data-stu-id="fb76b-131">For example, if the virtual host name is mbamvirtual.contoso.com, and the domain account used for the web application pools is contoso\\mbamapppooluser, the following command registers the SPN appropriately.</span></span>

    `Setspn -s http//mbamvirtual contoso\mbamapppooluser`

    `Setspn -s http//mbamvirtual.contoso.com contoso\mbamapppooluser`

2.  <span data-ttu-id="fb76b-132">次の MBAM web 機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="fb76b-132">Configure the following MBAM web features:</span></span>

    -   <span data-ttu-id="fb76b-133">MBAM web 機能をホストする各サーバーでは、アプリケーションプール管理者の資格情報と同じドメインアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb76b-133">On each server that will host the MBAM web features, use the same domain account for the application pool administrative credentials.</span></span>

    -   <span data-ttu-id="fb76b-134">ロードバランシングクラスターの仮想ホスト名 (DNS 名) と一致するホスト名を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb76b-134">Specify a host name that matches the virtual host name (DNS name) of the Load Balancing cluster.</span></span> <span data-ttu-id="fb76b-135">たとえば、"NLB1" という名前のサーバーに MBAM をインストールして、仮想ホスト名が**mbamvirtual.contoso.com**の場合は、Windows PowerShell コマンドレットで指定したホスト名が**mbamvirtual.contoso.com**であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fb76b-135">For example, when you install MBAM on a server called "NLB1" with a virtual host name of **mbamvirtual.contoso.com**, ensure that the host name that you specify in the Windows PowerShell cmdlet is **mbamvirtual.contoso.com**.</span></span>

3.  <span data-ttu-id="fb76b-136">Web ファームの web サイトをロードバランサーで構成する場合は、同じマシンキーを使用するように web サイトを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb76b-136">If you are configuring the websites in a web farm with a load balancer, you must configure the websites to use the same machine key.</span></span>

    <span data-ttu-id="fb76b-137">詳細については、「 [MachineKey 要素 (ASP.NET Settings Schema)](https://msdn.microsoft.com/library/vstudio/w8h3skw9.aspx)」の次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb76b-137">For more information, see the following sections in [machineKey Element (ASP.NET Settings Schema)](https://msdn.microsoft.com/library/vstudio/w8h3skw9.aspx):</span></span>

    -   <span data-ttu-id="fb76b-138">マシンキーの説明</span><span class="sxs-lookup"><span data-stu-id="fb76b-138">Machine Key Explained</span></span>

    -   <span data-ttu-id="fb76b-139">Web ファームの展開に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="fb76b-139">Web Farm Deployment Considerations</span></span>

    <span data-ttu-id="fb76b-140">キーを自動的に生成する方法については、「[マシンキーを生成する (IIS 7)](https://technet.microsoft.com/library/cc772287.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb76b-140">For instructions about how to automatically generate a key, see [Generate a Machine Key (IIS 7)](https://technet.microsoft.com/library/cc772287.aspx).</span></span>

<span data-ttu-id="fb76b-141">ロードバランシングに関する情報は、Windows Server 2012 または Windows Server2008R2 の IIS ネットワーク負荷分散 (NLB) クラスターにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="fb76b-141">The information about Load Balancing also applies to IIS Network Load Balancing (NLB) clusters in Windows Server 2012 or Windows Server2008R2.</span></span> <span data-ttu-id="fb76b-142">Windows Server 2012 の IIS ネットワーク負荷分散機能は、通常、Windows Server2008R2 と同じです。</span><span class="sxs-lookup"><span data-stu-id="fb76b-142">The IIS Network Load Balancing functionality in Windows Server 2012 is generally the same as in Windows Server2008R2.</span></span> <span data-ttu-id="fb76b-143">ただし、一部のタスクの詳細は Windows Server 2012 では異なります。</span><span class="sxs-lookup"><span data-stu-id="fb76b-143">However, some task details are different in Windows Server 2012.</span></span> <span data-ttu-id="fb76b-144">新しいタスクを実行する方法については、「 [Windows server 2012 R2 Preview の一般的な管理タスクとナビゲーション」および「Windows server 2012](https://go.microsoft.com/fwlink/?LinkId=316371)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb76b-144">For information about new ways to do tasks, see [Common Management Tasks and Navigation in Windows Server 2012 R2 Preview and Windows Server 2012](https://go.microsoft.com/fwlink/?LinkId=316371).</span></span>

## <a href="" id="bkmk-db-mirroring"></a><span data-ttu-id="fb76b-145">SQL Server でのデータベースのミラーリング</span><span class="sxs-lookup"><span data-stu-id="fb76b-145">Database mirroring in SQL Server</span></span>


<span data-ttu-id="fb76b-146">MBAM は、sql Server ミラーリングの使用をサポートしています。この場合、コンプライアンスと監査データベースと回復データベースは、各データベースで SQL Server の2つのインスタンスを使ってミラーリングされます。</span><span class="sxs-lookup"><span data-stu-id="fb76b-146">MBAM supports the use of SQL Server mirroring, where the Compliance and Audit Database and the Recovery Database are mirrored by using two instances of SQL Server for each database.</span></span> <span data-ttu-id="fb76b-147">ミラーリングを実装する前に、このトピックで既に説明した可用性グループを使用して、ミラーリングが徐々に段階的に行われることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fb76b-147">Before implementing mirroring, be aware that mirroring is slowly being phased out, in favor of availability groups, which are discussed earlier in this topic.</span></span>

<span data-ttu-id="fb76b-148">MBAM のミラーリングを実装するには、[ **Enable-MbamWebApplication** ] Windows PowerShell コマンドレットを使用して、ミラーリングされたデータベース構成の適切な接続文字列を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb76b-148">To implement mirroring for MBAM, you must specify the appropriate connection strings for the mirrored database configuration by using the **Enable-MbamWebApplication** Windows PowerShell cmdlet.</span></span> <span data-ttu-id="fb76b-149">MBAM 2.5 Windows PowerShell コマンドレットの詳細については、「 [Windows Powershell を使用して mbam 2.5 サーバー機能を構成](configuring-mbam-25-server-features-by-using-windows-powershell.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb76b-149">For more information about the MBAM 2.5 Windows PowerShell cmdlets, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md).</span></span>

### <span data-ttu-id="fb76b-150">Windows PowerShell を使用した SQL Server ミラーリングの実装の例</span><span class="sxs-lookup"><span data-stu-id="fb76b-150">Examples of implementing SQL Server mirroring by using Windows PowerShell</span></span>

<span data-ttu-id="fb76b-151">次の例は、Windows PowerShell コマンドレットを使用して SQL Server ミラーリングを実装する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="fb76b-151">The following examples show how you might implement SQL Server mirroring by using Windows PowerShell cmdlets.</span></span>

**<span data-ttu-id="fb76b-152">例 1</span><span class="sxs-lookup"><span data-stu-id="fb76b-152">Example 1</span></span>**

``` syntax
Enable-MbamWebApplication -AdministrationPortal -ComplianceAndAuditDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer;Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Compliance Status";' -RecoveryDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer;Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Recovery and Hardware";' -AdvancedHelpdeskAccessGroup “MyDomain\AdvancedUserGroup” -HelpdeskAccessGroup “MyDomain\StandardUserGroup” -ReportsReadOnlyAccessGroup "MyDomain\ReportUserGroup" -ReportUrl "https://MyReportServer/ReportServer" -Port 443 -WebServiceApplicationPoolCredential (Get-Credential) -Certificate (dir cert:\LocalMachine\My\E2A7EA5533890D6567E40DFC46F53B3D31D6B689)
```

**<span data-ttu-id="fb76b-153">例 2</span><span class="sxs-lookup"><span data-stu-id="fb76b-153">Example 2</span></span>**

``` syntax
Enable-MbamWebApplication -SelfServicePortal -ComplianceAndAuditDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer; Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Compliance Status";' -RecoveryDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer;I Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Recovery and Hardware";' -Port 443 -WebServiceApplicationPoolCredential (Get-Credential) -Certificate (dir cert:\LocalMachine\My\E2A7EA5533890D6567E40DFC46F53B3D31D6B689)
```

### <span data-ttu-id="fb76b-154">SQL Server のミラーリングに関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="fb76b-154">More information about SQL Server mirroring</span></span>

<span data-ttu-id="fb76b-155">SQL Server のミラーリングの構成の詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb76b-155">The following links provide more information about configuring SQL Server mirroring:</span></span>

-   [<span data-ttu-id="fb76b-156">方法: ミラーリング用のミラーデータベースの準備 (Transact-sql)</span><span class="sxs-lookup"><span data-stu-id="fb76b-156">How to: Prepare a Mirror Database for Mirroring (Transact-SQL)</span></span>](https://go.microsoft.com/fwlink/?LinkId=316375)

-   [<span data-ttu-id="fb76b-157">Windows 認証を使用してデータベースミラーリングセッションを確立する (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="fb76b-157">Establish a Database Mirroring Session Using Windows Authentication (SQL Server Management Studio)</span></span>](https://go.microsoft.com/fwlink/?LinkId=316377)

## <a href="" id="bkmk-vss"></a><span data-ttu-id="fb76b-158">ボリュームシャドウコピーサービス (VSS) を使用した MBAM データベースのバックアップ</span><span class="sxs-lookup"><span data-stu-id="fb76b-158">Backing up MBAM databases by using the Volume Shadow Copy Service (VSS)</span></span>


<span data-ttu-id="fb76b-159">MBAM は、Microsoft BitLocker 管理ライターと呼ばれるボリュームシャドウコピーサービス (VSS) ライターを提供します。</span><span class="sxs-lookup"><span data-stu-id="fb76b-159">MBAM provides a Volume Shadow Copy Service (VSS) writer, called the Microsoft BitLocker Administration and Management Writer.</span></span> <span data-ttu-id="fb76b-160">この VSS ライターは、コンプライアンスと監査データベースおよび回復データベースのバックアップを容易にします。</span><span class="sxs-lookup"><span data-stu-id="fb76b-160">This VSS writer facilitates the backup of the Compliance and Audit Database and the Recovery Database.</span></span>

<span data-ttu-id="fb76b-161">この VSS ライターは、MBAM web アプリケーションを有効にするすべてのサーバーに登録されています。</span><span class="sxs-lookup"><span data-stu-id="fb76b-161">The VSS writer is registered on every server where you enable an MBAM web application.</span></span> <span data-ttu-id="fb76b-162">MBAM VSS ライターは、Microsoft SQL Server インストールの一部として登録されている SQL Server VSS Writer に依存します。</span><span class="sxs-lookup"><span data-stu-id="fb76b-162">The MBAM VSS writer depends on the SQL Server VSS Writer, which is registered as part of the Microsoft SQL Server installation.</span></span> <span data-ttu-id="fb76b-163">VSS ライターを使用してバックアップを実行するすべてのバックアップテクノロジは、MBAM VSS ライターを検出できます。</span><span class="sxs-lookup"><span data-stu-id="fb76b-163">Any backup technology that uses VSS writers to perform backup can discover the MBAM VSS writer.</span></span>



## <span data-ttu-id="fb76b-164">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fb76b-164">Related topics</span></span>


[<span data-ttu-id="fb76b-165">MBAM 2.5 の展開計画</span><span class="sxs-lookup"><span data-stu-id="fb76b-165">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

 

 
## <span data-ttu-id="fb76b-166">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="fb76b-166">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="fb76b-167">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="fb76b-167">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="fb76b-168">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="fb76b-168">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




