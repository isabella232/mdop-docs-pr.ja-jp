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
# <span data-ttu-id="e2034-103">MBAM 1.0 機能を別のコンピューターに移動する方法</span><span class="sxs-lookup"><span data-stu-id="e2034-103">How to Move MBAM 1.0 Features to Another Computer</span></span>


<span data-ttu-id="e2034-104">このトピックでは、1つ以上の Microsoft BitLocker 管理および監視 (MBAM) 機能を別のコンピューターに移行するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="e2034-104">This topic describes the steps that you should take to move one or more Microsoft BitLocker Administration and Monitoring (MBAM) features to a different computer.</span></span> <span data-ttu-id="e2034-105">複数の MBAM 機能を別のコンピューターに移動する場合は、次の順序で移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2034-105">When you move more than one MBAM feature to another computer, you should move them in the following order:</span></span>

1.  <span data-ttu-id="e2034-106">回復とハードウェアデータベース</span><span class="sxs-lookup"><span data-stu-id="e2034-106">Recovery and Hardware Database</span></span>

2.  <span data-ttu-id="e2034-107">コンプライアンスと監査データベース</span><span class="sxs-lookup"><span data-stu-id="e2034-107">Compliance and Audit Database</span></span>

3.  <span data-ttu-id="e2034-108">コンプライアンスと監査レポート</span><span class="sxs-lookup"><span data-stu-id="e2034-108">Compliance and Audit Reports</span></span>

4.  <span data-ttu-id="e2034-109">管理と監視</span><span class="sxs-lookup"><span data-stu-id="e2034-109">Administration and Monitoring</span></span>

## <span data-ttu-id="e2034-110">回復とハードウェアデータベースを移動するには</span><span class="sxs-lookup"><span data-stu-id="e2034-110">To move the Recovery and Hardware Database</span></span>


<span data-ttu-id="e2034-111">次の手順を使用して、MBAM 回復とハードウェアデータベースを1台のコンピューターから別のコンピューターに移動できます (この MBAM Server 機能は、サーバー A からサーバー B に移動できます)。</span><span class="sxs-lookup"><span data-stu-id="e2034-111">You can use the following procedure to move the MBAM Recovery and Hardware Database from one computer to another (you can move this MBAM Server feature from Server A to Server B):</span></span>

****

1.  <span data-ttu-id="e2034-112">MBAM 管理および監視 web サイトのすべてのインスタンスを停止します。</span><span class="sxs-lookup"><span data-stu-id="e2034-112">Stop all instances of the MBAM Administration and Monitoring web site.</span></span>

2.  <span data-ttu-id="e2034-113">サーバー B で MBAM セットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2034-113">Run the MBAM Setup on Server B.</span></span>

3.  <span data-ttu-id="e2034-114">サーバー A 上の MBAM 回復とハードウェアデータベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="e2034-114">Back up the MBAM Recovery and Hardware database on Server A.</span></span>

4.  <span data-ttu-id="e2034-115">MBAM 回復とハードウェアデータベース (サーバー A から B)</span><span class="sxs-lookup"><span data-stu-id="e2034-115">MBAM Recovery and Hardware database from Server A to B</span></span>

5.  <span data-ttu-id="e2034-116">サーバー B で MBAM 回復とハードウェアデータベースを復元する</span><span class="sxs-lookup"><span data-stu-id="e2034-116">Restore the MBAM Recovery and Hardware database on Server B</span></span>

6.  <span data-ttu-id="e2034-117">サーバー B 上の MBAM 回復とハードウェアデータベースへのアクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="e2034-117">Configure the access to the MBAM Recovery and Hardware database on Server B</span></span>

7.  <span data-ttu-id="e2034-118">MBAM 管理および監視サーバー上のデータベース接続データを更新する</span><span class="sxs-lookup"><span data-stu-id="e2034-118">Update the database connection data on MBAM Administration and Monitoring servers</span></span>

8.  <span data-ttu-id="e2034-119">MBAM 管理および監視 web サイトのすべてのインスタンスを再開する</span><span class="sxs-lookup"><span data-stu-id="e2034-119">Resume all instances of the MBAM Administration and Monitoring web site</span></span>

**<span data-ttu-id="e2034-120">MBAM 管理と監視 web サイトのすべてのインスタンスを停止するには</span><span class="sxs-lookup"><span data-stu-id="e2034-120">To stop all instances of the MBAM Administration and Monitoring website</span></span>**

1.  <span data-ttu-id="e2034-121">インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、MBAM 管理と監視機能を実行している各サーバーで MBAM web サイトを停止します。</span><span class="sxs-lookup"><span data-stu-id="e2034-121">Use the Internet Information Services (IIS) Manager console to stop the MBAM website on each of the servers that run the MBAM Administration and Monitoring feature.</span></span> <span data-ttu-id="e2034-122">MBAM web サイトは、 **Microsoft BitLocker の管理と監視と**いう名前です。</span><span class="sxs-lookup"><span data-stu-id="e2034-122">The MBAM website is named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="e2034-123">この手順を自動化するために、Windows PowerShell を使用すると、コマンドプロンプトで次のようなコマンドを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="e2034-123">To automate this procedure, you can use a command at the command prompt that is similar to the following, by using Windows PowerShell:</span></span>

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

    **<span data-ttu-id="e2034-124">注</span><span class="sxs-lookup"><span data-stu-id="e2034-124">Note</span></span>**  
    <span data-ttu-id="e2034-125">この PowerShell コマンドプロンプトを実行するには、powershell の IIS モジュールを PowerShell の現在のインスタンスに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2034-125">To run this PowerShell command prompt, you must add the IIS Module for PowerShell to the current instance of PowerShell.</span></span> <span data-ttu-id="e2034-126">さらに、PowerShell の実行ポリシーを更新して、スクリプトの実行を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2034-126">In addition, you must update the PowerShell execution policy to enable the execution of scripts.</span></span>



**<span data-ttu-id="e2034-127">サーバー B で MBAM セットアップを実行するには</span><span class="sxs-lookup"><span data-stu-id="e2034-127">To run MBAM setup on Server B</span></span>**

1.  <span data-ttu-id="e2034-128">サーバー B で MBAM セットアップを実行し、インストール用の回復とハードウェアデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2034-128">Run the MBAM setup on Server B and select the Recovery and Hardware Database for installation.</span></span>

2.  <span data-ttu-id="e2034-129">この手順を自動化するために、Windows PowerShell を使用すると、コマンドプロンプトで次のようなコマンドを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="e2034-129">To automate this procedure, you can use a command at the command prompt that is similar to the following, by using Windows PowerShell:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=KeyDatabase ADMINANDMON_MACHINENAMES=$DOMAIN$\$SERVERNAME$$ RECOVERYANDHWDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="e2034-130">注</span><span class="sxs-lookup"><span data-stu-id="e2034-130">Note</span></span>**  
    <span data-ttu-id="e2034-131">上の例の次の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e2034-131">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="e2034-132">$SERVERNAME $ \ \ $SQLINSTANCENAME $-回復とハードウェアデータベースの移動先のサーバーとインスタンスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-132">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the name of the server and instance to which the Recovery and Hardware database will be moved.</span></span>

    -   <span data-ttu-id="e2034-133">$DOMAIN $ \ \ $SERVERNAME $-各 MBAM アプリケーションのドメイン名とサーバー名を入力します。これは、回復とハードウェアのデータベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="e2034-133">$DOMAIN$\\$SERVERNAME$ - Enter the domain and server names of each MBAM Application and Monitoring Server that will contact the Recovery and Hardware database.</span></span> <span data-ttu-id="e2034-134">複数のドメイン名とサーバー名がある場合は、セミコロンを使用してリスト内の各ドメインを区切ります。</span><span class="sxs-lookup"><span data-stu-id="e2034-134">If there are multiple domain and server names, use a semicolon to separate each one of them in the list.</span></span> <span data-ttu-id="e2034-135">たとえば、$DOMAIN \\SERVERNAME $; $DOMAIN \\ $SERVERNAME $ $。</span><span class="sxs-lookup"><span data-stu-id="e2034-135">For example, $DOMAIN\\SERVERNAME$;$DOMAIN\\$SERVERNAME$$.</span></span> <span data-ttu-id="e2034-136">また、各サーバー名の後には、を付ける必要があり **$** ます。</span><span class="sxs-lookup"><span data-stu-id="e2034-136">Additionally, each server name must be followed by a **$**.</span></span> <span data-ttu-id="e2034-137">たとえば、MyDomain\\MyServerName1 $、MyDomain\\MyServerName2 $ などです。</span><span class="sxs-lookup"><span data-stu-id="e2034-137">For example, MyDomain\\MyServerName1$, MyDomain\\MyServerName2$.</span></span>



**<span data-ttu-id="e2034-138">サーバー A 上のデータベースをバックアップするには</span><span class="sxs-lookup"><span data-stu-id="e2034-138">To back up the Database on Server A</span></span>**

1.  <span data-ttu-id="e2034-139">Server A 上の回復とハードウェアデータベースをバックアップするには、SQL Server Management Studio と [バックアップ] という名前のタスクを使用**し**ます。</span><span class="sxs-lookup"><span data-stu-id="e2034-139">To back up the Recovery and Hardware database on Server A, use SQL Server Management Studio and the Task named **Back Up…**.</span></span> <span data-ttu-id="e2034-140">既定では、データベース名は**Mbam 回復とハードウェアデータベース**です。</span><span class="sxs-lookup"><span data-stu-id="e2034-140">By default, the database name is **MBAM Recovery and Hardware Database**.</span></span>

2.  <span data-ttu-id="e2034-141">この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成します。</span><span class="sxs-lookup"><span data-stu-id="e2034-141">To automate this procedure, create a SQL file (.sql) that contains the following SQL script:</span></span>

    <span data-ttu-id="e2034-142">MBAM 回復とハードウェアデータベースを変更して、完全な回復モードを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2034-142">Modify the MBAM Recovery and Hardware Database to use the full recovery mode.</span></span>

    ```sql
    USE master;

    GO

    ALTER DATABASE "MBAM Recovery and Hardware"

       SET RECOVERY FULL;

    GO
    ```

    <span data-ttu-id="e2034-143">MBAM 回復とハードウェアデータベースデータと MBAM 回復論理バックアップデバイスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2034-143">Create MBAM Recovery and Hardware Database Data and MBAM Recovery logical backup devices.</span></span>

    ```sql
    USE master

    GO

    EXEC sp_addumpdevice 'disk', 'MBAM Recovery and Hardware Database Data Device',

    'Z:\MBAM Recovery and Hardware Database Data.bak';

    GO
    ```

    <span data-ttu-id="e2034-144">完全な MBAM 回復とハードウェアデータベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="e2034-144">Back up the full MBAM Recovery and Hardware database.</span></span>

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

    **<span data-ttu-id="e2034-145">注</span><span class="sxs-lookup"><span data-stu-id="e2034-145">Note</span></span>**  
    <span data-ttu-id="e2034-146">上の例の値を、環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e2034-146">Replace the values from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="e2034-147">$PASSWORD $-秘密キーファイルの暗号化に使用するパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-147">$PASSWORD$ - Enter a password that you will use to encrypt the Private Key file.</span></span>



3.  <span data-ttu-id="e2034-148">Sql Server PowerShell と、次のようなコマンドを使用して SQL ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2034-148">Execute the SQL file by using SQL Server PowerShell and a command that is similar to the following:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile 'Z:\BackupMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="e2034-149">注</span><span class="sxs-lookup"><span data-stu-id="e2034-149">Note</span></span>**  
    <span data-ttu-id="e2034-150">上の例の値を、環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e2034-150">Replace the value in the previous example with those that match your environment:</span></span>

    -   <span data-ttu-id="e2034-151">$SERVERNAME $ \ \ $SQLINSTANCENAME $-回復とハードウェアデータベースのバックアップを作成するサーバーとインスタンスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-151">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the name of the server and the instance from which you back up the Recovery and Hardware database.</span></span>



**<span data-ttu-id="e2034-152">サーバー A から B にデータベースと証明書を移動するには</span><span class="sxs-lookup"><span data-stu-id="e2034-152">To move the Database and Certificate from Server A to B</span></span>**

1.  <span data-ttu-id="e2034-153">Windows エクスプローラーを使用して、サーバー A からサーバー B に MBAM 回復とハードウェアデータベースデータの .bak を移動します。</span><span class="sxs-lookup"><span data-stu-id="e2034-153">Move the MBAM Recovery and Hardware database data.bak from Server A to Server B by using Windows Explorer.</span></span>

2.  <span data-ttu-id="e2034-154">暗号化されたデータベースの証明書を移動するには、次のオートメーションの手順を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2034-154">To move the certificate for the encrypted database, you will need to use the following automation steps.</span></span> <span data-ttu-id="e2034-155">この手順を自動化するために、Windows PowerShell を使用して、次のようなコマンドを入力できます。</span><span class="sxs-lookup"><span data-stu-id="e2034-155">To automate this procedure, you can use Windows PowerShell to enter a command that is similar to the following:</span></span>

    `PS C:\> Copy-Item “Z:\MBAM Recovery and Hardware Database Data.bak” \\$SERVERNAME$\$DESTINATIONSHARE$`

    `PS C:\> Copy-Item “Z:\SQLServerInstanceCertificateFile” \\$SERVERNAME$\$DESTINATIONSHARE$`

    `PS C:\> Copy-Item “Z:\SQLServerInstanceCertificateFilePrivateKey” \\$SERVERNAME$\$DESTINATIONSHARE$`

    **<span data-ttu-id="e2034-156">注</span><span class="sxs-lookup"><span data-stu-id="e2034-156">Note</span></span>**  
    <span data-ttu-id="e2034-157">上の例の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e2034-157">Replace the value from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="e2034-158">$SERVERNAME $-ファイルのコピー先となるサーバーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-158">$SERVERNAME$ - Enter the name of the server to which the files will be copied.</span></span>

    -   <span data-ttu-id="e2034-159">$DESTINATIONSHARE $-ファイルのコピー先となる共有とパスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-159">$DESTINATIONSHARE$ - Enter the name of the share and path to which the files will be copied.</span></span>



**<span data-ttu-id="e2034-160">サーバー B でデータベースを復元するには</span><span class="sxs-lookup"><span data-stu-id="e2034-160">To restore the Database on Server B</span></span>**

1.  <span data-ttu-id="e2034-161">SQL Server Management Studio と**Restore database**という名前のタスクを使用して、server B の回復およびハードウェアデータベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="e2034-161">Restore the Recovery and Hardware database on Server B by using the SQL Server Management Studio and the Task named **Restore Database**.</span></span>

2.  <span data-ttu-id="e2034-162">タスクが実行されたら、[**デバイスから**] オプションを選択してデータベースのバックアップファイルを選び、[**追加**] コマンドを使用して、Mbam 回復とハードウェアデータベースの**データ .bak**ファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="e2034-162">Once the task has been executed, choose the database backup file by selecting the **From Device** option, and then use the **Add** command to choose the MBAM Recovery and Hardware database **Data.bak** file.</span></span>

3.  <span data-ttu-id="e2034-163">[ **OK]** を選んで、復元プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="e2034-163">Select **OK** to complete the restoration process.</span></span>

4.  <span data-ttu-id="e2034-164">この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成します。</span><span class="sxs-lookup"><span data-stu-id="e2034-164">To automate this procedure, create a SQL file (.sql) that contains the following SQL script:</span></span>

    ```sql
    -- Restore MBAM Recovery and Hardware Database. 

    USE master

    GO
    ```

    <span data-ttu-id="e2034-165">MBAM セットアップで作成された証明書をドロップします。</span><span class="sxs-lookup"><span data-stu-id="e2034-165">Drop the certificate created by MBAM Setup.</span></span>

    ```sql
    DROP CERTIFICATE [MBAM Recovery Encryption Certificate]

    GO
    ```

    <span data-ttu-id="e2034-166">証明書を追加する</span><span class="sxs-lookup"><span data-stu-id="e2034-166">Add certificate</span></span>

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

    <span data-ttu-id="e2034-167">MBAM 回復とハードウェアデータベースデータとログファイルを復元します。</span><span class="sxs-lookup"><span data-stu-id="e2034-167">Restore the MBAM Recovery and Hardware database data and the log files.</span></span>

    ```sql
    RESTORE DATABASE [MBAM Recovery and Hardware]

       FROM DISK = 'Z:\MBAM Recovery and Hardware Database Data.bak'

       WITH REPLACE
    ```

    **<span data-ttu-id="e2034-168">注</span><span class="sxs-lookup"><span data-stu-id="e2034-168">Note</span></span>**  
    <span data-ttu-id="e2034-169">上の例の値を、環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e2034-169">Replace the values from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="e2034-170">$PASSWORD $-秘密キーファイルの暗号化に使用したパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-170">$PASSWORD$ - Enter the password that you used to encrypt the Private Key file.</span></span>



5.  <span data-ttu-id="e2034-171">Windows PowerShell を使用して、次のようなコマンドラインを入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-171">Use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile 'Z:\RestoreMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="e2034-172">注</span><span class="sxs-lookup"><span data-stu-id="e2034-172">Note</span></span>**  
    <span data-ttu-id="e2034-173">消えますの例の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e2034-173">Replace the value from the receding example with those that match your environment:</span></span>

    -   <span data-ttu-id="e2034-174">$SERVERNAME $ \ \ $SQLINSTANCENAME $-回復とハードウェアデータベースの復元先のサーバーとインスタンスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-174">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the name of the server and the instance to which the Recovery and Hardware Database will be restored.</span></span>



**<span data-ttu-id="e2034-175">サーバー B 上のデータベースへのアクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="e2034-175">Configure the access to the Database on Server B</span></span>**

1.  <span data-ttu-id="e2034-176">サーバー B では、サーバーマネージャーの [ローカルユーザーとグループ] スナップインを使用して、MBAM 管理と監視機能を実行している各サーバーから**Mbam Recovery とハードウェアデータベースアクセス**のローカルグループにコンピューターアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="e2034-176">On Server B, use the Local user and Groups snap-in from Server Manager, to add the computer accounts from each server that runs the MBAM Administration and Monitoring feature to the Local Group named **MBAM Recovery and Hardware DB Access**.</span></span>

2.  <span data-ttu-id="e2034-177">この手順を自動化するために、サーバー B で Windows PowerShell を使用して、次のようなコマンドを入力できます。</span><span class="sxs-lookup"><span data-stu-id="e2034-177">To automate this procedure, you can use Windows PowerShell on Server B to enter a command that is similar to the following:</span></span>

    `PS C:\> net localgroup "MBAM Recovery and Hardware DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    **<span data-ttu-id="e2034-178">注</span><span class="sxs-lookup"><span data-stu-id="e2034-178">Note</span></span>**  
    <span data-ttu-id="e2034-179">上の例の値を、環境に適した値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e2034-179">Replace the values from the preceding example with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="e2034-180">$DOMAIN $ \ \ $SERVERNAME $ $-MBAM 管理および監視サーバーのドメイン名とコンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-180">$DOMAIN$\\$SERVERNAME$$ - Enter the domain name and machine name of the MBAM Administration and Monitoring Server.</span></span> <span data-ttu-id="e2034-181">サーバー名の後に、「MyDomain\\MyServerName1 $」などのように指定する必要があり **$** ます。</span><span class="sxs-lookup"><span data-stu-id="e2034-181">The server name must be followed by a **$**, for example, MyDomain\\MyServerName1$.</span></span>



~~~
You must run the command for each Administration and Monitoring Server that will be accessing the database in your environment.
~~~

**<span data-ttu-id="e2034-182">MBAM 管理および監視サーバーでデータベース接続データを更新するには</span><span class="sxs-lookup"><span data-stu-id="e2034-182">To update the Database Connection data on MBAM Administration and Monitoring Servers</span></span>**

1. <span data-ttu-id="e2034-183">MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、Microsoft BitLocker の管理と監視の web サイトでホストされている次のアプリケーションの接続文字列情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="e2034-183">On each of the servers that run the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to update the Connection String information for the following applications, which are hosted in the Microsoft BitLocker Administration and Monitoring website:</span></span>

   -   <span data-ttu-id="e2034-184">MBAM 管理サービス</span><span class="sxs-lookup"><span data-stu-id="e2034-184">MBAM Administration Service</span></span>

   -   <span data-ttu-id="e2034-185">MBAM 回復とハードウェアサービス</span><span class="sxs-lookup"><span data-stu-id="e2034-185">MBAM Recovery And Hardware Service</span></span>

2. <span data-ttu-id="e2034-186">各アプリケーションを選択し、**機能ビュー**の [**管理**] セクションにある**構成エディター**機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2034-186">Select each application and use the **Configuration Editor** feature, which is located under the **Management** section of the **Feature View**.</span></span>

3. <span data-ttu-id="e2034-187">[セクションリスト] コントロールで [ **Configurationstrings** ] オプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="e2034-187">Select the **configurationStrings** option from the Section list control.</span></span>

4. <span data-ttu-id="e2034-188">" **(コレクション)**" という名前の行を選び、行の右側にあるボタンを選択して、**コレクションエディター**を開きます。</span><span class="sxs-lookup"><span data-stu-id="e2034-188">Choose the row named **(Collection)**, and open the **Collection Editor** by selecting the button on the right side of the row.</span></span>

5. <span data-ttu-id="e2034-189">**コレクションエディター**で、「Mbam管理サービス」アプリケーションの構成を更新したときに**keyrecoveryconnectionstring**という名前の行を選択するか、「 <strong> Microsoft Mbam recoveryandcompdatastore </strong> 」という名前の行を選択します。ConnectionString。 ' MBAMRecoveryAndHardwareService ' の構成を更新しています。</span><span class="sxs-lookup"><span data-stu-id="e2034-189">In the **Collection Editor**, choose the row named **KeyRecoveryConnectionString** when you updated the configuration for the ‘MBAMAdministrationService’ application, or choose the row named <strong>Microsoft.Mbam.RecoveryAndHardwareDataStore.</strong>ConnectionString, when updating the configuration for the ‘MBAMRecoveryAndHardwareService’.</span></span>

6. <span data-ttu-id="e2034-190">**Configurationstrings**プロパティの**データソース =** 値を更新して、サーバー名と、回復およびハードウェアデータベースの移動先のインスタンスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e2034-190">Update the **Data Source=** value for the **configurationStrings** property to list the server name and the instance where the Recovery and Hardware Database was moved to.</span></span> <span data-ttu-id="e2034-191">たとえば、$ \\ \ $SQLINSTANCENAME $ などの $SERVERNAME ます。</span><span class="sxs-lookup"><span data-stu-id="e2034-191">For example, $SERVERNAME$\\$SQLINSTANCENAME$.</span></span>

7. <span data-ttu-id="e2034-192">この手順を自動化するには、各管理サーバーと監視サーバーで Windows PowerShell を使用して、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2034-192">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell on each Administration and Monitoring Server:</span></span>

   `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="KeyRecoveryConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMAdministrationService" -Name "connectionString" -Value “Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and Hardware;Integrated Security=SSPI;”`

   `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="Microsoft.Mbam.RecoveryAndHardwareDataStore.ConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMRecoveryAndHardwareService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and Hardware;Integrated Security=SSPI;"`

   **<span data-ttu-id="e2034-193">注</span><span class="sxs-lookup"><span data-stu-id="e2034-193">Note</span></span>**  
   <span data-ttu-id="e2034-194">上の例の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e2034-194">Replace the value from the preceding example with those that match your environment:</span></span>

   -   <span data-ttu-id="e2034-195">$SERVERNAME $ \ \ $SQLINSTANCENAME $-回復とハードウェアデータベースのサーバー名とインスタンスを入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-195">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Recovery and Hardware database is.</span></span>



**<span data-ttu-id="e2034-196">MBAM 管理と監視 web サイトのすべてのインスタンスを再開するには</span><span class="sxs-lookup"><span data-stu-id="e2034-196">To resume all instances of the MBAM Administration and Monitoring website</span></span>**

1.  <span data-ttu-id="e2034-197">MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、 **Microsoft BitLocker の管理と監視と**いう名前の mbam web サイトを起動します。</span><span class="sxs-lookup"><span data-stu-id="e2034-197">On each of the servers that run the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to Start the MBAM website, which is named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="e2034-198">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2034-198">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell:</span></span>

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

## <span data-ttu-id="e2034-199">コンプライアンスステータスデータベース機能を移動するには</span><span class="sxs-lookup"><span data-stu-id="e2034-199">To move the Compliance Status Database feature</span></span>


<span data-ttu-id="e2034-200">MBAM コンプライアンスステータスデータベース機能をあるコンピューターから別のコンピューターに移動することを選択する場合 (たとえば、サーバー A からサーバー B に移動するなど)、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2034-200">If you choose to move the MBAM Compliance Status Database feature from one computer to another, such as from Server A to Server B, you should use the following procedure:</span></span>

1.  <span data-ttu-id="e2034-201">MBAM 管理および監視 web サイトのすべてのインスタンスを停止する</span><span class="sxs-lookup"><span data-stu-id="e2034-201">Stop all instances of the MBAM Administration and Monitoring website</span></span>

2.  <span data-ttu-id="e2034-202">サーバー B で MBAM セットアップを実行する</span><span class="sxs-lookup"><span data-stu-id="e2034-202">Run MBAM setup on Server B</span></span>

3.  <span data-ttu-id="e2034-203">サーバー A でデータベースをバックアップする</span><span class="sxs-lookup"><span data-stu-id="e2034-203">Backup the Database on Server A</span></span>

4.  <span data-ttu-id="e2034-204">サーバー A から B にデータベースを移動する</span><span class="sxs-lookup"><span data-stu-id="e2034-204">Move the Database from Server A to B</span></span>

5.  <span data-ttu-id="e2034-205">サーバー B でデータベースを復元する</span><span class="sxs-lookup"><span data-stu-id="e2034-205">Restore the Database on Server B</span></span>

6.  <span data-ttu-id="e2034-206">サーバー B 上のデータベースへのアクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="e2034-206">Configure Access to the Database on Server B</span></span>

7.  <span data-ttu-id="e2034-207">MBAM 管理および監視サーバー上のデータベース接続データを更新する</span><span class="sxs-lookup"><span data-stu-id="e2034-207">Update database connection data on MBAM Administration and Monitoring servers</span></span>

8.  <span data-ttu-id="e2034-208">MBAM 管理および監視 web サイトのすべてのインスタンスを再開する</span><span class="sxs-lookup"><span data-stu-id="e2034-208">Resume all instances of the MBAM Administration and Monitoring website</span></span>

**<span data-ttu-id="e2034-209">MBAM 管理と監視 web サイトのすべてのインスタンスを停止するには</span><span class="sxs-lookup"><span data-stu-id="e2034-209">To stop all instances of the MBAM Administration and Monitoring website</span></span>**

1.  <span data-ttu-id="e2034-210">MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、 **Microsoft BitLocker の管理と監視と**いう名前の mbam web サイトを停止します。</span><span class="sxs-lookup"><span data-stu-id="e2034-210">On each of the servers that run the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to Stop the MBAM website, which is named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="e2034-211">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2034-211">To automate this procedure, you can use a command that is similar to the following one,by using Windows PowerShell:</span></span>

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

    **<span data-ttu-id="e2034-212">注</span><span class="sxs-lookup"><span data-stu-id="e2034-212">Note</span></span>**  
    <span data-ttu-id="e2034-213">このコマンドを実行するには、powershell の IIS モジュールを PowerShell の現在のインスタンスに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2034-213">To execute this command, you must add the IIS Module for PowerShell to current instance of PowerShell.</span></span> <span data-ttu-id="e2034-214">さらに、PowerShell の実行ポリシーを更新して、スクリプトの実行を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2034-214">In addition, you must update the PowerShell execution policy to enable the execution of scripts.</span></span>



**<span data-ttu-id="e2034-215">サーバー B で MBAM セットアップを実行するには</span><span class="sxs-lookup"><span data-stu-id="e2034-215">To run MBAM Setup on Server B</span></span>**

1.  <span data-ttu-id="e2034-216">サーバー B で MBAM セットアップを実行し、インストール用のコンプライアンスステータスデータベース機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2034-216">Run MBAM Setup on Server B and select the Compliance Status Database feature for installation.</span></span>

2.  <span data-ttu-id="e2034-217">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2034-217">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal= ReportsDatabase ADMINANDMON_MACHINENAMES=$DOMAIN$\$SERVERNAME$ COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ REPORTS_USERACCOUNT=$DOMAIN$\$USERNAME$`

    **<span data-ttu-id="e2034-218">注</span><span class="sxs-lookup"><span data-stu-id="e2034-218">Note</span></span>**  
    <span data-ttu-id="e2034-219">上の例の値を、環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e2034-219">Replace the values from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="e2034-220">$SERVERNAME $ \ \ $SQLINSTANCENAME $-コンプライアンスステータスデータベースの移動先のサーバー名とインスタンスを入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-220">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Compliance Status Database will be moved to.</span></span>

    -   <span data-ttu-id="e2034-221">$DOMAIN $ \ \ $SERVERNAME $-各 MBAM アプリケーションのドメイン名とサーバー名を入力して、コンプライアンスステータスデータベースに接続するサーバーを監視します。</span><span class="sxs-lookup"><span data-stu-id="e2034-221">$DOMAIN$\\$SERVERNAME$ - Enter the domain names and server names of each MBAM Application and Monitoring Server that will contact the Compliance Status Database.</span></span> <span data-ttu-id="e2034-222">複数のドメイン名とサーバー名がある場合は、セミコロンを使用してリスト内のそれぞれの名前を区切ります。</span><span class="sxs-lookup"><span data-stu-id="e2034-222">If there are multiple domain names and server names, use a semicolon to separate each one of them in the list.</span></span> <span data-ttu-id="e2034-223">たとえば、$DOMAIN \\SERVERNAME $; $DOMAIN \\ $SERVERNAME $ $。</span><span class="sxs-lookup"><span data-stu-id="e2034-223">For example, $DOMAIN\\SERVERNAME$;$DOMAIN\\$SERVERNAME$$.</span></span> <span data-ttu-id="e2034-224">各サーバー名の後に、 **$** 例に示されているようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2034-224">Each server name must be followed by a **$** as shown in the example.</span></span> <span data-ttu-id="e2034-225">たとえば、MyDomain\\MyServerName1 $、MyDomain\\MyServerName2 $ などです。</span><span class="sxs-lookup"><span data-stu-id="e2034-225">For example, MyDomain\\MyServerName1$, MyDomain\\MyServerName2$.</span></span>

    -   <span data-ttu-id="e2034-226">$DOMAIN $ \ \ $USERNAME $-コンプライアンスと監査レポート機能が使用するドメインとユーザー名を入力して、コンプライアンスステータスデータベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="e2034-226">$DOMAIN$\\$USERNAME$ - Enter the domain and user name that will be used by the Compliance and Audit reports feature to connect to the Compliance Status Database.</span></span>



**<span data-ttu-id="e2034-227">サーバー A 上のコンプライアンスデータベースのバックアップを作成するには</span><span class="sxs-lookup"><span data-stu-id="e2034-227">To back up the Compliance Database on Server A</span></span>**

1.  <span data-ttu-id="e2034-228">Server A 上のコンプライアンスデータベースをバックアップするには、SQL Server Management Studio と [**バックアップ**] という名前のタスクを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2034-228">To back up the Compliance Database on Server A, use SQL Server Management Studio and the Task named **Back Up…**.</span></span> <span data-ttu-id="e2034-229">既定では、データベース名は**Mbam コンプライアンスステータスデータベース**です。</span><span class="sxs-lookup"><span data-stu-id="e2034-229">By default, the database name is **MBAM Compliance Status Database**.</span></span>

2.  <span data-ttu-id="e2034-230">この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成します。</span><span class="sxs-lookup"><span data-stu-id="e2034-230">To automate this procedure, create a SQL file (.sql) that contains the following-SQL script:</span></span>

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

3.  <span data-ttu-id="e2034-231">SQL Server PowerShell を使用して、次のようなコマンドで SQL ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2034-231">Run the SQL file with a command that is similar to the following one, by using the SQL Server PowerShell:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile "Z:\BackupMBAMComplianceStatusDatabaseScript.sql" –ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="e2034-232">注</span><span class="sxs-lookup"><span data-stu-id="e2034-232">Note</span></span>**  
    <span data-ttu-id="e2034-233">上の例の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e2034-233">Replace the value from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="e2034-234">$SERVERNAME $ \ \ $SQLINSTANCENAME $-サーバー名と、コンプライアンスステータスデータベースのバックアップの対象となるインスタンスを入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-234">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and the instance from where the Compliance Status database will be backed up.</span></span>



**<span data-ttu-id="e2034-235">サーバー A から B にデータベースを移動するには</span><span class="sxs-lookup"><span data-stu-id="e2034-235">To move the Database from Server A to B</span></span>**

1.  <span data-ttu-id="e2034-236">Windows エクスプローラーを使用して、次のファイルをサーバー A からサーバー B に移動します。</span><span class="sxs-lookup"><span data-stu-id="e2034-236">Move the following files from Server A to Server B, by using Windows Explorer:</span></span>

    -   <span data-ttu-id="e2034-237">MBAM コンプライアンスステータスデータベースデータ .bak</span><span class="sxs-lookup"><span data-stu-id="e2034-237">MBAM Compliance Status Database Data.bak</span></span>

2.  <span data-ttu-id="e2034-238">この手順を自動化するには、Windows PowerShell を使用して次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2034-238">To automate this procedure, you can use a command that is similar to the following using Windows PowerShell:</span></span>

    `PS C:\> Copy-Item “Z:\MBAM Compliance Status Database Data.bak” \\$SERVERNAME$\$DESTINATIONSHARE$`

    **<span data-ttu-id="e2034-239">注</span><span class="sxs-lookup"><span data-stu-id="e2034-239">Note</span></span>**  
    <span data-ttu-id="e2034-240">上の例の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e2034-240">Replace the value from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="e2034-241">$SERVERNAME $-ファイルのコピー先のサーバー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-241">$SERVERNAME$ - Enter the server name where the files will be copied to.</span></span>

    -   <span data-ttu-id="e2034-242">$DESTINATIONSHARE $-ファイルのコピー先の共有名とパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-242">$DESTINATIONSHARE$ - Enter the name of share and path where the files will be copied to.</span></span>



**<span data-ttu-id="e2034-243">サーバー B でデータベースを復元するには</span><span class="sxs-lookup"><span data-stu-id="e2034-243">To restore the Database on Server B</span></span>**

1.  <span data-ttu-id="e2034-244">SQL Server Management Studio と [**データベースの復元**] という名前のタスクを使用して、サーバー B 上のコンプライアンスステータスデータベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="e2034-244">Restore the Compliance Status database on Server B by using SQL Server Management Studio and the Task named **Restore Database…**.</span></span>

2.  <span data-ttu-id="e2034-245">タスクが実行されたら、[デバイスから] オプションを選択してデータベースバックアップファイルを選び、[追加] コマンドを使用して MBAM コンプライアンスステータスデータベースデータ .bak ファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="e2034-245">Once the task is executed, select the database backup file, by selecting the From Device option, and then use the Add command to choose the MBAM Compliance Status Database Data.bak file.</span></span> <span data-ttu-id="e2034-246">[OK] をクリックして、復元プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="e2034-246">Click OK to complete the restoration process.</span></span>

3.  <span data-ttu-id="e2034-247">この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成します。</span><span class="sxs-lookup"><span data-stu-id="e2034-247">To automate this procedure, create a SQL file (.sql) that contains the following-SQL script:</span></span>

    ```sql
    -- Create MBAM Compliance Status Database Data logical backup devices. 

    Use master

    GO

    -- Restore the MBAM Compliance Status database data files.

    RESTORE DATABASE [MBAM Compliance Status Database]

       FROM DISK = 'C:\test\MBAM Compliance Status Database Data.bak'

       WITH REPLACE
    ```

4.  <span data-ttu-id="e2034-248">SQL Server PowerShell を使用して、次のようなコマンドで SQL ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2034-248">Run the SQL File with a command that is similar to the following one, by using the SQL Server PowerShell:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile "Z:\RestoreMBAMComplianceStatusDatabaseScript.sql" -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="e2034-249">注</span><span class="sxs-lookup"><span data-stu-id="e2034-249">Note</span></span>**  
    <span data-ttu-id="e2034-250">上の例の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e2034-250">Replace the value from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="e2034-251">$SERVERNAME $ \ \ $SQLINSTANCENAME $-コンプライアンスステータスデータベースが復元されるサーバー名とインスタンスを入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-251">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Compliance Status Database will be restored to.</span></span>



**<span data-ttu-id="e2034-252">サーバー B 上のデータベースへのアクセスを構成するには</span><span class="sxs-lookup"><span data-stu-id="e2034-252">To configure the Access to the Database on Server B</span></span>**

1.  <span data-ttu-id="e2034-253">サーバー B では、サーバーマネージャーの [ローカルユーザーとグループ] スナップインを使用して、MBAM の管理と監視機能を実行する各サーバーから、 **Mbam コンプライアンス状態の DB Access**という名前のローカルグループにマシンアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="e2034-253">On Server B use the Local user and Groups snap-in from Server Manager to add the machine accounts from each server that runs the MBAM Administration and Monitoring feature to the Local Group named **MBAM Compliance Status DB Access**.</span></span>

2.  <span data-ttu-id="e2034-254">この手順を自動化するには、サーバー B で Windows PowerShell を使用して、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2034-254">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell on Server B:</span></span>

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$REPORTSUSERNAME$  /add`

    **<span data-ttu-id="e2034-255">注</span><span class="sxs-lookup"><span data-stu-id="e2034-255">Note</span></span>**  
    <span data-ttu-id="e2034-256">上の例の値を、環境に適した値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e2034-256">Replace the value from the preceding example with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="e2034-257">$DOMAIN $ \ \ $SERVERNAME $ $-MBAM 管理および監視サーバーのドメインとコンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-257">$DOMAIN$\\$SERVERNAME$$ - Enter the domain and machine name of the MBAM Administration and Monitoring Server.</span></span> <span data-ttu-id="e2034-258">サーバー名の後には、という名前を付ける必要があり **$** ます。たとえば、MyDomain\\MyServerName1 $ とします。</span><span class="sxs-lookup"><span data-stu-id="e2034-258">The server name must be followed by a **$**.For example, MyDomain\\MyServerName1$.</span></span>

    -   <span data-ttu-id="e2034-259">$DOMAIN $ \ \ $REPORTSUSERNAME $-コンプライアンスおよび監査レポートのデータソースを構成するために使用されたユーザーアカウント名を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-259">$DOMAIN$\\$REPORTSUSERNAME$ - Enter the user account name that was used to configure the data source for the Compliance and Audit reports</span></span>



~~~
For each Administration and Monitoring Server that will access the database of your environment, you must run the command that will add the servers to the MBAM Compliance Auditing DB Access local group.
~~~

**<span data-ttu-id="e2034-260">MBAM 管理および監視サーバーでデータベース接続データを更新するには</span><span class="sxs-lookup"><span data-stu-id="e2034-260">To update the database connection data on MBAM Administration and Monitoring servers</span></span>**

1.  <span data-ttu-id="e2034-261">MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、Microsoft BitLocker の管理と監視の web サイトでホストされている次のアプリケーションの接続文字列情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="e2034-261">On each of the servers that run the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to update the Connection String information for the following Applications, which are hosted in the Microsoft BitLocker Administration and Monitoring website:</span></span>

    -   <span data-ttu-id="e2034-262">Mbam管理サービス</span><span class="sxs-lookup"><span data-stu-id="e2034-262">MBAMAdministrationService</span></span>

    -   <span data-ttu-id="e2034-263">MBAMComplianceStatusService</span><span class="sxs-lookup"><span data-stu-id="e2034-263">MBAMComplianceStatusService</span></span>

2.  <span data-ttu-id="e2034-264">各アプリケーションを選択し、**機能ビュー**の [**管理**] セクションにある**構成エディター**機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2034-264">Select each application and use the **Configuration Editor** feature, which is located under the **Management** section of the **Feature View**.</span></span>

3.  <span data-ttu-id="e2034-265">[セクションリスト] コントロールで [ **Configurationstrings** ] オプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="e2034-265">Select the **configurationStrings** option from the Section list control.</span></span>

4.  <span data-ttu-id="e2034-266">" **(コレクション)**" という名前の行を選び、行の右側にあるボタンを選択して、コレクションエディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="e2034-266">Select the row named **(Collection)**, and open the Collection Editor by selecting the button on the right side of the row.</span></span>

5.  <span data-ttu-id="e2034-267">**コレクションエディター**で、mbamComplianceStatusConnectionString という**ComplianceStatusConnectionString**名前の行を選択します。この場合は、MBAMComplianceStatusService の構成を更新するときに、 **mbammanagement**service アプリケーションの構成を更新するか、またはという名前の行を選びます。</span><span class="sxs-lookup"><span data-stu-id="e2034-267">In the **Collection Editor**, select the row named **ComplianceStatusConnectionString**, when you update the configuration for the MBAMAdministrationService application, or the row named **Microsoft.Windows.Mdop.BitLockerManagement.StatusReportDataStore.ConnectionString**, when you update the configuration for the MBAMComplianceStatusService.</span></span>

6.  <span data-ttu-id="e2034-268">**Configurationstrings**プロパティの**データソース =** 値を更新して、サーバー名とインスタンス名を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="e2034-268">Update the **Data Source=** value for the **configurationStrings** property to list the server name and the instance name.</span></span> <span data-ttu-id="e2034-269">たとえば、回復とハードウェアデータベースが移動された $SERVERNAME $ \ \ $SQLINSTANCENAME。</span><span class="sxs-lookup"><span data-stu-id="e2034-269">For example, $SERVERNAME$\\$SQLINSTANCENAME, to which the Recovery and Hardware Database was moved.</span></span>

7.  <span data-ttu-id="e2034-270">この手順を自動化するために、Windows PowerShell を使用して、各管理および監視サーバーに次のようなコマンドを入力できます。</span><span class="sxs-lookup"><span data-stu-id="e2034-270">To automate this procedure, you can use Windows PowerShell to enter a command that is similar to the following one on each Administration and Monitoring Server:</span></span>

    `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="ComplianceStatusConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMAdministrationService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Compliance Status;Integrated Security=SSPI;"`

    `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="Microsoft.Windows.Mdop.BitLockerManagement.StatusReportDataStore.ConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMComplianceStatusService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME;Initial Catalog=MBAM Compliance Status;Integrated Security=SSPI;"`

    **<span data-ttu-id="e2034-271">注</span><span class="sxs-lookup"><span data-stu-id="e2034-271">Note</span></span>**  
    <span data-ttu-id="e2034-272">上の例の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e2034-272">Replace the value from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="e2034-273">$SERVERNAME $ \ \ $SQLINSTANCENAME $-回復とハードウェアデータベースが配置されているサーバー名とインスタンス名を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-273">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance name where the Recovery and Hardware Database is located.</span></span>



**<span data-ttu-id="e2034-274">MBAM 管理と監視 web サイトのすべてのインスタンスを再開するには</span><span class="sxs-lookup"><span data-stu-id="e2034-274">To resume all instances of the MBAM Administration and Monitoring website</span></span>**

1.  <span data-ttu-id="e2034-275">MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、 **Microsoft BitLocker の管理と監視と**いう名前の mbam web サイトを起動します。</span><span class="sxs-lookup"><span data-stu-id="e2034-275">On each of the servers running the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to start the MBAM web site named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="e2034-276">この手順を自動化するために、Windows PowerShell を使用して、次のようなコマンドを入力できます。</span><span class="sxs-lookup"><span data-stu-id="e2034-276">To automate this procedure, you can use Windows PowerShell to enter a command that is similar to the following:</span></span>

    **<span data-ttu-id="e2034-277">PS c &gt; : Web サイト "Microsoft BitLocker の管理と監視"</span><span class="sxs-lookup"><span data-stu-id="e2034-277">PS C:\\&gt; Start-Website “Microsoft BitLocker Administration and Monitoring”</span></span>**

## <span data-ttu-id="e2034-278">コンプライアンスおよび監査レポートを移動するには</span><span class="sxs-lookup"><span data-stu-id="e2034-278">To moving the Compliance and Audit Reports</span></span>


<span data-ttu-id="e2034-279">MBAM コンプライアンスと監査レポートを1台のコンピューターから別のコンピューターに移動する場合 (具体的には、サーバー A からサーバー B に機能を移行する場合)、次の手順と手順を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2034-279">If you choose to move the MBAM Compliance and Audit Reports from one computer to another (specifically, if you move feature from Server A to Server B), you should use the following procedure and steps:</span></span>

1.  <span data-ttu-id="e2034-280">サーバー B で MBAM セットアップを実行する</span><span class="sxs-lookup"><span data-stu-id="e2034-280">Run MBAM setup on Server B</span></span>

2.  <span data-ttu-id="e2034-281">サーバー B のコンプライアンスおよび監査レポートへのアクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="e2034-281">Configure Access to the Compliance and Audit Reports on Server B</span></span>

3.  <span data-ttu-id="e2034-282">MBAM 管理および監視 web サイトのすべてのインスタンスを停止する</span><span class="sxs-lookup"><span data-stu-id="e2034-282">Stop all instances of the MBAM Administration and Monitoring website</span></span>

4.  <span data-ttu-id="e2034-283">MBAM 管理および監視サーバーでのレポート接続データの更新</span><span class="sxs-lookup"><span data-stu-id="e2034-283">Update the reports connection data on MBAM Administration and Monitoring servers</span></span>

5.  <span data-ttu-id="e2034-284">MBAM 管理および監視 web サイトのすべてのインスタンスを再開する</span><span class="sxs-lookup"><span data-stu-id="e2034-284">Resume all instances of the MBAM Administration and Monitoring website</span></span>

**<span data-ttu-id="e2034-285">サーバー B で MBAM セットアップを実行するには</span><span class="sxs-lookup"><span data-stu-id="e2034-285">To run MBAM setup on Server B</span></span>**

1.  <span data-ttu-id="e2034-286">サーバー B で MBAM セットアップを実行し、インストールのコンプライアンスと監査機能のみを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2034-286">Run MBAM setup on Server B and only select the Compliance and Audit feature for installation.</span></span>

2.  <span data-ttu-id="e2034-287">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2034-287">To automate this procedure, you can use a command that is similar to the following, by using Windows PowerShell:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=Reports COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ REPORTS_USERACCOUNTPW=$PASSWORD$`

    **<span data-ttu-id="e2034-288">注</span><span class="sxs-lookup"><span data-stu-id="e2034-288">Note</span></span>**  
    <span data-ttu-id="e2034-289">上の例の値を、環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e2034-289">Replace the values from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="e2034-290">$SERVERNAME $ \ \ $SQLINSTANCENAME $-コンプライアンスステータスデータベースが配置されているサーバー名とインスタンスを入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-290">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Compliance Status Database is located.</span></span>

    -   <span data-ttu-id="e2034-291">$DOMAIN $ \ \ $USERNAME $-コンプライアンスと監査レポート機能で使用される、コンプライアンスステータスデータベースに接続するためのドメイン名とユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-291">$DOMAIN$\\$USERNAME$ - Enter the domain name and user name that will be used by the Compliance and Audit reports feature to connect to the Compliance Status Database.</span></span>

    -   <span data-ttu-id="e2034-292">$PASSWORD $-コンプライアンスステータスデータベースへの接続に使用されるユーザーアカウントのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-292">$PASSWORD$ - Enter the password of the user account that will be used to connect to the Compliance Status Database.</span></span>



**<span data-ttu-id="e2034-293">サーバー B のコンプライアンスおよび監査レポートへのアクセスを構成するには</span><span class="sxs-lookup"><span data-stu-id="e2034-293">To configure the access to the Compliance and Audit Reports on Server B</span></span>**

1.  <span data-ttu-id="e2034-294">サーバー B では、[サーバーマネージャー] から [ローカルユーザーとグループ] スナップインを使用して、コンプライアンスレポートおよび監査レポートへのアクセス権を持つユーザーアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="e2034-294">On Server B, use the Local user and Groups snap-in from Server Manager to add the user accounts that will have access to the Compliance and Audit Reports.</span></span> <span data-ttu-id="e2034-295">ユーザーアカウントを "MBAM レポートユーザー" という名前のローカルグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="e2034-295">Add the user accounts to the local group named “MBAM Report Users”.</span></span>

2.  <span data-ttu-id="e2034-296">この手順を自動化するために、サーバー B で Windows PowerShell を使用することで、次のようなコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2034-296">To automate this procedure, you can use a command that is similar to the following, by using Windows PowerShell on Server B.</span></span>

    `PS C:\> net localgroup "MBAM Report Users" $DOMAIN$\$REPORTSUSERNAME$  /add`

    **<span data-ttu-id="e2034-297">注</span><span class="sxs-lookup"><span data-stu-id="e2034-297">Note</span></span>**  
    <span data-ttu-id="e2034-298">上の例の次の値を、環境に適した値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e2034-298">Replace the following value from the preceding example with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="e2034-299">$DOMAIN $ \ \ $REPORTSUSERNAME $-コンプライアンスおよび監査レポートのデータソースを構成するために使用されたユーザーアカウント名を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-299">$DOMAIN$\\$REPORTSUSERNAME$ - Enter the user account name that was used to configure the data source for the Compliance and Audit reports</span></span>



~~~
The command to add the users to the MBAM Report Users local group must be run for each user that will be accessing the reports in your environment.
~~~

**<span data-ttu-id="e2034-300">MBAM 管理と監視 web サイトのすべてのインスタンスを停止するには</span><span class="sxs-lookup"><span data-stu-id="e2034-300">To stop all instances of the MBAM Administration and Monitoring website</span></span>**

1.  <span data-ttu-id="e2034-301">MBAM 管理と監視機能を実行する各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、 **Microsoft BitLocker の管理と監視と**いう名前の mbam web サイトを停止します。</span><span class="sxs-lookup"><span data-stu-id="e2034-301">On each of the servers that run the MBAM Administration and Monitoring Feature use the Internet Information Services (IIS) Manager console to Stop the MBAM website named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="e2034-302">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2034-302">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell:</span></span>

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

**<span data-ttu-id="e2034-303">MBAM 管理および監視サーバーでデータベース接続データを更新するには</span><span class="sxs-lookup"><span data-stu-id="e2034-303">To update the Database Connection Data on MBAM Administration and Monitoring Servers</span></span>**

1. <span data-ttu-id="e2034-304">MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、コンプライアンスレポート URL を更新します。</span><span class="sxs-lookup"><span data-stu-id="e2034-304">On each of the servers that run the MBAM Administration and Monitoring Feature, use the Internet Information Services (IIS) Manager console to update the Compliance Reports URL.</span></span>

2. <span data-ttu-id="e2034-305">**Microsoft BitLocker の管理と監視**の web サイトを選び、**機能ビュー**の [**管理**] セクションにある [**構成エディター** ] 機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2034-305">Select the **Microsoft BitLocker Administration and Monitoring** website and use the **Configuration Editor** feature which can be found under the **Management** section of the **Feature View**.</span></span>

3. <span data-ttu-id="e2034-306">[セクションリスト] コントロールから [ **appSettings** ] オプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="e2034-306">Select the **appSettings** option from the Section list control.</span></span>

4. <span data-ttu-id="e2034-307">ここで、 **(コレクション)** という名前の行を選び、行の右側にあるボタンを選択して、**コレクションエディター**を開きます。</span><span class="sxs-lookup"><span data-stu-id="e2034-307">From here, select the row named **(Collection)**, and open the **Collection Editor** by selecting the button on the right side of the row.</span></span>

5. <span data-ttu-id="e2034-308">**コレクションエディター**で、"Microsoft Mbam. .url" という名前の行を選びます。</span><span class="sxs-lookup"><span data-stu-id="e2034-308">In the **Collection Editor**, select the row named “Microsoft.Mbam.Reports.Url”.</span></span>

6. <span data-ttu-id="e2034-309">サーバー B のサーバー名を反映するには、"Mbam" の値を更新します。コンプライアンスと監査レポート機能が名前付き SQL Reporting Services インスタンスにインストールされている場合は、URL にインスタンスの名前を追加または更新してください。</span><span class="sxs-lookup"><span data-stu-id="e2034-309">Update the value for Microsoft.Mbam.Reports.Url to reflect the server name for Server B. If the Compliance and Audit reports feature was installed on a named SQL Reporting Services instance, make sure that you add or update the name of the instance to the URL.</span></span> <span data-ttu-id="e2034-310">たとえば、http://$SERVERNAME $/Report/Pages.... $ SQLSRSINSTANCENAME $</span><span class="sxs-lookup"><span data-stu-id="e2034-310">For example, http://$SERVERNAME$/ReportServer\_$SQLSRSINSTANCENAME$/Pages....</span></span>

7. <span data-ttu-id="e2034-311">この手順を自動化するために、Windows PowerShell を使用して、各管理および監視サーバーに次のようなコマンドを入力できます。</span><span class="sxs-lookup"><span data-stu-id="e2034-311">To automate this procedure, you can use Windows PowerShell to enter a command that is similar to the following one on each Administration and Monitoring Server:</span></span>

   `PS C:\> Set-WebConfigurationProperty '/appSettings/add[@key="Microsoft.Mbam.Reports.Url"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring" -Name "Value" -Value “http://$SERVERNAME$/ReportServer_$SRSINSTANCENAME$/Pages/ReportViewer.aspx?/Malta+Compliance+Reports/”`

   **<span data-ttu-id="e2034-312">注</span><span class="sxs-lookup"><span data-stu-id="e2034-312">Note</span></span>**  
   <span data-ttu-id="e2034-313">上の例の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e2034-313">Replace the value from the preceding example with those that match your environment:</span></span>

   -   <span data-ttu-id="e2034-314">$SERVERNAME $: コンプライアンスと監査レポートがインストールされたサーバーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-314">$SERVERNAME$ - Enter the name of the server to which the Compliance and Audit Reports were installed.</span></span>

   -   <span data-ttu-id="e2034-315">$SRSINSTANCENAME $-コンプライアンスと監査レポートがインストールされた SQL Reporting Services インスタンスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-315">$SRSINSTANCENAME$ - Enter the name of the SQL Reporting Services instance to which the Compliance and Audit Reports were installed.</span></span>



**<span data-ttu-id="e2034-316">MBAM 管理と監視 web サイトのすべてのインスタンスを再開するには</span><span class="sxs-lookup"><span data-stu-id="e2034-316">To resume all instances of the MBAM Administration and Monitoring website</span></span>**

1.  <span data-ttu-id="e2034-317">MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、 **Microsoft BitLocker の管理と監視と**いう名前の mbam web サイトを起動します。</span><span class="sxs-lookup"><span data-stu-id="e2034-317">On each of the servers that run the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to Start the MBAM web site named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="e2034-318">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2034-318">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell:</span></span>

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

    **<span data-ttu-id="e2034-319">注</span><span class="sxs-lookup"><span data-stu-id="e2034-319">Note</span></span>**  
    <span data-ttu-id="e2034-320">このコマンドを実行するには、powershell の IIS モジュールが PowerShell の現在のインスタンスに追加されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2034-320">To execute this command, the IIS Module for PowerShell must be added to the current instance of PowerShell.</span></span> <span data-ttu-id="e2034-321">さらに、PowerShell の実行ポリシーを更新して、スクリプトの実行を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2034-321">In addition, you must update the PowerShell execution policy to enable execution of scripts.</span></span>



## <span data-ttu-id="e2034-322">管理と監視機能を移動するには</span><span class="sxs-lookup"><span data-stu-id="e2034-322">To move the Administration and Monitoring feature</span></span>


<span data-ttu-id="e2034-323">MBAM 管理と監視レポート機能をあるコンピューターから別のコンピューターに移動することを選択した場合 (機能をサーバー A からサーバー B に移動した場合) は、次の手順を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2034-323">If you choose to move the MBAM Administration and Monitoring Reports feature from one computer to another, (if you move feature from Server A to Server B), you should use the following procedure.</span></span> <span data-ttu-id="e2034-324">このプロセスには、次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e2034-324">The process includes the following steps:</span></span>

1.  <span data-ttu-id="e2034-325">サーバー B で MBAM セットアップを実行する</span><span class="sxs-lookup"><span data-stu-id="e2034-325">Run MBAM setup on Server B</span></span>

2.  <span data-ttu-id="e2034-326">サーバー B 上のデータベースへのアクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="e2034-326">Configure Access to the Database on Server B</span></span>

**<span data-ttu-id="e2034-327">サーバー B で MBAM セットアップを実行するには</span><span class="sxs-lookup"><span data-stu-id="e2034-327">To run MBAM setup on Server B</span></span>**

1.  <span data-ttu-id="e2034-328">サーバー B で MBAM セットアップを実行し、インストールの管理機能のみを選択します。</span><span class="sxs-lookup"><span data-stu-id="e2034-328">Run MBAM setup on Server B and only select the Administration feature for installation.</span></span>

2.  <span data-ttu-id="e2034-329">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2034-329">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=AdministrationMonitoringServer,HardwareCompatibility COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ RECOVERYANDHWDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ SRS_REPORTSITEURL=$REPORTSSERVERURL$`

    **<span data-ttu-id="e2034-330">注</span><span class="sxs-lookup"><span data-stu-id="e2034-330">Note</span></span>**  
    <span data-ttu-id="e2034-331">上の例の値を、環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e2034-331">Replace the values from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="e2034-332">$SERVERNAME $ \ \ $SQLINSTANCENAME $-COMPLIDB \ _SQLINSTANCE パラメーターには、コンプライアンスステータスデータベースが配置されているサーバー名とインスタンスを入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-332">$SERVERNAME$\\$SQLINSTANCENAME$ - For the COMPLIDB\_SQLINSTANCE parameter, input the server name and instance where the Compliance Status Database is located.</span></span> <span data-ttu-id="e2034-333">RECOVERYANDHWDB \ _SQLINSTANCE パラメーターには、回復とハードウェアデータベースが配置されているサーバー名とインスタンスを入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-333">For the RECOVERYANDHWDB\_SQLINSTANCE parameter, input the server name and instance where the Recovery and Hardware Database is located.</span></span>

    -   <span data-ttu-id="e2034-334">$DOMAIN $ \ \ $USERNAME $-コンプライアンスと監査レポート機能が使用するドメインとユーザー名を入力して、コンプライアンスステータスデータベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="e2034-334">$DOMAIN$\\$USERNAME$ - Enter the domain and user name that will be used by the Compliance and Audit reports feature to connect to the Compliance Status Database.</span></span>

    -   <span data-ttu-id="e2034-335">$ ¥ SERVERURL $-SQL Reporting Service web サイトのホームの場所の URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-335">$ REPORTSSERVERURL$ - Enter the URL for the Home location of the SQL Reporting Service website.</span></span> <span data-ttu-id="e2034-336">レポートが既定の SRS インスタンスにインストールされている場合、URL 形式は "http://$SERVERNAME $/ReportServer" と書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="e2034-336">If the reports were installed to a default SRS instance the URL format will formatted “http:// $SERVERNAME$/ReportServer”.</span></span> <span data-ttu-id="e2034-337">レポートが既定の SRS インスタンスにインストールされていた場合、URL 形式は "http://$SERVERNAME $/report% _ $ SQLINSTANCENAME $" に書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="e2034-337">If the reports were installed to a default SRS instance, the URL format will be formatted to “http://$SERVERNAME$/ReportServer\_$SQLINSTANCENAME$”.</span></span>



**<span data-ttu-id="e2034-338">データベースへのアクセスを構成するには</span><span class="sxs-lookup"><span data-stu-id="e2034-338">To configure the Access to the Databases</span></span>**

1.  <span data-ttu-id="e2034-339">回復とハードウェアを備えたサーバーまたはサーバーの場合また、コンプライアンスおよび監査データベースが展開されている場合は、サーバーマネージャーの [ローカルユーザーとグループ] スナップインを使用して、MBAM 管理と監視機能を実行する各サーバーから、"MBAM Recovery and Hardware DB Access" (Recovery and Hardware db Server) と "MBAM コンプライアンスステータス DB Access" (コンプライアンスおよび監査データベースサーバー) という名前の</span><span class="sxs-lookup"><span data-stu-id="e2034-339">On server or servers where the Recovery and Hardware, and Compliance and Audit databases are deployed, use the Local user and Groups snap-in from Server Manager to add the machine accounts from each server that run the MBAM Administration and Monitoring feature to the Local Groups named “MBAM Recovery and Hardware DB Access” (Recovery and Hardware DB Server) and “MBAM Compliance Status DB Access” (Compliance and Audit DB Server).</span></span>

2.  <span data-ttu-id="e2034-340">この手順を自動化するには、コンプライアンスデータベースと監査データベースが展開されているサーバー上で Windows PowerShell を使用することで、次のようなコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e2034-340">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell on the server where the Compliance and Audit databases were deployed.</span></span>

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$REPORTSUSERNAME$  /add`

3.  <span data-ttu-id="e2034-341">回復とハードウェアデータベースが展開されたサーバーで、Windows PowerShell を使用して、次のようなコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e2034-341">On the server where the Recovery and Hardware databases were deployed, run a command that is similar to the following one, by using Windows PowerShell.</span></span>

    `PS C:\> net localgroup "MBAM Recovery and Hardware DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    **<span data-ttu-id="e2034-342">注</span><span class="sxs-lookup"><span data-stu-id="e2034-342">Note</span></span>**  
    <span data-ttu-id="e2034-343">上の例の値を、環境に適した値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e2034-343">Replace the value from the preceding example with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="e2034-344">$DOMAIN $ \ \ $SERVERNAME $ $-MBAM 管理および監視サーバーのドメインとコンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-344">$DOMAIN$\\$SERVERNAME$$ - Enter the domain and machine name of the MBAM Administration and Monitoring Server.</span></span> <span data-ttu-id="e2034-345">サーバー名の後には、という名前を付ける必要があり **$** ます。</span><span class="sxs-lookup"><span data-stu-id="e2034-345">The server name must be followed by a **$**.</span></span> <span data-ttu-id="e2034-346">たとえば、MyDomain\\MyServerName1 $)</span><span class="sxs-lookup"><span data-stu-id="e2034-346">For example, MyDomain\\MyServerName1$)</span></span>

    -   <span data-ttu-id="e2034-347">$DOMAIN $ \ \ $REPORTSUSERNAME $-コンプライアンスおよび監査レポートのデータソースを構成するために使用されたユーザーアカウント名を入力します。</span><span class="sxs-lookup"><span data-stu-id="e2034-347">$DOMAIN$\\$REPORTSUSERNAME$ - Enter the user account name that was used to configure the data source for the Compliance and Audit reports.</span></span>



~~~
The commands listed for adding the server computer accounts to the MBAM local groups must be run for each Administration and Monitoring Server that will be accessing the databases in your environment.
~~~

## <span data-ttu-id="e2034-348">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e2034-348">Related topics</span></span>


[<span data-ttu-id="e2034-349">MBAM 1.0 機能の管理</span><span class="sxs-lookup"><span data-stu-id="e2034-349">Administering MBAM 1.0 Features</span></span>](administering-mbam-10-features.md)









