---
title: パッケージのバージョンを削除する方法
description: パッケージのバージョンを削除する方法
author: dansimp
ms.assetid: a55adb9d-ffa6-4df3-a2d1-5e0c73c35e1b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cc77e60ac9745033ae8f074ae71db0cb8517a202
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817564"
---
# <span data-ttu-id="a6c93-103">パッケージのバージョンを削除する方法</span><span class="sxs-lookup"><span data-stu-id="a6c93-103">How to Delete a Package Version</span></span>


<span data-ttu-id="a6c93-104">Application Virtualization Server 管理コンソールで、複数のバージョンがあるパッケージについては、次の手順を使用して1つ以上のバージョンを削除し、残りのバージョンのパッケージを引き続きストリームできます。</span><span class="sxs-lookup"><span data-stu-id="a6c93-104">From the Application Virtualization Server Management Console, for a package that has multiple versions, you can use the following procedure to delete one or more versions and still stream the remaining versions of the package.</span></span> <span data-ttu-id="a6c93-105">この操作を行うと、サーバー上のファイルをより効率的に管理したり、古いバージョンを削除したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a6c93-105">You might do this to more effectively manage files on the server or to remove an obsolete version.</span></span>

<span data-ttu-id="a6c93-106">**注** バージョンの削除を選択すると、クライアントコンピューターが引き続き使用している可能性があることを示す確認ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6c93-106">**Note** When you choose to delete a version, a confirmation box reminds you that client computers might still be using it.</span></span> <span data-ttu-id="a6c93-107">使用中のバージョンを削除する前に、ユーザーにアプリケーションを終了してアンロードするように指示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6c93-107">You should advise users to exit and unload any applications before you remove a version that is in use.</span></span>

 

**<span data-ttu-id="a6c93-108">パッケージバージョンを削除するには</span><span class="sxs-lookup"><span data-stu-id="a6c93-108">To delete a package version</span></span>**

1.  <span data-ttu-id="a6c93-109">Application Virtualization Server 管理コンソールの左側のパネルで、[**パッケージ**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="a6c93-109">In the left panel of the Application Virtualization Server Management Console, expand **Packages**.</span></span>

2.  <span data-ttu-id="a6c93-110">削除するバージョンが含まれているパッケージをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6c93-110">Click the package that contains the version you want to delete.</span></span>

3.  <span data-ttu-id="a6c93-111">中央のウィンドウで、削除するパッケージのバージョンを右クリックし、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6c93-111">In the center pane, right-click the version of the package you want to delete and choose **Delete**.</span></span>

4.  <span data-ttu-id="a6c93-112">確認ウィンドウを読み、[**はい**] をクリックして操作を完了します。</span><span class="sxs-lookup"><span data-stu-id="a6c93-112">Read the confirmation window, and click **Yes** to complete the action.</span></span>

    <span data-ttu-id="a6c93-113">**注** ユーザーが切断された操作を実行している場合は、次回サーバーに接続するときに、そのユーザーのアプリケーションは新しいバージョンに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="a6c93-113">**Note** If you have users in disconnected operation, their applications will be replaced with the new versions the next time they connect to the servers.</span></span> <span data-ttu-id="a6c93-114">すべてのユーザーがアプリケーションを更新したことを確認したら、古いバージョンを削除できます。</span><span class="sxs-lookup"><span data-stu-id="a6c93-114">After you are sure all users have updated applications, you can delete old versions.</span></span>

     

## <span data-ttu-id="a6c93-115">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a6c93-115">Related topics</span></span>


[<span data-ttu-id="a6c93-116">パッケージを削除する方法</span><span class="sxs-lookup"><span data-stu-id="a6c93-116">How to Delete a Package</span></span>](how-to-delete-a-packageserver.md)

[<span data-ttu-id="a6c93-117">サーバー管理コンソールでパッケージを管理する方法</span><span class="sxs-lookup"><span data-stu-id="a6c93-117">How to Manage Packages in the Server Management Console</span></span>](how-to-manage-packages-in-the-server-management-console.md)

 

 





