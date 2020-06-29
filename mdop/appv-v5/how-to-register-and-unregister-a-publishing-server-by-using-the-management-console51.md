---
title: 管理コンソールを使用して公開サーバーを登録および登録解除する方法
description: 管理コンソールを使用して公開サーバーを登録および登録解除する方法
author: dansimp
ms.assetid: 69cef0a8-8102-4697-b1ba-f16e0f25216b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b63922ff03ea19326e395e57236fcd079711bd43
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813755"
---
# <span data-ttu-id="29dbf-103">管理コンソールを使用して公開サーバーを登録および登録解除する方法</span><span class="sxs-lookup"><span data-stu-id="29dbf-103">How to Register and Unregister a Publishing Server by Using the Management Console</span></span>


<span data-ttu-id="29dbf-104">App-v 5.1 management サーバーと同期させる発行サーバーの登録と登録解除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="29dbf-104">You can register and unregister publishing servers that will synchronize with the App-V 5.1 management server.</span></span> <span data-ttu-id="29dbf-105">また、発行サーバーが管理サーバーと情報を同期した前回の試行を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="29dbf-105">You can also see the last attempt that the publishing server made to synchronize the information with the management server.</span></span>

<span data-ttu-id="29dbf-106">発行サーバーを登録または登録解除するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="29dbf-106">Use the following procedure to register or unregister a publishing server.</span></span>

**<span data-ttu-id="29dbf-107">管理コンソールを使用して発行サーバーを登録するには</span><span class="sxs-lookup"><span data-stu-id="29dbf-107">To register a publishing server using the Management Console</span></span>**

1.  <span data-ttu-id="29dbf-108">管理コンソールに接続し、[**サーバー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="29dbf-108">Connect to the Management Console and select **Servers**.</span></span> <span data-ttu-id="29dbf-109">管理コンソールに接続する方法の詳細については、「[管理コンソールに接続する方法](how-to-connect-to-the-management-console-51.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29dbf-109">For more information about how to connect to the Management Console, see [How to Connect to the Management Console](how-to-connect-to-the-management-console-51.md).</span></span>

2.  <span data-ttu-id="29dbf-110">管理サーバーと既に同期されている発行サーバーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="29dbf-110">A list of publishing servers that already synchronize with the management server is displayed.</span></span> <span data-ttu-id="29dbf-111">[新しいサーバーの登録] をクリックして新しいサーバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="29dbf-111">Click Register New Server to register a new server.</span></span>

3.  <span data-ttu-id="29dbf-112">[**サーバー名**] 行に、[ドメインに参加しているコンピューター] のコンピューター名を入力して、サーバーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="29dbf-112">Type a computer name of a domain joined computer on the **Server Name** line, to specify a name for the server.</span></span> <span data-ttu-id="29dbf-113">また、 **MyDomain\\TestServer**のようなドメイン名も含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="29dbf-113">You should also include a domain name, for example, **MyDomain\\TestServer**.</span></span> <span data-ttu-id="29dbf-114">[**チェック**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29dbf-114">Click **Check**.</span></span>

4.  <span data-ttu-id="29dbf-115">コンピューターを選択し、[**追加**] をクリックして、コンピューターをサーバーの一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="29dbf-115">Select the computer and click **Add** to add the computer to the list of servers.</span></span> <span data-ttu-id="29dbf-116">新しいサーバーが一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="29dbf-116">The new server will be displayed in the list.</span></span>

**<span data-ttu-id="29dbf-117">管理コンソールを使用して発行サーバーの登録を解除するには</span><span class="sxs-lookup"><span data-stu-id="29dbf-117">To unregister a publishing server using the Management Console</span></span>**

1.  <span data-ttu-id="29dbf-118">管理コンソールに接続し、[**サーバー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="29dbf-118">Connect to the Management Console and select **Servers**.</span></span> <span data-ttu-id="29dbf-119">管理コンソールに接続する方法の詳細については、「[管理コンソールに接続する方法](how-to-connect-to-the-management-console-51.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29dbf-119">For more information about how to connect to the Management Console, see [How to Connect to the Management Console](how-to-connect-to-the-management-console-51.md).</span></span>

2.  <span data-ttu-id="29dbf-120">管理サーバーと同期する発行サーバーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="29dbf-120">A list of publishing servers that synchronize with the management server is displayed.</span></span>

3.  <span data-ttu-id="29dbf-121">サーバーの登録を解除するには、コンピューター名を右クリックし、コンピューター名を選択して、[**サーバーの登録解除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="29dbf-121">To unregister the server, right-click the computer name and select the computer name and select **unregister server**.</span></span>

    <span data-ttu-id="29dbf-122">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="29dbf-122">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="29dbf-123">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="29dbf-123">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="29dbf-124">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="29dbf-124">Got an App-V issue?</span></span>** <span data-ttu-id="29dbf-125">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="29dbf-125">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="29dbf-126">関連トピック</span><span class="sxs-lookup"><span data-stu-id="29dbf-126">Related topics</span></span>


[<span data-ttu-id="29dbf-127">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="29dbf-127">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





