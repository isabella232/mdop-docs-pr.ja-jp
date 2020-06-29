---
title: Microsoft Application Virtualization Management System のリリースノート 4.5 SP1
description: Microsoft Application Virtualization Management System のリリースノート 4.5 SP1
author: dansimp
ms.assetid: 5d6b11ea-7b87-4084-9a7c-0d831f247aa3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 5c24d2e98ad09460ca22e4b29d75ae2b9c72d0bf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816157"
---
# Microsoft Application Virtualization Management System のリリースノート 4.5 SP1


これらのリリースノートを検索するには、CTRL キーを押しながら F キーを押します。

**重要** アプリケーションの仮想化管理システムをインストールする前に、これらのリリースノートをよくお読みください。 これらのリリースノートには、Application Virtualization 管理システムを正常にインストールするために必要な情報が含まれています。 これらのリリースノートには、製品のマニュアルに記載されていない情報が含まれています。 これらのリリースノートとその他の Application Virtualization 管理システムのドキュメントの間に不一致がある場合は、最新の変更を、権限のあるものと見なす必要があります。

 

既知の問題に関する最新情報については、Microsoft TechNet ライブラリのを参照してください <https://go.microsoft.com/fwlink/?LinkId=122918> 。

## Microsoft Application Virtualization 4.5 Service Pack 1 について


これらのリリースノートは、Microsoft Application Virtualization (App-v) 4.5 Service Pack1 (SP1) で導入された変更を反映するように更新されています。 この service pack には、次の変更が含まれています。

-   Windows 7 および Windows Server 2008 R2: App-v 4.5 SP1 は、windows 7 および Windows Server 2008 R2 のサポートを提供します。これには、タスクバー、AppLocker、BranchCache、BitLocker To Go などの Windows 7 機能のサポートが含まれます。Windows Server 2008 R2 のサポートは、Application Virtualization サーバーのみを対象としています。 Windows 7 の AppLocker のサポートについて詳しくは、「」をご覧ください <https://go.microsoft.com/fwlink/?LinkID=156732> 。

-   サードパーティの Kerberos 領域のサポート: App-v 4.5 SP1 は、信頼関係と、Windows ドメインと MIT Kerberos 領域間のマッピングされたユーザーアカウントを持ち、多くの大学で共通するシナリオである環境をサポートします。 このサポートを有効にする方法については、Microsoft TechNet ライブラリのを参照してください <https://go.microsoft.com/fwlink/?LinkId=166004> 。

-   HTTP/HTTPS を介したアプリケーションの発行とストリーミングのサポートが改善されました: App-v 4.5 SP1 では、Windows XP Home Edition、windows Vista Home Basic、Windows 7 Home Basic の HTTP/HTTPS プロトコルを使用して、アプリケーションの発行とストリーミングをサポートしています。

-   カスタマーフィードバックと修正プログラムのロールアップ: アプリ-V 4.5 SP1 には、Microsoft Application Virtualization (App-v) 4.5 CU1 リリース以降で検出された問題に対処するための修正プログラムが含まれています。 この更新プログラムは、microsoft の内部チーム、パートナー、およびアプリ-V 4.5 を使用しているお客様からの既知の問題とお客様からのフィードバックによって生じます。 更新プログラムの完全な一覧については、のサポート技術情報の記事を参照してください <https://go.microsoft.com/fwlink/?LinkId=167121> 。

## 製品ドキュメントについて


Application Virtualization (app-v) の包括的なドキュメントは、Microsoft TechNet の Application Virtualization (App-v) TechCenter で入手でき <https://go.microsoft.com/fwlink/?LinkId=122939> ます。 TechNet のドキュメントには、Application Virtualization Sequencer、Application Virtualization クライアント、Application Virtualization Server のオンラインヘルプが含まれています。 また、Application Virtualization Planning and Deployment Guide と Application Virtualization 運用ガイドも含まれています。

## セキュリティの脆弱性とウイルスから保護する


セキュリティの脆弱性やウイルスから保護するために、インストールされている新しいソフトウェアには、使用可能な最新のセキュリティ更新プログラムをインストールすることをお勧めします。 詳細については、Microsoft セキュリティ Web サイトを参照してください <https://go.microsoft.com/fwlink/?LinkId=3482> 。

## フィードバックの提供


Microsoft application virtualization TechCenter () のコミュニティフォーラムを通じて、フィードバックを提供したり、提案を行ったり、問題を報告したりすることができ <https://go.microsoft.com/fwlink/?LinkId=122917> ます。

ドキュメントについてのフィードバックは、App-v ドキュメントチームに直接提供することもできます。 ドキュメントのフィードバックを appvdocs@microsoft.com に送信します。

## Application Virtualization 4.5 SP1 の既知の問題


このセクションでは、Microsoft Application Virtualization (App-v) 4.5 SP1 の問題に関する最新情報について説明します。 これらの問題は製品ドキュメントには記載されていないため、場合によっては、既存の製品ドキュメントに矛盾が生じることがあります。 この問題は、可能な限り、ソフトウェアの以降のリリースで対処される予定です。

### サーバー管理コンソールをインストールするためのガイダンス

主要アプリケーション仮想化パブリッシングとストリーミングサーバー以外のシステムに管理ソフトウェアをインストールする必要がある場合、サーバーのインストールでは、管理コンソールと管理 Web サービスを、プライマリアプリの管理サーバーから別のサーバーにインストールすることがサポートされています。 複数のサーバー間で管理コンポーネントを配布するには、Web サービスがインストールされているサーバーで Kerberos 委任を有効にする必要があります。 このサポートを有効にする方法については、Microsoft TechNet ライブラリの次のページを参照してください。 <https://go.microsoft.com/fwlink/?LinkId=166682>

### setup.msi を使用してクライアントをアプリ-V 4.5 SP1 にインストールまたはアップグレードするためのガイダンス

setup.msi を使用して app-v クライアントを App-v 4.5 SP1 にインストールまたはアップグレードすると、前提条件が自動的にインストールされることはありません。

回避策いただけは、app-v client toApp-V 4.5 SP1 をインストールまたはアップグレードする前に、前提条件を手動でインストールする必要があります。 前提条件と App-v クライアントをインストールするための詳細な手順については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=144106> 。

この操作が完了したら、昇格された特権で setup.msi を使って、App-v 4.5 SP1 クライアントをインストールします。 このファイルは、インストーラ \ クライアントフォルダーの App-v 4.5 SP1 リリースメディアで入手できます。

Microsoft アプリケーションエラー報告をインストールするときに、アプリ-V 4.5 SP1 デスクトップクライアントをインストールまたはアップグレードする場合は、次のコマンドを使用します。

    msiexec /i dw20shared.msi APPGUID={93468B43-C19D-44F9-8BCC-114076DB0443}  allusers=1 reboot=suppress REINSTALL=all REINSTALLMODE=vomus

または、リモートデスクトップサービス (以前のターミナルサービス) 用の App-v 4.5 SP1 クライアントをインストールまたはアップグレードする場合は、次のコマンドを使用します。

    msiexec /i dw20shared.msi APPGUID={0042AD3C-99A4-4E58-B5F0-744D5AD96E1C} allusers=1 reboot=suppress REINSTALL=all REINSTALLMODE=vomus

**注** APPGUID パラメーターは、インストールまたはアップグレードする App-v クライアントの製品コードを参照します。 製品コードは setup.msi ごとに固有です。 Orca データベースエディターまたは同様のツールを使用して、Windows インストーラファイルを調査し、製品コードを確認することができます。 この手順は、すべてのインストールまたは App-v 4.5 SP1 へのアップグレードに必要です。

 

### .NET Framework をシーケンス処理するときのパフォーマンスを向上させる

.NET Framework のシーケンスを行うときに、Microsoft .NET Framework NGEN サービスがバックグラウンドタスクとしてアセンブリをプリコンパイルしようとするため、システムのパフォーマンスが低下することがあります。

WORKAROUNDWhen の順序付け .NET Framework では、監視フェーズを完了した後で、Microsoft .NET Framework NGEN サービス (mscorsvw.exe) を無効にします。 Sequencer で [**仮想サービス**] タブを使用し、スタートアップの種類を [無効] に変更する必要があります。

### Microsoft Application Virtualization クライアントをアンインストールすると、アンインストールを実行したユーザーに関連付けられているユーザー設定は削除されます。

App-v クライアントをアンインストールすると、Windows インストーラーによって、現在のユーザーのプロファイルから Application Virtualization の設定が削除されます。 コンピューターでローミングプロファイルを使用している場合は、お使いのコンピューター上の仮想アプリケーションの設定が削除されるため、お客様のパーソナルネットワークアカウントを使用してクライアントをアンインストールしないでください。

回避策いただけは、仮想アプリケーションの実行に使用されない管理者アカウントを使用して、App-v クライアントのアンインストールを実行する必要があります。

### シーケンスウィザードの実行中に、仮想ファイルシステムと仮想レジストリタブで行った編集を保存する必要があります。

アップグレードを実行するためにパッケージを開いた場合、またはシーケンスウィザードを新しいパッケージで既に実行していて、仮想ファイルシステムまたは仮想レジストリタブでパッケージを変更した場合、これらの変更は自動的に保存されません。

ウィザードを再実行する前に変更を WORKAROUNDSave し、ウィザードの仮想環境に確実に反映されるようにします。

### コマンドラインの Sequencer は、昇格されたコマンドプロンプトから実行する必要があります。

コマンドライン Sequencer を使用しても、昇格のメッセージは表示されません。

昇格されたコマンドプロンプトを使ってコマンドライン Sequencer を WORKAROUNDRun します。

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

### .NET の互換性の変更

Microsoft Application Virtualization (App-v) 累積 Update1 以降では、WindowsXP (SP2 以降) での .NET Framework のシーケンスがサポートされています。 SoftGrid 4.2 用に記述された .NET アプリケーションのシーケンス処理ルーチンは、App-v 4.5 Sequencer と共に使用する場合に更新が必要になることがあります。 詳細と回避策については、のサポート技術情報の記事を参照してください <https://go.microsoft.com/fwlink/?LinkId=123412> 。

### <a href="" id="after-client-upgrade-from-app-v-4-2--some-applications-are-not-shown-"></a>App-v 4.2 からクライアントにアップグレードした後、一部のアプリケーションが表示されない

ログに次のエラーがあるかどうかを確認します。 "アプリケーション仮想化クライアントは OSD ファイルを解析できませんでした"。 App-v 4.5 クライアントは、空の OS タグ (os/Os) を含む OSD ファイルが含まれているアプリケーションをフィルター処理し &lt; &gt; &lt; &gt; ます。

OSD ファイルから空の OS タグを WORKAROUNDDelete します。

### 特定のプロセスについては、App-v server でファイアウォールの適用除外が必要です

サーバーがアプリケーションを適切にストリーミングするために、ディスパッチャーなどのサーバーのコアプロセスは、ファイアウォールを介してアクセスする必要があります。

次のプロセスについて、サーバーのファイアウォールの WORKAROUNDSet を除外します。 sghwsvr.exe と sghwdsptr.exe。 これは、App-v 管理サーバーと App-v Streaming Server に適用されます。

### サーバーインストーラーがサイレントモードで実行されているときに、MSXML6 が正しくチェックされない

App-v Management Server は、MSXML6 によって異なります。 ただし、サイレントモードでインストーラーを実行している場合 (たとえば、MSXML6 がまだインストールされていないシステム上で "msiexec.exe-i setup.msi/qn" というコマンドを使用した場合など)、インストーラーでは見つからない依存関係が検出されず、そのままインストールされます。 そのため、クライアントは、アプリからの公開情報を更新しようとすると、エラーが表示されます。

WORKAROUNDVerify は、MSXML6 がシステムにインストールされていることを示します。

### Application Virtualization 管理コンソールに接続しようとしたときに発生するエラーコード000C800

Application hyper-v 管理 Web サービスサーバーのローカル管理者ではないアプリケーション仮想化管理者が、App-v 管理コンソールに接続しようとしたときにエラー (エラーコード: 000C800) を受け取ります。この場合は、sftmmc 対するアクセスが拒否されたことを示すメッセージが表示されます。 App-v 管理コンソールに正常に接続するには、App-v Management Web サービスサーバーのローカル管理者権限を持たない管理者が、SftMgmt .udl ファイルの読み取りおよび実行のアクセス許可を少なくとも持っている必要があります。

アプリケーションの仮想化管理者には、% s ドライブ% ¥ Program filesの Virt ファイルに対する読み取りと実行のアクセス許可を付与する必要があります。 Microsoft System Center App Management server¥ Virt Management Service。

### KEEPCURRENTSETTINGS = 1 と組み合わせて使用すると、クライアントインストーラーのコマンドラインパラメーターが無視される

KEEPCURRENTSETTINGS = 1 と組み合わせて使用する場合、次のクライアントインストーラーコマンドラインパラメーターは無視されます。 SWICACHESIZE、MINFREESPACEMB、ALLOWINDEPENDENTFILESTREAMING、APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、SYSTEMEVENTLOGLEVEL、SWIGLOBALDATA、DOTIMEOUTMINUTES、SWIFSDRIVE、AUTOLOADTARGET、AUTOLOADTARGET、SWIUSERDATA、および REQUIRESECURECONNECTION。

WORKAROUNDIf 設定を保持するには、[KEEPCURRENTSETTINGS = 1] を使用し、展開後に他のパラメーターを設定します。 App-v ADM テンプレートを使って、次のクライアント設定を設定できます。 APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、AUTOLOADTARGET、AUTOLOADTARGET、DOTIMEOUTMINUTES、ALLOWINDEPENDENTFILESTREAMING。 ADM テンプレートはにあり <https://go.microsoft.com/fwlink/?LinkId=121835> ます。

## リリースノートの著作権情報


このドキュメントに記載されている情報 (URL などのインターネット Web サイトへの参照を含む) は、予告なしに変更される可能性があり、情報提供のみを目的として提供されます。 このドキュメントを使用することによる使用または結果のすべてのリスクは、ユーザーにはとどまりません。また、Microsoft Corporation は、明示的または黙示を問わず、いかなる保証も行いません。 特に記載がない限り、ここに記載されている会社、組織、製品、ドメイン名、電子メールアドレス、ロゴ、人物、場所、およびイベントは架空のものです。 実際の会社、組織、製品、ドメイン名、電子メールアドレス、ロゴ、人物、場所、イベントなどとの関連付けは、意図したものであるか、または推測されるものではありません。 お客様ご自身の責任において、適用されるすべての著作権関連法規に従ったご使用をお願いします。 このドキュメントのいかなる部分も、米国 Microsoft Corporation の書面による許諾を受けることなく、検索システムに複製、格納、導入したり、その目的を問わず、いかなる形態や手段であっても、転送することは禁じられています。ここでいう手段とは、電子的、機械的、複写、録音など、すべての手段を含みます。ただしこれは、著作権法上のお客様の権利を制限するものではありません。

Microsoft は、このドキュメントに記載されている内容に関して、特許、特許申請、商標、著作権、またはその他の知的財産権を有する場合があります。 Microsoft による使用許諾契約書によって明示的に許可されている場合を除き、このドキュメントの提供によって、これらの特許権、商標、著作権、またはその他の知的財産権のライセンスが貴社に供与されることはありません。



Microsoft、Active Directory、ActiveSync、MS-DOS、Windows、WindowsServer、Windows Vista は、Microsoft の会社グループの商標です。

その他のすべての商標は、該当する所有者に帰属します。

 

 





