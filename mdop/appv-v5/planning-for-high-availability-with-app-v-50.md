---
title: App-V 5.0 の高可用性の計画
description: App-V 5.0 の高可用性の計画
author: dansimp
ms.assetid: 6d9a6492-23f8-465c-82e5-49c863594156
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ebf586de7cae19d40d76c9c0c845f93e7bd9021b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813491"
---
# App-V 5.0 の高可用性の計画


Microsoft Application Virtualization 5.0 (App-v 5.0) システム構成は、利用可能な高レベルのサービスを維持するオプションを利用できます。

次のセクションの情報を使用して、高可用性構成で App-v 5.0 を展開するオプションについて理解してください。

-   [Microsoft SQL Server クラスタリングのサポート](#bkmk-sqlcluster)

-   [IIS ネットワーク負荷分散のサポート](#bkmk-iisloadbal)

-   [(SCS) モードでのクラスター化されたファイルサーバーのサポート](#bkmk-clusterscsmode)

-   [Microsoft SQL Server ミラーリングのサポート](#bkmk-sqlmirroring)

-   [Microsoft SQL Server が常にサポートされる](#bkmk-sqlalwayson)

## <a href="" id="bkmk-sqlcluster"></a>Microsoft SQL Server クラスタリングのサポート


Microsoft SQL Server クラスターを実行しているコンピューターで、App-v 管理データベースとレポートデータベースを実行できます。 ただし、スクリプトを使用してデータベースをインストールする必要があります。

手順については、「 [SQL スクリプトを使用して App-v データベースを展開する方法](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md)」を参照してください。

## <a href="" id="bkmk-iisloadbal"></a>IIS ネットワーク負荷分散のサポート


インターネットインフォメーションサービス (IIS) のネットワーク負荷分散を使って、アプリを実行しているコンピューターに対して可用性の高い環境を構成することができます。これは、IIS によって展開される、管理、公開、レポートサービスです。

Windows Server オペレーティングシステムを実行しているコンピューターで IIS とネットワーク負荷分散を構成する方法については、次の情報を参照してください。

-   インターネットインフォメーションサービス (IIS) 7.0 の構成について説明します。

    [高可用性とスケーラビリティを実現する-ARR と NLB](https://go.microsoft.com/fwlink/?LinkId=316369) (https://go.microsoft.com/fwlink/?LinkId=316369)

-   Microsoft Windows Server の構成

    [ネットワーク負荷分散](https://go.microsoft.com/fwlink/?LinkId=316370)( https://go.microsoft.com/fwlink/?LinkId=316370) .

    この情報は、Windows Server2008、Windows Server2008R2、または Windows Server2012 の IIS ネットワーク負荷分散 (NLB) クラスターにも適用されます。

    **注** Windows Server2012 の IIS ネットワーク負荷分散機能は、通常、Windows Server2008R2 と同じです。 ただし、一部のタスクの詳細は Windows Server2012 で変更されています。 新しいタスクを実行する方法については、「 [Windows server 2012 R2 Preview の一般的な管理タスクとナビゲーション」および「Windows server 2012](https://go.microsoft.com/fwlink/?LinkId=316371) (」を参照してください https://go.microsoft.com/fwlink/?LinkId=316371) 。

     

## <a href="" id="bkmk-clusterscsmode"></a>(SCS) モードでのクラスター化されたファイルサーバーのサポート


クラスター化されたファイルサーバーを使用して、共有コンテンツストア (SCS) モードでの App-v 5.0 の実行がサポートされています。

この構成を有効にするには、次の手順を使用します。

-   クライアント SCS モードで実行するようにアプリ-V 5.0 を構成します。 App-v 5.0 SCS モードの構成の詳細については、「[共有コンテンツストアモード用に app-v 5.0 クライアントをインストールする方法](how-to-install-the-app-v-50-client-for-shared-content-store-mode.md)」を参照してください。

-   Microsoft Server2012 scale out モードとプレ**2012**モードの両方で構成されているファイルサーバークラスターを仮想 SAN で構成します。

次の手順を使用して、構成を検証することができます。

1.  公開サーバーにパッケージを追加します。 パッケージの追加の詳細については、「[管理コンソールを使用してパッケージを追加またはアップグレードする方法](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)」を参照してください。

2.  App-v 5.0 クライアントを実行しているコンピューターで公開更新を実行し、アプリケーションを開きます。

3.  フェールオーバーが正常に動作するように、クラスターノードの中間公開の更新と中間ストリームを切り替えます。

Windows Server フェールオーバークラスターの構成の詳細については、以下を参照してください。

-   [チェックリスト: クラスター化されたファイルサーバーを作成する](https://go.microsoft.com/fwlink/?LinkId=316372)( https://go.microsoft.com/fwlink/?LinkId=316372) .

-   [Windows Server 2012 フェールオーバークラスター () でクラスターの共有ボリュームを使用](https://go.microsoft.com/fwlink/?LinkId=316373) https://go.microsoft.com/fwlink/?LinkId=316373) します。

## <a href="" id="bkmk-sqlmirroring"></a>Microsoft SQL Server ミラーリングのサポート


Microsoft SQL Server ミラーリング (app-v 5.0 management server データベースが2つの SQL Server インスタンスを使ってミラーリングされている場合は、app-v 5.0 management server データベースがサポートされます。

Microsoft SQL Server ミラーリングの構成の詳細については、次の情報を参照してください。

-   [方法: ミラーリング用のミラーデータベースの準備 (transact-sql)](https://go.microsoft.com/fwlink/?LinkId=316375) (https://go.microsoft.com/fwlink/?LinkId=316375)

-   [Windows 認証を使ってデータベースミラーリングセッションを確立する (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=316377) (https://go.microsoft.com/fwlink/?LinkId=316377)

次の手順を使用して、構成を検証することができます。

1.  Microsoft SQL Server ミラーリングセッションを開始します。

2.  新しいマスター Microsoft SQL Server インスタンスを指定するには、[**フェールオーバー** ] を選択します。

3.  フェールオーバー後も App-v 5.0 management server が予期したとおりに機能することを確認します。

管理サーバー上の接続文字列を変更して、**フェールオーバーパートナー = &lt; server2 &gt; **を含めることができます。 これは、ミラーのプライマリがセカンダリにフェールオーバーされた場合にのみ役立ちます。また、App-v 5.0 クライアントを実行しているコンピューターでは、再起動した後に新しい接続が行われます。

次の手順を使用して、**フェイルオーバーパートナー = &lt; server2 &gt; **を含むように接続文字列を変更します。

**重要** このトピックでは、レジストリエディターを使用して Windows レジストリを変更する方法について説明します。 Windows レジストリを誤って変更した場合、Windows の再インストールが必要になる可能性のある重大な問題が発生する可能性があります。 レジストリを変更する前に、レジストリファイル (system.dat とユーザー) のバックアップコピーを作成しておく必要があります。 Microsoft は、レジストリを変更したときに発生する可能性のある問題を解決できないことを保証できません。 レジストリは、自分の責任において変更してください。

 

1.  管理サーバーにログインして、 **regedit**を開きます。

2.  ウイルス対策**\ _LOCAL \ _MACHINE**  \\  **Software**  \\  **Microsoft**  \\  **AppV**  \\  **Server**  \\  **ManagementService**に移動します。

3.  **フェールオーバーパートナー = &lt; &gt; server2**を使用して、**管理 \ _SQL \ _CONNECTION \ _STRING**の値を変更します。

4.  IIS コンソールを使用して、管理サービスを再起動します。

    **注** Microsoft sql Server 2012 で利用可能な**AlwaysOn**機能により、データベースのミラーリングは、Microsoft sql Server2012 の廃止されたデータベースエンジン機能の一覧にあります。

     

詳細については、次のリンクをクリックしてください。

-   [方法: ミラーリング用のミラーデータベースの準備 (transact-sql)](https://go.microsoft.com/fwlink/?LinkId=394235) ( https://go.microsoft.com/fwlink/?LinkId=394235) .

-   [方法: データベースミラーリングセッションを構成する (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=394236) ( https://go.microsoft.com/fwlink/?LinkId=394236) .

-   [Windows 認証を使ってデータベースミラーリングセッションを確立する (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=394237) ( https://go.microsoft.com/fwlink/?LinkId=394237) .

-   [SQL Server 2012 () で廃止されたデータベースエンジンの機能](https://go.microsoft.com/fwlink/?LinkId=394238) https://go.microsoft.com/fwlink/?LinkId=394238)

## <a href="" id="bkmk-sqlalwayson"></a>Microsoft SQL Server のサポートは常に構成される


App-v 5.0 management server データベースは、 **[常に**構成する (Microsoft SQL server) を実行しているコンピューターへの展開をサポートします。

## 関連トピック


[App-V の展開計画](planning-to-deploy-app-v.md)

 

 





