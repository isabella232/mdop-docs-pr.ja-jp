---
title: MBAM 1.0 のセキュリティに関する考慮事項
description: MBAM 1.0 のセキュリティに関する考慮事項
author: dansimp
ms.assetid: 5e1c8b8c-235b-4a92-8b0b-da50dca17353
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b06c343c8193293dde91bc7af2541f35f332d261
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826194"
---
# MBAM 1.0 のセキュリティに関する考慮事項


このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) に関するアカウントとグループ、ログファイル、およびその他のセキュリティ関連の考慮事項について簡単に説明します。 詳細については、この記事のリンクを参照してください。

## 一般的なセキュリティの考慮事項


**セキュリティのリスクについて説明します。** MBAM の最も重大なリスクは、許可されていないユーザーが BitLocker 暗号化を再構成して、MBAM クライアントで BitLocker 暗号化キーデータを取得できるということです。 ただし、サービス拒否攻撃のために、しばらくの間、MBAM 機能が失われても、通常は致命的な影響はありません。

**コンピューターを物理的に保護**します。 セキュリティは物理的なセキュリティがない状態では完了しません。 MBAM サーバーに物理的にアクセスできるすべての人が、クライアントベース全体を攻撃する可能性があります。 物理的な攻撃が発生する可能性がある場合は、リスクが高いと考えられ、適切に軽減されます。 MBAM サーバは、アクセスを管理することで、物理的に安全なサーバ室に保存する必要があります。 オペレーティングシステムによってコンピューターがロックされている場合、またはセキュアなスクリーンセーバーを使用している場合は、管理者が物理的に存在しない場合は、これらのコンピューターをセキュリティで保護します。

**すべてのコンピューターに最新のセキュリティ更新プログラムを適用**します。 セキュリティ通知サービス () をサブスクライブすることにより、オペレーティングシステム、Microsoft SQL Server、MBAM の新しい更新について常に情報を受け取ることが <https://go.microsoft.com/fwlink/p/?LinkId=28819> できます。

**強力なパスワードを使用するか、語句を渡し**ます。 すべての MBAM および MBAM 管理者アカウントには、必ず15文字以上の強力なパスワードを使用してください。 空のパスワードは使用しないでください。 パスワードの概念の詳細については、TechNet の「アカウントのパスワードとポリシー」を参照してください <https://go.microsoft.com/fwlink/p/?LinkId=30009> 。

## MBAM のアカウントとグループ


ユーザーアカウントの管理については、ドメイングローバルグループを作成し、ユーザーアカウントを追加することをお勧めします。 次に、MBAM サーバー上の必要な MBAM ローカルグループにドメインのグローバルアカウントを追加します。

### ActiveDirectoryDomainServices グループ

MBAM セットアップ中に自動的にグループが作成されることはありません。 ただし、MBAM 操作を管理するには、次の ActiveDirectoryDomainServices グローバルグループを作成する必要があります。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">グループ名</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MBAM Advanced ヘルプデスクユーザー</p></td>
<td align="left"><p>このグループを作成して、mbam セットアップで作成された MBAM Advanced ヘルプデスクユーザーのローカルグループのメンバーを管理します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM コンプライアンス監査データベースアクセス</p></td>
<td align="left"><p>このグループを作成して、mbam セットアップで作成された MBAM コンプライアンス監査 DB Access ローカルグループのメンバーを管理します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM ハードウェアユーザー</p></td>
<td align="left"><p>このグループを作成して、mbam セットアップで作成された MBAM Hardware Users ローカルグループのメンバーを管理します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM ヘルプデスクユーザー</p></td>
<td align="left"><p>このグループを作成すると、MBAM セットアップで作成された MBAM ヘルプデスクユーザーのローカルグループのメンバーを管理できます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM 回復とハードウェアデータベースへのアクセス</p></td>
<td align="left"><p>このグループを作成して、mbam セットアップで作成された MBAM Recovery と Hardware DB Access ローカルグループのメンバーを管理します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM レポートユーザー</p></td>
<td align="left"><p>このグループを作成して、mbam セットアップで作成された MBAM Report Users ローカルグループのメンバーを管理します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM システム管理者</p></td>
<td align="left"><p>このグループを作成して、MBAM セットアップで作成された MBAM システム管理者ローカルグループのメンバーを管理します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>BitLocker 暗号化の除外</p></td>
<td align="left"><p>このグループを作成して、ログオン先のコンピューターで開始する BitLocker 暗号化から除外する必要があるユーザーアカウントを管理します。</p></td>
</tr>
</tbody>
</table>

 

### MBAM サーバーのローカルグループ

MBAM セットアップは、MBAM 操作をサポートするローカルグループを作成します。 MBAM セキュリティとデータアクセス権限を構成するために、適切な MBAM ローカルグループに ActiveDirectoryDomainServices グローバルグループを追加する必要があります。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">グループ名</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MBAM Advanced ヘルプデスクユーザー</p></td>
<td align="left"><p>このグループのメンバーは、Microsoft BitLocker の管理と監視のヘルプデスク機能へのアクセスが拡張されています。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM コンプライアンス監査データベースアクセス</p></td>
<td align="left"><p>このグループには、MBAM コンプライアンス監査データベースへのアクセス権を持つコンピューターが含まれています。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM ハードウェアユーザー</p></td>
<td align="left"><p>このグループのメンバーは、Microsoft BitLocker の管理と監視の一部のハードウェア機能機能にアクセスできます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM ヘルプデスクユーザー</p></td>
<td align="left"><p>このグループのメンバーは、Microsoft BitLocker の管理と監視の一部のヘルプデスク機能にアクセスできます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM 回復とハードウェアデータベースへのアクセス</p></td>
<td align="left"><p>このグループには、MBAM 回復とハードウェアデータベースへのアクセス権を持つコンピューターが含まれています。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM レポートユーザー</p></td>
<td align="left"><p>このグループのメンバーは、Microsoft BitLocker の管理と監視に関するコンプライアンスおよび監査レポートにアクセスできます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM システム管理者</p></td>
<td align="left"><p>このグループのメンバーは、Microsoft BitLocker の管理と監視のすべての機能にアクセスできます。</p></td>
</tr>
</tbody>
</table>

 

### SSRS レポートアクセスアカウント

SQL Server Reporting Services (SSRS) レポートサービスアカウントは、SSRS で利用可能な MBAM レポートを実行するためのセキュリティコンテキストを提供します。 このアカウントは、MBAM セットアップ中に構成されます。

## MBAM ログファイル


MBAM のセットアップ時に、次の MBAM セットアップログファイルが、インストールしたユーザーの% temp% フォルダーに作成されます。

**MBAM サーバーセットアップログファイル**

<a href="" id="msi-five-random-characters--log"></a>MSI <em> &lt; 5 ランダム文字 &gt; </em> ログ  
MBAM セットアップおよび MBAM サーバー機能のインストール中に実行されたアクションをログに記録します。

<a href="" id="installcompliancedatabase-log"></a>InstallComplianceDatabase  
MBAM コンプライアンスステータスデータベースの設定を作成するために実行されたアクションをログに記録します。

<a href="" id="installkeycompliancedatabase-log"></a>InstallKeyComplianceDatabase  
MBAM 回復とハードウェアデータベースを作成するために実行されたアクションをログに記録します。

<a href="" id="addhelpdeskdbauditusers-log"></a>Addhelpdbauditusers .log  
MBAM コンプライアンスステータスデータベースで SQL Server ログインを作成するために実行されたアクションをログに記録し、レポート用のデータベースへのヘルプデスク web サービスを承認します。

<a href="" id="addhelpdeskdbusers-log"></a>Addhelpdbusers .log  
Web サービスをデータベースに対して承認するために実行された操作を、キーの回復のためにログに記録し、MBAM 回復とハードウェアデータベースへのログインを作成します。

<a href="" id="addkeycompliancedbusers-log"></a>AddKeyComplianceDbUsers  
Web サービスを認証するために実行されたアクションを、コンプライアンスレポート用の MBAM コンプライアンスステータスデータベースに記録します。

<a href="" id="addrecoveryandhardwaredbusers-log"></a>Addrecoveryandハードウェア Dbusers .log  
Web サービスを MBAM 回復とハードウェアデータベースに対して、キーの回復用に承認するために実行されたアクションをログに記録します。

**注** MBAM セットアップログファイルを追加するには、 **msiexec**パッケージと **/l** location オプションを使用して、Microsoft BitLocker の管理と監視をインストールする必要があり &lt; &gt; ます。 指定した場所でログファイルが作成されます。

 

**MBAM クライアントのセットアップログファイル**

<a href="" id="msi-five-random-characters--log"></a>MSI <em> &lt; 5 ランダム文字 &gt; </em> ログ  
MBAM クライアントのインストール中に実行されたアクションをログに記録します。

## MBAM データベースの除外の考慮事項


SQL Server 2008 で利用できる透過データ暗号化 (TDE) 機能は、MBAM データベース機能をホストするデータベースインスタンスに必要なインストール必須要件です。

TDE では、リアルタイムの完全なデータベースレベルの暗号化を実行できます。 TDE は、法令遵守または企業データセキュリティ標準に準拠するために、一括暗号化の選択肢として適しています。 TDE は、2つの Windows 機能 (暗号化ファイルシステム (EFS) と BitLocker ドライブ暗号化) に似ていますが、どちらもハードドライブ上のデータを暗号化します。 TDE では、セルレベルの暗号化、EFS、または BitLocker は置き換えられません。

データベースで TDE を有効にすると、すべてのバックアップが暗号化されます。 そのため、データベース暗号化キー (DEK) を保護するために使用された証明書がバックアップされ、データベースのバックアップで維持されるように、特別な注意を払う必要があります。 証明書がない場合、データは解読されません。 データベースと共に証明書をバックアップします。 各証明書のバックアップには、2つのファイルが必要です。これらのファイルはどちらもアーカイブする必要があります。セキュリティのためにデータベースバックアップファイルから個別にアーカイブすることをお勧めします。

MBAM データベースインスタンスの TDE を有効にする方法の例については、「 [mbam 1.0 の評価](evaluating-mbam-10.md)」を参照してください。

SQLServer 2008 の TDE の詳細については、「 [SQL Server 2008 Enterprise Edition のデータベース暗号化](https://go.microsoft.com/fwlink/?LinkId=269703)」を参照してください。

## 関連トピック


[MBAM 1.0 のセキュリティとプライバシー](security-and-privacy-for-mbam-10.md)

 

 





