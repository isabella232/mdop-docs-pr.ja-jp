---
title: Configuration Manager による MBAM の展開計画
description: Configuration Manager による MBAM の展開計画
author: dansimp
ms.assetid: fb768306-48c2-40b4-ac4e-c279db987391
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e8588ce03c86a8a5138d591327e5f95503dce5ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825627"
---
# Configuration Manager による MBAM の展開計画


Configuration Manager トポロジで MBAM を展開するには、20万クライアントをサポートする3つのサーバーアーキテクチャが推奨されます。 Configuration Manager を実行するには、別のサーバーを使用し、[[はじめ](getting-started---using-mbam-with-configuration-manager.md)に] のアーキテクチャイメージに示されているように、2つのサーバーに基本的な管理機能と監視機能をインストールします。

**重要**  
Configuration Manager 2007 で MBAM の統合トポロジをインストールする場合、Windows To Go はサポートされません。



## MBAM を Configuration Manager にインストールするための展開の前提条件


MBAM を Configuration Manager にインストールする前に、次の前提条件を満たしていることを確認します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">受講</th>
<th align="left">追加情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Configuration Manager サーバーが Configuration Manager システムのプライマリサイトであることを確認します。</p></td>
<td align="left"><p>なし</p></td>
</tr>
<tr class="even">
<td align="left"><p>Configuration Manager サーバーでハードウェアインベントリクライアントエージェントを有効にします。</p></td>
<td align="left"><p>Configuration Manager 2007 については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=301656" data-raw-source="[How to Configure Hardware Inventory for a Site](https://go.microsoft.com/fwlink/?LinkId=301656)"> サイトのハードウェアインベントリを構成する方法」を参照してください </a> 。</p>
<p>System Center 2012 構成マネージャーについては、「 <a href="https://go.microsoft.com/fwlink/?LinkId=301685" data-raw-source="[How to Configure Hardware Inventory in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301685)"> 構成マネージャーでハードウェアインベントリを構成する方法」を参照してください </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>使用している Configuration Manager のバージョンに応じて、目的の構成管理 (DCM) エージェントまたはコンプライアンス設定を有効にします。</p></td>
<td align="left"><p>Configuration Manager 2007 の場合は、[ <a href="https://go.microsoft.com/fwlink/?LinkId=301686" data-raw-source="[Desired Configuration Management Client Agent Properties](https://go.microsoft.com/fwlink/?LinkId=301686)"> 必要な構成管理クライアントエージェントのプロパティを確認する] を有効にし </a> ます。</p>
<p>System Center 2012 構成マネージャーについては、「 <a href="https://go.microsoft.com/fwlink/?LinkId=301687" data-raw-source="[Configuring Compliance Settings in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301687)"> 構成マネージャーでコンプライアンス設定を構成する」を参照してください </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>構成マネージャーでレポートサービスポイントを定義します。 SQL Reporting Services の場合は必須です。</p></td>
<td align="left"><p>Configuration Manager 2007 については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=301688" data-raw-source="[How to Create a Reporting Services Point for SQL Reporting Services](https://go.microsoft.com/fwlink/?LinkId=301688)"> SQL Reporting services 用のレポートサービスポイントを作成する方法」を参照してください </a> 。</p>
<p>System Center 2012 構成マネージャーについては、「 <a href="https://go.microsoft.com/fwlink/?LinkId=301689" data-raw-source="[Prerequisites for Reporting in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301689)"> 構成マネージャーでレポートを作成するための前提条件」を参照してください </a> 。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="---------configuration-manager-supported-versions"></a> Configuration Manager でサポートされているバージョン


MBAM は次のバージョンの Configuration Manager をサポートしています。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">サポートされているバージョン</th>
<th align="left">Service pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft System Center Configuration Manager 2007 R2</p></td>
<td align="left"><p>SP1 以降</p></td>
<td align="left"><p>64 ビット</p>
<div class="alert">
<strong>注</strong><br/><p>Configuration Manager 2007 は32ビットですが、64ビット MBAM ソフトウェアと一致させるためには、64ビットのオペレーティングシステムにインストールする必要があります。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft System Center 2012 構成マネージャー</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
</tbody>
</table>



Configuration Manager サーバーでサポートされている構成の一覧については、使用している Configuration Manager のバージョンに対応した web ページを参照してください。 MBAM には、Configuration Manager サーバーに関する追加のシステム要件はありません。

## <a href="" id="---------mbam-and-sql-server-system-requirements"></a> MBAM と SQL Server のシステム要件


MBAM サーバーおよび Configuration Manager トポロジの SQL Server でサポートされる構成とシステム要件は、スタンドアロントポロジの場合と同じです。 単体システム要件については、「 [Mbam 2.0 でサポートされている構成](mbam-20-supported-configurations-mbam-2.md)」を参照してください。 MBAM サーバーと SQL Server プロセッサ、RAM、および Configuration Manager のトポロジに必要なディスク容量の要件については、次のセクションを参照してください。

## MBAM サーバプロセッサ、RAM、および MBAM のディスク容量要件


次の表は、Configuration Manager の統合トポロジを使用している場合に、MBAM サーバーのサーバープロセッサ、RAM、およびディスク領域の要件を示しています。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ハードウェアコンポーネント</th>
<th align="left">最小要件</th>
<th align="left">推奨要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>処理者</p></td>
<td align="left"><p>2.33 GHz</p></td>
<td align="left"><p>2.33 GHz 以上</p></td>
</tr>
<tr class="even">
<td align="left"><p>RAM</p></td>
<td align="left"><p>4 GB</p></td>
<td align="left"><p>8 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>空きディスク領域</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>2 GB</p></td>
</tr>
</tbody>
</table>



## SQL Server プロセッサ、RAM、ディスク容量の要件


次の表は、構成マネージャーの統合トポロジを使用している場合の SQL Server コンピューターのサーバープロセッサ、RAM、ディスク容量の要件を示しています。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ハードウェアコンポーネント</th>
<th align="left">最小要件</th>
<th align="left">推奨要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>処理者</p></td>
<td align="left"><p>2.33 GHz</p></td>
<td align="left"><p>2.33 GHz 以上</p></td>
</tr>
<tr class="even">
<td align="left"><p>RAM</p></td>
<td align="left"><p>4 GB</p></td>
<td align="left"><p>8 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>空きディスク領域</p></td>
<td align="left"><p>5 GB</p></td>
<td align="left"><p>5 GB 以上</p></td>
</tr>
</tbody>
</table>



## MBAM サーバーをインストールするのに必要な権限


Configuration Manager を使用して MBAM をインストールするには、次の表に示されている最低限の権限を持つセキュリティロールを持つ、構成マネージャーの管理者ユーザーがいる必要があります。 また、この表には、MBAM サーバーをインストールするために、基本的なコンピューターの管理者権限以外に必要な権限が表示されています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">アクセス許可</th>
<th align="left">MBAM サーバー機能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>SQL インスタンスログインサーバーロール:-dbcreator-processadmin</p></td>
<td align="left"><p>- 回復データベース-監査データベース</p></td>
</tr>
<tr class="even">
<td align="left"><p>SQL Server Reporting Services インスタンスの権限:-フォルダーの作成-レポートの発行</p></td>
<td align="left"><p>- System Center Configuration Manager の統合</p></td>
</tr>
</tbody>
</table>



**System Center 2012 Configuration Manager**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">アクセス許可</th>
<th align="left">Configuration Manager サーバー機能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Configuration Manager サイトの権限:-読み取り</p></td>
<td align="left"><p>System Center Configuration Manager の統合</p></td>
</tr>
<tr class="even">
<td align="left"><p>Configuration Manager コレクションの権限:-作成-削除-読み取り-修正-構成アイテムの展開</p></td>
<td align="left"><p>System Center Configuration Manager の統合</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Configuration Manager 構成項目の権限:-作成-削除-読み取り</p></td>
<td align="left"><p>System Center Configuration Manager の統合</p></td>
</tr>
</tbody>
</table>



**Configuration Manager 2007**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">アクセス許可</th>
<th align="left">Configuration Manager サーバー機能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Configuration Manager サイトの権限:-読み取り</p></td>
<td align="left"><p>System Center Configuration Manager の統合</p></td>
</tr>
<tr class="even">
<td align="left"><p>Configuration Manager コレクションの権限:-作成-削除-読み取り専用リソース</p></td>
<td align="left"><p>System Center Configuration Manager の統合</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Configuration Manager 構成項目の権限:-作成-削除-読み取り-配布</p></td>
<td align="left"><p>System Center Configuration Manager の統合</p></td>
</tr>
</tbody>
</table>



## Configuration Manager トポロジ用の MBAM 機能の展開順序


Configuration Manager サーバーに MBAM を展開する場合は、次の順序で展開タスクを完了する必要があります。

1.  Configuration Manager サーバーで構成の .mof ファイルを編集します。

2.  Sms \ _def のファイル構成マネージャーサーバーを作成または編集します。

3.  Configuration Manager サーバーに MBAM をインストールします。

4.  データベースサーバーに回復データベースと監査データベースをインストールします。

5.  管理/監視サーバーに MBAM 機能をインストールします。

## MBAM を Configuration Manager と共にインストールするための計画チェックリスト


このチェックリストは、推奨される手順と、構成マネージャーを使用して展開を監視するために Microsoft BitLocker の管理と監視を計画する際に考慮する項目の概要を示しています。 このチェックリストをスプレッドシートプログラムにコピーして、用途に合わせてカスタマイズすることをお勧めします。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">タスク</th>
<th align="left">参照先</th>
<th align="left">備考</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>「はじめに」の情報を確認します。これは、Configuration Manager と MBAM の連携方法と、推奨される高レベルのアーキテクチャを示しています。</p></td>
<td align="left"><p><a href="getting-started---using-mbam-with-configuration-manager.md" data-raw-source="[Getting Started - Using MBAM with Configuration Manager](getting-started---using-mbam-with-configuration-manager.md)">はじめに - MBAM と Configuration Manager の使用</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>展開の前提条件、サポートされている構成、必要なアクセス許可、および各機能の展開順序について説明する計画情報を確認します。</p></td>
<td align="left"><p>Configuration Manager による MBAM の展開計画</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM グループポリシー要件を計画して構成します。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-group-policy-requirements-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md)">MBAM 2.0 グループ ポリシー要件の計画</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>必要な Active Directory ドメインサービスセキュリティグループを計画して作成し、MBAM ローカルセキュリティグループメンバーシップの要件を計画します。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)">MBAM 2.0 管理者ロールの計画</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM クライアント展開の展開を計画します。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-client-deployment-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Client Deployment](planning-for-mbam-20-client-deployment-mbam-2.md)">MBAM 2.0 クライアントの展開計画</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## 関連トピック


[MBAM と Configuration Manager の使用](using-mbam-with-configuration-manager.md)









