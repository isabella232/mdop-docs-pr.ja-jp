---
title: MBAM 2.0 のセキュリティ上の考慮事項
description: MBAM 2.0 のセキュリティ上の考慮事項
author: dansimp
ms.assetid: 0aa5c6e2-d92c-4e30-9f6a-b48abb667ae5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 04dc9b667faddecab629b50f4c5d909fd7b2829e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823914"
---
# MBAM 2.0 のセキュリティ上の考慮事項


このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) に関するアカウントとグループ、ログファイル、およびその他のセキュリティ関連の考慮事項について簡単に説明します。 詳細については、この記事に記載されているリンクを参照してください。

## 一般的なセキュリティの考慮事項


**セキュリティのリスクについて説明します。** Microsoft BitLocker の管理と監視の最も重大なリスクは、BitLocker 暗号化を再構成し、MBAM クライアントで BitLocker 暗号化キーデータを取得できる、承認されていないユーザーがその機能をハイジャックする可能性があるということです。 ただし、サービス拒否攻撃のために MBAM 機能が短期間で失われても、メール、ネットワーク通信、ライト、停電などのように、通常、壊滅的な影響を受けることはありません。

**コンピューターを物理的に保護**します。 物理的なセキュリティがない場合は、セキュリティは必要ありません。 MBAM サーバーに物理的にアクセスできる攻撃者は、クライアントベース全体を攻撃するためにそれを使用する可能性があります。 すべての潜在的な物理的な攻撃は、高リスクと見なされ、適切に軽減する必要があります。 MBAM サーバは、アクセスを制御できる安全なサーバールームに保存する必要があります。 オペレーティングシステムによってコンピューターがロックされている場合、またはセキュアなスクリーンセーバーを使用している場合は、管理者が物理的に存在しない場合は、これらのコンピューターをセキュリティで保護します。

**すべてのコンピューターに最新のセキュリティ更新プログラムを適用**します。 セキュリティ通知サービス () をサブスクライブすることにより、オペレーティングシステム、Microsoft SQL Server、MBAM の新しい更新について常に情報を受け取ることが <https://go.microsoft.com/fwlink/?LinkId=28819> できます。

**強力なパスワードを使用するか、語句を渡し**ます。 すべての MBAM および MBAM 管理者アカウントには、必ず15文字以上の強力なパスワードを使用してください。 空のパスワードは使用しないでください。 パスワードの概念の詳細については、TechNet の「アカウントのパスワードとポリシー」を参照してください <https://go.microsoft.com/fwlink/?LinkId=30009> 。

## MBAM のアカウントとグループ


ユーザーアカウントを管理するためのベストプラクティスは、ドメイングローバルグループを作成し、ユーザーアカウントを追加することです。 次に、MBAM サーバー上の必要な MBAM ローカルグループにドメインのグローバルアカウントを追加します。

### ActiveDirectoryDomainServices グループ

MBAM セットアッププロセス中に、Active Directory グループは自動的に作成されません。 ただし、MBAM 操作を管理するには、次の ActiveDirectoryDomainServices グローバルグループを作成することをお勧めします。

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
<td align="left"><p>このグループを作成して、MBAM セットアップで作成された MBAM Advanced ヘルプデスクユーザーのローカルグループのメンバーを管理します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM コンプライアンス監査データベースアクセス</p></td>
<td align="left"><p>Mbam セットアップで作成された MBAM コンプライアンス監査 DB Access ローカルグループのメンバーを管理するには、このグループを作成します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM ヘルプデスクユーザー</p></td>
<td align="left"><p>このグループを作成すると、MBAM セットアップで作成された MBAM ヘルプデスクユーザーのローカルグループのメンバーを管理できます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 回復とハードウェアデータベースへのアクセス</p></td>
<td align="left"><p>このグループを作成して、MBAM セットアップで作成された MBAM Recovery とハードウェア DB Access ローカルグループのメンバーを管理します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM レポートユーザー</p></td>
<td align="left"><p>Mbam セットアップで作成された MBAM レポートのローカルグループのメンバーを管理するには、このグループを作成します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM システム管理者</p></td>
<td align="left"><p>このグループを作成して、MBAM セットアップで作成した MBAM システム管理者ローカルグループのメンバーを管理します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>BitLocker 暗号化の除外</p></td>
<td align="left"><p>このグループを作成して、ログオン先のコンピューターで開始する BitLocker 暗号化から除外する必要があるユーザーアカウントを管理します。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="-------------mbam-server-local-groups"></a> MBAM サーバーのローカルグループ

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
<td align="left"><p>このグループのメンバーは、MBAM からのヘルプデスク機能へのアクセス権を強化しています。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM コンプライアンス監査データベースアクセス</p></td>
<td align="left"><p>MBAM コンプライアンスおよび監査データベースへのアクセス権を持つコンピューターが含まれています。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM ヘルプデスクユーザー</p></td>
<td align="left"><p>このグループのメンバーは、MBAM のヘルプデスクの一部の機能にアクセスできます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM 回復とハードウェアデータベースへのアクセス</p></td>
<td align="left"><p>MBAM 回復データベースへのアクセス権を持つコンピューターが含まれています。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM レポートユーザー</p></td>
<td align="left"><p>このグループのメンバーは、MBAM からのコンプライアンスおよび監査レポートにアクセスできます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM システム管理者</p></td>
<td align="left"><p>このグループのメンバーは、すべての MBAM 機能にアクセスできます。</p></td>
</tr>
</tbody>
</table>

 

### SSRS レポートサービスアカウント

SSRS レポートサービスアカウントは、SSRS で利用可能な MBAM レポートを実行するためのセキュリティコンテキストを提供します。 これは、MBAM セットアップ中に構成されます。

SSRS レポートサービスアカウントを構成する場合は、ドメインユーザーアカウントを指定し、有効期限が切れないようにパスワードを構成します。

**注** MBAM の展開後にサービスアカウントの名前を変更する場合は、新しいサービスアカウントの資格情報を使用するようにレポートデータソースを再設定する必要があります。 そうしないと、ヘルプデスクポータルにアクセスできなくなります。

 

## <a href="" id="---------mbam-log-files"></a> MBAM ログファイル


MBAM セットアップ中に、インストールユーザーの% temp% フォルダーに、次の MBAM セットアップログファイルが作成されます。

**MBAM サーバーセットアップログファイル**

<a href="" id="msi-five-random-characters--log"></a>MSI <em> &lt; 5 ランダム文字 &gt; </em> ログ  
MBAM セットアップおよび MBAM サーバー機能のインストール中に実行されたアクションをログに記録します。

<a href="" id="installcompliancedatabase-log"></a>InstallComplianceDatabase  
MBAM コンプライアンスと監査データベースの設定を作成するために実行されたアクションをログに記録します。

<a href="" id="installkeycompliancedatabase-log"></a>InstallKeyComplianceDatabase  
MBAM 回復データベースを作成するために実行されたアクションをログに記録します。

<a href="" id="addhelpdeskdbauditusers-log"></a>Addhelpdbauditusers .log  
MBAM コンプライアンスおよび監査データベース上で SQL Server ログインを作成するために実行されたアクションをログに記録し、レポートのデータベースに対してヘルプデスク web サービスを承認します。

<a href="" id="addhelpdeskdbusers-log"></a>Addhelpdbusers .log  
キーの回復のために web サービスをデータベースに承認するために実行されたアクションをログに記録し、MBAM 回復データベースへのログインを作成します。

<a href="" id="addkeycompliancedbusers-log"></a>AddKeyComplianceDbUsers  
Web サービスを認証するために実行された操作を、コンプライアンスレポートのための MBAM コンプライアンスおよび監査データベースに記録します。

<a href="" id="addrecoveryandhardwaredbusers-log"></a>Addrecoveryandハードウェア Dbusers .log  
Web サービスをキー回復用の MBAM 回復データベースに承認するために実行されたアクションをログに記録します。

**注** MBAM セットアップログファイルを追加するには、msiexec.exe パッケージと/L location オプションを使用して MBAM をインストールする必要があり &lt; &gt; ます。 指定した場所でログファイルが作成されます。

 

**MBAM クライアントのセットアップログファイル**

<a href="" id="msi-five-random-characters--log"></a>MSI <em> &lt; 5 ランダム文字 &gt; </em> ログ  
MBAM クライアントのインストール中に実行されたアクションをログに記録します。

## <a href="" id="---------mbam-database-tde-considerations"></a> MBAM データベースの除外の考慮事項


SQL Server で使用できる透過データ暗号化 (TDE) 機能は、MBAM データベース機能をホストするデータベースインスタンスのオプションのインストールです。

TDE では、リアルタイムの完全なデータベースレベルの暗号化を実行できます。 TDE は、法令遵守または企業データセキュリティ標準に準拠するために、一括暗号化に最適な選択肢です。 TDE は、2つの Windows 機能 (暗号化ファイルシステム (EFS) と BitLocker ドライブ暗号化) に似ていますが、どちらもハードドライブ上のデータを暗号化します。 TDE では、セルレベルの暗号化、EFS、または BitLocker は置き換えられません。

データベースで TDE を有効にすると、すべてのバックアップが暗号化されます。 そのため、データベース暗号化キーを保護するために使用された証明書がバックアップされ、データベースのバックアップと維持されるように、特別な注意を払う必要があります。 この証明書 (または証明書) が失われると、データを読み取ることができなくなります。 データベースと共に証明書をバックアップします。 各証明書のバックアップには、2つのファイルが必要です。 これらのファイルはどちらもアーカイブする必要があります (理想的には、セキュリティのためにデータベースのバックアップファイルとは別に用意されています)。 または、拡張キー管理 (EKM) 機能の使用を検討してください (「拡張キー管理」を参照してください)。

MBAM データベースインスタンスの TDE を有効にする方法の例については、「 [mbam 2.0 の評価](evaluating-mbam-20-mbam-2.md)」を参照してください。

SQLServer 2008 の TDE の詳細については、「 [SQL Server の暗号化]( https://go.microsoft.com/fwlink/?LinkId=299883)」を参照してください。

## 関連トピック


[MBAM 2.0 のセキュリティとプライバシー](security-and-privacy-for-mbam-20-mbam-2.md)

 

 





