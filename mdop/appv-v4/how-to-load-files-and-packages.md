---
title: ファイルとパッケージを読み込む方法
description: ファイルとパッケージを読み込む方法
author: dansimp
ms.assetid: f86f5bf1-99a4-44d7-ae2f-e6049c482f68
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9427fd8089ec9c22d7d379b15ae94bf421ca2d44
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817237"
---
# ファイルとパッケージを読み込む方法


次の手順を使用して、Application Virtualization サーバーにファイルやパッケージを読み込むことができます。

**注** インストールプロセス中に、**コンテンツパス**ページ上の \\ コンテンツディレクトリの場所を指定しました。 このディレクトリは、その場所をポイントする前に、標準のファイル共有として作成して構成する必要があります。

 

**ファイルとパッケージを読み込むには**

1.  アプリケーションをストリーミングするコンピューターで、\\ コンテンツディレクトリに指定した場所に移動します。 必要に応じて、ディレクトリを作成し、標準のファイル共有として構成します。

2.  仮想アプリケーションとパッケージの SFT ファイルを、\\ コンテンツディレクトリに移動します。 お使いの SFT ファイルを整理して、混乱を避けるために、アプリケーションとパッケージを専用のサブフォルダーに配置します。

3.  次の条件を考慮して、シナリオと構成の要件に従って、アプリケーションとパッケージを読み込みます。

    -   アプリケーションやパッケージが Application Virtualization (App-v) Management サーバーに保存されている場合は、管理コンソールから読み込みます。 詳細については、「[アプリケーションを読み込みまたはアンロードする方法](how-to-load-or-unload-an-application.md)」または「[デスクトップ通知領域から仮想アプリケーションを読み込む](how-to-load-virtual-applications-from-the-desktop-notification-area.md)方法」を参照してください。

    -   アプリケーションが、app-v Streaming Server、Web サーバー、またはファイルサーバーとして構成されたコンピューターに保存されている場合は、アプリケーションを自動的に読み込むことができます。

        **注** App-v ストリーミングサーバーは、アプリケーションやパッケージ用の \\ コンテンツディレクトリを自動的にポーリングし、この情報を RAM に入れてアプリケーション要求を処理します。

        アプリケーションとパッケージを Web サーバーとファイルサーバーから取得するように、App-v クライアントが適切に構成されている必要があります。 詳細については、「[アプリケーションパッケージの取得用にクライアントを構成する方法](how-to-configure-the-client-for-application-package-retrieval.md)」を参照してください。

         

## 関連トピック


[Application Virtualization サーバー](application-virtualization-server.md)

 

 





