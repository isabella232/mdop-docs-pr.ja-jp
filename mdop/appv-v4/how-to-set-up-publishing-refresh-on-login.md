---
title: ログイン時に公開の更新をセットアップする方法
description: ログイン時に公開の更新をセットアップする方法
author: dansimp
ms.assetid: 196448db-7645-4fd5-a854-ef6405b15db4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dd131ab5acbb8224e60077dfcc4272d4aa132b5e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816557"
---
# <span data-ttu-id="87fee-103">ログイン時に公開の更新をセットアップする方法</span><span class="sxs-lookup"><span data-stu-id="87fee-103">How to Set Up Publishing Refresh on Login</span></span>


<span data-ttu-id="87fee-104">次の手順を使用して、コンピューターにログインするたびにサーバーから公開情報を更新するように Application Virtualization (App-v) クライアントを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="87fee-104">You can use the following procedure to configure the Application Virtualization (App-V) Client to refresh the publishing information from the server each time you log in to the computer.</span></span> <span data-ttu-id="87fee-105">クライアントが構成されると、更新操作は自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="87fee-105">After the client is configured, the refresh operation is automatic.</span></span>

**<span data-ttu-id="87fee-106">ログイン時に公開情報を更新するには</span><span class="sxs-lookup"><span data-stu-id="87fee-106">To refresh the publishing information on login</span></span>**

1.  <span data-ttu-id="87fee-107">[**範囲**] ウィンドウで [**パブリッシングサーバー** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87fee-107">Click **Publishing Servers** in the **Scope** pane.</span></span>

2.  <span data-ttu-id="87fee-108">[**結果**] ウィンドウで、目的のサーバーを右クリックし、ポップアップメニューから [**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="87fee-108">In the **Results** pane, right-click the desired server and select **Properties** from the pop-up-menu.</span></span>

3.  <span data-ttu-id="87fee-109">[**プロパティ**] ダイアログボックスの [**更新**] タブで、[**ユーザーログイン時に構成サーバーを更新**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="87fee-109">In the **Properties** dialog box, on the **Refresh** tab, select the **Refresh configuration server on user login** check box.</span></span>

4.  <span data-ttu-id="87fee-110">[**適用**] をクリックして構成を変更します。</span><span class="sxs-lookup"><span data-stu-id="87fee-110">Click **Apply** to change the configuration.</span></span>

5.  <span data-ttu-id="87fee-111">設定の構成が完了したら、[ **OK** ] をクリックしてダイアログボックスを閉じ、Application Virtualization 管理コンソールに戻ります。</span><span class="sxs-lookup"><span data-stu-id="87fee-111">When you finish configuring the settings, click **OK** to exit the dialog box and return to the Application Virtualization Management Console.</span></span>

    <span data-ttu-id="87fee-112">公開情報は、システムにログインするたびに更新されるようになります。</span><span class="sxs-lookup"><span data-stu-id="87fee-112">The publishing information will now be refreshed each time you log in to the system.</span></span>

## <span data-ttu-id="87fee-113">関連トピック</span><span class="sxs-lookup"><span data-stu-id="87fee-113">Related topics</span></span>


[<span data-ttu-id="87fee-114">Application Virtualization Client Management Console でクライアントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="87fee-114">How to Configure the Client in the Application Virtualization Client Management Console</span></span>](how-to-configure-the-client-in-the-application-virtualization-client-management-console.md)

 

 





