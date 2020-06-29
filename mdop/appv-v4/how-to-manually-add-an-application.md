---
title: アプリケーションを手動で追加する方法
description: アプリケーションを手動で追加する方法
author: dansimp
ms.assetid: c635b07a-5c7f-4ab2-ba18-366457146cb9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 868939553fae6172ccca549ddc3f08aa76ee3c56
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817097"
---
# <span data-ttu-id="9b08d-103">アプリケーションを手動で追加する方法</span><span class="sxs-lookup"><span data-stu-id="9b08d-103">How to Manually Add an Application</span></span>


<span data-ttu-id="9b08d-104">Application Virtualization Management Server にアプリケーションを追加する場合は、インポートすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b08d-104">When adding an application to the Application Virtualization Management Server, it is recommended that you import it.</span></span> <span data-ttu-id="9b08d-105">アプリケーションを手動で追加することもできますが、このセクションでは、アプリケーションに関する詳細な詳細情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b08d-105">You can add an application manually, but you must provide the precise, detailed information about the application called for in this section.</span></span>

**<span data-ttu-id="9b08d-106">新しいアプリケーションを手動で追加するには</span><span class="sxs-lookup"><span data-stu-id="9b08d-106">To manually add a new application</span></span>**

1.  <span data-ttu-id="9b08d-107">左側のウィンドウで、[**アプリケーション**] ノードを右クリックし、[**新しいアプリケーション**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b08d-107">In the left pane, right-click the **Applications** node and choose **New Application**.</span></span>

2.  <span data-ttu-id="9b08d-108">**新しいアプリケーションウィザード**で、 **[一般的な情報**] ダイアログボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="9b08d-108">In the **New Application Wizard**, complete the **General Information** dialog box:</span></span>

    1.  <span data-ttu-id="9b08d-109">[**アプリケーション名**の指定: ユーザーに表示する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="9b08d-109">**Application Name**—Type the name you want the users to see.</span></span>

    2.  <span data-ttu-id="9b08d-110">**バージョン**—アプリケーションのバージョンを入力します。</span><span class="sxs-lookup"><span data-stu-id="9b08d-110">**Version**—Type the application version.</span></span>

    3.  <span data-ttu-id="9b08d-111">**有効**: このボックスは、アプリケーションを作成した後にストリーミングするために選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b08d-111">**Enabled**—This box must be selected to stream the application after you create it.</span></span>

    4.  <span data-ttu-id="9b08d-112">**説明**—管理者用の説明を入力します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="9b08d-112">**Description**—Type an optional description for administrative use.</span></span>

    5.  <span data-ttu-id="9b08d-113">[ **OSD Path**] —ネットワークでアプリケーションのオープンソフトウェア記述子 (OSD) ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="9b08d-113">**OSD Path**—Browse the network to the application's Open Software Descriptor (OSD) file.</span></span> <span data-ttu-id="9b08d-114">このファイルは共有ネットワークフォルダーに存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b08d-114">This file must be in a shared network folder.</span></span>

    6.  <span data-ttu-id="9b08d-115">**アイコンパス**—アプリケーションの ICO ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="9b08d-115">**Icon Path**—Browse to the application's ICO file.</span></span>

    7.  <span data-ttu-id="9b08d-116">[**アプリケーションライセンス] グループ**-ライセンスグループを設定している場合は、プルダウンリストでアプリを選ぶことによってアプリケーションを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="9b08d-116">**Application License Group**—If you have set up license groups, you can assign the application to one by selecting it in the pull-down list.</span></span>

    8.  <span data-ttu-id="9b08d-117">[**サーバーグループ**] —複数の Application Virtualization サーバーがある場合は、プルダウンリストでアプリケーションを選択してアプリケーションを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="9b08d-117">**Server Group**—If you have multiple Application Virtualization Servers, you can assign the application to one by selecting it in the pull-down list.</span></span>

3.  <span data-ttu-id="9b08d-118">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b08d-118">Click **Next**.</span></span>

4.  <span data-ttu-id="9b08d-119">**[パッケージの選択**] ダイアログボックスで、関連するパッケージを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b08d-119">In the **Select Package** dialog box, select the related package and click **Next**.</span></span>

5.  <span data-ttu-id="9b08d-120">[公開された**ショートカット**] 画面で、クライアントコンピューターにアプリケーションのショートカットを表示する場所のチェックボックスをオンにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b08d-120">On the **Published Shortcuts** screen, select the boxes for the locations where you would like the application shortcuts to appear on the client computers and click **Next**.</span></span>

6.  <span data-ttu-id="9b08d-121">[**ファイルの関連付け**] 画面で、このアプリケーションに新しい種類のファイルの関連付けを追加できます。</span><span class="sxs-lookup"><span data-stu-id="9b08d-121">In the **File Associations** screen, you can add new type file associations to this application.</span></span> <span data-ttu-id="9b08d-122">そのためには、[**追加**] をクリックし、拡張機能 (前のドットは不要) を入力して、説明を入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b08d-122">To do so, click **Add**, enter the extension (without a preceding dot), enter a description, and click **OK**.</span></span>

7.  <span data-ttu-id="9b08d-123">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b08d-123">Click **Next**.</span></span>

8.  <span data-ttu-id="9b08d-124">[**アクセス許可**] ダイアログボックスで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b08d-124">In the **Access Permissions** dialog box, click **Add**.</span></span>

9.  <span data-ttu-id="9b08d-125">[**ユーザーグループの追加/編集**] ダイアログボックスで、[ユーザー] グループに移動します。</span><span class="sxs-lookup"><span data-stu-id="9b08d-125">In the **Add/Edit User Group** dialog box, navigate to the user group.</span></span> <span data-ttu-id="9b08d-126">各フィールドに情報を入力して、ドメインとグループを入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="9b08d-126">You can also enter the domain and group by typing the information in the respective fields.</span></span> <span data-ttu-id="9b08d-127">完了したら、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b08d-127">When you finish, click **OK**.</span></span> <span data-ttu-id="9b08d-128">同じページを持つ他のグループを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="9b08d-128">You can add other groups with the same pages.</span></span>

10. <span data-ttu-id="9b08d-129">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b08d-129">Click **Next**.</span></span>

11. <span data-ttu-id="9b08d-130">[**概要**] 画面では、インポート設定を確認できます。</span><span class="sxs-lookup"><span data-stu-id="9b08d-130">On the **Summary** screen, you can review the import settings.</span></span> <span data-ttu-id="9b08d-131">[**完了**] をクリックしてアプリケーションを追加し、[**戻る**] をクリックして情報を変更するか、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b08d-131">Click **Finish** to add the application, click **Back** to change the information, or click **Cancel**.</span></span>

## <span data-ttu-id="9b08d-132">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9b08d-132">Related topics</span></span>


[<span data-ttu-id="9b08d-133">サーバー管理コンソールでアプリケーションを管理する方法</span><span class="sxs-lookup"><span data-stu-id="9b08d-133">How to Manage Applications in the Server Management Console</span></span>](how-to-manage-applications-in-the-server-management-console.md)

 

 





