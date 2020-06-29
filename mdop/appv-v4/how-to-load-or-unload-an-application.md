---
title: アプリケーションの読み込みまたはアンロードを行う方法
description: アプリケーションの読み込みまたはアンロードを行う方法
author: dansimp
ms.assetid: 8c149761-c591-433f-972b-91793a69c654
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7eb99b1f38034ccb7bc16b2c8ebdcfa1cc8b36a9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817234"
---
# <span data-ttu-id="ae420-103">アプリケーションの読み込みまたはアンロードを行う方法</span><span class="sxs-lookup"><span data-stu-id="ae420-103">How to Load or Unload an Application</span></span>


<span data-ttu-id="ae420-104">次の手順を使用して、アプリケーションの仮想化クライアント管理コンソールの [**アプリケーション**] ノードの [**結果**] ウィンドウから直接、キャッシュからアプリケーションを読み込みまたはアンロードできます。</span><span class="sxs-lookup"><span data-stu-id="ae420-104">You can use the following procedures to load or unload an application from the cache, directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span> <span data-ttu-id="ae420-105">このノードを選択すると、[**結果**] ウィンドウにアプリケーションの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae420-105">When you select this node, the **Results** pane displays a list of applications.</span></span>

<span data-ttu-id="ae420-106">**注** パッケージを読み込みまたはアンロードすると、パッケージ内のすべてのアプリケーションがキャッシュに読み込まれるか、またはキャッシュから削除されます。</span><span class="sxs-lookup"><span data-stu-id="ae420-106">**Note** When you load or unload a package, all the applications in the package are loaded into or removed from cache.</span></span> <span data-ttu-id="ae420-107">パッケージを読み込むときに、キャッシュ内にアプリケーションを読み込むための十分な領域がない場合は、キャッシュサイズを大きくします。</span><span class="sxs-lookup"><span data-stu-id="ae420-107">When loading a package, if you do not have adequate space in cache to load the applications, increase your cache size.</span></span> <span data-ttu-id="ae420-108">キャッシュサイズの詳細については、「[キャッシュサイズとドライブ文字の指定を変更する方法](how-to-change-the-cache-size-and-the-drive-letter-designation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae420-108">For more information about cache size, see [How to Change the Cache Size and the Drive Letter Designation](how-to-change-the-cache-size-and-the-drive-letter-designation.md).</span></span>

 

**<span data-ttu-id="ae420-109">アプリケーションを読み込むには</span><span class="sxs-lookup"><span data-stu-id="ae420-109">To load an application</span></span>**

1.  <span data-ttu-id="ae420-110">[**結果**] ウィンドウにカーソルを移動し、目的のアプリケーションを右クリックして、ポップアップメニューから [**読み込み**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae420-110">Move the cursor to the **Results** pane, right-click the desired application, and select **Load** from the pop-up menu.</span></span>

2.  <span data-ttu-id="ae420-111">アプリケーションが自動的に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="ae420-111">The application is automatically loaded.</span></span> <span data-ttu-id="ae420-112">進捗状況は、[**パッケージステータス**というラベルの列で追跡されます。</span><span class="sxs-lookup"><span data-stu-id="ae420-112">The progress is tracked in the column labeled **Package Status**.</span></span> <span data-ttu-id="ae420-113">ロードが完了していることを確認するか、進行状況を表示するには、ビューを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae420-113">You must refresh the view to see that the load is complete or to see the progress.</span></span>

**<span data-ttu-id="ae420-114">アプリケーションをアンロードするには</span><span class="sxs-lookup"><span data-stu-id="ae420-114">To unload an application</span></span>**

1.  <span data-ttu-id="ae420-115">[**結果**] ウィンドウにカーソルを移動し、目的のアプリケーションを右クリックして、ポップアップメニューから [**アンロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae420-115">Move the cursor to the **Results** pane, right-click the desired application, and select **Unload** from the pop-up menu.</span></span>

2.  <span data-ttu-id="ae420-116">アプリケーションは自動的にアンロードされ、[**パッケージの状態**] 列が更新されて変更が反映されます。</span><span class="sxs-lookup"><span data-stu-id="ae420-116">The application is automatically unloaded, and the **Package Status** column is updated to reflect the change.</span></span>

## <span data-ttu-id="ae420-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ae420-117">Related topics</span></span>


[<span data-ttu-id="ae420-118">キャッシュ サイズおよびドライブ文字の指定を変更する方法</span><span class="sxs-lookup"><span data-stu-id="ae420-118">How to Change the Cache Size and the Drive Letter Designation</span></span>](how-to-change-the-cache-size-and-the-drive-letter-designation.md)

 

 





