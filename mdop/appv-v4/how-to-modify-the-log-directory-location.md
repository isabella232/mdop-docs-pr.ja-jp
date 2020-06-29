---
title: ログ ディレクトリの場所を変更する方法
description: ログ ディレクトリの場所を変更する方法
author: dansimp
ms.assetid: 203c674f-8d46-4d42-9af0-245a2681fc0f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 267b37a7f629551b5556aab95b131b88aec9ad17
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816957"
---
# <span data-ttu-id="e0827-103">ログ ディレクトリの場所を変更する方法</span><span class="sxs-lookup"><span data-stu-id="e0827-103">How to Modify the Log Directory Location</span></span>


<span data-ttu-id="e0827-104">Log ディレクトリの場所では、Application Virtualization (App-v) Sequencer がアプリケーションのシーケンスに関する情報を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="e0827-104">The log directory location is where the Application Virtualization (App-V) Sequencer writes information about the sequencing of an application.</span></span>

<span data-ttu-id="e0827-105">**重要** ログの場所ディレクトリは、App-v Sequencer を実行しているコンピューター上に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0827-105">**Important** The log location directory must be located on the computer running the App-V Sequencer.</span></span>

 

<span data-ttu-id="e0827-106">次の手順を使用して、アプリ-V Sequencer が関連するログを保存するディレクトリの場所を変更します。</span><span class="sxs-lookup"><span data-stu-id="e0827-106">Use the following procedure to change the location of the directory where the App-V Sequencer will save associated logs.</span></span>

**<span data-ttu-id="e0827-107">ログディレクトリの場所を変更するには</span><span class="sxs-lookup"><span data-stu-id="e0827-107">To modify the log directory location</span></span>**

1.  <span data-ttu-id="e0827-108">App-v sequencer コンソールを開くには、app-v sequencer を実行しているコンピューターで、[プログラムの**開始**] microsoft application virtualization sequencer を選択し  /  **Programs**  /  **Microsoft Application Virtualization**  /  **Microsoft Application Virtualization Sequencer**ます。</span><span class="sxs-lookup"><span data-stu-id="e0827-108">To open the App-V Sequencer Console, on the computer running the App-V Sequencer, select **Start** / **Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="e0827-109">[App-v Sequencer の**オプション**] ダイアログボックスにアクセスするには、[**ツール**] の [オプション] を選択し  /  **Options**ます。</span><span class="sxs-lookup"><span data-stu-id="e0827-109">To access the App-V Sequencer **Options** dialog box, select **Tools** / **Options**.</span></span> <span data-ttu-id="e0827-110">[**全般**] タブで、app-v Sequencer ログファイル情報を保存する新しいディレクトリの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0827-110">On the **General** tab, specify the new directory location where you want the App-V Sequencer log file information to be saved.</span></span> <span data-ttu-id="e0827-111">または、[**参照**] をクリックし、[**フォルダーの参照**] ダイアログボックスを使用して新しい場所を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e0827-111">Alternatively, you can click **Browse** and use the **Browse For Folder** dialog box to specify a new location.</span></span>

3.  <span data-ttu-id="e0827-112">新しい場所を保存して [**オプション**] ダイアログボックスを閉じるには、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0827-112">To save the new location and close the **Options** dialog box, click **OK**.</span></span>

## <span data-ttu-id="e0827-113">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e0827-113">Related topics</span></span>


[<span data-ttu-id="e0827-114">Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="e0827-114">Application Virtualization Sequencer</span></span>](application-virtualization-sequencer.md)

[<span data-ttu-id="e0827-115">App-V Sequencer を構成する方法</span><span class="sxs-lookup"><span data-stu-id="e0827-115">How to Configure the App-V Sequencer</span></span>](how-to-configure-the-app-v-sequencer.md)

 

 





