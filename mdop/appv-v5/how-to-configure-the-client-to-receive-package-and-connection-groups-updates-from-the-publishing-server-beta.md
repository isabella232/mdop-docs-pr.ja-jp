---
title: 公開サーバーからパッケージと接続グループの更新を受信するように Client を構成する方法
description: 公開サーバーからパッケージと接続グループの更新を受信するように Client を構成する方法
author: dansimp
ms.assetid: f5dfd96d-4b63-468c-8d93-9dfdf47c28fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7e9df1f8b324430449d8d1dd3624d9f1157968a5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814387"
---
# <span data-ttu-id="e0f91-103">公開サーバーからパッケージと接続グループの更新を受信するように Client を構成する方法</span><span class="sxs-lookup"><span data-stu-id="e0f91-103">How to Configure the Client to Receive Package and Connection Groups Updates From the Publishing Server</span></span>


<span data-ttu-id="e0f91-104">App-v 5.0 発行サーバーを使用してパッケージと接続グループを展開すると、単一ポイント管理と高いスケーラビリティが実現されるため便利です。</span><span class="sxs-lookup"><span data-stu-id="e0f91-104">Deploying packages and connection groups using the App-V 5.0 publishing server is helpful because it offers single-point management and high scalability.</span></span>

<span data-ttu-id="e0f91-105">次の手順を使用して、公開サーバーから更新プログラムを受け取るように、App-v 5.0 クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="e0f91-105">Use the following steps to configure the App-V 5.0 client to receive updates from the publishing server.</span></span>

<span data-ttu-id="e0f91-106">**注** 次の手順では、管理サーバーが**MyMgmtSrv**という名前のコンピューターにインストールされており、発行サーバーが**MyPubSrv**という名前のコンピューターにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="e0f91-106">**Note** For the following procedures the management server was installed on a computer named **MyMgmtSrv**, and the publishing server was installed on a computer named **MyPubSrv**.</span></span>

 

**<span data-ttu-id="e0f91-107">公開サーバーから更新プログラムを受信するように App-v 5.0 クライアントを構成するには</span><span class="sxs-lookup"><span data-stu-id="e0f91-107">To configure the App-V 5.0 client to receive updates from the publishing server</span></span>**

1.  <span data-ttu-id="e0f91-108">App-v 5.0 management と発行サーバーを展開し、必要なパッケージと接続グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="e0f91-108">Deploy the App-V 5.0 management and publishing servers, and add the required packages and connection groups.</span></span> <span data-ttu-id="e0f91-109">パッケージと接続グループの追加の詳細については、「[管理コンソールを使用してパッケージを追加またはアップグレードする方法](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)」と「[接続グループを作成する方法](how-to-create-a-connection-group.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0f91-109">For more information about adding packages and connection groups, see [How to Add or Upgrade Packages by Using the Management Console](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md) and [How to Create a Connection Group](how-to-create-a-connection-group.md).</span></span>

2.  <span data-ttu-id="e0f91-110">管理コンソールを開くには、次のリンクをクリックし、ブラウザーを開いて次のように入力し http://MyMgmtSrv/AppvManagement/Console.html ます。 web ブラウザーで、すべてのパッケージと接続グループをインポート、公開、entitle して、特定のユーザーのセットに必要となるすべてのパッケージと接続グループを設定します。</span><span class="sxs-lookup"><span data-stu-id="e0f91-110">To open the management console click the following link, open a browser and type the following: http://MyMgmtSrv/AppvManagement/Console.html in a web browser, and import, publish, and entitle all the packages and connection groups which will be necessary for a particular set of users.</span></span>

3.  <span data-ttu-id="e0f91-111">App-v 5.0 クライアントを実行しているコンピューターで、管理者特権の PowerShell コマンドプロンプトを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0f91-111">On the computer running the App-V 5.0 client, open an elevated PowerShell command prompt, run the following command:</span></span>

    **<span data-ttu-id="e0f91-112">AppvPublishingServer-Name ABC-URL http://MyPubSrv/AppvPublishing</span><span class="sxs-lookup"><span data-stu-id="e0f91-112">Add-AppvPublishingServer -Name ABC -URL http:// MyPubSrv/AppvPublishing</span></span>**

    <span data-ttu-id="e0f91-113">このコマンドは、指定した発行サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="e0f91-113">This command will configure the specified publishing server.</span></span> <span data-ttu-id="e0f91-114">次のような出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0f91-114">You should see output similar to the following:</span></span>

    <span data-ttu-id="e0f91-115">Id: 1</span><span class="sxs-lookup"><span data-stu-id="e0f91-115">Id : 1</span></span>

    <span data-ttu-id="e0f91-116">SetByGroupPolicy: False</span><span class="sxs-lookup"><span data-stu-id="e0f91-116">SetByGroupPolicy : False</span></span>

    <span data-ttu-id="e0f91-117">名前: ABC</span><span class="sxs-lookup"><span data-stu-id="e0f91-117">Name : ABC</span></span>

    <span data-ttu-id="e0f91-118">URL: http://MyPubSrv/AppvPublishing</span><span class="sxs-lookup"><span data-stu-id="e0f91-118">URL : http:// MyPubSrv/AppvPublishing</span></span>

    <span data-ttu-id="e0f91-119">GlobalRefreshEnabled: False</span><span class="sxs-lookup"><span data-stu-id="e0f91-119">GlobalRefreshEnabled : False</span></span>

    <span data-ttu-id="e0f91-120">GlobalRefreshOnLogon: False</span><span class="sxs-lookup"><span data-stu-id="e0f91-120">GlobalRefreshOnLogon : False</span></span>

    <span data-ttu-id="e0f91-121">GlobalRefreshInterval: 0</span><span class="sxs-lookup"><span data-stu-id="e0f91-121">GlobalRefreshInterval : 0</span></span>

    <span data-ttu-id="e0f91-122">GlobalRefreshIntervalUnit: Day</span><span class="sxs-lookup"><span data-stu-id="e0f91-122">GlobalRefreshIntervalUnit : Day</span></span>

    <span data-ttu-id="e0f91-123">UserRefreshEnabled: True</span><span class="sxs-lookup"><span data-stu-id="e0f91-123">UserRefreshEnabled : True</span></span>

    <span data-ttu-id="e0f91-124">UserRefreshOnLogon True</span><span class="sxs-lookup"><span data-stu-id="e0f91-124">UserRefreshOnLogon : True</span></span>

    <span data-ttu-id="e0f91-125">UserRefreshInterval: 0</span><span class="sxs-lookup"><span data-stu-id="e0f91-125">UserRefreshInterval : 0</span></span>

    <span data-ttu-id="e0f91-126">UserRefreshIntervalUnit: Day</span><span class="sxs-lookup"><span data-stu-id="e0f91-126">UserRefreshIntervalUnit : Day</span></span>

    <span data-ttu-id="e0f91-127">返された Id –この例では1</span><span class="sxs-lookup"><span data-stu-id="e0f91-127">The returned Id – in this case 1</span></span>

4.  <span data-ttu-id="e0f91-128">App-v 5.0 クライアントを実行しているコンピューターで、PowerShell コマンドプロンプトを開き、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="e0f91-128">On the computer running the App-V 5.0 client, open a PowerShell command prompt, and type the following command:</span></span>

    **<span data-ttu-id="e0f91-129">同期-AppvPublishingServer-ServerId 1</span><span class="sxs-lookup"><span data-stu-id="e0f91-129">Sync-AppvPublishingServer -ServerId 1</span></span>**

    <span data-ttu-id="e0f91-130">このコマンドは、管理サーバーで構成されたパッケージと接続グループの権限に基づいて、特定のクライアントに対して追加または削除する必要があるパッケージと接続グループの発行サーバーを照会します。</span><span class="sxs-lookup"><span data-stu-id="e0f91-130">The command will query the publishing server for the packages and connection groups that need to be added or removed for this particular client based on the entitlements for the packages and connection groups as configured on the management server.</span></span>

    <span data-ttu-id="e0f91-131">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="e0f91-131">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="e0f91-132">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="e0f91-132">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="e0f91-133">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="e0f91-133">Got an App-V issue?</span></span>** <span data-ttu-id="e0f91-134">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0f91-134">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="e0f91-135">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e0f91-135">Related topics</span></span>


[<span data-ttu-id="e0f91-136">APP-V 5.0 の操作</span><span class="sxs-lookup"><span data-stu-id="e0f91-136">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





