---
title: 非接続操作モード設定を無効化または変更する方法
description: 非接続操作モード設定を無効化または変更する方法
author: dansimp
ms.assetid: 39f166d7-2d25-4899-8405-b45f051facb8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 288c35c8d43352037c8514b4c060e847b456267c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817484"
---
# <span data-ttu-id="79c3c-103">非接続操作モード設定を無効化または変更する方法</span><span class="sxs-lookup"><span data-stu-id="79c3c-103">How to Disable or Modify Disconnected Operation Mode Settings</span></span>


<span data-ttu-id="79c3c-104">切断された操作モードの設定を無効または変更するには、Application Virtualization クライアントで次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="79c3c-104">Use the following procedures in Application Virtualization Client to disable or modify disconnected operation mode settings.</span></span>

**<span data-ttu-id="79c3c-105">切断操作を無効にするには</span><span class="sxs-lookup"><span data-stu-id="79c3c-105">To disable disconnected operation</span></span>**

1.  <span data-ttu-id="79c3c-106">コンソールで [ **Application Virtualization** ] ノードを右クリックし、ポップアップメニューから [**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79c3c-106">Right-click the **Application Virtualization** node in the console, and select **Properties** from the pop-up menu.</span></span>

2.  <span data-ttu-id="79c3c-107">[**接続**] タブをクリックし、[切断された**操作を許可する**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="79c3c-107">Click the **Connectivity** tab, and then clear **Allow disconnected operation** check box.</span></span>

3.  <span data-ttu-id="79c3c-108">[ **OK]** をクリックして変更を確定します。</span><span class="sxs-lookup"><span data-stu-id="79c3c-108">Click **OK** to accept the change.</span></span>

**<span data-ttu-id="79c3c-109">タイムアウトを変更するには</span><span class="sxs-lookup"><span data-stu-id="79c3c-109">To change the time-out</span></span>**

1.  <span data-ttu-id="79c3c-110">コンソールで [ **Application Virtualization** ] ノードを右クリックし、ポップアップメニューから [**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79c3c-110">Right-click the **Application Virtualization** node in the console, and select **Properties** from the pop-up menu.</span></span>

2.  <span data-ttu-id="79c3c-111">[**接続**] タブをクリックし、[**切断操作を制限する**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="79c3c-111">Click the **Connectivity** tab, and then select the **Limit disconnected operation to** check box.</span></span>

3.  <span data-ttu-id="79c3c-112">フィールドに、1 ~ 999999 (日数を表す) の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="79c3c-112">In the field, enter a value from 1–999999 (representing days).</span></span> <span data-ttu-id="79c3c-113">既定値は90日です。</span><span class="sxs-lookup"><span data-stu-id="79c3c-113">The default value is 90 days.</span></span>

4.  <span data-ttu-id="79c3c-114">[ **OK]** をクリックして変更を確定します。</span><span class="sxs-lookup"><span data-stu-id="79c3c-114">Click **OK** to accept the change.</span></span>

**<span data-ttu-id="79c3c-115">オフラインで作業するには</span><span class="sxs-lookup"><span data-stu-id="79c3c-115">To work offline</span></span>**

1.  <span data-ttu-id="79c3c-116">コンソールで [ **Application Virtualization** ] ノードを右クリックし、ポップアップメニューから [**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="79c3c-116">Right-click the **Application Virtualization** node in the console, and select **Properties** from the pop-up menu.</span></span>

2.  <span data-ttu-id="79c3c-117">[**接続**] タブをクリックし、[**オフライン作業**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="79c3c-117">Click the **Connectivity** tab, and then select the **Work offline** check box.</span></span>

3.  <span data-ttu-id="79c3c-118">[ **OK]** をクリックして変更を確定します。</span><span class="sxs-lookup"><span data-stu-id="79c3c-118">Click **OK** to accept the change.</span></span>

## <span data-ttu-id="79c3c-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="79c3c-119">Related topics</span></span>


[<span data-ttu-id="79c3c-120">非接続操作モード</span><span class="sxs-lookup"><span data-stu-id="79c3c-120">Disconnected Operation Mode</span></span>](disconnected-operation-mode.md)

[<span data-ttu-id="79c3c-121">Application Virtualization をオフラインまたはオンラインで作業する方法</span><span class="sxs-lookup"><span data-stu-id="79c3c-121">How to Work Offline or Online with Application Virtualization</span></span>](how-to-work-offline-or-online-with-application-virtualization.md)

 

 





