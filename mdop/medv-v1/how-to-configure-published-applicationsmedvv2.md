---
title: 公開されたアプリケーションを構成する方法
description: 公開されたアプリケーションを構成する方法
author: dansimp
ms.assetid: 43a59ff7-5d4e-49dc-84e5-1082bc4dd8f4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cb5736382f03e818ef10aa814a8e61044ca2b73a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824314"
---
# 公開されたアプリケーションを構成する方法


ホストオペレーティングシステムと互換性のないアプリケーションは、MED-V ワークスペース内で実行し、デスクトップから開始する場合と同じ方法で、[スタート] メニューまたはローカルのホストショートカットから開始する方法と同じ方法で、med-v ワークスペース内で実行できます。 選択して定義されたアプリケーションは、"公開アプリケーション" と呼ばれます。 このセクションの手順では、公開されたアプリケーションを追加および削除する方法について説明します。

アプリケーションは、次のいずれかの方法で公開できます。

-   アプリケーションとして: アプリケーションのコマンドラインに入力して、特定のアプリケーションを選択します。 選択されたアプリケーションのみが公開されます。

-   メニューとして: 複数のアプリケーションが含まれているフォルダーを選択します。 フォルダー内のすべてのアプリケーションが公開され、メニューとして表示されます。

## <a href="" id="bkmk-addingapublishedapplication"></a>公開されたアプリケーションを MED-V ワークスペースに追加する方法


**MED-V ワークスペースにアプリケーションを追加するには**

1.  構成する MED-V ワークスペースをクリックします。

2.  [**アプリケーション**] ウィンドウの [公開された**アプリケーション**] セクションで、[**追加**] をクリックして新しいアプリケーションを追加します。

3.  次の表で説明するように、アプリケーションのプロパティを構成します。

4.  [**ポリシー** ] メニューで、[**コミット**] を選びます。

    **注**  
    Web リダイレクションが適切に動作するように Internet Explorer を公開アプリケーションとして設定している場合は、パラメーターがかっこ内にないことを確認してください。



**公開されたアプリケーションのプロパティ**

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
<td align="left"><p>有効</p></td>
<td align="left"><p>公開されているアプリケーションを有効にするには、このチェックボックスをオンにします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>表示名</p></td>
<td align="left"><p>ユーザー&#39;s Windows の [スタート] メニューのショートカットの名前。</p>
<div class="alert">
<strong>注</strong><br/><p>表示名には <strong> 、 </strong> 大文字と小文字は区別されません。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>説明</p></td>
<td align="left"><p>公開されたアプリケーションの説明。ユーザー&#39;s マウスをショートカットの上に置いたときにヒントとして表示されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>コマンド ライン</p></td>
<td align="left"><p>MED-V ワークスペース内からアプリケーションを実行するために使用されるコマンド。 完全なパスが必要であり、他の Windows コマンドと同様の方法でパラメーターをアプリケーションに渡すことができます。</p>
<p>Revertible MED ワークスペースでは、mapnetworkdrive のパスを使ったネットワークドライブ &quot; <em> &lt; &gt; &lt; &gt; </em> &quot; ( &quot; <em> mapnetworkdrive t: \ tux\ date など) </em> &quot; をマップできます。</p>
<p>たとえば、Windows エクスプローラーを公開するには、次の構文を使用します。 &quot; <em> c: &lt; /em &gt; &quot; または &quot; <em> c:\windows </em> 。&quot;</p>
<div class="alert">
<strong>注</strong><br/><p>名前解決を行うには、次のいずれかを実行する必要があります。</p>
</div>
<div>

</div>
<ul>
<li><p>ベースの MED-V ワークスペースイメージで DNS を構成します。</p></li>
<li><p>DNS 解決がホストで定義されていることを確認し、ホスト DNS を使用するように構成します。</p></li>
<li><p>ネットワークドライブの定義には IP を使用します。</p></li>
</ul>
<div class="alert">
<strong>注</strong><br/><p>パスにスペースが含まれている場合は、パス全体を引用符で囲む必要があります。</p>
</div>
<div>

</div>
<div class="alert">
<strong>注</strong><br/><p>パスの末尾にはバックスラッシュ () を使用しないでください。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>スタート メニュー</p></td>
<td align="left"><p>このチェックボックスをオンにすると、ユーザー&#39;s Windows の [スタート] メニューにアプリケーションのショートカットが作成されます。</p></td>
</tr>
</tbody>
</table>



公開されているすべてのアプリケーションは、Windows の [**スタート**] メニューにショートカットとして表示されます ([**すべてのプログラム] &gt; &gt; med-v アプリケーションを起動**します)。

## MED-V ワークスペースから公開されたアプリケーションを削除する方法


**MED-V ワークスペースからアプリケーションを削除するには**

1.  MED-V ワークスペースをクリックします。

2.  [**アプリケーション**] ウィンドウの [公開された**アプリケーション**] セクションで、削除するアプリケーションを選択します。

3.  [**削除**] をクリックします。

    アプリケーションが公開されたアプリケーションのリストから削除されます。

4.  [**ポリシー** ] メニューで、[**コミット**] を選びます。

## 公開したメニューを MED-V ワークスペースに追加する方法


**公開したメニューを MED-V ワークスペースに追加するには**

1.  構成する MED-V ワークスペースをクリックします。

2.  [**アプリケーション**] ウィンドウの [**発行済みメニュー** ] セクションで、[**追加**] をクリックして新しいメニューを追加します。

3.  次の表で説明するように、メニューのプロパティを構成します。

4.  [**ポリシー** ] メニューで、[**コミット**] を選びます。

**発行済みメニューのプロパティ**

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
<td align="left"><p>有効</p></td>
<td align="left"><p>このチェックボックスをオンにすると、公開されたメニューが有効になります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>表示名</p></td>
<td align="left"><p>ユーザー&#39;s Windows の [スタート] メニューのショートカットの名前。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>説明</p></td>
<td align="left"><p>ユーザー&#39;s マウスをショートカットの上に置いたときのヒントとして表示される説明。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ワークスペース内のフォルダー</p></td>
<td align="left"><p>フォルダー内のすべてのアプリケーションを含むメニューとして公開するフォルダーを選択します。</p>
<p>表示されるテキストは、[プログラム] フォルダーからの相対パスです。</p>
<div class="alert">
<strong>注</strong><br/><p>空白のままにすると、ホスト上のすべてのプログラムがメニューとして発行されます。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



公開されているすべてのメニューは、Windows の [**スタート**] メニュー ([すべてのプログラム]、[** &gt; すべて &gt; のプログラム**]) にショートカットとして表示されます。 ショートカットの名前を変更するには、[**スタート] メニューのショートカットフォルダ**フィールドを設定します。

**注**  
2つの MED-V ワークスペースを構成するときは、[スタート] メニューのショートカットフォルダーに対して別の名前を構成することをお勧めします。



## MED-V ワークスペースから公開されたメニューを削除する方法


**MED-V ワークスペースから公開されたメニューを削除するには**

1.  MED-V ワークスペースをクリックします。

2.  [**アプリケーション**] ウィンドウの [**発行済みメニュー** ] セクションで、削除するメニューを選択します。

3.  [**削除**] をクリックします。

    メニューが公開されたメニューの一覧から削除されます。

4.  [**ポリシー** ] メニューで、[**コミット**] を選びます。

## クライアントのコマンドラインから公開されたアプリケーションを実行する


管理者は、次のコマンドを使用して、デスクトップショートカットなど、任意の場所から公開されたアプリケーションを実行できます。

``` syntax
"<Install path>\Manager\KidaroCommands.exe" /run "<published application name>" "<MED-V workspace name>"
```

**注**  
公開したアプリケーションが定義されている MED-V ワークスペースが実行されている必要があります。



## 関連トピック


[高度な設定で公開されたアプリケーションを編集する方法](how-to-edit-a-published-application-with-advanced-settings.md)

[MED-V 管理コンソールのユーザー インターフェイスの使用](using-the-med-v-management-console-user-interface.md)

[MED-V ワークスペースの作成](creating-a-med-v-workspacemedv-10-sp1.md)









