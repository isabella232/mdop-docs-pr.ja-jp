---
title: SQL スクリプトを使用して APP-V データベースを展開する方法
description: SQL スクリプトを使用して APP-V データベースを展開する方法
author: dansimp
ms.assetid: 1183b1bc-d4d7-4914-a049-06e82bf2d96d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4695d105c1aa6732efb6b8ed05169cf29e7f972b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814106"
---
# <span data-ttu-id="bdb14-103">SQL スクリプトを使用して APP-V データベースを展開する方法</span><span class="sxs-lookup"><span data-stu-id="bdb14-103">How to Deploy the App-V Databases by Using SQL Scripts</span></span>

<span data-ttu-id="bdb14-104">Windows インストーラーではなく SQL スクリプトを使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bdb14-104">Use the following instructions to use SQL scripts, rather than the Windows Installer, to:</span></span>

- <span data-ttu-id="bdb14-105">App-v 5.1 データベースをインストールする</span><span class="sxs-lookup"><span data-stu-id="bdb14-105">Install the App-V 5.1 databases</span></span>
- <span data-ttu-id="bdb14-106">App-v データベースを最新バージョンにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="bdb14-106">Upgrade the App-V databases to a later version</span></span>

> [!NOTE]
> <span data-ttu-id="bdb14-107">既に app-v 5.0 SP3 データベースを展開している場合、SQL スクリプトは、App-v 5.1 にアップグレードする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bdb14-107">If you have already deployed the App-V 5.0 SP3 database, the SQL scripts are not required to upgrade to App-V 5.1.</span></span>

## <span data-ttu-id="bdb14-108">SQL スクリプトを使用して app-v データベースをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="bdb14-108">How to install the App-V databases by using SQL scripts</span></span>

1. <span data-ttu-id="bdb14-109">データベーススクリプトをインストールする前に、「App-v ライセンス条項のコピー」を確認して保存します。</span><span class="sxs-lookup"><span data-stu-id="bdb14-109">Before you install the database scripts, review and keep a copy of the App-V license terms.</span></span> <span data-ttu-id="bdb14-110">データベーススクリプトを実行すると、ライセンス条項に同意したことになります。</span><span class="sxs-lookup"><span data-stu-id="bdb14-110">By running the database scripts, you are agreeing to the license terms.</span></span> <span data-ttu-id="bdb14-111">同意しない場合は、このソフトウェアを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="bdb14-111">If you do not accept them, you should not use this software.</span></span>
1. <span data-ttu-id="bdb14-112">**appv\_server\_setup.exe**を app-v リリースメディアから一時的な場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="bdb14-112">Copy the **appv\_server\_setup.exe** from the App-V release media to a temporary location.</span></span>
1. <span data-ttu-id="bdb14-113">コマンドプロンプトで**appv\_server\_setup.exe**を実行し、データベーススクリプトを抽出するための一時的な場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="bdb14-113">From a command prompt, run **appv\_server\_setup.exe** and specify a temporary location for extracting the database scripts.</span></span>

    <span data-ttu-id="bdb14-114">例: appv\_server\_setup.exe/layout ¥ &lt; _temp location path_&gt;</span><span class="sxs-lookup"><span data-stu-id="bdb14-114">Example: appv\_server\_setup.exe /layout c:\\&lt;_temporary location path_&gt;</span></span>

1. <span data-ttu-id="bdb14-115">作成した一時的な場所を参照し、抽出された [ **Databasescripts** ] フォルダーを開いて、手順について適切な Readme.txt ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="bdb14-115">Browse to the temporary location that you created, open the extracted **DatabaseScripts** folder, and review the appropriate Readme.txt file for instructions:</span></span>

    | <span data-ttu-id="bdb14-116">Database (データベース)</span><span class="sxs-lookup"><span data-stu-id="bdb14-116">Database</span></span> | <span data-ttu-id="bdb14-117">使用する Readme.txt ファイルの場所</span><span class="sxs-lookup"><span data-stu-id="bdb14-117">Location of Readme.txt file to use</span></span> |
    |--|--|
    | <span data-ttu-id="bdb14-118">管理データベース</span><span class="sxs-lookup"><span data-stu-id="bdb14-118">Management database</span></span> | <span data-ttu-id="bdb14-119">ManagementDatabase サブフォルダー</span><span class="sxs-lookup"><span data-stu-id="bdb14-119">ManagementDatabase subfolder</span></span> |
    | <span data-ttu-id="bdb14-120">レポートデータベース</span><span class="sxs-lookup"><span data-stu-id="bdb14-120">Reporting database</span></span> | <span data-ttu-id="bdb14-121">ReportingDatabase サブフォルダー</span><span class="sxs-lookup"><span data-stu-id="bdb14-121">ReportingDatabase subfolder</span></span> |

> [!CAUTION]
> <span data-ttu-id="bdb14-122">ManagementDatabase サブフォルダーの readme.txt ファイルが最新の状態ではありません。</span><span class="sxs-lookup"><span data-stu-id="bdb14-122">The readme.txt file in the ManagementDatabase subfolder is out of date.</span></span> <span data-ttu-id="bdb14-123">以下の更新された readme ファイルの情報は最新のものであり、「 **Databasescripts** 」フォルダーに記載されている readme 情報を置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdb14-123">The information in the updated readme files below is the most current and should supersede the readme information provided in the **DatabaseScripts** folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bdb14-124">InsertVersionInfo スクリプトは、アプリ-V 5.0 SP3 より後のバージョンの App-v 管理データベースでは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bdb14-124">The InsertVersionInfo.sql script is not required for versions of the App-V management database later than App-V 5.0 SP3.</span></span>

<span data-ttu-id="bdb14-125">アクセス許可の sql スクリプトは、[サポート技術情報の記事 3031340](https://support.microsoft.com/kb/3031340)の**手順 2**に従って更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bdb14-125">The Permissions.sql script should be updated according to **Step 2** in [KB article 3031340](https://support.microsoft.com/kb/3031340).</span></span> <span data-ttu-id="bdb14-126">App-v 5.0 SP3 より後のバージョンの App-v では、**手順 1**は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bdb14-126">**Step 1** is not required for versions of App-V later than App-V 5.0 SP3.</span></span>

## <span data-ttu-id="bdb14-127">更新された管理データベース README ファイルのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="bdb14-127">Updated management database README file content</span></span>

```plaintext
******************************************************************
Before you install and use the Application Virtualization Database Scripts you must:
1.Review the Microsoft Application Virtualization Server 5.0 license terms.
2.Print and retain a copy of the license terms for your records.
By running the Microsoft Application Virtualization Database Scripts you agree to such license terms.  If you do not accept them, do not use the software.
******************************************************************


Steps to install "AppVManagement" schema in SQL SERVER.


## PREREQUISITES:

 1. Review the installation package.  The following files MUST exist:

    SQL files
    ---------
    Database.sql
    CreateTables.sql
    CreateStoredProcs.sql
    UpdateTables.sql
    Permissions.sql

 2. Ensure the target SQL Server instance and SQL Server Agent service are running.

 3. If you are not running the scripts directly on the server, ensure the
    necessary SQL Server client software is installed and available from
    the specified location.  Specifically, the "osql" command must
##     be supported for these scripts to run.



## PREPARATION:

 1. Review the database.sql file and modify as necessary.  Although the
    defaults are likely sufficient, it is suggested that the following
    settings be reviewed:

    DATABASE - ensure name is satisfactory - default is "AppVManagement".

 2. Review the Permissions.sql file and provide all the necessary account information
    for setting up read and write access on the database. Note: Default settings
##     in the file will not work.



## INSTALLATION:

 1. Run the database.sql against the "master" database.  Your user
    credential must have the ability to create databases.
    This script will create the database.

 2. Run the following scripts against the "AppVManagement" database using the
    same account as above in order.

    CreateTables.sql
    CreateStoredProcs.sql
    UpdateTables.sql
##     Permissions.sql

```

## <span data-ttu-id="bdb14-128">レポートデータベースの README ファイルの内容が更新されました</span><span class="sxs-lookup"><span data-stu-id="bdb14-128">Updated reporting database README file content</span></span>

```plaintext
******************************************************************
Before you install and use the Application Virtualization Database Scripts you must:
1.Review the Microsoft Application Virtualization Server 5.0 license terms.
2.Print and retain a copy of the license terms for your records.
By running the Microsoft Application Virtualization Database Scripts you agree to such license terms.  If you do not accept them, do not use the software.
******************************************************************

Steps to install "AppVReporting" schema in SQL SERVER.


## PREREQUISITES:

 1. Review the installation package.  The following files MUST exist:

    SQL files
    ---------
    Database.sql
    UpgradeDatabase.sql
    CreateTables.sql
    CreateReportingStoredProcs.sql
    CreateStoredProcs.sql
    CreateViews.sql
    InsertVersionInfo.sql
    Permissions.sql
    ScheduleReportingJob.sql

 2. Ensure the target SQL Server instance and SQL Server Agent service are running.

 3. If you are not running the scripts directly on the server, ensure the 
    necessary SQL Server client software is installed and executable from
    the location you have chosen.  Specifically, the "osql" command must
##     be supported for these scripts to run.



## PREPARATION:

 1. Review the database.sql file and modify as necessary.  Although the
    defaults are likely sufficient, it is suggested that the following
    settings be reviewed:

    DATABASE - ensure name is satisfactory - default is "AppVReporting".

 2. Review the Permissions.sql file and provide all the necessary account information
    for setting up read and write access on the database. Note: Default settings
    in the file will not work.

 3. Review the ScheduleReportingJob.sql file and make sure that the stored proc schedule
    time is acceptable. The default stored proc schedule time is at 12.01 AM (line 84). 
    If this time is not suitable, you can change this to a more suitable time. The time is
##     in the format HHMMSS.



## INSTALLATION:

 1. Run the database.sql against the "master" database.  Your user
    credential must have the ability to create databases.
    This script will create the database.

 2. If upgrading the database, run UpgradeDatabase.sql This will upgrade database schema.

 2. Run the following scripts against the "AppVReporting" database using the
    same account as above in order.

    CreateTables.sql
    CreateReportingStoredProcs.sql
    CreateStoredProcs.sql
    CreateViews.sql
    InsertVersionInfo.sql
    Permissions.sql
##     ScheduleReportingJob.sql

```

**<span data-ttu-id="bdb14-129">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="bdb14-129">Got an App-V issue?</span></span>** <span data-ttu-id="bdb14-130">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="bdb14-130">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="bdb14-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bdb14-131">Related topics</span></span>

[<span data-ttu-id="bdb14-132">App-V 5.1 Server の展開</span><span class="sxs-lookup"><span data-stu-id="bdb14-132">Deploying the App-V 5.1 Server</span></span>](deploying-the-app-v-51-server.md)

[<span data-ttu-id="bdb14-133">App-V 5.1 Server を展開する方法</span><span class="sxs-lookup"><span data-stu-id="bdb14-133">How to Deploy the App-V 5.1 Server</span></span>](how-to-deploy-the-app-v-51-server.md)
