---
title: '[パッケージ アクセラレータの選択] ページ (詳細情報)'
description: '[パッケージ アクセラレータの選択] ページ (詳細情報)'
author: dansimp
ms.assetid: 2db51514-8695-4b5e-b3e5-1e96e3ee4cc7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d51df0f8eb16816bacf681b1acaf4c911ee9da55
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815597"
---
# <span data-ttu-id="9e0e4-103">[パッケージ アクセラレータの選択] ページ (詳細情報)</span><span class="sxs-lookup"><span data-stu-id="9e0e4-103">Select Package Accelerator (Learn More) Page</span></span>


<span data-ttu-id="9e0e4-104">信頼できる発行元からのパッケージアクセラレータのみを実行します。</span><span class="sxs-lookup"><span data-stu-id="9e0e4-104">Only run Package Accelerators from publishers that you trust.</span></span> <span data-ttu-id="9e0e4-105">パッケージアクセラレータには、通常、デジタル署名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9e0e4-105">Package Accelerators usually include a digital signature.</span></span> <span data-ttu-id="9e0e4-106">デジタル署名は、ソフトウェアの発行元を示すことができる電子セキュリティマークであり、変換が最初に署名された後でパッケージが改ざんされていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="9e0e4-106">A digital signature is an electronic security mark that can help indicate the publisher of the software, and that the package has not been tampered with after the transform was originally signed.</span></span> <span data-ttu-id="9e0e4-107">発行元によってデジタル署名されている変換を使用し、発行元が証明機関で身元を確認した場合は、その発行元からの変換であり、改変されていないという確信があります。</span><span class="sxs-lookup"><span data-stu-id="9e0e4-107">If you use a transform that has been digitally signed by a publisher and the publisher has verified its identity with a certification authority, you can be more confident that the transform comes from that specific publisher and has not been altered.</span></span>

<span data-ttu-id="9e0e4-108">Sequencer は、次のいずれかの条件が満たされた場合に通知します。</span><span class="sxs-lookup"><span data-stu-id="9e0e4-108">The sequencer notifies you if any of the following conditions are true:</span></span>

-   <span data-ttu-id="9e0e4-109">選択された変換は、デジタル署名されていません。</span><span class="sxs-lookup"><span data-stu-id="9e0e4-109">The selected transform has not been digitally signed.</span></span>

-   <span data-ttu-id="9e0e4-110">選択した変換は、証明機関によって身元を確認していない発行元によって署名されています。</span><span class="sxs-lookup"><span data-stu-id="9e0e4-110">The selected transform is signed by a publisher that has not verified its identity with a certification authority.</span></span>

-   <span data-ttu-id="9e0e4-111">選択した変換は、デジタル署名され、リリースされた後に変更されています。</span><span class="sxs-lookup"><span data-stu-id="9e0e4-111">The selected transform has been altered after it was digitally signed and released.</span></span>

<span data-ttu-id="9e0e4-112">パッケージアクセラレータを使用してこれらのメッセージのいずれかが表示されている場合は、パッケージアクセラレータの publisher の web サイトにアクセスして、デジタル署名された変換のバージョンを取得してください。</span><span class="sxs-lookup"><span data-stu-id="9e0e4-112">If any of these messages are displayed when using a Package Accelerator, visit the Package Accelerators publisher’s website to get a digitally signed version of the transform.</span></span>

## <span data-ttu-id="9e0e4-113">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9e0e4-113">Related topics</span></span>


[<span data-ttu-id="9e0e4-114">Sequencer ウィザード - パッケージ アクセラレータ (AppV 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="9e0e4-114">Sequencer Wizard - Package Accelerator (AppV 4.6 SP1)</span></span>](sequencer-wizard---package-accelerator--appv-46-sp1-.md)

 

 





