---
title: App-V でフォルダー リダイレクトを使用するための計画
description: App-V でフォルダー リダイレクトを使用するための計画
author: dansimp
ms.assetid: 6bea9a8f-a915-4d7d-be67-ef1cca1398ed
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 507aef186579da0efdb3af7b6e1088a5e725ad70
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813386"
---
# App-V でフォルダー リダイレクトを使用するための計画


Microsoft Application Virtualization (App-v) 5.1 では、フォルダーリダイレクションの使用がサポートされています。この機能を使うと、ユーザーと管理者はフォルダーのパスを新しい場所にリダイレクトすることができます。

ここでは、以下のトピックについて説明します。

-   [フォルダーリダイレクションを使用するための要件](#bkmk-folder-redir-reqs)

-   [App-v で使用するためにフォルダーのリダイレクトを構成する方法](#bkmk-folder-redir-cfg)

-   [フォルダーリダイレクションと app-v の連携](#bkmk-folder-redir-works)

-   [フォルダーリダイレクションの概要](#bkmk-folder-redir-overview)

## <a href="" id="bkmk-folder-redir-reqs"></a>フォルダーリダイレクションを使用するための要件とサポートされていないシナリオ


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>要件</p></td>
<td align="left"><p>% AppData% フォルダーのリダイレクションを使用するには、次のことを行う必要があります。</p>
<ul>
<li><p>AppData 仮想ファイルシステム (VFS) フォルダーを持つ App-v パッケージがあること。</p></li>
<li><p>フォルダーのリダイレクトを有効にし、ユーザーのフォルダーを共有フォルダー (通常はネットワークフォルダー) にリダイレクトします。</p></li>
<li><p>次の両方のどちらか一方または両方をローミングします。</p>
<ul>
<li><p>%Appdata%\Microsoft\AppV\Client\Catalog のファイル</p></li>
<li><p>HKEY_CURRENT_USER \Software\Microsoft\AppV\Client\Packages の [レジストリ設定]</p>
<p>詳しくは、「 <a href="application-publishing-and-client-interaction.md#bkmk-clt-inter-roam-reqs" data-raw-source="[Application Publishing and Client Interaction](application-publishing-and-client-interaction.md#bkmk-clt-inter-roam-reqs)"> アプリケーションの発行とクライアントの操作」をご覧ください </a> 。</p></li>
</ul></li>
<li><p>App-v 5.0 SP2 以降のクライアントを実行しているコンピューターにログインしている各ユーザーが、次のフォルダーを使用できるようにします。</p>
<ul>
<li><p>% AppData% は、目的のネットワークの場所 (オフラインファイルのサポートありまたはなし) に構成されてい <a href="https://technet.microsoft.com/library/cc780552.aspx" data-raw-source="[Offline Files](https://technet.microsoft.com/library/cc780552.aspx)"> </a> ます。</p></li>
<li><p>% LocalAppData% は目的のローカルフォルダに設定されています。</p></li>
</ul></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>サポートされていないシナリオ</p></td>
<td align="left"><ul>
<li><p>% LocalAppData% をネットワークドライブとして構成しています。</p></li>
<li><p>複数ユーザーの場合は、[スタート] メニューを1つのフォルダーにリダイレクトします。</p></li>
<li><p>ローミングの場合 (% AppData%)は、使用できないネットワーク共有にリダイレクトされます。この場合、App-v アプリケーションは次のように起動できなくなります。</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v のバージョン</th>
<th align="left">シナリオの説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 5.0 ~ app-v 5.0 SP2 plus ホットフィックス</p></td>
<td align="left"><p>このエラーは、オフラインファイルが有効になっているかどうかに関係なく発生します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 5.0 SP3 以降</p></td>
<td align="left"><p>オフラインファイルで利用できないネットワーク共有が有効になっている場合は、App-v アプリケーションが正常に起動します。</p></td>
</tr>
</tbody>
</table>
<p> </p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-folder-redir-cfg"></a>App-v で使用するためにフォルダーのリダイレクトを構成する方法


フォルダーのリダイレクトは、デスクトップ、マイドキュメント、写真など、さまざまなフォルダーに適用できます。ただし、App-v アプリケーションの使用に影響を与える唯一のフォルダーは、ユーザーのローミング AppData フォルダー (% AppData%) です。 他のサポートされているフォルダーには、App-v に影響を与えることなく、フォルダーリダイレクションを適用できます。

## <a href="" id="bkmk-folder-redir-works"></a>フォルダーリダイレクションと app-v の連携


次の表では、% AppData% がネットワークにリダイレクトされ、この記事の前半で説明した要件を満たしている場合の、フォルダーのリダイレクトの動作について説明します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">仮想環境の状態</th>
<th align="left">実行されるアクション</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>仮想環境の開始時</p></td>
<td align="left"><p>仮想ファイルシステム (VFS) AppData フォルダーはローカルの AppData フォルダにマッピングされています (% LocalAppData%)ユーザーのローミング用の AppData フォルダ (% AppData%) の代わりに</p>
<ul>
<li><p>LocalAppData には、使用中のパッケージのユーザーのローミングの AppData フォルダーのローカルキャッシュが含まれています。 ローカルキャッシュは次の場所にあります。</p>
<p><code>%LocalAppData%\Microsoft\AppV\Client\VFS\PackageGUID\AppData</code></p></li>
<li><p>ユーザーのローミングの AppData フォルダーからの最新データは、ローカルキャッシュ内の現在のデータにコピーされ、置き換えられます。</p></li>
<li><p>仮想環境が実行されている間、データはローカルキャッシュに保存されたままになります。 データは、% LocalAppData% からのみ配信され、エンドユーザーがコンピューターをシャットダウンするまで、% AppData% との間で移動または同期されません。</p></li>
<li><p>AppData フォルダーへのエントリは、システムコンテキストではなく、ユーザーコンテキストを使用して作成されます。</p></li>
</ul>
<div class="alert">
<strong>注</strong><br/><p>App-v クライアントフォルダーリダイレクションは、% AppData% から% LocalAppData% にファイルを移動することができない場合があります。 「 <a href="release-notes-for-app-v-50-sp2.md#bkmk-folderredirection" data-raw-source="[Release Notes for App-V 5.0 SP2](release-notes-for-app-v-50-sp2.md#bkmk-folderredirection)"> App-v 5.0 SP2 のリリースノート」を参照してください </a> 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>仮想環境のシャットダウン時</p></td>
<td align="left"><p>AppData (ローミング) 内のローカルにキャッシュされたデータは、% AppData% の "本物" ローミング AppData フォルダーに圧縮され、コピーされます。 最後の既知のアップロードを示すタイムスタンプは、次のレジストリキーとして同時に保存されます。</p>
<p><code>HKCU\Software\Microsoft\AppV\Client\Packages&amp;lt;PACKAGE_GUID&gt;\AppDataTime</code></p>
<p>冗長性を提供するために、App-v は、圧縮されたデータの3つの最新のコピーを% AppData% で保持します。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-folder-redir-overview"></a>フォルダーリダイレクションの概要


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>目的</p></td>
<td align="left"><p>エンドユーザーが別のフォルダーにリダイレクトされたファイルを、ローカルドライブでまだ存在しているかのように、そのファイルを操作できるようにします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>説明</p></td>
<td align="left"><p>フォルダーリダイレクションを使用すると、ユーザーと管理者はフォルダーのパスをネットワーク上の場所にリダイレクトできます。 フォルダー内のドキュメントは、ネットワーク上のどのコンピューターからでもユーザーが利用できます。</p>
<ul>
<li><p>フォルダーリダイレクションを使用すると、ユーザーと管理者はフォルダーのパスをネットワーク上の場所にリダイレクトできます。 フォルダー内のドキュメントは、ネットワーク上のどのコンピューターからでもユーザーが利用できます。</p></li>
<li><p>新しい場所には、ローカルコンピューター上のフォルダーまたは共有ネットワーク上のフォルダーを指定できます。</p></li>
<li><p>フォルダーリダイレクションによってファイルがすぐに更新されますが、通常、ユーザーがログインまたはログオフすると、ローミングデータが同期されます。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>使用例</p></td>
<td align="left"><p>[ドキュメント] フォルダー (通常はコンピューター&#39;s ローカルハードディスクに保存されている) をネットワーク上の場所にリダイレクトすることができます。 ユーザーは、ネットワーク上の任意のコンピューターからフォルダー内のドキュメントにアクセスできます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>その他のリソース</p></td>
<td align="left"><p><a href="https://technet.microsoft.com/library/cc778976.aspx" data-raw-source="[Folder redirection overview](https://technet.microsoft.com/library/cc778976.aspx)">フォルダリダイレクションの概要</a></p></td>
</tr>
</tbody>
</table>
















