---
title: 既存の Windows インストーラー ファイルに関連付けられているオペレーティング システムを変更する方法
description: 既存の Windows インストーラー ファイルに関連付けられているオペレーティング システムを変更する方法
author: dansimp
ms.assetid: 0633f7e2-aebf-4e00-be02-35bc59dec420
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 63184852f996cbe09b476f456f7c2b509549f4fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816954"
---
# <span data-ttu-id="bce75-103">既存の Windows インストーラー ファイルに関連付けられているオペレーティング システムを変更する方法</span><span class="sxs-lookup"><span data-stu-id="bce75-103">How to Modify the Operating Systems Associated With an Existing Windows Installer File</span></span>


<span data-ttu-id="bce75-104">次の手順を使用して、App-v Sequencer を使用して作成された既存の Windows インストーラー (**MSI**) ファイルに関連付けられているオペレーティングシステムのバージョンを変更します。</span><span class="sxs-lookup"><span data-stu-id="bce75-104">Use the following procedure to modify the operating system versions associated with an existing Windows Installer (**MSI**) file that was created by using the App-V Sequencer.</span></span>

**<span data-ttu-id="bce75-105">既存の Windows インストーラーファイルのオペレーティングシステムを変更するには</span><span class="sxs-lookup"><span data-stu-id="bce75-105">To modify the operating systems of an existing Windows Installer file</span></span>**

1.  <span data-ttu-id="bce75-106">オペレーティングシステムのみがインストールされている環境内のコンピューターに、App-v Sequencer をインストールします。</span><span class="sxs-lookup"><span data-stu-id="bce75-106">Install the App-V Sequencer on a computer in your environment that has only the operating system installed.</span></span> <span data-ttu-id="bce75-107">または、仮想環境を実行しているコンピューター (Microsoft Virtual PC など) に Sequencer をインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bce75-107">Alternatively, you can install the Sequencer on a computer running a virtual environment—for example, Microsoft Virtual PC.</span></span> <span data-ttu-id="bce75-108">この方法は、最小限の追加構成で再利用できるクリーンなシーケンス環境を維持するのが容易であるために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bce75-108">This method is useful because it is easier to maintain a clean sequencing environment that you can reuse with minimal additional configuration.</span></span> <span data-ttu-id="bce75-109">App-v Sequencer のインストールの詳細については、「 [Sequencer をインストールする方法](how-to-install-the-sequencer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bce75-109">For more information about installing the App-V Sequencer, see [How to Install the Sequencer](how-to-install-the-sequencer.md).</span></span>

2.  <span data-ttu-id="bce75-110">変更する Windows Installer ファイルが格納されている仮想アプリケーションパッケージ全体を、Sequencer を実行しているコンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="bce75-110">Copy the entire virtual application package that contains the Windows Installer file you want to modify to the computer running the Sequencer.</span></span>

3.  <span data-ttu-id="bce75-111">Windows インストーラファイルを変更するには、Sequencer コンソールを開き、[**パッケージ**を開く] を選択し  /  **Open**て、Windows installer ファイルに関連付けられている仮想アプリケーションパッケージの保存場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="bce75-111">To modify the Windows Installer file, open the Sequencer console, select **Package** / **Open**, and then browse to the location where the virtual application package associated with the Windows Installer file is saved.</span></span>

4.  <span data-ttu-id="bce75-112">オペレーティングシステムを追加または削除するには、Sequencer コンソールの [**展開**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="bce75-112">To add or remove operating systems, select the **Deployment** tab in the Sequencer console.</span></span> <span data-ttu-id="bce75-113">Windows インストーラーファイルに関連付けられる追加のオペレーティングシステムを指定するには、目的のオペレーティングシステムを選択し、**選択**したオペレーティングシステムのリストコントロールを指す矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bce75-113">To specify additional operating systems that will be associated with the Windows Installer file, select the desired operating system, and then click the arrow that points to the **Selected** operating system list control.</span></span>

    <span data-ttu-id="bce75-114">オペレーティングシステムの関連付けを削除するには、削除するオペレーティングシステムを選択し、**使用可能な**オペレーティングシステムのリストコントロールを指す矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bce75-114">To remove an operating system association, select the operating system you want to remove, and then click the arrow that points to the **Available** operating system list control.</span></span>

5.  <span data-ttu-id="bce75-115">仮想アプリケーションパッケージに関連付けられる新しい Windows インストーラーを作成するには、[ **Microsoft Windows installer (MSI) パッケージの生成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="bce75-115">To create a new Windows Installer that will be associated with the virtual application package, select **Generate Microsoft Windows Installer (MSI) Package**.</span></span> <span data-ttu-id="bce75-116">または、「**ツール**」「MSI の作成」を選択することもでき  /  **Create MSI**ます。</span><span class="sxs-lookup"><span data-stu-id="bce75-116">Alternatively, you can select **Tools** / **Create MSI**.</span></span>

    <span data-ttu-id="bce75-117">**注** [**ツール**] の [MSI の作成] を選ん / **Create MSI**で新しい Windows インストーラーファイルを作成する場合は、**手順 6**を省略できます。</span><span class="sxs-lookup"><span data-stu-id="bce75-117">**Note** If you select **Tools** / **Create MSI** to create a new Windows Installer file, you can skip **Step 6** of this procedure.</span></span>

     

6.  <span data-ttu-id="bce75-118">仮想アプリケーションパッケージを保存するには、[**パッケージ**の保存] を選び  /  **Save**ます。</span><span class="sxs-lookup"><span data-stu-id="bce75-118">To save the virtual application package, select **Package** / **Save**.</span></span>

## <span data-ttu-id="bce75-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bce75-119">Related topics</span></span>


[<span data-ttu-id="bce75-120">Application Virtualization Sequencer のタスク</span><span class="sxs-lookup"><span data-stu-id="bce75-120">Tasks for the Application Virtualization Sequencer</span></span>](tasks-for-the-application-virtualization-sequencer.md)

 

 





