---
title: '[パッケージ アクセラレータの選択] ページ'
description: '[パッケージ アクセラレータの選択] ページ'
author: dansimp
ms.assetid: 865c2702-4dfd-41ae-8cfc-3514d5f41f76
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a5723f8244563539c27a3fa915c1a680905e61e9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815594"
---
# <span data-ttu-id="0faa3-103">[パッケージ アクセラレータの選択] ページ</span><span class="sxs-lookup"><span data-stu-id="0faa3-103">Select Package Accelerator Page</span></span>


<span data-ttu-id="0faa3-104">**[パッケージアクセラレータの選択**] ページを使用して、新しい仮想アプリケーションパッケージの作成に使用するパッケージアクセラレータを選択します。</span><span class="sxs-lookup"><span data-stu-id="0faa3-104">Use the **Select Package Accelerator** page to select the Package Accelerator that will be used to create the new virtual application package.</span></span> <span data-ttu-id="0faa3-105">パッケージアクセラレータは、App-v Sequencer を実行しているコンピューター上のフォルダーにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0faa3-105">You must copy the Package Accelerator to a folder on the computer running the App-V Sequencer.</span></span> <span data-ttu-id="0faa3-106">詳細については、「app-v[パッケージアクセラレータについて (app-v 4.6 SP1)](about-app-v-package-accelerators--app-v-46-sp1-.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0faa3-106">For more information, see [About App-V Package Accelerators (App-V 4.6 SP1)](about-app-v-package-accelerators--app-v-46-sp1-.md).</span></span>

<span data-ttu-id="0faa3-107">信頼できる発行元からのパッケージアクセラレータのみを実行します。</span><span class="sxs-lookup"><span data-stu-id="0faa3-107">Only run Package Accelerators from publishers that you trust.</span></span> <span data-ttu-id="0faa3-108">パッケージアクセラレータには、通常、デジタル署名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0faa3-108">Package Accelerators usually include a digital signature.</span></span> <span data-ttu-id="0faa3-109">デジタル署名は、ソフトウェアの発行元を示すことができる電子セキュリティマークであり、変換が最初に署名された後でパッケージが改ざんされたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0faa3-109">A digital signature is an electronic security mark that can help indicate the publisher of the software, and whether the package has been tampered with after the transform was originally signed.</span></span> <span data-ttu-id="0faa3-110">発行元によってデジタル署名されている変換を使用し、発行元が証明機関で身元を確認した場合は、その発行元からの変換であり、改変されていないという確信があります。</span><span class="sxs-lookup"><span data-stu-id="0faa3-110">If you use a transform that has been digitally signed by a publisher and the publisher has verified its identity with a certification authority, you can be more confident that the transform comes from that specific publisher and has not been altered.</span></span>

<span data-ttu-id="0faa3-111">次の条件のいずれかに該当する場合は、App-v によって通知されます。</span><span class="sxs-lookup"><span data-stu-id="0faa3-111">The App-V Sequencer notifies you if any of the following conditions are true:</span></span>

-   <span data-ttu-id="0faa3-112">選択された変換は、デジタル署名されていません。</span><span class="sxs-lookup"><span data-stu-id="0faa3-112">The selected transform has not been digitally signed.</span></span>

-   <span data-ttu-id="0faa3-113">選択した変換は、証明機関によって身元を確認していない発行元によって署名されています。</span><span class="sxs-lookup"><span data-stu-id="0faa3-113">The selected transform is signed by a publisher that has not verified its identity with a certification authority.</span></span>

-   <span data-ttu-id="0faa3-114">選択した変換は、デジタル署名され、リリースされた後に変更されています。</span><span class="sxs-lookup"><span data-stu-id="0faa3-114">The selected transform has been altered after it was digitally signed and released.</span></span>

<span data-ttu-id="0faa3-115">パッケージアクセラレータを使用してこれらのメッセージが表示された場合は、パッケージアクセラレータの publisher の web サイトにアクセスして、デジタル署名された変換のバージョンを取得してください。</span><span class="sxs-lookup"><span data-stu-id="0faa3-115">If any of these messages are displayed when using a Package Accelerators, visit the Package Accelerators publisher’s website to get a digitally signed version of the transform.</span></span>

<span data-ttu-id="0faa3-116">このページには、次の要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0faa3-116">This page contains the following elements:</span></span>

<a href="" id="browse"></a>**<span data-ttu-id="0faa3-117">閲覧</span><span class="sxs-lookup"><span data-stu-id="0faa3-117">Browse</span></span>**  
<span data-ttu-id="0faa3-118">[**参照**] をクリックして、仮想アプリケーションパッケージの作成に使うパッケージアクセラレータを指定します。</span><span class="sxs-lookup"><span data-stu-id="0faa3-118">Click **Browse** to specify the Package Accelerator that you will use to create the virtual application package.</span></span> <span data-ttu-id="0faa3-119">Sequencer を実行しているコンピューター上で、ローカルで指定したパッケージアクセラレータを保存します。</span><span class="sxs-lookup"><span data-stu-id="0faa3-119">Save the Package Accelerator you specified locally on the computer that is running the Sequencer.</span></span>

## <span data-ttu-id="0faa3-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0faa3-120">Related topics</span></span>


[<span data-ttu-id="0faa3-121">Sequencer ウィザード - パッケージ アクセラレータ (AppV 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="0faa3-121">Sequencer Wizard - Package Accelerator (AppV 4.6 SP1)</span></span>](sequencer-wizard---package-accelerator--appv-46-sp1-.md)

 

 





