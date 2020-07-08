---
title: Microsoft User Experience Virtualization (UE-V) 2.1 リリース ノート
description: Microsoft User Experience Virtualization (UE-V) 2.1 リリース ノート
author: dansimp
ms.assetid: 79a36c77-fa0c-4651-8028-4a79763a2fd2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0677dda93f2c2dc60ec627ae0c3f4bd8c199db6c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825277"
---
# Microsoft User Experience Virtualization (UE-V) 2.1 リリース ノート


Microsoft User Experience Virtualization (UE-V) 2.0 のリリースノートを検索するには、Ctrl キーを押しながら F キーを押します。

UE-V をインストールする前に、これらのリリースノートを完全に読む必要があります。 リリースノートには、ユーザーエクスペリエンスの仮想化を正常にインストールするために必要な情報や、製品のドキュメントに記載されていない追加情報が含まれています。 これらのリリースノートと他の UE-V ドキュメントの違いがある場合は、最新の変更を、権威を持つものとして扱う必要があります。 これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。

## フィードバックの提供


フィードバックとコメントを提供して、MDOP のドキュメントについてご意見をお寄せください。 ドキュメントのフィードバックを[mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation)に送信します。

## UE-V の既知の問題


このセクションには、ユーザーエクスペリエンスの仮想化のリリースノートが含まれています。

### Skype の UE-V 設定場所テンプレート skype がクラッシュする原因

ユーザーが Skype デスクトップアプリケーション用に有効な設定場所テンプレートを生成し、それを登録して、skype デスクトップアプリケーションを起動すると、Skype がクラッシュします。 ACCESS \ _VIOLATION は、アプリケーションイベントログに記録されます。

回避策: skype のテンプレートを削除するか、登録を解除して、Skype を再び使用できるようにします。

### UE-V のサイレントインストール用の既存のスクリプトが失敗することがある

UE-V インストーラーに対して2つの変更を行うと、UE-V 2.1 をインストールするときに、以前のバージョンの UE-V で動作していたサイレントインストールスクリプトが失敗する可能性があります。 1つ目は、サイレントインストール中でも、ユーザーがライセンス条項に同意し、カスタマーエクスペリエンス向上プログラム (CEIP) への参加を承諾または拒否する必要がある新しい要件です。 /Q パラメーターを使用すると、CEIP に参加するためのライセンス条項とライセンス契約の同意を示す必要がなくなります。

次に、UE-V エージェントをインストールした後、インストーラーによってコンピューターが強制的に再起動されるようになりました。 このため、再起動が想定されていない場合は、インストールスクリプトが失敗する可能性があります (たとえば、最初に UE-V Agent をインストールしてから、すぐにジェネレーターをインストールします)。

回避策: UE-V installer (.msi) には、サイレントインストールをサポートする2つの新しいコマンドラインパラメーターがあります。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">パラメーター</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>/Acceptlicenseterms = True</strong></p></td>
<td align="left"><p><strong>Ue-v をサイレントインストールするには、このパラメーターを True に設定 </strong> します。 このパラメーターを追加すると、ユーザーは UE-V ライセンス条項 (既定で) を受け取ることになります。%ProgramFiles%\Microsoft User Experience Virtualization\Agent</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>/NORESTART</strong></p></td>
<td align="left"><p>このパラメーターを指定すると、UE-V エージェントをインストールした後に、必須の再起動が行われません。 リターンコード3010は、UE-V を使う前に再起動が必要であることを示します。</p></td>
</tr>
</tbody>
</table>

 

### 同じコンピューター上の App-v とネイティブアプリケーションの間でレジストリ設定が同期されない

コンピューターに、Application Virtualization (App-v) と Windows Installer (.msi) ファイルを使ってインストールされたアプリケーションがある場合、これらのテクノロジの間でレジストリベースの設定は同期されません。

対応策: この問題を解決するには、2つのテクノロジのどちらか1つを選択してアプリケーションを実行します。両方を選択することはできません。

### Office 2010 と Office 2013 の両方で予期しない結果が表示される

ユーザーに Office 2010 と Office 2013 の両方がインストールされている場合、2つのバージョンの Office 間の一般的な設定は、UE-V によってローミングされます。 このため、Office 2010 パッケージのサイズが大きすぎるか、特に Office 365 が使用されている場合は、予期しない2013との競合が発生する可能性があります。

回避策: いずれかのバージョンの Office をインストールするか、UE-V で同期される設定を制限します。

### Windows 8 アプリをアンインストールして再インストールすると、設定が初期状態に戻ります

Windows 8 アプリで UE-V 設定の同期を使用しているときに、ユーザーがアプリをアンインストールしてから、アプリを再インストールすると、アプリの設定は既定値に戻ります。この問題が発生するのは、アンインストールによってアプリの設定のローカル (キャッシュされた) コピーが削除されますが、ローカルの UE-V 設定パッケージは削除されないためです。アプリを再インストールして起動すると、UE-V は、アプリの既定値にリセットされたアプリの設定を収集し、中央の保存場所に既定の設定をアップロードします。その他のアプリを実行しているコンピューターで、既定の設定をダウンロードします。この動作は、デスクトップアプリケーションの動作と同じです。

回避策: なし。

### UE-V は、32ビット版と64ビット版の Microsoft Office 間でのローミング設定をサポートしていません。

32ビットと64ビットの両方のオペレーティングシステムに対して、32ビット版の Microsoft Office をインストールすることをお勧めします。 必要な Microsoft Office のバージョンを選択するには、ここをクリックします。 ([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)). UE-V は、同じアーキテクチャバージョンの Office 間のローミング設定をサポートしています。 たとえば、32ビット版の office の設定は、すべての32ビット版の Office インスタンス間でローミングされます。 UE-V は、32ビット版と64ビット版の Office 間でのローミング設定をサポートしていません。

回避策: なし

### <a href="" id="msi-s-are-not-localized"></a>MSI がローカライズされていない

UE-V 2.0 には、UE-V Agent と UE-V generator の両方のローカライズされたセットアッププログラムが含まれています。 これらの MSI ファイルは引き続き使用できますが、ユーザーインターフェイスは最小化され、MSI は英語でのみ表示されます。 英語版のファイルにもかかわらず、セットアッププログラムはインストール中にサポートされるすべての言語をインストールします。

回避策: なし

### Internet Explorer 9 のお気に入りに関連付けられている Favicons はローミングされません

Internet Explorer 9 のお気に入りに関連付けられている favicons は、ユーザーエクスペリエンスの仮想化によってローミングされず、新しいコンピューターでお気に入りが最初に表示されたときには表示されません。

回避策: Internet Explorer 9 ブラウザーでブックマークを使用してキャッシュすると、Favicons が関連するお気に入りと共に表示されます。

### ファイル設定のパスはレジストリに保存される

一部のアプリケーション設定では、構成ファイルと設定ファイルのパスがレジストリの値として格納されています。 設定がコンピューター間でローミングするときに、レジストリでパスとして参照されているファイルを同期する必要があります。

回避策: フォルダーリダイレクションまたはその他の技術を使用して、ファイル設定パスとして参照されているすべてのファイルが、設定をローミングするすべてのコンピューターの同じ場所に配置されていることを確認します。

### 長い設定の記憶域のパスでエラーが発生することがある

設定のストレージパスをできるだけ短くします。 長いパスを使えば、解決や同期ができなくなることがあります。 UE-V は、設定を保存するための計算パスの一部として、設定の記憶域パスを使用します。 このパスは次のように計算されます。設定の保存パス + "settingspackages" + パッケージディレクトリ (テンプレート ID) + パッケージ名 (テンプレート ID) と pkgx。 この計算パスが260文字を超える場合、パッケージストレージは失敗し、UE-V の操作イベントログで次のエラーメッセージが生成されます。

`[boost::filesystem::copy_file: The system cannot find the path specified]`

操作ログイベントを確認するには、イベントビューアーを開き、[アプリケーションとサービスログ]、[Microsoft/ユーザーエクスペリエンスの仮想化/ログ/運用] の順に移動します。

回避策: なし。

### 一部のオペレーティングシステム設定は、同じバージョンのオペレーティングシステム間でのみローミングします。

ナレーターのオペレーティングシステム設定と、ロケールに固有の通貨文字 (言語と地域の設定など) は、オペレーティングシステムバージョンの Windows と同じようにローミングされます。 たとえば、Windows 7 と Windows 8 の間では、通貨文字はローミングされません。

回避策: なし

### <a href="" id="ue-v-1-agent-generates-errors-when-running-ue-v-2-templates-"></a>Ue-v 2 テンプレートを実行しているときに UE-V 1 agent がエラーを生成する

Ue-v 2 設定の場所テンプレートが UE-V 1 エージェントと共にインストールされたコンピューターに配布されている場合、一部の設定はコンピューター間で同期されず、エージェントはイベントログのエラーを報告します。

回避策: UE-V 1 から UE-V 2 に移行するときに、以前のバージョンのエージェントを実行しているコンピューターが存在する可能性がある場合は、ue-v 2.0 エージェントとテンプレートをサポートするために、別の UE-V 2.0 カタログを作成します。

## UE-V 2.1 の修正プログラムとサポート技術情報の記事


このセクションには、UE-V 2.1 の修正プログラムとサポート技術情報の記事が含まれています。

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
<td align="left"><p>3018608</p></td>
<td align="left"><p>Ue-v WMI クラスが見つからない場合に、UE-V 2.1-TemplateConsole.exe がクラッシュする</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3018608/EN-US" data-raw-source="[support.microsoft.com/kb/3018608/EN-US](https://support.microsoft.com/kb/3018608/EN-US)">support.microsoft.com/kb/3018608/EN-US</a></p></td>
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
<td align="left"><p>2769631</p></td>
<td align="left"><p>破損した UE-V のインストールを修復する方法</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769631/EN-US" data-raw-source="[support.microsoft.com/kb/2769631/EN-US](https://support.microsoft.com/kb/2769631/EN-US)">support.microsoft.com/kb/2769631/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2850989</p></td>
<td align="left"><p>Microsoft UE-V での MAPI プロファイルの移行はサポートされていません</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850989/EN-US" data-raw-source="[support.microsoft.com/kb/2850989/EN-US](https://support.microsoft.com/kb/2850989/EN-US)">support.microsoft.com/kb/2850989/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2769586</p></td>
<td align="left"><p>UE-V ローミング: 空のフォルダーとレジストリキー</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769586/EN-US" data-raw-source="[support.microsoft.com/kb/2769586/EN-US](https://support.microsoft.com/kb/2769586/EN-US)">support.microsoft.com/kb/2769586/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2782997</p></td>
<td align="left"><p>Microsoft User Experience Virtualization (UE-V) でデバッグログを有効にする方法</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2782997/EN-US" data-raw-source="[support.microsoft.com/kb/2782997/EN-US](https://support.microsoft.com/kb/2782997/EN-US)">support.microsoft.com/kb/2782997/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2769570</p></td>
<td align="left"><p>UE-V で RDS または VDI セッションのテーマが更新されない</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769570/EN-US" data-raw-source="[support.microsoft.com/kb/2769570/EN-US](https://support.microsoft.com/kb/2769570/EN-US)">support.microsoft.com/kb/2769570/EN-US</a></p></td>
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

 






 

 





