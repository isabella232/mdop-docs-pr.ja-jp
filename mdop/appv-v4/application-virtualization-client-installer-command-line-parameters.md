---
title: Application Virtualization Client インストーラーのコマンド ライン パラメーター
description: Application Virtualization Client インストーラーのコマンド ライン パラメーター
author: dansimp
ms.assetid: 508fa404-52a5-4919-8788-2a3dfb00639b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 911d333c80060c1881c96430c1d2d0516b6a4855
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819717"
---
# Application Virtualization Client インストーラーのコマンド ライン パラメーター


次の表に、使用できるすべての Microsoft Application Virtualization クライアントインストーラーのコマンドラインパラメーターとその値、および各パラメーターの簡単な説明を示します。 パラメーターは大文字と小文字を区別し、すべて大文字で入力する必要があります。 すべてのパラメーター値は二重引用符で囲む必要があります。

**注**  
-   App-v バージョン4.6 の場合、クライアントのアップグレード中にコマンドラインパラメーターを使用することはできません。

-   *Swicachesize*と*MINFREESPACEMB*の各パラメーターは、コマンドラインで組み合わせることはできません。 両方を使用する場合、 *Swicachesize*パラメーターは無視されます。



<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">パラメーター</th>
<th align="left">値</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><em>ALLOWINDEPENDENTFILESTREAMING</em></p></td>
<td align="left"><p>TRUE</p>
<p>FALSE</p></td>
<td align="left"><p>クライアントが APPLICATIONSOURCEROOT パラメーターで構成されているかどうかに関係なく、ファイルからのストリーミングを有効にするかどうかを示し <em> </em> ます。 FALSE に設定すると、OSD HREF または <em> APPLICATIONSOURCEROOT </em> パラメーターにファイルパスが含まれている場合でも、トランスポートでファイルのストリーミングを有効にすることはできません。</p>
<p>設定可能な値:</p>
<ul>
<li><p>TRUE: 手動で展開されたアプリケーションは、ディスクから読み込むことができます。</p></li>
<li><p>FALSE の場合、すべてのアプリケーションはソースストリーミングサーバーから取得する必要があります。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><em>APPLICATIONSOURCEROOT</em></p></td>
<td align="left"><p>RTSP:// <em> URL </em> (動的なパッケージ配信用)</p>
<p>File:// <em> URL </em> または <em> UNC </em> (ファイルパッケージ配信からの読み込みの場合)</p></td>
<td align="left"><p>管理者または電子ソフトウェアの配布システムを有効にして、アプリケーションの読み込みがトポロジ管理スキームに準拠していることを確認するには、アプリケーション HREF 要素 (ソースの場所) の OSD コードベースを上書きできるようにします。 この値が "" (既定値) の場合は、既存の OSD ファイルの設定が使用されます。</p>
<p>URL にはいくつかの部分があります。</p>
<p>&lt;protocol &gt; :/ &lt; server &gt; : &lt; port &gt; / &lt; path &gt; / &lt; ? クエリ &gt; &lt; #fragment&gt;</p>
<p>UNC パスには、次の3つの部分があります。</p>
<p>&amp;lt; computername &gt; &amp; lt; フォルダーの共有 &gt; &amp; lt; リソース&gt;</p>
<p><em>クライアントで APPLICATIONSOURCEROOT パラメーターが指定されている場合 </em> 、クライアントは、osd ファイルの URL または UNC パスを構成要素に区切り、osd セクションを対応する APPLICATIONSOURCEROOT セクションに置き換えます <em> </em> 。</p>
<div class="alert">
<strong>重要</strong><br/><p>UNC パスを使用して file://を使用する場合は、必ず正しい形式を使用してください。 正しい形式は file:// &amp; lt; server &gt; &amp; lt; 共有 &gt; です。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><em>ICONSOURCEROOT</em></p></td>
<td align="left"><p><em>UNC</em></p>
<p>HTTP:// <em> url </em> または HTTPS:// <em> url</em></p></td>
<td align="left"><p>管理者が、シーケンス処理されたアプリケーションパッケージのアイコン取得のソースの場所を、文書中に指定できるようにします。 アイコンソースルートは UNC パスと Url (HTTP または HTTPS) をサポートします。 この値が "" (既定値) の場合は、既存の OSD ファイルの設定が使用されます。</p>
<p>URL にはいくつかの部分があります。</p>
<p>&lt;protocol &gt; :/ &lt; server &gt; : &lt; port &gt; / &lt; path &gt; / &lt; ? クエリ &gt; &lt; #fragment&gt;</p>
<p>UNC パスには、次の3つの部分があります。</p>
<p>&amp;lt; computername &gt; &amp; lt; フォルダーの共有 &gt; &amp; lt; リソース&gt;</p>
<div class="alert">
<strong>重要</strong><br/><p>UNC パスを使用する場合は、必ず正しい形式を使用してください。 使用可能な形式は &amp; lt、server &gt; &amp; lt、共有 &gt; または &lt; ドライブ文字 &gt; : &amp; lt; フォルダー &gt; 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><em>OSDSOURCEROOT</em></p></td>
<td align="left"><p><em>UNC</em></p>
<p>HTTP:// <em> url </em> または HTTPS:// <em> url</em></p></td>
<td align="left"><p>公開時に、管理者がアプリケーションパッケージの OSD ファイル取得のソースの場所を指定できるようにします。 OSD ソースのルートは、UNC パスと Url (HTTP または HTTPS) をサポートします。 この値が "" (既定値) の場合は、既存の OSD ファイルの設定が使用されます。</p>
<p>URL にはいくつかの部分があります。</p>
<p>&lt;protocol &gt; :/ &lt; server &gt; : &lt; port &gt; / &lt; path &gt; / &lt; ? クエリ &gt; &lt; #fragment&gt;</p>
<p>UNC パスには、次の3つの部分があります。</p>
<p>&amp;lt; computername &gt; &amp; lt; フォルダーの共有 &gt; &amp; lt; リソース&gt;</p>
<div class="alert">
<strong>重要</strong><br/><p>UNC パスを使用する場合は、必ず正しい形式を使用してください。 使用可能な形式は &amp; lt、server &gt; &amp; lt、共有 &gt; または &lt; ドライブ文字 &gt; : &amp; lt; フォルダー &gt; 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><em>AUTOLOADONLOGIN</em></p>
<p><em>AUTOLOADONLAUNCH</em></p>
<p><em>AUTOLOADONREFRESH</em></p></td>
<td align="left"><p>[0 | 1]</p></td>
<td align="left"><p>アプリケーションの自動読み込みを開始するイベントを定義する自動ロードトリガー。 自動ロードは、バックグラウンドストリーミングを暗黙的に使用して、アプリケーションをキャッシュに完全に読み込むことができるようにします。</p>
<p>プライマリ機能ブロックはできるだけ早く読み込まれます。 その他の機能ブロックはバックグラウンドで読み込まれ、ユーザーのアプリケーション操作などのフォアグラウンド操作が優先され、最適なパフォーマンスが提供されます。</p>
<div class="alert">
<strong>注</strong><br/><p><em>自動読み込み対象のアプリケーションは、autoloadtarget </em> パラメーターによって決定されます。 既定では、 <em> autoloadtarget が設定されていない限り、使用されているパッケージは自動ロードされ </em> ます。</p>
</div>
<div>

</div>
<p>各パラメーターは、次のように読み込み動作に影響します。</p>
<ul>
<li><p><em>AUTOLOADONLOGIN </em> : ユーザーがログインしたときに読み込みが開始されます。</p></li>
<li><p><em>AUTOLOADONLAUNCH </em> : 読み込みは、ユーザーがアプリケーションを開始したときに開始されます。</p></li>
<li><p><em>AUTOLOADONREFRESH </em> —公開の更新が行われると、読み込みが開始されます。</p></li>
</ul>
<p>3つの値を組み合わせることができます。 次の例では、自動ロードトリガーは、ユーザーログイン時と公開更新が発生するときの両方で有効になります。</p>
<p><em>AUTOLOADONLOGIN AUTOLOADONLOGIN</em></p>
<div class="alert">
<strong>注</strong><br/><p>クライアントが最初のインストール時にこれらの値で構成されている場合は、ユーザーが次回ログオフして再びログオンするまで、自動ロードはトリガーされません。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><em>AUTOLOADTARGET</em></p></td>
<td align="left"><p>-</p>
<p>[ALL] (すべて)</p>
<p>PREVUSED</p></td>
<td align="left"><p>自動ロードトリガーが発生したときに自動的に読み込まれる内容を示します。</p>
<p>設定可能な値:</p>
<ul>
<li><p>NONE: 設定されているトリガーに関係なく、自動読み込みは行われません。</p></li>
<li><p>[すべて]: 自動ロードトリガーが有効になっている場合、すべてのパッケージは、起動されたかどうかにかかわらず、自動的に読み込まれます。</p>
<div class="alert">
<strong>注</strong><br/><p>この設定は、SFTMIME を追加してパッケージコマンドを構成することで、個々のパッケージに対して構成され <strong> </strong> <strong> </strong> ます。 これらのコマンドの詳細については、「 <a href="sftmime--command-reference.md" data-raw-source="[SFTMIME Command Reference](sftmime--command-reference.md)"> sftmime コマンドのリファレンス」を参照してください </a> 。</p>
</div>
<div>

</div></li>
<li><p>PREVUSED —自動ロードトリガーが有効になっている場合は、パッケージ内の少なくとも1つのアプリケーションが以前に使用されていた (つまり、起動または precached) パッケージのみを読み込みます。</p></li>
</ul>
<div class="alert">
<strong>注</strong><br/><p>読み取り専用キャッシュ (たとえば、VDI サーバーの実装として) を使用するように App-v クライアントをインストールする場合、 <em> </em> クライアントが読み取り専用キャッシュ内のアプリケーションを更新しないように、autoloadtarget パラメーターを NONE に設定する必要があります。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><em>DOTIMEOUTMINUTES</em></p></td>
<td align="left"><p>29600 (既定)</p>
<p>1– 1439998560 minutes (範囲)</p></td>
<td align="left"><p>切断された操作でアプリケーションを使うことができる分数を示します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>INSTALLDIR</em></p></td>
<td align="left"><p>&lt;>&gt;</p></td>
<td align="left"><p>App-v クライアントのインストールディレクトリを指定します。</p>
<p>例: INSTALLDIR = &quot; C:\Program の Application Virtualization クライアント&quot;</p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>OPTIN</em></p></td>
<td align="left"><p>TRUE</p>
<p>“”</p></td>
<td align="left"><p>Microsoft Application Virtualization クライアントコンポーネントは、一般公開の更新プログラムが利用可能になったときに、Microsoft Update を通じてアップグレード可能になります。 Windows オペレーティングシステムにインストールされている Microsoft Update エージェントでは、サービスを使用するためにユーザーが明示的にオプトインする必要があります。 このオプトインは、デバイス上のすべてのアプリケーションで1回だけ必要です。 既に Microsoft Update に登録している場合は、デバイス上の Microsoft Application Virtualization コンポーネントによって自動的にサービスが利用されます。</p>
<p>コマンドラインインストールの場合、microsoft update を手動で有効にする必要があるため、Microsoft Update は既定でオプトインされます (以前のアプリケーションで既にデバイスが有効になっている場合を除きます)。 そのため、コマンドラインインストールの場合は、[in in] を明示的に指定する必要があります。 コマンドラインパラメーター <em> OPTIN </em> を TRUE に設定すると、Microsoft Update のオプトインが強制的に設定されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>REQUIREのキャッシュ</em></p></td>
<td align="left"><p>TRUE</p>
<p>FALSE</p></td>
<td align="left"><p>アプリケーションが既にキャッシュに含まれているかどうかにかかわらず、常に承認が必要かどうかを示します。</p>
<p>設定可能な値:</p>
<ul>
<li><p>TRUE: アプリケーションは、起動時に常に承認されている必要があります。 RTSP ストリームアプリケーションの場合は、ユーザー認証トークンがサーバーに送信され、承認があります。 ファイルベースのアプリケーションの場合、ファイル Acl は、ユーザーがアプリケーションにアクセスできるかどうかを指定します。</p></li>
<li><p>FALSE —常にサーバーへの接続を試みます。 サーバーへの接続を確立できない場合でも、クライアントは、以前にキャッシュに読み込まれているアプリケーションを起動することを許可します。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><em>SWICACHESIZE</em></p></td>
<td align="left"><p>キャッシュサイズ (MB)</p></td>
<td align="left"><p>クライアントキャッシュのサイズ (mb 単位) を指定します。 既定のサイズは 4096 MB で、最大サイズは 1048576 MB (1 TB) です。 システムはインストール時に利用可能な領域をチェックしますが、スペースは予約されません。</p>
<p>例: <strong> swicachesize = &quot; 1024&quot;</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em>SWIPUBSVRDISPLAY</em></p></td>
<td align="left"><p>表示名</p></td>
<td align="left"><p>公開サーバーの表示名を指定します。SWIPUBSVRHOST を使用する場合に必要 <em> </em> です。</p>
<p>例: <strong> SWIPUBSVRDISPLAY = &quot; PRODUCTION ENVIRONMENT&quot;</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>SWIPUBSVRTYPE</em></p></td>
<td align="left"><p>[HTTP |RTSP</p></td>
<td align="left"><p>発行サーバーの種類を指定します。 既定のサーバーの種類は、Application Virtualization サーバーです。 セキュリティ保護された <strong> </strong> スイッチは、大文字と小文字を区別しません。</p>
<ul>
<li><p>HTTP —標準の HTTP サーバー</p></li>
<li><p>HTTP <strong> /secure </strong> —強化されたセキュリティ HTTP サーバー</p></li>
<li><p>RTSP — Application Virtualization Server</p></li>
<li><p>RTSP <strong> /secure </strong> —強化されたセキュリティアプリケーションの仮想化サーバー</p></li>
</ul>
<p>例: <strong> SWIPUBSVRTYPE = &quot; HTTP/secure&quot;</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em>SWIPUBSVRHOST</em></p></td>
<td align="left"><p>IP address | host name</p></td>
<td align="left"><p>アプリケーションの仮想化サーバーの IP アドレス、またはサーバー&#39;の IP アドレスに解決されるサーバーのホスト名のいずれかを指定します。SWIPUBSVRDISPLAY を使用する場合に必要 <em> </em> です。</p>
<p>例: <strong> SWIPUBSVRHOST = &quot; SERVER01&quot;</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>SWIPUBSVRPORT</em></p></td>
<td align="left"><p>ポート番号</p></td>
<td align="left"><p>この Application Virtualization サーバーがクライアントからの要求をリッスンするために使用する論理ポートを指定します (既定値 = 554)。</p>
<ul>
<li><p>標準 HTTP サーバー (既定 = 80)</p></li>
<li><p>強化されたセキュリティ HTTP サーバー (既定 = 443)。</p></li>
<li><p>Application Virtualization Server (既定 = 554)</p></li>
<li><p>強化されたセキュリティアプリケーション仮想化サーバー-既定値は322です。</p></li>
</ul>
<p>例: <strong> SWIPUBSVRPORT = &quot; 443&quot;</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em>SWIPUBSVRPATH</em></p></td>
<td align="left"><p>パス名</p></td>
<td align="left"><p>ファイルの種類の関連付けを定義するファイルの発行サーバー上の場所 (既定値 =/) を指定します。<em>SWIPUBSVRTYPE </em> パラメーターの値が HTTP のときに必要です。</p>
<p>例: <strong> SWIPUBSVRPATH = &quot; /AppVirt/appsntypes.xml&quot;</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>SWIPUBSVRREFRESH</em></p></td>
<td align="left"><p>[オン |ない</p></td>
<td align="left"><p>ユーザーがクライアントにログインしたときに、ファイルの種類の関連付けとアプリケーションの公開サーバーに自動的にクエリを行うかどうかを指定します (既定値 = ON)。</p>
<p>例: <strong> SWIPUBSVRREFRESH = &quot; off&quot;</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em>SWIGLOBALDATA</em></p></td>
<td align="left"><p>グローバルデータディレクトリ</p></td>
<td align="left"><p>特定のユーザーに固有ではないデータを格納するディレクトリを指定します (既定 = C:\documents and and Settings\All Users\Documents)。</p>
<p>例: <strong> SWIGLOBALDATA = &quot; D:\Microsoft Application Virtualization Client\Global&quot;</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>SWIUSERDATA</em></p></td>
<td align="left"><p>ユーザーデータディレクトリ</p></td>
<td align="left"><p>特定のユーザーに固有のデータを格納するディレクトリを指定します (既定値 =% APPDATA%)。</p>
<p>例: <strong> SWIUSERDATA = &quot; H:\Windows\Microsoft Application Virtualization クライアント&quot;</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em>SWIFSDRIVE</em></p></td>
<td align="left"><p>優先ドライブ文字</p></td>
<td align="left"><p>仮想ドライブ用に選択したドライブ文字に対応します。</p>
<p>例: <strong> SWIFSDRIVE = &quot; S&quot;</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>SYSTEMEVENTLOGLEVEL</em></p></td>
<td align="left"><p>0 ~ 4</p></td>
<td align="left"><p>ログメッセージが NT イベントログに書き込まれるログレベルを示します。 この値は、ログに記録されるもののしきい値を示します。つまり、その値と同じか、またはそれより小さいすべてのものがログに記録されます。 たとえば、値 0x3 (警告) の場合は、警告 (0x3)、エラー (0x2)、および重大なエラー (0x1) が記録されます。</p>
<p>設定可能な値:</p>
<ul>
<li><p>0 = = なし</p></li>
<li><p>1 = Critical</p></li>
<li><p>2 = = エラー</p></li>
<li><p>3 = = 警告</p></li>
<li><p>4 = = 情報</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><em>MINFREESPACEMB</em></p></td>
<td align="left"><p>MB</p></td>
<td align="left"><p>キャッシュサイズを増やすためにホストで使用できる空き領域の量 (mb 単位) を指定します。 次の例では、キャッシュのサイズを増加させる前に、ディスク上に少なくとも 5 GB の空き領域を確保するようにクライアントを構成します。 既定では、インストール時にディスク上で使用できる 5000 MB の空き領域があります。</p>
<p>例: <strong> MINFREESPACEMB = &quot; 5000 &quot; (5 GB)</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>KEEPCURRENTSETTINGS</em></p></td>
<td align="left"><p>[0 | 1]</p></td>
<td align="left"><p>クライアントを展開する前に (グループポリシーを使用するなど)、レジストリ設定を適用したときに使用されます。 クライアントが展開されたら、レジストリ設定を上書きしないように、このパラメーターを値1に設定します。</p>
<div class="alert">
<strong>重要</strong><br/><p>値1に設定すると、次のクライアントインストーラーコマンドラインパラメーターが無視されます。</p>
<p><strong>SWICACHESIZE </strong> 、 <strong> MINFREESPACEMB </strong> 、 <strong> ALLOWINDEPENDENTFILESTREAMING </strong> 、 <strong> APPLICATIONSOURCEROOT </strong> 、 <strong> ICONSOURCEROOT </strong> 、 <strong> osdsourceroot </strong> 、 <strong> SYSTEMEVENTLOGLEVEL </strong> 、 <strong> SWIGLOBALDATA </strong> 、 <strong> dotimeoutminutes </strong> 、 <strong> SWIFSDRIVE </strong> 、 <strong> autoloadtarget </strong> 、 <strong> autoloadtarget </strong> 、および <strong> SWIUSERDATA </strong> 。</p>
<p>これらの値をインストール後に設定する方法について詳しくは、Application Virtualization (App-v) Operations Guide () のコマンドラインを使用して、App-v クライアントのレジストリ設定を構成する方法をご覧ください <a href="https://go.microsoft.com/fwlink/?LinkId=122939" data-raw-source="[https://go.microsoft.com/fwlink/?LinkId=122939](https://go.microsoft.com/fwlink/?LinkId=122939)"> https://go.microsoft.com/fwlink/?LinkId=122939 </a> 。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## 関連トピック


[Application Virtualization Client を手動でインストールする方法](how-to-manually-install-the-application-virtualization-client.md)

[Application Virtualization Client をアップグレードする方法](how-to-upgrade-the-application-virtualization-client.md)

[SFTMIME コマンドリファレンス](sftmime--command-reference.md)









