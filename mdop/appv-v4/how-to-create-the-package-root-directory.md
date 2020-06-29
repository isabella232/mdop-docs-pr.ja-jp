---
title: パッケージ ルート ディレクトリを作成する方法
description: パッケージ ルート ディレクトリを作成する方法
author: dansimp
ms.assetid: bcfe3bd4-6c60-409a-8ffa-cc22f27194b1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c9e1e7be71627d4e55eff7a4e2582a21b834876d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817627"
---
# <span data-ttu-id="ad196-103">パッケージ ルート ディレクトリを作成する方法</span><span class="sxs-lookup"><span data-stu-id="ad196-103">How to Create the Package Root Directory</span></span>


<span data-ttu-id="ad196-104">パッケージルートディレクトリは、シーケンス付けされたアプリケーションのファイルがインストールされる、App-v Sequencer を実行しているコンピューター上のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="ad196-104">The package root directory is the directory on the computer running the App-V Sequencer where files for the sequenced application are installed.</span></span> <span data-ttu-id="ad196-105">このディレクトリは、シーケンスされたアプリケーションをストリーミングするコンピューター上でも実質的に存在します。</span><span class="sxs-lookup"><span data-stu-id="ad196-105">This directory also exists virtually on the computer to which a sequenced application will be streamed.</span></span> <span data-ttu-id="ad196-106">新しいアプリケーションのインストールを監視する前に、パッケージルートディレクトリを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad196-106">You should create the package root directory before you monitor the installation of a new application.</span></span>

<span data-ttu-id="ad196-107">パッケージルートディレクトリを作成したら、アプリケーションのシーケンスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="ad196-107">After you have created the package root directory, you can begin sequencing applications.</span></span> <span data-ttu-id="ad196-108">新しいアプリケーションのシーケンスの詳細については、「 [Sequencer をインストールする方法](how-to-install-the-sequencer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad196-108">For more information about sequencing a new application, see [How to Install the Sequencer](how-to-install-the-sequencer.md).</span></span>

**<span data-ttu-id="ad196-109">パッケージルートディレクトリを作成するには</span><span class="sxs-lookup"><span data-stu-id="ad196-109">To create the package root directory</span></span>**

1.  <span data-ttu-id="ad196-110">パッケージルートディレクトリを作成するには、App-v Sequencer を実行しているコンピューターで、Q:\\ drive を指定したネットワークの場所にマップします。</span><span class="sxs-lookup"><span data-stu-id="ad196-110">To create the package root directory, on the computer running the App-V Sequencer, map the Q:\\ drive to the specified network location.</span></span> <span data-ttu-id="ad196-111">指定した場所には、順序を設定するアプリケーションを保存するための十分な領域がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad196-111">The location you specify should have sufficient space to save the application you are sequencing.</span></span>

2.  <span data-ttu-id="ad196-112">新しい仮想アプリケーションに使用できるディレクトリを作成するには、Q:\\ ドライブ上にフォルダーを作成し、それに名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ad196-112">To create a directory that you can use for a new virtual application, create a folder on the Q:\\ drive and assign it a name.</span></span>

    <span data-ttu-id="ad196-113">**重要** パッケージルートディレクトリに保存される仮想アプリケーションファイルに割り当てる名前では、8.3 の名前付け形式を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad196-113">**Important** The name you assign to virtual application files that will be saved in the package root directory should use the 8.3 naming format.</span></span> <span data-ttu-id="ad196-114">ファイル名は、3文字のファイル名拡張子を持つ8文字以内にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad196-114">The file names should be no longer than 8 characters with a three-character file name extension.</span></span>

     

## <span data-ttu-id="ad196-115">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ad196-115">Related topics</span></span>


[<span data-ttu-id="ad196-116">Application Virtualization Sequencer のタスク</span><span class="sxs-lookup"><span data-stu-id="ad196-116">Tasks for the Application Virtualization Sequencer</span></span>](tasks-for-the-application-virtualization-sequencer.md)

 

 





