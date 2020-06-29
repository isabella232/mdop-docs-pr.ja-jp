---
title: 管理コンソールを使用して管理者を追加または削除する方法
description: 管理コンソールを使用して管理者を追加または削除する方法
author: dansimp
ms.assetid: 0e8ab443-1931-4b1a-95df-6ccbecc9efc5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f9289f4ad5204bee85f0fa5bfebed407317f69f2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814499"
---
# <span data-ttu-id="47a6e-103">管理コンソールを使用して管理者を追加または削除する方法</span><span class="sxs-lookup"><span data-stu-id="47a6e-103">How to Add or Remove an Administrator by Using the Management Console</span></span>


<span data-ttu-id="47a6e-104">次の手順を使用して、App-v 5.0 server の管理者を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="47a6e-104">Use the following procedures to add or remove an administrator on the App-V 5.0 server.</span></span>

**<span data-ttu-id="47a6e-105">管理コンソールを使用して管理者を追加するには</span><span class="sxs-lookup"><span data-stu-id="47a6e-105">To add an administrator using the Management Console</span></span>**

1.  <span data-ttu-id="47a6e-106">App V 5.0 管理コンソールを開き、ナビゲーションウィンドウで [**管理者**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47a6e-106">Open the App-V 5.0 Management Console and click **Administrators** in the navigation pane.</span></span> <span data-ttu-id="47a6e-107">ナビゲーションウィンドウには、現在、App-v 5.0 server への管理アクセス権がある Access ディレクトリ (AD) ユーザーとグループの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="47a6e-107">The navigation pane displays a list of Access Directory (AD) users and groups that currently have administrative access to the App-V 5.0 server.</span></span>

2.  <span data-ttu-id="47a6e-108">新しい管理者を追加するには、[**管理者の追加**] をクリックし、[ **Active Directory 名**] フィールドに追加する管理者の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="47a6e-108">To add a new administrator, click **Add Administrator** Type the name of the administrator that you want to add in the **Active Directory Name** field.</span></span> <span data-ttu-id="47a6e-109">関連付けられたユーザーアカウントドメイン名を指定していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="47a6e-109">Ensure you provide the associated user account domain name.</span></span> <span data-ttu-id="47a6e-110">たとえば、**ドメイン**の  \\  **ユーザー名**。</span><span class="sxs-lookup"><span data-stu-id="47a6e-110">For example, **Domain** \\ **UserName**.</span></span>

3.  <span data-ttu-id="47a6e-111">追加するアカウントを選択し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47a6e-111">Select the account that you want to add and click **Add**.</span></span> <span data-ttu-id="47a6e-112">新しいアカウントがサーバー管理者の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="47a6e-112">The new account is displayed in the list of server administrators.</span></span>

**<span data-ttu-id="47a6e-113">管理コンソールを使用して管理者を削除するには</span><span class="sxs-lookup"><span data-stu-id="47a6e-113">To remove an administrator using the Management Console</span></span>**

1.  <span data-ttu-id="47a6e-114">App V 5.0 管理コンソールを開き、ナビゲーションウィンドウで [**管理者**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="47a6e-114">Open the App-V 5.0 Management Console and click **Administrators** in the navigation pane.</span></span> <span data-ttu-id="47a6e-115">ナビゲーションウィンドウには、現在、App-v 5.0 server への管理アクセス権がある広告ユーザーとグループの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="47a6e-115">The navigation pane displays a list of AD users and groups that currently have administrative access to the App-V 5.0 server.</span></span>

2.  <span data-ttu-id="47a6e-116">管理者のリストから削除するアカウントを右クリックし、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="47a6e-116">Right-click the account to be removed from the list of administrators and select **Remove**.</span></span>

    <span data-ttu-id="47a6e-117">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="47a6e-117">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="47a6e-118">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="47a6e-118">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="47a6e-119">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="47a6e-119">Got an App-V issue?</span></span>** <span data-ttu-id="47a6e-120">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="47a6e-120">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="47a6e-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="47a6e-121">Related topics</span></span>


[<span data-ttu-id="47a6e-122">APP-V 5.0 の操作</span><span class="sxs-lookup"><span data-stu-id="47a6e-122">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





