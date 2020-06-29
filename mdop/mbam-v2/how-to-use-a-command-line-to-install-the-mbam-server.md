---
title: コマンド ラインを使用して MBAM サーバーをインストールする方法
description: コマンド ラインを使用して MBAM サーバーをインストールする方法
author: dansimp
ms.assetid: 6ffc6d41-a793-42c2-b997-95ba47550648
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a689a2df77300300073b2731281004feac87305f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825644"
---
# コマンド ラインを使用して MBAM サーバーをインストールする方法


コマンドラインを使用して、スタンドアロンまたは構成マネージャーのトポロジで MBAM サーバーをインストールすることができます。 次のコマンドラインの例は、1つのサーバーに MBAM を展開するためのものであり、テスト環境でのみ使用する必要があります。 複数のサーバーがある運用環境に MBAM を展開する場合は、それに応じてコマンドラインを変更する必要があります。

## スタンドアロントポロジで MBAM 2.0 サーバーを展開するためのコマンドライン


次のようなコマンドラインを使用して、MBAM サーバーをスタンドアロントポロジでインストールできます。

``` syntax
MbamSetup.exe /qb /l*v MaltaServerInstall.log TOPOLOGY=0 I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 ADDLOCAL=KeyDatabase,ReportsDatabase,Reports,AdministrationMonitoringServer,SelfServiceServer,PolicyTemplate,REPORTS_USERACCOUNT=[UserDomain]\[UserName1] REPORTS_USERACCOUNTPW=[UserPwd1] COMPLIDB_SQLINSTANCE=%computername% RECOVERYANDHWDB_SQLINSTANCE=%computername% SRS_INSTANCENAME=%computername% ADMINANDMON_WEBSITE_PORT=83 WEBSITE_PORT=83
```

次の表では、スタンドアロントポロジで MBAM サーバーを展開するためのコマンドラインパラメーターについて説明します。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">パラメーター</th>
<th align="left">パラメーター値</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>トポロジ</p></td>
<td align="left"><p>0</p></td>
<td align="left"><p>0–スタンドアロントポロジ</p></td>
</tr>
<tr class="even">
<td align="left"><p>I_ACCEPT_ENDUSER_LICENSE_AGREEMENT</p></td>
<td align="left"><p>付き</p></td>
<td align="left"><p>0–ライセンス agreement1 に同意しない–使用許諾契約に同意してください。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ADDLOCAL</p></td>
<td align="left"><p></p></td>
<td align="left"><p>サーバーにインストールされる機能</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>KeyDatabase</p></td>
<td align="left"><p>回復用データベース</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p>レポートデータベース</p></td>
<td align="left"><p>コンプライアンスと監査レポートデータベース</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>レポート</p></td>
<td align="left"><p>コンプライアンスと監査レポート</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p>管理 Monitoringserver</p></td>
<td align="left"><p>管理と監視の web サイト</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>SelfServiceServer</p></td>
<td align="left"><p>セルフサービスポータル</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p>PolicyTemplate</p></td>
<td align="left"><p>MBAM グループポリシーテンプレート</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTS_USERACCOUNT</p></td>
<td align="left"><p>[UserDomain][UserName1]</p></td>
<td align="left"><p>コンプライアンスと監査データベースにアクセスする Reporting Services サービスアカウントのドメインとユーザーアカウント</p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTS_USERACCOUNTPW</p></td>
<td align="left"><p>[UserPwd1]</p></td>
<td align="left"><p>コンプライアンスと監査データベースにアクセスする Reporting Services サービスアカウントのパスワード</p></td>
</tr>
<tr class="even">
<td align="left"><p>COMPLIDB_SQLINSTANCE</p></td>
<td align="left"><p>名</p></td>
<td align="left"><p>コンプライアンスおよび監査データベースの SQL Server インスタンス名– <strong> % computername% </strong> をコンピューター名で置き換えます</p></td>
</tr>
<tr class="odd">
<td align="left"><p>RECOVERYANDHWDB_SQLINSTANCE</p></td>
<td align="left"><p>名</p></td>
<td align="left"><p>回復データベースの SQL Server インスタンス名– <strong> % computername% </strong> をコンピューター名で置き換えます</p></td>
</tr>
<tr class="even">
<td align="left"><p>SRS_INSTANCENAME</p></td>
<td align="left"><p>名</p></td>
<td align="left"><p>コンプライアンスと監査レポートがインストールされる SQL Server Reporting Server インスタンス– <strong> % computername% </strong> をコンピューター名で置き換えます</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ADMINANDMON_WEBSITE_PORT</p></td>
<td align="left"><p>83</p></td>
<td align="left"><p>管理と監視の web サイトのポート"83" は一例にすぎません</p></td>
</tr>
<tr class="even">
<td align="left"><p>WEBSITE_PORT</p></td>
<td align="left"><p>83</p></td>
<td align="left"><p>セルフサービスポータル web サイトのポート。"83" は一例にすぎません</p></td>
</tr>
</tbody>
</table>

 

## Configuration Manager トポロジを使用して MBAM 2.0 サーバーを展開するためのコマンドライン


Configuration Manager トポロジを使用して MBAM サーバーをインストールするには、次のようなコマンドラインを使用できます。

``` syntax
MbamSetup.exe /qn /l*v MaltaServerInstall.log I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 TOPOLOGY=1 COMPLIDB_SQLINSTANCE=%computername% RECOVERYANDHWDB_SQLINSTANCE=%computername% SRS_INSTANCENAME=%computername% REPORTS_USERACCOUNT=[UserDomain]\[UserName] REPORTS_USERACCOUNTPW=[UserPwd] ADMINANDMON_WEBSITE_PORT=83 WEBSITE_PORT=83
```

次の表では、Configuration Manager トポロジを持つ MBAM 2.0 サーバーをインストールするためのコマンドラインパラメーターについて説明します。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">パラメーター</th>
<th align="left">パラメーター値</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>トポロジ</p></td>
<td align="left"><p>件</p></td>
<td align="left"><p>1– Configuration Manager のトポロジ</p></td>
</tr>
<tr class="even">
<td align="left"><p>I_ACCEPT_ENDUSER_LICENSE_AGREEMENT</p></td>
<td align="left"><p>付き</p></td>
<td align="left"><p>0–ライセンス agreement1 に同意しない–使用許諾契約に同意してください。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>COMPLIDB_SQLINSTANCE</p></td>
<td align="left"><p>名</p></td>
<td align="left"><p>監査データベースの SQL Server インスタンス名– <strong> % computername% </strong> をコンピューター名で置き換えます</p></td>
</tr>
<tr class="even">
<td align="left"><p>RECOVERYANDHWDB_SQLINSTANCE</p></td>
<td align="left"><p>名</p></td>
<td align="left"><p>回復データベースの SQL Server インスタンス名- <strong> % computername% </strong> をコンピューター名で置き換えます</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SRS_INSTANCENAME</p></td>
<td align="left"><p>名</p></td>
<td align="left"><p>監査レポートがインストールされる SQL Server Reporting Server インスタンス–% computername% をコンピューター名で置き換えます</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTS_USERACCOUNT</p></td>
<td align="left"><p>[UserDomain][UserName1]</p></td>
<td align="left"><p>コンプライアンスと監査データベースにアクセスする Reporting Services サービスアカウントのドメインとユーザーアカウント</p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTS_USERACCOUNTPW</p></td>
<td align="left"><p>[UserPwd1]</p></td>
<td align="left"><p>コンプライアンスと監査データベースにアクセスする Reporting Services サービスアカウントのパスワード</p></td>
</tr>
<tr class="even">
<td align="left"><p>ADMINANDMON_WEBSITE_PORT</p></td>
<td align="left"><p>83</p></td>
<td align="left"><p>管理と監視の web サイトのポート"83" は一例にすぎません</p></td>
</tr>
<tr class="odd">
<td align="left"><p>WEBSITE_PORT</p></td>
<td align="left"><p>83</p></td>
<td align="left"><p>セルフサービスポータル web サイトのポート。"83" は一例にすぎません</p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[MBAM 2.0 サーバー インフラストラクチャの展開](deploying-the-mbam-20-server-infrastructure-mbam-2.md)

 

 





