---
title: FileSystem キャッシュをリセットする方法
description: FileSystem キャッシュをリセットする方法
author: dansimp
ms.assetid: 7777259d-8c21-4c06-9384-9599b69f9828
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 680634d98f8aac048af605c62029a0ee6b20af03
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816714"
---
# FileSystem キャッシュをリセットする方法


ファイルシステムキャッシュのリセットは、通常必要となるものではありません。 ただし、トラブルシューティングのためにファイルシステムキャッシュを完全にリセットする必要がある場合は、次の手順を実行します。 この操作を実行するには、管理者権限が必要です。

**FileSystem キャッシュをリセットするには**

1.  次のレジストリ値を 0 (ゼロ) に設定します。

    HKEY \ _LOCAL \ _MACHINE ¥ $ ¥ (\) \ すべてのアプリの状態

2.  コンピューターを再起動します。

## 関連トピック


[コマンド ラインを使用して App-V Client レジストリ設定を構成する方法](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





