---
title: Application Virtualization Sequencer Console の概要
description: Application Virtualization Sequencer Console の概要
author: dansimp
ms.assetid: 681bb40d-2937-4645-82aa-4a44775232d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4c2f977fccaaded0309181a1d74c16b749498abb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822194"
---
# <span data-ttu-id="20c26-103">Application Virtualization Sequencer Console の概要</span><span class="sxs-lookup"><span data-stu-id="20c26-103">Application Virtualization Sequencer Console Overview</span></span>


<span data-ttu-id="20c26-104">Application Virtualization (App-v) Sequencer は、仮想アプリケーションとして仮想環境で実行できるように、アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="20c26-104">The Application Virtualization (App-V) Sequencer creates applications so that they can be run in a virtual environment, as virtual applications.</span></span> <span data-ttu-id="20c26-105">アプリケーションが順序付けされた後、アプリの hyper-v Server から実行して、app-v デスクトップクライアントを実行しているコンピューターまたはリモートデスクトップサービス (以前のターミナルサービス) 用の App-v クライアントを実行しているコンピューターを、ストリーミングと呼ばれるプロセスを使ってターゲットにすることができます。</span><span class="sxs-lookup"><span data-stu-id="20c26-105">After an application has been sequenced, it can run from an App-V Server to target computers that are running the App-V Desktop Client or the App-V Client for Remote Desktop Services (formerly Terminal Services) by using a process called streaming.</span></span> <span data-ttu-id="20c26-106">App-v Sequencer は、アプリケーションのインストールとセットアップのプロセスを監視し、仮想環境でアプリケーションを実行するために必要なすべての情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="20c26-106">The App-V Sequencer monitors the installation and setup process for applications, and it records all the information necessary for the application to run in the virtual environment.</span></span> <span data-ttu-id="20c26-107">このプロセスでは、すべてのユーザーに適用されるファイルと構成、およびユーザーがカスタマイズできる構成を決定することもできます。</span><span class="sxs-lookup"><span data-stu-id="20c26-107">This process also determines which files and configurations are applicable to all users and which configurations users can customize.</span></span> <span data-ttu-id="20c26-108">仮想アプリケーションはターゲットコンピューターで実行され、ターゲットコンピューターまたはターゲットコンピューターにインストールされているアプリケーションで実行されているオペレーティングシステムには影響しません。</span><span class="sxs-lookup"><span data-stu-id="20c26-108">Virtual applications run on target computers and have no effect on the operating system running on the target computer or on any applications that are installed on the target computer.</span></span>

## <span data-ttu-id="20c26-109">Application Virtualization Sequencer のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="20c26-109">Application Virtualization Sequencer Security Considerations</span></span>


<span data-ttu-id="20c26-110">App-v Sequencer は、ローカルシステムアカウントを使ってシーケンス処理中に検出されたすべてのサービスを実行し、サービス制御要求ではセキュリティ記述子を適用しません。</span><span class="sxs-lookup"><span data-stu-id="20c26-110">The App-V Sequencer runs all services detected at sequencing time using the Local System account and does not enforce security descriptors on service control requests.</span></span> <span data-ttu-id="20c26-111">サービスが別のユーザーアカウントを使用してインストールされている場合、またはセキュリティ記述子が別のユーザーグループ固有のサービスのアクセス許可を付与することを意図している場合は、サービスを仮想化する必要があるかどうか慎重に検討してください。</span><span class="sxs-lookup"><span data-stu-id="20c26-111">If the service was installed using a different user account or if the security descriptors are intended to grant different user groups specific service permissions, consider carefully whether the service should be virtualized.</span></span> <span data-ttu-id="20c26-112">場合によっては、対象のサービスセキュリティが維持されるように、サービスをローカルにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="20c26-112">In some cases, you should install the service locally to ensure that the intended service security is preserved.</span></span>

## <span data-ttu-id="20c26-113">Application Virtualization Sequencer コンソールの [オプション]</span><span class="sxs-lookup"><span data-stu-id="20c26-113">Application Virtualization Sequencer Console Menu Options</span></span>


<span data-ttu-id="20c26-114">次のメニュー項目は、App-v の Sequencer コンソールで使用できます。</span><span class="sxs-lookup"><span data-stu-id="20c26-114">The following menu items are available in the App-V Sequencer Console:</span></span>

-   <span data-ttu-id="20c26-115">[**ファイル**] —シーケンスアプリケーションの作成、オープン、変更、保存に役立つさまざまなコマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="20c26-115">**File**—Contains various commands to help create, open, modify, and save sequenced applications.</span></span>

-   <span data-ttu-id="20c26-116">**編集**: 既存の仮想アプリケーションを編集するためのさまざまなコマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="20c26-116">**Edit**—Contains various commands for editing existing virtual applications.</span></span>

-   <span data-ttu-id="20c26-117">**ビュー**: 仮想アプリケーションのプロパティを表示するためのさまざまなコマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="20c26-117">**View**—Contains various commands for viewing properties of a virtual application.</span></span>

-   <span data-ttu-id="20c26-118">**ツール**: 仮想アプリケーションを構成するためのさまざまなツールと診断が含まれています。</span><span class="sxs-lookup"><span data-stu-id="20c26-118">**Tools**—Contains various tools and diagnostics for configuring virtual applications.</span></span>

## <span data-ttu-id="20c26-119">Application Virtualization Sequencer コンソールのツールバーオプション</span><span class="sxs-lookup"><span data-stu-id="20c26-119">Application Virtualization Sequencer Console Toolbar Options</span></span>


<span data-ttu-id="20c26-120">次のツールバーボタンは、App-v の Sequencer コンソールで使用できます。</span><span class="sxs-lookup"><span data-stu-id="20c26-120">The following toolbar buttons are available in the App-V Sequencer Console:</span></span>

-   <span data-ttu-id="20c26-121">[**新しいパッケージ**]: クリックして新しいシーケンスアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="20c26-121">**New Package**—Click to create a new sequenced application.</span></span>

-   <span data-ttu-id="20c26-122">**Open**—アプリのプログラムパッケージをクリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="20c26-122">**Open**—Click to open a sequenced application package in the App-V Sequencer Console.</span></span>

-   <span data-ttu-id="20c26-123">**アップグレードのために開く**: シーケンス中のアプリケーションをクリックして起動し、更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="20c26-123">**Open for Upgrade**—Click to open a sequenced application to upgrade or apply an update.</span></span>

-   <span data-ttu-id="20c26-124">[**保存**] —連続した仮想アプリケーションを保存します。</span><span class="sxs-lookup"><span data-stu-id="20c26-124">**Save**—Click to save a sequenced virtual application.</span></span>

-   <span data-ttu-id="20c26-125">**シーケンスウィザード**—クリックしてシーケンスウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="20c26-125">**Sequencing Wizard**—Click to open the Sequencing Wizard.</span></span> <span data-ttu-id="20c26-126">[**ツール**] オプションの [**全般**] タブで変更を行う場合は、このボタンを使用してシーケンスウィザードを開始する必要があり  /  **Options**ます。</span><span class="sxs-lookup"><span data-stu-id="20c26-126">You should use this button to start the Sequencing Wizard if you make any changes on the **General** tab under **Tools** / **Options**.</span></span>

## <span data-ttu-id="20c26-127">仮想アプリケーションのタブ</span><span class="sxs-lookup"><span data-stu-id="20c26-127">Virtual Application Tabs</span></span>


<span data-ttu-id="20c26-128">次のタブは、App-v Sequencer コンソールで仮想アプリケーションを表示したときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="20c26-128">The following tabs are displayed when you view a virtual application in the App-V Sequencer Console:</span></span>

-   <span data-ttu-id="20c26-129">[ **Properties**] —選択した仮想アプリケーションに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="20c26-129">**Properties**—Displays information about the selected virtual application.</span></span> <span data-ttu-id="20c26-130">仮想アプリケーションに関連付けられている**パッケージ名**と**コメント**を更新することができます。</span><span class="sxs-lookup"><span data-stu-id="20c26-130">You can update the **Package Name** and **Comments** associated with the virtual application.</span></span>

-   <span data-ttu-id="20c26-131">[**展開**: ターゲットコンピューターが仮想アプリケーションにアクセスする方法についての情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="20c26-131">**Deployment**—Displays information about how the virtual application will be accessed by target computers.</span></span> <span data-ttu-id="20c26-132">仮想アプリケーションの配信方法を構成することができます。また、ターゲットコンピューターでどのオペレーティングシステムを実行する必要があるかを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="20c26-132">You can configure the virtual application delivery method, and you can configure which operating systems must be running on the target computer.</span></span> <span data-ttu-id="20c26-133">関連する出力オプションを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="20c26-133">You can also configure the associated output options.</span></span> <span data-ttu-id="20c26-134">クライアントがファイルから仮想アプリケーションにアクセスすることを計画している場合は、 **File://server/share/path/.sft**を指定するときに、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="20c26-134">If you plan to have clients access a virtual application from a file, use the following format when specifying the path: **File://server/share/path/.sft**.</span></span> <span data-ttu-id="20c26-135">[**セキュリティ記述子を適用**] を選択して、アップグレード中にパッケージに関連付けられているセキュリティを保持するか、アップグレード中にアクセス許可をリセットします。</span><span class="sxs-lookup"><span data-stu-id="20c26-135">Select **Enforce Security Descriptors** to preserve security associated with the package during an upgrade, or the permissions will be reset during the upgrade.</span></span>

-   <span data-ttu-id="20c26-136">[**変更履歴**-仮想アプリケーションに対して行われた更新に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="20c26-136">**Change History**—Displays information about updates that have been made to the virtual application.</span></span>

-   <span data-ttu-id="20c26-137">[**ファイル**-選択した仮想アプリケーションに関連付けられているファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="20c26-137">**Files**—Displays the files associated with the selected virtual application.</span></span> <span data-ttu-id="20c26-138">適切なフィールドを使用して、関連付けられているファイルのプロパティに対して軽微な変更を加えることができます。</span><span class="sxs-lookup"><span data-stu-id="20c26-138">You can make minor revisions to the associated file properties by using the appropriate fields.</span></span>

-   <span data-ttu-id="20c26-139">**仮想レジストリ**—選択した仮想アプリケーションに関連付けられている仮想レジストリを表示します。</span><span class="sxs-lookup"><span data-stu-id="20c26-139">**Virtual Registry**—Displays the virtual registry associated with the selected virtual application.</span></span> <span data-ttu-id="20c26-140">適切なエントリを右クリックして、レジストリキーの追加または削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="20c26-140">You can add or delete registry keys by right-clicking the appropriate entry.</span></span>

-   <span data-ttu-id="20c26-141">**仮想ファイルシステム**—選択した仮想アプリケーションに関連付けられている仮想ファイルシステムを表示します。</span><span class="sxs-lookup"><span data-stu-id="20c26-141">**Virtual File System**—Displays the virtual file systems associated with the selected virtual application.</span></span> <span data-ttu-id="20c26-142">このタブでファイルシステムエントリを追加、削除、または編集するには、該当するエントリを右クリックして、オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="20c26-142">You can add, delete, or edit file system entries on this tab by right-clicking the appropriate entry and selecting the option.</span></span>

-   <span data-ttu-id="20c26-143">**仮想サービス**: 選択した仮想アプリケーションに関連付けられているサービスを表示します。</span><span class="sxs-lookup"><span data-stu-id="20c26-143">**Virtual Services**—Displays the services associated with the selected virtual application.</span></span>

-   <span data-ttu-id="20c26-144">**Osd**—仮想アプリケーションに関連付けられているオープンソフトウェア記述子 (OSD) に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="20c26-144">**OSD**—Displays information about the Open Software Descriptor (OSD) associated with the virtual application.</span></span> <span data-ttu-id="20c26-145">OSD ファイルに関連付けられているファイルを更新するには、該当するエントリを右クリックして、目的のアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="20c26-145">You can update the files associated with the OSD file by right-clicking the appropriate entry and selecting the action that you want.</span></span>

## <span data-ttu-id="20c26-146">関連トピック</span><span class="sxs-lookup"><span data-stu-id="20c26-146">Related topics</span></span>


[<span data-ttu-id="20c26-147">Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="20c26-147">Application Virtualization Sequencer</span></span>](application-virtualization-sequencer.md)

 

 





