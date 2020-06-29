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
ms.openlocfilehash: 69fcf119faaf35e53ae36f386bcb3480e2ee3b0e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814731"
---
# アプリケーションの公開とクライアントとのやり取り


この記事では、一般的な App-v クライアント操作とローカルオペレーティングシステムとの統合に関する技術情報について説明します。

-   [Sequencer によって作成された app-v パッケージファイル](#bkmk-appv-pkg-files-list)

-   [Appv ファイルには何がありますか?](#bkmk-appv-file-contents)

-   [App-v クライアントデータの保存場所](#bkmk-files-data-storage)

-   [パッケージレジストリ](#bkmk-pkg-registry)

-   [App-v パッケージストアの動作](#bkmk-pkg-store-behavior)

-   [ローミングのレジストリとデータ](#bkmk-roaming-reg-data)

-   [App-v クライアントアプリケーションのライフサイクル管理](#bkmk-clt-app-lifecycle)

-   [App-v パッケージの統合](#bkmk-integr-appv-pkgs)

-   [動的構成処理](#bkmk-dynamic-config)

-   [Side-by-side アセンブリ](#bkmk-sidebyside-assemblies)

-   [クライアントログ](#bkmk-client-logging)

その他の参照情報については、 [Microsoft Application Virtualization (app-v) のドキュメントリソースのダウンロードページ](https://www.microsoft.com/download/details.aspx?id=27760)を参照してください。

## <a href="" id="bkmk-appv-pkg-files-list"></a>Sequencer によって作成された app-v パッケージファイル


Sequencer は App-v パッケージを作成し、仮想化されたアプリケーションを生成します。 シーケンス処理では、次のファイルが作成されます。

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
<td align="left"><p>appv</p></td>
<td align="left"><ul>
<li><p>シーケンス処理からキャプチャされたアセットと状態情報を含むプライマリパッケージファイル。</p></li>
<li><p>パッケージファイル、公開情報、およびトークン化された形式での、配布時にコンピューターと特定のユーザーに再適用可能なレジストリのアーキテクチャ。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>.MSI</p></td>
<td align="left"><p>手動で、またはサードパーティの展開プラットフォームを使用して、app-v ファイルを展開するために使用できる実行可能な展開ラッパー。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>_DeploymentConfig.XML</p></td>
<td align="left"><p>App-v クライアントを実行しているコンピューター上のすべてのユーザーにグローバルに展開されるパッケージ内のすべてのアプリケーションの既定の発行パラメーターをカスタマイズするために使用されるファイル。</p></td>
</tr>
<tr class="even">
<td align="left"><p>_UserConfig.XML</p></td>
<td align="left"><p>App-v クライアントを実行しているコンピューター上の特定のユーザーに展開されているパッケージ内のすべてのアプリケーションの発行パラメーターをカスタマイズするために使用されるファイルです。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Report.xml</p></td>
<td align="left"><p>ドライバーの除外、ファイル、レジストリの場所など、シーケンス処理の結果として発生するメッセージの概要。</p></td>
</tr>
<tr class="even">
<td align="left"><p>.CAB</p></td>
<td align="left"><p><em>オプション: </em> 以前にシーケンスされた仮想アプリケーションパッケージを自動的に再構築するために使用されるパッケージアクセラレータファイル。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>appvt</p></td>
<td align="left"><p><em>オプション: </em> 一般的に再利用される sequencer 設定を保持するために使用される sequencer テンプレートファイル。</p></td>
</tr>
</tbody>
</table>

 

シーケンスの詳細については、「 [Application Virtualization シーケンスのガイド](https://go.microsoft.com/fwlink/?LinkID=269810)」を参照してください。

## <a href="" id="bkmk-appv-file-contents"></a>Appv ファイルには何がありますか?


Appv ファイルは、XML ファイルと XML 以外のファイルを1つのエンティティに保存するコンテナーです。 このファイルは、オープンパッケージ規則 (OPC) 標準に基づいた AppX 形式で作成されています。

Appv ファイルの内容を表示するには、パッケージのコピーを作成し、コピーしたファイルの名前を ZIP 拡張子に変更します。

Appv ファイルには、仮想アプリケーションを作成して発行するときに使用する、次のフォルダーとファイルが含まれています。

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
<td align="left"><p>シーケンス中にキャプチャされる、仮想化されたアプリケーションのファイルシステムを含むディレクトリ。</p></td>
</tr>
<tr class="even">
<td align="left"><p>[Content_Types] .xml</p></td>
<td align="left"><p>XML ファイル</p></td>
<td align="left"><p>Appv ファイル (DLL、EXE、BIN など) の主要なコンテンツタイプの一覧です。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AppxBlockMap.xml</p></td>
<td align="left"><p>XML ファイル</p></td>
<td align="left"><p>Appv ファイルのレイアウト。ファイル、ブロック、およびブロックマップ要素を使用します。これにより、App-v パッケージ内のファイルの場所と検証が有効になります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>AppxManifest.xml</p></td>
<td align="left"><p>XML ファイル</p></td>
<td align="left"><p>パッケージの追加、発行、起動に必要な情報が含まれているパッケージのメタデータ。 パッケージに関連付けられている拡張ポイント (ファイルの種類の関連付けとショートカット) と、名前と Guid が含まれます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>FilesystemMetadata.xml</p></td>
<td align="left"><p>XML ファイル</p></td>
<td align="left"><p>シーケンス中にキャプチャされたファイルの一覧。属性 (例: ディレクトリ、ファイル、非透過ディレクトリ、空のディレクトリ、および長い名前と短い名前) が含まれます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>PackageHistory.xml</p></td>
<td align="left"><p>XML ファイル</p></td>
<td align="left"><p>シーケンスコンピューターについての情報 (オペレーティングシステムのバージョン、Internet Explorer のバージョン、.Net Framework のバージョン) とプロセス (アップグレード、パッケージバージョン) について説明します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>.Dat</p></td>
<td align="left"><p>DAT ファイル</p></td>
<td align="left"><p>パッケージのシーケンス処理中にキャプチャされたレジストリキーと値。</p></td>
</tr>
<tr class="even">
<td align="left"><p>StreamMap.xml</p></td>
<td align="left"><p>XML ファイル</p></td>
<td align="left"><p>プライマリおよび発行機能ブロックのファイルのリスト。 発行機能ブロックには、パッケージを発行するためのファイル (EXE と DLL) の ICO ファイルと必要な部分が含まれています。 存在する場合、プライマリ機能ブロックには、シーケンス処理中にストリーミング用に最適化されたファイルが含まれます。</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-files-data-storage"></a>App-v クライアントデータの保存場所


App-v クライアントは、仮想アプリケーションが適切に動作し、ローカルにインストールされたアプリケーションと同じように動作するように、タスクを実行します。 仮想アプリケーションを開いて実行するプロセスには、仮想ファイルシステムとレジストリからのマッピングが必要です。これにより、ユーザーが予期している従来のアプリケーションの必要なコンポーネントをアプリケーションに確実に持たせることができます。 このセクションでは、仮想アプリケーションを実行するために必要なアセットと、App-v にアセットが保存されている場所を一覧表示します。

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
<td align="left"><p>パッケージストア</p></td>
<td align="left"><p>%ProgramData%\App-V</p></td>
<td align="left"><p>読み取り専用パッケージファイルの既定の場所</p></td>
</tr>
<tr class="even">
<td align="left"><p>マシンカタログ</p></td>
<td align="left"><p>%ProgramData%\Microsoft\AppV\Client\Catalog</p></td>
<td align="left"><p>コンピューターごとの構成ドキュメントが含まれています</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ユーザーカタログ</p></td>
<td align="left"><p>%AppData%\Microsoft\AppV\Client\Catalog</p></td>
<td align="left"><p>ユーザーごとの構成ドキュメントが含まれています</p></td>
</tr>
<tr class="even">
<td align="left"><p>ショートカットバックアップ</p></td>
<td align="left"><p>%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups</p></td>
<td align="left"><p>パッケージの未公開の復元を可能にする、以前の統合ポイントが保存されます</p></td>
</tr>
<tr class="odd">
<td align="left"><p>書き込み時 (COW) ローミング</p></td>
<td align="left"><p>%AppData%\Microsoft\AppV\Client\VFS</p></td>
<td align="left"><p>パッケージを変更するための書き込み可能なローミングの場所</p></td>
</tr>
<tr class="even">
<td align="left"><p>書き込み時 (COW) のローカルコピー</p></td>
<td align="left"><p>%LocalAppData%\Microsoft\AppV\Client\VFS</p></td>
<td align="left"><p>パッケージを変更するための書き込み可能なローミングしない場所</p></td>
</tr>
<tr class="odd">
<td align="left"><p>コンピューターのレジストリ</p></td>
<td align="left"><p>HKLM\Software\Microsoft\AppV</p></td>
<td align="left"><p>VReg for machine またはグローバルに公開されたパッケージ (コンピューターハイブ) などのパッケージの状態情報が含まれています。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ユーザーレジストリ</p></td>
<td align="left"><p>HKCU\Software\Microsoft\AppV</p></td>
<td align="left"><p>VReg などのユーザーパッケージの状態情報が含まれています。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ユーザーレジストリクラス</p></td>
<td align="left"><p>Hkcu\ ソフトウェア \ クラス \ AppV</p></td>
<td align="left"><p>追加のユーザーパッケージの状態情報が含まれています</p></td>
</tr>
</tbody>
</table>

 

表の詳細については、次のセクションとドキュメント全体で説明します。

### パッケージストア

App-v クライアントは、パッケージストアにマウントされているアプリケーションアセットを管理します。 この既定の保存場所はですが `%ProgramData%\App-V` 、セットアップ中またはセットアップ後に構成するには、 `Set-AppVClientConfiguration` ローカルレジストリ ( `PackageInstallationRoot` キーの下の値) を変更する PowerShell コマンドを使用し `HKLM\Software\Microsoft\AppV\Client\Streaming` ます。 パッケージストアは、クライアントオペレーティングシステムのローカルパスに配置されている必要があります。 個々のパッケージは、パッケージ GUID とバージョン GUID という名前のサブディレクトリのパッケージストアに格納されます。

特定のアプリケーションへのパスの例:

``` syntax
C:\ProgramData\App-V\PackGUID\VersionGUID
```

セットアップ時にパッケージストアの既定の場所を変更する方法については、「 [App-v クライアントを展開する方法](how-to-deploy-the-app-v-client-51gb18030.md)」を参照してください。

### 共有コンテンツストア

App-v クライアントが共有コンテンツストアモードで構成されている場合、ストリームフォールトが発生したときに、データはディスクに書き込まれません。つまり、パッケージでは、最小限のローカルディスク領域 (パブリッシュデータ) が必要です。 ディスク領域を節約するには、ローカルストレージを制限できるため、高パフォーマンスのネットワーク上の場所 (SAN など) からアプリケーションをストリーミングすることをお勧めします。 共有コンテンツストアモードの詳細については、を参照してください <https://go.microsoft.com/fwlink/p/?LinkId=392750> 。

**注** App-v クライアントで共有コンテンツストアの構成を使用している場合でも、コンピューターとパッケージストアはローカルドライブに配置されている必要があります。

 

### パッケージカタログ

App-v クライアントは、次の2つのファイルベースの場所を管理します。

-   **カタログ (ユーザーとコンピューター)**

-   **レジストリの場所**: パッケージの発行方法によって異なります。 コンピューターのカタログ (データストア) と個々のユーザーのカタログがあります。 コンピューターカタログには、すべてのユーザーまたは任意のユーザーに適用されるグローバル情報が保存され、ユーザーカタログには特定のユーザーに適用される情報が格納されます。 カタログは、動的構成とマニフェストファイルのコレクションです。パッケージバージョンごとの file と registry のどちらにも個別のデータがあります。 

### マシンカタログ

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>説明</p></td>
<td align="left"><p>パッケージが追加されて発行されるときに、コンピューター上のユーザーが利用できるパッケージドキュメントを保存します。 ただし、公開時にパッケージが "グローバル" の場合、すべてのユーザーが統合を利用できます。</p>
<p>パッケージがグローバルでない場合は、特定のユーザーに対してのみ統合が公開されますが、グローバルリソースは、クライアントコンピューター上のすべてのユーザーに対して変更されて表示されます (たとえば、パッケージディレクトリは共有ディスクの場所にあります)。</p>
<p>パッケージがコンピューター上のユーザー (グローバルまたは非グローバル) で利用できる場合、マニフェストはコンピューターカタログに格納されます。 パッケージがグローバルに公開されている場合、コンピューターカタログに保存されている動的構成ファイルがあります。したがって、パッケージがグローバルであるかどうかは、コンピューターカタログのポリシーファイル (UserDeploymentConfiguration ファイル) があるかどうかによって定義されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>既定の保存場所</p></td>
<td align="left"><p><code>%programdata%\Microsoft\AppV\Client\Catalog&lt;/code&gt;</p>
<p>この場所は、パッケージストアの場所とは異なります。 パッケージストアは、パッケージファイルのゴールデンまたは pristine のコピーです。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Machine カタログ内のファイル</p></td>
<td align="left"><ul>
<li><p>Manifest.xml</p></li>
<li><p>DeploymentConfiguration.xml</p></li>
<li><p>UserManifest.xml (グローバルに公開されるパッケージ)</p></li>
<li><p>UserDeploymentConfiguration.xml (グローバルに公開されるパッケージ)</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>パッケージが接続グループの一部であるときに使用される、追加のコンピューターカタログの場所</p></td>
<td align="left"><p>次の場所は、上で説明した特定のパッケージの場所に加えています。</p>
<p><code>%programdata%\Microsoft\AppV\Client\Catalog\PackageGroups\ConGroupGUID\ConGroupVerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p>パッケージが接続グループの一部である場合の、コンピューターカタログ内の追加ファイル</p></td>
<td align="left"><ul>
<li><p>PackageGroupDescriptor.xml</p></li>
<li><p>UserPackageGroupDescriptor.xml (グローバルに公開された接続グループ)</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### ユーザーカタログ

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>説明</p></td>
<td align="left"><p>発行プロセス中に作成されます。 パッケージの公開に使用される情報が含まれています。また、起動時に、特定のユーザーにパッケージがプロビジョニングされていることを確認するためにも使われます。 ローミングの場所に作成され、ユーザー固有の公開情報が含まれます。</p>
<p>ユーザーに対してパッケージが公開されると、ポリシーファイルがユーザーカタログに格納されます。 同時に、マニフェストのコピーもユーザーカタログに保存されます。 ユーザーに対してパッケージの利用資格が削除されると、関連するパッケージファイルがユーザーカタログから削除されます。 ユーザーカタログを見ると、管理者は動的な構成ファイルの存在を見ることができます。これは、パッケージがそのユーザーの権利を持つことを示します。</p>
<p>ローミングユーザーの場合は、ユーザーカタログをローミングまたは共有の場所に置いて、既定でターゲットユーザーを指定するようにする必要があります。 利用資格とポリシーは、コンピューターではなくユーザーに関連付けられているため、プロビジョニングされたユーザーと一緒に移動する必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>既定の保存場所</p></td>
<td align="left"><p><code>appdata\roaming\Microsoft\AppV\Client\Catalog\Packages\PkgGUID\VerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p>ユーザーカタログ内のファイル</p></td>
<td align="left"><ul>
<li><p>UserManifest.xml</p></li>
<li><p>DynamicConfiguration.xml または UserDeploymentConfiguration.xml</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>パッケージが接続グループの一部であるときに使用される追加のユーザーカタログの場所</p></td>
<td align="left"><p>次の場所は、上で説明した特定のパッケージの場所に加えています。</p>
<p><code>appdata\roaming\Microsoft\AppV\Client\Catalog\PackageGroups\PkgGroupGUID\PkgGroupVerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p>パッケージが接続グループの一部である場合の、コンピューターカタログ内の追加ファイル</p></td>
<td align="left"><p><code>UserPackageGroupDescriptor.xml</code></p></td>
</tr>
</tbody>
</table>

 

### ショートカットバックアップ

公開プロセス中に、App-v クライアントは、ショートカットと統合ポイントをこのバックアップにバックアップし `%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups.` ます。これにより、パッケージが未公開の場合、これらの統合ポイントを以前のバージョンに復元することができます。

### 書き込み時にファイルをコピーする

パッケージストアには、発行サーバーからストリーミングされたパッケージファイルの pristine コピーが含まれています。 App-v アプリケーションの通常の操作では、ユーザーまたはサービスはファイルの変更が必要になることがあります。 アプリを修復する機能を維持するために、これらの変更はパッケージストアでは行われません。そのため、これらの変更は削除されます。 これらの場所は、書き込み時にコピー (COW) と呼ばれ、ローミングとローミング以外の場所の両方をサポートします。 変更が保存される場所は、ネイティブエクスペリエンスに変更を書き込むためにプログラムがプログラミングされている場所によって異なります。

### COW ローミング

上で説明した COW ローミングの場所には、一般的な% AppData% の場所または \\Users\\{username}\\AppData\\Roaming の場所を対象とするファイルとディレクトリへの変更が保存されています。 これらのディレクトリとファイルは、オペレーティングシステムの設定に基づいてローミングされます。

### COW ローカル

COW ローカルの場所はローミングの場所と似ていますが、ローミングサポートが構成されている場合でも、ディレクトリとファイルは他のコンピューターにはローミングされません。 上で説明した COW ローカル上の場所は、一般的な windows に適用されますが、% AppData% の場所は変更できません。 一覧に表示されるディレクトリは異なりますが、Windows の標準的な場所 (一般的な AppData や一般的な AppDataS など) には2つの場所があります。 **S**は、仮想サービスが、ログオンしているユーザーとは別の管理者として変更を要求した場合に、制限された場所を示します。 非**S**位置には、ユーザーベースの変更が保存されます。

## <a href="" id="bkmk-pkg-registry"></a>パッケージレジストリ


アプリケーションがパッケージのレジストリデータにアクセスできるようにするには、その前に、App-v クライアントでパッケージのレジストリデータをアプリケーションで使用できるようにする必要があります。 App-v クライアントは、実際のレジストリをすべてのレジストリデータのバッキングストアとして使用します。

新しいパッケージを App-v クライアントに追加すると、レジストリのコピーが作成されます。パッケージからの DAT ファイルは、で作成され `%ProgramData%\Microsoft\AppV\Client\VREG\{Version GUID}.dat` ます。 ファイルの名前は、のバージョン GUID です。DAT 拡張機能。 このコピーが行われる理由は、パッケージの実際のハイブファイルが使用されていないことを確認することです。これにより、後でパッケージを削除できなくなります。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>パッケージストアからのレジストリ</strong></p></td>
<td align="left"><p><strong> &gt; </strong></p></td>
<td align="left"><p><strong>%ProgramData%\Microsoft\AppV\Client\Vreg {VersionGuid} .dat</strong></p></td>
</tr>
</tbody>
</table>

 

クライアントでパッケージの最初のアプリケーションが起動されると、クライアントはハイブファイルの内容をステージまたはコピーし、別の場所でパッケージレジストリデータを再作成し `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\Packages\PackageGuid\Versions\VersionGuid\REGISTRY` ます。 ステージされたレジストリデータには、2つの異なる種類のコンピューターデータとユーザーデータがあります。 マシンデータは、マシン上のすべてのユーザーに対して共有されます。 ユーザーデータは、ユーザーごとにユーザー固有の場所にステージングされ `HKCU\Software\Microsoft\AppV\Client\Packages\PackageGuid\Registry\User` ます。 マシンデータは、パッケージの削除時に最終的に削除され、ユーザーのデータが削除された場合にユーザーデータが削除されます。

### パッケージレジストリステージングと接続グループレジストリステージング

接続グループが存在する場合、以前のレジストリのステージングプロセスは true を保持しますが、1つの hive ファイルを処理する代わりに、複数のハイブファイルがあります。 ファイルは、接続グループ XML に表示されている順序で処理され、最初のライターが競合に勝利します。

ステージされたレジストリは、1つのパッケージケースと同じように維持されます。 ステージングされたユーザーのレジストリデータは、無効になるまで接続グループに残ります。接続グループの削除時にステージマシンのレジストリデータが削除されます。

### 仮想レジストリ

仮想レジストリ (VREG) の目的は、パッケージレジストリとネイティブレジストリの1つのマージされたビューをアプリケーションに提供することです。 また、書き込み時書き込み (COW) 機能も提供します。これは、仮想プロセスのコンテキストからレジストリに加えられたすべての変更を、個別の COW 位置に作成することです。 つまり、VREG は、レジストリの COW-ネイティブで設定されている場所に基づいて、最大3つの個別のレジストリ位置を1つのビューに結合する必要があることを意味し &gt; &gt; ます。 レジストリデータに対する要求が行われると、要求されたデータが検出されるまで順番に検索されます。 つまり、COW の場所に格納されている値がある場合は、他の場所に移動しません。ただし、COW の場所にデータが存在しない場合は、パッケージに進み、適切なデータが見つかるまで、ネイティブの場所に格納します。

### レジストリの場所

パッケージが個別に公開されるか、または接続グループの一部として公開されるかに応じて、2つのパッケージレジストリの場所と2つの接続グループの場所があります。 パッケージ用の COW 場所は3つあり、接続グループには3つあり、VREG によって作成および管理されます。 パッケージと接続グループの設定は共有されません。

**シングルパッケージ VReg:**

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
<td align="left"><p><strong>手法</strong></p></td>
<td align="left"><ul>
<li><p>コンピューター Registry\Client\Packages\PkgGUID\REGISTRY (書き込みできるのは昇格プロセスのみ)</p></li>
<li><p>ユーザー Registry\Client\Packages\PkgGUID\REGISTRY (ユーザーローミング (ソフトウェア \ クラス以外の HKCU の下に記載されているもの)</p></li>
<li><p>User Registry Classes\Client\Packages\PkgGUID\REGISTRY (hkcu¥ソフトウェア \ クラスの書き込みと、昇格していないプロセスの HKLM)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Package</strong></p></td>
<td align="left"><ul>
<li><p>コンピューター Registry\Client\Packages\PkgGUID\Versions\VerGuid\Registry\Machine</p></li>
<li><p>User Registry Classes\Client\Packages\PkgGUID\Versions\VerGUID\Registry</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>先住民</strong></p></td>
<td align="left"><ul>
<li><p>ネイティブアプリケーションのレジストリの場所</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

 

**接続グループの VReg:**

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
<td align="left"><p><strong>手法</strong></p></td>
<td align="left"><ul>
<li><p>コンピューター Registry\Client\PackageGroups\GrpGUID\REGISTRY (書き込みできるのは昇格プロセスのみ)</p></li>
<li><p>ユーザー Registry\Client\PackageGroups\GrpGUID\REGISTRY (ソフトウェア \ クラス以外の HKCU に書き込まれているもの)</p></li>
<li><p>User Registry Classes\Client\PackageGroups\GrpGUID\REGISTRY</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Package</strong></p></td>
<td align="left"><ul>
<li><p>コンピューター Registry\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</p></li>
<li><p>User Registry Classes\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>先住民</strong></p></td>
<td align="left"><ul>
<li><p>ネイティブアプリケーションのレジストリの場所</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

 

HKLM には2つの COW の場所があります。昇格した管理者以外のプロセス 昇格されたプロセスは、HKLM の下のセキュリティ保護された COW に HKLM の変更を常に書き込みます。 昇格されていないプロセスは、常に、セキュリティで保護されていない COW に HKLM の変更を記録します。 アプリケーションが HKLM から変更を読み取ると、昇格したプロセスは HKLM のセキュリティ保護された COW からの変更を読み取ります。 どちらからも昇格していない読み取りは、安全でない COW の最初に行われた変更を favoring します。

### パススルーキー

パススルーキーを使用すると、管理者は、パッケージと COW の場所をバイパスしてネイティブレジストリからのみ読み取り可能になるように、特定のキーを構成できます。 パススルー場所は、(パッケージ固有ではなく) マシンに対してグローバルであり、キーへのパスを追加することで構成できます。これは、キーのパスを渡すことによって、キーのパスを、キーのパス**と呼ばれる** **REG \ _MULTI \ _SZ**値に渡すことができ `HKLM\Software\Microsoft\AppV\Subsystem\VirtualRegistry` ます。 この複数文字列値 (およびその子) の下に表示されるすべてのキーは、パススルーとして扱われます。

既定では、次の場所がパススルー場所として構成されます。

-   HKEY \ _CURRENT \ _USER \ ソフトウェア \ クラス \\ ローカル Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel

-   HKEY \ _LOCAL \ _MACHINE \ ソフトウェア \ クラス \\ ローカル Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel

-   HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WINEVT

-   HKEY \ _LOCAL \ _MACHINE \\SYSTEM\\CurrentControlSet\\services\\eventlog\\Application

-   HKEY \ _LOCAL \ _MACHINE \\SYSTEM\\CurrentControlSet\\Control\\WMI\\Autologger

-   HKEY \ _CURRENT \ _USER \\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet の設定

-   HKEY \ _LOCAL \ _MACHINE \ ソフトウェア \\ Windows nt¥のバージョン \\ Perflib

-   HKEY \ _LOCAL \ _MACHINE \\ ソフトウェア \\ ポリシー

-   HKEY \ _CURRENT \ _USER \\ ソフトウェア \\ ポリシー

パススルーキーの目的は、仮想アプリケーションが VReg で、操作や統合を成功させるために非仮想アプリケーションに必要なレジストリデータを書き込むことがないようにすることです。 [ポリシー] キーを使うと、管理者によって設定されたグループポリシーベースの設定が使用されるようになり、パッケージ設定ごとには使用できなくなります。 AppModel キーは、Windows モダン UI ベースのアプリケーションと統合するために必要です。 既定のパススルーキーを変更しないことをお勧めしますが、場合によっては、アプリケーションの動作に基づいて追加のパススルーキーを追加する必要があります。

## <a href="" id="bkmk-pkg-store-behavior"></a>App-v パッケージストアの動作


App-v 5 は、パッケージストアを管理します。これは、appv ファイルから展開されたアセットファイルが保存される場所です。 既定では、この場所は、\ programdata% ¥¥ V に保存され、記憶域の制限は空きディスク領域に限定されます。 パッケージストアは、前のセクションで説明したパッケージとバージョンの Guid によって整理されます。

### パッケージを追加する

App-v パッケージは、App-v クライアントのコンピューターに加えて、ステージングされます。 App-v クライアントでは、オンデマンドステージングが提供されます。 公開または手動による AppVClientPackage の場合、データ構造はパッケージストア (c:\\programdata\\App-V\\{PkgGUID}\\{VerGUID}) に組み込まれています。 StreamMap.xml で定義されている発行ブロックで識別されたパッケージファイルがシステムに追加され、最上位のフォルダーと子ファイルがステージングされて、起動時に適切なアプリケーションアセットが存在することが保証されます。

### パッケージのマウント

パッケージは、PowerShell を使って明示的に読み込むことも、 `Mount-AppVClientPackage` または**APP-V クライアント UI**を使ってパッケージをダウンロードすることもできます。 この操作では、パッケージ全体がパッケージストアに完全に読み込まれます。

### ストリーミングパッケージ

App-v クライアントを構成して、ストリーミングの既定の動作を変更することができます。 すべてのストリーミングポリシーは、次のレジストリキーに保存され `HKEY_LOCAL_MAcHINE\Software\Microsoft\AppV\Client\Streaming` ます。 ポリシーは、PowerShell コマンドレットを使って設定し `Set-AppvClientConfiguration` ます。 ストリーミングには、次のポリシーが適用されます。

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
<td align="left"><p>Windows 8 以降では、3G および携帯電話ネットワーク上でのストリーミングが可能になります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ロード</p></td>
<td align="left"><p>バックグラウンド読み込み設定を指定します。</p>
<p><strong>0 </strong> - 無効</p>
<p><strong>1 </strong> -以前に使用したパッケージのみ</p>
<p><strong>2 </strong> –すべてのパッケージ</p></td>
</tr>
<tr class="odd">
<td align="left"><p>PackageInstallationRoot</p></td>
<td align="left"><p>ローカルコンピューターのパッケージストアのルートフォルダー</p></td>
</tr>
<tr class="even">
<td align="left"><p>パッケージパッケージ</p></td>
<td align="left"><p>パッケージをストリーミングする必要があるルートの上書き</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SharedContentStoreMode</p></td>
<td align="left"><p>VDI シナリオで共有コンテンツストアを使用できるようにします。</p></td>
</tr>
</tbody>
</table>

 

 

これらの設定は、クライアントに対する App-v パッケージアセットの動作に影響します。 既定では、最初の発行とプライマリ機能ブロックをダウンロードした後に必要なアセットのみがアプリによってダウンロードされます。 ストリーミングパッケージについては、次の3つの具体的な動作について説明する必要があります。

-   バックグラウンドストリーミング

-   最適化されたストリーミング

-   ストリームフォールト

### バックグラウンドストリーミング

PowerShell コマンドレットを使用して、 `Get-AppvClientConfiguration` バックグラウンドストリーミングの現在のモードを確認できます。これには、AppvClientConfiguration または registry (HKLM\\SOFTWARE\\Microsoft\\AppV\\ClientStreaming key) を使って、自動読み込み設定を使用します。 バックグラウンドストリーミングは既定の設定で、以前に使用したパッケージをダウンロードするための自動ロード設定が設定されています。 既定の設定 (値 = 1) に基づく動作は、アプリケーションが起動された後にバックグラウンドで App-v データブロックをダウンロードします。 この設定は、起動されているかどうかにかかわらず、すべてのパッケージ (値 = 0) またはすべてのパッケージ (value = 2) で無効にすることができます。

### 最適化されたストリーミング

アプリ-V パッケージは、シーケンス中にプライマリ機能ブロックを使って構成できます。 この設定により、シーケンスエンジニアは、特定のアプリケーションやアプリケーションの起動ファイルを監視し、パッケージ内のアプリケーションの最初の起動時にストリーミングのために、ストリーミング用にデータのブロックをマークすることができます。

### ストリームフォールト

発行データとプライマリ機能ブロックの最初のストリームの後に、追加のファイルの要求によってストリームフォールトが実行されます。 これらのデータのブロックは、必要に応じてパッケージストアにダウンロードされます。 これにより、ユーザーはパッケージのわずかな部分のみをダウンロードできます。通常は、パッケージを起動して通常のタスクを実行します。 他のすべてのブロックは、ユーザーが現在パッケージストアに含まれていないデータを必要とする操作を開始したときにダウンロードされます。

App-v パッケージのストリーミングアクセスの詳細については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=392770> 。

ストリーミング最適化のシーケンスは、次のページで参照でき <https://go.microsoft.com/fwlink/?LinkId=392771> ます。

### パッケージのアップグレード

App-v パッケージを適用するには、アプリケーションのライフサイクル全体を通じて更新する必要があります。 App-v パッケージのアップグレードは、パッケージの公開操作と似ていますが、各バージョンは独自の "パッケージ" という場所で作成され `%ProgramData%\App-V\{PkgGUID}\{newVerGUID}` ます。 アップグレード操作は、同じパッケージの他のバージョンから、同一およびストリーム形式のファイルへのハードリンクを作成することによって最適化されています。

### パッケージの削除

パッケージが削除されるときの App-v クライアントの動作は、削除に使用されるメソッドによって異なります。 アプリケーションの発行を取り下げるために、App-v の完全なインフラストラクチャを使うと、ユーザーカタログファイル (グローバルに公開されたアプリケーションのコンピューターカタログ) は削除されますが、パッケージストアの場所と COW の場所は保持されます。 PowerShell コマンドレットを `Remove-AppVClientPackge` 使用して App-v パッケージを削除すると、パッケージストアの場所がクリーンアップされます。 管理サーバーからの App-v パッケージの未発行は、削除操作を実行しないことに注意してください。 どちらの操作でも、パッケージストアパッケージファイルは削除されません。

## <a href="" id="bkmk-roaming-reg-data"></a>ローミングのレジストリとデータ


アプリ-V 5 は、使用されているアプリケーションの書き込み方法に応じて、ローミング時にほぼネイティブなエクスペリエンスを提供できます。 既定では、オペレーティングシステムのローミング構成に基づいて、ローミングの場所に格納されている App-v ローミングの AppData が指定されています。 ファイルベースのデータを格納するための他の場所は、ローミングされていない場所にあるため、コンピューター間ではローミングされません。

### <a href="" id="bkmk-clt-inter-roam-reqs"></a>ローミング要件とユーザーカタログデータストレージ

App-v は、次の形式のデータを保存します。これは、ユーザーのカタログの状態を表します。

-   %Appdata%\\Microsoft\\AppV\\Client\\Catalog のファイル

-   レジストリ設定 `HKEY_CURRENT_USER\Software\Microsoft\AppV\Client\Packages`

これらのファイルとレジストリ設定は、ユーザーのカタログを表しているため、どちらもローミングするか、または特定のユーザーに対してローミングする必要があります。 App-v はローミング% AppData% をサポートしていませんが、ユーザーのプロファイル (レジストリ) をローミングすることはできません。またその逆もできません。

**注** **AppvClientPackage**コマンドレットでは、ユーザーのアプリの状態が [不足] または [ `HKEY_CURRENT_USER` % appdata%] のデータと一致しない場合、パッケージの発行状態は修復されません。

 

### レジストリベースのデータ

App-v registry ローミングは、次の表のように2つのシナリオに分類されます。

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
<td align="left"><p>標準ユーザーが App-v アプリケーションを起動すると、アプリケーションの HKLM と HKCU の両方が、コンピューター上の HKCU ハイブに保存されます。 これは、2つの異なるパスとして表示されます。</p>
<ul>
<li><p>HKLM: HKCU\SOFTWARE\Classes\AppV\Client\Packages {PkgGUID} \ REGISTRY\MACHINE\SOFTWARE</p></li>
<li><p>HKCU: HKCU\SOFTWARE\Microsoft\AppV\Client\Packages {PkgGUID} \ REGISTRY\USER {UserSID} \ ソフトウェア</p></li>
</ul>
<p>この場所は、オペレーティングシステムの設定に基づいてローミングが有効になっています。</p></td>
</tr>
<tr class="even">
<td align="left"><p>昇格を使用して実行されるアプリケーション</p></td>
<td align="left"><p>昇格を使ってアプリケーションを起動すると、次のようになります。</p>
<ul>
<li><p>HKLM データはローカルコンピューターの HKLM ハイブに保存されている</p></li>
<li><p>HKCU データは、ユーザーのレジストリの場所に格納されます。</p></li>
</ul>
<p>このシナリオでは、これらの設定は通常のオペレーティングシステムローミング構成ではローミングされず、作成したレジストリキーと値は次の場所に格納されます。</p>
<ul>
<li><p>HKLM\SOFTWARE\Microsoft\AppV\Client\Packages {PkgGUID} {UserSID} \ REGISTRY\MACHINE\SOFTWARE</p></li>
<li><p>HKCU\SOFTWARE\Microsoft\AppV\Client\Packages {PkgGUID} \ Registry\User {UserSID} \ ソフトウェア</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### App-v とフォルダーのリダイレクト

App-v 5.1 は、ローミング AppData フォルダーのフォルダーリダイレクション (% AppData%) をサポートしています。 仮想環境が開始されると、ユーザーのローミングの AppData ディレクトリからローミングの AppData の状態がローカルキャッシュにコピーされます。 逆に、仮想環境がシャットダウンされると、特定のユーザーのローミング AppData に関連付けられているローカルキャッシュは、そのユーザーのローミング用の AppData ディレクトリの実際の場所に転送されます。

一般的なパッケージには、appdata¥ Local と AppData\\Roaming. の両方の設定のために、ユーザーのバッキングストアでマップされた複数の場所があります。 これらの場所は、ユーザーのプロファイル内のユーザーごとに保存され、パッケージの VFS ディレクトリに加えられた変更を保存し、既定のパッケージの VFS を保護するために使用される、書き込み場所のコピーです。

次の表は、フォルダリダイレクションが実装されていない場合のローカルとローミングの場所を示しています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">パッケージ内の VFS ディレクトリ</th>
<th align="left">バッキングストアのマップされた場所</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ProgramFilesX86</p></td>
<td align="left"><p>C:\users\jsmith\AppData の &lt; 強い &gt; 地元 </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ programfilesx86</p></td>
</tr>
<tr class="even">
<td align="left"><p>SystemX86</p></td>
<td align="left"><p>C:\users\jsmith\AppData の &lt; 強い &gt; 地元 </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ systemx86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows</p></td>
<td align="left"><p>C:\users\jsmith\AppData の &lt; 強い &gt; 地元 </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \windows</p></td>
</tr>
<tr class="even">
<td align="left"><p>appv_ROOT</p></td>
<td align="left"><p>C:\users\jsmith\AppData の &lt; 強い &gt; 地元 </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ appv_ROOT</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AppData</p></td>
<td align="left"><p>C:\users\jsmith\AppData の &lt; 強い &gt; ローミング </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ AppData</p></td>
</tr>
</tbody>
</table>

 

 

次の表では、フォルダリダイレクションが% AppData% に実装されていて、場所がリダイレクトされている場合 (通常はネットワーク上の場所) を示しています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">パッケージ内の VFS ディレクトリ</th>
<th align="left">バッキングストアのマップされた場所</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ProgramFilesX86</p></td>
<td align="left"><p>C:\users\jsmith\AppData の &lt; 強い &gt; 地元 </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ programfilesx86</p></td>
</tr>
<tr class="even">
<td align="left"><p>SystemX86</p></td>
<td align="left"><p>C:\users\jsmith\AppData の &lt; 強い &gt; 地元 </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ systemx86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows</p></td>
<td align="left"><p>C:\users\jsmith\AppData の &lt; 強い &gt; 地元 </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \windows</p></td>
</tr>
<tr class="even">
<td align="left"><p>appv_ROOT</p></td>
<td align="left"><p>C:\users\jsmith\AppData の &lt; 強い &gt; 地元 </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ appv_ROOT</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AppData</p></td>
<td align="left"><p><strong>\ サーバ </strong> \users\jsmith\roaming\Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ AppData</p></td>
</tr>
</tbody>
</table>

 

 

現在の App-v クライアントの VFS ドライバーは、ネットワーク上の場所に書き込むことができないため、App-v クライアントは、フォルダーリダイレクションの存在を検出し、発行時と仮想環境の開始時にローカルドライブ上のデータをコピーします。 ユーザーが app-v アプリケーションを閉じた後、App-v クライアントが仮想環境を閉じると、VFS AppData のローカルストレージがネットワークにコピーされて、他のコンピューターへのローミングが有効になり、プロセスが繰り返されます。 プロセスの詳細な手順は次のとおりです。

1.  パブリッシングまたは仮想環境の起動時に、App-v クライアントによって AppData ディレクトリの場所が検出されます。

2.  ローミングの AppData パスが local または ino appdata¥ローミングの場所がマッピングされている場合は、何も起こりません。

3.  ローミングの AppData パスがローカルではない場合、VFS AppData ディレクトリはローカルの AppData ディレクトリにマップされます。

このプロセスによって、App-v クライアントの VFS ドライバーでサポートされていないローカル以外の% AppData% の問題が解決されます。 ただし、この新しい場所に保存されているデータは、フォルダーリダイレクションではローミングされません。 アプリケーションの実行中のすべての変更は、local AppData の位置情報に対して行われ、リダイレクトされた場所にコピーする必要があります。 このプロセスの詳細な手順は次のとおりです。

1.  App-v アプリケーションがシャットダウンされ、仮想環境がシャットダウンされます。

2.  ローミング用の AppData の場所のローカルキャッシュは圧縮され、ZIP ファイルに保存されます。

3.  ZIP パッケージ処理の最後のタイムスタンプを使って、ファイルに名前を指定します。

4.  タイムスタンプは、 &lt; &gt; 最後の既知の AppData のタイムスタンプとして、HKEY \ _CURRENT \ _USER \\Software\\microsoft\\appv\\client\\packages\\ GUID \\AppDataTime のレジストリに記録されます。

5.  フォルダリダイレクションプロセスが呼び出されて、ローミングの AppData ディレクトリにアップロードされた ZIP ファイルが評価され、開始されます。

このタイムスタンプは、競合が発生した場合に "最後のライター wins" シナリオを決定するために使用され、アプリが公開されたとき、または仮想環境が開始されたときにデータのダウンロードを最適化するために使われます。 フォルダーリダイレクションは、サポートポリシーによってカバーされている他のクライアントからデータを利用できるようにします。また、appdata¥ローミングデータをクライアント上の local AppData の場所に保存するプロセスを開始します。 詳細なプロセスは次のとおりです。

1.  ユーザーは、アプリケーションを起動して仮想環境を開始します。

2.  アプリケーションの仮想環境では、最新のタイムスタンプ付き ZIP ファイルが存在する場合は、そのファイルがチェックされます。

3.  レジストリのチェックボックスがオンになっている場合は、最後にアップロードされた既知のタイムスタンプを確認します。

4.  ローカルの最後のアップロードのタイムスタンプが ZIP ファイルのタイムスタンプ以上でなければ、最新の ZIP ファイルがダウンロードされます。

5.  ローカルの最終既知のアップロードのタイムスタンプが、ローミングの AppData の最新の ZIP ファイルよりも前にある場合は、ZIP ファイルはユーザーのプロファイルのローカルの temp ディレクトリに抽出されます。

6.  ZIP ファイルが正常に抽出されると、ローミングの AppData ディレクトリのローカルキャッシュが名前が変更され、新しいデータが所定の位置に移動されます。

7.  名前を変更したディレクトリが削除され、最近保存されたローミングの AppData データでアプリケーションが開きます。

これにより、appdata¥ローミング場所に存在するアプリケーション設定の移動が正常に完了します。 対処する必要があるその他の条件は、パッケージの修復操作だけです。 プロセスの詳細は次のとおりです。

1.  修復中に、ユーザーのローミング用の AppData ディレクトリへのパスがローカルでないかどうかを検出します。

2.  ローカル以外のローミングパスのターゲットをマップすると、期待されるローミングとローカル AppData の場所が再作成されます。

3.  レジストリに保存されているタイムスタンプを削除します (存在する場合)。

このプロセスでは、AppData のローカルとネットワークの場所の両方を再作成し、タイムスタンプのレジストリレコードを削除します。

## <a href="" id="bkmk-clt-app-lifecycle"></a>App-v クライアントアプリケーションのライフサイクル管理


アプリが順番に実行された場合、アプリは、アプリの順序が付けられた後、アプリの管理と発行サーバーを介して、ユーザーまたはコンピューターに管理され、公開されます。 このセクションでは、共通の App-v アプリケーションのライフサイクル操作 (追加、公開、起動、アップグレード、および削除) の際に発生する操作と、App-v クライアントの視点から変更および変更されたファイルとレジストリの場所について詳しく説明します。 App-v クライアント操作は、App-v クライアントを実行しているコンピューターで開始される一連の PowerShell コマンドとして実行されます。

このドキュメントでは、App-v の完全なインフラストラクチャソリューションに焦点を当てています。 Configuration Manager 2012 との App-v との統合の詳細については、「」を参照してください <https://go.microsoft.com/fwlink/?LinkId=392773> 。

App-v アプリケーションのライフサイクルタスクは、ユーザーのログイン (既定)、コンピューターの起動時、またはバックグラウンドの時間指定操作でトリガーされます。 公開サーバー、更新間隔、パッケージスクリプトの有効化などの、App-v クライアント操作の設定は、クライアントのセットアップまたは PowerShell コマンドを使ってセットアップするときに構成します。 TechNet の「クライアントを展開する方法」を参照してください。 [App-v クライアントを展開する方法](how-to-deploy-the-app-v-client-51gb18030.md)、または PowerShell を使用する方法について説明します。

```powershell
get-command *appv*
```

### 公開の更新

発行の更新処理は、App-v クライアントで実行されるいくつかの小さな操作で構成されます。 App-v はアプリケーションの仮想化テクノロジであり、タスクスケジュール技術ではないため、Windows タスクスケジューラを使用して、ユーザーのログオン、コンピューターの起動時、およびスケジュールされた間隔でプロセスを有効にすることができます。 上記のセットアップ中のクライアントの構成は、適切な設定でクライアントを大規模なコンピューターグループに配布する場合に推奨される方法です。 これらのクライアント設定は、次の PowerShell コマンドレットを使用して構成できます。

-   **Add-AppVPublishingServer:** App-v パッケージを提供する App-v パブリッシングサーバーでクライアントを構成します。

-   **Set-AppVPublishingServer:** App-v 発行サーバーの現在の設定を変更します。

-   **Set-AppVClientConfiguration:** App-v クライアントの currents 設定を変更します。

-   **同期-AppVPublishingServer:** App-v の公開更新プロセスを手動で開始します。 これは、発行サーバーの構成中に作成されたスケジュールされたタスクでも使用されます。

以下のセクションでは、App-v の公開更新のさまざまなフェーズで発生する操作の詳細について説明します。 次のトピックが含まれます。

-   App-v パッケージを追加する

-   App-v パッケージの発行

### App-v パッケージを追加する

クライアントへの App-v パッケージの追加は、公開の更新プロセスの最初の手順です。 最終的な結果は `Add-AppVClientPackage` PowerShell のコマンドレットと同じですが、[発行更新の追加] プロセスの場合を除いて、構成済みの発行サーバーは接続され、1つのパッケージ追加操作ではなく、より詳細な情報を取得するために、クライアントに上位レベルのアプリケーションの一覧を渡します。 このプロセスは、パッケージまたは接続グループの追加または更新のためにクライアントを構成して続行し、appv ファイルにアクセスします。 次に、appv ファイルの内容が展開され、ローカルオペレーティングシステムの適切な場所に配置されます。 次に、パッケージがフォールトストリーミング用に構成されていることを前提とした、プロセスの詳細なワークフローを示します。

**App-v パッケージを追加する方法**

1.  PowerShell 経由の手動開始、または発行更新プロセスのタスクシーケンスの開始。

    1.  App-v クライアントは、HTTP 接続を行って、ターゲットに基づいてアプリケーションの一覧を要求します。 発行の更新プロセスでは、ターゲットコンピューターまたはユーザーがサポートされます。

    2.  App-v 発行サーバーは、開始するターゲット、ユーザー、またはコンピューターの id を使用し、データベースにアプリケーションの一覧を照会します。 アプリケーションの一覧は XML 応答として提供されます。クライアントは、パッケージごとに追加の要求をサーバーに送信するために使用します。

2.  App-v クライアントの発行エージェントは、次のすべての操作をシリアル化して実行します。

    接続グループの一部であるパッケージバージョンの更新を処理できないため、未発行または無効なすべての接続グループを評価します。

3.  追加操作または更新操作を識別して、パッケージを構成します。

    1.  App-v クライアントでは、Windows の AppX API を利用し、発行サーバーから appv ファイルにアクセスします。

    2.  パッケージファイルが開かれ、AppXManifest.xml と StreamMap.xml がパッケージストアにダウンロードされます。

    3.  StreamMap.xml で定義された完全な公開ブロックデータ。 パッケージストア¥ pkgguid¥ verguid¥の公開ブロックデータを格納します。

        -   アイコン: 拡張ポイントのターゲット。

        -   移植可能な実行可能ヘッダー (PE ヘッダー): イメージに関する基本情報が含まれる拡張ポイントのターゲット。ディスク上に直接アクセスしているか、ファイルの種類を介して直接アクセスします。

        -   スクリプト: 発行プロセス全体で使用するために、スクリプトディレクトリをダウンロードします。

    4.  パッケージストアにデータを設定します。

        1.  一覧表示されているすべてのディレクトリについて抽出されたパッケージを表す、ディスク上にスパースファイルを作成します。

        2.  ルートの下にある上位レベルのファイルとディレクトリをステージ化します。

        3.  その他のすべてのファイルは、ディレクトリがディスクのスパースとして表示され、オンデマンドでストリーミングされたときに作成されます。

    5.  マシンカタログエントリを作成します。 パッケージファイルから Manifest.xml と DeploymentConfiguration.xml を作成します (パッケージ内の DeploymentConfiguration.xml ファイルがプレースホルダーに作成されていない場合)。

    6.  レジストリ HKLM\\Software\\Microsoft\\AppV\\Client\\Packages\\PkgGUID\\Versions\\VerGUID\\Catalog でパッケージストアの場所を作成します。

    7.  パッケージストアから%ProgramData%\\Microsoft\\AppV\\Client\\VReg\\ {VersionGUID} .dat に、レジストリファイルを作成します。

    8.  App-v カーネルモードドライバー HKLM\\Microsoft\\Software\\AppV\\MAV でパッケージを登録します。

    9.  パッケージの AppxManifest.xml または DeploymentConfig.xml ファイルからスクリプトを呼び出して、タイミングを追加します。

4.  追加と有効化または無効化によって接続グループを構成します。

5.  ターゲット (ユーザーまたはコンピューター) に発行されていないオブジェクトを削除します。

    **注** この操作では、パッケージ削除は実行されませんが、特定のターゲット (ユーザーまたはコンピューター) の統合ポイントが削除され、ユーザーカタログファイル (グローバルに公開されているコンピューターカタログファイル) が削除されます。

     

6.  クライアント構成に基づいて、バックグラウンドでの読み込みマウントを呼び出します。

7.  マシンまたはユーザーについて既に公開情報を持っているパッケージは、直ちに復元されます。

    **注** この状態は、パッケージをバックグラウンドで追加することなく、削除しなくても削除の製品として発生します。

     

これにより、App-v パッケージの発行更新プロセスが完了します。 次の手順では、パッケージを特定のターゲット (コンピューターまたはユーザー) に公開します。

![パッケージファイルとレジストリデータを追加する](images/packageaddfileandregistrydata.png)

### App-v パッケージの発行

公開の更新操作では、特定の発行操作 (AppVClientPackage) によって、ユーザーカタログにエントリが追加され、ユーザーに資格が割り当てられ、ローカルストアが識別され、統合手順が完了して終了します。 次に、詳細な手順を示します。

**公開と App-v パッケージの発行方法**

1.  パッケージエントリがユーザーカタログに追加される

    1.  ユーザーを対象にしたパッケージ: ユーザーカタログのコンピューターに UserDeploymentConfiguration.xml と UserManifest.xml が配置されます。

    2.  マシンの対象指定 (グローバル) パッケージ: UserDeploymentConfiguration.xml がコンピューターカタログに配置される

2.  HKLM\\Software\\Microsoft\\AppV\\MAV でユーザーのためにカーネルモードドライバーでパッケージを登録します。

3.  統合タスクを実行します。

    1.  延長点を作成します。

    2.  ユーザーのレジストリとローミングプロファイル (ショートカットバックアップ) にバックアップ情報を保存します。

        **注** これにより、パッケージが未公開の場合は、拡張ポイントを復元できるようになります。

         

    3.  公開タイミングのターゲットとなるスクリプトを実行します。

接続グループの一部である App-v パッケージの公開は、上記のプロセスと非常に似ています。 接続グループの場合、特定のカタログ情報を格納するパスには、カタログディレクトリの子として PackageGroups が含まれます。 詳細については、上記のコンピューターとユーザーのカタログ情報を確認してください。

![パッケージファイルとレジストリデータの追加-グローバル](images/packageaddfileandregistrydata-global.png)

### アプリケーションの起動

公開の更新プロセスが完了すると、ユーザーはアプリを起動し、その後で App-v アプリケーションを再起動します。 このプロセスは非常にシンプルで、最小限のネットワークトラフィックですばやく起動するように最適化されています。 App-v クライアントは、発行中に作成されたファイルについて、ユーザーカタログへのパスを確認します。 パッケージを起動する権利が確立されると、App-v クライアントは仮想環境を作成し、必要なデータのストリーミングを開始し、仮想環境の作成時に適切なマニフェストと展開構成ファイルを適用します。 仮想環境が作成され、特定のパッケージとアプリケーション用に構成されると、アプリケーションが起動します。

**App-v アプリケーションを起動する方法**

1.  ユーザーは、ショートカットまたはファイルの種類の呼び出しをクリックしてアプリケーションを起動します。

2.  App-v クライアントが、次のファイルに対するユーザーカタログの存在を確認します。

    -   UserDeploymentConfiguration.xml

    -   UserManifest.xml

3.  ファイルが存在する場合、アプリケーションはその特定のユーザーの資格を持ち、アプリケーションは起動のプロセスを開始します。 この時点では、ネットワークトラフィックはありません。

4.  次に、app-v クライアントは、App-v Client サービスに登録されているパッケージのパスがレジストリで検出されていることを確認します。

5.  パッケージストアへのパスを見つけると、仮想環境が作成されます。 初めての起動の場合は、プライマリ機能ブロックがある場合はダウンロードされます。

6.  ダウンロードした後、App-v クライアントサービスはマニフェストと展開構成ファイルを使用して、仮想環境とすべての App-v サブシステムの読み込みを構成します。

7.  アプリケーションが起動します。 パッケージストア (スパースファイル) に不足しているファイルがある場合は、必要に応じて、ファイルが stream によってエラーが発生します。

    ![パッケージファイルとレジストリデータストリームの追加](images/packageaddfileandregistrydata-stream.png)

### App-v パッケージのアップグレード

App-v 5 パッケージのアップグレードプロセスは、以前のバージョンの App-v とは異なります。 App-v では、異なるユーザーに対してコンピューター上の同じパッケージの複数のバージョンがサポートされています。 パッケージバージョンは、パッケージストアとしていつでも追加できます。また、新しいリソースでカタログが更新されます。 新しいバージョンリソースの追加に固有のプロセスは、記憶域の最適化です。 アップグレード中は、新しいバージョンのストアの場所に新しいファイルのみが追加され、変更されていないファイルに対してハードリンクが作成されます。 これにより、ディスク上の1つの場所でファイルを表示して、ディスク上のファイルの場所エントリを持つすべてのフォルダーに投影するだけで、全体的な記憶域が削減されます。 App-v パッケージのアップグレードの具体的な詳細は次のとおりです。

**App-v パッケージのアップグレード方法**

1.  App-v クライアントは、公開の更新を実行し、新しいバージョンの App-v パッケージを検出します。

2.  パッケージエントリは、新しいバージョンの適切なカタログに追加されます。

    1.  ユーザーを対象にしたパッケージ: appdata\\roaming\\Microsoft\\AppV\\Client\\Catalog\\Packages\\PkgGUID\\VerGUID でユーザーカタログのコンピューターに配置される UserDeploymentConfiguration.xml と UserManifest.xml

    2.  コンピューターの対象指定 (グローバル) パッケージ: UserDeploymentConfiguration.xml は、%programdata%\\Microsoft\\AppV\\Client\\Catalog\\Packages\\PkgGUID\\VerGUID のコンピューターカタログに配置されます。

3.  HKLM\\Software\\Microsoft\\AppV\\MAV でユーザーのためにカーネルモードドライバーでパッケージを登録します。

4.  統合タスクを実行します。

    -   マニフェストおよび動的構成ファイルから拡張機能 (EP) を統合します。

    1.  ファイルベースの EP データは、パッケージストアからの接合ポイントを利用する AppData フォルダーに格納されます。

    2.  新しいバージョンが使用可能になったときに、バージョン1の EPs は既に存在します。

    3.  拡張ポイントは、新しいまたは更新された拡張ポイントについて、マシンまたはユーザーのカタログ内のバージョン2の場所に切り替えられます。

5.  公開タイミングのターゲットとなるスクリプトを実行します。

6.  必要に応じて、side-by-side アセンブリをインストールします。

### 使用中の App-v パッケージのアップグレード

**App-v 5 SP2 以降**: エンドユーザーが使用しているパッケージをアップグレードしようとすると、アップグレードタスクは保留状態になります。 アップグレードは、次のルールに従って後で実行されます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスクの種類</th>
<th align="left">該当するルール</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ユーザーベースのタスク (パッケージをユーザーに公開するなど)</p></td>
<td align="left"><p>保留中のタスクは、ユーザーがログオフしてから再びログインした後に実行されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>グローバルに基づくタスク (例: 接続グループをグローバルに有効にする)</p></td>
<td align="left"><p>保留中のタスクは、コンピューターをシャットダウンしてから再起動したときに実行されます。</p></td>
</tr>
</tbody>
</table>

 

タスクが保留状態になっている場合、App-v クライアントは、次のように、保留中のタスクのレジストリキーも生成します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ユーザーベースまたはグローバルベースのタスク</th>
<th align="left">レジストリキーが生成される場所</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ユーザーベースのタスク</p></td>
<td align="left"><p>KEY_CURRENT_USER \Software\Microsoft\AppV\Client\PendingTasks</p></td>
</tr>
<tr class="even">
<td align="left"><p>グローバルに基づくタスク</p></td>
<td align="left"><p>HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\PendingTasks</p></td>
</tr>
</tbody>
</table>

 

ユーザーが新しいバージョンのパッケージを使用できるようにするには、次の操作を完了する必要があります。

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
<td align="left"><p>このタスクはコンピューターに固有のものであり、上記のパッケージ追加のセクションの手順に従って、いつでも実行できます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>パッケージを公開する</p></td>
<td align="left"><p>手順については、上記のパッケージ発行に関するセクションを参照してください。 このプロセスでは、システムの拡張ポイントを更新する必要があります。 このタスクを完了するときにエンドユーザーがアプリケーションを使用することはできません。</p></td>
</tr>
</tbody>
</table>

 

パッケージを更新するためのガイドとして、次のシナリオの例を使用します。

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
<td align="left"><p>アップグレードしようとしたときに、app-v パッケージが使用されない</p></td>
<td align="left"><p>仮想アプリケーション、COM サーバー、またはシェルの拡張機能を使って、パッケージの次のコンポーネントを使用することはできません。</p>
<p>管理者が新しいバージョンのパッケージを公開し、次回パッケージ内のコンポーネントまたはアプリケーションが起動したときにアップグレードが動作します。 パッケージの新しいバージョンがストリーミングされ、実行されます。 このシナリオでは、アプリ-v 5 の以前のリリースからの app-v 5 SP2 では何も変更されていません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>管理者がパッケージの新しいバージョンを発行するときに、app-v パッケージが使用されている</p></td>
<td align="left"><p>アップグレード操作は、App-v クライアントによって保留状態に設定されます。つまり、パッケージが使用されていないときに、キューに登録され、後で実行されることを意味します。</p>
<p>パッケージアプリケーションを使用している場合、ユーザーは仮想アプリケーションをシャットダウンした後、アップグレードが発生する可能性があります。</p>
<p>パッケージにシェル拡張機能 (Office 2013) が含まれている場合、Windows エクスプローラーによって完全に読み込まれるため、ユーザーはログインできません。 ユーザーはログオフし、もう一度ログインして、App-v パッケージのアップグレードを開始する必要があります。</p></td>
</tr>
</tbody>
</table>

 

### グローバル vs ユーザー発行

App-v パッケージは、次の2つの方法のいずれかで公開できます。特定のユーザーまたはユーザーのグループに対してアプリ V パッケージを適用し、コンピューターのすべてのユーザーに対して、アプリ全体に対して app-v パッケージを適用するユーザー。 パッケージのアップグレードが保留になっていて、App-v パッケージが使用されていない場合は、次の2種類の発行を検討してください。

-   **グローバルに公開済み**: アプリケーションはコンピューターに公開されます。そのコンピューター上のすべてのユーザーがそれを使うことができます。 アップグレードは、App-v Client サービスが開始されたときに発生します。これは、実質的にコンピューターの再起動を意味します。

-   **ユーザーが公開**されました: アプリケーションはユーザーに公開されます。 コンピューターに複数のユーザーがいる場合、そのアプリケーションはユーザーのサブセットに公開できます。 アップグレードは、ユーザーがログインしたとき、または再び公開されたとき (定期的に、ConfigMgr ポリシーの更新と評価、または PowerShell コマンドを使って明示的に実行した場合) に行われます。

### App-v パッケージの削除

完全なインフラストラクチャでの App-v アプリケーションの削除は、未発行操作であり、パッケージの削除は実行されません。 このプロセスは、上の発行プロセスと同じですが、削除プロセスを追加する代わりに、App-v パッケージに加えられた変更を元に戻します。

### App-v パッケージを修復する

修復操作は非常に簡単ですが、コンピューター上の多くの場所に影響する可能性があります。 前に説明した Copy on Write (COW) の場所は削除され、拡張ポイントは統合されていない状態になり、再び統合されます。 COW データの配置場所を確認するには、レジストリに登録されている場所を確認してください。 この操作は自動的に実行され、アプリ-V クライアント本体または PowerShell 経由 (AppVClientPackage) から修復操作を開始する場合以外に、管理者が制御することはできません。

## <a href="" id="bkmk-integr-appv-pkgs"></a>App-v パッケージの統合


App-v クライアントとパッケージアーキテクチャは、パッケージの追加と発行中にローカルのオペレーティングシステムとの固有の統合を実現します。 3つのファイルは、App-v パッケージの統合または拡張ポイントを定義します。

-   AppXManifest.xml: パッケージの内部に保存され、パッケージストアとユーザープロファイルに保存されているフォールバックコピーが含まれます。 シーケンス処理中に作成されたオプションが含まれています。

-   DeploymentConfig.xml: コンピューターとユーザーによる統合の拡張ポイントの構成情報を提供します。

-   UserConfig.xml: ユーザーベースの構成のみを提供し、ユーザーベースの拡張ポイントのみをターゲットとする Deploymentconfig.xml のサブセット。

### 統合のルール

App-v アプリケーションが app-v クライアントを備えたコンピューターに公開されると、次の一覧に示すように特定の操作が行われます。

-   グローバル公開: ショートカットは、[すべてのユーザー] プロファイルの場所と他の拡張ポイントに保存され、HKLM ハイブのレジストリに格納されます。

-   ユーザー公開: ショートカットは、現在のユーザーアカウントプロファイルに保存され、その他の拡張ポイントは、HKCU ハイブのレジストリに格納されます。

-   バックアップと復元: 既存のネイティブアプリケーションデータとレジストリ (FTA 登録など) は、発行時にバックアップされます。

    1.  App-v パッケージには、所有権が最新の公開された App-v アプリケーションに渡される、最後の統合パッケージに基づいて所有権が付与されます。

    2.  所有している App-v パッケージが公開されていない場合は、1つのアプリから別のアプリに所有権が転送されます。 これにより、データまたはレジストリの復元が開始されることはありません。

    3.  拡張ポイントごとに、最後のパッケージが未公開または削除されたときに、バックアップしたデータを復元します。

### 拡張点

App-v の公開ファイル (マニフェストと動的構成) には、アプリケーションをローカルオペレーティングシステムと統合できるようにするいくつかの拡張ポイントが用意されています。 これらの拡張機能は、ショートカットの配置、ファイルの種類の関連付けの作成、コンポーネントの登録など、一般的なアプリケーションのインストールタスクを実行します。 従来のアプリケーションと同じ方法でインストールされない仮想アプリケーションは、いくつかの違いがあります。 このセクションで取り上げている拡張ポイントの一覧を次に示します。

-   ショートカット

-   ファイルの種類の関連付け

-   シェルの拡張機能

-   COM

-   ソフトウェアクライアント

-   アプリケーションの機能

-   URL プロトコルハンドラー

-   AppPath

-   仮想アプリケーション

### ショートカット

短い切り取りは、OS との統合の基本的な要素の1つであり、App-v アプリケーションを直接ユーザーが起動するためのインターフェイスです。 App-v アプリケーションの発行と発行取り消し中。

パッケージマニフェストと動的構成 XML ファイルから、特定のアプリケーションの実行可能ファイルへのパスは、次のようなセクションにあります。

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

前に説明したように、App-v のショートカットは、更新操作に基づいて既定でユーザーのプロファイルに配置されます。 グローバル更新場所 [すべてのユーザー] プロファイルとユーザー更新のショートカットは、特定のユーザーのプロファイルに格納されます。 実際の実行可能ファイルは、パッケージストアに格納されます。 ICO ファイルの場所は、App-v パッケージ内のトークン化された場所です。

### ファイルの種類の関連付け

App-v クライアントは、発行中にローカルのオペレーティングシステムのファイルの種類の関連付けを管理します。これにより、ユーザーはファイルの種類の呼び出しを使用したり、明示的に登録された拡張子 (.docx) を使ってファイルを開いたりして、App-v アプリケーションを起動することができます。 ファイルの種類の関連付けは、次の例で示すようにマニフェストと動的構成ファイルに存在します。

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

**注** この例では、次の操作を行います。

-   `<Name>.xdp</Name>` は拡張機能です

-   `<Name>AcroExch.XDPDoc</Name>` は ProgId 値 (付加された ProgId を指します)

-   `<CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe" "%1"</CommandLine>` はコマンドラインで、アプリケーションの実行可能ファイルを指します。

 

### シェル拡張

シェルの拡張機能は、シーケンス処理中にパッケージに自動的に埋め込まれます。 パッケージがグローバルに公開されると、シェル拡張によって、アプリケーションがローカルにインストールされている場合と同じ機能をユーザーに提供できます。 アプリケーションでは、シェルの拡張機能を有効にするために、クライアントで追加のセットアップや構成を行う必要はありません。

**シェルの拡張機能を使用するための要件:**

-   埋め込まれたシェルの拡張機能を含むパッケージは、グローバルに公開する必要があります。

-   アプリケーション、Sequencer、および App-v クライアントの "ビット" は一致する必要があります。また、シェルの拡張機能は使用できません。 以下に例を示します。

    -   このアプリケーションのバージョンは64ビットです。

    -   Sequencer は64ビットコンピューターで実行されています。

    -   パッケージは、64ビットの App-v クライアントコンピューターに配信されます。

次の表は、サポートされているシェルの拡張機能を示しています。

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
<td align="left"><p>コンテキストメニューハンドラー</p></td>
<td align="left"><p>コンテキストメニューにメニュー項目を追加します。 コンテキストメニューが表示される前に呼び出されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ドラッグアンドドロップハンドラー</p></td>
<td align="left"><p>ドラッグアンドドロップを右クリックし、表示されるコンテキストメニューを変更して、アクションを制御します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ドロップターゲットハンドラー</p></td>
<td align="left"><p>データオブジェクトがドラッグアンドドロップされた後、ファイルなどのドロップターゲットを介して、アクションを制御します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>データオブジェクトハンドラー</p></td>
<td align="left"><p>ファイルがクリップボードにコピーされた後、またはドロップターゲットをドラッグアンドドロップした後にアクションを制御します。 ドロップターゲットには、追加のクリップボード形式を指定できます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>プロパティシートハンドラー</p></td>
<td align="left"><p>ページをオブジェクトの [プロパティシート] ダイアログボックスに置換または追加します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ヒントハンドラー</p></td>
<td align="left"><p>マウスをポイントしたときに、項目のフラグとヒントの情報を取得し、ポップアップヒントの中に表示することができます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>列ハンドラー</p></td>
<td align="left"><p>Windows エクスプローラーの [詳細] ビューでカスタム列の作成と表示を行うことができ <em> </em> ます。 並べ替えとグループ化を拡張するために使うことができます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>プレビューハンドラー</p></td>
<td align="left"><p>エクスプローラーのプレビューウィンドウにファイルのプレビューが表示されるようにします。</p></td>
</tr>
</tbody>
</table>

 

### COM

App-v クライアントでは、COM 統合と仮想化のサポートによってアプリケーションの公開がサポートされています。 COM の統合により、App-v クライアントは、ローカルのオペレーティングシステムとオブジェクトの仮想化に COM オブジェクトを登録することができます。 このドキュメントでは、COM オブジェクトの統合について追加の詳細情報が必要です。

App-v では、プロセス外とインプロセスの2種類のプロセスを使用して、パッケージからローカルオペレーティングシステムへの COM オブジェクトの登録をサポートしています。 COM オブジェクトの登録は、オフ、分離、統合された特定のアプリ-V パッケージの複数の操作モードの組み合わせで行われます。 統合モードは、アウトプロセスまたはインプロセスのいずれかの種類に対して構成されます。 COM のモードと型の構成は、動的構成ファイル (deploymentconfig.xml または userconfig.xml) を使用して実現されます。

App-v との統合について詳しくは、次のページをご覧 <https://go.microsoft.com/fwlink/?LinkId=392834> ください。

### ソフトウェアクライアントとアプリケーション機能

App-v は、仮想化されたアプリケーションをオペレーティングシステムのソフトウェアクライアントに登録するために、特定のソフトウェアクライアントとアプリケーション機能の拡張ポイントをサポートします。 これにより、ユーザーは、メール、インスタントメッセージ、メディアプレーヤーなどの操作のための既定のプログラムを選ぶことができます。 この操作は、コントロールパネルで、[プログラムのアクセスとコンピューターの既定の設定] を使用して実行され、マニフェストまたは動的構成ファイルのシーケンス中に構成されます。 アプリケーション機能は、App-v アプリケーションがグローバルに公開されている場合にのみサポートされます。

App-v ベースのメールクライアントのソフトウェアクライアント登録の例。

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

**注** この例では、次の操作を行います。

-   `<ClientConfiguration EmailEnabled="true" />` ソフトウェアクライアント全体がメールクライアントを統合するように設定されている

-   `<EMail MakeDefault="true">` 既定のメールクライアントとして特定のメールクライアントを設定するためのフラグ

-   `<MAPILibrary>[{ProgramFilesX86}]\Mozilla Thunderbird\mozMapi32_InUse.dll</MAPILibrary>` は MAPI dll の登録です

 

### URL プロトコルハンドラー

アプリケーションは、ファイルの種類の呼び出しを利用する、常に仮想化されたアプリケーションとは限りません。 たとえば、ドキュメントまたは web ページ内の mailto: リンクの埋め込みをサポートしているアプリケーションの場合、ユーザーは mailto: リンクをクリックして、登録されているメールクライアントを取得することを想定しています。 App-v では、ローカルオペレーティングシステムでパッケージ単位で登録できる URL プロトコルハンドラーがサポートされています。 シーケンス中に、URL プロトコルハンドラーがパッケージに自動的に追加されます。

特定の URL プロトコルハンドラーを登録できるアプリケーションが複数ある場合は、動的な構成ファイルを使用して動作を変更し、プライマリアプリケーションとして起動しないアプリケーションに対してこの機能を抑制または無効にすることができます。

### AppPath

AppPath extension ポイントでは、オペレーティングシステムから直接、App-v アプリケーションの呼び出しをサポートします。 通常、この操作は、オペレーティングシステムによっては、実行可能ファイルへの特定のパスを呼び出すことなく、管理者がオペレーティングシステムのコマンドまたはスクリプトから App-v アプリケーションへのアクセスを提供できるようにするために行われます。 そのため、公開時に実行されるため、すべてのシステムでシステムパス環境変数を変更する必要はありません。

AppPath extension point は、マニフェストまたは動的構成ファイルのいずれかで構成され、ユーザーの発行時にローカルコンピューター上のレジストリに格納されます。 AppPath review の詳細については、次の情報を参照 <https://go.microsoft.com/fwlink/?LinkId=392835> してください。

### 仮想アプリケーション

このサブシステムは、シーケンス中にキャプチャされたアプリケーションのリストを提供します。これは通常、他の App-v コンポーネントによって消費されます。 動的構成ファイルを使用すると、特定のアプリケーションに属する拡張点の統合を無効にすることができます。 たとえば、2つのアプリケーションがパッケージに含まれている場合は、他のアプリケーションの拡張ポイントとの統合のみを許可するために、1つのアプリケーションに属するすべての拡張機能を無効にすることができます。

### 拡張ポイントルール

上記で説明した拡張ポイントは、パッケージの公開方法に基づいてオペレーティングシステムに統合されています。 [グローバル発行] では、[公共のコンピューター上の場所] に拡張ポイントが配置されます。ここでは、ユーザーの発行によって、ユーザーの場所に拡張 たとえば、デスクトップ上に作成され、グローバルに公開されたショートカットは、ショートカットのファイルデータ (% public% ¥ desktop) とレジストリデータ (HKLM\\Software\\Classes) になります。 同じショートカットには、ファイルデータ (%UserProfile%\\Desktop) とレジストリデータ (hkcu¥¥ $ Classes) が含まれます。

拡張ポイントは、すべて同じ方法で公開されるわけではありません。一部の拡張ポイントには、グローバル発行が必要であり、他の場合は、特定のオペレーティングシステムやアーキテクチャでの順序付けが必要になります。 以下に、これら2つの主要なルールについて説明します。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">仮想拡張機能</th>
<th align="left">ターゲット OS のシーケンスが必要</th>
<th align="left">グローバル発行が必要</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>キー</p></td>
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
<td align="left"><p>ソフトウェアクライアント</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>アプリケーションの機能</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p>○</p></td>
</tr>
<tr class="even">
<td align="left"><p>コンテキストメニューハンドラー</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p>○</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ドラッグアンドドロップハンドラー</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>データオブジェクトハンドラー</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>プロパティシートハンドラー</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>ヒントハンドラー</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>列ハンドラー</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>シェルの拡張機能</p></td>
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

 

## <a href="" id="bkmk-dynamic-config"></a>動的構成処理


App-v パッケージを1台のコンピューターまたはユーザーに展開するのは非常に簡単です。 ただし、組織が大量のビジネスラインと地理的および政治的な境界を越えて AppV アプリケーションを展開すると、1つの設定でアプリケーションを1つの方法でシーケンスすることができなくなります。 App-v は、マニフェストファイルでシーケンス処理中に特定の設定と構成をキャプチャすることに加えて、動的構成ファイルでの変更もサポートするため、このシナリオ向けに設計されています。

App-v の動的構成では、マシンレベルまたはユーザーレベルでパッケージのポリシーを指定することができます。 動的構成ファイルを使用すると、シーケンスエンジニアは、ユーザーまたはコンピューターの個々のグループのニーズに対応するために、パッケージの構成を変更することができます。 場合によっては、App-v 環境内で適切な機能を提供するために、アプリケーションの変更が必要になることがあります。 たとえば、アプリケーションの実行中に特定の操作を実行できるようにするには、\ _ \ * config.xml ファイルに変更を加える必要がある場合があります。これは、仮想化されたアプリケーションが別のアプリケーションからその拡張機能を上書きしないように mailto 拡張機能を無効にするなどの場合です。

App-v パッケージには、(シーケンス操作の代表者である) appv パッケージファイル内のマニフェストファイルが含まれています。また、動的構成ファイルが特定のパッケージに割り当てられている場合を除き、これらのポリシーが選択されます。 事後処理のために、動的構成ファイルを変更して、さまざまな内線番号を持つ別のデスクトップまたはユーザーにアプリケーションを発行できるようにすることができます。 2つの動的構成ファイルは、動的展開構成 (DDC) と動的ユーザー構成 (DUC) ファイルです。 このセクションでは、マニフェストと動的構成ファイルの組み合わせについて説明します。

### 動的構成ファイルの例

次の例では、発行後のマニフェスト、展開構成、ユーザー構成ファイルの組み合わせについて説明します。 次の例では、各ファイルの簡単な例を示します。 目的として、ファイルの組み合わせのみが表示され、各ファイルで利用可能な特定のカテゴリについての完全な説明はありません。 詳細については、次のページを参照してください。 <https://go.microsoft.com/fwlink/?LinkID=269810>

**ノート**

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

## <a href="" id="bkmk-sidebyside-assemblies"></a>Side-by-side アセンブリ


App-v は、仮想アプリケーションの発行中にクライアントに対してシーケンス処理と展開を行うときに、side-by-side (SxS) アセンブリの自動パッケージ化をサポートします。 App-v 5 SP2 では、シーケンスコンピューターにアセンブリが存在しない場合のシーケンス中の SxS アセンブリのキャプチャがサポートされています。 さらに、Visual C++ (バージョン8以降) と MSXML ランタイムで構成されているアセンブリの場合、Sequencer は、監視中にインストールされていない場合でも、これらの依存関係を自動的に検出してキャプチャします。 Side-by-side アセンブリ機能を使用すると、アプリ-V の以前のバージョンの制限を削除します。これは、シーケンスワークステーションに既に存在するアセンブリをアプリによってキャプチャすることはできません。また、パッケージごとに1つのビットバージョンに制限されているアセンブリを公開することもできます。 この動作では、展開された App-v アプリケーションで、必要な SxS アセンブリが見つからないため、アプリケーションの起動エラーが発生していました。 これにより、パッケージ化プロセスを文書化した後、仮想アプリケーションのサポートを確実にするために、パッケージに必要なすべてのアセンブリが、ユーザーのクライアントオペレーティングシステムにローカルにインストールされていることを確認します。 このタスクは、アセンブリの数と、必要な依存関係に関するアプリケーションドキュメントがないことに基づいて、管理と実装の両方の課題となっていました。

App-v の side by Side Assembly のサポートには、次の機能があります。

-   アセンブリがシーケンスワークステーションに既にインストールされているかどうかに関係なく、シーケンス中の SxS アセンブリの自動キャプチャ。

-   アプリが存在しない場合、App-v クライアントは、要求された SxS アセンブリを発行時にクライアントコンピューターに自動的にインストールします。

-   Sequencer は、Sequencer のレポートメカニズムで VC ランタイム依存関係を報告します。

-   Sequencer では、Sequencer に既にインストールされているアセンブリを選ぶことはできません。これらのアセンブリがターゲットコンピューターに既にインストールされているシナリオをサポートします。

### SxS アセンブリの自動発行

SxS アセンブリを使用して app-v パッケージを発行するときに、App-v クライアントはコンピューター上にアセンブリが存在するかどうかを確認します。 アセンブリが存在しない場合、クライアントはアセンブリをコンピューターに展開します。 接続グループの一部であるパッケージは、アセンブリインストールに関する情報が接続グループに含まれていないため、基本パッケージの一部である Side-by-side アセンブリインストールに依存します。

**注** アセンブリをパッケージ化または削除しても、そのパッケージのアセンブリは削除されません。

 

## <a href="" id="bkmk-client-logging"></a>クライアントログ


App-v クライアントは、標準の ETW 形式で Windows イベントログに情報を記録します。 特定の App-v イベントは、[アプリケーションとサービスの Logs\\Microsoft\\AppV\\Client.] の下にあるイベントビューアーで見つけることができます。

**注** App-v 5.0 SP3 では、一部のログが統合され、次の場所に移動されました。

`Event logs/Applications and Services Logs/Microsoft/AppV/ServiceLog`

移動したログの一覧については、「 [app-v 5.0 SP3 につい](about-app-v-50-sp3.md#bkmk-event-logs-moved)て」を参照してください。

 

以下に記載されている、3つの特定のイベントカテゴリがあります。

[**管理者**]: アプリ-V クライアントに適用される構成のイベントをログに記録し、プライマリ警告とエラーを格納します。

**オペレーショナル**: app-v クライアントで完了した app-v 操作の監査ログを作成する、各コンポーネントの一般的なアプリの実行と使用のログを記録します。

**仮想アプリケーション**: 仮想アプリケーションは、仮想化サブシステムの起動と使用をログに記録します。






 

 





