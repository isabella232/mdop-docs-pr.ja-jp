---
title: セルフサービス ポータルの "HelpdeskURL" をローカライズする方法
description: セルフサービス ポータルの "HelpdeskURL" をローカライズする方法
author: dansimp
ms.assetid: 86798460-077b-459b-8d54-4b605e07d2f1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0d7ec4ce87bbe5aab56e9fa877ced5f51625a5dc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826707"
---
# <span data-ttu-id="6d87c-103">セルフサービス ポータルの "HelpdeskURL" をローカライズする方法</span><span class="sxs-lookup"><span data-stu-id="6d87c-103">How to Localize the Self-Service Portal “HelpdeskURL”</span></span>


<span data-ttu-id="6d87c-104">既定でエンドユーザーに表示するセルフサービスポータル URL のローカライズされたバージョンを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="6d87c-104">You can configure a localized version of the Self-Service Portal URL to display to end users by default.</span></span> <span data-ttu-id="6d87c-105">セルフサービスポータル URL は、パラメーター **Helpデスク url**で表されます。</span><span class="sxs-lookup"><span data-stu-id="6d87c-105">The Self-Service Portal URL is represented by the parameter **HelpdeskURL**.</span></span>

<span data-ttu-id="6d87c-106">次の手順で説明するように、ローカライズされたバージョンを作成すると、Microsoft BitLocker の管理と監視 (MBAM) でローカライズされたバージョンが検索されて表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d87c-106">If you create a localized version, as described in the following instructions, Microsoft BitLocker Administration and Monitoring (MBAM) finds and displays the localized version.</span></span> <span data-ttu-id="6d87c-107">MBAM でローカライズされたバージョンが見つからない場合は、パラメーター **Helpデスク url**に対して構成されている url が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d87c-107">If MBAM does not find a localized version, it displays the URL that is configured for the parameter **HelpDeskURL**.</span></span>

<span data-ttu-id="6d87c-108">**注** 次の手順では、 *selfservice*がセルフサービスポータルの既定の仮想ディレクトリ名です。</span><span class="sxs-lookup"><span data-stu-id="6d87c-108">**Note** In the following instructions, *SelfService* is the default virtual directory name for the Self-Service Portal.</span></span> <span data-ttu-id="6d87c-109">セルフサービスポータルを構成したときに、別の名前が使用されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6d87c-109">You might have used a different name when you configured the Self-Service Portal.</span></span>

 

**<span data-ttu-id="6d87c-110">セルフサービスポータル URL をローカライズするには</span><span class="sxs-lookup"><span data-stu-id="6d87c-110">To localize the Self-Service Portal URL</span></span>**

1.  <span data-ttu-id="6d87c-111">セルフサービスポータルを構成したサーバーで、[**サイト**の管理]、[ &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **サービス** &gt; **アプリケーション設定**の監視] の各サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="6d87c-111">On the server where you configured the Self-Service Portal, browse to **Sites** &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **SelfService** &gt; **Application Settings**.</span></span>

2.  <span data-ttu-id="6d87c-112">[**操作**] ウィンドウの [**追加**] をクリックして、[**アプリケーション設定の追加**] ダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="6d87c-112">In the **Actions** pane, click **Add** to open the **Add Application Setting** dialog box.</span></span>

3.  <span data-ttu-id="6d87c-113">[**名前**] フィールドに「**ヘルプ**」と入力し &lt; *Language* &gt; ます。ここで、 &lt; *言語* &gt; は url の適切な言語コードです。</span><span class="sxs-lookup"><span data-stu-id="6d87c-113">In the **Name** field, type **HelpdeskURL**\_&lt;*Language*&gt;, where &lt;*Language*&gt; is the appropriate language code for the URL.</span></span>

    <span data-ttu-id="6d87c-114">たとえば、スペイン語でローカライズされた値のローカライズされたバージョンを作成するには、 `HelpdeskURL` パラメーターに「**ヘルプデスク url \ _es**という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d87c-114">For example, to create a localized version of the `HelpdeskURL` value in Spanish, name the parameter **HelpdeskURL\_es-es**.</span></span>

    <span data-ttu-id="6d87c-115">言語フォルダーの名前は、 **es\*\*\*\*の代わりに**言語のニュートラル名にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6d87c-115">The name of the Language folder can also be the language neutral name **es** instead of **es-es**.</span></span> <span data-ttu-id="6d87c-116">エンドユーザーのブラウザーが**es**に設定されていて、そのフォルダーが存在しない場合、(.net で定義されている) 親ロケールが再帰的に取得されてチェックされ、その &lt; 後、Mbam セルフサービスインストールディレクトリ &gt;\\SelfServiceWebsite\\es\\Notice.txt が、最終的に既定の Notice.txt ファイルになります。</span><span class="sxs-lookup"><span data-stu-id="6d87c-116">If the end user’s browser is set to **es-es** and that folder does not exist, the parent locale (as defined in .NET) is recursively retrieved and checked, resolving to &lt;MBAM Self-Service Install Directory&gt;\\SelfServiceWebsite\\es\\Notice.txt before finally becoming the default Notice.txt file.</span></span> <span data-ttu-id="6d87c-117">この再帰的フォールバックは、.NET リソース読み込みルールを模倣します。</span><span class="sxs-lookup"><span data-stu-id="6d87c-117">This recursive fallback mimics the .NET resource loading rules.</span></span>

    <span data-ttu-id="6d87c-118">使用できる有効な言語コードの一覧については、「[各国語サポート (NLS) API リファレンス](https://go.microsoft.com/fwlink/?LinkId=317947)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6d87c-118">For a list of the valid language codes you can use, see [National Language Support (NLS) API Reference](https://go.microsoft.com/fwlink/?LinkId=317947).</span></span>

4.  <span data-ttu-id="6d87c-119">[**値**] フィールドに、エンドユーザーに対して表示するローカライズされたバージョンの値を入力し `HelpdeskURL` ます。</span><span class="sxs-lookup"><span data-stu-id="6d87c-119">In the **Value** field, type the localized version of the `HelpdeskURL` value that you want to display to end users.</span></span>



## <span data-ttu-id="6d87c-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6d87c-120">Related topics</span></span>


[<span data-ttu-id="6d87c-121">組織のセルフサービス ポータルのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="6d87c-121">Customizing the Self-Service Portal for Your Organization</span></span>](customizing-the-self-service-portal-for-your-organization.md)

 

 
## <span data-ttu-id="6d87c-122">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="6d87c-122">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="6d87c-123">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="6d87c-123">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="6d87c-124">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="6d87c-124">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




