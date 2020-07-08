---
title: APP-V サーバーの公開メタデータの表示
description: APP-V サーバーの公開メタデータの表示
author: dansimp
ms.assetid: d5fa9eb5-647c-478d-8a4d-0ecda018bce6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 97c59301678280febe23b8061c08033a88ae49c7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813234"
---
# APP-V サーバーの公開メタデータの表示


公開に関連する問題を解決するために役立つ公開メタデータを表示するには、次の手順を使用します。 この手順を使用するには、App-v Management server を使用している必要があります。

この記事には、次の情報が含まれています。

-   [公開メタデータを表示するための app-v 5.1 の要件](#bkmk-51-reqs-pub-meta)

-   [公開メタデータの表示に使う構文](#bkmk-syntax-view-pub-meta)

-   [クライアントのオペレーティングシステムとバージョンのクエリ値](#bkmk-values-query-pub-meta)

-   [発行メタデータの定義](#bkmk-whatis-pub-metadata)

## <a href="" id="bkmk-51-reqs-pub-meta"></a>公開メタデータを表示するための app-v 5.1 の要件


App-v 5.1 では、メタデータのために App-v パブリッシングサーバーにクエリを実行するときに、アドレスに次の値を指定する必要があります。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">値</th>
<th align="left">追加情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>ClientVersion</strong></p></td>
<td align="left"><p><strong>クエリから clientversion パラメーターを省略した場合 </strong> 、メタデータには、APP-V 5.0 SP3 で新しく追加された機能が除外されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>ClientOS</strong></p></td>
<td align="left"><p>この値を指定する必要があるのは、パッケージの順序を指定するときに特定のクライアントオペレーティングシステムを選択する場合のみです。 既定の (すべてのオペレーティングシステム) を選択した場合は、この値をクエリで指定しないでください。</p>
<p><strong>クエリから clientos パラメーターを省略した場合 </strong> 、任意のオペレーティングシステムをサポートするように指定されたパッケージのみがメタデータに表示されます。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-syntax-view-pub-meta"></a>公開メタデータを表示するためのクエリ構文


次の表は、構文とクエリの例を示しています。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v のバージョン</th>
<th align="left">クエリ構文</th>
<th align="left">パラメーターの説明</th>
<th align="left">例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 5.0 SP3 およびアプリ-V 5.1</p></td>
<td align="left"><p><code>http://&lt;PubServer&gt;:&lt;Publishing Port#&gt;/?ClientVersion=&lt;AppvClientVersion&gt;&amp;ClientOS=&lt;OSStringValue&gt;</code></p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">パラメーター</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>&lt;PubServer&gt;</p></td>
<td align="left"><p>App-v 発行サーバーの名前。</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;公開ポート#&gt;</p></td>
<td align="left"><p>発行サーバーの構成時に定義した App-v 発行サーバーへのポート。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ClientVersion = &lt; AppvClientVersion&gt;</p></td>
<td align="left"><p>App-v クライアントのバージョン。 使用する適切な値については、次の表を参照してください。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ClientOS = &lt; osstringvalue&gt;</p></td>
<td align="left"><p>App-v クライアントを実行しているコンピューターのオペレーティングシステム。 使用する適切な値については、次の表を参照してください。</p></td>
</tr>
</tbody>
</table>
<p> </p>
<p>公開サーバーの名前とポート番号 (http:// &lt; pubserver &gt; : &lt; publishing port #) を app-v クライアントから取得するには &gt; 、 <strong> APPVPUBLISHINGSERVER PowerShell コマンドレットの URL 構成を確認し </strong> ます。</p></td>
<td align="left"><p><code><a href="http://pubsvr01:2718/?clientversion=5.0.10066.0&amp;clientos=WindowsClient_6.2_x64" data-raw-source="http://pubsvr01:2718/?clientversion=5.0.10066.0&amp;amp;clientos=WindowsClient_6.2_x64">http://pubsvr01:2718/?clientversion=5.0.10066.0&amp;clientos=WindowsClient_6.2_x64</a></code></p>
<p>次に例を示します。</p>
<ul>
<li><p>"Pubsvr01" という名前の Windows Server 2012 R2 は、発行サービスをホストします。</p></li>
<li><p>Windows クライアントは Windows 8.1 64 ビットです。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>App-V 5.0 ~ app-v 5.0 SP2</p></td>
<td align="left"><p><code>http://&lt;PubServer&gt;:&lt;Publishing Port#&gt;/ </code></p>
<div class="alert">
<strong>注</strong><br/><p><strong>ClientVersion </strong> と <strong> clientos </strong> は、app-v 5.0 SP3 および app-v 5.1 でのみサポートされます。</p>
</div>
<div>

</div></td>
<td align="left"><p>App-v 5.0 SP3 および App-v 5.1 の情報を参照してください。</p></td>
<td align="left"><p><code><a href="http://pubsvr01:2718" data-raw-source="http://pubsvr01:2718">http://pubsvr01:2718</a></code></p>
<p>この例では、"pubsvr01" という名前の Windows Server 2012 R2 は、管理サービスと発行サービスをホストしています。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-values-query-pub-meta"></a>クライアントのオペレーティングシステムとバージョンのクエリ値


公開メタデータクエリで、使用しているクライアントのオペレーティングシステムとバージョンに対応する文字列値を入力します。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">アーキテクチャ</th>
<th align="left">操作文字列文字列値</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>WindowsClient_10 0_x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>32 ビット</p></td>
<td align="left"><p>WindowsClient_10 0_x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 8.1</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>WindowsClient_6 2_x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8.1</p></td>
<td align="left"><p>32 ビット</p></td>
<td align="left"><p>WindowsClient_6 2_x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 8</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>WindowsClient_6 2_x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8</p></td>
<td align="left"><p>32 ビット</p></td>
<td align="left"><p>WindowsClient_6 2_x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012 R2</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>WindowsServer_6 2_x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012 R2</p></td>
<td align="left"><p>32 ビット</p></td>
<td align="left"><p>WindowsServer_6 2_x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>WindowsServer_6 2_x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>32 ビット</p></td>
<td align="left"><p>WindowsServer_6 2_x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>WindowsClient_6 1_x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>32 ビット</p></td>
<td align="left"><p>WindowsClient_6 1_x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>WindowsServer_6 1_x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>32 ビット</p></td>
<td align="left"><p>WindowsServer_6 1_x86</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-whatis-pub-metadata"></a>発行メタデータの定義


App-v クライアントを実行しているコンピューターにパッケージが公開されると、そのコンピューターにメタデータが送信され、どのパッケージと接続グループが公開されているかが示されます。 App-v クライアントでは、次の2つの個別の要求が行われます。

-   クライアントコンピューターに付属しているパッケージと接続グループ。

-   現在のユーザーに与えられているパッケージと接続グループ。

発行サーバーは、管理サーバーと通信して、要求者が利用できるパッケージと接続グループを決定します。 メタデータを生成するには、発行サーバーが管理サーバーに登録されている必要があります。

インターネットブラウザーでは、特定のユーザーまたはコンピューターのコンテキストに含まれるクエリを使用して、各要求のメタデータを表示できます。






## 関連トピック


[App-V 5.1 テクニカル リファレンス](technical-reference-for-app-v-51.md)









