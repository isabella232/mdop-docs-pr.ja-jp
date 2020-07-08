---
title: MBAM 1.0 グループ ポリシー要件の計画
description: MBAM 1.0 グループ ポリシー要件の計画
author: dansimp
ms.assetid: 0fc9c509-7850-4a8e-bb82-b949025bcb02
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f5061748107dc1d00baa41188b8cf240ec187317
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812435"
---
# MBAM 1.0 グループ ポリシー要件の計画


Microsoft BitLocker 管理および監視 (MBAM) クライアント管理では、カスタムグループポリシー設定を適用する必要があります。 このトピックでは、MBAM を使って企業の BitLocker ドライブ暗号化を管理する場合に、グループポリシーオブジェクト (GPO) に使用できるポリシーオプションについて説明します。

**重要**  
MBAM は、Windows BitLocker ドライブ暗号化の既定の GPO 設定を使いません。 既定の設定が有効になっている場合、競合する動作が発生する可能性があります。 MBAM を有効にするには、MBAM グループポリシーテンプレートをインストールした後で、GPO ポリシー設定を定義する必要があります。



MBAM グループポリシーテンプレートをインストールした後、MBAM がエンタープライズ BitLocker 暗号化を管理できるようにする、使用可能なカスタム MBAM GPO ポリシー設定を表示して変更することができます。 MBAM グループポリシーテンプレートは、グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) の MDOP 技術を実行できるコンピューターにインストールする必要があります。 次に、該当する gpo を編集するには、GPMC または AGPM を開き、次の gpo ノードに移動します。**コンピューターの構成** \\ **管理用テンプレート** \\ **Windows コンポーネント** \\ **MDOP mbam (BitLocker 管理)**。

MDOP MBAM (BitLocker Management) GPO ノードには、4つのグローバルポリシー設定と4つの子 GPO 設定ノードが含まれています。 4つの GPO グローバルポリシー設定は、クライアント管理、固定ドライブ、オペレーティングシステムドライブ、およびリムーバブルドライブです。 以下のセクションでは、MBAM GPO ポリシー設定要件の計画に役立つポリシー定義と推奨されるポリシー設定について説明します。

**注**  
BitLocker 暗号化の管理を可能にする GPO の推奨設定の最小値の構成の詳細については、「 [mbam 1.0 GPO 設定を編集する方法](how-to-edit-mbam-10-gpo-settings.md)」を参照してください。



## グローバルポリシー定義


このセクションでは、mbam グローバルポリシー定義について説明します。これは、**コンピューター構成** \\ **管理用テンプレート** \\ **Windows コンポーネント**の \\ **MDOP mbam (BitLocker 管理)** が含まれています。

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


このセクションでは、mbam のクライアント管理ポリシー定義について説明します。**コンピューター構成** \\ **管理用テンプレート** \\ **Windows コンポーネント** \\ **MDOP mbam (BitLocker 管理)**  \\  **クライアント管理**。

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
<li><p><strong>MBAM Recovery and Hardware service endpoint </strong> 。 これは、MBAM クライアント BitLocker 暗号化管理を有効にするために構成する必要がある最初のポリシー設定です。 この設定では、次の例のようなエンドポイントの場所を入力します。 <strong> http:// </strong><em> &lt; mbam 管理と監視サーバー名 &gt; </em><strong> : </strong><em> &lt; web サービスは/MBAMRecoveryAndHardwareService/CoreService.svc にバインドされてい &gt; </em><strong> </strong> ます。</p></li>
<li><p><strong>保存する BitLocker 回復情報を選択し </strong> ます。 このポリシー設定では、BitLocker 回復情報をバックアップするためのキー回復サービスを構成できます。 また、コンプライアンスと監査レポートを収集するためのステータスレポートサービスを構成することもできます。 このポリシーには、重要な情報がないためにデータの損失を防ぐために、BitLocker によって暗号化されたデータを回復する管理方法が用意されています。 状態レポートとキー回復アクティビティは、自動的に、構成済みレポートサーバーの場所に送信されます。</p>
<p>構成しなかった場合、またはこのポリシー設定を無効にした場合、キーの回復情報は保存されず、ステータスレポートとキーの回復アクティビティはサーバーに報告されません。 この設定を <strong> [回復パスワードとキーパッケージ] に設定すると、 </strong> 回復パスワードとキーパッケージは、構成済みのキー回復サーバーの場所に自動的にバックアップされます。</p></li>
<li><p><strong>クライアントチェックの状態の頻度を分単位で入力し </strong> ます。 このポリシー設定は、クライアントが BitLocker 保護ポリシーとクライアントコンピューターの状態を確認する頻度を管理します。 このポリシーは、クライアントのコンプライアンスの状態をサーバーに保存する頻度も管理します。 クライアントは、クライアントコンピューター上の BitLocker 保護ポリシーと状態を確認し、構成された頻度でクライアント回復キーもバックアップします。</p>
<p>コンピューターのコンプライアンスの状態を確認する頻度と、クライアント回復キーをバックアップする頻度について、会社が確立した要件に基づいてこの頻度を設定します。</p></li>
<li><p><strong>MBAM ステータスレポートサービスのエンドポイント </strong> 。 これは、MBAM クライアント BitLocker 暗号化の管理を有効にするために構成する必要がある2番目のポリシー設定です。 この設定では、次の例を使用して、エンドポイントの場所を入力します。 <strong> http:// </strong><em> &lt; mbam 管理と監視サーバー名 &gt; </em><strong> : </strong><em> &lt; web サービスが/MBAMComplianceStatusService/StatusReportingService. にバインドされ &gt; </em><strong> ている svc </strong> 。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>ハードウェアの互換性のチェックを許可する</p></td>
<td align="left"><p>推奨される構成: <strong> 有効</strong></p>
<p>このポリシー設定では、MBAM クライアントコンピューターのドライブで BitLocker の保護を有効にする前に、ハードウェア互換性の確認を管理することができます。</p>
<p>エンタープライズに、トラステッドプラットフォームモジュール (TPM) をサポートしていない旧式のコンピューターハードウェアまたはコンピューターがある場合は、このポリシーオプションを有効にする必要があります。 これらの条件のいずれかが true の場合は、ハードウェア互換性の確認を有効にして、MBAM が BitLocker をサポートするコンピューターモデルにのみ適用されることを確認します。 組織内のすべてのコンピューターで BitLocker がサポートされている場合、ハードウェアの互換性を展開する必要はありません。また、このポリシーを [未構成] に設定することもでき <strong> </strong> ます。</p>
<p>このポリシー設定を有効にした場合、コンピューターのモデルは24時間ごとに1回、ハードウェア互換性リストに対して検証されます。これにより、ポリシーによって、コンピュータードライブの BitLocker の保護が有効になります。</p>
<div class="alert">
<strong>注</strong><br/><p>このポリシー設定を有効にする前に、mbam <strong> </strong> サービスの構成オプションで Mbam 回復とハードウェアサービスのエンドポイントの設定が構成されていることを確認してください <strong> </strong> 。</p>
</div>
<div>

</div>
<p>このポリシー設定を無効にした場合、または構成しなかった場合、コンピューターモデルはハードウェア互換性リストに対して検証されません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ユーザーの免税ポリシーを構成する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシー設定では、ユーザーに対して BitLocker 暗号化の除外を要求するように指示する、web サイトのアドレス、メールアドレス、または電話番号を構成できます。</p>
<p>このポリシー設定を有効にして、web サイトのアドレス、メールアドレス、または電話番号を指定すると、除外を適用して BitLocker 保護を適用する方法の手順を示すダイアログボックスが表示されます。 ユーザーに対して BitLocker 暗号化の除外を有効にする方法の詳細については、「 <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md)"> ユーザー Bitlocker 暗号化の除外を管理する方法」を参照してください </a> 。</p>
<p>このポリシー設定を無効にするか、未構成にした場合、除外要求に適用するための手順はユーザーには表示されません。</p>
<div class="alert">
<strong>注</strong><br/><p>ユーザーの除外は、コンピューターごとではなく、ユーザーごとに管理されます。 複数のユーザーが同じコンピューターにログオンしていて、1人のユーザーが除外されていない場合、コンピューターは暗号化されます。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## 固定ドライブのポリシー定義


このセクションでは、mbam の固定ドライブポリシー定義について説明します。これは、次の GPO ノードで確認できます。**コンピューター構成** \\ **管理用テンプレート** \\ **Windows コンポーネント** \\ **MDOP mbam (BitLocker 管理)**  \\  **固定ドライブ**。

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
<td align="left"><p>推奨される構成: 有効にして、 <strong> </strong> <strong> </strong> オペレーティングシステムのボリュームが暗号化されている必要がある場合は、[固定データドライブの自動ロック解除を行う] チェックボックスをオンにします。</p>
<p>このポリシー設定では、固定ドライブを暗号化するかどうかを管理できます。</p>
<p>このポリシーを有効にする場合は、[ <strong> 固定データドライブのパスワードの使用を構成する] ポリシーを無効にしないでください </strong> 。</p>
<p>[ <strong> 固定データドライブの自動ロック解除を行う] チェックボックスがオンになっている場合は、 </strong> オペレーティングシステムのボリュームが暗号化されている必要があります。</p>
<p>このポリシー設定を有効にした場合、ユーザーはすべての固定ドライブを BitLocker 保護下に置き、ドライブを暗号化する必要があります。</p>
<p>このポリシーを構成していない場合、またはこのポリシーを無効にした場合、ユーザーは BitLocker 保護の下に固定ドライブを配置する必要はありません。</p>
<p>このポリシーを無効にすると、MBAM エージェントは暗号化された固定ドライブを暗号化解除します。</p>
<p>オペレーティングシステムのボリュームを暗号化する必要がない場合は、[ <strong> 固定データドライブの自動ロックを有効にする] チェックボックスをオフにし </strong> ます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>BitLocker で保護されていない固定ドライブに対する "書き込み" アクセス許可を拒否する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシー設定は、書き込み可能なコンピューター上の固定ドライブに対して BitLocker 保護が必要かどうかを決定します。 このポリシー設定は、BitLocker を有効にすると適用されます。</p>
<p>ポリシーが構成されていない場合、コンピューター上のすべての固定ドライブは読み取り/書き込みアクセス許可を使用してマウントされます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>BitLocker で保護された固定ドライブへのアクセスを以前のバージョンの Windows から許可する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシーを有効にすると、Windows Server 2008、Windows Vista、Windows XP SP3、または Windows XP SP2 を実行しているコンピューター上で、ファイルアロケーションテーブル (FAT) ファイルシステムでフォーマットされた固定ドライブのロックを解除して表示することができます。</p>
<p>これらのオペレーティングシステムは、BitLocker で保護されたドライブに対して読み取り専用のアクセス許可を持っています。</p>
<p>ポリシーが無効になっている場合、FAT ファイルシステムで書式設定された固定ドライブのロックを解除することはできません。 Windows Server 2008、Windows Vista、Windows XP SP3、または Windows XP SP2 を実行しているコンピューターでは、これらのコンテンツを表示することはできません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>固定ドライブのパスワードの使用を構成する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシーを有効にして、固定ドライブのパスワード保護を構成します。</p>
<p>ポリシーが構成されていない場合は、パスワードの複雑さの要件を含まず、8文字のみを必要とする既定の設定でパスワードがサポートされます。</p>
<p>セキュリティを高めるには、このポリシーを有効にして、[ <strong> 固定データドライブにパスワードを要求する] を選択し </strong> 、[ <strong> パスワードの複雑さを要求する] を選択し </strong> て、必要なパスワードの長さを設定し <strong> </strong> ます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>BitLocker で保護された固定ドライブの回復方法を選択する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>BitLocker データ回復エージェントを有効にする、または Active Directory ドメインサービス (AD DS) に BitLocker 回復情報を保存するには、このポリシーを構成します。</p>
<p>このポリシーが構成されていない場合、BitLocker データ回復エージェントは許可され、回復情報は AD DS にバックアップされません。 MBAM は、AD DS に回復情報をバックアップする必要はありません。</p></td>
</tr>
</tbody>
</table>



## オペレーティングシステムドライブのポリシー定義


このセクションでは、mbam のオペレーティングシステムドライブのポリシー定義について説明します。**コンピューター構成** \\ **管理用テンプレート** \\ **Windows コンポーネント** \\ **MDOP mbam (BitLocker 管理)**  \\  **オペレーティングシステムドライブ**。

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
<p>このポリシー設定は、オペレーティングシステムのドライブが暗号化されるかどうかを決定します。</p>
<p>このポリシーを構成して、次の操作を実行します。</p>
<ul>
<li><p>オペレーティングシステムドライブに対して BitLocker 保護を適用します。</p></li>
<li><p>PIN の使用を構成して、オペレーティングシステムの保護にトラステッドプラットフォームモジュール (TPM) PIN を使用します。</p></li>
<li><p>拡張起動 Pin を構成して、大文字、小文字、数字などの文字を許可します。 MBAM は、拡張ピンでの記号とスペースの使用をサポートしていません。ただし、BitLocker では記号とスペースがサポートされています。</p></li>
</ul>
<p>このポリシー設定を有効にした場合、ユーザーは BitLocker を使用してオペレーティングシステムドライブをセキュリティで保護する必要があります。</p>
<p>構成しない場合、または設定を無効にした場合、ユーザーは BitLocker を使用してオペレーティングシステムドライブを保護する必要はありません。</p>
<p>このポリシーを無効にすると、MBAM エージェントは暗号化されたオペレーティングシステムボリュームを暗号化解除します。</p>
<p>有効になっている場合、このポリシー設定では、ユーザーは BitLocker 保護を使用してオペレーティングシステムをセキュリティで保護する必要があり、ドライブは暗号化されます。 暗号化の要件に基づいて、オペレーティングシステムドライブの保護方法を選ぶことができます。</p>
<p>セキュリティ要件を高くするには、TPM + PIN を使用し、拡張 Pin を許可して、PIN の最小の長さを8文字に設定します。</p>
<p>TPM + PIN プロテクターでこのポリシーが有効になっている場合は、 <strong> システムの </strong>  /  <strong> Power Management の </strong>  /  <strong> スリープ設定 </strong> で次のポリシーを無効にすることを検討してください。</p>
<ul>
<li><p>スリープ中 (電源に接続されているとき) にスタンバイ状態 (S1 ~ S3) を許可する</p></li>
<li><p>スリープ中 (バッテリー) でスタンバイ状態 (S1-S3) を許可する</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>TPM プラットフォームの検証プロファイルを構成する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシー設定では、コンピューター上の TPM セキュリティハードウェアが BitLocker 暗号化キーをセキュリティで保護する方法を構成できます。 このポリシー設定は、コンピューターに互換性のある TPM が搭載されていない場合、または BitLocker で TPM 保護が有効になっている場合は適用されません。</p>
<p>このポリシーが構成されていない場合、TPM では、既定のプラットフォーム検証プロファイルまたはセットアップスクリプトで指定されたプラットフォームの検証プロファイルが使用されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>BitLocker で保護されたオペレーティングシステムドライブの回復方法を選択する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>BitLocker データ回復エージェントを有効にする、または Active Directory ドメインサービス (AD DS) に BitLocker 回復情報を保存するには、このポリシーを構成します。</p>
<p>このポリシーが構成されていない場合、データ回復エージェントは許可され、回復情報は AD DS にバックアップされません。</p>
<p>MBAM 操作では、回復情報を AD DS にバックアップする必要はありません。</p></td>
</tr>
</tbody>
</table>



## リムーバブルドライブのポリシー定義


このセクションでは、mbam のリムーバブルドライブポリシー定義について説明します。**コンピューター構成** \\ **管理用テンプレート** \\ **Windows コンポーネント** \\ **MDOP mbam (BitLocker 管理)**  \\  **リムーバブルドライブ**。

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
<p>[ <strong> リムーバブルデータドライブに対して bitlocker 保護を適用することをユーザーに許可する </strong> ] オプションを有効にして、ユーザーがリムーバブルデータドライブで bitlocker セットアップウィザードを実行できるようにします。</p>
<p><strong>[リムーバブルデータドライブ上の bitlocker を一時停止して暗号化を解除する] オプションを有効にして、 </strong> ユーザーがドライブから bitlocker ドライブ暗号化を削除できるようにします。または、メンテナンスが実行されている間、暗号化を中断します。</p>
<p>このポリシーを有効にして、[ <strong> ユーザーにリムーバブルデータドライブへの BitLocker 保護の適用を許可する] オプションが選択されている場合 </strong> 、Mbam クライアントは、リムーバブルドライブに関する回復情報を mbam キー回復サーバーに保存し、パスワードが失われた場合にユーザーがドライブを回復できるようにします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>BitLocker で保護されていないリムーバブルドライブに対する "書き込み" アクセス許可を拒否する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシーを有効にして、BitLocker で保護されたドライブへの書き込み専用アクセス許可を付与します。</p>
<p>このポリシーを有効にすると、コンピューター上のすべてのリムーバブルデータドライブは、書き込み権限が許可される前に暗号化が必要になります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>以前のバージョンの Windows から BitLocker で保護されているリムーバブルドライブへのアクセスを許可する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシーを有効にすると、Windows Server 2008、Windows Vista、Windows XP SP3、または Windows XP SP2 を実行しているコンピューター上で、(FAT) ファイルシステムでフォーマットされている固定ドライブをロック解除して表示することができます。</p>
<p>これらのオペレーティングシステムは、BitLocker で保護されたドライブに対して読み取り専用のアクセス許可を持っています。</p>
<p>ポリシーが無効になっている場合、FAT ファイルシステムで書式設定されたリムーバブルドライブのロックを解除することはできません。 Windows Server 2008、Windows Vista、Windows XP SP3、または Windows XP SP2 を実行しているコンピューターでは、これらのコンテンツを表示することはできません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>リムーバブルデータドライブのパスワードを使用するように構成する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシーを有効にして、リムーバブルデータドライブのパスワード保護を構成します。</p>
<p>このポリシーが構成されていない場合は、パスワードの複雑さの要件が含まれておらず、8文字のみを必要とする既定の設定でパスワードがサポートされます。</p>
<p>セキュリティ強化のために、このポリシーを有効にして、[リムーバブルデータドライブにパスワードを要求する] を選択し、[パスワードの複雑さを要求する] を選択して、[パスワード <strong> </strong> <strong> </strong> の最小文字数] を設定し <strong> </strong> ます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>BitLocker で保護されたリムーバブルドライブの回復方法を選択する</p></td>
<td align="left"><p>推奨される構成: <strong> 未構成</strong></p>
<p>このポリシーを構成して、BitLocker データ回復エージェントを有効にしたり、Active Directory ドメインサービス (AD DS) に BitLocker 回復情報を保存したりすることができます。</p>
<p>ポリシーが未構成に設定されている場合 <strong> </strong> 、データ回復エージェントは許可され、回復情報は AD DS にバックアップされません。</p>
<p>MBAM 操作では、回復情報を AD DS にバックアップする必要はありません。</p></td>
</tr>
</tbody>
</table>



## 関連トピック


[MBAM 1.0 に対応する環境の準備](preparing-your-environment-for-mbam-10.md)









