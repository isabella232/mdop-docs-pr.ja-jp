---
title: キャッシュ領域管理機能を使用する方法
description: キャッシュ領域管理機能を使用する方法
author: dansimp
ms.assetid: 60965660-c015-46a8-88ac-54cbc050fe33
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fcb9cc4bc076e1acf52fb1c03797384c45b82f7b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816407"
---
# キャッシュ領域管理機能を使用する方法


ファイルシステムキャッシュスペース管理機能には、最近使用した (LRU) アルゴリズムが使用されており、既定で有効になっています。 新しいパッケージに必要な領域がキャッシュ内の空き領域を超える場合は、Application Virtualization (App-v) クライアントでこの機能を使用して、既存のパッケージがキャッシュから削除され、新しいパッケージ用のスペースが確保されるかどうかを確認します。 クライアントは、"MinPkgAge" レジストリ値で指定された値よりも古い最終アクセス日のパッケージを削除します。 ファイルシステムキャッシュスペース管理機能を使用すると、キャッシュスペースの問題を回避することもできます。

必要に応じて、複数のパッケージが削除されます。 ロックされているパッケージは削除されません。

**注** 展開される可能性のあるすべてのパッケージに対して十分な領域がキャッシュに割り当てられるようにするには、必要に応じてキャッシュを拡大できるように、クライアントを構成するときに、[**空きディスク領域のしきい値を使用**する] 設定を使用します。 または、アプリの V キャッシュに必要なディスク容量を事前に確認して、インストール時にキャッシュサイズを適切に設定します。

 

キャッシュスペース管理機能は、UnloadLeastRecentlyUsed registry 値によって制御されます。 値1を指定すると機能が有効になり、0 (ゼロ) を指定すると無効になります。

**キャッシュスペース管理機能を有効または無効にするには**

-   LRU アルゴリズムを有効にするには、次のレジストリ値を1に設定します。 この機能を無効にするには、0 (ゼロ) に設定します。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\UnloadLeastRecentlyUsed

**破棄できるパッケージを制御するには**

-   Discard の対象としてパッケージを選択できるかどうかを判断するには、次のレジストリ値を、パッケージに最後にアクセスしてから経過した日数と同じになるように設定します。 最近使用されたパッケージは破棄されません。

    HKEY \ _LOCAL \ _MACHINE ¥ $ ¥ (英語) \ ソフト (\\) \ すべてのアプリ

    **注意** このレジストリキーの最大値は、0x00011111 です。 値を大きくすると、キャッシュ領域管理機能の適切な操作ができなくなります。

     

## 関連トピック


[コマンド ラインを使用して App-V Client レジストリ設定を構成する方法](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





