---
title: Client の構成設定について
description: Client の構成設定について
author: dansimp
ms.assetid: cc7ae28c-b2ac-4f68-b992-5ccdbd5316a4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 289f5b35ac223d488152ff7ee1f42b1cf50341df
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814939"
---
# Client の構成設定について


Microsoft Application Virtualization (App-v) 5.0 クライアントでは、その構成がレジストリに格納されます。 レジストリ内のデータの形式を理解している場合は、クライアントに関する有用な情報を収集することができます。 また、レジストリエントリを変更して、多くのクライアント操作を構成することもできます。 このトピックでは、App-v 5.0 クライアント構成の設定を示し、その使い方について説明します。 PowerShell を使用して、クライアント構成の設定を変更することができます。 PowerShell と App-v 5.0 の使用方法について詳しくは、「 [Powershell を使用](administering-app-v-by-using-powershell.md)した App-v の管理」をご覧ください。

## <a href="" id="---------app-v-5-0-client-configuration-settings"></a> App-v 5.0 クライアント構成の設定


次の表は、App-v 5.0 クライアントの構成設定に関する情報を示しています。

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">設定名</th>
<th align="left">設定フラグ</th>
<th align="left">説明</th>
<th align="left">オプションを設定する</th>
<th align="left">レジストリキー値</th>
<th align="left">ポリシーの状態のキーと値が無効になっている</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>PackageInstallationRoot</p></td>
<td align="left"><p>PACKAGEINSTALLATIONROOT</p></td>
<td align="left"><p>すべての新しいアプリケーションと更新プログラムをインストールするディレクトリを指定します。</p></td>
<td align="left"><p>String</p></td>
<td align="left"><p>Streaming\PackageInstallationRoot</p></td>
<td align="left"><p>ポリシー値が書き込まれていない (構成されていない)</p></td>
</tr>
<tr class="even">
<td align="left"><p>パッケージパッケージ</p></td>
<td align="left"><p>パッケージパッケージ</p></td>
<td align="left"><p>パッケージコンテンツをダウンロードするためのソースの場所をオーバーライドします。</p></td>
<td align="left"><p>String</p></td>
<td align="left"><p>Streaming\PackageSourceRoot</p></td>
<td align="left"><p>ポリシー値が書き込まれていない (構成されていない)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AllowHighCostLaunch</p></td>
<td align="left"><p>利用不可。</p></td>
<td align="left"><p>この設定は、従量制課金接続を介して接続された Windows 8 コンピューターで、仮想化されたアプリケーションを起動するかどうかを制御します (4G など)。</p></td>
<td align="left"><p>True (有効)、False (無効状態)</p></td>
<td align="left"><p>Streaming\AllowHighCostLaunch</p></td>
<td align="left"><p>0</p></td>
</tr>
<tr class="even">
<td align="left"><p>ReestablishmentRetries</p></td>
<td align="left"><p>利用不可。</p></td>
<td align="left"><p>ドロップしたセッションを再試行する回数を指定します。</p></td>
<td align="left"><p>Integer (0-99)</p></td>
<td align="left"><p>Streaming\ReestablishmentRetries</p></td>
<td align="left"><p>ポリシー値が書き込まれていない (構成されていない)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ReestablishmentInterval</p></td>
<td align="left"><p>利用不可。</p></td>
<td align="left"><p>ドロップされたセッションを再確立するまでの試行の秒数を指定します。</p></td>
<td align="left"><p>Integer (0-3600)</p></td>
<td align="left"><p>Streaming\ReestablishmentInterval</p></td>
<td align="left"><p>ポリシー値が書き込まれていない (構成されていない)</p></td>
</tr>
<tr class="even">
<td align="left"><p>ロード</p></td>
<td align="left"><p>ロード</p></td>
<td align="left"><p>特定のコンピューター上の App-v によって、新しいパッケージを自動的に読み込む方法を指定します。</p></td>
<td align="left"><p>(0x0) なし;(0x1) 以前に使用されました。(0x2) すべて</p></td>
<td align="left"><p>Streaming\AutoLoad</p></td>
<td align="left"><p>ポリシー値が書き込まれていない (構成されていない)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LocationProvider</p></td>
<td align="left"><p>利用不可。</p></td>
<td align="left"><p>IAppvPackageLocationProvider インターフェイスの互換性のある実装の CLSID を指定します。</p></td>
<td align="left"><p>String</p></td>
<td align="left"><p>Streaming\LocationProvider</p></td>
<td align="left"><p>ポリシー値が書き込まれていない (構成されていない)</p></td>
</tr>
<tr class="even">
<td align="left"><p>CertFilterForClientSsl</p></td>
<td align="left"><p>利用不可。</p></td>
<td align="left"><p>証明書ストア内の有効な証明書へのパスを指定します。</p></td>
<td align="left"><p>String</p></td>
<td align="left"><p>Streaming\CertFilterForClientSsl</p></td>
<td align="left"><p>ポリシー値が書き込まれていない (構成されていない)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>VerifyCertificateRevocationList</p></td>
<td align="left"><p>利用不可。</p></td>
<td align="left"><p>HTTPS を使用して steaming する前にサーバー証明書の取り消し状態を確認します。</p></td>
<td align="left"><p>True (有効)、False (無効状態)</p></td>
<td align="left"><p>Streaming\VerifyCertificateRevocationList</p></td>
<td align="left"><p>0</p></td>
</tr>
<tr class="even">
<td align="left"><p>SharedContentStoreMode</p></td>
<td align="left"><p>SHAREDCONTENTSTOREMODE</p></td>
<td align="left"><p>ストリーミングされたパッケージコンテンツをローカルのハードディスクに保存しないように指定します。</p></td>
<td align="left"><p>True (有効)、False (無効状態)</p></td>
<td align="left"><p>Streaming\SharedContentStoreMode</p></td>
<td align="left"><p>0</p></td>
</tr>
<tr class="odd">
<td align="left"><p>名前</p>
<div class="alert">
<strong>注</strong><br/><p>この設定は、 <strong> AppvclientConfiguration コマンドレットを使用して変更することはできません </strong> 。 AppvPublishingServer コマンドレットを使用する必要があり <strong> </strong> ます。</p>
</div>
<div>

</div></td>
<td align="left"><p>発行サーバー名</p></td>
<td align="left"><p>発行サーバーの名前が表示されます。</p></td>
<td align="left"><p>String</p></td>
<td align="left"><p>Publishing\Servers {serverId} \ FriendlyName</p></td>
<td align="left"><p>ポリシー値が書き込まれていない (構成されていない)</p></td>
</tr>
<tr class="even">
<td align="left"><p>URL</p>
<div class="alert">
<strong>注</strong><br/><p>この設定は、 <strong> AppvclientConfiguration コマンドレットを使用して変更することはできません </strong> 。 AppvPublishingServer コマンドレットを使用する必要があり <strong> </strong> ます。</p>
</div>
<div>

</div></td>
<td align="left"><p>発行する SERVERURL</p></td>
<td align="left"><p>発行サーバーの URL を表示します。</p></td>
<td align="left"><p>String</p></td>
<td align="left"><p>Publishing\Servers {serverId} \ URL</p></td>
<td align="left"><p>ポリシー値が書き込まれていない (構成されていない)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>GlobalRefreshEnabled</p>
<div class="alert">
<strong>注</strong><br/><p>この設定は、 <strong> AppvclientConfiguration コマンドレットを使用して変更することはできません </strong> 。 AppvPublishingServer コマンドレットを使用する必要があり <strong> </strong> ます。</p>
</div>
<div>

</div></td>
<td align="left"><p>GLOBALREFRESHENABLED</p></td>
<td align="left"><p>グローバル発行の更新 (ブール値) を有効にします。</p></td>
<td align="left"><p>True (有効)、False (無効状態)</p></td>
<td align="left"><p>Publishing\Servers {serverId} \ GlobalEnabled</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="even">
<td align="left"><p>GlobalRefreshOnLogon</p>
<div class="alert">
<strong>注</strong><br/><p>この設定は、 <strong> AppvclientConfiguration コマンドレットを使用して変更することはできません </strong> 。 AppvPublishingServer コマンドレットを使用する必要があり <strong> </strong> ます。</p>
</div>
<div>

</div></td>
<td align="left"><p>GLOBALREFRESHONLOGON</p></td>
<td align="left"><p>ログオン時にグローバル公開の更新をトリガーします。 ブール</p></td>
<td align="left"><p>True (有効)、False (無効状態)</p></td>
<td align="left"><p>Publishing\Servers {serverId} \ GlobalLogonRefresh</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="odd">
<td align="left"><p>GlobalRefreshInterval</p>
<div class="alert">
<strong>注</strong><br/><p>この設定は、 <strong> AppvclientConfiguration コマンドレットを使用して変更することはできません </strong> 。 AppvPublishingServer コマンドレットを使用する必要があり <strong> </strong> ます。</p>
</div>
<div>

</div></td>
<td align="left"><p>GLOBALREFRESHINTERVAL  </p></td>
<td align="left"><p>GlobalRefreshIntervalUnit を使った公開の更新間隔を指定します。 パッケージの更新を無効にするには、[0] を選びます。</p></td>
<td align="left"><p>Integer (0-744</p></td>
<td align="left"><p>Publishing\Servers{serverId}\GlobalPeriodicRefreshInterval</p></td>
<td align="left"><p>0</p></td>
</tr>
<tr class="even">
<td align="left"><p>GlobalRefreshIntervalUnit</p>
<div class="alert">
<strong>注</strong><br/><p>この設定は、 <strong> AppvclientConfiguration コマンドレットを使用して変更することはできません </strong> 。 AppvPublishingServer コマンドレットを使用する必要があり <strong> </strong> ます。</p>
</div>
<div>

</div></td>
<td align="left"><p>GLOBALREFRESHINTERVALUNI</p></td>
<td align="left"><p>間隔の単位 (Hour 0-23, Day 0-31) を指定します。 </p></td>
<td align="left"><p>0 (hour)、1日の場合</p></td>
<td align="left"><p>Publishing\Servers {serverId} \ GlobalPeriodicRefreshIntervalUnit</p></td>
<td align="left"><p>件</p></td>
</tr>
<tr class="odd">
<td align="left"><p>UserRefreshEnabled</p>
<div class="alert">
<strong>注</strong><br/><p>この設定は、 <strong> AppvclientConfiguration コマンドレットを使用して変更することはできません </strong> 。 AppvPublishingServer コマンドレットを使用する必要があり <strong> </strong> ます。</p>
</div>
<div>

</div></td>
<td align="left"><p>USERREFRESHENABLED </p></td>
<td align="left"><p>ユーザー発行の更新 (ブール値) を有効にします。</p></td>
<td align="left"><p>True (有効)、False (無効状態)</p></td>
<td align="left"><p>Publishing\Servers {serverId} \ UserEnabled</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="even">
<td align="left"><p>UserRefreshOnLogon 使い方</p>
<div class="alert">
<strong>注</strong><br/><p>この設定は、 <strong> AppvclientConfiguration コマンドレットを使用して変更することはできません </strong> 。 AppvPublishingServer コマンドレットを使用する必要があり <strong> </strong> ます。</p>
</div>
<div>

</div></td>
<td align="left"><p>USERREFRESHONLOGON 使い方</p></td>
<td align="left"><p>ユーザー公開の更新方法をトリガーします。 ブール</p>
<p>文字数 (スペースを含む):60</p></td>
<td align="left"><p>True (有効)、False (無効状態)</p></td>
<td align="left"><p>Publishing\Servers {serverId} \ UserLogonRefresh</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="odd">
<td align="left"><p>UserRefreshInterval</p>
<div class="alert">
<strong>注</strong><br/><p>この設定は、 <strong> AppvclientConfiguration コマンドレットを使用して変更することはできません </strong> 。 AppvPublishingServer コマンドレットを使用する必要があり <strong> </strong> ます。</p>
</div>
<div>

</div></td>
<td align="left"><p>USERREFRESHINTERVAL     </p></td>
<td align="left"><p>UserRefreshIntervalUnit を使った公開の更新間隔を指定します。 パッケージの更新を無効にするには、[0] を選びます。</p>
<p>文字数 (スペースを含む):85</p></td>
<td align="left"><p>Integer (0-744 時間)</p></td>
<td align="left"><p>Publishing\Servers{serverId}\UserPeriodicRefreshInterval</p></td>
<td align="left"><p>0</p></td>
</tr>
<tr class="even">
<td align="left"><p>UserRefreshIntervalUnit</p>
<div class="alert">
<strong>注</strong><br/><p>この設定は、 <strong> AppvclientConfiguration コマンドレットを使用して変更することはできません </strong> 。 AppvPublishingServer コマンドレットを使用する必要があり <strong> </strong> ます。</p>
</div>
<div>

</div></td>
<td align="left"><p>USERREFRESHINTERVALUNIT  </p></td>
<td align="left"><p>間隔の単位 (Hour 0-23, Day 0-31) を指定します。 </p></td>
<td align="left"><p>0 (hour)、1日の場合</p></td>
<td align="left"><p>Publishing\Servers {serverId} \ UserPeriodicRefreshIntervalUnit</p></td>
<td align="left"><p>件</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MigrationMode</p></td>
<td align="left"><p>MIGRATIONMODE</p></td>
<td align="left"><p>移行モードでは、以前のバージョンの App-v を使用して作成されたパッケージのショートカットと FTA を、App-v クライアントで変更することができます。</p></td>
<td align="left"><p>True (有効状態)False (無効状態)</p></td>
<td align="left"><p>Coexistence\MigrationMode</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>CEIPOPTIN</p></td>
<td align="left"><p>CEIPOPTIN</p></td>
<td align="left"><p>アプリケーションをさらに向上させるために、App-v 5.0 クライアントを実行しているコンピューターで特定の使用状況情報を収集して返すことを許可します。</p></td>
<td align="left"><p>無効の場合は0有効にする場合は1</p></td>
<td align="left"><p>ソフトウェア/Microsoft/AppV/CEIP/CEIPEnable</p></td>
<td align="left"><p>0</p></td>
</tr>
<tr class="odd">
<td align="left"><p>EnablePackageScripts</p></td>
<td align="left"><p>ENABLEPACKAGESCRIPTS</p></td>
<td align="left"><p>実行する必要がある構成ファイルのパッケージマニフェストで定義されているスクリプトを有効にします。</p></td>
<td align="left"><p>True (有効)、False (無効状態)</p></td>
<td align="left"><p>\Scripting\EnablePackageScripts</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>RoamingFileExclusions</p></td>
<td align="left"><p>ROAMINGFILEEXCLUSIONS</p></td>
<td align="left"><p>ユーザー&#39;s プロファイルでローミングしない% userprofile% を基準としたファイルパスを指定します。 使用例:/ROAMINGFILEEXCLUSIONS =&#39;デスクトップ、マイピクチャ&#39;</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>RoamingRegistryExclusions</p></td>
<td align="left"><p>ROAMINGREGISTRYEXCLUSIONS</p></td>
<td align="left"><p>ユーザープロファイルでローミングされないレジストリパスを指定します。 使用例:/ROAMINGREGISTRYEXCLUSIONS = ソフトウェア \ クラス; ソフトウェア \ クライアント</p></td>
<td align="left"><p>String</p></td>
<td align="left"><p>Integration\RoamingRegistryExclusions</p></td>
<td align="left"><p>ポリシー値が書き込まれていない (構成されていない)</p></td>
</tr>
<tr class="even">
<td align="left"><p>統合ルートユーザ</p></td>
<td align="left"><p>利用不可。</p></td>
<td align="left"><p>ユーザーごとに公開されたパッケージの現在のバージョンに関連付けられているシンボリックリンクを作成する場所を指定します。 ショートカットやファイルの種類の関連付けなどのすべての仮想アプリケーションの拡張は、このパスをポイントします。 パスを指定しない場合、パッケージを公開するときにシンボリックリンクは使用されません。 例:%localappdata%\Microsoft\AppV\Client\Integration.</p></td>
<td align="left"><p>String</p></td>
<td align="left"><p>統合と統合 rootuser</p></td>
<td align="left"><p>ポリシー値が書き込まれていない (構成されていない)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>統合 Rootグローバル</p></td>
<td align="left"><p>利用不可。</p></td>
<td align="left"><p>グローバルに公開されたパッケージの現在のバージョンに関連付けられているシンボリックリンクを作成する場所を指定します。 ショートカットやファイルの種類の関連付けなどのすべての仮想アプリケーションの拡張は、このパスをポイントします。 パスを指定しない場合、パッケージを公開するときにシンボリックリンクは使用されません。 例:%allusersprofile%\Microsoft\AppV\Client\Integration</p></td>
<td align="left"><p>String</p></td>
<td align="left"><p>統合と統合 rootグローバル</p></td>
<td align="left"><p>ポリシー値が書き込まれていない (構成されていない)</p></td>
</tr>
<tr class="even">
<td align="left"><p>VirtualizableExtensions</p></td>
<td align="left"><p>利用不可。</p></td>
<td align="left"><p>ローカルにインストールされたアプリケーションを仮想環境で実行できるかどうかを判断するために使用できるファイル名拡張子のコンマ区切りリスト。</p>
<p>公開時にショートカット、FTAs、およびその他の拡張ポイントを作成すると、その拡張ポイントに関連付けられたアプリケーションがローカルにインストールされている場合、App-v はファイル名の拡張子を一覧と比較します。 拡張機能がある場合は、 <strong> runvirtual </strong> コマンドラインパラメーターが追加され、アプリケーションは実質的に実行されます。</p>
<p><strong>Runvirtual パラメーターの詳細につい </strong> ては、「 <a href="running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md" data-raw-source="[Running a Locally Installed Application Inside a Virtual Environment with Virtualized Applications](running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md)"> 仮想化されたアプリケーションを使って、仮想環境内でローカルにインストールされたアプリケーションを実行する」を参照してください </a> 。</p></td>
<td align="left"><p>String</p></td>
<td align="left"><p>統合 \ virtualizableextensions</p></td>
<td align="left"><p>ポリシーの値が書き込まれない</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ReportingEnabled</p></td>
<td align="left"><p>利用不可。</p></td>
<td align="left"><p>クライアントが情報をレポートサーバーに返すことができるようにします。</p></td>
<td align="left"><p>True (有効)、False (無効状態)</p></td>
<td align="left"><p>Reporting\EnableReporting</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="even">
<td align="left"><p>ReportingServerURL</p></td>
<td align="left"><p>利用不可。</p></td>
<td align="left"><p>クライアント情報が保存されている、レポートサーバー上の場所を指定します。</p></td>
<td align="left"><p>String</p></td>
<td align="left"><p>Reporting\ReportingServer</p></td>
<td align="left"><p>ポリシー値が書き込まれていない (構成されていない)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Reportingdatacachlimit</p></td>
<td align="left"><p>利用不可。</p></td>
<td align="left"><p>レポート情報を格納する XML キャッシュの最大サイズ (MB) を指定します。 サイズは、メモリ内のキャッシュに適用されます。 上限に達すると、ログファイルがロールオーバーされます。 0 ~ 1024 の間で設定します。</p></td>
<td align="left"><p>Integer [0-1024]</p></td>
<td align="left"><p>Reporting\DataCacheLimit</p></td>
<td align="left"><p>ポリシー値が書き込まれていない (構成されていない)</p></td>
</tr>
<tr class="even">
<td align="left"><p>Reportingの各の Locksize</p></td>
<td align="left"><p>利用不可。</p></td>
<td align="left"><p>アップロード要求を報告するためにサーバーに送信する最大サイズ (バイト単位) を指定します。 これにより、ログのサイズが大きくなったときに、永続的な送信エラーが発生しないようにすることができます。 1024と無制限の間で設定します。</p></td>
<td align="left"><p>Integer [1024-実質無制限]</p></td>
<td align="left"><p>Reporting\DataBlockSize</p></td>
<td align="left"><p>ポリシー値が書き込まれていない (構成されていない)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ReportingStartTime</p></td>
<td align="left"><p>利用不可。</p></td>
<td align="left"><p>クライアントの開始時刻を指定して、データをレポートサーバーに送信します。 1日の時刻に対応する0-23 の間に有効な整数を指定する必要があります。 既定では、 <strong> reportingstarttime は、 </strong> 現在の日である 10 P. または22で開始されます。</p>
<div class="alert">
<strong>注</strong><br/><p>この設定は、App-v 5.0 クライアントを実行しているコンピューターが少なくともオフラインになる可能性のある時刻に設定する必要があります。</p>
</div>
<div>

</div></td>
<td align="left"><p>整数 (0 ~ 23)</p></td>
<td align="left"><p>レポート \ 開始時刻</p></td>
<td align="left"><p>ポリシー値が書き込まれていない (構成されていない)</p></td>
</tr>
<tr class="even">
<td align="left"><p>ReportingInterval</p></td>
<td align="left"><p>利用不可。</p></td>
<td align="left"><p>クライアントがデータをレポートサーバーに再送信するために使用する再試行間隔を指定します。</p></td>
<td align="left"><p>Integer</p></td>
<td align="left"><p>Reporting\RetryInterval</p></td>
<td align="left"><p>ポリシー値が書き込まれていない (構成されていない)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ReportingRandomDelay</p></td>
<td align="left"><p>利用不可。</p></td>
<td align="left"><p>レポートサーバーに送信されるデータの最大遅延 (分単位) を指定します。 スケジュールされたタスクが開始されると、クライアントは0と ReportingRandomDelay の間のランダムな遅延を生成 <strong> </strong> し、データを送信する前に指定された期間待機します。 これは、サーバーでの競合を防ぐのに役立ちます。</p></td>
<td align="left"><p>Integer [0-ReportingRandomDelay]</p></td>
<td align="left"><p>Reporting\RandomDelay</p></td>
<td align="left"><p>ポリシー値が書き込まれていない (構成されていない)</p></td>
</tr>
<tr class="even">
<td align="left"><p>EnableDynamicVirtualization</p>
<div class="alert">
<strong>重要</strong><br/><p>この設定は、App-v 5.0 SP2 以降でのみ使用できます。</p>
</div>
<div>

</div></td>
<td align="left"><p>利用不可。</p></td>
<td align="left"><p>サポートされているシェルの拡張機能、ブラウザーヘルパーオブジェクト、アクティブな X コントロールを仮想アプリケーションで仮想化して実行できるようにします。</p></td>
<td align="left"><p>1 (有効)、0 (無効)</p></td>
<td align="left"><p>HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\Virtualization</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>EnablePublishingRefreshUI</p>
<div class="alert">
<strong>重要</strong><br/><p>この設定は、App-v 5.0 SP2 でのみ使用できます。</p>
</div>
<div>

</div></td>
<td align="left"><p>利用不可。</p></td>
<td align="left"><p>App-v 5.0 クライアントを実行しているコンピューターの公開更新の進行状況バーを有効にします。</p></td>
<td align="left"><p>1 (有効)、0 (無効)</p></td>
<td align="left"><p>HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\Publishing</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>HideUI</p>
<div class="alert">
<strong>重要</strong><br/><p>この設定は、App-v 5.0 SP2 でのみ使用できます。</p>
</div>
<div>

</div></td>
<td align="left"><p>利用不可。</p></td>
<td align="left"><p>公開の更新の進行状況バーを非表示にします。</p></td>
<td align="left"><p>1 (有効)、0 (無効)</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>プロセスの仮想コンポーネントの方法</p></td>
<td align="left"><p>利用不可。</p></td>
<td align="left"><p>プロセスパス (ワイルドカードが含まれている可能性がある) の一覧を指定します。これは、動的仮想化 (サポートされているシェル拡張機能、ブラウザーヘルパーオブジェクト、および ActiveX コントロール) を使用するための候補です。 完全なパスがこれらの項目のいずれかに一致するプロセスのみが、動的仮想化を使うことができます。</p></td>
<td align="left"><p>String</p></td>
<td align="left"><p>Virtualization\ProcessesUsingVirtualComponents</p></td>
<td align="left"><p>空の文字列。</p></td>
</tr>
</tbody>
</table>








## 関連トピック


[App-V 5.0 Sequencer および Client の展開](deploying-the-app-v-50-sequencer-and-client.md)

[ADMX テンプレートとグループ ポリシーを使用して App-V 5.0 Client 構成を変更する方法](how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md)

[APP-V Client を展開する方法](how-to-deploy-the-app-v-client-gb18030.md)









