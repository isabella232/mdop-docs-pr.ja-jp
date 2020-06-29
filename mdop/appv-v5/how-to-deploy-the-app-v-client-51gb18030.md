---
title: APP-V Client を展開する方法
description: APP-V Client を展開する方法
author: dansimp
ms.assetid: 981f57c9-56c3-45da-8261-0972bfad3e5b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: ea216f6b86820f752e0c0ac693470eac72cb847a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814123"
---
# APP-V Client を展開する方法


Microsoft Application Virtualization (App-v) 5.1 クライアントとリモートデスクトップサービスクライアントをインストールするには、次の手順を使用します。 ターゲットコンピューターのオペレーティングシステムと一致するバージョンのクライアントをインストールする必要があります。

<a href="" id="bkmk-clt-install-prereqs"></a>**始める前に行うこと**

1. ソフトウェアの前提条件を確認してインストールします。

   インストールする App-v のバージョンに対応する必須ソフトウェアをインストールします。

   -   [App-V 5.1 について](about-app-v-51.md)

   -   [App-V 5.1 の前提条件](app-v-51-prerequisites.md)

2. インストールに適用できるように、クライアントの共存とサポートされていないシナリオを確認します。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p>共存するアプリ-V クライアントを展開する</p></td>
   <td align="left"><p><a href="planning-for-the-app-v-51-sequencer-and-client-deployment.md" data-raw-source="[Planning for the App-V 5.1 Sequencer and Client Deployment](planning-for-the-app-v-51-sequencer-and-client-deployment.md)">App-V 5.1 Sequencer および Client の展開計画</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>サポートされていない、または限定されたインストールシナリオ</p></td>
   <td align="left"><p>「 <a href="app-v-51-supported-configurations.md" data-raw-source="[App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md)"> App-v 5.1 でサポートされる構成」の「クライアント」セクションを参照してください。</a></p></td>
   </tr>
   </tbody>
   </table>



3. クライアントのレジストリ、ログ、トラブルシューティング情報の場所を確認します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>クライアントレジストリ情報</p></td>
<td align="left"><ul>
<li><p>既定では、App-v 5.1 クライアントをインストールした後、クライアント情報は次のレジストリキーのレジストリに格納されます。</p>
<p><strong>HKEY_LOCAL_MACHINE \ SOFTWARE \ MICROSOFT \ APPV \ クライアント</strong></p></li>
<li><p>App-v クライアントを実行しているコンピューターに仮想化されたパッケージを展開すると、関連付けられたパッケージデータは次の場所に格納されます。</p>
<p><strong>C: \ ProgramData \ App-V</strong></p>
<p>ただし、次のレジストリキーを使用して、この場所を再構成することができます。</p>
<p><strong>HKEY_LOCAL_MACHINE \ SOFTWARE \ MICROSOFT \ SOFTWARE \ MICROSOFT \ APP-V \ CLIENT \ STREAMING \ PACKAGEINSTALLATIONROOT</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>クライアントログファイル</p></td>
<td align="left"><ul>
<li><p>App-v 5.1 クライアントに関連付けられているログファイル情報については、次のログを検索します。</p>
<p><strong>イベントログ/アプリケーションとサービスログ/Microsoft/AppV</strong></p></li>
<li><p>App-v 5.0 SP3 では、一部のログが統合され、次の場所に移動されました。</p>
<p><strong>イベントログ/アプリケーションとサービスログ/Microsoft/AppV/ServiceLog</strong></p>
<p>移動したログの一覧については、「 <a href="about-app-v-50-sp3.md#bkmk-event-logs-moved" data-raw-source="[About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved)"> app-v 5.0 SP3 について」を参照してください </a> 。</p></li>
<li><p>App-v 5.1 クライアントを実行しているコンピューターに現在保存されているパッケージは、次の場所に保存されます。</p>
<p><strong>C:\ProgramData\App-V &amp; lt; パッケージ id &gt; &amp; lt; バージョン id&gt;</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>クライアントのインストールのトラブルシューティング情報</p></td>
<td align="left"><p><strong>% Temp% フォルダーのエラーログを参照してください </strong> 。 ログファイルを確認するには、[ <strong> スタート] をクリックし、 </strong> 「 <strong> % temp%」と入力して、 </strong> <strong> appv_ ログを探し </strong> ます。</p></td>
</tr>
</tbody>
</table>



**App-v 5.1 クライアントをインストールするには**

1.  アプリがインストールされているコンピューターに、App-v 5.1 クライアントインストールファイルをコピーします。 次のクライアントの種類から選びます。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">クライアントの種類</th>
    <th align="left">使用するファイル</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>クライアントの標準バージョン</p></td>
    <td align="left"><p><strong>appv_client_setup.exe</strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>クライアントのリモートデスクトップサービスバージョン</p></td>
    <td align="left"><p><strong>appv_client_setup_rds.exe</strong></p></td>
    </tr>
    </tbody>
    </table>



2.  インストールファイルをダブルクリックし、[**インストール**] をクリックします。 インストールが開始される前に、インストーラーは、不足している[アプリ– V 5.1 の前提条件](app-v-51-prerequisites.md)をコンピューターで確認します。

3.  ソフトウェアライセンス条項を確認して同意し、Microsoft Update を使用するかどうか、Microsoft カスタマーエクスペリエンス向上プログラムに参加するかどうかを選択して、[**インストール**] をクリックします。

4.  [**セットアップが正常に完了しました**] ページで、[**閉じる**] をクリックします。

    インストールにより、**プログラム**で次のような app-v クライアントのエントリが作成されます。

    -   **.exe**

    -   **.msi**

    -   **言語パック**

        **注**  
        インストール後、.exe ファイルのみをアンインストールできます。



**スクリプトを使用して App-v 5.1 クライアントをインストールするには**

1. 必要なすべての必須ソフトウェアをターゲットコンピューターにインストールします。 [開始する前に実行する操作を](#bkmk-clt-install-prereqs)参照してください。 .Msi ファイルを使用してクライアントをインストールした場合、前提条件が見つからないと、インストールが失敗します。

2. スクリプトを使用して App-v 5.1 クライアントをインストールするには、 **appv\_client\_setup.exe**で次のパラメーターを使用します。

   **注**  
   クライアントの Windows インストーラー (.msi) では、 **/log**パラメーターを除き、同じスイッチセットがサポートされています。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p>/INSTALLDIR</p></td>
   <td align="left"><p>インストールディレクトリを指定します。 使用例: <strong> /INSTALLDIR = C:\Program Files\AppV Client</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/CEIPOPTIN</p></td>
   <td align="left"><p>カスタマーエクスペリエンス向上プログラムへの参加を可能にします。 使用例: <strong> /CEIPOPTIN = [0 | 1]</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/Muoptin</p></td>
   <td align="left"><p>Microsoft Update を有効にします。 使用例: <strong> /muoptin = [0 | 1]</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/Packageinstallationroot</p></td>
   <td align="left"><p>すべての新しいアプリケーションと更新プログラムをインストールするディレクトリを指定します。 使用例: <strong> /packageinstallationroot =&#39;C:\ Apppackages&#39;</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/パッケージ ourceroot</p></td>
   <td align="left"><p>パッケージコンテンツをダウンロードするためのソースの場所をオーバーライドします。 使用例: <strong> /パッケージ ourceroot =&#39;<a href="http://packageStore" data-raw-source="http://packageStore"> http://packageStore </a>&#39;</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/自動ロード</p></td>
   <td align="left"><p>特定のコンピューター上の App-v 5.1 で新しいパッケージを読み込む方法を指定します。 次のオプションが有効になっています: [1];すべてのパッケージを自動的に読み込む [2];または、パッケージを自動的に読み込まない [0] を選びます。 <strong>使用例:/自動ロード = [0 | 1 | 2]</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/Sharedcontentstoremode</p></td>
   <td align="left"><p>ストリーミングされたパッケージコンテンツをローカルのハードディスクに保存しないように指定します。 使用例: <strong> /sharedcontentstoremode = [0 | 1]</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/MIGRATIONMODE</p></td>
   <td align="left"><p>以前のバージョンで作成されたパッケージに関連付けられているショートカットと FTAs App-v 5.1 クライアントが変更できるようにします。 使用例: <strong> /MIGRATIONMODE = [0 | 1]</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/ENABLEPACKAGESCRIPTS</p></td>
   <td align="left"><p>パッケージマニフェストファイルまたは実行する構成ファイルで定義されているスクリプトを有効にします。 使用例: <strong> /ENABLEPACKAGESCRIPTS = [0 | 1]</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/ROAMINGREGISTRYEXCLUSIONS</p></td>
   <td align="left"><p>ユーザープロファイルでローミングされないレジストリパスを指定します。 使用例: <strong> /ROAMINGREGISTRYEXCLUSIONS = ソフトウェア \ クラス; ソフトウェア \ クライアント</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/ROAMINGFILEEXCLUSIONS</p></td>
   <td align="left"><p>ユーザー&#39;s プロファイルでローミングしない% userprofile% を基準としたファイルパスを指定します。 使用例: <strong> /ROAMINGFILEEXCLUSIONS &#39;デスクトップ、マイピクチャ&#39;</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/S [1-5] 発行サーバー名</p></td>
   <td align="left"><p>発行サーバーの名前が表示されます。 使用例: <strong> /S2PUBLISHINGSERVERNAME = MyPublishingServer</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/S [1-5] 発行する SERVERURL</p></td>
   <td align="left"><p>発行サーバーの URL を表示します。 使用例: <strong> /S2PUBLISHINGSERVERURL = \ pubserver</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/S [1-5] GLOBALREFRESHENABLED-</p></td>
   <td align="left"><p>グローバル発行の更新を有効にします。 使用例: <strong> /S2GLOBALREFRESHENABLED = [0 | 1]</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/S [1-5] GLOBALREFRESHVALU</p></td>
   <td align="left"><p>ユーザーがログオンしたときにグローバル公開の更新を開始します。 使用例: <strong> /S2LOGONREFRESH = [0 | 1]</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/S [1-5] GLOBALREFRESHINTERVAL-</p></td>
   <td align="left"><p>公開の更新間隔を指定し <strong> ます。ここで、0 </strong> は定期的に更新されないことを示します。 使用例: <strong> /S2PERIODICREFRESHINTERVAL = [0-744]</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/S [1-5] GLOBALREFRESHINTERVALUNIT</p></td>
   <td align="left"><p>間隔の単位 (時間 [0]、日数 [1]) を指定します。 使用例: <strong> /S2GLOBALREFRESHINTERVALUNIT = [0 | 1]</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/S [1-5] USERREFRESHENABLED</p></td>
   <td align="left"><p>ユーザー公開の更新を有効にします。 使用例: <strong> /S2USERREFRESHENABLED = [0 | 1]</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/S [1-5] USERREFRESHONLOGON 詳細</p></td>
   <td align="left"><p>ユーザーがログオンしたときにユーザーの公開更新を開始します。 使用例: <strong> /S2LOGONREFRESH = [0 | 1]</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/S [1-5] USERREFRESHINTERVAL-</p></td>
   <td align="left"><p>公開の更新間隔を指定し <strong> ます。ここで、0 </strong> は定期的に更新されないことを示します。 使用例: <strong> /S2PERIODICREFRESHINTERVAL = [0-744]</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/S [1-5] USERREFRESHINTERVALUNIT</p></td>
   <td align="left"><p>間隔の単位 (時間 [0]、日数 [1]) を指定します。 使用例: <strong> /S2USERREFRESHINTERVALUNIT = [0 | 1]</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/Log</p></td>
   <td align="left"><p>ログ情報が保存されている場所を指定します。 既定の場所は% Temp% です。 使用例: <strong> /Log C:\logs\log.log</strong></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/q</p></td>
   <td align="left"><p>無人インストールを指定します。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/REPAIR</p></td>
   <td align="left"><p>以前のクライアントインストールを修復します。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/NORESTART</p></td>
   <td align="left"><p>クライアントのインストール後にコンピューターが再起動しないようにします。</p>
   <p>このパラメーターを使用すると、各更新プログラムをインストールした後にエンドユーザーのコンピューターが再起動しないようにし、都合のよいときに再起動をスケジュールすることができます。 たとえば、Service Pack のインストール後に、再起動しなくても、App-v 5.1 をインストールしてから、修正プログラムパッケージ Y をインストールすることができます。 インストール後、App-v の使用を開始する前に再起動する必要があります。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/UNINSTALL</p></td>
   <td align="left"><p>クライアントをアンインストールします。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/ACCEPTEULA</p></td>
   <td align="left"><p>ライセンス契約を承諾します。 これは、無人インストールの場合に必要になります。 使用例: <strong> /ACCEPTEULA </strong> または <strong> /ACCEPTEULA = 1 </strong> 。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/レイアウト</p></td>
   <td align="left"><p>関連付けられているレイアウトアクションを指定します。 また、Windows インストーラー (.msi) とスクリプトファイルも、App-v 5.1 をインストールせずにフォルダーに展開します。 値は予期されません。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>/Layoutdir</p></td>
   <td align="left"><p>レイアウトディレクトリを指定します。 文字列値が必要です。 使用例: <strong> /layoutdir = "C:\ Application Virtualization Client" </strong> 。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>/?、/h、/help</p></td>
   <td align="left"><p>以前のインストールパラメーターに関するヘルプを要求します。</p></td>
   </tr>
   </tbody>
   </table>



**Windows インストーラー (.msi) ファイルを使用して App-v 5.1 クライアントをインストールするには**

1.  ターゲットコンピューターに必要な前提条件をインストールします。 [開始する前に実行する操作を](#bkmk-clt-install-prereqs)参照してください。 前提条件が満たされていない場合、インストールは失敗します。

2.  アプリ-V 5.1 Windows Installer (.msi) ファイルを使用してクライアントをインストールする前に、ターゲットコンピューターに保留中の再起動がないことを確認します。 Windows インストーラのファイルには、保留中の再起動のフラグは設定されません。

3.  ターゲットコンピューターに次のいずれかの Windows インストーラーファイルを展開します。 指定するファイルは、ターゲットコンピューターの構成と一致している必要があります。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">展開の種類</th>
    <th align="left">このファイルを展開</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>コンピューターで32ビットの Microsoft Windows オペレーティングシステムが実行されている</p></td>
    <td align="left"><p>appv_client_MSI_x86.msi</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>コンピューターで64ビットの Microsoft Windows オペレーティングシステムが実行されている</p></td>
    <td align="left"><p>appv_client_MSI_x64.msi</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>アプリ-V 5.1 リモートデスクトップサービスクライアントを展開しています</p></td>
    <td align="left"><p>appv_client_rds_MSI_x64.msi</p></td>
    </tr>
    </tbody>
    </table>



4.  次の表の情報を使用して、ターゲットコンピューターの目的の言語に基づいて、**インストールする適切**な言語パックを選びます。 表の**xxxx**は、言語パックのターゲットロケールを示しています。

    **始める前に知っておくべきこと:**

    -   言語パックは、標準の App-v 5.1 クライアントと、App-V 5.1 クライアントのリモートデスクトップサービスバージョンの両方に共通です。

    -   **.Exe**を使って app-v 5.1 クライアントをインストールする場合、インストーラーは、ターゲットコンピューターで実行されているオペレーティングシステムと一致する言語パックのみを展開します。

    -   追加の言語パックをターゲットコンピューターに展開するには、 **Windows Installer (.msi) ファイルを使用して**、この手順に従って app-v 5.1 クライアントをインストールします。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">展開の種類</th>
    <th align="left">このファイルを展開</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>コンピューターで32ビットの Microsoft Windows オペレーティングシステムが実行されている</p></td>
    <td align="left"><p>appv_client_LP_xxxx_ x86.msi</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>コンピューターで64ビットの Microsoft Windows オペレーティングシステムが実行されている</p></td>
    <td align="left"><p>appv_client_LP_xxxx_ x64.msi</p></td>
    </tr>
    </tbody>
    </table>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 関連トピック


[APP-V 5.1 の展開](deploying-app-v-51.md)

[Client の構成設定について](about-client-configuration-settings51.md)

[App-V 5.1 Client をアンインストールする方法](how-to-uninstall-the-app-v-51-client.md)









