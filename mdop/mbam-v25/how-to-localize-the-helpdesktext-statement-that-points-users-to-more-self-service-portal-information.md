---
title: ユーザーがセルフサービス ポータルの情報にさらに注目するように HelpdeskText ステートメントをローカライズする方法
description: ユーザーがセルフサービス ポータルの情報にさらに注目するように HelpdeskText ステートメントをローカライズする方法
author: dansimp
ms.assetid: 09ba2a07-3186-45d9-adef-4034c70ae7cf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2367424185da813a46fa52f3614c03083864f75f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823424"
---
# <span data-ttu-id="6d759-103">ユーザーがセルフサービス ポータルの情報にさらに注目するように HelpdeskText ステートメントをローカライズする方法</span><span class="sxs-lookup"><span data-stu-id="6d759-103">How to Localize the “HelpdeskText” Statement that Points Users to More Self-Service Portal Information</span></span>


<span data-ttu-id="6d759-104">自分がセルフサービスポータルを使用しているときに追加のヘルプを取得する方法について、エンドユーザーに通知する、ローカライズされたバージョンのセルフサービスポータル "Helpデスク Text" ステートメントを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="6d759-104">You can configure a localized version of the Self-Service Portal "HelpdeskText" statement, which informs end users about how to get additional help when they are using the Self-Service Portal.</span></span> <span data-ttu-id="6d759-105">以下の手順で説明するように、ステートメントのローカライズされたテキストを構成すると、MBAM でローカライズされたバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d759-105">If you configure localized text for the statement, as described in the following instructions, MBAM displays the localized version.</span></span> <span data-ttu-id="6d759-106">MBAM でローカライズされたバージョンが見つからない場合は、 **Helpデスクテキスト**パラメーターの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d759-106">If MBAM does not find the localized version, it displays the value that is in the **HelpdeskText** parameter.</span></span>

<span data-ttu-id="6d759-107">**注** 次の手順では、 *selfservice*がセルフサービスポータルの既定の仮想ディレクトリ名です。</span><span class="sxs-lookup"><span data-stu-id="6d759-107">**Note** In the following instructions, *SelfService* is the default virtual directory name for the Self-Service Portal.</span></span> <span data-ttu-id="6d759-108">セルフサービスポータルを構成したときに、別の名前が使用されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6d759-108">You might have used a different name when you configured the Self-Service Portal.</span></span>

 

**<span data-ttu-id="6d759-109">Helpデスクテキストステートメントのローカライズされたバージョンを表示するには</span><span class="sxs-lookup"><span data-stu-id="6d759-109">To display a localized version of the HelpdeskText statement</span></span>**

1.  <span data-ttu-id="6d759-110">セルフサービスポータルを構成したサーバーで、[**サイト**の管理]、[ &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **サービス** &gt; **アプリケーション設定**の監視] の各サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="6d759-110">On the server where you configured the Self-Service Portal, browse to **Sites** &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **SelfService** &gt; **Application Settings**.</span></span>

2.  <span data-ttu-id="6d759-111">[**操作**] ウィンドウの [**追加**] をクリックして、[**アプリケーション設定の追加**] ダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="6d759-111">In the **Actions** pane, click **Add** to open the **Add Application Setting** dialog box.</span></span>

3.  <span data-ttu-id="6d759-112">[**名前**] フィールドに「**ヘルプ**」と入力し &lt; *Language* &gt; ます。ここで、 &lt; *言語* &gt; は、テキストの適切な言語コードです。</span><span class="sxs-lookup"><span data-stu-id="6d759-112">In the **Name** field, type **HelpdeskText**\_&lt;*Language*&gt;, where &lt;*Language*&gt; is the appropriate language code for the text.</span></span>

    <span data-ttu-id="6d759-113">たとえば、スペイン語でヘルプデスクのローカライズされたテキストステートメントを作成するには、パラメーターとして「 **\ _es**」という名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6d759-113">For example, to create a localized HelpdeskText statement in Spanish, name the parameter **HelpdeskText\_es-es**.</span></span>

    <span data-ttu-id="6d759-114">言語フォルダーの名前は、 **es\*\*\*\*の代わりに**言語のニュートラル名にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6d759-114">The name of the Language folder can also be the language neutral name **es** instead of **es-es**.</span></span> <span data-ttu-id="6d759-115">エンドユーザーのブラウザーが**es**に設定されていて、そのフォルダーが存在しない場合、(.net で定義されている) 親ロケールが再帰的に取得されてチェックされ、その &lt; 後、Mbam セルフサービスインストールディレクトリ &gt;\\SelfServiceWebsite\\es\\Notice.txt が、最終的に既定の Notice.txt ファイルになります。</span><span class="sxs-lookup"><span data-stu-id="6d759-115">If the end user’s browser is set to **es-es** and that folder does not exist, the parent locale (as defined in .NET) is recursively retrieved and checked, resolving to &lt;MBAM Self-Service Install Directory&gt;\\SelfServiceWebsite\\es\\Notice.txt before finally becoming the default Notice.txt file.</span></span> <span data-ttu-id="6d759-116">この再帰的フォールバックは、.NET リソース読み込みルールを模倣します。</span><span class="sxs-lookup"><span data-stu-id="6d759-116">This recursive fallback mimics the .NET resource loading rules.</span></span>

    <span data-ttu-id="6d759-117">使用できる有効な言語コードの一覧については、「[各国語サポート (NLS) API リファレンス](https://go.microsoft.com/fwlink/?LinkId=317947)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6d759-117">For a list of the valid language codes you can use, see [National Language Support (NLS) API Reference](https://go.microsoft.com/fwlink/?LinkId=317947).</span></span>

4.  <span data-ttu-id="6d759-118">[**値**] フィールドに、エンドユーザーに対して表示するローカライズされたテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="6d759-118">In the **Value** field, type the localized text that you want to display to end users.</span></span>



## <span data-ttu-id="6d759-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6d759-119">Related topics</span></span>


[<span data-ttu-id="6d759-120">組織のセルフサービス ポータルのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="6d759-120">Customizing the Self-Service Portal for Your Organization</span></span>](customizing-the-self-service-portal-for-your-organization.md)

 

 

## <span data-ttu-id="6d759-121">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="6d759-121">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="6d759-122">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="6d759-122">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="6d759-123">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="6d759-123">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>



