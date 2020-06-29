---
title: MBAM 2.5 グループ ポリシー要件の計画
description: MBAM 2.5 グループ ポリシー要件の計画
author: dansimp
ms.assetid: 82d545dc-3fbf-4b46-b62f-47fe178a7c44
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4beeb9f88f16e7d48d145861c398a90fa29f3491
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823767"
---
# MBAM 2.5 グループ ポリシー要件の計画


以下の情報を使用して、組織内で Microsoft BitLocker 管理および監視 (MBAM) クライアントコンピューターを管理するために使用できる BitLocker プロテクターの種類を決定してください。

## MBAM でサポートされている BitLocker プロテクターの種類


MBAM は、次の種類の BitLocker プロテクターをサポートしています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ドライブまたはボリュームの種類</th>
<th align="left">サポートされている BitLocker プロテクター</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>オペレーティングシステムボリューム</p></td>
<td align="left"><ul>
<li><p><strong>トラステッド プラットフォーム モジュール (TPM)</strong></p></li>
<li><p><strong>TPM + PIN</strong></p></li>
<li><p><strong>TPM + USB キー </strong> – MBAM をインストールする前にオペレーティングシステムのボリュームが暗号化されている場合にのみサポートされます。</p></li>
<li><p><strong>TPM + PIN + USB キーは </strong> - 、mbam をインストールする前にオペレーティングシステムのボリュームが暗号化されている場合にのみサポートされます。</p></li>
<li><p><strong>パスワードは </strong> - 、Windows to Go デバイス、固定データドライブ、windows 8、windows 8.1、TPM を搭載していない windows 10 デバイスでのみサポートされます。</p></li>
<li><p><strong>数値パスワードは </strong> - ボリューム暗号化の一部として自動的に適用され、Windows 7 で FIPS モードを除き、構成する必要はありません。</p></li>
<li><p><strong>データ回復エージェント (DRA)</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>固定データドライブ</p></td>
<td align="left"><ul>
<li><p><strong>パスワード</strong></p></li>
<li><p><strong>自動ロック解除</strong></p></li>
<li><p><strong>数値パスワードは </strong> - ボリューム暗号化の一部として自動的に適用され、Windows 7 で FIPS モードを除き、構成する必要はありません。</p></li>
<li><p><strong>データ回復エージェント (DRA)</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>リムーバブルドライブ</p></td>
<td align="left"><ul>
<li><p><strong>パスワード</strong></p></li>
<li><p><strong>自動ロック解除</strong></p></li>
<li><p><strong>数値パスワードは </strong> - ボリューム暗号化の一部として自動的に適用され、構成する必要はありません。</p></li>
<li><p><strong>データ回復エージェント (DRA)</strong></p></li>
</ul></td>
</tr>
</tbody>
</table>



### 使用済みスペース暗号化の BitLocker ポリシーのサポート

MBAM 2.5 SP1 では、BitLocker グループポリシーによって使用されるスペースの暗号化を有効にすると、MBAM クライアントによって受け入れられます。

このグループポリシー設定は、**オペレーティングシステムドライブでの [ドライブの暗号化の種類の強制**] と呼ばれ、次の GPO ノードにあります。**コンピューターの構成** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **BitLocker ドライブ暗号化** &gt; **オペレーティングシステムドライブ**。 このポリシーを有効にして、**使用領域のみの暗号化**として暗号化の種類を選択した場合、mbam ではポリシーが優先され、BitLocker はボリュームで使用されているディスク領域のみを暗号化します。

## MBAM グループポリシーテンプレートを取得して設定を編集する方法


MBAM グループポリシー設定を構成する準備ができたら、次の操作を行います。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">手順</th>
<th align="left">手順を表示する場所</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="https://go.microsoft.com/fwlink/p/?LinkId=393941" data-raw-source="[How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941)">MDOP グループポリシー (admx) テンプレートの取得方法から MBAM グループポリシーテンプレートをコピー </a> し、グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) を実行できるコンピューターにインストールします。</p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)">MBAM 2.5 グループ ポリシー テンプレートのコピー</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>エンタープライズで使用するグループポリシー設定を構成します。</p></td>
<td align="left"><p><a href="editing-the-mbam-25-group-policy-settings.md" data-raw-source="[Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md)">MBAM 2.5 グループ ポリシー設定の編集</a></p></td>
</tr>
</tbody>
</table>



## MBAM グループポリシー設定の説明


**MDOP MBAM (BitLocker Management)** gpo ノードには、4つのグローバルポリシー設定と4つの子 GPO ノード (**クライアント管理**、**固定ドライブ**、**オペレーティングシステムドライブ**、および**リムーバブルドライブ**) が含まれています。 以下のセクションでは、MBAM グループポリシー設定の設定と提案について説明します。

**重要**  
**BitLocker ドライブ暗号化**ノードのグループポリシー設定を変更しないようにします。または、mbam が正しく動作しません。 MBAM は、 **MDOP mbam (BitLocker Management)** ノードの設定を構成するときに、このノードの設定を自動的に構成します。



### グローバルグループポリシーの定義

以下のセクションでは、mbam グローバルグループポリシー定義について説明します。**コンピューター構成** &gt; **ポリシー** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **MDOP mbam (BitLocker 管理)**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ポリシー名</th>
<th align="left">概要と推奨されるグループポリシー設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ドライブの暗号化方法と暗号強度を選ぶ</p></td>
<td align="left"><p>推奨される構成: <strong> 有効</strong></p>
<p>特定の暗号化方法と暗号強度を使用するように、このポリシーを構成します。</p>
<p>このポリシーが構成されていない場合、BitLocker では、ディフューザー付き AES 128 ビットという既定の暗号化方法が使用されます。</p>
<div class="alert">
<strong>注</strong><br/><p>BitLocker コンピューターのコンプライアンスレポートの問題が発生すると &quot; &quot; 、既定値を使用している場合でも、暗号強度に対して [不明] と表示されます。 この問題を回避するには、この設定を有効にして暗号強度の値を設定してください。</p>
</div>
<div>

</div>
<ul>
<li><p>AES 128 ビットディフューザー付き AES – Windows 7 のみ</p></li>
<li><p>Windows 8、Windows 8.1、Windows 10 用の AES 128</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>再起動時にメモリの上書きを防止する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシーを構成して、再起動時にメモリ内の BitLocker シークレットを上書きせずに、再起動のパフォーマンスを向上させます。</p>
<p>このポリシーが構成されていない場合、コンピューターを再起動すると、BitLocker シークレットがメモリから削除されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>スマートカード証明書の使用規則を検証する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>スマートカード証明書ベースの BitLocker 保護を使用するように、このポリシーを構成します。</p>
<p>このポリシーが構成されていない場合は、既定のオブジェクト識別子1.3.6.1.4.1.311.67.1.1 が証明書の指定に使用されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>組織固有の識別子を指定する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>証明書ベースのデータ回復エージェントまたは BitLocker To Go リーダーを使用するように、このポリシーを構成します。</p>
<p>このポリシーが構成されていない場合、[ <strong> id </strong> ] フィールドは使用されません。</p>
<p>会社でより高いセキュリティの測定が必要な場合は、[id] フィールドを構成して、 <strong> </strong> すべての USB デバイスでこのフィールドセットが設定され、このフィールドがこのグループポリシー設定に合わせて調整されるようにすることができます。</p></td>
</tr>
</tbody>
</table>



### クライアント管理グループポリシーの定義

以下のセクションでは、mbam のクライアント管理ポリシー定義について説明します。**コンピューター構成** &gt; **ポリシー** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **MDOP mbam (BitLocker 管理)** &gt; **クライアントの管理**。

次の表に示すように、スタンドアロンおよび System Center Configuration Manager の統合トポロジに対して同じグループポリシー設定を設定することができます。構成マネージャーの統合トポロジを使用している場合は、「 **Mbam service &gt; Mbam Status reporting service Endpoint の構成**」の設定を無効にします。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ポリシー名</th>
<th align="left">概要と推奨されるグループポリシー設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MBAM サービスを設定する</p></td>
<td align="left"><p>推奨される構成: <strong> 有効</strong></p>
<ul>
<li><p><strong>MBAM Recovery and Hardware service endpoint </strong> 。 MBAM クライアント BitLocker 暗号化管理を有効にするには、この設定を使います。 次の例のようなエンドポイントの場所を入力します。 <strong> http (s)// </strong><em> &lt; mbam 管理と監視サーバー名 &gt; </em><strong> : </strong><em> &lt; web サービスが/MBAMRecoveryAndHardwareService/CoreService.svc にバインドさ &gt; </em><strong> </strong> れているポート。</p></li>
<li><p><strong>保存する BitLocker 回復情報を選択し </strong> ます。 このポリシー設定では、BitLocker 回復情報をバックアップするためのキー回復サービスを構成できます。 また、レポートを収集するためのステータスレポートサービスを構成することもできます。 ポリシーには、BitLocker によって暗号化されたデータを回復するための管理方法が用意されており、重要な情報がないためにデータの損失を防ぐことができます。 状態レポートとキー回復アクティビティは、自動的に、構成されたレポートサーバーの場所に自動的に送信されます。</p>
<p>このポリシー設定を構成しなかった場合、または無効にした場合、キーの回復情報は保存されず、状態レポートとキー回復操作はサーバーに報告されません。 この設定が <strong> [回復パスワードとキーパッケージ] に設定されている場合 </strong> 、回復パスワードとキーパッケージは自動的に、構成されたキー回復サーバーの場所に自動的にバックアップされます。</p></li>
<li><p><strong>クライアントチェックの状態の頻度を分単位で入力し </strong> ます。 このポリシー設定は、クライアントがクライアントコンピューター上の BitLocker 保護ポリシーと状態を確認する頻度を管理します。 このポリシーは、クライアントのコンプライアンスの状態をサーバーに保存する頻度も管理します。 クライアントは、クライアントコンピューター上の BitLocker 保護ポリシーと状態を確認し、構成された頻度でクライアント回復キーもバックアップします。</p>
<p>この頻度は、お客様の会社によって設定された要件に基づいて、コンピューターのコンプライアンスの状態と、クライアント回復キーをバックアップする頻度に基づいて設定します。</p></li>
<li><p><strong>MBAM Status reporting service エンドポイント:</strong></p>
<p><strong>スタンドアロンのトポロジの MBAM の場合 </strong> : Mbam クライアント BitLocker 暗号化管理を有効にするには、この設定を構成する必要があります。</p>
<p>次の例のようなエンドポイントの場所を入力します。</p>
<p><strong>http (s)/ </strong><em> &lt; mbam 管理と監視サーバー名 &gt; </em><strong> : </strong><em> &lt; web サービスが/MBAMComplianceStatusService/StatusReportingService.svc にバインドされているポート &gt; </em><strong></strong></p>
<p><strong>Configuration Manager の統合トポロジの MBAM の場合 </strong> : この設定を無効にします。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>ユーザーの免税ポリシーを構成する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシー設定では、ユーザーに対して BitLocker 暗号化の除外を要求するように指示する web サイトアドレス、メールアドレス、または電話番号を構成できます。</p>
<p>このポリシー設定を有効にして、web サイトのアドレス、メールアドレス、または電話番号を指定すると、除外を適用して BitLocker 保護を適用する方法の手順を示すダイアログボックスが表示されます。 ユーザーに対して BitLocker 暗号化の適用除外を有効にする方法については、「 <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-25.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-25.md)"> ユーザー Bitlocker 暗号化の除外を管理する方法」を参照してください </a> 。</p>
<p>このポリシー設定を無効にするか、未構成にした場合、除外要求の手順はユーザーに表示されません。</p>
<div class="alert">
<strong>注</strong><br/><p>ユーザーの除外は、コンピューターごとではなく、ユーザーごとに管理されます。 複数のユーザーが同じコンピューターにログオンしていて、1人のユーザーが除外されていない場合、コンピューターは暗号化されます。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>カスタマーエクスペリエンス向上プログラムの構成</p></td>
<td align="left"><p>推奨される構成: <strong> 有効</strong></p>
<p>このポリシー設定では、MBAM ユーザーがカスタマーエクスペリエンス向上プログラムに参加する方法を構成できます。 このプログラムでは、コンピューターのハードウェアに関する情報を収集し、ユーザーの作業を中断することなく MBAM を使用する方法について説明します。 この情報は、Microsoft が改善する MBAM 機能を特定するのに役立ちます。 Microsoft は、MBAM ユーザーを特定したり連絡したりするためにこの情報を使用することはありません。</p>
<p>このポリシー設定を有効にした場合、ユーザーはカスタマーエクスペリエンス向上プログラムに参加できます。</p>
<p>このポリシー設定を無効にすると、ユーザーはカスタマーエクスペリエンス向上プログラムに参加できなくなります。</p>
<p>このポリシー設定を構成しない場合、ユーザーはカスタマーエクスペリエンス向上プログラムに参加するためのオプションを利用できます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>セキュリティポリシーのリンクの URL を指定する</p></td>
<td align="left"><p>推奨される構成: <strong> 有効</strong></p>
<p>このポリシー設定を使用して、エンドユーザーに "会社セキュリティポリシー" という名前のリンクとして表示される URL を指定し &quot; ます。 &quot;このリンクは、会社の内部セキュリティポリシーを指し、暗号化要件に関する情報をエンドユーザーに提供します。 このリンクは、ユーザーが MBAM によってドライブを暗号化するように求められた場合に表示されます。</p>
<p>このポリシー設定を有効にした場合は、セキュリティポリシーのリンクの URL を構成することができます。</p>
<p>このポリシー設定を無効にした場合、または構成しなかった場合、[セキュリティポリシー] リンクはユーザーに表示されません。</p></td>
</tr>
</tbody>
</table>



### 固定ドライブのグループポリシー定義

このセクションでは、Microsoft BitLocker の管理と監視を行うための、次の GPO ノードでの固定ドライブポリシー定義について説明します。**コンピューター構成** &gt; **ポリシー** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **MDOP mbam (BitLocker 管理)** &gt; **固定ドライブ**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ポリシー名</th>
<th align="left">概要と推奨されるグループポリシー設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>固定データドライブの暗号化設定</p></td>
<td align="left"><p>推奨される構成: <strong> 有効</strong></p>
<p>このポリシー設定では、固定データドライブを暗号化する必要があるかどうかを管理できます。</p>
<p>オペレーティングシステムのボリュームが暗号化されている必要がある場合は、[ <strong> 固定データドライブを自動ロック解除する] をクリックし </strong> ます。</p>
<p>このポリシーを有効にする場合は、 <strong> </strong> 固定データドライブの自動ロック解除を有効にするか、または要求しない限り、固定データドライブのパスワードの使用を構成しないようにしてください。</p>
<p>固定データドライブの自動ロック解除を使用する必要がある場合は、暗号化されるようにオペレーティングシステムのボリュームを構成する必要があります。</p>
<p>このポリシー設定を有効にした場合、ユーザーはすべての固定データドライブを BitLocker 保護の下に置く必要があり、データドライブは暗号化されます。</p>
<p>このポリシー設定を構成しない場合、ユーザーは、固定データドライブを BitLocker による保護の対象として配置する必要はありません。 固定データドライブが暗号化された後にこのポリシーを適用すると、MBAM エージェントは暗号化された固定データドライブを解読します。</p>
<p>このポリシー設定を無効にした場合、ユーザーは固定データドライブを BitLocker 保護下に配置することはできません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>BitLocker で保護されていない固定ドライブへの書き込みアクセスを拒否する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシー設定は、固定データドライブをコンピューター上で書き込み可能にするために BitLocker の保護が必要かどうかを決定します。 このポリシー設定は、BitLocker を有効にすると適用されます。</p>
<p>ポリシーが構成されていない場合、コンピューター上のすべての固定データドライブは読み取り/書き込みアクセス許可を使用してマウントされます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>BitLocker で保護された固定ドライブへのアクセスを以前のバージョンの Windows から許可する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシーを有効にすると、Windows Server 2008、Windows Vista、Windows XP、または Windows XP SP2 を実行しているコンピューターで、FAT ファイルシステムで固定されたドライブのロックを解除し、表示することができます。</p>
<p>ポリシーが有効になっているか、構成されていない場合は、FAT ファイルシステムで書式設定された固定ドライブのロックを解除することができ、windows Server 2008、Windows Vista、Windows XP SP3、または Windows XP SP2 を実行しているコンピューターでそれらのコンテンツを表示できます。 これらのオペレーティングシステムは、BitLocker で保護されたドライブに対して読み取り専用のアクセス許可を持っています。</p>
<p>ポリシーが無効になっている場合、FAT ファイルシステムでフォーマットされている固定ドライブのロックを解除することはできません。 Windows Server 2008、Windows Vista、Windows XP SP3、または Windows XP SP2 を実行しているコンピューターでは、これらのコンテンツを表示することはできません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>固定ドライブのパスワードの使用を構成する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシーを使って、BitLocker で保護された固定データドライブのロックを解除するためにパスワードが必要かどうかを指定します。</p>
<p>このポリシー設定を有効にした場合、ユーザーは定義した要件を満たすパスワードを構成できます。 BitLocker を使用すると、ユーザーはドライブで利用可能な任意のプロテクターでドライブのロックを解除することができます。</p>
<p>これらの設定は、ボリュームのロックを解除しても、BitLocker を有効にするときに適用されます。</p>
<p>このポリシー設定を無効にした場合、ユーザーはパスワードを使用することはできません。</p>
<p>ポリシーが構成されていない場合、パスワードは既定の設定でサポートされます。パスワードの複雑さの要件は含まれず、8文字しか必要ありません。</p>
<p>セキュリティを高めるには、このポリシーを有効にして、[ <strong> 固定データドライブにパスワードを要求する] を選び </strong> 、[パスワードの複雑さを要求する] をクリックして、 <strong> </strong> <strong> 必要なパスワードの最小の長さを設定し </strong> ます。</p>
<p>このポリシー設定を無効にした場合、ユーザーはパスワードを使用することはできません。</p>
<p>このポリシー設定を構成しない場合、パスワードは既定の設定でサポートされます。これにはパスワードの複雑さの要件は含まれず、8文字しか必要ありません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>BitLocker で保護された固定ドライブの回復方法を選択する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>BitLocker データ回復エージェントを有効にする、または Active Directory ドメインサービス (AD DS) に BitLocker 回復情報を保存するには、このポリシーを構成します。</p>
<p>ポリシーが構成されていない場合、BitLocker データ回復エージェントは許可され、回復情報は AD DS にバックアップされません。 MBAM は、AD DS にバックアップするための回復情報を必要としません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>暗号化ポリシーの適用設定</p></td>
<td align="left"><p>推奨される構成: <strong> 有効</strong></p>
<p>このポリシー設定を使用して、MBAM ポリシーへの準拠を強制されるまで固定データドライブが準拠していない日数を構成します。 ユーザーは、猶予期間後に、必要な操作を延期したり、除外を要求したりすることはできません。 猶予期間は、固定データドライブが準拠していないと判断された場合に始まります。 ただし、固定データドライブポリシーは、オペレーティングシステムドライブに準拠するまでは適用されません。</p>
<p>猶予期間の経過後も固定データドライブが準拠していない場合、ユーザーには、除外を延期または要求するオプションはありません。 暗号化プロセスでユーザーの入力が必要な場合は、ユーザーが必要な情報を提供するまで閉じることができないダイアログボックスが表示されます。</p>
<p>「0」と入力して <strong> </strong> 、 <strong> </strong> オペレーティングシステムドライブの猶予期間が終了した直後に暗号化処理が開始されるように、[固定ドライブの猶予期間 (分単位) を構成します。</p>
<p>この設定を無効にした場合、または構成しなかった場合、ユーザーは MBAM ポリシーに準拠することは強制されません。</p>
<p>プロテクターを追加するためにユーザーの操作が必要ない場合は、猶予期間が終了した後にバックグラウンドで暗号化が開始されます。</p></td>
</tr>
</tbody>
</table>



### オペレーティングシステムドライブのグループポリシーの定義

このセクションでは、Microsoft BitLocker の管理と監視に使用するオペレーティングシステムドライブのポリシー定義を次の GPO ノードで説明します。**コンピューター構成** &gt; **ポリシー** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **MDOP mbam (BitLocker 管理)** &gt; **オペレーティングシステムドライブ**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ポリシー名</th>
<th align="left">概要と推奨されるグループポリシー設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>オペレーティングシステムドライブの暗号化の設定</p></td>
<td align="left"><p>推奨される構成: <strong> 有効</strong></p>
<p>このポリシー設定では、オペレーティングシステムドライブを暗号化する必要があるかどうかを管理できます。</p>
<p>セキュリティを高めるには、 <strong> </strong> &gt; <strong> </strong> &gt; <strong> </strong> TPM + PIN プロテクターを使って、システムの電源管理のスリープ設定で次のポリシー設定を無効にすることを検討してください。</p>
<ul>
<li><p>スリープ中 (電源に接続されているとき) にスタンバイ状態 (S1 ~ S3) を許可する</p></li>
<li><p>スリープ中 (バッテリー) でスタンバイ状態 (S1-S3) を許可する</p></li>
</ul>
<p>Microsoft Windows 8 以降を実行していて、TPM がないコンピューターで BitLocker を使用する場合は、[ <strong> 互換性のある tpm なしで bitlocker を許可する] チェックボックスをオンにし </strong> ます。 このモードでは、起動時にパスワードを入力する必要があります。 パスワードを忘れた場合は、BitLocker の回復オプションのいずれかを使ってドライブにアクセスする必要があります。</p>
<p>互換性のある TPM が搭載されたコンピューターでは、2種類の認証方法を使用して、暗号化されたデータの保護を強化できます。 コンピューターの起動時には、TPM のみを認証に使うことができます。また、暗証番号 (PIN) の入力を要求することもできます。</p>
<p>このポリシー設定を有効にした場合、ユーザーは、オペレーティングシステムドライブを [BitLocker 保護] の下に置く必要があり、ドライブは暗号化されます。</p>
<p>このポリシーを無効にした場合、ユーザーは、オペレーティングシステムドライブを BitLocker で保護することはできません。 オペレーティングシステムドライブが暗号化された後にこのポリシーを適用すると、ドライブは暗号化解除されます。</p>
<p>このポリシーを構成しない場合、オペレーティングシステムドライブは、BitLocker による保護の下に配置する必要はありません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>スタートアップの拡張 Pin を許可する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシー設定を使用して、強化されたスタートアップ Pin が BitLocker と共に使用されるかどうかを構成します。 拡張されたスタートアップ Pin では、大文字と小文字、記号、数字、スペースなどの文字を使用できます。 このポリシー設定は、BitLocker を有効にすると適用されます。</p>
<p>このポリシー設定を有効にすると、すべての新しい BitLocker スタートアップ Pin が設定され、エンドユーザーは拡張 Pin を作成できるようになります。 ただし、プレブート環境では、すべてのコンピューターで拡張ピンがサポートされているわけではありません。 使用を有効にする前に、管理者がこの機能に対応しているかどうかを評価することを強くお勧めします。</p>
<p><strong> </strong> プレブート環境に入力できる文字数を制限するコンピューターとの互換性を向上させるには、[ASCII のみの pin を使用する] チェックボックスをオンにします。</p>
<p>このポリシー設定を無効にした場合、または構成しなかった場合は、強化された Pin は使用されません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>BitLocker で保護されたオペレーティングシステムドライブの回復方法を選択する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>BitLocker データ回復エージェントを有効にする、または Active Directory ドメインサービス (AD DS) に BitLocker 回復情報を保存するには、このポリシーを構成します。</p>
<p>このポリシーが構成されていない場合、データ回復エージェントは許可され、回復情報は AD DS にバックアップされません。</p>
<p>MBAM 操作では、AD DS に回復情報をバックアップする必要はありません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>オペレーティングシステムドライブのパスワードの使用を構成する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>BitLocker で保護されたオペレーティングシステムドライブのロックを解除するために使用するパスワードの制約を設定するには、このポリシー設定を使います。 オペレーティングシステムドライブで TPM 以外のプロテクターが許可されている場合は、パスワードのプロビジョニング、パスワードの複雑さの要件の適用、パスワードの最小文字数の構成を行うことができます。 複雑さの要件の設定を有効にするには、[コンピューターの構成] の &quot; &quot; [Windows 設定] の [アカウントポリシー] のパスワードポリシーにある複雑さの要件を満たすように、グループポリシーの設定を有効にする必要があり &gt; &gt; &gt; &gt; ます。</p>
<div class="alert">
<strong>注</strong><br/><p>これらの設定は、ボリュームのロックを解除しても、BitLocker を有効にするときに適用されます。 BitLocker では、ドライブで利用できる任意のプロテクターでドライブのロックを解除することができます。</p>
</div>
<div>

</div>
<p>このポリシー設定を有効にした場合、ユーザーは定義した要件を満たすパスワードを構成できます。 パスワードに複雑さの要件を適用するには、[パスワードの複雑さを要求する] をクリックし <strong> </strong> ます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>BIOS ベースのファームウェア構成の TPM プラットフォーム検証プロファイルを構成する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシー設定では、コンピューター&#39;s のトラステッドプラットフォームモジュール (TPM) セキュリティハードウェアが BitLocker 暗号化キーをセキュリティで保護する方法を構成できます。 このポリシー設定は、コンピューターに互換性のある TPM が搭載されていない場合、または TPM 保護で BitLocker が既に有効になっている場合は適用されません。</p>
<div class="alert">
<strong>重要</strong><br/><p>このグループポリシー設定は、BIOS 構成のコンピューター、または、互換性サービスモジュール (CSM) が有効になっている UEFI ファームウェアを使用しているコンピューターにのみ適用されます。 ネイティブの UEFI ファームウェア構成を使用するコンピューターは、異なる値をプラットフォーム構成レジスタ (Pcr) に保存します。 ネイティブの uefi &quot; ファームウェア構成用に tpm プラットフォーム検証プロファイルを構成 &quot; するグループポリシー設定を使用して、ネイティブの uefi ファームウェアを使用するコンピューターの tpm PCR プロファイルを構成します。</p>
</div>
<div>

</div>
<p>BitLocker を有効にする前にこのポリシー設定を有効にした場合は、BitLocker で暗号化されたオペレーティングシステムドライブへのアクセスをロック解除する前に、TPM が検証するブートコンポーネントを構成できます。 BitLocker の保護が有効になっている間に、これらのコンポーネントのいずれかが変更された場合、TPM は暗号化キーを解放してドライブのロックを解除します。代わりに、コンピューターは BitLocker 回復コンソールを表示し、回復パスワードまたは回復キーを指定してドライブのロックを解除する必要があります。</p>
<p>このポリシー設定を無効にするか、未構成にした場合、BitLocker では、既定のプラットフォーム検証プロファイルまたはセットアップスクリプトで指定されたプラットフォーム検証プロファイルが使用されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>TPM プラットフォームの検証プロファイルを構成する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシー設定では、コンピューター&#39;s のトラステッドプラットフォームモジュール (TPM) セキュリティハードウェアが BitLocker 暗号化キーをセキュリティで保護する方法を構成できます。 このポリシー設定は、コンピューターに互換性のある TPM が搭載されていない場合、または TPM 保護で BitLocker が既に有効になっている場合は適用されません。</p>
<p>BitLocker を有効にする前にこのポリシー設定を有効にした場合は、BitLocker で暗号化されたオペレーティングシステムドライブへのアクセスをロック解除する前に、TPM が検証するブートコンポーネントを構成できます。 BitLocker の保護が有効になっている間に、これらのコンポーネントのいずれかが変更された場合、TPM は暗号化キーを解放してドライブのロックを解除します。代わりに、コンピューターは BitLocker 回復コンソールを表示し、回復パスワードまたは回復キーを指定してドライブのロックを解除する必要があります。</p>
<p>このポリシー設定を無効にするか、未構成にした場合、BitLocker では、既定のプラットフォーム検証プロファイルまたはセットアップスクリプトで指定されたプラットフォーム検証プロファイルが使用されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ネイティブの UEFI ファームウェア構成の TPM プラットフォーム検証プロファイルを構成する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシー設定では、コンピューター&#39;s のトラステッドプラットフォームモジュール (TPM) セキュリティハードウェアが BitLocker 暗号化キーをセキュリティで保護する方法を構成できます。 このポリシー設定は、コンピューターに互換性のある TPM が搭載されていない場合、または TPM 保護で BitLocker が既に有効になっている場合は適用されません。</p>
<div class="alert">
<strong>重要</strong><br/><p>このグループポリシー設定は、ネイティブの UEFI ファームウェア構成を使用しているコンピューターにのみ適用されます。</p>
</div>
<div>

</div>
<p>BitLocker を有効にする前にこのポリシー設定を有効にした場合は、BitLocker で暗号化されたオペレーティングシステムドライブへのアクセスをロック解除する前に TPM が検証するブートコンポーネントを構成できます。 BitLocker の保護が有効になっている間に、これらのコンポーネントのいずれかが変更された場合、TPM は暗号化キーを解放してドライブのロックを解除します。代わりに、コンピューターは BitLocker 回復コンソールを表示し、回復パスワードまたは回復キーを指定してドライブのロックを解除する必要があります。</p>
<p>このポリシー設定を無効にするか、未構成にした場合、BitLocker では、既定のプラットフォーム検証プロファイルまたはセットアップスクリプトで指定されたプラットフォーム検証プロファイルが使用されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>BitLocker の回復後にプラットフォームの検証データを再設定する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシー設定を使用して、BitLocker の回復後に Windows を起動したときに、プラットフォームの検証データを更新するかどうかを制御します。</p>
<p>このポリシー設定を有効にした場合、BitLocker の回復後に Windows を起動すると、プラットフォームの検証データが更新されます。 このポリシー設定を無効にした場合、BitLocker の回復後に Windows を起動すると、プラットフォームの検証データは更新されません。 このポリシー設定を構成しない場合、BitLocker の回復後に Windows を起動すると、プラットフォームの検証データが更新されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>強化されたブート構成データの入力規則プロファイルを使用する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシー設定では、プラットフォームの検証中に確認する特定のブート構成データ (BCD) 設定を選ぶことができます。</p>
<p>このポリシー設定を有効にした場合、その他の設定を追加したり、既定の設定を削除したりすることができます。 このポリシー設定を無効にすると、Windows 7 で使用される既定の BCD プロファイルと同じように、コンピューターは BCD プロファイルに戻ります。 このポリシー設定を構成しない場合、コンピューターは既定の Windows BCD 設定を確認します。</p>
<div class="alert">
<strong>注</strong><br/><p>保護されたブート構成データ (BCD) 整合性検証のために BitLocker がセキュリティで保護されたブート構成データ (BCD) を使用している場合、[整合性を検証するためにセキュアブートを許可する] ポリシーで定義されているように、[強化された &quot; &quot; &quot; ブート構成データの入力規則] &quot;</p>
</div>
<div>

</div>
<p>ブートデバッグを制御する設定 (0x16000010) は常に検証され、指定されたフィールドに含まれている場合は効果がありません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>暗号化ポリシーの適用設定</p></td>
<td align="left"><p>推奨される構成: <strong> 有効</strong></p>
<p>このポリシー設定を使用して、ユーザーがオペレーティングシステムドライブの MBAM ポリシーに準拠して延期できる日数を構成します。 猶予期間は、オペレーティングシステムが最初に準拠していないと検出されたときに始まります。 この猶予期間の期限が切れた後は、ユーザーは必要な操作を延期したり、除外を要求したりすることはできません。</p>
<p>暗号化プロセスでユーザーの入力が必要な場合は、ユーザーが必要な情報を提供するまで閉じることができないダイアログボックスが表示されます。</p>
<p>この設定を無効にした場合、または構成しなかった場合、ユーザーは MBAM ポリシーに準拠することは強制されません。</p>
<p>プロテクターを追加するためにユーザーの操作が必要ない場合は、猶予期間が終了した後にバックグラウンドで暗号化が開始されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>プレブート回復メッセージと URL を構成する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシー設定を有効にして、カスタム回復メッセージを構成するか、OS ドライブがロックされているときにプレブートの BitLocker 回復画面に表示される URL を指定します。 この設定は、Windows 10 を実行しているクライアントコンピューターでのみ使用できます。</p>
<p>このポリシーが有効になっている場合は、プレブート回復メッセージに対して次のいずれかのオプションを選ぶことができます。</p>
<ul>
<li><p><strong>[カスタム回復メッセージを使う] </strong> : プレブートの BitLocker 回復画面にカスタムメッセージを含めるには、このオプションを選択します。 [ <strong> カスタム回復メッセージ] オプション </strong> ボックスに、表示するメッセージを入力します。 回復 URL も指定する場合は、カスタム回復メッセージの一部として含めます。</p></li>
<li><p><strong>[カスタム回復 URL を使用する] </strong> : プレブートの BitLocker 回復画面に表示される既定の URL を置き換えるには、このオプションを選択します。 [ <strong> カスタム回復 url] オプション </strong> ボックスに、表示する url を入力します。</p></li>
<li><p><strong>[既定の回復メッセージと URL を使用 </strong> する]: 既定の bitlocker 回復メッセージと url をプレブートの bitlocker 回復画面に表示するには、このオプションを選択します。 以前にカスタム回復メッセージまたは URL を構成していて、既定のメッセージに戻す場合は、このポリシーを有効にして、[ <strong> 既定の回復メッセージと URL を使用する] オプションを選択する必要があり </strong> ます。</p></li>
</ul>
<div class="alert">
<strong>注</strong><br/><p>プリブートでは、すべての文字と言語がサポートされるわけではありません。 カスタムメッセージまたは URL に使用した文字が、プレブートの BitLocker 回復画面で正しく表示されることをテストすることをお勧めします。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



### リムーバブルドライブのグループポリシーの定義

このセクションでは、Microsoft BitLocker の管理と監視を行うためのリムーバブルドライブのグループポリシー定義について説明します。**コンピューター構成** &gt; **ポリシー** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **MDOP mbam (BitLocker 管理)** &gt; **リムーバブルドライブ**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ポリシー名</th>
<th align="left">概要と推奨されるグループポリシー設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>リムーバブルドライブでの BitLocker の使用を制御する</p></td>
<td align="left"><p>推奨される構成: <strong> 有効</strong></p>
<p>このポリシーは、リムーバブルデータドライブでの BitLocker の使用を制御します。</p>
<p>[ <strong> ユーザーがリムーバブルデータドライブに bitlocker 保護を適用することを許可する] をクリックして </strong> 、ユーザーがリムーバブルデータドライブで bitlocker セットアップウィザードを実行できるようにします。</p>
<p>[ <strong> ユーザーがリムーバブルデータドライブ上の bitlocker を一時停止して暗号化を解除することを許可する] をクリックして </strong> 、ユーザーが bitlocker ドライブ暗号化をドライブから削除するか、メンテナンスが実行されているときに暗号化を中断できるようにします。</p>
<p>このポリシーが有効になっている場合、[ <strong> ユーザーにリムーバブルデータドライブへの BitLocker 保護の適用を許可する] をクリックすると、 </strong> Mbam クライアントがリムーバブルドライブに関する回復情報を mbam key recovery サーバーに保存し、パスワードが失われた場合にユーザーがドライブを回復できるようにします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>BitLocker で保護されていないリムーバブル ドライブへの書き込みアクセスを拒否する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシーを有効にして、BitLocker で保護されたドライブに対する書き込みアクセス許可のみを許可します。</p>
<p>このポリシーを有効にすると、コンピューター上のすべてのリムーバブルデータドライブは、書き込み権限が許可される前に暗号化が必要になります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>以前のバージョンの Windows から BitLocker で保護されているリムーバブルドライブへのアクセスを許可する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシーを有効にすると、FAT ファイルシステムを実行しているコンピューターで、windows Server 2008、Windows Vista、Windows XP、または Windows XP SP2 を実行しているコンピューターで、固定ドライブのロックを解除して表示することができます。</p>
<p>このポリシーが構成されていない場合、FAT ファイルシステムで書式設定されたリムーバブルドライブは、Windows Server 2008、Windows Vista、Windows XP (SP3)、または Windows XP SP2 を実行しているコンピューターではロック解除でき、そのコンテンツは表示できます。 これらのオペレーティングシステムは、BitLocker で保護されたドライブに対して読み取り専用のアクセス許可を持っています。</p>
<p>ポリシーが無効になっている場合、FAT ファイルシステムで書式設定されたリムーバブルドライブのロックを解除することはできません。 Windows Server 2008、Windows Vista、Windows XP SP3、または Windows XP SP2 を実行しているコンピューターでは、これらのコンテンツを表示することはできません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>リムーバブルデータドライブのパスワードの使用を構成する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシーを有効にして、リムーバブルデータドライブのパスワード保護を構成します。</p>
<p>このポリシーが構成されていない場合、パスワードは、パスワードの複雑さの要件を含まず、8文字のみを必要とする既定の設定でサポートされます。</p>
<p>セキュリティ強化のために、このポリシーを有効にして <strong> 、[リムーバブルデータドライブにパスワードを要求する] を選び </strong> 、[パスワードの複雑さを要求する] をクリックし、 <strong> </strong> 推奨される <strong> パスワードの最小文字数を設定 </strong> することができます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>BitLocker で保護されたリムーバブルドライブの回復方法を選択する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>BitLocker データ回復エージェントを有効にする、または Active Directory ドメインサービス (AD DS) に BitLocker 回復情報を保存するには、このポリシーを構成します。</p>
<p>[未構成] に設定すると、 <strong> </strong> データ回復エージェントが許可され、回復情報は AD DS にバックアップされません。</p>
<p>MBAM 操作では、AD DS に回復情報をバックアップする必要はありません。</p></td>
</tr>
</tbody>
</table>




## 関連トピック


[MBAM 2.5 に対応する環境の準備](preparing-your-environment-for-mbam-25.md)

[MBAM 2.5 展開の前提条件](mbam-25-deployment-prerequisites.md)


## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。






