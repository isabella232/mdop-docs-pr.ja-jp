---
title: App-V 5.0 の新機能
description: App-V 5.0 の新機能
author: dansimp
ms.assetid: 79ff6e02-e926-4803-87d8-248a6b28099d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dabe264f033bd5c9897f07d931f799a42e6b72e9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813219"
---
# App-V 5.0 の新機能


このセクションは、既に App-v に精通していて、アプリ5.0 で何が変更されたかを確認する必要があるユーザーを対象としています。既に App-v に慣れていない場合は、まず「 [app-v 5.0 の計画](planning-for-app-v-50-rc.md)」を参照してください。

## 標準機能の変更点


以下のセクションでは、App-v 5.0 の標準機能の変更点について説明します。

### サポートされているオペレーティングシステムの変更

詳細については、「 [app-v 5.0 でサポートされている構成](app-v-50-supported-configurations.md)」を参照してください。

## Sequencer の変更点


以下のセクションでは、App-v 5.0 sequencer での変更に関する情報について説明します。

### Sequencer に対する特定の変更

次の表には、App-v 5.0 sequencer で変更された内容に関する情報が表示されています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Sequencer 機能</th>
<th align="left">App-v 5.0 Sequencer の機能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>再起動処理</p></td>
<td align="left"><p>アプリケーションで再起動を求めるメッセージが表示されたら、アプリが sequencer を実行しているコンピューターを再起動することを許可する必要があります。 Sequencer を実行しているコンピューターが再起動し、監視モードで sequencer が再開されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>仮想アプリケーションディレクトリの指定</p></td>
<td align="left"><p>仮想アプリケーションディレクトリは必須のパラメーターです。 最善の結果を得るには、アプリケーションインストーラーのインストールディレクトリと一致している必要があります。 これにより、パフォーマンスとアプリケーションの互換性が最適化されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>編集ショートカット/FTAs</p></td>
<td align="left"><p>[ショートカット/FTA] ページは <strong> 、 </strong> シーケンスウィザードが完了した後の [詳細編集] ページにあります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>[変更履歴] タブ</p></td>
<td align="left"><p>App-V 5.0 の [変更履歴] タブが削除されました。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>[OSD] タブ</p></td>
<td align="left"><p>[OSD] タブは、App-v 5.0 用に削除されました。</p></td>
</tr>
<tr class="even">
<td align="left"><p>[仮想サービス] タブ</p></td>
<td align="left"><p>App-V 5.0 の [仮想サービス] タブが削除されました。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>[ファイル]/[仮想ファイルシステム] タブ</p></td>
<td align="left"><p>これらのタブは、パッケージファイルを変更できるようになっています。</p></td>
</tr>
<tr class="even">
<td align="left"><p>[展開] タブ</p></td>
<td align="left"><p>パッケージでサーバーの URL を構成するためのオプションはありません。 これは、展開構成、または管理サーバーを使用して構成する必要があります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>パッケージコンバーターツール</p></td>
<td align="left"><p>PowerShell を使用して、以前のバージョンで作成されたパッケージを変換できるようになりました。</p></td>
</tr>
<tr class="even">
<td align="left"><p>アドオン/ミドルウェア</p></td>
<td align="left"><p>アドオンまたはミドルウェアアプリケーションの順序を付けている場合は、親パッケージを展開できます。 アドオンとミドルウェアパッケージは、App-v 5.0 の接続グループを使用して接続されている必要があります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ファイルの出力</p></td>
<td align="left"><p>次のファイルは、App-v 5.0、Windows Installer (.msi)、appv、展開構成、ユーザー構成、Report.XML を使って作成されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>圧縮/セキュリティ記述子/MSI パッケージ</p></td>
<td align="left"><p>Windows Installer (.msi) ファイルの圧縮と作成は、すべてのパッケージで自動的に行われるため、今後セキュリティ記述子を上書きすることはできません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ツール/オプション</p></td>
<td align="left"><p>診断ウィンドウも削除されました。その他の設定もいくつかあります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>インストールドライブ</p></td>
<td align="left"><p>アプリケーションをインストールするときに、インストールドライブは不要になりました。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>OOS ストリーミング</p></td>
<td align="left"><p>ストリームの最適化が実行されていない場合、アプリが起動されるまで、アプリが app-v 5.0 クライアントを実行しているコンピューターから要求された場合、パッケージはストリームの途中で処理されません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Q: &lt; /p&gt;</td>
<td align="left"><p>App-v 5.0 はネイティブファイルシステムを使用し、Q:. は不要になります。</p></td>
</tr>
</tbody>
</table>

 

## シーケンスエラーの検出


アプリ-V 5.0 sequencer は、シーケンス中に一般的なシーケンスの問題を検出できます。 シーケンスウィザードの最後にある [**インストールレポート**] ページには、問題の重大度に応じて、**エラー**、**警告**、および**情報**に分類された診断メッセージが表示されます。

イベントに関する詳細情報を表示するには、レポートでレビューするアイテムをダブルクリックします。 シーケンスの問題と、問題の解決方法に関する提案が表示されます。 パッケージの作成が完了すると、システム準備レポートとインストールレポートの情報が集計されます。 次のリストは、レポートで利用可能な問題の種類を示しています。

-   除外されたファイル。

-   ドライバー情報。

-   COM + システムの相違点。

-   Side-by-side (SxS) の競合。

-   シェルの拡張機能。

-   サポートされていないサービスに関する情報。

-   分散.

## 接続グループ


以前は**動的 Suite コンポジション**と呼ばれていた app-v 機能が、app-v 5.0 で**接続グループ**として参照されるようになりました。 接続グループの使用の詳細については、「[接続グループを管理する](managing-connection-groups.md)」を参照してください。

## ライセンスとメータリングの機能


アプリケーションとライセンス機能は、App-v 5.0 では削除されています。 環境内の実際のライセンスの位置は、関連付けられているライセンス条項によって付与される特定のソフトウェアタイトルライセンスおよび使用権によって異なります。

## ファイルとアプリケーションのキャッシュ


App-v 5.0 では、ファイルまたはアプリケーションのキャッシュは利用できません。






## 関連トピック


[App-V 5.0 について](about-app-v-50.md)

 

 





