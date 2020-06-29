---
title: DaRT 7.0 を展開する方法
description: DaRT 7.0 を展開する方法
author: dansimp
ms.assetid: 30522441-40cb-4eca-99b4-dff758f5c647
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2059b64e5f3ae7af8926bc00e5965598ede4288
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813050"
---
# <span data-ttu-id="9d3cb-103">DaRT 7.0 を展開する方法</span><span class="sxs-lookup"><span data-stu-id="9d3cb-103">How to Deploy DaRT 7.0</span></span>


<span data-ttu-id="9d3cb-104">このトピックでは、お使いの環境に Microsoft Diagnostics and Recovery ツールセット (DaRT) 7 を展開する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-104">This topic provides instructions to deploy Microsoft Diagnostics and Recovery Toolset (DaRT)7 in your environment.</span></span> <span data-ttu-id="9d3cb-105">このトピックの最初の手順では、すべての機能を1つの管理者コンピューターにインストールすることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-105">The first procedure in this topic assumes that you are installing all functionality on one administrator computer.</span></span> <span data-ttu-id="9d3cb-106">たとえば、電子的なソフトウェア配布システムを使用して、複数のコンピューターに DaRT を展開またはアンインストールする必要がある場合は、コマンドラインインストールオプションの使用が簡単になることがあります。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-106">When you need to deploy or uninstall DaRT on multiple computers, using an electronic software distribution system for example, it might be easier to use command line installation options.</span></span> <span data-ttu-id="9d3cb-107">これらのオプションは、このトピックの2番目の手順で定義されています。ここでは、使用可能なコマンドラインオプションの使用例を示します。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-107">Those options are defined in the second procedure in this topic which provides example usage for the available command line options.</span></span>

<span data-ttu-id="9d3cb-108">**重要** DaRT をインストールする前に、コンピューターが[dart 7.0 でサポートされている構成](dart-70-supported-configurations-dart-7.md)の最小システム要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-108">**Important** Before you install DaRT, ensure that the computer meets the minimum system requirements listed in [DaRT 7.0 Supported Configurations](dart-70-supported-configurations-dart-7.md).</span></span>

 

**<span data-ttu-id="9d3cb-109">管理者コンピューターに DaRT をインストールするには</span><span class="sxs-lookup"><span data-stu-id="9d3cb-109">To install DaRT on an administrator computer</span></span>**

1.  <span data-ttu-id="9d3cb-110">ソフトウェアのダウンロードの一部として受け取った DaRT インストールファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-110">Locate the DaRT installation files that you received as part of your software download.</span></span>

2.  <span data-ttu-id="9d3cb-111">システム要件に対応する DaRT インストールファイル (32 ビットまたは64ビット) をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-111">Double-click the DaRT installation file that corresponds to your system requirements, either 32-bit or 64-bit.</span></span> <span data-ttu-id="9d3cb-112">DaRT のインストールファイルには**MSDaRT70.msi**という名前が付いています。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-112">The DaRT installation file is named **MSDaRT70.msi**.</span></span>

3.  <span data-ttu-id="9d3cb-113">Microsoft ソフトウェアライセンス条項に同意し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-113">Accept the Microsoft Software License Terms, and then click **Next**.</span></span>

4.  <span data-ttu-id="9d3cb-114">DaRT をインストールする保存先フォルダーを選択し、すべてのユーザに対して DaRT をインストールするか、現在のユーザのみをインストールするかを選択して、「**次へ**」をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-114">Select the destination folder for installing DaRT, select whether DaRT should be installed for all users or just the current user, and then click **Next**.</span></span>

5.  <span data-ttu-id="9d3cb-115">インストールを**標準**、**カスタム**、または**完全**のいずれにするかを選び、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-115">Select whether the installation should be **Typical**, **Custom**, or **Complete**, and then click **Next**.</span></span>

    -   <span data-ttu-id="9d3cb-116">**一般的**には、よく使われるツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-116">**Typical** installs the tools that are most frequently used.</span></span> <span data-ttu-id="9d3cb-117">この方法は、ほとんどのユーザーにお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-117">This method is recommended for most users.</span></span>

    -   <span data-ttu-id="9d3cb-118">[**カスタム**] インストールされているツールとそのインストール場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-118">**Custom** lets you select the tools that are installed and where they will be installed.</span></span> <span data-ttu-id="9d3cb-119">これは、特にさまざまなヘルプデスクのコンピューターにさまざまな DaRT ツールをインストールする場合に、上級ユーザーに推奨されます。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-119">This is recommended for advanced users, especially if you are installing different DaRT tools on different helpdesk computers.</span></span>

    -   <span data-ttu-id="9d3cb-120">**完了**すべての DaRT ツールをインストールし、最も多くのディスク領域を必要とします。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-120">**Complete** installs all DaRT tools and requires the most disk space.</span></span>

    <span data-ttu-id="9d3cb-121">インストール方法を選択したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-121">After you have selected your method of installation, click **Next**.</span></span>

6.  <span data-ttu-id="9d3cb-122">インストールを開始するには、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-122">To start the installation, click **Install**.</span></span>

7.  <span data-ttu-id="9d3cb-123">インストールが正常に完了したら、[**完了**] をクリックしてウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-123">After the installation is completed successfully, click **Finish** to exit the wizard.</span></span>

**<span data-ttu-id="9d3cb-124">コマンドプロンプトで DaRT をインストールするには</span><span class="sxs-lookup"><span data-stu-id="9d3cb-124">To install DaRT at the command prompt</span></span>**

1.  <span data-ttu-id="9d3cb-125">次の例は、すべての DaRT 機能をインストールする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-125">The following example shows how to install all DaRT functionality.</span></span>

    ``` syntax
    msiexec /i MSDaRT70.msi ADDLOCAL=CommonFiles,MSDaRTHelp,DaRTRecoveryImage,CrashAnalyzer,RemoteViewer 
    ```

2.  <span data-ttu-id="9d3cb-126">次の例は、 **DaRT Recovery イメージウィザード**のみをインストールする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-126">The following example shows how to install only the **DaRT Recovery Image Wizard**.</span></span>

    ``` syntax
    msiexec /i MSDaRT70.msi ADDLOCAL=CommonFiles,MSDaRTHelp,DaRTRecoveryImage
    ```

3.  <span data-ttu-id="9d3cb-127">次の例は、Crash Analyzer と DaRT リモート接続ビューアーのみをインストールする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-127">The following example shows how to install only the Crash Analyzer and the DaRT Remote Connection Viewer.</span></span>

    ``` syntax
    msiexec /i MSDaRT70.msi ADDLOCAL=CommonFiles,MSDaRTHelp,CrashAnalyzer,RemoteViewer 
    ```

4.  <span data-ttu-id="9d3cb-128">次の例では、Windows インストーラーのセットアップログを作成します。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-128">The following example creates a setup log for the Windows Installer.</span></span> <span data-ttu-id="9d3cb-129">これは、デバッグに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-129">This is valuable for debugging.</span></span>

    ``` syntax
    msiexec.exe /i MSDaRT70.msi /l*v log.txt 
    ```

<span data-ttu-id="9d3cb-130">**注** すべての DaRT インストールコマンドプロンプトオプションに/qn または/qb を追加して、サイレントインストールを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="9d3cb-130">**Note** You can add /qn or /qb to any of the DaRT installation command prompt options to perform a silent installation.</span></span>

 

## <span data-ttu-id="9d3cb-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9d3cb-131">Related topics</span></span>


[<span data-ttu-id="9d3cb-132">管理者用コンピューターへの DaRT 7.0 の展開</span><span class="sxs-lookup"><span data-stu-id="9d3cb-132">Deploying DaRT 7.0 to Administrator Computers</span></span>](deploying-dart-70-to-administrator-computers-dart-7.md)

 

 





