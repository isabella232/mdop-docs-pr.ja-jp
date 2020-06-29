---
title: パッケージを開くコマンドを使用してパッケージをアップグレードする方法
description: パッケージを開くコマンドを使用してパッケージをアップグレードする方法
author: dansimp
ms.assetid: 67c10440-de8a-4547-a34b-f83206d0cc3b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cca438fe90373e8f934d1d790246544cdf46fa18
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816517"
---
# <span data-ttu-id="ca54c-103">パッケージを開くコマンドを使用してパッケージをアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="ca54c-103">How to Upgrade a Package Using the Open Package Command</span></span>


<span data-ttu-id="ca54c-104">シーケンスされたアプリケーションパッケージの更新をアップグレードまたは適用するには、[パッケージを開く] コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ca54c-104">Use the Open Package command to upgrade or apply an update to a sequenced application package.</span></span> <span data-ttu-id="ca54c-105">コマンドラインを使用して既存の仮想アプリケーションパッケージをアップグレードすると、元のバージョンの sft ファイルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="ca54c-105">When you upgrade an existing virtual application package using the command line, the original version of the .sft file is deleted.</span></span> <span data-ttu-id="ca54c-106">コマンドラインを使用してパッケージをアップグレードする前に、関連付けられた sft ファイルをバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca54c-106">You should backup the associated .sft file before upgrading the package using the command line.</span></span>

**<span data-ttu-id="ca54c-107">[パッケージを開く] コマンドを使ってパッケージをアップグレードするには</span><span class="sxs-lookup"><span data-stu-id="ca54c-107">To upgrade a package using the Open Package command</span></span>**

1.  <span data-ttu-id="ca54c-108">アップグレードされるパッケージを開くには、Application Virtualization (App-v) コンソールで、[**ファイル**]、[**アップグレードのためにパッケージを開く**] の順番に選びます。</span><span class="sxs-lookup"><span data-stu-id="ca54c-108">To open the package that will be upgraded, in the Application Virtualization (App-V) console select **File**, **Open Package for Upgrade**.</span></span> <span data-ttu-id="ca54c-109">[**ファイルを開く**] ダイアログボックスで、アップグレードされるパッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="ca54c-109">In the **Open** dialog box, select the package that will be upgraded.</span></span>

2.  <span data-ttu-id="ca54c-110">**シーケンス**ウィザードを開始するには、[**ツール**] の [シーケンス処理]**ウィザード**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca54c-110">To start the **Sequencing** wizard, select **Tools**, **Sequencing Wizard**.</span></span> <span data-ttu-id="ca54c-111">ウィザードを完了して構成の変更を適用し、新しいシーケンス処理されたアプリケーションを保存するには、[**ファイル**]、[**保存**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ca54c-111">Complete the wizard applying the configuration changes, to save the new sequenced application, select **File**, **Save**.</span></span>

3.  <span data-ttu-id="ca54c-112">パッケージ名にバージョン番号を追加するには、Sequencer コンソールで [**ツール**] の [**オプション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca54c-112">To append the version number to the package name, in the Sequencer console, select **Tools**, **Options**.</span></span> <span data-ttu-id="ca54c-113">[**ファイル名にパッケージバージョンを追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca54c-113">Select **Append Package Version to Filename**.</span></span> <span data-ttu-id="ca54c-114">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca54c-114">Click **OK**.</span></span>

    <span data-ttu-id="ca54c-115">**重要** パッケージバージョンを使ってファイル名を更新することは、アップグレードを正常に完了するために不可欠です。</span><span class="sxs-lookup"><span data-stu-id="ca54c-115">**Important** Updating the file name with the package version is essential to successfully completing the upgrade.</span></span>

     

## <span data-ttu-id="ca54c-116">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ca54c-116">Related topics</span></span>


[<span data-ttu-id="ca54c-117">コマンド ラインを使用して仮想アプリケーションを管理する方法</span><span class="sxs-lookup"><span data-stu-id="ca54c-117">How to Manage Virtual Applications Using the Command Line</span></span>](how-to-manage-virtual-applications-using-the-command-line.md)

 

 





