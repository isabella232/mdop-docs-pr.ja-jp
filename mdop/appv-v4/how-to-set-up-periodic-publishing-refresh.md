---
title: 定期的な公開の更新をセットアップする方法
description: 定期的な公開の更新をセットアップする方法
author: dansimp
ms.assetid: c358c765-cb88-4881-b4e7-0a2e87304870
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a5bbea1c661d6cb5a78f0bb9de29538e0222cda6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816554"
---
# <span data-ttu-id="639fc-103">定期的な公開の更新をセットアップする方法</span><span class="sxs-lookup"><span data-stu-id="639fc-103">How to Set Up Periodic Publishing Refresh</span></span>


<span data-ttu-id="639fc-104">次の手順を使用して、アプリ-V サーバーから公開情報を定期的に更新するようにクライアントを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="639fc-104">You can use the following procedure to configure the client to periodically refresh the publishing information from the App-V servers.</span></span> <span data-ttu-id="639fc-105">クライアントが構成されると、更新操作は自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="639fc-105">After the client is configured, the refresh operation is automatic.</span></span> <span data-ttu-id="639fc-106">これらの設定では、このコンピューターのすべてのユーザーに同じ設定が表示されるように、クライアントの既定の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="639fc-106">These settings configure the default settings for the client so that all users on this computer will see the same settings.</span></span>

<span data-ttu-id="639fc-107">**注** この手順を実行すると、ログイン時の最初の更新後に、新しい設定に応じて発行情報が更新されます。</span><span class="sxs-lookup"><span data-stu-id="639fc-107">**Note** After you have performed this procedure, the publishing information will be refreshed according to the new settings after the first refresh at login.</span></span> <span data-ttu-id="639fc-108">この最初の更新が行われると、構成方法に応じて、サーバーがさまざまな設定でコンピューターの設定を上書きする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="639fc-108">When this first refresh occurs, the server might override the computer settings with different settings, depending on how it is configured.</span></span> <span data-ttu-id="639fc-109">[**プロパティ**] ダイアログボックスの [**更新**] タブには、ローカルで構成されているクライアントコンピューターの設定と、発行サーバーによってユーザーに対して構成されている可能性があるすべての設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="639fc-109">The **Refresh** tab in the **Properties** dialog box shows the locally configured client computer settings and any settings that might have been configured for the user by the publishing server.</span></span>

 

**<span data-ttu-id="639fc-110">アプリケーションの仮想化サーバーから定期的に発行情報を更新するには</span><span class="sxs-lookup"><span data-stu-id="639fc-110">To periodically refresh the publishing information from the Application Virtualization Servers</span></span>**

1.  <span data-ttu-id="639fc-111">[**範囲**] ウィンドウで [**パブリッシングサーバー** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="639fc-111">Click **Publishing Servers** in the **Scope** pane.</span></span>

2.  <span data-ttu-id="639fc-112">[**結果**] ウィンドウで、目的のサーバーを右クリックし、ポップアップメニューから [**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="639fc-112">In the **Results** pane, right-click the desired server and select **Properties** from the pop-up-menu.</span></span>

3.  <span data-ttu-id="639fc-113">[**プロパティ**] ダイアログボックスの [**更新**] タブで、[**構成の更新間隔**] チェックボックスをオンにして、フィールドの頻度を表す数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="639fc-113">In the **Properties** dialog box, on the **Refresh** tab, select the **Refresh configuration every** check box and enter a number that represents the frequency in the field.</span></span> <span data-ttu-id="639fc-114">次に、ドロップダウンメニューから [**分**]、[**時間**]、[**日**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="639fc-114">Then select **Minutes**, **Hours**, **Days** from the drop-down menu.</span></span>

    <span data-ttu-id="639fc-115">**注** この設定により、構成された期間が経過するたびにクライアントが発行情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="639fc-115">**Note** This setting will cause the client to refresh publishing information every time the configured period elapses.</span></span> <span data-ttu-id="639fc-116">ユーザーがログインしていない場合に更新を行うと、ユーザーが次回ログインしたときに更新が行われます。</span><span class="sxs-lookup"><span data-stu-id="639fc-116">If the user is not logged in when it's time to do a refresh, the refresh will take place when the user next logs in.</span></span> <span data-ttu-id="639fc-117">次の期間、タイマーが再び開始されます。</span><span class="sxs-lookup"><span data-stu-id="639fc-117">The timer is then started again for the next period.</span></span>

     

4.  <span data-ttu-id="639fc-118">[**適用**] をクリックして構成を変更します。</span><span class="sxs-lookup"><span data-stu-id="639fc-118">Click **Apply** to change the configuration.</span></span>

5.  <span data-ttu-id="639fc-119">サーバーの構成が完了したら、[ **OK** ] をクリックしてダイアログボックスを閉じ、Application Virtualization クライアント管理コンソールに戻ります。</span><span class="sxs-lookup"><span data-stu-id="639fc-119">When you finish configuring the server, click **OK** to exit the dialog box and return to the Application Virtualization Client Management Console.</span></span>

## <span data-ttu-id="639fc-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="639fc-120">Related topics</span></span>


[<span data-ttu-id="639fc-121">Application Virtualization Client Management Console でクライアントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="639fc-121">How to Configure the Client in the Application Virtualization Client Management Console</span></span>](how-to-configure-the-client-in-the-application-virtualization-client-management-console.md)

 

 





