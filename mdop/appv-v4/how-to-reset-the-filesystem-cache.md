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
# <span data-ttu-id="c2686-103">FileSystem キャッシュをリセットする方法</span><span class="sxs-lookup"><span data-stu-id="c2686-103">How to Reset the FileSystem Cache</span></span>


<span data-ttu-id="c2686-104">ファイルシステムキャッシュのリセットは、通常必要となるものではありません。</span><span class="sxs-lookup"><span data-stu-id="c2686-104">Resetting the FileSystem cache is not something that should usually be necessary.</span></span> <span data-ttu-id="c2686-105">ただし、トラブルシューティングのためにファイルシステムキャッシュを完全にリセットする必要がある場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c2686-105">However if you need to completely reset the FileSystem cache, perhaps for troubleshooting purposes, you can use the following procedure.</span></span> <span data-ttu-id="c2686-106">この操作を実行するには、管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="c2686-106">Administrative rights are required to perform this action.</span></span>

**<span data-ttu-id="c2686-107">FileSystem キャッシュをリセットするには</span><span class="sxs-lookup"><span data-stu-id="c2686-107">To reset the FileSystem cache</span></span>**

1.  <span data-ttu-id="c2686-108">次のレジストリ値を 0 (ゼロ) に設定します。</span><span class="sxs-lookup"><span data-stu-id="c2686-108">Set the following registry value to 0 (zero):</span></span>

    <span data-ttu-id="c2686-109">HKEY \ _LOCAL \ _MACHINE ¥ $ ¥ (\) \ すべてのアプリの状態</span><span class="sxs-lookup"><span data-stu-id="c2686-109">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\State</span></span>

2.  <span data-ttu-id="c2686-110">コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="c2686-110">Restart the computer.</span></span>

## <span data-ttu-id="c2686-111">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c2686-111">Related topics</span></span>


[<span data-ttu-id="c2686-112">コマンド ラインを使用して App-V Client レジストリ設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="c2686-112">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





