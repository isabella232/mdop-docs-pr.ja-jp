---
title: コマンド ラインを使用してシーケンス処理されたアプリケーションを開く方法
description: コマンド ラインを使用してシーケンス処理されたアプリケーションを開く方法
author: dansimp
ms.assetid: dc23ee65-8aea-470e-bb3f-a2f2b06cb241
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c99ab6b41947fc255afa9cad5b3ed2e22e672c3e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816917"
---
# <span data-ttu-id="d30d4-103">コマンド ラインを使用してシーケンス処理されたアプリケーションを開く方法</span><span class="sxs-lookup"><span data-stu-id="d30d4-103">How to Open a Sequenced Application Using the Command Line</span></span>


<span data-ttu-id="d30d4-104">仮想アプリケーションパッケージは、コマンドラインを使用して開くことができます。</span><span class="sxs-lookup"><span data-stu-id="d30d4-104">You can open virtual application packages using the command line.</span></span> <span data-ttu-id="d30d4-105">**コマンド**プロンプトは管理者として実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d30d4-105">You must run the **cmd** prompt as an administrator.</span></span>

<span data-ttu-id="d30d4-106">コマンドラインを使用してシーケンス処理されたアプリケーションパッケージを開くには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="d30d4-106">Use the following procedure to open sequenced application packages using the command line</span></span>

**<span data-ttu-id="d30d4-107">コマンドラインを使用してシーケンスされたアプリケーションを開くには</span><span class="sxs-lookup"><span data-stu-id="d30d4-107">To open a sequenced application using the command line</span></span>**

1.  <span data-ttu-id="d30d4-108">コマンドプロンプトを開くには、[**開始**] をクリックして、[**実行**] を選択し、「 **cmd**」と入力して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d30d4-108">To open the command prompt, click **Start**, and select **Run**, type **cmd**, and click **OK**.</span></span>

2.  <span data-ttu-id="d30d4-109">コマンドプロンプトで「 **cd\ \** 」と入力して、Sequencer がインストールされているディレクトリへのパスを指定し、enter キーを押し\*\*ます。*\*</span><span class="sxs-lookup"><span data-stu-id="d30d4-109">At a command prompt, type **cd\\** and specify the path to the directory where the Sequencer is installed and then press **Enter.**</span></span>

3.  <span data-ttu-id="d30d4-110">コマンドプロンプトで、次のコマンドを入力します。斜体のテキストは、入力した値に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="d30d4-110">At the command prompt, type the following command, replacing the italicized text with your values:</span></span>

    <span data-ttu-id="d30d4-111">SFTSequencer/open:*"開くために sprj ファイルを指定してください"*</span><span class="sxs-lookup"><span data-stu-id="d30d4-111">SFTSequencer /OPEN:*”specifies the .sprj file to open"*</span></span>

    <span data-ttu-id="d30d4-112">Enter**キーを押します**。</span><span class="sxs-lookup"><span data-stu-id="d30d4-112">Press **Enter**.</span></span>

4.  <span data-ttu-id="d30d4-113">次のオプションのパラメーターを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d30d4-113">You can also specify the following optional parameters.</span></span> <span data-ttu-id="d30d4-114">コマンドプロンプトで、次のコマンドを入力します。斜体のテキストは、入力した値に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="d30d4-114">At the command prompt, type the following commands, replacing the italicized text with your values:</span></span>

    <span data-ttu-id="d30d4-115">/PACKAGENAME: "*パッケージ名を指定します"*</span><span class="sxs-lookup"><span data-stu-id="d30d4-115">/PACKAGENAME:"*specifies the package name"*</span></span>

    <span data-ttu-id="d30d4-116">/MSI-関連付けられている Microsoft Windows インストーラーの生成を指定します。</span><span class="sxs-lookup"><span data-stu-id="d30d4-116">/MSI - specifies generating an associated Microsoft Windows Installer.</span></span>

    <span data-ttu-id="d30d4-117">/COMPRESS –パッケージを圧縮するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d30d4-117">/COMPRESS – specifies if the package will be compressed.</span></span> <span data-ttu-id="d30d4-118">既定では、パッケージは圧縮されません。</span><span class="sxs-lookup"><span data-stu-id="d30d4-118">By default, packages are not compressed.</span></span>

    <span data-ttu-id="d30d4-119">Enter**キーを押します**。</span><span class="sxs-lookup"><span data-stu-id="d30d4-119">Press **Enter**.</span></span>

    <span data-ttu-id="d30d4-120">**注** インストーラーパッケージまたは Windows Installer パッケージにグラフィカルなユーザーインターフェイスが含まれている場合は、コマンドラインパラメーターを指定した後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d30d4-120">**Note** If the installer or Windows Installer package has a graphical user interface, it will be displayed after you specify the command-line parameters.</span></span>

     

## <span data-ttu-id="d30d4-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d30d4-121">Related topics</span></span>


[<span data-ttu-id="d30d4-122">コマンド ラインを使用して仮想アプリケーションを管理する方法</span><span class="sxs-lookup"><span data-stu-id="d30d4-122">How to Manage Virtual Applications Using the Command Line</span></span>](how-to-manage-virtual-applications-using-the-command-line.md)

 

 





