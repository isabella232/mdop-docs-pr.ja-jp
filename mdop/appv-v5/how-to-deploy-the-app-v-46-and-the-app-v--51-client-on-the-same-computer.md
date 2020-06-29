---
title: 同じコンピューター上に App-v 4.6 と App-v 5.1 クライアントを展開する方法
description: 同じコンピューター上に App-v 4.6 と App-v 5.1 クライアントを展開する方法
ms.assetid: 498d50c7-f13d-4fbb-8ea1-b959ade26fdf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 354db96223e623a7cd0416cb49ad67eb4d8f7162
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814171"
---
# <span data-ttu-id="02357-103">同じコンピューター上に App-v 4.6 と App-v 5.1 クライアントを展開する方法</span><span class="sxs-lookup"><span data-stu-id="02357-103">How to Deploy the App-V 4.6 and the App-V 5.1 Client on the Same Computer</span></span>

<span data-ttu-id="02357-104">**注:** App-v 4.6 は、メインストリームサポートを終了しました。</span><span class="sxs-lookup"><span data-stu-id="02357-104">**Note:** App-V 4.6 has exited Mainstream support.</span></span>

<span data-ttu-id="02357-105">Microsoft Application Virtualization (App-v) 5.1 クライアントをインストールするには、次の情報を使用します (推奨されるのは、最新の Service Pack およびホットフィックスを使用します)。また、同じコンピューター上の app-v 4.6 SP2 クライアントまたは app-v 4.6 S3 クライアントをインストールする場合もあります。</span><span class="sxs-lookup"><span data-stu-id="02357-105">Use the following information to install the Microsoft Application Virtualization (App-V) 5.1 client (preferably, with the latest Service Packs and hotfixes) and the App-V 4.6SP2 client or the App-V 4.6S3 client on the same computer.</span></span> <span data-ttu-id="02357-106">サポートされているバージョン、要件、およびその他の計画情報については、「[以前のバージョンの app-v からの移行を計画](planning-for-migrating-from-a-previous-version-of-app-v51.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02357-106">For supported versions, requirements, and other planning information, see [Planning for Migrating from a Previous Version of App-V](planning-for-migrating-from-a-previous-version-of-app-v51.md).</span></span>

**<span data-ttu-id="02357-107">同じコンピューターに App-v 5.1 クライアントと App-v 4.6 クライアントを展開するには</span><span class="sxs-lookup"><span data-stu-id="02357-107">To deploy the App-V 5.1 client and App-V 4.6 client on the same computer</span></span>**

1.  <span data-ttu-id="02357-108">App-v 4.6 を実行しているコンピューターに、次のバージョンの App-v クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="02357-108">Install the following version of the App-V client on the computer that is running App-V 4.6.</span></span>

    -   [<span data-ttu-id="02357-109">Microsoft Application Virtualization 4.6 Service Pack 3</span><span class="sxs-lookup"><span data-stu-id="02357-109">Microsoft Application Virtualization 4.6 Service Pack 3</span></span>](https://www.microsoft.com/download/details.aspx?id=41187)

2.  <span data-ttu-id="02357-110">App-v 4.6 SP3 バージョンのクライアントを実行しているコンピューターに、App-v 5.1 クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="02357-110">Install the App-V 5.1 client on the computer that is running the App-V 4.6 SP3 version of the client.</span></span> <span data-ttu-id="02357-111">最善の結果を得るために、利用可能なすべての更新プログラムを、App-v 5.1 クライアントにインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="02357-111">For best results, we recommend that you install all available updates to the App-V 5.1 client.</span></span>

3.  <span data-ttu-id="02357-112">パッケージを段階的に変換または再シーケンスします。</span><span class="sxs-lookup"><span data-stu-id="02357-112">Convert or re-sequence the packages gradually.</span></span>

    -   <span data-ttu-id="02357-113">パッケージを変換するには、App-v 5.1 パッケージコンバーターを使用し、必要なパッケージを App-v 5.1 (**appv**) ファイル形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="02357-113">To convert the packages, use the App-V 5.1 package converter and convert the required packages to the App-V 5.1 (**.appv**) file format.</span></span>

    -   <span data-ttu-id="02357-114">パッケージの順序を変更するには、最善の結果を得るために、最新バージョンの Sequencer の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="02357-114">To re-sequence the packages, consider using the latest version of the Sequencer for best results.</span></span>

    <span data-ttu-id="02357-115">パッケージの発行の詳細については、「[管理コンソールを使用してパッケージを公開する方法](how-to-publish-a-package-by-using-the-management-console-51.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02357-115">For more information about publishing packages, see [How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-51.md).</span></span>

4.  <span data-ttu-id="02357-116">クライアントコンピューターにパッケージを展開します。</span><span class="sxs-lookup"><span data-stu-id="02357-116">Deploy packages to the client computers.</span></span>

5.  <span data-ttu-id="02357-117">必要に応じて、拡張点を変換します。</span><span class="sxs-lookup"><span data-stu-id="02357-117">Convert extension points, as needed.</span></span> <span data-ttu-id="02357-118">詳しくは、次のリソースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="02357-118">For more information, see the following resources:</span></span>

    -   [<span data-ttu-id="02357-119">特定のコンピューター上の全ユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.1 パッケージに移行する方法</span><span class="sxs-lookup"><span data-stu-id="02357-119">How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.1 Package for All Users on a Specific Computer</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-51-package-for-all-users-on-a-specific-computer.md)

    -   [<span data-ttu-id="02357-120">特定のユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.1 パッケージに移行する方法</span><span class="sxs-lookup"><span data-stu-id="02357-120">How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.1 for a Specific User</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-51-for-a-specific-user.md)

    -   [<span data-ttu-id="02357-121">以前のバージョンの APP-V で作成されたパッケージを変換する方法</span><span class="sxs-lookup"><span data-stu-id="02357-121">How to Convert a Package Created in a Previous Version of App-V</span></span>](how-to-convert-a-package-created-in-a-previous-version-of-app-v51.md)

6.  <span data-ttu-id="02357-122">App-v 5.1 パッケージが正常に処理されたことをテストし、4.6 パッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="02357-122">Test that your App-V 5.1 packages are successful, and then remove the 4.6 packages.</span></span> <span data-ttu-id="02357-123">クライアントコンピューターのユーザーの状態を確認するには、[ユーザーエクスペリエンスの仮想化](https://technet.microsoft.com/library/dn458947.aspx)または他のユーザー環境管理ツールを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="02357-123">To check the user state of your client computers, we recommend that you use [User Experience Virtualization](https://technet.microsoft.com/library/dn458947.aspx) or another user environment management tool.</span></span>

    <span data-ttu-id="02357-124">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="02357-124">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="02357-125">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="02357-125">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="02357-126">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="02357-126">Got an App-V issue?</span></span>** <span data-ttu-id="02357-127">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="02357-127">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="02357-128">関連トピック</span><span class="sxs-lookup"><span data-stu-id="02357-128">Related topics</span></span>


[<span data-ttu-id="02357-129">APP-V の以前のバージョンからの移行計画</span><span class="sxs-lookup"><span data-stu-id="02357-129">Planning for Migrating from a Previous Version of App-V</span></span>](planning-for-migrating-from-a-previous-version-of-app-v51.md)

[<span data-ttu-id="02357-130">App-V 5.1 Sequencer および Client の展開</span><span class="sxs-lookup"><span data-stu-id="02357-130">Deploying the App-V 5.1 Sequencer and Client</span></span>](deploying-the-app-v-51-sequencer-and-client.md)

 

 





