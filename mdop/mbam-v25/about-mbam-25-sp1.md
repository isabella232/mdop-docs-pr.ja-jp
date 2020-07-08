---
title: MBAM 2.5 SP1 の概要
description: MBAM 2.5 SP1 の概要
author: dansimp
ms.assetid: 6f12e605-44e6-4646-9c20-aee89c8ff0b7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 09/27/2016
ms.openlocfilehash: 41e47e1561629c00d30b45ad2dcd94f37753af5b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823784"
---
# MBAM 2.5 SP1 の概要


MBAM 2.5 SP1 には、BitLocker ドライブ暗号化用の簡素化された管理インターフェイスが用意されています。 BitLocker は、紛失または盗難になったコンピューターのデータ盗難またはデータ漏洩に対する保護を強化します。 BitLocker は、Windows オペレーティングシステムとドライブに保存されているすべてのデータを暗号化し、データドライブを構成します。

## MBAM の概要


MBAM 2.5 SP1 には、次の機能があります。

-   管理者は、企業全体のクライアント コンピューター上のボリュームを暗号化するプロセスを自動化できます。

-   セキュリティ担当者は、個々のコンピューターまたは企業全体の準拠状態をすばやく判断できます。

-   Microsoft System Center Configuration Manager により、一元的なレポートおよびハードウェア管理を行うことができます。

-   ヘルプデスクの作業負荷を減らし、BitLocker PIN と回復キー要求を使ってエンドユーザーを支援します。

-   エンド ユーザーは、セルフ サービス ポータルを使って、暗号化されたデバイスを自分で回復できます。

-   セキュリティ責任者が、重要な情報を回復するためのアクセスを簡単に監査できるようにします。

-   企業データの保護を保証することにより、Windows Enterprise ユーザーがどこにいても作業を継続できるようにします。

MBAM は、企業に対して設定した BitLocker 暗号化ポリシーオプションを適用し、それらのポリシーでクライアントコンピューターのコンプライアンスを監視し、企業および個人のコンピューターの暗号化状態に関するレポートを作成します。 また、ユーザーが PIN やパスワードを忘れた場合や、BIOS またはブートレコードが変更された場合は、MBAM を使用して回復キーの情報にアクセスすることができます。

次のグループは、BitLocker を管理するために MBAM を使用することに関心を持っている可能性があります。

-   管理者、IT セキュリティの専門家、および機密データが承認されずに公開されないように責任を持つコンプライアンス責任者

-   リモートまたは支店でコンピューターのセキュリティを担当する管理者

-   Windows を実行しているクライアントコンピューターに責任を持つ管理者

**注** この MBAM 文書では、BitLocker について詳しくは説明していません。 詳細については、「 [BitLocker ドライブの暗号化の概要](https://go.microsoft.com/fwlink/p/?LinkId=225013)」を参照してください。

 

## <a href="" id="what-s-new-in-mbam-2-5-sp1"></a>MBAM 2.5 SP1 の新機能


このセクションでは、MBAM 2.5 SP1 の新機能について説明します。

### MBAM 2.5 SP1 クライアントで新しくサポートされる言語

以下の追加言語は、MBAM クライアント用の MBAM 2.5 SP1 でサポートされるようになりました (セルフサービスポータルを含む)。

チェコ語 (チェコ共和国) .cs-CZ

デンマーク語 (デンマーク) da-DK

オランダ語 (オランダ) nl-NL

フィンランド語 (フィンランド) fi

ギリシャ語 (ギリシャ) el-GR

ハンガリー語 (ハンガリー) hu-HU

ノルウェー語、ブークモール (ノルウェー) nb-いいえ

ポーランド語 (ポーランド) pl-PL

ポルトガル語 (ポルトガル) の pt-PT

スロバキア語 (スロバキア) sk-SK

スロベニア語 (スロベニア) sl-SI

スウェーデン語 (スウェーデン) sv-SE

トルコ語 (トルコ) tr-TR

MBAM 2.5 および MBAM 2.5 SP1 でのクライアントとサーバーでサポートされているすべての言語の一覧については、「 [mbam 2.5 サポートされる構成](mbam-25-supported-configurations.md)」を参照してください。

### Windows 10 のサポート

MBAM 2.5 SP1 は、以前のバージョンの MBAM でサポートされているものと同じソフトウェアに加えて、Windows 10 および Windows Server 2016 のサポートを追加します。

Windows 10 は、MBAM 2.5 と MBAM 2.5 SP1 の両方でサポートされています。

### Microsoft SQL Server 2014 SP1 のサポート

MBAM 2.5 SP1 は、以前のバージョンの MBAM でサポートされているものと同じソフトウェアに加えて、Microsoft SQL Server 2014 SP1 のサポートを追加します。

### MBAM は別の MSI で出荷されなくなりました

MBAM 2.5 SP1 以降、MBAM 製品には別の MSI が含まれなくなりました。 ただし、製品に含まれている実行可能ファイル (.exe) から MSI を抽出することはできます。

### MBAM は、TPM を所有していない場合に、所有権の認証パスワードを使うことができます

以前は、MBAM が TPM を所有していなかった場合、TPM OwnerAuth を MBAM データベースに預託たりすることはできませんでした。 TPM を所有し、パスワードを保存するために MBAM を構成するには、TPM の自動プロビジョニングを無効にし、クライアントコンピューター上の TPM をクリアする必要がありました。

Windows 8 以上では、MBAM 2.5 SP1 では、TPM を所有していない場合でも OwnerAuth パスワードをエスクローすることができます。 サービスの起動時に、MBAM は、TPM が既に所有されているかどうかを確認して、その場合はオペレーティングシステムからパスワードを要求します。 パスワードは、MBAM データベースに預託たりされます。 また、OwnerAuth がローカルで削除されないように、グループポリシーを設定する必要があります。

Windows 7 では、mbam データベースの TPM OwnerAuth 情報を自動的に設定するために、MBAM は TPM を所有している必要があります。 MBAM が、tpm と Active Directory (AD) のバックアップを所有していない場合は、グループポリシーを使用して tpm の active **directory (ad) データをインポート**するためのコマンドレットを使用して、AD から mbam データベースに Tpm ownerauth をコピーする必要があります。 これは、MBAM データベースに事前設定された5つの新しい PowerShell コマンドレットであり、ボリューム回復と、Active Directory に保存されている TPM 所有者情報が含まれています。

詳細については、「 [Mbam 2.5 セキュリティに関する考慮事項](mbam-25-security-considerations.md#bkmk-tpm)」を参照してください。

### MBAM はロックアウト後に TPM を自動的にロック解除する

TPM 1.2 を実行しているコンピューターでは、ロックアウトの場合に TPM を自動的にロック解除するように MBAM を構成できるようになりました。 TPM のロックアウト自動リセット機能が有効になっている場合、MBAM は、ユーザーがロックされていることを検出し、MBAM データベースから OwnerAuth パスワードを取得して、ユーザーの TPM を自動的にロック解除します。

この機能は、サーバー側とクライアント側のグループポリシーの両方で有効になっている必要があります。 詳細については、「 [Mbam 2.5 セキュリティに関する考慮事項](mbam-25-security-considerations.md#bkmk-autounlock)」を参照してください。

### FIPS に準拠した BitLocker 数値パスワード保護機能のサポート

MBAM 2.5 では、Windows 8.1 オペレーティングシステムを実行しているデバイスで連邦情報処理規格 (FIPS) に準拠した BitLocker 回復キーのサポートが追加されています。 ただし、windows は Windows 7 で FIPS 準拠の回復キーを実装していません。 そのため、Windows 7 デバイスと Windows 8 デバイスでは、回復用のデータ回復エージェント (DRA) プロテクターが必要です。

Windows チームでは、backported FIPS 対応の回復キーがホットフィックスと共にあり、MBAM 2.5 SP1 でもサポートが追加されています。

**注** Windows8 オペレーティングシステムを実行しているクライアントコンピューターには、修正プログラムがその OS に backported れていないため、引き続き DRA プロテクターが必要です。 Windows 7 および Windows 8 コンピューター用の BitLocker ホットフィックスをダウンロードしてインストールするには、「 [bitlocker の管理と2.5 監視を行うための修正プログラムパッケージ 2](https://support.microsoft.com/kb/3015477) 」を参照してください。 DRA の詳細については、「 [BitLocker でデータ回復エージェントを使用する](https://go.microsoft.com/fwlink/?LinkId=393557)」を参照してください。

 

組織で FIPS のコンプライアンスを有効にするには、連邦情報処理標準 (FIPS) のグループポリシー設定を構成する必要があります。 構成手順については、「 [BitLocker グループポリシーの設定](https://go.microsoft.com/fwlink/?LinkId=393560)」を参照してください。

### 新しいグループポリシー設定でプレブート回復メッセージと URL をカスタマイズする

新しいグループポリシー設定で、**プレブート回復メッセージと url を構成**すると、カスタム回復メッセージを構成するか、OS ドライブがロックされているときにプレブート BitLocker 回復画面に表示される URL を指定することができます。 この設定は、Windows 10 を実行しているクライアントコンピューターでのみ使用できます。

このポリシー設定を有効にした場合、プレブート回復メッセージに対して次のいずれかのオプションを選ぶことができます。

-   [**カスタム回復メッセージを使う**]: プレブートの BitLocker 回復画面にカスタムメッセージを含めるには、このオプションを選択します。

-   [**カスタム回復 URL を使用**する]: プレブートの BitLocker 回復画面に表示される既定の URL を置き換えるには、このオプションを選択します。

-   [**既定の回復メッセージと Url を使用**する]: 既定の bitlocker 回復メッセージと url をプレブートの bitlocker 回復画面に表示するには、このオプションを選択します。 以前にカスタム回復メッセージまたは URL を構成していて、既定のメッセージに戻す場合は、このポリシーを有効にして、このオプションを選択する必要があります。

新しいグループポリシーの設定は、次の GPO ノードにあります。**コンピューター構成** &gt; **ポリシー** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **MDOP mbam (BitLocker 管理)** &gt; **オペレーティングシステムドライブ**。 詳細については、「 [MBAM 2.5 グループポリシーの要件の計画](planning-for-mbam-25-group-policy-requirements.md)」を参照してください。

### MBAM 使用領域の暗号化のサポートが追加されました

MBAM 2.5 SP1 では、BitLocker グループポリシーによって使用されるスペースの暗号化を有効にすると、MBAM クライアントによって受け入れられます。

このグループポリシー設定は、**オペレーティングシステムドライブでの [ドライブの暗号化の種類の強制**] と呼ばれ、次の GPO ノードにあります。**コンピューターの構成** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **BitLocker ドライブ暗号化** &gt; **オペレーティングシステムドライブ**。 このポリシーを有効にして、**使用領域のみの暗号化**として暗号化の種類を選択した場合、mbam ではポリシーが優先され、BitLocker はボリュームで使用されているディスク領域のみを暗号化します。

詳細については、「 [MBAM 2.5 グループポリシーの要件の計画](planning-for-mbam-25-group-policy-requirements.md)」を参照してください。

### 暗号化されたハードドライブ向け MBAM クライアントのサポート

MBAM は、Opal と IEEE 1667 標準の TCG 仕様要件を満たす、暗号化されたハードドライブ上の BitLocker をサポートしています。 これらのデバイスで BitLocker が有効になっている場合は、暗号化されたドライブでキーを生成し、管理機能を実行します。 詳細については、「[暗号化されたハードドライブ](https://technet.microsoft.com/library/hh831627.aspx)」を参照してください。

### Spn の登録時に委任構成が不要になった

アプリケーションプールアカウントに登録する Spn の制約付き委任を構成するための要件は、MBAM 2.5 SP1 では必要なくなりました。 ただし、まだ MBAM 2.5 の要件となっています。

### Windows 展開の一部として MBAM を使用して BitLocker を有効にする

MBAM 2.5 SP1 では、PowerShell スクリプトを使って、MBAM サーバーに対して BitLocker ドライブ暗号化とエスクローの回復キーを構成することができます。

詳細については、「 [Windows 展開の一部として MBAM を使用して BitLocker を有効にする方法](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md)」を参照してください。

### セルフサービスポータルは、PowerShell または SSP カスタマイズウィザードを使用してカスタマイズできます。

MBAM 2.5 SP1 の場合、セルフサービスポータルは、カスタマイズウィザードと PowerShell を使用して構成できます。 [MBAM 2.5 Web アプリケーションを構成する方法に](how-to-configure-the-mbam-25-web-applications.md)ついて説明します。

### Web ブラウザーが管理者として意図せずに動作しなくなった

MBAM 2.5 の問題により、サーバー構成ツールのヘルプリンクが表示され、ブラウザーウィンドウが管理者権限で開くようになりました。 この問題は、MBAM 2.5 SP1 で修正されています。

### CDN にアクセスできない場合は、JavaScript ファイルをダウンロードしてセルフサービスポータルを構成する必要がなくなりました

MBAM 2.5 およびそれ以前のバージョンでは、セルフサービスポータルにアクセスしているクライアントがインターネットにアクセスできなかった場合に、セルフサービスポータルの構成に使用される jQuery ファイルを事前に CDN からダウンロードする必要がありました。 MBAM 2.5 SP1 では、すべての JavaScript ファイルが製品に含まれているため、ダウンロードする必要はありません。

### レポートは、レポートビルダー3.0 で開くことができます。

MBAM 2.5 SP1 では、レポートは最新のレポート定義言語スキーマに更新されているため、ユーザーはレポート3.0 ビルダーのレポートを開いてカスタマイズし、レポートファイルを破損せずにすぐに保存することができます。

### 新しい PowerShell コマンドレット

MBAM 2.5 SP1 用の新しい PowerShell コマンドレットを使用すると、データベース、レポート、web アプリケーションなどのさまざまな MBAM 機能を構成して管理できます。 各機能には対応する PowerShell コマンドレットがあり、機能を有効または無効にしたり、機能に関する情報を取得したりすることができます。

MBAM 2.5 SP1 には、次のコマンドレットが実装されています。

-   書き込み-MbamTpmInformation

-   書き込み用の MbamRecoveryInformation

-   読み取り-ADTpmInformation

-   読み取り-ADRecoveryInformation

-   書き込み用の MbamComputerUser

MBAM 2.5 SP1 の Enable-MbamWebApplication およびテスト用の MbamWebApplication コマンドレットには、次のパラメーターが実装されています。

-   DataMigrationAccessGroup

-   TpmAutoUnlock

コマンドレットの詳細については、「 [Mbam 2.5 セキュリティに関する考慮事項](mbam-25-security-considerations.md)」および「 [Microsoft Bitlocker 管理と監視コマンドレットのヘルプ](https://technet.microsoft.com/library/dn720418.aspx)」を参照してください。

### MBAM エージェントでプレゼンテーションモードが検出される

MBAM エージェントは、コンピューターがプレゼンテーションモードになっているときに、その時点で MBAM UI が呼び出されないようにすることができます。

### MBAM エージェントサービスが遅延開始を使用するように構成されるようになりました

インストール後、サービスは、遅延開始を使用するように MBAM エージェントサービスを設定し、Windows を起動するのにかかる時間を減らします。

### ロックされた固定データボリュームは、コンプライアンスとして報告する

"ロックされた固定データ" ボリュームのコンプライアンス計算ロジックは、ボリュームを "準拠" として報告するように変更されましたが、プロテクターの状態と暗号化の状態は "不明" で、コンプライアンスの状態は "ボリュームはロックされています" という情報になります。 以前は、ロックされているボリュームは、"非準拠"、プロテクターの状態が "暗号化"、暗号化の状態が "不明"、暗号化状態の詳細に "不明なエラー" と報告されました。


## MDOP 技術の入手方法


MBAM は Microsoft デスクトップ最適化パック (MDOP) の一部です。 MDOP は、Microsoft ソフトウェアアシュアランスプログラムに含まれています。 Microsoft ソフトウェアアシュアランスプログラムと MDOP の入手方法の詳細については、「 [mdop の入手](https://go.microsoft.com/fwlink/?LinkId=322049)方法」を参照してください。

## MBAM 2.5 SP1 リリースノート


このドキュメントに記載されていない詳細および最新ニュースについては、「 [MBAM 2.5 SP1 のリリースノート](release-notes-for-mbam-25-sp1.md)」を参照してください。

## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。

## 関連トピック


[Microsoft BitLocker Administration and Monitoring 2.5](index.md)

[MBAM 2.5 をお使いになる前に](getting-started-with-mbam-25.md)

 

 





