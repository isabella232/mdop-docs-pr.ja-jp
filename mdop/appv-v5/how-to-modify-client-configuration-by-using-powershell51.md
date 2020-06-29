---
title: PowerShell を使用してクライアント構成を変更する方法
description: PowerShell を使用してクライアント構成を変更する方法
author: dansimp
ms.assetid: c3a59592-bb0d-43b6-8f4e-44f3a2d5b7ea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 368a0d12c12e10a623afad3f9040ae01cee6cb38
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813811"
---
# <span data-ttu-id="70d7b-103">PowerShell を使用してクライアント構成を変更する方法</span><span class="sxs-lookup"><span data-stu-id="70d7b-103">How to Modify Client Configuration by Using PowerShell</span></span>


<span data-ttu-id="70d7b-104">次の手順を使用して、App-v 5.1 クライアント構成を構成します。</span><span class="sxs-lookup"><span data-stu-id="70d7b-104">Use the following procedure to configure the App-V 5.1 client configuration.</span></span>

**<span data-ttu-id="70d7b-105">PowerShell を使用して App-v 5.1 クライアント構成を変更するには</span><span class="sxs-lookup"><span data-stu-id="70d7b-105">To modify App-V 5.1 client configuration using PowerShell</span></span>**

1.  <span data-ttu-id="70d7b-106">PowerShell を使用してクライアント設定を構成するには、 **AppvClientConfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="70d7b-106">To configure the client settings using PowerShell, use the **Set-AppvClientConfiguration** cmdlet.</span></span> <span data-ttu-id="70d7b-107">PowerShell のインストールの詳細とコマンドレットの一覧については、「 [Powershell コマンドレットを読み込み、コマンドレットのヘルプを取得する方法](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-51.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70d7b-107">For more information about installing PowerShell, and a list of cmdlets see, [How to Load the PowerShell Cmdlets and Get Cmdlet Help](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-51.md).</span></span>

2.  <span data-ttu-id="70d7b-108">クライアント構成を変更するには、PowerShell コマンドプロンプトを開き、必要なパラメーターを指定して次のコマンドレット**AppvClientConfiguration**を実行します。</span><span class="sxs-lookup"><span data-stu-id="70d7b-108">To modify the client configuration, open a PowerShell Command prompt and run the following cmdlet **Set-AppvClientConfiguration** with any required parameters.</span></span> <span data-ttu-id="70d7b-109">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="70d7b-109">For example:</span></span>

    `$config = Get-AppvClientConfiguration`

    `Set-AppvClientConfiguration $config`

    `Set-AppvClientConfiguration –AutoLoad 2`

    <span data-ttu-id="70d7b-110">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="70d7b-110">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="70d7b-111">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="70d7b-111">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="70d7b-112">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="70d7b-112">Got an App-V issue?</span></span>** <span data-ttu-id="70d7b-113">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="70d7b-113">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="70d7b-114">関連トピック</span><span class="sxs-lookup"><span data-stu-id="70d7b-114">Related topics</span></span>


[<span data-ttu-id="70d7b-115">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="70d7b-115">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





