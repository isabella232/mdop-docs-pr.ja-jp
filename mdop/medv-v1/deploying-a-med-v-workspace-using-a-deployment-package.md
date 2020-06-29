---
title: 展開パッケージを使用した MED-V ワークスペースの展開
description: 展開パッケージを使用した MED-V ワークスペースの展開
author: dansimp
ms.assetid: e07fa70a-1a9f-486f-9a86-b33593b234da
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dc16b32fd44e45606df5502fda2e580d404dbb19
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823634"
---
# 展開パッケージを使用した MED-V ワークスペースの展開


展開パッケージのインストールでは、必要なすべての前提条件と、管理者によって定義されたすべての設定と共に、MED-V クライアントをインストールする方法が提供されます。

展開パッケージを使用する場合、パッケージは共有ネットワークまたはリムーバブルメディア経由で配布されます。 画像はパッケージに含めることも、個別に配布することもできます。

展開パッケージを作成する前に、展開の準備が整った MED-V イメージを作成していることを確認します。 MED-V イメージの作成について詳しくは、「 [Med-v イメージを作成](creating-a-med-v-image.md)する」をご覧ください。

MED-V イメージの準備が整ったら、環境にイメージを配布するための最適な方法を検討してください。 画像は、次のいずれかの方法で配布できます。

-   Web にアップロードされ、Web ダウンロードによって配布されます。必要に応じて、Trim Transfer テクノロジを使用します。

-   プレステージイメージを使用して配布されます。

-   展開パッケージに含まれており、他のすべての MED-V コンポーネントと共に配布されます。

画像がパッケージに含まれている場合、その画像に必要なその他の構成はありません。 画像が展開パッケージに含まれない場合は、次のいずれかの操作を行います。

-   Web 経由でイメージを展開する場合は、イメージ Web 配布サーバーに MED-V イメージをアップロードします。 画像 Web 配布サーバーの構成の詳細については、「[イメージ Web 配布サーバーを構成する方法](how-to-configure-the-image-web-distribution-server.md)」を参照してください。 画像をサーバーにアップロードする方法については、「 [Med-v イメージをサーバーにアップロードする方法](how-to-upload-a-med-v-image-to-the-server.md)」を参照してください。

-   イメージのプレステージでイメージを展開する場合は、プレステージフォルダーを構成し、そのフォルダーに MED-V イメージをプッシュします。 イメージの事前ステージングの構成の詳細については、「[イメージの事前ステージングを構成する方法](how-to-configure-image-pre-staging.md)」を参照してください。

**注** イメージの事前ステージングを使用している場合は、展開パッケージを作成する前に、イメージの事前ステージフォルダーを構成することが重要です。 フォルダーパスは展開パッケージに含まれている必要があります。

 

最後に、展開パッケージを作成します。 展開パッケージの作成の詳細については、「[展開パッケージを構成する方法](how-to-configure-a-deployment-package.md)」を参照してください。 パッケージが完了したら、パッケージを展開用に配布します。

展開パッケージが配布された後、MED-V クライアントをインストールして、イメージを展開することができます。 MED-V クライアントのインストールの詳細については、「 [Med-v クライアントをインストールする方法](how-to-install-med-v-clientdeployment-package.md)」を参照してください。 イメージの展開の詳細については、「[ワークスペースイメージを展開する方法](how-to-deploy-a-workspace-imagedeployment-package.md)」を参照してください。

 

 





