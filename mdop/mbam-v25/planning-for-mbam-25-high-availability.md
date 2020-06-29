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
# MBAM 2.5 の高可用性のための計画


Microsoft BitLocker の管理と監視 (MBAM) では、次のセクションで説明されている1つ以上のテクノロジを使用することで、高可用性を維持することができます。

-   [SQL Server AlwaysOn 可用性グループ](#bkmk-alwayson)

-   [Microsoft SQL Server クラスタリング](#bkmk-sql-clustering)

-   [IIS ネットワーク負荷分散](#bkmk-load-balance)

-   [SQL Server でのデータベースのミラーリング](#bkmk-db-mirroring)

-   [ボリュームシャドウコピーサービス (VSS) を使用した MBAM データベースのバックアップ](#bkmk-vss)

次のセクションの情報を使用して、MBAM を高可用性構成で展開するためのオプションについて理解してください。

## <a href="" id="bkmk-alwayson"></a>SQL Server AlwaysOn 可用性グループのサポート


MBAM は、Microsoft SQL Server のデータベースの可用性グループの構成と管理を行うことができます。 MBAM の可用性グループは、コンプライアンスと監査データベース、および回復データベースが個別ではなく互いにフェイルオーバーするフェールオーバー環境をサポートしています。

可用性グループでは、一連の読み取り/書き込みプライマリデータベースと、対応するセカンダリデータベースのセットがサポートされています。 必要に応じて、セカンダリデータベースは読み取り専用のアクセス許可、一部のバックアップ操作、またはその両方で使用できます。

可用性グループの設定方法について詳しくは、「 [AlwaysOn 可用性グループ](https://go.microsoft.com/fwlink/?LinkId=393277)」をご覧ください。

## <a href="" id="bkmk-sql-clustering"></a>Microsoft SQL Server クラスタリング


MBAM 2.5 コンプライアンスと監査データベース、および SQL Server クラスターを実行しているコンピューター上の回復データベースは、実行できます。

## <a href="" id="bkmk-load-balance"></a>IIS ネットワーク負荷分散


ネットワーク負荷分散を使って、管理と監視の Web サイト (ヘルプデスクとも呼ばれます)、セルフサービスポータル、およびインターネットインフォメーションサービス (IIS) を介して展開された web サービスを実行しているコンピューター向けに、可用性の高い環境を構成することができます。

### 前提条件

ロードバランシングを構成する前に、次の前提条件を満たしていることを確認します。

-   ロードバランサーを使用できるようにする必要があります。 ロードバランサーは、Microsoft または別の会社から使うことができます。 Microsoft ロードバランサー技術の詳細については、「 [IIS サーバーで Web ファームを構築する](https://go.microsoft.com/fwlink/?LinkId=393326)」を参照してください。

-   少なくとも2台のサーバーが IIS を実行しており、ASP.NET MVC 4 を含む、web 機能をサポートするためのすべての MBAM 前提条件を満たしている。

-   MBAM データベースおよびレポートはサーバー上で実行されています。

### <a href="" id="-------------mbam-specific-changes-that-are-required-to-enable-load-balancing"></a> ロードバランシングを有効にするために必要な MBAM 固有の変更

次のタスクを実行します。

1.  Web アプリケーションプールに使用しているドメインアカウントの下に、仮想ホスト名のサービスプリンシパル名 (SPN) を登録します。 たとえば、仮想ホスト名が mbamvirtual.contoso.com で、web アプリケーションプールに使用されているドメインアカウントが contoso\\mbamapppooluser の場合は、次のコマンドで SPN を適切に登録します。

    `Setspn -s http//mbamvirtual contoso\mbamapppooluser`

    `Setspn -s http//mbamvirtual.contoso.com contoso\mbamapppooluser`

2.  次の MBAM web 機能を構成します。

    -   MBAM web 機能をホストする各サーバーでは、アプリケーションプール管理者の資格情報と同じドメインアカウントを使用します。

    -   ロードバランシングクラスターの仮想ホスト名 (DNS 名) と一致するホスト名を指定します。 たとえば、"NLB1" という名前のサーバーに MBAM をインストールして、仮想ホスト名が**mbamvirtual.contoso.com**の場合は、Windows PowerShell コマンドレットで指定したホスト名が**mbamvirtual.contoso.com**であることを確認します。

3.  Web ファームの web サイトをロードバランサーで構成する場合は、同じマシンキーを使用するように web サイトを構成する必要があります。

    詳細については、「 [MachineKey 要素 (ASP.NET Settings Schema)](https://msdn.microsoft.com/library/vstudio/w8h3skw9.aspx)」の次のセクションを参照してください。

    -   マシンキーの説明

    -   Web ファームの展開に関する考慮事項

    キーを自動的に生成する方法については、「[マシンキーを生成する (IIS 7)](https://technet.microsoft.com/library/cc772287.aspx)」を参照してください。

ロードバランシングに関する情報は、Windows Server 2012 または Windows Server2008R2 の IIS ネットワーク負荷分散 (NLB) クラスターにも適用されます。 Windows Server 2012 の IIS ネットワーク負荷分散機能は、通常、Windows Server2008R2 と同じです。 ただし、一部のタスクの詳細は Windows Server 2012 では異なります。 新しいタスクを実行する方法については、「 [Windows server 2012 R2 Preview の一般的な管理タスクとナビゲーション」および「Windows server 2012](https://go.microsoft.com/fwlink/?LinkId=316371)」を参照してください。

## <a href="" id="bkmk-db-mirroring"></a>SQL Server でのデータベースのミラーリング


MBAM は、sql Server ミラーリングの使用をサポートしています。この場合、コンプライアンスと監査データベースと回復データベースは、各データベースで SQL Server の2つのインスタンスを使ってミラーリングされます。 ミラーリングを実装する前に、このトピックで既に説明した可用性グループを使用して、ミラーリングが徐々に段階的に行われることに注意してください。

MBAM のミラーリングを実装するには、[ **Enable-MbamWebApplication** ] Windows PowerShell コマンドレットを使用して、ミラーリングされたデータベース構成の適切な接続文字列を指定する必要があります。 MBAM 2.5 Windows PowerShell コマンドレットの詳細については、「 [Windows Powershell を使用して mbam 2.5 サーバー機能を構成](configuring-mbam-25-server-features-by-using-windows-powershell.md)する」を参照してください。

### Windows PowerShell を使用した SQL Server ミラーリングの実装の例

次の例は、Windows PowerShell コマンドレットを使用して SQL Server ミラーリングを実装する方法を示しています。

**例 1**

``` syntax
Enable-MbamWebApplication -AdministrationPortal -ComplianceAndAuditDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer;Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Compliance Status";' -RecoveryDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer;Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Recovery and Hardware";' -AdvancedHelpdeskAccessGroup “MyDomain\AdvancedUserGroup” -HelpdeskAccessGroup “MyDomain\StandardUserGroup” -ReportsReadOnlyAccessGroup "MyDomain\ReportUserGroup" -ReportUrl "https://MyReportServer/ReportServer" -Port 443 -WebServiceApplicationPoolCredential (Get-Credential) -Certificate (dir cert:\LocalMachine\My\E2A7EA5533890D6567E40DFC46F53B3D31D6B689)
```

**例 2**

``` syntax
Enable-MbamWebApplication -SelfServicePortal -ComplianceAndAuditDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer; Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Compliance Status";' -RecoveryDBConnectionString 'Integrated Security=SSPI;Data Source=MyDatabaseServer;I Failover Partner=myMirrorServerAddress;Initial Catalog="MBAM Recovery and Hardware";' -Port 443 -WebServiceApplicationPoolCredential (Get-Credential) -Certificate (dir cert:\LocalMachine\My\E2A7EA5533890D6567E40DFC46F53B3D31D6B689)
```

### SQL Server のミラーリングに関する詳細情報

SQL Server のミラーリングの構成の詳細については、次のリンクを参照してください。

-   [方法: ミラーリング用のミラーデータベースの準備 (Transact-sql)](https://go.microsoft.com/fwlink/?LinkId=316375)

-   [Windows 認証を使用してデータベースミラーリングセッションを確立する (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=316377)

## <a href="" id="bkmk-vss"></a>ボリュームシャドウコピーサービス (VSS) を使用した MBAM データベースのバックアップ


MBAM は、Microsoft BitLocker 管理ライターと呼ばれるボリュームシャドウコピーサービス (VSS) ライターを提供します。 この VSS ライターは、コンプライアンスと監査データベースおよび回復データベースのバックアップを容易にします。

この VSS ライターは、MBAM web アプリケーションを有効にするすべてのサーバーに登録されています。 MBAM VSS ライターは、Microsoft SQL Server インストールの一部として登録されている SQL Server VSS Writer に依存します。 VSS ライターを使用してバックアップを実行するすべてのバックアップテクノロジは、MBAM VSS ライターを検出できます。



## 関連トピック


[MBAM 2.5 の展開計画](planning-to-deploy-mbam-25.md)

 

 
## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。




