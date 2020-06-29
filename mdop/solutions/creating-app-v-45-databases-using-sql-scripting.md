---
title: SQL スクリプトを使用した APP-V 4.5 データベースの作成
description: SQL スクリプトを使用した APP-V 4.5 データベースの作成
author: dansimp
ms.assetid: 6cd0b180-163e-463f-a658-939ab9a7cfa1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d9ab2c102a43701bfdeaac49359b4ca3c4a063fa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825977"
---
# <span data-ttu-id="286c5-103">SQL スクリプトを使用した APP-V 4.5 データベースの作成</span><span class="sxs-lookup"><span data-stu-id="286c5-103">Creating App-V 4.5 Databases Using SQL Scripting</span></span>


**<span data-ttu-id="286c5-104">このソリューションの目的</span><span class="sxs-lookup"><span data-stu-id="286c5-104">Who is this solution intended for?</span></span>** <span data-ttu-id="286c5-105">Application Virtualization (App-v) 4.5 データベースを管理する it 技術者。</span><span class="sxs-lookup"><span data-stu-id="286c5-105">Information technology professionals who manage Application Virtualization (App-V) 4.5 databases.</span></span>

**<span data-ttu-id="286c5-106">このガイドはどのように役立つのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="286c5-106">How can this guide help you?</span></span>** <span data-ttu-id="286c5-107">この解決策では、管理者のインストールで SQL Server に "sysadmin" 権限が付与されていない場合に、Microsoft Application Virtualization Server をインストールする手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="286c5-107">This solution explains and documents the procedure to install the Microsoft Application Virtualization Server when the administrator installing does not have “sysadmin” privileges to the SQL Server.</span></span>

## <span data-ttu-id="286c5-108">概要</span><span class="sxs-lookup"><span data-stu-id="286c5-108">Overview</span></span>


<span data-ttu-id="286c5-109">Microsoft Application Virtualization 4.5 (App-v) をインストールする際の問題の1つとして、インストールプログラムでは、サーバー機能をインストールするユーザーはローカルコンピューターの管理者であると同時に、データストアをホストする SQL server の SQL 管理者権限を持つ必要があると見なされます。</span><span class="sxs-lookup"><span data-stu-id="286c5-109">One of the challenges of installing Microsoft Application Virtualization 4.5 (App-V) is that the install program assumes that the user installing the server features will not only be a local computer administrator, but also have SQL administrator privileges on the SQL server that will host the Data Store.</span></span> <span data-ttu-id="286c5-110">この要件は、データベースがインストールの一部として作成されたものであり、適切な役割とアクセス許可が作成されていることに基づいています。</span><span class="sxs-lookup"><span data-stu-id="286c5-110">This requirement is based on the fact that the database, as well as the appropriate roles and permissions, are created as part of the install.</span></span> <span data-ttu-id="286c5-111">ただし、ほとんどの企業では、SQL server は、App-v をインストールするインフラストラクチャチームとは別に管理されます。</span><span class="sxs-lookup"><span data-stu-id="286c5-111">However, in most enterprises, SQL servers are managed separately from the infrastructure team who will be installing App-V.</span></span> <span data-ttu-id="286c5-112">これらのセキュリティ要件により、SQL 管理者は、App-v の適切な権限をインストールすることが困難になります。同様に、SQL 管理者には、インフラストラクチャチームの製品をインストールするために必要な権限がありません。</span><span class="sxs-lookup"><span data-stu-id="286c5-112">These security requirements will make it difficult to get SQL administrators to give the infrastructure administrator installing App-V adequate rights; similarly, the SQL administrators will not have the required privileges to install the product for the infrastructure team.</span></span>

<span data-ttu-id="286c5-113">現時点では、App-v をインストールしようとしている管理者は、SQL "sysadmin" 権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="286c5-113">Currently, an administrator attempting the installation of App-V must have SQL “sysadmin” privileges.</span></span> <span data-ttu-id="286c5-114">以前のバージョンの製品では、SQL 管理者は、一時的な "sysadmin" アカウントを作成するか、インストール中に "sysadmin" 権限を持つ資格情報を提供するように設定することができます。</span><span class="sxs-lookup"><span data-stu-id="286c5-114">In previous versions of the product the setup allowed for the SQL administrators to either create a temporary “sysadmin” account or be present during installation to provide credentials with “sysadmin” privileges.</span></span> <span data-ttu-id="286c5-115">このリリースでは、すべての管理者がインフラストラクチャを実装するときに使用するために、リリースされた製品でスクリプトを提供しています。</span><span class="sxs-lookup"><span data-stu-id="286c5-115">In this release, scripts are provided in the released product for all administrators to use when implementing their infrastructure.</span></span>

<span data-ttu-id="286c5-116">このホワイトペーパーでは、インストールを2つの別々のタスク (SQL データベースの作成、アプリ-V server 機能のインストール) に分ける必要があるシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="286c5-116">This whitepaper discusses the scenario in which the install will need to be divided into two separate tasks: creating the SQL database, and installing the App-V server features.</span></span> <span data-ttu-id="286c5-117">SQL 管理者は、SQL スクリプトを確認し、他のデータベースとの競合を解決したり、他のツールとの統合をサポートしたりするように変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="286c5-117">The SQL administrators would be able to review the SQL scripts and make modifications to resolve any conflicts with other databases, or to support integration with other tools.</span></span> <span data-ttu-id="286c5-118">スクリプトの結果として、sql 管理者は、sql server の高度な権限を付与する必要がないように、データベースの準備を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="286c5-118">The result of the scripts is to allow SQL administrators to prepare the database so that the infrastructure administrators do not have to be granted any advanced rights on the SQL server.</span></span> <span data-ttu-id="286c5-119">これは、セキュリティポリシーによって禁止されている環境で重要です。</span><span class="sxs-lookup"><span data-stu-id="286c5-119">This is important in environments where security policies would prohibit this.</span></span>

### <span data-ttu-id="286c5-120">SQL データベースの作成プロセス</span><span class="sxs-lookup"><span data-stu-id="286c5-120">SQL Database Creation Process</span></span>

<span data-ttu-id="286c5-121">SQL スクリプトを使用すると、SQL 管理者が必要なデータベースを作成できるようにしたり、アプリの管理者が環境を正常にインストールして管理するための権限を設定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="286c5-121">The SQL scripts allow for SQL administrators to create the required database and also set up the privileges for the App-V administrators to successfully install and manage the environment.</span></span> <span data-ttu-id="286c5-122">これらのタスクを完了する手順は、このドキュメントの後半に記載されています。</span><span class="sxs-lookup"><span data-stu-id="286c5-122">The steps for completing these tasks are listed later in this document.</span></span>

<span data-ttu-id="286c5-123">このプロセスでは、データベースの作成と構成のアクションが、実際の App-v インストールから分離されます。</span><span class="sxs-lookup"><span data-stu-id="286c5-123">This process separates the database creation and configuration actions from the actual App-V installation.</span></span>

**<span data-ttu-id="286c5-124">SQL 管理者に提供される情報</span><span class="sxs-lookup"><span data-stu-id="286c5-124">Information to be provided to SQL administrators</span></span>**

-   <span data-ttu-id="286c5-125">App-v 管理者の権限を持つ広告グループの名前</span><span class="sxs-lookup"><span data-stu-id="286c5-125">Name of AD group that is going to be the App-V admin’s</span></span>

-   <span data-ttu-id="286c5-126">App-v Management Server をインストールするサーバーの名前</span><span class="sxs-lookup"><span data-stu-id="286c5-126">Name of the server where App-V Management Server will be installed</span></span>

**<span data-ttu-id="286c5-127">インフラストラクチャ管理者に返す情報</span><span class="sxs-lookup"><span data-stu-id="286c5-127">Information to be returned to the Infrastructure administrators</span></span>**

-   <span data-ttu-id="286c5-128">データベースサーバーまたはインスタンスの名前と、App-v データベースの名前</span><span class="sxs-lookup"><span data-stu-id="286c5-128">Name of the database server or instance and the name of the App-V database</span></span>

<span data-ttu-id="286c5-129">データベースの準備が完了したら、App-v 管理者は、SQL 管理者権限を持たずに app-v のインストールを実行できます。</span><span class="sxs-lookup"><span data-stu-id="286c5-129">Once the database has been prepared, the App-V administrators can run the App-V installation without SQL administrator privileges.</span></span>

### <span data-ttu-id="286c5-130">SQL セットアップスクリプトを使用する</span><span class="sxs-lookup"><span data-stu-id="286c5-130">Using the SQL Setup Scripts</span></span>

**<span data-ttu-id="286c5-131">要件</span><span class="sxs-lookup"><span data-stu-id="286c5-131">Requirements</span></span>**

<span data-ttu-id="286c5-132">選択した抽出位置のルートの support\\createdb フォルダーにあるスクリプトを使用するための要件の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="286c5-132">The following is a list of requirements for using the scripts which are located in the support\\createdb folder at the root of the selected extract location.</span></span>

-   <span data-ttu-id="286c5-133">スクリプトは、実行先のコンピューター上の書き込み可能な場所にコピーする必要があります (コピーされた後にこれらのスクリプトから読み取り専用属性を削除してください)。 SQL クライアントツールは、そのコンピューターに読み込む必要があります (osql は、ローカルコンピューターでサンプルのバッチファイルを実行する場合のみ必要です)。</span><span class="sxs-lookup"><span data-stu-id="286c5-133">Scripts must be copied to a writeable location on the computer where they will be run (be sure to remove the read only attribute from these scripts after they have been copied) and SQL client tools must be loaded on that computer (osql is only required for running the sample batch files on the local computer).</span></span>

-   <span data-ttu-id="286c5-134">SQL Server は Windows 認証をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="286c5-134">The SQL Server must support Windows Authentication.</span></span>

-   <span data-ttu-id="286c5-135">SQL Server インスタンスと SQL エージェントサービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="286c5-135">Ensure that the SQL Server Instance and SQL Agent Service are running.</span></span>

-   <span data-ttu-id="286c5-136">スクリプトが実行されるコンピューターの SQL 管理者 (sysadmin) であるドメインアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="286c5-136">Log on with a domain account that is a SQL administrator (sysadmin) on the computer where the scripts will be done.</span></span>

<span data-ttu-id="286c5-137">スクリプトは、ログオンしているユーザーのドメイン資格情報で実行されます。</span><span class="sxs-lookup"><span data-stu-id="286c5-137">The scripts runs under the logged-on user’s domain credentials.</span></span>

**<span data-ttu-id="286c5-138">SQL スクリプトを使用したデータベースの作成</span><span class="sxs-lookup"><span data-stu-id="286c5-138">Database Creation Using SQL Scripts</span></span>**

**<span data-ttu-id="286c5-139">SQL 管理者が実行するタスク:</span><span class="sxs-lookup"><span data-stu-id="286c5-139">Tasks to be performed by SQL administrators:</span></span>**

1.  <span data-ttu-id="286c5-140">選択した抽出場所のルートから、スクリプトが実行されるコンピューターに、support\\createdb フォルダーに含まれているスクリプトをコピーします。</span><span class="sxs-lookup"><span data-stu-id="286c5-140">Copy the scripts contained in the support\\createdb folder from the root of the selected extract location to the computer where the scripts will be run.</span></span> <span data-ttu-id="286c5-141">スクリプトを正しく実行するためには次のファイルが必要であり、次の順序で呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="286c5-141">The following files are required for the scripts to run properly and must be called in the order presented below.</span></span>

    -   <span data-ttu-id="286c5-142">データベース。 sql</span><span class="sxs-lookup"><span data-stu-id="286c5-142">database.sql</span></span>

    -   <span data-ttu-id="286c5-143">ロール. sql</span><span class="sxs-lookup"><span data-stu-id="286c5-143">roles.sql</span></span>

    -   <span data-ttu-id="286c5-144">表 \ _CODES</span><span class="sxs-lookup"><span data-stu-id="286c5-144">table\_CODES.sql</span></span>

    -   <span data-ttu-id="286c5-145">関数 \ _before \ _tables</span><span class="sxs-lookup"><span data-stu-id="286c5-145">functions\_before\_tables.sql</span></span>

    -   <span data-ttu-id="286c5-146">表 .sql</span><span class="sxs-lookup"><span data-stu-id="286c5-146">tables.sql</span></span>

    -   <span data-ttu-id="286c5-147">関数 .sql</span><span class="sxs-lookup"><span data-stu-id="286c5-147">functions.sql</span></span>

    -   <span data-ttu-id="286c5-148">views</span><span class="sxs-lookup"><span data-stu-id="286c5-148">views.sql</span></span>

    -   <span data-ttu-id="286c5-149">手順 .sql</span><span class="sxs-lookup"><span data-stu-id="286c5-149">procedures.sql</span></span>

    -   <span data-ttu-id="286c5-150">triggers</span><span class="sxs-lookup"><span data-stu-id="286c5-150">triggers.sql</span></span>

    -   <span data-ttu-id="286c5-151">データ \ _codes .sql</span><span class="sxs-lookup"><span data-stu-id="286c5-151">data\_codes.sql</span></span>

    -   <span data-ttu-id="286c5-152">データ \ _messages .sql</span><span class="sxs-lookup"><span data-stu-id="286c5-152">data\_messages.sql</span></span>

    -   <span data-ttu-id="286c5-153">データ \ _defaults .sql</span><span class="sxs-lookup"><span data-stu-id="286c5-153">data\_defaults.sql</span></span>

    -   <span data-ttu-id="286c5-154">通知 \ _jobs</span><span class="sxs-lookup"><span data-stu-id="286c5-154">alerts\_jobs.sql</span></span>

    -   <span data-ttu-id="286c5-155">dbversion .sql</span><span class="sxs-lookup"><span data-stu-id="286c5-155">dbversion.sql</span></span>

2.  <span data-ttu-id="286c5-156">ファイルを確認し、必要に応じて変更し `database.sql` ます。</span><span class="sxs-lookup"><span data-stu-id="286c5-156">Review and modify, if necessary, the `database.sql` file.</span></span> <span data-ttu-id="286c5-157">既定の設定では、データベースに "APPVIRTDB" という名前が付いています。</span><span class="sxs-lookup"><span data-stu-id="286c5-157">The default settings will name the database “APPVIRTDB.”</span></span>

    -   <span data-ttu-id="286c5-158">必要に応じて、が使用されるのインスタンスをに置き換え `APPVIRTDB` `database name` ます。</span><span class="sxs-lookup"><span data-stu-id="286c5-158">If necessary replace instances of `APPVIRTDB` with the `database name` that will be used.</span></span>

    -   <span data-ttu-id="286c5-159">`FILENAME`スクリプト内のプロパティを、データベースを作成する SQL Server の適切なパスに変更します。</span><span class="sxs-lookup"><span data-stu-id="286c5-159">Modify the `FILENAME` property in the script with the appropriate path for the SQL Server where the database will be created.</span></span>

3.  <span data-ttu-id="286c5-160">必要に応じて、 `database name [APPVIRTDB]` データベースの .sql ファイルで `roles.sql` 使用されていたファイルの内容を確認して変更します。</span><span class="sxs-lookup"><span data-stu-id="286c5-160">Review and modify, if necessary, the `database name [APPVIRTDB]` in the `roles.sql` file that was used in the database.sql file.</span></span>

****

### <span data-ttu-id="286c5-161">バッチファイルを使用してプロセスを自動化する方法の例</span><span class="sxs-lookup"><span data-stu-id="286c5-161">Example of how to automate the process using batch files</span></span>

<span data-ttu-id="286c5-162">この2つのサンプルバッチファイルを使用すると、次のような方法で SQL スクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="286c5-162">If used, the two sample batch files provided run the SQL scripts in the following manner:</span></span>

1.  **<span data-ttu-id="286c5-163">Create\_schema.bat (1)</span><span class="sxs-lookup"><span data-stu-id="286c5-163">Create\_schema.bat (1)</span></span>**

    -   <span data-ttu-id="286c5-164">データベース。 sql</span><span class="sxs-lookup"><span data-stu-id="286c5-164">database.sql</span></span>

    -   <span data-ttu-id="286c5-165">ロール. sql</span><span class="sxs-lookup"><span data-stu-id="286c5-165">roles.sql</span></span>

2.  **<span data-ttu-id="286c5-166">Create\_tables.bat (2)</span><span class="sxs-lookup"><span data-stu-id="286c5-166">Create\_tables.bat (2)</span></span>**

    -   <span data-ttu-id="286c5-167">表 \ _CODES</span><span class="sxs-lookup"><span data-stu-id="286c5-167">table\_CODES.sql</span></span>

    -   <span data-ttu-id="286c5-168">関数 \ _before \ _tables</span><span class="sxs-lookup"><span data-stu-id="286c5-168">functions\_before\_tables.sql</span></span>

    -   <span data-ttu-id="286c5-169">表 .sql</span><span class="sxs-lookup"><span data-stu-id="286c5-169">tables.sql</span></span>

    -   <span data-ttu-id="286c5-170">関数 .sql</span><span class="sxs-lookup"><span data-stu-id="286c5-170">functions.sql</span></span>

    -   <span data-ttu-id="286c5-171">views</span><span class="sxs-lookup"><span data-stu-id="286c5-171">views.sql</span></span>

    -   <span data-ttu-id="286c5-172">手順 .sql</span><span class="sxs-lookup"><span data-stu-id="286c5-172">procedures.sql</span></span>

    -   <span data-ttu-id="286c5-173">triggers</span><span class="sxs-lookup"><span data-stu-id="286c5-173">triggers.sql</span></span>

    -   <span data-ttu-id="286c5-174">データ \ _codes .sql</span><span class="sxs-lookup"><span data-stu-id="286c5-174">data\_codes.sql</span></span>

    -   <span data-ttu-id="286c5-175">データ \ _messages .sql</span><span class="sxs-lookup"><span data-stu-id="286c5-175">data\_messages.sql</span></span>

    -   <span data-ttu-id="286c5-176">データ \ _defaults .sql</span><span class="sxs-lookup"><span data-stu-id="286c5-176">data\_defaults.sql</span></span>

    -   <span data-ttu-id="286c5-177">通知 \ _jobs</span><span class="sxs-lookup"><span data-stu-id="286c5-177">alerts\_jobs.sql</span></span>

    -   <span data-ttu-id="286c5-178">dbversion .sql</span><span class="sxs-lookup"><span data-stu-id="286c5-178">dbversion.sql</span></span>

**<span data-ttu-id="286c5-179">注</span><span class="sxs-lookup"><span data-stu-id="286c5-179">Note</span></span>**  
<span data-ttu-id="286c5-180">スクリプトを変更するときは慎重に考慮する必要があります。また、適切な知識を持っているユーザーだけが実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="286c5-180">Careful consideration when modifying the scripts must be taken and should only be done by someone with the appropriate knowledge.</span></span> <span data-ttu-id="286c5-181">また、表示されるサンプルファイルは、次のように変更する必要があります。 **create\_schema.bat**、 **create\_tables.bat**、 **.sql**、および**roles**。</span><span class="sxs-lookup"><span data-stu-id="286c5-181">Also, of the sample files presented only the following should be changed: **create\_schema.bat**, **create\_tables.bat**, **database.sql**, and **roles.sql**.</span></span> <span data-ttu-id="286c5-182">その他のすべてのファイルを変更しないようにする必要があります。これにより、データベースが正しく作成されないことがあります。これにより、App-v サービスのインストールに失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="286c5-182">All other files should not be modified in any way as this could cause the database to be created incorrectly, which will lead to the failure of App-V services to be installed.</span></span>



<span data-ttu-id="286c5-183">この2つのサンプルバッチファイルは、コンピューター上の他の SQL スクリプトのコピー先と同じディレクトリに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="286c5-183">The two sample batch files must be placed in the same directory where the rest of the SQL scripts were copied to on the computer.</span></span>

1.  <span data-ttu-id="286c5-184">サンプルの**create\_schema.bat**ファイルを実行してデータベースを作成します。</span><span class="sxs-lookup"><span data-stu-id="286c5-184">Run the sample **create\_schema.bat** file to create the database.</span></span> <span data-ttu-id="286c5-185">このスクリプトは、完了までに数秒かかりますので、中断する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="286c5-185">This script will take several seconds to complete and should not be interrupted.</span></span>

    -   <span data-ttu-id="286c5-186">コピー先のディレクトリから [create schema.bat ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="286c5-186">Run the create schema.bat file from the directory where it was copied to.</span></span> <span data-ttu-id="286c5-187">書式: "Create\_schema.bat `SQLSERVERNAME` "</span><span class="sxs-lookup"><span data-stu-id="286c5-187">Syntax is: “Create\_schema.bat `SQLSERVERNAME`”</span></span>

        ![AppV46SQLcreatebat](images/appv46sqlcreatebat.bmp)

    -   <span data-ttu-id="286c5-189">このスクリプトが新しい "APPVIRTDB" データベースの作成中に失敗した場合は、上記のようにログを確認して問題を修正します。</span><span class="sxs-lookup"><span data-stu-id="286c5-189">If this script fails during the creation of the new “APPVIRTDB” database, check the log as indicated to correct the issue.</span></span> <span data-ttu-id="286c5-190">以降の試行が適切に動作するようにするために、スクリプトの一部を実行して作成されたデータベースを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="286c5-190">It will be necessary to delete the database that was created with a partial running of the scripts in order to ensure that subsequent attempts will work properly.</span></span>

2.  <span data-ttu-id="286c5-191">ファイルを実行して `create_tables.bat` データベース内のテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="286c5-191">Run the `create_tables.bat` file to create the tables in the database.</span></span> <span data-ttu-id="286c5-192">このスクリプトは、完了までに数秒かかりますので、中断する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="286c5-192">This script will take several seconds to complete and should not be interrupted.</span></span>

    -   <span data-ttu-id="286c5-193">コピーされたディレクトリから create\_tables.bat ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="286c5-193">Run the create\_tables.bat file from the directory where it was copied.</span></span> <span data-ttu-id="286c5-194">書式: "create\_tables.bat `SQLSERVERNAME DBNAME` "</span><span class="sxs-lookup"><span data-stu-id="286c5-194">Syntax is: “create\_tables.bat `SQLSERVERNAME DBNAME`”</span></span>

        ![app-v 4.6 sql create\-table.bat](images/appv46sqlcreate-tablebat.gif)

        <span data-ttu-id="286c5-196">テーブルの作成時にスクリプトが失敗した場合は、上記のようにログを確認して問題を修正します。</span><span class="sxs-lookup"><span data-stu-id="286c5-196">If the script fails during the creation of the tables, check the log as indicated to correct the issue.</span></span> <span data-ttu-id="286c5-197">データベースを削除して create\_schema.bat 実行してから、create\_tables.bat ファイルを実行しようとするたびに実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="286c5-197">It will be necessary to delete the database and run create\_schema.bat before attempting to run the create\_tables.bat file on all subsequent attempts.</span></span>

### <span data-ttu-id="286c5-198">App-v データベースのアクセス許可を設定する</span><span class="sxs-lookup"><span data-stu-id="286c5-198">Setting permissions on the App-V database</span></span>

<span data-ttu-id="286c5-199">アプリのインストール、展開、継続的な管理のために、新しいデータベースに対する特定の権限と役割を持つ SQL server 上で、次のアカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="286c5-199">The following accounts will need to be created on the SQL server with specific permissions and roles to the new database for the installation, deployment and ongoing administration of the App-V environment.</span></span>

-   <span data-ttu-id="286c5-200">SQL Server 上の App-v 管理グループのログインを作成し、"domain\\App-V Admins" ("domain" と "App-v Admins" は、自分の環境を反映するために変更されます) APPVIRTDB データベースを作成し、それを SFTAdmin と SFTEveryone database role に追加します。</span><span class="sxs-lookup"><span data-stu-id="286c5-200">Create a login for the App-V administrators group on the SQL Server and the APPVIRTDB database for the “domain\\App-V Admins” (where “domain” and “App-V Admins” will be changed to reflect your own environment) and add them to the SFTAdmin and SFTEveryone database role.</span></span>

    ![app-v 4.6 sql スクリプト: 権限とロールを設定する](images/appv46sqlscriptsetpermsroles.gif)

-   <span data-ttu-id="286c5-202">グローバルレベルで "VIEW ANY DEFINITION" アクセス許可を与える (Microsoft Application Virtualization Management Server のセットアッププロセスでは、管理サーバーのログインが既に存在することを確認できます)。</span><span class="sxs-lookup"><span data-stu-id="286c5-202">Grant this group “VIEW ANY DEFINITION” permission at the global level (This allows the Microsoft Application Virtualization Management Server setup process to verify that the Management Server login already exists).</span></span> <span data-ttu-id="286c5-203">[MS SQL 2005] の下で、.master に含まれるメタデータに対するアクセス制限が追加されました。</span><span class="sxs-lookup"><span data-stu-id="286c5-203">Under MS-SQL 2005 and above access restrictions to the metadata contained in master.db were added.</span></span> <span data-ttu-id="286c5-204">前の手順で作成したユーザーには、サーバーのインストールに必要な権限が既定で付与されることはありません。</span><span class="sxs-lookup"><span data-stu-id="286c5-204">The user created in the previous step will by default not have the rights needed by the server installation.</span></span> <span data-ttu-id="286c5-205">以前に作成したログインプロパティ-Securables のプロパティを開き &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="286c5-205">Open the properties of the previously created login, Login Properties-&gt;Securables.</span></span> <span data-ttu-id="286c5-206">次のスクリーンショットのように、データベースインスタンスを追加して、"すべての定義を表示" に "GRANT" を有効にします。</span><span class="sxs-lookup"><span data-stu-id="286c5-206">Add the Database instance and enable “GRANT” for “View any definition” as shown in the screenshot below.</span></span>

    ![app-v 4.6 sql スクリプト表示の権限を付与する](images/appv46sqlscriptviewanydef.gif)

-   <span data-ttu-id="286c5-208">前の手順で作成したログインの役割 \ _ASSIGNMENTS テーブルに役割を追加して、Application Virtualization 管理コンソールへのアクセスを許可します。役割 = "ADMIN" とグループ \ _ref = "domain\\App-V administrator" ("domain" と "App-info Admins") は、自分の環境を反映するように変更されます)。</span><span class="sxs-lookup"><span data-stu-id="286c5-208">Add a role to the ROLE\_ASSIGNMENTS table for the login created in the previous step to allow App-V administrators access to the Application Virtualization Management Console, with role = “ADMIN” and group\_ref = “domain\\App-V Admins” (where “domain” and “App-V Admins” will be changed to reflect your own environment).</span></span>

    ![app-v 4.6 sql スクリプトの役割の割り当て](images/appv46sqlscriptroleassign.gif)

-   <span data-ttu-id="286c5-210">管理サーバーの SQL Server と App-v データベースのログインを作成します。</span><span class="sxs-lookup"><span data-stu-id="286c5-210">Create login for SQL Server and App-V database for the Management Server.</span></span> <span data-ttu-id="286c5-211">このアカウントは、Microsoft Application Virtualization Management Server がデータストアに接続するために使用され、ストリーミングされたアプリケーションに対するクライアント要求の処理を担当します。</span><span class="sxs-lookup"><span data-stu-id="286c5-211">This account is used by the Microsoft Application Virtualization Management Server to connect to the data store and is responsible for servicing client requests for streamed applications.</span></span> <span data-ttu-id="286c5-212">SQL Server と管理サーバーをインストールする場所に応じて、次の2つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="286c5-212">There are two options, depending on where the SQL Server and Management Server are to be installed:</span></span>

    1.  <span data-ttu-id="286c5-213">管理サーバーと SQL Server が同じコンピューターにインストールされる場合は、NT AUTHORITY\\NETWORK SERVICE のログインを追加して、SFTUser と SFTEveryone database ロールに追加します。</span><span class="sxs-lookup"><span data-stu-id="286c5-213">If Management Server and SQL Server are going to be installed on the same computer, add a login for NT AUTHORITY\\NETWORK SERVICE and add it to the SFTUser and SFTEveryone database roles.</span></span>

    2.  <span data-ttu-id="286c5-214">管理サーバーと SQL Server を異なるコンピューターにインストールする場合は、"domain\\App-V Server Name $" ("App-V Server Name $") のログインを追加して、SFTUser ロールと SFTEveryone database ロールにそのサーバーの名前が追加されるようにします。</span><span class="sxs-lookup"><span data-stu-id="286c5-214">If the Management Server and SQL Server are to be installed on different computers, add a login for “domain\\App-V Server Name$” (where “App-V Server Name” is the name of the server where the App-V Management Server will be installed) and add it to the SFTUser and SFTEveryone database roles.</span></span>

-   <span data-ttu-id="286c5-215">SQL ウィンドウで [クエリ] ウィンドウを開いて、次の SQL を実行します。</span><span class="sxs-lookup"><span data-stu-id="286c5-215">Open the query window on the SQL window and run the following SQL:</span></span>

    ``` syntax
    USE APPVIRTDB
    GRANT ALTER ON ROLE::SFTuser TO “domain\App-V Admins”
    ```

    <span data-ttu-id="286c5-216">ここで、APPVIRTDB は、前の手順で SQL Server で作成された App-v データベースの名前であり、アプリをインストールするユーザーは "domain\\App-V Admins" のメンバーである必要があります ("domain" と "App V Admins" は、自分の環境を反映するように変更されます)。</span><span class="sxs-lookup"><span data-stu-id="286c5-216">Where the APPVIRTDB is the name of the App-V Database created on the SQL Server in the previous step, and the user who is going to do the install of the App-v server needs to be a member of “domain\\App-V Admins” (where “domain” and “App-V Admins” will be changed to reflect your own environment).</span></span>

### <span data-ttu-id="286c5-217">インフラストラクチャ管理者によって実行されるタスク</span><span class="sxs-lookup"><span data-stu-id="286c5-217">Tasks to be performed by the Infrastructure administrators</span></span>

1.  <span data-ttu-id="286c5-218">"App-v Admins" グループの管理者は、App-v をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="286c5-218">Administrator in the “App-V Admins” group should install App-V.</span></span>

    <span data-ttu-id="286c5-219">SQL 管理者からの情報を使用して、前の手順で作成した SQL Server とデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="286c5-219">Use information from the SQL administrators for selecting the SQL Server and database created in the previous steps.</span></span>

2.  <span data-ttu-id="286c5-220">"App-v Admins" グループの管理者は、Application Virtualization 管理コンソールにログインし、管理コンソールから次のオブジェクトを削除します。</span><span class="sxs-lookup"><span data-stu-id="286c5-220">Administrator in the “App-V Admins” group logs in to Application Virtualization Management Console and deletes the following objects from the Management Console.</span></span>

    **<span data-ttu-id="286c5-221">Warning</span><span class="sxs-lookup"><span data-stu-id="286c5-221">Warning</span></span>**  
    <span data-ttu-id="286c5-222">これは、既存のデータベースに対してインストールを実行する場合、従来のセットアップによってデータベース内の特定のレコードに入力される必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="286c5-222">This is required as the traditional setup populates certain records in the database that are not populated if you run the install against an already existing database.</span></span> <span data-ttu-id="286c5-223">次のオブジェクトを削除します。</span><span class="sxs-lookup"><span data-stu-id="286c5-223">Delete the following objects:</span></span>

    -   <span data-ttu-id="286c5-224">[サーバーグループ] の下で、"既定のサーバーグループ" というアプリケーション仮想化管理サーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="286c5-224">Under “Server Groups,” “Default Server Group,” delete “Application Virtualization Management Server”</span></span>

    -   <span data-ttu-id="286c5-225">[サーバーグループ] の [既定のサーバーグループの削除]</span><span class="sxs-lookup"><span data-stu-id="286c5-225">Under “Server Groups,” delete “Default Server Group”</span></span>

    -   <span data-ttu-id="286c5-226">"プロバイダーポリシー" で、"既定のプロバイダー" を削除します。</span><span class="sxs-lookup"><span data-stu-id="286c5-226">Under “Provider Policies,” delete “Default Provider”</span></span>



3.  <span data-ttu-id="286c5-227">App-v admins グループの管理者は次のものを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="286c5-227">Administrator in the App-V admins group should then create:</span></span>

    -   <span data-ttu-id="286c5-228">[プロバイダーポリシー] の下で、新しいプロバイダーポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="286c5-228">Under “Provider Policies,” create a New Provider Policy</span></span>

    -   <span data-ttu-id="286c5-229">"既定のサーバーグループ" を作成する</span><span class="sxs-lookup"><span data-stu-id="286c5-229">Create a “Default Server Group”</span></span>

        **<span data-ttu-id="286c5-230">注</span><span class="sxs-lookup"><span data-stu-id="286c5-230">Note</span></span>**  
        <span data-ttu-id="286c5-231">使用しない場合でも、"既定のサーバー" グループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="286c5-231">You must create a “Default Server” group even if you will not be used.</span></span> <span data-ttu-id="286c5-232">サーバーのインストーラーでは、サーバーを追加しようとしたときに、"既定のサーバーグループ" のみが検索されます。</span><span class="sxs-lookup"><span data-stu-id="286c5-232">The server installer only looks for the "Default Server Group" when trying to add the server.</span></span>  <span data-ttu-id="286c5-233">"既定のサーバーグループ" が存在しない場合、インストールは失敗します。</span><span class="sxs-lookup"><span data-stu-id="286c5-233">If there is no "Default Server Group" then the installation will fail.</span></span> <span data-ttu-id="286c5-234">既定以外のサーバーグループを使用することを計画している場合は、その後の App-v 管理サーバーをインフラストラクチャに追加する予定がある場合は、"既定のサーバーグループ" を保持する必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="286c5-234">If you plan on using server groups other than the default that is fine, it’s just necessary to retain the "Default Server Group" if you plan on adding subsequent App-V Management Servers to your infrastructure.</span></span>



~~~
-   Assign the App-V Users Group to the New Provider Policy created above

-   Under “Server Groups,” create a New Server Group, specifying the New Provider Policy

-   Under the New Server group, create a New Application Virtualization Management Server

    **Important**  
    Do not restart the service before completing all of the above steps!



-   Administrator restarts the Application Virtualization Management Server service.
~~~

## <span data-ttu-id="286c5-235">まとめ</span><span class="sxs-lookup"><span data-stu-id="286c5-235">Conclusion</span></span>


<span data-ttu-id="286c5-236">このドキュメントに記載されている情報により、管理者は、組織内のセキュリティと管理部門に対応する展開パスを開発するために、SQL 管理者と作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="286c5-236">In conclusion, the information in this document allows an administrator to work with the SQL administrators to develop a deployment path that works for the security and administrative divisions in an organization.</span></span> <span data-ttu-id="286c5-237">このドキュメントを読み、文書化されたタスクをテストした後、管理者はこの種類の環境にアプリの app-v インフラストラクチャを実装する準備ができている必要があります。</span><span class="sxs-lookup"><span data-stu-id="286c5-237">After reading this document and testing the tasks documented, an administrator should be ready to implement their App-V infrastructure in this type of environment.</span></span>









