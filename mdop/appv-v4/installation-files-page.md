---
title: '[インストール ファイル] ページ'
description: '[インストール ファイル] ページ'
author: dansimp
ms.assetid: b0aad26f-b143-4f09-87a1-9f016a23cb62
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 08a2e7318271503f072298ca137a1e65e16c0178
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816344"
---
# <span data-ttu-id="f3374-103">[インストール ファイル] ページ</span><span class="sxs-lookup"><span data-stu-id="f3374-103">Installation Files Page</span></span>


<span data-ttu-id="f3374-104">[**インストールファイル**] ページを使用して、このウィザードの **[パッケージの選択**] ページで指定した仮想アプリケーションパッケージの作成に使用したインストールファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3374-104">Use the **Installation Files** page to specify the installation files that were used to create the virtual application package specified on the **Select Package** page of this wizard.</span></span> <span data-ttu-id="f3374-105">複数のアプリケーションを含む仮想アプリケーションパッケージを作成した場合は、必要なすべてのインストールファイルを、Microsoft Application Virtualization Sequencer を実行しているコンピューター上の1つのフォルダーにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3374-105">If you created a virtual application package that contains multiple applications, you should copy all required installation files to a single folder on the computer running the Microsoft Application Virtualization Sequencer.</span></span>

<span data-ttu-id="f3374-106">このページには、次の要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f3374-106">This page contains the following elements:</span></span>

<a href="" id="original-installation-files"></a>**<span data-ttu-id="f3374-107">元のインストールファイル</span><span class="sxs-lookup"><span data-stu-id="f3374-107">Original Installation Files</span></span>**  
<span data-ttu-id="f3374-108">[**参照**] をクリックして、仮想アプリケーションパッケージを作成するために最初に使用したインストールファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3374-108">Click **Browse** to specify the installation files that were originally used to create the virtual application package.</span></span> <span data-ttu-id="f3374-109">指定した親ディレクトリは、Sequencer を実行しているコンピューターにローカルに保存され、インストールファイルを含む必要なすべてのインストールファイルまたはサブフォルダーが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3374-109">The parent directory you specify should be saved locally to the computer running the Sequencer and must contain all required installation files or subfolders that contain the installation files.</span></span> <span data-ttu-id="f3374-110">インストールファイルは、親フォルダーまたは指定した親フォルダーの任意のサブフォルダーに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f3374-110">The installation files can be contained in the parent folder or in any of the subfolders of the specified parent folder.</span></span>

<a href="" id="files-installed-on-local-system"></a>**<span data-ttu-id="f3374-111">ローカルシステムにインストールされたファイル</span><span class="sxs-lookup"><span data-stu-id="f3374-111">Files installed on local system</span></span>**  
<span data-ttu-id="f3374-112">[**参照**] をクリックして、Sequencer を実行しているコンピューターにローカルでインストールされているインストールファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3374-112">Click **Browse** to specify the installation files that have been installed locally on the computer running the Sequencer.</span></span> <span data-ttu-id="f3374-113">このオプションを選ぶことができるのは、アプリケーションのインストールファイルがアプリケーションの既定の場所にインストールされている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="f3374-113">You can only select this option if the application installation files have been installed to the application’s default location.</span></span>

<span data-ttu-id="f3374-114">**注** 指定する既定のインストール場所は、次の条件によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f3374-114">**Note** The default installation location you provide depends on the following conditions:</span></span>

 

-   <span data-ttu-id="f3374-115">パッケージが最初に作成されたときに指定されたパッケージルート。</span><span class="sxs-lookup"><span data-stu-id="f3374-115">The package root specified when the package was originally created.</span></span>

-   <span data-ttu-id="f3374-116">パッケージを最初に作成したときに Windows インストーラーで指定したインストール場所。</span><span class="sxs-lookup"><span data-stu-id="f3374-116">The installation location specified in the Windows Installer when the package was originally created.</span></span>

-   <span data-ttu-id="f3374-117">既定のアプリケーションのインストールパス。</span><span class="sxs-lookup"><span data-stu-id="f3374-117">The default application installation path.</span></span>

<span data-ttu-id="f3374-118">たとえば、指定されたパッケージルートが**Q:\\Office12**であり、インストール中に、既定のインストール場所が Q:\\Office12 **at ファイル**¥ office 12 から**Q:\\Office12**に変更されている場合、退避時に指定したパスは**c/l ¥ Office 12**に変更します。</span><span class="sxs-lookup"><span data-stu-id="f3374-118">For example, if the package root specified is **Q:\\Office12** and during installation, the default installation location is changed from **C:\\Program Files\\Office12** to **Q:\\Office12**, then the path specified during dehydration must be **C:\\Program Files\\Office 12**.</span></span>

<span data-ttu-id="f3374-119">指定されたパッケージルートが**Q:\\Microsoft**であり、インストール中に、退避中に指定されたパスが**Q:\\Microsoft\\Office12**の**ファイル\*\*\*\*に変更**されます。</span><span class="sxs-lookup"><span data-stu-id="f3374-119">If the package root specified is **Q:\\Microsoft** and during installation, the default installation location is changed from **C:\\Program Files\\Office12** to **Q:\\Microsoft\\Office12**, then the path specified during dehydration must be **C:\\Program Files**.</span></span>

<span data-ttu-id="f3374-120">パッケージアクセラレータを使ってパッケージを作成する場合、パッケージ**Q:\\Office12\\file.txt**内の各ファイルは、パッケージルート**Q:\\Office12**を作成したときに指定された既定の場所 (たとえば、c/ **l/12**) に置き換えて、ローカルコンピューターで検出されます。</span><span class="sxs-lookup"><span data-stu-id="f3374-120">When you create a package using a package accelerator, each file in the package, for example **Q:\\Office12\\file.txt** is found on the local computer by replacing the package root **Q:\\Office12** with the default location specified when the Package Accelerator was created, for example, **C:\\Program Files\\Office12**.</span></span> <span data-ttu-id="f3374-121">上の例では、ファイルは\*\*c/c \*\*/1 Files\\Office12\\file.txtにあります。</span><span class="sxs-lookup"><span data-stu-id="f3374-121">In the previous example, the file should be located in **C:\\Program Files\\Office12\\file.txt**.</span></span>

## <span data-ttu-id="f3374-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f3374-122">Related topics</span></span>


[<span data-ttu-id="f3374-123">パッケージ アクセラレータの作成ウィザード (AppV 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="f3374-123">Create Package Accelerator Wizard (AppV 4.6 SP1)</span></span>](create-package-accelerator-wizard--appv-46-sp1-.md)

 

 





