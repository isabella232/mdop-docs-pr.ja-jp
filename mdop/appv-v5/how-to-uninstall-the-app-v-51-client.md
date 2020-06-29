---
title: App-V 5.1 Client をアンインストールする方法
description: App-V 5.1 Client をアンインストールする方法
author: dansimp
ms.assetid: 21f2d946-fc9f-4cd3-899b-ac52b3fbc306
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9338bef6b8a3123f9b8f49036427121987e7aa9f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813658"
---
# <span data-ttu-id="f6977-103">App-V 5.1 Client をアンインストールする方法</span><span class="sxs-lookup"><span data-stu-id="f6977-103">How to Uninstall the App-V 5.1 Client</span></span>


<span data-ttu-id="f6977-104">コンピューターから Microsoft Application Virtualization (App-v) 5.1 クライアントをアンインストールするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="f6977-104">Use the following procedure to uninstall the Microsoft Application Virtualization (App-V) 5.1 client from a computer.</span></span> <span data-ttu-id="f6977-105">App-v 5.1 クライアントをアンインストールすると、クライアントを実行しているコンピューターに公開されているすべてのパッケージも削除されます。</span><span class="sxs-lookup"><span data-stu-id="f6977-105">When you uninstall the App-V 5.1 client all packages published to the computer running the client are also removed.</span></span> <span data-ttu-id="f6977-106">アンインストール操作が完了しない場合、パッケージは、App-v 5.1 クライアントを実行しているコンピューターに再公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6977-106">If the uninstall operation does not complete the packages will need to be re-published to the computer running the App-V 5.1 client.</span></span>

**<span data-ttu-id="f6977-107">重要</span><span class="sxs-lookup"><span data-stu-id="f6977-107">Important</span></span>**  
<span data-ttu-id="f6977-108">アンインストール手順を実行する前に、App-v 5.1 クライアントサービスが実行されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6977-108">You should ensure that the App-V 5.1 client service is running prior to performing the uninstall procedure.</span></span>



**<span data-ttu-id="f6977-109">App-v 5.1 クライアントをアンインストールするには</span><span class="sxs-lookup"><span data-stu-id="f6977-109">To uninstall the App-V 5.1 Client</span></span>**

1.  <span data-ttu-id="f6977-110">コントロールパネルで、[**プログラム**]、[プログラムのアンインストール] の順にダブルクリックし、[  /  **Uninstall a Program** **Microsoft Application Virtualization Client**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f6977-110">In Control Panel, double-click **Programs** / **Uninstall a Program**, and then double-click **Microsoft Application Virtualization Client**.</span></span>

2.  <span data-ttu-id="f6977-111">ダイアログボックスが表示されたら、[**はい**] をクリックしてアンインストールプロセスを続行します。</span><span class="sxs-lookup"><span data-stu-id="f6977-111">In the dialog box that appears, click **Yes** to continue with the uninstall process.</span></span>

    **<span data-ttu-id="f6977-112">重要</span><span class="sxs-lookup"><span data-stu-id="f6977-112">Important</span></span>**  
    <span data-ttu-id="f6977-113">アンインストールプロセスをキャンセルまたは中断することはできません。</span><span class="sxs-lookup"><span data-stu-id="f6977-113">The uninstall process cannot be canceled or interrupted.</span></span>



3.  <span data-ttu-id="f6977-114">進行状況バーに残りの時間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6977-114">A progress bar shows the time remaining.</span></span> <span data-ttu-id="f6977-115">この手順が完了したら、アンインストールプロセスを完了するために、関連するすべてのドライバーを停止できるように、コンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6977-115">When this step finishes, you must restart the computer so that all associated drivers can be stopped to complete the uninstall process.</span></span>

    **<span data-ttu-id="f6977-116">注</span><span class="sxs-lookup"><span data-stu-id="f6977-116">Note</span></span>**  
    <span data-ttu-id="f6977-117">コマンドラインを使用して、次のスイッチ ( **/uninstall**) で app-v 5.1 クライアントをアンインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f6977-117">You can also use the command line to uninstall the App-V 5.1 client with the following switch: **/UNINSTALL**.</span></span>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="f6977-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f6977-118">Related topics</span></span>


[<span data-ttu-id="f6977-119">APP-V 5.1 の展開</span><span class="sxs-lookup"><span data-stu-id="f6977-119">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)









