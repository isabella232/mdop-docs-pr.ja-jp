---
title: Microsoft Application Virtualization Management System のリリースノート
description: Microsoft Application Virtualization Management System のリリースノート
author: dansimp
ms.assetid: e1a4d5ee-53c7-4b48-814c-a34ce0e698dc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c34abab9a49bd69f760a9b531d0950cc581253c1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816164"
---
# Microsoft Application Virtualization Management System のリリースノート


これらのリリースノートを検索するには、CTRL キーを押しながら F キーを押します。

**重要** アプリケーションの仮想化管理システムをインストールする前に、これらのリリースノートをよくお読みください。 これらのリリースノートには、Application Virtualization 管理システムを正常にインストールするために必要な情報が含まれています。 このドキュメントには、製品のドキュメントでは利用できない情報が含まれています。 これらのリリースノートとその他の Application Virtualization 管理システムのドキュメントの間に不一致がある場合は、最新の変更を、権限のあるものと見なす必要があります。 これらのリリースノートは、この製品に含まれているコンテンツに置き換わるものです。

 

既知の問題に関する最新情報については、Microsoft TechNet ライブラリのを参照してください <https://go.microsoft.com/fwlink/?LinkId=122918> 。

## Microsoft Application Virtualization 4.5 累積更新プログラムについて1


これらのリリースノートは、Microsoft Application Virtualization 4.5 累積的な Update1 (app-v 4.5 CU1) で導入された変更を反映するように更新されています。これは、Application Virtualization (App-v) 4.5 の最新の更新プログラムを提供します。 この累積的な更新プログラムには、次の変更が含まれています。

-   Windows7 ベータ版と Windows Server2008R2 ベータ版のサポート: App-V 4.5 CU1 では、Windows7 ベータ版と Windows Server2008R2 ベータ版との互換性の問題に対処しています。 Windows7 のプレ RTM バージョンのテスト環境では、CU1 が実行されていないことを示すブロックの問題についてサポートが提供されます。 これにより、アプリの Hyper-v 4.5 クライアントと Windows7 ベータの間の互換性が必要なテスト環境で仮想アプリケーションを正常に実行できることを確認できます。

    **重要** ライブオペレーティング環境の任意のバージョンの Windows7 または Windows Server2008R2 での CU1 の実行はサポートされていません。

     

-   .NET Framework のシーケンス処理のサポートが改善されました: App-v 4.5 CU1 は、.NET Framework 3.5 以前のバージョンでは、WindowsXP (SP2 以降) でのシーケンスの問題に対応しています。 新機能の詳細については、TechNet の記事を参照してください <https://go.microsoft.com/fwlink/?LinkId=123412> 。

-   カスタマーフィードバックと修正プログラムのロールアップ: アプリ-V 4.5 CU1 には、app-v 4.5 RTM リリース以降に見つかった問題に対処するための修正プログラムが含まれています。 これには、既知の問題と、社内チーム、パートナー、および App-v 4.5 を使用しているお客様からのお客様からのフィードバックの組み合わせが含まれます。 含まれている更新プログラムの完全な一覧については、のサポート技術情報の記事を参照してください <https://go.microsoft.com/fwlink/?LinkId=141258> 。

## 製品ドキュメントについて


Application Virtualization (app-v) の包括的なドキュメントは、Microsoft TechNet の Application Virtualization (App-v) TechCenter で入手でき <https://go.microsoft.com/fwlink/?LinkId=122939> ます。 TechNet のドキュメントには、Application Virtualization Sequencer、Application Virtualization クライアント、Application Virtualization Server のオンラインヘルプが含まれています。 また、Application Virtualization Planning and Deployment Guide と Application Virtualization 運用ガイドも含まれています。

## セキュリティの脆弱性とウイルスから保護する


セキュリティの脆弱性やウイルスから保護するために、インストールされている新しいソフトウェアに使用できる最新のセキュリティ更新プログラムをインストールすることが重要です。 詳細については、Microsoft セキュリティ Web サイトを参照してください <https://go.microsoft.com/fwlink/?LinkId=3482> 。

## フィードバックの提供


Microsoft application virtualization TechCenter () のコミュニティフォーラムを通じて、フィードバックを提供したり、提案を行ったり、問題を報告したりすることができ <https://go.microsoft.com/fwlink/?LinkId=122917> ます。

ドキュメントについてのフィードバックは、App-v ドキュメントチームに直接提供することもできます。 ドキュメントのフィードバックを appvdocs@microsoft.com に送信します。

## Application Virtualization 4.5 CU1 の既知の問題


このセクションでは、Microsoft Application Virtualization (App-v) 4.5 CU1 の問題に関する最新情報について説明します。 これらの問題は製品ドキュメントには記載されていないため、場合によっては、既存の製品ドキュメントに矛盾が生じることがあります。 この問題は、可能な限り将来のリリースで解決されます。

### setup.msi を使用してクライアントをアプリにインストールまたはアップグレードするためのガイダンス CU1

setup.msi を使用して app-v クライアントを App-v 4.5 CU1 にインストールまたはアップグレードする場合、前提条件は自動的にインストールされません。

回避策いただけは、App-v クライアントを 4.5 CU1 にインストールまたはアップグレードする前に、前提条件を手動でインストールする必要があります。 前提条件と App-v クライアントをインストールするための詳細な手順については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=144106> 。

この操作が完了したら、昇格された権限を持つ setup.msi を使用して、App V 4.5 CU1 クライアントをインストールします。 このファイルは、インストーラ \ クライアントフォルダの App-v CU1 release メディアで入手できます。

Microsoft アプリケーションエラー報告をインストールするときに、アプリ-V 4.5 CU1 デスクトップクライアントをインストールまたはアップグレードする場合は、次のコマンドを使用します。

    msiexec /i dw20shared.msi APPGUID={FE495DBC-6D42-4698-B61F-86E655E0796D}  allusers=1 reboot=suppress REINSTALL=all REINSTALLMODE=vomus

または、App-v 4.5 CU1 ターミナルサービスクライアントをインストールまたはアップグレードする場合は、次のコマンドを使用します。

    msiexec /i dw20shared.msi APPGUID={8A97C241-D92A-47DC-B360-E716C1AAA929} allusers=1 reboot=suppress REINSTALL=all REINSTALLMODE=vomus

**注** APPGUID パラメーターは、インストールまたはアップグレードする App-v クライアントの製品コードを参照します。 製品コードは setup.msi ごとに固有です。 Orca データベースエディターまたは同様のツールを使用して、Windows インストーラファイルを調査し、製品コードを確認することができます。 この手順は、すべてのインストールまたは App-v 4.5 CU1 へのアップグレードのために必要です。

 

### <a href="" id="some-applications-might-fail-to-install-during-the-monitoring-phase-when-sequencing-on-windows-7-beta--"></a>Windows7 ベータ版でシーケンス処理を行うときに、一部のアプリケーションが監視フェーズ中にインストールに失敗する場合がある

Windows7 ベータまたは Windows Installer 5.0 を搭載したコンピューターでシーケンスを実行している場合、監視フェーズ中に一部のアプリケーションがインストールに失敗することがあります。

回避策いただけでは、Everyone グループに次のレジストリキーへのフルコントロールのアクセス許可を手動で与える必要があります。

    HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\SystemGuard

**重要** [このオブジェクトの親から継承可能なアクセス許可を含める] オプションを設定するには、 **[詳細設定**] ボタンを使用する必要があります。

 

### Windows7 ベータ版でシーケンス処理中にパッケージを保存できない

Windows7 ベータ版でシーケンスを実行している場合、共有違反のため、シーケンス処理されたパッケージを保存できない場合があります。

WORKAROUNDAs Microsoft Application Virtualization 4.5 シーケンスガイドの [ベストプラクティス] セクションで指定されています (「」を参照してください <https://go.microsoft.com/fwlink/?LinkId=144108> )。シーケンスを開始する前に、次のソフトウェアプログラムをシャットダウンして無効にする必要があります。

-   Windows Defender

-   ウイルス対策ソフトウェア

-   ディスクの最適化ソフトウェア

-   Windows Search

-   開いている Windows エクスプローラーセッション

また、シーケンスステーションで Microsoft Update を実行していて、パッケージの更新プロセス中に更新プログラムをキャプチャしている場合は、シーケンスを開始する前に、VFS の除外として "C:\\Windows\\SoftwareDistribution" を追加する必要があります。

### .NET Framework をシーケンス処理するときのパフォーマンスを向上させる

.NET Framework のシーケンスを行うときに、Microsoft .NET Framework NGEN サービスがバックグラウンドタスクとしてアセンブリをプリコンパイルしようとするため、システムのパフォーマンスが低下することがあります。

WORKAROUNDWhen の順序付け .NET Framework では、監視フェーズを完了した後で、Microsoft .NET Framework NGEN サービス (mscorsvw.exe) を無効にします。 Sequencer で [**仮想サービス**] タブを使用し、スタートアップの種類を [無効] に変更する必要があります。

### Windows7 タスクバーの相互運用性に関する問題

Windows7 で Application Virtualization クライアントを実行した場合、Windows7 タスクバーでは、仮想アプリケーションの複数のインスタンスが1つのタスクバーボタンに折りたたまれることはありません。 さらに、アプリケーションが Windows7 タスクバーにピン留めされていない場合は、仮想アプリケーションのタスクバーボタンを右クリックしても、ジャンプリストは表示されません。

### Microsoft Application Virtualization クライアントをアンインストールすると、アンインストールを実行したユーザーに関連付けられているユーザー設定は削除されます。

Microsoft Application Virtualization クライアントをアンインストールすると、Windows インストーラーによって、現在のユーザーのプロファイルから Application Virtualization の設定が削除されます。 コンピューターでローミングプロファイルを使用している場合は、お使いのコンピューター上の仮想アプリケーションの設定が削除されるため、お客様のパーソナルネットワークアカウントを使用してクライアントをアンインストールしないでください。

回避策いただけは、仮想アプリケーションの実行に使用されない管理者アカウントを使用して、App-v クライアントのアンインストールを実行する必要があります。

### シーケンスウィザードの実行中に、仮想ファイルシステムと仮想レジストリタブで行った編集を保存する必要があります。

アップグレードを実行するためにパッケージを開いた場合、またはシーケンスウィザードを新しいパッケージで既に実行していて、[仮想ファイルシステム] タブまたは [仮想レジストリ] タブでパッケージを変更した場合、これらの変更は自動的に保存されません。

ウィザードを再実行する前に変更を WORKAROUNDSave し、ウィザードの仮想環境に確実に反映されるようにします。

### コマンドラインの Sequencer は、昇格されたコマンドプロンプトから実行する必要があります。

コマンドライン Sequencer を使用しても、昇格のメッセージは表示されません。

昇格されたコマンドプロンプトを使ってコマンドライン Sequencer を WORKAROUNDRun します。

### 分散環境でのサーバー管理コンソールの構成

主要アプリケーション仮想化パブリッシングとストリーミングサーバー以外のシステムに管理コンポーネントをインストールする必要がある場合、サーバーのインストールでは、適切に構成されている場合に、プライマリアプリケーション仮想化サーバーから別のサーバーに管理コンソールと Web サービスをインストールすることがサポートされています。

複数のサーバー間で管理コンポーネントを配布するには、Web サービスがインストールされているサーバーで Kerberos 委任を有効にする必要があります。

### OSD ファイルで短い path 変数名を使うとエラーが発生する場合がある

エラー450478が表示された場合: 1F702339-0000010B "クライアントで仮想アプリケーションを起動すると、OSD の変数が正しく設定されていない可能性があります。 これは、アプリケーションのインストーラーでシーケンス中に短いパス名が設定されている場合に発生する可能性があります。

OSD ファイルに存在する任意の CSIDL 変数から末尾のチルダを WORKAROUNDRemove します。

### <a href="" id="correct-syntax-for-decodepath-parameter-for-command-line-sequencer-"></a>コマンドライン Sequencer の DECODEPATH パラメーターの正しい構文

コマンドライン Sequencer でパッケージを開いて、そのパッケージを Q ドライブのルートにデコードする場合、 *DECODEPATH*パラメーターの構文に末尾のスラッシュを含めることはできません。

回避策いただけでは、 **Q:\\** (末尾の "\ \" 文字を省略します)**を使うこと**ができます。

### <a href="" id="when-upgrading-4-2-packages--you-encounter-problems-caused-by-windows-installer-files-in-the-virtual-file-system-"></a>4.2 パッケージをアップグレードするときに、仮想ファイルシステムの Windows Installer ファイルが原因で問題が発生する

4.2 からパッケージをアップグレードするときに問題が発生する可能性があります。これは、4.2 に既定で含まれていた Windows installer のシステムファイルと、シーケンス用のワークステーションにローカルにインストールされている Windows Installer ライブラリに関連する問題が発生する可能性があります。 次のファイルは、CSIDL \ _SYSTEM \ \ に保存されています。

cabinet.dll

msi.dll

msiexec.exe

msihnd.dll

msimsg.dlll

上記のすべてのファイルをパッケージから WORKAROUNDDelete します。 [ **VFS** ] タブのマッピングと、デコードパスにある CSIDL \ _SYSTEM フォルダー内の実際のファイルを削除します。

### <a href="" id="on-windows-xp--client-install-logging-is-not-enabled-by-default-"></a>WindowsXP では、クライアントのインストールログは既定で有効になっていません。

クライアントをインストールするときに、トラブルシューティングのためにインストールエラーがキャプチャされていることを確認するには、コマンドラインを使用してログを有効にする必要があります。

次の例に示すように、パラメーター */l\ * vx! log.txt*をコマンドラインに WORKAROUNDAdd します。

setup.exe/s/v "/qn/l\ * vx! log.txt "

msiexec.exe/i setup.msi/qn/l\ * vx! log.txt

または、レジストリキーを次の値に設定することもできます。

\ [HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Policies\\Microsoft\\Windows\\Installer\] "Logging" = "voicewarmupx!"

### Kerberos 認証が機能するためには、サービスプリンシパル名 (Spn) が IIS に登録されている必要があります。

IIS 6.0 または 7.0 for the icon または OSD ファイルの取得とストリーミングを使用する場合、Kerberos 認証を有効にするには、Spn を次のように登録する必要があります。

-   IIS サーバーで SETSPN.EXE リソースキットツールを使用して、次のコマンドを実行します。 サーバーの完全修飾ドメイン名 (FQDN) を使用する必要があります。

    Setspn-r SOFTGRID/ &lt; SERVER FQDN&gt;

    Setspn-r HTTP/ &lt; SERVER FQDN&gt;

詳細については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=131407> 。

### RC からアップグレードする場合、クライアントログの既定のアクセス許可では、管理者以外のユーザーがトラブルシューティングとサポートのためにログにアクセスすることは許可されていません。

Application VirtualizationRC クライアントのクライアントログの既定のアクセス許可では、管理者以外の方法でログファイルにアクセスすることはできませんでしたが、これらのログアクセス許可に対する手動の変更は、クライアントが再起動したときに元に戻されました。 これは、新しいクライアントのインストールのために RTM リリースで修正されましたが、RC からアップグレードした場合、既存のログファイルに対するカスタムアクセス許可はリセットされません。 ただし、新しいログが作成された場合、またはログのリセット後に、ファイルに新しい既定のアクセス許可が設定されます。

回避策: アップグレードを実行するか、既存のクライアントログをリセットするか、手動でアクセス許可を変更します。

### .NET の互換性の変更

Microsoft Application Virtualization 累積 Update1 は、WindowsXP (SP2 以降) での .NET Framework のシーケンスをサポートしています。 SoftGrid 4.2 用に記述された .NET アプリケーションのシーケンス処理ルーチンは、App-v 4.5 Sequencer と共に使用する場合に更新が必要になることがあります。 詳細と回避策については、のサポート技術情報の記事を参照してください <https://go.microsoft.com/fwlink/?LinkId=123412> 。

### <a href="" id="after-client-upgrade-from-app-v-4-2--some-applications-are-not-shown-"></a>App-v 4.2 からクライアントにアップグレードした後、一部のアプリケーションが表示されない

ログに次のエラーがあるかどうかを確認します。 "アプリケーション仮想化クライアントは OSD ファイルを解析できませんでした"。 Microsoft Application Virtualization 4.5 クライアントは、空の OS タグ (os/Os) を含む OSD ファイルが含まれているアプリケーションをフィルター処理し &lt; &gt; &lt; &gt; ます。

OSD ファイルから空の OS タグを WORKAROUNDDelete します。

### 特定のプロセスについては、App-v server でファイアウォールの適用除外が必要です

サーバーがアプリケーションを適切にストリーミングするために、ディスパッチャーなどのサーバーのコアプロセスは、ファイアウォールを介してアクセスする必要があります。

次のプロセスについて、サーバーのファイアウォールの WORKAROUNDSet を除外します。 sghwsvr.exe と sghwdsptr.exe。 これは、App-v 管理サーバーと App-v Streaming Server に適用されます。

### 新しい Visual Basic ランタイムを必要とするシーケンスパッケージが失敗することがある

古いバージョンの VBruntime がインストールされているシステムで、新しいバージョンの Visual Basic (VB) ランタイムを使っているパッケージをシーケンスすると、パッケージを使おうとすると、クラッシュまたはその他の予期しない動作が発生する可能性があります。 たとえば、vbruntime のバージョン6.00.9782 を使う Microsoft Money2007 を、6.00.9690 のバージョンの WindowsXP システムで使っている場合、その古い VBruntime を使って別の WindowsXP システムで実行しようとすると、請求書デザイナーでクラッシュが発生する可能性があります。

回避策: アプリケーションをシーケンスコンピューターにインストールしているときに、まだ監視しているときに、適切な (新しい) VBruntime を、実行可能ファイルが開始されたパッケージ内のディレクトリにコピーします。 これにより、シーケンス処理されたアプリケーションで、開始時に、必要なバージョンの VBruntime を見つけることができます。

**重要** この問題は、Microsoft Application Virtualization 4.5 の累積 Update1 で修正されました。

 

### サーバーインストーラーがサイレントモードで実行されているときに、MSXML6 が正しくチェックされない

App-v Management Server は、MSXML6 によって異なります。 ただし、たとえば、MSXML6 がまだインストールされていないシステム上で "msiexec.exe-i setup.msi/qn" というコマンドを使用してインストーラーをサイレントモードで実行した場合、インストーラーでは見つからない依存関係が表示されず、そのままインストールされます。 最も一般的な結果として、クライアントが App-v Management Server から発行情報を更新しようとすると、エラーが表示されます。

WORKAROUNDVerify は、MSXML6 がシステムにインストールされていることを示します。

### Application Virtualization 管理コンソールに接続しようとしたときに発生するエラーコード000C800

Application virtualization management Service server のローカル管理者ではない Application Virtualization 管理者が、Application Virtualization 管理コンソールに接続しようとしたときに、エラー (エラーコード: 000C800) を受け取ります。この場合は、Sftmmc/.udl へのアクセスが拒否されたことを示します。 Application virtualization 管理コンソールに正常に接続するには、application Virtualization Management Service サーバーのローカル管理者ではないアプリケーション仮想化管理者が、少なくとも SftMgmt .udl ファイルへの読み取りと実行のアクセス権を持っている必要があります。

アプリケーションの仮想化管理者には、% s ドライブ% ¥ Program filesの Virt ファイルに対する読み取りと実行のアクセス許可を付与する必要があります。 Microsoft System Center App Management server¥ Virt Management Service。

### KEEPCURRENTSETTINGS = 1 と組み合わせて使用すると、クライアントインストーラーのコマンドラインパラメーターが無視される

KEEPCURRENTSETTINGS = 1 と組み合わせて使用する場合、次のクライアントインストーラーコマンドラインパラメーターは無視されます。 SWICACHESIZE、MINFREESPACEMB、ALLOWINDEPENDENTFILESTREAMING、APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、SYSTEMEVENTLOGLEVEL、SWIGLOBALDATA、DOTIMEOUTMINUTES、SWIFSDRIVE、AUTOLOADTARGET、AUTOLOADTARGET、SWIUSERDATA、および REQUIRESECURECONNECTION。

WORKAROUNDIf 設定を保持するには、[KEEPCURRENTSETTINGS = 1] を使用し、展開後に他のパラメーターを設定します。 App-v ADM テンプレートを使って、次のクライアント設定を設定できます。 APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、AUTOLOADTARGET、AUTOLOADTARGET、DOTIMEOUTMINUTES、ALLOWINDEPENDENTFILESTREAMING。 ADM テンプレートはにあり <https://go.microsoft.com/fwlink/?LinkId=121835> ます。

### シマンテック Endpoint Protection での仮想アプリケーションの初期化エラー

アプリケーションとデバイスコントロール機能を有効にして Symantec Endpoint Protection を使用すると、仮想アプリケーションの起動に失敗することがあります。 "アプリケーションは適切に初期化できませんでした (0xc000007b)" というエラーが表示されます。 詳細と回避策については、のサポート技術情報の記事を参照してください <https://go.microsoft.com/fwlink/?LinkId=125851> 。

**重要** この問題は、Microsoft Application Virtualization 4.5 の累積 Update1 で修正されました。

 

## リリースノートの著作権情報


このドキュメントに記載されている情報 (URL などのインターネット Web サイトへの参照を含む) は、予告なしに変更される可能性があり、情報提供のみを目的として提供されます。 このドキュメントを使用することによるすべてのリスクは、ユーザーにはとどまりません。 Microsoft Corporation は、明示的または黙示を問わず、いかなる保証も行いません。 ここで例示した会社、組織、製品、人物、イベントの例は架空のものです。 実際の会社、組織、製品、人物、またはイベントとの関係はありません。また、推定する必要があります。 お客様ご自身の責任において、適用されるすべての著作権関連法規に従ったご使用をお願いします。 このドキュメントのいかなる部分も、米国 Microsoft Corporation の書面による許諾を受けることなく、検索システムに複製、格納、導入したり、その目的を問わず、いかなる形態や手段であっても、転送することは禁じられています。ここでいう手段とは、電子的、機械的、複写、録音など、すべての手段を含みます。ただしこれは、著作権法上のお客様の権利を制限するものではありません。

Microsoft は、このドキュメントに記載されている内容に関して、特許、特許申請、商標、著作権、またはその他の知的財産権を有する場合があります。 Microsoft による使用許諾契約書によって明示的に許可されている場合を除き、このドキュメントの提供によって、これらの特許権、商標、著作権、またはその他の知的財産権のライセンスが貴社に供与されることはありません。



Microsoft、MS-DOS、Windows、WindowsServer、Windows Vista、Active Directory、および ActiveSync は、U.S.A. やその他の国において、マイクロソフトコーポレーションの登録商標または商標です。

ここに記載されている実際の会社と製品の名前は、各所有者の商標である場合があります。

 

 





