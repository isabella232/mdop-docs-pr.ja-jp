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
# <span data-ttu-id="abf83-103">MBAM 2.5 のデータベースを移動する方法</span><span class="sxs-lookup"><span data-stu-id="abf83-103">How to Move the MBAM 2.5 Databases</span></span>

<span data-ttu-id="abf83-104">次の手順を使用して、次のデータベースを別のコンピューターに移動します。サーバー A からサーバー B に、たとえば次のようにします。</span><span class="sxs-lookup"><span data-stu-id="abf83-104">Use these procedures to move the following databases from one computer to another; from Server A to Server B, for example:</span></span>

-   <span data-ttu-id="abf83-105">コンプライアンスと監査データベース</span><span class="sxs-lookup"><span data-stu-id="abf83-105">Compliance and Audit Database</span></span>

-   <span data-ttu-id="abf83-106">回復用データベース</span><span class="sxs-lookup"><span data-stu-id="abf83-106">Recovery Database</span></span>

>[!NOTE]
><span data-ttu-id="abf83-107">MBAM 構成ウィザードを実行する前に、コンピューター B にデータベースを復元して、それを更新または構成することが重要です。</span><span class="sxs-lookup"><span data-stu-id="abf83-107">It is important that the databases be restored to Machine B PRIOR to running the MBAM Configuration Wizard to update/configure them.</span></span>

<span data-ttu-id="abf83-108">データベースが存在しない場合、構成ウィザードでは、新しい空のデータベースが作成されます。</span><span class="sxs-lookup"><span data-stu-id="abf83-108">If the databases are NOT present, the Configuration Wizard creates NEW, empty, databases.</span></span> <span data-ttu-id="abf83-109">このプロセスによって既存のデータベースが復元されると、MBAM 構成が失われます。</span><span class="sxs-lookup"><span data-stu-id="abf83-109">When your existing databases are then restored, this process will break the MBAM configuration.</span></span>

<span data-ttu-id="abf83-110">データベースを復元してから、MBAM 構成ウィザードを実行して、[データベース] オプションを選択すると、構成ウィザードは復元したデータベースに "接続" します。プロセスの一部として必要に応じてアップグレードする。</span><span class="sxs-lookup"><span data-stu-id="abf83-110">Restore the databases FIRST, then run the MBAM Configuration Wizard, choose the database option, and the Configuration Wizard will “connect” to the databases you restored; upgrading them if needed as part of the process.</span></span>

**<span data-ttu-id="abf83-111">複数の機能を移動する場合は、次の順序で移動します。</span><span class="sxs-lookup"><span data-stu-id="abf83-111">If you are moving multiple features, move them in the following order:</span></span>**

1.  <span data-ttu-id="abf83-112">回復用データベース</span><span class="sxs-lookup"><span data-stu-id="abf83-112">Recovery Database</span></span>

2.  <span data-ttu-id="abf83-113">コンプライアンスと監査データベース</span><span class="sxs-lookup"><span data-stu-id="abf83-113">Compliance and Audit Database</span></span>

3.  <span data-ttu-id="abf83-114">レポート</span><span class="sxs-lookup"><span data-stu-id="abf83-114">Reports</span></span>

4.  <span data-ttu-id="abf83-115">管理と監視の Web サイト</span><span class="sxs-lookup"><span data-stu-id="abf83-115">Administration and Monitoring Website</span></span>

5.  <span data-ttu-id="abf83-116">セルフサービスポータル</span><span class="sxs-lookup"><span data-stu-id="abf83-116">Self-Service Portal</span></span>

>[!Note]
><span data-ttu-id="abf83-117">このトピックで説明する Windows PowerShell スクリプトの例を実行するには、Windows PowerShell 実行ポリシーを更新して、スクリプトを実行できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="abf83-117">To run the example Windows PowerShell scripts provided in this topic, you must update the Windows PowerShell execution policy to enable scripts to be run.</span></span> <span data-ttu-id="abf83-118">手順については、「 [Windows PowerShell スクリプトを実行](https://technet.microsoft.com/library/ee176949.aspx)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abf83-118">See [Running Windows PowerShell Scripts](https://technet.microsoft.com/library/ee176949.aspx) for instructions.</span></span>

## <span data-ttu-id="abf83-119">回復用データベースを移動する</span><span class="sxs-lookup"><span data-stu-id="abf83-119">Move the Recovery Database</span></span>

<span data-ttu-id="abf83-120">回復データベースを移動するための大まかな手順は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="abf83-120">The high-level steps for moving the Recovery Database are:</span></span>

1.  <span data-ttu-id="abf83-121">MBAM 管理および監視 Web サイトのすべてのインスタンスを停止する</span><span class="sxs-lookup"><span data-stu-id="abf83-121">Stop all instances of the MBAM Administration and Monitoring Website</span></span>

2.  <span data-ttu-id="abf83-122">サーバー A 上の回復データベースをバックアップする</span><span class="sxs-lookup"><span data-stu-id="abf83-122">Back up the Recovery Database on Server A</span></span>

3.  <span data-ttu-id="abf83-123">回復データベースをサーバー A からサーバー B に移動する</span><span class="sxs-lookup"><span data-stu-id="abf83-123">Move the Recovery Database from Server A to Server B</span></span>

4.  <span data-ttu-id="abf83-124">サーバー B の回復データベースを復元する</span><span class="sxs-lookup"><span data-stu-id="abf83-124">Restore the Recovery Database on Server B</span></span>

5.  <span data-ttu-id="abf83-125">サーバー B 上のデータベースへのアクセスを構成し、接続データを更新する</span><span class="sxs-lookup"><span data-stu-id="abf83-125">Configure access to the Database on Server B and update connection data</span></span>

6.  <span data-ttu-id="abf83-126">MBAM サーバーソフトウェアをインストールして、サーバー B で MBAM サーバー構成ウィザードを実行する</span><span class="sxs-lookup"><span data-stu-id="abf83-126">Install MBAM Server software and run the MBAM Server Configuration wizard on Server B</span></span>

7.  <span data-ttu-id="abf83-127">管理と監視の Web サイトのインスタンスを再開する</span><span class="sxs-lookup"><span data-stu-id="abf83-127">Resume the instance of the Administration and Monitoring Website</span></span>

### <span data-ttu-id="abf83-128">回復データベースを移動する方法</span><span class="sxs-lookup"><span data-stu-id="abf83-128">How to move the Recovery Database</span></span>

**<span data-ttu-id="abf83-129">MBAM 管理と監視 Web サイトのすべてのインスタンスを停止します。</span><span class="sxs-lookup"><span data-stu-id="abf83-129">Stop all instances of the MBAM Administration and Monitoring Website.</span></span>** <span data-ttu-id="abf83-130">MBAM 管理と監視サーバー Web サイトを実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、管理と監視の Web サイトを停止します。</span><span class="sxs-lookup"><span data-stu-id="abf83-130">On each server that is running the MBAM Administration and Monitoring Server Website, use the Internet Information Services (IIS) Manager console to stop the Administration and Monitoring Website.</span></span>

<span data-ttu-id="abf83-131">この手順を自動化するために、Windows PowerShell を使用して、次のようなコマンドを入力できます。</span><span class="sxs-lookup"><span data-stu-id="abf83-131">To automate this procedure, you can use Windows PowerShell to enter a command that is similar to the following:</span></span>

```powershell
Stop-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
><span data-ttu-id="abf83-132">このコマンドを実行するには、windows PowerShell のインターネットインフォメーションサービス (IIS) モジュールを Windows PowerShell の現在のインスタンスに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abf83-132">To run this command, you must add the Internet Information Services (IIS) module for Windows PowerShell to the current instance of Windows PowerShell.</span></span>

### <span data-ttu-id="abf83-133">サーバー A 上の回復データベースをバックアップする</span><span class="sxs-lookup"><span data-stu-id="abf83-133">Back up the Recovery Database on Server A</span></span>

1.  <span data-ttu-id="abf83-134">SQL Server Management Studio で**バックアップ**タスクを使用して、サーバー A 上の回復データベースをバックアップします。 既定では、データベース名は**Mbam 回復データベース**です。</span><span class="sxs-lookup"><span data-stu-id="abf83-134">Use the **Back Up** task in SQL Server Management Studio to back up the Recovery Database on Server A.  By default, the database name is **MBAM Recovery Database**.</span></span>

2.  <span data-ttu-id="abf83-135">この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成し、完全回復モードを使用するように MBAM 回復データベースを変更します。</span><span class="sxs-lookup"><span data-stu-id="abf83-135">To automate this procedure, create a SQL file (.sql) that contains the following SQL script, and change the MBAM Recovery Database to use the full recovery mode:</span></span>

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

3.  <span data-ttu-id="abf83-136">次の値を使用して、コード例の値を環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="abf83-136">Use the following value to replace the values in the code example with values that match your environment:</span></span>

    <span data-ttu-id="abf83-137">**$PASSWORD $** -秘密キーファイルの暗号化に使用するパスワード。</span><span class="sxs-lookup"><span data-stu-id="abf83-137">**$PASSWORD$** - password that you use to encrypt the Private Key file.</span></span>

4.  <span data-ttu-id="abf83-138">Windows PowerShell で、ファイルに保存されている次のようなスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="abf83-138">In Windows PowerShell, run the script that is stored in the file and similar to the following:</span></span>

    ```powershell
    Invoke-Sqlcmd -InputFile
    'Z:\BackupMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$
    ```
5.  <span data-ttu-id="abf83-139">次の値を使用して、コード例の値を環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="abf83-139">Use the following value to replace the values in the code example with values that match your environment:</span></span>

    <span data-ttu-id="abf83-140">**$SERVERNAME $ \ $SQLINSTANCENAME $** -サーバー名と回復データベースのバックアップ元のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="abf83-140">**$SERVERNAME$\$SQLINSTANCENAME$** - server name and instance from which the Recovery Database will be backed up.</span></span>

### <span data-ttu-id="abf83-141">回復データベースをサーバー A からサーバー B に移動する</span><span class="sxs-lookup"><span data-stu-id="abf83-141">Move the Recovery Database from Server A to Server B</span></span>

<span data-ttu-id="abf83-142">Windows エクスプローラーを使用して、 **Mbam 回復データベースの .bak**ファイルをサーバー a からサーバー B に移動します。</span><span class="sxs-lookup"><span data-stu-id="abf83-142">Use Windows Explorer to move the **MBAM Recovery Database Data.bak** file from Server A to Server B.</span></span>

<span data-ttu-id="abf83-143">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="abf83-143">To automate this procedure, you can use Windows PowerShell to run a command that is similar to the following:</span></span>

```powershell
Copy-Item "Z:\MBAM Recovery Database Data.bak"
\\$SERVERNAME$\$DESTINATIONSHARE$

Copy-Item "Z:\SQLServerInstanceCertificateFile"
\\$SERVERNAME$\$DESTINATIONSHARE$

Copy-Item "Z:\SQLServerInstanceCertificateFilePrivateKey"
\\$SERVERNAME$\$DESTINATIONSHARE$
```
<span data-ttu-id="abf83-144">次の表の情報を使用して、コード例の値を環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="abf83-144">Use the information in the following table to replace the values in the code example with values that match your environment.</span></span>

| **<span data-ttu-id="abf83-145">パラメーター</span><span class="sxs-lookup"><span data-stu-id="abf83-145">Parameter</span></span>**        | **<span data-ttu-id="abf83-146">説明</span><span class="sxs-lookup"><span data-stu-id="abf83-146">Description</span></span>**  |
|----------------------|------------------|
| <span data-ttu-id="abf83-147">$SERVERNAME $</span><span class="sxs-lookup"><span data-stu-id="abf83-147">$SERVERNAME$</span></span>       | <span data-ttu-id="abf83-148">ファイルのコピー先となるサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="abf83-148">Name of the server to which the files will be copied.</span></span> |
| <span data-ttu-id="abf83-149">$DESTINATIONSHARE $</span><span class="sxs-lookup"><span data-stu-id="abf83-149">$DESTINATIONSHARE$</span></span> | <span data-ttu-id="abf83-150">ファイルのコピー先の共有とパスの名前。</span><span class="sxs-lookup"><span data-stu-id="abf83-150">Name of the share and path to which the files will be copied.</span></span> |


### <span data-ttu-id="abf83-151">サーバー B の回復データベースを復元する</span><span class="sxs-lookup"><span data-stu-id="abf83-151">Restore the Recovery Database on Server B</span></span>

1.  <span data-ttu-id="abf83-152">SQL Server Management Studio の**データベースの復元**タスクを使用して、サーバー B の回復データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="abf83-152">Restore the Recovery Database on Server B by using the **Restore Database** task in SQL Server Management Studio.</span></span>

2.  <span data-ttu-id="abf83-153">前のタスクが完了したら、[**デバイスから**] を選択し、データベースバックアップファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="abf83-153">When the previous task finishes, select **From Device**, and then select the database backup file.</span></span>

3.  <span data-ttu-id="abf83-154">[**追加**] コマンドを使用して、 **Mbam 回復データベースの .bak**ファイルを選び、[ **OK** ] をクリックして復元プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="abf83-154">Use the **Add** command to select the **MBAM Recovery Database Data.bak** file, and click **OK** to complete the restoration process.</span></span>

4.  <span data-ttu-id="abf83-155">この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成します。</span><span class="sxs-lookup"><span data-stu-id="abf83-155">To automate this procedure, create a SQL file (.sql) that contains the following SQL script:</span></span>

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

5.  <span data-ttu-id="abf83-156">次の値を使用して、コード例の値を環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="abf83-156">Use the following value to replace the values in the code example with values that match your environment.</span></span>

    <span data-ttu-id="abf83-157">**$PASSWORD $** -秘密キーファイルの暗号化に使用したパスワード。</span><span class="sxs-lookup"><span data-stu-id="abf83-157">**$PASSWORD$** - password that you used to encrypt the Private Key file.</span></span>

6.  <span data-ttu-id="abf83-158">Windows PowerShell で、ファイルに保存されている次のようなスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="abf83-158">In Windows PowerShell, run the script that is stored in the file and similar to the following:</span></span>

    ```powershell
    Invoke-Sqlcmd -InputFile 'Z:\RestoreMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$
    ```
7.  <span data-ttu-id="abf83-159">次の値を使用して、コード例の値を環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="abf83-159">Use the following value to replace the values in the code example with values that match your environment.</span></span>

    <span data-ttu-id="abf83-160">**$SERVERNAME $ \ $SQLINSTANCENAME $** -サーバー名と回復データベースが復元されるインスタンス。</span><span class="sxs-lookup"><span data-stu-id="abf83-160">**$SERVERNAME$\$SQLINSTANCENAME$** - Server name and instance to which the Recovery Database will be restored.</span></span>

### <span data-ttu-id="abf83-161">サーバー B 上のデータベースへのアクセスを構成し、接続データを更新する</span><span class="sxs-lookup"><span data-stu-id="abf83-161">Configure access to the Database on Server B and update connection data</span></span>

1. <span data-ttu-id="abf83-162">復元されたデータベースの回復データベースアクセスを有効にする Microsoft SQL Server ユーザーログインが、構成プロセスで指定したアクセスアカウントにマップされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="abf83-162">Verify that the Microsoft SQL Server user login that enables Recovery Database access on the restored database is mapped to the access account that you provided during the configuration process.</span></span>

   >[!NOTE]
   ><span data-ttu-id="abf83-163">ログインが同じではない場合は、SQL Server Management Studio を使用してログインを作成し、既存のデータベースユーザーにマップします。</span><span class="sxs-lookup"><span data-stu-id="abf83-163">If the login is not the same, create a login by using SQL Server Management Studio, and map it to the existing database user.</span></span>

2. <span data-ttu-id="abf83-164">管理と監視の Web サイトを実行しているサーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、MBAM web サイトの接続文字列情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="abf83-164">On the server that is running the Administration and Monitoring Website, use the Internet Information Services (IIS) Manager console to update the connection string information for the MBAM websites.</span></span>

3. <span data-ttu-id="abf83-165">次のレジストリキーを編集します。</span><span class="sxs-lookup"><span data-stu-id="abf83-165">Edit the following registry key:</span></span>

   **<span data-ttu-id="abf83-166">HKLM\\Software\\Microsoft\\MBAM Server\\ web¥ recoverydbconnectionstring</span><span class="sxs-lookup"><span data-stu-id="abf83-166">HKLM\\Software\\Microsoft\\MBAM Server\\Web\\RecoveryDBConnectionString</span></span>**

4. <span data-ttu-id="abf83-167">回復データベースの移動先のサーバーとインスタンスの名前 (\ $SERVERNAME \ $ \\ \ \ $SQLINSTANCENAME など) で、**データソース**の値を更新します。</span><span class="sxs-lookup"><span data-stu-id="abf83-167">Update the **Data Source** value with the name of the server and instance (for example, \$SERVERNAME\$\\\$SQLINSTANCENAME) to which the Recovery Database was moved.</span></span>

5. <span data-ttu-id="abf83-168">回復されたデータベース名で**最初のカタログ**の値を更新します。</span><span class="sxs-lookup"><span data-stu-id="abf83-168">Update the **Initial Catalog** value with the recovered database name.</span></span>

6. <span data-ttu-id="abf83-169">このプロセスを自動化するために、Windows PowerShell コマンドプロンプトを使用して、次のような管理および監視サーバーにコマンドラインを入力することができます。</span><span class="sxs-lookup"><span data-stu-id="abf83-169">To automate this process, you can use the Windows PowerShell command prompt to enter a command line on the Administration and Monitoring Server that is similar to the following:</span></span>

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
   ><span data-ttu-id="abf83-170">この接続文字列は、すべてのローカル MBAM web アプリケーションによって共有されます。</span><span class="sxs-lookup"><span data-stu-id="abf83-170">This connection string is shared by all local MBAM web applications.</span></span> <span data-ttu-id="abf83-171">そのため、サーバーごとに1回だけ更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abf83-171">Therefore, it needs to be updated only once per server.</span></span>


7. <span data-ttu-id="abf83-172">次の表を使用して、コード例の値を環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="abf83-172">Use the following table to replace the values in the code example with values that match your environment.</span></span>

   |<span data-ttu-id="abf83-173">パラメーター</span><span class="sxs-lookup"><span data-stu-id="abf83-173">Parameter</span></span>|<span data-ttu-id="abf83-174">説明</span><span class="sxs-lookup"><span data-stu-id="abf83-174">Description</span></span>|
   |---------|-----------|
   |<span data-ttu-id="abf83-175">$SERVERNAME $/\ $SQLINSTANCENAME $</span><span class="sxs-lookup"><span data-stu-id="abf83-175">$SERVERNAME$/\$SQLINSTANCENAME$</span></span>|<span data-ttu-id="abf83-176">回復データベースが配置されているサーバー名と SQL Server のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="abf83-176">Server name and instance of SQL Server where the Recovery Database is located.</span></span>|
   |<span data-ttu-id="abf83-177">$DATABASE $</span><span class="sxs-lookup"><span data-stu-id="abf83-177">$DATABASE$</span></span>|<span data-ttu-id="abf83-178">回復データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="abf83-178">Name of the Recovery database.</span></span>|


### <span data-ttu-id="abf83-179">MBAM サーバーソフトウェアをインストールして、サーバー B で MBAM サーバー構成ウィザードを実行する</span><span class="sxs-lookup"><span data-stu-id="abf83-179">Install MBAM Server software and run the MBAM Server Configuration wizard on Server B</span></span>

1.  <span data-ttu-id="abf83-180">サーバー B に MBAM 2.5 サーバーソフトウェアをインストールします。詳細については、「 [MBAM 2.5 サーバーソフトウェアをインストールする](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abf83-180">Install the MBAM 2.5 Server software on Server B. For details, see [Installing the MBAM 2.5 Server Software](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software).</span></span>

2.  <span data-ttu-id="abf83-181">サーバー B で、MBAM サーバー構成ウィザードを起動し、[**新しい機能の追加**] をクリックして、[**回復データベース**] 機能のみを選びます。</span><span class="sxs-lookup"><span data-stu-id="abf83-181">On Server B, start the MBAM Server Configuration wizard, click **Add New Features**, and then select only the **Recovery Database** feature.</span></span> <span data-ttu-id="abf83-182">データベースの構成方法の詳細については、「 [MBAM 2.5 データベースを構成する方法](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abf83-182">For details on how to configure the databases, see [How to Configure the MBAM 2.5 Databases](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases).</span></span>

    >[!TIP]
    ><span data-ttu-id="abf83-183">または、 **MbamDatabase** Windows PowerShell コマンドレットを使用して回復用データベースを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="abf83-183">Alternatively, you can use the **Enable-MbamDatabase** Windows PowerShell cmdlet to configure the Recovery Database.</span></span>


### <span data-ttu-id="abf83-184">管理と監視の Web サイトのインスタンスを再開する</span><span class="sxs-lookup"><span data-stu-id="abf83-184">Resume the instance of the Administration and Monitoring Website</span></span>

<span data-ttu-id="abf83-185">管理と監視の Web サイトを実行しているサーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、管理と監視の Web サイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="abf83-185">On the server that is running the Administration and Monitoring Website, use the Internet Information Services (IIS) Manager console to start the Administration and Monitoring Website.</span></span>

<span data-ttu-id="abf83-186">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="abf83-186">To automate this procedure, you can use Windows PowerShell to run a command that is similar to the following:</span></span>

```powershell
Start-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
><span data-ttu-id="abf83-187">このコマンドを実行するには、windows powershell の IIS モジュールを Windows PowerShell の現在のインスタンスに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abf83-187">To run this command, you must add the IIS module for Windows PowerShell to the current instance of Windows PowerShell.</span></span>

## <span data-ttu-id="abf83-188">コンプライアンスと監査データベースを移動する</span><span class="sxs-lookup"><span data-stu-id="abf83-188">Move the Compliance and Audit Database</span></span>

<span data-ttu-id="abf83-189">コンプライアンスと監査データベースを移動するための大まかな手順は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="abf83-189">The high-level steps for moving the Compliance and Audit Database are:</span></span>

1.  <span data-ttu-id="abf83-190">MBAM 管理および監視 Web サイトのすべてのインスタンスを停止する</span><span class="sxs-lookup"><span data-stu-id="abf83-190">Stop all instances of the MBAM Administration and Monitoring Website</span></span>

2.  <span data-ttu-id="abf83-191">サーバー A 上のコンプライアンスおよび監査データベースのバックアップを作成する</span><span class="sxs-lookup"><span data-stu-id="abf83-191">Back up the Compliance and Audit Database on Server A</span></span>

3.  <span data-ttu-id="abf83-192">コンプライアンスと監査データベースをサーバー A からサーバー B に移動する</span><span class="sxs-lookup"><span data-stu-id="abf83-192">Move the Compliance and Audit Database from Server A to Server B</span></span>

4.  <span data-ttu-id="abf83-193">サーバー B でコンプライアンスと監査データベースを復元する</span><span class="sxs-lookup"><span data-stu-id="abf83-193">Restore the Compliance and Audit Database on Server B</span></span>

5.  <span data-ttu-id="abf83-194">サーバー B 上のデータベースへのアクセスを構成し、接続データを更新する</span><span class="sxs-lookup"><span data-stu-id="abf83-194">Configure access to the Database on Server B and update connection data</span></span>

6.  <span data-ttu-id="abf83-195">MBAM サーバーソフトウェアをインストールして、サーバー B で MBAM サーバー構成ウィザードを実行する</span><span class="sxs-lookup"><span data-stu-id="abf83-195">Install MBAM Server software and run the MBAM Server Configuration wizard on Server B</span></span>

7.  <span data-ttu-id="abf83-196">管理と監視の Web サイトのインスタンスを再開する</span><span class="sxs-lookup"><span data-stu-id="abf83-196">Resume the instance of the Administration and Monitoring Website</span></span>

### <span data-ttu-id="abf83-197">コンプライアンスと監査データベースを移動する方法</span><span class="sxs-lookup"><span data-stu-id="abf83-197">How to move the Compliance and Audit Database</span></span>

**<span data-ttu-id="abf83-198">MBAM 管理と監視 Web サイトのすべてのインスタンスを停止します。</span><span class="sxs-lookup"><span data-stu-id="abf83-198">Stop all instances of the MBAM Administration and Monitoring Website.</span></span>**  <span data-ttu-id="abf83-199">MBAM 管理と監視サーバー Web サイトを実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、管理と監視の Web サイトを停止します。</span><span class="sxs-lookup"><span data-stu-id="abf83-199">On each server that is running the MBAM Administration and Monitoring Server Website, use the Internet Information Services (IIS) Manager console to stop the Administration and Monitoring Website.</span></span>

<span data-ttu-id="abf83-200">この手順を自動化するために、Windows PowerShell を使用して、次のようなコマンドを入力できます。</span><span class="sxs-lookup"><span data-stu-id="abf83-200">To automate this procedure, you can use Windows PowerShell to enter a command that is similar to the following:</span></span>

```powershell
Stop-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
><span data-ttu-id="abf83-201">このコマンドを実行するには、windows PowerShell のインターネットインフォメーションサービス (IIS) モジュールを Windows PowerShell の現在のインスタンスに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abf83-201">To run this command, you must add the Internet Information Services (IIS) module for Windows PowerShell to the current instance of Windows PowerShell.</span></span>

### <span data-ttu-id="abf83-202">サーバー A 上のコンプライアンスおよび監査データベースのバックアップを作成する</span><span class="sxs-lookup"><span data-stu-id="abf83-202">Back up the Compliance and Audit Database on Server A</span></span>

1.  <span data-ttu-id="abf83-203">SQL Server Management Studio で**バックアップ**タスクを使用して、Server A 上のコンプライアンスおよび監査データベースをバックアップします。既定では、データベース名は**Mbam コンプライアンスステータスデータベース**です。</span><span class="sxs-lookup"><span data-stu-id="abf83-203">Use the **Back Up** task in SQL Server Management Studio to back up the Compliance and Audit Database on Server A. By default, the database name is **MBAM Compliance Status Database**.</span></span>

2.  <span data-ttu-id="abf83-204">この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成します。</span><span class="sxs-lookup"><span data-stu-id="abf83-204">To automate this procedure, create a SQL file (.sql) that contains the following SQL script:</span></span>

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

3.  <span data-ttu-id="abf83-205">次のような Windows PowerShell コマンドを使用して、.sql ファイルに保存されているスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="abf83-205">Run the script that is stored in the .sql file by using a Windows PowerShell command that is similar to the following:</span></span>

    ```powershell
    Invoke-Sqlcmd -InputFile "Z:\BackupMBAMComplianceStatusDatabaseScript.sql" –ServerInstance     $SERVERNAME$\$SQLINSTANCENAME$

    ```

4.  <span data-ttu-id="abf83-206">次の値を使用して、コード例の値を環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="abf83-206">Using the following value, replace the values in the code example with values that match your environment:</span></span>

    <span data-ttu-id="abf83-207">**$SERVERNAME $ \ $SQLINSTANCENAME $** -server 名と、コンプライアンスおよび監査データベースがバックアップされるインスタンス。</span><span class="sxs-lookup"><span data-stu-id="abf83-207">**$SERVERNAME$\$SQLINSTANCENAME$** - server name and instance from which the Compliance and Audit Database will be backed up.</span></span>

### <span data-ttu-id="abf83-208">コンプライアンスと監査データベースをサーバー A からサーバー B に移動する \* \*</span><span class="sxs-lookup"><span data-stu-id="abf83-208">Move the Compliance and Audit Database from Server A to Server B\*\*</span></span>

1.  <span data-ttu-id="abf83-209">Windows エクスプローラーを使用して、 **Mbam コンプライアンスの状態データベースデータ .bak**ファイルをサーバー a からサーバー B に移動します。</span><span class="sxs-lookup"><span data-stu-id="abf83-209">Use Windows Explorer to move the **MBAM Compliance Status Database Data.bak** file from Server A to Server B.</span></span>

2.  <span data-ttu-id="abf83-210">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="abf83-210">To automate this procedure, you can use Windows PowerShell to run a command that is similar to the following:</span></span>

    ```powershell
    Copy-Item "Z:\MBAM Compliance Status Database Data.bak"
    \\$SERVERNAME$\$DESTINATIONSHARE$
    ```

3.  <span data-ttu-id="abf83-211">次の表を使用して、コード例の値を環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="abf83-211">Using the following table, replace the values in the code example with values that match your environment.</span></span>

    | **<span data-ttu-id="abf83-212">パラメーター</span><span class="sxs-lookup"><span data-stu-id="abf83-212">Parameter</span></span>**        | **<span data-ttu-id="abf83-213">説明</span><span class="sxs-lookup"><span data-stu-id="abf83-213">Description</span></span>**                                               |
    |----------------------|---------------------------------------------------------------|
    | <span data-ttu-id="abf83-214">$SERVERNAME $</span><span class="sxs-lookup"><span data-stu-id="abf83-214">$SERVERNAME$</span></span>       | <span data-ttu-id="abf83-215">ファイルのコピー先となるサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="abf83-215">Name of the server to which the files will be copied.</span></span>         |
    | <span data-ttu-id="abf83-216">$DESTINATIONSHARE $</span><span class="sxs-lookup"><span data-stu-id="abf83-216">$DESTINATIONSHARE$</span></span> | <span data-ttu-id="abf83-217">ファイルのコピー先の共有とパスの名前。</span><span class="sxs-lookup"><span data-stu-id="abf83-217">Name of the share and path to which the files will be copied.</span></span> |


### <span data-ttu-id="abf83-218">サーバー B でコンプライアンスと監査データベースを復元する</span><span class="sxs-lookup"><span data-stu-id="abf83-218">Restore the Compliance and Audit Database on Server B</span></span>

1.  <span data-ttu-id="abf83-219">SQL Server Management Studio の**データベースの復元**タスクを使用して、Server B 上のコンプライアンスおよび監査データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="abf83-219">Restore the Compliance and Audit Database on Server B by using the **Restore Database** task in SQL Server Management Studio.</span></span>

2.  <span data-ttu-id="abf83-220">前のタスクが完了したら、[**デバイスから**] を選択し、データベースバックアップファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="abf83-220">When the previous task finishes, select **From Device**, and then select the database backup file.</span></span>

3.  <span data-ttu-id="abf83-221">[**追加**] コマンドを使用して、 **Mbam コンプライアンスの状態データベースデータ .bak**ファイルを選び、[ **OK** ] をクリックして復元プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="abf83-221">Use the **Add** command to select the **MBAM Compliance Status Database Data.bak** file and click **OK** to complete the restoration process.</span></span>

4.  <span data-ttu-id="abf83-222">この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成します。</span><span class="sxs-lookup"><span data-stu-id="abf83-222">To automate this procedure, create a SQL file (.sql) that contains the following SQL script:</span></span>

    ```
    -- Create MBAM Compliance Status Database Data logical backup devices.

    Use master

    GO

    -- Restore the MBAM Compliance Status database data files.

    RESTORE DATABASE [MBAM Compliance Status]

    FROM DISK = 'C:\test\MBAM Compliance Status Database Data.bak'

    WITH REPLACE

    ```

5.  <span data-ttu-id="abf83-223">Windows PowerShell で、ファイルに保存されている次のようなスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="abf83-223">In Windows PowerShell, run the script that is stored in the file and similar to the following:</span></span>

    ```powershell
    Invoke-Sqlcmd -InputFile "Z:\RestoreMBAMComplianceStatusDatabaseScript.sql" -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$

    ```

6.  <span data-ttu-id="abf83-224">次の値を使用して、コード例の値を環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="abf83-224">Using the following value, replace the values in the code example with values that match your environment.</span></span>

    <span data-ttu-id="abf83-225">**$SERVERNAME $ \ $SQLINSTANCENAME $** -Server 名と、コンプライアンスおよび監査データベースが復元されるインスタンス。</span><span class="sxs-lookup"><span data-stu-id="abf83-225">**$SERVERNAME$\$SQLINSTANCENAME$** - Server name and instance to which the Compliance and Audit Database will be restored.</span></span>

### <span data-ttu-id="abf83-226">サーバー B 上のデータベースへのアクセスを構成し、接続データを更新する</span><span class="sxs-lookup"><span data-stu-id="abf83-226">Configure access to the Database on Server B and update connection data</span></span>

1. <span data-ttu-id="abf83-227">復元されたデータベースで、コンプライアンスと監査データベースへのアクセスを有効にする Microsoft SQL Server ユーザーログインが、構成プロセスで指定したアクセスアカウントにマップされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="abf83-227">Verify that the Microsoft SQL Server user login that enables Compliance and Audit Database access on the restored database is mapped to the access account that you provided during the configuration process.</span></span>

   >[!NOTE]
   ><span data-ttu-id="abf83-228">ログインが同じではない場合は、SQL Server Management Studio を使用してログインを作成し、既存のデータベースユーザーにマップします。</span><span class="sxs-lookup"><span data-stu-id="abf83-228">If the login is not the same, create a login by using SQL Server Management Studio, and map it to the existing database user.</span></span>

2. <span data-ttu-id="abf83-229">管理と監視の Web サイトを実行しているサーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、Web サイトの接続文字列情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="abf83-229">On the server that is running the Administration and Monitoring Website, use the Internet Information Services (IIS) Manager console to update the connection string information for the Website.</span></span>

3. <span data-ttu-id="abf83-230">次のレジストリキーを編集します。</span><span class="sxs-lookup"><span data-stu-id="abf83-230">Edit the following registry key:</span></span>

   **<span data-ttu-id="abf83-231">HKLM\\Software\\Microsoft\\MBAM Server\\Web\\ComplianceDBConnectionString</span><span class="sxs-lookup"><span data-stu-id="abf83-231">HKLM\\Software\\Microsoft\\MBAM Server\\Web\\ComplianceDBConnectionString</span></span>**

4. <span data-ttu-id="abf83-232">回復データベースの移動先のサーバーとインスタンスの名前 (\ $SERVERNAME \ $ \\ \ \ $SQLINSTANCENAME など) で、**データソース**の値を更新します。</span><span class="sxs-lookup"><span data-stu-id="abf83-232">Update the **Data Source** value with the name of the server and instance (for example, \$SERVERNAME\$\\\$SQLINSTANCENAME) to which the Recovery Database was moved.</span></span>

5. <span data-ttu-id="abf83-233">回復されたデータベース名で**最初のカタログ**の値を更新します。</span><span class="sxs-lookup"><span data-stu-id="abf83-233">Update the **Initial Catalog** value with the recovered database name.</span></span>

6. <span data-ttu-id="abf83-234">このプロセスを自動化するために、Windows PowerShell コマンドプロンプトを使用して、次のような管理および監視サーバーにコマンドラインを入力することができます。</span><span class="sxs-lookup"><span data-stu-id="abf83-234">To automate this process, you can use the Windows PowerShell command prompt to enter a command line on the Administration and Monitoring Server that is similar to the following:</span></span>

   ```powershell
   reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM Server\Web" /v
   ComplianceDBConnectionString /t REG_SZ /d "Integrated Security=SSPI;Initial
   Catalog=$DATABASE$;Data Source=$SERVERNAME$\$SQLINSTANCENAME$" /f
   ```
   >[!NOTE]
   ><span data-ttu-id="abf83-235">この接続文字列は、すべてのローカル MBAM web アプリケーションによって共有されます。</span><span class="sxs-lookup"><span data-stu-id="abf83-235">This connection string is shared by all local MBAM web applications.</span></span> <span data-ttu-id="abf83-236">そのため、サーバーごとに1回だけ更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abf83-236">Therefore, it needs to be updated only once per server.</span></span>


7. <span data-ttu-id="abf83-237">次の表を使用して、コード例の値を環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="abf83-237">Using the following table, replace the values in the code example with values that match your environment.</span></span>

   |<span data-ttu-id="abf83-238">パラメーター</span><span class="sxs-lookup"><span data-stu-id="abf83-238">Parameter</span></span> | <span data-ttu-id="abf83-239">説明</span><span class="sxs-lookup"><span data-stu-id="abf83-239">Description</span></span> |
   |---------|------------|
   |<span data-ttu-id="abf83-240">$SERVERNAME $ \ $SQLINSTANCENAME $</span><span class="sxs-lookup"><span data-stu-id="abf83-240">$SERVERNAME$\$SQLINSTANCENAME$</span></span> | <span data-ttu-id="abf83-241">回復データベースが配置されているサーバー名と SQL Server のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="abf83-241">Server name and instance of SQL Server where the Recovery Database is located.</span></span>|
   |<span data-ttu-id="abf83-242">$DATABASE $</span><span class="sxs-lookup"><span data-stu-id="abf83-242">$DATABASE$</span></span>|<span data-ttu-id="abf83-243">回復されたデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="abf83-243">Name of the recovered database.</span></span>|

### <span data-ttu-id="abf83-244">MBAM サーバーソフトウェアをインストールして、サーバー B で MBAM サーバー構成ウィザードを実行する</span><span class="sxs-lookup"><span data-stu-id="abf83-244">Install MBAM Server software and run the MBAM Server Configuration wizard on Server B</span></span>

1.  <span data-ttu-id="abf83-245">サーバー B に MBAM 2.5 サーバーソフトウェアをインストールします。詳細については、「 [MBAM 2.5 サーバーソフトウェアをインストールする](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abf83-245">Install the MBAM 2.5 Server software on Server B. For details, see [Installing the MBAM 2.5 Server Software](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software).</span></span>

2.  <span data-ttu-id="abf83-246">サーバー B で、MBAM サーバー構成ウィザードを起動し、[**新しい機能の追加**] をクリックして、[**コンプライアンスと監査データベース**] 機能のみを選択します。</span><span class="sxs-lookup"><span data-stu-id="abf83-246">On Server B, start the MBAM Server Configuration wizard, click **Add New Features**, and then select only the **Compliance and Audit Database** feature.</span></span> <span data-ttu-id="abf83-247">データベースの構成方法の詳細については、「 [MBAM 2.5 データベースを構成する方法](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abf83-247">For details on how to configure the databases, see [How to Configure the MBAM 2.5 Databases](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases).</span></span>

    >[!TIP]
    ><span data-ttu-id="abf83-248">または、 **MbamDatabase** Windows PowerShell コマンドレットを使用して、コンプライアンスと監査データベースを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="abf83-248">Alternatively, you can use the **Enable-MbamDatabase** Windows PowerShell cmdlet to configure the Compliance and Audit Database.</span></span>


### <span data-ttu-id="abf83-249">管理と監視の Web サイトのインスタンスを再開する</span><span class="sxs-lookup"><span data-stu-id="abf83-249">Resume the instance of the Administration and Monitoring Website</span></span>

<span data-ttu-id="abf83-250">管理と監視の Web サイトを実行しているサーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、管理と監視の Web サイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="abf83-250">On the server that is running the Administration and Monitoring Website, use the Internet Information Services (IIS) Manager console to start the Administration and Monitoring Website.</span></span>

<span data-ttu-id="abf83-251">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="abf83-251">To automate this procedure, you can use Windows PowerShell to run a command that is similar to the following:</span></span>

```powershell
Start-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
><span data-ttu-id="abf83-252">このコマンドを実行するには、windows powershell の IIS モジュールを Windows PowerShell の現在のインスタンスに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abf83-252">To run this command, you must add the IIS module for Windows PowerShell to the current instance of Windows PowerShell.</span></span>
