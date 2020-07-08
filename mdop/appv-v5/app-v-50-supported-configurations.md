---
title: App-V 5.0 でサポートされる構成
description: App-V 5.0 でサポートされる構成
author: dansimp
ms.assetid: 3787ff63-7ce7-45a8-8f01-81b4b6dced34
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 60236743d2a6b418ca7f4705168a7bf064b82156
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814787"
---
# App-V 5.0 でサポートされる構成


このトピックでは、お客様の環境に Microsoft Application Virtualization (App-v) 5.0 をインストールして実行するために必要な要件を示します。

**重要**  
**この記事でサポートされている構成は、app-v 5.0 にのみ適用さ**れます。 App-v 5.0 Service Pack に適用される構成については、次の web ページを参照してください。

-   [App-V 5.0 SP1 の新機能](whats-new-in-app-v-50-sp1.md)

-   [App-V 5.0 SP2 について](about-app-v-50-sp2.md)

-   [App-V 5.0 SP3 でサポートされる構成](app-v-50-sp3-supported-configurations.md)



## <a href="" id="---------app-v-5-0-server-system-requirements"></a> App-v 5.0 server のシステム要件


**重要**  
App-v 5.0 サーバーでは、次のシナリオはサポートされていません。



-   Microsoft Windows Server Core を実行しているコンピューターへの展開。

-   以前のバージョンの App-v 5.0 サーバーコンポーネントを実行しているコンピューターへの展開。

    **注**  
    App-v 5.0 をインストールするには、アプリ-V 4.5 ライトストリーミングサーバー (LWS) サーバーのみを使用します。 App-v 5.0 アプリケーションの仮想化管理サービス (HWS) サーバー4.5 とのアプリの展開は、サポートされていません。



-   Microsoft SQL Server Express edition を実行しているコンピューターへの展開。

-   管理サーバーデータベースまたはレポートデータベースのリモート展開。 データベースのインストールを成功させるには、インストーラーを Microsoft SQL を実行しているコンピューター上で直接実行する必要があります。

-   ドメインコントローラーへの展開。

-   短いパスはサポートされません。 短いパスの使用を計画している場合は、新しいボリュームを作成する必要があります。

### 管理サーバーのオペレーティングシステム要件

次の表は、App-v 5.0 management server のインストールでサポートされているオペレーティングシステムを示しています。

**注**  
Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。 お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。 Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">エディション</th>
<th align="left">Service pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2008 (標準、エンタープライズ、データセンター、または Web サーバー)</p></td>
<td align="left"><p>もたらし</p></td>
<td align="left"><p>SP1 以降</p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2012 (標準、データセンター)</p></td>
<td align="left"><p></p></td>
<td align="left"></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012 (標準、データセンター)</p></td>
<td align="left"><p>もたらし</p></td>
<td align="left"></td>
<td align="left"><p>64 ビット</p></td>
</tr>
</tbody>
</table>



**重要**  
リモートデスクトップ共有 (RDS) が有効になっているコンピューターへの管理サーバーの役割の展開はサポートされていません。



### <a href="" id="management-server-hardware-requirements-"></a>管理サーバーのハードウェア要件

-   プロセッサ: 1.4 GHz 以上、64ビット (x64) プロセッサ

-   RAM: 1 GB RAM (64 ビット)

-   ディスク領域: 200 MB のハードディスク領域。コンテンツディレクトリは含まれません。

### 発行サーバーのオペレーティングシステム要件

次の表は、App-v 5.0 発行サーバーのインストールでサポートされているオペレーティングシステムを示しています。

**注**  
Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。 お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。 Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">エディション</th>
<th align="left">Service pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2008 (標準、エンタープライズ、データセンター、または Web サーバー)</p></td>
<td align="left"><p>もたらし</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2012 (標準、データセンター)</p></td>
<td align="left"><p></p></td>
<td align="left"></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012 (標準、データセンター)</p></td>
<td align="left"><p>もたらし</p></td>
<td align="left"></td>
<td align="left"><p>64 ビット</p></td>
</tr>
</tbody>
</table>



### <a href="" id="publishing-server-hardware-requirements-"></a>発行サーバーのハードウェア要件

-   プロセッサー (1.4 GHz 以上)。 64ビット (x64) プロセッサ

-   RAM: 2 GB RAM (64 ビット)

-   ディスク領域: 200 MB のハードディスク領域。 コンテンツディレクトリを含まない

### レポートサーバーのオペレーティングシステム要件

次の表は、App-v 5.0 reporting server のインストールでサポートされているオペレーティングシステムを示しています。

**注**  
Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。 お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。 Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">エディション</th>
<th align="left">Service Pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2008 (標準、エンタープライズ、データセンター、または Web サーバー)</p></td>
<td align="left"><p>もたらし</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2012 (標準、データセンター)</p></td>
<td align="left"><p></p></td>
<td align="left"></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012 (標準、データセンター)</p></td>
<td align="left"><p>もたらし</p></td>
<td align="left"></td>
<td align="left"><p>64 ビット</p></td>
</tr>
</tbody>
</table>



### <a href="" id="reporting-server-hardware-requirements-"></a>レポートサーバーのハードウェア要件

-   プロセッサー (1.4 GHz 以上)。 64ビット (x64) プロセッサ

-   RAM: 2 GB RAM (64 ビット)

-   ディスク領域: 200 MB のハードディスク空き容量

### <a href="" id="sql-server-database-requirements-"></a>SQL Server データベースの要件

次の表は、App-v 5.0 データベースとサーバーのインストールでサポートされている SQL Server のバージョンを示しています。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v 5.0 サーバーの種類</th>
<th align="left">SQL Server のバージョン</th>
<th align="left">エディション</th>
<th align="left">Service pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>管理/レポート作成</p></td>
<td align="left"><p>Microsoft SQL Server 2008</p>
<p>(標準、Enterprise、Datacenter、または Developer エディション: <strong>データベースエンジンサービス </strong> )</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>管理/レポート作成</p></td>
<td align="left"><p>Microsoft SQL Server 2008 </p>
<p>(標準、Enterprise、Datacenter、または Developer エディション: <strong>データベースエンジンサービス </strong> )</p></td>
<td align="left"><p>もたらし</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>管理/レポート作成</p></td>
<td align="left"><p>Microsoft SQL Server 2012</p>
<p>(標準、Enterprise、Datacenter、または Developer エディション: <strong>データベースエンジンサービス </strong> )</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-client-supp-cfgs"></a> App-v 5.0 クライアントシステム要件


次の表は、App-v 5.0 クライアントのインストールでサポートされているオペレーティングシステムを示しています。

**注**  
Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。 お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。 Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。



<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">Service pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows 7</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows 8</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><div class="alert">
<strong>重要</strong><br/><p>Windows 8.1 は、app-v 5.0 SP2 でのみサポートされます。</p>
</div>
<div>

</div>
<p>Windows 8.1</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
</tbody>
</table>



次のような App-v クライアントインストールシナリオはサポートされていません。記載されている場合を除きます。

-   Windows Server を実行しているコンピューター

-   App-v 4.6 SP1 またはそれ以前のバージョンを実行しているコンピューター

-   App-v 5.0 リモートデスクトップサービスクライアントは、RDS 対応サーバーでのみサポートされます。

### <a href="" id="client-hardware-requirements-"></a>クライアントハードウェア要件

次の一覧は、App-v 5.0 クライアントのインストールでサポートされているハードウェア構成を示しています。

-   プロセッサ: 1.4 GHz 以上32ビット (x86) または64ビット (x64) プロセッサ

-   RAM: 1 GB (32 ビット) または 2 GB (64 ビット)

-   ディスク: 100 MB インストールの場合、仮想化されたアプリケーションによって使用されるディスク領域は含まれません。

## <a href="" id="---------app-v-5-0-remote-desktop-client-system-requirements"></a> App-v 5.0 リモートデスクトップクライアントシステム要件


次の表は、App-v 5.0 リモートデスクトップクライアントのインストールでサポートされているオペレーティングシステムを示しています。

**注**  
Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。 お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。 Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。



オペレーティングシステムエディションの Service pack Microsoft Windows Server 2008

もたらし

SP1

Microsoft Windows Server 2012

**重要**  
Windows Server 2012 R2 は、App-v 5.0 SP2 でのみサポートされます。



Microsoft Windows Server 2012 (標準、データセンター)

もたらし

64 ビット



### <a href="" id="remote-desktop-client-hardware-requirements-"></a>リモートデスクトップクライアントハードウェア要件

次の一覧は、App-v 5.0 クライアントのインストールでサポートされているハードウェア構成を示しています。

-   プロセッサ: 1.4 GHz 以上32ビット (x86) または64ビット (x64) プロセッサ

-   RAM: 1 GB (32 ビット) または 2 GB (64 ビット)

-   ディスク: 100 MB インストールの場合、仮想化されたアプリケーションによって使用されるディスク領域は含まれません。

## <a href="" id="---------app-v-5-0-sequencer-system-requirements"></a> App-v 5.0 Sequencer システム要件


次の表は、App-v 5.0 Sequencer のインストールでサポートされているオペレーティングシステムを示しています。

**注**  
Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。 お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。 Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">エディション</th>
<th align="left">Service pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows 7</p></td>
<td align="left"></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 ビットと 64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows 8</p></td>
<td align="left"></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットと 64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><div class="alert">
<strong>重要</strong><br/><p>Windows 8.1 は、app-v 5.0 SP2 でのみサポートされます。</p>
</div>
<div>

</div>
<p>Windows 8.1</p></td>
<td align="left"></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2008</p></td>
<td align="left"><p>もたらし</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 ビットと 64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012</p></td>
<td align="left"></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットと 64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><div class="alert">
<strong>重要</strong><br/><p>Windows Server 2012 R2 は、App-v 5.0 SP2 でのみサポートされます。</p>
</div>
<div>

</div>
<p>Microsoft Windows Server 2012</p></td>
<td align="left"><p>もたらし</p></td>
<td align="left"></td>
<td align="left"><p>64 ビット</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-supp-ver-sccm"></a>サポートされている System Center Configuration Manager のバージョン


Microsoft System Center 2012 Configuration Manager または System Center 2012 R2 構成マネージャーを使用して、App-v 仮想アプリケーション、レポート、その他の機能を管理できます。 次の表は、各バージョンの App-v でサポートされている Configuration Manager のバージョンを示しています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">サポートされている Configuration Manager バージョン</th>
<th align="left">App-v のバージョン</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft System Center 2012 構成マネージャー</p></td>
<td align="left"><ul>
<li><p>App-v 5.0</p></li>
<li><p>App-v 5.0 SP1</p></li>
<li><p>App-v 5.0 SP2</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>System Center 2012 R2 Configuration Manager</p></td>
<td align="left"><ul>
<li><p>App-v 5.0</p></li>
<li><p>App-v 5.0 SP1</p></li>
<li><p>App-v 5.0 SP2</p></li>
</ul></td>
</tr>
</tbody>
</table>



Configuration Manager と App-v の統合の詳細については、「 [Configuration manager を使用した app-v との統合の計画](https://technet.microsoft.com/library/jj822982.aspx)」を参照してください。






## 関連トピック


[App-V の展開計画](planning-to-deploy-app-v.md)

[App-V 5.0 の前提条件](app-v-50-prerequisites.md)









