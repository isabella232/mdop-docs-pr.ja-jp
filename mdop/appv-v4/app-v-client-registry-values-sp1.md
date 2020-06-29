---
title: App-V Client レジストリの値
description: App-V Client レジストリの値
author: dansimp
ms.assetid: 46af5209-9762-47b9-afdb-9a2947e013f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 05cd807ff9882bc478aca07abc4a28cdea83086a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819807"
---
# App-V Client レジストリの値


Microsoft Application Virtualization (App-v) クライアントでは、その構成がレジストリに格納されます。 レジストリ内のデータの形式を理解している場合は、クライアントに関する有用な情報を収集することができます。 また、レジストリエントリを変更して、多くのクライアント操作を構成することもできます。 このトピックでは、Application Virtualization (App-v) クライアントのレジストリキーをすべて一覧表示し、その用途について説明します。

**重要**  
64ビットオペレーティングシステムを実行しているコンピューターでは、次のセクションで説明されているキーと値は、HKEY \ _LOCAL \ _MACHINE \\ pc \\ wow6432node¥にあります。



## 構成キー


次の表では、HKEY \ _LOCAL \ _MACHINE \ ソフトウェア¥のレジストリ値に関連付けられているレジストリ値について説明します。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名前</th>
<th align="left">型</th>
<th align="left">データ (例)</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ProductName</p></td>
<td align="left"><p>String</p></td>
<td align="left"><p>Microsoft Application Virtualization デスクトップクライアント</p></td>
<td align="left"><p>変更しないでください。</p></td>
</tr>
<tr class="even">
<td align="left"><p>バージョン </p></td>
<td align="left"><p>String </p></td>
<td align="left"><p>4.5.0.xxx </p></td>
<td align="left"><p>変更しないでください。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>ドライバー </p></td>
<td align="left"><p>String </p></td>
<td align="left"><p>Sftfs.sys </p></td>
<td align="left"><p>このキー値が存在する場合、最後にコアが開始されたときに停止エラーの原因となったドライバーの名前が含まれます。 Stop エラーを修正した後、このキー値を削除して、sftlist を開始できるようにする必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>InstallPath </p></td>
<td align="left"><p>String </p></td>
<td align="left"><p>Default = C:\Program の Application Virtualization クライアント</p></td>
<td align="left"><p>クライアントがインストールされている場所。 変更しないでください。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>LogFileName </p></td>
<td align="left"><p>String </p></td>
<td align="left"><p>既定値 = CSIDL_COMMON_APPDATA \Microsoft\Application 仮想化 Client\sftlog.txt</p></td>
<td align="left"><p>クライアントログファイルのパスと名前。</p>
<div class="alert">
<strong>注</strong><br/><p>以前のバージョンの App-v 4.6 SP1 を実行していて、ログファイルの名前や場所を変更した場合は、その変更を有効にするには、sftlist サービスを再起動する必要があります。</p>
</div>
<div>

</div>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p>LogMinSeverity </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>既定値 = 4、情報</p></td>
<td align="left"><p>ログに書き込まれるメッセージを制御します。 この値は、ログに記録されるもののしきい値を示します。その値以下のすべてがログに記録されます。 たとえば、値 0x3 (警告) の場合は、警告 (0x3)、エラー (0x2)、および重大なエラー (0x1) が記録されます。</p>
<p>値の範囲: 0x0 = なし、0x1 = Critical、0x2 = エラー、0x3 = 警告、0x4 = Information (既定)、0x5 = Verbose。</p>
<p>ログレベルは、Application Virtualization (App-v) クライアント本体とコマンドプロンプトから構成できます。 コマンドプロンプトでは、/verboselog sftlist.exe コマンドはのログレベルを verbose に上げます。 コマンドラインの詳細について詳しくは、</p>
<p><a href="https://go.microsoft.com/fwlink/?LinkId=141467https://go.microsoft.com/fwlink/?LinkId=141467" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=141467https://go.microsoft.com/fwlink/?LinkId=141467">https://go.microsoft.com/fwlink/?LinkId=141467https://go.microsoft.com/fwlink/?LinkId=141467</a></p>
<p>.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LogRolloverCount</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 4</p></td>
<td align="left"><p>リセットされたときに保持されるログファイルのバックアップコピーの数を定義します。 有効な範囲は 0 ~ 9999 です。 既定値は4です。 値が0の場合、コピーは保持されません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LogMaxSize</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 256</p></td>
<td align="left"><p>リセットされるまでのログファイルの最大サイズをメガバイト (MB) で定義します。 既定のサイズは 256 MB です。 このサイズに達すると、次回の書き込み時にログのリセットが強制的に行われます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SystemEventLogLevel</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 0x4 (App-v 4.5)</p>
<p>Default = 0x3 (App-V 4.6)</p></td>
<td align="left"><p>ログメッセージが NT イベントログに書き込まれるログレベルを示します。 この値は、ログに記録されるもののしきい値を示します。つまり、その値と同じか、またはそれより小さいすべてのものがログに記録されます。 たとえば、値 0x3 (警告) の場合は、警告 (0x3)、エラー (0x2)、および重大なエラー (0x1) が記録されます。</p>
<p>値の範囲</p>
<p>0x0 = なし</p>
<p>0x1 = 重要</p>
<p>0x2 = エラー</p>
<p>0x3 = 警告</p>
<p>0x4 = 情報 (既定)</p>
<p>0x5 = Verbose</p></td>
</tr>
<tr class="even">
<td align="left"><p>AllowIndependentFileStreaming</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 0</p></td>
<td align="left"><p>クライアントが APPLICATIONSOURCEROOT パラメーターで構成されているかどうかに関係なく、ファイルからのストリーミングを有効にするかどうかを示します。 FALSE に設定すると、OSD HREF または APPLICATIONSOURCEROOT パラメーターにファイルパスが含まれている場合でも、トランスポートでファイルのストリーミングを有効にすることはできません。</p>
<p>0x0 = False (既定値)</p>
<p>0x1 = True</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ApplicationSourceRoot</p></td>
<td align="left"><p>String</p></td>
<td align="left"><p>rtsps://mainserver:322/prodapps</p>
<p><a href="https://mainserver:443/prodapps" data-raw-source="https://mainserver:443/prodapps">https://mainserver:443/prodapps</a></p>
<p>ファイル://\uncserver\share\prodapps</p>
<p>ファイル:/\ ターミナルの共有を、</p></td>
<td align="left"><p>管理者または電子ソフトウェア配布 (ESD) システムを有効にし、トポロジ管理スキームに従ってアプリケーションの読み込みを確実に実行できるようにします。 このキー値を使って、アプリケーションの HREF 要素 (ソースの場所など) の OSD コードベースをオーバーライドします。 アプリケーションソースのルートは、Url と汎用名前付け規則 (UNC) のパス形式をサポートします。</p>
<p>URL パスの正しい形式は、//servername: [port] [/path] [/] で、ポートとパスは省略可能です。 ポートが指定されていない場合は、プロトコルの既定のポートが使用されます。 OSD URL の protocol:/server: port 部分のみが置き換えられます。 </p>
<p>UNC パスの正しい形式は \ computer名のフォルダーです。 [フォルダー] []。フォルダーは省略可能です。 コンピューター名には完全修飾ドメイン名 (FQDN) または IP アドレスを使用できます。また、フォルダー名はドライブ文字にすることができます。 OSD パスの \ computer¥¥フォルダーまたはドライブ文字の部分のみが置換されます。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>OSDSourceRoot</p></td>
<td align="left"><p>String</p></td>
<td align="left"><p>\computername\sharefolder\resource</p>
<p>\ コンピューターのコンテンツ</p>
<p>C:\ フォルダー名</p>
<p><a href="http://computername/productivity/" data-raw-source="http://computername/productivity/">http://computername/productivity/</a></p>
<p><a href="https://computername/productivity/" data-raw-source="https://computername/productivity/">https://computername/productivity/</a></p></td>
<td align="left"><p>管理者が、文書中にシーケンス処理されたアプリケーションパッケージの OSD ファイル取得のソースの場所を指定できるようにします。 OSDSourceRoot の受け付け可能な形式には、UNC パスと Url (http または https) が含まれます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>IconSourceRoot</p></td>
<td align="left"><p>String</p></td>
<td align="left"><p>\computername\sharefolder\resource</p>
<p>\ コンピューターのコンテンツ</p>
<p>C:\ フォルダー名</p>
<p><a href="http://computername/productivity/" data-raw-source="http://computername/productivity/">http://computername/productivity/</a></p>
<p><a href="https://computername/productivity/" data-raw-source="https://computername/productivity/">https://computername/productivity/</a></p></td>
<td align="left"><p>管理者が、文書中にシーケンス処理されたアプリケーションパッケージのアイコンファイル取得のソースの場所を指定できるようにします。 IconSourceRoot に使用できる形式には、UNC パスと Url (http または https) が含まれます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>AutoLoadTriggers</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 5</p></td>
<td align="left"><p>自動ロードはクライアントランタイムポリシー構成パラメーターであり、仮想化されたアプリケーションのセカンダリ機能ブロックをバックグラウンドで自動的にクライアントにストリーミングすることを可能にします。 自動ロードトリガーは、アプリケーションの自動読み込みを開始するイベントを示すフラグです。 自動ロードは、バックグラウンドストリーミングを暗黙的に使用して、アプリケーションをキャッシュに完全に読み込むことができるようにします。 プライマリ機能ブロックが最初に読み込まれ、その他の機能ブロックがバックグラウンドに読み込まれて、アプリケーションのユーザー操作などのフォアグラウンド操作が有効になり、最適に認識されたパフォーマンスが得られます。</p>
<p>ビットマスク値:</p>
<p>(0) Never: どのビットも設定されていません (値は 0)。トリガーが設定されていないため、自動読み込みは実行されません。</p>
<p>(1) OnLaunch: 読み込みは、ユーザーがアプリケーションを起動したときに開始されます。</p>
<p>(2) OnRefresh: アプリケーションが公開されると、読み込みが開始されます。 これは、公開の更新が発生したときなど、パッケージレコードが追加または更新されたときに発生します。</p>
<p>(4) OnLogin: ユーザーがログインしたときに読み込みが開始されます。</p>
<p>(5) OnLaunch と Onlaunch: Default。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AutoLoadTarget</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>Default = 1</p></td>
<td align="left"><p>自動ロードトリガーが発生したときに自動的に読み込まれる内容を示します。 ビットマスク値:</p>
<p>(0) None: 設定されているトリガーに関係なく、自動読み込みは行われません。</p>
<p>(1) 以前に使用されたもの (既定): 自動ロードトリガーが有効になっている場合は、パッケージ内の少なくとも1つのアプリケーションが使用されている (開始または precached) パッケージのみを読み込みます。</p>
<p>(2) すべて: 自動ロードトリガーが有効になっている場合、パッケージ (パッケージごと) またはすべてのパッケージ (クライアント用に設定) のすべてのアプリケーションが、まだ開始されているかどうかにかかわらず、自動的に読み込まれます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Requireのキャッシュ</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>Default = 1</p></td>
<td align="left"><p>アプリケーションが既にキャッシュに含まれているかどうかにかかわらず、常に承認が必要であることを示します。 設定可能な値:</p>
<p>0 = False: 常にサーバーへの接続を試行します。 サーバーへの接続を確立できない場合でも、クライアントは、以前にキャッシュに読み込まれているアプリケーションを起動することを許可します。</p>
<p>1 = True (既定): アプリケーションは、起動時に常に承認されている必要があります。 RTSP ストリームアプリケーションの場合は、ユーザー認証トークンがサーバーに送信され、承認があります。 ファイルベースのアプリケーションの場合、ファイル Acl は、ユーザーがアプリケーションにアクセスできるかどうかを制御します。</p>
<p>変更を有効にするには、sftlist サービスを再起動します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>UserDataDirectory </p></td>
<td align="left"><p>String </p></td>
<td align="left"><p>APPDATA</p></td>
<td align="left"><p>アイコンキャッシュとユーザー設定が保存されている場所。</p></td>
</tr>
<tr class="even">
<td align="left"><p>GlobalDataDirectory </p></td>
<td align="left"><p>String </p></td>
<td align="left"><p>C:\Users\Public\Documents </p></td>
<td align="left"><p>グローバルアプリ-V データ (OSD ファイルのキャッシュ、アイコンファイル、ショートカット情報、.ini ファイルなどの SystemGuard リソースなど) に使用するディレクトリ。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AllowCrashes </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>0 または 1 </p></td>
<td align="left"><p>Default = 0: 値が0の場合は、内部のプログラムの例外をキャッチして、クラッシュが発生したときに他のユーザーのアプリケーションが回復して続行できるようにします。 値1は、クライアントが内部プログラムの例外を処理できるようにして、デバッガーでキャプチャできるようにすることを意味します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>CoreInternalTimeout </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>60</p></td>
<td align="left"><p>コアとフロントエンドの間の内部 IPC 要求のタイムアウト (秒単位)。 変更しないでください。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>Default・ Ecombinetime </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>常用</p></td>
<td align="left"><p>この値は、プログラムが終了してから、同じスイート内の別のアプリケーションが実行されているときに、エラーメッセージが表示されないようになるまでの時間を示すために使われます。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>SerializedSuiteLaunchTimeout </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>Default = 60000</p></td>
<td align="left"><p>同じスイートでプログラムをシリアル化しようとしているときにクライアントが待機する時間 (ミリ秒単位) を定義します。 クライアントがタイムアウトすると、プログラムの開始は続行されますが、シリアル化は行われません。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>ScriptTimeout </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>300</p></td>
<td align="left"><p>WAIT = TRUE の場合、OSD ファイル内のスクリプトの既定のタイムアウト (秒)。 タイムアウトを使って、スクリプト単位のタイムアウトを指定できます。 値が0の場合は待機しません。0xFFFFFFFF は無期限で待機することを意味します。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>LaunchRecordLogPath </p></td>
<td align="left"><p>String </p></td>
<td align="left"><p></p></td>
<td align="left"><p>HKLM または HKCU のいずれかで、この値にログファイルへの有効なパスが含まれている場合、SFTTray は、プログラムの起動、シャットダウン、起動に失敗したときに、接続されていないモードを開始または終了するときに、このログに書き込みを行います。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LaunchRecordMask </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>0x1A (26) ログ起動エラーと切断モードのエントリと終了アクティビティ。</p>
<p>0x1F (31) すべてをログに記録します。</p>
<p>0x0 (0) は何も記録しません。 </p></td>
<td align="left"><p>記録する5つのイベント (ビットマスク値) を指定します。</p>
<p>1プログラムの開始</p>
<p>2起動エラーエラー</p>
<p>4 (シャットダウンの場合)</p>
<p>切断モードに入るための8</p>
<p>16サーバーに再接続するための切断モードの終了</p>
<p>これらの番号の任意の組み合わせを追加して、各メッセージを有効にします。 レジストリにない場合は、既定値として0x1F が設定されます。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>LaunchRecordWriteTimeout </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>既定値 = 3000</p></td>
<td align="left"><p>別のプロセスで使用している場合に、開始レコードログへの書き込みを試みるときに、トレイが待機する時間 (ミリ秒単位) を指定します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ImportSearchPath </p></td>
<td align="left"><p>String </p></td>
<td align="left"><p>d:\files;C:\documents and と settings\user1\SFTs </p></td>
<td align="left"><p>ユーザーにディレクトリの選択を求める前に、ポータブル SFT ファイルを検索するための最大5つのディレクトリのセミコロンで区切られたリスト。 パスの末尾のバックスラッシュは省略可能です。 この値は既定では存在しないため、手動で設定する必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>UserImportPath</p></td>
<td align="left"><p>String </p></td>
<td align="left"><p>D:\SFTs\ </p></td>
<td align="left"><p>[HKCU] の下でのみ有効です。 パッケージのインポート用の SFT ファイルを検索しているときに、ユーザーが最後に参照した場所。 SFT が正常に見つかった場合は、自動的に設定します。 これは、SFT ファイルを自動的に検索するときに、以降のインポートで使用されます。</p></td>
</tr>
</tbody>
</table>



## 共有キー


HKEY \ _LOCAL \ _MACHINE \ ソフトウェア¥の共有キーは、App-v の各コンポーネント間で共有される値を制御します。 次の表は、共有キーに関連付けられているレジストリ値に関する情報を示しています。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名前 </th>
<th align="left">型 </th>
<th align="left">データ (例) </th>
<th align="left">説明 </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>DumpPath </p></td>
<td align="left"><p>String </p></td>
<td align="left"><p>Default = C:\ </p></td>
<td align="left"><p>例外でミニダンプを生成するときに、ダンプファイルを作成する既定のパス。 これは既定で C:\ になります。指定しない場合は、 クライアントインストーラーは、このキーを &lt; アプリの仮想化グローバルデータディレクトリ \Dumps. に設定します。 &gt; Sequencer インストーラーは、このキーをインストールディレクトリに設定します。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>DumpPathSizeLimit </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>1000</p></td>
<td align="left"><p>ミニダンプを保存するために使用できるディスク領域の最大サイズ (mb 単位) を指定します。 既定値は 1000 MB です。</p></td>
</tr>
</tbody>
</table>



## ネットワークキー


HKEY \ _LOCAL \ _MACHINE ¥ \ ソフトウェア¥ the \ Softgrid\\ 4. 5\ client¥ネットワークキーは、さまざまなネットワーク関連パラメーターを制御します。 このキーは主にネットワークトランスポートエージェントによって使用されます。 次の表は、ネットワークキーに関連付けられているレジストリ値に関する情報を示しています。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名前 </th>
<th align="left">型 </th>
<th align="left">データ (例) </th>
<th align="left">説明 </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>オンライン</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>Default = 1</p></td>
<td align="left"><p>オフラインモードを有効または無効にします。 0に設定されている場合、クライアントは App-v 管理サーバーまたは公開サーバーと通信しません。 切断された操作の場合、クライアントは、アプリが app-v 管理サーバーに接続されていない場合でも、読み込まれたアプリケーションを起動することができます。 オフラインモードの場合、クライアントは、App-v 管理サーバーまたは公開サーバーに接続しようとしません。 切断された操作をオフラインでも使用できるようにする必要があります。 既定値は1が有効 (オンライン) で、0は無効 (オフライン) です。</p></td>
</tr>
<tr class="even">
<td align="left"><p>AllowDisconnectedOperation </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>Default = 1</p></td>
<td align="left"><p>切断された操作を有効または無効にします。 既定値は1が有効で、0は無効です。 切断された操作が有効になっている場合、app-v クライアントは、アプリが Hyper-v 管理サーバーに接続されていない場合でも、読み込まれたアプリケーションを起動することができます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>FastConnectTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 1000</p></td>
<td align="left"><p>この値は、切断された操作モードに移行するタイミングを判断するために TCP 接続タイムアウト (ミリ秒単位) を指定します。 この値は、既定の ConnectTimeout (20 秒) を上書きするために使用できます (ネットワークトランザクションの場合は、アプリ間の接続タイムアウト)。または、システムの TCP タイムアウトの約25秒。 これにより、クライアントがすぐに切断された操作モードになります。 次の接続で適用されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LimitDisconnectedOperation</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>Default = 1 </p></td>
<td align="left"><p>AllowDisconnectedOperation が1の場合にのみ適用されます。 この値は、接続されていない操作でクライアントが操作できる時間制限があるかどうかを決定します。 1 = 限定。 0 = 無制限。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DOTimeoutMinutes</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 129600</p></td>
<td align="left"><p>切断された操作モードでアプリケーションを使うことができる分数を示します。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>有効な値は、1 ~ 999999 (1 ~ 1439998560 分) で表されます。 既定値は、90日または129600分です。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>プロトコル</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 8</p></td>
<td align="left"><p>使用する既定のプロトコル (TCP vs SSL)。 [オプション] ダイアログで構成します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ReadTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>超える</p></td>
<td align="left"><p>ネットワークトランザクションのタイムアウトを秒単位で確認します。 変更しないでください。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>WriteTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>超える</p></td>
<td align="left"><p>ネットワークトランザクションのタイムアウトを秒単位で作成します。 変更しないでください。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ConnectTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>超える</p></td>
<td align="left"><p>ネットワークトランザクションのタイムアウトを秒単位で接続します。 変更しないでください。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ReestablishmentRetries</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>-</p></td>
<td align="left"><p>ドロップしたセッションを再確立する回数。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ReestablishmentInterval</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>マート</p></td>
<td align="left"><p>ドロップされたセッションを再確立するまでに待機する秒数。</p></td>
</tr>
</tbody>
</table>



## Http キー


HKEY \ _LOCAL \ _MACHINE ¥ \ ソフトウェア¥ the \ Softgrid\\ 2015 (5: \) http キーは、Http ストリーミングに関連するパラメーターを制御します。 このキーは主にネットワークトランスポートエージェントによって使用されます。 次の表は、Http キーに関連付けられているレジストリ値に関する情報を示しています。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名前 </th>
<th align="left">型 </th>
<th align="left">データ (例) </th>
<th align="left">説明 </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>LaunchIfNotFound</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 0</p></td>
<td align="left"><p>Http サーバーへの接続が確立され、パッケージファイルが HTTP サーバーに存在しない場合の HTTP ストリーミングの動作を制御します。 値が存在しない場合、または1に設定されていない場合は、以前にキャッシュに読み込まれていたアプリケーションを起動できません。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>件</p></td>
<td align="left"><p>この値が1に設定されている場合は、以前にキャッシュに読み込まれたアプリケーションを App-v クライアントから起動できます。</p></td>
</tr>
</tbody>
</table>



## ファイルシステムキー


HKEY \ _LOCAL \ _MACHINE ¥ xxx ¥ xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx ¥ xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx 次の表は、AppFS キーに関連付けられているレジストリ値に関する情報を示しています。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名前 </th>
<th align="left">型 </th>
<th align="left">データ (例) </th>
<th align="left">説明 </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>FileSize </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>4096</p></td>
<td align="left"><p>ファイルシステムキャッシュファイルの最大サイズ (mb)。 レジストリでこの値を変更する場合は、状態を0に設定して再起動する必要があります。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>FileName </p></td>
<td align="left"><p>String </p></td>
<td align="left"><p>C:\Users\Public\Documents\SoftGrid Client\sftfs.fsd </p></td>
<td align="left"><p>ファイルシステムキャッシュファイルの場所。 レジストリでこの値を変更する場合は、同じサイズのままにして、再起動するか、状態を0に設定して再起動する必要があります。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>ドライブ </p></td>
<td align="left"><p>String </p></td>
<td align="left"><p>Q: </p></td>
<td align="left"><p>使用可能な場合は、App-v ファイルシステムがマウントされるドライブ。 この値はリスナーまたはインストーラーによって設定され、ファイルシステムによって読み取られます。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>状態 </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>0x100 </p></td>
<td align="left"><p>ファイルシステムの状態。 0に設定して再起動すると、ファイルシステムキャッシュが完全に消去されます。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>FileSystemStorage </p></td>
<td align="left"><p>String </p></td>
<td align="left"><p>¥ C $ SG </p></td>
<td align="left"><p>[HKCU] の下に設定する、シンボリックリンクのパス。 変更しない (構成の下でデータディレクトリを使用)。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>GlobalFileSystemStorage </p></td>
<td align="left"><p>String </p></td>
<td align="left"><p>C:\Users\Public\Documents\SoftGrid Client\AppFS ストレージ </p></td>
<td align="left"><p>グローバルファイルシステムデータのパス。 変更しないでください。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>MaxPercentToLockInCache </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>既定値 = 90 </p></td>
<td align="left"><p>ロック可能なファイルシステムキャッシュファイルの最大割合を指定します。 変更しないでください。</p></td>
</tr>
<tr class="even">
<td align="left"><p>UnloadLeastRecentlyUsed</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>Default = 1</p></td>
<td align="left"><p>ファイルシステムキャッシュスペース管理機能では、最近使用した (LRU) アルゴリズムが使用され、既定で有効になっています。 新しいパッケージに必要な領域がキャッシュ内の空き領域を超えている場合、App-v Client はこの機能を使用して、既存のパッケージがキャッシュから削除され、新しいパッケージ用のスペースが確保されるかどうかを判断します。 クライアントは、"MinPkgAge" レジストリ値で指定された値よりも古い最終アクセス日のパッケージを削除します。 0 (無効) と 1 (既定値、有効) の値を指定します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MinPackageAge</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>件</p></td>
<td align="left"><p>Discard の対象としてパッケージを選択できるかどうかを判断するには、このレジストリ値を、パッケージが最後にアクセスされてからの経過時間の最小日数と等しくなるように設定します。 最近使用されたパッケージは破棄されません。</p></td>
</tr>
</tbody>
</table>



## 権限キー


ユーザーによるミスを防ぐために、管理者は、ユーザーが誤ってプログラムをアンロードしないようにするなど、管理者以外のユーザーのための一部の操作へのアクセスを制御するために、HKEY \ _LOCAL \ _MACHINE \ ソフトウェア \\ のアクセス許可キーを使用できます。 管理者権限を持つユーザーは、次のいずれかのアクセス許可を与えることができます。 リモートデスクトップセッションホスト (RD セッションホスト) サーバー (旧 Terminal Server) システムなどの共有システムでは、これらのアクセス許可の一部によって、ユーザーがシステム上のすべてのユーザーによって使用されるアプリケーションを制御することができるため、ユーザーにアクセス許可を付与する際に注意してください。 これらの設定に使用できる値は 1 (許可) と 0 (許可しない) です。

アクセス許可キーの設定では、名前付きのアクションを有効にするすべてのインターフェイスを制御します。 これには、[オプション] ダイアログ、SFTTray、Sfttray が含まれます。 これらの設定は管理者には影響ありません。 次の表は、アクセス許可キーに関連付けられたレジストリ値に関する情報を示しています。

名前の種類データ (例) 説明 ChangeFSDrive

DWORD

既定値 = 0

値1を指定すると、ユーザーはファイルシステムドライブとして使用する別のドライブ文字を選ぶことができます。

ChangeCacheSize

DWORD

既定値 = 0

値1を指定すると、ユーザーはキャッシュサイズを変更できます。

ChangeLogSettings

DWORD

既定値 = 0

値1を指定すると、ユーザーはログレベルを変更したり、位置を変更したり、ユーザーインターフェイスでリセットしたりできます。

AddApp

DWORD

既定値 = 0

値1を指定すると、ユーザーはアプリケーションを明示的に追加できます。 これは、公開の更新によって追加されたアプリケーションには影響しません。また、まだ追加されていないアプリケーションは、ユーザーがアプリを起動することはできません。 値は0または1です。

LoadApp 

DWORD 

0

ユーザーがアプリケーションを読み込むことはできません。 これは、RD セッションホストの既定値です。 モバイルユーザーの場合は、接続されていない操作またはオフラインモードでアプリを使用するために、キャッシュにアプリケーションを完全に読み込むことをお勧めします。 アプリケーションを App-v 管理サーバーまたは App-v ストリーミングサーバーからストリーミングするには、アプリケーションを読み込むためにサーバーに接続している必要があります。

件

ユーザーがアプリケーションを読み込むことを許可します。 これは、Windows デスクトップの既定値です。 

UnloadApp 

DWORD 

0

ユーザーがアプリケーションをアンロードすることを許可しません。 パッケージを読み込みまたはアンロードすると、パッケージ内のすべてのアプリケーションがキャッシュに読み込まれるか、またはキャッシュから削除されます。

件

ユーザーがアプリケーションをアンロードできるようにします。 

LockApp 

DWORD 

0

ユーザーは、アプリケーションのロックとロック解除を行うことはできません。 これは、RD セッションホストの既定値です。 ロックされたアプリケーションをキャッシュから削除して、新しいアプリケーションのためのスペースを確保することはできません。 ロックされているアプリケーションを、リモートデスクトップサービス (以前のターミナルサービス) キャッシュの App-v デスクトップまたはクライアントから削除するには、ロックを解除する必要があります。

件

ユーザーがアプリケーションのロックとロック解除を行うことができるようにします。 これは、Windows デスクトップの既定値です。 

ManageTypes 

DWORD 

0

ユーザーは、そのユーザーに対してファイルの種類の関連付けを追加、編集、または削除することはできません。 これは、RD セッションホストの既定値です。 

件

ユーザーは、グローバルにではなく、そのユーザーに対してのみ、ファイルの種類の関連付けの追加、編集、削除を行うことができます。 これは、Windows デスクトップの既定値です。 

RefreshServer 

DWORD 

0

ユーザーが MIME 設定の更新をトリガーすることはできません。 これは、RD セッションホストの既定値です。 

件

ユーザーが MIME 設定の更新を開始できるようにします。 これは、Windows デスクトップの既定値です。 

UpdateOSDFile

DWORD

既定値 = 0

値1を指定すると、ユーザーは修正された OSD ファイルを使用できます。

ImportApp 

DWORD 

0

ユーザーがアプリケーションをキャッシュにインポートすることを許可しません。 読み込みとインポートの違いは、読み込みがトリガーされると、クライアントは、OSD、ASR、または Override URL に含まれる現在構成されている場所からパッケージを取得することです。 インポートを使用する場合は、パッケージを取得する場所を指定する必要があります。 

件

ユーザーがアプリケーションをキャッシュにインポートできるようにします。 

ChangeRefreshSettings

DWORD

既定値 = 0

値1を指定すると、ユーザーはサーバーの更新設定を変更できます (ログイン時と定期的な更新時に更新)。 これは、ユーザーが他のサーバー設定 (path、host など) を変更できるというわけではありません。

ManageServers

DWORD

既定値 = 0

値1を指定すると、ユーザーは、ChangeRefreshSettings アクセス許可によって制御される更新設定を編集することを除き、サーバーの追加、編集、削除を行うことができます。

PublishShortcut

DWORD

既定値 = 0

値1を指定すると、ユーザーはユーザーインターフェイスを使ってショートカットを発行できます。 これは、公開の更新中に公開されるショートカットには影響しません。

ViewAllApplications

DWORD

既定値 = 0

値1を指定すると、すべてのアプリケーションがユーザーインターフェイスを通じて表示されます。そうしないと、ユーザーのアプリケーションのみが表示されます。

RepairApp

DWORD

Default = 1

値1を指定すると、ユーザーは SFTMime またはクライアント管理コンソールのアプリケーションで修復操作を使用することができます。 アプリケーションを修復する場合は、カスタムユーザー設定を削除して、既定の設定に戻すことができます。 この操作では、ショートカットやファイルの種類の関連付けは変更または削除されず、キャッシュからアプリケーションが削除されることはありません。

アプリのクリア

DWORD

Default = 1

値1を指定すると、ユーザーは SFTMime またはクライアント管理コンソールのアプリケーションに対してクリアアクションを使うことができます。 コンソールからアプリケーションをクリアすると、そのアプリケーションは使えなくなります。 ただし、アプリケーションはキャッシュ内に保持され、同じシステム上の他のユーザーは引き続き使用できます。 公開したアプリが更新されると、消去されたアプリケーションが再び利用できるようになります。

DeleteApp

DWORD

既定値 = 0

値1を指定すると、ユーザーは SFTMime またはクライアント管理コンソールのアプリケーションに対して削除アクションを使用できます。 アプリケーションを削除すると、そのクライアントのユーザーは選択したアプリケーションを使用できなくなります。 ショートカットとファイルの種類の関連付けが削除され、アプリケーションがキャッシュから削除されます。 ただし、他のアプリケーションが、選択したアプリケーションのファイルシステムキャッシュまたは設定データを参照している場合は、これらの項目は削除されません。

公開した後は、削除されたアプリケーションを再び利用できるようになります。

ToggleOfflineMode

DWORD

値1を指定すると、ユーザーはオフラインモードでクライアントを実行することを選択できます。 オフラインモードでは、application virtualization クライアントは、Application Virtualization Server に接続していない場合でも、読み込まれたアプリケーションを開始できます。



## カスタム設定


HKEY \ _LOCAL \ _MACHINE ¥ $ ¥¥ \ Softgrid\\ 4.8 5 \ client¥ customsettings キーには、フロントエンドコンポーネントに固有の値が含まれています。 すべてのカスタム設定は文字列として保存されます。 次の表は、CustomSettings キーに関連付けられたレジストリ値に関する情報を示しています。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名前 </th>
<th align="left">型 </th>
<th align="left">データ (例) </th>
<th align="left">説明 </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>TrayErrorDelay </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>既定値 = 30 </p></td>
<td align="left"><p>アプリケーションの仮想化通知領域に起動失敗などのエラーメッセージが表示されるまでの時間 (秒) &quot; &quot; 。 最小値は1です。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>TraySuccessDelay </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>既定値 = 10 </p></td>
<td align="left"><p>Appvmed 通知領域に、Word が起動された、 &quot; &quot; または Excel が &quot; シャットダウンしたときなどの成功メッセージが表示されるまでの時間 (秒) &quot; 。 0の場合、これらのメッセージは抑制されます。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>TrayVisibility</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 0</p></td>
<td align="left"><p>0 = 仮想化されたアプリケーションを使用している場合は、[トレイを表示] を選びます。</p>
<p>1 = トレイを常に表示します。</p>
<p>2 = トレイを表示しません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>TrayShowRefresh</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p></p></td>
<td align="left"><p>値1に設定すると、メニュー項目更新アプリケーションがトレイメニューに表示され、ユーザーがアクセスできるようになります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>TrayShowLoad</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p></p></td>
<td align="left"><p>値1に設定すると、メニュー項目の読み込みアプリケーションがトレイメニューに表示され、ユーザーがアクセスできるようになります。</p></td>
</tr>
</tbody>
</table>



## レポートの設定


HKEY \ _LOCAL \ _MACHINE ¥¥¥¥ \ xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx () 次の表は、レポートキーに関連付けられているレジストリ値に関する情報を示しています。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名前 </th>
<th align="left">型 </th>
<th align="left">データ (例) </th>
<th align="left">説明 </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>DataCacheLimit</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>既定値 = 20</p></td>
<td align="left"><p>この値は、レポート情報を格納する XML キャッシュの最大サイズ (MB) を指定します。 サイズは、メモリ内のキャッシュに適用されます。 上限に達すると、ログファイルがロールオーバーされます。 新しいレコードが追加されると (リストの一番下にある)、空き領域を増やすために、1つ以上の最も古いレコード (リストの先頭) が削除されます。 このイベントが発生すると、最初に警告が表示されます。これは、送信時にキャッシュが正常に消去され、ログが再びいっぱいになるまで、ログに記録されません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>"の場合</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>Default = 65536</p></td>
<td align="left"><p>この値は、更新の公開時にサーバーに一度に送信する最大サイズをバイト単位で指定します。ログのサイズが大きくなったときに、永続的な転送エラーが発生しないようにします。 既定値は65536です。 レポートデータをサーバーに送信する場合、1つのアプリケーションレコードのブロック (XML データのバイト単位のブロックサイズ以下) は、キャッシュから削除され、サーバーに送信されます。 各ブロックには、一般的なクライアントデータとグローバルパッケージリストデータが付加されます。これらは、ブロックサイズの計算には関係ありません。非常に大きいパッケージリストの場合は、低帯域幅または信頼性の低い接続での伝送エラーの原因となる可能性があります。</p></td>
</tr>
</tbody>
</table>



## 関連トピック


[Application Virtualization Client リファレンス](application-virtualization-client-reference.md)









