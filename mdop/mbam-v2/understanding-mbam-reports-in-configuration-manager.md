---
title: Configuration Manager の MBAM レポートの概要
description: Configuration Manager の MBAM レポートの概要
author: dansimp
ms.assetid: b2582190-c9de-4e64-bd5a-f31ac1916f53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 995d628cafd03c8bdd209e467c9d22169b7e03c3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823824"
---
# Configuration Manager の MBAM レポートの概要


Configuration Manager の統合トポロジを使用して Microsoft BitLocker の管理と監視 (MBAM) をインストールすると、ハードウェアのコンプライアンスとレポート機能は構成マネージャーインフラストラクチャに移動され、MBAM から除外されます。 Configuration Manager トポロジを使用している場合は、MBAM からではなく構成マネージャーからレポートを実行します。ただし、引き続き管理と監視の Web サイトを使用してアクセスする回復監査レポートは除きます。

Configuration Manager の統合されたトポロジのレポートには、企業の BitLocker のコンプライアンス、および MBAM 管理されている個々のコンピューターとデバイスが表示されます。 レポートには、表形式の情報とグラフの両方が用意されており、レポートをフィルター処理してさまざまな視点からのデータを表示することができます。

このトピックでは、Configuration Manager から実行する MBAM レポートについて説明します。 スタンドアロントポロジ用の MBAM レポートの詳細については、「 [MBAM レポートについ](understanding-mbam-reports-mbam-2.md)て」を参照してください。

## Configuration Manager でレポートにアクセスする


Configuration Manager のレポート機能にアクセスするには、 **Configuration manager コンソール**を開きます。 利用可能なレポートの一覧を表示するには、次の操作を行います。

-   Configuration Manager 2007 で、[**コンピューターの管理**] ノードを展開し、[**レポート**] ノードを展開します。

-   SystemCenter2012 ConfigurationManager の [**概要**] の下にある [監視] ワークスペースで、[**レポート**] ノードを展開し、[**レポート**] をクリックします。

### BitLocker エンタープライズコンプライアンスダッシュボード

BitLocker Enterprise コンプライアンスダッシュボードには、次のグラフが用意されています。これは、企業全体での BitLocker のコンプライアンスの状態を示します。

-   コンプライアンスの状態の配布

-   不適合エラー分布

-   ドライブの種類によるコンプライアンスの状態の配布

**コンプライアンスの状態の配布**

この円グラフは、企業内のコンピューターのコンプライアンスの状態を示し、選択されたコレクション内のコンピューターの合計数と比較して、そのコンプライアンスの状態を表示しているコンピューターの割合を示します。 各状態の実際のコンピューターの数も表示されます。 円グラフには、次のコンプライアンスの状態が表示されます。

-   仕様

-   非準拠

-   ユーザの除外

-   テンポラリユーザの除外

-   ポリシーが適用されない

-   不明-状態がエラーとして報告された、またはコレクションの一部であるが、組織から切断されているなど、コンプライアンスの状態を報告していないコンピューター

**不適合エラー分布**

この円グラフには、BitLocker ドライブ暗号化ポリシーに準拠していない企業内のコンピューターのカテゴリが表示され、各カテゴリのコンピューターの数が表示されます。 各カテゴリのパーセンテージは、コレクション内の非準拠コンピューターの合計数から計算されます。

-   ユーザーによる暗号化の延期

-   互換性のある TPM が見つかりません

-   システムパーティションが利用できない、または大きすぎる

-   ポリシーの競合

-   TPM 自動プロビジョニングを待機しています

-   不明なエラーが発生しました

-   情報なし: MBAM クライアントがインストールされていない場合、または MBAM クライアントがインストールされていても、ライセンス認証されていない場合は、サービスが機能していないことを示します。

**ドライブの種類によるコンプライアンスの状態の配布**

この棒グラフは、ドライブの種類別の現在の BitLocker コンプライアンスの状態を示します。 状態は、"準拠" および "非準拠" です。 固定データドライブとオペレーティングシステムドライブの場合は、バーが表示されます。 固定データドライブを持っていないコンピューターは、オペレーティングシステムのドライブバーにのみ表示されます。 このグラフには、BitLocker ドライブ暗号化ポリシーまたは "ポリシーなし" カテゴリの除外を許可されているユーザーは含まれません。

### BitLocker Enterprise コンプライアンスの詳細レポート

このレポートには、BitLocker の使用を目的としたコンピューターのコレクションに対する、エンタープライズ全体での BitLocker のコンプライアンス全体に関する情報が表示されます。

**BitLocker エンタープライズコンプライアンスの詳細レポートフィールド**

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
<td align="left"><p>% 不明のコンプライアンス</p></td>
<td align="left"><p>コンプライアンスの状態が不明なコンピューターの割合。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>% 免税</p></td>
<td align="left"><p>BitLocker 暗号化要件から除外されたコンピューターの割合。</p></td>
</tr>
<tr class="even">
<td align="left"><p>% 免税以外</p></td>
<td align="left"><p>BitLocker 暗号化要件から除外されたコンピューターの割合。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>仕様</p></td>
<td align="left"><p>企業内の準拠しているコンピューターの割合。</p></td>
</tr>
<tr class="even">
<td align="left"><p>準拠していない</p></td>
<td align="left"><p>企業内の非準拠コンピューターの割合。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>不明なコンプライアンス</p></td>
<td align="left"><p>コンプライアンスの状態が不明なコンピューターの割合。</p></td>
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

 

**BitLocker エンタープライズコンプライアンスの詳細レポート-コンプライアンスの状態**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コンプライアンスの状態</th>
<th align="left">除外</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>互換性</p></td>
<td align="left"><p>非課税</p></td>
<td align="left"><p>指定したポリシーに従って、コンピューターが準拠していません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>仕様</p></td>
<td align="left"><p>非課税</p></td>
<td align="left"><p>コンピューターは、指定されたポリシーに準拠しています。</p></td>
</tr>
</tbody>
</table>

 

### BitLocker Enterprise コンプライアンスサマリーレポート

このレポートの種類を使用して、組織全体の BitLocker のコンプライアンス全体に関する情報を表示したり、BitLocker の使用を目的としているコンピューターのコレクション内にある個々のコンピューターのコンプライアンスを表示したりします。

**BitLocker エンタープライズコンプライアンスの概要レポートフィールド**

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
<td align="left"><p>% 不明のコンプライアンス</p></td>
<td align="left"><p>コンプライアンスの状態が不明なコンピューターの割合。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>% 免税</p></td>
<td align="left"><p>BitLocker 暗号化要件から除外されたコンピューターの割合。</p></td>
</tr>
<tr class="even">
<td align="left"><p>% 免税以外</p></td>
<td align="left"><p>BitLocker 暗号化要件から除外されたコンピューターの割合。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>仕様</p></td>
<td align="left"><p>企業内の準拠しているコンピューターの割合。</p></td>
</tr>
<tr class="even">
<td align="left"><p>準拠していない</p></td>
<td align="left"><p>企業内の非準拠コンピューターの割合。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>不明なコンプライアンス</p></td>
<td align="left"><p>コンプライアンスの状態が不明なコンピューターの割合。</p></td>
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

 

**BitLocker エンタープライズコンプライアンスの概要レポート-コンピューターの詳細**

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
<td align="left"><p>コンプライアンスの状態</p></td>
<td align="left"><p>MBAM で管理されているコンピューターの全体のコンプライアンス状態。 有効な状態は、準拠して準拠していません。 ドライブあたりのコンプライアンスの状態 (その後の表を参照) が、さまざまなコンプライアンスの状態を示している可能性があることに注目してください。 ただし、このフィールドは、指定したポリシーに従って、コンプライアンスの状態を表します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>除外</p></td>
<td align="left"><p>ユーザーが除外されているか、BitLocker ポリシーから除外されているかを示す状態。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>デバイスユーザー</p></td>
<td align="left"><p>デバイスのユーザー。</p></td>
</tr>
<tr class="even">
<td align="left"><p>コンプライアンスステータスの詳細</p></td>
<td align="left"><p>指定したポリシーに従って、コンピューターのコンプライアンスの状態に関するエラーメッセージと状態メッセージ。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>最終連絡先</p></td>
<td align="left"><p>コンピューターがコンプライアンス状態を報告するためにサーバーに最後に接続した日時です。 連絡先の頻度は構成可能です (「MBAM ポリシー設定」をご覧ください)。</p></td>
</tr>
</tbody>
</table>

 

### BitLocker コンピューターのコンプライアンスレポート

このレポートの種類を使用して、コンピューターに固有の情報を収集します。 コンピューターのコンプライアンスレポートは、コンピューター上の各ドライブ (オペレーティングシステムと固定データドライブ) に関する詳細な暗号化情報を提供します。また、コンピューター上の各ドライブの種類に適用されるポリシーを示しています。 各ドライブの詳細を表示するには、[コンピューター名] エントリを展開します。

**注** リムーバブルデータボリュームの暗号化の状態は、レポートには表示されません。

 

**BitLocker コンピューターのコンプライアンスレポート–コンピューターの詳細のフィールド**

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
<td align="left"><p>全体のコンプライアンス</p></td>
<td align="left"><p>MBAM で管理されているコンピューターの全体のコンプライアンス状態。 有効な状態は、準拠して準拠していません。 ドライブあたりのコンプライアンスの状態 (その後の表を参照) が、さまざまなコンプライアンスの状態を示している可能性があることに注目してください。 ただし、このフィールドは、指定したポリシーに従って、コンプライアンスの状態を表します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>オペレーティングシステムのコンプライアンス</p></td>
<td align="left"><p>MBAM で管理されているオペレーティングシステムのコンプライアンスの状態。 有効な状態は、準拠して準拠していません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>固定データドライブのコンプライアンス</p></td>
<td align="left"><p>MBAM で管理されている固定データドライブのコンプライアンスステータス。 有効な状態は、準拠して準拠していません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>最終更新日</p></td>
<td align="left"><p>コンピューターがコンプライアンス状態を報告するためにサーバーに最後に接続した日時です。 連絡先の頻度は構成可能です (「MBAM ポリシー設定」をご覧ください)。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>除外</p></td>
<td align="left"><p>ユーザーが除外されているか、BitLocker ポリシーから除外されているかを示す状態。</p></td>
</tr>
<tr class="even">
<td align="left"><p>除外対象ユーザー</p></td>
<td align="left"><p>BitLocker ポリシーから除外されているユーザー。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>免税日</p></td>
<td align="left"><p>免税が付与された日付。</p></td>
</tr>
<tr class="even">
<td align="left"><p>コンプライアンスステータスの詳細</p></td>
<td align="left"><p>指定したポリシーに従って、コンピューターのコンプライアンスの状態に関するエラーメッセージと状態メッセージ。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ポリシー暗号強度</p></td>
<td align="left"><p>MBAM ポリシー仕様に基づいて管理者によって選択された暗号強度。 (例: ディフューザー付きの128ビット)。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ポリシー: オペレーティングシステムドライブ</p></td>
<td align="left"><p>O/S と適切なプロテクターの種類に対して暗号化が必要かどうかを示します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ポリシー: 固定データドライブ</p></td>
<td align="left"><p>固定ドライブに暗号化が必要かどうかを示します。</p></td>
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
<td align="left"><p>デバイスユーザー</p></td>
<td align="left"><p>MBAM で管理されているコンピューター上の既知のユーザー。</p></td>
</tr>
</tbody>
</table>

 

**BitLocker コンピューターのコンプライアンスレポート–コンピューターのボリュームフィールド**

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
<td align="left"><p>オペレーティングシステムまたは固定ボリュームの暗号化に使用するポリシーによって選択されたプロテクターの種類。 オペレーティングシステムで有効なプロテクター型は、TPM または TPM + PIN であり、固定データボリュームにはパスワードです。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>プロテクターの状態</p></td>
<td align="left"><p>MBAM で管理されているコンピューターが、ポリシーで指定されているプロテクターの種類を有効にしていることを示します。 有効な状態は、オンまたはオフです。</p></td>
</tr>
<tr class="even">
<td align="left"><p>暗号化の状態</p></td>
<td align="left"><p>ドライブの暗号化の状態。 有効な状態は、暗号化され、暗号化されず、暗号化されます。</p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[MBAM と Configuration Manager の使用](using-mbam-with-configuration-manager.md)

 

 





