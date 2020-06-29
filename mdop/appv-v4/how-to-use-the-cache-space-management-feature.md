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
# <span data-ttu-id="2c2c1-103">キャッシュ領域管理機能を使用する方法</span><span class="sxs-lookup"><span data-stu-id="2c2c1-103">How to Use the Cache Space Management Feature</span></span>


<span data-ttu-id="2c2c1-104">ファイルシステムキャッシュスペース管理機能には、最近使用した (LRU) アルゴリズムが使用されており、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="2c2c1-104">The FileSystem cache space management feature uses a Least Recently Used (LRU) algorithm and is enabled by default.</span></span> <span data-ttu-id="2c2c1-105">新しいパッケージに必要な領域がキャッシュ内の空き領域を超える場合は、Application Virtualization (App-v) クライアントでこの機能を使用して、既存のパッケージがキャッシュから削除され、新しいパッケージ用のスペースが確保されるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="2c2c1-105">If the space that is required for a new package would exceed the available free space in the cache, the Application Virtualization (App-V) Client uses this feature to determine which, if any, existing packages it can delete from the cache to make room for the new package.</span></span> <span data-ttu-id="2c2c1-106">クライアントは、"MinPkgAge" レジストリ値で指定された値よりも古い最終アクセス日のパッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="2c2c1-106">The client deletes the package with the oldest last-accessed date if it is older than the value specified in the MinPkgAge registry value.</span></span> <span data-ttu-id="2c2c1-107">ファイルシステムキャッシュスペース管理機能を使用すると、キャッシュスペースの問題を回避することもできます。</span><span class="sxs-lookup"><span data-stu-id="2c2c1-107">Use of the FileSystem cache space management feature can also help to avoid low cache space problems.</span></span>

<span data-ttu-id="2c2c1-108">必要に応じて、複数のパッケージが削除されます。</span><span class="sxs-lookup"><span data-stu-id="2c2c1-108">More than one package is deleted if necessary.</span></span> <span data-ttu-id="2c2c1-109">ロックされているパッケージは削除されません。</span><span class="sxs-lookup"><span data-stu-id="2c2c1-109">Packages that are locked are not deleted.</span></span>

<span data-ttu-id="2c2c1-110">**注** 展開される可能性のあるすべてのパッケージに対して十分な領域がキャッシュに割り当てられるようにするには、必要に応じてキャッシュを拡大できるように、クライアントを構成するときに、[**空きディスク領域のしきい値を使用**する] 設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="2c2c1-110">**Note** To ensure that the cache has sufficient space allocated for all packages that might be deployed, use the **Use free disk space threshold** setting when you configure the client so that the cache can grow as needed.</span></span> <span data-ttu-id="2c2c1-111">または、アプリの V キャッシュに必要なディスク容量を事前に確認して、インストール時にキャッシュサイズを適切に設定します。</span><span class="sxs-lookup"><span data-stu-id="2c2c1-111">Alternatively, determine in advance how much disk space will be needed for the App-V cache, and at installation time, set the cache size accordingly.</span></span>

 

<span data-ttu-id="2c2c1-112">キャッシュスペース管理機能は、UnloadLeastRecentlyUsed registry 値によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="2c2c1-112">The cache space management feature is controlled by the UnloadLeastRecentlyUsed registry value.</span></span> <span data-ttu-id="2c2c1-113">値1を指定すると機能が有効になり、0 (ゼロ) を指定すると無効になります。</span><span class="sxs-lookup"><span data-stu-id="2c2c1-113">A value of 1 enables the feature, and a value of 0 (zero) disables it.</span></span>

**<span data-ttu-id="2c2c1-114">キャッシュスペース管理機能を有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="2c2c1-114">To enable or disable the cache space management feature</span></span>**

-   <span data-ttu-id="2c2c1-115">LRU アルゴリズムを有効にするには、次のレジストリ値を1に設定します。</span><span class="sxs-lookup"><span data-stu-id="2c2c1-115">Set the following registry value to 1 to enable the LRU algorithm.</span></span> <span data-ttu-id="2c2c1-116">この機能を無効にするには、0 (ゼロ) に設定します。</span><span class="sxs-lookup"><span data-stu-id="2c2c1-116">Set it to 0 (zero) to disable the feature.</span></span>

    <span data-ttu-id="2c2c1-117">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\UnloadLeastRecentlyUsed</span><span class="sxs-lookup"><span data-stu-id="2c2c1-117">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\UnloadLeastRecentlyUsed</span></span>

**<span data-ttu-id="2c2c1-118">破棄できるパッケージを制御するには</span><span class="sxs-lookup"><span data-stu-id="2c2c1-118">To control which packages can be discarded</span></span>**

-   <span data-ttu-id="2c2c1-119">Discard の対象としてパッケージを選択できるかどうかを判断するには、次のレジストリ値を、パッケージに最後にアクセスしてから経過した日数と同じになるように設定します。</span><span class="sxs-lookup"><span data-stu-id="2c2c1-119">To determine when the package can be selected for discard, set the following registry value to equal the minimum number of days you want to elapse since the package was last accessed.</span></span> <span data-ttu-id="2c2c1-120">最近使用されたパッケージは破棄されません。</span><span class="sxs-lookup"><span data-stu-id="2c2c1-120">Packages that have been used more recently are not discarded.</span></span>

    <span data-ttu-id="2c2c1-121">HKEY \ _LOCAL \ _MACHINE ¥ $ ¥ (英語) \ ソフト (\\) \ すべてのアプリ</span><span class="sxs-lookup"><span data-stu-id="2c2c1-121">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS\\MinPkgAge</span></span>

    <span data-ttu-id="2c2c1-122">**注意** このレジストリキーの最大値は、0x00011111 です。</span><span class="sxs-lookup"><span data-stu-id="2c2c1-122">**Caution** The maximum value for this registry key is 0x00011111.</span></span> <span data-ttu-id="2c2c1-123">値を大きくすると、キャッシュ領域管理機能の適切な操作ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="2c2c1-123">Larger values will prevent the correct operation of the cache space management feature.</span></span>

     

## <span data-ttu-id="2c2c1-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2c2c1-124">Related topics</span></span>


[<span data-ttu-id="2c2c1-125">コマンド ラインを使用して App-V Client レジストリ設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="2c2c1-125">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





