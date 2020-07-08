---
title: MBAM 2.5 SP1 のリリース ノート
description: MBAM 2.5 SP1 のリリース ノート
author: dansimp
ms.assetid: 3ac424c8-c490-4d62-aba4-1b462c02e962
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 09/06/2017
ms.openlocfilehash: 837892897aeca341433de54aca1228c0faeee124
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824987"
---
# MBAM 2.5 SP1 のリリース ノート


これらのリリースノートを検索するには、Ctrl キーを押しながら F キーを押します。

Microsoft BitLocker 管理および監視 (MBAM) 2.5 SP1 をインストールする前に、これらのリリースノートをよくお読みください。 これらのリリースノートには、MBAM を正常にインストールするために必要な情報が含まれており、製品のマニュアルに記載されていない情報が含まれていることがあります。 これらのリリースノートが、他の MBAM 2.5 SP1 のドキュメントと異なる場合は、最新の変更について、権限を持つことを検討してください。 これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。

## <a href="" id="---------mbam-2-5-sp1-known-issues"></a> MBAM 2.5 SP1 の既知の問題


このセクションには、MBAM 2.5 SP1 のリリースノートが記載されています。

### <a href="" id="powershell-read-ad--cmdlets-do-not-provide-feedback-if-user-does-not-have-sufficient-rights"></a>PowerShell の読み取り-AD \ * コマンドレットは、ユーザーが十分な権限を持っていない場合はフィードバックを提供しません

PowerShell を使用しようとしているユーザーが、MBAM サーバーのコマンドレットで、Active Directory の回復情報を読み取るか、TPM 情報を読み取る権限がない場合、コマンドレットによってエラーや警告がユーザーに提供されることはありません。

**回避策:** 必要なユーザー権限がある場合にのみ、PowerShell の読み取り広告 \ * コマンドレットを使います。

### MBAM Active Directory (AD) 移行コマンドレットでボリューム回復情報が取得されない

MBAM Active Directory (AD) 移行コマンドレットでは、スラッシュ文字 (/) が OU 名の一部である場合に、組織単位 (Ou) 内のコンピューターのボリューム回復情報を取得できません。 このエラーが発生すると、パイプラインの終了エラーが発生したため、AD の重複は繰り返されません。

**技術的な詳細:** コマンドの実行時に、次のエラーが表示されます。

``` syntax
Read-ADRecoveryInformation : Unknown error (0x80005000)
At line:1 char:1
+ Read-ADRecoveryInformation -Server "…" -SearchBase " ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [Read-ADRecoveryInformation], COMException
    + FullyQualifiedErrorId : System.Runtime.InteropServices.COMException,Microsoft.Mbam.Server.Commands.ADPullCommands.ReadADRecoveryInformationCommand
```

さらに、例外スタックトレース `Error[0].Exception.StackTrace` は次のようになります。

``` syntax
   at System.DirectoryServices.DirectoryEntry.Bind(Boolean throwIfFail)
   at System.DirectoryServices.DirectoryEntry.Bind()
   at System.DirectoryServices.DirectoryEntry.get_AdsObject()
   at System.DirectoryServices.PropertyValueCollection.PopulateList()
   at System.DirectoryServices.PropertyValueCollection..ctor(DirectoryEntry entry, String propertyName)
   at System.DirectoryServices.PropertyCollection.get_Item(String propertyName)
   at Microsoft.Mbam.Server.Commands.ADPullCommands.ReadCore.VerifySettingsConnectivity()
   at Microsoft.Mbam.Server.Commands.ADPullCommands.ReadCore.ExecuteRead()
   at Microsoft.Mbam.Server.Commands.ADPullCommands.ReadADInformationBase.ProcessRecord()
   at System.Management.Automation.CommandProcessor.ProcessRecord()
```

**回避策:** この問題を解決するには、次のいずれかのタスクを実行します。

-   OU の名前を変更して、スラッシュ文字を削除してから、スクリプトを実行します。

-   問題のある OU をバックアッププロセスから除外するには、名前にスラッシュ文字が含まれていない Ou の一覧を探します。 これらの Ou で、一度に1つずつスクリプトを実行します。

### <a href="" id="-------------mbam-fails-to-encrypt-a-volume-and-reports-an-error-if-you-set-a-tpm---pin-protector-on-a-tablet-device"></a> Pc で TPM + PIN プロテクターを設定すると、MBAM でボリュームの暗号化に失敗し、エラーが報告される

エンドユーザーがタブレットデバイスで TPM + PIN プロテクターを設定しようとすると、MBAM が暗号化に失敗し、エラーが報告されます。 この問題は、タブレットデバイスがプレブート環境キーボードを持っていないために発生します。

**回避策:**[**タブレットでのプレブートキーボード入力を必要とする BitLocker 認証の有効化**を有効にする] グループポリシー設定 この設定は、BitLocker グループポリシー設定であり、MBAM グループポリシーテンプレートでは使用できません。

### すべてのサービスアカウントにユーザープリンシパル名が必要

MBAM のすべてのサービスアカウントにユーザープリンシパル名 (UPN) を設定する必要があります。 アカウントの UPN の作成に失敗した場合、構成プロセス中に、ユーザーまたはグループが Active Directory で見つからなかったことを示すエラーメッセージが表示されます。

**回避策:** サービスアカウントに UPN を追加します。

### IIS を .NET Framework 4.5 にアップグレードした後、セルフサービスポータルと管理と監視の Web サイトが開かない

インターネットインフォメーションサービス (IIS) を Microsoft .NET Framework 4.5 にアップグレードすると、セルフサービスポータルと管理と監視の Web サイトが開かなくなります。

**回避策:**[「.Net Framework 4.0 をインストールした後のエラーメッセージ」を参照してください。 "' HttpModule ' 型を読み込めませんでした](https://go.microsoft.com/fwlink/?LinkId=393568)。

### レポートが構成されていない場合に、管理と監視の Web サイトに "レポートが見つかりません" というエラーメッセージが表示される

管理と監視の Web サイトを構成して、最初にレポート機能を構成せずにレポートを表示しようとすると、レポートが見つからないことを示すエラーメッセージが表示されます。

**回避策:** Web アプリケーションを構成する前に、レポート機能を構成します。

### 管理と監視の Web サイトにあるレポートで、SSL が SSRS で構成されていない場合は警告が表示される

SQL Server Reporting Services (SSRS) が Secure Socket Layer (SSL) を使用するように構成されていない場合、MBAM サーバーを構成するときに、レポート機能の URL は HTTPS ではなく、HTTP に設定されます。 その後、管理と監視の Web サイトを開き、レポートを選択すると、"セキュリティで保護されたコンテンツのみが表示されます" というエラーメッセージが表示されます。

**回避策:** レポートを表示するには、[**すべてのコンテンツを表示**] をクリックします。 この問題を解決するには、SQL Server Reporting Services がインストールされている MBAM コンピューターにアクセスし、 **Reporting Services 構成マネージャー**を実行して、[ **WEB サービスの URL**] をクリックします。 サーバーに適切な SSL 証明書を選択し、適切な SSL ポート (既定のポートは 443) を入力して、[**適用**] をクリックします。

### BitLocker のコンプライアンスの概要レポートで [戻る] をクリックすると、エラーが発生することがある

BitLocker のコンプライアンスサマリーレポートにドリルダウンし、SSRS レポートの [**戻る**] リンクをクリックすると、エラーがスローされることがあります。

**回避策:**-.

### BitLocker コンピューターのコンプライアンスレポートで暗号強度が正しく表示されない

**[ドライブの暗号化方法を選択**してください] グループポリシーオブジェクトで特定の暗号強度を設定していない場合、暗号強度で既定の128ビット暗号化が使用されている場合でも、構成マネージャーの統合トポロジの BitLocker コンピューターのコンプライアンスレポートでは、暗号強度に対して "unknown" が常に表示されます。 グループポリシーオブジェクトで特定の暗号強度を設定すると、レポートに正しい暗号強度が表示されます。

**回避策:****[ドライブの暗号化方法と暗号強度**のグループポリシーオブジェクトを選択してください] で、常に特定の暗号強度を設定します。

### ドライブの種類別のコンプライアンスの状態の配布構成項目の更新後に古いデータが表示される

SystemCenter2012 ConfigurationManager で MBAM 構成項目を更新すると、BitLocker Enterprise コンプライアンスダッシュボードの [コンプライアンスの状態] バーグラフに、古いバージョンの構成項目からの情報を基にしたデータが表示されます。

**回避策:**-. MBAM 構成項目の変更はサポートされていません。また、レポートは予期したとおりに表示されない可能性があります。

### 強化されたセキュリティ構成により、レポートにエラーメッセージが誤って表示される場合がある

Internet Explorer の [セキュリティ強化の構成] (ESC) が有効になっている場合、MBAM サーバーでレポートを表示しようとすると、"アクセス拒否" というエラーメッセージが表示されることがあります。 既定では、web コンテンツとアプリケーションスクリプトを介して発生する可能性のある攻撃に対してサーバーの脅威が減ることで、サーバーを保護するために ESC が有効になっています。

**回避策:** MBAM サーバーでレポートを表示しようとしたときに "アクセス拒否" というエラーメッセージが表示される場合は、グループポリシーオブジェクトを設定するか、イメージ内の既定値を手動で変更して、強化されたセキュリティ構成を無効にすることができます。 また、ESC が有効になっていない別のコンピューターからレポートを表示することもできます。

### Bitlocker XTS-AES 暗号化アルゴリズムのサポート
Bitlocker は、Windows 10 バージョン1511での XTS 暗号化アルゴリズムのサポートを追加しました。 HF02 を使用すると、MBAM によってこの Bitlocker オプションのクライアントサポートが追加され、HF04 にサーバー側のサポートが追加されました。 ただし、いくつかの既知の制限があります。

* お客様は、同じマシン上の OS とデータボリュームに同じ暗号化強度を使用する必要があります。
異なる暗号化強度が使用されている場合、MBAM は**非準拠**としてコンピューターを報告します。

### セルフサービスポータルによってキー ID エントリに "-" が自動的に追加される
HF02 の場合、MBAM セルフサービスポータルによって、キー ID エントリの '-' が自動的に追加されます。  
**注:** Javascript が有効になるようにサーバーを再構成する必要があります。

### MBAM 2.5 Sp1 レポートが機能しない、または正しく表示されない
SSRS が SQL Server 2016 エディションでホストされている場合、[レポート] ページは適切に表示されません。 
たとえば、ヘルプデスクへの参照-レポートをクリックします。 (強調表示されている部分には "x" が表示されています) これをさらに詳しく調査するには、Fiddler を使用して4.0、レポートをクリックします。

**回避策:** サイトのマスタコードを見ると、X UA モードが IE8 として認識されました。 IE8 が終わりを超えているため、お客様は IE11 を使用しています。 以下のコードの設定を更新します。 これにより、サイトが IE11 のレンダリングテクノロジを利用できるようになります。

    <meta http-equiv="X-UA-Compatible" content="IE=Edge" />

元の設定: 

    <meta http-equiv="X-UA-Compatible" content="IE=8" />


これは、Chrome、Firefox などの他のブラウザーで問題が発生しなかった理由を示しています。



## 関連トピック


[MBAM 2.5 の概要](about-mbam-25.md)

 

## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





