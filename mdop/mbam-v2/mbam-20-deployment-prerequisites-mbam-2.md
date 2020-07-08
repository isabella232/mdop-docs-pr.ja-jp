---
title: MBAM 2.0 展開の前提条件
description: MBAM 2.0 展開の前提条件
author: dansimp
ms.assetid: 57d1c2bb-5ea3-457e-badd-dd9206ff0f20
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ef7ee64a3661009f18e0963d738c57a59885cb20
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826014"
---
# MBAM 2.0 展開の前提条件


Microsoft BitLocker の管理と監視 (MBAM) セットアップを始める前に、製品をインストールするための前提条件を満たしていることを確認する必要があります。 このセクションには、Microsoft BitLocker の管理および監視サーバーの機能とクライアントを展開する前に、コンピューティング環境の計画を成功させるために役立つ情報が含まれています。 MBAM を Configuration Manager にインストールする場合は、「 [Configuration manager を使用して MBAM を展開する](planning-to-deploy-mbam-with-configuration-manager-2.md)場合の計画」を参照してください。

## MBAM Server 機能のインストールの前提条件


Mbam 機能を正常にインストールするには、MBAM サーバーの各機能について特定の前提条件を満たしている必要があります。 MBAM セットアップインストールを開始する前に、すべての前提条件が満たされていることを確認します。

### 管理および監視サーバーの前提条件

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
<td align="left"><p><strong>Windows Server Web サーバーの役割</strong></p></td>
<td align="left"><p>この役割は、管理と監視サーバー機能でサポートされているサーバーオペレーティングシステムに追加する必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Web サーバー (IIS) 管理ツール</strong></p></td>
<td align="left"><p>[ <strong> IIS 管理スクリプトとツール] を選び </strong> ます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>SSL 証明書</strong></p></td>
<td align="left"><p>省略可能。 クライアントと web サービス間の通信をセキュリティで保護するために、信頼されたセキュリティ機関が署名した証明書を取得してインストールする必要があります。</p></td>
</tr>
<tr class="even">
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
<tr class="odd">
<td align="left"><p><strong>Windows Server の機能</strong></p></td>
<td align="left"><p><strong>.NET Framework 3.5.1 の機能:</strong></p>
<ul>
<li><p>.NET Framework 3.5.1</p></li>
<li><p>WCF のアクティブ化</p>
<ul>
<li><p>HTTP アクティベーション</p></li>
<li><p>HTTP 以外のアクティベーション</p></li>
</ul></li>
</ul>
<p><strong>Windows プロセスアクティブ化サービス:</strong></p>
<ul>
<li><p>プロセスモデル</p></li>
<li><p>.NET 環境</p></li>
<li><p>構成 Api</p></li>
</ul></td>
</tr>
</tbody>
</table>



**注**  
サポートされているオペレーティングシステムの一覧については、「 [Mbam 2.0 でサポートされている構成](mbam-20-supported-configurations-mbam-2.md)」を参照してください。



### コンプライアンスおよび監査レポートの前提条件

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
<td align="left"><p>サポートされているバージョンの SQL Server</p>
<p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"> </a> サポートされているバージョン用の mbam 2.0 サポートされている構成</p></td>
<td align="left"><p>次のような SQL Server をインストールします。</p>
<ul>
<li><p>SQL_Latin1_General_CP1_CI_AS の照合</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>SQL Server Reporting Services (SSRS)</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>SSRS インスタンスの権限–レポートからデータベースを個別のサーバーにインストールする場合にのみ、レポートをインストールする必要があります。</p></td>
<td align="left"><p>必要なインスタンスの権限:</p>
<ul>
<li><p>フォルダーを作成する</p></li>
<li><p>レポートを発行する</p></li>
</ul>
<p>SSRS は、MBAM サーバのインストール中にインストールして実行する必要があります。 SSRS は "ネイティブ" モードで、未構成または "SharePoint" モードでは構成されません。</p></td>
</tr>
</tbody>
</table>



### 回復データベースの前提条件

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
<td align="left"><p>サポートされているバージョンの SQL Server</p>
<p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"> </a> サポートされているバージョン用の mbam 2.0 サポートされている構成</p></td>
<td align="left"><p>次のような SQL Server をインストールします。</p>
<ul>
<li><p>SQL_Latin1_General_CP1_CI_AS の照合</p></li>
<li><p>SQL Server 管理ツール</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>必須の SQL Server 権限</p></td>
<td align="left"><p>必要な権限:</p>
<ul>
<li><p>SQL インスタンスログインサーバーの役割:</p>
<ul>
<li><p>dbcreator</p></li>
<li><p>processadmin</p></li>
</ul></li>
<li><p>SQL Server Reporting Services インスタンスの権限:</p>
<ul>
<li><p>フォルダーを作成する</p></li>
<li><p>レポートを発行する</p></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>オプション-透過的なデータ暗号化 (TDE) 機能をインストールする (SQL Server で利用可能)</p></td>
<td align="left"><p>TDE SQL Server 機能は、データとログファイルの入出力の暗号化と暗号化解除をリアルタイムで実行します。これは、さまざまな産業で確立された多くの法律、規制、ガイドラインに準拠するのに役立ちます。</p>
<div class="alert">
<strong>注</strong><br/><p>TDE は、データベース情報のリアルタイムの暗号化解除を実行します。つまり、ログオンしているアカウントに SQL Server テーブルの回復キー情報を表示しているときに、データベースへのアクセス許可が与えられている場合は、回復キーの情報が表示されます。</p>
</div>
<div>

</div>
<p>TDE: <a href="mbam-20-security-considerations-mbam-2.md" data-raw-source="[MBAM 2.0 Security Considerations](mbam-20-security-considerations-mbam-2.md)"> mbam 2.0 セキュリティに関する考慮事項 </a> の詳細。</p></td>
</tr>
</tbody>
</table>



### コンプライアンスおよび監査データベースの前提条件

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
<td align="left"><p>サポートされているバージョンの SQL Server</p>
<p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"> </a> サポートされているバージョン用の mbam 2.0 サポートされている構成</p></td>
<td align="left"><p>次のような SQL Server をインストールします。</p>
<ul>
<li><p>SQL_Latin1_General_CP1_CI_AS の照合</p></li>
<li><p>SQL Server 管理ツール</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>必須の SQL Server 権限</p></td>
<td align="left"><p>必要な権限:</p>
<ul>
<li><p>SQL インスタンスログインサーバーの役割:</p>
<ul>
<li><p>dbcreator</p></li>
<li><p>processadmin</p></li>
</ul></li>
<li><p>SQL Server Reporting Services インスタンスの権限:</p>
<ul>
<li><p>フォルダーを作成する</p></li>
<li><p>レポートを発行する</p></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>オプション-透過的データ暗号化 (TDE) 機能を SQL Server にインストールします。</p></td>
<td align="left"><p>TDE SQL Server 機能は、データとログファイルの入出力の暗号化と暗号化解除をリアルタイムで実行します。これは、さまざまな産業で確立された多くの法律、規制、ガイドラインに準拠するのに役立ちます。</p>
<div class="alert">
<strong>注</strong><br/><p>TDE は、データベース情報のリアルタイムの暗号化解除を実行します。つまり、ログオンしているアカウントに SQL Server テーブルの回復キー情報を表示しているときに、データベースへのアクセス許可が与えられている場合は、回復キーの情報が表示されます。</p>
</div>
<div>

</div>
<p>TDE: <a href="mbam-20-security-considerations-mbam-2.md" data-raw-source="[MBAM 2.0 Security Considerations](mbam-20-security-considerations-mbam-2.md)"> mbam 2.0 セキュリティの考慮事項の詳細</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>SQL Server では、MBAM サーバーのインストール中にデータベースエンジンサービスをインストールして実行する必要があります。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>SQL Server エージェントサービスが実行されていて、SQL Server の選択されたインスタンスで自動開始に設定されている必要があります。</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



### セルフサービスポータルの前提条件

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
<td align="left"><p>サポートされているバージョンの Windows Server</p>
<p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"> </a> サポートされているバージョン用の mbam 2.0 サポートされている構成</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>ASP.NET MVC 2.0</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=392270" data-raw-source="[ASP.NET MVC 2 download](https://go.microsoft.com/fwlink/?LinkId=392270)">ASP.NET MVC 2 ダウンロード</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Web サービス IIS 管理ツール</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## MBAM クライアントの前提条件


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
<td align="left"><p><strong>Windows 7 クライアントには </strong> - 、トラステッドプラットフォームモジュール (TPM) 機能が必要です。</p></td>
<td align="left"><p>TPM バージョンは、1.2 以降である必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>TPM チップは BIOS で有効になっていて、オペレーティングシステムから resettable されている必要があります。</p></td>
<td align="left"><p>詳細については、BIOS のマニュアルを参照してください。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Windows 8 クライアントのみ: MBAM の保存と管理には、tpm の自動プロビジョニング機能を無効にする必要があります。また、mbam は、mbam を </strong> 展開する前に tpm の所有者として設定する必要があります。 TPM 自動プロビジョニング機能を無効にするには、「Disable-TpmAutoProvisioning」を参照してください <a href="https://go.microsoft.com/fwlink/?LinkId=286468" data-raw-source="[Disable-TpmAutoProvisioning](https://go.microsoft.com/fwlink/?LinkId=286468)"> </a> 。</p>
<ul>
<li><p>TPM 自動プロビジョニング機能を無効にする必要があります。</p></li>
<li><p>MBAM を展開する前に、MBAM を TPM の所有者として設定する必要があります。</p></li>
</ul></td>
<td align="left"><p>TPM 自動プロビジョニング機能を無効にするには、「Disable-TpmAutoProvisioning」を参照してください <a href="https://go.microsoft.com/fwlink/?LinkId=286468" data-raw-source="[Disable-TpmAutoProvisioning](https://go.microsoft.com/fwlink/?LinkId=286468)"> </a> 。</p>
<div class="alert">
<strong>注</strong><br/><p>キーボード、ビデオ、マウスが直接接続されていて、キーボード、ビデオ、マウス (KVM) スイッチで管理されていないことを確認します。 KVM スイッチでは、コンピュータの物理機能がハードウェアの物理的な存在を検出してしまう可能性があります。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## 関連トピック


[MBAM 2.0 の展開計画](planning-to-deploy-mbam-20-mbam-2.md)

[MBAM 2.0 がサポートされる構成](mbam-20-supported-configurations-mbam-2.md)









