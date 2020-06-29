---
title: MBAM 2.5 スタンドアロン レポートについて
description: MBAM 2.5 スタンドアロン レポートについて
author: dansimp
ms.assetid: 78b5aaf4-8257-4722-8eb9-e0de48db6a11
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 45e84c7c3b2bcb1602890c7c5a09592324da691e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812778"
---
# MBAM 2.5 スタンドアロン レポートについて


このトピックでは、スタンドアロントポロジで Microsoft BitLocker の管理と監視 (MBAM) を実行しているときに使用できるレポートについて説明します。

**注**  
Configuration Manager の統合トポロジで MBAM を実行している場合は、MBAM からではなく、Configuration Manager からレポートを生成します。 これらのレポートの詳細については[、「Configuration Manager の統合トポロジの MBAM 2.5 レポートを表示](viewing-mbam-25-reports-for-the-configuration-manager-integration-topology.md)する」を参照してください。



## MBAM 単体のトポロジレポートについて


MBAM には、組織で BitLocker のコンプライアンスを監視するために使用できる、次の3種類のレポートが用意されています。

-   [エンタープライズコンプライアンスレポート](#bkmk-enterprisecompliance)

-   [コンピューターのコンプライアンスレポート](#bkmk-compliance)

-   [回復監査レポート](#bkmk-recovery)

単体のトポロジで MBAM を実行しているときに MBAM レポートにアクセスするには、web ブラウザーを開いて、[管理と監視] Web サイトを開きます。 左側のメニューバーで [**レポート**] を選択します。 上部のメニューバーで、生成するレポートの種類を選択します。 これらのレポートを生成する方法について詳しくは、「 [MBAM 2.5 単体レポートの生成](generating-mbam-25-stand-alone-reports.md)」をご覧ください。

### <a href="" id="bkmk-enterprisecompliance"></a>エンタープライズコンプライアンスレポート

このレポートの種類を使用して、組織内の全体的な BitLocker のコンプライアンスに関する情報を収集します。 組織内のコンピューターのコンプライアンスの状態とエラー状態について詳しく知るには、フィルターを使用して検索結果を絞り込むことができます。

**エンタープライズコンプライアンスの概要**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">列名</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>管理されたコンピューター</p></td>
<td align="left"><p>MBAM で管理されているコンピューターの数です。</p></td>
</tr>
<tr class="even">
<td align="left"><p>% 準拠</p></td>
<td align="left"><p>企業内の準拠しているコンピューターの割合。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>% 非準拠率</p></td>
<td align="left"><p>企業内の非準拠コンピューターの割合。</p></td>
</tr>
<tr class="even">
<td align="left"><p>% 免税</p></td>
<td align="left"><p>BitLocker 暗号化要件から除外されたコンピューターの割合。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>% 免税以外</p></td>
<td align="left"><p>BitLocker 暗号化要件の対象から除外されていないコンピューターの割合。</p></td>
</tr>
<tr class="even">
<td align="left"><p>仕様</p></td>
<td align="left"><p>企業内の準拠しているコンピューターの割合。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>準拠していない</p></td>
<td align="left"><p>企業内の非準拠コンピューターの割合。</p></td>
</tr>
<tr class="even">
<td align="left"><p>適用除外</p></td>
<td align="left"><p>BitLocker 暗号化要件から除外されたコンピューターの合計数。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>非免税</p></td>
<td align="left"><p>BitLocker 暗号化要件の対象から除外されていないコンピューターの合計数。</p></td>
</tr>
</tbody>
</table>



**エンタープライズコンプライアンスコンピューターの詳細**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">列名</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>コンピューター名</p></td>
<td align="left"><p>MBAM で管理されるユーザー指定の DNS 名。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ドメイン名</p></td>
<td align="left"><p>クライアントコンピューターが存在し、MBAM で管理されている完全修飾ドメイン名。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>コンプライアンスの状態</p></td>
<td align="left"><p>コンピューターに対して指定されたポリシーに従って、コンピューターのコンプライアンスの状態を指定します。 状態は準拠していないため、準拠しています。 コンプライアンスの状態を解釈する方法の詳細については、次の「企業コンプライアンスレポートのコンプライアンス状態」の表を参照してください。</p></td>
</tr>
<tr class="even">
<td align="left"><p>除外</p></td>
<td align="left"><p>このコンピューターが BitLocker ポリシーから除外されているかどうかを示す状態。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>コンプライアンスステータスの詳細</p></td>
<td align="left"><p>指定したポリシーに従って、コンピューターのコンプライアンスの状態に関するエラーメッセージと状態メッセージ。</p></td>
</tr>
<tr class="even">
<td align="left"><p>最終連絡先</p></td>
<td align="left"><p>コンピューターが最後にサーバーに接続してコンプライアンス状態を報告した日付と時刻。 コンタクトの周波数は構成可能です。 詳細については、「MBAM グループポリシーの設定」を参照してください。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-compliance"></a>コンピューターのコンプライアンスレポート

このレポートの種類を使用して、コンピューターまたはユーザーに固有の情報を収集します。

このレポートを表示するには、[エンタープライズコンプライアンス] レポートでコンピューター名をクリックするか、コンピューターのコンプライアンスレポートでコンピューター名を入力します。 このレポートには、コンピューター上の各ドライブ (オペレーティングシステムと固定データドライブ) に関する詳細な暗号化情報が表示されます。 また、コンピューター上の各ドライブの種類に適用されるポリシーを示します。 各ドライブの詳細を表示するには、[コンピューター名] エントリを展開します。

**注**  
リムーバブルデータボリュームの暗号化の状態は、このレポートには表示されません。



**コンピューターのコンプライアンスレポートのフィールド**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">列名</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>コンピューター名</p></td>
<td align="left"><p>MBAM で管理されるユーザー指定の DNS コンピューター名。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ドメイン名</p></td>
<td align="left"><p>クライアントコンピューターが存在し、MBAM で管理されている完全修飾ドメイン名。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>コンピュータの種類</p></td>
<td align="left"><p>コンピューターの種類。 有効な型は、ポータブルでもポータブルでもありません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>オペレーティング システム</p></td>
<td align="left"><p>MBAM で管理されているクライアントコンピューターで検出されたオペレーティングシステムの種類。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>コンプライアンスの状態</p></td>
<td align="left"><p>MBAM で管理されているコンピューターの全体のコンプライアンス状態。 有効な状態は、準拠して準拠していません。</p>
<p>ドライブあたりのコンプライアンスの状態 (次の表を参照) は、異なるコンプライアンスの状態を示している可能性があることに注意してください。 ただし、このフィールドは、指定したポリシーに従って、コンプライアンスの状態を表します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ポリシー暗号強度</p></td>
<td align="left"><p>MBAM ポリシー仕様に基づいて管理者によって選択された暗号強度 (例: ディフューザー付きの128ビット)。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ポリシーのオペレーティングシステムドライブ</p></td>
<td align="left"><p>オペレーティングシステムに暗号化が必要かどうかを示します。適切なプロテクターの種類が表示されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ポリシー-固定データドライブ</p></td>
<td align="left"><p>固定データドライブに暗号化が必要かどうかを示します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ポリシーのリムーバブルデータドライブ</p></td>
<td align="left"><p>リムーバブルドライブに暗号化が必要かどうかを示します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>デバイスユーザー</p></td>
<td align="left"><p>MBAM で管理されているコンピューター上の既知のユーザー。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>除外</p></td>
<td align="left"><p>このコンピューターが BitLocker ポリシーから除外されているかどうかを示す状態。</p></td>
</tr>
<tr class="even">
<td align="left"><p>製造元</p></td>
<td align="left"><p>コンピューターの BIOS に表示されるコンピューターの製造元名。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>モデル</p></td>
<td align="left"><p>コンピューターの BIOS に表示されたコンピューターの製造元のモデル名。</p></td>
</tr>
<tr class="even">
<td align="left"><p>コンプライアンスステータスの詳細</p></td>
<td align="left"><p>指定したポリシーに従って、コンピューターのコンプライアンスの状態に関するエラーメッセージと状態メッセージ。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>最終連絡先</p></td>
<td align="left"><p>コンピューターがコンプライアンス状態を報告するためにサーバーに最後に接続した日時です。 コンタクトの周波数は構成可能です。 詳細については、「MBAM グループポリシーの設定」を参照してください。</p></td>
</tr>
</tbody>
</table>



**コンピューターのコンプライアンスレポートのドライブフィールド**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">列名</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ドライブ文字</p></td>
<td align="left"><p>ユーザーが特定のドライブに割り当てたコンピューターのドライブ文字です。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ドライブの種類</p></td>
<td align="left"><p>ドライブの種類。 有効な値は、オペレーティングシステムドライブと固定データドライブです。 これらは論理ボリュームではなく物理ドライブです。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>暗号強度</p></td>
<td align="left"><p>MBAM ポリシー仕様に基づいて管理者によって選択された暗号強度。</p></td>
</tr>
<tr class="even">
<td align="left"><p>プロテクターの種類</p></td>
<td align="left"><p>オペレーティングシステムまたは固定データボリュームの暗号化に使用するグループポリシー設定によって選択されたプロテクターの種類。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>プロテクターの状態</p></td>
<td align="left"><p>MBAM で管理されているコンピューターが、ポリシーで指定されているプロテクターの種類を有効にしていることを示します。 有効な状態は、オンまたはオフです。</p></td>
</tr>
<tr class="even">
<td align="left"><p>暗号化の状態</p></td>
<td align="left"><p>ドライブの暗号化の状態。 有効な状態は、暗号化され、暗号化されず、暗号化されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>コンプライアンスの状態</p></td>
<td align="left"><p>ドライブがポリシーに準拠しているかどうかを示す状態。 状態は準拠していないため、準拠しています。</p></td>
</tr>
<tr class="even">
<td align="left"><p>コンプライアンスステータスの詳細</p></td>
<td align="left"><p>指定したポリシーに従って、コンピューターのコンプライアンスの状態に関するエラーメッセージと状態メッセージ。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-recovery"></a>回復監査レポート

このレポートの種類を使用して、BitLocker 回復キーへのアクセスを要求したユーザーを監査します。 レポートには、目的のフィルター条件に基づいて、いくつかのフィルターが用意されています。 特定の種類のユーザー (ヘルプデスクユーザーまたはエンドユーザー) に対して、要求が失敗したか、成功したか、要求された特定の種類のキー、取得した日付範囲に基づいてフィルターを適用できます。

**回復監査レポートのフィールド**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">列名</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>日付と時刻を要求する</p></td>
<td align="left"><p>エンドユーザーまたはヘルプデスクのユーザーによってキーの取得要求が行われた日時。</p></td>
</tr>
<tr class="even">
<td align="left"><p>監査要求ソース</p></td>
<td align="left"><p>要求が開始されたサイト。 このエントリには、 <strong> セルフサービスポータル </strong> または <strong> ヘルプデスクの2つの値のいずれかが表示され </strong> ます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>リクエストの状態</p></td>
<td align="left"><p>リクエストのステータス。 有効な状態 (キーが取得された)、または失敗 (キーは取得されませんでした)。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ヘルプデスクユーザー</p></td>
<td align="left"><p>キーの取得要求を開始したヘルプデスクのユーザー。</p>
<div class="alert">
<strong>注</strong><br/><p>上級のヘルプデスクユーザーがエンドユーザーを指定せずにキーを回復した場合、[ <strong> 終了ユーザー </strong> ] フィールドは空白になります。 標準のヘルプデスクユーザーは、エンドユーザーを指定する必要があります。そのユーザーはこのフィールドに表示されます。</p>
<p>セルフサービスポータルによる回復では、このフィールドと [エンドユーザー] フィールドの両方に、要求側のエンドユーザーの一覧が表示され <strong> </strong> ます。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>エンドユーザー</p></td>
<td align="left"><p>キーの取得要求を開始したエンドユーザー。</p></td>
</tr>
<tr class="even">
<td align="left"><p>コンピューター</p></td>
<td align="left"><p>回復されたコンピューターのコンピューター名。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>キーの種類</p></td>
<td align="left"><p>ヘルプデスクユーザーまたはエンドユーザーによって要求されたキーの種類。 MBAM で収集されるキーには、次の3種類があります。</p>
<ul>
<li><p>回復キーパスワード (回復モードでコンピューターを回復するために使用)</p></li>
<li><p>回復キー ID (別のユーザーの代わりに回復モードでコンピューターを回復するために使用されます)</p></li>
<li><p>TPM パスワードハッシュ (ロックされている TPM を使用してコンピューターを回復するために使用)</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>理由の説明</p></td>
<td align="left"><p>理由指定されたキーの種類が、ヘルプデスクユーザーまたはエンドユーザーによって要求された理由です。 この理由は、ドライブの回復で指定され、管理と監視の Web サイトの TPM 機能を管理します。 有効なエントリは、ユーザーが入力したテキスト、または次の理由コードのいずれかです。</p>
<ul>
<li><p>オペレーティングシステムのブート順序が変更されました</p></li>
<li><p>BIOS が変更されました</p></li>
<li><p>オペレーティングシステムファイルが変更されました</p></li>
<li><p>失われたスタートアップキー</p></li>
<li><p>PIN を紛失</p></li>
<li><p>TPM リセット</p></li>
<li><p>パスフレーズの紛失</p></li>
<li><p>紛失したスマートカード</p></li>
<li><p>PIN のロックアウトをリセットする</p></li>
<li><p>TPM を有効にする</p></li>
<li><p>TPM をオフにする</p></li>
<li><p>TPM パスワードを変更する</p></li>
<li><p>TPM をクリアする</p></li>
</ul></td>
</tr>
</tbody>
</table>



**注**  
レポートの結果をファイルに保存するには、[**レポート**] メニューバーの [**エクスポート**] をクリックします。




## 関連トピック


[MBAM 2.5 での BitLocker 準拠の監視とレポート](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)

[MBAM 2.5 スタンドアロン レポートの生成](generating-mbam-25-stand-alone-reports.md)



## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





