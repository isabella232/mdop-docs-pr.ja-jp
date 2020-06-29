---
title: サーバー管理コンソールアプリケーションの仮想化システムノード
description: サーバー管理コンソールアプリケーションの仮想化システムノード
author: dansimp
ms.assetid: 9450832e-335c-41e7-af24-fddb8ffc327c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 51256ee7e96a97016e73dc79c87e4d422198cfb3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815444"
---
# <span data-ttu-id="3af40-103">サーバー管理コンソール: Application Virtualization システム ノード</span><span class="sxs-lookup"><span data-stu-id="3af40-103">Server Management Console: Application Virtualization System Node</span></span>


<span data-ttu-id="3af40-104">Application Virtualization システムノードは、**スコープ**ウィンドウのトップレベルノードです。</span><span class="sxs-lookup"><span data-stu-id="3af40-104">The Application Virtualization System node is the top-level node in the **Scope** pane.</span></span> <span data-ttu-id="3af40-105">このノードには、本体が現在制御しているサーバーの名前が表示されます。または、コンソールがローカルコンピューターに接続されている場合は、ローカルコンピューターの名前 (名前によって接続されている場合) または "local" を表示します。</span><span class="sxs-lookup"><span data-stu-id="3af40-105">This node displays the name of the server the console is currently controlling, or it displays the name of the local computer (if you are connected by the name) or "local" when the console is connected to the local computer.</span></span> <span data-ttu-id="3af40-106">Application Virtualization システムノードから、別のコンピューターに接続するか、別の資格情報を使用して現在のコンピューターに接続することができます。</span><span class="sxs-lookup"><span data-stu-id="3af40-106">From the Application Virtualization System node, you can connect to another computer or you can connect to the current computer with a different set of credentials.</span></span>

<span data-ttu-id="3af40-107">Application Virtualization システムノードを右クリックすると、次の要素が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3af40-107">You can right-click the Application Virtualization System node to display the following elements.</span></span>

<a href="" id="configure-connection"></a>**<span data-ttu-id="3af40-108">接続を構成する</span><span class="sxs-lookup"><span data-stu-id="3af40-108">Configure Connection</span></span>**  
<span data-ttu-id="3af40-109">このダイアログボックスでは、次の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="3af40-109">In this dialog box, you can modify the following settings:</span></span>

- <span data-ttu-id="3af40-110">[ **Web Service Host Name**]: 接続するアプリケーションの仮想化システムの名前を入力できます。または、 **localhost**を入力してローカルコンピューターに接続します。</span><span class="sxs-lookup"><span data-stu-id="3af40-110">**Web Service Host Name**—Enables you to enter the name of the Application Virtualization System to which you want to connect, or you can enter **localhost** to connect to the local computer.</span></span>

- <span data-ttu-id="3af40-111">[**セキュリティで保護された接続を使用**]: セキュリティで保護された接続でサーバーに接続する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="3af40-111">**Use Secure Connection**—Select if you want to connect to the server with a secure connection.</span></span>

- <span data-ttu-id="3af40-112">[ **Port (ポート**): 接続に使用するポート番号を入力することができます。</span><span class="sxs-lookup"><span data-stu-id="3af40-112">**Port**—Enables you to enter the port number you want to use for the connection.</span></span> <span data-ttu-id="3af40-113">80は既定の標準ポート番号で、443は既定のセキュリティで保護されたポート番号です。</span><span class="sxs-lookup"><span data-stu-id="3af40-113">80 is the default regular port number, and 443 is default secure port number.</span></span>

- <span data-ttu-id="3af40-114">[**現在の Windows アカウントを使う**]: 現在の windows アカウントの資格情報を使用する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="3af40-114">**Use Current Windows Account**—Select to use the current Windows account credentials.</span></span>

- <span data-ttu-id="3af40-115">[ **Windows アカウントの指定**]: 別のユーザーとしてサーバーに接続する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="3af40-115">**Specify Windows Account**—Select when you want to connect to the server as a different user.</span></span>

- <span data-ttu-id="3af40-116">[ **Name (名前**) *DOMAIN\\username*または username@domain のいずれかの形式を使用して、新しいユーザーの名前を入力することができ <em> </em> ます。</span><span class="sxs-lookup"><span data-stu-id="3af40-116">**Name**—Enables you to enter the name of the new user by using either the *DOMAIN\\username* or the <em>username@domain</em> format.</span></span>

- <span data-ttu-id="3af40-117">[ **Password (パスワード**): 新しいユーザーに対応するパスワードを入力できます。</span><span class="sxs-lookup"><span data-stu-id="3af40-117">**Password**—Enables you to enter the password that corresponds to the new user.</span></span>

<a href="" id="system-options"></a>**<span data-ttu-id="3af40-118">システムオプション</span><span class="sxs-lookup"><span data-stu-id="3af40-118">System Options</span></span>**  
<span data-ttu-id="3af40-119">このダイアログボックスの次のタブで、関連付けられている設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="3af40-119">On the following tabs on this dialog box, you can modify the associated settings:</span></span>

-   <span data-ttu-id="3af40-120">**[全般] タブ**: OSD およびアイコンファイルが保存されている**既定のコンテンツパス**を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3af40-120">**General Tab**—Enables you to specify the **Default Content Path** where the OSD and icon files are stored.</span></span>

-   <span data-ttu-id="3af40-121">**[データベース] タブ**: データベースの最大**サイズ**と**利用履歴**を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3af40-121">**Database Tab**—Enables you to specify the maximum **Database Size** and the **Usage History**.</span></span>

<a href="" id="view"></a>**<span data-ttu-id="3af40-122">View</span><span class="sxs-lookup"><span data-stu-id="3af40-122">View</span></span>**  
<span data-ttu-id="3af40-123">Application Virtualization Server 管理コンソールの外観を変更します。</span><span class="sxs-lookup"><span data-stu-id="3af40-123">Changes the appearance of the Application Virtualization Server Management Console.</span></span> <span data-ttu-id="3af40-124">本体の表示を変更する方法については、Microsoft 管理コンソールのヘルプファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3af40-124">For more information about changing the appearance of the console, refer to the help files for the Microsoft Management Console.</span></span>

<a href="" id="new-window-from-here"></a>**<span data-ttu-id="3af40-125">ここから新しいウィンドウ</span><span class="sxs-lookup"><span data-stu-id="3af40-125">New Window from Here</span></span>**  
<span data-ttu-id="3af40-126">新しい管理コンソールウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="3af40-126">Opens a new management console window.</span></span>

<a href="" id="export-list"></a>**<span data-ttu-id="3af40-127">エクスポートリスト</span><span class="sxs-lookup"><span data-stu-id="3af40-127">Export List</span></span>**  
<span data-ttu-id="3af40-128">**結果**ペインの内容を含むタブ区切りのテキストファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3af40-128">Creates a tab-delimited text file that contains the contents of the **Results** pane.</span></span> <span data-ttu-id="3af40-129">この項目は、作成するテキストファイルの場所を指定する、標準の [**ファイルの保存**] ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="3af40-129">This item displays a standard **File Save** dialog box where you specify the location for the text file you are creating.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="3af40-130">ヘルプ</span><span class="sxs-lookup"><span data-stu-id="3af40-130">Help</span></span>**  
<span data-ttu-id="3af40-131">管理コンソールのヘルプファイルを開始します。</span><span class="sxs-lookup"><span data-stu-id="3af40-131">Starts the management console help file.</span></span>

## <span data-ttu-id="3af40-132">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3af40-132">Related topics</span></span>


[<span data-ttu-id="3af40-133">Application Virtualization サーバー管理コンソール リファレンス</span><span class="sxs-lookup"><span data-stu-id="3af40-133">Application Virtualization Server Management Console Reference</span></span>](application-virtualization-server-management-console-reference.md)

 

 





