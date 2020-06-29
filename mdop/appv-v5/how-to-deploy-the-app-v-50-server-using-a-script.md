---
title: スクリプトを使用して APP-V 5.0 Server を展開する方法
description: スクリプトを使用して APP-V 5.0 Server を展開する方法
author: dansimp
ms.assetid: b91a35c8-df9e-4065-9187-abafbe565b84
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/15/2018
ms.openlocfilehash: aeb16d166fe7b1c4bb418c212024c49f6b151b94
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814170"
---
# スクリプトを使用して APP-V 5.0 Server を展開する方法


コマンドラインを正常に実行するために**appv\_server\_setup.exe** Server のセットアップを完了するには、複数のパラメーターを指定して結合する必要があります。

コマンドラインを使用した App-v 5.0 サーバーのインストールの詳細については、次の表を参照してください。

>[!NOTE]
> 次の表の情報は、次のコマンドを入力してコマンドラインを使用してアクセスすることもできます。
>```
> appv\_server\_setup.exe /?
>```

## 一般的なパラメーターと例

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>管理サーバーと管理データベースをローカルコンピューターにインストールします。</p></td>
    <td align="left"><p>Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</p>
    <ul>
    <li><p>/MANAGEMENT_SERVER</p></li>
    <li><p>/MANAGEMENT_ADMINACCOUNT</p></li>
    <li><p>/MANAGEMENT_WEBSITE_NAME</p></li>
    <li><p>/MANAGEMENT_WEBSITE_PORT</p></li>
    <li><p>/DB_PREDEPLOY_MANAGEMENT</p></li>
    <li><p>/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</p></li>
    <li><p>/MANAGEMENT_DB_NAME</p></li>
    </ul>
    <p>Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します。</p>
    <ul>
    <li><p>/MANAGEMENT_SERVER</p></li>
    <li><p>/MANAGEMENT_ADMINACCOUNT</p></li>
    <li><p>/MANAGEMENT_WEBSITE_NAME</p></li>
    <li><p>/MANAGEMENT_WEBSITE_PORT</p></li>
    <li><p>/DB_PREDEPLOY_MANAGEMENT</p></li>
    <li><p>/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</p></li>
    <li><p>/MANAGEMENT_DB_NAME</p></li>
    </ul>
    <p>Microsoft SQL Server のカスタムインスタンスの使用例:</p>
    <p>/appv_server_setup.exe/QUIET</p>
    <p>/MANAGEMENT_SERVER</p>
    <p>/MANAGEMENT_ADMINACCOUNT = "Domain\AdminGroup"</p>
    <p>/MANAGEMENT_WEBSITE_NAME = "Microsoft AppV 管理サービス"</p>
    <p>/MANAGEMENT_WEBSITE_PORT = "8080"</p>
    <p>/DB_PREDEPLOY_MANAGEMENT</p>
    <p>/MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</p>
    <p>/MANAGEMENT_DB_NAME = "AppVManagement"</p></td>
    </tr>
    </tbody>
    </table>
     
<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>ローカルコンピューター上の既存の管理データベースを使用して、管理サーバーをインストールします。</p></td>
    <td align="left"><p>Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</p>
    <ul>
    <li><p>/MANAGEMENT_SERVER</p></li>
    <li><p>/MANAGEMENT_ADMINACCOUNT</p></li>
    <li><p>/MANAGEMENT_WEBSITE_NAME</p></li>
    <li><p>/MANAGEMENT_WEBSITE_PORT</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_NAME</p></li>
    </ul>
    <p>Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します。</p>
    <ul>
    <li><p>/MANAGEMENT_SERVER</p></li>
    <li><p>/MANAGEMENT_ADMINACCOUNT</p></li>
    <li><p>/MANAGEMENT_WEBSITE_NAME</p></li>
    <li><p>/MANAGEMENT_WEBSITE_PORT</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_NAME</p></li>
    </ul>
    <p>Microsoft SQL Server のカスタムインスタンスの使用例:</p>
    <p>/appv_server_setup.exe/QUIET</p>
    <p>/MANAGEMENT_SERVER</p>
    <p>/MANAGEMENT_ADMINACCOUNT = "Domain\AdminGroup"</p>
    <p>/MANAGEMENT_WEBSITE_NAME = "Microsoft AppV 管理サービス"</p>
    <p>/MANAGEMENT_WEBSITE_PORT = "8080"</p>
    <p>/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</p>
    <p>/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</p>
    <p>/EXISTING_MANAGEMENT_DB_NAME = "AppVManagement"</p></td>
    </tr>
    </tbody>
    </table>  

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>リモートコンピューター上の既存の管理データベースを使用して、管理サーバーをインストールします。</p></td>
    <td align="left"><p>Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</p>
    <ul>
    <li><p>/MANAGEMENT_SERVER</p></li>
    <li><p>/MANAGEMENT_ADMINACCOUNT</p></li>
    <li><p>/MANAGEMENT_WEBSITE_NAME</p></li>
    <li><p>/MANAGEMENT_WEBSITE_PORT</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_NAME</p></li>
    </ul>
    <p>Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します。</p>
    <ul>
    <li><p>/MANAGEMENT_SERVER</p></li>
    <li><p>/MANAGEMENT_ADMINACCOUNT</p></li>
    <li><p>/MANAGEMENT_WEBSITE_NAME</p></li>
    <li><p>/MANAGEMENT_WEBSITE_PORT</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE</p></li>
    <li><p>/EXISTING_MANAGEMENT_DB_NAME</p></li>
    </ul>
    <p>Microsoft SQL Server のカスタムインスタンスの使用例:</p>
    <p>/appv_server_setup.exe/QUIET</p>
    <p>/MANAGEMENT_SERVER</p>
    <p>/MANAGEMENT_ADMINACCOUNT = "Domain\AdminGroup"</p>
    <p>/MANAGEMENT_WEBSITE_NAME = "Microsoft AppV 管理サービス"</p>
    <p>/MANAGEMENT_WEBSITE_PORT = "8080"</p>
    <p>/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME = "SqlServermachine"</p>
    <p>/EXISTING_MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</p>
    <p>/EXISTING_MANAGEMENT_DB_NAME = "AppVManagement"</p></td>
    </tr>
    </tbody>
    </table>
    
<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>管理データベースと管理サーバーを同じコンピューターにインストールします。</p></td>
    <td align="left"><p>Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</p>
    <ul>
    <li><p>/DB_PREDEPLOY_MANAGEMENT</p></li>
    <li><p>/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</p></li>
    <li><p>/MANAGEMENT_DB_NAME</p></li>
    <li><p>/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</p></li>
    <li><p>/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</p></li>
    </ul>
    <p>Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します。</p>
    <ul>
    <li><p>/DB_PREDEPLOY_MANAGEMENT</p></li>
    <li><p>/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</p></li>
    <li><p>/MANAGEMENT_DB_NAME</p></li>
    <li><p>/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</p></li>
    <li><p>/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</p></li>
    </ul>
    <p>Microsoft SQL Server のカスタムインスタンスの使用例:</p>
    <p>/appv_server_setup.exe/QUIET</p>
    <p>/DB_PREDEPLOY_MANAGEMENT</p>
    <p>/MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</p>
    <p>/MANAGEMENT_DB_NAME = "AppVManagement"</p>
    <p>/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</p>
    <p>/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT = "\" \ installadminadminaccount "</p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>管理データベースを管理サーバーとは異なるコンピューターにインストールするには、以下のようにします。</p></td>
    <td align="left"><p>Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</p>
    <ul>
    <li><p>/DB_PREDEPLOY_MANAGEMENT</p></li>
    <li><p>/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</p></li>
    <li><p>/MANAGEMENT_DB_NAME</p></li>
    <li><p>/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</p></li>
    <li><p>/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</p></li>
    </ul>
    <p>Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します。</p>
    <ul>
    <li><p>/DB_PREDEPLOY_MANAGEMENT</p></li>
    <li><p>/MANAGEMENT_DB_CUSTOM_SQLINSTANCE</p></li>
    <li><p>/MANAGEMENT_DB_NAME</p></li>
    <li><p>/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</p></li>
    <li><p>/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</p></li>
    </ul>
    <p>Microsoft SQL Server のカスタムインスタンスの使用例:</p>
    <p>/appv_server_setup.exe/QUIET</p>
    <p>/DB_PREDEPLOY_MANAGEMENT</p>
    <p>/MANAGEMENT_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</p>
    <p>/MANAGEMENT_DB_NAME = "AppVManagement"</p>
    <p>/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT = "\ アカウントアカウント"</p>
    <p>/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT = "\" \ installadminadminaccount "</p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>を選び、発行サーバーをインストールします。</p></td>
    <td align="left"><p>Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</p>
    <ul>
    <li><p>/PUBLISHING_SERVER</p></li>
    <li><p>/PUBLISHING_MGT_SERVER</p></li>
    <li><p>/PUBLISHING_WEBSITE_NAME</p></li>
    <li><p>/PUBLISHING_WEBSITE_PORT</p></li>
    </ul>
    <p>Microsoft SQL Server のカスタムインスタンスの使用例:</p>
    <p>/appv_server_setup.exe/QUIET</p>
    <p>/PUBLISHING_SERVER</p>
    <p>/PUBLISHING_MGT_SERVER = " http://ManagementServerName:ManagementPort "</p>
    <p>/PUBLISHING_WEBSITE_NAME = "Microsoft AppV 公開サービス"</p>
    <p>/PUBLISHING_WEBSITE_PORT = "8081"</p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>レポートサーバーとレポートデータベースをローカルコンピューターにインストールします。</p></td>
    <td align="left"><p>Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</p>
    <ul>
    <li><p>/レポート _SERVER</p></li>
    <li><p>/レポート _WEBSITE_NAME</p></li>
    <li><p>/レポート _WEBSITE_PORT</p></li>
    <li><p>/DB_PREDEPLOY_REPORTING</p></li>
    <li><p>/レポート _DB_SQLINSTANCE_USE_DEFAULT</p></li>
    <li><p>/レポート _DB_NAME</p></li>
    </ul>
    <p>Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します。</p>
    <ul>
    <li><p>/レポート _SERVER</p></li>
    <li><p>/レポート _ADMINACCOUNT</p></li>
    <li><p>/レポート _WEBSITE_NAME</p></li>
    <li><p>/レポート _WEBSITE_PORT</p></li>
    <li><p>/DB_PREDEPLOY_REPORTING</p></li>
    <li><p>/レポート _DB_CUSTOM_SQLINSTANCE</p></li>
    <li><p>/レポート _DB_NAME</p></li>
    </ul>
    <p>Microsoft SQL Server のカスタムインスタンスの使用例:</p>
    <ul>
    <li><p>/appv_server_setup.exe/QUIET</p></li>
    <li><p>/REPORTING_SERVER</p></li>
    <li><p>/REPORTING_WEBSITE_NAME = "Microsoft AppV Reporting Service"</p></li>
    <li><p>/REPORTING_WEBSITE_PORT = "8082"</p></li>
    <li><p>/DB_PREDEPLOY_REPORTING</p></li>
    <li><p>/REPORTING_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</p></li>
    <li><p>/REPORTING_DB_NAME = "AppVReporting"</p></li>
    </ul></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>レポートサーバーをインストールして、ローカルコンピューターに既存のレポートデータベースを使用します。</p></td>
    <td align="left"><p>Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</p>
    <ul>
    <li><p>/レポート _SERVER</p></li>
    <li><p>/レポート _WEBSITE_NAME</p></li>
    <li><p>/レポート _WEBSITE_PORT</p></li>
    <li><p>/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</p></li>
    <li><p>/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</p></li>
    <li><p>/EXISTING_REPORTING _DB_NAME</p></li>
    </ul>
    <p>Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します。</p>
    <ul>
    <li><p>/レポート _SERVER</p></li>
    <li><p>/レポート _ADMINACCOUNT</p></li>
    <li><p>/レポート _WEBSITE_NAME</p></li>
    <li><p>/レポート _WEBSITE_PORT</p></li>
    <li><p>/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</p></li>
    <li><p>/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</p></li>
    <li><p>/EXISTING_REPORTING _DB_NAME</p></li>
    </ul>
    <p>Microsoft SQL Server のカスタムインスタンスの使用例:</p>
    <p>/appv_server_setup.exe/QUIET</p>
    <p>/REPORTING_SERVER</p>
    <p>/REPORTING_WEBSITE_NAME = "Microsoft AppV Reporting Service"</p>
    <p>/REPORTING_WEBSITE_PORT = "8082"</p>
    <p>/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</p>
    <p>/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</p>
    <p>/EXITING_REPORTING_DB_NAME = "AppVReporting"</p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>リモートコンピューター上の既存のレポートデータベースを使用して、レポートサーバーをインストールします。</p></td>
    <td align="left"><p>Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</p>
    <ul>
    <li><p>/レポート _SERVER</p></li>
    <li><p>/レポート _WEBSITE_NAME</p></li>
    <li><p>/レポート _WEBSITE_PORT</p></li>
    <li><p>/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</p></li>
    <li><p>/EXISTING_REPORTING _DB_SQLINSTANCE_USE_DEFAULT</p></li>
    <li><p>/EXISTING_REPORTING _DB_NAME</p></li>
    </ul>
    <p>Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します。</p>
    <ul>
    <li><p>/レポート _SERVER</p></li>
    <li><p>/レポート _ADMINACCOUNT</p></li>
    <li><p>/レポート _WEBSITE_NAME</p></li>
    <li><p>/レポート _WEBSITE_PORT</p></li>
    <li><p>/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</p></li>
    <li><p>/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE</p></li>
    <li><p>/EXISTING_REPORTING _DB_NAME</p></li>
    </ul>
    <p>Microsoft SQL Server のカスタムインスタンスの使用例:</p>
    <p>/appv_server_setup.exe/QUIET</p>
    <p>/REPORTING_SERVER</p>
    <p>/REPORTING_WEBSITE_NAME = "Microsoft AppV Reporting Service"</p>
    <p>/REPORTING_WEBSITE_PORT = "8082"</p>
    <p>/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME = "SqlServerMachine"</p>
    <p>/EXISTING_REPORTING _DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</p>
    <p>/EXITING_REPORTING_DB_NAME = "AppVReporting"</p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>レポートサーバーと同じコンピューターにレポートデータベースをインストールする。</p></td>
    <td align="left"><p>Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</p>
    <ul>
    <li><p>/DB_PREDEPLOY_REPORTING</p></li>
    <li><p>/レポート _DB_SQLINSTANCE_USE_DEFAULT</p></li>
    <li><p>/レポート _DB_NAME</p></li>
    <li><p>/REPORTING_SERVER_MACHINE_USE_LOCAL</p></li>
    <li><p>/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</p></li>
    </ul>
    <p>Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します。</p>
    <ul>
    <li><p>/DB_PREDEPLOY_REPORTING</p></li>
    <li><p>/レポート _DB_CUSTOM_SQLINSTANCE</p></li>
    <li><p>/レポート _DB_NAME</p></li>
    <li><p>/REPORTING_SERVER_MACHINE_USE_LOCAL</p></li>
    <li><p>/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</p></li>
    </ul>
    <p>Microsoft SQL Server のカスタムインスタンスの使用例:</p>
    <p>/appv_server_setup.exe/QUIET</p>
    <p>/DB_PREDEPLOY_REPORTING</p>
    <p>/REPORTING_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</p>
    <p>/REPORTING_DB_NAME = "AppVReporting"</p>
    <p>/REPORTING_SERVER_MACHINE_USE_LOCAL</p>
    <p>/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = "\" \ installadminadminaccount "</p></td>
    </tr>
    </tbody>
    </table>

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p>レポートデータベースをレポートサーバーとは別のコンピューターにインストールする。</p></td>
    <td align="left"><p>Microsoft SQL Server の既定のインスタンスを使用するには、次のパラメーターを使用します。</p>
    <ul>
    <li><p>/DB_PREDEPLOY_REPORTING</p></li>
    <li><p>/レポート _DB_SQLINSTANCE_USE_DEFAULT</p></li>
    <li><p>/レポート _DB_NAME</p></li>
    <li><p>/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</p></li>
    <li><p>/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</p></li>
    </ul>
    <p>Microsoft SQL Server のカスタムインスタンスを使用するには、次のパラメーターを使用します。</p>
    <ul>
    <li><p>/DB_PREDEPLOY_REPORTING</p></li>
    <li><p>/レポート _DB_CUSTOM_SQLINSTANCE</p></li>
    <li><p>/レポート _DB_NAME</p></li>
    <li><p>/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</p></li>
    <li><p>/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</p></li>
    </ul>
    <p>Microsoft SQL Server のカスタムインスタンスの使用例:</p>
    <p>/appv_server_setup.exe/QUIET</p>
    <p>/DB_PREDEPLOY_REPORTING</p>
    <p>/REPORTING_DB_CUSTOM_SQLINSTANCE = "SqlInstanceName"</p>
    <p>/REPORTING_DB_NAME = "AppVReporting"</p>
    <p>/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT = "\ アカウントアカウント"</p>
    <p>/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = "\" \ installadminadminaccount "</p></td>
    </tr>
    </tbody>
    </table>

## パラメーターの定義

### 一般的なパラメーター

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">パラメーター</th>
    <th align="left">情報</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>/QUIET</p></td>
    <td align="left"><p>サイレントインストールを指定します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/UNINSTALL</p></td>
    <td align="left"><p>アンインストールを指定します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/レイアウト</p></td>
    <td align="left"><p>レイアウトアクションを指定します。 これにより、実際には製品をインストールせずに、MSIs ファイルとスクリプトファイルがフォルダーに抽出されます。 値は予期されません。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/Layoutdir</p></td>
    <td align="left"><p>レイアウトディレクトリを指定します。 文字列を受け取ります。 たとえば、/layoutdir = "C:\ Application Virtualization Server"</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/INSTALLDIR</p></td>
    <td align="left"><p>インストールディレクトリを指定します。 文字列を受け取ります。 例: /INSTALLDIR = "C:\Program Files\Application Virtualization\Server"</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/Muoptin</p></td>
    <td align="left"><p>Microsoft Update を有効にします。 値は期待されません。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/ACCEPTEULA</p></td>
    <td align="left"><p>ライセンス契約を承諾します。 これは、無人インストールの場合に必要になります。 使用例: <strong> /ACCEPTEULA </strong> または <strong> /ACCEPTEULA = 1 </strong> 。</p></td>
    </tr>
    </tbody>
    </table>

### 管理サーバーのインストールパラメーター

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">パラメーター</th>
    <th align="left">情報</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>/MANAGEMENT_SERVER</p></td>
    <td align="left"><p>管理サーバーをインストールすることを指定します。 値は期待されません。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/MANAGEMENT_ADMINACCOUNT</p></td>
    <td align="left"><p>管理サーバーへの管理者アクセス許可を持つことができるアカウントを指定します。このアカウントは、個々のユーザーアカウントまたはグループにすることができます。 使用例: <strong> /MANAGEMENT_ADMINACCOUNT = "my" 管理者 " </strong> 。 <strong>/MANAGEMENT_SERVER </strong> が指定されていない場合は、無視されます。 管理サーバーへの管理者アクセスが許可されるアカウントを指定します。 これは、ユーザーアカウントまたはグループのいずれかになります。 たとえば、 <strong> /MANAGEMENT_ADMINACCOUNT = &quot; myの管理者 &quot; </strong> 。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/MANAGEMENT_WEBSITE_NAME</p></td>
    <td align="left"><p>管理サービス用に作成される web サイトの名前を指定します。 たとえば、/MANAGEMENT_WEBSITE_NAME = "Microsoft App-V Management Service"</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>MANAGEMENT_WEBSITE_PORT</p></td>
    <td align="left"><p>管理サービスが使用するポート番号を指定します。 たとえば、/MANAGEMENT_WEBSITE_PORT = 82 とします。</p></td>
    </tr>
    </tbody>
    </table>

### 管理サーバーデータベースのパラメーター

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">パラメーター</th>
    <th align="left">情報</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>/DB_PREDEPLOY_MANAGEMENT</p></td>
    <td align="left"><p>管理データベースをインストールすることを指定します。 このインストールを完了するには、十分なデータベース権限が必要です。 値は期待されません。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</p></td>
    <td align="left"><p>既定の SQL インスタンスを使用する必要があることを示します。 値は予期されません。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</p></td>
    <td align="left"><p>新しいデータベースの作成に使用するカスタム SQL インスタンスの名前を指定します。 使用例: <strong> /MANAGEMENT_DB_ CUSTOM_SQLINSTANCE = "MYSQLSERVER" </strong> 。 /DB_PREDEPLOY_MANAGEMENT が指定されていない場合は、無視されます。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/MANAGEMENT_DB_NAME</p></td>
    <td align="left"><p>作成する新しい管理データベースの名前を指定します。 使用例: <strong> /MANAGEMENT_DB_NAME = "AppVMgmtDB" </strong> /DB_PREDEPLOY_MANAGEMENT が指定されていない場合は、無視されます。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/MANAGEMENT_SERVER_MACHINE_USE_LOCAL</p></td>
    <td align="left"><p>データベースにアクセスする管理サーバーがローカルサーバーにインストールされているかどうかを示します。 スイッチパラメーター。値は予期されません。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</p></td>
    <td align="left"><p>管理サーバーをインストールするリモートコンピューターのコンピューターアカウントを指定します。 使用例: <strong> /MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT = "domain\computername"</strong></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</p></td>
    <td align="left"><p>管理サーバーをインストールするために使用される管理者アカウントを示します。 使用例: <strong> /MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT = "domain\alias"</strong></p></td>
    </tr>
    </tbody>
    </table>

### 発行サーバーをインストールするためのパラメーター

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">パラメーター</th>
    <th align="left">情報</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>/PUBLISHING_SERVER</p></td>
    <td align="left"><p>発行サーバーをインストールすることを指定します。 値は期待されません。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/PUBLISHING_MGT_SERVER</p></td>
    <td align="left"><p>発行サーバーが接続する管理サービスの URL を指定します。 使用例: <strong> http:// &lt; management server name &gt; : &lt; 管理サーバーのポート番号 &gt; </strong> 。 /PUBLISHING_SERVER が使用されていない場合、このパラメーターは無視されます。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/PUBLISHING_WEBSITE_NAME</p></td>
    <td align="left"><p>発行サービス用に作成される web サイトの名前を指定します。 たとえば、/PUBLISHING_WEBSITE_NAME = "Microsoft App-V Publishing Service"</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/PUBLISHING_WEBSITE_PORT</p></td>
    <td align="left"><p>発行サービスによって使用されるポート番号を指定します。 たとえば、/PUBLISHING_WEBSITE_PORT = 83</p></td>
    </tr>
    </tbody>
    </table>

### レポートサーバーのパラメーター

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">パラメーター</th>
    <th align="left">情報</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>/REPORTING_SERVER</p></td>
    <td align="left"><p>レポートサーバーをインストールすることを指定します。 値は期待されません。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/REPORTING_WEBSITE_NAME</p></td>
    <td align="left"><p>レポートサービス用に作成される web サイトの名前を指定します。 例: /REPORTING_WEBSITE_NAME = &quot; Microsoft App-V ReportingService&quot;</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/REPORTING_WEBSITE_PORT</p></td>
    <td align="left"><p>レポートサービスが使用するポート番号を指定します。 例: /REPORTING_WEBSITE_PORT = 82</p></td>
    </tr>
    </tbody>
    </table>

     

### 既存のレポートサーバーデータベースを使用するためのパラメーター

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">パラメーター</th>
    <th align="left">情報</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>/EXISTING_REPORTING_DB_SQL_SERVER_USE_LOCAL</p></td>
    <td align="left"><p>Microsoft SQL Server がローカルサーバーにインストールされていることを示します。 スイッチパラメーター。値は予期されません。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/EXISTING_REPORTING_DB_REMOTE_SQL_SERVER_NAME</p></td>
    <td align="left"><p>SQL Server がインストールされているリモートコンピューターの名前を指定します。 文字列を受け取ります。 例: /EXISTING_REPORTING_DB_ REMOTE_SQL_SERVER_NAME = &quot; mycomputer1&quot;</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>レポート DB_SQLINSTANCE_USE_DEFAULT の EXISTING_ <em></p></td>
    <td align="left"><p>既定の SQL インスタンスが使用されることを示します。 スイッチパラメーター。値は予期されません。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>既存の </em> REPORTING_DB_CUSTOM_SQLINSTANCE</p></td>
    <td align="left"><p>使用するカスタム SQL インスタンスの名前を指定します。 文字列を受け取ります。 例: /EXISTING_REPORTING_DB_ CUSTOM_SQLINSTANCE = &quot; MYSQLSERVER&quot;</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>レポート _DB_NAME の EXISTING_</p></td>
    <td align="left"><p>使用する既存のレポートデータベースの名前を指定します。 文字列を受け取ります。 例: /EXISTING_REPORTING_DB_NAME = &quot; AppVReporting&quot;</p></td>
    </tr>
    </tbody>
    </table>

### レポートサーバーデータベースをインストールするためのパラメーター

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">パラメーター</th>
    <th align="left">情報</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>/DB_PREDEPLOY_REPORTING</p></td>
    <td align="left"><p>レポートデータベースがインストールされることを指定します。 このインストールには、DBA 権限が必要です。 値は期待されません。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/REPORTING_DB_SQLINSTANCE_USE_DEFAULT</p></td>
    <td align="left"><p>使用するカスタム SQL インスタンスの名前を指定します。 文字列を受け取ります。 例: /REPORTING_DB_ CUSTOM_SQLINSTANCE = &quot; MYSQLSERVER&quot;</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/REPORTING_DB_NAME</p></td>
    <td align="left"><p>作成する新しいレポートデータベースの名前を指定します。 文字列を受け取ります。 例: /REPORTING_DB_NAME = &quot; AppVMgmtDB&quot;</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/REPORTING_SERVER_MACHINE_USE_LOCAL</p></td>
    <td align="left"><p>データベースにアクセスするレポートサーバーがローカルサーバーにインストールされていることを示します。 スイッチパラメーター。値は予期されません。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</p></td>
    <td align="left"><p>レポートサーバーをインストールするリモートコンピューターのコンピューターアカウントを指定します。 文字列を受け取ります。 例: /REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT = &quot; domain\computername&quot;</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</p></td>
    <td align="left"><p>App-v レポートサーバーをインストールするために使用される管理者アカウントを示します。 文字列を受け取ります。 例: /REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT = &quot; domain\alias&quot;</p></td>
    </tr>
    </tbody>
    </table>

### 既存の管理サーバーデータベースを使用するためのパラメーター

<table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">パラメーター</th>
    <th align="left">情報</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>/EXISTING_MANAGEMENT_DB_SQL_SERVER_USE_LOCAL</p></td>
    <td align="left"><p>SQL Server がローカルサーバーにインストールされていることを示します。 スイッチパラメーター。値は予期されません。/DB_PREDEPLOY_MANAGEMENT が指定されている場合、これは無視されます。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/EXISTING_MANAGEMENT_DB_REMOTE_SQL_SERVER_NAME</p></td>
    <td align="left"><p>SQL Server がインストールされているリモートコンピューターの名前を指定します。 文字列を受け取ります。 例: /EXISTING_MANAGEMENT_DB_ REMOTE_SQL_SERVER_NAME = &quot; mycomputer1&quot;</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/EXISTING_ MANAGEMENT_DB_SQLINSTANCE_USE_DEFAULT</p></td>
    <td align="left"><p>既定の SQL インスタンスが使用されることを示します。 スイッチパラメーター。値は予期されません。 /DB_PREDEPLOY_MANAGEMENT が指定されている場合、これは無視されます。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>/EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE</p></td>
    <td align="left"><p>使用されるカスタム SQL インスタンスの名前を指定します。 使用例 <strong> /EXISTING_MANAGEMENT_DB_ CUSTOM_SQLINSTANCE = "AppVManagement" </strong> 。 /DB_PREDEPLOY_MANAGEMENT が指定されている場合、これは無視されます。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>/EXISTING_MANAGEMENT_DB_NAME</p></td>
    <td align="left"><p>使用する既存の管理データベースの名前を指定します。 使用例: <strong> /EXISTING_MANAGEMENT_DB_NAME = "AppVMgmtDB" </strong> /DB_PREDEPLOY_MANAGEMENT が指定されている場合、これは無視されます。</p>
    <p></p>
    <p><strong>App-v の提案をお寄せ </strong> ください。 ここで候補を追加または投票 <a href="http://appv.uservoice.com/forums/280448-microsoft-application-virtualization" data-raw-source="[here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)"> </a> してください。 <strong>App-v issu e をお持ち </strong> ですか? App-v の <a href="https://social.technet.microsoft.com/Forums/home?forum=mdopappv" data-raw-source="[App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)"> TechNet フォーラムを使用し </a> ます。</p></td>
</tr>
</tbody>
</table>
  

## 関連トピック

[App-V 5.0 Server の展開](deploying-the-app-v-50-server.md)

 

 





