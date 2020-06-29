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
# <span data-ttu-id="2fe5d-103">MBAM 2.0 機能を別のコンピューターに移動する方法</span><span class="sxs-lookup"><span data-stu-id="2fe5d-103">How to Move MBAM 2.0 Features to Another Computer</span></span>


<span data-ttu-id="2fe5d-104">このトピックでは、1つ以上の Microsoft BitLocker 管理および監視 (MBAM) 機能を別のコンピューターに移行するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-104">This topic describes the steps that you should take to move one or more Microsoft BitLocker Administration and Monitoring (MBAM) features to a different computer.</span></span> <span data-ttu-id="2fe5d-105">複数の Microsoft BitLocker 管理および監視機能を移動する場合は、次の順序で移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-105">When moving more than one Microsoft BitLocker Administration and Monitoring feature, you should move them in the following order:</span></span>

1.  <span data-ttu-id="2fe5d-106">回復用データベース</span><span class="sxs-lookup"><span data-stu-id="2fe5d-106">Recovery Database</span></span>

2.  <span data-ttu-id="2fe5d-107">コンプライアンスと監査データベース</span><span class="sxs-lookup"><span data-stu-id="2fe5d-107">Compliance and Audit Database</span></span>

3.  <span data-ttu-id="2fe5d-108">コンプライアンスと監査レポート</span><span class="sxs-lookup"><span data-stu-id="2fe5d-108">Compliance and Audit Reports</span></span>

4.  <span data-ttu-id="2fe5d-109">管理と監視</span><span class="sxs-lookup"><span data-stu-id="2fe5d-109">Administration and Monitoring</span></span>

## <span data-ttu-id="2fe5d-110">回復データベースの移動</span><span class="sxs-lookup"><span data-stu-id="2fe5d-110">Moving the Recovery Database</span></span>


<span data-ttu-id="2fe5d-111">1台のコンピューターから別のコンピューターに回復用データベースを移動するには (たとえば、サーバー A からサーバー B に移動する)、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-111">To move the Recovery Database from one computer to another (for example, from Server A to Server B), use the following procedure.</span></span>

1.  <span data-ttu-id="2fe5d-112">管理と監視の web サイトのすべてのインスタンスを停止します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-112">Stop all instances of the Administration and Monitoring web site.</span></span>

2.  <span data-ttu-id="2fe5d-113">サーバー B で MBAM セットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-113">Run MBAM Setup on Server B.</span></span>

3.  <span data-ttu-id="2fe5d-114">サーバー A 上の MBAM 回復データベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-114">Back up the MBAM Recovery Database on Server A.</span></span>

4.  <span data-ttu-id="2fe5d-115">MBAM 回復データベースをサーバー A から B に移動します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-115">Move the MBAM Recovery Database from Server A to B.</span></span>

5.  <span data-ttu-id="2fe5d-116">サーバー B の MBAM 回復データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-116">Restore the MBAM Recovery Database on Server B.</span></span>

6.  <span data-ttu-id="2fe5d-117">サーバー B 上の MBAM 回復データベースへのアクセスを構成します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-117">Configure access to the MBAM Recovery Database on Server B.</span></span>

7.  <span data-ttu-id="2fe5d-118">MBAM 管理および監視サーバーのデータベース接続データを更新します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-118">Update the database connection data on MBAM Administration and Monitoring servers.</span></span>

8.  <span data-ttu-id="2fe5d-119">MBAM 管理と監視 web サイトのすべてのインスタンスを再開します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-119">Resume all instances of the MBAM Administration and Monitoring website.</span></span>

**<span data-ttu-id="2fe5d-120">MBAM 管理および監視 Web サイトのすべてのインスタンスを停止する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-120">Stop All Instances of the MBAM Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="2fe5d-121">MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、 **Microsoft BitLocker の管理と監視と**いう名前の mbam web サイトを停止します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-121">On each of the servers running the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to stop the MBAM website, which is named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="2fe5d-122">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-122">To automate this procedure, you can use Windows PowerShell to enter command line that is similar to the:</span></span>

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

    **<span data-ttu-id="2fe5d-123">注</span><span class="sxs-lookup"><span data-stu-id="2fe5d-123">Note</span></span>**  
    <span data-ttu-id="2fe5d-124">この PowerShell コマンドラインを実行するには、powershell の IIS モジュールを PowerShell の現在のインスタンスに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-124">To run this PowerShell command line, the IIS Module for PowerShell must be added to current instance of PowerShell.</span></span> <span data-ttu-id="2fe5d-125">さらに、PowerShell の実行ポリシーを更新して、スクリプトの実行を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-125">In addition, you must update the PowerShell execution policy to enable execution of scripts.</span></span>



**<span data-ttu-id="2fe5d-126">サーバー B で MBAM セットアップを実行する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-126">Run MBAM Setup on Server B</span></span>**

1.  <span data-ttu-id="2fe5d-127">サーバー B で MBAM セットアップを実行し、インストール用の**回復データベース**のみを選択します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-127">Run MBAM Setup on Server B and select only the **Recovery Database** for installation.</span></span>

2.  <span data-ttu-id="2fe5d-128">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-128">To automate this procedure, you can use Windows PowerShell to enter command line that is similar to the following:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=KeyDatabase ADMINANDMON_MACHINENAMES=$DOMAIN$\$SERVERNAME$$ RECOVERYANDHWDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ TOPOLOGY=$X$`

    **<span data-ttu-id="2fe5d-129">注</span><span class="sxs-lookup"><span data-stu-id="2fe5d-129">Note</span></span>**  
    <span data-ttu-id="2fe5d-130">上の例の次の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-130">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="2fe5d-131">$SERVERNAME $ \ \ $SQLINSTANCENAME $-回復データベースの移動先のサーバーとインスタンスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-131">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the name of the server and instance to which the Recovery Database will be moved.</span></span>

    -   <span data-ttu-id="2fe5d-132">$DOMAIN $ \ \ $SERVERNAME $-各 MBAM 管理と監視サーバーのドメイン名を入力します。これにより、回復データベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-132">$DOMAIN$\\$SERVERNAME$ - Enter the domain and server names of each MBAM Administration and Monitoring Server that will contact the Recovery Database.</span></span> <span data-ttu-id="2fe5d-133">セミコロンを使用して、リスト内の各ドメインとサーバーのペアを区切ります (たとえば、$DOMAIN \\SERVERNAME $; $DOMAIN \ \ $SERVERNAME $ $)。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-133">Use a semi-colon to separate each domain and server pairs in the list (for example, $DOMAIN\\SERVERNAME$;$DOMAIN\\$SERVERNAME$$).</span></span> <span data-ttu-id="2fe5d-134">例に示されているように、各サーバー名の後に "$" 記号を付ける必要があります (MyDomain\\MyServerName1 $;MyDomain\\MyServerName2 $)。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-134">Each server name must be followed by a “$” symbol, as shown in the example (MyDomain\\MyServerName1$; MyDomain\\MyServerName2$).</span></span>

    -   <span data-ttu-id="2fe5d-135">$X $-スタンドアロンの MBAM トポロジをインストールする場合は「 **0** 」、Mbam Configuration Manager トポロジをインストールする場合は「 **1** 」を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-135">$X$ - Enter **0** if you are installing the MBAM Stand-alone topology, or **1** if you are installing the MBAM Configuration Manager topology.</span></span>



**<span data-ttu-id="2fe5d-136">サーバー A 上の回復データベースをバックアップする</span><span class="sxs-lookup"><span data-stu-id="2fe5d-136">Back Up the Recovery Database on Server A</span></span>**

1.  <span data-ttu-id="2fe5d-137">サーバー A 上の回復データベースをバックアップするには、SQL Server Management Studio とバックアップという名前のタスクを使用します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-137">To back up the Recovery Database on Server A, use SQL Server Management Studio and the Task named Back Up.</span></span> <span data-ttu-id="2fe5d-138">既定では、データベース名は**Mbam 回復データベース**です。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-138">By default, the database name is **MBAM Recovery Database**.</span></span>

2.  <span data-ttu-id="2fe5d-139">この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-139">To automate this procedure, create a SQL file (.sql) that contains the following SQL script:</span></span>

    <span data-ttu-id="2fe5d-140">MBAM 回復データベースを変更して完全な回復モードを使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-140">Modify the MBAM Recovery Database to use the full recovery mode.</span></span>

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

    **<span data-ttu-id="2fe5d-141">注</span><span class="sxs-lookup"><span data-stu-id="2fe5d-141">Note</span></span>**  
    <span data-ttu-id="2fe5d-142">上の例の次の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-142">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="2fe5d-143">$PASSWORD $-秘密キーファイルの暗号化に使用するパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-143">$PASSWORD$ - Enter a password that you will use to encrypt the Private Key file.</span></span>



3.  <span data-ttu-id="2fe5d-144">Sql Server PowerShell と、次のようなコマンドラインを使用して SQL ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-144">Run the SQL File by using SQL Server PowerShell and a command line that is similar to the following:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile 'Z:\BackupMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="2fe5d-145">注</span><span class="sxs-lookup"><span data-stu-id="2fe5d-145">Note</span></span>**  
    <span data-ttu-id="2fe5d-146">上の例の次の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-146">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="2fe5d-147">$SERVERNAME $ \ \ $SQLINSTANCENAME $-回復データベースをバックアップするサーバーとインスタンスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-147">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the name of the server and instance from which the Recovery Database will be backed up.</span></span>



**<span data-ttu-id="2fe5d-148">サーバー A からサーバー B に回復データベースと証明書を移動する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-148">Move the Recovery Database and Certificate from Server A to Server B</span></span>**

1.  <span data-ttu-id="2fe5d-149">Windows エクスプローラーを使用して、次のファイルをサーバー A からサーバー B に移動します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-149">Move the following file from Server A to Server B by using Windows Explorer.</span></span>

    -   <span data-ttu-id="2fe5d-150">MBAM 回復データベースのデータ .bak</span><span class="sxs-lookup"><span data-stu-id="2fe5d-150">MBAM Recovery Database data.bak</span></span>

2.  <span data-ttu-id="2fe5d-151">暗号化されたデータベースの証明書を移動するには、次のオートメーションの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-151">To move the certificate for the encrypted database, use the following automation steps.</span></span> <span data-ttu-id="2fe5d-152">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-152">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Copy-Item “Z:\MBAM Recovery Database Data.bak” \\$SERVERNAME$\$DESTINATIONSHARE$`

    `PS C:\> Copy-Item “Z:\SQLServerInstanceCertificateFile” \\$SERVERNAME$\$DESTINATIONSHARE$`

    `PS C:\> Copy-Item “Z:\SQLServerInstanceCertificateFilePrivateKey” \\$SERVERNAME$\$DESTINATIONSHARE$`

    **<span data-ttu-id="2fe5d-153">注</span><span class="sxs-lookup"><span data-stu-id="2fe5d-153">Note</span></span>**  
    <span data-ttu-id="2fe5d-154">上の例の次の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-154">Replace the following value in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="2fe5d-155">$SERVERNAME $-ファイルのコピー先となるサーバーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-155">$SERVERNAME$ - Enter the name of the server to which the files will be copied.</span></span>

    -   <span data-ttu-id="2fe5d-156">$DESTINATIONSHARE $-ファイルのコピー先となる共有とパスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-156">$DESTINATIONSHARE$ - Enter the name of the share and path to which the files will be copied.</span></span>



**<span data-ttu-id="2fe5d-157">サーバー B の回復データベースを復元する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-157">Restore the Recovery Database on Server B</span></span>**

1.  <span data-ttu-id="2fe5d-158">SQL Server Management Studio と**Restore database**という名前のタスクを使用して、サーバー B の回復データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-158">Restore the Recovery Database on Server B by using SQL Server Management Studio and the task named **Restore Database**.</span></span>

2.  <span data-ttu-id="2fe5d-159">タスクが完了したら、[**デバイスから**] オプションを選択してデータベースのバックアップファイルを選び、[**追加**] コマンドを使用して mbam Recovery データベースの **.bak**ファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-159">Once the task has been completed, select the database backup file by selecting the **From Device** option and then use the **Add** command to select the MBAM Recovery database **Data.bak** file.</span></span>

3.  <span data-ttu-id="2fe5d-160">[ **OK]** を選んで、復元プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-160">Select **OK** to complete the restoration process.</span></span>

4.  <span data-ttu-id="2fe5d-161">この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-161">To automate this procedure, create a SQL file (.sql) that contains the following-SQL script:</span></span>

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

    **<span data-ttu-id="2fe5d-162">注</span><span class="sxs-lookup"><span data-stu-id="2fe5d-162">Note</span></span>**  
    <span data-ttu-id="2fe5d-163">上の例の次の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-163">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="2fe5d-164">$PASSWORD $-秘密キーファイルの暗号化に使用したパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-164">$PASSWORD$ - Enter a password that you used to encrypt the Private Key file.</span></span>



5.  <span data-ttu-id="2fe5d-165">Windows PowerShell を使用すると、次のようなコマンドラインを入力できます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-165">You can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile 'Z:\RestoreMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="2fe5d-166">注</span><span class="sxs-lookup"><span data-stu-id="2fe5d-166">Note</span></span>**  
    <span data-ttu-id="2fe5d-167">上の例の次の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-167">Replace the following value in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="2fe5d-168">$SERVERNAME $ \ \ $SQLINSTANCENAME $-回復データベースが復元されるサーバーとインスタンスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-168">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the name of the server and instance to which the Recovery Database will be restored.</span></span>



**<span data-ttu-id="2fe5d-169">サーバー B の回復データベースへのアクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-169">Configure Access to the Recovery Database on Server B</span></span>**

1.  <span data-ttu-id="2fe5d-170">サーバー B では、サーバーマネージャーから [ローカルユーザーとグループ] スナップインを使って、mbam **Recovery とハードウェアデータベースアクセス**の名前のローカルグループに対して、Mbam 管理と監視機能を実行している各サーバーからコンピューターアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-170">On Server B, use the Local user and Groups snap-in from Server Manager to add the computer accounts from each server that is running the MBAM Administration and Monitoring feature to the Local Group named **MBAM Recovery and Hardware DB Access**.</span></span>

2.  <span data-ttu-id="2fe5d-171">復元されたデータベースの SQL login **Mbam 回復とハードウェアデータベースアクセス**がログイン名 **$MachineName $ ¥ mbam RECOVERY とハードウェアデータベースアクセス**にマップされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-171">Verify that the SQL login **MBAM Recovery and Hardware DB Access** on the restored database is mapped to the login name **$MachineName$\\MBAM Recovery and Hardware DB Access**.</span></span> <span data-ttu-id="2fe5d-172">記載されているとおりにマップされていない場合は、類似したグループメンバーシップを持つ別のログインを作成し、ログイン名 **$MachineName $ ¥ mbam 回復とハードウェアデータベースアクセス**にマップします。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-172">If it is not mapped as described, create another login with similar group memberships, and map it to the login name **$MachineName$\\MBAM Recovery and Hardware DB Access**.</span></span>

3.  <span data-ttu-id="2fe5d-173">この手順を自動化するために、サーバー B で Windows PowerShell を使用して、次のようなコマンドラインを入力することができます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-173">To automate this procedure, you can use Windows PowerShell on Server B to enter a command line that is similar to the following:</span></span>

    `PS C:\> net localgroup "MBAM Recovery and Hardware DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    **<span data-ttu-id="2fe5d-174">注</span><span class="sxs-lookup"><span data-stu-id="2fe5d-174">Note</span></span>**  
    <span data-ttu-id="2fe5d-175">上の例の次の値を、環境に適した値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-175">Replace the following values in the example above with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="2fe5d-176">$DOMAIN $ \ \ $SERVERNAME $ $-MBAM 管理および監視サーバーのドメインとコンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-176">$DOMAIN$\\$SERVERNAME$$ - Enter the domain and machine name of the MBAM Administration and Monitoring Server.</span></span> <span data-ttu-id="2fe5d-177">例に示されているように、サーバー名の後に $ が続いている必要があります (たとえば、MyDomain\\MyServerName1 $)。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-177">The server name must be followed by a $, as shown in the example (for example, MyDomain\\MyServerName1$).</span></span>



~~~
This command line must be run for each Administration and Monitoring Server that will be accessing the database in your environment.
~~~

**<span data-ttu-id="2fe5d-178">MBAM 管理および監視サーバー上の回復データベース接続データを更新する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-178">Update the Recovery Database Connection Data on the MBAM Administration and Monitoring Servers</span></span>**

1. <span data-ttu-id="2fe5d-179">MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、次のアプリケーションの接続文字列情報を更新します。これは、管理と監視の web サイトでホストされています。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-179">On each of the servers running the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to update the Connection String information for the following applications, which are hosted in the Administration and Monitoring website:</span></span>

   -   <span data-ttu-id="2fe5d-180">Mbam管理サービス</span><span class="sxs-lookup"><span data-stu-id="2fe5d-180">MBAMAdministrationService</span></span>

   -   <span data-ttu-id="2fe5d-181">Mbamrecoveryandハードウェアサービス</span><span class="sxs-lookup"><span data-stu-id="2fe5d-181">MBAMRecoveryAndHardwareService</span></span>

2. <span data-ttu-id="2fe5d-182">各アプリケーションを選択し、**機能ビュー**の [**管理**] セクションにある**構成エディター**機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-182">Select each application and use the **Configuration Editor** feature, which is located under the **Management** section of the **Feature View**.</span></span>

3. <span data-ttu-id="2fe5d-183">[**セクションリスト**] コントロールで [ **configurationstrings** ] オプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-183">Select the **configurationStrings** option from the **Section list** control.</span></span>

4. <span data-ttu-id="2fe5d-184">" **(コレクション)** " という行を選択し、行の右側にあるボタンを選択して、**コレクションエディター**を開きます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-184">Select the row named **(Collection)** and open the **Collection Editor** by selecting the button on the right side of the row.</span></span>

5. <span data-ttu-id="2fe5d-185">**コレクションエディター**で、Mbamgraph service アプリケーションの構成を更新するときは**keyrecoveryconnectionstring**という名前の行を選択します。それについては、「 <strong> Microsoft Mb"recoveryandcompdatastore </strong> " という名前の行を選びます。ConnectionString は、Mbamrecoveryandなサービスの構成を更新するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-185">In the **Collection Editor**, select the row named **KeyRecoveryConnectionString** when updating the configuration for the MBAMAdministrationService application or the row named <strong>Microsoft.Mbam.RecoveryAndHardwareDataStore.</strong>ConnectionString when updating the configuration for the MBAMRecoveryAndHardwareService.</span></span>

6. <span data-ttu-id="2fe5d-186">**Configurationstrings**プロパティの**データソース =** 値を更新して、回復用データベースの移動先のサーバー名とインスタンス (たとえば $SERVERNAME $ \ \ $SQLINSTANCENAME $) を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-186">Update the **Data Source=** value for the **configurationStrings** property to list the server name and instance (for example, $SERVERNAME$\\$SQLINSTANCENAME$) where the Recovery Database was moved to.</span></span>

7. <span data-ttu-id="2fe5d-187">この手順を自動化するために、Windows を使用して、次のようなコマンドラインを各管理および監視サーバーに入力することができます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-187">To automate this procedure, you can use Windows to enter a command line, that is similar to the following, on each Administration and Monitoring Server:</span></span>

   `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="KeyRecoveryConnectionString"]' -PSPath "IIS:\sites\Microsoft Bitlocker Administration and Monitoring\MBAMAdministrationService" -Name "connectionString" -Value “Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and Hardware;Integrated Security=SSPI;”`

   `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="Microsoft.Mbam.RecoveryAndHardwareDataStore.ConnectionString"]' -PSPath "IIS:\sites\Microsoft Bitlocker Administration and Monitoring\MBAMRecoveryAndHardwareService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and Hardware;Integrated Security=SSPI;"`

   **<span data-ttu-id="2fe5d-188">注</span><span class="sxs-lookup"><span data-stu-id="2fe5d-188">Note</span></span>**  
   <span data-ttu-id="2fe5d-189">上の例の次の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-189">Replace the following value in the example above with those that match your environment:</span></span>

   -   <span data-ttu-id="2fe5d-190">$SERVERNAME $ \ \ $SQLINSTANCENAME $-回復用データベースのサーバー名とインスタンスを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-190">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Recovery Database is.</span></span>



**<span data-ttu-id="2fe5d-191">MBAM 管理および監視 Web サイトのすべてのインスタンスを再開する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-191">Resume all Instances of the MBAM Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="2fe5d-192">MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、 **Microsoft BitLocker の管理と監視と**いう名前の mbam web サイトを起動します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-192">On each server that is running the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to start the MBAM website, which is named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="2fe5d-193">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-193">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the:</span></span>

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

## <span data-ttu-id="2fe5d-194">コンプライアンスと監査データベース機能の移動</span><span class="sxs-lookup"><span data-stu-id="2fe5d-194">Moving the Compliance and Audit Database Feature</span></span>


<span data-ttu-id="2fe5d-195">MBAM コンプライアンスと監査データベースを1台のコンピューターから別のコンピューターに移動する場合 (つまり、サーバー A からサーバー B にデータベースを移動する場合)、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-195">If you want to move the MBAM Compliance and Audit Database from one computer to another (that is, move the database from Server A to Server B), use the following procedure.</span></span> <span data-ttu-id="2fe5d-196">このプロセスには、次のような大まかな手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-196">The process includes the following high-level steps:</span></span>

1.  <span data-ttu-id="2fe5d-197">管理と監視の web サイトのすべてのインスタンスを停止します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-197">Stop all instances of the Administration and Monitoring website.</span></span>

2.  <span data-ttu-id="2fe5d-198">サーバー B で MBAM セットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-198">Run MBAM setup on Server B.</span></span>

3.  <span data-ttu-id="2fe5d-199">サーバー A 上のデータベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-199">Back up the Database on Server A.</span></span>

4.  <span data-ttu-id="2fe5d-200">サーバー A から B にデータベースを移動します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-200">Move the Database from Server A to B.</span></span>

5.  <span data-ttu-id="2fe5d-201">サーバー B でデータベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-201">Restore the Database on Server B.</span></span>

6.  <span data-ttu-id="2fe5d-202">サーバー B 上のデータベースへのアクセスを構成します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-202">Configure access to the Database on Server B.</span></span>

7.  <span data-ttu-id="2fe5d-203">MBAM 管理および監視サーバー上のデータベース接続データを更新します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-203">Update the database connection data on the MBAM Administration and Monitoring servers.</span></span>

8.  <span data-ttu-id="2fe5d-204">SSRS レポートデータソース接続文字列を、コンプライアンスと監査データベースの新しい場所で更新します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-204">Update the SSRS reports data source connection string with the new location of the Compliance and Audit Database.</span></span>

9.  <span data-ttu-id="2fe5d-205">管理と監視の web サイトのすべてのインスタンスを再開します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-205">Resume all instances of the Administration and Monitoring website.</span></span>

**<span data-ttu-id="2fe5d-206">管理と監視の Web サイトのすべてのインスタンスを停止する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-206">Stop All Instances of the Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="2fe5d-207">MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、 **Microsoft BitLocker の管理と監視と**いう名前の mbam web サイトを停止します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-207">On each server that is running the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to stop the MBAM website named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="2fe5d-208">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-208">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Stop-s “Microsoft BitLocker Administration and Monitoring”`

    **<span data-ttu-id="2fe5d-209">注</span><span class="sxs-lookup"><span data-stu-id="2fe5d-209">Note</span></span>**  
    <span data-ttu-id="2fe5d-210">このコマンドラインを実行するには、powershell の IIS モジュールを PowerShell の現在のインスタンスに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-210">To run this command line, you must add the IIS Module for PowerShell to the current instance of PowerShell.</span></span> <span data-ttu-id="2fe5d-211">さらに、PowerShell の実行ポリシーを更新して、スクリプトを実行できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-211">In addition, you must update the PowerShell execution policy to enable scripts to be run.</span></span>



**<span data-ttu-id="2fe5d-212">サーバー B で MBAM セットアップを実行する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-212">Run MBAM Setup on Server B</span></span>**

1.  <span data-ttu-id="2fe5d-213">サーバー B で MBAM セットアップを実行し、インストール用の**コンプライアンスおよび監査データベース**のみを選択します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-213">Run MBAM Setup on Server B and select only the **Compliance and Audit Database** for installation.</span></span>

2.  <span data-ttu-id="2fe5d-214">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-214">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal= ReportsDatabase ADMINANDMON_MACHINENAMES=$DOMAIN$\$SERVERNAME$ COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ REPORTS_USERACCOUNT=$DOMAIN$\$USERNAME$ TOPOLOGY=$X$`

    **<span data-ttu-id="2fe5d-215">注</span><span class="sxs-lookup"><span data-stu-id="2fe5d-215">Note</span></span>**  
    <span data-ttu-id="2fe5d-216">注: 上の例の次の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-216">Note: Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="2fe5d-217">$SERVERNAME $ \ \ $SQLINSTANCENAME $-コンプライアンスと監査データベースの移動先のサーバー名とインスタンスを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-217">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Compliance and Audit Database will be moved to.</span></span>

    -   <span data-ttu-id="2fe5d-218">$DOMAIN $ \ \ $SERVERNAME $-各 MBAM 管理と監視サーバーのドメイン名を入力します。これは、コンプライアンスと監査データベースに連絡します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-218">$DOMAIN$\\$SERVERNAME$ - Enter the domain and server names of each MBAM Administration and Monitoring Server that will contact the Compliance and Audit Database.</span></span> <span data-ttu-id="2fe5d-219">セミコロンを使用して、リスト内の各ドメインとサーバーのペアを区切ります (たとえば、$DOMAIN \\SERVERNAME $; $DOMAIN \ \ $SERVERNAME $ $)。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-219">Use a semi-colon to separate each domain and server pair in the list (for example, $DOMAIN\\SERVERNAME$;$DOMAIN\\$SERVERNAME$$).</span></span> <span data-ttu-id="2fe5d-220">例に示されているように、各サーバー名の後に "$" 記号を付ける必要があります (MyDomain\\MyServerName1 $;MyDomain\\MyServerName2 $)。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-220">Each server name must be followed by a “$” symbol, as shown in the example (MyDomain\\MyServerName1$; MyDomain\\MyServerName2$).</span></span>

    -   <span data-ttu-id="2fe5d-221">$DOMAIN $ \ \ $USERNAME $-コンプライアンスおよび監査レポート機能でコンプライアンスと監査データベースに接続するために使用されるドメインとユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-221">$DOMAIN$\\$USERNAME$ - Enter the domain and user name that will be used by the Compliance and Audit Reports feature to connect to the Compliance and Audit Database.</span></span>

    -   <span data-ttu-id="2fe5d-222">$X $-スタンドアロンの MBAM トポロジをインストールする場合は「 **0** 」、Mbam Configuration Manager トポロジをインストールする場合は「 **1** 」を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-222">$X$ - Enter **0** if you are installing the MBAM Stand-alone topology, or **1** if you are installing the MBAM Configuration Manager topology.</span></span>



**<span data-ttu-id="2fe5d-223">サーバー A 上のコンプライアンスおよび監査データベースのバックアップを作成する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-223">Back Up the Compliance and Audit Database on Server A</span></span>**

1.  <span data-ttu-id="2fe5d-224">Server A 上のコンプライアンスおよび監査データベースをバックアップするには、SQL Server Management Studio と**バックアップ**という名前のタスクを使用します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-224">To back up the Compliance and Audit Database on Server A, use SQL Server Management Studio and the task named **Back Up**.</span></span> <span data-ttu-id="2fe5d-225">既定では、データベース名は**Mbam コンプライアンスステータスデータベース**です。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-225">By default, the database name is **MBAM Compliance Status Database**.</span></span>

2.  <span data-ttu-id="2fe5d-226">この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-226">To automate this procedure, create a SQL file (.sql) that contains the following-SQL script:</span></span>

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

3.  <span data-ttu-id="2fe5d-227">次のような Windows PowerShell コマンドラインを使用して、SQL ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-227">Run the SQL file by using a Windows PowerShell command line that is similar to the following:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile "Z:\BackupMBAMComplianceStatusDatabaseScript.sql" –ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="2fe5d-228">注</span><span class="sxs-lookup"><span data-stu-id="2fe5d-228">Note</span></span>**  
    <span data-ttu-id="2fe5d-229">上の例の次の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-229">Replace the following value in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="2fe5d-230">$SERVERNAME $ \ \ $SQLINSTANCENAME $-コンプライアンスと監査データベースがバックアップされるサーバー名とインスタンスを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-230">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Compliance and Audit database will be backed up from.</span></span>



**<span data-ttu-id="2fe5d-231">コンプライアンスと監査データベースをサーバー A から B に移動する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-231">Move the Compliance and Audit Database from Server A to B</span></span>**

1.  <span data-ttu-id="2fe5d-232">Windows エクスプローラーを使用して、次のファイルをサーバー A からサーバー B に移動します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-232">Move the following files from Server A to Server B using Windows Explorer.</span></span>

    -   <span data-ttu-id="2fe5d-233">MBAM コンプライアンスステータスデータベースデータ .bak</span><span class="sxs-lookup"><span data-stu-id="2fe5d-233">MBAM Compliance Status Database Data.bak</span></span>

2.  <span data-ttu-id="2fe5d-234">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-234">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Copy-Item “Z:\MBAM Compliance Status Database Data.bak” \\$SERVERNAME$\$DESTINATIONSHARE$`

    **<span data-ttu-id="2fe5d-235">注</span><span class="sxs-lookup"><span data-stu-id="2fe5d-235">Note</span></span>**  
    <span data-ttu-id="2fe5d-236">上の例の次の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-236">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="2fe5d-237">$SERVERNAME $-ファイルのコピー先のサーバー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-237">$SERVERNAME$ - Enter the server name where the files will be copied to.</span></span>

    -   <span data-ttu-id="2fe5d-238">$DESTINATIONSHARE $-ファイルのコピー先の共有名とパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-238">$DESTINATIONSHARE$ - Enter the name of share and path where the files will be copied to.</span></span>



**<span data-ttu-id="2fe5d-239">サーバー B でコンプライアンスと監査データベースを復元する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-239">Restore the Compliance and Audit Database on Server B</span></span>**

1.  <span data-ttu-id="2fe5d-240">SQL Server Management Studio と**Restore database**という名前のタスクを使用して、server B 上のコンプライアンスおよび監査データベースを復元します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-240">Restore the Compliance and Audit Database on Server B by using SQL Server Management Studio and the task named **Restore Database**.</span></span>

2.  <span data-ttu-id="2fe5d-241">タスクが完了したら、[**デバイスから**] オプションを選択してデータベースバックアップファイルを選び、[**追加**] コマンドを使用して、Mbam コンプライアンスステータスデータベースデータ .bak ファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-241">Once the task has been completed, select the database backup file by selecting the **From Device** option and then use the **Add** command to select the MBAM Compliance Status Database Data.bak file.</span></span> <span data-ttu-id="2fe5d-242">[ **OK]** を選んで、復元プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-242">Select **OK** to complete the restoration process.</span></span>

3.  <span data-ttu-id="2fe5d-243">この手順を自動化するには、次の SQL スクリプトを含む SQL ファイル (.sql) を作成します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-243">To automate this procedure, create a SQL file (.sql) that contains the following-SQL script:</span></span>

    ```sql
    -- Create MBAM Compliance Status Database Data logical backup devices. 

    Use master

    GO

    -- Restore the MBAM Compliance Status database data files.

    RESTORE DATABASE [MBAM Compliance Status]

       FROM DISK = 'C:\test\MBAM Compliance Status Database Data.bak'

       WITH REPLACE
    ```

4.  <span data-ttu-id="2fe5d-244">次のような Windows PowerShell コマンドラインを使用して、SQL ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-244">Run the SQL File by using a Windows PowerShell command line that is similar to the following:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile "Z:\RestoreMBAMComplianceStatusDatabaseScript.sql" -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="2fe5d-245">注</span><span class="sxs-lookup"><span data-stu-id="2fe5d-245">Note</span></span>**  
    <span data-ttu-id="2fe5d-246">上の例の次の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-246">Replace the following value in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="2fe5d-247">$SERVERNAME $ \ \ $SQLINSTANCENAME $-コンプライアンスと監査データベースが復元されるサーバー名とインスタンスを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-247">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Compliance and Audit Database will be restored to.</span></span>



**<span data-ttu-id="2fe5d-248">サーバー B 上のコンプライアンスおよび監査データベースへのアクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-248">Configure Access to the Compliance and Audit Database on Server B</span></span>**

1.  <span data-ttu-id="2fe5d-249">サーバー B では、サーバーマネージャーの [ローカルユーザーとグループ] スナップインを使用して、mbam の管理と監視の機能を実行している各サーバーから、 **Mbam コンプライアンスステータスの DB Access**という名前のローカルグループにコンピューターアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-249">On Server B, use the Local user and Groups snap-in from Server Manager to add the computer accounts from each server that is running the MBAM Administration and Monitoring feature to the local group named **MBAM Compliance Status DB Access**.</span></span>

2.  <span data-ttu-id="2fe5d-250">復元されたデータベースの SQL login **Mbam コンプライアンス監査データベースアクセス**がログイン名 **$MachineName $ \ \ MBAM コンプライアンス監査データベースアクセス**にマップされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-250">Verify that the SQL login **MBAM Compliance Auditing DB Access** on the restored database is mapped to the login name **$MachineName$\\ MBAM Compliance Auditing DB Access**.</span></span> <span data-ttu-id="2fe5d-251">記載されている手順に従ってマッピングされていない場合は、類似したグループメンバーシップを使用して別のログインを作成し、ログイン名 **$MachineName $ \ \ MBAM コンプライアンス監査データベースアクセス**にマップします。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-251">If it is not mapped as described, create another login with similar group memberships, and map it to the login name **$MachineName$\\ MBAM Compliance Auditing DB Access**.</span></span>

3.  <span data-ttu-id="2fe5d-252">この手順を自動化するには、Windows PowerShell を使用して、次のようなサーバー B にコマンドラインを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-252">To automate this procedure, you can use Windows PowerShell to enter a command line on Server B that is similar to the following:</span></span>

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$REPORTSUSERNAME$  /add`

    **<span data-ttu-id="2fe5d-253">注</span><span class="sxs-lookup"><span data-stu-id="2fe5d-253">Note</span></span>**  
    <span data-ttu-id="2fe5d-254">上の例の次の値を、環境に適した値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-254">Replace the following values in the example above with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="2fe5d-255">$DOMAIN $ \ \ $SERVERNAME $ $-MBAM 管理および監視サーバーのドメインとコンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-255">$DOMAIN$\\$SERVERNAME$$ - Enter the domain and machine name of the MBAM Administration and Monitoring Server.</span></span> <span data-ttu-id="2fe5d-256">例に示されているように、サーバー名の後に "$" を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-256">The server name must be followed by a “$” as shown in the example.</span></span> <span data-ttu-id="2fe5d-257">(MyDomain\\MyServerName1 $ など)</span><span class="sxs-lookup"><span data-stu-id="2fe5d-257">(for example, MyDomain\\MyServerName1$)</span></span>

    -   <span data-ttu-id="2fe5d-258">$DOMAIN $ \ \ $REPORTSUSERNAME $-コンプライアンスおよび監査レポートのデータソースを構成するために使用されたユーザーアカウント名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-258">$DOMAIN$\\$REPORTSUSERNAME$ - Enter the user account name that was used to configure the data source for the Compliance and Audit Reports.</span></span>



~~~
The command line for adding the servers to the MBAM Compliance and Audit Database access local group must be run for each Administration and Monitoring Server that will be accessing the database in your environment.
~~~

**<span data-ttu-id="2fe5d-259">MBAM 管理および監視サーバー上のデータベース接続データを更新する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-259">Update the Database Connection Data on MBAM Administration and Monitoring Servers</span></span>**

1.  <span data-ttu-id="2fe5d-260">MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、次のアプリケーションの接続文字列情報を更新します。これは、管理と監視の web サイトでホストされています。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-260">On each server that is running the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to update the connection string information for the following applications, which are hosted in the Administration and Monitoring website:</span></span>

    -   <span data-ttu-id="2fe5d-261">Mbam管理サービス</span><span class="sxs-lookup"><span data-stu-id="2fe5d-261">MBAMAdministrationService</span></span>

    -   <span data-ttu-id="2fe5d-262">MBAMComplianceStatusService</span><span class="sxs-lookup"><span data-stu-id="2fe5d-262">MBAMComplianceStatusService</span></span>

2.  <span data-ttu-id="2fe5d-263">各アプリケーションを選択し、**機能ビュー**の [**管理**] セクションにある**構成エディター**機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-263">Select each application and use the **Configuration Editor** feature, which is located under the **Management** section of the **Feature View**.</span></span>

3.  <span data-ttu-id="2fe5d-264">[**セクションリスト**] コントロールで [ **configurationstrings** ] オプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-264">Select the **configurationStrings** option from the **Section list** control.</span></span>

4.  <span data-ttu-id="2fe5d-265">" **(コレクション)**" という名前の行を選び、行の右側にあるボタンを選択して、**コレクションエディター**を開きます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-265">Select the row named **(Collection)**, and open the **Collection Editor** by selecting the button on the right side of the row.</span></span>

5.  <span data-ttu-id="2fe5d-266">**コレクションエディター**で、MBAMAdministrationService アプリケーションの構成を更新するときに**ComplianceStatusConnectionString**という名前の行を選択するか、MBAMComplianceStatusService の構成を更新するときに、**という名前の**行を選びます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-266">In the **Collection Editor**, select the row named **ComplianceStatusConnectionString** when updating the configuration for the MBAMAdministrationService application, or the row named **Microsoft.Windows.Mdop.BitLockerManagement.StatusReportDataStore.ConnectionString** when updating the configuration for the MBAMComplianceStatusService.</span></span>

6.  <span data-ttu-id="2fe5d-267">**Configurationstrings**プロパティの**データソース =** 値を更新して、回復データベースの移動先のサーバーとインスタンスの名前を一覧表示します (例: $SERVERNAME $ \ \ $SQLINSTANCENAME)。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-267">Update the **Data Source=** value for the **configurationStrings** property to list the name of the server and instance (for example, $SERVERNAME$\\$SQLINSTANCENAME) to which the Recovery Database was moved.</span></span>

7.  <span data-ttu-id="2fe5d-268">この手順を自動化するために、Windows を使用して、次のような管理および監視サーバーごとにコマンドラインを入力することができます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-268">To automate this procedure, you can use Windows to enter a command line on each Administration and Monitoring Server that is similar to the following:</span></span>

    `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="ComplianceStatusConnectionString"]' -PSPath "IIS:\sites\Microsoft Bitlocker Administration and Monitoring\MBAMAdministrationService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Compliance Status;Integrated Security=SSPI;"`

    `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="Microsoft.Windows.Mdop.BitLockerManagement.StatusReportDataStore.ConnectionString"]' -PSPath "IIS:\sites\Microsoft Bitlocker Administration and Monitoring\MBAMComplianceStatusService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME;Initial Catalog=MBAM Compliance Status;Integrated Security=SSPI;"`

    **<span data-ttu-id="2fe5d-269">注</span><span class="sxs-lookup"><span data-stu-id="2fe5d-269">Note</span></span>**  
    <span data-ttu-id="2fe5d-270">上の例の次の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-270">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="2fe5d-271">$SERVERNAME $ \ \ $SQLINSTANCENAME $-回復用データベースが配置されているサーバー名とインスタンスを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-271">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Recovery Database is located.</span></span>



**<span data-ttu-id="2fe5d-272">MBAM 管理および監視 Web サイトのすべてのインスタンスを再開する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-272">Resume All Instances of the MBAM Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="2fe5d-273">MBAM 管理と監視機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、 **Microsoft BitLocker の管理と監視と**いう名前の mbam web サイトを起動します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-273">On each server that is running the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to start the MBAM website named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="2fe5d-274">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-274">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

## <span data-ttu-id="2fe5d-275">コンプライアンスおよび監査レポートを移動する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-275">Moving the Compliance and Audit Reports</span></span>


<span data-ttu-id="2fe5d-276">MBAM コンプライアンスと監査レポートを1台のコンピューターから別のコンピューターに移動する場合 (つまり、サーバー A からサーバー B にレポートを移動する場合)、次の手順を実行します。これには、次のような大まかな手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-276">If you want to move the MBAM Compliance and Audit Reports from one computer to another (that is, move the reports from Server A to Server B), use the following procedure, which includes the following high-level steps:</span></span>

1.  <span data-ttu-id="2fe5d-277">サーバー B で MBAM セットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-277">Run MBAM setup on Server B.</span></span>

2.  <span data-ttu-id="2fe5d-278">サーバー B のコンプライアンスおよび監査レポートへのアクセスを構成します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-278">Configure access to the Compliance and Audit Reports on Server B.</span></span>

3.  <span data-ttu-id="2fe5d-279">MBAM 管理と監視 web サイトのすべてのインスタンスを停止します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-279">Stop all instances of the MBAM Administration and Monitoring website.</span></span>

4.  <span data-ttu-id="2fe5d-280">MBAM 管理および監視サーバーのレポート接続データを更新します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-280">Update the reports connection data on MBAM Administration and Monitoring servers.</span></span>

5.  <span data-ttu-id="2fe5d-281">MBAM 管理と監視 web サイトのすべてのインスタンスを再開します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-281">Resume all instances of the MBAM Administration and Monitoring website.</span></span>

**<span data-ttu-id="2fe5d-282">サーバー B で MBAM セットアップを実行する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-282">Run MBAM Setup on Server B</span></span>**

1.  <span data-ttu-id="2fe5d-283">サーバー B で MBAM セットアップを実行し、インストールの**コンプライアンスおよび監査レポート**機能のみを選択します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-283">Run MBAM Setup on Server B and select only the **Compliance and Audit Reports** feature for installation.</span></span>

2.  <span data-ttu-id="2fe5d-284">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-284">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=Reports COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ REPORTS_USERACCOUNTPW=$PASSWORD$ TOPOLOGY=$X$`

    **<span data-ttu-id="2fe5d-285">注</span><span class="sxs-lookup"><span data-stu-id="2fe5d-285">Note</span></span>**  
    <span data-ttu-id="2fe5d-286">上の例の次の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-286">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="2fe5d-287">$SERVERNAME $ \ \ $SQLINSTANCENAME $-コンプライアンスと監査データベースが配置されているサーバー名とインスタンスを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-287">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Compliance and Audit Database is located.</span></span>

    -   <span data-ttu-id="2fe5d-288">$DOMAIN $ \ \ $USERNAME $-コンプライアンスおよび監査レポート機能でコンプライアンスと監査データベースに接続するために使用されるドメインとユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-288">$DOMAIN$\\$USERNAME$ - Enter the domain and user name that will be used by the Compliance and Audit Reports feature to connect to the Compliance and Audit Database.</span></span>

    -   <span data-ttu-id="2fe5d-289">$PASSWORD $-コンプライアンスと監査データベースへの接続に使用されるユーザーアカウントのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-289">$PASSWORD$ - Enter the password of the user account that will be used to connect to the Compliance and Audit Database.</span></span>

    -   <span data-ttu-id="2fe5d-290">$X $-スタンドアロンの MBAM トポロジをインストールする場合は「 **0** 」、Mbam Configuration Manager トポロジをインストールする場合は「 **1** 」を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-290">$X$ - Enter **0** if you are installing the MBAM Stand-alone topology, or **1** if you are installing the MBAM Configuration Manager topology.</span></span>



**<span data-ttu-id="2fe5d-291">サーバー B のコンプライアンスおよび監査レポートへのアクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-291">Configure Access to the Compliance and Audit Reports on Server B</span></span>**

1.  <span data-ttu-id="2fe5d-292">サーバー B では、[サーバーマネージャー] から [ローカルユーザーとグループ] スナップインを使用して、コンプライアンスレポートおよび監査レポートへのアクセス権を持つユーザーアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-292">On Server B, use the Local user and Groups snap-in from Server Manager to add the user accounts that will have access to the Compliance and Audit Reports.</span></span> <span data-ttu-id="2fe5d-293">MBAM レポートユーザーという名前のローカルグループにユーザーアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-293">Add the user accounts to the local group named MBAM Report Users.</span></span>

2.  <span data-ttu-id="2fe5d-294">この手順を自動化するには、Windows PowerShell を使用して、次のようなサーバー B にコマンドラインを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-294">To automate this procedure, you can use Windows PowerShell to enter a command line on Server B that is similar to the following:</span></span>

    `PS C:\> net localgroup "MBAM Report Users" $DOMAIN$\$REPORTSUSERNAME$  /add`

    **<span data-ttu-id="2fe5d-295">注</span><span class="sxs-lookup"><span data-stu-id="2fe5d-295">Note</span></span>**  
    <span data-ttu-id="2fe5d-296">上の例の次の値を、環境に適した値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-296">Replace the following values in the example above with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="2fe5d-297">$DOMAIN $ \ \ $REPORTSUSERNAME $-コンプライアンスおよび監査レポートのデータソースを構成するために使用されたユーザーアカウント名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-297">$DOMAIN$\\$REPORTSUSERNAME$ - Enter the user account name that was used to configure the data source for the Compliance and Audit reports.</span></span>



~~~
The command line for adding the users to the MBAM Report Users local group must be run for each user that will be accessing the reports in your environment.
~~~

**<span data-ttu-id="2fe5d-298">MBAM 管理および監視 Web サイトのすべてのインスタンスを停止する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-298">Stop All Instances of the MBAM Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="2fe5d-299">MBAM 管理と監視サーバー機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、 **Microsoft BitLocker の管理と監視と**いう名前の mbam web サイトを停止します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-299">On each server that is running the MBAM Administration and Monitoring Server feature, use the Internet Information Services (IIS) Manager console to stop the MBAM website named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="2fe5d-300">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-300">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

**<span data-ttu-id="2fe5d-301">MBAM 管理および監視サーバー上のデータベース接続データを更新する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-301">Update the Database Connection Data on the MBAM Administration and Monitoring Servers</span></span>**

1. <span data-ttu-id="2fe5d-302">MBAM 管理および監視サーバー機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、コンプライアンスと監査レポートの URL を更新します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-302">On each server that is running the MBAM Administration and Monitoring Server feature, use the Internet Information Services (IIS) Manager console to update the Compliance and Audit Reports URL.</span></span>

2. <span data-ttu-id="2fe5d-303">**Microsoft BitLocker の管理と監視**の web サイトを選び、**機能ビュー**の [**管理**] セクションの下にある [**構成エディター** ] 機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-303">Select the **Microsoft BitLocker Administration and Monitoring** website, and use the **Configuration Editor** feature that is location under the **Management** section of the **Feature View**.</span></span>

3. <span data-ttu-id="2fe5d-304">[**セクションリスト**] コントロールから [ **appSettings** ] オプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-304">Select the **appSettings** option from the **Section list** control.</span></span>

4. <span data-ttu-id="2fe5d-305">" **(コレクション)** " という行を選択し、行の右側にあるボタンを選択して、**コレクションエディター**を開きます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-305">Select the row named **(Collection)** and open the **Collection Editor** by selecting the button on the right side of the row.</span></span>

5. <span data-ttu-id="2fe5d-306">**コレクションエディター**で、「 **Mbam. .url**」という名前の行を選びます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-306">In the **Collection Editor**, select the row named **Microsoft.Mbam.Reports.Url**.</span></span>

6. <span data-ttu-id="2fe5d-307">サーバー B のサーバー名を反映するには、" **Mbam** " の値を更新します。指定した SQL Reporting Services インスタンスにコンプライアンスと監査レポート機能がインストールされている場合は、URL にインスタンスの名前を追加または更新してください (例 http://$SERVERNAME $/reportserver _ $ SQLSRSINSTANCENAME $/Pages....)。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-307">Update the value for **Microsoft.Mbam.Reports.Url** to reflect the server name for Server B. If the Compliance and Audit Reports feature was installed on a named SQL Reporting Services instance, be sure to add or update the name of the instance to the URL (for example, http://$SERVERNAME$/ReportServer\_$SQLSRSINSTANCENAME$/Pages....)</span></span>

7. <span data-ttu-id="2fe5d-308">この手順を自動化するために、Windows PowerShell を使用して、次のような管理および監視サーバーごとにコマンドラインを入力することができます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-308">To automate this procedure, you can use Windows PowerShell to enter a command line on each Administration and Monitoring Server that is similar to the following:</span></span>

   `PS C:\> Set-WebConfigurationProperty '/appSettings/add[@key="Microsoft.Mbam.Reports.Url"]' -PSPath "IIS:\ \sites\Microsoft Bitlocker Administration and Monitoring\HelpDesk" -Name "Value" -Value “http://$SERVERNAME$/ReportServer_$SRSINSTANCENAME$/Pages/ReportViewer.aspx?/ Microsoft+BitLocker+Administration+and+Monitoring/”`

   **<span data-ttu-id="2fe5d-309">注</span><span class="sxs-lookup"><span data-stu-id="2fe5d-309">Note</span></span>**  
   <span data-ttu-id="2fe5d-310">上の例の次の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-310">Replace the following values in the example above with those that match your environment:</span></span>

   -   <span data-ttu-id="2fe5d-311">$SERVERNAME $-コンプライアンスと監査レポートがインストールされたサーバー名の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-311">$SERVERNAME$ - Enter the name of the server name to which the Compliance and Audit Reports were installed.</span></span>

   -   <span data-ttu-id="2fe5d-312">$SRSINSTANCENAME $-コンプライアンスと監査レポートがインストールされた SQL Reporting Services インスタンスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-312">$SRSINSTANCENAME$ - Enter the name of the SQL Reporting Services instance to which the Compliance and Audit Reports were installed.</span></span>



**<span data-ttu-id="2fe5d-313">MBAM 管理および監視 Web サイトのすべてのインスタンスを再開する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-313">Resume All Instances of the MBAM Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="2fe5d-314">MBAM 管理と監視サーバー機能を実行している各サーバーで、インターネットインフォメーションサービス (IIS) マネージャーコンソールを使用して、 **Microsoft BitLocker の管理と監視と**いう名前の mbam web サイトを起動します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-314">On each server that is running the MBAM Administration and Monitoring Server feature, use the Internet Information Services (IIS) Manager console to Start the MBAM website named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="2fe5d-315">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-315">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

    **<span data-ttu-id="2fe5d-316">注</span><span class="sxs-lookup"><span data-stu-id="2fe5d-316">Note</span></span>**  
    <span data-ttu-id="2fe5d-317">このコマンドラインを実行するには、powershell の IIS モジュールを PowerShell の現在のインスタンスに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-317">To run this command line, you must add the IIS Module for PowerShell to current instance of PowerShell.</span></span> <span data-ttu-id="2fe5d-318">さらに、PowerShell の実行ポリシーを更新して、スクリプトを実行できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-318">In addition, you must update the PowerShell execution policy to enable scripts to be run.</span></span>



## <span data-ttu-id="2fe5d-319">管理と監視機能の移動</span><span class="sxs-lookup"><span data-stu-id="2fe5d-319">Moving the Administration and Monitoring Feature</span></span>


<span data-ttu-id="2fe5d-320">MBAM 管理と監視レポート機能をあるコンピューターから別のコンピューターに移動する場合 (つまり、サーバー A からサーバー B にその機能を移行する場合)、次の手順を実行します。これには、次のような大まかな手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-320">If you want to move the MBAM Administration and Monitoring Reports feature from one computer to another (that is, move the feature from Server A to Server B), use the following procedure, which includes the following high-level steps:</span></span>

1.  <span data-ttu-id="2fe5d-321">サーバー B で MBAM セットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-321">Run MBAM Setup on Server B.</span></span>

2.  <span data-ttu-id="2fe5d-322">サーバー B 上のデータベースへのアクセスを構成します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-322">Configure access to the Database on Server B.</span></span>

**<span data-ttu-id="2fe5d-323">サーバー B で MBAM セットアップを実行する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-323">Run MBAM Setup on Server B</span></span>**

1.  <span data-ttu-id="2fe5d-324">サーバー B で MBAM セットアップを実行し、インストールの [**管理/監視サーバー** ] 機能のみを選択します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-324">Run MBAM Setup on Server B and select only the **Administration and Monitoring Server** feature for installation.</span></span>

2.  <span data-ttu-id="2fe5d-325">この手順を自動化するには、Windows PowerShell を使用して、次のようなコマンドラインを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-325">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=AdministrationMonitoringServer, COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ RECOVERYANDHWDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ SRS_REPORTSITEURL=$REPORTSSERVERURL$ TOPOLOGY=$X$`

    **<span data-ttu-id="2fe5d-326">注</span><span class="sxs-lookup"><span data-stu-id="2fe5d-326">Note</span></span>**  
    <span data-ttu-id="2fe5d-327">上の例の次の値を、使用している環境に一致する値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-327">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="2fe5d-328">$SERVERNAME $ \ \ $SQLINSTANCENAME $-COMPLIDB \ _SQLINSTANCE パラメーターには、コンプライアンスと監査データベースが配置されているサーバー名とインスタンスを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-328">$SERVERNAME$\\$SQLINSTANCENAME$ - For the COMPLIDB\_SQLINSTANCE parameter, enter the server name and instance where the Compliance and Audit Database is located.</span></span> <span data-ttu-id="2fe5d-329">RECOVERYANDHWDB \ _SQLINSTANCE パラメーターには、回復データベースが配置されているサーバー名とインスタンスを入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-329">For the RECOVERYANDHWDB\_SQLINSTANCE parameter, enter the server name and instance where the Recovery Database is located.</span></span>

    -   <span data-ttu-id="2fe5d-330">$DOMAIN $ \ \ $USERNAME $-コンプライアンスおよび監査レポート機能でコンプライアンスと監査データベースに接続するために使用されるドメインとユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-330">$DOMAIN$\\$USERNAME$ - Enter the domain and user name that will be used by the Compliance and Audit Reports feature to connect to the Compliance and Audit Database.</span></span>

    -   <span data-ttu-id="2fe5d-331">$ ¥ SERVERURL $-SQL Reporting Service web サイトのホームの場所の URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-331">$ REPORTSSERVERURL$ - Enter the URL for the Home location of the SQL Reporting Service website.</span></span> <span data-ttu-id="2fe5d-332">レポートが既定の SRS インスタンスにインストールされている場合、URL 形式は "http://$SERVERNAME $/ReportServer" の形式になります。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-332">If the reports were installed to a default SRS instance, the URL format will have the format “http:// $SERVERNAME$/ReportServer”.</span></span> <span data-ttu-id="2fe5d-333">レポートが既定の SRS インスタンスにインストールされていた場合、URL 形式の形式は "http://$SERVERNAME $/report% _ $ SQLINSTANCENAME $" の形式になります。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-333">If the reports were installed to a default SRS instance, the URL format will have the format “http://$SERVERNAME$/ReportServer\_$SQLINSTANCENAME$”.</span></span>

    -   <span data-ttu-id="2fe5d-334">$X $-スタンドアロンの MBAM トポロジをインストールする場合は「 **0** 」、Mbam Configuration Manager トポロジをインストールする場合は「 **1** 」を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-334">$X$ - Enter **0** if you are installing the MBAM Stand-alone topology, or **1** if you are installing the MBAM Configuration Manager topology.</span></span>



**<span data-ttu-id="2fe5d-335">データベースへのアクセスを構成する</span><span class="sxs-lookup"><span data-stu-id="2fe5d-335">Configure Access to the Databases</span></span>**

1.  <span data-ttu-id="2fe5d-336">回復データベースとコンプライアンスおよび監査データベースが展開されているサーバー上で、サーバーマネージャーから [ローカルユーザーとグループ] スナップインを使用して、mbam **Recovery とハードウェアデータベースアクセス**(回復用データベースサーバー) と**Mbam コンプライアンスステータス DB access** (コンプライアンスおよび監査データベースサーバー) を実行している各サーバーから、コンピューターアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-336">On the server or servers where the Recovery Database and Compliance and Audit Database are deployed, use the Local user and Groups snap-in from Server Manager to add the computer accounts from each server that is running the MBAM Administration and Monitoring Server feature to the local groups named **MBAM Recovery and Hardware DB Access** (Recovery DB Server) and **MBAM Compliance Status DB Access** (Compliance and Audit Database Server).</span></span>

2.  <span data-ttu-id="2fe5d-337">この手順を自動化するために、Windows PowerShell を使用して、コンプライアンスと監査データベースが展開されたサーバー上で、次のようなコマンドラインを入力できます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-337">To automate this procedure, you can use Windows PowerShell to enter a command line, that is similar to the following, on the server where the Compliance and Audit Database was deployed.</span></span>

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$SERVERNAME$$  /add`

3.  <span data-ttu-id="2fe5d-338">回復データベースが展開されたサーバーでは、Windows PowerShell を使用して、次のようなコマンドラインを入力することができます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-338">On the server where the Recovery database was deployed, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> net localgroup "MBAM Recovery and Hardware DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    **<span data-ttu-id="2fe5d-339">注</span><span class="sxs-lookup"><span data-stu-id="2fe5d-339">Note</span></span>**  
    <span data-ttu-id="2fe5d-340">上の例の次の値を、環境に適した値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-340">Replace the following value in the example above with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="2fe5d-341">$DOMAIN $ \ \ $SERVERNAME $ $-管理および監視サーバーのドメインとマシン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-341">$DOMAIN$\\$SERVERNAME$$ - Enter the domain and machine name of the Administration and Monitoring Server.</span></span> <span data-ttu-id="2fe5d-342">例に示されているように、サーバー名の後に "$" 記号を付ける必要があります (たとえば、MyDomain\\MyServerName1 $ など)。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-342">The server name must be followed by a “$” symbol, as shown in the example (for example, MyDomain\\MyServerName1$).</span></span>

    -   <span data-ttu-id="2fe5d-343">$DOMAIN $ \ \ $REPORTSUSERNAME $-コンプライアンスおよび監査レポートのデータソースを構成するために使用されたユーザーアカウント名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2fe5d-343">$DOMAIN$\\$REPORTSUSERNAME$ - Enter the user account name that was used to configure the data source for the Compliance and Audit Reports.</span></span>



~~~
The command lines that are listed for adding server computer accounts to the MBAM local groups must be run for each Administration and Monitoring Server that will be accessing the databases in your environment.
~~~

## <span data-ttu-id="2fe5d-344">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2fe5d-344">Related topics</span></span>


[<span data-ttu-id="2fe5d-345">MBAM 2.0 の保守</span><span class="sxs-lookup"><span data-stu-id="2fe5d-345">Maintaining MBAM 2.0</span></span>](maintaining-mbam-20-mbam-2.md)









