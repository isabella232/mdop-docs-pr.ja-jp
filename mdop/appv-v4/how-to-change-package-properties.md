---
title: パッケージのプロパティを変更する方法
description: パッケージのプロパティを変更する方法
author: dansimp
ms.assetid: 6050916a-d4fe-4dac-8f2a-47308dbbf481
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d2427a2651f3941f967c171ae7854facc62b4aa9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818044"
---
# <span data-ttu-id="b1209-103">パッケージのプロパティを変更する方法</span><span class="sxs-lookup"><span data-stu-id="b1209-103">How to Change Package Properties</span></span>


<span data-ttu-id="b1209-104">次の手順を使用して、Application Virtualization パッケージの名前とそれに関連付けられているコメントを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="b1209-104">You can use the following procedures to modify an Application Virtualization package name and its associated comments.</span></span>

<span data-ttu-id="b1209-105">パッケージを初めて作成する場合は、シーケンスのパラメーターブロックサイズを変更することもできます。これにより、シーケンス処理されたアプリケーションパッケージがアプリケーションの仮想化サーバーからアプリケーションの仮想化デスクトップクライアントにストリーミングされる方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="b1209-105">If this is the first time the package has been created, you can also change the sequencing parameter block size, which determines how a sequenced application package is streamed from an Application Virtualization Server to an Application Virtualization Desktop Client.</span></span>

<span data-ttu-id="b1209-106">**注** ブロックサイズを選択するときは、SFT ファイルのサイズとネットワーク帯域幅を考慮します。</span><span class="sxs-lookup"><span data-stu-id="b1209-106">**Note** When selecting a block size, consider the size of the SFT file and your network bandwidth.</span></span> <span data-ttu-id="b1209-107">ブロックサイズの小さいファイルはネットワーク上でのストリーミングには時間がかかりますが、帯域幅の消費も少なくありません。</span><span class="sxs-lookup"><span data-stu-id="b1209-107">A file with a smaller block size takes longer to stream over the network, but it is less bandwidth intensive.</span></span> <span data-ttu-id="b1209-108">ブロックサイズが大きいファイルは、より速くストリーミングされる可能性がありますが、より多くのネットワーク帯域幅を使用します。</span><span class="sxs-lookup"><span data-stu-id="b1209-108">Files with larger block sizes might stream faster, but they use more network bandwidth.</span></span> <span data-ttu-id="b1209-109">実験を通じて、ネットワーク上のストリーミングアプリケーションに最適なブロックサイズを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="b1209-109">Through experimentation, you can discover the optimum block size for streaming applications on your network.</span></span>

 

<span data-ttu-id="b1209-110">[**プロパティ**] タブのパッケージプロパティの残りは自動的に生成され、このタブでは変更できません。</span><span class="sxs-lookup"><span data-stu-id="b1209-110">The remainder of the package properties on the **Properties** tab is automatically generated and cannot be modified on this tab.</span></span>

**<span data-ttu-id="b1209-111">パッケージの名前またはコメントを変更するには</span><span class="sxs-lookup"><span data-stu-id="b1209-111">To change the package name or comments</span></span>**

1.  <span data-ttu-id="b1209-112">[**プロパティ**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1209-112">Click the **Properties** tab.</span></span>

2.  <span data-ttu-id="b1209-113">[**パッケージ名**] テキストボックスに、パッケージに使用する1つの名前を入力するか、編集します。複数のアプリケーションを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b1209-113">In the **Package Name** text box, enter or edit the single name used for the package, which can contain multiple applications.</span></span>

3.  <span data-ttu-id="b1209-114">[**コメント**] テキストボックスで、必要に応じてコメントを入力または編集します。</span><span class="sxs-lookup"><span data-stu-id="b1209-114">In the **Comments** text box, optionally enter or edit any comments.</span></span> <span data-ttu-id="b1209-115">推奨されるベストプラクティスは、パッケージと順序に関する詳細情報を提供することです。</span><span class="sxs-lookup"><span data-stu-id="b1209-115">The suggested best practice is to provide detail information about the package and sequencing.</span></span>

4.  <span data-ttu-id="b1209-116">[**ファイル**] メニューで、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1209-116">From the **File** menu, select **Save**.</span></span>

**<span data-ttu-id="b1209-117">ブロックサイズを変更するには</span><span class="sxs-lookup"><span data-stu-id="b1209-117">To change the block size</span></span>**

1.  <span data-ttu-id="b1209-118">[**プロパティ**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1209-118">Click the **Properties** tab.</span></span>

2.  <span data-ttu-id="b1209-119">[**ブロックサイズ**] ドロップダウンリストで、[ **4 KB**、 **16 kb**、 **32 kb**、または**64 KB**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b1209-119">On the **Block Size** drop-down list, select **4 KB**, **16 KB**, **32 KB**, or **64 KB**.</span></span>

3.  <span data-ttu-id="b1209-120">[**ファイル**] メニューで、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1209-120">From the **File** menu, select **Save**.</span></span>

## <span data-ttu-id="b1209-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b1209-121">Related topics</span></span>


[<span data-ttu-id="b1209-122">[プロパティ] タブについて</span><span class="sxs-lookup"><span data-stu-id="b1209-122">About the Properties Tab</span></span>](about-the-properties-tab.md)

[<span data-ttu-id="b1209-123">Sequencer Console</span><span class="sxs-lookup"><span data-stu-id="b1209-123">Sequencer Console</span></span>](sequencer-console.md)

 

 





