---
title: デスクトップ通知領域から仮想アプリケーションを読み込む方法
description: デスクトップ通知領域から仮想アプリケーションを読み込む方法
author: dansimp
ms.assetid: f52758eb-8b81-4b3c-9bc3-adcf7c00c238
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d7004f9e0031dfeeedc8b6a916e2f3488f1d31e1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817217"
---
# デスクトップ通知領域から仮想アプリケーションを読み込む方法


モバイルユーザーの場合は、接続されていない操作またはオフラインモードでアプリを使用するために、キャッシュにアプリケーションを完全に読み込むことをお勧めします。 アプリケーションの仮想化 (app-v) サーバーまたは Application Virtualization (App-v) ストリーミングサーバーからアプリケーションをストリーミングするには、アプリケーションを読み込むためにサーバーに接続する必要があります。 アプリケーションの読み込み時にサーバーに接続していない場合は、システムによって適切なエラーメッセージが生成されます。 また、ファイルまたはディスクからクライアントにアプリケーションをストリーミングすることもできます。

アプリケーションは一度に1つのアプリケーションに読み込まれます。 進行状況バーには、アプリの名前、アプリのロード率、およびキューに登録されているアプリケーションの合計数と比較して処理されたアプリケーションの数が表示されます。 進行中のアプリケーションは、100% ロードされる前にスキップできます。 残りのすべてのアプリケーションの読み込みをスキップすることもできます。

**注** システムでアプリケーションの読み込み中にエラーが発生した場合は、エラーが報告されます。 次のアプリケーションを読み込む前に、エラーダイアログを閉じる必要があります。

 

**すべてのアプリケーションを読み込むには**

1.  通知領域の [Application Virtualization システム] アイコンを右クリックします。

2.  ポップアップメニューから [**アプリケーションの読み込み**] を選びます。

**アプリケーションをスキップするには**

1.  進行状況バーをクリックしてダイアログボックスを表示します。

2.  目的の結果を得るには、次のいずれかのボタンを選択します。

    1.  [**スキップ**: 現在の読み込み中のアプリケーションをスキップします。

    2.  **すべてスキップ**: 残りのすべてのアプリケーションをスキップします。

    3.  **続行**: ダイアログボックスをキャンセルしてアプリケーションの読み込みを続行します。

## 関連トピック


[Application Virtualization Client Management の デスクトップ通知領域を使用する方法](how-to-use-the-desktop-notification-area-for-application-virtualization-client-management.md)

 

 





