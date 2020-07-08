---
title: 制御された GPO のコマンド
description: 制御された GPO のコマンド
author: dansimp
ms.assetid: 370d3db9-4efc-4799-983d-e29ba5f32b07
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 65e9d06beb4c36762e845e452bab497a8d3da747
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821117"
---
# 制御された GPO のコマンド


[**コントロール**] タブ:

-   高度なグループポリシー管理 (AGPM) によって管理されているグループポリシーオブジェクト (Gpo) の一覧を表示します。

-   Gpo を管理するためのコマンドと、Gpo の履歴とレポートを表示するためのショートカットメニューが用意されています。

-   選択された GPO へのアクセス許可を持つグループとユーザーの一覧が表示されます。

このタブの [**グループポリシーオブジェクト**] リストを右クリックすると、ショートカットメニューが表示されます。 このメニューには、次のいずれかのオプションが適用されます。

## コントロールと履歴


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コマンド</th>
<th align="left">効果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>新しい制御された GPO</strong></p></td>
<td align="left"><p>AGPM で変更コントロールが管理される新しい GPO を作成し、ドメインの運用環境に展開します。 GPO を作成するアクセス許可が与えられていない場合は、要求を送信するように求められます。 (このオプションは、の右クリックで GPO が選択されていない場合に表示されます <strong> 。グループポリシーオブジェクト </strong> リスト)</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>履歴</strong></p></td>
<td align="left"><p>アーカイブに保存されている選択した GPO のすべてのバージョンを一覧表示するウィンドウを開きます。 履歴から、GPO 内の設定のレポートを取得したり、2つのバージョンの GPO を比較したり、GPO をテンプレートと比較したり、GPO の以前のバージョンにロールバックしたりすることができます。</p></td>
</tr>
</tbody>
</table>

 

## レポート


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コマンド</th>
<th align="left">効果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>設定</strong></p></td>
<td align="left"><p>選択された GPO 内の設定を表示する HTML ベースまたは XML ベースのレポートを生成するか、GPO が最後に制御、インポート、またはチェックインされた時点から、組織単位から選んだ GPO へのリンクを表示します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>相違点</strong></p></td>
<td align="left"><p>選択した2つの Gpo、または選んだ GPO とテンプレート内の設定を比較して、HTML ベースまたは XML ベースのレポートを作成します。</p></td>
</tr>
</tbody>
</table>

 

## 編集


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コマンド</th>
<th align="left">効果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Edit</strong></p></td>
<td align="left"><p>[ <strong> グループポリシー管理エディター </strong> ] ウィンドウを開いて、選択されている GPO を変更します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>チェックアウト</strong></p></td>
<td align="left"><p>オフライン編集のために、選択した GPO のコピーをアーカイブから取得して、他のユーザーがその GPO をアーカイブにチェックインするまで他のユーザーが編集できないようにします。 チェックアウトは、AGPM 管理者 (フルコントロール) によって無効にすることができます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>チェックイン</strong></p></td>
<td align="left"><p>選択した GPO の編集されたバージョンをアーカイブにチェックインすると、他の承認された編集者が変更を加えたり、承認者がそのドメインの運用環境に GPO を展開したりできるようになります。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>チェックアウトを取り消す</strong></p></td>
<td align="left"><p>チェックアウトされた GPO をアーカイブに戻します。変更はありません。</p></td>
</tr>
</tbody>
</table>

 

## バージョン管理


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コマンド</th>
<th align="left">効果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>生産からのインポート</strong></p></td>
<td align="left"><p>選択した GPO について、ドメインの運用環境のバージョンをアーカイブにコピーします。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>ファイルからインポートする</strong></p></td>
<td align="left"><p>選択されているチェックアウト済み GPO のポリシー設定を、GPO バックアップファイルのポリシー設定と置き換えます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Delete</strong></p></td>
<td align="left"><p>選択した GPO をごみ箱に移動し、展開されたバージョン (存在する場合) を運用環境に残しておくか、アーカイブ内のバージョンに加えて展開されたバージョンを削除するかを指定します。 GPO を削除するアクセス許可が付与されていない場合は、要求を送信するように求められます。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>展開</strong></p></td>
<td align="left"><p>アーカイブにチェックインされている選んだ GPO を、ドメインの運用環境に移動します。 このアクションにより、ネットワーク上でアクティブになり、以前にアクティブだったバージョンの GPO が存在する場合は上書きされます。 GPO を展開する権限がない場合は、要求を送信するように求められます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>エクスポート先</strong></p></td>
<td align="left"><p>選択した GPO を別のドメインにコピーできるようにバックアップファイルに保存します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Label</strong></p></td>
<td align="left"><p>選択した GPO をわかりやすいラベル ( &quot; [既知の問題] など &quot; ) と [記録の記録] のコメントにマークします。 [状態] 列にラベルが、[ <strong> </strong> <strong> </strong> 履歴] ウィンドウの [コメント] 列にコメントが表示され <strong> </strong> ます。 以前のバージョンの GPO を特定することで、問題が発生した場合にロールバックすることができます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Rename</strong></p></td>
<td align="left"><p>選択した GPO の名前を変更します。 GPO が既に展開されている場合、その名前は、GPO が再展開されたときに、ドメインの運用環境で更新されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>テンプレートとして保存</strong></p></td>
<td align="left"><p>選んだ GPO の設定に基づいて新しいテンプレートを作成します。</p></td>
</tr>
</tbody>
</table>

 

## その他


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コマンド</th>
<th align="left">効果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Refresh</strong></p></td>
<td align="left"><p>グループポリシー管理コンソール (GPMC) の表示を更新して、変更を反映します。 表示が更新されるまで、一部の変更は表示されません。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>ヘルプ</strong></p></td>
<td align="left"><p>AGPM のヘルプを表示します。</p></td>
</tr>
</tbody>
</table>

 

### その他の参照情報

-   [[内容] タブ](contents-tab-agpm40.md)

-   [編集者タスクの実行](performing-editor-tasks-agpm40.md)

-   [承認者タスクの実行](performing-approver-tasks-agpm40.md)

-   [レビュー担当者タスクの実行](performing-reviewer-tasks-agpm40.md)

 

 





