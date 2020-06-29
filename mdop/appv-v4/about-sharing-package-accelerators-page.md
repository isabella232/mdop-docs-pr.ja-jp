---
title: '[パッケージ アクセラレータの共有について] ページ'
description: '[パッケージ アクセラレータの共有について] ページ'
author: dansimp
ms.assetid: 9630cde0-e2c3-476f-8fa1-58b3c9f7d3f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 34fe55d910a7532f011b239ff5b8162aa9240f32
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819994"
---
# [パッケージ アクセラレータの共有について] ページ


ここでは、パッケージアクセラレータの共有方法に関するベストプラクティスについて説明します。 パッケージアクセラレータファイルを共有する予定がある場合は、コンピューター名、ユーザーアカウント情報、変換に含まれるアプリケーションに関する情報などの情報がパッケージアクセラレータファイルに含まれている可能性があります。 アプリケーションに個人情報が含まれていないことを確認するには、仮想アプリケーションパッケージに関連付けられている設定または構成ファイルを確認する必要があります。このページには、次の要素が含まれています。

-   **ユーザー名**。 Microsoft App-v Sequencer を実行しているコンピューターにログオンするときは、組み込みの**管理者**アカウントなどの一般的なユーザーアカウントを使用する必要があります。 既存のユーザー名に基づくアカウントは使用しないでください。

-   **コンピューター名**。 Sequencer を実行しているコンピューターの一般的ではない識別名を指定します。

-   **サーバーの URL**。 App-v Sequencer コンソールの [**展開**] タブで、サーバー URL 構成情報の既定の設定を使用します。

-   **アプリケーション**。 パッケージアクセラレータの作成時に、Sequencer を実行しているコンピューターにインストールされているアプリケーションの一覧を共有しない場合は、 **appv\_manifest.xml**ファイルを削除する必要があります。 このファイルは、仮想アプリケーションパッケージのパッケージルートディレクトリにあります。

## 関連トピック


[パッケージ アクセラレータの作成ウィザード (AppV 4.6 SP1)](create-package-accelerator-wizard--appv-46-sp1-.md)

[App-V パッケージ アクセラレータについて (App-V 4.6 SP1)](about-app-v-package-accelerators--app-v-46-sp1-.md)

 

 





