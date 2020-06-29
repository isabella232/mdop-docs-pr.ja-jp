---
title: 順序を指定するアプリケーションの種類を決定する方法 (App-v 4.6 SP1)
description: 順序を指定するアプリケーションの種類を決定する方法 (App-v 4.6 SP1)
author: dansimp
ms.assetid: 936abee2-98f1-45fb-9f0d-786e1d7464b1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 001f6afa36ca28eb1b8e0cc2ccc161cef4194d24
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817487"
---
# <span data-ttu-id="14dc4-103">順序を指定するアプリケーションの種類を決定する方法 (App-v 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="14dc4-103">How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)</span></span>


<span data-ttu-id="14dc4-104">Microsoft Application Virtualization (App-v) Sequencer を使用して、3種類の基本的なアプリケーションをシーケンスできます。</span><span class="sxs-lookup"><span data-stu-id="14dc4-104">You can sequence three basic types of applications by using Microsoft Application Virtualization (App-V) Sequencer.</span></span>

## <span data-ttu-id="14dc4-105">順序を指定するアプリケーションの種類を決定するには</span><span class="sxs-lookup"><span data-stu-id="14dc4-105">To determine which type of application to sequence</span></span>


<span data-ttu-id="14dc4-106">次の表を使用して、どの種類のアプリケーションを順序指定するかを決定し、アプリケーションの順序を指定する方法についての詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="14dc4-106">Use the following table to determine which type of application you should sequence and to obtain more information about how to sequence the application.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="14dc4-107">アプリケーションの種類</span><span class="sxs-lookup"><span data-stu-id="14dc4-107">Application Type</span></span></th>
<th align="left"><span data-ttu-id="14dc4-108">説明</span><span class="sxs-lookup"><span data-stu-id="14dc4-108">Description</span></span></th>
<th align="left"><span data-ttu-id="14dc4-109">詳細情報</span><span class="sxs-lookup"><span data-stu-id="14dc4-109">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="14dc4-110">標準</span><span class="sxs-lookup"><span data-stu-id="14dc4-110">Standard</span></span></p></td>
<td align="left"><p><span data-ttu-id="14dc4-111">アプリケーションまたはアプリケーションスイートを含むパッケージを作成するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="14dc4-111">Select this option to create a package that contains an application or a suite of applications.</span></span> <span data-ttu-id="14dc4-112">順序を設定するほとんどのアプリケーションには、このオプションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14dc4-112">You should select this option for most applications that you plan to sequence.</span></span></p></td>
<td align="left"><p><a href="how-to-sequence-a-new-standard-application--app-v-46-sp1-.md" data-raw-source="[How to Sequence a New Standard Application (App-V 4.6 SP1)](how-to-sequence-a-new-standard-application--app-v-46-sp1-.md)"><span data-ttu-id="14dc4-113">新しい標準アプリケーションをシーケンス処理する方法 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="14dc4-113">How to Sequence a New Standard Application (App-V 4.6 SP1)</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="14dc4-114">アドオンまたはプラグイン</span><span class="sxs-lookup"><span data-stu-id="14dc4-114">Add-on or Plug-in</span></span></p></td>
<td align="left"><p><span data-ttu-id="14dc4-115">このオプションは、Microsoft Excel のプラグインなど、標準アプリケーションの機能を拡張するパッケージを作成する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="14dc4-115">Select this option to create a package that extends the functionality of a standard application, for example, a plug-in for Microsoft Excel.</span></span> <span data-ttu-id="14dc4-116">さらに、ネイティブにインストールされているアプリケーション、または動的なスイートコンポジションを使ってリンクされている別のパッケージのプラグインを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="14dc4-116">Additionally, you can use plug-ins for natively installed applications, or another package that is linked by using Dynamic Suite Composition.</span></span> <span data-ttu-id="14dc4-117">動的なスイートコンポジションの詳細については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="[How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkId=203804)"> 動的なスイートコンポジション </a> () の使い方」を参照してください <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=203804"> https://go.microsoft.com/fwlink/?LinkId=203804 </a> 。</span><span class="sxs-lookup"><span data-stu-id="14dc4-117">For more information about Dynamic Suite Composition, see <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="[How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkId=203804)">How To Use Dynamic Suite Composition</a> (<a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=203804">https://go.microsoft.com/fwlink/?LinkId=203804</a>).</span></span></p></td>
<td align="left"><p><a href="how-to-sequence-a-new-add-on-or-plug-in-application--app-v-46-sp1-.md" data-raw-source="[How to Sequence a New Add-on or Plug-in Application (App-V 4.6 SP1)](how-to-sequence-a-new-add-on-or-plug-in-application--app-v-46-sp1-.md)"><span data-ttu-id="14dc4-118">新しいアドオンまたはプラグイン アプリケーションをシーケンス処理する方法 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="14dc4-118">How to Sequence a New Add-on or Plug-in Application (App-V 4.6 SP1)</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="14dc4-119">ミドルウェア</span><span class="sxs-lookup"><span data-stu-id="14dc4-119">Middleware</span></span></p></td>
<td align="left"><p><span data-ttu-id="14dc4-120">標準アプリケーション (Microsoft .NET Framework など) で必要なパッケージを作成するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="14dc4-120">Select this option to create a package that is required by a standard application, for example, the Microsoft .NET Framework.</span></span> <span data-ttu-id="14dc4-121">ミドルウェアパッケージは、動的スイートコンポジションを使用して他のパッケージにリンクするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="14dc4-121">Middleware packages are used for linking to other packages by using Dynamic Suite Composition.</span></span> <span data-ttu-id="14dc4-122">動的なスイートコンポジションの詳細については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="[How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkId=203804)"> 動的なスイートコンポジション </a> () の使い方」を参照してください <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=203804"> https://go.microsoft.com/fwlink/?LinkId=203804 </a> 。</span><span class="sxs-lookup"><span data-stu-id="14dc4-122">For more information about Dynamic Suite Composition, see <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="[How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkId=203804)">How To Use Dynamic Suite Composition</a> (<a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=203804">https://go.microsoft.com/fwlink/?LinkId=203804</a>).</span></span></p></td>
<td align="left"><p><a href="how-to-sequence-a-new-middleware-application--app-v-46-sp1-.md" data-raw-source="[How to Sequence a New Middleware Application (App-V 4.6 SP1)](how-to-sequence-a-new-middleware-application--app-v-46-sp1-.md)"><span data-ttu-id="14dc4-123">新しいミドルウェア アプリケーションをシーケンス処理する方法 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="14dc4-123">How to Sequence a New Middleware Application (App-V 4.6 SP1)</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="14dc4-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="14dc4-124">Related topics</span></span>


[<span data-ttu-id="14dc4-125">Application Virtualization Sequencer のタスク (APP-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="14dc4-125">Tasks for the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

 

 





