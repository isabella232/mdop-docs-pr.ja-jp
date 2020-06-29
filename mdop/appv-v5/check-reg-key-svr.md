---
title: APP-V 5.x Server をインストールする前にレジストリ キーを確認する
description: APP-V 5.x Server をインストールする前にレジストリ キーを確認する
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.openlocfilehash: 9fe5a1b37d0fb5208d138939bb2fc79c89171fb3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814707"
---
# APP-V 5.x Server をインストールする前にレジストリ キーを確認する

App-v Server を App-v 5.0 SP1 修正プログラムパッケージ3以降からアップグレードする場合は、このセクションの手順を実行してから、app-v Server をインストールしてください。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>この手順が必要な場合</strong></p></td>
<td align="left"><p>.Msp ファイルを使用してインストールした後続の修正プログラムパッケージを使用して、App-v 5.0 SP1 からアップグレードします。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>この手順を実行する必要があるコンポーネント</strong></p></td>
<td align="left"><p>アップグレードしている App-v Server コンポーネントのみ</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>この手順を実行する必要がある場合</strong></p></td>
<td align="left"><p>App-v Server をアプリ-V 5.x にアップグレードする前に</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>必要な作業</strong></p></td>
<td align="left"><p>次の表の情報を使用して、[ <code>HKLM\Software\Microsoft\AppV\Server</code> 元のサーバーインストールで指定した値を使用して、各レジストリキーの値を更新します] を選びます。 この手順を完了すると、App-v 5.0 SP1 修正プログラムパッケージをインストールしたときに削除された可能性があるレジストリ値が復元されます。</p></td>
</tr>
</tbody>
</table>

 

**ManagementDatabase キー**

管理データベースをインストールする場合は、次のレジストリキーをに設定 `HKLM\Software\Microsoft\AppV\Server\ManagementDatabase` します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">キー名</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</p></td>
<td align="left"><p>ローカル以外の管理データベースにアクセスするためにパブリックアクセスアカウントが必要かどうかを指定します。 値が必要な場合は、"1" に設定されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_DB_NAME</p></td>
<td align="left"><p>管理データベースの名前。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT</p></td>
<td align="left"><p>読み取り (パブリック) 管理データベースへのアクセスに使用するアカウント。</p>
<p>"1" に設定されているときに使われ <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> ます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_SID</p></td>
<td align="left"><p>管理データベースへの読み取り (パブリック) アクセスに使用されるアカウントのセキュリティ識別子 (SID)。</p>
<p>"1" に設定されているときに使われ <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> ます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_DB_SQL_INSTANCE</p></td>
<td align="left"><p>管理データベースの SQL Server インスタンス。</p>
<p>この値が空白の場合、既定のデータベースインスタンスが使用されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT</p></td>
<td align="left"><p>管理データベースへの書き込み (管理者) アクセスのために使用されるアカウント。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT_SID</p></td>
<td align="left"><p>管理データベースへの書き込み (管理者) アクセスのために使用されるアカウントのセキュリティ識別子 (SID)。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</p></td>
<td align="left"><p>管理サーバーのリモートコンピューターアカウント (ドメイン \ アカウント)。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</p></td>
<td align="left"><p>管理サーバー (ドメイン \ アカウント) のインストール管理者ログイン。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_SERVER_MACHINE_USE_LOCAL</p></td>
<td align="left"><p>有効な値は次のとおりです。</p>
<ul>
<li><p><strong>1 </strong> –管理サービスはローカルコンピューターにあります。つまり、MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT は空白です。</p></li>
<li><p><strong>0 </strong> - 管理サービスは、ローカルコンピューターとは別のコンピューターにあります。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**ManagementService キー**

管理サーバーをインストールする場合は、次のレジストリキーをに設定 `HKLM\Software\Microsoft\AppV\Server\ManagementService` します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">キー名</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MANAGEMENT_ADMINACCOUNT</p></td>
<td align="left"><p>Active Directory ドメインサービス (AD DS) グループまたは、App-v (ドメイン \ アカウント) を管理する権限が与えられているアカウント。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_DB_SQL_INSTANCE</p></td>
<td align="left"><p>管理データベースを含む SQL server インスタンス。</p>
<p>この値が空白の場合、既定のデータベースインスタンスが使用されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_DB_SQL_SERVER_NAME</p></td>
<td align="left"><p>管理データベースのあるリモート SQL server の名前。</p>
<p>この値が空白の場合は、ローカルコンピューターが使用されます。</p></td>
</tr>
</tbody>
</table>

 

**ReportingDatabase キー**

レポートデータベースをインストールする場合は、次のレジストリキーをに設定 `HKLM\Software\Microsoft\AppV\Server\ReportingDatabase` します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">キー名</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</p></td>
<td align="left"><p>ローカル以外のレポートデータベースにアクセスするためにパブリックアクセスアカウントが必要かどうかを指定します。 値が必要な場合は、"1" に設定されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_DB_NAME</p></td>
<td align="left"><p>レポートデータベースの名前。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTING_DB_PUBLIC_ACCESS_ACCOUNT</p></td>
<td align="left"><p>レポートデータベースへの読み取り (パブリック) アクセスに使用されるアカウント。</p>
<p>"1" に設定されているときに使われ <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> ます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_SID</p></td>
<td align="left"><p>レポートデータベースへの読み取り (パブリック) アクセスに使用されるアカウントのセキュリティ識別子 (SID)。</p>
<p>"1" に設定されているときに使われ <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> ます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTING_DB_SQL_INSTANCE</p></td>
<td align="left"><p>レポートデータベースの SQL Server インスタンス。</p>
<p>この値が空白の場合、既定のデータベースインスタンスが使用されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_DB_WRITE_ACCESS_ACCOUNT</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTING_DB_WRITE_ACCESS_ACCOUNT_SID</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</p></td>
<td align="left"><p>レポートサーバーのリモートコンピューターアカウント (ドメイン \ アカウント)。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</p></td>
<td align="left"><p>[Reporting server (ドメイン \ アカウント)] のインストール管理者としてログインします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_SERVER_MACHINE_USE_LOCAL</p></td>
<td align="left"><p>有効な値は次のとおりです。</p>
<ul>
<li><p><strong>1 </strong> –レポートサービスはローカルコンピューターにあります。つまり、REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT は空白です。</p></li>
<li><p><strong>0 </strong> - レポートサービスは、ローカルコンピューターの別のコンピューターにあります。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**ReportingService キー**

レポートサーバーをインストールする場合は、次のレジストリキーをに設定 `HKLM\Software\Microsoft\AppV\Server\ReportingService` します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">キー名</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>REPORTING_DB_SQL_INSTANCE</p></td>
<td align="left"><p>レポートデータベースの SQL Server インスタンス。</p>
<p>この値が空白の場合、既定のデータベースインスタンスが使用されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_DB_SQL_SERVER_NAME</p></td>
<td align="left"><p>レポートデータベースのあるリモート SQL server の名前。</p>
<p>この値が空白の場合は、ローカルコンピューターが使用されます。</p></td>
</tr>
</tbody>
</table>

