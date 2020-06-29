---
title: レポートを生成する方法
description: レポートを生成する方法
author: dansimp
ms.assetid: 9f8ba28e-1993-4c11-a28a-493718051e5d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 930b7061d3e5e2fb9951d45b1422915836cbc00e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826994"
---
# レポートを生成する方法


次のレポートの種類は、MED-V で管理者が作成できます。

-   [[状態](#bkmk-generatingastatusreport)] — [状態] レポートを使用して、定義された期間に基づいて、すべてのアクティブユーザーとすべての med-v ワークスペースの現在の状態を確認します。 これには、サーバーに現在接続されているコンピューター、または現在接続されていない場合は、サーバーに最後に接続した日付と時刻、各コンピューターの状態、その他の関連情報が表示されます。

-   [アクティビティログ](#bkmk-generatinganactivitylogreport)—このレポートを使用して、定義された日付範囲内の特定のホストまたはユーザーからのイベントを確認します。

-   [エラーログ](#bkmk-generatinganerrorlogreport): このレポートを使用して、定義された日付範囲内の特定のホストまたはユーザーから発生したエラーを表示します。

レポートの結果は、適切な列名をクリックして、任意の列によって並べ替えることができます。

レポートの結果をグループ化するには、列見出しをレポートの一番上にドラッグします。 複数の列見出しをドラッグして、他の列の後に1つの列をグループ化します。

## <a href="" id="bkmk-generatingastatusreport"></a>進捗レポートを生成する方法


**進捗レポートを生成するには**

1.  [**レポート**の管理] ボタンをクリックします。

2.  **レポート**モジュールの [**レポートの種類**] メニューで、[**状態**] を選択し、[**生成**] をクリックします。

    [レポートパラメーター] ダイアログボックスが表示されます。

3.  [**レポートパラメーター** ] ダイアログボックスの [**日数**] フィールドに数値を入力するか、または矢印を使用して進捗レポートに含める日数を選択し、[ **OK]** をクリックします。

    進捗レポートが生成されます。 レポートパラメーターは、次の表で定義されています。

**クライアントの MED-V ワークスペースのプロパティ**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">プロパティ</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>時間</p></td>
<td align="left"><p>イベントが発生した日付と時刻。</p>
<div class="alert">
<strong>注</strong><br/><p>既定では、イベントは降順の日付で表示されます。 ただし、[受信時刻] 列をクリックして変更することができます。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>ユーザー名</p></td>
<td align="left"><p>イベントを開始したユーザー。</p>
<div class="alert">
<strong>注</strong><br/><p>ユーザーがログオンする前にイベントが発生した場合、ユーザー名はシステムです。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>ホスト名</p></td>
<td align="left"><p>ホストコンピューターの名前。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ワークスペース名</p></td>
<td align="left"><p>MED-V ワークスペースの名前。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ワークスペースコンピューター名</p></td>
<td align="left"><p>MED-V ワークスペースが実行されているコンピューターの名前。</p></td>
</tr>
<tr class="even">
<td align="left"><p>オンライン</p></td>
<td align="left"><p>クライアントコンピューターの現在の状態:</p>
<ul>
<li><p><strong>中断</strong></p></li>
<li><p><strong>&lt;ワークスペースが開始されたときの開始日&gt;</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>クライアントのバージョン</p></td>
<td align="left"><p>クライアントのバージョン番号。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ポリシーのバージョン</p></td>
<td align="left"><p>MED-V ワークスペースで現在使用されているポリシーバージョン。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>画像名</p></td>
<td align="left"><p>画像の名前。</p></td>
</tr>
<tr class="even">
<td align="left"><p>画像のバージョン</p></td>
<td align="left"><p>MED-V ワークスペースで現在使用されている画像のバージョン。</p>
<div class="alert">
<strong>注</strong><br/><p>MED-V ワークスペースバージョンがまだコンピューターにダウンロードされていない場合は、不明の場合があります。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-generatinganactivitylogreport"></a>アクティビティログレポートを生成する方法


**アクティビティログレポートを生成するには**

1.  [**レポート**の管理] ボタンをクリックします。

    レポートモジュールが表示されます。

2.  **レポート**モジュールの [**レポートの種類**] メニューで [**アクティビティログ**] を選択し、[**生成**] をクリックします。

3.  [**レポートパラメーター** ] ダイアログボックスで、次のパラメーターを1つ以上構成します。

    -   **日数**(日数): レポートに表示する日数。

    -   **ユーザー名**には、入力されたテキストがユーザー名に含まれているすべてのイベントがレポートに含まれます。

    -   [ **Host name contains**] —入力したテキストがホスト名に含まれているすべてのイベントがレポートに含まれます。

4.  **[OK]** をクリックします。

    選択されたイベントと日付でレポートが生成されます。 レポートパラメーターは、次の表で定義されています。

**アクティビティログレポートのプロパティ**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">プロパティ</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>イベント ID</p></td>
<td align="left"><p>イベント ID。</p></td>
</tr>
<tr class="even">
<td align="left"><p>重大度</p></td>
<td align="left"><p><strong>情報、エラー、警告</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p>カテゴリ</p></td>
<td align="left"><p>レポートで参照されているモジュール。</p></td>
</tr>
<tr class="even">
<td align="left"><p>説明</p></td>
<td align="left"><p>イベントの説明。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>受信時刻</p></td>
<td align="left"><p>サーバーでイベントが受信された日付と時刻。</p>
<div class="alert">
<strong>注</strong><br/><p>クライアントがオフラインで作業している場合、クライアントがオンラインであるときにサーバーはレポートを受け取ります。</p>
</div>
<div>

</div>
<div class="alert">
<strong>注</strong><br/><p>既定では、イベントは降順の日付で表示されます。 ただし、[受信時刻] 列をクリックして変更することができ <strong> </strong> ます。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>クライアント時間</p></td>
<td align="left"><p>クライアントのクロックに従ってイベントが発生した日付と時刻。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ホスト名</p></td>
<td align="left"><p>ホストコンピューターの名前。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ユーザー名</p></td>
<td align="left"><p>イベントを開始したユーザー。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ワークスペース名</p></td>
<td align="left"><p>MED-V ワークスペースの名前。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ワークスペースコンピューター名</p></td>
<td align="left"><p>MED-V ワークスペースが実行されているコンピューターの名前。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-generatinganerrorlogreport"></a>エラーログレポートを生成する方法


**エラーログレポートを生成するには**

1.  [**レポート**の管理] ボタンをクリックします。

2.  **レポート**モジュールの [**レポートの種類**] メニューで、[**エラーログ**] を選択し、[**生成**] をクリックします。

3.  [**レポートパラメーター** ] ダイアログボックスで、次のパラメーターを1つ以上構成します。

    -   **日数**(日数): レポートに表示する日数。

    -   **ユーザー名**には、入力されたテキストがユーザー名に含まれているすべてのイベントがレポートに含まれます。

    -   [ **Host name contains**] —入力したテキストがホスト名に含まれているすべてのイベントがレポートに含まれます。

4.  **[OK]** をクリックします。

    選択されたイベントと日付でレポートが生成されます。 レポートパラメーターは、次の表で定義されています。

**エラーログレポートのプロパティ**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">プロパティ</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>イベント ID</p></td>
<td align="left"><p>イベント ID。</p></td>
</tr>
<tr class="even">
<td align="left"><p>カテゴリ</p></td>
<td align="left"><p>レポートで参照されているモジュール。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>説明</p></td>
<td align="left"><p>イベントの説明。</p></td>
</tr>
<tr class="even">
<td align="left"><p>受信時刻</p></td>
<td align="left"><p>サーバーでイベントが受信された日付と時刻。</p>
<div class="alert">
<strong>注</strong><br/><p>クライアントがオフラインで作業している場合、クライアントがオンラインであるときにサーバーはレポートを受け取ります。</p>
</div>
<div>

</div>
<div class="alert">
<strong>注</strong><br/><p>既定では、イベントは降順の日付で表示されます。 ただし、[受信時刻] 列をクリックして変更することができ <strong> </strong> ます。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>クライアント時間</p></td>
<td align="left"><p>クライアントのクロックに従ってイベントが発生した日付と時刻。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ホスト名</p></td>
<td align="left"><p>ホストコンピューターの名前。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ユーザー名</p></td>
<td align="left"><p>イベントを開始したユーザー。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ワークスペース名</p></td>
<td align="left"><p>MED-V ワークスペースの名前。</p></td>
</tr>
</tbody>
</table>











