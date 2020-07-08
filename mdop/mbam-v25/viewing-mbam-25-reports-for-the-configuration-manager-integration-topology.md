---
title: MBAM 2.5 レポートの表示 (Configuration Manager 統合トポロジ)
description: MBAM 2.5 レポートの表示 (Configuration Manager 統合トポロジ)
author: dansimp
ms.assetid: 60d11b2f-3a76-4023-8da4-f89e9f35b790
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3384fee62d302ac47775fe106265456ef119ab47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824044"
---
# MBAM 2.5 レポートの表示 (Configuration Manager 統合トポロジ)


このトピックでは、Configuration Manager の統合トポロジを使用して Microsoft BitLocker 管理と監視 (MBAM) を構成するときに使用できるレポートについて説明します。 このレポートには、エンタープライズの BitLocker コンプライアンスと、MBAM 管理されている個々のコンピューターとデバイスが表示されます。 レポートには表形式の情報とグラフが用意されており、さまざまな視点からのデータを表示できるフィルターがあります。

Configuration Manager の統合トポロジでは、管理と監視の Web サイトからではなく、構成マネージャーからレポートを表示します。**回復監査レポート**は除き、管理と監視の web サイトから引き続き表示できます。

スタンドアロントポロジ用の MBAM レポートについては、「 [mbam 2.5 レポートでスタンドアロントポロジを表示](viewing-mbam-25-reports-for-the-stand-alone-topology.md)する」を参照してください。

## Configuration Manager でレポートにアクセスする


構成マネージャーでレポート機能にアクセスするには、次の操作を行います。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Configuration Manager のバージョン</th>
<th align="left">レポートを表示する方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>SystemCenter2012 ConfigurationManager</p></td>
<td align="left"><ol>
<li><p>左側のウィンドウで、[監視] ワークスペースを選択し <strong> </strong> ます。</p></li>
<li><p>ツリーで、[ <strong> 概要 </strong> &gt; <strong> レポート </strong> &gt; <strong> レポート </strong> &gt; <strong> mbam </strong> ] を展開します。</p></li>
<li><p>レポートを表示する言語を表すフォルダーを選択し、右側のウィンドウからレポートを選択します。</p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p>Configuration Manager 2007</p></td>
<td align="left"><ol>
<li><p>左側のウィンドウで、[ <strong> コンピューター管理] レポート </strong> &gt; <strong> </strong> &gt; <strong> サービス </strong> &gt; <strong> &lt; サーバー名 &gt; </strong> &gt; <strong> レポートフォルダー </strong> &gt; <strong> mbam </strong> を展開します。</p></li>
<li><p>レポートを表示する言語を表すフォルダーを選択し、右側のウィンドウからレポートを選択します。</p></li>
</ol></td>
</tr>
</tbody>
</table>

 

## Configuration Manager のレポートの説明


構成マネージャーの統合トポロジおよびスタンドアロントポロジのレポートには、いくつかのわずかな違いがあります。 以下のセクションでは、Configuration Manager 統合トポロジの MBAM レポートのデータについて説明します。

-   [BitLocker エンタープライズコンプライアンスダッシュボード](#bkmk-dashboard)

-   [BitLocker Enterprise コンプライアンスの詳細](#bkmk-compliancedetails)

-   [BitLocker Enterprise コンプライアンスの概要](#bkmk-compliancesummary)

-   [BitLocker コンピューターのコンプライアンスレポート](#bkmk-compliancereport)

### <a href="" id="bkmk-dashboard"></a>BitLocker エンタープライズコンプライアンスダッシュボード

BitLocker Enterprise コンプライアンスダッシュボードには、次のグラフが用意されています。これは、企業全体での BitLocker のコンプライアンスの状態を示します。

-   コンプライアンスの状態の配布

-   不適合エラー分布

-   ドライブの種類によるコンプライアンスの状態の配布

**コンプライアンスの状態の配布**

この円グラフは、企業内のコンピューターのコンプライアンスの状態を示します。 また、選択したコレクション内のコンピューターの合計数と比較して、そのコンプライアンスの状態を示すコンピューターの割合も表示されます。 各状態の実際のコンピューターの数も表示されます。 円グラフには、次のコンプライアンスの状態が表示されます。

-   仕様

-   非準拠

-   ユーザの除外

-   テンポラリユーザの除外

-   ポリシーが適用されない

-   未. これらのコンピューターでは、状態エラーが報告されたか、またはコレクションの一部であるが、コンプライアンスの状態は報告していません。 コンピューターが組織から切断されていると、コンプライアンスの状態がない場合があります。

**不適合エラー分布**

この円グラフには、BitLocker ドライブ暗号化ポリシーに準拠していない企業内のコンピューターのカテゴリが表示され、各カテゴリのコンピューターの数が表示されます。 各カテゴリのパーセンテージは、コレクション内の非準拠コンピューターの合計数から計算されます。

-   ユーザーによる暗号化の延期

-   互換性のある TPM が見つかりません

-   システムパーティションが利用できない、または大きすぎる

-   ポリシーの競合

-   TPM 自動プロビジョニングを待機しています

-   不明なエラーが発生しました

-   情報がありません。 これらのコンピューターに MBAM クライアントがインストールされていない場合、または MBAM クライアントがインストールされていても、ライセンス認証されていない場合 (サービスが動作していない場合など)。

**ドライブの種類によるコンプライアンスの状態の配布**

この棒グラフは、ドライブの種類別の現在の BitLocker コンプライアンスの状態を示します。 状態は、**準拠**していないものであり、**準拠**していません。 固定データドライブとオペレーティングシステムドライブの場合は、バーが表示されます。 固定データドライブを持っていないコンピューターは、**オペレーティングシステムのドライブ**バーにのみ表示されます。 このグラフには、BitLocker ドライブ暗号化ポリシーまたはポリシーなしカテゴリの除外を許可されているユーザーは含まれません。

### <a href="" id="bkmk-compliancedetails"></a>BitLocker Enterprise コンプライアンスの詳細

このレポートには、BitLocker の使用を目的としたコンピューターのコレクションに対する、エンタープライズ全体での BitLocker のコンプライアンス全体に関する情報が表示されます。

**BitLocker エンタープライズコンプライアンスの詳細フィールド**

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
<td align="left"><p>コンプライアンスの状態が不明であるコンピューターの割合。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>% 免税</p></td>
<td align="left"><p>BitLocker 暗号化要件から除外されたコンピューターの割合。</p></td>
</tr>
<tr class="even">
<td align="left"><p>% 免税以外</p></td>
<td align="left"><p>BitLocker 暗号化要件の対象から除外されていないコンピューターの割合。</p></td>
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
<td align="left"><p>コンプライアンスの状態が不明であるコンピューターの割合。</p></td>
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

 

**BitLocker エンタープライズコンプライアンスの詳細の状態**

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

 

### <a href="" id="bkmk-compliancesummary"></a>BitLocker Enterprise コンプライアンスの概要

このレポートの種類を使用して、組織全体の BitLocker のコンプライアンス全体に関する情報を表示したり、BitLocker の使用を目的としているコンピューターのコレクション内にある個々のコンピューターのコンプライアンスを表示したりします。

**BitLocker エンタープライズコンプライアンスの概要フィールド**

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
<td align="left"><p>コンプライアンスの状態が不明であるコンピューターの割合。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>% 免税</p></td>
<td align="left"><p>BitLocker 暗号化要件から除外されたコンピューターの割合。</p></td>
</tr>
<tr class="even">
<td align="left"><p>% 免税以外</p></td>
<td align="left"><p>BitLocker 暗号化要件の対象から除外されていないコンピューターの割合。</p></td>
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
<td align="left"><p>コンプライアンスの状態が不明であるコンピューターの割合。</p></td>
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

 

**BitLocker Enterprise コンプライアンスサマリーコンピューターの詳細**

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
<td align="left"><p>MBAM で管理されているコンピューターの全体のコンプライアンス状態。 有効な状態は、準拠して準拠していません。 ドライブあたりのコンプライアンスの状態 (後の表を参照) が、異なるコンプライアンスの状態を示している可能性があることに注意してください。 ただし、このフィールドは、指定したポリシーに従って、コンプライアンスの状態を表します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>除外</p></td>
<td align="left"><p>ユーザーが除外されているか、非表示になっているかを BitLocker ポリシーから除外するかどうかを示す状態。</p></td>
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
<td align="left"><p>コンピューターがコンプライアンス状態を報告するためにサーバーに最後に接続した日時です。 連絡先の頻度は、グループポリシー設定を通じて構成できます。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-compliancereport"></a>BitLocker コンピューターのコンプライアンスレポート

このレポートの種類を使用して、コンピューターに固有の情報を収集します。 BitLocker コンピューターのコンプライアンスレポートは、コンピューター上の各ドライブ (オペレーティングシステムと固定データドライブ) に関する詳細な暗号化情報を提供します。 また、コンピューター上の各ドライブの種類に適用されるポリシーを示します。 各ドライブの詳細を表示するには、[コンピューター名] エントリを展開します。

**注** リムーバブルデータボリュームの暗号化の状態は、このレポートには表示されません。

 

**BitLocker コンピューターのコンプライアンスレポート: コンピューターの詳細フィールド**

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
<td align="left"><p>MBAM で管理されているコンピューターの全体のコンプライアンス状態。 有効な状態は、準拠して準拠していません。 ドライブあたりのコンプライアンスの状態 (後の表を参照) が、異なるコンプライアンスの状態を示している可能性があることに注意してください。 ただし、このフィールドは、指定したポリシーに準拠したコンプライアンスの状態を表します。</p></td>
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
<td align="left"><p>コンピューターがコンプライアンス状態を報告するためにサーバーに最後に接続した日時です。 連絡先の頻度は、グループポリシー設定を通じて構成できます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>除外</p></td>
<td align="left"><p>ユーザーが除外されているか、非表示になっているかを BitLocker ポリシーから除外するかどうかを示す状態。</p></td>
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
<td align="left"><p>MBAM ポリシー仕様の間に管理者によって選択された暗号強度 (例: ディフューザー付きの128ビット)。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ポリシー: オペレーティングシステムドライブ</p></td>
<td align="left"><p>オペレーティングシステムと適切なプロテクターの種類に対して暗号化が必要かどうかを示します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ポリシー: 固定データドライブ</p></td>
<td align="left"><p>固定データドライブに暗号化が必要かどうかを示します。</p></td>
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

 

**BitLocker コンピューターのコンプライアンスレポート: コンピューターのボリュームフィールド**

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
<td align="left"><p>オペレーティングシステムまたは固定データドライブの暗号化に使用するポリシーを通じて選択されたプロテクターの種類。 オペレーティングシステムの有効なプロテクターの種類は、TPM または TPM + PIN です。 固定データドライブの有効なプロテクター型はパスワードです。</p></td>
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


[MBAM 2.5 での BitLocker 準拠の監視とレポート](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)

 

## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





