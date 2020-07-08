---
title: FileSystem キャッシュのサイズを変更する方法
description: FileSystem キャッシュのサイズを変更する方法
author: dansimp
ms.assetid: 6ed17ba3-293b-4482-b3fa-31e5f606dad6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d63c98d53ccb31e8eb64bc70d3d79b2198c506e2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818004"
---
# FileSystem キャッシュのサイズを変更する方法


コマンドラインを使用して、ファイルシステムキャッシュのサイズを変更できます。 この操作を行うには、キャッシュの完全なリセットが必要です。また、管理者権限が必要です。

**ファイルシステムキャッシュのサイズを変更するには**

1.  次のレジストリ値を 0 (ゼロ) に設定します。

    HKEY \ _LOCAL \ _MACHINE ¥ $ ¥ (\) \ すべてのアプリの状態

2.  次のレジストリ値を、8192 MB などのパッケージを保持するために必要な最大キャッシュサイズ (MB 単位) に設定します。

    HKEY \ _LOCAL \ _MACHINE ¥ $ (英語) \ ソフト (\\) \ すべてのサイズ

3.  コンピューターを再起動します。

## 関連トピック


[コマンド ラインを使用して App-V Client レジストリ設定を構成する方法](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





