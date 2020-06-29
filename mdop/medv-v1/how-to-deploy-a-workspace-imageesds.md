---
title: ワークスペースのイメージを展開する方法
description: ワークスペースのイメージを展開する方法
author: dansimp
ms.assetid: ccc8e89b-1625-4b58-837e-4c6d93d46070
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4cb16b0a4c278d135fdc9b737aa7a6e9b46115e1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827004"
---
# ワークスペースのイメージを展開する方法


エンタープライズソフトウェア配布システムを使用している場合、次のいずれかの方法で、クライアントコンピューターに新しい画像を展開することができます。

-   [Web ダウンロード](#bkmk-howtodeployaworkspaceimageviatheweb)

-   [プレステージイメージ](#bkmk-howtodeployaworkspaceimageusingimageprestaging)

## <a href="" id="bkmk-howtodeployaworkspaceimageviatheweb"></a>Web 経由でワークスペースイメージを展開する方法


**Web 経由でワークスペースイメージを展開するには**

1.  MED-V イメージをサーバーにアップロードします。

    画像をアップロードする方法については、「 [Med-v イメージをサーバーにアップロードする方法](how-to-upload-a-med-v-image-to-the-server.md)」を参照してください。

2.  エンタープライズソフトウェア配布システムを使用して、ユーザーのコンピューターに MED-V クライアントの .msi パッケージをインストールします。

    MED-V の client.msi パッケージをインストールする方法については、「 [Med-v クライアントをインストールする方法](how-to-install-med-v-clientesds.md)」を参照してください。

    MED-V クライアントは、初めてインストールされて開始されます。 初回起動時に、クライアントは、クライアントのインストールで指定されたサーバーアドレスから画像をダウンロードします。

## <a href="" id="bkmk-howtodeployaworkspaceimageusingimageprestaging"></a>イメージの事前ステージングを使用してワークスペースイメージを展開する方法


**イメージの事前ステージングを使用してワークスペースイメージを展開するには**

1.  イメージの事前ステージフォルダーを作成し、そのフォルダーにイメージをプッシュします。

    イメージの事前ステージングの構成の詳細については、「[イメージの事前ステージングを構成する方法](how-to-configure-image-pre-staging.md)」を参照してください。

2.  エンタープライズソフトウェア配布システムを使用して、ユーザーのコンピューターに MED-V クライアントの .msi パッケージをインストールします。

    MED-V の client.msi パッケージをインストールする方法については、「 [Med-v クライアントをインストールする方法](how-to-install-med-v-clientesds.md)」を参照してください。

    MED-V クライアントは、初めてインストールされて開始されます。 初めて起動するときに、クライアントは、クライアントのインストールで指定された事前ステージフォルダーから画像を取得します。

## 関連トピック


[イメージ Web 配布サーバーを構成する方法](how-to-configure-the-image-web-distribution-server.md)

 

 





