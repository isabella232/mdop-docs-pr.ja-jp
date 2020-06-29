---
title: 公開方法の選択
description: 公開方法の選択
author: dansimp
ms.assetid: 1f2d0d39-5d65-457a-b826-4f45b00c8c85
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9a6b19b12c28ab67e3250909cb32ddb8419f399a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821677"
---
# 公開方法の選択


Application Virtualization Sequencer を使用してアプリケーションをシーケンスした後は、そのアプリケーションをユーザーに*公開*する必要があります。 アプリケーションの公開は、アイコン、パッケージ定義情報、およびアプリケーションの仮想化クライアントがインストールされている各コンピューターへのコンテンツソースの場所の配信で構成されます。 次の表では、電子ソフトウェア配布 (ESD) システムを使用してアプリケーションの仮想化を展開するときにサポートされる発行方法について説明します。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">メソッド</th>
<th align="left">長所</th>
<th align="left">短所</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>シーケンス中に Windows インストーラーファイルを生成し、スタンドアロンソリューションとして作成します。</p></td>
<td align="left"><ul>
<li><p>簡単に使うことができます。</p></li>
<li><p>パッケージは各コンピューター上のキャッシュにローカルに読み込まれます。</p></li>
<li><p>ユーザーに表示されるアイコン。</p></li>
<li><p>従来のソフトウェア展開と似ています。</p></li>
<li><p>ストリーミングサーバは不要。</p></li>
</ul></td>
<td align="left"><ul>
<li><p>コンピューター上のパッケージコンテンツの場所を柔軟に指定することはできません。すべてのコンピューター上の同じ場所にあります。</p></li>
<li><p>アプリケーションを削除するには、[プログラムの追加と削除] を使用する必要があります。</p></li>
<li><p>パッケージの更新に必要な新しいバージョンの削除と置き換え。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>シーケンス中に、MODE、LOAD、OVERRIDEURL コマンドラインプロパティとパッケージマニフェストと共に使用される Windows インストーラーファイルを生成します。</p></td>
<td align="left"><ul>
<li><p>使いやすく、柔軟性が向上しました。</p></li>
<li><p>ユーザーに表示されるアイコン。</p></li>
<li><p>アプリケーションを含む SFT ファイルをストリーミングソースの場所に配置し、クライアントがその場所を使用するように構成することができます。</p></li>
</ul></td>
<td align="left"><ul>
<li><p>限定された柔軟性: パッケージコンテンツの場所のみを実行時に制御できます。</p></li>
<li><p>アプリケーションを削除するには、[プログラムの追加と削除] を使用する必要があります。</p></li>
<li><p>ストリーミングサーバーを使用しない限り、パッケージの更新に必要な新しいバージョンの削除と置き換え。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>SFTMIME コマンドを実行します。</p></td>
<td align="left"><ul>
<li><p>完全な柔軟性—すべてのパッケージ管理機能を完全に制御できます。</p></li>
</ul></td>
<td align="left"><ul>
<li><p>ESD システムで使用するためにコマンドをスクリプト化する必要があります。</p></li>
<li><p>コマンドは、各コンピューターで正しい順序で実行されている必要があります。</p></li>
<li><p>コマンド言語と慎重な計画について詳しく理解している。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

これらの発行方法の使い方については、「[クライアントで仮想アプリケーションを公開する方法](how-to-publish-a-virtual-application-on-the-client.md)」を参照してください。

## 関連トピック


[ストリーミング方法の選択](determine-your-streaming-method.md)

[電子ソフトウェア配布ベースのシナリオ](electronic-software-distribution-based-scenario.md)

[電子ソフトウェア配布ベースのシナリオ概要](electronic-software-distribution-based-scenario-overview.md)

[クライアントで仮想アプリケーションを公開する方法](how-to-publish-a-virtual-application-on-the-client.md)

[SFTMIME コマンドリファレンス](sftmime--command-reference.md)

 

 





