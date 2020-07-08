---
title: MBAM 2.0 機能を別のコンピューターに移動する方法
description: MBAM 2.0 機能を別のコンピューターに移動する方法
author: dansimp
ms.assetid: 49bc0792-60a4-473f-89cc-ada30191e04a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 340d87e26d87f124a9ab64c63d33e89c293d8a86
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825077"
---
# MBAM 2.0 機能を別のコンピューターに移動する方法


このトピックでは、1つ以上の Microsoft BitLocker 管理および監視 (MBAM) 機能を別のコンピューターに移行するために必要な手順について説明します。 複数の Microsoft BitLocker 管理および監視機能を移動する場合は、次の順序で移動する必要があります。

1.  回復用データベース

2.  コンプライアンスと監査データベース

3.  コンプライアンスと監査レポート

4.  管理と監視

## 回復データベースの移動


1台のコンピューターから別のコンピューターに回復用データベースを移動するには (たとえば、サーバー A からサーバー B に移動する)、次の手順を使用します。

1.  管理と監視の web サイトのすべてのインスタンスを停止します。

2.  サーバー B で MBAM セットアップを実行します。

3.  サーバー A 上の MBAM 回復データベースをバックアップします。

4.  MBAM 回復データベースをサーバー A から B に移動します。

5.  サーバー B の MBAM 回復データベースを復元します。

6.  サーバー B 上の MBAM 回復データベースへのアクセスを構成します。

7.  MBAM 管理および監視サーバーのデータベース接続データを更新します。

8.  MBAM 管理と監視 web サイトのすべてのインスタンスを再開します。

**MBAM 管理および監視 Web サイトのすべてのインスタンスを停止する**

1.  MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、 **Microsoft BitLocker の管理と監視と**いう名前の mbam web サイトを停止します。

2.  この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

    **注**  
    この PowerShell コマンドラインを実行するには、powershell の IIS モジュールを PowerShell の現在のインスタンスに追加する必要があります。 さらに、PowerShell の実行ポリシーを更新して、スクリプトの実行を有効にする必要があります。



**サーバー B で MBAM セットアップを実行する**

1.  サーバー B で MBAM セットアップを実行し、インストール用の**回復データベース**のみを選択します。

2.  この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=KeyDatabase ADMINANDMON_MACHINENAMES=$DOMAIN$\$SERVERNAME$$ RECOVERYANDHWDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ TOPOLOGY=$X$`

    **注**  
    上の例の次の値を、使用している環境に一致する値に置き換えます。

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-回復データベースの移動先のサーバーとインスタンスの名前を入力します。

    -   $DOMAIN $ \ \ $SERVERNAME $-各 MBAM 管理と監視サーバーのドメイン名を入力します。これにより、回復データベースに接続します。 セミコロンを使用して、リスト内の各ドメインとサーバーのペアを区切ります (たとえば、$DOMAIN \\SERVERNAME $; $DOMAIN \ \ $SERVERNAME $ $)。 例に示されているように、各サーバー名の後に "$" 記号を付ける必要があります (MyDomain\\MyServerName1 $;MyDomain\\MyServerName2 $)。

    -   $X $-スタンドアロンの MBAM トポロジをインストールする場合は「 **0** 」、Mbam Configuration Manager トポロジをインストールする場合は「 **1** 」を入力します。



**サーバー A 上の回復データベースをバックアップする**

1.  サーバー A 上の回復データベースをバックアップするには、SQL Server Management Studio とバックアップという名前のタスクを使用します。 既定では、データベース名は**Mbam 回復データベース**です。

2.  この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成します。

    MBAM 回復データベースを変更して完全な回復モードを使用するようにします。

    ```sql
    USE master;

    GO

    ALTER DATABASE "MBAM Recovery and Hardware"

       SET RECOVERY FULL;

    GO

    -- Create MBAM Recovery Database Data and MBAM Recovery logical backup devices.

    USE master

    GO

    EXEC sp_addumpdevice 'disk', 'MBAM Recovery and Hardware Database Data Device',

    'Z:\MBAM Recovery Database Data.bak';

    GO

    -- Back up the full MBAM Recovery Database.

    BACKUP DATABASE [MBAM Recovery and Hardware] TO [MBAM Recovery and Hardware Database Data Device];

    GO

    BACKUP CERTIFICATE [MBAM Recovery Encryption Certificate]

    TO FILE = 'Z:\SQLServerInstanceCertificateFile'

    WITH PRIVATE KEY

    (

        FILE = ' Z:\SQLServerInstanceCertificateFilePrivateKey',

        ENCRYPTION BY PASSWORD = '$PASSWORD$'

    );

    GO
    ```

    **注**  
    上の例の次の値を、使用している環境に一致する値に置き換えます。

    -   $PASSWORD $-秘密キーファイルの暗号化に使用するパスワードを入力します。



3.  Sql Server PowerShell と、次のようなコマンドラインを使用して SQL ファイルを実行します。

    `PS C:\> Invoke-Sqlcmd -InputFile 'Z:\BackupMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **注**  
    上の例の次の値を、使用している環境に一致する値に置き換えます。

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-回復データベースをバックアップするサーバーとインスタンスの名前を入力します。



**サーバー A からサーバー B に回復データベースと証明書を移動する**

1.  Windows エクスプローラーを使用して、次のファイルをサーバー A からサーバー B に移動します。

    -   MBAM 回復データベースのデータ .bak

2.  暗号化されたデータベースの証明書を移動するには、次のオートメーションの手順を使用します。 この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。

    `PS C:\> Copy-Item “Z:\MBAM Recovery Database Data.bak” \\$SERVERNAME$\$DESTINATIONSHARE$`

    `PS C:\> Copy-Item “Z:\SQLServerInstanceCertificateFile” \\$SERVERNAME$\$DESTINATIONSHARE$`

    `PS C:\> Copy-Item “Z:\SQLServerInstanceCertificateFilePrivateKey” \\$SERVERNAME$\$DESTINATIONSHARE$`

    **注**  
    上の例の次の値を、使用している環境に一致する値に置き換えます。

    -   $SERVERNAME $-ファイルのコピー先となるサーバーの名前を入力します。

    -   $DESTINATIONSHARE $-ファイルのコピー先となる共有とパスの名前を入力します。



**サーバー B の回復データベースを復元する**

1.  SQL Server Management Studio と**Restore database**という名前のタスクを使用して、サーバー B の回復データベースを復元します。

2.  タスクが完了したら、[**デバイスから**] オプションを選択してデータベースのバックアップファイルを選び、[**追加**] コマンドを使用して mbam Recovery データベースの **.bak**ファイルを選びます。

3.  [ **OK]** を選んで、復元プロセスを完了します。

4.  この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成します。

    ```sql
    -- Restore MBAM Recovery Database. 

    USE master

    GO

    -- Drop certificate created by MBAM Setup.

    DROP CERTIFICATE [MBAM Recovery Encryption Certificate]

    GO

    --Add certificate

    CREATE CERTIFICATE [MBAM Recovery Encryption Certificate]

    FROM FILE = 'Z: \SQLServerInstanceCertificateFile'

    WITH PRIVATE KEY

    (

        FILE = ' Z:\SQLServerInstanceCertificateFilePrivateKey',

        DECRYPTION BY PASSWORD = '$PASSWORD$'

    );

    GO

    -- Restore the MBAM Recovery Database data and log files.

    RESTORE DATABASE [MBAM Recovery and Hardware]

       FROM DISK = 'Z:\MBAM Recovery Database Data.bak'

       WITH REPLACE
    ```

    **注**  
    上の例の次の値を、使用している環境に一致する値に置き換えます。

    -   $PASSWORD $-秘密キーファイルの暗号化に使用したパスワードを入力します。



5.  Windows PowerShell を使用すると、次のようなコマンドラインを入力できます。

    `PS C:\> Invoke-Sqlcmd -InputFile 'Z:\RestoreMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **注**  
    上の例の次の値を、使用している環境に一致する値に置き換えます。

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-回復データベースが復元されるサーバーとインスタンスの名前を入力します。



**サーバー B の回復データベースへのアクセスを構成する**

1.  サーバー B では、サーバーマネージャーから [ローカルユーザーとグループ] スナップインを使って、mbam **Recovery とハードウェアデータベースアクセス**の名前のローカルグループに対して、Mbam 管理と監視機能を実行している各サーバーからコンピューターアカウントを追加します。

2.  復元されたデータベースの SQL login **Mbam 回復とハードウェアデータベースアクセス**がログイン名 **$MachineName $ ¥ mbam RECOVERY とハードウェアデータベースアクセス**にマップされていることを確認します。 記載されているとおりにマップされていない場合は、類似したグループメンバーシップを持つ別のログインを作成し、ログイン名 **$MachineName $ ¥ mbam 回復とハードウェアデータベースアクセス**にマップします。

3.  この手順を自動化するために、サーバー B で Windows PowerShell を使用して、次のようなコマンドラインを入力することができます。

    `PS C:\> net localgroup "MBAM Recovery and Hardware DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    **注**  
    上の例の次の値を、環境に適した値に置き換えます。

    -   $DOMAIN $ \ \ $SERVERNAME $ $-MBAM 管理および監視サーバーのドメインとコンピューター名を入力します。 例に示されているように、サーバー名の後に $ が続いている必要があります (たとえば、MyDomain\\MyServerName1 $)。



~~~
This command line must be run for each Administration and Monitoring Server that will be accessing the database in your environment.
~~~

**MBAM 管理および監視サーバー上の回復データベース接続データを更新する**

1. MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、次のアプリケーションの接続文字列情報を更新します。これは、管理と監視の web サイトでホストされています。

   -   Mbam管理サービス

   -   Mbamrecoveryandハードウェアサービス

2. 各アプリケーションを選択し、**機能ビュー**の [**管理**] セクションにある**構成エディター**機能を使用します。

3. [**セクションリスト**] コントロールで [ **configurationstrings** ] オプションを選びます。

4. " **(コレクション)** " という行を選択し、行の右側にあるボタンを選択して、**コレクションエディター**を開きます。

5. **コレクションエディター**で、Mbamgraph service アプリケーションの構成を更新するときは**keyrecoveryconnectionstring**という名前の行を選択します。それについては、「 <strong> Microsoft Mb"recoveryandcompdatastore </strong> " という名前の行を選びます。ConnectionString は、Mbamrecoveryandなサービスの構成を更新するときに使用します。

6. **Configurationstrings**プロパティの**データソース =** 値を更新して、回復用データベースの移動先のサーバー名とインスタンス (たとえば $SERVERNAME $ \ \ $SQLINSTANCENAME $) を一覧表示します。

7. この手順を自動化するために、Windows を使用して、次のようなコマンドラインを各管理および監視サーバーに入力することができます。

   `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="KeyRecoveryConnectionString"]' -PSPath "IIS:\sites\Microsoft Bitlocker Administration and Monitoring\MBAMAdministrationService" -Name "connectionString" -Value “Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and Hardware;Integrated Security=SSPI;”`

   `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="Microsoft.Mbam.RecoveryAndHardwareDataStore.ConnectionString"]' -PSPath "IIS:\sites\Microsoft Bitlocker Administration and Monitoring\MBAMRecoveryAndHardwareService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and Hardware;Integrated Security=SSPI;"`

   **注**  
   上の例の次の値を、使用している環境に一致する値に置き換えます。

   -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-回復用データベースのサーバー名とインスタンスを入力します。



**MBAM 管理および監視 Web サイトのすべてのインスタンスを再開する**

1.  MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、 **Microsoft BitLocker の管理と監視と**いう名前の mbam web サイトを起動します。

2.  この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

## コンプライアンスと監査データベース機能の移動


MBAM コンプライアンスと監査データベースを1台のコンピューターから別のコンピューターに移動する場合 (つまり、サーバー A からサーバー B にデータベースを移動する場合)、次の手順を使用します。 このプロセスには、次のような大まかな手順が含まれます。

1.  管理と監視の web サイトのすべてのインスタンスを停止します。

2.  サーバー B で MBAM セットアップを実行します。

3.  サーバー A 上のデータベースをバックアップします。

4.  サーバー A から B にデータベースを移動します。

5.  サーバー B でデータベースを復元します。

6.  サーバー B 上のデータベースへのアクセスを構成します。

7.  MBAM 管理および監視サーバー上のデータベース接続データを更新します。

8.  SSRS レポートデータソース接続文字列を、コンプライアンスと監査データベースの新しい場所で更新します。

9.  管理と監視の web サイトのすべてのインスタンスを再開します。

**管理と監視の Web サイトのすべてのインスタンスを停止する**

1.  MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、 **Microsoft BitLocker の管理と監視と**いう名前の mbam web サイトを停止します。

2.  この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。

    `PS C:\> Stop-s “Microsoft BitLocker Administration and Monitoring”`

    **注**  
    このコマンドラインを実行するには、powershell の IIS モジュールを PowerShell の現在のインスタンスに追加する必要があります。 さらに、PowerShell の実行ポリシーを更新して、スクリプトを実行できるようにする必要があります。



**サーバー B で MBAM セットアップを実行する**

1.  サーバー B で MBAM セットアップを実行し、インストール用の**コンプライアンスおよび監査データベース**のみを選択します。

2.  この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal= ReportsDatabase ADMINANDMON_MACHINENAMES=$DOMAIN$\$SERVERNAME$ COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ REPORTS_USERACCOUNT=$DOMAIN$\$USERNAME$ TOPOLOGY=$X$`

    **注**  
    注: 上の例の次の値を、使用している環境に一致する値に置き換えます。

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-コンプライアンスと監査データベースの移動先のサーバー名とインスタンスを入力します。

    -   $DOMAIN $ \ \ $SERVERNAME $-各 MBAM 管理と監視サーバーのドメイン名を入力します。これは、コンプライアンスと監査データベースに連絡します。 セミコロンを使用して、リスト内の各ドメインとサーバーのペアを区切ります (たとえば、$DOMAIN \\SERVERNAME $; $DOMAIN \ \ $SERVERNAME $ $)。 例に示されているように、各サーバー名の後に "$" 記号を付ける必要があります (MyDomain\\MyServerName1 $;MyDomain\\MyServerName2 $)。

    -   $DOMAIN $ \ \ $USERNAME $-コンプライアンスおよび監査レポート機能でコンプライアンスと監査データベースに接続するために使用されるドメインとユーザー名を入力します。

    -   $X $-スタンドアロンの MBAM トポロジをインストールする場合は「 **0** 」、Mbam Configuration Manager トポロジをインストールする場合は「 **1** 」を入力します。



**サーバー A 上のコンプライアンスおよび監査データベースのバックアップを作成する**

1.  Server A 上のコンプライアンスおよび監査データベースをバックアップするには、SQL Server Management Studio と**バックアップ**という名前のタスクを使用します。 既定では、データベース名は**Mbam コンプライアンスステータスデータベース**です。

2.  この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成します。

    ```sql
    -- Modify the MBAM Compliance Status Database to use the full recovery model.

    USE master;

    GO

    ALTER DATABASE "MBAM Compliance Status"

       SET RECOVERY FULL;

    GO

    -- Create MBAM Compliance Status Data logical backup devices.

    USE master

    GO

    EXEC sp_addumpdevice 'disk', 'MBAM Compliance Status Database Data Device',

    'Z: \MBAM Compliance Status Database Data.bak';

    GO

    -- Back up the full MBAM Recovery database.

    BACKUP DATABASE [MBAM Compliance Status] TO [MBAM Compliance Status Database Data Device];

    GO
    ```

3.  次のような Windows PowerShell コマンドラインを使用して、SQL ファイルを実行します。

    `PS C:\> Invoke-Sqlcmd -InputFile "Z:\BackupMBAMComplianceStatusDatabaseScript.sql" –ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **注**  
    上の例の次の値を、使用している環境に一致する値に置き換えます。

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-コンプライアンスと監査データベースがバックアップされるサーバー名とインスタンスを入力します。



**コンプライアンスと監査データベースをサーバー A から B に移動する**

1.  Windows エクスプローラーを使用して、次のファイルをサーバー A からサーバー B に移動します。

    -   MBAM コンプライアンスステータスデータベースデータ .bak

2.  この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。

    `PS C:\> Copy-Item “Z:\MBAM Compliance Status Database Data.bak” \\$SERVERNAME$\$DESTINATIONSHARE$`

    **注**  
    上の例の次の値を、使用している環境に一致する値に置き換えます。

    -   $SERVERNAME $-ファイルのコピー先のサーバー名を入力します。

    -   $DESTINATIONSHARE $-ファイルのコピー先の共有名とパスを入力します。



**サーバー B でコンプライアンスと監査データベースを復元する**

1.  SQL Server Management Studio と**Restore database**という名前のタスクを使用して、server B 上のコンプライアンスおよび監査データベースを復元します。

2.  タスクが完了したら、[**デバイスから**] オプションを選択してデータベースバックアップファイルを選び、[**追加**] コマンドを使用して、Mbam コンプライアンスステータスデータベースデータ .bak ファイルを選びます。 [ **OK]** を選んで、復元プロセスを完了します。

3.  この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成します。

    ```sql
    -- Create MBAM Compliance Status Database Data logical backup devices. 

    Use master

    GO

    -- Restore the MBAM Compliance Status database data files.

    RESTORE DATABASE [MBAM Compliance Status]

       FROM DISK = 'C:\test\MBAM Compliance Status Database Data.bak'

       WITH REPLACE
    ```

4.  次のような Windows PowerShell コマンドラインを使用して、SQL ファイルを実行します。

    `PS C:\> Invoke-Sqlcmd -InputFile "Z:\RestoreMBAMComplianceStatusDatabaseScript.sql" -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **注**  
    上の例の次の値を、使用している環境に一致する値に置き換えます。

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-コンプライアンスと監査データベースが復元されるサーバー名とインスタンスを入力します。



**サーバー B 上のコンプライアンスおよび監査データベースへのアクセスを構成する**

1.  サーバー B では、サーバーマネージャーの [ローカルユーザーとグループ] スナップインを使用して、mbam の管理と監視の機能を実行している各サーバーから、 **Mbam コンプライアンスステータスの DB Access**という名前のローカルグループにコンピューターアカウントを追加します。

2.  復元されたデータベースの SQL login **Mbam コンプライアンス監査データベースアクセス**がログイン名 **$MachineName $ \ \ MBAM コンプライアンス監査データベースアクセス**にマップされていることを確認します。 記載されている手順に従ってマッピングされていない場合は、類似したグループメンバーシップを使用して別のログインを作成し、ログイン名 **$MachineName $ \ \ MBAM コンプライアンス監査データベースアクセス**にマップします。

3.  この手順を自動化するには、Windows PowerShell を使用して、次のようなサーバー B にコマンドラインを入力します。

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$REPORTSUSERNAME$  /add`

    **注**  
    上の例の次の値を、環境に適した値に置き換えます。

    -   $DOMAIN $ \ \ $SERVERNAME $ $-MBAM 管理および監視サーバーのドメインとコンピューター名を入力します。 例に示されているように、サーバー名の後に "$" を付ける必要があります。 (MyDomain\\MyServerName1 $ など)

    -   $DOMAIN $ \ \ $REPORTSUSERNAME $-コンプライアンスおよび監査レポートのデータソースを構成するために使用されたユーザーアカウント名を入力します。



~~~
The command line for adding the servers to the MBAM Compliance and Audit Database access local group must be run for each Administration and Monitoring Server that will be accessing the database in your environment.
~~~

**MBAM 管理および監視サーバー上のデータベース接続データを更新する**

1.  MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、次のアプリケーションの接続文字列情報を更新します。これは、管理と監視の web サイトでホストされています。

    -   Mbam管理サービス

    -   MBAMComplianceStatusService

2.  各アプリケーションを選択し、**機能ビュー**の [**管理**] セクションにある**構成エディター**機能を使用します。

3.  [**セクションリスト**] コントロールで [ **configurationstrings** ] オプションを選びます。

4.  " **(コレクション)**" という名前の行を選び、行の右側にあるボタンを選択して、**コレクションエディター**を開きます。

5.  **コレクションエディター**で、MBAMAdministrationService アプリケーションの構成を更新するときに**ComplianceStatusConnectionString**という名前の行を選択するか、MBAMComplianceStatusService の構成を更新するときに、**という名前の**行を選びます。

6.  **Configurationstrings**プロパティの**データソース =** 値を更新して、回復データベースの移動先のサーバーとインスタンスの名前を一覧表示します (例: $SERVERNAME $ \ \ $SQLINSTANCENAME)。

7.  この手順を自動化するために、Windows を使用して、次のような管理および監視サーバーごとにコマンドラインを入力することができます。

    `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="ComplianceStatusConnectionString"]' -PSPath "IIS:\sites\Microsoft Bitlocker Administration and Monitoring\MBAMAdministrationService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Compliance Status;Integrated Security=SSPI;"`

    `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="Microsoft.Windows.Mdop.BitLockerManagement.StatusReportDataStore.ConnectionString"]' -PSPath "IIS:\sites\Microsoft Bitlocker Administration and Monitoring\MBAMComplianceStatusService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME;Initial Catalog=MBAM Compliance Status;Integrated Security=SSPI;"`

    **注**  
    上の例の次の値を、使用している環境に一致する値に置き換えます。

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-回復用データベースが配置されているサーバー名とインスタンスを入力します。



**MBAM 管理および監視 Web サイトのすべてのインスタンスを再開する**

1.  MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、 **Microsoft BitLocker の管理と監視と**いう名前の mbam web サイトを起動します。

2.  この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

## コンプライアンスおよび監査レポートを移動する


MBAM コンプライアンスと監査レポートを1台のコンピューターから別のコンピューターに移動する場合 (つまり、サーバー A からサーバー B にレポートを移動する場合)、次の手順を実行します。これには、次のような大まかな手順が含まれます。

1.  サーバー B で MBAM セットアップを実行します。

2.  サーバー B のコンプライアンスおよび監査レポートへのアクセスを構成します。

3.  MBAM 管理と監視 web サイトのすべてのインスタンスを停止します。

4.  MBAM 管理および監視サーバーのレポート接続データを更新します。

5.  MBAM 管理と監視 web サイトのすべてのインスタンスを再開します。

**サーバー B で MBAM セットアップを実行する**

1.  サーバー B で MBAM セットアップを実行し、インストールの**コンプライアンスおよび監査レポート**機能のみを選択します。

2.  この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=Reports COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ REPORTS_USERACCOUNTPW=$PASSWORD$ TOPOLOGY=$X$`

    **注**  
    上の例の次の値を、使用している環境に一致する値に置き換えます。

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-コンプライアンスと監査データベースが配置されているサーバー名とインスタンスを入力します。

    -   $DOMAIN $ \ \ $USERNAME $-コンプライアンスおよび監査レポート機能でコンプライアンスと監査データベースに接続するために使用されるドメインとユーザー名を入力します。

    -   $PASSWORD $-コンプライアンスと監査データベースへの接続に使用されるユーザーアカウントのパスワードを入力します。

    -   $X $-スタンドアロンの MBAM トポロジをインストールする場合は「 **0** 」、Mbam Configuration Manager トポロジをインストールする場合は「 **1** 」を入力します。



**サーバー B のコンプライアンスおよび監査レポートへのアクセスを構成する**

1.  サーバー B では、[サーバーマネージャー] から [ローカルユーザーとグループ] スナップインを使用して、コンプライアンスレポートおよび監査レポートへのアクセス権を持つユーザーアカウントを追加します。 MBAM レポートユーザーという名前のローカルグループにユーザーアカウントを追加します。

2.  この手順を自動化するには、Windows PowerShell を使用して、次のようなサーバー B にコマンドラインを入力します。

    `PS C:\> net localgroup "MBAM Report Users" $DOMAIN$\$REPORTSUSERNAME$  /add`

    **注**  
    上の例の次の値を、環境に適した値に置き換えます。

    -   $DOMAIN $ \ \ $REPORTSUSERNAME $-コンプライアンスおよび監査レポートのデータソースを構成するために使用されたユーザーアカウント名を入力します。



~~~
The command line for adding the users to the MBAM Report Users local group must be run for each user that will be accessing the reports in your environment.
~~~

**MBAM 管理および監視 Web サイトのすべてのインスタンスを停止する**

1.  MBAM 管理と監視サーバー機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、 **Microsoft BitLocker の管理と監視と**いう名前の mbam web サイトを停止します。

2.  この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

**MBAM 管理および監視サーバー上のデータベース接続データを更新する**

1. MBAM 管理および監視サーバー機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、コンプライアンスと監査レポートの URL を更新します。

2. **Microsoft BitLocker の管理と監視**の web サイトを選び、**機能ビュー**の [**管理**] セクションの下にある [**構成エディター** ] 機能を使用します。

3. [**セクションリスト**] コントロールから [ **appSettings** ] オプションを選びます。

4. " **(コレクション)** " という行を選択し、行の右側にあるボタンを選択して、**コレクションエディター**を開きます。

5. **コレクションエディター**で、「 **Mbam. .url**」という名前の行を選びます。

6. サーバー B のサーバー名を反映するには、" **Mbam** " の値を更新します。指定した SQL Reporting Services インスタンスにコンプライアンスと監査レポート機能がインストールされている場合は、URL にインスタンスの名前を追加または更新してください (例 http://$SERVERNAME $/reportserver _ $ SQLSRSINSTANCENAME $/Pages....)。

7. この手順を自動化するために、Windows PowerShell を使用して、次のような管理および監視サーバーごとにコマンドラインを入力することができます。

   `PS C:\> Set-WebConfigurationProperty '/appSettings/add[@key="Microsoft.Mbam.Reports.Url"]' -PSPath "IIS:\ \sites\Microsoft Bitlocker Administration and Monitoring\HelpDesk" -Name "Value" -Value “http://$SERVERNAME$/ReportServer_$SRSINSTANCENAME$/Pages/ReportViewer.aspx?/ Microsoft+BitLocker+Administration+and+Monitoring/”`

   **注**  
   上の例の次の値を、使用している環境に一致する値に置き換えます。

   -   $SERVERNAME $-コンプライアンスと監査レポートがインストールされたサーバー名の名前を入力します。

   -   $SRSINSTANCENAME $-コンプライアンスと監査レポートがインストールされた SQL Reporting Services インスタンスの名前を入力します。



**MBAM 管理および監視 Web サイトのすべてのインスタンスを再開する**

1.  MBAM 管理と監視サーバー機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、 **Microsoft BitLocker の管理と監視と**いう名前の mbam web サイトを起動します。

2.  この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

    **注**  
    このコマンドラインを実行するには、powershell の IIS モジュールを PowerShell の現在のインスタンスに追加する必要があります。 さらに、PowerShell の実行ポリシーを更新して、スクリプトを実行できるようにする必要があります。



## 管理と監視機能の移動


MBAM 管理と監視レポート機能をあるコンピューターから別のコンピューターに移動する場合 (つまり、サーバー A からサーバー B にその機能を移行する場合)、次の手順を実行します。これには、次のような大まかな手順が含まれます。

1.  サーバー B で MBAM セットアップを実行します。

2.  サーバー B 上のデータベースへのアクセスを構成します。

**サーバー B で MBAM セットアップを実行する**

1.  サーバー B で MBAM セットアップを実行し、インストールの [**管理/監視サーバー** ] 機能のみを選択します。

2.  この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=AdministrationMonitoringServer, COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ RECOVERYANDHWDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ SRS_REPORTSITEURL=$REPORTSSERVERURL$ TOPOLOGY=$X$`

    **注**  
    上の例の次の値を、使用している環境に一致する値に置き換えます。

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-COMPLIDB \ _SQLINSTANCE パラメーターには、コンプライアンスと監査データベースが配置されているサーバー名とインスタンスを入力します。 RECOVERYANDHWDB \ _SQLINSTANCE パラメーターには、回復データベースが配置されているサーバー名とインスタンスを入力します。

    -   $DOMAIN $ \ \ $USERNAME $-コンプライアンスおよび監査レポート機能でコンプライアンスと監査データベースに接続するために使用されるドメインとユーザー名を入力します。

    -   $ ¥ SERVERURL $-SQL Reporting Service web サイトのホームの場所の URL を入力します。 レポートが既定の SRS インスタンスにインストールされている場合、URL 形式は "http://$SERVERNAME $/ReportServer" の形式になります。 レポートが既定の SRS インスタンスにインストールされていた場合、URL 形式の形式は "http://$SERVERNAME $/report% _ $ SQLINSTANCENAME $" の形式になります。

    -   $X $-スタンドアロンの MBAM トポロジをインストールする場合は「 **0** 」、Mbam Configuration Manager トポロジをインストールする場合は「 **1** 」を入力します。



**データベースへのアクセスを構成する**

1.  回復データベースとコンプライアンスおよび監査データベースが展開されているサーバー上で、サーバーマネージャーから [ローカルユーザーとグループ] スナップインを使用して、mbam **Recovery とハードウェアデータベースアクセス**(回復用データベースサーバー) と**Mbam コンプライアンスステータス DB access** (コンプライアンスおよび監査データベースサーバー) を実行している各サーバーから、コンピューターアカウントを追加します。

2.  この手順を自動化するために、Windows PowerShell を使用して、コンプライアンスと監査データベースが展開されたサーバー上で、次のようなコマンドラインを入力できます。

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$SERVERNAME$$  /add`

3.  回復データベースが展開されたサーバーでは、Windows PowerShell を使用して、次のようなコマンドラインを入力することができます。

    `PS C:\> net localgroup "MBAM Recovery and Hardware DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    **注**  
    上の例の次の値を、環境に適した値に置き換えます。

    -   $DOMAIN $ \ \ $SERVERNAME $ $-管理および監視サーバーのドメインとマシン名を入力します。 例に示されているように、サーバー名の後に "$" 記号を付ける必要があります (たとえば、MyDomain\\MyServerName1 $ など)。

    -   $DOMAIN $ \ \ $REPORTSUSERNAME $-コンプライアンスおよび監査レポートのデータソースを構成するために使用されたユーザーアカウント名を入力します。



~~~
The command lines that are listed for adding server computer accounts to the MBAM local groups must be run for each Administration and Monitoring Server that will be accessing the databases in your environment.
~~~

## 関連トピック


[MBAM 2.0 の保守](maintaining-mbam-20-mbam-2.md)









