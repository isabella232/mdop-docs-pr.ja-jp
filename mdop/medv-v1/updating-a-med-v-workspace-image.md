---
title: MED-V ワークスペース イメージの更新
description: MED-V ワークスペース イメージの更新
author: dansimp
ms.assetid: 1b9c4a73-3487-43d2-98e3-43dbc79e10e3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 60a5d12622e0cb7012c6d0a22124d63c085f6d0a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825854"
---
# MED-V ワークスペース イメージの更新


画像は、次のいずれかの方法で更新できます。

-   エンタープライズソフトウェア配布システムを使用して、更新プログラムをゲストオペレーティングシステムにプッシュすることができます。

-   更新プログラムはイメージ Web 配布サーバーにアップロードでき、クライアントによってダウンロードされ、MED-V イメージに適用されます。

-   MED-V の基本イメージを更新して再展開することができます。

## <a href="" id="bkmk-howtoupdateamedvimageusinganesd"></a>エンタープライズソフトウェア配布システムを使用して MED-V イメージを更新する方法


**エンタープライズソフトウェア配布システムを使用して MED-V イメージを更新するには**

-   使用しているシステムのマニュアルを参照してください。

## <a href="" id="bkmk-howtoupdateamedvimageusingwebdownload"></a>Web ダウンロードを使用して MED-V イメージを更新する方法


**Web ダウンロードを使用して MED-V イメージを更新するには**

1.  [**仮想マシン**] タブで、更新される med-v イメージに関連付けられている med-v ワークスペースポリシーに、次の設定が適用されていることを確認します。

    -   [**新しいバージョンが利用可能になったときに更新を提案**する] チェックボックスがオンになっている。

    -   必要に応じて、[**このワークスペースのイメージをダウンロードするときにトリム転送を使用**する] チェックボックスがオンになっている必要があります。

    詳細については、「[仮想マシンの設定を Med-v ワークスペースに適用する方法](how-to-apply-virtual-machine-settings-to-a-med-v-workspace.md)」を参照してください。

2.  イメージの Web 配布サーバーにイメージの更新をアップロードします。

    更新する必要がある画像を含むすべてのクライアントは、更新プログラムを自動的にダウンロードして画像に適用します。

## <a href="" id="bkmk-howtoupdateamedvbaseimage"></a>MED-V ベースイメージを更新する方法


**MED-V ベースイメージを更新するには**

1.  仮想 PC2007 で既存の画像を開きます。

2.  イメージに必要な変更を加え、イメージを更新します (新しいソフトウェアをインストールするなど)。

3.  Virtual PC2007 を閉じます。

4.  画像をテストします。

5.  画像のテストが完了したら、既存の画像と同じ名前を使って、その画像をローカルリポジトリにパックします。

    **注** 画像に既存のバージョンとは異なる名前を指定した場合は、既存の画像の新しいバージョンではなく、新しい画像が作成されます。

     

6.  新しいバージョンをサーバーにアップロードし、イメージの事前ステージフォルダーにプッシュするか、展開パッケージで配布します。

## 関連トピック


[MED-V イメージの作成](creating-a-med-v-image.md)

[MED-V イメージを更新する方法](how-to-update-a-med-v-image.md)

[MED-V ワークスペース ポリシーの構成](configuring-med-v-workspace-policies.md)

[イメージ Web 配布サーバーを構成する方法](how-to-configure-the-image-web-distribution-server.md)

 

 





