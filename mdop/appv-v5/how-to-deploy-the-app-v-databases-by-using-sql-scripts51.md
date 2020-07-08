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
# SQL スクリプトを使用して APP-V データベースを展開する方法

Windows インストーラーではなく SQL スクリプトを使用するには、次の手順を実行します。

- App-v 5.1 データベースをインストールする
- App-v データベースを最新バージョンにアップグレードする

> [!NOTE]
> 既に app-v 5.0 SP3 データベースを展開している場合、SQL スクリプトは、App-v 5.1 にアップグレードする必要はありません。

## SQL スクリプトを使用して app-v データベースをインストールする方法

1. データベーススクリプトをインストールする前に、「App-v ライセンス条項のコピー」を確認して保存します。 データベーススクリプトを実行すると、ライセンス条項に同意したことになります。 同意しない場合は、このソフトウェアを使用しないでください。
1. **appv\_server\_setup.exe**を app-v リリースメディアから一時的な場所にコピーします。
1. コマンドプロンプトで**appv\_server\_setup.exe**を実行し、データベーススクリプトを抽出するための一時的な場所を指定します。

    例: appv\_server\_setup.exe/layout ¥ &lt; _temp location path_&gt;

1. 作成した一時的な場所を参照し、抽出された [ **Databasescripts** ] フォルダーを開いて、手順について適切な Readme.txt ファイルを確認します。

    | Database (データベース) | 使用する Readme.txt ファイルの場所 |
    |--|--|
    | 管理データベース | ManagementDatabase サブフォルダー |
    | レポートデータベース | ReportingDatabase サブフォルダー |

> [!CAUTION]
> ManagementDatabase サブフォルダーの readme.txt ファイルが最新の状態ではありません。 以下の更新された readme ファイルの情報は最新のものであり、「 **Databasescripts** 」フォルダーに記載されている readme 情報を置き換える必要があります。

> [!IMPORTANT]
> InsertVersionInfo スクリプトは、アプリ-V 5.0 SP3 より後のバージョンの App-v 管理データベースでは必要ありません。

アクセス許可の sql スクリプトは、[サポート技術情報の記事 3031340](https://support.microsoft.com/kb/3031340)の**手順 2**に従って更新する必要があります。 App-v 5.0 SP3 より後のバージョンの App-v では、**手順 1**は必要ありません。

## 更新された管理データベース README ファイルのコンテンツ

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

## レポートデータベースの README ファイルの内容が更新されました

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

**App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック

[App-V 5.1 Server の展開](deploying-the-app-v-51-server.md)

[App-V 5.1 Server を展開する方法](how-to-deploy-the-app-v-51-server.md)
