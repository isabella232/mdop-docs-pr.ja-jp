---
title: Application Virtualization Client のユーザー アクセス許可
description: Application Virtualization Client のユーザー アクセス許可
author: dansimp
ms.assetid: 7459374c-810c-45e3-b205-fdd1f8514f80
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1083faffb48aa58a0ee0c81b58fae307e53548b8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815117"
---
# Application Virtualization Client のユーザー アクセス許可


[**プロパティ**] ダイアログボックスの [**アクセス許可**] タブで、アプリケーションの仮想化クライアントの管理コンソールで [**アプリケーションの仮想化**] ノードを右クリックするとアクセスできるため、管理者はさまざまなクライアント機能を使用するためのアクセス許可をユーザーに与えることができます。

**注** ユーザーの権限を変更する前に、権限の変更が、ユーザー権限を付与するための組織のガイドラインと一致していることを確認してください。

 

次の表では、ユーザーに付与できる権限について説明します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">権限名</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>アプリケーションの追加</p></td>
<td align="left"><p>新しいアプリケーションを登録するには、sfttray.exe、sftmime.exe または MMC を使用して、新しい OSD ファイルをクライアントに渡します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ファイルシステムのキャッシュサイズを変更する</p></td>
<td align="left"><p>ファイルシステムキャッシュのサイズを大きくします。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ファイルシステムドライブを変更する</p></td>
<td align="left"><p>ファイルシステムの別の優先ドライブ文字を選択します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ログ設定を変更する</p></td>
<td align="left"><p>クライアントログファイルのログレベルまたはログパスを変更します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>OSD ファイルの変更</p></td>
<td align="left"><p>登録されているアプリケーションの OSD ファイルを変更してクライアントに渡します。 これは、公開の更新には影響しません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>アプリケーション設定をクリアする</p></td>
<td align="left"><p>ファイルの種類、ショートカット、現在のユーザーの構成を削除します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>アプリケーションを削除する</p></td>
<td align="left"><p>コンピューター上のすべてのユーザーに対して、ファイルシステムと OSD キャッシュからアプリケーションへのすべての参照を削除します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>キャッシュにアプリケーションをインポートする</p></td>
<td align="left"><p>指定した SFT ファイルからファイルシステムキャッシュにアプリケーションデータを直接読み込みます。 これはすべてのユーザーに影響します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>キャッシュにアプリケーションを読み込む</p></td>
<td align="left"><p>アプリの SFT ファイルの読み込みを、構成されているソースから開始します。たとえば、App-v Streaming Server などです。 これにより、コンピューター上のすべてのユーザーのアプリケーションが読み込まれます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>キャッシュ内のアプリケーションのロックとロック解除</p></td>
<td align="left"><p>ファイルシステムキャッシュからアプリケーションがアンロードされないようにします。 これは、コンピューター上のすべてのユーザーに影響します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ファイルの種類の関連付けを管理する</p></td>
<td align="left"><p>ファイルの種類の関連付けは、現在のユーザーに対してのみ追加、変更、または削除します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>公開の更新設定を管理する</p></td>
<td align="left"><p>コンピューター上のすべてのユーザーに対して公開の更新のタイミングを制御する設定を変更します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>公開サーバーを管理する</p></td>
<td align="left"><p>コンピューター上のすべてのユーザーの発行サーバーを追加、変更、または削除します。 このアクセス許可には、公開の更新設定を管理するアクセス許可が暗黙的に含まれます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>公開ショートカット</p></td>
<td align="left"><p>登録されているアプリケーションへの新しいショートカットを作成します。 ユーザーは、ローカルファイルシステムでファイルを作成する権限も持っている必要があります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>アプリケーションを修復する</p></td>
<td align="left"><p>ショートカットやファイルの種類の関連付けを削除せずに、現在のユーザーのアプリケーション固有の構成を削除します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>公開の更新を開始する</p></td>
<td align="left"><p>現在のユーザーのスケジュールされていない公開の更新を開始します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>オフラインモードの切り替え</p></td>
<td align="left"><p>すべてのユーザーについて、クライアント全体をオンラインからオフラインモードに変更します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>キャッシュからアプリケーションをアンロードする</p></td>
<td align="left"><p>ユーザー固有の設定、ショートカット、またはファイルの種類の関連付けを削除することなく、すべてのユーザーに対してファイルシステムキャッシュからアプリケーションデータを消去します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>すべてのアプリケーションを表示する</p></td>
<td align="left"><p>コンピューターに登録されているすべてのユーザーの仮想アプリケーションをユーザーに表示することを許可します。</p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[ユーザーのアクセス許可を変更する方法](how-to-change-user-access-permissions.md)

 

 





