---
title: App-V 5.0 のレポート機能について
description: App-V 5.0 のレポート機能について
author: dansimp
ms.assetid: 27c33dda-f017-41e3-8a78-1b681543ec4f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a29585886aa20233f49c85101cff570a098c69ba
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815024"
---
# App-V 5.0 のレポート機能について


Microsoft Application Virtualization (App-v) 5.0 には、App-v 5.0 クライアントを実行しているコンピューターと仮想アプリケーションパッケージの使用状況に関する情報を収集するために役立つ組み込みのレポート機能が含まれています。 この情報を使用して、集中化されたデータベースからレポートを生成できます。

## <a href="" id="---------app-v-5-0-reporting-overview"></a> App-v 5.0 レポートの概要


次の一覧には、App-v 5.0 でレポートするためのエンドツーエンドの上位レベルのワークフローが表示されています。

1.  Microsoft Application Virtualization (App-v) 5.0 レポートサーバーには、次の前提条件があります。

    -   インターネットインフォメーションサービス (IIS) web サーバーの役割

    -   Windows 認証の役割 ([ **IIS/セキュリティ**] の下)

    -   Sql Server Reporting Services (SSRS) で SQL Server をインストールして実行する

    SQL Server Reporting Services が実行されていることを確認するには、 `http://localhost/Reports` app-v 5.0 レポートをホストするサーバーの管理者として web ブラウザーで表示します。 SQL Server Reporting Services のホームページが表示されます。

2.  App-v 5.0 レポートサーバーと関連データベースをインストールします。 レポートサーバーのインストールの詳細については、「[レポートサーバーをスタンドアロンコンピューターにインストールしてデータベースに接続する方法」を](how-to-install-the-reporting-server-on-a-standalone-computer-and-connect-it-to-the-database.md)参照してください。 App-v 5.0 クライアントを実行しているコンピューターが、レポートサーバーにデータを送信する時刻を構成します。

3.  構成マネージャーなどの電子ソフトウェア配布システムを使用してレポートを表示していない場合は、SQL Server Reporting Service でレポートを定義できます。 定義済みの appvshort レポートをダウンロードセンターからダウンロード <https://go.microsoft.com/fwlink/?LinkId=397255> します。

    **注** Configuration Manager との統合を App-v 5.0 と共に使用している場合、ほとんどのレポートは、App-v 5.0 ではなく構成マネージャーから生成されます。

     

4.  管理者として App-v 5.0 PowerShell モジュールをインポートした後 `Import-Module AppvClient` 、app-v 5.0 クライアントを有効にします。 このサンプル PowerShell コマンドレットでは、App-v 5.0 レポートを有効にできます。

    ``` syntax
    Set-AppvClientConfiguration –reportingserverurl <url>:<port> -reportingenabled 1 – ReportingStartTime <0-23> - ReportingRandomDelay <#min>
    ```

    App-v 5.0 レポートデータをすぐに送信するには、 `Send-AppvClientReport` app-v 5.0 クライアントで実行します。

    レポートが有効になっている App-v 5.0 クライアントのインストールの詳細については、「[クライアント構成の設定につい](about-client-configuration-settings.md)て」を参照してください。 Windows PowerShell を使用して App-v 5.0 のレポートを管理する方法については、「 [Powershell を使用して app-v 5.0 クライアントでレポートを有効にする方法](how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md)」を参照してください。

5.  レポートサーバーは、App-v 5.0 クライアントからデータを受信した後、データをレポートデータベースに送信します。 データベースがクライアントデータを受信して処理すると、成功応答がレポートサーバーに送信され、その後、通知が App-v 5.0 クライアントに送信されます。

6.  App-v 5.0 クライアントは、正常に完了通知を受け取ると、データキャッシュを空にして容量を節約します。

    **注** 既定では、サーバーがデータの受信を確認した後、キャッシュが消去されます。 データキャッシュを保存するようにクライアントを手動で構成することができます。

     

~~~
If the App-V 5.0 client device does not receive a success notification from the server, it retains data in the cache and tries to resend data at the next configured interval. Clients continue to collect data and add it to the cache.
~~~

### <a href="" id="-------------app-v-5-0-reporting-server-frequently-asked-questions"></a> App-v 5.0 レポートサーバーについてよく寄せられる質問

次の表は、App-v 5.0 レポートについてよく寄せられる質問に対する回答を示しています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">質問</th>
<th align="left">詳細情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>レポート情報がレポートデータベースに送信される頻度はどのようなものですか?</p></td>
<td align="left"><p>頻度は、App-v 5.0 クライアントを実行しているコンピューターでレポートタスクがどのように構成されているかによって異なります。 レポートデータを送信する頻度と間隔を構成する必要があります。 既定では、app-v 5.0 レポートは有効になっていません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>レポートサーバーデータベースにはどのような情報が格納されますか?</p></td>
<td align="left"><p>次の一覧は、レポートデータベースに保存されている内容を示しています。</p>
<ul>
<li><p>App-v 5.0 クライアントを実行しているコンピューターで実行されているオペレーティングシステム: ホスト名、バージョン、service pack、種類-クライアント/サーバー、プロセッサアーキテクチャ。</p></li>
<li><p>App-v 5.0 クライアント情報: バージョン。</p></li>
<li><p>公開されているパッケージの一覧: GUID、バージョン GUID、name。</p></li>
<li><p>アプリケーションの使用状況の情報: name、version、streaming server、user (domain\alias)、パッケージバージョン GUID、起動状態と時刻、シャットダウン時間。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>レポートサーバーに送信される情報の平均量は何ですか。</p></td>
<td align="left"><p>事によりけりです。 次のリストは、レポートサーバーに送信されたデータの3つのセットを示しています。</p>
<ol>
<li><p>オペレーティングシステムと App-v 5.0 クライアント情報。 このデータが送信されるたびに、最大150バイト。</p></li>
<li><p>公開されたパッケージの一覧。 30パッケージの場合は ~ 7 KB。 これは、パッケージリストが公開更新によって更新された場合にのみ送信されます。この処理はあまり行われません。変更がない場合、この情報は送信されません。</p></li>
<li><p>仮想アプリケーションの利用状況情報–1イベントあたり 0.25 KB。 情報を送信する前に両方が発生した場合に、開始と終了のカウントが1つのイベントとしてカウントされます。 スケジュールされたタスクを使って送信する場合、最後に正常にアップロードされたデータのみがサーバーに送信されます。 PowerShell コマンドレットを使用して手動で送信する場合は、次にデータを再送信する必要があるかどうかを制御するオプションの引数があります。その引数は <strong> DeleteOnSuccess です </strong> 。</p>
<p></p>
<p>たとえば、20個のアプリケーションを開いて閉じ、レポート情報を毎日送信する予定の場合、一般的な1日のトラフィックは 0.15 KB + 20 x 0.25 KB、または 5KB/ユーザーについてのことをお勧めします。</p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p>レポートのスケジュールを設定できますか?</p></td>
<td align="left"><p>はい、できます。 PowerShell コマンドレット (Send-AppvClientReport) を使って手動でレポートを送信する以外に <strong> </strong> 、タスクを自動的に実行するようにスケジュール設定することができます。 レポートのスケジュールを設定するには、次の2つの方法があります。</p>
<ol>
<li><p>PowerShell コマンドレット AppvClientConfiguration を使用し <strong> </strong> ます。 以下に例を示します。</p>
<p>Set-AppvClientConfiguration-ReportingEnabled 1-Reportingenabled<a href="http://any.com/appv-reporting" data-raw-source="http://any.com/appv-reporting">http://any.com/appv-reporting</a></p>
<p></p>
<p>クライアント構成の設定の完全な一覧については、「 <a href="about-client-configuration-settings.md" data-raw-source="[About Client Configuration Settings](about-client-configuration-settings.md)"> </a> <strong> reportingenabled </strong> 、 <strong> reportingenabled </strong> 、 <strong> reportingdatac、reportingenabled </strong> <strong> locksize </strong> 、 <strong> reportingenabled </strong> 、 <strong> ReportingRandomDelay </strong> 、 <strong> reportingenabled </strong> の各エントリを参照してください。</p>
<p></p></li>
<li><p>グループポリシーを使用する。 ドメインコントローラーを使用して配布されている場合、設定は前の一覧と同じです。</p>
<div class="alert">
<strong>注</strong><br/><p>グループポリシー設定は、PowerShell を使用して構成されたローカル設定よりも優先されます。</p>
</div>
<div>

</div></li>
</ol></td>
</tr>
</tbody>
</table>
 


## <a href="" id="---------app-v-5-0-client-reporting"></a> App-v 5.0 クライアントレポート


App-v 5.0 レポートを使用するには、App-v 5.0 クライアントをインストールして構成する必要があります。 クライアントがインストールされたら、 **AppVClientConfiguration** PowerShell コマンドレットまたは**ADMX テンプレート**を使用してレポートを構成します。 レポート機能のコマンドレットは、次のリンクを使用して使用できます。また、[**レポート**] の前にあります。 クライアント構成の設定の完全な一覧については、「[クライアント構成の設定につい](about-client-configuration-settings.md)て」を参照してください。 次のセクションでは、PowerShell を使用した App-v 5.0 クライアントレポート構成の例を示します。

### PowerShell を使用して App-v クライアントレポートを構成する

次の例は、PowerShell パラメーターを使用して、App-v 5.0 クライアントのレポート機能を構成する方法を示しています。

**注**  
次の構成タスクは、App-v 5.0 ADMX テンプレートのグループポリシー設定を使用して構成することもできます。 ADMX テンプレートの使用方法について詳しくは、「 [Admx テンプレートとグループポリシーを使用して app-v 5.0 クライアント構成を変更する方法](how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md)」をご覧ください。
 


**レポートを有効にし、app-v 5.0 クライアントを実行しているコンピューターでデータ収集を開始するに**は、次の操作を行います。

`Set-AppVClientConfiguration –ReportingEnabled 1`

**データを特定のレポートサーバーに自動的に送信するようにクライアントを構成するには、次の操作を**行います。

``` syntax
Set-AppVClientConfiguration –ReportingServerURL http://MyReportingServer:MyPort/ -ReportingStartTime 20 -ReportingInterval 1 -ReportingRandomDelay 30
```

`-ReportingInterval 1 -ReportingRandomDelay 30`

この例では、レポートデータをレポートサーバーの URL に自動的に送信するようにクライアントを構成し <strong> http://MyReportingServer:MyPort/ </strong> ます。 さらに、レポートデータは、セッションに生成されるランダム遅延に応じて、8:00 と 8:30 PM の間で毎日送信されます。

**クライアントのデータキャッシュのサイズを制限するに**は、次の操作を行います。

`Set-AppvClientConfiguration –ReportingDataCacheLimit 100`

アプリ-V 5.0 クライアントを実行しているコンピューター上のレポートキャッシュの最大サイズを 100 MB に構成します。 データをサーバーに送信する前に、キャッシュの制限に達した場合、ログはロールオーバーになり、データは必要に応じて上書きされます。

**クライアントとサーバーの間でネットワーク経由で転送されるデータブロックサイズを構成するには、次の操作を**行います。

`Set-AppvClientConfiguration –ReportingDataBlockSize 10240`

クライアントが 10240 MB に送信するデータブロックの最大値を指定します。

### 収集されるデータの種類

次の表は、App-v 5.0 レポートを使って収集できる情報の種類を示しています。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">クライアント情報</th>
<th align="left">パッケージ情報</th>
<th align="left">アプリケーションの使用状況</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ホスト名</p></td>
<td align="left"><p>パッケージ名</p></td>
<td align="left"><p>開始時刻と終了時刻</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 5.0 クライアントのバージョン</p></td>
<td align="left"><p>パッケージバージョン</p></td>
<td align="left"><p>実行状態</p></td>
</tr>
<tr class="odd">
<td align="left"><p>プロセッサのアーキテクチャ</p></td>
<td align="left"><p>パッケージソース</p></td>
<td align="left"><p>シャットダウンの状態</p></td>
</tr>
<tr class="even">
<td align="left"><p>オペレーティングシステムのバージョン</p></td>
<td align="left"><p>キャッシュ割合</p></td>
<td align="left"><p>アプリケーション名</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Service Pack レベル</p></td>
<td align="left"><p></p></td>
<td align="left"><p>アプリケーションのバージョン</p></td>
</tr>
<tr class="even">
<td align="left"><p>オペレーティングシステムの種類</p></td>
<td align="left"><p></p></td>
<td align="left"><p>ユーザー名</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>接続グループ</p></td>
</tr>
</tbody>
</table>
 


クライアントは、このデータを**xml**形式で収集して保存します。 データキャッシュは既定で非表示になっており、XML ファイルを開くには管理者権限が必要です。

### サーバーにデータを送信する

App-v 5.0 クライアントを実行しているコンピューターを構成して、指定したレポートサーバーにデータが自動的に送信されるようにすることができます。 サーバーを指定するには、 **AppvClientConfiguration**コマンドレットを使用して次の設定を行います。

-   ReportingEnabled

-   ReportingServerURL

-   ReportingStartTime

-   ReportingInterval

-   ReportingRandomDelay

前の設定を構成したら、スケジュールされたタスクを作成する必要があります。 スケジュールされたタスクは、 **Reportingserverurl**設定で指定されたサーバーに接続し、転送が開始されます。 スケジュールされた時間外にデータを手動で送信する場合は、次の PowerShell コマンドレットを使用します。

`Send-AppVClientReport –URL http://MyReportingServer:MyPort/ -DeleteOnSuccess`

レポートサーバーが以前に構成されている場合は、 **– URL**パラメーターを省略できます。 または、データを別の場所に送信する必要がある場合は、別の URL を指定して、このデータコレクションに対して構成された**Reportingserverurl**をオーバーライドします。

**-DeleteOnSuccess**パラメーターは、転送が成功した場合にデータキャッシュをクリアすることを示します。 指定しない場合、キャッシュは消去されません。

### 手動のデータ収集

また、 **AppVClientReport**コマンドレットを使用して手動でデータを収集することもできます。 このソリューションは、既存のレポートサーバーの場合に便利です。 次のリストは、レポートサーバーを使用してデータを収集するか、またはレポートサーバーを使わないかに関する情報を示します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">レポートサーバーでの操作</th>
<th align="left">レポートサーバーがない場合</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>既存の App-v 5.0 レポートサーバーがある場合は、カスタマイズされたスケジュールタスクまたはスクリプトを作成します。 クライアントが指定した場所に、目的の頻度でデータを送信することを指定します。</p></td>
<td align="left"><p>既存の App-v 5.0 レポートサーバーがない場合は、– URL パラメーターを使用して、 <strong> </strong> 指定した共有にデータを送信します。 以下に例を示します。</p>
<p><code>Send-AppVClientReport –URL \Myshare\MyData\ -DeleteOnSuccess</code></p>
<p>前の例では、 <strong> &lt; &gt; -URL パラメーターで指定された \MyShare\MyData/強力な場所にレポートデータを送信し <strong> </strong> ます。 データが送信されると、キャッシュが消去されます。</p>
<div class="alert">
<strong>注</strong><br/><p>レポートサーバー以外の場所を指定した場合、データは .xml 形式で送信され、 <strong> </strong> 追加の処理は行われません。</p>
</div>
<div>
 
</div></td>
</tr>
</tbody>
</table>

 

### レポートの作成

App-v 5.0 を使ってレポート情報を取得し、レポートを作成するには、次のいずれかの方法を使用する必要があります。

-   Microsoft sql **Server Reporting services (SSRS)** -microsoft Sql Server reporting services は、Microsoft sql server で利用できます。 SSRS は、App-v 5.0 レポートサーバーをインストールするときにはインストールされません。 関連するレポートを生成するには、別途展開する必要があります。

    [MICROSOFT SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=285596)の使用に関する詳細については、次のリンクを参照してください。

-   **スクリプティング**–レポートは、app-v 5.0 レポートデータベースに対して直接スクリプトを使って生成できます。 以下に例を示します。

    **ストアドプロシージャ:**

    **Spprocessclientreport**は、深夜または 12:00 AM で実行するようにスケジュールされています。

    Microsoft SQL Server のスケジュールされたストアドプロシージャを実行するには、Microsoft SQL Server エージェントが実行されている必要があります。 Microsoft SQL Server エージェントが**自動起動**に設定されていることを確認する必要があります。 詳細については、「 [AUTOSTART Sql Server Agent (Sql Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=287045)」を参照してください。

    このストアドプロシージャは、App-v 5.0 データベーススクリプトを使用する場合にも作成されます。

また、レポートサーバーの web サービスの**最大同時接続数**が、可用性に影響を与えることなく、サーバーが管理できる値に設定されていることも確認する必要があります。 **レポート Web サービス**の推奨される**最大の接続**数は**1万**です。






## 関連トピック


[App-V 5.0 Server の展開](deploying-the-app-v-50-server.md)

[スタンドアロン コンピューターにレポート サーバーをインストールしてデータベースに接続する方法](how-to-install-the-reporting-server-on-a-standalone-computer-and-connect-it-to-the-database.md)

 

 





