---
title: コマンド ラインを使用してパッケージを削除する方法
description: コマンド ラインを使用してパッケージを削除する方法
author: dansimp
ms.assetid: 47697ec7-20e5-4258-8865-a0a710d41d5a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b282830802f34bfb0670ddfdb8e2852d3559e3f7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816824"
---
# <span data-ttu-id="5e402-103">コマンド ラインを使用してパッケージを削除する方法</span><span class="sxs-lookup"><span data-stu-id="5e402-103">How to Remove a Package by Using the Command Line</span></span>


<span data-ttu-id="5e402-104">次のコマンドラインの手順を使用して、特定のコンピューター上の Application Virtualization (App-v) クライアントから仮想アプリケーションパッケージを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="5e402-104">You can use the following command-line procedures to delete a virtual application package from the Application Virtualization (App-V) Client on a specific computer.</span></span>

**<span data-ttu-id="5e402-105">仮想アプリケーションパッケージをすべてのユーザー用に削除するには</span><span class="sxs-lookup"><span data-stu-id="5e402-105">To delete a virtual application package for all users</span></span>**

-   <span data-ttu-id="5e402-106">/グローバルスイッチを使用して、パッケージをすべてのユーザーに対して以前に追加した場合は、次のコマンドを使用して、パッケージとグローバルファイルの種類とショートカットを削除します。</span><span class="sxs-lookup"><span data-stu-id="5e402-106">If the package was previously added for all users by using the /GLOBAL switch, use the following command to delete the package and the global file types and shortcuts.</span></span> <span data-ttu-id="5e402-107">管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="5e402-107">Administrator rights are required.</span></span> <span data-ttu-id="5e402-108">この場合、このコマンドでは常にパッケージのグローバル削除が実行されるため、/グローバルスイッチは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5e402-108">The /GLOBAL switch is not needed in this case because the command always performs a global deletion of the package.</span></span>

    `SFTMIME DELETE PACKAGE:”name”`

**<span data-ttu-id="5e402-109">個々のユーザー用に以前に追加されたパッケージを削除するには</span><span class="sxs-lookup"><span data-stu-id="5e402-109">To delete a package previously added for individual users</span></span>**

1.  <span data-ttu-id="5e402-110">パッケージが個別のユーザー用に既に追加されている場合は、いくつかのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="5e402-110">If the package was previously added for individual users, you have several options.</span></span>

    <span data-ttu-id="5e402-111">パッケージが公開されたユーザーアカウントの下で、次のコマンドを1回実行します。</span><span class="sxs-lookup"><span data-stu-id="5e402-111">Run the following command once under the user account of each person the package was published to.</span></span> <span data-ttu-id="5e402-112">これにより、ユーザーが別のコンピューターに移動した場合に、そのアプリケーションへのアクセスが拒否されます。</span><span class="sxs-lookup"><span data-stu-id="5e402-112">This denies the user access to the applications if they roam to another computer.</span></span> <span data-ttu-id="5e402-113">この操作により、特定のユーザーの設定、ショートカット、ファイルの種類がプロファイルから削除され、ユーザーのコンテキストでバックグラウンドの読み込みが停止されます。</span><span class="sxs-lookup"><span data-stu-id="5e402-113">It deletes the specific user’s settings, shortcuts, and file types from the profile, and it stops background loads under the user’s context.</span></span>

    `SFTMIME UNPUBLISH PACKAGE:”name”`

2.  <span data-ttu-id="5e402-114">または、パッケージが公開された各ユーザーのユーザーアカウントで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e402-114">Alternatively, run the following command under the user account of each person the package was published to.</span></span>

    `SFTMIME UNPUBLISH PACKAGE:”name”`

    <span data-ttu-id="5e402-115">次に、パッケージに対してこのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5e402-115">Then run this command for the package.</span></span>

    `SFTMIME DELETE PACKAGE:”name”`

    <span data-ttu-id="5e402-116">これにより、パッケージが完全に削除され、すべてのユーザー設定、ショートカット、ファイルの種類がプロファイルから削除されます。</span><span class="sxs-lookup"><span data-stu-id="5e402-116">This completely removes the package, and it deletes all user settings, shortcuts, and file types from their profiles.</span></span> <span data-ttu-id="5e402-117">後でパッケージをもう一度追加する場合は、ユーザーは設定をもう一度指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e402-117">If the package is subsequently re-added, the users will have to specify their settings again.</span></span> <span data-ttu-id="5e402-118">このコマンドを実行するには、"アプリケーションの削除" (**Deleteapp**) アクセス許可のみが必要です。</span><span class="sxs-lookup"><span data-stu-id="5e402-118">Only “Delete applications” (**DeleteApp**) permission is needed to run this command.</span></span>

3.  <span data-ttu-id="5e402-119">第3の選択肢として、[**パッケージの発行を取り消す**] コマンドを使わずに、[パッケージの**削除**] コマンドを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="5e402-119">As a third alternative, you can simply run the **DELETE PACKAGE** command without using the **UNPUBLISH PACKAGE** command.</span></span> <span data-ttu-id="5e402-120">この場合、各ユーザーのファイルの種類とショートカットは、削除されるのではなく非表示になり、ユーザー設定は保持されます。</span><span class="sxs-lookup"><span data-stu-id="5e402-120">In this case, file types and shortcuts for each user are hidden rather than deleted, and the user settings are retained.</span></span> <span data-ttu-id="5e402-121">つまり、その後、そのユーザーに対してパッケージを再度追加すると、ファイルの種類とショートカットが復元され、ユーザー設定が再適用されます。</span><span class="sxs-lookup"><span data-stu-id="5e402-121">This means that if the package is subsequently re-added for the user, the file types and shortcuts are restored, and the user settings are reapplied.</span></span>

## <span data-ttu-id="5e402-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5e402-122">Related topics</span></span>


[<span data-ttu-id="5e402-123">コマンド ラインを使用してパッケージを追加する方法</span><span class="sxs-lookup"><span data-stu-id="5e402-123">How to Add a Package by Using the Command Line</span></span>](how-to-add-a-package-by-using-the-command-line.md)

[<span data-ttu-id="5e402-124">コマンド ラインを使用してすべての仮想アプリケーションを削除する方法</span><span class="sxs-lookup"><span data-stu-id="5e402-124">How to Delete All Virtual Applications by Using the Command Line</span></span>](how-to-delete-all-virtual-applications-by-using-the-command-line.md)

 

 





