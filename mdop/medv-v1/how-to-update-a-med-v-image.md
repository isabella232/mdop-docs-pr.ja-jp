---
title: MED-V イメージを更新する方法
description: MED-V イメージを更新する方法
author: dansimp
ms.assetid: 61eacf50-3a00-4bb8-b2f3-7350a6467fa1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2f62cbd54d8593646460700a86ea48b5df4ce437
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812498"
---
# MED-V イメージを更新する方法


## MED-V イメージを更新する方法


既存の MED-V イメージを更新して、新しいバージョンのイメージを作成することができます。 これで、新しいバージョンがクライアントコンピューターに展開され、既存の画像が置き換えられます。

**注** 新しいバージョンがクライアントに展開されると、既存のイメージが上書きされます。 画像を更新するときに、クライアント上のデータを保存する必要がないことを確認します。

 

**MED-V イメージを更新するには**

1.  仮想 PC2007 で既存の画像を開きます。

2.  イメージに必要な変更を加え、イメージを更新します (新しいソフトウェアをインストールするなど)。

3.  Virtual PC2007 を閉じます。

4.  画像をテストします。

5.  画像のテストが完了したら、既存の画像と同じ名前を使って、その画像をローカルリポジトリにパックします。

    **注** 画像に既存のバージョンとは異なる名前を指定した場合は、既存の画像の新しいバージョンではなく、新しい画像が作成されます。

     

6.  サーバーに新しいバージョンをアップロードするか、展開パッケージを使用して配布します。

## 関連トピック


[MED-V の仮想 PC イメージの作成](creating-a-virtual-pc-image-for-med-v.md)

[MED-V イメージを作成してテストする方法](how-to-create-and-test-a-med-v-image.md)

[MED-V イメージをパックする方法](how-to-pack-a-med-v-image.md)

[MED-V イメージをサーバーにアップロードする方法](how-to-upload-a-med-v-image-to-the-server.md)

[MED-V ワークスペース イメージの更新](updating-a-med-v-workspace-image.md)

 

 





