---
title: '[展開] タブについて'
description: '[展開] タブについて'
author: dansimp
ms.assetid: 12891798-baa4-45a5-b845-b9505ab95633
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 147e8b1057c789d97087461a585fa3f365089784
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819964"
---
# [展開] タブについて


Application Virtualization Sequencer コンソールの [**展開**] タブを使用して、順序を変更するアプリケーションの情報を変更します。 このタブには、次の要素が含まれています。

## サーバーの URL


**サーバー URL**コントロールを使用して、仮想アプリケーションサーバーの構成設定を指定します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コントロール</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>プロトコル</strong></p></td>
<td align="left"><p>シーケンス付きのアプリケーションパッケージを仮想アプリケーションサーバーからアプリケーション仮想化デスクトップクライアントにストリーミングするプロトコルを選ぶことができます。 次のプロトコルを使用できます。</p>
<ul>
<li><p><strong>RTSP </strong> : 既定では、リアルタイムストリーミングプロトコルが仮想化対応アプリケーションの交換を制御することを指定します。</p></li>
<li><p><strong>RTSPS </strong> —トランスポートレイヤーセキュリティ付きのリアルタイムストリーミングプロトコルが、シーケンスされたアプリケーションパッケージの交換を制御することを指定します。</p></li>
<li><p><strong>[File </strong> (ファイル) (ファイル): 指定されたアプリケーションをファイル共有からストリーミングすることを指定します。</p></li>
<li><p><strong>HTTPS </strong> : セキュリティで保護されたハイパーテキストトランスポートプロトコルがパッケージの交換を制御することを指定します。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Hostname]</strong></p></td>
<td align="left"><p>ソフトウェアパッケージをアプリケーションの仮想化デスクトップクライアントにストリーミングする仮想アプリケーションサーバーのグループの前で、仮想アプリケーションサーバーまたはロードバランサーを選ぶことができます。 シーケンス処理されたアプリケーションパッケージを作成するには、この項目を完了する必要がありますが、既定の% SFT_SOFTGRIDSERVER% 環境変数は、仮想アプリケーションサーバーの実際のホスト名または IP アドレスに変更することができます。</p>
<div class="alert">
<strong>注</strong><br/><p>静的なホスト名または IP アドレスを指定しない場合は、各 Application Virtualization デスクトップクライアントで SFT_SOFTGRIDSERVER という環境変数を設定する必要があります。 この値は、クライアント&#39;s アプリケーションのソースである仮想アプリケーションサーバーまたはロードバランサーのホスト名または IP アドレスである必要があります。 この環境変数は、ユーザー変数ではなくシステム変数にする必要があります。 この変数の割り当て中にこのコンピューターで実行されている Application Virtualization デスクトップクライアントセッションは、すべて閉じる必要があります。そのため、再開されたセッションで新しいアプリケーションソースが認識されるようにする必要があります。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Port</strong></p></td>
<td align="left"><p>仮想アプリケーションサーバーまたはロードバランサーが、アプリの仮想化デスクトップクライアント&#39;s 要求をリッスンするポートを指定できるようにします。 パッケージを作成するには、この情報が必要ですが、変更することもできます。 既定のポートは554です。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>パス</strong></p></td>
<td align="left"><p>ソフトウェアパッケージが保存され、ストリーミングされる仮想アプリケーションサーバー上の相対パスを指定できます。 この情報は、SFT ファイルがコンテンツのサブディレクトリに保存されている場合に、パッケージを作成するために必要です。それ以外の場合、この情報は必要ありません。</p></td>
</tr>
</tbody>
</table>



## オペレーティングシステム


**オペレーティングシステム**のコントロールを使って、アプリケーションのオペレーティングシステム要件を指定します。 選択されたオペレーティングシステムをサポートできないアプリケーションの仮想化デスクトップクライアントの場合、アプリケーションは起動しません。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コントロール</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>利用可能なオペレーティングシステム</strong></p></td>
<td align="left"><p>パッケージ内のアプリケーションをサポートできるオペレーティングシステムの一覧が表示されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>選択されたオペレーティングシステム</strong></p></td>
<td align="left"><p>パッケージ内のアプリケーションをサポートする、選択したオペレーティングシステムの一覧が表示されます。</p></td>
</tr>
</tbody>
</table>



## 出力オプション


[**出力オプション]** コントロールを使用して、インストールするアプリケーションの出力オプションを指定します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コントロール</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>圧縮アルゴリズム</strong></p></td>
<td align="left"><p>ネットワーク経由でストリーミングするための SFT ファイルの圧縮方法を選択する場合に使用します。 次のいずれかの圧縮方法を選択します。</p>
<ul>
<li><p><strong>[圧縮済み </strong> : SFT ファイルが ZLIB 形式で圧縮されていることを指定し <a href="https://go.microsoft.com/fwlink/?LinkId=111475" data-raw-source="[ZLIB](https://go.microsoft.com/fwlink/?LinkId=111475)"> </a> ます。</p></li>
<li><p><strong>圧縮なし </strong> : 既定では、SFT ファイルが圧縮されないことを指定します。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>セキュリティ記述子を適用する</strong></p></td>
<td align="left"><p>クライアントに展開された後に、パッケージ内のアプリケーションのセキュリティ記述子を適用する場合に選択します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Microsoft Windows Installer (MSI) パッケージを生成する</strong></p></td>
<td align="left"><p>Windows Installer でシーケンス付きのアプリケーションパッケージをインストールまたは展開する場合に選択します。 Sequencer を使用して何らかの変更を加えた場合、その変更は Windows インストーラファイルには含まれません。 Windows Installer ファイルは、ハードディスクに保存されている sft ファイルを使用して、常に作成されます。</p></td>
</tr>
</tbody>
</table>



## 関連トピック


[展開のプロパティを変更する方法](how-to-change-deployment-properties.md)

[Sequencer Console](sequencer-console.md)









