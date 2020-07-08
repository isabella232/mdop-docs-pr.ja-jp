---
title: エンタープライズ ソフトウェア配布システムを使用した MED-V ワークスペースの展開
description: エンタープライズ ソフトウェア配布システムを使用した MED-V ワークスペースの展開
author: dansimp
ms.assetid: 867faed6-74ce-4573-84be-8bf26e66c08c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fb9ebbc0fb605f84c5a8e67fc77fd9be51b29ff4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823627"
---
# エンタープライズ ソフトウェア配布システムを使用した MED-V ワークスペースの展開


MED-V クライアントは、Microsoft System Center Configuration Manager などのエンタープライズソフトウェア配布システムを使用して配布できます。

**注** Microsoft System Center Configuration Manager を使用して MED-V をインストールする場合は、MED-V のパッケージを作成するときに、[実行] モードを [管理者権限] に設定します。

 

エンタープライズソフトウェア配布システムを使用して MED-V を展開する前に、展開の準備が整った MED-V イメージを作成したことを確認します。 MED-V イメージの作成について詳しくは、「 [Med-v イメージを作成](creating-a-med-v-image.md)する」をご覧ください。

MED-V イメージの準備が整ったら、環境にイメージを配布するための最適な方法を検討してください。 画像は、次のいずれかの方法で配布できます。

-   Web にアップロードされ、Web ダウンロードによって配布されます。必要に応じて、Trim Transfer テクノロジを利用できます。

-   プレステージイメージを使用して配布されます。

## Web 経由でのイメージの展開


Web 経由で画像を展開する場合は、MED-V イメージを画像 Web 配布サーバーにアップロードします。 画像 Web 配布サーバーの構成の詳細については、「[イメージ Web 配布サーバーを構成する方法](how-to-configure-the-image-web-distribution-server.md)」を参照してください。 画像をサーバーにアップロードする方法については、「 [Med-v イメージをサーバーにアップロードする方法](how-to-upload-a-med-v-image-to-the-server.md)」を参照してください。

## プレステージ経由でのイメージの展開


イメージのプレステージでイメージを展開する場合は、プレステージフォルダーを構成し、そのフォルダーに MED-V イメージをプッシュします。 イメージの事前ステージングの構成の詳細については、「[イメージの事前ステージングを構成する方法](how-to-configure-image-pre-staging.md)」を参照してください。

**注** イメージの事前ステージングを使用している場合は、client.msi パッケージをプッシュする前に、イメージの事前ステージフォルダーを構成することが重要です。 フォルダーパスは、client.msi パッケージに含まれている必要があります。

 

最後に、エンタープライズソフトウェアの配布センターを使用して、client.msi パッケージをプッシュします。 その後、MED-V をインストールして、イメージを展開することができます。 MED-V クライアントのインストールの詳細については、「 [Med-v クライアントをインストールする方法](how-to-install-med-v-clientesds.md)」を参照してください。 イメージの展開の詳細については、「[ワークスペースイメージを展開する方法](how-to-deploy-a-workspace-imageesds.md)」を参照してください。

 

 





