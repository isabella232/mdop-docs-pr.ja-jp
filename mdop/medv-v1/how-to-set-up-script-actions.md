---
title: スクリプトのアクションを設定する方法
description: スクリプトのアクションを設定する方法
author: dansimp
ms.assetid: 367e28f1-d8c2-4845-a01b-2fff9128ccfd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2bfa264be447a0a8560e4af16ccaadc2ec1db3f6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812387"
---
# スクリプトのアクションを設定する方法


スクリプトアクションエディターを使用すると、管理者は、MED-V workspace のセットアップ中に実行される操作を作成できるだけでなく、実行する順序を定義することもできます。

ドメイン設定スクリプトに追加できる操作の一覧を次に示します。

-   **Windows を再起動**します。 windows を再起動します。

-   [**ドメインに参加**]: ドメインに参加している場合、この操作を行い、ユーザー名、パスワード、完全修飾ドメイン名、NetBIOS ドメイン名、および組織単位 (省略可能) を構成します。

-   [**接続の確認**] —接続するサーバーを構成し、med-v ワークスペースがネットワークリソース (ドメインサーバーなど) に接続できることを確認します。

-   **コマンドライン**-med-v ワークスペースのスクリプトを構成し、スクリプトのパスとスクリプトの引数を含むコマンドラインを入力します。

-   [**コンピューター名の変更**] —定義された設定に基づいて仮想マシンコンピューターの名前を変更します。

-   **自動ログオンを無効に**する-Windows 自動ログオンを無効にします。 この操作は、コンピューターをドメインに追加するスクリプトの最後に追加する必要があります。

## <a href="" id="how-to-set-up-script-actions-"></a>スクリプトのアクションを設定する方法


**スクリプトアクションを設定するには**

1.  [ **VM のセットアップ**] タブで、[**スクリプトエディター**] をクリックします。

2.  [**スクリプト操作**] ダイアログボックスの [**追加**] をクリックし、サブメニューで目的の操作をクリックします。

3.  次の表で説明するように、アクションを構成します。

    **注** 
    [**コンピューター名の変更**] が [ **VM の設定**] タブで構成されています。詳細については、「 [VM コンピューター名パターンプロパティを構成する方法](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)」を参照してください。

     

~~~
**Note**  
To rename a computer, Windows must be restarted. It is recommended to add a Restart Windows action following a Rename Computer action.
~~~



4. アクションの順序を設定するには、アクションを選んで、[**上**] または [**下**] をクリックします。

5. **[OK]** をクリックします。

**注**  
スクリプトを動作させるために、Join ドメインスクリプトを実行している場合、MED-V ワークスペース仮想マシンにログインしているユーザーは、ローカル管理者の権限を持っている必要があります。



**注**  
自動ログオンスクリプトを無効にする場合は、最初のセットアップが完了したら、自動ログオンで使用されるローカルゲストアカウントを無効にすることをお勧めします。



### <a href="" id="bkmk-joindomainproperties"></a>

**ドメインのプロパティに参加する**

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
<td align="left"><p>VM をドメインに参加させるときに使用する資格情報</p></td>
<td align="left"><p>VM をドメインに参加させるときに使用する資格情報のいずれかを選択します。</p>
<ul>
<li><p><strong>MED-V の資格情報を使っ </strong> て、エンドユーザーの資格情報を使います。</p></li>
<li><p><strong>次の資格情報を使用します </strong> 。指定された資格情報は、対応するフィールドにユーザー名とパスワードを入力します。</p></li>
</ul>
<div class="alert">
<strong>注</strong><br/><p>入力した資格情報は、すべての MED-V ワークスペースユーザーに表示されます。 ドメイン管理者の資格情報を提供することはお勧めしません。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>参加するドメイン</p></td>
<td align="left"><p>次のいずれかのオプションを選択してください:</p>
<ul>
<li><p><strong>ワークスペースの開始で使用されていたドメイン名を使用し </strong> ます。 med-v クライアントにログインするときに、エンドユーザーによって入力されたドメインに参加します。</p>
<p>NetBIOS から完全修飾ドメイン名へのマッピングを定義するには、[ <strong> グローバルドメインマッピングテーブル] をクリックし </strong> ます。 グローバルドメインマッピングテーブルで [追加] <strong> をクリックし </strong> 、 <strong> NetBIOS ドメイン名 </strong> と <strong> 完全修飾ドメイン名を入力 </strong> して、[OK] をクリックし <strong> </strong> ます。</p></li>
<li><p><strong>次のドメイン名を使用します </strong> 。指定したドメインに参加します。対応するフィールドにドメイン名と NetBIOS ドメイン名を入力します。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>組織単位</p></td>
<td align="left"><p>組織単位 (OU) を指定して、コンピューターを特定の OU に参加させることができます。 この形式は、ou 識別名の後に指定する必要があります。 OU = &lt; 組織単位 &gt; 、 &lt; ドメインコントローラー &gt; (例: OU = QATest、dc = IL、dc = MED、dc =、dc = com)。</p>
<div class="alert">
<strong>Warning</strong><br/><p>上の例のように、1レベルの OU のみがサポートされます。</p>
</div>
<div>
 
</div></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-checkconnectivityproperties"></a>

**接続のプロパティを確認する**

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
<td align="left"><p>IP アドレス</p></td>
<td align="left"><p>接続を確認するサーバーの IP アドレス。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Port</p></td>
<td align="left"><p>接続を確認しようとしているサーバーのポート。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>タイムアウト</p></td>
<td align="left"><p>応答を待つまでの待機時間 (秒数)。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-commandlineproperties"></a>

**コマンドラインのプロパティ**

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
<td align="left"><p>Path</p></td>
<td align="left"><p>コマンドラインのパス。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Arguments</p></td>
<td align="left"><p>コマンドライン引数。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>終了を待つ</p></td>
<td align="left"><p>このチェックボックスをオンにすると、スクリプトの操作が続行されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>エラー発生時</p></td>
<td align="left"><p>戻り値が指定された値以外の場合は、このチェックボックスをオンにします。</p>
<p>コマンドを正常に実行するための値を入力します。</p>
<p>既定値: <strong> 0</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p>一度だけ実行する</p></td>
<td align="left"><p>コマンドラインを1回だけ実行する場合は、このチェックボックスをオンにします。 スクリプトが失敗するかキャンセルされた場合は、このコマンドは再実行されません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>このコマンドラインは、ワークスペースの Windows を再起動します</p></td>
<td align="left"><p>コマンドラインで完了後に再起動する場合は、このチェックボックスをオンにします。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>操作の許可</p></td>
<td align="left"><p>コマンドでユーザーの操作が必要な場合は、このチェックボックスをオンにします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>進行状況メッセージ</p></td>
<td align="left"><p>コマンドの実行中にユーザーに表示されるメッセージ。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>エラーメッセージ</p></td>
<td align="left"><p>コマンドが失敗した場合にユーザーに表示されるメッセージ。</p></td>
</tr>
</tbody>
</table>

 

コマンドライン操作を構成するときに、次の表で定義されているように、いくつかの変数を使うことができます。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">パラメーター</th>
<th align="left">値</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>% MEDVUser%</p></td>
<td align="left"><p>認証されたユーザー名。</p></td>
<td align="left"><p>MED-V で認証されたユーザー名。 ユーザー名とパスワードは、[ドメインの参加] セットアップスクリプトで使うことができます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>% MEDVPassword%</p></td>
<td align="left"><p>認証されたパスワード。</p></td>
<td align="left"><p>MED-V で認証されたパスワード。 ユーザー名とパスワードは、[ドメインの参加] セットアップスクリプトで使うことができます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>% MEDVDomain%</p></td>
<td align="left"><p>構成済みドメイン。</p></td>
<td align="left"><p>MED-V 認証で構成されているドメイン。 VM のセットアップスクリプトで使うことができます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>%DesiredMachineName%</p></td>
<td align="left"><p>コンピューター名。</p></td>
<td align="left"><p>管理アプリケーションで構成されている一意のコンピューター名。 これは、VM のセットアップスクリプトで使うことができます。</p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[MED-V ワークスペースの仮想マシンのセットアップを構成する方法](how-to-configure-the-virtual-machine-setup-for-a-med-v-workspacemedvv2.md)

[VM のコンピューター名パターンのプロパティを構成する方法](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)

 

 





