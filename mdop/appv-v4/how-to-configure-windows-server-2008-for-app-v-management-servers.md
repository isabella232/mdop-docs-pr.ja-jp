---
title: App-V Management Server 用に Windows Server 2008 を構成する方法
description: App-V Management Server 用に Windows Server 2008 を構成する方法
author: dansimp
ms.assetid: 38b4016f-de82-4209-9159-387d20ddee25
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2d1cd7e84ffc0036c98e70a9a0ee1fd3a4ade790
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817724"
---
# <span data-ttu-id="fa56e-103">App-V Management Server 用に Windows Server 2008 を構成する方法</span><span class="sxs-lookup"><span data-stu-id="fa56e-103">How to Configure Windows Server 2008 for App-V Management Servers</span></span>


<span data-ttu-id="fa56e-104">Microsoft Application Virtualization (App-v) Management Web サービスをインストールする Windows Server 2008 サーバーでは、インターネットインフォメーションサービス (IIS) がサーバー上の役割としてインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa56e-104">The Windows Server 2008 server on which you install the Microsoft Application Virtualization (App-V) Management Web Service requires Internet Information Services (IIS) to be installed as a role on the server.</span></span> <span data-ttu-id="fa56e-105">次の手順を使用して、Vserver のインストールをサポートするように Windows Server 2008 を構成します。</span><span class="sxs-lookup"><span data-stu-id="fa56e-105">Use the following procedure to configure Windows Server 2008 to support App-Vserver installation.</span></span>

**<span data-ttu-id="fa56e-106">Windows Server2008 コンピューターに IIS をインストールするには</span><span class="sxs-lookup"><span data-stu-id="fa56e-106">To install IIS on a Windows Server2008 computer</span></span>**

1.  <span data-ttu-id="fa56e-107">Windows Server2008 コンピューターで、[**スタート**] をクリックし、[**すべてのプログラム**]、[**管理ツール**]、[**サーバーマネージャー** ] の順にクリックしてサーバーマネージャーを起動します。</span><span class="sxs-lookup"><span data-stu-id="fa56e-107">On the Windows Server2008 computer, click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Server Manager** to start Server Manager.</span></span> <span data-ttu-id="fa56e-108">サーバーマネージャーで、[**役割**] ノードを右クリックし、[役割の**追加**] をクリックして**役割の追加ウィザード**を開始します。</span><span class="sxs-lookup"><span data-stu-id="fa56e-108">In Server Manager, right-click the **Roles** node, and click **Add Roles** to start the **Add Roles Wizard**.</span></span>

2.  <span data-ttu-id="fa56e-109">役割の**追加ウィザード**の **[サーバーの役割の選択**] ページで、[ **Web サーバー (IIS)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fa56e-109">In the **Add Roles Wizard**, on the **Select Server Roles** page, select **Web Server (IIS)**.</span></span> <span data-ttu-id="fa56e-110">メッセージが表示されたら、[**必須機能の追加**] をクリックして、依存機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="fa56e-110">When prompted, click **Add Required Features** to add the dependent features.</span></span>

3.  <span data-ttu-id="fa56e-111">[**サーバーの役割の選択**] ページで、[**次へ**] をクリックし、もう一度 [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa56e-111">On the **Select Server Roles** page, Click **Next**, and then click **Next** again.</span></span>

4.  <span data-ttu-id="fa56e-112">役割の**追加ウィザード**の **[役割サービスの選択**] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fa56e-112">In the **Add Roles Wizard**, on the **Select Role Services** page:</span></span>

    1.  <span data-ttu-id="fa56e-113">[**アプリケーション開発**] の下の [ **ASP.NET** ] を選択し、メッセージが表示されたら、[**必須ロールサービスの追加**] をクリックして、依存型ロールのサービスと機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="fa56e-113">Under **Application Development**, select **ASP.NET** and, when prompted, click **Add Required Role Services** to add the dependent roles services and features.</span></span>

    2.  <span data-ttu-id="fa56e-114">[**セキュリティ**] で、[ **Windows 認証**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fa56e-114">Under **Security**, select **Windows Authentication**.</span></span>

    3.  <span data-ttu-id="fa56e-115">[ **Management Tools** ] ノードで、[ **IIS 管理スクリプトとツール**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fa56e-115">In the **Management Tools** node, select **IIS Management Scripts and Tools**.</span></span> <span data-ttu-id="fa56e-116">[ **IIS6 Management compatibility**] で、[ **IIS6 メタベースの互換性**と**IIS6 の WMI 互換**] の両方が選択されていることを確認して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa56e-116">Under **IIS6 Management Compatibility**, ensure that both **IIS6 Metabase Compatibility** and **IIS6 WMI Compatibility** are selected, and then click **Next**.</span></span>

5.  <span data-ttu-id="fa56e-117">[**インストールオプションの確認**] ページで、[**インストール**] をクリックし、ウィザードの残りの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fa56e-117">On the **Confirm Installation Selections** page, click **Install**, and then complete the rest of the wizard.</span></span>

6.  <span data-ttu-id="fa56e-118">[**閉じる**] をクリックして**役割の追加ウィザード**を終了し、[サーバーマネージャー] を閉じます。</span><span class="sxs-lookup"><span data-stu-id="fa56e-118">Click **Close** to exit the **Add Roles Wizard**, and then close Server Manager.</span></span>

## <span data-ttu-id="fa56e-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fa56e-119">Related topics</span></span>


[<span data-ttu-id="fa56e-120">Application Virtualization の展開要件</span><span class="sxs-lookup"><span data-stu-id="fa56e-120">Application Virtualization Deployment Requirements</span></span>](application-virtualization-deployment-requirements.md)

[<span data-ttu-id="fa56e-121">Application Virtualization の展開およびアップグレードのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="fa56e-121">Application Virtualization Deployment and Upgrade Checklists</span></span>](application-virtualization-deployment-and-upgrade-checklists.md)

 

 





