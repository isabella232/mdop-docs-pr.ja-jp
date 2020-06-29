---
title: クライアント コンピューターが Microsoft Content Delivery Network にアクセスできない場合にセルフサービス ポータルを構成する方法
description: クライアント コンピューターが Microsoft Content Delivery Network にアクセスできない場合にセルフサービス ポータルを構成する方法
author: dansimp
ms.assetid: 90ee76db-9876-41b5-994a-118556d5ed3b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ffce3dd023cb6ff9bd5cdb13ea789b348661de24
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824494"
---
# <span data-ttu-id="2af82-103">クライアント コンピューターが Microsoft Content Delivery Network にアクセスできない場合にセルフサービス ポータルを構成する方法</span><span class="sxs-lookup"><span data-stu-id="2af82-103">How to Configure the Self-Service Portal When Client Computers Cannot Access the Microsoft Content Delivery Network</span></span>


<span data-ttu-id="2af82-104">組織内のクライアントコンピューターが Microsoft Ajax コンテンツ配信ネットワーク (CDN) にアクセスできない場合は、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2af82-104">Follow these instructions if the client computers in your organization do not have access to the Microsoft Ajax Content Delivery Network (CDN).</span></span>

**<span data-ttu-id="2af82-105">構成が必要な理由:</span><span class="sxs-lookup"><span data-stu-id="2af82-105">Why you need to configure this:</span></span>**

<span data-ttu-id="2af82-106">クライアントコンピューターは CDN にアクセスする必要があります。これにより、セルフサービスポータルで、特定の JavaScript ファイルに必要なアクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="2af82-106">Your client computers need access to the CDN, which gives the Self-Service Portal the required access to certain JavaScript files.</span></span> <span data-ttu-id="2af82-107">クライアントコンピューターが CDN にアクセスできないときにセルフサービスポータルを構成しないと、会社名とエンドユーザーがログインするアカウントのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2af82-107">If you don’t configure the Self-Service Portal when client computers cannot access CDN, only the company name and the account under which the end user logs in will be displayed.</span></span> <span data-ttu-id="2af82-108">エラーメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="2af82-108">No error message will be shown.</span></span>

<span data-ttu-id="2af82-109">**注** MBAM 2.5 SP1 では、JavaScript ファイルは製品に含まれており、このセクションの手順に従って、インターネットにアクセスできないクライアントをサポートするように SSP を構成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2af82-109">**Note** In MBAM 2.5 SP1, the JavaScript files are included in the product, and you do not need to follow the instructions in this section to configure the SSP to support clients that cannot access the internet.</span></span>

 

**<span data-ttu-id="2af82-110">クライアントコンピューターが CDN にアクセスできないときにセルフサービスポータルを構成する方法</span><span class="sxs-lookup"><span data-stu-id="2af82-110">How to configure the Self-Service Portal when client computers cannot access the CDN</span></span>**

1. <span data-ttu-id="2af82-111">CDN から次の JavaScript ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="2af82-111">Download the following JavaScript files from the CDN:</span></span>

   -   [<span data-ttu-id="2af82-112">jQuery-1.10.2.min.js</span><span class="sxs-lookup"><span data-stu-id="2af82-112">jQuery-1.10.2.min.js</span></span>](https://go.microsoft.com/fwlink/?LinkID=390515)

   -   [<span data-ttu-id="2af82-113">jQuery.validate.min.js</span><span class="sxs-lookup"><span data-stu-id="2af82-113">jQuery.validate.min.js</span></span>](https://go.microsoft.com/fwlink/?LinkID=390516)

   -   [<span data-ttu-id="2af82-114">jQuery.validate.unobtrusive.min.js</span><span class="sxs-lookup"><span data-stu-id="2af82-114">jQuery.validate.unobtrusive.min.js</span></span>](https://go.microsoft.com/fwlink/?LinkID=390517)

2. <span data-ttu-id="2af82-115">JavaScript ファイルをセルフサービスポータルの**Scripts**ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="2af82-115">Copy the JavaScript files to the **Scripts** directory of the Self-Service Portal.</span></span> <span data-ttu-id="2af82-116">このディレクトリは、 <em> &lt; mbam セルフサービスインストールディレクトリ &gt; \\ </em> セルフサービス Website\\Scripts. にあります。</span><span class="sxs-lookup"><span data-stu-id="2af82-116">This directory is located in <em>&lt;MBAM Self-Service Install Directory&gt;\\</em>Self Service Website\\Scripts.</span></span>

3. <span data-ttu-id="2af82-117">インターネットインフォメーションサービス (IIS) マネージャーを開きます。</span><span class="sxs-lookup"><span data-stu-id="2af82-117">Open Internet Information Services (IIS) Manager.</span></span>

4. <span data-ttu-id="2af82-118">**Sites** &gt; **Microsoft BitLocker の管理と監視**を展開し、[ **selfservice**] を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="2af82-118">Expand **Sites** &gt; **Microsoft BitLocker Administration and Monitoring**, and highlight **SelfService**.</span></span>

   **<span data-ttu-id="2af82-119">注</span><span class="sxs-lookup"><span data-stu-id="2af82-119">Note</span></span>**  
   <span data-ttu-id="2af82-120">*Selfservice*は、既定の仮想ディレクトリ名です。</span><span class="sxs-lookup"><span data-stu-id="2af82-120">*SelfService* is the default virtual directory name.</span></span> <span data-ttu-id="2af82-121">構成時にこのディレクトリに別の名前を選択した場合は、次の手順の*Selfservice*を、選択した名前に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="2af82-121">If you chose a different name for this directory during the configuration, remember to replace *SelfService* in these instructions with the name you chose.</span></span>

     

5. <span data-ttu-id="2af82-122">中央のウィンドウで、[アプリケーションの**設定**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="2af82-122">In the middle pane, double-click **Application Settings**.</span></span>

6. <span data-ttu-id="2af82-123">次のリストの各アイテムについて、新しい場所を参照するようにアプリケーションの設定を編集します。これには、/ &lt; *virtual directory* &gt; selfservice/(または構成時に選択した任意の名前) を使用します。</span><span class="sxs-lookup"><span data-stu-id="2af82-123">For each item in the following list, edit the application settings to reference the new location by replacing /&lt;*virtual directory*&gt;/ with /SelfService/ (or whatever name you chose during configuration).</span></span> <span data-ttu-id="2af82-124">たとえば、仮想ディレクトリのパスは、/Selfservice/スクリプト/jQuery-1.10.2.min.js に似ています。</span><span class="sxs-lookup"><span data-stu-id="2af82-124">For example, the virtual directory path will be similar to /selfservice/Scripts/ jQuery-1.10.2.min.js.</span></span>

   -   <span data-ttu-id="2af82-125">jQueryPath:/ &lt; *virtual directory*/ &gt; スクリプト/jQuery-1.10.2.min.js</span><span class="sxs-lookup"><span data-stu-id="2af82-125">jQueryPath: /&lt;*virtual directory*&gt;/Scripts/jQuery-1.10.2.min.js</span></span>

   -   <span data-ttu-id="2af82-126">jQueryValidatePath:/ &lt; *virtual directory*/ &gt; スクリプト/jQuery.validate.min.js</span><span class="sxs-lookup"><span data-stu-id="2af82-126">jQueryValidatePath: /&lt;*virtual directory*&gt;/Scripts/jQuery.validate.min.js</span></span>

   -   <span data-ttu-id="2af82-127">jQueryValidateUnobtrusivePath:/ &lt; *virtual directory*/ &gt; スクリプト/jQuery.validate.unobtrusive.min.js</span><span class="sxs-lookup"><span data-stu-id="2af82-127">jQueryValidateUnobtrusivePath: /&lt;*virtual directory*&gt;/Scripts/jQuery.validate.unobtrusive.min.js</span></span>



## <span data-ttu-id="2af82-128">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2af82-128">Related topics</span></span>


[<span data-ttu-id="2af82-129">MBAM 2.5 Web アプリケーションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="2af82-129">How to Configure the MBAM 2.5 Web Applications</span></span>](how-to-configure-the-mbam-25-web-applications.md)

 

## <span data-ttu-id="2af82-130">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="2af82-130">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="2af82-131">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="2af82-131">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="2af82-132">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="2af82-132">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





