---
title: MBAM レポートの概要
description: MBAM レポートの概要
author: dansimp
ms.assetid: 34e4aaeb-7f89-41a1-b816-c6fe8397b060
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa64a4724c87a42774e569b556013bfec2ed5514
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822867"
---
# MBAM レポートの概要


Microsoft BitLocker の管理と監視 (MBAM) では、BitLocker の使用状況とコンプライアンスを監視するさまざまなレポートが生成されます。 このトピックでは、企業のコンプライアンス、個々のコンピューター、ハードウェアの互換性、およびキーの回復アクティビティに関する MBAM レポートについて説明します。

## レポートについて


MBAM のレポート機能にアクセスするには、MBAM 管理 web サイトを開きます。 ナビゲーションウィンドウで [**レポート**] を選択します。 次に、[メインコンテンツ] ウィンドウで、レポートの種類のタブをクリックします。**エンタープライズコンプライアンスレポート**、**コンピューターのコンプライアンスレポート**、**ハードウェア監査レポート**、または**回復監査レポート**。

### エンタープライズコンプライアンスレポート

エンタープライズコンプライアンスレポートは、組織内の全体的な BitLocker のコンプライアンスに関する情報を提供します。 このレポートで利用可能なフィルターを使用すると、コンプライアンスの状態やエラー状態に応じて、検索結果を絞り込むことができます。 このレポートは6時間ごとに実行されます。

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
<td align="left"><p>コンピューターに指定されているポリシーに従って、コンピューターのコンプライアンスの状態。 可能な状態は、準拠していません。 詳細については、このトピックの「エンタープライズコンプライアンスレポートのコンプライアンスの状態」を参照してください。</p></td>
</tr>
<tr class="even">
<td align="left"><p>除外</p></td>
<td align="left"><p>ハードウェアの種類の識別を決定するコンピューターハードウェアの状態と、コンピューターがポリシーの適用除外を行っているかどうかを示します。 次の3つの状態があります。ハードウェア不明 (ハードウェアの種類は MBAM によって識別されていません)、ハードウェアの除外 (ハードウェアの種類は、MBAM policy から除外されたものとマークされていましたが、ハードウェアはポリシーに適用されていませんでした)。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>デバイスユーザー</p></td>
<td align="left"><p>MBAM で管理されているコンピューター上の既知のユーザー。</p></td>
</tr>
<tr class="even">
<td align="left"><p>コンプライアンスステータスの詳細</p></td>
<td align="left"><p>指定したポリシーに従った、コンピューターのコンプライアンスの状態に関するエラーメッセージと状態メッセージ。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>最終連絡先</p></td>
<td align="left"><p>コンピューターが最後にサーバーに接続してコンプライアンス状態を報告した日付と時刻。 この時刻は構成可能です。 「MBAM ポリシーの設定」を参照してください。</p></td>
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
<td align="left"><p>指定したポリシーに準拠していないコンピューターで、ハードウェアの種類がポリシーの適用除外として指定されていない。</p></td>
<td align="left"><p>[ <strong> コンピューター名] をクリックして </strong> 、コンピューターのコンプライアンスレポートを展開し、各ドライブの状態が指定したポリシーに準拠しているかどうかを確認します。 暗号化の状態にコンピューターが暗号化されていないことが示されている場合、暗号化が処理中であるか、またはコンピューターにエラーが発生している可能性があります。 エラーがない場合、原因としては、コンピューターがまだ暗号化状態の接続または確立のプロセスを行っていることが考えられます。 後でもう一度確認して、状態が変わっていないかどうかを確認します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>仕様</p></td>
<td align="left"><p>非課税</p></td>
<td align="left"><p>コンピューターは、指定されたポリシーに準拠しています。</p></td>
<td align="left"><p>操作は必要ありません。 必要に応じて、コンピューターのコンプライアンスレポートを表示して、コンピューターの状態を確認することができます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>仕様</p></td>
<td align="left"><p>ハードウェア適用除外</p></td>
<td align="left"><p>ハードウェアの種類が免税の場合。 ポリシーがどのように設定されているか、または各ハードドライブの個々の状態に関係なく、全体的な状態は準拠するものと見なされます。</p></td>
<td align="left"><p>操作は必要ありません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>仕様</p></td>
<td align="left"><p>ハードウェア不明</p></td>
<td align="left"><p>MBAM はハードウェアの種類を認識していますが、MBAM は、除外されているかどうかを確認しません。 これは、管理者がハードウェアの互換性の状態を設定していない場合に発生します。 そのため、既定では、MBAM は準拠状態に戻ります。</p></td>
<td align="left"><p>これは、新しく展開された MBAM クライアントの初期状態です。 通常は一時的な状態でしかありません。 管理者がハードウェアを互換性のあるものとしてマークしている場合でも、クライアントコンピューターが再び報告される前に、大幅な遅延、または構成可能な待ち時間が発生する可能性があります。 最後の連絡先の時刻をメモし、指定した間隔の後にもう一度チェックインして、状態が変わったかどうかを確認します。 状態が変更されていない場合は、このコンピューターまたはハードウェアの種類にエラーが発生している可能性があります。</p></td>
</tr>
</tbody>
</table>

 

### コンピューターのコンプライアンスレポート

コンピューターのコンプライアンスレポートには、コンピューターまたはユーザーに固有の情報が表示されます。

コンピューターのコンプライアンスレポートは、オペレーティングシステムドライブや固定データドライブなど、コンピューター上の各ドライブについて、詳細な暗号化情報と適用されるポリシーを提供します。 このレポートの種類を表示するには、[エンタープライズコンプライアンス] レポートでコンピューター名をクリックするか、コンピューターのコンプライアンスレポートでコンピューター名を入力します。 各ドライブの詳細を表示するには、[コンピューター名] エントリを展開します。

**注** このレポートでは、リムーバブルデータボリュームの暗号化の状態は提供されません。

 

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
<td align="left"><p>MBAM で管理されているユーザー指定の DNS コンピューター名。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ドメイン名</p></td>
<td align="left"><p>クライアントコンピューターが存在し、MBAM で管理されている完全修飾ドメイン名。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>コンピュータの種類</p></td>
<td align="left"><p>コンピュータの移植性の種類。 有効な型は、ポータブルでもポータブルでもありません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>オペレーティング システム</p></td>
<td align="left"><p>MBAM 管理クライアントコンピューターにインストールされているオペレーティングシステムの種類。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>コンプライアンスの状態</p></td>
<td align="left"><p>MBAM で管理されているコンピューターの全体的なコンプライアンスの状態。 有効な状態は、準拠して準拠していません。 同じコンピューターに準拠しているドライブと準拠していないドライブを含めることはできますが、このフィールドには、指定したポリシーごとの全体的なコンピューターのコンプライアンスが示されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ポリシー Cypher 強度</p></td>
<td align="left"><p>MBAM ポリシー仕様に基づいて管理者によって選択された暗号強度。 たとえば、ディフューザー付きの128ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ポリシーのオペレーティングシステムドライブ</p></td>
<td align="left"><p>O/S とプロテクターの種類に対して暗号化が必要かどうかを示します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ポリシー固定データドライブ</p></td>
<td align="left"><p>固定ドライブで暗号化が必要かどうかを示します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ポリシーのリムーバブルデータドライブ</p></td>
<td align="left"><p>リムーバブルドライブに暗号化が必要かどうかを示します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>デバイスユーザー</p></td>
<td align="left"><p>コンピューター上の既知のユーザーの id を提供します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>除外</p></td>
<td align="left"><p>コンピューターのハードウェアの種類が MBAM で認識されているかどうかを示します。また、既知の場合は、コンピューターがポリシーの適用除外として示されているかどうかを示します。 [ハードウェア不明] という3つの状態があります (ハードウェアの種類は MBAM で識別されていません)。ハードウェア除外 (ハードウェアの種類は、MBAM ポリシーの適用除外として指定されました)除外されていない (ハードウェアは認識されており、ポリシーの対象外である)。</p></td>
</tr>
<tr class="even">
<td align="left"><p>製造元</p></td>
<td align="left"><p>コンピューターの BIOS に表示されるコンピューターの製造元名。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>モデル</p></td>
<td align="left"><p>コンピューターの BIOS に表示されるコンピューターの製造元のモデル名。</p></td>
</tr>
<tr class="even">
<td align="left"><p>コンプライアンスステータスの詳細</p></td>
<td align="left"><p>指定したポリシーに従って、コンピューターのコンプライアンスの状態に関するエラーメッセージと状態メッセージ。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>最終連絡先</p></td>
<td align="left"><p>コンピューターがコンプライアンス状態を報告するためにサーバーに最後に接続した日時です。 T</p></td>
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
<td align="left"><p>ユーザーがこの特定のドライブに割り当てたコンピューターのドライブ文字です。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ドライブの種類</p></td>
<td align="left"><p>ドライブの種類。 有効な値は、オペレーティングシステムドライブと固定データドライブです。 これらは論理ボリュームではなく物理ドライブです。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Cypher 強度</p></td>
<td align="left"><p>MBAM ポリシー仕様に基づいて管理者によって選択された暗号強度。</p></td>
</tr>
<tr class="even">
<td align="left"><p>プロテクターの種類</p></td>
<td align="left"><p>オペレーティングシステムまたは固定ボリュームの暗号化に使用するポリシーによって選択されたプロテクターの種類。 オペレーティングシステムドライブ上の有効なプロテクターの種類は、TPM または TPM + PIN です。 固定データボリュームの有効な保護機能の種類は、パスワードのみです。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>プロテクターの状態</p></td>
<td align="left"><p>このフィールドは、コンピューターでポリシーに指定されているプロテクターの種類が有効になっているかどうかを示します。 有効な状態は、オンまたはオフです。</p></td>
</tr>
<tr class="even">
<td align="left"><p>暗号化の状態</p></td>
<td align="left"><p>これは、ドライブの現在の暗号化の状態です。 有効な状態は、暗号化され、暗号化されず、暗号化されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>コンプライアンスの状態</p></td>
<td align="left"><p>ドライブがポリシーに準拠しているかどうかを示します。 状態は準拠していないため、準拠しています。</p></td>
</tr>
<tr class="even">
<td align="left"><p>コンプライアンスステータスの詳細</p></td>
<td align="left"><p>コンピューターのコンプライアンスの状態に関するエラーと状態のメッセージが含まれています。</p></td>
</tr>
</tbody>
</table>

 

### ハードウェア監査レポート

このレポートは、特定のコンピューターの作成およびモデルのハードウェア互換性状態の変更を監査するのに役立ちます。 検索結果を絞り込むために、このレポートには、変更の種類や発生時間などの条件に対するフィルターが含まれています。 各状態の変更は、ユーザーと日付と時刻によって追跡されます。 ハードウェアの種類は、クライアントコンピューターで実行される MBAM エージェントによって自動的に設定されます。 このレポートは、MBAM 管理コンピューターから直接収集された情報に対するユーザーによる変更を追跡します。 一般的な管理上の変更は、互換性のあるものから互換性がないものに変更されます。 ただし、管理者はフィールドを変更することもできます。

**ハードウェア監査レポートのフィールド**

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
<td align="left"><p>日付と時刻</p></td>
<td align="left"><p>ハードウェアの種類に変更が加えられた日付と時刻。 すべての固有のハードウェアの種類が、少なくとも1つのエントリに割り当てられていることに注意してください。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ユーザー</p></td>
<td align="left"><p>特定のエントリに変更を加えた管理ユーザー。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>種類を変更する</p></td>
<td align="left"><p>ハードウェアの種類情報に加えられた変更の種類。 有効な値は、追加 (新しいエントリ)、更新 (既存のエントリの変更)、または削除 (既存のエントリの削除) です。</p></td>
</tr>
<tr class="even">
<td align="left"><p>元の値</p></td>
<td align="left"><p>変更が加えられる前のハードウェアの種類仕様の値。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>現在価値</p></td>
<td align="left"><p>変更が加えられた後のハードウェアの種類仕様の値。</p></td>
</tr>
</tbody>
</table>

 

### 回復監査レポート

回復監査レポートは、回復キーへのアクセスを要求したユーザーを監査するのに役立ちます。 このレポートのフィルター条件には、要求を行っているユーザーの種類、要求されたキーの種類、発生の時間、発生時間、ユーザー要求の種類 (ヘルプデスク、エンドユーザー) が含まれます。 このレポートを使用すると、管理者は必要に応じてコンテキストレポートを作成できます。

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
<td align="left"><p>エンドユーザーまたはヘルプデスクユーザーによってキーの取得要求が行われた日付と時刻。</p></td>
</tr>
<tr class="even">
<td align="left"><p>リクエストの状態</p></td>
<td align="left"><p>リクエストのステータス。 有効な状態は、成功したか (キーが取得された)、失敗した (キーが取得されなかった) かどうか。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ヘルプデスクユーザー</p></td>
<td align="left"><p>キーの取得要求を開始したヘルプデスクのユーザー。 ヘルプデスクのユーザーがエンドユーザーの代わりにキーを取得した場合、[終了ユーザー] フィールドは空白になります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ユーザー</p></td>
<td align="left"><p>キーの取得要求を開始したエンドユーザー。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>キーの種類</p></td>
<td align="left"><p>要求されたキーの種類。 MBAM は、回復キーパスワード (回復モードでコンピューターを回復する) という3種類のキーを収集します。回復キー ID (別のユーザーの代わりに回復モードでコンピューターを回復する場合)。トラステッドプラットフォームモジュール (TPM) パスワードハッシュ (ロックされている TPM を使用してコンピューターを回復します)。</p></td>
</tr>
<tr class="even">
<td align="left"><p>理由の説明</p></td>
<td align="left"><p>指定したキーの種類が要求された理由。 この理由は、ドライブの回復で指定され、管理 web サイトの TPM 機能を管理します。 有効なエントリには、ユーザーが入力したテキスト、または次の理由コードのいずれかが含まれます。</p>
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
</ul>
<p></p></td>
</tr>
</tbody>
</table>

 

**注** レポートの結果をファイルに保存するには、[レポート] メニューバーの [**エクスポート**] ボタンをクリックします。

 

## 関連トピック


[MBAM 1.0 での BitLocker 準拠の監視とレポート](monitoring-and-reporting-bitlocker-compliance-with-mbam-10.md)

 

 





