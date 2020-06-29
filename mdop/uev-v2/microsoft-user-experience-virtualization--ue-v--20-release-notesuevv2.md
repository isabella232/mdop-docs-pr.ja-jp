---
title: Microsoft User Experience Virtualization (UE-V) 2.0 リリース ノート
description: Microsoft User Experience Virtualization (UE-V) 2.0 リリース ノート
author: dansimp
ms.assetid: 5ef66cd1-ba2b-4383-9f45-e7cde41f1ba1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ad3deffa5cd567a70711e5447197e630f04ea254
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825284"
---
# Microsoft User Experience Virtualization (UE-V) 2.0 リリース ノート


Microsoft User Experience Virtualization (UE-V) 2.0 のリリースノートを検索するには、Ctrl キーを押しながら F キーを押します。

UE-V をインストールする前に、これらのリリースノートを完全に読む必要があります。 リリースノートには、ユーザーエクスペリエンスの仮想化を正常にインストールするために必要な情報や、製品のドキュメントに記載されていない追加情報が含まれています。 これらのリリースノートと他の UE-V ドキュメントの違いがある場合は、最新の変更を、権威を持つものとして扱う必要があります。 これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。

## フィードバックの提供


フィードバックとコメントを提供して、MDOP のドキュメントについてご意見をお寄せください。 ドキュメントのフィードバックを[mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation)に送信します。

## UE-V の既知の問題


このセクションには、ユーザーエクスペリエンスの仮想化のリリースノートが含まれています。

### 同じコンピューター上の App-v とネイティブアプリケーションの間でレジストリ設定が同期されない

コンピューターに Application Virtualization (App-v) と Windows Installer (.msi) ファイルを使用してローカルにインストールされたアプリケーションがある場合、これらのテクノロジの間でレジストリベースの設定は同期されません。

**回避策:** この問題を解決するには、2つのテクノロジのどちらか1つを選択してアプリケーションを実行します。両方を選択することはできません。

### <a href="" id="settings-do-not-synchronization-when-network-share-is-outside-user-s-domain"></a>ネットワーク共有がユーザーのドメイン外の場合、設定は同期されません。

Windows®8がオペレーティングシステム設定の同期を実行しようとすると、同期が失敗し、次のエラーメッセージが表示されます:**昇格:: filesystem:: 存在:: ユーザー名またはパスワードが正しくありませ**ん。 このエラーは、ネットワーク共有がユーザーのドメインに含まれていないか、またはそのドメインとの信頼関係を持つドメインの外部にあることを示している可能性があります。 操作ログイベントを確認するには、**イベントビューアー**を開き、[**アプリケーションとサービスログ**] に移動し  /  **Microsoft**  /  ます。 Microsoft**User Experience Virtualization**  /  **Logging**  /  **operational** UE-V の設定の保存場所に使用されるネットワーク共有は、ユーザーまたはユーザーのドメインの信頼済みドメインと同じ Active Directory ドメインに存在する必要があります。

**回避策:** ユーザーと同じ Active Directory ドメインのネットワーク共有を使用します。

### Office 2010 と Office 2013 の両方で予期しない結果が表示される

ユーザーに Office 2010 と Office 2013 の両方がインストールされている場合、2つのバージョンの Office 間の一般的な設定は、UE-V によってローミングされます。 このため、Office 2010 パッケージのサイズが大きすぎるか、特に Office 365 が使用されている場合は、予期しない2013との競合が発生する可能性があります。

**回避策:** 1つのバージョンの Office のみをインストールするか、UE-V で同期される設定を制限します。

### Windows 8 アプリをアンインストールして再インストールすると、設定が初期状態に戻ります

Windows 8 アプリで UE-V 設定の同期を使用しているときに、ユーザーがアプリをアンインストールしてから、アプリを再インストールすると、アプリの設定は既定値に戻ります。この問題が発生するのは、アンインストールによってアプリの設定のローカル (キャッシュされた) コピーが削除されますが、ローカルの UE-V 設定パッケージは削除されないためです。アプリを再インストールして起動すると、UE-V は、アプリの既定値にリセットされたアプリの設定を収集し、中央の保存場所に既定の設定をアップロードします。その他のアプリを実行しているコンピューターで、既定の設定をダウンロードします。この動作は、デスクトップアプリケーションの動作と同じです。

**回避策:**-.

### Outlook 2010 のメール署名のローミング

UE-V は、Outlook 2010 の署名ファイルをデバイス間でローミングします。 ただし、新しいメッセージ、返信、転送の既定の署名オプションは同期されません。 この2つの設定は Outlook プロファイルに保存され、UE-V はローミングしません。

**回避策:**-.

### UE-V は、32ビット版と64ビット版の Microsoft Office 間でのローミング設定をサポートしていません。

最新のコンピューターには、64ビット版の Microsoft Office をインストールすることをお勧めします。 必要なバージョンを特定するには、[ここをクリック](https://support.office.com/article/choose-between-the-64-bit-or-32-bit-version-of-office-2dee7807-8f95-4d0c-b5fe-6c6f49b8d261?ui=en-US&rs=en-US&ad=US#32or64Bit=Newer_Versions)します。 UE-V は、同じアーキテクチャバージョンの Office 間のローミング設定をサポートしています。 たとえば、32ビット版の office の設定は、すべての32ビット版の Office インスタンス間でローミングされます。 UE-V は、32ビット版と64ビット版の Office 間でのローミング設定をサポートしていません。

**回避策:**-

### <a href="" id="msi-s-are-not-localized"></a>MSI がローカライズされていない

UE-V 2.0 には、UE-V Agent と UE-V generator の両方のローカライズされたセットアッププログラムが含まれています。 これらの MSI ファイルは引き続き使用できますが、ユーザーインターフェイスは最小化され、MSI は英語でのみ表示されます。 英語版のファイルにもかかわらず、セットアッププログラムはインストール中にサポートされるすべての言語をインストールします。

**回避策:**-

### Internet Explorer 9 のお気に入りに関連付けられている Favicons はローミングされません

Internet Explorer 9 のお気に入りに関連付けられている favicons は、ユーザーエクスペリエンスの仮想化によってローミングされず、新しいコンピューターでお気に入りが最初に表示されたときには表示されません。

**回避策:** ブックマークを使用して Internet Explorer 9 ブラウザーでキャッシュすると、Favicons に関連付けられたお気に入りが表示されます。

### ファイル設定のパスはレジストリに保存される

一部のアプリケーション設定では、構成ファイルと設定ファイルのパスがレジストリの値として格納されています。 設定がコンピューター間でローミングするときに、レジストリでパスとして参照されているファイルを同期する必要があります。

**回避策:** フォルダーリダイレクションなどの技術を使用して、ファイル設定パスとして参照されているすべてのファイルが、設定をローミングするすべてのコンピューターで同じ場所に配置されるようにします。

### 長い設定の記憶域のパスでエラーが発生することがある

設定のストレージパスをできるだけ短くします。 長いパスを使えば、解決や同期ができなくなることがあります。 UE-V は、設定を保存するための計算パスの一部として、設定の記憶域パスを使用します。 このパスは次のように計算されます。設定の保存パス + "settingspackages" + パッケージディレクトリ (テンプレート ID) + パッケージ名 (テンプレート ID) と pkgx。 この計算パスが260文字を超える場合、パッケージストレージは失敗し、UE-V の操作イベントログで次のエラーメッセージが生成されます。

`[boost::filesystem::copy_file: The system cannot find the path specified]`

操作ログイベントを確認するには、イベントビューアーを開き、[アプリケーションとサービスログ]、[Microsoft/ユーザーエクスペリエンスの仮想化/ログ/運用] の順に移動します。

**回避策:**-.

### 一部のオペレーティングシステム設定は、同じバージョンのオペレーティングシステム間でのみローミングします。

ナレーターのオペレーティングシステム設定と、ロケールに固有の通貨文字 (言語と地域の設定など) は、オペレーティングシステムバージョンの Windows と同じようにローミングされます。 たとえば、Windows 7 と Windows 8 の間では、通貨文字はローミングされません。

**回避策:**-

### Windows 8 アプリが予期せずに終了した後にアプリを再起動したときに、設定が同期されない

起動後に Windows 8 アプリが予期せずに終了した場合、アプリケーションを再起動すると、アプリケーションの設定が同期されないことがあります。

**回避策:** Windows 8 アプリを閉じ、UevAppMonitor.exe アプリケーションを終了して再起動し (TaskManager を使用)、Windows 8 アプリを再起動します。

### <a href="" id="ue-v-1-agent-generates-errors-when-running-ue-v-2-templates-"></a>Ue-v 2 テンプレートを実行しているときに UE-V 1 agent がエラーを生成する

Ue-v 2 設定の場所テンプレートが UE-V 1 エージェントと共にインストールされたコンピューターに配布されている場合、一部の設定はコンピューター間で同期されず、エージェントはイベントログのエラーを報告します。

**回避策:** UE-V 1 から UE-V 2 に移行するときに、以前のバージョンのエージェントを実行しているコンピューターが存在する可能性がある場合は、ue-v 2.0 エージェントとテンプレートをサポートするために、個別の UE-V 2.0 カタログを作成します。

## UE-V 2.0 の修正プログラムとサポート技術情報の記事


このセクションには、UE-V 2.0 の修正プログラムとサポート技術情報の記事が含まれています。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>サポート技術情報の記事</strong></th>
<th align="left">タイトル</th>
<th align="left"><strong>リンク</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>2927019</p></td>
<td align="left"><p>Microsoft User Experience Virtualization 2.0 の修正プログラムパッケージ1</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2927019" data-raw-source="[support.microsoft.com/kb/2927019](https://support.microsoft.com/kb/2927019)">support.microsoft.com/kb/2927019</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2903501</p></td>
<td align="left"><p>UE-V: user Experience Virtualization (UE-V) ユーザープロファイルとの互換性</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2903501/EN-US" data-raw-source="[support.microsoft.com/kb/2903501/EN-US](https://support.microsoft.com/kb/2903501/EN-US)">support.microsoft.com/kb/2903501/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2770042</p></td>
<td align="left"><p>UE-V のレジストリ設定</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2770042/EN-US" data-raw-source="[support.microsoft.com/kb/2770042/EN-US](https://support.microsoft.com/kb/2770042/EN-US)">support.microsoft.com/kb/2770042/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2847017</p></td>
<td align="left"><p>Internet Explorer によってレプリケートされた UE-V の設定</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2847017/EN-US" data-raw-source="[support.microsoft.com/kb/2847017/EN-US](https://support.microsoft.com/kb/2847017/EN-US)">support.microsoft.com/kb/2847017/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2930271</p></td>
<td align="left"><p>Microsoft UE-V でのローミング Outlook 署名の制限事項について</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2930271/EN-US" data-raw-source="[support.microsoft.com/kb/2930271/EN-US](https://support.microsoft.com/kb/2930271/EN-US)">support.microsoft.com/kb/2930271/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2769631</p></td>
<td align="left"><p>破損した UE-V のインストールを修復する方法</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769631/EN-US" data-raw-source="[support.microsoft.com/kb/2769631/EN-US](https://support.microsoft.com/kb/2769631/EN-US)">support.microsoft.com/kb/2769631/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2850989</p></td>
<td align="left"><p>Microsoft UE-V での MAPI プロファイルの移行はサポートされていません</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850989/EN-US" data-raw-source="[support.microsoft.com/kb/2850989/EN-US](https://support.microsoft.com/kb/2850989/EN-US)">support.microsoft.com/kb/2850989/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2769586</p></td>
<td align="left"><p>UE-V ローミング: 空のフォルダーとレジストリキー</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769586/EN-US" data-raw-source="[support.microsoft.com/kb/2769586/EN-US](https://support.microsoft.com/kb/2769586/EN-US)">support.microsoft.com/kb/2769586/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2782997</p></td>
<td align="left"><p>Microsoft User Experience Virtualization (UE-V) でデバッグログを有効にする方法</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2782997/EN-US" data-raw-source="[support.microsoft.com/kb/2782997/EN-US](https://support.microsoft.com/kb/2782997/EN-US)">support.microsoft.com/kb/2782997/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2769570</p></td>
<td align="left"><p>UE-V で RDS または VDI セッションのテーマが更新されない</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769570/EN-US" data-raw-source="[support.microsoft.com/kb/2769570/EN-US](https://support.microsoft.com/kb/2769570/EN-US)">support.microsoft.com/kb/2769570/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2901856</p></td>
<td align="left"><p>UE-V を有効にしているコンピューターで再起動すると、アプリケーションの設定が同期されない</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2901856/EN-US" data-raw-source="[support.microsoft.com/kb/2901856/EN-US](https://support.microsoft.com/kb/2901856/EN-US)">support.microsoft.com/kb/2901856/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2850582</p></td>
<td align="left"><p>App-v アプリケーションで Microsoft ユーザーエクスペリエンス仮想化を使用する方法</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850582/EN-US" data-raw-source="[support.microsoft.com/kb/2850582/EN-US](https://support.microsoft.com/kb/2850582/EN-US)">support.microsoft.com/kb/2850582/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>3041879</p></td>
<td align="left"><p>Microsoft User Experience Virtualization の現在のファイルバージョン</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3041879/EN-US" data-raw-source="[support.microsoft.com/kb/3041879/EN-US](https://support.microsoft.com/kb/3041879/EN-US)">support.microsoft.com/kb/3041879/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2843592</p></td>
<td align="left"><p>ユーザーエクスペリエンスの仮想化と高可用性に関する情報</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2843592/EN-US" data-raw-source="[support.microsoft.com/kb/2843592/EN-US](https://support.microsoft.com/kb/2843592/EN-US)">support.microsoft.com/kb/2843592/EN-US</a></p></td>
</tr>
</tbody>
</table>

 

 

 





