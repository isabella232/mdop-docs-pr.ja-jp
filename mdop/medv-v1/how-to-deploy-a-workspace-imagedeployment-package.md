---
title: ワークスペースのイメージを展開する方法
description: ワークスペースのイメージを展開する方法
author: dansimp
ms.assetid: b2c77e0d-101d-4956-a27c-8beb0e4f262e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d691514691286c92bd62d6fda6666345e17eb9f3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827014"
---
# ワークスペースのイメージを展開する方法


展開パッケージを使用する場合、次のいずれかの方法で、クライアントコンピューターに新しい画像を展開することができます。

-   [Web ダウンロード](#bkmk-howtodeployaworkspaceimageviatheweb)

-   [プレステージイメージ](#bkmk-howtodeployaworkspaceimageusingimageprestaging)

-   [展開パッケージ内に画像を展開する](#bkmk-howtodeployaworkspaceimageusingadeploymentapackage)

## <a href="" id="bkmk-howtodeployaworkspaceimageviatheweb"></a>Web 経由でワークスペースイメージを展開する方法


**Web 経由でワークスペースイメージを展開するには**

1.  MED-V イメージをサーバーにアップロードします。

    画像をアップロードする方法については、「 [Med-v イメージをサーバーにアップロードする方法](how-to-upload-a-med-v-image-to-the-server.md)」を参照してください。

2.  展開パッケージを作成し、イメージの場所へのサーバーパスを含めます。

    展開パッケージを作成する方法については、「[展開パッケージを構成する方法](how-to-configure-a-deployment-package.md)」を参照してください。

3.  パッケージをエンドユーザーに展開します。

    パッケージの展開の詳細については、「 [Med-v クライアントをインストールする方法](how-to-install-med-v-clientdeployment-package.md)」を参照してください。

    MED-V クライアントは、初めてインストールされて開始されます。 初回起動時に、クライアントは、クライアントのインストールで指定されたサーバーアドレスから画像をダウンロードします。

## <a href="" id="bkmk-howtodeployaworkspaceimageusingimageprestaging"></a>イメージの事前ステージングを使用してワークスペースイメージを展開する方法


**イメージの事前ステージングを使用してワークスペースイメージを展開するには**

1.  イメージの事前ステージフォルダーを作成し、そのフォルダーにイメージをプッシュします。

    イメージの事前ステージングの構成の詳細については、「[イメージの事前ステージングを構成する方法](how-to-configure-image-pre-staging.md)」を参照してください。

2.  展開パッケージを作成し、イメージの事前ステージフォルダーへのパスを含めます。

    展開パッケージを作成する方法については、「[展開パッケージを構成する方法](how-to-configure-a-deployment-package.md)」を参照してください。

3.  パッケージをエンドユーザーに展開します。

    パッケージの展開の詳細については、「 [Med-v クライアントをインストールする方法](how-to-install-med-v-clientdeployment-package.md)」を参照してください。

    MED-V クライアントは、初めてインストールされて開始されます。 初めて起動するときに、クライアントは、クライアントのインストールで指定された事前ステージフォルダーから画像を取得します。

## <a href="" id="bkmk-howtodeployaworkspaceimageusingadeploymentapackage"></a>展開パッケージを使用してワークスペースイメージを展開する方法


**展開パッケージを使用してワークスペースイメージを展開するには**

1.  展開パッケージを作成し、その画像をパッケージに含めます。

    展開パッケージを作成する方法については、「[展開パッケージを構成する方法](how-to-configure-a-deployment-package.md)」を参照してください。

2.  パッケージをエンドユーザーに展開します。

    パッケージの展開の詳細については、「 [Med-v クライアントをインストールする方法](how-to-install-med-v-clientdeployment-package.md)」を参照してください。

    パッケージのインストールの一部として、この画像がホストにインポートされます。

## 関連トピック


[イメージ Web 配布サーバーを構成する方法](how-to-configure-the-image-web-distribution-server.md)

[展開パッケージを構成する方法](how-to-configure-a-deployment-package.md)

 

 





