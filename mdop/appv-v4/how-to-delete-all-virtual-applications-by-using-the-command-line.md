---
title: コマンド ラインを使用してすべての仮想アプリケーションを削除する方法
description: コマンド ラインを使用してすべての仮想アプリケーションを削除する方法
author: dansimp
ms.assetid: bfe13b5c-825a-4eb1-a979-6c4b8d8b2a9c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 55c809df31fa5c19f2f1a56c143d492b092156c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817537"
---
# コマンド ラインを使用してすべての仮想アプリケーションを削除する方法


特定のコンピューターからすべての仮想アプリケーションを削除するには、次の手順に従います。

**注** すべてのアプリケーションがパッケージから削除されると、Application Virtualization (App-v) クライアントもパッケージを削除します。

 

**すべてのアプリケーションを削除するには**

-   次のコマンドを実行して、コマンドが実行されているユーザーアカウントのすべてのアプリケーションを削除します。 オプションの/グローバルスイッチを指定してコマンドを実行すると、管理者権限を持つアカウントを使用して、すべてのユーザーのアプリケーションが削除されます。

    `SFTMIME DELETE OBJ:APP [/GLOBAL]`

    **注** すべてのアプリケーションがパッケージから削除されると、Application Virtualization (App-v) クライアントもパッケージを削除します。

     

## 関連トピック


[コマンド ラインを使用してパッケージを追加する方法](how-to-add-a-package-by-using-the-command-line.md)

[コマンド ラインを使用してパッケージを削除する方法](how-to-remove-a-package-by-using-the-command-line.md)

 

 





