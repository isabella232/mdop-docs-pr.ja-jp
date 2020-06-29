---
title: Web ベース アプリケーションの仮想環境を作成する方法
description: Web ベース アプリケーションの仮想環境を作成する方法
author: dansimp
ms.assetid: d2b16e9d-369c-4bd6-b2a0-16dd24c0e32c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3a53bec6869b3af9666775600b181c57eec3be93
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817664"
---
# <span data-ttu-id="b03d6-103">Web ベース アプリケーションの仮想環境を作成する方法</span><span class="sxs-lookup"><span data-stu-id="b03d6-103">How to Create a Virtual Environment for a Web-Based Application</span></span>


<span data-ttu-id="b03d6-104">分離する web アプリケーションの仮想環境を個別に作成することができます。</span><span class="sxs-lookup"><span data-stu-id="b03d6-104">You can create separate virtual environments for web applications you want to isolate.</span></span> <span data-ttu-id="b03d6-105">個別の web 環境を作成することは、web ベースのアプリケーションのプラグインに、互いに競合する構成が必要な場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="b03d6-105">Creating separate web environments is useful if the web-based applications require plug-ins of have configurations that conflict with each other.</span></span>

**<span data-ttu-id="b03d6-106">Web ベースのアプリケーションの仮想環境を作成するには</span><span class="sxs-lookup"><span data-stu-id="b03d6-106">To create a virtual environment for a Web-based application</span></span>**

1.  <span data-ttu-id="b03d6-107">シーケンスウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="b03d6-107">Open the sequencing wizard.</span></span> <span data-ttu-id="b03d6-108">アプリケーションのシーケンスの詳細については[、「新しいアプリケーションを順序付ける方法」を](how-to-sequence-a-new-application.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="b03d6-108">For more information about sequencing an application see [How to Sequence a New Application](how-to-sequence-a-new-application.md).</span></span>

2.  <span data-ttu-id="b03d6-109">[**モニターのインストール**] ページで、アプリケーションのインストールの監視を開始するには、[**監視の開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b03d6-109">On the **Monitor Installation** page, to start monitoring the installation of the application, click **Begin Monitoring**.</span></span> <span data-ttu-id="b03d6-110">Web ブラウザーを開き、アプリケーションに関連付けられているインストーラファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="b03d6-110">Open a web browser and navigate to the installer file associated with the application.</span></span> <span data-ttu-id="b03d6-111">アプリケーションをインストールし、必要なポストインストール構成タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="b03d6-111">Install the application, and perform any required post installation configuration tasks.</span></span>

3.  <span data-ttu-id="b03d6-112">アプリケーションを確実に起動するには、アプリケーションを3回開きます。</span><span class="sxs-lookup"><span data-stu-id="b03d6-112">To ensure the applications starts, open the application three times.</span></span>

4.  <span data-ttu-id="b03d6-113">同じ仮想環境内に存在する必要があるその他のアプリケーションをインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="b03d6-113">Install and configure any additional applications that need to reside in the same virtual environment.</span></span>

5.  <span data-ttu-id="b03d6-114">シーケンスウィザードの残りの手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="b03d6-114">Complete the remainder of the Sequencing Wizard.</span></span>

6.  <span data-ttu-id="b03d6-115">アプリケーションを保存するには、[**ファイル**] を選択し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b03d6-115">To save the application, select **File**, and click **Save**.</span></span>

## <span data-ttu-id="b03d6-116">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b03d6-116">Related topics</span></span>


[<span data-ttu-id="b03d6-117">Application Virtualization Sequencer のタスク</span><span class="sxs-lookup"><span data-stu-id="b03d6-117">Tasks for the Application Virtualization Sequencer</span></span>](tasks-for-the-application-virtualization-sequencer.md)

 

 





