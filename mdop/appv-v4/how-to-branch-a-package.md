---
title: パッケージを分岐する方法
description: パッケージを分岐する方法
author: dansimp
ms.assetid: bfe46a8a-f0ee-4a71-9e9c-64ac08aac9c1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2de36fae1a09aeae4d1b7b21ebe00f683e3b3693
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818127"
---
# <span data-ttu-id="1ca1e-103">パッケージを分岐する方法</span><span class="sxs-lookup"><span data-stu-id="1ca1e-103">How to Branch a Package</span></span>


<span data-ttu-id="1ca1e-104">次の手順を使用して、シーケンスされた既存のアプリケーションパッケージを並べて実行できるように、既存のシーケンスされたアプリケーションパッケージを変更します。</span><span class="sxs-lookup"><span data-stu-id="1ca1e-104">Use this procedure to modify an existing sequenced application package so you can run it side-by-side with the original sequenced application package.</span></span> <span data-ttu-id="1ca1e-105">このプロセスは "分岐" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="1ca1e-105">This process is called branching.</span></span> <span data-ttu-id="1ca1e-106">仮想アプリケーションパッケージを分岐すると、同じパッケージの2つのバージョンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="1ca1e-106">When you branch a virtual application package you are able to run two versions of the same package.</span></span> <span data-ttu-id="1ca1e-107">たとえば、既存のパッケージにサービスパックを適用し、元の順序が付けられた仮想アプリケーションパッケージと並行して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="1ca1e-107">For example, you can apply a service pack to an existing package, and run it side-by-side with the original sequenced virtual application package.</span></span>

<span data-ttu-id="1ca1e-108">順序付けされた仮想アプリケーションパッケージを分岐するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="1ca1e-108">Use the following procedure to branch a sequenced virtual application package.</span></span>

**<span data-ttu-id="1ca1e-109">シーケンス仮想アプリケーションパッケージを分岐するには</span><span class="sxs-lookup"><span data-stu-id="1ca1e-109">To branch a sequenced virtual application package</span></span>**

1.  <span data-ttu-id="1ca1e-110">Microsoft Application Virtualization (App-v) Sequencer を開きます。</span><span class="sxs-lookup"><span data-stu-id="1ca1e-110">Open the Microsoft Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="1ca1e-111">分岐するパッケージ (sprj) を含むターゲットディレクトリを指定するには、[**ファイル**]、[**開く**] のように選びます。</span><span class="sxs-lookup"><span data-stu-id="1ca1e-111">To specify the destination directory that contains the package (.sprj) you want to branch select **File**, **Open**.</span></span>

2.  <span data-ttu-id="1ca1e-112">分岐する順序が付けられたアプリケーションが含まれているディレクトリに移動し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ca1e-112">Navigate to the directory that contains the sequenced application you plan to branch and click **Open**.</span></span>

3.  <span data-ttu-id="1ca1e-113">パッケージのコピーを保存するには、App-v の Sequencer で [**ファイル**]、[**名前を付けて保存**] の順番に選びます。</span><span class="sxs-lookup"><span data-stu-id="1ca1e-113">To save a copy of the package, in the App-V Sequencer, select **File**, **Save As**.</span></span> <span data-ttu-id="1ca1e-114">新しい一意の名前を指定し、パッケージのコピー用に新しい一意のパッケージルートディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="1ca1e-114">Specify a new, unique name, and specify a new unique package root directory for the copy of the package.</span></span> <span data-ttu-id="1ca1e-115">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ca1e-115">Click **Save**.</span></span>

    **<span data-ttu-id="1ca1e-116">重要</span><span class="sxs-lookup"><span data-stu-id="1ca1e-116">Important</span></span>**  
    <span data-ttu-id="1ca1e-117">新しいパッケージ名を指定する必要があります。パッケージの既存のバージョンは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="1ca1e-117">You must specify a new package name or you will overwrite the existing version of the package.</span></span>



~~~
The sequencer will automatically generate new GUID files for the new package. The version number associated with the package will also be automatically appended to the OSD file name.
~~~

4. <span data-ttu-id="1ca1e-118">新しいバージョンを保存した後で、必要な構成の変更を適用し、関連付けられた ICO、OSD、SFT、SPRJ の各ファイルを Application Virtualization (App-v) サーバー上の適切な場所に保存できます。</span><span class="sxs-lookup"><span data-stu-id="1ca1e-118">After you save the new version you can apply the required configuration changes and save the associated ICO, OSD, SFT, and SPRJ files to correct location on the Application Virtualization (App-V) server.</span></span>

## <span data-ttu-id="1ca1e-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1ca1e-119">Related topics</span></span>


[<span data-ttu-id="1ca1e-120">Application Virtualization Sequencer のタスク</span><span class="sxs-lookup"><span data-stu-id="1ca1e-120">Tasks for the Application Virtualization Sequencer</span></span>](tasks-for-the-application-virtualization-sequencer.md)









