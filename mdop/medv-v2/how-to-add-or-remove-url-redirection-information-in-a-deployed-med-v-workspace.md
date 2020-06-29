---
title: 展開された MED-V ワークスペースの URL リダイレクトの情報を追加または削除する方法
description: 展開された MED-V ワークスペースの URL リダイレクトの情報を追加または削除する方法
author: dansimp
ms.assetid: bf55848d-bf77-452e-aaa5-4dd4868ff5bd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: f0892b16bfc10e6b3f28fe99c51c2c5cedb73d7f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826444"
---
# <span data-ttu-id="bf6f9-103">展開された MED-V ワークスペースの URL リダイレクトの情報を追加または削除する方法</span><span class="sxs-lookup"><span data-stu-id="bf6f9-103">How to Add or Remove URL Redirection Information in a Deployed MED-V Workspace</span></span>


<span data-ttu-id="bf6f9-104">展開された MED-V ワークスペースの URL リダイレクション情報を編集するには、グループポリシーを使ってシステムレジストリを更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bf6f9-104">To edit URL redirection information in a deployed MED-V workspace, we recommend that you update the system registry by using Group Policy.</span></span> <span data-ttu-id="bf6f9-105">お勧めしませんが、更新された URL リダイレクション情報を使用して、MED-V ワークスペースを再構築および再展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="bf6f9-105">Although we do not recommend it, you can also rebuild and redeploy the MED-V workspace with the updated URL redirection information.</span></span>

<span data-ttu-id="bf6f9-106">通常、レジストリキーは次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="bf6f9-106">The registry key is usually located at:</span></span>

<span data-ttu-id="bf6f9-107">Computer¥¥ \ Key\ _LOCAL \ _MACHINE ¥¥¥¥¥¥¥¥¥ |</span><span class="sxs-lookup"><span data-stu-id="bf6f9-107">Computer\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MEDV\\v2\\UserExperience</span></span>

<span data-ttu-id="bf6f9-108">次の複数文字列値が存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf6f9-108">The following multi-string value must be present:</span></span> `RedirectUrls`

<span data-ttu-id="bf6f9-109">の値のデータ `RedirectUrls` は、 **Med-v ワークスペースパッケージャー**を使って med-v ワークスペースパッケージをビルドしたときに、リダイレクト用に指定したすべての url の一覧です。</span><span class="sxs-lookup"><span data-stu-id="bf6f9-109">The value data for `RedirectUrls` is a list of all of the URLs that you specified for redirection when you built the MED-V workspace package by using the **MED-V Workspace Packager**.</span></span> <span data-ttu-id="bf6f9-110">詳細については、「 [Med-v ワークスペースパッケージを作成する](create-a-med-v-workspace-package.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf6f9-110">For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).</span></span>

<span data-ttu-id="bf6f9-111">次のいずれかのタスクを実行して、URL リダイレクション情報を追加および削除できます。</span><span class="sxs-lookup"><span data-stu-id="bf6f9-111">You can add and remove URL redirection information by performing one of the following tasks:</span></span>

-   [<span data-ttu-id="bf6f9-112">URL リダイレクションレジストリキーを編集して、グループポリシーを使用して展開する</span><span class="sxs-lookup"><span data-stu-id="bf6f9-112">Edit the URL Redirection Registry Key and Deploy Using Group Policy</span></span>](#bkmk-editreg)

-   [<span data-ttu-id="bf6f9-113">URL リダイレクションテキストファイルを編集して、MED-V ワークスペースを再構築する</span><span class="sxs-lookup"><span data-stu-id="bf6f9-113">Edit the URL Redirection Text File and Rebuild the MED-V Workspace</span></span>](#bkmk-edittext)

<a href="" id="bkmk-editreg"></a>**<span data-ttu-id="bf6f9-114">グループポリシーを使用して URL リダイレクション情報を更新するには</span><span class="sxs-lookup"><span data-stu-id="bf6f9-114">To update URL Redirection information by using Group Policy</span></span>**

1.  <span data-ttu-id="bf6f9-115">という名前のレジストリキーの複数文字列値を編集し `RedirectUrls` ます。</span><span class="sxs-lookup"><span data-stu-id="bf6f9-115">Edit the registry key multi-string value that is named `RedirectUrls`.</span></span> <span data-ttu-id="bf6f9-116">この値は、通常、次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="bf6f9-116">This value is typically located at:</span></span>

    <span data-ttu-id="bf6f9-117">Computer¥¥ \ Key\ _LOCAL \ _MACHINE ¥¥¥¥¥¥¥¥¥ |</span><span class="sxs-lookup"><span data-stu-id="bf6f9-117">Computer\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MEDV\\v2\\UserExperience</span></span>

    <span data-ttu-id="bf6f9-118">レジストリキーに Url を追加する場合は、MED-V ワークスペースパッケージを作成するときに必要となりますが、1行あたりに1つの Url を入力します。</span><span class="sxs-lookup"><span data-stu-id="bf6f9-118">If you are adding URLs to the registry key, enter them one per line, as was required when you built the MED-V workspace package.</span></span> <span data-ttu-id="bf6f9-119">詳細については、「 [Med-v ワークスペースパッケージを作成する](create-a-med-v-workspace-package.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf6f9-119">For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).</span></span>

2.  <span data-ttu-id="bf6f9-120">グループポリシーを使用して、更新されたレジストリキーを展開します。</span><span class="sxs-lookup"><span data-stu-id="bf6f9-120">Deploy the updated registry key by using Group Policy.</span></span> <span data-ttu-id="bf6f9-121">グループポリシーの使用方法の詳細については、「[グループポリシーソフトウェアのインストール](https://go.microsoft.com/fwlink/?LinkId=195931)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=195931) 。</span><span class="sxs-lookup"><span data-stu-id="bf6f9-121">For more information about how to use Group Policy, see [Group Policy Software Installation](https://go.microsoft.com/fwlink/?LinkId=195931) (https://go.microsoft.com/fwlink/?LinkId=195931).</span></span>

<span data-ttu-id="bf6f9-122">**注** URL リダイレクション情報を編集するこの方法は、MED-V のベストプラクティスです。</span><span class="sxs-lookup"><span data-stu-id="bf6f9-122">**Note** This method of editing URL redirection information is a MED-V best practice.</span></span>

 

<a href="" id="bkmk-edittext"></a>**<span data-ttu-id="bf6f9-123">更新された URL テキストファイルを使用して、MED-V ワークスペースを再構築するには</span><span class="sxs-lookup"><span data-stu-id="bf6f9-123">To rebuild the MED-V workspace by using an updated URL text file</span></span>**

-   <span data-ttu-id="bf6f9-124">リダイレクトリストから Url を追加したり削除したりするもう1つの方法は、URL リダイレクションテキストファイルを更新し、それを使って新しい MED-V ワークスペースを構築することです。</span><span class="sxs-lookup"><span data-stu-id="bf6f9-124">Another method of adding and removing URLs from the redirection list is to update the URL redirection text file and then use it to build a new MED-V workspace.</span></span> <span data-ttu-id="bf6f9-125">次に、ESD システムなどの展開の標準的なプロセスを使用して、以前と同様に MED-V ワークスペースを再展開することができます。</span><span class="sxs-lookup"><span data-stu-id="bf6f9-125">You can then redeploy the MED-V workspace as before, by using your standard process of deployment, such as an ESD system.</span></span>

    <span data-ttu-id="bf6f9-126">**重要** この方法では、URL リダイレクション情報を編集することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="bf6f9-126">**Important** We do not recommend this method of editing URL redirection information.</span></span> <span data-ttu-id="bf6f9-127">さらに、MED-V ワークスペースをエンタープライズに再展開する場合は、最初にセットアップをもう一度実行する必要があります。仮想マシンに保存されているデータはすべて失われます。</span><span class="sxs-lookup"><span data-stu-id="bf6f9-127">In addition, any time that you redeploy the MED-V workspace back out to your enterprise, first time setup must run again, and any data saved in the virtual machine is lost.</span></span>

     

## <span data-ttu-id="bf6f9-128">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bf6f9-128">Related topics</span></span>


[<span data-ttu-id="bf6f9-129">URL のリダイレクトをテストする方法</span><span class="sxs-lookup"><span data-stu-id="bf6f9-129">How to Test URL Redirection</span></span>](how-to-test-url-redirection.md)

[<span data-ttu-id="bf6f9-130">MED-V ワークスペースに展開されたアプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="bf6f9-130">Managing Applications Deployed to MED-V Workspaces</span></span>](managing-applications-deployed-to-med-v-workspaces.md)

[<span data-ttu-id="bf6f9-131">MED-V ワークスペース パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="bf6f9-131">Create a MED-V Workspace Package</span></span>](create-a-med-v-workspace-package.md)

 

 





