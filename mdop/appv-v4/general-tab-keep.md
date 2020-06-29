---
title: '[全般] タブ'
description: '[全般] タブ'
author: dansimp
ms.assetid: aeefae39-60cd-4ad4-9575-c07d7e2b1e59
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 327635422030b713aeadbc5de0007685b69e1c2e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821474"
---
# <span data-ttu-id="da133-103">[全般] タブ</span><span class="sxs-lookup"><span data-stu-id="da133-103">General Tab</span></span>


<span data-ttu-id="da133-104">**[全般**] タブを使用して、Microsoft Application Virtualization (App-v) Sequencer のオプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="da133-104">Use the **General** tab to configure options for Microsoft Application Virtualization (App-V) Sequencer.</span></span>

<a href="" id="scratch-directory"></a>**<span data-ttu-id="da133-105">スクラッチディレクトリ</span><span class="sxs-lookup"><span data-stu-id="da133-105">Scratch Directory</span></span>**  
<span data-ttu-id="da133-106">シーケンス中に生成されたファイルを Sequencer が一時的に保存する場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="da133-106">Specifies the path to the location where the Sequencer will temporarily save files generated during sequencing.</span></span> <span data-ttu-id="da133-107">既定のパスは C:\\ProgramFiles\\Microsoft Application Virtualization Sequencer\\Scratch.</span><span class="sxs-lookup"><span data-stu-id="da133-107">The default path is C:\\ProgramFiles\\Microsoft Application Virtualization Sequencer\\Scratch.</span></span> <span data-ttu-id="da133-108">新しいパスを指定するには、[**参照**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da133-108">To specify a new path, click **Browse**.</span></span>

<a href="" id="log-directory"></a>**<span data-ttu-id="da133-109">Log ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="da133-109">Log Directory</span></span>**  
<span data-ttu-id="da133-110">Sequencer がログファイルを保存するディレクトリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="da133-110">Specifies the path to the directory where the Sequencer will save log files.</span></span> <span data-ttu-id="da133-111">既定のパスは C:\\ProgramFiles\\Microsoft Application Virtualization Sequencer\\Logs.</span><span class="sxs-lookup"><span data-stu-id="da133-111">The default path is C:\\ProgramFiles\\Microsoft Application Virtualization Sequencer\\Logs.</span></span> <span data-ttu-id="da133-112">新しいパスを指定するには、[**参照**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da133-112">To specify a new path, click **Browse**</span></span>

<a href="" id="allow-use-of-msi-installer"></a>**<span data-ttu-id="da133-113">MSI インストーラの使用を許可する</span><span class="sxs-lookup"><span data-stu-id="da133-113">Allow Use of MSI Installer</span></span>**  
<span data-ttu-id="da133-114">Sequencer とアプリケーションインストーラー間の操作を許可するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="da133-114">Select this option to allow interaction between the Sequencer and the application installer.</span></span> <span data-ttu-id="da133-115">既定では、このオプションが選択されています。</span><span class="sxs-lookup"><span data-stu-id="da133-115">This option is selected by default.</span></span>

<a href="" id="allow-virtualization-of-events"></a>**<span data-ttu-id="da133-116">イベントの仮想化を許可する</span><span class="sxs-lookup"><span data-stu-id="da133-116">Allow Virtualization of Events</span></span>**  
<span data-ttu-id="da133-117">このオプションを選択すると、シーケンス処理されたアプリケーションパッケージが App-v デスクトップクライアントで実行されるときに、アプリケーションの下位レベルのオペレーティングシステムアクティビティが仮想化されます。</span><span class="sxs-lookup"><span data-stu-id="da133-117">Select this option to allow low-level operating system activities of the application to be virtualized when a sequenced application package is run on App-V Desktop Clients.</span></span> <span data-ttu-id="da133-118">既定では、このオプションが選択されています。</span><span class="sxs-lookup"><span data-stu-id="da133-118">This option is selected by default.</span></span>

<a href="" id="allow-virtualization-of-services"></a>**<span data-ttu-id="da133-119">サービスの仮想化を許可する</span><span class="sxs-lookup"><span data-stu-id="da133-119">Allow Virtualization of Services</span></span>**  
<span data-ttu-id="da133-120">アプリケーションをアプリで実行するときに、アプリケーションで必要なサービスが仮想化されるようにするには、このオプションをオンにします。</span><span class="sxs-lookup"><span data-stu-id="da133-120">Select this option to allow services required by the application to be virtualized when the application is run on App-V Desktop Clients.</span></span> <span data-ttu-id="da133-121">既定では、このオプションが選択されています。</span><span class="sxs-lookup"><span data-stu-id="da133-121">This option is selected by default.</span></span>

<a href="" id="append-package-version-to-filename"></a>**<span data-ttu-id="da133-122">ファイル名にパッケージバージョンを追加する</span><span class="sxs-lookup"><span data-stu-id="da133-122">Append Package Version to Filename</span></span>**  
<span data-ttu-id="da133-123">シーケンス付きのアプリケーションパッケージのバージョン番号をファイル名に自動的に追加するには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="da133-123">Select this option to automatically append the sequenced application package version number to the file name.</span></span> <span data-ttu-id="da133-124">既定では、このオプションが選択されています。</span><span class="sxs-lookup"><span data-stu-id="da133-124">This option is selected by default.</span></span>

<a href="" id="ok"></a>**<span data-ttu-id="da133-125">OK</span><span class="sxs-lookup"><span data-stu-id="da133-125">OK</span></span>**  
<span data-ttu-id="da133-126">変更を保存し、ダイアログボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="da133-126">Saves changes and closes the dialog box.</span></span>

<a href="" id="cancel"></a>**<span data-ttu-id="da133-127">Cancel</span><span class="sxs-lookup"><span data-stu-id="da133-127">Cancel</span></span>**  
<span data-ttu-id="da133-128">変更を保存せずにダイアログボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="da133-128">Exits the dialog box without saving any changes.</span></span>

<a href="" id="apply"></a>**<span data-ttu-id="da133-129">[適用]</span><span class="sxs-lookup"><span data-stu-id="da133-129">Apply</span></span>**  
<span data-ttu-id="da133-130">変更を保存し、ダイアログボックスに残ります。</span><span class="sxs-lookup"><span data-stu-id="da133-130">Saves the changes and remains in the dialog box.</span></span>

## <span data-ttu-id="da133-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="da133-131">Related topics</span></span>


[<span data-ttu-id="da133-132">Application Virtualization Sequencer [オプション] ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="da133-132">Application Virtualization Sequencer Options Dialog Box</span></span>](application-virtualization-sequencer-options-dialog-box.md)

 

 





