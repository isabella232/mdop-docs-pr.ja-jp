---
title: 共有コンテンツ ストア モードの App-V 5.1 Client のインストール方法
description: 共有コンテンツ ストア モードの App-V 5.1 Client のインストール方法
author: dansimp
ms.assetid: 6f3ecb1b-b5b5-4ae0-8de9-b4ffdfd2c216
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a7ce8114a44762180bf9bb0240913dca50c55d31
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814051"
---
# <span data-ttu-id="65e45-103">共有コンテンツ ストア モードの App-V 5.1 Client のインストール方法</span><span class="sxs-lookup"><span data-stu-id="65e45-103">How to Install the App-V 5.1 Client for Shared Content Store Mode</span></span>


<span data-ttu-id="65e45-104">Microsoft Application Virtualization (App-v) 5.1 クライアントをインストールするには、次の手順を使用して、App-v 5.1 Shared Content Store (SCS) モードを使用するようにします。</span><span class="sxs-lookup"><span data-stu-id="65e45-104">Use the following procedure to install the Microsoft Application Virtualization (App-V) 5.1 client so that it uses the App-V 5.1 Shared Content Store (SCS) mode.</span></span> <span data-ttu-id="65e45-105">必要なすべての前提条件が、インストール先のコンピューターにインストールされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65e45-105">You should ensure that all required prerequisites are installed on the computer you plan to install to.</span></span> <span data-ttu-id="65e45-106">以下のリンクを使用して、 [app-v 5.1 の前提条件](app-v-51-prerequisites.md)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="65e45-106">Use the following link to see [App-V 5.1 Prerequisites](app-v-51-prerequisites.md).</span></span>

<span data-ttu-id="65e45-107">**注** 必要に応じてこの手順を実行する前に、既存のバージョンの App-v 5.1 クライアントをアンインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="65e45-107">**Note** Before performing this procedure if necessary uninstall any existing version of the App-V 5.1 client.</span></span>

 

<span data-ttu-id="65e45-108">SCS モードの詳細については、「 [Microsoft App の共有コンテンツストア-V 5.0 –バックグラウンドでの共有コンテンツストア ()](https://go.microsoft.com/fwlink/?LinkId=316879) 」を参照してください https://go.microsoft.com/fwlink/?LinkId=316879) 。</span><span class="sxs-lookup"><span data-stu-id="65e45-108">For more information about SCS mode, see [Shared Content Store in Microsoft App-V 5.0 – Behind the Scenes](https://go.microsoft.com/fwlink/?LinkId=316879) (https://go.microsoft.com/fwlink/?LinkId=316879).</span></span>

**<span data-ttu-id="65e45-109">SCS モード用に App-v 5.1 クライアントをインストールして構成する</span><span class="sxs-lookup"><span data-stu-id="65e45-109">Install and configure the App-V 5.1 client for SCS mode</span></span>**

1.  <span data-ttu-id="65e45-110">アプリがインストールされているコンピューターに、App-v 5.1 クライアントのインストールファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="65e45-110">Copy the App-V 5.1 client installation files to the computer on which it will be installed.</span></span> <span data-ttu-id="65e45-111">インストールファイルが保存されているディレクトリからコマンドラインを開き、インストールしているクライアントのバージョンに応じて、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="65e45-111">Open a command line and from the directory where the installation files are saved type one of the following options depending on the version of the client you are installing:</span></span>

    -   <span data-ttu-id="65e45-112">RDS バージョンの App-v 5.1 クライアントの種類をインストールするには、 **appv\_client\_setup\_rds.exe/sharedcontentstoremode = 1/q**</span><span class="sxs-lookup"><span data-stu-id="65e45-112">To install the RDS version of the App-V 5.1 client type: **appv\_client\_setup\_rds.exe /SHAREDCONTENTSTOREMODE=1 /q**</span></span>

    -   <span data-ttu-id="65e45-113">App-v 5.1 クライアントの種類の標準バージョンをインストールするには、 **appv\_client\_setup.exe/sharedcontentstoremode = 1/q**</span><span class="sxs-lookup"><span data-stu-id="65e45-113">To install the standard version of the App-V 5.1 client type: **appv\_client\_setup.exe /SHAREDCONTENTSTOREMODE=1 /q**</span></span>

        <span data-ttu-id="65e45-114">**重要** サイレントインストールを実行する必要があります。インストールは失敗します。</span><span class="sxs-lookup"><span data-stu-id="65e45-114">**Important** You must perform a silent installation or the installation will fail.</span></span>

         

2.  <span data-ttu-id="65e45-115">インストールが完了したら、クライアントを実行しているコンピューターにパッケージを展開することができます。また、すべてのパッケージコンテンツはネットワーク経由でストリーミングされます。</span><span class="sxs-lookup"><span data-stu-id="65e45-115">After you have completed the installation you can deploy packages to the computer running the client and all package contents will be streamed across the network.</span></span>

    <span data-ttu-id="65e45-116">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="65e45-116">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="65e45-117">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="65e45-117">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="65e45-118">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="65e45-118">Got an App-V issue?</span></span>** <span data-ttu-id="65e45-119">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="65e45-119">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="65e45-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="65e45-120">Related topics</span></span>


[<span data-ttu-id="65e45-121">App-V 5.1 Sequencer および Client の展開</span><span class="sxs-lookup"><span data-stu-id="65e45-121">Deploying the App-V 5.1 Sequencer and Client</span></span>](deploying-the-app-v-51-sequencer-and-client.md)

 

 





