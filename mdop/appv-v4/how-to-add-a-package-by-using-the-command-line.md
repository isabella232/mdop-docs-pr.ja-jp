---
title: コマンド ラインを使用してパッケージを追加する方法
description: コマンド ラインを使用してパッケージを追加する方法
author: dansimp
ms.assetid: e75af49e-811a-407a-a7f0-6de8562b9188
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ab418017a075300f308d4ef4c6eceb4f623a05c7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821407"
---
# <span data-ttu-id="4e306-103">コマンド ラインを使用してパッケージを追加する方法</span><span class="sxs-lookup"><span data-stu-id="4e306-103">How to Add a Package by Using the Command Line</span></span>


<span data-ttu-id="4e306-104">次の手順では、特定のコンピューター上の Application Virtualization (App-v) クライアントに仮想アプリケーションパッケージを追加するために必要な手順を示します。</span><span class="sxs-lookup"><span data-stu-id="4e306-104">The following procedures list the steps that are necessary to add a virtual application package to the Application Virtualization (App-V) Client on a specific computer.</span></span>

**<span data-ttu-id="4e306-105">特定のユーザーの仮想アプリケーションパッケージを追加するには</span><span class="sxs-lookup"><span data-stu-id="4e306-105">To add a virtual application package for a specific user</span></span>**

-   <span data-ttu-id="4e306-106">パッケージを取得するユーザーのユーザーアカウントの下で、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4e306-106">Run the following command under the user account of the person who is to get the package.</span></span> <span data-ttu-id="4e306-107">このコマンドによって、そのユーザーのパッケージが追加され、公開されます。</span><span class="sxs-lookup"><span data-stu-id="4e306-107">The command adds and publishes the package for that user.</span></span>

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path>`

**<span data-ttu-id="4e306-108">仮想アプリケーションパッケージをすべてのユーザー用に追加するには</span><span class="sxs-lookup"><span data-stu-id="4e306-108">To add a virtual application package for all users</span></span>**

-   <span data-ttu-id="4e306-109">管理者権限を持つアカウントで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4e306-109">Run the following command under an account that has administrator rights.</span></span> <span data-ttu-id="4e306-110">コンピューター上のすべてのユーザーに対してパッケージが追加され、公開されます。</span><span class="sxs-lookup"><span data-stu-id="4e306-110">The package is added and published for all users on the computer.</span></span>

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path> /GLOBAL`

**<span data-ttu-id="4e306-111">電子ソフトウェア配布システムを使用してパッケージを追加するには</span><span class="sxs-lookup"><span data-stu-id="4e306-111">To add a package using an electronic software distribution system</span></span>**

1.  <span data-ttu-id="4e306-112">コンピューターの**システム**アカウントの下でコマンドを実行する電子ソフトウェア配布システムを使用している場合、/グローバルスイッチを使用しない限り、パッケージはそのアカウントに対してのみ公開されます。</span><span class="sxs-lookup"><span data-stu-id="4e306-112">If you are using an electronic software distribution system that runs the commands under the computer’s **SYSTEM** account, the package is published for that account only, unless you use the /GLOBAL switch.</span></span> <span data-ttu-id="4e306-113">次のコマンドを実行して、コンピューター上のすべてのユーザーに対してパッケージを追加し、公開します。</span><span class="sxs-lookup"><span data-stu-id="4e306-113">Run the following command to add and publish the package for all users on the computer:</span></span>

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path> /GLOBAL`

2.  

    <span data-ttu-id="4e306-114">特定のユーザーに対してのみパッケージを追加する場合は、[**パッケージの追加**] を実行し、各ユーザーのユーザーアカウントの下で次の [パッケージの**発行**] コマンドを実行して、各ユーザーのパッケージを明示的に公開します。</span><span class="sxs-lookup"><span data-stu-id="4e306-114">If you want to add the package for specific users only, run the **ADD PACKAGE** command, and then explicitly publish the package for each user by running the following **PUBLISH PACKAGE** command under each person’s user account:</span></span>

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path>`

    `SFTMIME PUBLISH PACKAGE:”name” /MANIFEST <manifest-path>`

    <span data-ttu-id="4e306-115">グローバルパラメーターを指定せずにパッケージを発行すると、ユーザーはパッケージ内のアプリケーションにアクセスできるようになり、マニフェストに記載されているファイルの種類とショートカットがユーザーのプロファイルに発行されます。</span><span class="sxs-lookup"><span data-stu-id="4e306-115">Publishing the package without the GLOBAL parameter grants the user access to the applications in the package and publishes the file types and shortcuts that are listed in the manifest to the user’s profile.</span></span> <span data-ttu-id="4e306-116">必要なアクセス許可は、"ファイルの種類の関連付けを管理する" (**Managetypes**) と "ショートカットの公開" (**publishshortcut**) です。</span><span class="sxs-lookup"><span data-stu-id="4e306-116">Permissions required are “Manage file type associations” (**ManageTypes**) and “Publish shortcuts” (**PublishShortcut**).</span></span>

## <span data-ttu-id="4e306-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4e306-117">Related topics</span></span>


[<span data-ttu-id="4e306-118">コマンド ラインを使用してすべての仮想アプリケーションを削除する方法</span><span class="sxs-lookup"><span data-stu-id="4e306-118">How to Delete All Virtual Applications by Using the Command Line</span></span>](how-to-delete-all-virtual-applications-by-using-the-command-line.md)

[<span data-ttu-id="4e306-119">コマンド ラインを使用してパッケージを削除する方法</span><span class="sxs-lookup"><span data-stu-id="4e306-119">How to Remove a Package by Using the Command Line</span></span>](how-to-remove-a-package-by-using-the-command-line.md)

 

 





