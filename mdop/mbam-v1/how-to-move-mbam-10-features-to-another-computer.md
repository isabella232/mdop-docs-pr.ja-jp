---
title: MBAM 1.0 機能を別のコンピューターに移動する方法
description: MBAM 1.0 機能を別のコンピューターに移動する方法
author: dansimp
ms.assetid: e1907d92-6b42-4ba3-b0e4-60a9cc8285cc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 874c3983220f341e39fa5fb7c60f655e2f208082
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812947"
---
# MBAM 1.0 機能を別のコンピューターに移動する方法


このトピックでは、1つ以上の Microsoft BitLocker 管理および監視 (MBAM) 機能を別のコンピューターに移行するために必要な手順について説明します。 複数の MBAM 機能を別のコンピューターに移動する場合は、次の順序で移動する必要があります。

1.  回復とハードウェアデータベース

2.  コンプライアンスと監査データベース

3.  コンプライアンスと監査レポート

4.  管理と監視

## 回復とハードウェアデータベースを移動するには


次の手順を使用して、MBAM 回復とハードウェアデータベースを1台のコンピューターから別のコンピューターに移動できます (この MBAM Server 機能は、サーバー A からサーバー B に移動できます)。

****

1.  MBAM 管理および監視 web サイトのすべてのインスタンスを停止します。

2.  サーバー B で MBAM セットアップを実行します。

3.  サーバー A 上の MBAM 回復とハードウェアデータベースをバックアップします。

4.  MBAM 回復とハードウェアデータベース (サーバー A から B)

5.  サーバー B で MBAM 回復とハードウェアデータベースを復元する

6.  サーバー B 上の MBAM 回復とハードウェアデータベースへのアクセスを構成する

7.  MBAM 管理および監視サーバー上のデータベース接続データを更新する

8.  MBAM 管理および監視 web サイトのすべてのインスタンスを再開する

**MBAM 管理と監視 web サイトのすべてのインスタンスを停止するには**

1.  インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、MBAM 管理と監視機能を実行している各サーバーで MBAM web サイトを停止します。 MBAM web サイトは、 **Microsoft BitLocker の管理と監視と**いう名前です。

2.  この手順を自動化するために、Windows PowerShell を使用すると、コマンドプロンプトで次のようなコマンドを使うことができます。

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

    **注**  
    この PowerShell コマンドプロンプトを実行するには、powershell の IIS モジュールを PowerShell の現在のインスタンスに追加する必要があります。 さらに、PowerShell の実行ポリシーを更新して、スクリプトの実行を有効にする必要があります。



**サーバー B で MBAM セットアップを実行するには**

1.  サーバー B で MBAM セットアップを実行し、インストール用の回復とハードウェアデータベースを選択します。

2.  この手順を自動化するために、Windows PowerShell を使用すると、コマンドプロンプトで次のようなコマンドを使うことができます。

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=KeyDatabase ADMINANDMON_MACHINENAMES=$DOMAIN$\$SERVERNAME$$ RECOVERYANDHWDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$`

    **注**  
    上の例の次の値を、使用している環境に一致する値に置き換えます。

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-回復とハードウェアデータベースの移動先のサーバーとインスタンスの名前を入力します。

    -   $DOMAIN $ \ \ $SERVERNAME $-各 MBAM アプリケーションのドメイン名とサーバー名を入力します。これは、回復とハードウェアのデータベースに接続します。 複数のドメイン名とサーバー名がある場合は、セミコロンを使用してリスト内の各ドメインを区切ります。 たとえば、$DOMAIN \\SERVERNAME $; $DOMAIN \\ $SERVERNAME $ $。 また、各サーバー名の後には、を付ける必要があり **$** ます。 たとえば、MyDomain\\MyServerName1 $、MyDomain\\MyServerName2 $ などです。



**サーバー A 上のデータベースをバックアップするには**

1.  Server A 上の回復とハードウェアデータベースをバックアップするには、SQL Server Management Studio と [バックアップ] という名前のタスクを使用**し**ます。 既定では、データベース名は**Mbam 回復とハードウェアデータベース**です。

2.  この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成します。

    MBAM 回復とハードウェアデータベースを変更して、完全な回復モードを使用します。

    ```sql
    USE master;

    GO

    ALTER DATABASE "MBAM Recovery and Hardware"

       SET RECOVERY FULL;

    GO
    ```

    MBAM 回復とハードウェアデータベースデータと MBAM 回復論理バックアップデバイスを作成します。

    ```sql
    USE master

    GO

    EXEC sp_addumpdevice 'disk', 'MBAM Recovery and Hardware Database Data Device',

    'Z:\MBAM Recovery and Hardware Database Data.bak';

    GO
    ```

    完全な MBAM 回復とハードウェアデータベースをバックアップします。

    ```sql
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
    上の例の値を、環境に一致する値に置き換えます。

    -   $PASSWORD $-秘密キーファイルの暗号化に使用するパスワードを入力します。



3.  Sql Server PowerShell と、次のようなコマンドを使用して SQL ファイルを実行します。

    `PS C:\> Invoke-Sqlcmd -InputFile 'Z:\BackupMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **注**  
    上の例の値を、環境に一致する値に置き換えます。

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-回復とハードウェアデータベースのバックアップを作成するサーバーとインスタンスの名前を入力します。



**サーバー A から B にデータベースと証明書を移動するには**

1.  Windows エクスプローラーを使用して、サーバー A からサーバー B に MBAM 回復とハードウェアデータベースデータの .bak を移動します。

2.  暗号化されたデータベースの証明書を移動するには、次のオートメーションの手順を使用する必要があります。 この手順を自動化するために、Windows PowerShell を使用して、次のようなコマンドを入力できます。

    `PS C:\> Copy-Item “Z:\MBAM Recovery and Hardware Database Data.bak” \\$SERVERNAME$\$DESTINATIONSHARE$`

    `PS C:\> Copy-Item “Z:\SQLServerInstanceCertificateFile” \\$SERVERNAME$\$DESTINATIONSHARE$`

    `PS C:\> Copy-Item “Z:\SQLServerInstanceCertificateFilePrivateKey” \\$SERVERNAME$\$DESTINATIONSHARE$`

    **注**  
    上の例の値を、使用している環境に一致する値に置き換えます。

    -   $SERVERNAME $-ファイルのコピー先となるサーバーの名前を入力します。

    -   $DESTINATIONSHARE $-ファイルのコピー先となる共有とパスの名前を入力します。



**サーバー B でデータベースを復元するには**

1.  SQL Server Management Studio と**Restore database**という名前のタスクを使用して、server B の回復およびハードウェアデータベースを復元します。

2.  タスクが実行されたら、[**デバイスから**] オプションを選択してデータベースのバックアップファイルを選び、[**追加**] コマンドを使用して、Mbam 回復とハードウェアデータベースの**データ .bak**ファイルを選びます。

3.  [ **OK]** を選んで、復元プロセスを完了します。

4.  この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成します。

    ```sql
    -- Restore MBAM Recovery and Hardware Database. 

    USE master

    GO
    ```

    MBAM セットアップで作成された証明書をドロップします。

    ```sql
    DROP CERTIFICATE [MBAM Recovery Encryption Certificate]

    GO
    ```

    証明書を追加する

    ```sql
    CREATE CERTIFICATE [MBAM Recovery Encryption Certificate]

    FROM FILE = 'Z: \SQLServerInstanceCertificateFile'

    WITH PRIVATE KEY

    (

        FILE = ' Z:\SQLServerInstanceCertificateFilePrivateKey',

        DECRYPTION BY PASSWORD = '$PASSWORD$'

    );

    GO
    ```

    MBAM 回復とハードウェアデータベースデータとログファイルを復元します。

    ```sql
    RESTORE DATABASE [MBAM Recovery and Hardware]

       FROM DISK = 'Z:\MBAM Recovery and Hardware Database Data.bak'

       WITH REPLACE
    ```

    **注**  
    上の例の値を、環境に一致する値に置き換えます。

    -   $PASSWORD $-秘密キーファイルの暗号化に使用したパスワードを入力します。



5.  Windows PowerShell を使用して、次のようなコマンドラインを入力します。

    `PS C:\> Invoke-Sqlcmd -InputFile 'Z:\RestoreMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **注**  
    消えますの例の値を、使用している環境に一致する値に置き換えます。

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-回復とハードウェアデータベースの復元先のサーバーとインスタンスの名前を入力します。



**サーバー B 上のデータベースへのアクセスを構成する**

1.  サーバー B では、サーバーマネージャーの [ローカルユーザーとグループ] スナップインを使用して、MBAM 管理と監視機能を実行している各サーバーから**Mbam Recovery とハードウェアデータベースアクセス**のローカルグループにコンピューターアカウントを追加します。

2.  この手順を自動化するために、サーバー B で Windows PowerShell を使用して、次のようなコマンドを入力できます。

    `PS C:\> net localgroup "MBAM Recovery and Hardware DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    **注**  
    上の例の値を、環境に適した値に置き換えます。

    -   $DOMAIN $ \ \ $SERVERNAME $ $-MBAM 管理および監視サーバーのドメイン名とコンピューター名を入力します。 サーバー名の後に、「MyDomain\\MyServerName1 $」などのように指定する必要があり **$** ます。



~~~
You must run the command for each Administration and Monitoring Server that will be accessing the database in your environment.
~~~

**MBAM 管理および監視サーバーでデータベース接続データを更新するには**

1. MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、Microsoft BitLocker の管理と監視の web サイトでホストされている次のアプリケーションの接続文字列情報を更新します。

   -   MBAM 管理サービス

   -   MBAM 回復とハードウェアサービス

2. 各アプリケーションを選択し、**機能ビュー**の [**管理**] セクションにある**構成エディター**機能を使用します。

3. [セクションリスト] コントロールで [ **Configurationstrings** ] オプションを選びます。

4. " **(コレクション)**" という名前の行を選び、行の右側にあるボタンを選択して、**コレクションエディター**を開きます。

5. **コレクションエディター**で、「Mbam管理サービス」アプリケーションの構成を更新したときに**keyrecoveryconnectionstring**という名前の行を選択するか、「 <strong> Microsoft Mbam recoveryandcompdatastore </strong> 」という名前の行を選択します。ConnectionString。 ' MBAMRecoveryAndHardwareService ' の構成を更新しています。

6. **Configurationstrings**プロパティの**データソース =** 値を更新して、サーバー名と、回復およびハードウェアデータベースの移動先のインスタンスを一覧表示します。 たとえば、$ \\ \ $SQLINSTANCENAME $ などの $SERVERNAME ます。

7. この手順を自動化するには、各管理サーバーと監視サーバーで Windows PowerShell を使用して、次のようなコマンドを実行します。

   `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="KeyRecoveryConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMAdministrationService" -Name "connectionString" -Value “Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and Hardware;Integrated Security=SSPI;”`

   `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="Microsoft.Mbam.RecoveryAndHardwareDataStore.ConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMRecoveryAndHardwareService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and Hardware;Integrated Security=SSPI;"`

   **注**  
   上の例の値を、使用している環境に一致する値に置き換えます。

   -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-回復とハードウェアデータベースのサーバー名とインスタンスを入力します。



**MBAM 管理と監視 web サイトのすべてのインスタンスを再開するには**

1.  MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、 **Microsoft BitLocker の管理と監視と**いう名前の mbam web サイトを起動します。

2.  この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを使用できます。

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

## コンプライアンスステータスデータベース機能を移動するには


MBAM コンプライアンスステータスデータベース機能をあるコンピューターから別のコンピューターに移動することを選択する場合 (たとえば、サーバー A からサーバー B に移動するなど)、次の手順を実行する必要があります。

1.  MBAM 管理および監視 web サイトのすべてのインスタンスを停止する

2.  サーバー B で MBAM セットアップを実行する

3.  サーバー A でデータベースをバックアップする

4.  サーバー A から B にデータベースを移動する

5.  サーバー B でデータベースを復元する

6.  サーバー B 上のデータベースへのアクセスを構成する

7.  MBAM 管理および監視サーバー上のデータベース接続データを更新する

8.  MBAM 管理および監視 web サイトのすべてのインスタンスを再開する

**MBAM 管理と監視 web サイトのすべてのインスタンスを停止するには**

1.  MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、 **Microsoft BitLocker の管理と監視と**いう名前の mbam web サイトを停止します。

2.  この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを使用できます。

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

    **注**  
    このコマンドを実行するには、powershell の IIS モジュールを PowerShell の現在のインスタンスに追加する必要があります。 さらに、PowerShell の実行ポリシーを更新して、スクリプトの実行を有効にする必要があります。



**サーバー B で MBAM セットアップを実行するには**

1.  サーバー B で MBAM セットアップを実行し、インストール用のコンプライアンスステータスデータベース機能を選択します。

2.  この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを使用できます。

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal= ReportsDatabase ADMINANDMON_MACHINENAMES=$DOMAIN$\$SERVERNAME$ COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ REPORTS_USERACCOUNT=$DOMAIN$\$USERNAME$`

    **注**  
    上の例の値を、環境に一致する値に置き換えます。

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-コンプライアンスステータスデータベースの移動先のサーバー名とインスタンスを入力します。

    -   $DOMAIN $ \ \ $SERVERNAME $-各 MBAM アプリケーションのドメイン名とサーバー名を入力して、コンプライアンスステータスデータベースに接続するサーバーを監視します。 複数のドメイン名とサーバー名がある場合は、セミコロンを使用してリスト内のそれぞれの名前を区切ります。 たとえば、$DOMAIN \\SERVERNAME $; $DOMAIN \\ $SERVERNAME $ $。 各サーバー名の後に、 **$** 例に示されているようにする必要があります。 たとえば、MyDomain\\MyServerName1 $、MyDomain\\MyServerName2 $ などです。

    -   $DOMAIN $ \ \ $USERNAME $-コンプライアンスと監査レポート機能が使用するドメインとユーザー名を入力して、コンプライアンスステータスデータベースに接続します。



**サーバー A 上のコンプライアンスデータベースのバックアップを作成するには**

1.  Server A 上のコンプライアンスデータベースをバックアップするには、SQL Server Management Studio と [**バックアップ**] という名前のタスクを使用します。 既定では、データベース名は**Mbam コンプライアンスステータスデータベース**です。

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

    -- Back up the full MBAM Recovery and Hardware database.

    BACKUP DATABASE [MBAM Compliance Status] TO [MBAM Compliance Status Database Data Device];

    GO
    ```

3.  SQL Server PowerShell を使用して、次のようなコマンドで SQL ファイルを実行します。

    `PS C:\> Invoke-Sqlcmd -InputFile "Z:\BackupMBAMComplianceStatusDatabaseScript.sql" –ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **注**  
    上の例の値を、使用している環境に一致する値に置き換えます。

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-サーバー名と、コンプライアンスステータスデータベースのバックアップの対象となるインスタンスを入力します。



**サーバー A から B にデータベースを移動するには**

1.  Windows エクスプローラーを使用して、次のファイルをサーバー A からサーバー B に移動します。

    -   MBAM コンプライアンスステータスデータベースデータ .bak

2.  この手順を自動化するには、Windows PowerShell を使用して次のようなコマンドを実行します。

    `PS C:\> Copy-Item “Z:\MBAM Compliance Status Database Data.bak” \\$SERVERNAME$\$DESTINATIONSHARE$`

    **注**  
    上の例の値を、使用している環境に一致する値に置き換えます。

    -   $SERVERNAME $-ファイルのコピー先のサーバー名を入力します。

    -   $DESTINATIONSHARE $-ファイルのコピー先の共有名とパスを入力します。



**サーバー B でデータベースを復元するには**

1.  SQL Server Management Studio と [**データベースの復元**] という名前のタスクを使用して、サーバー B 上のコンプライアンスステータスデータベースを復元します。

2.  タスクが実行されたら、[デバイスから] オプションを選択してデータベースバックアップファイルを選び、[追加] コマンドを使用して MBAM コンプライアンスステータスデータベースデータ .bak ファイルを選びます。 [OK] をクリックして、復元プロセスを完了します。

3.  この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成します。

    ```sql
    -- Create MBAM Compliance Status Database Data logical backup devices. 

    Use master

    GO

    -- Restore the MBAM Compliance Status database data files.

    RESTORE DATABASE [MBAM Compliance Status Database]

       FROM DISK = 'C:\test\MBAM Compliance Status Database Data.bak'

       WITH REPLACE
    ```

4.  SQL Server PowerShell を使用して、次のようなコマンドで SQL ファイルを実行します。

    `PS C:\> Invoke-Sqlcmd -InputFile "Z:\RestoreMBAMComplianceStatusDatabaseScript.sql" -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **注**  
    上の例の値を、使用している環境に一致する値に置き換えます。

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-コンプライアンスステータスデータベースが復元されるサーバー名とインスタンスを入力します。



**サーバー B 上のデータベースへのアクセスを構成するには**

1.  サーバー B では、サーバーマネージャーの [ローカルユーザーとグループ] スナップインを使用して、MBAM の管理と監視機能を実行する各サーバーから、 **Mbam コンプライアンス状態の DB Access**という名前のローカルグループにマシンアカウントを追加します。

2.  この手順を自動化するには、サーバー B で Windows PowerShell を使用して、次のようなコマンドを実行します。

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$REPORTSUSERNAME$  /add`

    **注**  
    上の例の値を、環境に適した値に置き換えます。

    -   $DOMAIN $ \ \ $SERVERNAME $ $-MBAM 管理および監視サーバーのドメインとコンピューター名を入力します。 サーバー名の後には、という名前を付ける必要があり **$** ます。たとえば、MyDomain\\MyServerName1 $ とします。

    -   $DOMAIN $ \ \ $REPORTSUSERNAME $-コンプライアンスおよび監査レポートのデータソースを構成するために使用されたユーザーアカウント名を入力します。



~~~
For each Administration and Monitoring Server that will access the database of your environment, you must run the command that will add the servers to the MBAM Compliance Auditing DB Access local group.
~~~

**MBAM 管理および監視サーバーでデータベース接続データを更新するには**

1.  MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、Microsoft BitLocker の管理と監視の web サイトでホストされている次のアプリケーションの接続文字列情報を更新します。

    -   Mbam管理サービス

    -   MBAMComplianceStatusService

2.  各アプリケーションを選択し、**機能ビュー**の [**管理**] セクションにある**構成エディター**機能を使用します。

3.  [セクションリスト] コントロールで [ **Configurationstrings** ] オプションを選びます。

4.  " **(コレクション)**" という名前の行を選び、行の右側にあるボタンを選択して、コレクションエディターを開きます。

5.  **コレクションエディター**で、mbamComplianceStatusConnectionString という**ComplianceStatusConnectionString**名前の行を選択します。この場合は、MBAMComplianceStatusService の構成を更新するときに、 **mbammanagement**service アプリケーションの構成を更新するか、またはという名前の行を選びます。

6.  **Configurationstrings**プロパティの**データソース =** 値を更新して、サーバー名とインスタンス名を一覧表示します。 たとえば、回復とハードウェアデータベースが移動された $SERVERNAME $ \ \ $SQLINSTANCENAME。

7.  この手順を自動化するために、Windows PowerShell を使用して、各管理および監視サーバーに次のようなコマンドを入力できます。

    `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="ComplianceStatusConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMAdministrationService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Compliance Status;Integrated Security=SSPI;"`

    `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="Microsoft.Windows.Mdop.BitLockerManagement.StatusReportDataStore.ConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMComplianceStatusService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME;Initial Catalog=MBAM Compliance Status;Integrated Security=SSPI;"`

    **注**  
    上の例の値を、使用している環境に一致する値に置き換えます。

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-回復とハードウェアデータベースが配置されているサーバー名とインスタンス名を入力します。



**MBAM 管理と監視 web サイトのすべてのインスタンスを再開するには**

1.  MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、 **Microsoft BitLocker の管理と監視と**いう名前の mbam web サイトを起動します。

2.  この手順を自動化するために、Windows PowerShell を使用して、次のようなコマンドを入力できます。

    **PS c &gt; : Web サイト "Microsoft BitLocker の管理と監視"**

## コンプライアンスおよび監査レポートを移動するには


MBAM コンプライアンスと監査レポートを1台のコンピューターから別のコンピューターに移動する場合 (具体的には、サーバー A からサーバー B に機能を移行する場合)、次の手順と手順を使用する必要があります。

1.  サーバー B で MBAM セットアップを実行する

2.  サーバー B のコンプライアンスおよび監査レポートへのアクセスを構成する

3.  MBAM 管理および監視 web サイトのすべてのインスタンスを停止する

4.  MBAM 管理および監視サーバーでのレポート接続データの更新

5.  MBAM 管理および監視 web サイトのすべてのインスタンスを再開する

**サーバー B で MBAM セットアップを実行するには**

1.  サーバー B で MBAM セットアップを実行し、インストールのコンプライアンスと監査機能のみを選択します。

2.  この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを使用できます。

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=Reports COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ REPORTS_USERACCOUNTPW=$PASSWORD$`

    **注**  
    上の例の値を、環境に一致する値に置き換えます。

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-コンプライアンスステータスデータベースが配置されているサーバー名とインスタンスを入力します。

    -   $DOMAIN $ \ \ $USERNAME $-コンプライアンスと監査レポート機能で使用される、コンプライアンスステータスデータベースに接続するためのドメイン名とユーザー名を入力します。

    -   $PASSWORD $-コンプライアンスステータスデータベースへの接続に使用されるユーザーアカウントのパスワードを入力します。



**サーバー B のコンプライアンスおよび監査レポートへのアクセスを構成するには**

1.  サーバー B では、[サーバーマネージャー] から [ローカルユーザーとグループ] スナップインを使用して、コンプライアンスレポートおよび監査レポートへのアクセス権を持つユーザーアカウントを追加します。 ユーザーアカウントを "MBAM レポートユーザー" という名前のローカルグループに追加します。

2.  この手順を自動化するために、サーバー B で Windows PowerShell を使用することで、次のようなコマンドを使用できます。

    `PS C:\> net localgroup "MBAM Report Users" $DOMAIN$\$REPORTSUSERNAME$  /add`

    **注**  
    上の例の次の値を、環境に適した値に置き換えます。

    -   $DOMAIN $ \ \ $REPORTSUSERNAME $-コンプライアンスおよび監査レポートのデータソースを構成するために使用されたユーザーアカウント名を入力します。



~~~
The command to add the users to the MBAM Report Users local group must be run for each user that will be accessing the reports in your environment.
~~~

**MBAM 管理と監視 web サイトのすべてのインスタンスを停止するには**

1.  MBAM 管理と監視機能を実行する各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、 **Microsoft BitLocker の管理と監視と**いう名前の mbam web サイトを停止します。

2.  この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを使用できます。

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

**MBAM 管理および監視サーバーでデータベース接続データを更新するには**

1. MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、コンプライアンスレポート URL を更新します。

2. **Microsoft BitLocker の管理と監視**の web サイトを選び、**機能ビュー**の [**管理**] セクションにある [**構成エディター** ] 機能を使用します。

3. [セクションリスト] コントロールから [ **appSettings** ] オプションを選びます。

4. ここで、 **(コレクション)** という名前の行を選び、行の右側にあるボタンを選択して、**コレクションエディター**を開きます。

5. **コレクションエディター**で、"Microsoft Mbam. .url" という名前の行を選びます。

6. サーバー B のサーバー名を反映するには、"Mbam" の値を更新します。コンプライアンスと監査レポート機能が名前付き SQL Reporting Services インスタンスにインストールされている場合は、URL にインスタンスの名前を追加または更新してください。 たとえば、http://$SERVERNAME $/Report/Pages.... $ SQLSRSINSTANCENAME $

7. この手順を自動化するために、Windows PowerShell を使用して、各管理および監視サーバーに次のようなコマンドを入力できます。

   `PS C:\> Set-WebConfigurationProperty '/appSettings/add[@key="Microsoft.Mbam.Reports.Url"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring" -Name "Value" -Value “http://$SERVERNAME$/ReportServer_$SRSINSTANCENAME$/Pages/ReportViewer.aspx?/Malta+Compliance+Reports/”`

   **注**  
   上の例の値を、使用している環境に一致する値に置き換えます。

   -   $SERVERNAME $: コンプライアンスと監査レポートがインストールされたサーバーの名前を入力します。

   -   $SRSINSTANCENAME $-コンプライアンスと監査レポートがインストールされた SQL Reporting Services インスタンスの名前を入力します。



**MBAM 管理と監視 web サイトのすべてのインスタンスを再開するには**

1.  MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、 **Microsoft BitLocker の管理と監視と**いう名前の mbam web サイトを起動します。

2.  この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを使用できます。

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

    **注**  
    このコマンドを実行するには、powershell の IIS モジュールが PowerShell の現在のインスタンスに追加されている必要があります。 さらに、PowerShell の実行ポリシーを更新して、スクリプトの実行を有効にする必要があります。



## 管理と監視機能を移動するには


MBAM 管理と監視レポート機能をあるコンピューターから別のコンピューターに移動することを選択した場合 (機能をサーバー A からサーバー B に移動した場合) は、次の手順を使用する必要があります。 このプロセスには、次の手順が含まれます。

1.  サーバー B で MBAM セットアップを実行する

2.  サーバー B 上のデータベースへのアクセスを構成する

**サーバー B で MBAM セットアップを実行するには**

1.  サーバー B で MBAM セットアップを実行し、インストールの管理機能のみを選択します。

2.  この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを使用できます。

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=AdministrationMonitoringServer,HardwareCompatibility COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ RECOVERYANDHWDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ SRS_REPORTSITEURL=$REPORTSSERVERURL$`

    **注**  
    上の例の値を、環境に一致する値に置き換えます。

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-COMPLIDB \ _SQLINSTANCE パラメーターには、コンプライアンスステータスデータベースが配置されているサーバー名とインスタンスを入力します。 RECOVERYANDHWDB \ _SQLINSTANCE パラメーターには、回復とハードウェアデータベースが配置されているサーバー名とインスタンスを入力します。

    -   $DOMAIN $ \ \ $USERNAME $-コンプライアンスと監査レポート機能が使用するドメインとユーザー名を入力して、コンプライアンスステータスデータベースに接続します。

    -   $ ¥ SERVERURL $-SQL Reporting Service web サイトのホームの場所の URL を入力します。 レポートが既定の SRS インスタンスにインストールされている場合、URL 形式は "http://$SERVERNAME $/ReportServer" と書式設定されます。 レポートが既定の SRS インスタンスにインストールされていた場合、URL 形式は "http://$SERVERNAME $/report% _ $ SQLINSTANCENAME $" に書式設定されます。



**データベースへのアクセスを構成するには**

1.  回復とハードウェアを備えたサーバーまたはサーバーの場合また、コンプライアンスおよび監査データベースが展開されている場合は、サーバーマネージャーの [ローカルユーザーとグループ] スナップインを使用して、MBAM 管理と監視機能を実行する各サーバーから、"MBAM Recovery and Hardware DB Access" (Recovery and Hardware db Server) と "MBAM コンプライアンスステータス DB Access" (コンプライアンスおよび監査データベースサーバー) という名前の

2.  この手順を自動化するには、コンプライアンスデータベースと監査データベースが展開されているサーバー上で Windows PowerShell を使用することで、次のようなコマンドを使用できます。

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$REPORTSUSERNAME$  /add`

3.  回復とハードウェアデータベースが展開されたサーバーで、Windows PowerShell を使用して、次のようなコマンドを実行します。

    `PS C:\> net localgroup "MBAM Recovery and Hardware DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    **注**  
    上の例の値を、環境に適した値に置き換えます。

    -   $DOMAIN $ \ \ $SERVERNAME $ $-MBAM 管理および監視サーバーのドメインとコンピューター名を入力します。 サーバー名の後には、という名前を付ける必要があり **$** ます。 たとえば、MyDomain\\MyServerName1 $)

    -   $DOMAIN $ \ \ $REPORTSUSERNAME $-コンプライアンスおよび監査レポートのデータソースを構成するために使用されたユーザーアカウント名を入力します。



~~~
The commands listed for adding the server computer accounts to the MBAM local groups must be run for each Administration and Monitoring Server that will be accessing the databases in your environment.
~~~

## 関連トピック


[MBAM 1.0 機能の管理](administering-mbam-10-features.md)









