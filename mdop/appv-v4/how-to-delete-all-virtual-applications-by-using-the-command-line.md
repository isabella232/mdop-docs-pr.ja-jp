---
title: コマンド ラインを使用してすべての仮想アプリケーションを削除する方法
description: コマンド ラインを使用してすべての仮想アプリケーションを削除する方法
author: dansimp
ms.assetid: bfe13b5c-825a-4eb1-a979-6c4b8d8b2a9c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 55c809df31fa5c19f2f1a56c143d492b092156c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817537"
---
# <span data-ttu-id="08a1a-103">コマンド ラインを使用してすべての仮想アプリケーションを削除する方法</span><span class="sxs-lookup"><span data-stu-id="08a1a-103">How to Delete All Virtual Applications by Using the Command Line</span></span>


<span data-ttu-id="08a1a-104">特定のコンピューターからすべての仮想アプリケーションを削除するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="08a1a-104">You can use the following procedure to delete all virtual applications from a specific computer.</span></span>

<span data-ttu-id="08a1a-105">**注** すべてのアプリケーションがパッケージから削除されると、Application Virtualization (App-v) クライアントもパッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="08a1a-105">**Note** When all applications are deleted from a package, the Application Virtualization (App-V) Client also deletes the package.</span></span>

 

**<span data-ttu-id="08a1a-106">すべてのアプリケーションを削除するには</span><span class="sxs-lookup"><span data-stu-id="08a1a-106">To delete all applications</span></span>**

-   <span data-ttu-id="08a1a-107">次のコマンドを実行して、コマンドが実行されているユーザーアカウントのすべてのアプリケーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="08a1a-107">Run the following command to delete all applications for the user account under which the command is run.</span></span> <span data-ttu-id="08a1a-108">オプションの/グローバルスイッチを指定してコマンドを実行すると、管理者権限を持つアカウントを使用して、すべてのユーザーのアプリケーションが削除されます。</span><span class="sxs-lookup"><span data-stu-id="08a1a-108">If you run the command with the optional /GLOBAL switch, using an account with administrative rights, all applications are deleted for all users.</span></span>

    `SFTMIME DELETE OBJ:APP [/GLOBAL]`

    <span data-ttu-id="08a1a-109">**注** すべてのアプリケーションがパッケージから削除されると、Application Virtualization (App-v) クライアントもパッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="08a1a-109">**Note** When all applications are deleted from a package, the Application Virtualization (App-V) Client also deletes the package.</span></span>

     

## <span data-ttu-id="08a1a-110">関連トピック</span><span class="sxs-lookup"><span data-stu-id="08a1a-110">Related topics</span></span>


[<span data-ttu-id="08a1a-111">コマンド ラインを使用してパッケージを追加する方法</span><span class="sxs-lookup"><span data-stu-id="08a1a-111">How to Add a Package by Using the Command Line</span></span>](how-to-add-a-package-by-using-the-command-line.md)

[<span data-ttu-id="08a1a-112">コマンド ラインを使用してパッケージを削除する方法</span><span class="sxs-lookup"><span data-stu-id="08a1a-112">How to Remove a Package by Using the Command Line</span></span>](how-to-remove-a-package-by-using-the-command-line.md)

 

 





