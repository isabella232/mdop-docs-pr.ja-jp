---
title: PowerShell を使用してクライアント構成を変更する方法
description: PowerShell を使用してクライアント構成を変更する方法
author: dansimp
ms.assetid: 53ccb2cf-ef81-4310-a853-efcb395f006e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b5d3173944abfe2c2b3d30aa9654dae81f204a32
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813827"
---
# <span data-ttu-id="54bcc-103">PowerShell を使用してクライアント構成を変更する方法</span><span class="sxs-lookup"><span data-stu-id="54bcc-103">How to Modify Client Configuration by Using PowerShell</span></span>


<span data-ttu-id="54bcc-104">次の手順を使用して、App-v 5.0 クライアント構成を構成します。</span><span class="sxs-lookup"><span data-stu-id="54bcc-104">Use the following procedure to configure the App-V 5.0 client configuration.</span></span>

**<span data-ttu-id="54bcc-105">PowerShell を使用して App-v 5.0 クライアント構成を変更するには</span><span class="sxs-lookup"><span data-stu-id="54bcc-105">To modify App-V 5.0 client configuration using PowerShell</span></span>**

1.  <span data-ttu-id="54bcc-106">PowerShell を使用してクライアント設定を構成するには、 **AppvClientConfiguration**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="54bcc-106">To configure the client settings using PowerShell, use the **Set-AppvClientConfiguration** cmdlet.</span></span>

2.  <span data-ttu-id="54bcc-107">クライアント構成を変更するには、PowerShell コマンドプロンプトを開き、必要なパラメーターを指定して次のコマンドレット**AppvClientConfiguration**を実行します。</span><span class="sxs-lookup"><span data-stu-id="54bcc-107">To modify the client configuration, open a PowerShell Command prompt and run the following cmdlet **Set-AppvClientConfiguration** with any required parameters.</span></span> <span data-ttu-id="54bcc-108">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="54bcc-108">For example:</span></span>

    `$config = Get-AppvClientConfiguration`

    `Set-AppvClientConfiguration $config`

    `Set-AppvClientConfiguration –AutoLoad 2`

    <span data-ttu-id="54bcc-109">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="54bcc-109">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="54bcc-110">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="54bcc-110">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="54bcc-111">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="54bcc-111">Got an App-V issue?</span></span>** <span data-ttu-id="54bcc-112">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="54bcc-112">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="54bcc-113">関連トピック</span><span class="sxs-lookup"><span data-stu-id="54bcc-113">Related topics</span></span>


[<span data-ttu-id="54bcc-114">APP-V 5.0 の操作</span><span class="sxs-lookup"><span data-stu-id="54bcc-114">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





