---
title: MED-V イメージをサーバーにアップロードする方法
description: MED-V イメージをサーバーにアップロードする方法
author: dansimp
ms.assetid: 0e70dfdf-3e3a-4860-970c-535806caa907
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6703eb24bc3542c280af41988a257a2f14643645
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825704"
---
# MED-V イメージをサーバーにアップロードする方法


MED-V イメージのテストが完了したら、それをパックしてからサーバーにアップロードすることができます。 画像 Web 配布サーバーの構成の詳細については、「[イメージ Web 配布サーバーを構成する方法](how-to-configure-the-image-web-distribution-server.md)」を参照してください。

MED-V イメージがパックされてサーバーにアップロードされると、エンタープライズソフトウェア配布センターを使用してユーザーに配布するか、展開パッケージを使用してユーザーがダウンロードすることができます。 エンタープライズソフトウェアの配布センターを使用した展開については、「[エンタープライズソフトウェアの配布システムを使用した Med-v ワークスペースの展開](deploying-a-med-v-workspace-using-an-enterprise-software-distribution-system.md)」を参照してください。 パッケージを使用した展開について詳しくは、「[展開パッケージを使用した Med-v ワークスペースの展開](deploying-a-med-v-workspace-using-a-deployment-package.md)」をご覧ください。

**注**  
画像をアップロードする前に、Web プロキシがブラウザーの設定で定義されていないこと、および Windows Update が現在実行されていないことを確認します。



**サーバーに MED-V イメージをアップロードするには**

1.  [**ローカルパック**されたイメージ] ウィンドウで、作成した画像を選択します。

2.  [**アップロード**] をクリックします。

    画像がサーバーにアップロードされます。 これには時間がかかることがあります。

    サーバー上の画像は、次の表に示すプロパティで定義されています。

**サーバープロパティでのパックされた画像**

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

[MED-V イメージをパックする方法](how-to-pack-a-med-v-image.md)









