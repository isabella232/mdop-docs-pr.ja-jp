---
title: スタンドアロン構成での MBAM 2.5 の展開
description: スタンドアロン構成で MBAM 2.5 を展開する方法について説明します。
author: Deland-Han
ms.reviewer: dcscontentpm
manager: dansimp
ms.author: delhan
ms.sitesec: library
ms.prod: w10
ms.date: 09/16/2019
ms.openlocfilehash: 1ceccf3973bb131484f91917c2b80cd676d1c31b
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910472"
---
# <a name="deploying-mbam-25-in-a-standalone-configuration"></a>スタンドアロン構成での MBAM 2.5 の展開

この記事では、Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 をスタンドアロン構成にインストールする手順について説明します。 このガイドでは、2 サーバー構成を使用します。 2 つのサーバーの 1 つは、2012 年から 2012 年Microsoft SQL Serverされます。 このサーバーは MBAM データベースとレポートをホストします。 追加のサーバーは、「管理Windows Server 2012サーバー」と「セルフサービス ポータル」をホストする Web サーバーになります。

## <a name="preparation-steps-before-installing-mbam-25-server-software"></a>MBAM 2.5 サーバー ソフトウェアをインストールする前の準備手順

### <a name="step-1-installation-and-configuration-of-servers"></a>手順 1: サーバーのインストールと構成

MBAM 2.5 の構成を開始する前に、両方のサーバーが MBAM システム要件に従って構成されていることを確認する必要があります。 [「MBAM 最小システム要件」を参照し](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-supported-configurations#-mbam-server-system-requirements)、これらの要件を満たす構成を選択します。 

#### <a name="step-11-deploying-prerequisites-for-database-and-reporting-server"></a>手順 1.1: データベースサーバーとレポート サーバーの前提条件を展開する

1. Server 2008 R2 (Windows以降) オペレーティング システムを実行しているサーバーをインストールして構成します。

2. 3.0 Windows PowerShellインストールします。

3. 最新Microsoft SQL Server含む 2008 R2 以降のバージョンをインストールします。 MBAM 用に SQL Server の新しいインスタンスをインストールする場合は、インストールする SQL Server に SQL_Latin1_General_CP1_CI_AS 照合順序が含まれる必要があります。 次の機能をインストールするSQL Serverがあります。

    * データベース エンジン
    * Reporting Services
    * クライアント ツールの接続
    * 管理ツール – 完了

    > [!Note]
    > 必要に応じて、Transparent Data Encryption [(TDE)](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-security-considerations)機能をインストールSQL Server。

    SQL Server Reporting Services未構成モードまたは "SharePoint" モードではなく、"ネイティブ" モードでインストールおよび構成する必要があります。

    ![必要なSQL Server機能。](images/deploying-MBAM-1.png)

4. 管理および監視 Web サイトに SSL を使用する場合は、管理および監視 Web サイトを構成する前に、SQL Server Reporting Services (SSRS) が Secure Sockets Layer (SSL) プロトコルを使用する構成を行う必要があります。 それ以外の場合、レポート機能は暗号化 (HTTPS) ではなく暗号化されていない (HTTP) データ トランスポートを使用します。

    [ネイティブ モード [のレポート サーバーで SSL 接続](https://docs.microsoft.com/sql/reporting-services/security/configure-ssl-connections-on-a-native-mode-report-server?view=sql-server-2017) を構成する] に従って、レポート サーバーで SSL を構成できます。
    
    > [!Note]
    > それぞれのバージョンのインストール SQL Serverガイドに従って、SQL ServerインストールSQL Server。 リンクは次のとおりです。
        > * [SQL Server 2014](https://docs.microsoft.com/sql/sql-server/install/planning-a-sql-server-installation?view=sql-server-2014)
        > * [SQL Server 2012](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/bb500442(v=sql.110))
        > * [SQL Server 2008 R2](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/bb500442(v=sql.110))

5. SQL Server のインストール後に、SQL Server でユーザー アカウントをプロビジョニングし、データベース サーバーで MBAM データベースとレポートの役割を構成するユーザーに次のアクセス許可を割り当てます。

    インスタンスのロールは次SQL Server。
        
    * dbcreator
    * processadmin

    次のオブジェクトのインスタンスSQL Server Reporting Services。
    
    * フォルダーの作成
    * レポートの発行

データベース サーバーで MBAM 2.5 の役割を構成する準備ができました。 次のサーバーに移動します。

#### <a name="step-12-deploying-prerequisites-for-administration-and-monitoring-server"></a>手順 1.2: 管理サーバーと監視サーバーの前提条件を展開する

MBAM システム要件のドキュメントで説明されているハードウェア構成を満たす [サーバーを選択します](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-supported-configurations#-mbam-server-system-requirements)。 サーバー 2008 R2 Windows以降のオペレーティング システムと最新のサービス パックと更新プログラムを組み合わせて実行している必要があります。 サーバーの準備が整った後、次の役割と機能をインストールします。

##### <a name="roles"></a>ロール

* Web サーバー (IIS) 管理ツール ([IIS 管理スクリプトとツールの選択])

* Web サーバーの役割サービス

    * 一般的な HTTP 機能<br />
      静的コンテンツ<br />
      既定のドキュメント

    * アプリケーションの開発<br />
      ASP.NET<br />
      .NET 機能拡張<br />
      ISAPI 拡張機能<br />
      ISAPI フィルター<br />
      セキュリティ<br />
      Windows 認証<br />
      要求フィルター

    * Web サービス IIS 管理ツール

##### <a name="feature"></a>機能

* .NET Framework 4.5 の機能
  
  * Microsoft .NET Framework 4.5
  
    R2 Windows Server 2012またはWindows Server 2012、.NET Framework 4.5 は、これらのバージョンの Windows Server 用にWindowsされています。 ただし、有効にする必要があります。
  
    Windows サーバー 2008 R2 の場合.NET Framework 4.5 は、Windowsサーバー 2008 R2 には含まれません。 したがって、4.5 .NET Frameworkダウンロードして個別にインストールする必要があります。
  
  * WCF ライセンス認証<br />
    HTTP ライセンス認証<br />
    非 HTTP ライセンス認証
  
  * TCP ライセンス認証
  
  * Windowsプロセス ライセンス認証サービス:<br />
    プロセス モデル<br />
    .NET Framework環境<br />
    構成 API

セルフサービス ポータルを機能するには[、MVC 4.0](https://go.microsoft.com/fwlink/?linkid=392271)をダウンロードして ASP.NET インストールする必要があります。

次の手順では、Active Directory で必要な MBAM ユーザーとグループを作成します。

### <a name="step-2-creating-users-and-groups-in-active-directory-domain-services"></a>手順 2: Active Directory ドメイン サービスでのユーザーとグループの作成
 
前提条件の一部として、MBAM で使用される特定の役割とアカウントを定義して、SQL Server のインスタンスで実行されているデータベースや管理および監視サーバーで実行されている Web アプリケーションなど、特定のサーバーと機能にセキュリティとアクセス権を提供する必要があります。

Active Directory で次のグループとユーザーを作成します。 (グループとユーザーには任意の名前を使用できます)。ユーザーは、より大きなユーザー権限を持つ必要はない。 ドメイン ユーザー アカウントで十分です。 MBAM 2.5 の構成時に、これらのグループの名前を指定する必要があります。

* **MBAMAppPool**  

  **種類**: ドメイン ユーザー

  **説明**: コンプライアンスおよび監査データベースと回復データベースに対する読み取りまたは書き込みアクセス許可を持つドメイン ユーザーが、Web アプリケーションがこれらのデータベース内のデータとレポートにアクセスできます。 また、Web アプリケーションのアプリケーション プールでも使用されます。

  **アカウントの役割 (MBAM の構成時) :**

  1. Web サービス アプリケーション プール ドメイン アカウント

  2. レポートのコンプライアンスと監査データベースと回復データベースの読み取り/書き込みユーザー

* **MBAMROUser**

  **種類**: ドメイン ユーザー

  **説明**: コンプライアンスデータベースと監査データベースRead-Onlyアクセスして、レポートがこのデータベースのコンプライアンスデータと監査データにアクセスできるドメイン ユーザー。 また、コンプライアンスと監査データベースへのアクセスにローカル SQL Server Reporting Services使用するドメイン ユーザー アカウントになります。

  **アカウントの役割 (MBAM の構成時) :**

  1. レポートのコンプライアンスと監査データベースの読み取り専用ユーザー

  2. コンプライアンスとデータベースのドメイン ユーザー アカウントの監査

* **MBAMAdvHelpDsk**

  **種類**: ドメイン グループ

  **説明**: MBAM Advanced Helpdesk Users access group: メンバーが管理および監視 Web サイトのすべての領域にアクセスできるドメイン ユーザー グループ。 この役割を持つユーザーは、ユーザーがドライブの回復を支援するときに、ユーザーのドメインとユーザー名ではなく、回復キーのみを入力する必要があります。 ユーザーが MBAM ヘルプデスク ユーザー グループと MBAM Advanced Helpdesk Users グループの両方のメンバーである場合、MBAM Advanced Helpdesk Users グループのアクセス許可は MBAM ヘルプデスク グループのアクセス許可を上書きします。

  **アカウントの役割 (MBAM の構成時)**: MBAM Advanced Helpdesk Users

* **MBAMHelpDsk**

  **種類**: ドメイン グループ

  **説明**: MBAM ヘルプデスク ユーザー アクセス グループ: MBAM 管理および監視 Web サイトの [TPM とドライブの回復の管理] 領域にメンバーがアクセスできるドメイン ユーザー グループ。 この役割を持つユーザーは、いずれかのオプションを使用する場合、すべてのフィールドに入力する必要があります。 これには、ユーザーのドメイン名とアカウント名が含まれます。

  **アカウントの役割 (MBAM の構成時)**: MBAM ヘルプデスク ユーザー

* **MBAMRUGrp**

  **種類**: ドメイン グループ

  **説明**: メンバーが管理および監視 Web サイトの [レポート] 領域のレポートに読み取り専用アクセス権を持つドメイン ユーザー グループ。

  **アカウントの役割 (MBAM の構成時) :**

  1. レポートの読み取り専用ドメイン アクセス グループ

  2. MBAM レポート ユーザー アクセス グループ

### <a name="step-3-optional-configure-and-install-ssl-certificate-on-administration-and-monitoring-server"></a>手順 3 (オプション): 管理サーバーと監視サーバーに SSL 証明書を構成してインストールする

省略可能ですが、MBAM クライアントと管理および監視 Web サイトと Self-Service ポータル Web サイトとの間の通信をセキュリティで保護するために証明書を使用することを強くお勧めします。 セキュリティ上の明らかな理由から、自己署名証明書を使用することをお勧めしません。 信頼できる証明機関の Web サーバーの種類証明書を使用してください。 これを行うには、KB の [証明機関によって承認された証明書の使用] セクションを[参照2754259。](https://support.microsoft.com/help/2754259)

証明書が発行された後、管理および監視サーバーの個人用ストアに証明書を追加する必要があります。 証明書を追加するには、ローカル コンピューター上の証明書ストアを開きます。 これを行うには、次の手順を実行します。

1. [スタート] を右クリックし、[実行] を選択します。

   ![[選択] を選択します。](images/deploying-MBAM-2.png)

2. "MMC.EXE" (二重引用符なし) と入力し **、[OK] を選択します**。

   ![[実行] ボックス。](images/deploying-MBAM-3.png) 

3. 開 **いた新** しい MMC で [ファイル] を選択し、[スナップインの追加と削除] **を選択します**。
   
   ![[選択] を選択します。](images/deploying-MBAM-4.png)

4. [証明書] **スナップインを** 強調表示し、[追加] を **選択します**。

   ![[スナップインの追加と削除] ウィンドウ。](images/deploying-MBAM-5.png)

5. [コンピューター アカウント **] オプションを** 選択し、[次へ] を **選択します**。
   
   ![証明書スナップイン ウィンドウ。](images/deploying-MBAM-6.png)

6. 次の **画面で [** ローカル コンピューター] を選択し、[完了] を **選択します**。
   
   ![[コンピューター] ウィンドウを選択します。](images/deploying-MBAM-7.png)

7. これで、証明書スナップインが追加されました。 これにより、コンピューターの証明書ストア内の証明書を使用できます。

   ![[スナップインの追加と削除] ウィンドウ。](images/deploying-MBAM-8.png)

8. Web サーバー証明書をコンピューターの証明書ストアにインポートします。

   証明書スナップインにアクセスできるので、Web サーバー証明書をコンピューターの証明書ストアにインポートできます。 これを行うには、次の手順に従います。

9. 証明書 (ローカル コンピューター) スナップインを開き、[個人用****] と [証明書]**の順に参照します**。
   
   ![証明書 (ローカル コンピューター) スナップイン ウィンドウ。](images/deploying-MBAM-9.png)

   > [!Note]
   > 証明書スナップインが表示されない場合があります。 インストールされていない場合、証明書はインストールされません。

10. [証明書] を**右クリックし、[****すべてのタスク] を**選択し、[インポート] を**選択します**。

    ![証明書 (ローカル コンピューター) スナップイン ウィンドウ。](images/deploying-MBAM-10.png)

11. ウィザードが起動したら、[次へ] を **選択します**。 サーバー証明書とプライベート キーを含む作成したファイルを参照し、[次へ] を選択 **します**。

    ![[証明書のインポート ウィザード] ウィンドウ。](images/deploying-MBAM-11.png)

12. ファイルの作成時にパスワードを指定した場合は、パスワードを入力します。

   ![パスワード ウィンドウを入力します。](images/deploying-MBAM-12.png)

   > [!Note]
   > このコンピューター **からキー** ペアを再度エクスポートする場合は、[キーをエクスポート可能としてマークする] オプションが選択されている必要があります。 追加のセキュリティ対策として、このオプションをオフのままにして、誰も自分のプライベート キーのバックアップを作成しきれない場合があります。
 
13. [ **次へ**] を選択し、証明書 **を** 保存する証明書ストアを選択します。

    ![[証明書のインポート ウィザード] ウィンドウ。](images/deploying-MBAM-13.png)

    > [!Note]
    > Web サーバー証明書 **なので、[** 個人用] を選択する必要があります。 証明書を証明書階層に含める場合は、このストアにも追加されます。
 
14. [次 **へ] を**選択し、[完了] を **選択します**。

    ![[証明書のインポート ウィザード] ウィンドウ。](images/deploying-MBAM-14.png)

これで、Web サーバーのサーバー証明書が [個人証明書] リストに表示されます。 サーバーの共通名で示されます。 (これは、証明書の件名セクションで確認できます)。

詳細については、次の情報を参照してください。

[MBAM 2.5 のセキュリティに関する考慮事項](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-security-considerations)

[MBAM Web サイトをセキュリティで保護する方法の計画](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites)

次の手順では、アプリケーション プール アカウントのサービス原則名を登録します。

### <a name="step-4-configuring-ssl-certificate-for-mbam-web-server"></a>手順 4: MBAM Web Server の SSL 証明書を構成する

クライアントとサーバーの間で SSL 通信を使用している場合は、証明書に拡張キー使用法 OID (1.3.6.1.5.5.7.3.1) と (1.3.6.1.5.5.7.3.2) が設定されている必要があります。 つまり、サーバー認証とクライアント認証が追加されている必要があります。

サービス URL を参照しようとするときに証明書エラーが表示された場合、別の名前に発行された証明書を使用している場合、または正しくない URL を使用して参照している場合。

ブラウザーから証明書のエラー メッセージが表示される場合がありますが、続行できますが、MBAM Web サービスは証明書エラーを無視し、接続をブロックします。 MBAM クライアントの MBAM Admin イベント ログに証明書関連のエラーが表示されます。 エイリアスを使用して管理および監視サーバーに接続する場合は、エイリアス名に証明書を発行する必要があります。 つまり、証明書のサブジェクト名はエイリアス名で、ローカル サーバーの DNS 名を証明書の [サブジェクトの別名]**** フィールドに追加する必要があります。

例:

仮想名が "bitlocker.contoso.com" で、MBAM 管理および監視サーバー名が "adminserver.contoso.com" の場合は、証明書を bitlocker.contoso.com (サブジェクト名) に発行し、adminserver.contoso.com を証明書の [サブジェクトの代替**** 名] フィールドに追加する必要があります。

同様に、ロード バランサーを使用して負荷のバランスを取る複数の管理サーバーと監視サーバーがインストールされている場合は、仮想名に SSL 証明書を発行する必要があります。 つまり、証明書のサブジェクト名フィールドに仮想名を設定し、すべてのローカル サーバーの名前を証明書の [サブジェクトの代替名]**** フィールドに追加する必要があります。

例:

仮想名が "bitlocker.contoso.com" で、サーバーが "adminserver1.contoso.com" と "adminiserver2.contoso.com" の場合は、証明書を bitlocker.contoso.com (サブジェクト名) と adminserver1.contoso.com に発行し、adminiserver2.contoso.com を証明書の [サブジェクトの代替名]**** フィールドに追加する必要があります。

MBAM を使用して SSL 通信を構成する手順については、サポート技術情報の記事 [「KB](https://support.microsoft.com/help/2754259)2754259。

### <a name="step-5-register-spns-for-the-application-pool-account-and-configure-constrained-delegation"></a>手順 5: アプリケーション プール アカウントに SPNS を登録し、制約付き委任を構成する

> [!Note]
> 制約付き委任は 2.5 でのみ必要であり、2.5 Service Pack 1 以降では必要ありません。

MBAM サーバーが管理および監視 Web サイトと Self-Service ポータルからの通信を認証するには、Web アプリケーション プールで使用しているドメイン アカウントのホスト名にサービス プリンシパル名 (SPN) を登録する必要があります。 次の記事では、SPN を登録するための手順について説明します。MBAM Web サイトをセキュリティで保護する方法 [を計画する](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites)

SPN を構成した後、SPN に制約付き委任を設定する必要があります。 これを行うには、次の手順を実行します。

1. [Active Directory] に移動し、前の手順で MBAM Web サイト用に構成したアプリ プール資格情報を検索します。

2. 資格情報を右クリックし、[プロパティ] を **選択します**。

3. [委任] **タブを** 選択します。

4. Kerberos 認証のオプションを選択します。

5. [ **参照]** を選択し、アプリ プールの資格情報を再度参照します。 その後、アプリ プール creds アカウントでセットアップされているすべての SPN が表示されます。 (SPN は"http/bitlocker.fqdn.com"に似ている必要があります)。 MBAM のインストール時に指定したホスト名と同じ SPN を強調表示します。

6. **[OK]** を選択します。

これで、前提条件が満たされます。 次の手順では、MBAM ソフトウェアをサーバーにインストールして構成します。

## <a name="installing-and-configuring-mbam-25-server-software"></a>MBAM 2.5 サーバー ソフトウェアのインストールと構成

### <a name="step-6-install-mbam-25-server-software"></a>手順 6: MBAM 2.5 サーバー ソフトウェアをインストールする 

データベース サーバーと管理サーバーと監視サーバーの両方で Microsoft BitLocker 管理および監視セットアップ ウィザードを使用して MBAM Server ソフトウェアをインストールするには、次の手順を実行します。

1. MBAM をインストールするサーバーで、Microsoft BitLocker のMBAMserversetup.exe監視セットアップ ウィザードを起動します。

2. [ようこそ] ページで、[次へ] を **選択します**。

3. Microsoft ソフトウェア 使用許諾契約書を読んで同意し、[次へ] を選択 **して** インストールを続行します。

4. 更新プログラムを確認するときに Microsoft Update を使用するかどうかを決定し、[次へ] を **選択します**。

5. カスタマー エクスペリエンス向上プログラムに参加するかどうかを決定し、[次へ] を **選択します**。

6. インストールを開始するには、[インストール] を **選択します**。

7. MBAM Server ソフトウェアのインストールが完了した後にサーバー機能を構成するには、[ウィザードを閉じて **から MBAM サーバー** 構成を実行する] チェック ボックスをオンにします。 または、サーバー インストールによって [スタート] メニューに作成される **MBAM サーバー** 構成ショートカットを使用して、後で MBAM を **構成** できます。

8. [完了 **] を選択します**。

詳細については [、「MBAM 2.5 Server Software のインストール」を参照してください](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software)。

### <a name="step-7-configure-mbam-25-database-and-reports-role"></a>手順 7: MBAM 2.5 データベースとレポートの役割を構成する

この手順では、MBAM ウィザードを使用して MBAM 2.5 データベースとレポート コンポーネントを構成します。

1. ウィザードを使用して、コンプライアンスデータベースと監査データベースと回復データベースを構成します。
   
   1. データベースを構成するサーバーで **、MBAM Server 構成ウィザードを起動します**。 [スタート] メニュー **の [MBAM サーバー構成** ] **を選択** して、ウィザードを開きます。

   2. [ **新機能の追加] を選択**し、[ **コンプライアンスと監査データベース]**、[ **回復データベースとレポート**] の順に選択し、[次へ] を **選択します**。 ウィザードは、データベースのすべての前提条件が満たされていることを確認します。

   3. 前提条件の確認が成功した場合は、[次へ] **を選択して** 続行します。 それ以外の場合は、不足している前提条件を解決し、[前提条件の確認] **を再度選択します**。
   
   4. 次の説明を使用して、ウィザードにフィールド値を入力します。

2. コンプライアンスと監査データベース

   |フィールド   |説明|
   |-------|-------|
   |SQL Server名 |コンプライアンスデータベースと監査データベースを構成するサーバーの名前。 <br /> コンプライアンス と監査データベース コンピューターに例外を追加して、受信受信トラフィックを受信ポートSQL Serverがあります。 既定のポート番号は 1433 です。|
   |SQL Server データベース インスタンス    |コンプライアンスおよび監査データが格納されるデータベース インスタンスの名前。 既定のインスタンスを使用している場合は、このフィールドを空白のままにする必要があります。 また、データベース情報の場所を指定する必要があります。|
   |データベース名   |コンプライアンス データを格納するデータベースの名前。 後の手順でこの情報を提供する必要がある場合は、ここで指定するデータベースの名前に注意する必要があります。|
   |読み取り/書き込みアクセス許可ドメイン のユーザーまたはグループ  |手順 2 で構成されている MBAMAppPool ユーザーの名前を指定します。|
   |読み取り専用アクセス ドメイン ユーザーまたはグループ   |手順 2 で構成されている MBAMROUser ユーザーの名前を指定します。|

3. 回復データベース。

   |フィールド   |説明|
   |-----|-----|
   |SQL Server名 |回復データベースを構成するサーバーの名前。 回復データベース コンピューターに例外を追加して、受信トラフィックを受信ポートで有効SQL Serverがあります。 既定のポート番号は 1433 です。|
   |SQL Server データベース インスタンス    |回復データが格納されるデータベース インスタンスの名前。 既定のインスタンスを使用している場合は、このフィールドを空白のままにする必要があります。 また、データベース情報の場所を指定する必要があります。|
   |データベース名   |回復データを格納するデータベースの名前。|
   |読み取り/書き込みアクセス許可ドメイン のユーザーまたはグループ  |このデータベースに対する読み取り/書き込みアクセス許可を持つドメイン ユーザーまたはグループ。 <br />このフィールドにユーザーを入力する場合は、[Web アプリケーションの構成] ページの **[Web サービス** アプリケーション プール ドメイン アカウント] フィールドの値と同じ **値である必要** があります。 <br />このフィールドにグループを入力する場合 **、[Web**アプリケーションの構成] ページの **[Web サービス**アプリケーション プール ドメイン アカウント] フィールドの値は、このフィールドに入力するグループのメンバーである必要があります。|
   
   エントリが完了したら、[次へ] を **選択します**。 ウィザードは、データベースのすべての前提条件が満たされていることを確認します。
   
   前提条件の確認が成功した場合は、[次へ] **を選択して** 続行します。 それ以外の場合は、不足している前提条件を解決し、もう一度 [次へ] **を選択** します。

4. レポート。

   |フィールド   |説明|
   |----|----|
   |SQL Server Reporting Servicesインスタンス  |レポートがSQL Server Reporting Servicesする場所のインスタンス。 既定のインスタンスを使用している場合は、このフィールドを空白のままにする必要があります。|
   |レポート役割ドメイン グループ |手順 2 で説明したように、MBAMRUGrp の名前を指定します。|
   |SQL Server名 |コンプライアンスデータベースと監査データベースが構成されているサーバーの名前。|
   |SQL Server データベース インスタンス    |コンプライアンスおよび監査データが構成されているデータベース インスタンスの名前。 既定のインスタンスを使用している場合は、このフィールドを空白のままにする必要があります。 <br />レポート サーバーのポートで受信トラフィックを有効にするには、レポート コンピューターに例外を追加する必要があります。 (既定のポートは 80 です)。|
   |データベース名|  コンプライアンスデータベースと監査データベースの名前。 既定では、データベース名は MBAM コンプライアンス状態です。|
   |コンプライアンスとデータベースの監査ドメイン アカウント    |手順 2 で構成されている MBAMROUser ユーザーの名前を指定します。|
   
   エントリが完了したら、[次へ] を **選択します**。 ウィザードは、レポート機能のすべての前提条件が満たされていることを確認します。 続行するには、[次へ] を選択します。 [概要 **] ページ** で、追加する機能を確認します。
   
   詳細については [、「MBAM 2.5 データベース](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases)を構成する方法」を参照してください。

### <a name="step-8-configure-the-mbam-25-web-applications-role"></a>手順 8: MBAM 2.5 Web アプリケーションの役割を構成する

1. Web アプリケーションを構成するサーバーで、MBAM Server 構成ウィザードを起動します。 [スタート] メニュー **の [MBAM サーバー構成** ] **を選択** して、ウィザードを開きます。

2. [ **新機能の追加] を選択し**、[ **管理と監視の Web サイト** と **セルフサービス**ポータル] を選択し、[次へ] を **選択します**。 ウィザードは、データベースのすべての前提条件が満たされていることを確認します。

3. 前提条件の確認が成功した場合は、[次へ] **を選択して** 続行します。 それ以外の場合は、不足している前提条件を解決し、[前提条件の確認] **を再度選択します**。

4. ウィザードにフィールド値を入力するには、次の説明を使用します。

   |フィールド   |説明|
   |-----|-----|
   |セキュリティ証明書    |手順 3 で以前に作成した証明書を選択して、必要に応じて、管理および監視 Web サイトを構成する Web サービスとサーバー間の通信を暗号化します。 [証明書を使用しない] を選択すると、Web 通信が安全ではない可能性があります。|
   |ホスト名   |管理および監視 Web サイトを構成するホスト コンピューターの名前。 <br />コンピューターのホスト名である必要はありません。何でも可能です。 ただし、ホスト名がコンピューターの netbios 名と異なる場合は、A レコードを作成し、SPN が netbios 名ではなくカスタム ホスト名を使用する必要があります。 これは、負荷分散シナリオで一般的です。|
   |インストール パス   |管理および監視 Web サイトをインストールするパス。|
   |Port    |Web サイトの通信に使用するポート番号。 <br /> 指定したポートを介した通信を有効にするには、ファイアウォール例外を設定する必要があります。|
   |Web サービス アプリケーション プールのドメイン アカウントとパスワード    |手順 2 で構成されている MBAMAppPool ユーザーのユーザー アカウントとパスワードを指定します。 <br /> セキュリティを強化するには、資格情報で指定されているアカウントに制限されたユーザー権限を設定します。 また、アカウントのパスワードを有効期限が切れることはありません。|

5. 組み込みの IIS_IUSRS またはアプリケーション プール アカウントが認証後にクライアントを偽装し****、バッチ ジョブとしてログオンするローカル**** セキュリティ設定に追加されたのを確認します。

   アカウントがローカル セキュリティ設定に追加されたかどうかを確認するには、ローカル セキュリティ**** ポリシー エディターを開き、[ローカル ポリシー] ノードを**** 展開し、[ユーザー権利の割り当て] ノードを選択し****、認証後にクライアントを偽装し、右側のウィンドウで [ログオン] をバッチ ジョブ ポリシーとしてダブルクリックします。 **** ****

6. コンプライアンス データベースと監査データベースの接続情報をウィザードで構成するには、次のフィールドの説明を使用します。
   |フィールド   |説明|
   |------|------|
   |SQL Server名 |コンプライアンスデータベースと監査データベースが構成されているサーバーの名前。|
   |SQL Server データベース インスタンス    |コンプライアンス データベースと監査データベースSQL Server構成されているインスタンス (たとえば \<Server Name\> ) の名前。 既定のインスタンスを使用している場合は、この値を空白のままにします。|
   |データベース名   |コンプライアンスデータベースと監査データベースの名前。 既定では、"MBAM コンプライアンスの状態" です。|

7. 回復データベースのウィザードで接続情報を構成するには、次のフィールドの説明を使用します。
   |フィールド   |説明|
   |----|----|
   |SQL Server名 |回復データベースが構成されているサーバーの名前。|
   |SQL Server データベース インスタンス    |復旧データベースが構成されているSQL Serverインスタンス (たとえば \<Server Name\> ) の名前。 既定のインスタンスを使用している場合は、この値を空白のままにします。|
   |データベース名   |回復データベースの名前。 既定では、"MBAM の回復とハードウェア" です。|

8. 管理および監視 Web サイトを構成するには、次の説明を使用してウィザードにフィールド値を入力します。
   |フィールド   |説明|
   |----|----|
   |高度なヘルプデスク役割ドメイン グループ |手順 2 で構成されている MBAMAdvHelpDsk グループの名前を指定します。|
   |ヘルプデスクの役割ドメイン グループ  |手順 2 で構成されている MBAMHelpDsk グループの名前を指定します。|
   |統合System Center Configuration Manager使用 |このチェック ボックスをオフにします。     |
   |レポート役割ドメイン グループ |手順 2 で構成されている MBAMRUGrp グループの名前を指定します。    |
   |SQL Server Reporting ServicesURL   |MBAM レポートが構成されている SSRS サーバーの Web サービス URL を指定します。 この情報は、データベース サーバーの Reporting Services Configuration Manager にログインすることで確認できます。 <br /> 完全修飾ドメイン名の例: https://MyReportServer.Contoso.com/ReportServer <br />カスタム ホスト名の例: https://MyReportServer/ReportServer|
   |仮想ディレクトリ   |管理および監視 Web サイトの仮想ディレクトリ。 この名前は、サーバー上の Web サイトの物理ディレクトリに対応し、Web サイトのホスト名に追加されます。 以下に例を示します。 <br />http(s):// *\<host name\>* : *\<port\>* /HelpDesk/ <br />仮想ディレクトリを指定しない場合は、値 HelpDesk が使用されます。     |

9. 次の説明を使用して、ウィザードにフィールド値を入力し、ポータルのSelf-Serviceします。

   |フィールド   |説明|
   |----|----|
   |仮想ディレクトリ   |Web アプリケーションの仮想ディレクトリ。 この名前は、サーバー上の Web サイトの物理ディレクトリに対応し、Web サイトのホスト名に追加されます。 以下に例を示します。<br />http(s):// *\<host name\>* : *\<port\>* /SelfService/<br /> 仮想ディレクトリを指定しない場合は、値 "SelfService" が使用されます。|

10. エントリが完了したら、[次へ] を **選択します**。 ウィザードは、Web アプリケーションのすべての前提条件が満たされていることを確認します。

11. [次 **へ] を** 選択して続行します。

12. [概要 **] ページ** で、追加する機能を確認します。

13. [ **追加]** を選択して Web アプリケーションをサーバーに追加し、[閉じる] を **選択します**。

## <a name="customizing-and-validating-steps-after-installing-mbam-25-server-software"></a>MBAM 2.5 サーバー ソフトウェアのインストール後の手順のカスタマイズと検証

### <a name="step-9-customizing-the-self-server-portal-for-your-organization"></a>手順 9: 組織のセルフ サーバー ポータルをカスタマイズする

カスタム通知テキスト、会社名、詳細へのポインターを追加して Self-Service ポータルをカスタマイズするには、「組織の Self-Service ポータルのカスタマイズ」を [参照してください](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/customizing-the-self-service-portal-for-your-organization)。
 
### <a name="step-10-configure-the-self-server-portal-if-client-computers-cannot-access-the-cdn"></a>手順 10: クライアント コンピューターがサーバーにアクセスできない場合は、セルフ サーバー ポータルを構成CDN 

クライアント コンピューターが Microsoft AJAX サーバーにアクセスできるかどうかを確認Content Delivery Network (CDN)。 このCDNは、Self-Service JavaScript ファイルに対して必要なアクセス権をポータルに提供します。 クライアント コンピューターが CDN にアクセスできない場合に Self-Service ポータルを構成しない場合は、会社名とユーザーがサインインしたアカウントだけが表示されます。 エラー メッセージは表示されません。

次のいずれかの操作を行います。

* クライアント コンピューターがクライアント コンピューターにアクセスできる場合CDN何も行いません。 ポータルSelf-Serviceが完了しました。

* クライアント コンピューターが CDN にアクセスできない場合は、「クライアント コンピューターが Microsoft CDN ポータルにアクセスできない場合に Self-Service ポータルを構成する方法」の手順に[従Content Delivery Network。](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network)

### <a name="step-11-validate-the-mbam-25-server-feature-configuration"></a>手順 11: MBAM 2.5 サーバー機能の構成を検証する 

MBAM Server の展開を検証してスタンドアロン トポロジを使用するには、次の手順を実行します。

1. MBAM 機能が展開されている各サーバーで、[コントロール パネル**** プログラム] を選択  >  ****  >  **** プログラムと機能。 Microsoft **BitLocker 管理と監視が** [管理] **リストに表示** プログラムと機能します。
   > [!Note]
   > 検証を実行するには、各サーバーにローカル コンピューターの管理資格情報を持つドメイン アカウントを使用する必要があります。

2. 回復データベースが構成されているサーバーで、データベースを開SQL Server Management Studio **MBAM Recovery and Hardware**データベースが構成されていることを確認します。

3. コンプライアンスデータベースと監査データベースが構成されているサーバーで、SQL Server Management Studioを開き、MBAM コンプライアンス状態データベースが構成されていることを確認します。

4. レポート機能が構成されているサーバー onm で、管理資格情報を使用して Web ブラウザーを開き、web ブラウザーを開き、SQL Server Reporting Services サイトのホームページを参照します。
   
   サイト インスタンスの既定のホームページSQL Server Reporting Services http(s):// *\<MBAM Reports Server Name\>* : *\<port\>* /Reports.aspx
   
   実際の URL を検索するには、Reporting Services Configuration Manager ツールを使用し、セットアップ時に指定したインスタンスを選択します。
   
5. Microsoft BitLocker Administration and Monitoring という名前のレポート フォルダーに、マルタDataSource という名前のデータ ソースが含まれているか確認します。 このデータ ソースには、言語のローカル (en-us など) を表す名前を持つフォルダーが含まれています。 レポートは言語フォルダーに含まれています。

   > [!Note]
   > 指定SQL Server Reporting Services (SSRS) が名前付きインスタンスとして構成されている場合、URL は http(s):// \<MBAM Reports Server Name\> : \<port\> /Reports_\<SSRS Instance Name\>
   >
   > SSRS が Secure Socket Layer (SSL) を使用するように構成されていない場合、MBAM サーバーをインストールすると、レポートの URL は "HTTPS" ではなく "HTTP" に設定されます。 その後、[管理と監視] Web サイト (ヘルプデスクとも呼ばれる) に移動してレポートを選択すると、「セキュリティで保護されたコンテンツだけが表示されます」というメッセージが表示されます。 レポートを表示するには、[すべてのコンテンツを表示 **] を選択します**。

6. 管理および監視 Web サイト機能が構成されているサーバーで、サーバー マネージャーを実行し****、[役割] を参照し **、[Web サーバー (IIS)** マネージャーインターネット インフォメーション サービス選択  >  **** します。

7. [**接続]** で、[サイトの Microsoft BitLocker 管理と監視] を参照 \<computer name\> ****  >  **して選択します**。 次のリストが表示されるのを確認します。

   * MBAMAdministrationService
   * MBAMComplianceStatusService
   * MBAMRecoveryAndHardwareService

8. 管理および監視 Web サイトとポータルが構成されているサーバーSelf-Service、管理資格情報を使用して Web ブラウザーを開きます。

9. 次の Web サイトを参照して、正常に読み込まれます。
   * https(s):// \<MBAM Administration Server Name\> : \<port\> /HelpDesk/ (ナビゲーションとレポートの各リンクを確認する)
   * http(s):// \<MBAM Administration Server Name\> : \<port\> /SelfService/

   > [!Note]
   > ネットワークの暗号化を行わずに、既定のポートでサーバー機能を構成したと見なされます。 別のポートまたは仮想ディレクトリでサーバー機能を構成した場合は、URL を変更して適切なポートを含める。 たとえば、http(s):// \<host name\> : \<port\> /HelpDesk/ http(s):// \<host name\> / \<port\> / \<virtualdirectory\> サーバー機能がネットワーク暗号化を使用するように構成されている場合は、http:// を https:// に変更します。
   
10. 次の Web サービスを参照して、正常に読み込まれます。 サービスが実行されているページが開きます。 ただし、ページにはメタデータは表示されます。

    * http(s):// \<MBAM Administration Server Name> : \<port> /MBAMAdministrationService/AdministrationService.svc
    * http(s):// \<MBAM Administration Server Name> : \<port> /MBAMUserSupportService/UserSupportService.svc
    * http(s):// \<MBAM Administration Server Name> : \<port> /MBAMComplianceStatusService/StatusReportingService.svc
    * http(s):// \<MBAM Administration Server Name> : \<port> /MBAMRecoveryAndHardwareService/CoreService.svc

### <a name="step-12-configure-the-mbam-group-policy-templates"></a>手順 12: MBAM グループ ポリシー テンプレートを構成する

MBAM を展開するには、BitLocker ドライブ暗号化の MBAM 実装設定を定義するグループ ポリシー設定を設定する必要があります。 このタスクを完了するには、MBAM グループ ポリシー テンプレートを、グループ ポリシー管理コンソール (GPMC) または Advanced Group Policy Management (AGPM) を実行できるサーバーまたはワークステーションにコピーし、設定を編集する必要があります。

> [!Important]
> **BitLocker**ドライブ暗号化ノードのグループ ポリシー設定を変更しないか、MBAM が正しく動作しません。 **MDOP MBAM (BitLocker 管理)** ノードでグループ ポリシー設定を構成すると、MBAM によって**BitLocker ドライブ**の暗号化設定が自動的に構成されます。
 
#### <a name="copying-the-mbam-25-group-policy-templates"></a>MBAM 2.5 グループ ポリシー テンプレートのコピー

MBAM クライアントをインストールする前に、MBAM 固有のグループ ポリシー オブジェクト (GPO) を管理ワークステーションにコピーする必要があります。 これらの GPO は、BitLocker の MBAM 実装設定を定義します。 グループ ポリシー テンプレートは、サポートされている Windows ベースのサーバーまたはクライアント コンピューターであり、グループ ポリシー管理コンソール (GPMC) または Advanced Group Policy Management (AGPM) を実行できる任意のサーバーまたはワークステーションにコピーできます。

詳細については [、「MBAM 2.5](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/copying-the-mbam-25-group-policy-templates)グループ ポリシー テンプレートのコピー」を参照してください。
 
#### <a name="editing-mbam-25-gpo-settings"></a>MBAM 2.5 GPO 設定の編集

必要な GPO を作成した後、MBAM グループ ポリシー設定を組織のクライアント コンピューターに展開する必要があります。 GPO を表示および作成するには、グループ ポリシー管理コンソール (GPMC) または Advanced Group Policy Management (AGPM) がインストールされている必要があります。

詳細については[、「MBAM 2.5](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/editing-the-mbam-25-group-policy-settings)グループ ポリシー の編集」設定[MBAM 2.5 グループ](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-group-policy-requirements)ポリシー要件の計画」を参照してください。
 
### <a name="step-13-deploying-the-mbam-25-client"></a>手順 13: MBAM 2.5 クライアントの展開

Microsoft BitLocker 管理および監視クライアント ソフトウェアを展開する時期に応じて、ユーザーがコンピューターを受信する前、またはグループ ポリシーを構成し、エンタープライズ ソフトウェア展開システムを使用して MBAM クライアント ソフトウェアを展開することで、組織内のコンピューターで BitLocker を有効にできます。
 
#### <a name="deploy-the-mbam-client-to-desktop-or-portable-computers"></a>MBAM クライアントをデスクトップまたはポータブル コンピューターに展開する

グループ ポリシー設定を構成した後、Microsoft System Center 2012 Configuration Manager や Active Directory Domain Services (AD DS) などのエンタープライズ ソフトウェア展開システム製品を使用して、MBAM クライアント インストール Windows インストーラー ファイルをターゲット コンピューターに展開できます。 32 ビットまたは 64 ビットの MbamClientSetup.exe ファイル、または 32 ビットまたは 64 ビットのファイルMBAMClient.msiできます。 これらは、MBAM クライアント ソフトウェアと共に提供されます。

詳細については、「デスクトップまたはラップトップ [コンピューターに MBAM クライアントを展開する方法」を参照してください](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-25)。
 
#### <a name="deploy-the-mbam-client-as-part-of-a-windows-deployment"></a>MBAM クライアントを展開の一部としてWindowsする

コンピューターを一本的に受信および構成する組織では、MBAM クライアントをインストールして、ユーザー データが書き込まれる前に、各コンピューターで BitLocker Drive Encryption を管理できます。 このプロセスの利点は、すべてのコンピューターが BitLocker に準拠しているという利点があります。 管理者が既にコンピューターを暗号化済みなので、このメソッドはユーザー操作に依存しない。 このシナリオの主な前提は、組織のポリシーは、コンピューターがユーザーに配信される前に、Windowsイメージをインストールする方法です。 グループ ポリシーの設定が PIN を要求するように構成されている場合、ユーザーはポリシーを受け取った後に PIN の設定を求めるメッセージが表示されます。

詳細については[、「How to Deploy the MBAM Client as](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25)part of a a Windowsします。
 
#### <a name="how-to-deploy-the-mbam-client-by-using-a-command-line"></a>コマンド ラインを使用して MBAM クライアントを展開する方法

詳細については、「コマンド ライン [を使用して MBAM クライアントを展開する方法」を参照してください](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-deploy-the-mbam-client-by-using-a-command-line)。

#### <a name="post-deployment-of-clients"></a>クライアントの展開後

展開アクティビティが完了したら、次のログを確認し、クライアントが MBAM データベースに正常に報告されているかどうかを確認する必要があります。

## <a name="faq"></a>FAQ

### <a name="how-to-create-a-load-balanced-iis-servers"></a>負荷分散された IIS サーバーを作成する方法

* SPN は、フレンドリー名 (たとえば、bitlocker.corp.net) にのみ登録する必要があります。また、個々の IIS サーバーに登録する必要はありません。

* 証明書を使用する場合、証明書には、負荷分散グループ内のすべての IIS サーバーの [サブジェクトの**** 代替名] フィールドに FQDN 名と NetBIOS 名の両方が入力されている必要があります。また、フレンドリー名 (bitlocker.corp.net など)。 それ以外の場合、負荷分散されたアドレスを参照すると、証明書はブラウザーによって信頼されていないと報告されます。

詳細については [、「IIS ネットワーク](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-high-availability#a-href-idbkmk-load-balanceaiis-network-load-balancing) 負荷分散とアプリケーション プール アカウントの [SPN の登録」を参照してください](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites#registering-spns-for-the-application-pool-account)。

### <a name="how-to-configure-a-certificate"></a>証明書を構成する方法

* 2 つの証明書が必要です。 1 つの証明書はサーバー SQL、もう 1 つは IIS に使用されます。 MBAM インストールを開始する前にインストールする必要があります。

* インストーラーを使用して、証明書ファイルを手動で編集するのではなく、IIS 構成に証明書をweb.configすることをお勧めします。

* 証明書の "発行者" フィールドがサーバーの名前と一致しない場合、証明書は MBAM コンフィギュレーターによって受け入れされません。 この場合、一時的に IIS コンソールから自己署名証明書を作成し、それを Configurator で使用します。 これにより、Web アプリが SSL および HTTPS 用にインストールされていることを確認できます。 その後、MBAM Web サイトの IIS バインドから証明書を 1 に変更できます。

### <a name="the-sql-permissions-requirement-for-installation"></a>インストールSQLアクセス許可の要件

MBAM アプリ プールのアカウントを作成し、SecurityAdmin、Public、および DBCreator のアクセス許可のみを付与します。

詳細 [については、「MBAM Database configuration - 最小アクセス許可」](https://blogs.technet.microsoft.com/dubaisec/2016/02/02/mbam-database-configuration-minimum-permissions/) を参照してください。

> [!Note]
> * 一部の状況では、初期インストールおよびアップグレード操作に必要なアクセス許可が追加されます。
> * インストールに一時的な SA があるアカウントを使用します。
> * インストール エラーの原因となるので、SQL Server に変更を加えるのに十分なアクセス許可を持つユーザー アカウント (Run As) のコンテキストで Configurator を起動しません。
> * ユーザーに対するアクセス許可を持つアカウントを使用してログオンするSQL Server。 MBAM SQL Serverをリモートで実行することで、データベースを作成または更新できるのは、データベースのみです。 SSRS サーバーの場合、MBAM SSRS レポートをインストールまたは更新するには、MBAM をインストールし、ローカルで Configurator を実行する必要があります。

### <a name="the-permission-required-for-spn-registration"></a>SPN 登録に必要なアクセス許可

IIS ポータル インストールに使用するアカウントには、Write ServicePrincipalName アクセス許可と Write Validated SPN アクセス許可が必要です。 これらのアクセス許可がない場合、SPN を登録できないことを示す警告メッセージが表示されます。

> [!Note]
> これにより、この警告メッセージが 2 回表示されます。 これは、SPN に 2 つのオブジェクトが登録されている必要があるという意味ではありません。

詳細については [、「MBAM セットアップが失敗し、"SpN Deferred の登録" エラー メッセージが表示される」を参照してください](https://support.microsoft.com/help/2754138/)。

### <a name="did-i-have-to-update-the-admx-templates-to-the-latest-version"></a>ADMX テンプレートを最新バージョンに更新する必要がありますか?

ADMX テンプレートを最新バージョンに更新すると、GPO の MBAM ルート ノードに複数の OS オプションが表示されます。 たとえば、バージョン 7、Windows、Windows 8.1バージョン 1511 Windows 10以降のバージョンなどです。

ADMX テンプレートを更新する方法の詳細については、次の記事を参照してください。
* [MDOP グループ ポリシー (.admx) テンプレートをダウンロードして展開する方法](https://docs.microsoft.com/microsoft-desktop-optimization-pack/solutions/how-to-download-and-deploy-mdop-group-policy--admx--templates)
* [MBAM 2.5 のグループ ポリシー要件の計画](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-group-policy-requirements)
* [Microsoft Desktop Optimization Pack グループ ポリシー管理用テンプレート](https://www.microsoft.com/en-us/download/details.aspx?id=55531)
