---
title: 同じコンピューター上に App-v 4.6 と App-v 5.0 クライアントを展開する方法
description: 同じコンピューター上に App-v 4.6 と App-v 5.0 クライアントを展開する方法
ms.assetid: 5b7e27e4-4360-464c-b832-f1c7939e5485
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.date: 06/21/2016
ms.openlocfilehash: 38e77ce6ce6c0dba7c67f6c0dfa5c9e263e07e20
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814179"
---
# <span data-ttu-id="b35ba-103">同じコンピューター上に App-v 4.6 と App-v 5.0 クライアントを展開する方法</span><span class="sxs-lookup"><span data-stu-id="b35ba-103">How to Deploy the App-V 4.6 and the App-V 5.0 Client on the Same Computer</span></span>

<span data-ttu-id="b35ba-104">**注:** App-v 4.6 は、メインストリームサポートを終了しました。</span><span class="sxs-lookup"><span data-stu-id="b35ba-104">**Note:** App-V 4.6 has exited Mainstream support.</span></span> <span data-ttu-id="b35ba-105">次の例は、App-v 4.6 SP3 クライアントが既にインストールされていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="b35ba-105">The following assumes that the App-V 4.6 SP3 client is already installed.</span></span>

<span data-ttu-id="b35ba-106">次の情報を使用して、App-v 5.0 クライアント (お勧めの、最新の Service Pack と修正プログラムを含む) と、同じコンピューター上の App-v 4.6 SP3 クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b35ba-106">Use the following information to install the App-V 5.0 client (preferably, with the latest Service Packs and hotfixes) and the App-V 4.6SP3 client on the same computer.</span></span> <span data-ttu-id="b35ba-107">サポートされているバージョン、要件、およびその他の計画情報については、「[以前のバージョンの app-v からの移行を計画](planning-for-migrating-from-a-previous-version-of-app-v.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b35ba-107">For supported versions, requirements, and other planning information, see [Planning for Migrating from a Previous Version of App-V](planning-for-migrating-from-a-previous-version-of-app-v.md).</span></span>

**<span data-ttu-id="b35ba-108">同じコンピューターに App-v 5.0 クライアントと App-v 4.6 クライアントを展開するには</span><span class="sxs-lookup"><span data-stu-id="b35ba-108">To deploy the App-V 5.0 client and App-V 4.6 client on the same computer</span></span>**

1.  <span data-ttu-id="b35ba-109">App-v 4.6 バージョンのクライアントが実行されているコンピューターに、App-v 5.0 SP3 クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b35ba-109">Install the App-V 5.0 SP3 client on the computer that is running the App-V 4.6 version of the client.</span></span> <span data-ttu-id="b35ba-110">最善の結果を得るために、利用可能なすべての更新プログラムを、App-v 5.0 SP3 クライアントにインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b35ba-110">For best results, we recommend that you install all available updates to the App-V 5.0 SP3 client.</span></span>

2.  <span data-ttu-id="b35ba-111">パッケージを段階的に変換または再シーケンスします。</span><span class="sxs-lookup"><span data-stu-id="b35ba-111">Convert or re-sequence the packages gradually.</span></span>

    -   <span data-ttu-id="b35ba-112">パッケージを変換するには、App-v 5.0 パッケージコンバーターを使用し、必要なパッケージを App-v 5.0 (**appv**) ファイル形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="b35ba-112">To convert the packages, use the App-V 5.0 package converter and convert the required packages to the App-V 5.0 (**.appv**) file format.</span></span>

    -   <span data-ttu-id="b35ba-113">パッケージの順序を変更するには、最善の結果を得るために、最新バージョンの Sequencer の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="b35ba-113">To re-sequence the packages, consider using the latest version of the Sequencer for best results.</span></span>

    <span data-ttu-id="b35ba-114">パッケージの発行の詳細については、「[管理コンソールを使用してパッケージを公開する方法](how-to-publish-a-package-by-using-the-management-console-50.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b35ba-114">For more information about publishing packages, see [How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-50.md).</span></span>

3.  <span data-ttu-id="b35ba-115">クライアントコンピューターにパッケージを展開します。</span><span class="sxs-lookup"><span data-stu-id="b35ba-115">Deploy packages to the client computers.</span></span>

4.  <span data-ttu-id="b35ba-116">必要に応じて、拡張点を変換します。</span><span class="sxs-lookup"><span data-stu-id="b35ba-116">Convert extension points, as needed.</span></span> <span data-ttu-id="b35ba-117">詳しくは、次のリソースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b35ba-117">For more information, see the following resources:</span></span>

    -   [<span data-ttu-id="b35ba-118">特定のコンピューター上の全ユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.0 パッケージに移行する方法</span><span class="sxs-lookup"><span data-stu-id="b35ba-118">How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.0 Package for All Users on a Specific Computer</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)

    -   [<span data-ttu-id="b35ba-119">特定のユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.0 パッケージに移行する方法</span><span class="sxs-lookup"><span data-stu-id="b35ba-119">How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.0 for a Specific User</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md)

    -   [<span data-ttu-id="b35ba-120">以前のバージョンの APP-V で作成されたパッケージを変換する方法</span><span class="sxs-lookup"><span data-stu-id="b35ba-120">How to Convert a Package Created in a Previous Version of App-V</span></span>](how-to-convert-a-package-created-in-a-previous-version-of-app-v.md)

5.  <span data-ttu-id="b35ba-121">App-v 5.0 パッケージが正常に処理されたことをテストし、4.6 パッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="b35ba-121">Test that your App-V 5.0 packages are successful, and then remove the 4.6 packages.</span></span> <span data-ttu-id="b35ba-122">クライアントコンピューターのユーザーの状態を確認するには、[ユーザーエクスペリエンスの仮想化](https://technet.microsoft.com/library/dn458947.aspx)または他のユーザー環境管理ツールを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b35ba-122">To check the user state of your client computers, we recommend that you use [User Experience Virtualization](https://technet.microsoft.com/library/dn458947.aspx) or another user environment management tool.</span></span>

    <span data-ttu-id="b35ba-123">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="b35ba-123">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="b35ba-124">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="b35ba-124">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="b35ba-125">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="b35ba-125">Got an App-V issue?</span></span>** <span data-ttu-id="b35ba-126">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="b35ba-126">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="b35ba-127">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b35ba-127">Related topics</span></span>


[<span data-ttu-id="b35ba-128">APP-V の以前のバージョンからの移行計画</span><span class="sxs-lookup"><span data-stu-id="b35ba-128">Planning for Migrating from a Previous Version of App-V</span></span>](planning-for-migrating-from-a-previous-version-of-app-v.md)

[<span data-ttu-id="b35ba-129">App-V 5.0 Sequencer および Client の展開</span><span class="sxs-lookup"><span data-stu-id="b35ba-129">Deploying the App-V 5.0 Sequencer and Client</span></span>](deploying-the-app-v-50-sequencer-and-client.md)

 

 





