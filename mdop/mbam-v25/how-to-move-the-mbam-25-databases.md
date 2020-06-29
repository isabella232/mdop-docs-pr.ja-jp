---
title: MBAM 2.5 のデータベースを移動する方法
description: MBAM 2.5 のデータベースを移動する方法
author: dansimp
ms.assetid: 34b46f2d-0add-4377-8e4e-04b628fdfcf1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/15/2018
ms.openlocfilehash: 63c509e7ae1460ece815ef6c0a22350f76b52018
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812402"
---
# MBAM 2.5 のデータベースを移動する方法

次の手順を使用して、次のデータベースを別のコンピューターに移動します。サーバー A からサーバー B に、たとえば次のようにします。

-   コンプライアンスと監査データベース

-   回復用データベース

>[!NOTE]
>MBAM 構成ウィザードを実行する前に、コンピューター B にデータベースを復元して、それを更新または構成することが重要です。

データベースが存在しない場合、構成ウィザードでは、新しい空のデータベースが作成されます。 このプロセスによって既存のデータベースが復元されると、MBAM 構成が失われます。

データベースを復元してから、MBAM 構成ウィザードを実行して、[データベース] オプションを選択すると、構成ウィザードは復元したデータベースに "接続" します。プロセスの一部として必要に応じてアップグレードする。

**複数の機能を移動する場合は、次の順序で移動します。**

1.  回復用データベース

2.  コンプライアンスと監査データベース

3.  レポート

4.  管理と監視の Web サイト

5.  セルフサービスポータル

>[!Note]
>このトピックで説明する Windows PowerShell スクリプトの例を実行するには、Windows PowerShell 実行ポリシーを更新して、スクリプトを実行できるようにする必要があります。 手順については、「 [Windows PowerShell スクリプトを実行](https://technet.microsoft.com/library/ee176949.aspx)する」を参照してください。

## 回復用データベースを移動する

回復データベースを移動するための大まかな手順は、次のとおりです。

1.  MBAM 管理および監視 Web サイトのすべてのインスタンスを停止する

2.  サーバー A 上の回復データベースをバックアップする

3.  回復データベースをサーバー A からサーバー B に移動する

4.  サーバー B の回復データベースを復元する

5.  サーバー B 上のデータベースへのアクセスを構成し、接続データを更新する

6.  MBAM サーバーソフトウェアをインストールして、サーバー B で MBAM サーバー構成ウィザードを実行する

7.  管理と監視の Web サイトのインスタンスを再開する

### 回復データベースを移動する方法

**MBAM 管理と監視 Web サイトのすべてのインスタンスを停止します。** MBAM 管理と監視サーバー Web サイトを実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、管理と監視の Web サイトを停止します。

この手順を自動化するために、Windows PowerShell を使用して、次のようなコマンドを入力できます。

```powershell
Stop-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
>このコマンドを実行するには、windows PowerShell のインターネットインフォメーションサービス (IIS) モジュールを Windows PowerShell の現在のインスタンスに追加する必要があります。

### サーバー A 上の回復データベースをバックアップする

1.  SQL Server Management Studio で**バックアップ**タスクを使用して、サーバー A 上の回復データベースをバックアップします。 既定では、データベース名は**Mbam 回復データベース**です。

2.  この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成し、完全回復モードを使用するように MBAM 回復データベースを変更します。

    ```
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

3.  次の値を使用して、コード例の値を環境に一致する値に置き換えます。

    **$PASSWORD $** -秘密キーファイルの暗号化に使用するパスワード。

4.  Windows PowerShell で、ファイルに保存されている次のようなスクリプトを実行します。

    ```powershell
    Invoke-Sqlcmd -InputFile
    'Z:\BackupMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$
    ```
5.  次の値を使用して、コード例の値を環境に一致する値に置き換えます。

    **$SERVERNAME $ \ $SQLINSTANCENAME $** -サーバー名と回復データベースのバックアップ元のインスタンス。

### 回復データベースをサーバー A からサーバー B に移動する

Windows エクスプローラーを使用して、 **Mbam 回復データベースの .bak**ファイルをサーバー a からサーバー B に移動します。

この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを実行します。

```powershell
Copy-Item "Z:\MBAM Recovery Database Data.bak"
\\$SERVERNAME$\$DESTINATIONSHARE$

Copy-Item "Z:\SQLServerInstanceCertificateFile"
\\$SERVERNAME$\$DESTINATIONSHARE$

Copy-Item "Z:\SQLServerInstanceCertificateFilePrivateKey"
\\$SERVERNAME$\$DESTINATIONSHARE$
```
次の表の情報を使用して、コード例の値を環境に一致する値に置き換えます。

| **パラメーター**        | **説明**  |
|----------------------|------------------|
| $SERVERNAME $       | ファイルのコピー先となるサーバーの名前。 |
| $DESTINATIONSHARE $ | ファイルのコピー先の共有とパスの名前。 |


### サーバー B の回復データベースを復元する

1.  SQL Server Management Studio の**データベースの復元**タスクを使用して、サーバー B の回復データベースを復元します。

2.  前のタスクが完了したら、[**デバイスから**] を選択し、データベースバックアップファイルを選択します。

3.  [**追加**] コマンドを使用して、 **Mbam 回復データベースの .bak**ファイルを選び、[ **OK** ] をクリックして復元プロセスを完了します。

4.  この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成します。

    ```
    -- Restore MBAM Recovery Database.

    USE master

    GO

    -- Drop certificate created by MBAM Setup.

    DROP CERTIFICATE [MBAM Recovery Encryption Certificate]

    GO

    --Add certificate

    CREATE CERTIFICATE [MBAM Recovery Encryption Certificate]

    FROM FILE = 'Z:\SQLServerInstanceCertificateFile'

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

5.  次の値を使用して、コード例の値を環境に一致する値に置き換えます。

    **$PASSWORD $** -秘密キーファイルの暗号化に使用したパスワード。

6.  Windows PowerShell で、ファイルに保存されている次のようなスクリプトを実行します。

    ```powershell
    Invoke-Sqlcmd -InputFile 'Z:\RestoreMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$
    ```
7.  次の値を使用して、コード例の値を環境に一致する値に置き換えます。

    **$SERVERNAME $ \ $SQLINSTANCENAME $** -サーバー名と回復データベースが復元されるインスタンス。

### サーバー B 上のデータベースへのアクセスを構成し、接続データを更新する

1. 復元されたデータベースの回復データベースアクセスを有効にする Microsoft SQL Server ユーザーログインが、構成プロセスで指定したアクセスアカウントにマップされていることを確認します。

   >[!NOTE]
   >ログインが同じではない場合は、SQL Server Management Studio を使用してログインを作成し、既存のデータベースユーザーにマップします。

2. 管理と監視の Web サイトを実行しているサーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、MBAM web サイトの接続文字列情報を更新します。

3. 次のレジストリキーを編集します。

   **HKLM\\Software\\Microsoft\\MBAM Server\\ web¥ recoverydbconnectionstring**

4. 回復データベースの移動先のサーバーとインスタンスの名前 (\ $SERVERNAME \ $ \\ \ \ $SQLINSTANCENAME など) で、**データソース**の値を更新します。

5. 回復されたデータベース名で**最初のカタログ**の値を更新します。

6. このプロセスを自動化するために、Windows PowerShell コマンドプロンプトを使用して、次のような管理および監視サーバーにコマンドラインを入力することができます。

   ```powershell
   reg add "HKEY_LOCAL_MACHINE\SOFTWARE\\Microsoft\MBAM Server\\Web" /v
   RecoveryDBConnectionString /t REG_SZ /d "Integrated Security=SSPI;Initial
   Catalog=$DATABASE$;Data Source=$SERVERNAME$\$SQLINSTANCENAME$" /f

   Set-WebConfigurationProperty
   'connectionStrings/add[@name="KeyRecoveryConnectionString"]' -PSPath
   "IIS:\sites\Microsoft Bitlocker Administration and
   Monitoring\MBAMAdministrationService" -Name "connectionString" -Value "Data
   Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and
   Hardware;Integrated Security=SSPI;"

   Set-WebConfigurationProperty
   'connectionStrings/add[\@name="Microsoft.Mbam.RecoveryAndHardwareDataStore.ConnectionString"]'
   -PSPath "IIS:\sites\Microsoft Bitlocker Administration and
   Monitoring\MBAMRecoveryAndHardwareService" -Name "connectionString" -Value
   "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery
   and Hardware;Integrated Security=SSPI;"
   ```

   >[!Note]
   >この接続文字列は、すべてのローカル MBAM web アプリケーションによって共有されます。 そのため、サーバーごとに1回だけ更新する必要があります。


7. 次の表を使用して、コード例の値を環境に一致する値に置き換えます。

   |パラメーター|説明|
   |---------|-----------|
   |$SERVERNAME $/\ $SQLINSTANCENAME $|回復データベースが配置されているサーバー名と SQL Server のインスタンス。|
   |$DATABASE $|回復データベースの名前。|


### MBAM サーバーソフトウェアをインストールして、サーバー B で MBAM サーバー構成ウィザードを実行する

1.  サーバー B に MBAM 2.5 サーバーソフトウェアをインストールします。詳細については、「 [MBAM 2.5 サーバーソフトウェアをインストールする](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software)」を参照してください。

2.  サーバー B で、MBAM サーバー構成ウィザードを起動し、[**新しい機能の追加**] をクリックして、[**回復データベース**] 機能のみを選びます。 データベースの構成方法の詳細については、「 [MBAM 2.5 データベースを構成する方法](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases)」を参照してください。

    >[!TIP]
    >または、 **MbamDatabase** Windows PowerShell コマンドレットを使用して回復用データベースを構成することもできます。


### 管理と監視の Web サイトのインスタンスを再開する

管理と監視の Web サイトを実行しているサーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、管理と監視の Web サイトを開きます。

この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを実行します。

```powershell
Start-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
>このコマンドを実行するには、windows powershell の IIS モジュールを Windows PowerShell の現在のインスタンスに追加する必要があります。

## コンプライアンスと監査データベースを移動する

コンプライアンスと監査データベースを移動するための大まかな手順は、次のとおりです。

1.  MBAM 管理および監視 Web サイトのすべてのインスタンスを停止する

2.  サーバー A 上のコンプライアンスおよび監査データベースのバックアップを作成する

3.  コンプライアンスと監査データベースをサーバー A からサーバー B に移動する

4.  サーバー B でコンプライアンスと監査データベースを復元する

5.  サーバー B 上のデータベースへのアクセスを構成し、接続データを更新する

6.  MBAM サーバーソフトウェアをインストールして、サーバー B で MBAM サーバー構成ウィザードを実行する

7.  管理と監視の Web サイトのインスタンスを再開する

### コンプライアンスと監査データベースを移動する方法

**MBAM 管理と監視 Web サイトのすべてのインスタンスを停止します。**  MBAM 管理と監視サーバー Web サイトを実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、管理と監視の Web サイトを停止します。

この手順を自動化するために、Windows PowerShell を使用して、次のようなコマンドを入力できます。

```powershell
Stop-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
>このコマンドを実行するには、windows PowerShell のインターネットインフォメーションサービス (IIS) モジュールを Windows PowerShell の現在のインスタンスに追加する必要があります。

### サーバー A 上のコンプライアンスおよび監査データベースのバックアップを作成する

1.  SQL Server Management Studio で**バックアップ**タスクを使用して、Server A 上のコンプライアンスおよび監査データベースをバックアップします。既定では、データベース名は**Mbam コンプライアンスステータスデータベース**です。

2.  この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成します。

    ```
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

    -- Back up the full MBAM Compliance Recovery database.

    BACKUP DATABASE [MBAM Compliance Status] TO [MBAM Compliance Status Database Data Device];

    GO

    ```

3.  次のような Windows PowerShell コマンドを使用して、.sql ファイルに保存されているスクリプトを実行します。

    ```powershell
    Invoke-Sqlcmd -InputFile "Z:\BackupMBAMComplianceStatusDatabaseScript.sql" –ServerInstance     $SERVERNAME$\$SQLINSTANCENAME$

    ```

4.  次の値を使用して、コード例の値を環境に一致する値に置き換えます。

    **$SERVERNAME $ \ $SQLINSTANCENAME $** -server 名と、コンプライアンスおよび監査データベースがバックアップされるインスタンス。

### コンプライアンスと監査データベースをサーバー A からサーバー B に移動する * *

1.  Windows エクスプローラーを使用して、 **Mbam コンプライアンスの状態データベースデータ .bak**ファイルをサーバー a からサーバー B に移動します。

2.  この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを実行します。

    ```powershell
    Copy-Item "Z:\MBAM Compliance Status Database Data.bak"
    \\$SERVERNAME$\$DESTINATIONSHARE$
    ```

3.  次の表を使用して、コード例の値を環境に一致する値に置き換えます。

    | **パラメーター**        | **説明**                                               |
    |----------------------|---------------------------------------------------------------|
    | $SERVERNAME $       | ファイルのコピー先となるサーバーの名前。         |
    | $DESTINATIONSHARE $ | ファイルのコピー先の共有とパスの名前。 |


### サーバー B でコンプライアンスと監査データベースを復元する

1.  SQL Server Management Studio の**データベースの復元**タスクを使用して、Server B 上のコンプライアンスおよび監査データベースを復元します。

2.  前のタスクが完了したら、[**デバイスから**] を選択し、データベースバックアップファイルを選択します。

3.  [**追加**] コマンドを使用して、 **Mbam コンプライアンスの状態データベースデータ .bak**ファイルを選び、[ **OK** ] をクリックして復元プロセスを完了します。

4.  この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成します。

    ```
    -- Create MBAM Compliance Status Database Data logical backup devices.

    Use master

    GO

    -- Restore the MBAM Compliance Status database data files.

    RESTORE DATABASE [MBAM Compliance Status]

    FROM DISK = 'C:\test\MBAM Compliance Status Database Data.bak'

    WITH REPLACE

    ```

5.  Windows PowerShell で、ファイルに保存されている次のようなスクリプトを実行します。

    ```powershell
    Invoke-Sqlcmd -InputFile "Z:\RestoreMBAMComplianceStatusDatabaseScript.sql" -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$

    ```

6.  次の値を使用して、コード例の値を環境に一致する値に置き換えます。

    **$SERVERNAME $ \ $SQLINSTANCENAME $** -Server 名と、コンプライアンスおよび監査データベースが復元されるインスタンス。

### サーバー B 上のデータベースへのアクセスを構成し、接続データを更新する

1. 復元されたデータベースで、コンプライアンスと監査データベースへのアクセスを有効にする Microsoft SQL Server ユーザーログインが、構成プロセスで指定したアクセスアカウントにマップされていることを確認します。

   >[!NOTE]
   >ログインが同じではない場合は、SQL Server Management Studio を使用してログインを作成し、既存のデータベースユーザーにマップします。

2. 管理と監視の Web サイトを実行しているサーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、Web サイトの接続文字列情報を更新します。

3. 次のレジストリキーを編集します。

   **HKLM\\Software\\Microsoft\\MBAM Server\\Web\\ComplianceDBConnectionString**

4. 回復データベースの移動先のサーバーとインスタンスの名前 (\ $SERVERNAME \ $ \\ \ \ $SQLINSTANCENAME など) で、**データソース**の値を更新します。

5. 回復されたデータベース名で**最初のカタログ**の値を更新します。

6. このプロセスを自動化するために、Windows PowerShell コマンドプロンプトを使用して、次のような管理および監視サーバーにコマンドラインを入力することができます。

   ```powershell
   reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM Server\Web" /v
   ComplianceDBConnectionString /t REG_SZ /d "Integrated Security=SSPI;Initial
   Catalog=$DATABASE$;Data Source=$SERVERNAME$\$SQLINSTANCENAME$" /f
   ```
   >[!NOTE]
   >この接続文字列は、すべてのローカル MBAM web アプリケーションによって共有されます。 そのため、サーバーごとに1回だけ更新する必要があります。


7. 次の表を使用して、コード例の値を環境に一致する値に置き換えます。

   |パラメーター | 説明 |
   |---------|------------|
   |$SERVERNAME $ \ $SQLINSTANCENAME $ | 回復データベースが配置されているサーバー名と SQL Server のインスタンス。|
   |$DATABASE $|回復されたデータベースの名前。|

### MBAM サーバーソフトウェアをインストールして、サーバー B で MBAM サーバー構成ウィザードを実行する

1.  サーバー B に MBAM 2.5 サーバーソフトウェアをインストールします。詳細については、「 [MBAM 2.5 サーバーソフトウェアをインストールする](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software)」を参照してください。

2.  サーバー B で、MBAM サーバー構成ウィザードを起動し、[**新しい機能の追加**] をクリックして、[**コンプライアンスと監査データベース**] 機能のみを選択します。 データベースの構成方法の詳細については、「 [MBAM 2.5 データベースを構成する方法](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases)」を参照してください。

    >[!TIP]
    >または、 **MbamDatabase** Windows PowerShell コマンドレットを使用して、コンプライアンスと監査データベースを構成することもできます。


### 管理と監視の Web サイトのインスタンスを再開する

管理と監視の Web サイトを実行しているサーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、管理と監視の Web サイトを開きます。

この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを実行します。

```powershell
Start-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
>このコマンドを実行するには、windows powershell の IIS モジュールを Windows PowerShell の現在のインスタンスに追加する必要があります。
