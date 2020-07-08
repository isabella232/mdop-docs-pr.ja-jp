---
title: App-V 5.0 について
description: App-V 5.0 について
author: dansimp
ms.assetid: 5799141b-44bc-4033-afcc-212235e15f00
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 24d41bbe3a8f5f0af299490a025a57f4edbf8207
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814967"
---
# App-V 5.0 について


App-v 5.0 は、強化された統合プラットフォーム、より柔軟な仮想化、仮想化されたアプリケーションのための強力な管理機能を提供します。 詳細については、「 [app-v 5.0 の概要](https://go.microsoft.com/fwlink/?LinkId=325265)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=325265) 。

## <a href="" id="what-s-new-"></a>新機能


次の一覧は、App-v 5.0 の新機能を示しています。

-   **IT 診断と監視**-app-v 5.0 は、app-v 5.0 クライアントと仮想化されたパッケージを実行しているコンピューターに関するレポート情報を生成する機能を強化します。

-   **エンドツーエンドのプログラミング**-PowerShell 3.0 の活用-app-v 5.0 は、パッケージ化、クライアント操作、サーバー操作のための完全なプログラミングソリューションを提供します。

-   **シンプルかつ効果的なクライアント本体**-app-v 5.0 には、上位のエンドユーザーと Tier 1 のサポートエンジニアシナリオを簡略化するために設計された最新のクライアント本体が用意されています。

-   **仮想アプリケーション拡張機能**-app-v 5.0 の仮想アプリケーション拡張機能により、仮想パッケージをローカルにインストールされているかのように実行できます。

-   **ローカルドライブの作成**-アプリ-V 5.0 では、仮想アプリケーションの展開用に専用のローカルドライブ文字が必要なくなりました。

-   **共有コンテンツストア**– app-v 5.0 共有コンテンツストアは、以前のバージョンの app-v で利用可能なストリーミングサーバーと同様の機能を提供します。 また、新しいバージョンの準備ができ次第、ディスク容量が少なくなり、仮想アプリケーションの更新が利用できるようになります。

-   **接続グループ**-app-v 5.0 接続グループを使うと、仮想アプリケーションを対話形式で接続して実行できます。

## <a href="" id="bkmk-diff-46-50"></a>App-v 4.6 と app-v 5.0 の違い


次の表は、App-v 4.6 と App-v 5.0 の違いを示しています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v 4.6</th>
<th align="left">App-v 5.0</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>専用のドライブ文字 ( <strong> Q:/強) を使用する必要があり &lt; &gt; ます。</p></td>
<td align="left"><p>専用のドライブ文字は必要ありません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>4 GB のパッケージサイズの制限要件。</p></td>
<td align="left"><p>4 GB のパッケージサイズの制限要件はありません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>仮想アプリケーションは、ローカルにインストールされたアプリケーションから分離されます。</p></td>
<td align="left"><p>仮想アプリケーションは、ローカルアプリケーションの操作をサポートするために拡張できます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>動的なスイートコンポジションによるミドルウェアアプリケーションとの相互作用。</p></td>
<td align="left"><p>ピアアプリケーションは、接続グループを使って共有されます。 接続グループの詳細については、「接続グループを管理する」を参照してください <a href="managing-connection-groups.md" data-raw-source="[Managing Connection Groups](managing-connection-groups.md)"> </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>VDI/RDS 環境では、読み取り専用の共有キャッシュが必要です。</p></td>
<td align="left"><p><strong> </strong> 標準ワークフローを使用して、共有コンテンツストアを更新することができます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>制限付きのコマンドラインスクリプト。</p></td>
<td align="left"><p>Sequencer、クライアント、サーバーコンポーネントのための強力な PowerShell スクリプトをサポートしています。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p>Web ベースの管理機能を提供します。</p></td>
</tr>
</tbody>
</table>

 

## MDOP 技術の入手方法


App-v 5.0 は、Microsoft デスクトップ最適化パック (MDOP) に含まれています。 MDOP は、Microsoft ソフトウェアアシュアランスの一部です。 Microsoft ソフトウェアアシュアランスの詳細と MDOP の入手方法については、「 [mdop の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」を参照してください https://go.microsoft.com/fwlink/?LinkId=322049) 。






## 関連トピック


[App-V 5.0 をお使いになる前に](getting-started-with-app-v-50--rtm.md)

 

 





