---
title: App-V 5.0 SP1 の新機能
description: App-V 5.0 SP1 の新機能
author: dansimp
ms.assetid: e97c2dbb-7b40-46a0-8137-9ee4fc2bd071
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2542d0cc5a544d26b3279b24063cf3ef428b9f39
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813218"
---
# <span data-ttu-id="04023-103">App-V 5.0 SP1 の新機能</span><span class="sxs-lookup"><span data-stu-id="04023-103">What's new in App-V 5.0 SP1</span></span>


<span data-ttu-id="04023-104">このセクションは、既に App-v に精通していて、App-v 5.0 SP1 の変更内容を確認したいユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="04023-104">This section is for users who are already familiar with App-V and want to know what has changed in App-V 5.0 SP1.</span></span> <span data-ttu-id="04023-105">まだ App-v に精通していない場合は、まず「 [app-v 5.0 の計画](planning-for-app-v-50-rc.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04023-105">If you are not already familiar with App-V, you should start by reading [Planning for App-V 5.0](planning-for-app-v-50-rc.md).</span></span>

## <span data-ttu-id="04023-106">標準機能の変更点</span><span class="sxs-lookup"><span data-stu-id="04023-106">Changes in Standard Functionality</span></span>


<span data-ttu-id="04023-107">以下のセクションでは、App-v 5.0 SP1 の標準機能の変更に関する情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="04023-107">The following sections contain information about the changes in standard functionality for App-V 5.0 SP1.</span></span>

### <span data-ttu-id="04023-108">サポートされている言語に対する変更</span><span class="sxs-lookup"><span data-stu-id="04023-108">Changes to Supported Languages</span></span>

<span data-ttu-id="04023-109">詳細については、「 [app-v 5.0 SP1 につい](about-app-v-50-sp1.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04023-109">For more information, see [About App-V 5.0 SP1](about-app-v-50-sp1.md).</span></span>

<span data-ttu-id="04023-110">新しい言語パックの詳細については、次の一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04023-110">The following list contains more information about the new Language Packs:</span></span>

-   <span data-ttu-id="04023-111">App-v 5.0 SP1 言語パックは、すべての App-v 5.0 コンポーネントの**appv\_xxx\_setup.exe**インストーラーにバンドルされています。</span><span class="sxs-lookup"><span data-stu-id="04023-111">The App-V 5.0SP1 language packs are bundled into the **appv\_xxx\_setup.exe** installer for all the App-V 5.0 Components.</span></span>

-   <span data-ttu-id="04023-112">インストーラーを実行すると、対象のコンピューターで実行されている関連オペレーティングシステムのロケールに基づいて、適切な言語パックが自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="04023-112">When you run the installer it will automatically install the most appropriate language pack based on the locale of the associated operating system running on the target computer.</span></span>

-   <span data-ttu-id="04023-113">追加の言語パックが必要な場合は、次のコマンドを実行して、インストーラーからこれらの言語パックを抽出する必要があり `appv_xxx_setup.exe /Layout /LayoutDir=”<path>”` ます。</span><span class="sxs-lookup"><span data-stu-id="04023-113">If additional language packs are required, you must extract these language packs from the installer by running the following command: `appv_xxx_setup.exe /Layout /LayoutDir=”<path>”`.</span></span> <span data-ttu-id="04023-114">これを実行すると、インストーラーの内容が指定した場所に抽出されます。</span><span class="sxs-lookup"><span data-stu-id="04023-114">After this has been run, the contents of the installer are extracted to the specified location.</span></span>

-   <span data-ttu-id="04023-115">適切な言語パックの Windows インストールファイルを適用して、目的の言語パックをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04023-115">You must install the desired language pack by applying the appropriate Language pack Windows Installation file.</span></span> <span data-ttu-id="04023-116">たとえば、 **appv\_hib\_LP\_jmmb\_x86.msi**や**appv\_hib\_LP\_jmmb\_x64.msi**では、 **hib**はコンポーネントを指し、 **jmmb**はロケールを指します。</span><span class="sxs-lookup"><span data-stu-id="04023-116">For example, **appv\_hib\_LP\_jmmb\_x86.msi** or **appv\_hib\_LP\_jmmb\_x64.msi**, where **hib** refers to the component and **jmmb** refers to the locale.</span></span>

## <span data-ttu-id="04023-117">Microsoft 表紙の強化されたサポート</span><span class="sxs-lookup"><span data-stu-id="04023-117">Enhanced Support for Microsoft Office2010</span></span>


<span data-ttu-id="04023-118">**アプリケーションの仮想5.0 化用 Microsoft Office 2010 シーケンスキット**–ユーザーに対して、仮想化されたバージョンの Microsoft 表紙を使用した一貫したエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="04023-118">**Microsoft Office 2010 Sequencing Kit for Application Virtualization 5.0** – helps provide users with a consistent experience using a virtualized version of Microsoft Office2010.</span></span> <span data-ttu-id="04023-119">**Application Virtualization 5.0 用の Microsoft office 2010 シーケンスキット**は、 **Microsoft Office 2010 展開キット (app-v)** と組み合わせて使用されるほか、必要な microsoft 表紙ライセンスサービスも提供します。</span><span class="sxs-lookup"><span data-stu-id="04023-119">The **Microsoft Office 2010 Sequencing Kit for Application Virtualization 5.0** is used in conjunction with the **Microsoft Office 2010 Deployment Kit for App-V** and also provides the required Microsoft Office2010 licensing service.</span></span>






## <span data-ttu-id="04023-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="04023-120">Related topics</span></span>


[<span data-ttu-id="04023-121">App-V 5.0 について</span><span class="sxs-lookup"><span data-stu-id="04023-121">About App-V 5.0</span></span>](about-app-v-50.md)

 

 





