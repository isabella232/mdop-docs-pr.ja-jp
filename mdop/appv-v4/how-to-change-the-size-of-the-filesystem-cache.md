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
# <span data-ttu-id="22c75-103">FileSystem キャッシュのサイズを変更する方法</span><span class="sxs-lookup"><span data-stu-id="22c75-103">How to Change the Size of the FileSystem Cache</span></span>


<span data-ttu-id="22c75-104">コマンドラインを使用して、ファイルシステムキャッシュのサイズを変更できます。</span><span class="sxs-lookup"><span data-stu-id="22c75-104">You can change the size of the FileSystem cache by using the command line.</span></span> <span data-ttu-id="22c75-105">この操作を行うには、キャッシュの完全なリセットが必要です。また、管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="22c75-105">This action requires a complete reset of the cache, and it requires administrative rights.</span></span>

**<span data-ttu-id="22c75-106">ファイルシステムキャッシュのサイズを変更するには</span><span class="sxs-lookup"><span data-stu-id="22c75-106">To change the size of the FileSystem cache</span></span>**

1.  <span data-ttu-id="22c75-107">次のレジストリ値を 0 (ゼロ) に設定します。</span><span class="sxs-lookup"><span data-stu-id="22c75-107">Set the following registry value to 0 (zero):</span></span>

    <span data-ttu-id="22c75-108">HKEY \ _LOCAL \ _MACHINE ¥ $ ¥ (\) \ すべてのアプリの状態</span><span class="sxs-lookup"><span data-stu-id="22c75-108">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\State</span></span>

2.  <span data-ttu-id="22c75-109">次のレジストリ値を、8192 MB などのパッケージを保持するために必要な最大キャッシュサイズ (MB 単位) に設定します。</span><span class="sxs-lookup"><span data-stu-id="22c75-109">Set the following registry value to the maximum cache size, in MB, that is necessary to hold the packages—for example, 8192 MB:</span></span>

    <span data-ttu-id="22c75-110">HKEY \ _LOCAL \ _MACHINE ¥ $ (英語) \ ソフト (\\) \ すべてのサイズ</span><span class="sxs-lookup"><span data-stu-id="22c75-110">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\FileSize</span></span>

3.  <span data-ttu-id="22c75-111">コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="22c75-111">Restart the computer.</span></span>

## <span data-ttu-id="22c75-112">関連トピック</span><span class="sxs-lookup"><span data-stu-id="22c75-112">Related topics</span></span>


[<span data-ttu-id="22c75-113">コマンド ラインを使用して App-V Client レジストリ設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="22c75-113">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





