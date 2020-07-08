---
title: MBAM レポートの概要
description: MBAM レポートの概要
author: dansimp
ms.assetid: 8778f333-760e-4f26-acb4-4e73b6fbb536
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3c3ca5e4da4cbcea80c87520f0ecd05e1e7d6be0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823814"
---
# MBAM レポートの概要


Microsoft BitLocker の管理と監視 (MBAM) をインストールしたときに単体のトポロジを選んだ場合は、MBAM でさまざまなレポートを実行して、BitLocker の使用状況とコンプライアンスを監視することができます。 MBAM は、管理するすべてのコンピューターとデバイスに関するコンプライアンスおよびその他の情報を報告します。 このトピックの情報は、企業および個々のコンピューターのコンプライアンスおよび主要な回復アクティビティのための Microsoft BitLocker の管理および監視レポートの理解に役立つために使用できます。

**注** Microsoft BitLocker の管理と監視 (MBAM) をインストールしたときに Configuration Manager トポロジを選択した場合、レポートは MBAM からではなく構成マネージャーから生成されます。 構成マネージャーから実行されるレポートの詳細については、「 [Configuration manager での MBAM レポートに](understanding-mbam-reports-in-configuration-manager.md)ついて」を参照してください。

 

## レポートについて


Microsoft BitLocker の管理と監視のレポート機能にアクセスするには、web ブラウザーを開き、管理と監視の web サイトを開きます。 左側のメニューバーで [**レポート**] を選択し、トップメニューバーで、生成するレポートの種類を選択します。

### エンタープライズコンプライアンスレポート

このレポートの種類を使用して、組織内の全体的な BitLocker のコンプライアンスに関する情報を収集します。 さまざまなフィルターを使って、検索結果をコンプライアンスの状態やエラー状態に絞り込むことができます。 レポート情報は6時間ごとに更新されます。

**エンタープライズコンプライアンスレポートのフィールド**

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
<td align="left"><p>MBAM で管理されているユーザー指定の DNS 名。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ドメイン名</p></td>
<td align="left"><p>クライアントコンピューターが存在し、MBAM で管理されている完全修飾ドメイン名。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>コンプライアンスの状態</p></td>
<td align="left"><p>コンピューターに対して指定されたポリシーに従って、コンピューターのコンプライアンスの状態を指定します。 状態は準拠していないため、準拠しています。 コンプライアンスの状態を解釈する方法について詳しくは、「エンタープライズコンプライアンスレポートのコンプライアンス状態」をご覧ください。</p></td>
</tr>
<tr class="even">
<td align="left"><p>コンプライアンスステータスの詳細</p></td>
<td align="left"><p>指定したポリシーに従って、コンピューターのコンプライアンスの状態に関するエラーメッセージと状態メッセージ。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>最終連絡先</p></td>
<td align="left"><p>コンピューターが最後にサーバーに接続してコンプライアンス状態を報告した日付と時刻。 連絡先の頻度は構成可能です (「MBAM ポリシー設定」をご覧ください)。</p></td>
</tr>
</tbody>
</table>

 

**企業のコンプライアンスレポートのコンプライアンスの状態**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コンプライアンスの状態</th>
<th align="left">除外</th>
<th align="left">説明</th>
<th align="left">ユーザーの操作</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>互換性</p></td>
<td align="left"><p>非課税</p></td>
<td align="left"><p>指定したポリシーに従って、コンピューターが準拠していません。</p></td>
<td align="left"><p>[ <strong> コンピューター名 </strong> ] をクリックして、各ドライブの状態が指定したポリシーに準拠しているかどうかを確認します。 暗号化の状態にコンピューターが暗号化されていないことが示されている場合は、暗号化が処理中であるか、またはコンピューターにエラーが発生している可能性があります。 エラーがない場合、原因としては、コンピューターがまだ暗号化状態の接続または確立のプロセスを行っていることが考えられます。 後でもう一度確認して、状態が変わっていないかどうかを確認します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>仕様</p></td>
<td align="left"><p>非課税</p></td>
<td align="left"><p>指定したポリシーに従って、コンピューターは準拠しています。</p></td>
<td align="left"><p>操作は必要ありません。コンピューターのコンプライアンスレポートを表示することで、コンピューターの状態を確認できます。</p></td>
</tr>
</tbody>
</table>

 

### コンピューターのコンプライアンスレポート

このレポートの種類を使用して、コンピューターまたはユーザーに固有の情報を収集します。

このレポートを表示するには、[エンタープライズコンプライアンス] レポートでコンピューター名をクリックするか、コンピューターのコンプライアンスレポートでコンピューター名を入力します。 コンピューターのコンプライアンスレポートは、コンピューター上の各ドライブ (オペレーティングシステムと固定データドライブ) に関する詳細な暗号化情報を提供します。また、コンピューター上の各ドライブの種類に適用されるポリシーを示しています。 各ドライブの詳細を表示するには、[コンピューター名] エントリを展開します。

**注** リムーバブルデータボリュームの暗号化の状態は、レポートには表示されません。

 

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
<td align="left"><p>MBAM で管理されている、ユーザーが指定した DNS コンピューター名。</p></td>
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
<td align="left"><p>MBAM 管理クライアントコンピューターで検出されたオペレーティングシステムの種類。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>コンプライアンスの状態</p></td>
<td align="left"><p>MBAM で管理されているコンピューターの全体のコンプライアンス状態。 有効な状態は、準拠して準拠していません。 ドライブあたりのコンプライアンスの状態 (次の表を参照) は、異なるコンプライアンスの状態を示している可能性があることに注意してください。 ただし、このフィールドは、指定したポリシーに従って、コンプライアンスの状態を表します。</p></td>
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
<td align="left"><p>製造元</p></td>
<td align="left"><p>コンピューターの BIOS に表示されるコンピューターの製造元名。</p></td>
</tr>
<tr class="even">
<td align="left"><p>モデル</p></td>
<td align="left"><p>コンピューターの BIOS に表示されたコンピューターの製造元のモデル名。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>コンプライアンスステータスの詳細</p></td>
<td align="left"><p>指定したポリシーに従って、コンピューターのコンプライアンスの状態に関するエラーメッセージと状態メッセージ。</p></td>
</tr>
<tr class="even">
<td align="left"><p>最終連絡先</p></td>
<td align="left"><p>コンピューターがコンプライアンス状態を報告するためにサーバーに最後に接続した日時です。 連絡先の頻度は構成可能です (「MBAM ポリシー設定」をご覧ください)。</p></td>
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
<td align="left"><p>オペレーティングシステムまたは固定データボリュームの暗号化に使用されるポリシーによって選択されたプロテクターの種類。</p></td>
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

 

### 回復監査レポート

このレポートの種類を使用して、回復キーへのアクセスを要求したユーザーを監査します。 レポートには、目的のフィルター条件に基づいて、いくつかのフィルターが用意されています。 ユーザーは、ヘルプデスクユーザーまたはエンドユーザー、要求が失敗したか、成功したか、要求された特定の種類のキー、取得した日付の範囲など、特定の種類のユーザーに対してフィルター処理できます。 管理者は、必要に応じてコンテキストレポートを作成できます。

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
<td align="left"><p>リクエストの状態</p></td>
<td align="left"><p>リクエストのステータス。 有効な状態は、成功したか (キーが取得された)、失敗した (キーが取得されなかった) かどうか。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ヘルプデスクユーザー</p></td>
<td align="left"><p>キーの取得要求を開始したヘルプデスクユーザー。 注: ヘルプデスクのユーザーがエンドユーザーの代わりにキーを取得した場合、[エンドユーザー] フィールドは空白になります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ユーザー</p></td>
<td align="left"><p>キーの取得要求を開始したエンドユーザー。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>キーの種類</p></td>
<td align="left"><p>ヘルプデスクユーザーまたはエンドユーザーによって要求されたキーの種類。 MBAM で収集される3種類のキーには、回復キーパスワード (回復モードでコンピューターを回復するために使用されます)、回復キー ID (別のユーザーの代わりに回復モードでコンピューターを回復する場合に使用)、TPM パスワードハッシュ (ロックされた TPM を使用してコンピューターを回復するために使用) があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>理由の説明</p></td>
<td align="left"><p>理由指定されたキーの種類が、ヘルプデスクユーザーまたはエンドユーザーによって要求された理由です。 この理由は、ドライブの回復で指定され、管理と監視の web サイトの TPM 機能を管理します。 有効なエントリは、ユーザーが入力したテキスト、または次の理由コードのいずれかです。</p>
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

 

**注** レポートの結果をファイルに保存するには、[レポート] メニューバーの [**エクスポート**] をクリックします。 MBAM レポートの実行方法の詳細については、「 [Mbam レポートを生成する方法](how-to-generate-mbam-reports-mbam-2.md)」を参照してください。

 

## 関連トピック


[MBAM 2.0 での BitLocker 準拠の監視とレポート](monitoring-and-reporting-bitlocker-compliance-with-mbam-20-mbam-2.md)

 

 





