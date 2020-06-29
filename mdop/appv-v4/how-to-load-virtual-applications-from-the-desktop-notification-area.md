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
# <span data-ttu-id="aff73-103">デスクトップ通知領域から仮想アプリケーションを読み込む方法</span><span class="sxs-lookup"><span data-stu-id="aff73-103">How to Load Virtual Applications from the Desktop Notification Area</span></span>


<span data-ttu-id="aff73-104">モバイルユーザーの場合は、接続されていない操作またはオフラインモードでアプリを使用するために、キャッシュにアプリケーションを完全に読み込むことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="aff73-104">If you are a mobile user, you might want to fully load your applications in the cache to use them during disconnected operation or offline mode.</span></span> <span data-ttu-id="aff73-105">アプリケーションの仮想化 (app-v) サーバーまたは Application Virtualization (App-v) ストリーミングサーバーからアプリケーションをストリーミングするには、アプリケーションを読み込むためにサーバーに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aff73-105">To stream applications from the Application Virtualization (App-V) Server or the Application Virtualization (App-V) Streaming Server, you must be connected to a server to load applications.</span></span> <span data-ttu-id="aff73-106">アプリケーションの読み込み時にサーバーに接続していない場合は、システムによって適切なエラーメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="aff73-106">If you are not connected to the server when you attempt to load applications, your system will generate an appropriate error message.</span></span> <span data-ttu-id="aff73-107">また、ファイルまたはディスクからクライアントにアプリケーションをストリーミングすることもできます。</span><span class="sxs-lookup"><span data-stu-id="aff73-107">You can also stream applications to the client from a file or disk.</span></span>

<span data-ttu-id="aff73-108">アプリケーションは一度に1つのアプリケーションに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="aff73-108">The applications are loaded one application at a time.</span></span> <span data-ttu-id="aff73-109">進行状況バーには、アプリの名前、アプリのロード率、およびキューに登録されているアプリケーションの合計数と比較して処理されたアプリケーションの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aff73-109">The progress bar shows you the application name, the percentage of application loaded, and the number of applications already processed compared to the total number of the applications queued.</span></span> <span data-ttu-id="aff73-110">進行中のアプリケーションは、100% ロードされる前にスキップできます。</span><span class="sxs-lookup"><span data-stu-id="aff73-110">You can skip any application in progress before it is 100% loaded.</span></span> <span data-ttu-id="aff73-111">残りのすべてのアプリケーションの読み込みをスキップすることもできます。</span><span class="sxs-lookup"><span data-stu-id="aff73-111">You can skip the loading of all remaining applications as well.</span></span>

<span data-ttu-id="aff73-112">**注** システムでアプリケーションの読み込み中にエラーが発生した場合は、エラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="aff73-112">**Note** If your system encounters an error while loading an application, it reports the error to you.</span></span> <span data-ttu-id="aff73-113">次のアプリケーションを読み込む前に、エラーダイアログを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="aff73-113">You must dismiss the error dialog before it will load the next application.</span></span>

 

**<span data-ttu-id="aff73-114">すべてのアプリケーションを読み込むには</span><span class="sxs-lookup"><span data-stu-id="aff73-114">To load all applications</span></span>**

1.  <span data-ttu-id="aff73-115">通知領域の [Application Virtualization システム] アイコンを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="aff73-115">Right-click the Application Virtualization System icon in the notification area.</span></span>

2.  <span data-ttu-id="aff73-116">ポップアップメニューから [**アプリケーションの読み込み**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="aff73-116">Select **Load Applications** from the pop-up menu.</span></span>

**<span data-ttu-id="aff73-117">アプリケーションをスキップするには</span><span class="sxs-lookup"><span data-stu-id="aff73-117">To skip applications</span></span>**

1.  <span data-ttu-id="aff73-118">進行状況バーをクリックしてダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="aff73-118">Click the progress bar to display the dialog box.</span></span>

2.  <span data-ttu-id="aff73-119">目的の結果を得るには、次のいずれかのボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="aff73-119">Select one of the following buttons to achieve the desired results:</span></span>

    1.  <span data-ttu-id="aff73-120">[**スキップ**: 現在の読み込み中のアプリケーションをスキップします。</span><span class="sxs-lookup"><span data-stu-id="aff73-120">**Skip**—To skip the currently loading application.</span></span>

    2.  <span data-ttu-id="aff73-121">**すべてスキップ**: 残りのすべてのアプリケーションをスキップします。</span><span class="sxs-lookup"><span data-stu-id="aff73-121">**Skip All**—To skip all remaining applications.</span></span>

    3.  <span data-ttu-id="aff73-122">**続行**: ダイアログボックスをキャンセルしてアプリケーションの読み込みを続行します。</span><span class="sxs-lookup"><span data-stu-id="aff73-122">**Continue**—To cancel the dialog box and continue loading applications.</span></span>

## <span data-ttu-id="aff73-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="aff73-123">Related topics</span></span>


[<span data-ttu-id="aff73-124">Application Virtualization Client Management の デスクトップ通知領域を使用する方法</span><span class="sxs-lookup"><span data-stu-id="aff73-124">How to Use the Desktop Notification Area for Application Virtualization Client Management</span></span>](how-to-use-the-desktop-notification-area-for-application-virtualization-client-management.md)

 

 





