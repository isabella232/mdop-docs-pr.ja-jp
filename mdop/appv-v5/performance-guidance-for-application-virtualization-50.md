---
title: Application Virtualization 5.0 に関するパフォーマンス ガイダンス
description: Application Virtualization 5.0 に関するパフォーマンス ガイダンス
author: dansimp
ms.assetid: 6b3a3255-b957-4b9b-8bfc-a93fe8438a81
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 3b0f5ef07935fc34adce772e7b2fff85a12b01dc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813538"
---
# Application Virtualization 5.0 に関するパフォーマンス ガイダンス


最適なパフォーマンスを得るために App-v 5.0 を構成する方法、仮想アプリパッケージを最適化する方法、および RDS と VDI を使用してユーザーエクスペリエンスを向上させる方法について説明します。

複数の方法を実装することで、エンドユーザーエクスペリエンスを向上させることができます。 ただし、環境によっては、すべてのメソッドがサポートされないことがあります。

このドキュメントを読む前に、次の情報を読んで理解しておく必要があります。

-   [Microsoft Application Virtualization 5.0 管理者ガイド](microsoft-application-virtualization-50-administrators-guide.md)

-   [App-v 5 SP2 アプリケーションのパブリッシングとクライアントの対話式操作](https://go.microsoft.com/fwlink/?LinkId=395206)

-   [Microsoft Application Virtualization 5.0 シーケンスガイド](https://go.microsoft.com/fwlink/?LinkId=269953)

**注**  
このドキュメントで使用されている用語によっては、外部のソースとコンテキストによって意味が異なる場合があります。 このドキュメントで使用される用語の詳細については、 **\\** このドキュメントの「 [Application Virtualization のパフォーマンスに関するガイドライン](#bkmk-terms1)」を参照してください。



最後に、このドキュメントでは、App-v 5.0 クライアントを実行しているコンピューターと最適なパフォーマンスを得るための環境を構成するための情報を提供します。 Sequencer を使用してパフォーマンスの仮想アプリケーションパッケージを最適化し、ユーザーエクスペリエンスの仮想化 (UE-V) またはその他のユーザー環境管理テクノロジを使用して、リモートデスクトップサービス (RDS) と非永続的仮想デスクトップインフラストラクチャ (VDI) の両方で、最適なユーザー5.0 エクスペリエンスを提供する方法について説明します。

環境に関連する情報を特定するには、各セクションの簡単な概要と適用性のチェックリストを確認する必要があります。

## <a href="" id="---------app-v-5-0-in-stateful--non-persistent-deployments"></a> ステートフルな展開 (非永続的な展開) での app-v 5.0


このセクションでは、ログイン後にすべての仮想アプリケーションにユーザーがアクセスできるようにするために役立つ方法について説明します。 これを実現するには、長時間実行されることが多いアプリ-V 5.0 公開の更新に固有のアドレスを指定します。 アプローチの基礎となるのは、最も迅速な公開の更新です。実際に何もする必要はありません。 多くの条件を満たし、最適なユーザーエクスペリエンスを提供するための手順を実行する必要があります。

詳細については、次のセクションの情報を参照してください。

[使用シナリオ](#bkmk-us): 2 つのシナリオをレビューするときには、これらは非常によいアプローチであることに注意してください。 使用要件に基づいて、次の手順をユーザーや仮想アプリケーションパッケージのサブセットに適用することができます。

-   パフォーマンスの最適化–最適なエクスペリエンスを提供するために、基本イメージには、アプリの V 仮想アプリケーションパッケージの一部が含まれていることが想定されます。 その他の要件について説明します。

-   ストレージに最適化されています。記憶域への影響を懸念している場合は、このシナリオに従うことで問題解決に役立ちます。

[環境の準備](#bkmk-pe)

-   基本イメージを準備するための手順: 非永続的な VDI または RDSH 環境のどちらでも、この方法を有効にするためには、基本イメージの手順をいくつか実行する必要があります。

-   Ue-v のアプローチには、ユーザープロファイル管理 (UPM) ソリューションとして ue-v 2.0 を使用します。この方法の基盤は、いくつかのレジストリとファイルの場所だけのコンテンツを保持する UEM ソリューションの機能です。 これらの場所は、ユーザーインテグレーション \ * を構成します。 UPM ソリューションの固有の要件を確認してください。

[ユーザーエクスペリエンスのウォークスルー](#bkmk-uewt)

-   詳細については、この後の「アプリ-V および UE-V の操作」と「ユーザーが必要とする期待」の順を追って説明します。

-   [結果]-予期される結果が示されます。

[パッケージのライフサイクルへの影響](#bkmk-plc)

[パフォーマンスの最適化/チューニングを通じて VDI のエクスペリエンスを向上させる](#bkmk-evdi)

### <a href="" id="applicability-checklist-"></a>適用のチェックリスト

展開環境

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>非永続的な VDI または RDSH。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>ユーザーエクスペリエンスの仮想化 (UE-V)、その他の UPM ソリューション、またはユーザープロファイルディスク (UPD)。</p></td>
</tr>
</tbody>
</table>



期待される構成

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>User Experience Virtualization (UE-V) では、App-v のユーザー状態テンプレートが有効またはユーザープロファイル管理 (UPM) ソフトウェアが使用されています。 非 UE-V UPM ソフトウェアは、ログインまたはプロセス/アプリケーションの開始とログオフのトリガーに対応している必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>App-v 共有コンテンツストア (SCS) が構成されているか、構成することができます。</p></td>
</tr>
</tbody>
</table>



IT 管理

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>最適なパフォーマンスを確保するために、または管理者がさまざまなユーザーグループの複数の画像を管理する必要がある場合は、管理者が VM ベースイメージを定期的に更新する必要がある場合があります。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-us"></a>使用シナリオ

2つのシナリオを確認したら、これらの方法は非常に極端なものであることに注意してください。 使用要件に基づいて、これらの手順は、ユーザーのサブセット、仮想アプリケーションパッケージ、またはその両方に適用することができます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">パフォーマンスを最適化</th>
<th align="left">ストレージに最適化されている</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>最適なユーザーエクスペリエンスを提供するために、この手法では、UPM ソリューションの機能を活用し、追加のイメージの準備を行う必要があります。また、追加の画像管理のオーバーヘッドが発生する可能性があります。</p>
<p>次に、ステートフル非永続的展開でのさまざまなパフォーマンスの改善について説明します。 詳細については、 <strong> </strong> <strong> </strong> <strong> このドキュメントの「関連項目」セクションの「公開のパフォーマンスと5.0 参照用にパッケージを最適化する」のシーケンス手順を参照してください </strong> 。</p></td>
<td align="left"><p>前のシナリオの一般的な期待値は、ここにも適用されます。 ただし、VM イメージは通常、非常に高コストのアレイに保存されることに注意してください。アプローチに若干の変更が加えられました。 ベースイメージ内のユーザーによって対象化された仮想アプリケーションパッケージを事前に構成しないでください。</p>
<p>この変更による影響については、このドキュメントの「ユーザーエクスペリエンスのチュートリアル」を参照してください。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-pe"></a>環境の準備

次の表は、基本イメージと UE-V またはその他の UPM ソリューションを準備するために必要な手順を示しています。

**基本イメージを準備する**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">パフォーマンスを最適化</th>
<th align="left">ストレージに最適化されている</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p></p>
<ul>
<li><p>Application Virtualization 5.0 SP2 クライアントバージョンのクライアント用の修正プログラムパッケージ4をインストールします。</p></li>
<li><p>UE-V をインストールして、UE-V のテンプレートギャラリーから App-v の設定テンプレートをダウンロードします。次の手順を参照してください。</p></li>
<li><p>共有コンテンツストア (SCS) モードを構成します。 詳細については <a href="how-to-install-the-app-v-50-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.0 Client for Shared Content Store Mode](how-to-install-the-app-v-50-client-for-shared-content-store-mode.md)"> 、「共有コンテンツストアモード用の app-v 5.0 クライアントをインストールする方法」を参照してください </a> 。</p></li>
<li><p>ログインレジストリの DWORD でのユーザーの統合の保持を構成します。</p></li>
<li><p>すべてのユーザーとグローバルなパッケージを事前構成するたとえば、 <strong> AppvClientPackage を追加 </strong> します。</p></li>
<li><p>すべてのユーザーとグローバルな接続グループを事前構成し <strong> ます。たとえば、AppvClientConnectionGroup を追加し </strong> ます。</p></li>
<li><p>グローバルターゲットパッケージをすべて事前に発行します。</p>
<p></p>
<p>一方</p>
<ul>
<li><p>グローバル発行/更新を実行します。</p></li>
<li><p>ユーザーの発行/更新を実行します。</p></li>
<li><p>すべてのユーザー対象パッケージを公開解除します。</p></li>
<li><p>次のユーザー仮想ファイルシステム (VFS) エントリを削除します。</p></li>
</ul>
<p><code>AppData\Local\Microsoft\AppV\Client\VFS</code></p>
<p><code>AppData\Roaming\Microsoft\AppV\Client\VFS</code></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>Application Virtualization 5.0 SP2 クライアントバージョンのクライアント用の修正プログラムパッケージ4をインストールします。</p></li>
<li><p>UE-V をインストールして、UE-V のテンプレートギャラリーから App-v の設定テンプレートをダウンロードします。次の手順を参照してください。</p></li>
<li><p>共有コンテンツストア (SCS) モードを構成します。 詳細については <a href="how-to-install-the-app-v-50-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.0 Client for Shared Content Store Mode](how-to-install-the-app-v-50-client-for-shared-content-store-mode.md)"> 、「共有コンテンツストアモード用の app-v 5.0 クライアントをインストールする方法」を参照してください </a> 。</p></li>
<li><p>ログインレジストリの DWORD でのユーザーの統合の保持を構成します。</p></li>
<li><p>すべてのグローバル対象パッケージを事前構成し <strong> ます。たとえば、AppvClientPackage を追加 </strong> します。</p></li>
<li><p>すべてのグローバルターゲット接続グループを事前に構成するたとえば、 <strong> AppvClientConnectionGroup を追加 </strong> します。</p></li>
<li><p>グローバルターゲットパッケージをすべて事前に発行します。</p>
<p></p></li>
</ul></td>
</tr>
</tbody>
</table>



**構成**-重要な App-v クライアントの構成と、その他のコンテキストと使い方については、次の情報を確認してください。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">構成設定</th>
<th align="left">この機能について</th>
<th align="left">使い方を教えてください。</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>共有コンテンツストア (SCS) モード</p>
<ul>
<li><p><strong>AppvClientConfiguration </strong> – <strong> sharedcontentstoremode を使って PowerShell で構成でき </strong> ます。または</p></li>
<li><p>App-v 5.0 クライアントのインストール中。</p></li>
</ul></td>
<td align="left"><p>共有コンテンツストアを実行している場合、発行データはハードディスク上で管理されます。その他の仮想アプリケーションアセットは、メモリ (RAM) で管理されます。</p>
<p>これにより、ローカル記憶域を節約し、ディスク i/o を1秒あたり少なく (IOPS) 減らすことができます。</p></td>
<td align="left"><p>これは、App-v クライアントエンドポイントと SCS コンテンツサーバーである SAN の間で待機時間の短い接続が利用できる場合にお勧めします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>PreserveUserIntegrationsOnLogin</p>
<ul>
<li><p>[ <strong> HKEY_LOCAL_MACHINE </strong>  \  <strong> ソフトウェア </strong>  \  <strong> Microsoft </strong>  \  <strong> AppV </strong>  \  <strong> クライアント </strong>  \  <strong> </strong> との統合] の下のレジストリで構成します。</p></li>
<li><p>値1の DWORD 値 PreserveUserIntegrationsOnLogin を作成し <strong> </strong> <strong> </strong> ます。</p></li>
<li><p>App-v クライアントサービスを再起動するか、App-v クライアントを実行しているコンピューターを再起動します。</p></li>
</ul></td>
<td align="left"><p>特定のパッケージをまだ構成していない場合 (AppvClientPackage)、この設定が構成されていない場合 <strong> </strong> 、app-v クライアントは永続的なユーザー統合による統合を解除し、その後 * に再統合 * します。</p>
<p>上記の条件を満たしているすべてのパッケージについて、発行/更新の際に、効率的に2回作業が行われます。</p></td>
<td align="left"><p>ベースイメージで利用可能なすべてのユーザーパッケージを事前に構成する予定がない場合は、この設定を使用します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MaxConcurrentPublishingRefresh</p>
<ul>
<li><p>「Microsoft AppV 強力なクライアントの公開 HKEY_LOCAL_MACHINE」のレジストリで構成 <strong> </strong> &lt; &gt; </strong>  \  <strong> </strong>  \  <strong> </strong> &lt; &gt; </strong>  \  <strong> </strong> します。</p></li>
<li><p><strong> </strong> 同時発行の更新の最大数に応じて DWORD 値 MaxConcurrentPublishingrefresh を作成します。</p></li>
<li><p>App-v クライアントサービスとコンピューターを再起動する必要はありません。</p></li>
</ul></td>
<td align="left"><p>この設定は、同時に公開の更新/同期を実行できるユーザーの数を決定します。 既定の設定では、制限はありません。</p></td>
<td align="left"><p>同時発行の更新数を制限すると、コンピューターのパフォーマンスに影響を与える可能性のある CPU 使用量が過度に消費されることを回避できます。 この制限は、複数のユーザーが同じコンピューターに一度にログインして、発行更新同期を実行できる RDS 環境でお勧めします。</p>
<p>同時発行の更新しきい値に達した場合は、新しいアプリケーションを公開し、ログイン後にエンドユーザーがそれらのアプリを使用できるようにするために、一定の時間がかかることがあります。</p></td>
</tr>
</tbody>
</table>



### App-v のアプローチ用に UE-V ソリューションを構成する

Microsoft User Experience Virtualization (UE-V) を使用して、特定のユーザーのアプリケーション設定と Windows オペレーティングシステムの設定をキャプチャし、一元管理することをお勧めします。 これらの設定は、デスクトップコンピューター、ノート pc、仮想デスクトップインフラストラクチャ (VDI) セッションなど、ユーザーによってアクセスされるさまざまなコンピューターに適用されます。 UE-V は、RDS と VDI のシナリオに最適化されています。

詳細については、「[ユーザーエクスペリエンスの仮想化の概要 2.0](https://technet.microsoft.com/library/dn458936.aspx) 」を参照してください。

基本的に必要なことは、UE-V クライアントをインストールし、 [Microsoft User Experience Virtualization (ue-v) テンプレートギャラリー](https://gallery.technet.microsoft.com/Authored-UE-V-Settings-bb442a33)から次の microsoft 作成された app-v 設定テンプレートをダウンロードすることです。 テンプレートを登録します。 UE-V テンプレートの詳細については、「UE-V 固有のリソース」を参照してください。これにより、[テンプレートを取得して登録することが](https://technet.microsoft.com/library/dn458936.aspx)できます。

**注**  
追加の構成手順を実行しなくても、Microsoft User Environment Virtualization (UE-V) では、ターゲットコンピューター上の [スタート] メニューのショートカット (.lnk ファイル) を同期することはできません。 .Lnk ファイルの種類は、既定では除外されます。

UE-V は、RDS および VDI シナリオの除外リストから .lnk ファイルの種類を削除することのみをサポートします。ここでは、すべてのユーザーのデバイスが同じ場所にインストールされ、すべての .lnk ファイルがすべてのユーザーのデバイスで有効になります。 たとえば、現在、UE-V は、次の2つのシナリオをサポートしていません。そのため、すべてのデバイスではなく、ショートカットが有効になります。

-   .Lnk ファイルが有効になっているデバイスにユーザーがアプリケーションをインストールしていて、同じネイティブアプリケーションが別のデバイスにインストールされている場合は、.lnk ファイルが有効になっています。

-   ユーザーが1つのデバイスにアプリケーションをインストールしていて、.lnk ファイルが有効になっていない場合。



**重要**  
このトピックでは、レジストリエディターを使用して Windows レジストリを変更する方法について説明します。 Windows レジストリを誤って変更した場合、Windows の再インストールが必要になる可能性のある重大な問題が発生する可能性があります。 レジストリを変更する前に、レジストリファイル (system.dat とユーザー) のバックアップコピーを作成しておく必要があります。 Microsoft は、レジストリを変更したときに発生する可能性のある問題を解決できないことを保証できません。 レジストリは、自分の責任において変更してください。



Microsoft Registry Editor (regedit.exe) を使用して、ExcludedFileTypes の [ **HKEY \ _LOCAL \ _MACHINE**  \\  **Software**  \\  **Microsoft**  \\  **UEV**  \\  **Agent**  \\  **Configuration**  \\  **ExcludedFileTypes**に移動し、除外するファイルの種類から .lnk を削除し**ます**。

**他のユーザープロファイル管理 (UPM) ソリューションを App-v のアプローチとして構成する**

ステートフル環境で期待されるのは、UPM ソリューションが実装されていて、セッション間およびログイン間でのユーザーデータの常設をサポートできるということです。

UPM ソリューションの要件を次に示します。

最適化されたログインエクスペリエンスを有効にするには (たとえば、ユーザーの App-v 5.0 の方法)、ソリューションが次の機能をサポートしている必要があります。

-   ユーザープロファイル/ペルソナの一部として、次のユーザーの統合を保持します。

-   Login (または application start) でユーザープロファイル同期をトリガーすると、公開/更新の開始前にすべてのユーザー統合が適用されることを保証できます。

-   ユーザープロファイルディスク (UPD) またはユーザー統合を含む類似技術の接続とデタッチ。

-   セッションがログオフされる前に、ユーザー統合を構成する場所への変更をキャプチャします。

公開サーバー (**AppvPublishingServer**) を追加するときに app-v 5.0 を使用すると、ログオン時や指定した更新間隔の後など、同期を設定することができます。 どちらの場合も、スケジュールされたタスクが作成されます。

以前のバージョンの App-v 5.0 では、ユーザーとグローバル更新を開始する VBScript を使用して、両方のスケジュールされたタスクが構成されていました。 アプリケーションの仮想化 5.0 SP2 の修正プログラムパッケージ4を使用すると、ログオン時にユーザーの更新が**SyncAppvPublishingServer.exe**によって開始されます。 この変更は、UPM ソリューションにトリガープロセスを提供するために導入されました。 このプロセスでは、UPM ソリューションがユーザー統合を適用できるように、発行/更新が遅延されます。 公開/更新が完了すると終了します。

**ユーザーの統合**

Registry – HKEY \ _CURRENT \ _USER

-   Path-ソフトウェア \\ クラス

    除外: Local Settings、ActivatableClasses、AppX \ *

-   Path-ソフトウェア \ microsoft AppV

-   パス-Software\\Microsoft\\Windows\\CurrentVersion\\App のパス

**ファイルの場所**

-   ルート– "環境変数" APPDATA

    Path – Microsoft\\AppV\\Client\\Catalog

-   ルート– "環境変数" APPDATA

    Path – Microsoft\\AppV\\Client\\Integration

-   ルート– "環境変数" APPDATA

    Path-Microsoft\\Windows\\Start menu¥プログラム

-   (すべてのデスクトップショートカット、仮想と非仮想) を保持するには

    ルート-"KnownFolder" {B4BFCC3A-DB2C-424C-B029-7FE99A87C641} FileMask-\ * .lnk

**Microsoft User Experience Virtualization (UE-V)**

さらに、Microsoft User Experience Virtualization (UE-V) を使用して、特定のユーザーのアプリケーション設定と Windows オペレーティングシステムの設定をキャプチャして一元管理することをお勧めします。 これらの設定は、デスクトップコンピューター、ノート pc、仮想デスクトップインフラストラクチャ (VDI) セッションなど、ユーザーによってアクセスされるさまざまなコンピューターに適用されます。

詳細については、「[ユーザーエクスペリエンスの仮想化1.0 の概要](https://technet.microsoft.com/library/jj680015.aspx)」および「 [Ue-v のテンプレートギャラリーを使用した設定場所テンプレートの共有](https://technet.microsoft.com/library/jj679972.aspx)」を参照してください。

### <a href="" id="bkmk-uewt"></a>ユーザーエクスペリエンスのウォークスルー

ここでは、App-v および UPM の操作と、ユーザーが求める期待を段階的に説明します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">パフォーマンスを最適化</th>
<th align="left">ストレージに最適化されている</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>VDI/RDSH 環境でこの方法を実装した後、最初のログイン時に、</p>
<ul>
<li><p>実行ユーザーによる公開/更新が開始されます。 求めユーザーが初めて仮想アプリケーションを公開した場合 (永続的でない場合など) は、通常の公開/更新時間になります。</p></li>
<li><p>実行公開/更新後、UPM ソリューションによってユーザーの統合がキャプチャされます。 求めUPM ソリューションがどのように構成されているかによって、これはログオフプロセスの一部として発生することがあります。 これにより、ユーザーの状態を維持する場合と同様のオーバーヘッドが発生します。</p></li>
</ul>
<p>後続のログイン時:</p>
<ul>
<li><p>実行UPM ソリューションは、公開/更新の前にユーザー統合をシステムに適用します。</p>
<p>求めデスクトップまたは [スタート] メニューにショートカットが表示されます。この機能は、すぐに動作します。 公開/更新が完了すると (パッケージの資格の変更)、一部の機能が消える場合があります。</p></li>
<li><p>実行公開/更新では、ユーザーパッケージの利用資格の変更について、公開および公開操作が処理されます。 求め権利の変更がない場合、publishing1 は秒単位で完了します。 そうしないと、仮想アプリケーションの数と複雑さ * に関係なく発行/更新が増加します。</p></li>
<li><p>実行UPM ソリューションは、ログオフ時にもう一度ユーザーの統合をキャプチャします。 求め前と同じです。</p></li>
</ul>
<p>¹発行操作 (AppVClientPackage) では、 <strong> </strong> ユーザーカタログにエントリが追加され、ユーザーに資格がマッピングされ、ローカルストアが識別され、統合手順が完了して終了します。</p></td>
<td align="left"><p>VDI/RDSH 環境でこの方法を実装した後、最初のログイン時に、</p>
<ul>
<li><p>実行ユーザーによる公開/更新が開始されます。 求め</p>
<ul>
<li><p>ユーザーが初めて仮想アプリケーションを公開した場合 (永続的でない場合など) は、通常の公開/更新の期間がかかります。</p></li>
<li><p>最初と後のログインは、パッケージ (追加/更新) を事前に構成することによって影響を受けます。</p>
<p></p></li>
</ul></li>
<li><p>実行公開/更新後、UPM ソリューションによってユーザーの統合がキャプチャされます。 求めUPM ソリューションがどのように構成されているかによって、これはログオフプロセスの一部として発生することがあります。 これにより、ユーザーの状態を維持する場合と同様のオーバーヘッドが発生します。</p></li>
</ul>
<p>後続のログイン時:</p>
<ul>
<li><p>実行UPM ソリューションは、公開/更新の前にユーザー統合をシステムに適用します。</p></li>
<li><p>実行追加/更新では、ユーザーのすべてのターゲットアプリケーションを事前に構成する必要があります。 求め</p>
<ul>
<li><p>これにより、アプリケーションの可用性が大幅に向上することがあります (10 秒の順序で)。</p></li>
<li><p>これにより、仮想アプリケーションの数と複雑さ * に基づいて、公開の更新時間が増加します。</p>
<p></p></li>
</ul></li>
<li><p>実行公開/更新では、ユーザーパッケージの利用資格の変更について、公開および公開操作が処理されます。</p></li>
</ul></td>
</tr>
</tbody>
</table>



<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">成功</th>
<th align="left">成功</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p></p>
<ul>
<li><p>ユーザー統合は完全に保持されるため、たとえば、パブリッシング/refresh の統合などの機能はありません。 すべての仮想アプリケーションは、ログインしてから数秒以内で利用可能になります。</p></li>
<li><p>公開/更新では、エクスペリエンスに影響を与える仮想アプリケーションのユーザーに対する変更を処理します。</p></li>
</ul></td>
<td align="left"><p>追加/更新では、すべての仮想アプリケーションを仮想マシンに再構成する必要があるため、すべてのログインでの公開の更新時間は延長されます。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-plc"></a>パッケージライフサイクルへの影響

パッケージのアップグレードは、パッケージのライフサイクルにおいて非常に重要です。 ユーザーが適切にアップグレードされた (公開) またはダウングレードされた (公開されていない) 仮想アプリケーションパッケージにアクセスできることを保証するために、これらの変更を反映するように基本イメージを更新することをお勧めします。 次のセクションをレビューする理由について説明します。

App-v 5.0 SP2 では、保留状態の概念が導入されました。 かつては

-   管理者が権限を変更した場合、またはパッケージの新しいバージョン (アップグレード済み) を作成した場合、またはパッケージが使用されていた公開/更新時に、発行取り消し操作や公開操作が失敗することがあります。

-   これで、パッケージが使用中の場合、操作は保留されます。 公開/公開保留の操作は、サービスの再開時に処理されるか、または公開または非公開の別のコマンドが発行された場合に処理されます。 後者の場合、仮想アプリケーションが使用されている場合は、仮想アプリケーションは保留状態のままになります。 グローバルに公開されたパッケージの場合、再起動 (またはサービスの再起動) が必要になることがよくあります。

非永続的な環境では、保留中の操作が処理される可能性は低くなります。 タスクなどの保留中の操作は、[ **HKEY] \ _CURRENT \ _USER**  \\  **Software**  \\  **Microsoft**  \\  **AppV**  \\  **Client**  \\  **pendingtasks**] の下にキャプチャされます。 この場所は UPM ソリューションによって保持されますが、ログオン前に環境に適用されていない場合は処理されません。

### <a href="" id="bkmk-evdi"></a>パフォーマンス最適化のチューニングを通じて VDI のエクスペリエンスを向上させる

以下のセクションでは、パフォーマンスを向上させるために環境を最適化するときに役立つ可能性がある Microsoft のドキュメントとダウンロードに関する情報が記載されています。

**.NET NGEN ブログとスクリプト (強くお勧めします)**

NGEN テクノロジについて

-   [NGEN 最適化の速度を向上させる方法](https://blogs.msdn.com/b/dotnet/archive/2013/08/06/wondering-why-mscorsvw-exe-has-high-cpu-usage-you-can-speed-it-up.aspx)

-   [スクリプト](https://aka.ms/DrainNGenQueue)

**Windows サーバーおよびサーバーの役割**

のサーバーパフォーマンスのチューニングガイドライン

-   [Microsoft Windows Server 2012 R2](https://msdn.microsoft.com/library/windows/hardware/dn529133.aspx)

-   [Microsoft Windows Server 2012](https://download.microsoft.com/download/0/0/B/00BE76AF-D340-4759-8ECD-C80BC53B6231/performance-tuning-guidelines-windows-server-2012.docx)

-   [Microsoft Windows Server 2008 R2](https://download.microsoft.com/download/6/B/2/6B2EBD3A-302E-4553-AC00-9885BBF31E21/Perf-tun-srv-R2.docx)

**サーバーの役割**

-   [リモートデスクトップ仮想化ホスト](https://msdn.microsoft.com/library/windows/hardware/dn567643.aspx)

-   [リモートデスクトップセッションホスト](https://msdn.microsoft.com/library/windows/hardware/dn567648.aspx)

-   [IIS の関連度: App-v の管理、公開、レポート Web サービス](https://msdn.microsoft.com/library/windows/hardware/dn567678.aspx)

-   [ファイルサーバー (SMB) の関連度: アプリ V のコンテンツストレージと SCS モードでの配信に使用されている場合](https://technet.microsoft.com/library/jj134210.aspx)

**Windows クライアント (ゲスト OS) のパフォーマンスのチューニングガイダンス**

-   [Microsoft Windows 7](https://download.microsoft.com/download/E/5/7/E5783D68-160B-4366-8387-114FC3E45EB4/Performance Tuning Guidelines for Windows 7 Desktop Virtualization v1.9.docx)

-   [最適化スクリプト: (Microsoft サポートによって提供されます)](https://blogs.technet.com/b/jeff_stokes/archive/2012/10/15/the-microsoft-premier-field-engineer-pfe-view-on-virtual-desktop-vdi-density.aspx)

-   [Microsoft Windows 8](https://download.microsoft.com/download/6/0/1/601D7797-A063-4FA7-A2E5-74519B57C2B4/Windows_8_VDI_Image_Client_Tuning_Guide.pdf)

-   [最適化スクリプト: (Microsoft サポートによって提供されます)](https://blogs.technet.com/b/jeff_stokes/archive/2013/04/09/hot-off-the-presses-get-it-now-the-windows-8-vdi-optimization-script-courtesy-of-pfe.aspx)

## 公開のパフォーマンスのためにパッケージを最適化するためのシーケンス手順


App-v 5.0 と App-v 5.0 SP2 では、それぞれのリリースで重要な価値を提供しています。 新しいシナリオや新しい顧客の展開シナリオを可能にするいくつかの機能があります。 以下の機能は、発行操作と起動操作のパフォーマンスに影響を与える可能性があります。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ステップ</th>
<th align="left">考慮事項</th>
<th align="left">メリット</th>
<th align="left">オフ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>機能ブロック 1 (FB1、プライマリ FB とも呼ばれます) がありません</p></td>
<td align="left"><p>FB1 なしは、アプリがすぐに起動し、ストリームフォールトを発生させることを意味します (アプリケーションはファイル、DLL を要求し、起動時にネットワーク経由でプルダウンする必要があります)。ネットワークの制限事項がある場合は、FB1 は次のようになります。</p>
<ul>
<li><p>初めてアプリケーションを起動するときに使用されるストリームフォールトとネットワーク帯域幅の数を減らします。</p></li>
<li><p>FB1 全体がストリーミングされるまで、起動を遅らせます。</p></li>
</ul></td>
<td align="left"><p>ストリームの障害が発生すると、起動時間が短縮されます。</p></td>
<td align="left"><p>FB1 が構成されている仮想アプリケーションパッケージは、再順序付けする必要があります。</p></td>
</tr>
</tbody>
</table>



### FB1 を削除する

FB1 を削除しても、元のアプリケーションインストーラーは必要ありません。 次の手順を完了したら、sequencer を実行しているコンピューターをクリーンなスナップショットに戻すことをお勧めします。

**SEQUENCER UI** -新しい仮想アプリケーションパッケージを作成します。

1.  シーケンスの手順を完了して、ストリーミングをカスタマイズし &gt; ます。

2.  ストリーミング手順では、[**低速または信頼性の低いネットワーク経由の展開用にパッケージを最適化する**] を選択しないでください。

3.  必要に応じて、[**ターゲット OS**] に移動します。

**既存の仮想アプリケーションパッケージを変更する**

1.  シーケンス手順を完了してストリーミングを行います。

2.  [パッケージを**低速または信頼性の低いネットワーク経由で展開するために最適化**する] を選択しないでください。

3.  「**パッケージの作成**」に移動します。

**PowerShell** -既存の仮想アプリケーションパッケージを更新します。

1.  管理者特権の PowerShell セッションを開きます。

2.  インポート-モジュール**appvsequencer**。

3.  **更新-AppvSequencerPackage**  - **AppvPackageFilePath**

    "C:\\Packages\\MyPackage.appv"-インストーラ

    "C:\\PackageInstall\\PackageUpgrade.exe empty.exe"-OutputPath

    "C:\\UpgradedPackages"

    **注**  
    このコマンドレットを実行するには、実行可能ファイル (.exe) またはバッチファイル (.bat) が必要です。 空の (何もしない) 実行可能ファイルまたはバッチファイルを指定する必要があります。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ステップ</th>
<th align="left">考慮事項</th>
<th align="left">メリット</th>
<th align="left">オフ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>公開時に SXS はインストールされません (インストール前の SxS アセンブリ)</p></td>
<td align="left"><p>仮想アプリケーションパッケージの順序を変更する必要はありません。 SxS アセンブリは仮想アプリケーションパッケージに残しておくことができます。</p></td>
<td align="left"><p>SxS アセンブリの依存関係は、公開時にはインストールされません。</p></td>
<td align="left"><p>SxS アセンブリの依存関係が事前にインストールされている必要があります。</p></td>
</tr>
</tbody>
</table>



### Sequencer での新しい仮想アプリケーションパッケージの作成

Sequencer の監視中に、プログラムのインストールの一部として SxS アセンブリ (VC + + ランタイムなど) がインストールされている場合、SxS アセンブリは自動的に検出され、パッケージに含まれます。 管理者に通知され、SxS アセンブリを除外するオプションが表示されます。

**クライアント側**:

仮想アプリケーションパッケージを公開する場合、必要な SxS の依存関係が既にインストールされているかどうかが、App-v 5.0 SP2 クライアントによって検出されます。 この依存関係がコンピューターで利用できず、パッケージに含まれている場合は、従来の Windows インストーラー (.**msi**) SxS アセンブリのインストールが開始されます。 前に説明したように、クライアントを実行しているコンピューターに依存関係をインストールするだけで、Windows Installer (.msi) のインストールが行われないようにします。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ステップ</th>
<th align="left">考慮事項</th>
<th align="left">メリット</th>
<th align="left">オフ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>動的構成ファイルを選択的に使用する</p></td>
<td align="left"><p>App-v 5.0 クライアントは、これらの動的構成ファイルを解析して処理する必要があります。</p>
<p>ファイルのサイズと複雑さ (スクリプトの実行、VREG の包含/除外) について認識している必要があります。</p>
<p>多くの仮想アプリケーションパッケージには、ユーザーまたはコンピューター固有の動的構成ファイルが既に含まれている場合があります。</p></td>
<td align="left"><p>これらのファイルが選択されているかどうかによって、公開時間が向上します。</p></td>
<td align="left"><p>仮想アプリケーションパッケージは、個別に再構成する必要があります。または、App-v server 管理コンソールを使用して、関連付けられた動的構成ファイルを削除する必要があります。</p></td>
</tr>
</tbody>
</table>



### Powershell を使用した動的構成の無効化

-   既に公開されているパッケージ `Set-AppVClientPackage –Name Myapp –Path c:\Packages\Apps\MyApp.appv` の場合は、

    **-Dynamicdeploymentconfiguration**パラメーター

-   同様に、を使って新しいパッケージを追加する場合は、 `Add-AppVClientPackage –Path c:\Packages\Apps\MyApp.appv`

    **-Dynamicdeploymentconfiguration**パラメーター。

動的な構成を適用する方法については、以下を参照してください。

-   [PowerShell を使用してユーザー構成ファイルを適用する方法](how-to-apply-the-user-configuration-file-by-using-powershell.md)

-   [PowerShell を使用して展開構成ファイルを適用する方法](how-to-apply-the-deployment-configuration-file-by-using-powershell.md)

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ステップ</th>
<th align="left">考慮事項</th>
<th align="left">メリット</th>
<th align="left">オフ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>パッケージのライフサイクル中の同期スクリプト実行のアカウント。</p></td>
<td align="left"><p>スクリプトの資料がパッケージに埋め込まれている場合、Add (Powershell) の速度が大幅に低下することがあります。</p>
<p>仮想アプリケーションの起動時 (StartVirtualEnvironment、StartProcess)、または Add + Publish の間にスクリプトを実行すると、このようなライフサイクル操作の1つ以上で、認識されるパフォーマンスに影響します。</p></td>
<td align="left"><p>非同期 (非ブロッキング) スクリプトを使用すると、ライフサイクルの操作が効率的に完了します。</p></td>
<td align="left"><p>この手順には、関連付けられた動的構成ファイルを持ち、同期されている参照と実行を行う埋め込みスクリプトの資料を含む、すべての仮想アプリケーションパッケージについての実用的な知識が必要です。</p></td>
</tr>
<tr class="even">
<td align="left"><p>パッケージから余分な仮想フォントを削除します。</p></td>
<td align="left"><p>App-v 製品チームによって調査されたアプリケーションの大半は、少数のフォント (通常は20未満) を含んでいました。</p></td>
<td align="left"><p>仮想フォントは、公開の更新のパフォーマンスに影響します。</p></td>
<td align="left"><p>目的のフォントは、ネイティブで有効またはインストールする必要があります。 手順については、「フォントをインストールまたはアンインストールする」を参照してください。</p></td>
</tr>
</tbody>
</table>



### パッケージ内に存在する仮想フォントを確認する

-   パッケージのコピーを作成します。

-   パッケージ \ _copy を Package\_copy.zip に名前変更する

-   AppxManifest.xml を開き、次の内容を探します。

    &lt;appv: 拡張機能カテゴリ = "AppV. Fonts"&gt;

    &lt;appv: フォント&gt;

    &lt;appv: Font Path = "\ [{Fonts} \] \\private\\CalibriL.ttf" DelayLoad = "true" &gt; &lt; /Appv: font&gt;

    **注**  
    **Delayload**としてマークされているフォントがある場合は、最初の起動に影響しません。



~~~
&lt;/appv:Fonts&gt;
~~~

### パッケージから仮想フォントを除外する

ユーザーのスコープに最適な動的構成ファイルを使用します。コンピューター上のすべてのユーザーに対する展開構成、特定のユーザーまたはユーザー向けのユーザー構成。

-   展開またはユーザー構成でフォントを無効にします。

フォント

--&gt;

&lt;フォント有効 = "false"/&gt;

&lt;!--

## <a href="" id="bkmk-terms1"></a> App-v 5.0 のパフォーマンスガイダンスの用語


次の用語は、App-v 5.0 パフォーマンスの最適化に関する概念とアクションを記述するときに使われます。

-   **複雑さ**–事前構成 (**AppvClientPackage**) または統合 (**Publish-AppvClientPackage**) の実行中にパフォーマンスに影響を与える可能性のある1つ以上のパッケージの特性を指します。 特性の例としては、マニフェストのサイズ、仮想フォントの数、ファイルの数などがあります。

-   **統合の解除**–ユーザー統合を削除します

-   **再統合**–ユーザー統合を適用します。

-   **非永続的なプール**–仮想環境がログインするたびに実行されるコンピューターを作成します。

-   **永続的なパーソナル**–すべてのログインで同じ仮想環境を実行しているコンピューター。

-   **ステートフル**-このドキュメントでは、ユーザーの統合がセッション間で保持され、ユーザー環境管理テクノロジが永続的でない RDSH または VDI と併用されていることを意味します。

-   **ステートレス**–セッション間でユーザーの状態が保持されないシナリオを表します。

-   **トリガー** – (またはネイティブアクショントリガー)。 UPM では、これらの種類のトリガーを使って、監視または同期操作を開始します。

-   **ユーザーエクスペリエンス**-app-v 5.0 のコンテキストでは、ユーザーエクスペリエンス quantitatively は次の部分の合計です。

    -   ユーザーがログインを開始した時点から、ユーザーがデスクトップを操作できる場合。

    -   App-v 5.0 full server インフラストラクチャを使用しているときに、デスクトップが対話できるポイント (PowerShell 用語では、同期) が開始されます。 スタンドアロンインスタンスでは、 **AppVClientPackage**と**Publish AppVClientPackage Powershell**コマンドが開始されたときに実行されます。

    -   公開の更新の開始から完了まで。 スタンドアロンインスタンスの場合、これは最初に最後に公開された仮想アプリケーションです。

    -   仮想アプリケーションをショートカットから起動できる場所に移動します。 または、ファイルの種類の関連付けが登録されている時点から、指定された仮想アプリケーションを起動します。

-   **ユーザープロファイル管理**–環境に関連付けられているユーザーコンポーネントを管理するための制御された構造のアプローチです。 たとえば、ユーザープロファイル、基本設定とポリシーの管理、アプリケーションコントロール、アプリケーションの展開などです。 スクリプトまたはサードパーティのソリューションを使用して、必要に応じて環境を構成することができます。






## 関連トピック


[Microsoft Application Virtualization 5.0 管理者ガイド](microsoft-application-virtualization-50-administrators-guide.md)









