---
title: Application Virtualization システム コンポーネントを削除する方法
description: Application Virtualization システム コンポーネントを削除する方法
author: dansimp
ms.assetid: 45bb1e43-8708-48b7-9169-e3659f32686f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 450357bd682c1a6801f40a76a75f25516f55e7bb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816774"
---
# <span data-ttu-id="9c89c-103">Application Virtualization システム コンポーネントを削除する方法</span><span class="sxs-lookup"><span data-stu-id="9c89c-103">How to Remove the Application Virtualization System Components</span></span>


<span data-ttu-id="9c89c-104">次の手順を使用して、ターゲットコンピューターからすべてまたは選択したアプリケーションの仮想化ソフトウェアのコンポーネントを削除できます。</span><span class="sxs-lookup"><span data-stu-id="9c89c-104">You can use the following procedures to remove all or selected Application Virtualization software components from a target computer.</span></span>

**<span data-ttu-id="9c89c-105">1台のコンピューターからすべてのコンポーネントを削除するには</span><span class="sxs-lookup"><span data-stu-id="9c89c-105">To remove all components from a single computer</span></span>**

1.  <span data-ttu-id="9c89c-106">Windows デスクトップで、[**設定の開始] &gt; &gt; コントロールパネル**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c89c-106">From the Windows desktop, click **Start &gt; Settings &gt; Control Panel**.</span></span>

2.  <span data-ttu-id="9c89c-107">[コントロールパネル] ウィンドウで、[**プログラムの追加と削除**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c89c-107">In the Control Panel window, double-click **Add or Remove Programs**.</span></span>

3.  <span data-ttu-id="9c89c-108">[**プログラムの追加と削除**] ページで、[ **Microsoft system Center Application の仮想 Management server** ] または [ **Microsoft system center application Streaming server**] を選択し、メッセージが表示されたら [**はい**] をクリックして、すべてのアプリケーションの仮想化ソフトウェアコンポーネントをコンピューターから**削除します**。</span><span class="sxs-lookup"><span data-stu-id="9c89c-108">On the **Add or Remove Programs** page, select **Microsoft System Center Application Virtual Management Server** or **Microsoft System Center Application Streaming Server**, click **Remove**, and then click **Yes** at the prompt to remove all Application Virtualization software components from the computer.</span></span>

**<span data-ttu-id="9c89c-109">1つまたは複数のコンポーネントをコンピューターから削除するには</span><span class="sxs-lookup"><span data-stu-id="9c89c-109">To remove one or more components from a computer</span></span>**

1.  <span data-ttu-id="9c89c-110">ネットワーク上でアプリケーションの仮想化システムセットアッププログラムが保存されている場所に移動します。ネットワークからこのプログラムを実行するか、またはターゲットコンピューターにディレクトリをコピーして、[ **Setup.exe**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c89c-110">Navigate to the location of the Application Virtualization System setup program on the network, either run this program from the network or copy its directory to the target computer, and then double-click **Setup.exe**.</span></span>

2.  <span data-ttu-id="9c89c-111">[**ようこそ**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c89c-111">On the **Welcome** page, click **Next**.</span></span>

3.  <span data-ttu-id="9c89c-112">[**プログラムメンテナンス**] ページで [**変更**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c89c-112">On the **Program Maintenance** page, select **Modify** and then click **Next**.</span></span>

4.  <span data-ttu-id="9c89c-113">[**カスタムセットアップ**] ページで、削除するアプリケーション仮想化コンポーネントまたはコンポーネントの選択を解除し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c89c-113">On the **Custom Setup** page, deselect the Application Virtualization component or components you want to remove, and then click **Next**.</span></span>

5.  <span data-ttu-id="9c89c-114">[**プログラムを変更する準備ができ**ました] ページで、選択したコンポーネントを削除するには、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c89c-114">On the **Ready to Modify the Program** page, to remove the selected components, click **Install**.</span></span>

6.  <span data-ttu-id="9c89c-115">**インストールウィザード**の [完了] ページで、ウィザードを閉じるには、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c89c-115">On the **Installation Wizard Completed** page, to close the wizard click **Finish**.</span></span> <span data-ttu-id="9c89c-116">コンピューターを再起動するには、[**はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c89c-116">Click **Yes** to restart the computer.</span></span>

## <span data-ttu-id="9c89c-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9c89c-117">Related topics</span></span>


[<span data-ttu-id="9c89c-118">サーバーおよびシステム コンポーネントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="9c89c-118">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)

 

 





