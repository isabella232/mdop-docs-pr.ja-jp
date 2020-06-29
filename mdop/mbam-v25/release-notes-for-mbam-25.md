---
title: MBAM 2.5 のリリース ノート
description: MBAM 2.5 のリリース ノート
author: dansimp
ms.assetid: fcaf03e6-5e39-4771-af3c-a3cd468f3961
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4bcc17d6295b14a7f3276146d5630b869b94b7f0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824984"
---
# MBAM 2.5 のリリース ノート


これらのリリースノートを検索するには、Ctrl キーを押しながら F キーを押します。

Microsoft BitLocker 管理と監視 (MBAM) 2.5 をインストールする前に、これらのリリースノートをよくお読みください。 これらのリリースノートには、MBAM を正常にインストールするために必要な情報が含まれており、製品のマニュアルに記載されていない情報が含まれていることがあります。 これらのリリースノートが他の MBAM 2.5 ドキュメントと異なる場合は、最新の変更については、次の点を考慮してください。 これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。

## <a href="" id="---------mbam-2-5-known-issues"></a> MBAM 2.5 の既知の問題


このセクションには、MBAM 2.5 のリリースノートが記載されています。

### Web ブラウザーが管理者として予期せずに実行される

MBAM サーバー構成ツールのヘルプリンクを使用すると、ブラウザーウィンドウが管理者権限で開かれる可能性があります。

**回避策:** Internet Explorer 強化セキュリティの構成 (IESC) を有効にするか、web ブラウザーを閉じてから他のサイトに移動します。

**注** これは、MBAM 2.5 SP1 で修正されています。

 

### <a href="" id="-------------mbam-reports-as-noncompliant-a-client-encrypted-with-aes-256-bit-encryption-keys-and-diffuser"></a> MBAM は、AES 256 ビット暗号化キーとディフューザーで暗号化されたクライアントに準拠していないと報告

コンピューターに MBAM 2.5 クライアントがインストールされていて、AES 256 ビットをディフューザーの暗号強度で使用して暗号化されている場合、mbam コンプライアンスレポートでは、MBAM クライアントは準拠していないと報告されます。

**回避策:**[KB2975636](https://go.microsoft.com/fwlink/?LinkId=511972)に修正プログラムをインストールします。

### <a href="" id="-------------mbam-fails-to-encrypt-a-volume-and-reports-an-error-if-you-set-a-tpm---pin-protector-on-a-tablet-device"></a> Pc で TPM + PIN プロテクターを設定すると、MBAM でボリュームの暗号化に失敗し、エラーが報告される

エンドユーザーがタブレットデバイスで TPM + PIN プロテクターを設定しようとすると、MBAM が暗号化に失敗し、エラーが報告されます。 この問題は、タブレットデバイスがプレブート環境キーボードを持っていないために発生します。

**回避策:**[**タブレットでのプレブートキーボード入力を必要とする BitLocker 認証の有効化**を有効にする] グループポリシー設定 この設定は、BitLocker グループポリシー設定であり、MBAM グループポリシーテンプレートでは使用できません。

### すべてのサービスアカウントにユーザープリンシパル名が必要

MBAM のすべてのサービスアカウントにユーザープリンシパル名 (UPN) を設定する必要があります。 アカウントの UPN の作成に失敗した場合、構成プロセス中に、ユーザーまたはグループが Active Directory で見つからなかったことを示すエラーメッセージが表示されます。

**回避策:** サービスアカウントに UPN を追加します。

### クライアントコンピューターが Microsoft Ajax コンテンツ配信ネットワークにアクセスできない場合は、セルフサービスポータルで追加の構成が必要

クライアントコンピューターに Microsoft Ajax コンテンツ配信ネットワーク (CDN) へのアクセス権がなく、特定の JavaScript ファイルに必要なアクセス権をセルフサービスポータルに提供している場合は、アクセス可能なソースから JavaScript ファイルを参照するようにセルフサービスポータルを構成する必要があります。 クライアントコンピューターが CDN にアクセスできないときにセルフサービスポータルを構成していない場合は、会社名とログオン時に使用したアカウントのみが表示されます。 エラーメッセージは表示されません。

**回避策:** MBAM 2.5 SP1 をインストールします。 または、次の手順に従ってセルフサービスポータルを構成するか、[クライアントコンピューターが Microsoft コンテンツ配信ネットワークにアクセスできないときにセルフサービスポータルを構成する方法](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)に従います。

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

### 使用領域のみの暗号化が正常に動作しない

MBAM クライアントをインストールした後で初めてコンピューターを暗号化する場合、使用領域のみの暗号化を実装するグループポリシー設定を構成していると、MBAM は、ディスクの使用領域だけを暗号化するのではなく、ディスク全体を誤って暗号化します。 MBAM クライアントをインストールするときにのみ使用されるスペースでコンピューターが暗号化されていて、同じグループポリシー設定を構成している場合、MBAM はドライブが正しく暗号化されていることを報告します。ドライブは再暗号化されません。

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

## <a href="" id="hotfixes-and-knowledge-base-articles-for-mbam-2-5-"></a>MBAM 2.5 の修正プログラムとサポート技術情報の記事


次の表は、MBAM 2.5 の修正プログラムとサポート技術情報の記事を示しています。

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
<td align="left"><p>2975636</p></td>
<td align="left"><p>Microsoft BitLocker 管理および監視2.5 の修正プログラムパッケージ1</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2975636/EN-US" data-raw-source="[support.microsoft.com/kb/2975636/EN-US](https://support.microsoft.com/kb/2975636/EN-US)">support.microsoft.com/kb/2975636/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>3015477</p></td>
<td align="left"><p>BitLocker 管理および監視2.5 の修正プログラムパッケージ2</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3015477" data-raw-source="[support.microsoft.com/kb/3015477](https://support.microsoft.com/kb/3015477)">support.microsoft.com/kb/3015477</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>3011022</p></td>
<td align="left"><p>SSRS インスタンスの名前にアンダースコアが含まれている場合、MBAM 2.5 のインストールまたは構成マネージャーのレポートが失敗する</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3011022/EN-US" data-raw-source="[support.microsoft.com/kb/3011022/EN-US](https://support.microsoft.com/kb/3011022/EN-US)">support.microsoft.com/kb/3011022/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2756402</p></td>
<td align="left"><p>MBAM クライアントでイベント ID 4 およびエラーコード0x8004100E が表示されない</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2756402/EN-US" data-raw-source="[support.microsoft.com/kb/2756402/EN-US](https://support.microsoft.com/kb/2756402/EN-US)">support.microsoft.com/kb/2756402/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2639518</p></td>
<td align="left"><p>MBAM で Enterprise またはコンピューターのコンプライアンスレポートを開くときにエラーが発生する</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2639518/EN-US" data-raw-source="[support.microsoft.com/kb/2639518/EN-US](https://support.microsoft.com/kb/2639518/EN-US)">support.microsoft.com/kb/2639518/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2870842</p></td>
<td align="left"><p>SQL Server 2008 での Configuration Manager の統合シナリオ中に MBAM 2.0 セットアップが失敗する</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870842/EN-US" data-raw-source="[support.microsoft.com/kb/2870842/EN-US](https://support.microsoft.com/kb/2870842/EN-US)">support.microsoft.com/kb/2870842/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2975472</p></td>
<td align="left"><p>多くの MBAM クライアントが MBAM 回復データベースに接続されている場合の SQL デッドロック</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2975472/EN-US" data-raw-source="[support.microsoft.com/kb/2975472/EN-US](https://support.microsoft.com/kb/2975472/EN-US)">support.microsoft.com/kb/2975472/EN-US</a></p></td>
</tr>
</tbody>
</table>

 


## 関連トピック


[MBAM 2.5 の概要](about-mbam-25.md)

 

## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





