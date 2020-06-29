---
title: MED-V イメージをパックする方法
description: MED-V イメージをパックする方法
author: dansimp
ms.assetid: e1ce2307-0f1b-4bf8-b146-e4012dc138d2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0a330b8feca922239691bed083767c3acc57105d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824677"
---
# MED-V イメージをパックする方法


MED-V イメージは、展開パッケージに追加したり、サーバーにアップロードしたりする前に、パックする必要があります。

**パックされた MED イメージを作成するには**

1.  [**イメージ**管理] ボタンをクリックします。

2.  **Images**モジュールの [**ローカルパック**されたイメージ] ウィンドウで、[**新規**] をクリックします。

3.  [パックされた**画像の作成**] ダイアログボックスで、次のいずれかの操作を行って、仮想マシンのイメージを選択します。

    -   [ **Base image file** ] フィールドに、med-v 用に準備された MICROSOFT 仮想 PC イメージが配置されているディレクトリへのフルパスを入力します。

    -   [**参照**] をクリックして、med-v 用に準備されている MICROSOFT 仮想 PC イメージが配置されているディレクトリを参照します。

4.  次のいずれかの操作を行って、新しい画像の名前を指定します。

    -   [**イメージ名**] フィールドに、目的の名前を入力します。

        **注**  
        画像名には、次の文字を含めることはできません: space " &lt; &gt; |\\ / : \* ?



~~~
    A new packed image will be created.

-   From the drop-down list, select an existing name.

    A new version of the existing image will be created.
~~~

5. **[OK]** をクリックします。

   次の表で定義されたプロパティを使用して、新しい MED-V パックされた画像がホストコンピューター上に作成されます。

**注**  
ローカルの**パック**された画像と**サーバーウィンドウ上のパック**された画像では、各画像の最新バージョンが親ノードとして表示されます。 親ノードをクリックして、その他のすべての既存バージョンの画像を表示します。



**ローカルのパックされた画像のプロパティ**

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
<td align="left"><p>画像名</p></td>
<td align="left"><p>管理者がイメージを作成したときに定義されたパックされたイメージの名前です。</p></td>
</tr>
<tr class="even">
<td align="left"><p>バージョン</p></td>
<td align="left"><p>表示される画像のバージョン。</p>
<div class="alert">
<strong>注</strong><br/><p>削除しない限り、以前のすべてのバージョンは保持されます。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>ファイルサイズ (圧縮済み)</p></td>
<td align="left"><p>画像の物理圧縮サイズ。</p></td>
</tr>
<tr class="even">
<td align="left"><p>画像サイズ (非圧縮)</p></td>
<td align="left"><p>画像の圧縮されていない物理サイズ。</p></td>
</tr>
</tbody>
</table>



## 関連トピック


[MED-V クライアントと MED-V 管理コンソールをインストールする方法](how-to-install-med-v-client-and-med-v-management-console.md)

[MED-V 管理コンソールのユーザー インターフェイスの使用](using-the-med-v-management-console-user-interface.md)

[MED-V の仮想 PC イメージの作成](creating-a-virtual-pc-image-for-med-v.md)









