---
title: イメージ Web 配布サーバーを構成する方法
description: イメージ Web 配布サーバーを構成する方法
author: dansimp
ms.assetid: 2d32ae79-dff5-4c05-a412-dd15452b6007
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8a21b14fbaca6bbc09d4c35b4d8fb86365c42e3b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825157"
---
# イメージ Web 配布サーバーを構成する方法


イメージリポジトリは、イメージの配布に使用されるオプションのサーバーです (管理者は、新しいイメージをアップロードし、クライアントコンピューターは、新しいイメージをアップロードし、クライアントコンピューターは、サーバーを15分ごとに確認して、新しい画像が利用可能な場合は、そのイメージを更新します)。

## <a href="" id="bkmk-configuringanimagereporitoryusingiis"></a>


画像配布サーバーには、次のものが必要です。

-   インターネットインフォメーションサービス (IIS) —詳細については、「[インターネットインフォメーションサービス](https://go.microsoft.com/fwlink/?LinkId=142995)」を参照してください。

    IIS のインストール中に、役割サービスを追加するときに、次のサポートされている認証方法を選択します。

    -   **基本認証**

    -   **Windows 認証**

    -   **クライアント証明書のマッピング認証**

    IIS を構成する場合は、次の情報を含めます。

    -   **MEDVImages**という名前のエイリアスを使用して仮想ディレクトリを追加します。 物理パスは、画像の場所をポイントする必要があります。

    -   BITS を有効にします。

    -   次の MIME の種類を追加します。

        -   **ckm (アプリケーション/オクテット-ストリーム)**

        -   **. index (アプリケーション/オクテット-ストリーム**)

    -   MED-V サイトで、**すべてのユーザー**に読み取りアクセス許可を追加します。

    -   IIS を再起動します。

-   IIS 用 BITS サーバー拡張機能: 詳細については、「 [Bits サーバー拡張機能をインストール](https://go.microsoft.com/fwlink/?LinkId=142996)する」を参照してください。

## 関連トピック


[サポートされる構成](supported-configurationsmedv-orientation.md)

[MED-V イメージ リポジトリを設計する](design-the-med-v-image-repositories.md)

 

 





