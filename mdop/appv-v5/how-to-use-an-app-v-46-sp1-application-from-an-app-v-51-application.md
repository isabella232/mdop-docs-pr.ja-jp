---
title: App-v 5.1 アプリケーションから app-v 4.6 アプリケーションを使用する方法
description: App-v 5.1 アプリケーションから app-v 4.6 アプリケーションを使用する方法
author: dansimp
ms.assetid: 909b4391-762b-4988-b0cf-32b67f1fcf0e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: c0d308dcae33b02c089c101ffcd5041b2e665f59
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813635"
---
# <span data-ttu-id="0205e-103">App-v 5.1 アプリケーションから app-v 4.6 アプリケーションを使用する方法</span><span class="sxs-lookup"><span data-stu-id="0205e-103">How to Use an App-V 4.6 Application From an App-V 5.1 Application</span></span>

<span data-ttu-id="0205e-104">*注:*\* App-V 4.6 はメインストリームサポートを終了しました。</span><span class="sxs-lookup"><span data-stu-id="0205e-104">*Note:*\* App-V 4.6 has exited Mainstream support.</span></span> <span data-ttu-id="0205e-105">以下は、App-v 4.6 SP3 パッケージに適用されます。</span><span class="sxs-lookup"><span data-stu-id="0205e-105">The following applies to an App-V 4.6 SP3 package.</span></span>

<span data-ttu-id="0205e-106">スタンドアロンクライアントで app-v 5.1 アプリケーションを使用して app-v 4.6 アプリケーションを実行するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0205e-106">Use the following procedure to run an App-V4.6 application with App-V 5.1 applications on a standalone client.</span></span>

<span data-ttu-id="0205e-107">**注** この手順では、最新バージョンの App-v 4.6 が実行されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="0205e-107">**Note** This procedure assumes that you are running the latest version of App-V 4.6.</span></span>

**<span data-ttu-id="0205e-108">スタンドアロンクライアントでアプリケーションを実行するには</span><span class="sxs-lookup"><span data-stu-id="0205e-108">To run applications on a standalone client</span></span>**

1.  <span data-ttu-id="0205e-109">環境内で2つのアプリケーションを同時に開くことができます。</span><span class="sxs-lookup"><span data-stu-id="0205e-109">Select two applications in your environment that can be opened from one another.</span></span> <span data-ttu-id="0205e-110">たとえば、Microsoft Outlook や Adobe Acrobat Reader などです。</span><span class="sxs-lookup"><span data-stu-id="0205e-110">For example, Microsoft Outlook and Adobe Acrobat Reader.</span></span> <span data-ttu-id="0205e-111">Adobe Acrobat を使って作成されたメールの添付ファイルにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0205e-111">You can access an email attachment created using Adobe Acrobat.</span></span>

2.  <span data-ttu-id="0205e-112">App-v 5.1 形式を使用して、パッケージを変換するか、いずれかのアプリケーション用の新しいパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="0205e-112">Convert the packages, or create a new package for either of the applications using the App-V 5.1 format.</span></span> <span data-ttu-id="0205e-113">パッケージの変換の詳細については、「[アプリ-v 4.6 パッケージから、特定のコンピューター上のすべてのユーザー用に、変換されたアプリ-v 5.1 パッケージに拡張ポイントを移行する方法](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-51-package-for-all-users-on-a-specific-computer.md)」を参照してください。また、[特定のユーザーに対して、拡張ポイントを App-v 4.6 パッケージから App-v 5.1 に移行する方法](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-51-for-a-specific-user.md)を説明します。</span><span class="sxs-lookup"><span data-stu-id="0205e-113">For more information about converting packages see, [How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.1 Package for All Users on a Specific Computer](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-51-package-for-all-users-on-a-specific-computer.md) or [How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.1 for a Specific User](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-51-for-a-specific-user.md).</span></span>

3.  <span data-ttu-id="0205e-114">App-v 5.1 管理コンソールを使用して、パッケージを追加し、プロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="0205e-114">Add and provision the package using the App-V 5.1 management console.</span></span> <span data-ttu-id="0205e-115">パッケージの追加とプロビジョニングの詳細については、「[管理コンソールを使用してパッケージを追加またはアップグレードする方法](how-to-add-or-upgrade-packages-by-using-the-management-console-51-gb18030.md)」と「[管理コンソールを使用してパッケージへのアクセスを構成する方法](how-to-configure-access-to-packages-by-using-the-management-console-51.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0205e-115">For more information adding and provisioning packages see, [How to Add or Upgrade Packages by Using the Management Console](how-to-add-or-upgrade-packages-by-using-the-management-console-51-gb18030.md) and [How to Configure Access to Packages by Using the Management Console](how-to-configure-access-to-packages-by-using-the-management-console-51.md).</span></span>

4.  <span data-ttu-id="0205e-116">変換されたアプリケーションは、App-v 5.1 を使って実行されるようになり、もう1つのアプリケーションを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="0205e-116">The converted application now runs using App-V 5.1 and you can open one application from the other.</span></span> <span data-ttu-id="0205e-117">たとえば、Microsoft Office パッケージを App-v 5.1 パッケージに変換しても、Adobe Acrobat が依然として App V 4.6 パッケージとして実行されている場合は、Microsoft Outlook を使用して Adobe Acrobat Reader の添付ファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="0205e-117">For example, if you converted a Microsoft Office package to an App-V 5.1 package and Adobe Acrobat is still running as an App-V4.6 package, you can open an Adobe Acrobat Reader attachment using Microsoft Outlook.</span></span>

    <span data-ttu-id="0205e-118">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="0205e-118">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="0205e-119">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="0205e-119">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="0205e-120">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="0205e-120">Got an App-V issue?</span></span>** <span data-ttu-id="0205e-121">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="0205e-121">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="0205e-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0205e-122">Related topics</span></span>


[<span data-ttu-id="0205e-123">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="0205e-123">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





