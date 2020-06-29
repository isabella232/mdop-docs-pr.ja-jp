---
title: コマンド ライン エラー
description: コマンド ライン エラー
author: dansimp
ms.assetid: eea62568-4e90-4877-9cc7-e27ef5c05068
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ab29a77dc15a8c7bd3590b918a7ca8c1ca6e8c0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819407"
---
# <span data-ttu-id="d0cf4-103">コマンド ライン エラー</span><span class="sxs-lookup"><span data-stu-id="d0cf4-103">Command-Line Errors</span></span>


<span data-ttu-id="d0cf4-104">以下のエラーリストを使用して、コマンドラインの順序付けが正常に機能していない理由を特定します。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-104">Use the following list of errors to identify the reasons why command-line sequencing is not working properly.</span></span> <span data-ttu-id="d0cf4-105">また、sequencer ログファイルを表示して、これらのエラーを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-105">You can also see these errors by viewing the sequencer log file.</span></span>

<span data-ttu-id="d0cf4-106">**注** 順序付け時に複数のエラーが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-106">**Note** More than one error might be displayed when sequencing.</span></span> <span data-ttu-id="d0cf4-107">さらに、表示されるエラーコードは、2つのエラーコードの合計である場合があります。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-107">Furthermore, the error code displayed might be the sum of two error codes.</span></span> <span data-ttu-id="d0cf4-108">たとえば、 */InstallPath*パラメーターと */OutputFile*パラメーターが指定されていない場合、Microsoft System Center Application Virtualization Sequencer は 96 (2 つのエラーコードの合計) を返します。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-108">For example, if the */InstallPath* and */OutputFile* parameters are missing, the Microsoft System Center Application Virtualization Sequencer will return 96—the sum of the two error codes.</span></span>

 

<a href="" id="01"></a><span data-ttu-id="d0cf4-109">付き</span><span class="sxs-lookup"><span data-stu-id="d0cf4-109">01</span></span>  
<span data-ttu-id="d0cf4-110">予期しないエラーが発生しています。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-110">There is an unspecified error.</span></span>

<a href="" id="02"></a><span data-ttu-id="d0cf4-111">+</span><span class="sxs-lookup"><span data-stu-id="d0cf4-111">02</span></span>  
<span data-ttu-id="d0cf4-112">指定したインストールディレクトリ (/INSTALLPACKAGE) が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-112">The specified installation directory (/INSTALLPACKAGE) specified is not valid.</span></span>

<a href="" id="04"></a><span data-ttu-id="d0cf4-113">04</span><span class="sxs-lookup"><span data-stu-id="d0cf4-113">04</span></span>  
<span data-ttu-id="d0cf4-114">指定されたパッケージルートディレクトリ (/INSTALLPATH) が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-114">The specified package root directory (/INSTALLPATH) is not valid.</span></span>

<a href="" id="08"></a><span data-ttu-id="d0cf4-115">08</span><span class="sxs-lookup"><span data-stu-id="d0cf4-115">08</span></span>  
<span data-ttu-id="d0cf4-116">指定された */OutputFile*パラメーターが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-116">The */OutputFile* parameter that was specified is not valid.</span></span>

<a href="" id="16"></a><span data-ttu-id="d0cf4-117">16</span><span class="sxs-lookup"><span data-stu-id="d0cf4-117">16</span></span>  
<span data-ttu-id="d0cf4-118">インストールディレクトリ (/INSTALLPACKAGE) が指定されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-118">The installation directory (/INSTALLPACKAGE) was not specified.</span></span>

<a href="" id="32"></a><span data-ttu-id="d0cf4-119">32</span><span class="sxs-lookup"><span data-stu-id="d0cf4-119">32</span></span>  
<span data-ttu-id="d0cf4-120">パッケージルートディレクトリ (/INSTALLPATH) が指定されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-120">The package root directory (/INSTALLPATH) was not specified.</span></span>

<a href="" id="64"></a><span data-ttu-id="d0cf4-121">64</span><span class="sxs-lookup"><span data-stu-id="d0cf4-121">64</span></span>  
<span data-ttu-id="d0cf4-122">*/OutputFile*パラメーターが指定されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-122">The */OutputFile* parameter was not specified.</span></span>

<a href="" id="128"></a><span data-ttu-id="d0cf4-123">128</span><span class="sxs-lookup"><span data-stu-id="d0cf4-123">128</span></span>  
<span data-ttu-id="d0cf4-124">指定した application virtualization ドライブは有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-124">The specified application virtualization drive is not valid.</span></span>

<a href="" id="256"></a><span data-ttu-id="d0cf4-125">256</span><span class="sxs-lookup"><span data-stu-id="d0cf4-125">256</span></span>  
<span data-ttu-id="d0cf4-126">インストーラーが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-126">The installer failed.</span></span>

<a href="" id="512"></a><span data-ttu-id="d0cf4-127">512</span><span class="sxs-lookup"><span data-stu-id="d0cf4-127">512</span></span>  
<span data-ttu-id="d0cf4-128">アプリケーションのシーケンス処理に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-128">Sequencing the application failed.</span></span>

<a href="" id="1024"></a><span data-ttu-id="d0cf4-129">1024</span><span class="sxs-lookup"><span data-stu-id="d0cf4-129">1024</span></span>  
<span data-ttu-id="d0cf4-130">インストールされたショートカットの評価に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-130">Evaluating installed shortcuts failed.</span></span>

<a href="" id="2048"></a><span data-ttu-id="d0cf4-131">2048</span><span class="sxs-lookup"><span data-stu-id="d0cf4-131">2048</span></span>  
<span data-ttu-id="d0cf4-132">シーケンス付きのアプリケーションパッケージを保存できません。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-132">The sequenced application package cannot be saved.</span></span>

<a href="" id="4096"></a><span data-ttu-id="d0cf4-133">4096</span><span class="sxs-lookup"><span data-stu-id="d0cf4-133">4096</span></span>  
<span data-ttu-id="d0cf4-134">指定されたパッケージ名 (/PACKAGENAME) が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-134">The specified package name (/PACKAGENAME) is not valid.</span></span>

<a href="" id="8192"></a><span data-ttu-id="d0cf4-135">8192</span><span class="sxs-lookup"><span data-stu-id="d0cf4-135">8192</span></span>  
<span data-ttu-id="d0cf4-136">指定したブロックサイズ (/KB <em> ) </em> が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-136">The specified block size (/BLOCKSIZE<em>)</em> is not valid.</span></span>

<a href="" id="16384"></a><span data-ttu-id="d0cf4-137">16384</span><span class="sxs-lookup"><span data-stu-id="d0cf4-137">16384</span></span>  
<span data-ttu-id="d0cf4-138">指定された圧縮の種類 (圧縮) が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-138">The specified compression type (/COMPRESSION) is not valid.</span></span>

<a href="" id="32768"></a><span data-ttu-id="d0cf4-139">32768</span><span class="sxs-lookup"><span data-stu-id="d0cf4-139">32768</span></span>  
<span data-ttu-id="d0cf4-140">指定されたプロジェクトパスが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-140">The specified project path is not valid.</span></span>

<a href="" id="65536"></a><span data-ttu-id="d0cf4-141">65536</span><span class="sxs-lookup"><span data-stu-id="d0cf4-141">65536</span></span>  
<span data-ttu-id="d0cf4-142">指定されたアップグレードパラメーターが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-142">The specified upgrade parameter is not valid.</span></span>

<a href="" id="131072"></a><span data-ttu-id="d0cf4-143">131072</span><span class="sxs-lookup"><span data-stu-id="d0cf4-143">131072</span></span>  
<span data-ttu-id="d0cf4-144">指定されたアップグレードプロジェクトパラメーターが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-144">The specified upgrade project parameter is not valid.</span></span>

<a href="" id="262144"></a><span data-ttu-id="d0cf4-145">262144</span><span class="sxs-lookup"><span data-stu-id="d0cf4-145">262144</span></span>  
<span data-ttu-id="d0cf4-146">指定したデコードパスパラメーターが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-146">The specified decode path parameter is not valid.</span></span>

<a href="" id="525288"></a><span data-ttu-id="d0cf4-147">525288</span><span class="sxs-lookup"><span data-stu-id="d0cf4-147">525288</span></span>  
<span data-ttu-id="d0cf4-148">パッケージ名が指定されていませんでした。</span><span class="sxs-lookup"><span data-stu-id="d0cf4-148">The package name was not specified.</span></span>

## <span data-ttu-id="d0cf4-149">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d0cf4-149">Related topics</span></span>


[<span data-ttu-id="d0cf4-150">Sequencer コマンド ラインの使用について</span><span class="sxs-lookup"><span data-stu-id="d0cf4-150">About Using the Sequencer Command Line</span></span>](about-using-the-sequencer-command-line.md)

[<span data-ttu-id="d0cf4-151">コマンド ライン パラメーター</span><span class="sxs-lookup"><span data-stu-id="d0cf4-151">Command-Line Parameters</span></span>](command-line-parameters.md)

 

 





