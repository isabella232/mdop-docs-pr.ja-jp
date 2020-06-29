---
title: スクリプトを使用して App-V 5.1 Server を展開する方法
description: スクリプトを使用して App-V 5.1 Server を展開する方法
author: dansimp
ms.assetid: 15c33d7b-9b61-4dbc-8674-399bb33e5f7e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 03/20/2020
ms.openlocfilehash: 579ca685f677aaaa4f5ebb6ac8d2969fdcbe2cd2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814130"
---
# スクリプトを使用して App-V 5.1 Server を展開する方法

コマンドラインを正常に実行するために**appv\_server\_setup.exe** Server のセットアップを完了するには、複数のパラメーターを指定して結合する必要があります。

## スクリプトを使用して App-v 5.1 サーバーをインストールする

- コマンドラインを使用して App-v 5.1 サーバーをインストールする方法については、次の情報を参照してください。

    > [!NOTE]
    > 次の表の情報は、コマンドラインを使用して次のコマンドを入力することで、コマンドラインを使用してアクセスすることもできます。 **appv\_server\_setup.exe/?**

### 管理サーバーと管理データベースをローカルコンピューターにインストールする

次のパラメーターは、Microsoft SQL Server の default インスタンスと custom インスタンスの両方で有効です。

- /MANAGEMENT_SERVER
- /MANAGEMENT_ADMINACCOUNT
- /MANAGEMENT_WEBSITE_NAME
- /MANAGEMENT_WEBSITE_PORT
- /DB_PREDEPLOY_MANAGEMENT
- /MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT
- /MANAGEMENT_DB_NAME

**例: Microsoft SQL Server のカスタムインスタンスの使用**

```dos
appv_server_setup.exe /QUIET /MANAGEMENT_SERVER /MANAGEMENT_ADMINACCOUNT="Domain\AdminGroup" /MANAGEMENT_WEBSITE_NAME="Microsoft AppV Management Service" /MANAGEMENT_WEBSITE_PORT="8080" /DB_PREDEPLOY_MANAGEMENT /MANAGEMENT_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /MANAGEMENT_DB_NAME="AppVManagement"
```

### ローカルコンピューター上の既存の管理データベースを使用して、管理サーバーをインストールする

Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します (*斜体*のカスタムインスタンスとの相違)。

- /MANAGEMENT_SERVER
- /MANAGEMENT_ADMINACCOUNT
- /MANAGEMENT_WEBSITE_NAME
- /MANAGEMENT_WEBSITE_PORT
- /EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL
- */EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT*
- /EXISTING_MANAGEMENT_DB_NAME

Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します (*斜体*の既定のインスタンスとの相違)。

- /MANAGEMENT_SERVER
- /MANAGEMENT_ADMINACCOUNT
- /MANAGEMENT_WEBSITE_NAME
- /MANAGEMENT_WEBSITE_PORT
- /EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL
- */EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE*
- /EXISTING_MANAGEMENT_DB_NAME

**例: Microsoft SQL Server のカスタムインスタンスの使用**

```dos
appv_server_setup.exe /QUIET /MANAGEMENT_SERVER /MANAGEMENT_ADMINACCOUNT="Domain\AdminGroup" /MANAGEMENT_WEBSITE_NAME="Microsoft AppV Management Service" /MANAGEMENT_WEBSITE_PORT="8080" /EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL /EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE ="SqlInstanceName" /EXISTING_MANAGEMENT_DB_NAME ="AppVManagement"
```

### リモートコンピューター上の既存の管理データベースを使用して、管理サーバーをインストールする

Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します (*斜体*のカスタムインスタンスとの相違)。

- /MANAGEMENT_SERVER
- /MANAGEMENT_ADMINACCOUNT
- /MANAGEMENT_WEBSITE_NAME
- /MANAGEMENT_WEBSITE_PORT
- /EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME
- */EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT*
- /EXISTING_MANAGEMENT_DB_NAME

Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します (*斜体*の既定のインスタンスとの相違)。

- /MANAGEMENT_SERVER
- /MANAGEMENT_ADMINACCOUNT
- /MANAGEMENT_WEBSITE_NAME
- /MANAGEMENT_WEBSITE_PORT
- /EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME
- */EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE*
- /EXISTING_MANAGEMENT_DB_NAME

**例: Microsoft SQL Server のカスタムインスタンスの使用:**

```dos
appv_server_setup.exe /QUIET /MANAGEMENT_SERVER /MANAGEMENT_ADMINACCOUNT="Domain\AdminGroup" /MANAGEMENT_WEBSITE_NAME="Microsoft AppV Management Service" /MANAGEMENT_WEBSITE_PORT="8080" /EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME="SqlServermachine.domainName" /EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE ="SqlInstanceName" /EXISTING_MANAGEMENT_DB_NAME ="AppVManagement"
```

### 管理データベースと管理サーバーを同じコンピューターにインストールする

Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します (*斜体*のカスタムインスタンスとの相違)。

- /DB_PREDEPLOY_MANAGEMENT
- */MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT*
- /MANAGEMENT_DB_NAME
- /MANAGEMENT_SERVER_MACHINE_USE_LOCAL
- /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT

Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します (*斜体*の既定のインスタンスとの相違)。

- /DB_PREDEPLOY_MANAGEMENT
- */MANAGEMENT_DB_CUSTOM_SQLINSTANCE*
- /MANAGEMENT_DB_NAME
- /MANAGEMENT_SERVER_MACHINE_USE_LOCAL
- /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT

**例: Microsoft SQL Server のカスタムインスタンスの使用**

```dos
appv_server_setup.exe /QUIET /DB_PREDEPLOY_MANAGEMENT /MANAGEMENT_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /MANAGEMENT_DB_NAME="AppVManagement" /MANAGEMENT_SERVER_MACHINE_USE_LOCAL /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### 管理データベースを管理サーバーとは異なるコンピューターにインストールする

Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します (*斜体*のカスタムインスタンスとの相違)。

- /DB_PREDEPLOY_MANAGEMENT
- */MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT*
- /MANAGEMENT_DB_NAME
- /MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT
- /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT

Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します (*斜体*の既定のインスタンスとの相違)。

- /DB_PREDEPLOY_MANAGEMENT
- */MANAGEMENT_DB_CUSTOM_SQLINSTANCE*
- /MANAGEMENT_DB_NAME
- /MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT
- /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT

**例: Microsoft SQL Server のカスタムインスタンスの使用**

```dos
appv_server_setup.exe /QUIET /DB_PREDEPLOY_MANAGEMENT /MANAGEMENT_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /MANAGEMENT_DB_NAME="AppVManagement" /MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT="Domain\MachineAccount" /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### 発行サーバーをインストールする

Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。

- /PUBLISHING_SERVER
- /PUBLISHING_MGT_SERVER
- /PUBLISHING_WEBSITE_NAME
- /PUBLISHING_WEBSITE_PORT

**例: Microsoft SQL Server のカスタムインスタンスの使用:**

```dos
appv_server_setup.exe /QUIET /PUBLISHING_SERVER /PUBLISHING_MGT_SERVER="http://ManagementServerName:ManagementPort" /PUBLISHING_WEBSITE_NAME="Microsoft AppV Publishing Service" /PUBLISHING_WEBSITE_PORT="8081"
```

### ローカルコンピューターにレポートサーバーとレポートデータベースをインストールする

Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します (*斜体*のカスタムインスタンスとの相違)。

- /レポート _SERVER
- /レポート _WEBSITE_NAME
- /レポート _WEBSITE_PORT
- /DB_PREDEPLOY_REPORTING
- */レポート _DB_SQLINSTANCE_USE_DEFAULT*
- /レポート _DB_NAME

Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します (*斜体*の既定のインスタンスとの相違)。

- /レポート _SERVER
- */レポート _ADMINACCOUNT*
- /レポート _WEBSITE_NAME
- /レポート _WEBSITE_PORT
- /DB_PREDEPLOY_REPORTING
- */レポート _DB_CUSTOM_SQLINSTANCE*
- /レポート _DB_NAME

**例: Microsoft SQL Server のカスタムインスタンスの使用:**

```dos
appv_server_setup.exe /QUIET /REPORTING_SERVER /REPORTING_WEBSITE_NAME="Microsoft AppV Reporting Service" /REPORTING_WEBSITE_PORT="8082" /DB_PREDEPLOY_REPORTING /REPORTING_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /REPORTING_DB_NAME="AppVReporting"
```

### レポートサーバーをインストールし、ローカルコンピューター上に既存のレポートデータベースを使用する

Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します (*斜体*のカスタムインスタンスとの相違)。

- /レポート _SERVER
- /レポート _WEBSITE_NAME
- /レポート _WEBSITE_PORT
- /EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL
- */EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT*
- /EXISTING_REPORTING _DB_NAME

Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します (*斜体*の既定のインスタンスとの相違)。

- /レポート _SERVER
- */レポート _ADMINACCOUNT*
- /レポート _WEBSITE_NAME
- /レポート _WEBSITE_PORT
- /EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL
- */EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE*
- /EXISTING_REPORTING _DB_NAME

**例: Microsoft SQL Server のカスタムインスタンスの使用:**

```dos
appv_server_setup.exe /QUIET /REPORTING_SERVER /REPORTING_WEBSITE_NAME="Microsoft AppV Reporting Service" /REPORTING_WEBSITE_PORT="8082" /EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL /EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /EXITING_REPORTING_DB_NAME="AppVReporting"
```

### リモートコンピューター上の既存のレポートデータベースを使用して、レポートサーバーをインストールする

Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します (*斜体*のカスタムインスタンスとの相違)。

- /レポート _SERVER
- /レポート _WEBSITE_NAME
- /レポート _WEBSITE_PORT
- /EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME
- */EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT*
- /EXISTING_REPORTING _DB_NAME

Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します (*斜体*の既定のインスタンスとの相違)。

- /レポート _SERVER
- */レポート _ADMINACCOUNT*
- /レポート _WEBSITE_NAME
- /レポート _WEBSITE_PORT
- /EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME
- */EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE*
- /EXISTING_REPORTING _DB_NAME

**例: Microsoft SQL Server のカスタムインスタンスの使用:**

```dos
appv_server_setup.exe /QUIET /REPORTING_SERVER /REPORTING_WEBSITE_NAME="Microsoft AppV Reporting Service" /REPORTING_WEBSITE_PORT="8082" /EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME="SqlServerMachine.DomainName" /EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /EXITING_REPORTING_DB_NAME="AppVReporting"
```

### レポートサーバーと同じコンピューターにレポートデータベースをインストールする

Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します (*斜体*のカスタムインスタンスとの相違)。

- /DB_PREDEPLOY_REPORTING
- */レポート _DB_SQLINSTANCE_USE_DEFAULT*
- /レポート _DB_NAME
- /REPORTING_SERVER_MACHINE_USE_LOCAL
- /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT

Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します (*斜体*の既定のインスタンスとの相違)。

- /DB_PREDEPLOY_REPORTING
- */レポート _DB_CUSTOM_SQLINSTANCE*
- /レポート _DB_NAME
- /REPORTING_SERVER_MACHINE_USE_LOCAL
- /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT

**例: Microsoft SQL Server のカスタムインスタンスの使用:**

```dos
appv_server_setup.exe /QUIET /DB_PREDEPLOY_REPORTING /REPORTING_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /REPORTING_DB_NAME="AppVReporting" /REPORTING_SERVER_MACHINE_USE_LOCAL /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### レポートデータベースをレポートサーバーとは異なるコンピューターにインストールする

Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します (*斜体*のカスタムインスタンスとの相違)。

- /DB_PREDEPLOY_REPORTING
- /レポート _DB_SQLINSTANCE_USE_DEFAULT
- /レポート _DB_NAME
- /REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT
- /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT

Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します (*斜体*の既定のインスタンスとの相違)。

- /DB_PREDEPLOY_REPORTING
- /レポート _DB_CUSTOM_SQLINSTANCE
- /レポート _DB_NAME
- /REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT
- /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT

**例: Microsoft SQL Server のカスタムインスタンスの使用:**

```dos
 appv_server_setup.exe /QUIET /DB_PREDEPLOY_REPORTING /REPORTING_DB_CUSTOM_SQLINSTANCE="SqlInstanceName" /REPORTING_DB_NAME="AppVReporting" /REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT="Domain\MachineAccount" /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT="Domain\InstallAdminAccount"
```

### パラメーターの定義

#### 一般的なパラメーター

| パラメーター | 情報 |
|--|--|
| /QUIET | サイレントインストールを指定します。 |
| /UNINSTALL | アンインストールを指定します。 |
| /レイアウト | レイアウトアクションを指定します。 これにより、実際には製品をインストールせずに、MSIs ファイルとスクリプトファイルがフォルダーに抽出されます。 値は予期されません。 |
| /Layoutdir | レイアウトディレクトリを指定します。 文字列を受け取ります。 使用例: **/layoutdir = "C:\\Application Virtualization Server"** |
| /INSTALLDIR | インストールディレクトリを指定します。 文字列を受け取ります。 使用例: **/INSTALLDIR = "c/ファイル \\ アプリケーション Virtualization\\Server"** |
| /Muoptin | Microsoft Update を有効にします。 値は予期されません。 |
| /ACCEPTEULA | ライセンス契約を承諾します。 これは、無人インストールの場合に必要になります。 使用例: **/ACCEPTEULA**または **/ACCEPTEULA = 1** |

#### 管理サーバーのインストールパラメーター

|パラメーター |情報 |
|--|--|
| /MANAGEMENT_SERVER | 管理サーバーをインストールすることを指定します。 値は期待されません。 |
| /MANAGEMENT_ADMINACCOUNT | 管理サーバーへの管理者アクセスが許可されるアカウントを指定します。 これは、ユーザーアカウントまたはグループのいずれかになります。 使用例: **/MANAGEMENT_ADMINACCOUNT = "mydomain\\admin"** **/MANAGEMENT_SERVER**が指定されていない場合は、無視されます。 |
| /MANAGEMENT_WEBSITE_NAME | 管理サービス用に作成される web サイトの名前を指定します。 使用例: **/MANAGEMENT_WEBSITE_NAME = "Microsoft App-V MANAGEMENT Service"** |
| MANAGEMENT_WEBSITE_PORT | 管理サービスが使用するポート番号を指定します。 使用例: **/MANAGEMENT_WEBSITE_PORT = 82** |

#### 管理サーバーデータベースのパラメーター

| パラメーター | 情報 |
|--|--|
| /DB_PREDEPLOY_MANAGEMENT | 管理データベースをインストールすることを指定します。 このインストールを完了するには、十分なデータベース権限が必要です。 値は予期されません。 |
| /MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT | 既定の SQL インスタンスを使用する必要があることを示します。 値は予期されません。 |
| /MANAGEMENT_DB_ CUSTOM_SQLINSTANCE | 新しいデータベースの作成に使用するカスタム SQL インスタンスの名前を指定します。 使用例: **/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER"**。 **/DB_PREDEPLOY_MANAGEMENT**が指定されていない場合は、無視されます。 |
| /MANAGEMENT_DB_NAME | 作成する新しい管理データベースの名前を指定します。 使用例: **/MANAGEMENT_DB_NAME = "AppVMgmtDB"** **/DB_PREDEPLOY_MANAGEMENT**が指定されていない場合は、無視されます。 |
| /MANAGEMENT_SERVER_MACHINE_USE_LOCAL | データベースにアクセスする管理サーバーがローカルサーバーにインストールされているかどうかを示します。 スイッチパラメーター。値は予期されません。 |
| /MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT | 管理サーバーをインストールするリモートコンピューターのコンピューターアカウントを指定します。 使用例: **/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT = "domain\\computername ドメイン \"** |
| /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT | 管理サーバーをインストールするために使用される管理者アカウントを示します。 使用例: **/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT = "domain\\alias"** |

#### 発行サーバーをインストールするためのパラメーター

| パラメーター | 情報 |
|--|--|
| /PUBLISHING_SERVER | 発行サーバーをインストールすることを指定します。 値は予期されません。 |
| /PUBLISHING_MGT_SERVER | 発行サーバーが接続する管理サービスの URL を指定します。 使用例: **http:// &lt; management server name &gt; : &lt; 管理サーバーのポート &gt; 番号**。 **/PUBLISHING_SERVER**が使用されていない場合、このパラメーターは無視されます。 |
| /PUBLISHING_WEBSITE_NAME | 発行サービス用に作成される web サイトの名前を指定します。 使用例: **/PUBLISHING_WEBSITE_NAME = "Microsoft App-V PUBLISHING Service"** |
| /PUBLISHING_WEBSITE_PORT | 発行サービスによって使用されるポート番号を指定します。 使用例: **/PUBLISHING_WEBSITE_PORT = 83** |

#### レポートサーバーのパラメーター

| パラメーター | 情報 |
|--|--|
| /REPORTING_SERVER | レポートサーバーをインストールすることを指定します。 値は予期されません。 |
| /REPORTING_WEBSITE_NAME | レポートサービス用に作成される web サイトの名前を指定します。 使用例: **/REPORTING_WEBSITE_NAME = "Microsoft App-V ReportingService"** |
| /REPORTING_WEBSITE_PORT | レポートサービスが使用するポート番号を指定します。 使用例: **/REPORTING_WEBSITE_PORT = 82** |

#### 既存のレポートサーバーデータベースを使用するためのパラメーター

| パラメーター | 情報 |
|--|--|
| /EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL | Microsoft SQL Server がローカルサーバーにインストールされていることを示します。 スイッチパラメーター。値は予期されません。 |
| /EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME | SQL Server がインストールされているリモートコンピューターの名前を指定します。 文字列を受け取ります。 使用例: **/EXISTING_REPORTING_DB_ REMOTE_SQL_SERVER_NAME = "mycomputer1"** |
| レポート _DB_SQLINSTANCE_USE_DEFAULT の EXISTING_ | 既定の SQL インスタンスが使用されることを示します。 スイッチパラメーター。値は予期されません。 |
| /EXISTING_ REPORTING_DB_CUSTOM_SQLINSTANCE | 使用するカスタム SQL インスタンスの名前を指定します。 文字列を受け取ります。 使用例: **/EXISTING_REPORTING_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER"** |
| レポート _DB_NAME の EXISTING_ | 使用する既存のレポートデータベースの名前を指定します。 文字列を受け取ります。 使用例: **/EXISTING_REPORTING_DB_NAME = "AppVReporting"** |

#### レポートサーバーデータベースをインストールするためのパラメーター

| パラメーター | 情報 |
|--|--|
| /DB_PREDEPLOY_REPORTING | レポートデータベースがインストールされることを指定します。 このインストールには、DBA 権限が必要です。 値は予期されません。 |
| /REPORTING_DB_SQLINSTANCE_USE_DEFAULT | 使用するカスタム SQL インスタンスの名前を指定します。 文字列を受け取ります。 使用例: **/REPORTING_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER"** |
| /REPORTING_DB_NAME | 作成する新しいレポートデータベースの名前を指定します。 文字列を受け取ります。 使用例: **/REPORTING_DB_NAME = "AppVMgmtDB"** |
| /REPORTING_SERVER_MACHINE_USE_LOCAL | データベースにアクセスするレポートサーバーがローカルサーバーにインストールされていることを示します。 スイッチパラメーター。値は予期されません。 |
| /REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT | レポートサーバーをインストールするリモートコンピューターのコンピューターアカウントを指定します。 文字列を受け取ります。 使用例: **/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT = "domain\computername"** |
| /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT | App-v レポートサーバーをインストールするために使用される管理者アカウントを示します。 文字列を受け取ります。 使用例: **/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = "domain\\alias"** |

#### 既存の管理サーバーデータベースを使用するためのパラメーター

| パラメーター | 情報 |
|--|--|
| /EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL | SQL Server がローカルサーバーにインストールされていることを示します。 スイッチパラメーター。値は予期されません。**/DB_PREDEPLOY_MANAGEMENT**が指定されている場合、これは無視されます。 |
| /EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME | SQL Server がインストールされているリモートコンピューターの名前を指定します。 文字列を受け取ります。 使用例: **/EXISTING_MANAGEMENT_DB_ REMOTE_SQL_SERVER_NAME = "mycomputer1"** |
| /EXISTING_ MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT | 既定の SQL インスタンスが使用されることを示します。 スイッチパラメーター。値は予期されません。 **/DB_PREDEPLOY_MANAGEMENT**が指定されている場合、これは無視されます。 |
| /EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE | 使用されるカスタム SQL インスタンスの名前を指定します。 使用例 **/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE = "AppVManagement"**。 **/DB_PREDEPLOY_MANAGEMENT**が指定されている場合、これは無視されます。 |
| /EXISTING_MANAGEMENT_DB_NAME | 使用する既存の管理データベースの名前を指定します。 使用例: **/EXISTING_MANAGEMENT_DB_NAME = "AppVMgmtDB"** **/DB_PREDEPLOY_MANAGEMENT**が指定されている場合、これは無視されます。 |

App-v の問題が発生しましたか? App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック

[App-V 5.1 Server の展開](deploying-the-app-v-51-server.md)
