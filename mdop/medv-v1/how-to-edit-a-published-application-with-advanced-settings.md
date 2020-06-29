---
title: 高度な設定で公開されたアプリケーションを編集する方法
description: 高度な設定で公開されたアプリケーションを編集する方法
author: dansimp
ms.assetid: 06a79049-9ce9-490f-aad7-fd4fdf185590
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 843aebb38f54959f209e742b398e3979acac3334
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826997"
---
# 高度な設定で公開されたアプリケーションを編集する方法


公開されたアプリケーションを追加して構成した後、公開されたアプリケーションを編集したり、その他の詳細設定を構成したりできます。

**[詳細設定] で公開されているアプリケーションを編集するには**

1.  [**アプリケーション**] ウィンドウで、公開されたアプリケーションを追加して構成します。

2.  編集する公開済みアプリケーションを選択します。

3.  **[編集]** をクリックします。

4.  [公開された**アプリケーション**] ダイアログボックスで、次の表に示すようにパラメーターを構成します。

5.  **[OK]** をクリックします。

6.  [**ポリシー** ] メニューで、[**コミット**] を選びます。

**公開されたアプリケーションのプロパティを編集する**

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
<td align="left"><p>表示名</p></td>
<td align="left"><p>ユーザー&#39;s Windows の [スタート] メニューのショートカットの名前。</p>
<div class="alert">
<strong>注</strong><br/><p>表示名には <strong> 、 </strong> 大文字と小文字は区別されません。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>説明</p></td>
<td align="left"><p>公開されたメニューの説明。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>開始日</p></td>
<td align="left"><p>アプリケーションを起動するディレクトリ。</p>
<div class="alert">
<strong>注</strong><br/><p>パスに引用符を含める必要はありません。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>コマンド ライン</p></td>
<td align="left"><p>MED-V ワークスペース内からアプリケーションを実行するためのコマンド。</p>
<p>完全なパスが必要であり、他の Windows コマンドと同様の方法でパラメーターをアプリケーションに渡すことができます。</p>
<p>ドメイン構成では、通常、すべてのドメインコンピューターが対応しているサーバー上に共有ドライブが存在します。 ここでディレクトリをマップする必要があります。また、ユーザー認証が必要なフォルダーの場合は、[ <strong> このアプリケーションを実行するために med-v の資格情報を使用する </strong> ] チェックボックスをオンにする必要があります。</p>
<p>Revertible MED ワークスペースでは、mapnetworkdrive のパスを使用したネットワークドライブ &quot; <em> &lt; &gt; &lt; &gt; </em> &quot; ( &quot; <em> mapnetworkdrive t: \tux\data など) </em> &quot; をマップできます。</p>
<p>たとえば、Windows エクスプローラーを公開するには、次の構文を使用します。 &quot; <em> c: &amp; quot; または &quot; c:\windows </em> &quot; 。</p>
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
<td align="left"><p>ホストの Windows の [スタート] メニューにショートカットを追加する</p></td>
<td align="left"><p>このチェックボックスをオンにすると、ユーザー&#39;s Windows の [スタート] メニューにアプリケーションのショートカットが作成されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ワークスペースが開始されたときにこのアプリケーションを起動する</p></td>
<td align="left"><p>このチェックボックスをオンにすると、MED-V ワークスペースが開始されたときにアプリケーションが自動的に実行されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MED-V の資格情報を使用してこのアプリケーションを実行する</p></td>
<td align="left"><p>このチェックボックスをオンにすると、アプリケーションに対して設定された資格情報ではなく、MED-V 資格情報を使用してユーザー名とパスワードを要求するアプリケーションが認証されます。</p>
<div class="alert">
<strong>注</strong><br/><p>SSO を使用している場合、コマンドラインはフォルダーパスC:\Windows\Explorer.exe する必要があり <strong> &quot; &quot; </strong> ます。 SSO を使用していない場合、コマンドラインはフォルダーパスである必要があり &quot; <strong> </strong> &quot; ます。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## 関連トピック


[公開されたアプリケーションを構成する方法](how-to-configure-published-applicationsmedvv2.md)









