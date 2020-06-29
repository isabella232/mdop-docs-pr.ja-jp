---
title: セルフサービス ポータルの通知テキストをローカライズする方法
description: セルフサービス ポータルの通知テキストをローカライズする方法
author: dansimp
ms.assetid: a4c878b7-e5c8-45af-a537-761bb2991659
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a2385f6b00713e7373bd1707b02324b80f300c0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826714"
---
# <span data-ttu-id="0ebae-103">セルフサービス ポータルの通知テキストをローカライズする方法</span><span class="sxs-lookup"><span data-stu-id="0ebae-103">How to Localize the Self-Service Portal Notice Text</span></span>


<span data-ttu-id="0ebae-104">セルフサービスポータルで既定でエンドユーザーに表示する、ローカライズされた通知テキストを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="0ebae-104">You can configure localized notice text to display to end users by default in the Self-Service Portal.</span></span> <span data-ttu-id="0ebae-105">通知テキストを表示する Notice.txt ファイルは、次のルートディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="0ebae-105">The Notice.txt file that displays the notice text is in the following root directory:</span></span>

<span data-ttu-id="0ebae-106">&lt;*Mbam セルフサービスインストールディレクトリ* &gt;\\ セルフサービスの Website</span><span class="sxs-lookup"><span data-stu-id="0ebae-106">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\

<span data-ttu-id="0ebae-107">ローカライズされた通知テキストを表示するには、ローカライズされた Notice.txt ファイルを作成し、次の例のディレクトリの特定の言語フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="0ebae-107">To display localized notice text, you create a localized Notice.txt file, and then save it under a specific language folder in the following example directory:</span></span>

<span data-ttu-id="0ebae-108">&lt;*Mbam セルフサービスインストールディレクトリ* &gt;\\ セルフサービスの Website</span><span class="sxs-lookup"><span data-stu-id="0ebae-108">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\

<span data-ttu-id="0ebae-109">**注** [**アプリケーションの設定**] の**NoticeTextPath**アイテムを使用して、パスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="0ebae-109">**Note** You can configure the path by using the **NoticeTextPath** item in **Application Settings**.</span></span>

 

<span data-ttu-id="0ebae-110">MBAM 次のルールに基づいて、通知テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ebae-110">MBAM displays the notice text, based on the following rules:</span></span>

-   <span data-ttu-id="0ebae-111">ローカライズされた**Notice.txt**ファイルを適切な言語フォルダーに作成すると、既定の**Notice.txt**ファイルが存在する場合、mbam にローカライズされた通知テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ebae-111">If you create a localized **Notice.txt** file in the appropriate language folder, MBAM displays the localized notice text if the default **Notice.txt** file exists.</span></span> <span data-ttu-id="0ebae-112">既定の**Notice.txt**ファイルが存在しない場合は、既定のファイルが存在しないことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ebae-112">If the default **Notice.txt** file is missing, a message displays indicating that the default file is missing.</span></span>

-   <span data-ttu-id="0ebae-113">MBAM でローカライズされたバージョンの Notice.txt ファイルが見つからない場合は、既定の Notice.txt ファイルにテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ebae-113">If MBAM does not find a localized version of the Notice.txt file, it displays the text in the default Notice.txt file.</span></span>

-   <span data-ttu-id="0ebae-114">MBAM が既定の Notice.txt ファイルを見つけられない場合は、セルフサービスポータルに既定のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ebae-114">If MBAM does not find a default Notice.txt file, it displays the default text in the Self-Service Portal.</span></span>

<span data-ttu-id="0ebae-115">**注** エンドユーザーのブラウザーが、対応する言語のサブフォルダーまたは Notice.txt のない言語に設定されている場合、次のルートディレクトリにある Notice.txt ファイルのテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ebae-115">**Note** If an end user’s browser is set to a language that does not have a corresponding language subfolder or Notice.txt, the text in the Notice.txt file in the following root directory is displayed:</span></span>

<span data-ttu-id="0ebae-116">&lt;*Mbam セルフサービスインストールディレクトリ* &gt;\\ セルフサービスの Website</span><span class="sxs-lookup"><span data-stu-id="0ebae-116">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\

 

**<span data-ttu-id="0ebae-117">ローカライズされた Notice.txt ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="0ebae-117">To create a localized Notice.txt file</span></span>**

1.  <span data-ttu-id="0ebae-118">セルフサービスポータルを構成したサーバー上で、次のようなディレクトリの例の言語フォルダーを作成し &lt; *Language* &gt; ます。ここでは、language はローカライズされた &lt; *Language* &gt; 言語の名前を表しています。</span><span class="sxs-lookup"><span data-stu-id="0ebae-118">On the server where you configured the Self-Service Portal, create a &lt;*Language*&gt; folder in the following example directory, where &lt;*Language*&gt; represents the name of the localized language:</span></span>

    <span data-ttu-id="0ebae-119">&lt;*Mbam セルフサービスインストールディレクトリ* &gt;\\ セルフサービスの Website</span><span class="sxs-lookup"><span data-stu-id="0ebae-119">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\

    <span data-ttu-id="0ebae-120">**注** 一部の言語フォルダーは既に存在するため、フォルダーを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0ebae-120">**Note** Some language folders already exist, so you might not have to create a folder.</span></span> <span data-ttu-id="0ebae-121">言語フォルダーを作成する必要がある場合は、言語フォルダーに使用できる有効な名前の一覧については、「[各国語サポート (NLS) API リファレンス](https://go.microsoft.com/fwlink/?LinkId=317947)」を参照してください &lt; *Language* &gt; 。</span><span class="sxs-lookup"><span data-stu-id="0ebae-121">If you do have to create a language folder, see [National Language Support (NLS) API Reference](https://go.microsoft.com/fwlink/?LinkId=317947) for a list of the valid names that you can use for the &lt;*Language*&gt; folder.</span></span>

     

2.  <span data-ttu-id="0ebae-122">ローカライズされた通知テキストを含む Notice.txt ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="0ebae-122">Create a Notice.txt file that contains the localized notice text.</span></span>

3.  <span data-ttu-id="0ebae-123">Notice.txt ファイルを [言語] フォルダーに保存し &lt; *Language* &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="0ebae-123">Save the Notice.txt file in the &lt;*Language*&gt; folder.</span></span> <span data-ttu-id="0ebae-124">たとえば、スペイン語でローカライズされた Notice.txt ファイルを作成するには、ローカライズされた Notice.txt ファイルを次の例のディレクトリに保存します。</span><span class="sxs-lookup"><span data-stu-id="0ebae-124">For example, to create a localized Notice.txt file in Spanish, save the localized Notice.txt file in the following example directory:</span></span>

    <span data-ttu-id="0ebae-125">&lt;*Mbam セルフサービスインストールディレクトリ* &gt;\\ セルフサービスの Website\\Es-es</span><span class="sxs-lookup"><span data-stu-id="0ebae-125">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website\\Es-es</span></span>

    <span data-ttu-id="0ebae-126">言語フォルダーの名前は、 **es\*\*\*\*の代わりに**言語のニュートラル名にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0ebae-126">The name of the Language folder can also be the language neutral name **es** instead of **es-es**.</span></span> <span data-ttu-id="0ebae-127">エンドユーザーのブラウザーが**es**に設定されていて、そのフォルダーが存在しない場合、(.net で定義されている) 親ロケールが再帰的に取得されてチェックされ、その &lt; 後、Mbam セルフサービスインストールディレクトリ &gt;\\SelfServiceWebsite\\es\\Notice.txt が、最終的に既定の Notice.txt ファイルになります。</span><span class="sxs-lookup"><span data-stu-id="0ebae-127">If the end user’s browser is set to **es-es** and that folder does not exist, the parent locale (as defined in .NET) is recursively retrieved and checked, resolving to &lt;MBAM Self-Service Install Directory&gt;\\SelfServiceWebsite\\es\\Notice.txt before finally becoming the default Notice.txt file.</span></span> <span data-ttu-id="0ebae-128">この再帰的フォールバックは、.NET リソース読み込みルールを模倣します。</span><span class="sxs-lookup"><span data-stu-id="0ebae-128">This recursive fallback mimics the .NET resource loading rules.</span></span>



## <span data-ttu-id="0ebae-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0ebae-129">Related topics</span></span>


[<span data-ttu-id="0ebae-130">組織のセルフサービス ポータルのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="0ebae-130">Customizing the Self-Service Portal for Your Organization</span></span>](customizing-the-self-service-portal-for-your-organization.md)

 

## <span data-ttu-id="0ebae-131">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="0ebae-131">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="0ebae-132">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="0ebae-132">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="0ebae-133">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="0ebae-133">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





