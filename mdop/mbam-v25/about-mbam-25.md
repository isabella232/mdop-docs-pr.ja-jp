---
title: MBAM 2.5 の概要
description: MBAM 2.5 の概要
author: dansimp
ms.assetid: 1ce218ec-4d2e-4a75-8d1a-68d737a8f3c9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: d4c9ff0bc5ee3f7dc51a56cc428081a7c3783694
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824214"
---
# MBAM 2.5 の概要


Microsoft BitLocker の管理と監視 (MBAM) 2.5 は、BitLocker ドライブ暗号化用の簡素化された管理インターフェイスを提供します。 BitLocker は、紛失または盗難になったコンピューターのデータ盗難またはデータ漏洩に対する保護を強化します。 BitLocker は、Windows オペレーティングシステムボリュームとドライブに保存されているすべてのデータを暗号化し、データドライブを構成します。

## MBAM の概要


MBAM 2.5 には次の機能があります。

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

 

## <a href="" id="what-s-new-in-mbam-2-5"></a>MBAM 2.5 の新機能


このセクションでは、MBAM 2.5 の新機能について説明します。

### Microsoft SQL Server 2014 のサポート

MBAM は、以前のバージョンの MBAM でサポートされているものと同じソフトウェアも、Microsoft SQL Server 2014 のサポートを追加します。

### <a href="" id="-------------mbam-group-policy-templates-downloaded-separately"></a> 別々にダウンロードされた MBAM グループポリシーテンプレート

Mbam グループポリシーテンプレートは、MBAM インストールとは別にダウンロードする必要があります。 以前のバージョンの MBAM では、mbam installer に MBAM ポリシーテンプレートが含まれています。このテンプレートには、BitLocker ドライブ暗号化の MBAM 実装設定を定義する、必要な MBAM 固有のグループポリシーオブジェクト (Gpo) が含まれています。 これらの Gpo は、MBAM インストーラーから削除されています。 次に、MBAM クライアントのインストールを開始する前に、 [MDOP グループポリシー (admx) テンプレートを取得](https://go.microsoft.com/fwlink/p/?LinkId=393941)してサーバーまたはワークステーションにコピーする方法から gpo をダウンロードします。 グループポリシーテンプレートは、サポートされているバージョンの Windows サーバーまたは Windows オペレーティングシステムを実行している任意のサーバーまたはワークステーションにコピーできます。

**重要** **BitLocker ドライブ暗号化**ノードのグループポリシー設定を変更しないようにします。または、mbam が正しく動作しません。 [ **MDOP mbam (BitLocker Management)** ] ノードでグループポリシー設定を構成すると、mbam が自動的に Bitlocker ドライブ暗号化設定を構成します。

 

サーバーまたはワークステーションにコピーする必要があるテンプレートファイルは、次のとおりです。

-   BitLockerManagement

-   BitLockerManagement の admx

-   BitLockerUserManagement

-   BitLockerUserManagement。 admx

目的に合った場所にテンプレートファイルをコピーします。 言語固有のファイルの場合、言語固有のフォルダーにコピーする必要があります。そのためには、ファイルを表示するためにグループポリシー管理コンソールが必要です。

- テンプレートファイルをサーバーまたはワークステーションにローカルにインストールするには、次のいずれかの場所にファイルをコピーします。

  <table>
  <colgroup>
  <col width="50%" />
  <col width="50%" />
  </colgroup>
  <thead>
  <tr class="header">
  <th align="left">ファイルの種類</th>
  <th align="left">ファイルの場所</th>
  </tr>
  </thead>
  <tbody>
  <tr class="odd">
  <td align="left"><p>ニュートラル言語 (admx)</p></td>
  <td align="left"><p><em>% systemroot% </em> \ ポリシーの定義</p></td>
  </tr>
  <tr class="even">
  <td align="left"><p>言語固有の (adml)</p></td>
  <td align="left"><p><em>% systemroot% </em> \ policydefinitions [ <em> MUIculture </em> ] (たとえば、米国英語言語固有のファイルは、 <em> % systemroot% &lt; /em ポリシー定義に保存されます &gt; )</p></td>
  </tr>
  </tbody>
  </table>

     

- ドメイン内のすべてのグループポリシー管理者がテンプレートを利用できるようにするには、ドメインコントローラー上の次のいずれかの場所にファイルをコピーします。

  <table>
  <colgroup>
  <col width="50%" />
  <col width="50%" />
  </colgroup>
  <thead>
  <tr class="header">
  <th align="left">ファイルの種類</th>
  <th align="left">ドメインコントローラーファイルの場所</th>
  </tr>
  </thead>
  <tbody>
  <tr class="odd">
  <td align="left"><p>ニュートラル言語 (admx)</p></td>
  <td align="left"><p><em>% systemroot% </em> sysvol\domain\policies\PolicyDefinitions</p></td>
  </tr>
  <tr class="even">
  <td align="left"><p>言語固有の (adml)</p></td>
  <td align="left"><p><em>% systemroot% </em> \sysvol\domain\policies\PolicyDefinitions [ <em> MUIculture </em> ] (たとえば、米国英語の言語固有のファイルは <em> % systemroot% \sysvol\domain\policies\PolicyDefinitions\en-us に保存されます </em> )</p></td>
  </tr>
  </tbody>
  </table>

     

テンプレートファイルの詳細については、「[グループポリシーの ADMX ファイルを管理する](https://go.microsoft.com/fwlink/?LinkId=392818)」を参照してください。

### オペレーティングシステムと固定データドライブで暗号化ポリシーを適用する機能

MBAM 2.5 では、オペレーティングシステムと固定データドライブについて、組織内のコンピューターの暗号化ポリシーを適用し、MBAM 暗号化ポリシーに準拠するために要件の延期を要求できる日数を制限できます。

暗号化ポリシーの強制を構成できるようにするため、[暗号化ポリシーの強制設定] と呼ばれる新しいグループポリシー設定が、オペレーティングシステムドライブと固定データドライブに追加されています。 このポリシーについては、次の表を参照してください。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">グループ ポリシー設定</th>
<th align="left">説明</th>
<th align="left">この設定を構成するために使用されるグループポリシーノード</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>暗号化ポリシーの適用設定 (オペレーティングシステムドライブ)</p></td>
<td align="left"><p>この設定では、[オペレーティングシステムドライブの猶予期間の日数を設定する] オプションを使用して、 <strong> </strong> 猶予期間を構成します。</p>
<p>猶予期間は、ドライブが非準拠として検出された後、エンドユーザーが、使用しているオペレーティングシステムドライブの MBAM ポリシーに準拠することを可能にする日数を指定します。</p>
<p>設定された猶予期間の有効期限が切れた後は、ユーザーは必要な操作を延期したり、除外を要求したりすることはできません。</p>
<p>ユーザーの操作が必要な場合 (たとえば、トラステッドプラットフォームモジュール (TPM) + PIN を使用している場合、またはパスワードプロテクターを使用している場合) は、ダイアログボックスが表示され、ユーザーが必要な情報を入力するまで閉じることはできません。 プロテクターが TPM のみの場合は、ユーザー入力なしで暗号化がバックグラウンドで直ちに開始されます。</p>
<p>ユーザーは、BitLocker 暗号化ウィザードを使って、除外を要求することはできません。 代わりに、ヘルプデスクに問い合わせるか、組織が除外要求に使用するプロセスを使用する必要があります。</p></td>
<td align="left"><p>コンピューター構成 &gt; ポリシー &gt; 管理用テンプレート &gt; Windows コンポーネント &gt; MDOP Mbam (BitLocker 管理) &gt; オペレーティングシステムドライブ</p></td>
</tr>
<tr class="even">
<td align="left"><p>暗号化ポリシーの適用設定 (固定データドライブ)</p></td>
<td align="left"><p>この設定では、[固定ドライブの猶予期間の日数を設定する] オプションを使用して、 <strong> </strong> 猶予期間を構成します。</p>
<p>猶予期間は、ドライブが非準拠として検出された後、エンドユーザーが、固定ドライブの MBAM ポリシーに準拠することを延期できる日数を指定します。</p>
<p>猶予期間は、固定ドライブが準拠していないと判断されたときに始まります。 自動ロック解除を使用している場合は、オペレーティングシステムドライブが準拠するまでポリシーは適用されません。 ただし、自動ロック解除を使っていない場合は、オペレーティングシステムドライブが完全に暗号化される前に、固定データドライブの暗号化が開始されることがあります。</p>
<p>設定された猶予期間の有効期限が切れた後は、ユーザーは必要な操作を延期したり、除外を要求したりすることはできません。 ユーザーの操作が必要な場合は、ダイアログボックスが表示され、ユーザーが必要な情報を提供するまでそのダイアログボックスを閉じることはできません。</p></td>
<td align="left"><p>コンピューター構成 &gt; ポリシー &gt; 管理用テンプレート &gt; Windows コンポーネント &gt; MDOP Mbam (BitLocker 管理) &gt; 固定ドライブ</p></td>
</tr>
</tbody>
</table>

 

### BitLocker ドライブ暗号化ウィザードの URL を指定して、セキュリティポリシーをポイントする機能

新しいグループポリシー設定である [**セキュリティポリシー] リンクの url を指定**すると、[**会社セキュリティポリシー**] というリンクとしてエンドユーザーに表示される url を構成することができます。 このリンクは、MBAM がユーザーにボリュームの暗号化を要求したときに表示されます。

このポリシー設定を有効にした場合、**会社のセキュリティポリシー**のリンクの URL を構成することができます。 このポリシー設定を無効にした場合、または構成しなかった場合、[**会社セキュリティポリシー** ] リンクはユーザーに表示されません。

新しいグループポリシー設定は、次の GPO ノードにあります。**コンピューター構成** &gt; **ポリシー** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **MDOP mbam (BitLocker 管理) &gt; クライアントの管理**。

### FIPS 準拠の回復キーのサポート

MBAM 2.5、Windows 8.1 オペレーティングシステムを実行しているデバイスで連邦情報処理標準 (FIPS) に準拠する BitLocker 回復キーがサポートされています。 回復キーが以前のバージョンの Windows で FIPS に準拠していませんでした。 この機能拡張により、エンドユーザーが PIN またはパスワードを忘れた場合やコンピューターのロックを解除した場合に、セルフサービスポータルまたは管理と監視の Web サイト (ヘルプデスク) を使ってドライブを回復できるため、FIPS のコンプライアンスが必要な組織内のドライブの回復プロセスが向上します。 新しい FIPS コンプライアンス機能は、パスワード保護機能に拡張されません。

組織で FIPS のコンプライアンスを有効にするには、連邦情報処理標準 (FIPS) のグループポリシー設定を構成する必要があります。 構成手順については、「 [BitLocker グループポリシーの設定](https://go.microsoft.com/fwlink/?LinkId=393560)」を参照してください。

Windows8 または Windows7 オペレーティングシステムを実行しているクライアントコンピューターで、[インストール済みの BitLocker 修正プログラム](https://support.microsoft.com/kb/3015477)を使わない場合、IT 管理者は、FIPS に準拠している環境でデータ回復エージェント (DRA) プロテクターを使い続けることができます。 DRA の詳細については、「 [BitLocker でデータ回復エージェントを使用する](https://go.microsoft.com/fwlink/?LinkId=393557)」を参照してください。

Windows 7 および Windows 8 コンピューター用の BitLocker ホットフィックスをダウンロードしてインストールするには、「 [bitlocker の管理と2.5 監視を行うための修正プログラムパッケージ 2](https://support.microsoft.com/kb/3015477) 」を参照してください。

### 高可用性展開のサポート

MBAM は、標準の 2 server および Configuration Manager の統合トポロジに加えて、次の高可用性シナリオをサポートしています。

-   SQL Server AlwaysOn 可用性グループ

-   SQL Server クラスタリング

-   ネットワーク負荷分散 (NLB)

-   SQL Server のミラーリング

-   ボリュームシャドウコピーサービス (VSS) バックアップ

これらの機能の詳細については、「 [MBAM 2.5 の高可用性の計画](planning-for-mbam-25-high-availability.md)」を参照してください。

### <a href="" id="management-of-roles-for-administration-and-monitoring-website-changed-"></a>管理および監視する Web サイトの役割の管理が変更されました

MBAM 2.5 では、管理と監視の Web サイトへのアクセス権を提供する役割を管理するために、Active Directory ドメインサービス (ADDS) にセキュリティグループを作成する必要があります。 役割によって、特定のセキュリティグループに含まれるユーザーは、レポートを表示したり、エンドユーザーによる暗号化されたドライブの回復を支援したりするなど、web サイトでさまざまなタスクを実行できます。 以前のバージョンの MBAM では、役割はローカルグループを使って管理されていました。

MBAM 2.5 では、以前のバージョンの MBAM で使用されていた "管理者ロール" という用語は、"ロール" という用語に置き換えられます。 また、MBAM 2.5 では、"MBAM System Administrator" ロールは削除されています。

次の表は、AD DS で作成する必要があるセキュリティグループの一覧です。 セキュリティグループには任意の名前を使用できます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ロール</th>
<th align="left">管理と監視の Web サイトでのこのロールのアクセス権</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MBAM ヘルプデスクユーザー</p></td>
<td align="left"><p>MBAM 管理と監視 Web サイトの TPM およびドライブの回復領域へのアクセスを提供します。 これらの領域にアクセスできるユーザーは、いずれかの領域を使用するときにすべてのフィールドに入力する必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM レポートユーザー</p></td>
<td align="left"><p>管理と監視の Web サイトにあるレポートへのアクセスを提供します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM Advanced ヘルプデスクユーザー</p></td>
<td align="left"><p>管理と監視の Web サイトにあるすべての領域へのアクセスを提供します。 このグループのユーザーは、エンドユーザーがドライブを回復するときに、エンドユーザーのドメインとユーザー名ではなく、回復キーだけを入力する必要があります。 ユーザーが MBAM ヘルプデスクユーザーグループのメンバーであり、MBAM Advanced ヘルプデスクユーザーグループのメンバーである場合、MBAM Advanced ヘルプデスクのユーザーグループのアクセス許可は、MBAM [ヘルプデスクユーザー] グループの権限よりも優先されます。</p></td>
</tr>
</tbody>
</table>

 

追加されたセキュリティグループを作成した後で、ユーザーやグループを適切なセキュリティグループに割り当てると、その管理と監視の Web サイトに対して、対応するレベルのアクセスを有効にすることができます。 管理と監視の Web サイトにアクセスするために各ロールを持つユーザーを有効にするには、管理と監視の Web サイトを構成するときに、各セキュリティグループも指定する必要があります。

### MBAM Server 機能を構成するための Windows PowerShell コマンドレット

MBAM 2.5 用の Windows PowerShell コマンドレットを使用すると、MBAM サーバー機能の構成と管理を行うことができます。 各機能に対応する Windows PowerShell コマンドレットが用意されており、機能の有効化または無効化、またはこの機能に関する情報の取得に使うことができます。

Windows PowerShell を使用するための前提条件と前提条件については、「 [Windows Powershell を使用して MBAM 2.5 サーバー機能を構成](configuring-mbam-25-server-features-by-using-windows-powershell.md)する」を参照してください。

**MBAM サーバーソフトウェアをインストールした後に、Windows PowerShell コマンドレットの MBAM 2.5 ヘルプを読み込むには**

1.  Windows PowerShell または Windows PowerShell Integrated Scripting Environment (ISE) を開きます。

2.  「**更新プログラム-ヘルプ-モジュール Microsoft MBAM」と**入力します。

Windows PowerShell for MBAM のヘルプは、次の形式で使用できます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Windows PowerShell ヘルプの形式</th>
<th align="left">詳細情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows PowerShell コマンドプロンプトで、「 <strong> Get-ヘルプ </strong> &lt; <em> コマンドレット」と入力します。</em>&gt;</p></td>
<td align="left"><p>最新の Windows PowerShell コマンドレットをアップロードするには、前のセクションの手順に従って、MBAM の Windows PowerShell ヘルプを読み込む方法を参照してください。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Web ページとしての TechNet の場合</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393498" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393498">https://go.microsoft.com/fwlink/?LinkId=393498</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Word の .docx ファイルとしてダウンロードセンターで</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393497" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393497">https://go.microsoft.com/fwlink/?LinkId=393497</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>.Pdf ファイルとしてダウンロードセンターで</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393499" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393499">https://go.microsoft.com/fwlink/?LinkId=393499</a></p></td>
</tr>
</tbody>
</table>

 

### ASCII 専用および拡張ピンをサポートし、連続する文字や繰り返し文字を防ぐ機能

**スタートアップグループポリシー設定の拡張 Pin を許可する**

[**スタートアップの拡張 pin を許可**する] グループポリシー設定では、拡張されたスタートアップ Pin が BitLocker で使用されるかどうかを構成できます。 強化されたスタートアップ Pin を使用すると、大文字と小文字、記号、数字、スペースなど、フルキーボードでキーを入力できます。 このポリシー設定を有効にすると、設定されているすべての新しい BitLocker スタートアップ Pin が拡張ピンになります。 このポリシー設定を無効にした場合、または構成しなかった場合は、強化された Pin は使用できません。

すべてのコンピューターで、プレブート実行環境 (PXE) での拡張 Pin の入力がサポートされているわけではありません。 組織のためにこのグループポリシー設定を有効にする前に、BitLocker のセットアッププロセス中にシステムの確認を実行して、コンピューターの BIOS で PXE のフルキーボードの使用がサポートされていることを確認します。 詳細については、「 [MBAM 2.5 グループポリシーの要件の計画](planning-for-mbam-25-group-policy-requirements.md)」を参照してください。

**[ASCII のみの Pin を要求する] チェックボックス**

[**スタートアップグループポリシーの拡張 pin の使用を許可**する] グループポリシー設定には、[ **ASCII のみの pin を要求**する] チェックボックスも含まれています。 組織内のコンピューターで、PXE のフルキーボードの使用がサポートされていない場合は、[スタートアップグループポリシー**の拡張 pin を許可**する] チェックボックスをオンにし、[ **ascii のみ**の pin を要求する] チェックボックスをオンにして、拡張された pin に印刷可能な ascii 文字のみを使用するように設定します。

**連続していない、または繰り返さない文字の使用を強制した**

MBAM 2.5 では、エンドユーザーが繰り返しの数値 (1111 など) や連続番号 (1234 など) で構成されるピンを作成することはできません。 エンドユーザーが3つ以上の繰り返しまたは連続した番号を含むパスワードを入力しようとすると、Bitlocker ドライブ暗号化ウィザードでエラーメッセージが表示され、ユーザーが禁止された文字で PIN を入力できなくなります。

### BitLocker コンピューターのコンプライアンスレポートへの DRA 証明書の追加

新しいプロテクター型、データ回復エージェント (DRA) 証明書が、Configuration Manager の BitLocker コンピューターのコンプライアンスレポートに追加されました。 このプロテクターの種類は、オペレーティングシステムドライブに適用され、[**プロテクターの種類**] 列の [**コンピューターの音量**] セクションに表示されます。

### 複数フォレストのサポート展開のサポート

MBAM 2.5 は、次の種類のマルチフォレスト展開をサポートしています。

-   1つのドメインを持つ単一フォレスト

-   1つのツリーと複数のドメインがある単一フォレスト

-   複数のツリーと切り離された名前空間を持つ単一フォレスト

-   中央フォレストトポロジでの複数フォレスト

-   リソースフォレストトポロジ内の複数のフォレスト

フォレストの移行はサポートされません (単一から複数の、複数から単一の、1つのフォレストの間でのリソースなど)、またはアップグレードまたはダウングレードを行うことができます。

複数フォレスト展開で MBAM を展開するための前提条件は、次のとおりです。

-   フォレストは、サポートされているバージョンの Windows Server 上で実行されている必要があります。

-   双方向または一方向の信頼が必要です。 一方向の信頼では、サーバーのドメインがクライアントのドメインを信頼している必要があります。 つまり、サーバーのドメインはクライアントのドメインで示されます。

### 暗号化されたハードドライブ向け MBAM クライアントのサポート

MBAM は、Opal と IEEE 1667 標準の TCG 仕様要件を満たす、暗号化されたハードドライブ上の BitLocker をサポートしています。 これらのデバイスで BitLocker が有効になっている場合は、暗号化されたドライブでキーを生成し、管理機能を実行します。 詳細については、「[暗号化されたハードドライブ](https://technet.microsoft.com/library/hh831627.aspx)」を参照してください。

## MDOP 技術の入手方法


MBAM は Microsoft デスクトップ最適化パック (MDOP) の一部です。 MDOP は、Microsoft ソフトウェアアシュアランスプログラムに含まれています。 Microsoft ソフトウェアアシュアランスプログラムと MDOP の入手方法の詳細については、「 [mdop の入手](https://go.microsoft.com/fwlink/?LinkId=322049)方法」を参照してください。

## <a href="" id="---------mbam-2-5-release-notes"></a> MBAM 2.5 リリースノート


このドキュメントに記載されていない詳細および最新ニュースについては、「 [MBAM 2.5 のリリースノート](release-notes-for-mbam-25.md)」を参照してください。

## MBAM の提案をお寄せください。
- [ここ](https://support.microsoft.com/help/4021566/windows-10-send-feedback-to-microsoft-with-feedback-hub)にフィードバックを送信してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。

## 関連トピック


[Microsoft BitLocker Administration and Monitoring 2.5](index.md)

[MBAM 2.5 をお使いになる前に](getting-started-with-mbam-25.md)

 

 





