---
title: App-V 4.5 SP2 リリース ノート
description: App-V 4.5 SP2 リリース ノート
author: dansimp
ms.assetid: 1b3a8a83-4523-4634-9f75-29bc22ca5815
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 35cff3b2a2c110a4d8beba883a4cf9332381ea60
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819854"
---
# App-V 4.5 SP2 リリース ノート


これらのリリースノートを検索するには、CTRL キーを押しながら F キーを押します。

**重要** Microsoft Application Virtualization Management System をインストールする前に、これらのリリースノートをよくお読みください。 これらのリリースノートには、Application Virtualization 管理システムを正常にインストールするために必要な情報が含まれています。 これらのリリースノートには、製品のマニュアルに記載されていない情報が含まれています。 これらのリリースノートとその他の Application Virtualization 管理システムのドキュメントの間に不一致がある場合は、最新の変更を、権限のあるものと見なす必要があります。

 

既知の問題に関する最新情報については、Microsoft TechNet ライブラリの「 [app-v 4.5 SP2 リリースノート](https://go.microsoft.com/fwlink/?LinkId=184640)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=184640) 。

## Microsoft Application Virtualization 4.5 Service Pack 2 について


これらのリリースノートは、Microsoft Application Virtualization (App-v) 4.5 Service Pack2 (SP2) で導入された変更を反映するように更新されています。 この service pack には、次の変更が含まれています。

-   Office 2010 のサポート: App-V 4.5 SP2 では、Microsoft Office 2010 の仮想化がサポートされるようになりました。 Microsoft Office 2010 を App-v 4.5 SP2 と順序付けるための規範となるガイダンスについては、「 [Microsoft App-v 4.6 で office 2010 をシーケンス処理するための規範ガイダンス](https://go.microsoft.com/fwlink/?LinkId=191539)」を参照してください https://go.microsoft.com/fwlink/?LinkId=191539) 。

-   データベースミラーリングのサポート: App-v 4.5 SP2 では、Microsoft SQL Server データベースのミラーリングがサポートされるようになりました。 App-v 環境でのデータベースミラーリングの構成の詳細については、「 [app-v () の MICROSOFT SQL Server ミラーリングサポートを構成する方法](https://go.microsoft.com/fwlink/?LinkId=190880)」を参照してください https://go.microsoft.com/fwlink/?LinkId=190880) 。

-   カスタマーフィードバックと修正プログラムのロールアップ: アプリ-V 4.5 SP2 には、アプリ-v 4.5 SP1 の後に見つかった問題に対処するための修正プログラムが含まれています。 この更新プログラムでは、Microsoft の内部チーム、パートナー、および App-v を使用しているユーザーからの既知の問題とお客様からのフィードバックの組み合わせについて対処します。 更新プログラムの完全な一覧については、 [Microsoft Application Virtualization 4.5 Service Pack 2](https://go.microsoft.com/fwlink/?LinkId=191540) () に関する説明を参照して、Microsoft サポート技術情報の記事980847を参照してください https://go.microsoft.com/fwlink/?LinkId=191540) 。

## 製品ドキュメントについて


Application Virtualization (App-v) の包括的なドキュメントは、 [Application Virtualization TechCenter ライブラリ](https://go.microsoft.com/fwlink/?LinkId=122939)() の Microsoft TechNet で入手でき https://go.microsoft.com/fwlink/?LinkId=122939) ます。 TechNet のドキュメントには、Application Virtualization Sequencer、Application Virtualization クライアント、Application Virtualization Server のオンラインヘルプが含まれています。 また、Application Virtualization Planning and Deployment Guide と Application Virtualization 運用ガイドも含まれています。

## セキュリティの脆弱性とウイルスから保護する


セキュリティの脆弱性やウイルスから保護するために、インストールされている新しいソフトウェアには、使用可能な最新のセキュリティ更新プログラムをインストールすることをお勧めします。 詳細については、「 [Microsoft セキュリティ](https://go.microsoft.com/fwlink/?LinkId=3482)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=3482) 。

## フィードバックの提供


Application Virtualization TechCenter[アプリ-v ドキュメントフォーラム ()](https://go.microsoft.com/fwlink/?LinkId=122917)のコミュニティフォーラムを通じて、フィードバックを提供したり、提案を行ったり、問題を報告したりすることができ https://go.microsoft.com/fwlink/?LinkId=122917) ます。

ドキュメントのフィードバックは、の App-v ドキュメントチームに直接送信することもでき <appvdocs@microsoft.com> ます。

## Application Virtualization 4.5 SP2 の既知の問題


このセクションでは、Microsoft Application Virtualization (App-v) 4.5 SP2 の問題に関する最新情報について説明します。 これらの問題は製品ドキュメントには記載されていないため、場合によっては、既存の製品ドキュメントに矛盾が生じることがあります。 この問題は、可能な限り、ソフトウェアの以降のリリースで対処される予定です。

### サーバー管理コンソールをインストールするためのガイダンス

主要アプリケーション仮想化パブリッシングとストリーミングサーバー以外のシステムに管理ソフトウェアをインストールする必要がある場合、サーバーのインストールでは、Application Virtualization 管理コンソールと Application Virtualization 管理 Web サービスを、プライマリアプリの管理サーバーから別のサーバーにインストールすることがサポートされています。 複数のサーバー間で管理コンポーネントを配布するには、Application Virtualization Web サービスがインストールされているサーバーで Kerberos 委任を有効にする必要があります。 このサポートを有効にする方法については、「[委任に対して信頼されるようにサーバーを構成する方法](https://go.microsoft.com/fwlink/?LinkId=166682)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=166682) 。

### Setup.msi を使用して、クライアントを App-v 4.5 SP2 にインストールまたはアップグレードするためのガイダンス

Setup.msi を使用して app-v クライアントを App-v 4.5 SP2 にインストールまたはアップグレードすると、前提条件が自動的にインストールされることはありません。

回避策いただけは、アプリ-V 4.5 SP2 に App-v クライアントをインストールまたはアップグレードする前に、前提条件を手動でインストールする必要があります。 前提条件と App-v クライアントをインストールする方法について詳しくは、「[コマンドラインを使用してクライアントをインストールする方法](https://go.microsoft.com/fwlink/?LinkId=144106)」をご覧ください https://go.microsoft.com/fwlink/?LinkId=144106) 。

この操作が完了したら、管理者の資格情報を使用して Setup.msi を使用して、App-v 4.5 SP2 クライアントをインストールします。 このファイルは、インストーラ \ \ クライアントフォルダーの App-v 4.5 SP2 リリースメディアで利用できます。

Microsoft アプリケーションエラー報告をインストールするときに、4.5 アプリをインストールまたはアップグレードする場合は、次のコマンドを使用します。

**msiexec/i dw20shared.msi APPGUID = {C6FC75B9-7D86-4C44-8BDB-EAFE1F0E200D} allusers = 1 再起動 = 抑制 = すべての REINSTALLMODE = vomus**

または、リモートデスクトップサービス (旧ターミナルサービス) 用の App-v 4.5 SP2 クライアントをインストールまたはアップグレードする場合は、次のコマンドを使用します。

**msiexec/i dw20shared.msi APPGUID = {ECF80BBA-CA07-4A74-9ED6-E064F38AF1F5} allusers = 1 再起動 = 抑制 = すべての REINSTALLMODE = vomus**

**注**  
-   APPGUID パラメーターは、インストールまたはアップグレードする App-v クライアントの製品コードを参照します。 製品コードは Setup.msi ごとに固有です。 Orca データベースエディターまたは同様のツールを使用して、Windows インストーラファイルを調査し、製品コードを確認することができます。 この手順は、すべてのインストールまたは App-v 4.5 SP2 へのアップグレードに必要です。

-   アップグレードしていて、Dw20shared.msi を既にインストールしている場合は、この手順は必要ありません。

 

### .NET Framework をシーケンス処理するときのパフォーマンスを向上させる

.NET Framework NGEN サービスがバックグラウンドタスクとしてアセンブリをプリコンパイルしようとしているため、Microsoft .NET Framework の順序を示すときに、システムのパフォーマンスが低下することがあります。

WORKAROUNDWhen シーケンス .NET Framework では、監視フェーズを完了した後で .NET Framework NGEN サービス (Mscorsvw.exe) を無効にします。 App-v の Sequencer で [**仮想サービス**] タブを使用し、スタートアップの種類を [**無効**] に変更する必要があります。

### Microsoft Application Virtualization クライアントをアンインストールすると、アンインストールを実行しているユーザーに関連付けられているユーザー設定が削除される

App-v クライアントをアンインストールすると、Windows インストーラーは、現在のユーザーのプロファイルからアプリケーションの仮想化設定を削除します。 コンピューターでローミングプロファイルを使用している場合は、お使いのコンピューター上の仮想アプリケーションの設定が削除されるため、お客様のパーソナルネットワークアカウントを使用してクライアントをアンインストールしないでください。

回避策いただけは、仮想アプリケーションの実行に使用されていない管理者アカウントを使用して、App-v クライアントをアンインストールする必要があります。

### シーケンスウィザードの実行中に、仮想ファイルシステムと仮想レジストリタブで行った編集を保存する必要があります。

アップグレードを実行するためにパッケージを開いた場合、またはシーケンスウィザードを新しいパッケージで既に実行していて、仮想ファイルシステムまたは仮想レジストリタブでパッケージを変更した場合、これらの変更は自動的に保存されません。

ウィザードを再実行する前に変更を WORKAROUNDSave し、ウィザードの仮想環境に確実に反映されるようにします。

### コマンドラインの Sequencer は、昇格されたコマンドプロンプトから実行する必要があります。

コマンドライン Sequencer を使用しても、昇格のメッセージは表示されません。

昇格されたコマンドプロンプトを使用して、コマンドライン Sequencer を WORKAROUNDRun します。

### OSD ファイルで短い path 変数名を使うとエラーが発生する場合がある

エラー450478が表示された場合: 1F702339-0000010B "クライアントで仮想アプリケーションを起動すると、OSD の変数が正しく設定されていない可能性があります。 これは、アプリケーションのインストーラーでシーケンス中に短いパス名が設定されている場合に発生する可能性があります。

OSD ファイルに存在する任意の CSIDL 変数から末尾のチルダを WORKAROUNDRemove します。

### <a href="" id="correct-syntax-for-decodepath-parameter-for-command-line-sequencer-"></a>コマンドライン Sequencer の DECODEPATH パラメーターの正しい構文

コマンドライン Sequencer でパッケージを開いて、ドライブ Q のルートにデコードする場合、 *DECODEPATH*パラメーターの構文に末尾のスラッシュを含めることはできません。

回避策いただけでは、 **Q:\\** (末尾の "\ \" 文字を省略します)**を使うこと**ができます。

### <a href="" id="when-upgrading-app-v-4-2-packages--you-encounter-problems-caused-by-windows-installer-files-in-the-virtual-file-system-"></a>App-v 4.2 パッケージをアップグレードするときに、仮想ファイルシステムの Windows インストーラーファイルが原因で発生する問題が発生します。

App-v 4.2 からパッケージをアップグレードするときに問題が発生する可能性があります。 Windows インストーラーのシステムファイルが、アプリ-V 4.2 に既定で含まれていましたが、シーケンスワークステーションにローカルにインストールされている Windows Installer ライブラリに関する問題が発生する場合があります。 次のファイルは、CSIDL \ _SYSTEM \ \ に保存されています。

Cabinet.dll

Msi.dll

Msiexec.exe

Msihnd.dll

Msimsg.dlll

上記のすべてのファイルをパッケージから WORKAROUNDDelete します。 [ **VFS** ] タブのマッピングと、デコードパスにある CSIDL \ _SYSTEM フォルダー内の実際のファイルを削除します。

### <a href="" id="on-windows-xp--by-default--client-installation-logging-is-not-enabled-"></a>WindowsXP では、クライアントのインストールログは既定で有効になっていません。

クライアントをインストールするときに、トラブルシューティングのためにインストールエラーがキャプチャされていることを確認するには、コマンドラインを使用してログを有効にする必要があります。

次の例に示すように、パラメーター */l\ * vx! log.txt*をコマンドラインに WORKAROUNDAdd します。

**setup.exe/s/v "/qn/l\ * vx! log.txt "**

**msiexec.exe/i setup.msi/qn/l\ * vx! log.txt**

または、レジストリキーを次の値に設定することもできます。

**\ [HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Policies\\Microsoft\\Windows\\Installer\] "Logging" = "voicewarmupx!"**

### Kerberos 認証が機能するためには、サービスプリンシパル名 (Spn) が IIS に登録されている必要があります。

インターネットインフォメーションサービス (IIS) 6.0 orIIS 7.0 のアイコンまたは OSD ファイルの取得とストリーミングを使用している場合、Kerberos 認証を有効にするには、次のように Spn を登録する必要があります。

-   IIS サーバーで SETSPN.EXE リソースキットツールを使用して、次のコマンドを実行します。 サーバーの完全修飾ドメイン名 (FQDN) を使用する必要があります。

    **Setspn-r SOFTGRID/ &lt; SERVER FQDN&gt;**

    **Setspn-r HTTP/ &lt; SERVER FQDN&gt;**

詳細については、「[統合 Windows 認証 (IIS 6.0) (IIS) ()](https://go.microsoft.com/fwlink/?LinkId=131407) 」を参照してください https://go.microsoft.com/fwlink/?LinkId=131407) 。

### .NET の互換性の変更

Microsoft Application Virtualization (App-v) 累積 Update1 以降では、「WindowsXP SP2 以降での .NET Framework のシーケンス処理がサポートされています。 SoftGrid 4.2 用に記述された .NET アプリケーションのシーケンス処理ルーチンは、App-v 4.5 Sequencer と共に使用する場合に更新が必要になることがあります。 詳細と回避策については、「 [Microsoft Application virtualization 4.5 での .net のサポート](https://go.microsoft.com/fwlink/?LinkId=123412)」の「Application virtualization TechCenter の記事」を参照してください https://go.microsoft.com/fwlink/?LinkId=123412) 。

### <a href="" id="after-client-upgrade-from-app-v-4-2--some-applications-are-not-shown-"></a>App-v 4.2 からクライアントにアップグレードした後、一部のアプリケーションが表示されない

ログに次のエラーがあるかどうかを確認します。 "アプリケーション仮想化クライアントは OSD ファイルを解析できませんでした"。 App-v 4.5 クライアントは、空の OS タグ (os/Os) を含む OSD ファイルが含まれているアプリケーションをフィルター処理し &lt; &gt; &lt; &gt; ます。

OSD ファイルから空の OS タグを WORKAROUNDDelete します。

### 特定のプロセスについては、App-v server でファイアウォールの適用除外が必要です

サーバーがアプリケーションを適切にストリーミングするために、ディスパッチャーを含むサーバーのコアプロセスでは、ファイアウォール経由のアクセスが必要になります。

次のプロセスについて、サーバーのファイアウォールの WORKAROUNDSet を除外します。 Sghwsvr.exe と Sghwdsptr.exe。 これは、App-v 管理サーバーと App-v Streaming Server に適用されます。

### サーバーインストーラーがサイレントモードで実行されているときに、MSXML6 が正しくチェックされない

App-v Management Server は、MSXML6 によって異なります。 ただし、たとえば、MSXML6 がまだインストールされていないシステム上で、コマンド**setup.msi msiexec.exe**を使ってサイレントモードでインストーラーを実行した場合、インストーラーでは見つからない依存関係が検出されず、インストールが行われません。 そのため、クライアントは、アプリからの公開情報を更新しようとすると、エラーが発生します。

WORKAROUNDVerify は、MSXML6 がシステムにインストールされてから、アプリのサイレントインストールを実行します。

### Application Virtualization 管理コンソールに接続しようとしたときに発生するエラーコード000C800

Application Virtualization 管理者が、app-v management Web Service server のローカル管理者ではない場合、app-v 管理コンソールに接続しようとすると、エラー (エラーコード: 000C800) が発生します。この場合は、Sftmmc .udl へのアクセスが拒否されていることを示します。 App-v 管理コンソールに正常に接続するには、App-v Management Web サービスサーバーのローカル管理者権限を持たない管理者が、SftMgmt .udl ファイルの読み取りおよび実行のアクセス許可を少なくとも持っている必要があります。

アプリケーションの仮想化管理者は、フォルダー% ¥ xxx xxx xxx Virt xxx xxx xxx Virt xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx

### KEEPCURRENTSETTINGS = 1 と組み合わせて使用すると、クライアントインストーラーのコマンドラインパラメーターが無視される

KEEPCURRENTSETTINGS = 1 と組み合わせて使用する場合、次のクライアントインストーラーコマンドラインパラメーターは無視されます。 SWICACHESIZE、MINFREESPACEMB、ALLOWINDEPENDENTFILESTREAMING、APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、SYSTEMEVENTLOGLEVEL、SWIGLOBALDATA、DOTIMEOUTMINUTES、SWIFSDRIVE、AUTOLOADTARGET、AUTOLOADTARGET、SWIUSERDATA、および REQUIRESECURECONNECTION。

WORKAROUNDIf 設定を保持するには、[KEEPCURRENTSETTINGS = 1] を使用し、展開後に他のパラメーターを設定します。 App-v ADM テンプレートを使って、次のクライアント設定を設定できます。 APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、AUTOLOADTARGET、AUTOLOADTARGET、DOTIMEOUTMINUTES、ALLOWINDEPENDENTFILESTREAMING。 Microsoft ダウンロードセンターの ADM テンプレートは、 [Microsoft Application Virtualization 管理用テンプレート (Adm テンプレート) (Adm テンプレート) ()](https://go.microsoft.com/fwlink/?LinkId=121835)からダウンロードでき https://go.microsoft.com/fwlink/?LinkId=121835) ます。

### リリースノートの著作権情報

このドキュメントは「現状有姿のまま」提供されます。 このドキュメントに記載されている情報および見解 (URL 等のインターネット Web サイトに関する情報を含む) は、将来予告なしに変更されることがあります。 使用のリスクを負うことができます。

ここに示すいくつかの例は、例示のためだけに用意されており、架空のものでもあります。実際の関連付けや接続は意図していないか、または推定する必要があります。

このドキュメントは、マイクロソフト製品に含まれる知的財産に対していかなる法的権利も付与しません。 お客様は、内部的な参照目的に限り、このドキュメントを複製して使用することができます。 このドキュメントは、内部的な参照目的に合わせて変更できます。



Microsoft、Active Directory、ActiveSync、MS-DOS、Windows、WindowsServer、Windows Vista は、Microsoft の会社グループの商標です。

その他のすべての商標は、該当する所有者に帰属します。

 

 





