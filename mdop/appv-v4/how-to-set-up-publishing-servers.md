---
title: 公開サーバーをセットアップする方法
description: 公開サーバーをセットアップする方法
author: dansimp
ms.assetid: 2111f079-c202-4c49-b2a6-f4237068b2dc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2f060d862fd1449f5240ad495b53a1fa4e97697f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816527"
---
# <span data-ttu-id="60c9d-103">公開サーバーをセットアップする方法</span><span class="sxs-lookup"><span data-stu-id="60c9d-103">How to Set Up Publishing Servers</span></span>


<span data-ttu-id="60c9d-104">次の手順を使用して、クライアント管理コンソールからアプリケーションの仮想化サーバーを直接追加し、構成することができます。</span><span class="sxs-lookup"><span data-stu-id="60c9d-104">You can use the following procedures to add and configure Application Virtualization Servers directly from the Client Management Console.</span></span>

**<span data-ttu-id="60c9d-105">アプリケーション発行サーバーを追加するには</span><span class="sxs-lookup"><span data-stu-id="60c9d-105">To add an application publishing server</span></span>**

1.  <span data-ttu-id="60c9d-106">[**結果**] ウィンドウで、ポップアップメニューから [**新しいサーバー** ] を右クリックして選択し、新しい Application Virtualization server ウィザードを起動するか、または [**発行サーバー** ] ノードを右クリックして、ポップアップメニューから [**新しいサーバー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="60c9d-106">In the **Results** pane, right-click and select **New Server** from the pop-up-menu to start the New Application Virtualization Server Wizard, or alternatively, right-click the **Publishing Server** node and select **New Server** from the pop-up-menu.</span></span>

2.  <span data-ttu-id="60c9d-107">ウィザードの1ページ目で、[**表示名**] フィールドにサーバーの名前を入力し、[**種類**] ドロップダウンリストからサーバーの種類を選びます。</span><span class="sxs-lookup"><span data-stu-id="60c9d-107">On page one of the wizard, enter the name of the server in the **Display Name** field and select the server type from the **Type** drop-down list.</span></span> <span data-ttu-id="60c9d-108">サーバーの種類のドロップダウンリストから、 **Application Virtualization server**、 **Enhanced Security Application Virtualization server**、**標準の http サーバー**、強化された**セキュリティ HTTP サーバー**を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="60c9d-108">You can choose **Application Virtualization Server**, **Enhanced Security Application Virtualization Server**, **Standard HTTP Server**, or **Enhanced Security HTTP Server** from the drop-down list of server types.</span></span>

3.  <span data-ttu-id="60c9d-109">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60c9d-109">Click **Next**.</span></span>

4.  <span data-ttu-id="60c9d-110">ウィザードの2ページで、[**ホスト名**] フィールドと [**ポート**] フィールドに適切な情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="60c9d-110">On page two of the wizard, type the appropriate information into the **Host Name** and **Port** fields.</span></span> <span data-ttu-id="60c9d-111">**Path**フィールドは、Application Virtualization サーバーでは編集できません。</span><span class="sxs-lookup"><span data-stu-id="60c9d-111">The **Path** field is not editable for Application Virtualization Servers.</span></span> <span data-ttu-id="60c9d-112">標準 HTTP サーバーまたは強化されたセキュリティ HTTP サーバーのパスを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60c9d-112">You must enter a path for Standard HTTP Server or Enhanced Security HTTP Server.</span></span>

5.  <span data-ttu-id="60c9d-113">[**完了**] をクリックしてサーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="60c9d-113">Click **Finish** to add the server.</span></span>

**<span data-ttu-id="60c9d-114">アプリケーション発行サーバーをセットアップするには</span><span class="sxs-lookup"><span data-stu-id="60c9d-114">To set up an application publishing server</span></span>**

1.  <span data-ttu-id="60c9d-115">[**結果**] ウィンドウで、目的のサーバーを右クリックし、ポップアップメニューから [**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="60c9d-115">In the **Results** pane, right-click the desired server and select **Properties** from the pop-up menu.</span></span>

2.  <span data-ttu-id="60c9d-116">[**全般**] タブをクリックし、サーバー名を変更できます。サーバーの種類のドロップダウンリストから種類を選んで、ホスト名とポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="60c9d-116">Click the **General** tab, where you can change the server name, select a type from the drop-down list of server types, and specify the host name and port.</span></span> <span data-ttu-id="60c9d-117">サーバーの種類が [Standard HTTP Server] または [強化されたセキュリティ HTTP サーバー] である場合、[ **Path** ] フィールドも編集できます。</span><span class="sxs-lookup"><span data-stu-id="60c9d-117">When the server type is Standard HTTP Server or Enhanced Security HTTP Server, the **Path** field is also editable.</span></span>

3.  <span data-ttu-id="60c9d-118">[**更新**] タブをクリックします。既定では、[**ユーザーのログイン時に公開**する] チェックボックスがオンになっています。</span><span class="sxs-lookup"><span data-stu-id="60c9d-118">Click the **Refresh** tab, where the **Refresh publishing on user login** check box is selected by default.</span></span> <span data-ttu-id="60c9d-119">更新間隔を変更するには、[**発行の間隔**] チェックボックスをオンにして、フィールドの頻度を表す数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="60c9d-119">To change the refresh rate, select the **Refresh publishing every** check box and enter a number that represents the frequency in the field.</span></span> <span data-ttu-id="60c9d-120">次に、ドロップダウンメニューから [**分**]、[**時間**]、[**日**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="60c9d-120">Then select **Minutes**, **Hours**, **Days** from the drop-down menu.</span></span> <span data-ttu-id="60c9d-121">(入力できる最小時間は30分です。)</span><span class="sxs-lookup"><span data-stu-id="60c9d-121">(The minimum amount of time you can enter is 30 minutes.)</span></span>

4.  <span data-ttu-id="60c9d-122">[**適用**] をクリックして構成を変更します。</span><span class="sxs-lookup"><span data-stu-id="60c9d-122">Click **Apply** to change the configuration.</span></span>

5.  <span data-ttu-id="60c9d-123">発行が完了したら、[ **OK** ] をクリックしてダイアログボックスを終了し、クライアント管理コンソールに戻ります。</span><span class="sxs-lookup"><span data-stu-id="60c9d-123">When you are finished publishing, click **OK** to exit the dialog box and return to the Client Management Console.</span></span>

## <span data-ttu-id="60c9d-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="60c9d-124">Related topics</span></span>


[<span data-ttu-id="60c9d-125">非接続操作モード設定を無効化または変更する方法</span><span class="sxs-lookup"><span data-stu-id="60c9d-125">How to Disable or Modify Disconnected Operation Mode Settings</span></span>](how-to-disable-or-modify-disconnected-operation-mode-settings.md)

 

 





