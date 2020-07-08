---
title: MBAM 1.0 展開の前提条件
description: MBAM 1.0 展開の前提条件
author: dansimp
ms.assetid: bd9e1010-7d25-43e7-8dc6-b521226a659d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6ed14343d37a859364bcabbe6ca72c041502a23c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822664"
---
# MBAM 1.0 展開の前提条件


Microsoft BitLocker の管理と監視 (MBAM) セットアップを始める前に、製品をインストールするために必要な前提条件を満たしていることを確認してください。 このセクションには、MBAM クライアントとサーバー機能を展開する前に、コンピューティング環境を正常に準備するための情報が記載されています。

## MBAM Server 機能のインストールの前提条件


MBAM サーバーの各機能には、適切にインストールする前に満たす必要がある特定の前提条件があります。 MBAM セットアップインストールを開始する前に、すべての前提条件が満たされているかどうかを確認します。

### 管理および監視サーバーのインストールの前提条件

次の表には、MBAM 管理および監視サーバーのインストールの前提条件が含まれています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">受講</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Windows ServerWeb サーバーの役割</strong></p></td>
<td align="left"><p>この役割は、mbam 管理および監視サーバー機能でサポートされているサーバーオペレーティングシステムに追加する必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Web サーバー (IIS) 管理ツール</strong></p></td>
<td align="left"><p><strong>IIS 管理スクリプトとツール</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Web サーバーの役割サービス</strong></p></td>
<td align="left"><p><strong>一般的な HTTP 機能:</strong></p>
<ul>
<li><p>静的なコンテンツ</p></li>
<li><p>既定のドキュメント</p></li>
</ul>
<p><strong>アプリケーション開発:</strong></p>
<ul>
<li><p>ASP.NET</p></li>
<li><p>.NET の拡張性</p></li>
<li><p>ISAPI 拡張機能</p></li>
<li><p>ISAPI フィルター</p></li>
</ul>
<p><strong>証券</strong></p>
<ul>
<li><p>Windows 認証</p></li>
<li><p>フィルターを要求する</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Windows Server の機能</strong></p></td>
<td align="left"><p><strong>Microsoft .NET Framework 3.5.1 の機能:</strong></p>
<ul>
<li><p>.NET Framework 3.5.1</p></li>
<li><p>WCF のアクティブ化</p>
<ul>
<li><p>HTTP アクティベーション</p></li>
<li><p>HTTP 以外のアクティベーション</p></li>
</ul></li>
</ul>
<p><strong>Windows プロセス アクティブ化サービス</strong></p>
<ul>
<li><p>プロセスモデル</p></li>
<li><p>.NET 環境</p></li>
<li><p>構成 Api</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**注** サポートされているオペレーティングシステムの一覧については、「 [Mbam 1.0 でサポートされている構成](mbam-10-supported-configurations.md)」を参照してください。

 

### コンプライアンスおよび監査レポートのインストールの前提条件

コンプライアンスレポートおよび監査レポートは、サポートされているバージョンの SQLServer にインストールする必要があります。 この機能のインストールの前提条件には、SQL Server Reporting Services (SSRS) が含まれます。

SSRS は、MBAM server のインストール中にインストールして実行する必要があります。 また、SSRS は、"未構成" または "SharePoint" モードではなく、"ネイティブ" モードで構成する必要があります。

**注** サポートされているオペレーティングシステムと SQLServer のバージョンの一覧については、「 [Mbam 1.0 でサポートされている構成](mbam-10-supported-configurations.md)」をご覧ください。

 

### 回復とハードウェアデータベースのインストールの前提条件

回復とハードウェアのデータベースは、サポートされているバージョンの SQLServer にインストールする必要があります。

SQL Server は、MBAM サーバーのインストール中にデータベースエンジンサービスをインストールして実行している必要があります。 Transparent Data Encryption (TDE) 機能を有効にする必要があります。

**注** サポートされているオペレーティングシステムと SQLServer のバージョンの一覧については、「 [Mbam 1.0 でサポートされている構成](mbam-10-supported-configurations.md)」をご覧ください。

 

TDE SQLServer 機能は、データとログファイルのリアルタイムの入出力 (i/o) 暗号化と暗号化解除を実行します。 TDE は、データとログファイルを含む "残りの部分" のデータを保護します。 これにより、さまざまな業界で確立されている多くの法律、規制、ガイドラインを遵守することができます。

**注** TDE はデータベース情報のリアルタイムの復号化を実行するため、回復キー情報の SQL テーブルを表示するときに、ログインしているアカウントにデータベースへのアクセス許可があるかどうかを確認することができます。

 

### コンプライアンスと監査データベースのインストールの前提条件

コンプライアンスと監査データベースは、サポートされているバージョンの SQLServer にインストールする必要があります。

SQL Server では、MBAM サーバーのインストール中にデータベースエンジンサービスをインストールして実行する必要があります。

**注** サポートされているオペレーティングシステムと SQLServer のバージョンの一覧については、「 [Mbam 1.0 でサポートされている構成](mbam-10-supported-configurations.md)」をご覧ください。

 

## MBAM クライアントのインストールの前提条件


MBAM クライアントのインストールを開始する前に満たす必要がある必須要件は、次のとおりです。

-   トラステッドプラットフォームモジュール (TPM) v 1.2 機能

-   TPM チップが BIOS で有効になっていて、オペレーティングシステムから resettable されている必要があります。 詳細については、BIOS のマニュアルを参照してください。

**警告** キーボード、ビデオ、マウス (KVM) スイッチではなく、キーボード、マウス、およびビデオがコンピューターに直接接続されていることを確認します。 KVM スイッチでは、コンピュータの物理機能がハードウェアの物理的な存在を検出してしまう可能性があります。

 

## 関連トピック


[MBAM 1.0 の展開計画](planning-to-deploy-mbam-10.md)

[MBAM 1.0 がサポートされる構成](mbam-10-supported-configurations.md)

 

 





