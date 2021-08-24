---
title: アプリケーションの公開とクライアントとのやり取り
description: アプリケーションの公開とクライアントとのやり取り
author: dansimp
ms.assetid: 36a4bf6f-a917-41a6-9856-6248686df352
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b94ef87043d428ac92fe1656b3afeb8a8b743808
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910822"
---
# <a name="application-publishing-and-client-interaction"></a>アプリケーションの公開とクライアントとのやり取り


この記事では、一般的な App-V クライアント操作とローカル オペレーティング システムとの統合に関する技術情報を提供します。

-   [Sequencer によって作成された App-V パッケージ ファイル](#bkmk-appv-pkg-files-list)

-   [appv ファイルには何がありますか?](#bkmk-appv-file-contents)

-   [App-V クライアント のデータストレージの場所](#bkmk-files-data-storage)

-   [パッケージ レジストリ](#bkmk-pkg-registry)

-   [App-V パッケージ ストアの動作](#bkmk-pkg-store-behavior)

-   [ローミング レジストリとデータ](#bkmk-roaming-reg-data)

-   [App-V クライアント アプリケーションのライフサイクル管理](#bkmk-clt-app-lifecycle)

-   [App-V パッケージの統合](#bkmk-integr-appv-pkgs)

-   [動的構成処理](#bkmk-dynamic-config)

-   [サイド バイ サイド アセンブリ](#bkmk-sidebyside-assemblies)

-   [クライアント ログ](#bkmk-client-logging)

追加情報については [、「Microsoft Application Virtualization (App-V) Documentation Resources Download Page」を参照してください](https://www.microsoft.com/download/details.aspx?id=27760)。

## <a name="app-v-package-files-created-by-the-sequencer"></a><a href="" id="bkmk-appv-pkg-files-list"></a>Sequencer によって作成された App-V パッケージ ファイル


Sequencer は App-V パッケージを作成し、仮想化アプリケーションを生成します。 シーケンス処理によって、次のファイルが作成されます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ファイル</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>.appv</p></td>
<td align="left"><ul>
<li><p>プライマリ パッケージ ファイル(シーケンス 処理からキャプチャされたアセットと状態情報が含まれます)。</p></li>
<li><p>パッケージ ファイル、発行情報、およびレジストリのアーキテクチャをトークン化された形式で行い、配信時にコンピューターと特定のユーザーに再適用できます。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>.MSI</p></td>
<td align="left"><p>手動で、またはサードパーティの展開プラットフォームを使用して .appv ファイルを展開するために使用できる実行可能な展開ラッパー。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>_DeploymentConfig.XML</p></td>
<td align="left"><p>App-V クライアントを実行しているコンピューター上のすべてのユーザーにグローバルに展開されるパッケージ内のすべてのアプリケーションの既定の発行パラメーターをカスタマイズするために使用するファイル。</p></td>
</tr>
<tr class="even">
<td align="left"><p>_UserConfig.XML</p></td>
<td align="left"><p>App-V クライアントを実行しているコンピューター上の特定のユーザーに展開されたパッケージ内のすべてのアプリケーションの発行パラメーターをカスタマイズするために使用するファイル。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Report.xml</p></td>
<td align="left"><p>省略されたドライバー、ファイル、レジストリの場所など、シーケンス 処理に起因するメッセージの概要。</p></td>
</tr>
<tr class="even">
<td align="left"><p>.CAB</p></td>
<td align="left"><p><em>オプション: </em> 以前にシーケンスされた仮想アプリケーション パッケージを自動的に再構築するために使用されるパッケージ アクセラレータ ファイル。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>.appvt</p></td>
<td align="left"><p><em>オプション: 一般的に再利用されるシーケンサー設定を保持するために使用 </em> されるシーケンサー テンプレート ファイル。</p></td>
</tr>
</tbody>
</table>

 

シーケンスの詳細については [、「Application Virtualization Sequencing Guide」を参照してください](https://go.microsoft.com/fwlink/?LinkID=269810)。

## <a name="whats-in-the-appv-file"></a><a href="" id="bkmk-appv-file-contents"></a>appv ファイルには何がありますか?


appv ファイルは、XML ファイルと非 XML ファイルを一緒に 1 つのエンティティに格納するコンテナーです。 このファイルは、Open Packaging Conventions (OPC) 標準に基づく AppX 形式で作成されます。

appv ファイルの内容を表示するには、パッケージのコピーを作成し、コピーしたファイルの名前を ZIP 拡張子に変更します。

appv ファイルには、仮想アプリケーションの作成および発行時に使用される次のフォルダーとファイルが含まれます。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名前</th>
<th align="left">型</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ルート</p></td>
<td align="left"><p>ファイル フォルダー</p></td>
<td align="left"><p>シーケンス処理中にキャプチャされる仮想化アプリケーションのファイル システムを含むディレクトリ。</p></td>
</tr>
<tr class="even">
<td align="left"><p>[Content_Types].xml</p></td>
<td align="left"><p>XML ファイル</p></td>
<td align="left"><p>appv ファイル内のコア コンテンツ タイプの一覧 (DLL、EXE、BIN など)。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AppxBlockMap.xml</p></td>
<td align="left"><p>XML ファイル</p></td>
<td align="left"><p>App-V パッケージ内のファイルの場所と検証を可能にする File、Block、および BlockMap 要素を使用する appv ファイルのレイアウト。</p></td>
</tr>
<tr class="even">
<td align="left"><p>AppxManifest.xml</p></td>
<td align="left"><p>XML ファイル</p></td>
<td align="left"><p>パッケージの追加、発行、および起動に必要な情報を含むパッケージのメタデータ。 拡張ポイント (ファイルの種類の関連付けとショートカット) と、パッケージに関連付けられた名前と GUID が含まれます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>FilesystemMetadata.xml</p></td>
<td align="left"><p>XML ファイル</p></td>
<td align="left"><p>属性 (ディレクトリ、ファイル、不透明なディレクトリ、空のディレクトリ、長い名前と短い名前など) を含む、シーケンス中にキャプチャされるファイルの一覧。</p></td>
</tr>
<tr class="even">
<td align="left"><p>PackageHistory.xml</p></td>
<td align="left"><p>XML ファイル</p></td>
<td align="left"><p>シーケンス コンピューター (オペレーティング システムのバージョン、Internet Explorer バージョン、.Net Framework バージョン) とプロセス (アップグレード、パッケージ バージョン) に関する情報。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Registry.dat</p></td>
<td align="left"><p>DAT ファイル</p></td>
<td align="left"><p>パッケージのシーケンシング プロセス中にキャプチャされたレジストリ キーと値。</p></td>
</tr>
<tr class="even">
<td align="left"><p>StreamMap.xml</p></td>
<td align="left"><p>XML ファイル</p></td>
<td align="left"><p>プライマリ機能ブロックと発行機能ブロックのファイルの一覧。 発行機能ブロックには、ICO ファイルと、パッケージを発行するために必要なファイル (EXE および DLL) が含まれます。 存在する場合、プライマリ機能ブロックには、シーケンス処理中にストリーミング用に最適化されたファイルが含まれます。</p></td>
</tr>
</tbody>
</table>

 

## <a name="app-v-client-data-storage-locations"></a><a href="" id="bkmk-files-data-storage"></a>App-V クライアント のデータストレージの場所


App-V クライアントはタスクを実行して、仮想アプリケーションが適切に実行され、ローカルにインストールされたアプリケーションと同様に動作します。 仮想アプリケーションを開いて実行するプロセスでは、仮想ファイル システムとレジストリからのマッピングが必要であり、ユーザーが期待する従来のアプリケーションの必要なコンポーネントをアプリケーションに確実に持つ必要があります。 このセクションでは、仮想アプリケーションの実行に必要なアセットについて説明し、App-V がアセットを保存する場所を一覧表示します。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名前</th>
<th align="left">場所</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>パッケージ ストア</p></td>
<td align="left"><p>%ProgramData%\App-V</p></td>
<td align="left"><p>読み取り専用パッケージ ファイルの既定の場所</p></td>
</tr>
<tr class="even">
<td align="left"><p>マシン カタログ</p></td>
<td align="left"><p>%ProgramData%\Microsoft\AppV\Client\Catalog</p></td>
<td align="left"><p>コンピューターごとの構成ドキュメントが含まれる</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ユーザー カタログ</p></td>
<td align="left"><p>%AppData%\Microsoft\AppV\Client\Catalog</p></td>
<td align="left"><p>ユーザーごとの構成ドキュメントが含まれる</p></td>
</tr>
<tr class="even">
<td align="left"><p>ショートカット バックアップ</p></td>
<td align="left"><p>%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups</p></td>
<td align="left"><p>パッケージの非公開で復元を有効にする以前の統合ポイントを格納する</p></td>
</tr>
<tr class="odd">
<td align="left"><p>書き込み時のコピー (COW) ローミング</p></td>
<td align="left"><p>%AppData%\Microsoft\AppV\Client\VFS</p></td>
<td align="left"><p>パッケージ変更の書き込み可能なローミングの場所</p></td>
</tr>
<tr class="even">
<td align="left"><p>書き込み時のコピー (COW) ローカル</p></td>
<td align="left"><p>%LocalAppData%\Microsoft\AppV\Client\VFS</p></td>
<td align="left"><p>パッケージ変更の書き込み可能なローミング以外の場所</p></td>
</tr>
<tr class="odd">
<td align="left"><p>コンピューター レジストリ</p></td>
<td align="left"><p>HKLM\Software\Microsoft\AppV</p></td>
<td align="left"><p>コンピューターまたはグローバルに発行されたパッケージの VReg を含むパッケージの状態情報が含まれています (Machine hive)</p></td>
</tr>
<tr class="even">
<td align="left"><p>ユーザー レジストリ</p></td>
<td align="left"><p>HKCU\Software\Microsoft\AppV</p></td>
<td align="left"><p>VReg を含むユーザー パッケージの状態情報を含む</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ユーザー レジストリ クラス</p></td>
<td align="left"><p>HKCU\Software\Classes\AppV</p></td>
<td align="left"><p>追加のユーザー パッケージの状態情報が含まれています</p></td>
</tr>
</tbody>
</table>

 

表の詳細については、以下のセクションおよびドキュメント全体で説明します。

### <a name="package-store"></a>パッケージ ストア

App-V クライアントは、パッケージ ストアにマウントされているアプリケーションアセットを管理します。 この既定の保存場所は、PowerShell コマンドを使用してセットアップ中またはセットアップ後に構成できますが、ローカル レジストリ (キーの下の値) が `%ProgramData%\App-V` `Set-AppVClientConfiguration` `PackageInstallationRoot` 変更 `HKLM\Software\Microsoft\AppV\Client\Streaming` されます。 パッケージ ストアは、クライアント オペレーティング システム上のローカル パスにある必要があります。 個々のパッケージは、パッケージ GUID とバージョン GUID という名前のサブディレクトリのパッケージ ストアに格納されます。

特定のアプリケーションへのパスの例を次に示します。

``` syntax
C:\ProgramData\App-V\PackGUID\VersionGUID
```

セットアップ中にパッケージ ストアの既定の場所を変更するには [、「How to Deploy the App-V Client」を参照してください](how-to-deploy-the-app-v-client-51gb18030.md)。

### <a name="shared-content-store"></a>共有コンテンツ ストア

App-V クライアントが共有コンテンツ ストア モードで構成されている場合、ストリーム 障害が発生した場合はデータがディスクに書き込まれるので、パッケージには最小限のローカル ディスク領域 (発行データ) が必要です。 ローカル ストレージを制限できる VDI 環境では、ディスク領域の使用が非常に望ましく、パフォーマンスの高いネットワークの場所 (SAN など) からアプリケーションをストリーミングすることが望まれます。 共有コンテンツ ストア モードの詳細については、「. <https://go.microsoft.com/fwlink/p/?LinkId=392750>

**備考**  
App-V クライアントで共有コンテンツ ストア構成を使用している場合でも、コンピューターストアとパッケージ ストアはローカル ドライブ上にある必要があります。

 

### <a name="package-catalogs"></a>パッケージ カタログ

App-V クライアントは、次の 2 つのファイル ベースの場所を管理します。

-   **カタログ (ユーザーとコンピューター)。**

-   **レジストリの場所** - パッケージが発行の対象となる方法によって異なります。 コンピューターのカタログ (データ ストア) と、個々のユーザーのカタログがあります。 マシン カタログには、すべてのユーザーまたは任意のユーザーに適用可能なグローバル情報が格納され、ユーザー カタログには特定のユーザーに適用可能な情報が格納されます。 カタログは、動的構成ファイルとマニフェスト ファイルのコレクションです。パッケージ バージョンごとにファイルとレジストリの両方に個別のデータがあります。 

### <a name="machine-catalog"></a>コンピューター カタログ

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>説明</p></td>
<td align="left"><p>パッケージが追加および発行される際に、コンピューター上のユーザーが使用できるパッケージ ドキュメントを格納します。 ただし、パッケージが発行時に "グローバル" である場合は、すべてのユーザーが統合を利用できます。</p>
<p>パッケージがグローバル以外の場合、統合は特定のユーザーにのみ発行されますが、クライアント コンピューター上のすべてのユーザーに変更され表示されるグローバル リソースがまだ存在します (パッケージ ディレクトリが共有ディスクの場所にあるなど)。</p>
<p>コンピューター上のユーザー (グローバルまたは非グローバル) でパッケージを使用できる場合、マニフェストはマシン カタログに格納されます。 パッケージがグローバルに公開される場合、マシン カタログに格納されている動的構成ファイルがあります。したがって、パッケージがグローバルかどうかの決定は、マシン カタログにポリシー ファイル (UserDeploymentConfiguration ファイル) が含されているかどうかを基に定義されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>既定の記憶域の場所</p></td>
<td align="left"><p><code>%programdata%\Microsoft\AppV\Client\Catalog&lt;/code&gt;</p>
<p>この場所は、パッケージ ストアの場所と同じではありません。 パッケージ ストアは、パッケージ ファイルのゴールデン コピーまたは手付かずのコピーです。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>コンピューター カタログ内のファイル</p></td>
<td align="left"><ul>
<li><p>Manifest.xml</p></li>
<li><p>DeploymentConfiguration.xml</p></li>
<li><p>UserManifest.xml (グローバルに発行されたパッケージ)</p></li>
<li><p>UserDeploymentConfiguration.xml (グローバルに発行されたパッケージ)</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>パッケージが接続グループの一部である場合に使用される追加のコンピューター カタログの場所</p></td>
<td align="left"><p>次の場所は、上記の特定のパッケージの場所に加えてです。</p>
<p><code>%programdata%\Microsoft\AppV\Client\Catalog\PackageGroups\ConGroupGUID\ConGroupVerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p>パッケージが接続グループの一部である場合のコンピューター カタログ内の追加ファイル</p></td>
<td align="left"><ul>
<li><p>PackageGroupDescriptor.xml</p></li>
<li><p>UserPackageGroupDescriptor.xml (グローバルに公開された接続グループ)</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### <a name="user-catalog"></a>ユーザー カタログ

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>説明</p></td>
<td align="left"><p>発行プロセス中に作成されます。 パッケージの発行に使用される情報が含まれています。また、パッケージが特定のユーザーにプロビジョニングされるのを確認するために、起動時にも使用されます。 移動場所で作成され、ユーザー固有の発行情報が含まれます。</p>
<p>ユーザーのパッケージが発行される場合、ポリシー ファイルはユーザー カタログに保存されます。 同時に、マニフェストのコピーもユーザー カタログに格納されます。 ユーザーのパッケージ資格が削除されると、関連するパッケージ ファイルがユーザー カタログから削除されます。 ユーザー カタログを見て、管理者は動的構成ファイルの存在を表示できます。このファイルは、パッケージがユーザーの権限を持っているかどうかを示します。</p>
<p>ローミング ユーザーの場合、既定でユーザーをターゲットにした従来の App-V 動作を維持するには、ユーザー カタログがローミングまたは共有の場所にある必要があります。 エンタイトルメントとポリシーはコンピューターではなくユーザーに関連付けられているので、プロビジョニング後にユーザーとローミングする必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>既定の記憶域の場所</p></td>
<td align="left"><p><code>appdata\roaming\Microsoft\AppV\Client\Catalog\Packages\PkgGUID\VerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p>ユーザー カタログ内のファイル</p></td>
<td align="left"><ul>
<li><p>UserManifest.xml</p></li>
<li><p>DynamicConfiguration.xmlまたはUserDeploymentConfiguration.xml</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>パッケージが接続グループの一部である場合に使用される追加のユーザー カタログの場所</p></td>
<td align="left"><p>次の場所は、上記の特定のパッケージの場所に加えてです。</p>
<p><code>appdata\roaming\Microsoft\AppV\Client\Catalog\PackageGroups\PkgGroupGUID\PkgGroupVerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p>パッケージが接続グループの一部である場合のコンピューター カタログ内の追加ファイル</p></td>
<td align="left"><p><code>UserPackageGroupDescriptor.xml</code></p></td>
</tr>
</tbody>
</table>

 

### <a name="shortcut-backups"></a>ショートカット バックアップ

発行プロセス中に、App-V クライアントはショートカットと統合ポイントを [このバックアップ] にバックアップし、パッケージが公開されていないときに、これらの統合ポイントを以前のバージョンに復元できます。 `%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups.`

### <a name="copy-on-write-files"></a>書き込みファイルのコピー

パッケージ ストアには、発行サーバーからストリーミングされたパッケージ ファイルの元のコピーが含まれています。 App-V アプリケーションの通常の操作中に、ユーザーまたはサービスでファイルの変更が必要な場合があります。 これらの変更は、アプリケーションを修復する機能を維持するためにパッケージ ストアで行われたのではなく、これらの変更を削除します。 Copy on Write (COW) と呼ばれるこれらの場所は、ローミングと非ローミングの両方の場所をサポートします。 変更が保存される場所は、ネイティブ エクスペリエンスで変更を書き込むアプリケーションがプログラムされている場所によって異なります。

### <a name="cow-roaming"></a>COW ローミング

前述の COW ローミングの場所には、一般的な %AppData% の場所または \\Users\\{username}\\AppData\\Roaming の場所を対象とするファイルとディレクトリへの変更が格納されます。 これらのディレクトリとファイルは、オペレーティング システムの設定に基づいてローミングされます。

### <a name="cow-local"></a>COW ローカル

COW ローカルの場所はローミングの場所に似ていますが、ローミングサポートが構成されている場合でも、ディレクトリとファイルは他のコンピューターにローミングされません。 上記の COW ローカルの場所には、%AppData% の場所ではなく、一般的なウィンドウに適用される変更が格納されます。 一覧表示されるディレクトリは異なりますが、一般的な場所 (たとえば、共通 AppData と Common AppDataS) には 2 つの場所Windows場所があります。 **S は**、仮想サービスがログオンしているユーザーとは別の管理者特権ユーザーとして変更を要求するときに、制限された場所を示します。 S 以外の場所**には** 、ユーザー ベースの変更が格納されます。

## <a name="package-registry"></a><a href="" id="bkmk-pkg-registry"></a>パッケージ レジストリ


アプリケーションがパッケージ レジストリ データにアクセスするには、App-V クライアントでパッケージ レジストリ データをアプリケーションで使用できる必要があります。 App-V クライアントは、すべてのレジストリ データのバッキング ストアとして実際のレジストリを使用します。

App-V クライアントに新しいパッケージを追加すると、レジストリのコピーが作成されます。パッケージの DAT ファイルはで作成されます `%ProgramData%\Microsoft\AppV\Client\VREG\{Version GUID}.dat` 。 ファイルの名前は、 を持つバージョン GUID です。DAT 拡張子。 このコピーが作成される理由は、パッケージ内の実際のハイブ ファイルが使用されなかったことを確認し、後でパッケージを削除しないことです。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Registry.dat from Package Store</strong></p></td>
<td align="left"><p><strong> &gt; </strong></p></td>
<td align="left"><p><strong>%ProgramData%\Microsoft\AppV\Client\Vreg{VersionGuid}.dat</strong></p></td>
</tr>
</tbody>
</table>

 

パッケージの最初のアプリケーションがクライアントで起動すると、クライアントはハイブ ファイルからコンテンツをステージまたはコピーし、別の場所にパッケージ レジストリ データを再作成します `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\Packages\PackageGuid\Versions\VersionGuid\REGISTRY` 。 ステージレジストリ データには、マシン データとユーザー データの 2 つの異なる種類があります。 コンピューター のデータは、コンピューター上のすべてのユーザー間で共有されます。 ユーザー データは、ユーザーごとにユーザーの特定の場所に対してステージされます `HKCU\Software\Microsoft\AppV\Client\Packages\PackageGuid\Registry\User` 。 コンピューター データは最終的にパッケージの削除時に削除され、ユーザーの非公開操作でユーザー データが削除されます。

### <a name="package-registry-staging-vs-connection-group-registry-staging"></a>パッケージレジストリステージングと接続グループレジストリステージング

接続グループが存在する場合、レジストリをステージングする前のプロセスは true を保持しますが、1 つのハイブ ファイルを処理する代わりに、複数のファイルがあります。 ファイルは、接続グループ XML に表示される順序で処理され、最初のライターが競合を発生します。

ステージ化されたレジストリは、1 つのパッケージ ケースと同じ方法で保持されます。 ステージ化されたユーザー レジストリ データは、無効になるまで、接続グループに対して残ります。接続グループの削除時に、ステージ化されたコンピューター レジストリ データが削除されます。

### <a name="virtual-registry"></a>仮想レジストリ

仮想レジストリ (VREG) の目的は、パッケージ レジストリとネイティブ レジストリの単一のマージ ビューをアプリケーションに提供します。 また、コピーオンライト (COW) 機能も提供します。つまり、仮想プロセスのコンテキストからレジストリに加えた変更は、別の COW の場所に対して行います。 つまり、VREG は最大 3 つの個別のレジストリの場所を 1 つのビューに結合する必要があります。これは、レジストリの COW - パッケージ ( ネイティブ) に設定された場所に基づいて行 &gt; &gt; う必要があります。 レジストリ データに対する要求が行われた場合、要求したデータが見つから順に検索されます。 つまり、COW の場所に値が格納されている場合は、他の場所に進むことはありませんが、COW の場所にデータがない場合は、適切なデータが見つけるまで Package に進み、ネイティブの場所に移動します。

### <a name="registry-locations"></a>レジストリの場所

パッケージを個別に発行するか、接続グループの一部として発行するかに応じて、App-V クライアントがレジストリ情報を格納する 2 つのパッケージ レジストリの場所と 2 つの接続グループの場所があります。 パッケージには 3 つの COW 場所、VREG によって作成および管理される接続グループには 3 つの場所があります。 設定接続グループのグループは共有されない。

**単一パッケージ VReg:**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>場所</strong></p></td>
<td align="left"><p><strong>説明</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>COW</strong></p></td>
<td align="left"><ul>
<li><p>Machine Registry\Client\Packages\PkgGUID\REGISTRY (昇格プロセスのみ書き込み可能)</p></li>
<li><p>User Registry\Client\Packages\PkgGUID\REGISTRY (Software\Classes を除く HKCU で書かれたユーザー ローミング</p></li>
<li><p>ユーザー レジストリ クラス\クライアント\パッケージ\PkgGUID\REGISTRY (HKCU\Software\Classes 書き込みおよび非昇格プロセスの HKLM)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Package</strong></p></td>
<td align="left"><ul>
<li><p>Machine Registry\Client\Packages\PkgGUID\Versions\VerGuid\Registry\Machine</p></li>
<li><p>ユーザー レジストリ クラス\クライアント\パッケージ\PkgGUID\Versions\VerGUID\Registry</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>ネイティブ</strong></p></td>
<td align="left"><ul>
<li><p>ネイティブ アプリケーションレジストリの場所</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

 

**接続グループ VReg:**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>場所</strong></p></td>
<td align="left"><p><strong>説明</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>COW</strong></p></td>
<td align="left"><ul>
<li><p>Machine Registry\Client\PackageGroups\GrpGUID\REGISTRY (昇格プロセスのみ書き込み可能)</p></li>
<li><p>ユーザー レジストリ\クライアント\PackageGroups\GrpGUID\REGISTRY (Software\Classes を除く HKCU に書き込まれるもの</p></li>
<li><p>ユーザー レジストリ クラス\クライアント\PackageGroups\GrpGUID\REGISTRY</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Package</strong></p></td>
<td align="left"><ul>
<li><p>Machine Registry\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</p></li>
<li><p>ユーザー レジストリ クラス\クライアント\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>ネイティブ</strong></p></td>
<td align="left"><ul>
<li><p>ネイティブ アプリケーションレジストリの場所</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

 

HKLM には 2 つの COW 場所があります。昇格されたプロセスと昇格されていないプロセス。 昇格されたプロセスは、常に HKLM の下のセキュリティで保護された COW に HKLM の変更を書き込む。 昇格されていないプロセスは、常に HKCU\\Software\\Classes の下で、セキュリティ保護されていない COW に HKLM の変更を書き込む。 アプリケーションが HKLM から変更を読み取る場合、管理者特権のプロセスは HKLM の下のセキュリティで保護された COW から変更を読み取ります。 両方から昇格されていない読み取りを行い、セキュリティで保護されていない COW で行われた変更を最初に適用します。

### <a name="pass-through-keys"></a>パススルー キー

パススルー キーを使用すると、管理者は、パッケージと COW の場所をバイパスして、ネイティブ レジストリからのみ読み取り可能な特定のキーを構成できます。 パススルーの場所は、(パッケージ固有ではない) コンピューターに対してグローバルであり、キーにパスを追加して構成できます。これは、キーの**PassThroughPaths**と呼ばれる**REG\_MULTI\_SZ**値へのパススルーとして扱う必要があります。 `HKLM\Software\Microsoft\AppV\Subsystem\VirtualRegistry` この複数文字列値 (とその子) の下に表示されるキーは、パススルーとして扱います。

既定では、次の場所がパススルー場所として構成されます。

-   HKEY\_CURRENT\_USER\\SOFTWARE\\Classes\\Local 設定\\Software\\Microsoft\\\Windows\CurrentVersion\\AppModel

-   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Classes\\Local 設定\\Software\\Microsoft\\\Windows\\CurrentVersion\\AppModel

-   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\\Windows\CurrentVersion\\WINEVT

-   HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\services\\eventlog\\Application

-   HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\WMI\\Autologger

-   HKEY\_CURRENT\_USER\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet 設定

-   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\\Windows NT\CurrentVersion\\Perflib

-   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Policies

-   HKEY\_CURRENT\_USER\\SOFTWARE\\Policies

パススルー キーの目的は、仮想アプリケーションが、操作または統合を成功するために仮想アプリケーション以外のアプリケーションに必要なレジストリ データを VReg に書き込むのを確実にすることです。 Policyes キーを使用すると、管理者が設定したグループ ポリシー ベースの設定がパッケージ設定ごとに使用され、使用されません。 AppModel キーは、最新の UI ベースのWindowsと統合するために必要です。 管理者は既定のパススルー キーを変更しませんが、アプリケーションの動作に基づいて、追加のパススルー キーを追加する必要がある場合があります。

## <a name="app-v-package-store-behavior"></a><a href="" id="bkmk-pkg-store-behavior"></a>App-V パッケージ ストアの動作


App-V 5 は、appv ファイルから展開されたアセット ファイルが格納される場所であるパッケージ ストアを管理します。 既定では、この場所は %ProgramData%\\App-V に格納され、空きディスク領域によってのみストレージ機能の点で制限されます。 パッケージ ストアは、前のセクションで説明したように、パッケージとバージョンの GUID によって編成されます。

### <a name="add-packages"></a>パッケージの追加

App-V パッケージは、App-V クライアントを使用してコンピューターに追加するとステージされます。 App-V クライアントは、オンデマンド ステージングを提供します。 発行中または手動の Add-AppVClientPackage では、データ構造がパッケージ ストア (c:\\programdata\\App-V\\{PkgGUID}\{VerGUID}) に組み込まれます。 StreamMap.xml で定義されている発行ブロックで識別されるパッケージ ファイルは、システムに追加され、起動時に適切なアプリケーション資産が存在するためにステージ化されたトップ レベルのフォルダーと子ファイルが追加されます。

### <a name="mounting-packages"></a>マウント パッケージ

パッケージは、PowerShell を使用して明示的に読み込むか `Mount-AppVClientPackage` **、App-V クライアント UI** を使用してパッケージをダウンロードできます。 この操作では、パッケージ全体がパッケージ ストアに完全に読み込まれます。

### <a name="streaming-packages"></a>ストリーミング パッケージ

App-V クライアントは、ストリーミングの既定の動作を変更するように構成できます。 すべてのストリーミング ポリシーは、次のレジストリ キーの下に格納されます `HKEY_LOCAL_MAcHINE\Software\Microsoft\AppV\Client\Streaming` 。 ポリシーは PowerShell コマンドレットを使用して設定されます `Set-AppvClientConfiguration` 。 ストリーミングには、次のポリシーが適用されます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ポリシー</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AllowHighCostLaunch</p></td>
<td align="left"><p>このWindows 8以降では、3G および携帯電話ネットワーク上でのストリーミングが可能になります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>AutoLoad</p></td>
<td align="left"><p>[背景の読み込み] 設定を指定します。</p>
<p><strong>0 </strong> - 無効</p>
<p><strong>1 </strong> – 以前に使用したパッケージのみ</p>
<p><strong>2 </strong> – すべてのパッケージ</p></td>
</tr>
<tr class="odd">
<td align="left"><p>PackageInstallationRoot</p></td>
<td align="left"><p>ローカル コンピューターのパッケージ ストアのルート フォルダー</p></td>
</tr>
<tr class="even">
<td align="left"><p>PackageSourceRoot</p></td>
<td align="left"><p>パッケージをストリームするルートオーバーライド</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SharedContentStoreMode</p></td>
<td align="left"><p>VDI シナリオでの共有コンテンツ ストアの使用を有効にする</p></td>
</tr>
</tbody>
</table>

 

 

これらの設定は、App-V パッケージアセットをクライアントにストリーミングする動作に影響します。 既定では、App-V は、最初の発行およびプライマリ機能ブロックをダウンロードした後に必要なアセットのみをダウンロードします。 ストリーミング パッケージには、次の 3 つの具体的な動作について説明する必要があります。

-   バックグラウンド ストリーミング

-   最適化されたストリーミング

-   ストリーム の障害

### <a name="background-streaming"></a>バックグラウンド ストリーミング

PowerShell コマンドレットを使用して、AutoLoad 設定を使用してバックグラウンド ストリーミングの現在のモードを決定し、コマンドレット Set-AppvClientConfiguration またはレジストリ `Get-AppvClientConfiguration` (HKLM\\SOFTWARE\\Microsoft\\AppV\\ClientStreaming キー) で変更できます。 バックグラウンド ストリーミングは、以前に使用したパッケージをダウンロードする自動読み込み設定が設定されている既定の設定です。 既定の設定 (value=1) に基づく動作は、アプリケーションの起動後にバックグラウンドで App-V データ ブロックをダウンロードします。 この設定は、一緒に (value=0) すべて無効にするか、すべてのパッケージ (value=2) が起動されたかどうかに関して有効にできます。

### <a name="optimized-streaming"></a>最適化されたストリーミング

App-V パッケージは、シーケンス中にプライマリ機能ブロックを使用して構成できます。 この設定により、シーケンス エンジニアは、特定のアプリケーションまたはアプリケーションの起動ファイルを監視し、App-V パッケージ内のデータ ブロックに、パッケージ内のすべてのアプリケーションの最初の起動時にストリーミング用にマークを付けできます。

### <a name="stream-faults"></a>ストリームの障害

発行データの最初のストリームとプライマリ機能ブロックの後、追加のファイルの要求によってストリームエラーが実行されます。 これらのデータ ブロックは、必要に応じてパッケージ ストアにダウンロードされます。 これにより、ユーザーはパッケージの一部のみをダウンロードできます。通常は、パッケージを起動して通常のタスクを実行するのに十分です。 他のすべてのブロックは、ユーザーがパッケージ ストア内に現在ないデータを必要とする操作を開始するとダウンロードされます。

App-V パッケージストリーミングの詳細については、次のページを参照してください <https://go.microsoft.com/fwlink/?LinkId=392770> 。

ストリーミングの最適化のシーケンスは、次の場所で利用できます <https://go.microsoft.com/fwlink/?LinkId=392771> 。

### <a name="package-upgrades"></a>パッケージのアップグレード

App-V パッケージでは、アプリケーションのライフサイクル全体を通じて更新する必要があります。 App-V パッケージのアップグレードは、各バージョンが独自の PackageRoot の場所に作成されるので、パッケージ発行操作と似ています `%ProgramData%\App-V\{PkgGUID}\{newVerGUID}` 。 アップグレード操作は、同じパッケージの他のバージョンから同一ファイルとストリーム ファイルへのハード リンクを作成することで最適化されます。

### <a name="package-removal"></a>パッケージの削除

パッケージが削除される場合の App-V クライアントの動作は、削除に使用されるメソッドによって異なります。 App-V フル インフラストラクチャを使用してアプリケーションを公開解除すると、ユーザー カタログ ファイル (グローバルに公開されたアプリケーションのマシン カタログ) は削除されますが、パッケージ ストアの場所と COW の場所は保持されます。 PowerShell コマンドレットを使用して App-V パッケージを削除すると、 `Remove-AppVClientPackge` パッケージ ストアの場所がクリーンアップされます。 管理サーバーから App-V パッケージを公開解除しても、削除操作は実行されません。 どちらの操作も、パッケージ ストア パッケージ ファイルを削除します。

## <a name="roaming-registry-and-data"></a><a href="" id="bkmk-roaming-reg-data"></a>ローミング レジストリとデータ


App-V 5 は、使用するアプリケーションの書き込み方法に応じて、ローミング時にネイティブに近いエクスペリエンスを提供できます。 既定では、App-V は、オペレーティング システムのローミング構成に基づいて、ローミング場所に格納されている AppData をローミングします。 ファイル ベースのデータを格納する他の場所は、ローミングされていない場所にあるので、コンピューターからコンピューターにローミングされません。

### <a name="roaming-requirements-and-user-catalog-data-storage"></a><a href="" id="bkmk-clt-inter-roam-reqs"></a>ローミング要件とユーザー カタログ データ ストレージ

App-V は、ユーザーのカタログの状態を表すデータを次の形式で格納します。

-   %appdata%\\\Microsoft\\AppV\\Client\\Catalog の下のファイル

-   [レジストリの設定] `HKEY_CURRENT_USER\Software\Microsoft\AppV\Client\Packages`

これらのファイルとレジストリ設定は共にユーザーのカタログを表すので、両方をローミングする必要があります。または特定のユーザーに対してローミングする必要はありません。 App-V では、ローミング %AppData%はサポートされませんが、ユーザーのプロファイル (レジストリ) のローミングはサポートされていません。また、その逆もサポートされません。

**備考**  
**Repair-AppvClientPackage**コマンドレットは、パッケージの発行状態を修復しません。この場合、ユーザーの App-V 状態が %appdata% のデータと見つからないか、または不一致です `HKEY_CURRENT_USER` 。

 

### <a name="registry-based-data"></a>レジストリ ベースのデータ

App-V レジストリ ローミングは、次の表に示すように、2 つのシナリオに分きます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">シナリオ</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>標準ユーザーとして実行されるアプリケーション</p></td>
<td align="left"><p>標準ユーザーが App-V アプリケーションを起動すると、HKLM アプリケーションと HKCU for App-V アプリケーションの両方がコンピューター上の HKCU ハイブに格納されます。 これは、2 つの異なるパスとして表示されます。</p>
<ul>
<li><p>HKLM: HKCU\SOFTWARE\Classes\AppV\Client\Packages{PkgGUID}\REGISTRY\MACHINE\SOFTWARE</p></li>
<li><p>HKCU: HKCU\SOFTWARE\Microsoft\AppV\Client\Packages{PkgGUID}\REGISTRY\USER{UserSID}\SOFTWARE</p></li>
</ul>
<p>場所は、オペレーティング システムの設定に基づいてローミングが有効になります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>昇格を使用して実行されるアプリケーション</p></td>
<td align="left"><p>昇格を使用してアプリケーションを起動すると、次の条件が適用されます。</p>
<ul>
<li><p>HKLM データは、ローカル コンピューター上の HKLM ハイブに格納されます。</p></li>
<li><p>HKCU データは、ユーザー レジストリの場所に格納されます。</p></li>
</ul>
<p>このシナリオでは、これらの設定は通常のオペレーティング システムローミング構成ではローミングされません。その結果、レジストリ キーと値は次の場所に格納されます。</p>
<ul>
<li><p>HKLM\SOFTWARE\Microsoft\AppV\Client\Packages{PkgGUID}{UserSID}\REGISTRY\MACHINE\SOFTWARE</p></li>
<li><p>HKCU\SOFTWARE\Microsoft\AppV\Client\Packages{PkgGUID}\Registry\User{UserSID}\SOFTWARE</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### <a name="app-v-and-folder-redirection"></a>App-V とフォルダーのリダイレクト

App-V 5.1 では、ローミング AppData フォルダー (%AppData%)のフォルダー リダイレクトがサポートされています。 仮想環境が開始すると、ユーザーのローミング AppData ディレクトリからのローミング AppData 状態がローカル キャッシュにコピーされます。 逆に、仮想環境がシャットダウンすると、特定のユーザーのローミング AppData に関連付けられたローカル キャッシュが、そのユーザーのローミング AppData ディレクトリの実際の場所に転送されます。

一般的なパッケージには、AppData\\Local と AppData\\Roaming の両方の設定に対して、ユーザーのバッキング ストアにマップされた複数の場所があります。 これらの場所は、ユーザーのプロファイルにユーザーごとに保存され、パッケージの VFS ディレクトリに加えた変更を保存し、既定のパッケージ VFS を保護するために使用される、書き込み時にコピーする場所です。

次の表に、フォルダー リダイレクトが実装されていない場合のローカルとローミングの場所を示します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">パッケージ内の VFS ディレクトリ</th>
<th align="left">バッキング ストアのマップされた場所</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ProgramFilesX86</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ProgramFilesX86</p></td>
</tr>
<tr class="even">
<td align="left"><p>SystemX86</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \SystemX86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \Windows</p></td>
</tr>
<tr class="even">
<td align="left"><p>appv_ROOT</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \appv_ROOT</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AppData</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; 強力な &gt; ローミング </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \AppData</p></td>
</tr>
</tbody>
</table>

 

 

次の表に、%AppData%に対してフォルダー リダイレクトが実装され、その場所が (通常はネットワークの場所に) リダイレクトされている場合のローカルとローミングの場所を示します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">パッケージ内の VFS ディレクトリ</th>
<th align="left">バッキング ストアのマップされた場所</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ProgramFilesX86</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ProgramFilesX86</p></td>
</tr>
<tr class="even">
<td align="left"><p>SystemX86</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \SystemX86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \Windows</p></td>
</tr>
<tr class="even">
<td align="left"><p>appv_ROOT</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \appv_ROOT</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AppData</p></td>
<td align="left"><p><strong>\Fileserver </strong> \users\jsmith\roaming\Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \AppData</p></td>
</tr>
</tbody>
</table>

 

 

現在の App-V Client VFS ドライバーはネットワークの場所に書き込めないので、App-V クライアントはフォルダー リダイレクトの存在を検出し、発行中および仮想環境の開始時にローカル ドライブ上のデータをコピーします。 ユーザーが App-V アプリケーションを閉じ、App-V クライアントが仮想環境を閉じると、VFS AppData のローカル ストレージがネットワークにコピーされ、プロセスが繰り返される追加のコンピューターへのローミングが可能になります。 プロセスの詳細な手順は次のとおりです。

1.  発行または仮想環境の起動時に、App-V クライアントは AppData ディレクトリの場所を検出します。

2.  ローミング AppData パスがローカルまたは ino AppData\\Roaming の場所にマップされている場合、何も起こりません。

3.  ローミング AppData パスがローカルではない場合、VFS AppData ディレクトリはローカル AppData ディレクトリにマップされます。

このプロセスは、App-V クライアント VFS ドライバーでサポートされていないローカル以外の %AppData% の問題を解決します。 ただし、この新しい場所に格納されているデータは、フォルダーリダイレクトではローミングされません。 アプリケーションの実行中のすべての変更は、ローカルの AppData の場所に発生し、リダイレクトされた場所にコピーする必要があります。 このプロセスの詳細な手順は次のとおりです。

1.  App-V アプリケーションがシャットダウンされ、仮想環境がシャットダウンされます。

2.  ローミング AppData の場所のローカル キャッシュは圧縮され、ZIP ファイルに格納されます。

3.  ZIP パッケージ プロセスの最後のタイムスタンプを使用して、ファイルの名前を指定します。

4.  タイムスタンプはレジストリに記録されます。 HKEY\_CURRENT\_USER\\Software\\Microsoft\\AppV\\Client\\\Packages\\ &lt; GUID \\AppDataTime を最後に知られている AppData タイムスタンプとして記録します。 &gt;

5.  フォルダー リダイレクト プロセスが呼び出され、ローミング AppData ディレクトリにアップロードされた ZIP ファイルを評価して開始します。

タイムスタンプは、競合が発生した場合に "最後のライターが勝つ" シナリオを判断するために使用され、App-V アプリケーションの公開時または仮想環境の開始時にデータのダウンロードを最適化するために使用されます。 フォルダーリダイレクトは、サポート ポリシーの対象となる他のクライアントからデータを利用できるようにします。また、AppData\\Roaming データをクライアント上のローカル AppData の場所に保存するプロセスを開始します。 詳細なプロセスは次のとおりです。

1.  ユーザーは、アプリケーションを起動して仮想環境を開始します。

2.  アプリケーションの仮想環境は、最新のタイムスタンプ付き ZIP ファイル (存在する場合) をチェックします。

3.  レジストリは、最後にアップロードされた既知のタイムスタンプ (存在する場合) がチェックされます。

4.  最新の ZIP ファイルは、ローカルの最後の既知のアップロード タイムスタンプが ZIP ファイルのタイムスタンプ以上である場合を超えない限り、ダウンロードされます。

5.  ローカルの最後の既知のアップロード タイムスタンプが、ローミング AppData の場所の最新の ZIP ファイルよりも前の場合、ZIP ファイルはユーザーのプロファイル内のローカル一時ディレクトリに抽出されます。

6.  ZIP ファイルが正常に抽出されると、ローミング AppData ディレクトリのローカル キャッシュの名前が変更され、新しいデータが場所に移動されます。

7.  名前が変更されたディレクトリが削除され、アプリケーションが開き、最近保存されたローミング AppData データが表示されます。

これにより、AppData\\Roaming の場所に存在するアプリケーション設定のローミングが正常に完了します。 対処する必要があるその他の条件は、パッケージの修復操作のみです。 プロセスの詳細は次のとおりです。

1.  修復中に、ユーザーのローミング AppData ディレクトリへのパスがローカルではないか検出します。

2.  ローカル以外のローミング AppData パス ターゲットをマップすると、期待されるローミングとローカル AppData の場所が再作成されます。

3.  レジストリに保存されているタイムスタンプ (存在する場合) を削除します。

このプロセスでは、AppData のローカルとネットワークの両方の場所が再作成され、タイムスタンプのレジストリ レコードが削除されます。

## <a name="app-v-client-application-lifecycle-management"></a><a href="" id="bkmk-clt-app-lifecycle"></a>App-V クライアント アプリケーションのライフサイクル管理


App-V Full Infrastructure では、アプリケーションのシーケンスが実行された後、App-V 管理サーバーと発行サーバーを介してユーザーまたはコンピューターに管理および公開されます。 このセクションでは、App-V アプリケーションの一般的なライフサイクル操作 (追加、発行、起動、アップグレード、および削除) 中に発生する操作と、App-V クライアントの観点から変更および変更されたファイルとレジストリの場所について説明します。 App-V クライアント操作は、App-V クライアントを実行しているコンピューターで開始される一連の PowerShell コマンドとして実行されます。

このドキュメントでは、App-V フル インフラストラクチャ ソリューションに焦点を当て、 Configuration Manager 2012 との App-V 統合の詳細については、次のページをご覧ください <https://go.microsoft.com/fwlink/?LinkId=392773> 。

App-V アプリケーションのライフサイクル タスクは、ユーザー ログイン (既定)、コンピューターの起動、またはバックグラウンドの時間指定操作でトリガーされます。 発行サーバー、更新間隔、パッケージ スクリプトの有効化など、App-V クライアント操作の設定は、PowerShell コマンドを使用したクライアントのセットアップ中またはセットアップ後に構成されます。 TechNet の「How to Deploy the Client」セクションを参照してください。 [App-V クライアント](how-to-deploy-the-app-v-client-51gb18030.md) を展開する方法、または PowerShell を利用する方法:

```powershell
get-command *appv*
```

### <a name="publishing-refresh"></a>発行の更新

発行の更新プロセスは、App-V クライアントで実行されるいくつかの小さな操作で構成されます。 App-V はアプリケーション仮想化テクノロジであり、タスク スケジュール テクノロジでは実現できないので、Windows タスク スケジューラを使用して、ユーザー ログオン、コンピューターの起動、およびスケジュールされた間隔でプロセスを有効にします。 上記のセットアップ時のクライアントの構成は、正しい設定を持つ大規模なコンピューター グループにクライアントを配布する場合に推奨される方法です。 これらのクライアント設定は、次の PowerShell コマンドレットを使用して構成できます。

-   **Add-AppVPublishingServer:** App-V パッケージを提供する App-V 発行サーバーを使用してクライアントを構成します。

-   **Set-AppVPublishingServer:** App-V 発行サーバーの現在の設定を変更します。

-   **Set-AppVClientConfiguration:** App-V クライアントの現在の設定を変更します。

-   **Sync-AppVPublishingServer:** App-V 発行更新プロセスを手動で開始します。 これは、発行サーバーの構成中に作成されたスケジュールされたタスクでも使用されます。

次のセクションでは、App-V 発行更新の異なるフェーズで発生する操作の詳細を説明します。 トピックには、次のものが含まれます。

-   App-V パッケージの追加

-   App-V パッケージの発行

### <a name="adding-an-app-v-package"></a>App-V パッケージの追加

クライアントへの App-V パッケージの追加は、発行更新プロセスの最初の手順です。 最後の結果は PowerShell のコマンドレットと同じですが、発行更新の追加プロセス中は、構成済みの発行サーバーに接続され、アプリケーションのハイレベル リストがクライアントに渡され、より詳細な情報が取得され、パッケージの追加操作は 1 つではありません。 `Add-AppVClientPackage` このプロセスは、パッケージまたは接続グループの追加または更新用にクライアントを構成して続行し、appv ファイルにアクセスします。 次に、appv ファイルの内容が展開され、適切な場所にあるローカル オペレーティング システムに配置されます。 次に示すのは、パッケージがフォールト ストリーミング用に構成されている場合のプロセスの詳細なワークフローです。

**App-V パッケージを追加する方法**

1.  発行の更新プロセスの PowerShell またはタスク シーケンスの開始による手動の開始。

    1.  App-V クライアントは HTTP 接続を行い、ターゲットに基づいてアプリケーションの一覧を要求します。 発行の更新プロセスでは、コンピューターまたはユーザーのターゲット設定がサポートされています。

    2.  App-V Publishing Server は、開始するターゲット、ユーザー、またはコンピューターの ID を使用し、データベースに対して、資格を持つアプリケーションの一覧を照会します。 アプリケーションの一覧は XML 応答として提供され、クライアントはパッケージごとに詳細を確認するためにサーバーに追加の要求を送信するために使用します。

2.  App-V クライアントの発行エージェントは、シリアル化された以下のすべてのアクションを実行します。

    接続グループの一部であるパッケージ バージョンの更新は処理できないので、非公開または無効になっている接続グループを評価します。

3.  Add 操作または Update 操作を識別してパッケージを構成します。

    1.  App-V クライアントは、クライアントから AppX API をWindows発行サーバーから appv ファイルにアクセスします。

    2.  パッケージ ファイルが開き、AppXManifest.xmlとStreamMap.xmlパッケージ ストアにダウンロードされます。

    3.  アプリケーションで定義された発行ブロック データを完全にStreamMap.xml。 発行ブロック データをパッケージ ストア\\PkgGUID\\VerGUID\\Root に格納します。

        -   アイコン: 拡張ポイントのターゲット。

        -   ポータブル実行可能ヘッダー (PE ヘッダー): ディスク上のイメージの必要に関する基本情報を含む拡張ポイントのターゲット、直接アクセスされる、またはファイルの種類を介して。

        -   スクリプト: 発行プロセス全体で使用するスクリプト ディレクトリをダウンロードします。

    4.  パッケージ ストアに次の値を設定します。

        1.  リストされているディレクトリの抽出されたパッケージを表すスパース ファイルをディスク上に作成します。

        2.  ルートの下にトップ レベルのファイルとディレクトリをステージします。

        3.  その他のすべてのファイルは、ディレクトリがディスク上でスパースとしてリストされ、オンデマンドでストリーミングされると作成されます。

    5.  コンピューター カタログ エントリを作成します。 パッケージ ファイルManifest.xml作成DeploymentConfiguration.xmlを作成します (プレースホルダーが作成DeploymentConfiguration.xmlファイルがない場合)。

    6.  レジストリ HKLM\\Software\\Microsoft\\AppV\\Client\\Package\\PkgGUID\\Versions\\VerGUID\\Catalog にパッケージ ストアの場所を作成する

    7.  パッケージ ストアから %ProgramData%\\\Microsoft\\AppV\\Client\\VReg\\{VersionGUID}.dat に Registry.dat ファイルを作成します。

    8.  パッケージを App-V カーネル モード ドライバー HKLM\\Microsoft\\Software\\AppV\\MAV に登録する

    9.  パッケージの追加のタイミングをAppxManifest.xmlまたはDeploymentConfig.xmlファイルからスクリプトを呼び出します。

4.  接続グループを追加および有効化または無効化して構成します。

5.  ターゲット (ユーザーまたはコンピューター) に発行されていないオブジェクトを削除します。

    **備考**  
    これにより、パッケージの削除は実行されませんが、特定のターゲット (ユーザーまたはコンピューター) の統合ポイントを削除し、ユーザー カタログ ファイル (グローバルに発行されるマシン カタログ ファイル) を削除します。

     

6.  クライアント構成に基づいてバックグラウンド負荷のマウントを呼び出します。

7.  コンピューターまたはユーザーの発行情報が既に存在するパッケージは、直ちに復元されます。

    **備考**  
    この条件は、パッケージをバックグラウンドで追加して非公開にすることなく、削除の製品として発生します。

     

これで、発行更新プロセスの App-V パッケージの追加が完了します。 次の手順では、特定のターゲット (コンピューターまたはユーザー) にパッケージを発行します。

![パッケージは、ファイルとレジストリ データを追加します。](images/packageaddfileandregistrydata.png)

### <a name="publishing-an-app-v-package"></a>App-V パッケージの発行

発行更新操作中に、特定の発行操作 (Publish-AppVClientPackage) は、ユーザー カタログにエントリを追加し、エンタイトルメントをユーザーにマップし、ローカル ストアを識別し、統合手順を完了して終了します。 以下に、詳細な手順を示します。

**発行方法と App-V パッケージ**

1.  パッケージ エントリがユーザー カタログに追加される

    1.  ユーザーを対象としたパッケージ: UserDeploymentConfiguration.xmlとUserManifest.xmlユーザー カタログ内のコンピューターに配置されます。

    2.  コンピューターを対象とした (グローバル) パッケージ: UserDeploymentConfiguration.xmlがマシン カタログに配置される

2.  HKLM\\Software\\Microsoft\\AppV\\MAV でユーザーのカーネル モード ドライバーにパッケージを登録する

3.  統合タスクを実行します。

    1.  拡張ポイントを作成します。

    2.  ユーザーのレジストリと移動プロファイル (ショートカット バックアップ) にバックアップ情報を保存します。

        **備考**  
        これにより、パッケージが非公開の場合に拡張ポイントの復元が有効になります。

         

    3.  発行タイミングを対象としたスクリプトを実行します。

接続グループの一部である App-V パッケージの発行は、上記のプロセスと非常に似ています。 接続グループの場合、特定のカタログ情報を格納するパスには、カタログ ディレクトリの子として PackageGroups が含まれます。 コンピューターとユーザーが上記の情報をカタログで確認し、詳細を確認します。

![パッケージのファイルとレジストリ データの追加 - グローバル。](images/packageaddfileandregistrydata-global.png)

### <a name="application-launch"></a>アプリケーションの起動

発行の更新プロセスの後、ユーザーは App-V アプリケーションを起動し、その後再起動します。 このプロセスは非常に簡単で、最小限のネットワーク トラフィックで迅速に起動するために最適化されています。 App-V クライアントは、発行中に作成されたファイルのユーザー カタログへのパスをチェックします。 パッケージを起動する権限が確立されると、App-V クライアントは仮想環境を作成し、必要なデータのストリーミングを開始し、仮想環境の作成時に適切なマニフェストおよび展開構成ファイルを適用します。 仮想環境が作成され、特定のパッケージとアプリケーション用に構成されると、アプリケーションが起動します。

**App-V アプリケーションを起動する方法**

1.  ユーザーは、ショートカットまたはファイルの種類の呼び出しをクリックしてアプリケーションを起動します。

2.  App-V クライアントは、次のファイルのユーザー カタログ内の存在を確認します。

    -   UserDeploymentConfiguration.xml

    -   UserManifest.xml

3.  ファイルが存在する場合、アプリケーションにはその特定のユーザーの権限が与え、アプリケーションは起動プロセスを開始します。 この時点でネットワーク トラフィックはありません。

4.  次に、App-V クライアント は、App-V クライアント サービスに登録されているパッケージのパスがレジストリ内にあるか確認します。

5.  パッケージ ストアへのパスを見つけると、仮想環境が作成されます。 これが最初の起動である場合は、プライマリ機能ブロックが存在する場合にダウンロードされます。

6.  ダウンロード後、App-V クライアント サービスはマニフェスト構成ファイルと展開構成ファイルを使用して仮想環境を構成し、すべての App-V サブシステムが読み込まれます。

7.  アプリケーションが起動します。 パッケージ ストア内の不足しているファイル (スパース ファイル) の場合、App-V は必要に応じてファイルの障害をストリームします。

    ![パッケージの追加ファイルとレジストリ データ - ストリーム。](images/packageaddfileandregistrydata-stream.png)

### <a name="upgrading-an-app-v-package"></a>App-V パッケージのアップグレード

App-V 5 パッケージのアップグレード プロセスは、以前のバージョンの App-V とは異なります。 App-V は、異なるユーザーが使用できるコンピューター上の同じパッケージの複数のバージョンをサポートします。 パッケージ のバージョンは、パッケージ ストアとカタログが新しいリソースで更新された時点でいつでも追加できます。 新しいバージョン リソースの追加に固有の唯一のプロセスは、記憶域の最適化です。 アップグレード中に、新しいファイルだけが新しいバージョン ストアの場所に追加され、変更されていないファイルに対してハード リンクが作成されます。 これにより、ファイルを 1 つのディスクの場所にのみ表示し、そのファイルをディスク上のファイルの場所エントリを持つすべてのフォルダーに投影することで、全体的な記憶域が削減されます。 App-V パッケージのアップグレードの具体的な詳細は次のとおりです。

**App-V パッケージをアップグレードする方法**

1.  App-V クライアントは発行更新を実行し、App-V パッケージの新しいバージョンを検出します。

2.  パッケージ エントリが新しいバージョンの適切なカタログに追加される

    1.  ユーザー対象パッケージ: UserDeploymentConfiguration.xml および UserManifest.xml は、appdata\\roaming\\Microsoft\\AppV\\\Client\\Catalog\\Packages\\PkgGUID\\VerGUID のユーザー カタログ内のコンピューターに配置されます。

    2.  コンピューター対象 (グローバル) パッケージ: UserDeploymentConfiguration.xml は %programdata%\\\Microsoft\\AppV\\Client\\Catalog\\Packages\\PkgGUID\\VerGUID のマシン カタログに配置されます。

3.  HKLM\\Software\\Microsoft\\AppV\\MAV でユーザーのカーネル モード ドライバーにパッケージを登録する

4.  統合タスクを実行します。

    -   マニフェストおよび動的構成ファイルから拡張機能ポイント (EP) を統合します。

    1.  ファイル ベースの EP データは、パッケージ ストアのジャンクション ポイントを使用して AppData フォルダーに格納されます。

    2.  バージョン 1 の EPs は、新しいバージョンが使用可能になったときに既に存在します。

    3.  拡張ポイントは、新しい拡張ポイントまたは更新された拡張ポイントのマシン カタログまたはユーザー カタログ内のバージョン 2 の場所に切り替わります。

5.  発行タイミングを対象としたスクリプトを実行します。

6.  必要に応じてサイド バイ サイド アセンブリをインストールします。

### <a name="upgrading-an-in-use-app-v-package"></a>使用中の App-V パッケージのアップグレード

**App-V 5 SP2**から: エンド ユーザーが使用しているパッケージをアップグレードしようとする場合、アップグレード タスクは保留中の状態になります。 アップグレードは、次のルールに従って後で実行されます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスクの種類</th>
<th align="left">適用可能なルール</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ユーザー ベースのタスク (ユーザーへのパッケージの発行など)</p></td>
<td align="left"><p>保留中のタスクは、ユーザーがログオフしてからログオンした後に実行されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>グローバル ベースのタスク (グローバルに接続グループを有効にするなど)</p></td>
<td align="left"><p>保留中のタスクは、コンピューターをシャットダウンしてから再起動すると実行されます。</p></td>
</tr>
</tbody>
</table>

 

タスクが保留中の状態に置かれると、App-V クライアントは、次のように保留中のタスクのレジストリ キーも生成します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ユーザー ベースまたはグローバル ベースのタスク</th>
<th align="left">レジストリ キーが生成される場所</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ユーザー ベースのタスク</p></td>
<td align="left"><p>KEY_CURRENT_USER\Software\Microsoft\AppV\Client\PendingTasks</p></td>
</tr>
<tr class="even">
<td align="left"><p>グローバル ベースのタスク</p></td>
<td align="left"><p>HKEY_LOCAL_MACHINE\Software\Microsoft\AppV\Client\PendingTasks</p></td>
</tr>
</tbody>
</table>

 

ユーザーがパッケージの新しいバージョンを使用するには、次の操作を完了する必要があります。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスク</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>パッケージをコンピューターに追加する</p></td>
<td align="left"><p>このタスクはコンピューター固有のタスクであり、上記の [パッケージの追加] セクションの手順を完了することで、いつでも実行できます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>パッケージを発行する</p></td>
<td align="left"><p>手順については、上記の「パッケージ発行」セクションを参照してください。 このプロセスでは、システム上の拡張ポイントを更新する必要があります。 このタスクを完了すると、エンド ユーザーはアプリケーションを使用できません。</p></td>
</tr>
</tbody>
</table>

 

パッケージを更新するためのガイドとして、次のシナリオ例を使用します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">シナリオ</th>
<th align="left">要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>アップグレードしようとするときに App-V パッケージが使用されていない</p></td>
<td align="left"><p>仮想アプリケーション、COM サーバー、シェル拡張機能など、パッケージの次のコンポーネントを使用することはできません。</p>
<p>管理者はパッケージの新しいバージョンを発行し、パッケージ内のコンポーネントまたはアプリケーションが次回起動するとアップグレードが機能します。 パッケージの新しいバージョンがストリーミングされ、実行されます。 App-V 5 SP2 のこのシナリオでは、以前のリリースの App-V 5 から何も変更されません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>管理者が新しいバージョンのパッケージを発行するときに App-V パッケージが使用されている</p></td>
<td align="left"><p>アップグレード操作は App-V クライアントによって保留中に設定されます。つまり、パッケージが使用されていないときにキューに入れ、後で実行されます。</p>
<p>パッケージ アプリケーションが使用されている場合、ユーザーは仮想アプリケーションをシャットダウンし、その後アップグレードを実行できます。</p>
<p>パッケージにシェル拡張機能 (Office 2013) がある場合、Windows エクスプローラーによって完全に読み込まれる場合、ユーザーはログインできません。 App-V パッケージのアップグレードを開始するには、ユーザーがログオフしてログインし戻す必要があります。</p></td>
</tr>
</tbody>
</table>

 

### <a name="global-vs-user-publishing"></a>グローバル発行とユーザー発行

App-V パッケージは、次の 2 つの方法のいずれかを使用して発行できます。App-V パッケージを特定のユーザーまたはユーザー グループに与え、コンピューターのすべてのユーザーに対して App-V パッケージをコンピューター全体に適用するグローバルを指定するユーザー。 パッケージのアップグレードがペンドされ、App-V パッケージが使用されていない場合は、次の 2 種類の発行を検討してください。

-   **グローバルに発行**: アプリケーションはコンピューターに発行されます。コンピューター上のすべてのユーザーが使用できます。 アップグレードは、App-V クライアント サービスの開始時に行います。これは、事実上、コンピューターの再起動を意味します。

-   **発行されたユーザー**: アプリケーションがユーザーに発行されます。 コンピューターに複数のユーザーがある場合は、アプリケーションをユーザーのサブセットに公開できます。 アップグレードは、ユーザーがログインした場合、または再び発行された場合に発生します (定期的に、ConfigMgr ポリシーの更新と評価、または App-V の定期的な発行/更新、または PowerShell コマンドを使用して明示的に)。

### <a name="removing-an-app-v-package"></a>App-V パッケージの削除

フル インフラストラクチャで App-V アプリケーションを削除する操作は非公開の操作であり、パッケージの削除は実行しない。 このプロセスは上記の発行プロセスと同じですが、削除プロセスを追加する代わりに、App-V パッケージに対して行われた変更を元に戻します。

### <a name="repairing-an-app-v-package"></a>App-V パッケージの修復

修復操作は非常に簡単ですが、コンピューター上の多くの場所に影響を与える可能性があります。 前述の COPY on Write (COW) の場所は削除され、拡張ポイントは統合され、再統合されます。 レジストリに登録されている場所を確認して、COW データの配置場所を確認してください。 この操作は自動的に実行され、App-V クライアント コンソールまたは PowerShell (Repair-AppVClientPackage) を介して修復操作を開始する以外に管理制御はありません。

## <a name="integration-of-app-v-packages"></a><a href="" id="bkmk-integr-appv-pkgs"></a>App-V パッケージの統合


App-V Client and package architecture は、パッケージの追加および発行時にローカル オペレーティング システムとの特定の統合を提供します。 3 つのファイルは、App-V パッケージの統合ポイントまたは拡張ポイントを定義します。

-   AppXManifest.xml: パッケージ ストアとユーザー プロファイルに保存されたフォールバック コピーを含むパッケージの内部に格納されます。 シーケンス処理中に作成されたオプションが含まれる。

-   DeploymentConfig.xml: コンピューターとユーザー ベースの統合拡張ポイントの構成情報を提供します。

-   UserConfig.xml: ユーザー ベースの構成のみをDeploymentconfig.xmlユーザー ベースの拡張ポイントのみを対象とする、ユーザー ベースの拡張ポイントのサブセットです。

### <a name="rules-of-integration"></a>統合のルール

App-V アプリケーションが App-V クライアントを使用してコンピューターに発行される場合、以下の一覧で説明するように、特定のアクションが実行されます。

-   グローバル発行: ショートカットは [すべてのユーザー] プロファイルの場所に格納され、他の拡張ポイントは HKLM ハイブのレジストリに格納されます。

-   ユーザー発行: ショートカットは現在のユーザー アカウント プロファイルに格納され、その他の拡張ポイントは HKCU ハイブのレジストリに格納されます。

-   バックアップと復元: 既存のネイティブ アプリケーション データとレジストリ (FTA 登録など) は、発行中にバックアップされます。

    1.  App-V パッケージには、最新の公開された App-V アプリケーションに所有権が渡される最後の統合パッケージに基づいて所有権が与えられる。

    2.  所有権は、所有する App-V パッケージが公開されていないときに、ある App-V パッケージから別の App-V パッケージに転送されます。 これにより、データまたはレジストリの復元は開始されない。

    3.  最後のパッケージが公開されていないか、拡張ポイント単位で削除された場合は、バックアップされたデータを復元します。

### <a name="extension-points"></a>拡張ポイント

App-V 発行ファイル (マニフェストおよび動的構成) には、アプリケーションをローカル オペレーティング システムと統合できるいくつかの拡張ポイントが提供されます。 これらの拡張ポイントは、ショートカットの配置、ファイルの種類の関連付けの作成、コンポーネントの登録など、一般的なアプリケーション インストール タスクを実行します。 これらは、従来のアプリケーションと同じ方法でインストールされていない仮想化アプリケーションです。いくつかの違いがあります。 次に、このセクションで説明する拡張ポイントの一覧を示します。

-   ショートカット

-   ファイルの種類の関連付け

-   シェル拡張機能

-   COM

-   ソフトウェア クライアント

-   アプリケーションの機能

-   URL プロトコル ハンドラー

-   AppPath

-   仮想アプリケーション

### <a name="shortcuts"></a>ショートカット

短いカットは、OS との統合の基本的な要素の 1 つであり、App-V アプリケーションをユーザーが直接起動するインターフェイスです。 App-V アプリケーションの発行および公開解除中。

パッケージ マニフェストおよび動的構成 XML ファイルから、特定のアプリケーション実行可能ファイルへのパスは、次のようなセクションで確認できます。

```xml
<Extension Category="AppV.Shortcut">
          <Shortcut>
            <File>[{Common Desktop}]\Adobe Reader 9.lnk</File>
            <Target>[{AppVPackageRoot}]\Reader\AcroRd32.exe</Target>
            <Icon>[{Windows}]\Installer\{AC76BA86-7AD7-1033-7B44-A94000000001}\SC_Reader.ico</Icon>
            <Arguments />
            <WorkingDirectory />
            <ShowCommand>1</ShowCommand>
            <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
          </Shortcut>
        </Extension>
```

前述したように、App-V ショートカットは既定で更新操作に基づいてユーザーのプロファイルに配置されます。 グローバル更新では、すべてのユーザー プロファイルにショートカットが格納され、ユーザー更新によって特定のユーザーのプロファイルに保存されます。 実際の実行可能ファイルはパッケージ ストアに格納されます。 ICO ファイルの場所は、App-V パッケージ内のトークン化された場所です。

### <a name="file-type-associations"></a>ファイルの種類の関連付け

App-V クライアントは、発行中にローカル オペレーティング システムのファイルの種類の関連付けを管理します。これにより、ユーザーはファイルの種類の呼び出しを使用したり、特に登録されている拡張子 (.docx) を持つファイルを開き、App-V アプリケーションを開始できます。 ファイルの種類の関連付けは、次の例に示すマニフェストおよび動的構成ファイルに存在します。

```xml
<Extension Category="AppV.FileTypeAssociation">
          <FileTypeAssociation>
            <FileExtension MimeAssociation="true">
              <Name>.xdp</Name>
              <ProgId>AcroExch.XDPDoc</ProgId>
              <ContentType>application/vnd.adobe.xdp+xml</ContentType>
            </FileExtension>
            <ProgId>
              <Name>AcroExch.XDPDoc</Name>
              <Description>Adobe Acrobat XML Data Package File</Description>
              <EditFlags>65536</EditFlags>
              <DefaultIcon>[{Windows}]\Installer\{AC76BA86-7AD7-1033-7B44-A94000000001}\XDPFile_8.ico</DefaultIcon>
              <ShellCommands>
                <DefaultCommand>Read</DefaultCommand>
                <ShellCommand>
                  <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
                  <Name>Open</Name>
                  <CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe" "%1"</CommandLine>
                </ShellCommand>
                <ShellCommand>
                  <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
                  <Name>Printto</Name>
                  <CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe"  /t "%1" "%2" "%3" "%4"</CommandLine>
                </ShellCommand>
                <ShellCommand>
                  <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
                  <Name>Read</Name>
                  <FriendlyName>Open with Adobe Reader 9</FriendlyName>
                  <CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe" "%1"</CommandLine>
                </ShellCommand>
              </ShellCommands>
            </ProgId>
          </FileTypeAssociation>
        </Extension>
```

**備考**  
この例では、次の操作を行います。

-   `<Name>.xdp</Name>` は拡張機能です

-   `<Name>AcroExch.XDPDoc</Name>` は ProgId 値 (隣接する ProgId をポイントする) です。

-   `<CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe" "%1"</CommandLine>` はコマンド ラインで、アプリケーションの実行可能ファイルをポイントします。

 

### <a name="shell-extensions"></a>シェル拡張

シェル拡張機能は、シーケンスプロセス中に自動的にパッケージに埋め込まれます。 パッケージがグローバルに発行される場合、シェル拡張機能は、アプリケーションがローカルにインストールされた場合と同じ機能をユーザーに提供します。 アプリケーションでは、シェル拡張機能の機能を有効にするには、クライアントで追加のセットアップや構成を必要とします。

**シェル拡張機能を使用する場合の要件:**

-   埋め込みシェル拡張機能を含むパッケージは、グローバルに発行する必要があります。

-   アプリケーション、Sequencer、App-V クライアントの "bitness" が一致しているか、シェル拡張機能が機能しない必要があります。 以下に例を示します。

    -   アプリケーションのバージョンは 64 ビットです。

    -   Sequencer は 64 ビット コンピューターで実行されています。

    -   パッケージは 64 ビット App-V クライアント コンピューターに配信されています。

次の表に、サポートされているシェル拡張機能を示します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ハンドラー</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>コンテキスト メニュー ハンドラー</p></td>
<td align="left"><p>メニュー項目をコンテキスト メニューに追加します。 コンテキスト メニューが表示される前に呼び出されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ドラッグ アンド ドロップ ハンドラー</p></td>
<td align="left"><p>ドラッグ アンド ドロップを右クリックするとアクションを制御し、表示されるコンテキスト メニューを変更します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ドロップ ターゲット ハンドラー</p></td>
<td align="left"><p>ファイルなどのドロップ ターゲット上でデータ オブジェクトをドラッグ アンド ドロップした後のアクションを制御します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>データ オブジェクト ハンドラー</p></td>
<td align="left"><p>ファイルをクリップボードにコピーした後、またはドロップ 先にドラッグ アンド ドロップした後のアクションを制御します。 ドロップ ターゲットに追加のクリップボード形式を提供できます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>プロパティ シート ハンドラー</p></td>
<td align="left"><p>オブジェクトのプロパティ シート ダイアログ ボックスにページを置換または追加します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Infotip ハンドラー</p></td>
<td align="left"><p>アイテムのフラグとヒント情報を取得し、マウス ポインターを置くとポップアップ ヒント内に表示できます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>列ハンドラー</p></td>
<td align="left"><p>[エクスプローラーの詳細] ビューでカスタム列Windows表示 <em> できます </em> 。 並べ替えとグループ化を拡張するために使用できます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>プレビュー ハンドラー</p></td>
<td align="left"><p>エクスプローラー プレビュー ウィンドウにファイルのプレビューを表示Windows有効にします。</p></td>
</tr>
</tbody>
</table>

 

### <a name="com"></a>COM

App-V クライアントは、COM 統合と仮想化をサポートする発行アプリケーションをサポートしています。 COM 統合により、App-V クライアントはローカル オペレーティング システム上の COM オブジェクトとオブジェクトの仮想化を登録できます。 このドキュメントの目的上、COM オブジェクトの統合には追加の詳細が必要です。

App-V は、パッケージからローカル オペレーティング システムへの COM オブジェクトの登録をサポートし、アウトプロセスとインプロセスの 2 種類のプロセスを使用します。 COM オブジェクトの登録は、off、Isolated、および Integrated を含む特定の App-V パッケージの 1 つまたは複数の操作モードの組み合わせで行います。 統合モードは、アウトプロセスタイプまたはインプロセスタイプ用に構成されます。 COM モードと種類の構成は、動的構成ファイル (deploymentconfig.xmlまたはuserconfig.xml)。

App-V 統合の詳細については、次のページをご覧ください <https://go.microsoft.com/fwlink/?LinkId=392834> 。

### <a name="software-clients-and-application-capabilities"></a>ソフトウェア クライアントとアプリケーション機能

App-V は、仮想化されたアプリケーションをオペレーティング システムのソフトウェア クライアントに登録できる特定のソフトウェア クライアントとアプリケーション機能拡張ポイントをサポートします。 これにより、ユーザーは電子メール、インスタント メッセージング、メディア プレーヤーのような操作の既定のプログラムを選択できます。 この操作は、Set Program Access および Computer Defaults を使用してコントロール パネルで実行され、マニフェストまたは動的構成ファイルのシーケンス処理中に構成されます。 アプリケーション機能は、App-V アプリケーションがグローバルに公開されている場合にのみサポートされます。

App-V ベースのメール クライアントのソフトウェア クライアント登録の例。

```xml
    <SoftwareClients Enabled="true">
      <ClientConfiguration EmailEnabled="true" />
      <Extensions>
        <Extension Category="AppV.SoftwareClient">
          <SoftwareClients>
            <EMail MakeDefault="true">
              <Name>Mozilla Thunderbird</Name>
              <Description>Mozilla Thunderbird</Description>
              <DefaultIcon>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe,0</DefaultIcon>
              <InstallationInformation>
                <RegistrationCommands>
                  <Reinstall>"[{ProgramFilesX86}]\Mozilla Thunderbird\uninstall\helper.exe" /SetAsDefaultAppGlobal</Reinstall>
                  <HideIcons>"[{ProgramFilesX86}]\Mozilla Thunderbird\uninstall\helper.exe" /HideShortcuts</HideIcons>
                  <ShowIcons>"[{ProgramFilesX86}]\Mozilla Thunderbird\uninstall\helper.exe" /ShowShortcuts</ShowIcons>
                </RegistrationCommands>
                <IconsVisible>1</IconsVisible>
                <OEMSettings />
              </InstallationInformation>
              <ShellCommands>
                <ApplicationId>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe</ApplicationId>
                <Open>"[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe" -mail</Open>
              </ShellCommands>
              <MAPILibrary>[{ProgramFilesX86}]\Mozilla Thunderbird\mozMapi32_InUse.dll</MAPILibrary>
              <MailToProtocol>
                <Description>Thunderbird URL</Description>
                <EditFlags>2</EditFlags>
                <DefaultIcon>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe,0</DefaultIcon>
                <ShellCommands>
                  <ApplicationId>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe</ApplicationId>
                  <Open>"[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe" -osint -compose "%1"</Open>
                </ShellCommands>
              </MailToProtocol>
            </EMail>
          </SoftwareClients>
        </Extension>
      </Extensions>
    </SoftwareClients>
```

**備考**  
この例では、次の操作を行います。

-   `<ClientConfiguration EmailEnabled="true" />` は、電子メール クライアントを統合するソフトウェア クライアント全体の設定です。

-   `<EMail MakeDefault="true">` は、特定のメール クライアントを既定のメール クライアントとして設定するフラグです。

-   `<MAPILibrary>[{ProgramFilesX86}]\Mozilla Thunderbird\mozMapi32_InUse.dll</MAPILibrary>` は MAPI dll の登録です

 

### <a name="url-protocol-handler"></a>URL プロトコル ハンドラー

アプリケーションは、必ずしもファイルの種類の呼び出しを利用する仮想化アプリケーションと呼ばれるとは限りではありません。 たとえば、文書または Web ページ内の mailto: リンクの埋め込みをサポートするアプリケーションでは、ユーザーは mailto: リンクをクリックし、登録メール クライアントを取得すると予想されます。 App-V は、ローカル オペレーティング システムにパッケージ単位で登録できる URL プロトコル ハンドラーをサポートします。 シーケンスの間、URL プロトコル ハンドラーはパッケージに自動的に追加されます。

特定の URL プロトコル ハンドラーを登録できるアプリケーションが複数ある場合は、動的構成ファイルを使用して動作を変更し、起動するプライマリ アプリケーションではないアプリケーションに対してこの機能を抑制または無効にできます。

### <a name="apppath"></a>AppPath

AppPath 拡張ポイントは、オペレーティング システムから直接 App-V アプリケーションを呼び出す機能をサポートします。 これは通常、オペレーティング システムに応じて実行画面またはスタート画面から実行されます。これにより、管理者は、実行可能ファイルへの特定のパスを呼び出さずに、オペレーティング システムのコマンドまたはスクリプトから App-V アプリケーションにアクセスできます。 したがって、発行時に実行されるため、すべてのシステムでシステム パス環境変数を変更しないようにします。

AppPath 拡張ポイントは、マニフェストまたは動的構成ファイルで構成され、ユーザーの発行中にローカル コンピューターのレジストリに格納されます。 AppPath レビューの詳細については、次の情報を参照してください <https://go.microsoft.com/fwlink/?LinkId=392835> 。

### <a name="virtual-application"></a>仮想アプリケーション

このサブシステムは、シーケンス処理中にキャプチャされたアプリケーションの一覧を提供します。これは通常、他の App-V コンポーネントで使用されます。 特定のアプリケーションに属する拡張ポイントの統合は、動的構成ファイルを使用して無効にすることができます。 たとえば、パッケージに 2 つのアプリケーションが含まれている場合、他のアプリケーションの拡張ポイントのみを統合するために、1 つのアプリケーションに属するすべての拡張ポイントを無効にできます。

### <a name="extension-point-rules"></a>拡張ポイントルール

上記の拡張ポイントは、パッケージの発行方法に基づいてオペレーティング システムに統合されます。 グローバル発行では、拡張ポイントがパブリック コンピューターの場所に表示されます。ユーザー発行では、ユーザーの場所に拡張ポイントが表示されます。 たとえば、デスクトップ上に作成され、グローバルに公開されるショートカットは、ショートカット (%Public%\\Desktop) とレジストリ データ (HKLM\\Software\\Classes) のファイル データになります。 同じショートカットには、ファイル データ (%UserProfile%\\\Desktop) とレジストリ データ (HKCU\\Software\\Classes) があります。

拡張ポイントはすべて同じ方法で公開されるのではなく、一部の拡張ポイントはグローバル発行を必要とします。また、配信される特定のオペレーティング システムとアーキテクチャに対するシーケンシングが必要な拡張ポイントもあります。 以下に、これら 2 つの主要なルールを示す表を示します。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">仮想拡張機能</th>
<th align="left">ターゲット OS シーケンスが必要</th>
<th align="left">グローバル発行が必要</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ショートカット</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>ファイルの種類の関連付け</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>URL プロトコル</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>AppPaths</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>COM モード</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>ソフトウェア クライアント</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>アプリケーション機能</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p>○</p></td>
</tr>
<tr class="even">
<td align="left"><p>コンテキスト メニュー ハンドラー</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p>○</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ドラッグ アンド ドロップ ハンドラー</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>データ オブジェクト ハンドラー</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>プロパティ シート ハンドラー</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>Infotip Handler</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>列ハンドラー</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>シェル拡張機能</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Browser Helper オブジェクト</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p>○</p></td>
</tr>
<tr class="even">
<td align="left"><p>Active X オブジェクト</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p>○</p></td>
</tr>
</tbody>
</table>

 

## <a name="dynamic-configuration-processing"></a><a href="" id="bkmk-dynamic-config"></a>動的構成処理


App-V パッケージを 1 つのコンピューターまたはユーザーに展開する方法は非常に簡単です。 ただし、組織がビジネス ラインや地理的および政治的な境界を越えて AppV アプリケーションを展開する場合、1 つの設定セットでアプリケーションを 1 回シーケンスする機能は不可能になります。 App-V は、マニフェスト ファイルのシーケンス処理中に特定の設定と構成をキャプチャする一方で、動的構成ファイルの変更もサポートする、このシナリオ用に設計されています。

App-V 動的構成では、コンピューター レベルまたはユーザー レベルでパッケージのポリシーを指定できます。 動的構成ファイルを使用すると、シーケンス エンジニアは、ユーザーまたはコンピューターの個々のグループのニーズに対応するために、パッケージの構成 (シーケンス後) を変更できます。 場合によっては、App-V 環境内で適切な機能を提供するために、アプリケーションに変更を加える必要がある場合があります。 たとえば、\_\*config.xml ファイルを変更して、アプリケーションの実行中に特定のアクションを実行するようにする必要があります。たとえば、仮想化されたアプリケーションが別のアプリケーションからその拡張機能を上書きするのを防ぐために mailto 拡張機能を無効にするなどです。

App-V パッケージには appv パッケージ ファイル内のマニフェスト ファイルが含まれます。これはシーケンス処理を表し、動的構成ファイルが特定のパッケージに割り当てられていない限り、選択のポリシーです。 シーケンス後、動的構成ファイルを変更して、異なるデスクトップまたは異なる拡張ポイントを持つユーザーにアプリケーションを発行できます。 2 つの動的構成ファイルは、動的展開構成 (DDC) ファイルと動的ユーザー構成 (DUC) ファイルです。 このセクションでは、マニフェストと動的構成ファイルの組み合わせについて説明します。

### <a name="example-for-dynamic-configuration-files"></a>動的構成ファイルの例

次の例は、発行後および通常の操作中に、マニフェスト、展開構成、およびユーザー構成ファイルの組み合わせを示しています。 これらの例は、各ファイルの省略された例です。 目的は、ファイルの組み合わせのみを表示し、各ファイルで使用できる特定のカテゴリの完全な説明ではありません。 詳細については、「App-V 5 シーケンス ガイド」を参照してください。 <https://go.microsoft.com/fwlink/?LinkID=269810>

**マニフェスト**

```xml
<appv:Extension Category="AppV.Shortcut">
     <appv:Shortcut>
          <appv:File>[{Common Programs}]\7-Zip\7-Zip File Manager.lnk</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot}]\7zFM exe.O.ico</appv:Icon>
     </appv:Shortcut>
</appv:Extension>
```

**展開構成**

```xml
<MachineConfiguration>
     <Subsystems>
          <Registry>
               <Include>
                    <Key Path= "\REGISTRY\Machine\Software\7zip">
                    <Value Type="REG_SZ" Name="Config" Data="1234"/>
                    </Key>
               </Include>
          </Registry>
     </Subsystems>
```

**ユーザー構成**

```xml
<UserConfiguration>
     <Subsystems>
<appv:ExtensionCategory="AppV.Shortcut">
     <appv:Shortcut>
          <appv:File>[{Desktop}]\7-Zip\7-Zip File Manager.lnk</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot}]\7zFM exe.O.ico</appv:Icon>
     </appv:Shortcut>
</appv:Extension>
     </Subsystems>
<UserConfiguration>
     <Subsystems>
<appv:Extension Category="AppV.Shortcut">
     <appv:Shortcut>
          <appv:Fìle>[{Desktop}]\7-Zip\7-Zip File Manager.lnk</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot}]\7zFM.exe.O.ico</appv:Icon>
     </appv:Shortcut>
     <appv:Shortcut>
          <appv:File>[{Common Programs}]\7-Zip\7-Zip File Manager.Ink</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot)]\7zFM.exe.O.ico</appv: Icon>
     </appv:Shortcut>
</appv:Extension>
     </Subsystems>
<MachineConfiguration>
     <Subsystems>
          <Registry>
               <Include>
                    <Key Path="\REGISTRY\Machine\Software\7zip">
                    <Value Type=”REG_SZ" Name="Config" Data="1234"/>
               </Include>
          </Registry>
     </Subsystems>
```

## <a name="side-by-side-assemblies"></a><a href="" id="bkmk-sidebyside-assemblies"></a>サイド バイ サイド アセンブリ


App-V は、仮想アプリケーションの公開中にクライアントでのシーケンス処理と展開中に、サイド バイ サイド (SxS) アセンブリの自動パッケージ化をサポートします。 App-V 5 SP2 は、シーケンシング マシンに存在しないアセンブリのシーケンス中に SxS アセンブリをキャプチャできます。 Visual C++ (バージョン 8 以降) および/または MSXML 実行時で構成されるアセンブリの場合、監視中にインストールされていない場合でも、Sequencer はこれらの依存関係を自動的に検出してキャプチャします。 サイド バイ サイド アセンブリ機能は、以前のバージョンの App-V の制限を取り除きます。App-V Sequencer はシーケンス ワークステーションに既に存在するアセンブリをキャプチャし、パッケージごとに 1 ビット バージョンに制限されたアセンブリを民営化していなかった。 この動作により、必要な SxS アセンブリが欠落しているクライアントに App-V アプリケーションが展開され、アプリケーションの起動エラーが発生しました。 これにより、パッケージ化プロセスが文書化され、パッケージに必要なすべてのアセンブリがユーザーのクライアント オペレーティング システムにローカルにインストールされ、仮想アプリケーションのサポートが確保されます。 アセンブリの数と必要な依存関係に関するアプリケーション ドキュメントの不足に基づいて、このタスクは管理と実装の両方の課題でした。

App-V でのサイド バイ サイド アセンブリのサポートには、次の機能があります。

-   シーケンスワークステーションにアセンブリが既にインストールされているかどうかに関係なく、シーケンス中の SxS アセンブリの自動キャプチャ。

-   App-V クライアントは、必要な SxS アセンブリが存在しない発行時にクライアント コンピューターに自動的にインストールします。

-   Sequencer は、Sequencer レポートメカニズムで VC の実行時の依存関係を報告します。

-   Sequencer を使用すると、Sequencer に既にインストールされているアセンブリをパッケージ化することを選択し、アセンブリが以前にターゲット コンピューターにインストールされているシナリオをサポートします。

### <a name="automatic-publishing-of-sxs-assemblies"></a>SxS アセンブリの自動発行

SxS アセンブリを使用した App-V パッケージの発行中に、App-V クライアントはコンピューター上のアセンブリの有無を確認します。 アセンブリが存在しない場合、クライアントはアセンブリをコンピューターに展開します。 接続グループの一部であるパッケージは、接続グループにアセンブリのインストールに関する情報が含まれているので、基本パッケージの一部であるサイド バイ サイド アセンブリ インストールに依存します。

**備考**  
アセンブリを使用してパッケージを非公開または削除しても、そのパッケージのアセンブリは削除されません。

 

## <a name="client-logging"></a><a href="" id="bkmk-client-logging"></a>クライアント ログ


App-V クライアントは、標準 ETW 形式Windowsイベント ログに情報を記録します。 特定の App-V イベントは、イベント ビューアーの [アプリケーションとサービス ログ\\Microsoft\\AppV\\Client] にあります。

**備考**  
App-V 5.0 SP3 では、一部のログが統合され、次の場所に移動されました。

`Event logs/Applications and Services Logs/Microsoft/AppV/ServiceLog`

移動されたログの一覧については [、「App-V 5.0 SP3 について」を参照してください](about-app-v-50-sp3.md#bkmk-event-logs-moved)。

 

以下に示すイベントには、3 つの特定のカテゴリが記録されています。

**管理者**: App-V クライアントに適用されている構成のイベントをログに記録し、主な警告とエラーが含まれます。

**操作**: App-V クライアントで完了した App-V 操作の監査ログを作成する個々のコンポーネントの一般的な App-V の実行と使用状況をログに記録します。

**仮想アプリケーション**: 仮想アプリケーションの起動と仮想化サブシステムの使用をログに記録します。






 

 





