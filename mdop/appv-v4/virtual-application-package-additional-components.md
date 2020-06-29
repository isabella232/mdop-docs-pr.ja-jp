---
title: 仮想アプリケーション パッケージの追加コンポーネント
description: 仮想アプリケーション パッケージの追加コンポーネント
author: dansimp
ms.assetid: 476b0f40-ebd6-4296-92fa-61fa9495c03c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: d30c2c6561b0d2c08fd75e0c977bf4590d7e6688
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815077"
---
# <span data-ttu-id="cbe7e-103">仮想アプリケーション パッケージの追加コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cbe7e-103">Virtual Application Package Additional Components</span></span>


<span data-ttu-id="cbe7e-104">App-v のアセンブリに依存している、64ビットと32ビットの実行可能ファイルとダイナミックリンクライブラリ (.dll) ファイルが含まれているディレクトリを検出しました。</span><span class="sxs-lookup"><span data-stu-id="cbe7e-104">The App-V Sequencer has detected a directory that contains 64-bit and 32-bit executables and/or dynamic-link library (.dll) files that depend on the same side-by-side assembly.</span></span> <span data-ttu-id="cbe7e-105">通常、Sequencer は、パッケージで使用されるすべてのパブリックアセンブリに対してプライベート side-by-side アセンブリを作成します。ただし、32ビットバージョンと64ビットバージョンのプライベートアセンブリを同じディレクトリで作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="cbe7e-105">Typically, the Sequencer creates private side-by-side assemblies for all public assemblies that are used by the package; however, it is not possible to create 32-bit and 64-bit versions of the private assemblies in the same directory.</span></span>

<span data-ttu-id="cbe7e-106">Sequencer が1つの競合を検出した場合は、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="cbe7e-106">If the Sequencer detects a single conflict, it will perform the following actions:</span></span>

-   <span data-ttu-id="cbe7e-107">ディレクトリに競合があるかどうかにかかわらず、パッケージ全体で既存のすべての64ビットプライベートアセンブリを削除します。</span><span class="sxs-lookup"><span data-stu-id="cbe7e-107">Remove all of the existing 64-bit private assemblies in the entire package, whether or not the directory has a conflict.</span></span>

-   <span data-ttu-id="cbe7e-108">32ビットバージョンのプライベート side-by-side アセンブリのみを作成します。</span><span class="sxs-lookup"><span data-stu-id="cbe7e-108">Create only 32-bit versions of the private side-by-side assemblies.</span></span>

<span data-ttu-id="cbe7e-109">Sequencer を実行しているコンピューターとすべての App-v クライアントコンピューターに、必要なすべての64ビットアセンブリの公開バージョンをネイティブにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbe7e-109">You should natively install public versions of all the required 64-bit assemblies on the computer running the Sequencer and on all App-V client computers.</span></span>

<span data-ttu-id="cbe7e-110">必要な既存のパブリックアセンブリを見つけるには、パッケージが保存されているディレクトリを開き、 **VFS**フォルダーを確認します。</span><span class="sxs-lookup"><span data-stu-id="cbe7e-110">To locate the required existing public assemblies, open the directory where the package is saved and look in the **VFS** folder.</span></span> <span data-ttu-id="cbe7e-111">たとえば、パッケージのルートが**Q:\\MyApp**である場合は、アプリケーションをシーケンスするときに、 **Q:\\MyApp\\VFS\\CSIDL\ _Windows \\winsxs\\manifests**を探して、既存のパブリックアセンブリをすべて検索します。</span><span class="sxs-lookup"><span data-stu-id="cbe7e-111">For example, if the package root is **Q:\\MyApp**, when you sequence the application, look in **Q:\\MyApp\\VFS\\CSIDL\_Windows\\WinSxS\\Manifests** and locate all of the existing public assemblies.</span></span> <span data-ttu-id="cbe7e-112">これらのファイルの64ビットバージョンでは、常にマニフェスト名の先頭に次のテキストが表示され**ます。**</span><span class="sxs-lookup"><span data-stu-id="cbe7e-112">The 64-bit versions of these files will always start with the following text at the beginning of the manifest name: **amd64…**.</span></span> <span data-ttu-id="cbe7e-113">アセンブリの正確な名前とバージョンは、関連付けられているマニフェストファイルに含まれています。</span><span class="sxs-lookup"><span data-stu-id="cbe7e-113">The exact name and version of the assembly can be found in the associated manifest file.</span></span>

<span data-ttu-id="cbe7e-114">以下のリンクのいずれかを使用して、必要な前提条件の適切なバージョンをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="cbe7e-114">Use any of the following links to download and install the correct version of the required prerequisites:</span></span>

-   [<span data-ttu-id="cbe7e-115">Microsoft Visual C++ 2005 再頒布可能パッケージ (x64)</span><span class="sxs-lookup"><span data-stu-id="cbe7e-115">Microsoft Visual C++ 2005 Redistributable Package (x64)</span></span>](https://go.microsoft.com/fwlink/?LinkId=152697)

-   [<span data-ttu-id="cbe7e-116">Microsoft Visual C++ 2005 SP1 再頒布可能パッケージ (x64)</span><span class="sxs-lookup"><span data-stu-id="cbe7e-116">Microsoft Visual C++ 2005 SP1 Redistributable Package (x64)</span></span>](https://go.microsoft.com/fwlink/?LinkId=152698)

-   [<span data-ttu-id="cbe7e-117">Microsoft Visual C++ 2008 再頒布可能パッケージ (x64)</span><span class="sxs-lookup"><span data-stu-id="cbe7e-117">Microsoft Visual C++ 2008 Redistributable Package (x64)</span></span>](https://go.microsoft.com/fwlink/?LinkId=152699)

-   [<span data-ttu-id="cbe7e-118">Microsoft Visual C++ 2008 SP1 再頒布可能パッケージ (x64)</span><span class="sxs-lookup"><span data-stu-id="cbe7e-118">Microsoft Visual C++ 2008 SP1 Redistributable Package (x64)</span></span>](https://go.microsoft.com/fwlink/?LinkId=152700)

 

 





