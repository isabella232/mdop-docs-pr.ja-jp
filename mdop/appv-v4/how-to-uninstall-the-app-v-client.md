---
title: App-V Client をアンインストールする方法
description: App-V Client をアンインストールする方法
author: dansimp
ms.assetid: 07591270-9651-4bb5-a5b3-e0fc009bd9e2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: acb3f53b42027ff2c1b84fd2ab2bdde3c52f96de
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816524"
---
# <span data-ttu-id="bcd43-103">App-V Client をアンインストールする方法</span><span class="sxs-lookup"><span data-stu-id="bcd43-103">How to Uninstall the App-V Client</span></span>


<span data-ttu-id="bcd43-104">次の手順を使用して、コンピューターからアプリケーションの仮想化クライアントをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="bcd43-104">Use the following procedure to uninstall the Application Virtualization Client from the computer.</span></span>

**<span data-ttu-id="bcd43-105">Application Virtualization デスクトップクライアントをアンインストールするには</span><span class="sxs-lookup"><span data-stu-id="bcd43-105">To uninstall the Application Virtualization Desktop Client</span></span>**

1.  <span data-ttu-id="bcd43-106">コントロールパネルで、[プログラムの**追加と削除**] (または Windows Vista、[**プログラムと機能**]) をダブルクリックして、[ **Microsoft Application Virtualization Desktop Client**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="bcd43-106">In Control Panel, double-click **Add or Remove Programs** (or in Windows Vista, **Programs and Features**), and then double-click **Microsoft Application Virtualization Desktop Client**.</span></span>

2.  <span data-ttu-id="bcd43-107">ダイアログボックスが表示されたら、[**はい**] をクリックしてアンインストールプロセスを続行します。</span><span class="sxs-lookup"><span data-stu-id="bcd43-107">In the dialog box that appears, click **Yes** to continue with the uninstall process.</span></span>

    <span data-ttu-id="bcd43-108">**重要** アンインストールプロセスをキャンセルまたは中断することはできません。</span><span class="sxs-lookup"><span data-stu-id="bcd43-108">**Important** The uninstall process cannot be canceled or interrupted.</span></span>

     

3.  <span data-ttu-id="bcd43-109">続行する前に Microsoft Application Virtualization Client Tray アプリケーションを閉じておく必要があることを示すメッセージが表示されたら、通知領域の [App-V] アイコンを右クリックし、[**終了**] を選択してアプリケーションを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bcd43-109">When a message stating that the Microsoft Application Virtualization Client Tray application must be closed before continuing appears, right-click the App-V icon in the notification area and select **Exit** to close the application.</span></span> <span data-ttu-id="bcd43-110">次に、[**再試行**] をクリックして、アンインストールプロセスを続行します。</span><span class="sxs-lookup"><span data-stu-id="bcd43-110">Then click **Retry** to continue with the uninstall process.</span></span>

    <span data-ttu-id="bcd43-111">**重要** 1つまたは複数の仮想アプリケーションが使用されていることを示すメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="bcd43-111">**Important** You might see a message stating that one or more virtual applications are in use.</span></span> <span data-ttu-id="bcd43-112">続行する前に、開いているアプリケーションを閉じてデータを保存します。</span><span class="sxs-lookup"><span data-stu-id="bcd43-112">Close any open applications and save your data before you continue.</span></span> <span data-ttu-id="bcd43-113">[ **OK** ] をクリックして、アンインストールプロセスを続行します。</span><span class="sxs-lookup"><span data-stu-id="bcd43-113">Then click **OK** to continue with the uninstall process.</span></span>

     

4.  <span data-ttu-id="bcd43-114">進行状況バーに残りの時間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bcd43-114">A progress bar shows the time remaining.</span></span> <span data-ttu-id="bcd43-115">この手順が完了したら、アンインストールプロセスを完了するために、関連するすべてのドライバーを停止できるように、コンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcd43-115">When this step finishes, you must restart the computer so that all associated drivers can be stopped to complete the uninstall process.</span></span>

    <span data-ttu-id="bcd43-116">**注** アンインストールプロセスが完了すると、次のレジストリキーが保持されます。</span><span class="sxs-lookup"><span data-stu-id="bcd43-116">**Note** The following registry keys remain after the uninstall process is complete:</span></span>

    -   <span data-ttu-id="bcd43-117">HKEY \ _LOCAL \ _MACHINE ¥¥¥¥¥¥ | |</span><span class="sxs-lookup"><span data-stu-id="bcd43-117">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid</span></span>

    -   <span data-ttu-id="bcd43-118">HKEY \ _LOCAL \ _MACHINE ¥¥¥¥¥¥¥¥¥¥¥¥ # softgrid¥5</span><span class="sxs-lookup"><span data-stu-id="bcd43-118">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5</span></span>

    -   <span data-ttu-id="bcd43-119">HKEY \ _LOCAL \ _MACHINE \ ソフトウェア \\ wow6432node¥¥ 5Softgrid\\ 4.8 5 \ systemguard "クライアント" = dword: 00000000</span><span class="sxs-lookup"><span data-stu-id="bcd43-119">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard"Client"=dword:00000000</span></span>

    -   <span data-ttu-id="bcd43-120">HKEY \ _LOCAL \ _MACHINE ¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥ |</span><span class="sxs-lookup"><span data-stu-id="bcd43-120">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\SystemGuard\\SecKey</span></span>

     

## <span data-ttu-id="bcd43-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bcd43-121">Related topics</span></span>


[<span data-ttu-id="bcd43-122">コマンド ラインを使用してクライアントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="bcd43-122">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)

[<span data-ttu-id="bcd43-123">Application Virtualization Client を手動でインストールする方法</span><span class="sxs-lookup"><span data-stu-id="bcd43-123">How to Manually Install the Application Virtualization Client</span></span>](how-to-manually-install-the-application-virtualization-client.md)

[<span data-ttu-id="bcd43-124">クライアントで仮想アプリケーションを公開する方法</span><span class="sxs-lookup"><span data-stu-id="bcd43-124">How to Publish a Virtual Application on the Client</span></span>](how-to-publish-a-virtual-application-on-the-client.md)

 

 





