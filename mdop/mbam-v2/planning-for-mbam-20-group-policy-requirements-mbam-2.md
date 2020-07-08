---
title: MBAM 2.0 グループ ポリシー要件の計画
description: MBAM 2.0 グループ ポリシー要件の計画
author: dansimp
ms.assetid: f5e19dcb-eb15-4722-bb71-0734b3799eb8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f6092507996fe6f0234178c8b1abae5cea7bf836
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812827"
---
# MBAM 2.0 グループ ポリシー要件の計画


Microsoft BitLocker の管理と監視 (MBAM) クライアントコンピューターを管理するには、組織でサポートする BitLocker プロテクターの種類を考慮し、適用する対応するグループポリシー設定を構成する必要があります。 このトピックでは、Microsoft BitLocker の管理と監視を使用して、エンタープライズで BitLocker ドライブ暗号化を管理するときに使用できるグループポリシー設定について説明します。

MBAM は、オペレーティングシステムドライブ用の BitLocker プロテクターとして、トラステッドプラットフォームモジュール (TPM)、TPM + PIN、TPM + USB キー、TPM + PIN + USB キー、パスワード、数字パスワード、データ回復エージェントの各種類をサポートしています。 パスワードの保護機能がサポートされているのは、Windows To Go デバイスと TPM が搭載されていない Windows 8 デバイスのみです。 MBAM は、MBAM をインストールする前にオペレーティングシステムのボリュームが暗号化されている場合にのみ、TPM + USB キーと TPM + PIN + USB キーの保護機能をサポートします。

MBAM は、固定データドライブ用の BitLocker プロテクター (パスワード、自動ロック解除、数字パスワード、データ回復エージェント) をサポートしています。

数値パスワードプロテクターはボリューム暗号化の一部として自動的に適用されるため、構成する必要はありません。

**重要**  
既定の Windows BitLocker ドライブ暗号化グループポリシーオブジェクト (GPO) の設定は、MBAM では使われず、有効になっている場合は競合する動作が発生する可能性があります。 MBAM を有効にするには、mbam グループポリシーテンプレートをインストールした後でのみ、MBAM グループポリシー設定を定義する必要があります。



拡張されたスタートアップ Pin には、大文字と小文字、数字などの文字を含めることができます。 BitLocker とは異なり、MBAM は拡張ピンでの記号とスペースの使用をサポートしていません。

グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) の MDOP 技術を実行できるコンピューターに MBAM グループポリシーテンプレートをインストールします。 Mbam 機能を有効にする gpo 設定を編集するには、まず、mbam グループポリシーテンプレートをインストールして、該当する gpo を編集するために GPMC または AGPM を開いてから、次の gpo ノードに移動する必要があります。**コンピューター構成** \\ **ポリシー** \\ **管理用テンプレート** \\ **Windows コンポーネント** \\ **MDOP mbam (BitLocker 管理)。**

MDOP MBAM (BitLocker Management) GPO ノードには、4つのグローバルポリシー設定と4つの子 GPO 設定ノード (クライアント管理、固定ドライブ、オペレーティングシステムドライブ、およびリムーバブルドライブ) が含まれています。 以下のセクションでは、MBAM GPO ポリシー設定要件の計画に役立つポリシー定義と推奨されるポリシー設定について説明します。

**注**  
最低限の推奨される GPO 設定を構成して、MBAM で BitLocker 暗号化を管理できるようにする方法については、「 [mbam 2.0 GPO 設定を編集する方法](how-to-edit-mbam-20-gpo-settings-mbam-2.md)」を参照してください。



## グローバルポリシー定義


このセクションでは、次の GPO ノードで検索される mbam グローバルポリシー定義について説明します。**コンピューター構成** \\ **ポリシー** \\ **管理用テンプレート** \\ **Windows コンポーネント** \\ **MDOP mbam (BitLocker 管理)**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ポリシー名</th>
<th align="left">概要と推奨されるポリシー設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ドライブの暗号化方法と暗号強度を選ぶ</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>特定の暗号化方法と暗号強度を使用するように、このポリシーを構成します。</p>
<p>このポリシーが構成されていない場合、BitLocker では、AES 128 ビットとディフューザーの既定の暗号化方法、またはセットアップスクリプトで指定された暗号化メソッドを使用します。</p></td>
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
<p>このポリシーが構成されていない場合、証明書の指定には既定のオブジェクト識別子1.3.6.1.4.1.311.67.1.1 が使用されます。</p></td>
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



## クライアント管理ポリシーの定義


このセクションでは、次の GPO ノードで検出された Microsoft BitLocker 管理および監視のクライアント管理ポリシー定義について説明します。**コンピューター構成** \\ **ポリシー** \\ **管理用テンプレート** \\ **Windows コンポーネント** \\ **MDOP mbam (BitLocker 管理)** \\ **クライアントの管理**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ポリシー名</th>
<th align="left">概要と推奨されるポリシー設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MBAM サービスを設定する</p></td>
<td align="left"><p>推奨される構成: <strong> 有効</strong></p>
<ul>
<li><p><strong>MBAM Recovery and Hardware service endpoint </strong> 。 MBAM クライアント BitLocker 暗号化管理を有効にするには、この設定を使います。 次のようなエンドポイントの場所を入力します。 <strong> http:// </strong><em> &lt; mbam Administration and Monitoring Server Name &gt; </em><strong> : </strong><em> &lt; web サービスは/MBAMRecoveryAndHardwareService/CoreService.svc にバインドされてい &gt; </em><strong> </strong> ます。</p></li>
<li><p><strong>保存する BitLocker 回復情報を選択し </strong> ます。 このポリシー設定では、BitLocker 回復情報をバックアップするためのキー回復サービスを構成できます。 また、コンプライアンスと監査レポートを収集するためのステータスレポートサービスを構成することもできます。 ポリシーには、BitLocker によって暗号化されたデータを回復するための管理方法が用意されており、重要な情報がないためにデータの損失を防ぐことができます。 状態レポートとキー回復アクティビティは、自動的に、構成済みレポートサーバーの場所に送信されます。</p>
<p>構成しなかった場合、またはこのポリシー設定を無効にした場合、キーの回復情報は保存されず、ステータスレポートとキーの回復アクティビティはサーバーに報告されません。 この設定を <strong> [回復パスワードとキーパッケージ] に設定すると、 </strong> 回復パスワードとキーパッケージは、構成済みのキー回復サーバーの場所に自動的にバックアップされます。</p></li>
<li><p><strong>クライアントチェックの状態の頻度を分単位で入力し </strong> ます。 このポリシー設定は、クライアントがクライアントコンピューター上の BitLocker 保護ポリシーと状態を確認する頻度を管理します。 このポリシーは、クライアントのコンプライアンスの状態をサーバーに保存する頻度も管理します。 クライアントは、クライアントコンピューター上の BitLocker 保護ポリシーと状態を確認し、構成された頻度でクライアント回復キーもバックアップします。</p>
<p>この頻度は、お客様の会社によって設定された要件に基づいて、コンピューターのコンプライアンスの状態を確認する頻度と、クライアント回復キーをバックアップする頻度に基づいて設定します。</p></li>
<li><p><strong>MBAM ステータスレポートサービスのエンドポイント </strong> 。 MBAM クライアント BitLocker 暗号化管理を有効にするには、この設定を構成する必要があります。 次のようなエンドポイントの場所を入力します。 <strong> http:// </strong><em> &lt; mbam Administration and Monitoring Server Name &gt; </em><strong> : </strong><em> &lt; web サービスは/MBAMComplianceStatusService/StatusReportingService.svc にバインドされてい &gt; </em><strong> </strong> ます。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>ユーザーの免税ポリシーを構成する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシー設定では、ユーザーに対して BitLocker 暗号化の除外を要求するように指示する、web サイトのアドレス、メールアドレス、または電話番号を構成できます。</p>
<p>このポリシー設定を有効にして、web サイトのアドレス、メールアドレス、または電話番号を指定すると、除外を適用して BitLocker 保護を適用する方法を示すダイアログがユーザーに表示されます。 ユーザーに対して BitLocker 暗号化の適用除外を有効にする方法については、「 <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md)"> ユーザー Bitlocker 暗号化の除外を管理する方法」を参照してください </a> 。</p>
<p>このポリシー設定を無効にするか、未構成にした場合、除外要求の手順はユーザーに表示されません。</p>
<div class="alert">
<strong>注</strong><br/><p>ユーザーの除外は、コンピューターごとではなく、ユーザーごとに管理されます。 複数のユーザーが同じコンピューターにログオンしていて、1人のユーザーが除外されていない場合、コンピューターは暗号化されます。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>カスタマーエクスペリエンス向上プログラムの構成</p></td>
<td align="left"><p>このポリシー設定では、MBAM ユーザーがカスタマーエクスペリエンス向上プログラムに参加する方法を構成できます。 このプログラムでは、コンピューターのハードウェアに関する情報を収集し、ユーザーの作業を中断することなく MBAM を使用する方法について説明します。 この情報は、Microsoft が改善する MBAM 機能を特定するのに役立ちます。 Microsoft は、MBAM ユーザを特定したり連絡したりするためにこの情報を使用することはありません。</p>
<p>このポリシー設定を有効にすると、ユーザーはカスタマーエクスペリエンス向上プログラムに参加できます。</p>
<p>このポリシー設定を無効にすると、ユーザーはカスタマーエクスペリエンス向上プログラムに参加できなくなります。</p>
<p>このポリシー設定を構成しない場合、ユーザーにはカスタマーエクスペリエンス向上プログラムに参加するオプションが表示されます。</p></td>
</tr>
</tbody>
</table>



## 固定ドライブのポリシー定義


このセクションでは、Microsoft BitLocker の管理と監視に関する、次の GPO ノードで検出される固定ドライブポリシーの定義について説明します。**コンピューター構成** \\ **ポリシー** \\ **管理用テンプレート** \\ **Windows コンポーネント** \\ **MDOP mbam (BitLocker 管理)** \\ **固定ドライブ**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ポリシー名</th>
<th align="left">概要と推奨されるポリシー設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>固定データドライブの暗号化設定</p></td>
<td align="left"><p>推奨される構成: <strong> 有効</strong></p>
<p>このポリシー設定を使用すると、固定ドライブを暗号化する必要があるかどうかを管理できます。</p>
<p>オペレーティングシステムのボリュームが暗号化される必要がある場合は、[ <strong> 固定データドライブの自動ロックを有効にする] オプションを選択し </strong> ます。</p>
<p>このポリシーを有効にするとき <strong> </strong> は、固定データドライブの自動ロック解除を許可するか必要としない限り、[固定データドライブのパスワードの使用を構成する] ポリシーを無効にしないでください。</p>
<p>固定データドライブの自動ロック解除を使用する必要がある場合は、暗号化されるようにオペレーティングシステムのボリュームを構成する必要があります。</p>
<p>このポリシー設定を有効にした場合、ユーザーはすべての固定ドライブを BitLocker で保護する必要があり、ドライブは暗号化されます。</p>
<p>このポリシー設定を構成しない場合、ユーザーは、BitLocker 保護の下に固定ドライブを配置する必要はありません。 固定データドライブが暗号化された後にこのポリシーを適用すると、MBAM エージェントは暗号化された固定ドライブを暗号化解除します。</p>
<p>このポリシー設定を無効にした場合、ユーザーは固定データドライブを BitLocker 保護の下に配置することはできません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>BitLocker で保護されていない固定ドライブへの書き込みアクセスを拒否する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシー設定は、固定ドライブがコンピューターで書き込み可能であることを確認するために BitLocker の保護が必要かどうかを決定します。 このポリシー設定は、BitLocker を有効にすると適用されます。</p>
<p>ポリシーが構成されていない場合は、コンピューター上のすべての固定データドライブが読み取りと書き込みのアクセス許可付きでマウントされます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>BitLocker で保護された固定ドライブへのアクセスを以前のバージョンの Windows から許可する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシーを有効にすると、Windows Server 2008、Windows Vista、Windows XP、または Windows XP SP2 を実行しているコンピューターで、FAT ファイルシステムの固定ドライブのロックを解除し、表示することができます。</p>
<p>ポリシーが有効になっているか、構成されていない場合、FAT ファイルシステムで書式設定された固定ドライブのロックを解除することができ、windows Server 2008、Windows Vista、Windows XP SP3、または Windows XP SP2 を実行しているコンピューターでコンテンツを表示できます。 これらのオペレーティングシステムは、BitLocker で保護されたドライブに対する読み取り専用アクセス権を持ちます。</p>
<p>ポリシーが無効になっている場合、FAT ファイルシステムで書式設定された固定ドライブのロックを解除することはできません。 Windows Server 2008、Windows Vista、Windows XP SP3、または Windows XP SP2 を実行しているコンピューターでは、これらのコンテンツを表示することはできません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>固定ドライブのパスワードの使用を構成する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシーを使って、BitLocker で保護された固定データドライブのロックを解除するためにパスワードが必要かどうかを指定します。</p>
<p>このポリシー設定を有効にした場合、ユーザーは定義した要件を満たすパスワードを構成できます。 BitLocker では、ドライブで使用できる任意のプロテクターでドライブのロックを解除することができます。</p>
<p>これらの設定は、ボリュームのロックを解除するときにではなく、BitLocker を有効にするときに適用されます。</p>
<p>このポリシー設定を無効にした場合、ユーザーはパスワードを使用することはできません。</p>
<p>ポリシーが構成されていない場合、パスワードは既定の設定でサポートされます。パスワードの複雑さの要件は含まれず、8文字しか必要ありません。</p>
<p>セキュリティを高めるには、このポリシーを有効にして、[ <strong> 固定データドライブにパスワードを要求する] を選択し </strong> 、[ <strong> パスワードの複雑さを要求する] を選択し </strong> て、必要なパスワードの長さを設定し <strong> </strong> ます。</p>
<p>このポリシー設定を無効にした場合、ユーザーはパスワードを使用することはできません。</p>
<p>このポリシー設定を構成しない場合、パスワードは既定の設定でサポートされます。パスワードの複雑さの要件は含まれません。これには8文字しか必要ありません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>BitLocker で保護された固定ドライブの回復方法を選択する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>BitLocker データ回復エージェントを有効にする、または Active Directory ドメインサービス (AD DS) に BitLocker 回復情報を保存するには、このポリシーを構成します。</p>
<p>ポリシーが構成されていない場合、BitLocker データ回復エージェントは許可され、回復情報は AD DS にバックアップされません。 MBAM は、AD DS にバックアップするための回復情報を必要としません。</p></td>
</tr>
</tbody>
</table>



## オペレーティングシステムドライブのポリシー定義


このセクションでは、Microsoft BitLocker の管理と監視に使用するオペレーティングシステムドライブのポリシー定義について説明します。**コンピューター構成** \\ **ポリシー** \\ **管理用テンプレート** \\ **Windows コンポーネント** \\ **MDOP mbam (BitLocker 管理)** \\ **オペレーティングシステムドライブ**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ポリシー名</th>
<th align="left">概要と推奨されるポリシー設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>オペレーティングシステムドライブの暗号化の設定</p></td>
<td align="left"><p>推奨される構成: <strong> 有効</strong></p>
<p>このポリシー設定では、オペレーティングシステムドライブを暗号化する必要があるかどうかを管理できます。</p>
<p>セキュリティを高めるには、 <strong> </strong> TPM + PIN プロテクターを使って、システム/電源管理/スリープ設定で次のポリシー設定を無効にすることを検討してください。</p>
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
<td align="left"><p>TPM プラットフォームの検証プロファイルを構成する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシー設定では、コンピューター上の TPM セキュリティハードウェアが BitLocker 暗号化キーをセキュリティで保護する方法を構成できます。 このポリシー設定は、コンピューターに互換性のある TPM が搭載されていない場合、または TPM 保護で BitLocker が既に有効になっている場合は適用されません。</p>
<p>このポリシー設定が構成されていない場合、TPM では、既定のプラットフォーム検証プロファイルまたはセットアップスクリプトで指定されたプラットフォーム検証プロファイルが使用されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>BitLocker で保護されたオペレーティングシステムドライブの回復方法を選択する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>BitLocker データ回復エージェントを有効にする、または Active Directory ドメインサービス (AD DS) に BitLocker 回復情報を保存するには、このポリシーを構成します。</p>
<p>このポリシーが構成されていない場合、データ回復エージェントは許可され、回復情報は AD DS にバックアップされません。</p>
<p>MBAM 操作では、AD DS に回復情報をバックアップする必要はありません。</p></td>
</tr>
</tbody>
</table>



## リムーバブルドライブのポリシー定義


このセクションでは、Microsoft BitLocker の管理と監視に使用されるリムーバブルドライブポリシーの定義について説明します。次の GPO ノードで検出されます。**コンピューター構成** \\ **ポリシー** \\ **管理用テンプレート** \\ **Windows コンポーネント** \\ **MDOP mbam (BitLocker 管理)**  \\  **リムーバブルドライブ**。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ポリシー名</th>
<th align="left">概要と推奨されるポリシー設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>リムーバブルドライブでの BitLocker の使用を制御する</p></td>
<td align="left"><p>推奨される構成: <strong> 有効</strong></p>
<p>このポリシーは、リムーバブルデータドライブでの BitLocker の使用を制御します。</p>
<p>[ <strong> リムーバブルデータドライブ上に bitlocker 保護を適用することをユーザーに許可する] オプションを有効にして、 </strong> ユーザーがリムーバブルデータドライブで bitlocker セットアップウィザードを実行できるようにします。</p>
<p><strong>[リムーバブルデータドライブ上の bitlocker を一時停止して暗号化を解除する] オプションを有効にして、 </strong> ユーザーがドライブから bitlocker ドライブ暗号化を削除できるようにします。または、メンテナンスが実行されている間、暗号化を中断します。</p>
<p>このポリシーを有効にして、[ <strong> リムーバブルデータドライブに対する BitLocker 保護の適用を許可する] オプションが選択されている場合 </strong> 、Mbam クライアントは、リムーバブルドライブに関する回復情報を mbam キー回復サーバーに保存し、パスワードが失われた場合にユーザーがドライブを回復できるようにします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>BitLocker で保護されていないリムーバブル ドライブへの書き込みアクセスを拒否する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシーを有効にして、BitLocker で保護されたドライブへの書き込みアクセスのみを許可します。</p>
<p>このポリシーを有効にすると、コンピューター上のすべてのリムーバブルデータドライブは、書き込みアクセスが許可される前に暗号化が必要になります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>以前のバージョンの Windows から BitLocker で保護されているリムーバブルドライブへのアクセスを許可する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシーを有効にすると、FAT ファイルシステムを実行しているコンピューターで、windows Server 2008、Windows Vista、Windows XP、または Windows XP SP2 を実行しているコンピューターで、固定ドライブのロックを解除して表示することができます。</p>
<p>このポリシーが構成されていない場合は、FAT ファイルシステムで書式設定されたリムーバブルデータドライブは、Windows Server 2008、Windows Vista、Windows XP、SP3、または Windows XP を実行しているコンピューターでロックを解除することができ、そのコンテンツは表示できます。 これらのオペレーティングシステムは、BitLocker で保護されたドライブに対する読み取り専用アクセス権を持ちます。</p>
<p>ポリシーが無効になっている場合、FAT ファイルシステムで書式設定されたリムーバブルドライブのロックを解除することはできません。 Windows Server 2008、Windows Vista、Windows XP SP3、または Windows XP SP2 を実行しているコンピューターでは、これらのコンテンツを表示することはできません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>リムーバブルデータドライブのパスワードの使用を構成する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシーを有効にして、リムーバブルデータドライブのパスワード保護を構成します。</p>
<p>このポリシーが構成されていない場合、パスワードは、パスワードの複雑さの要件を含まず、8文字のみを必要とする既定の設定でサポートされます。</p>
<p>セキュリティを強化するために、このポリシーを有効にして、 <strong> [リムーバブルデータドライブにパスワードを要求する] をオンにし </strong> 、[パスワードの複雑さを要求する] を選択し、推奨される <strong> </strong> <strong> パスワードの最小文字数を設定し </strong> ます。</p></td>
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


[MBAM 2.0 展開の前提条件](mbam-20-deployment-prerequisites-mbam-2.md)









