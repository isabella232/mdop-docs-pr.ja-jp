---
title: Sequencer コマンド ライン エラー コード
description: Sequencer コマンド ライン エラー コード
author: dansimp
ms.assetid: 3d491314-4923-45fd-9839-c541c5e620bd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 74f5bd0c1b66656ac6891dcc1c019254fa36fdac
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815557"
---
# <span data-ttu-id="13b03-103">Sequencer コマンド ライン エラー コード</span><span class="sxs-lookup"><span data-stu-id="13b03-103">Sequencer Command-Line Error Codes</span></span>


<span data-ttu-id="13b03-104">次の一覧は、コマンドラインを使用したアプリケーションの順序付けに関連するエラーを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="13b03-104">Use the following list to help identify errors that are related to sequencing applications by using the command line.</span></span> <span data-ttu-id="13b03-105">この情報は、関連する App-v のログファイルを表示することでも確認できます。</span><span class="sxs-lookup"><span data-stu-id="13b03-105">You can also see this information by viewing the associated App-V Sequencer log file.</span></span>

<span data-ttu-id="13b03-106">**注** シーケンス中に複数のエラーが発生する可能性があります。この場合、表示されるエラーコードは、2つのエラーコードの合計である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="13b03-106">**Note** Multiple errors can occur during sequencing, and if this happens, the error code that is displayed might be the sum of two error codes.</span></span> <span data-ttu-id="13b03-107">たとえば、 */InstallPath*パラメーターと */OutputFile*パラメーターが指定されていない場合、app-v Sequencer は**96**(2 つのエラーコードの合計) を返します。</span><span class="sxs-lookup"><span data-stu-id="13b03-107">For example, if the */InstallPath* and */OutputFile* parameters are missing, the App-V Sequencer will return **96**—the sum of the two error codes.</span></span>

 

<a href="" id="01"></a><span data-ttu-id="13b03-108">付き</span><span class="sxs-lookup"><span data-stu-id="13b03-108">01</span></span>  
<span data-ttu-id="13b03-109">予期しないエラーが発生しています。</span><span class="sxs-lookup"><span data-stu-id="13b03-109">There is an unspecified error.</span></span>

<a href="" id="02"></a><span data-ttu-id="13b03-110">+</span><span class="sxs-lookup"><span data-stu-id="13b03-110">02</span></span>  
<span data-ttu-id="13b03-111">指定されたインストールディレクトリ (/INSTALLPACKAGE) が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="13b03-111">The specified installation directory (/INSTALLPACKAGE) is not valid.</span></span>

<a href="" id="04"></a><span data-ttu-id="13b03-112">04</span><span class="sxs-lookup"><span data-stu-id="13b03-112">04</span></span>  
<span data-ttu-id="13b03-113">指定されたパッケージルートディレクトリ (/INSTALLPATH) が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="13b03-113">The specified package root directory (/INSTALLPATH) is not valid.</span></span>

<a href="" id="08"></a><span data-ttu-id="13b03-114">08</span><span class="sxs-lookup"><span data-stu-id="13b03-114">08</span></span>  
<span data-ttu-id="13b03-115">指定された */OutputFile*パラメーターが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="13b03-115">The specified */OutputFile* parameter is not valid.</span></span>

<a href="" id="16"></a><span data-ttu-id="13b03-116">16</span><span class="sxs-lookup"><span data-stu-id="13b03-116">16</span></span>  
<span data-ttu-id="13b03-117">インストールディレクトリ (/INSTALLPACKAGE) が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="13b03-117">The installation directory (/INSTALLPACKAGE) is not specified.</span></span>

<a href="" id="32"></a><span data-ttu-id="13b03-118">32</span><span class="sxs-lookup"><span data-stu-id="13b03-118">32</span></span>  
<span data-ttu-id="13b03-119">パッケージルートディレクトリ (/INSTALLPATH) が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="13b03-119">The package root directory (/INSTALLPATH) is not specified.</span></span>

<a href="" id="64"></a><span data-ttu-id="13b03-120">64</span><span class="sxs-lookup"><span data-stu-id="13b03-120">64</span></span>  
<span data-ttu-id="13b03-121">*/OutputFile*パラメーターが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="13b03-121">The */OutputFile* parameter is not specified.</span></span>

<a href="" id="128"></a><span data-ttu-id="13b03-122">128</span><span class="sxs-lookup"><span data-stu-id="13b03-122">128</span></span>  
<span data-ttu-id="13b03-123">指定した application virtualization ドライブは有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="13b03-123">The specified application virtualization drive is not valid.</span></span>

<a href="" id="256"></a><span data-ttu-id="13b03-124">256</span><span class="sxs-lookup"><span data-stu-id="13b03-124">256</span></span>  
<span data-ttu-id="13b03-125">インストーラーが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="13b03-125">The installer failed.</span></span>

<a href="" id="512"></a><span data-ttu-id="13b03-126">512</span><span class="sxs-lookup"><span data-stu-id="13b03-126">512</span></span>  
<span data-ttu-id="13b03-127">アプリケーションのシーケンス処理に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="13b03-127">Sequencing the application failed.</span></span>

<a href="" id="1024"></a><span data-ttu-id="13b03-128">1024</span><span class="sxs-lookup"><span data-stu-id="13b03-128">1024</span></span>  
<span data-ttu-id="13b03-129">インストールされたショートカットの評価に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="13b03-129">Evaluating installed shortcuts failed.</span></span>

<a href="" id="2048"></a><span data-ttu-id="13b03-130">2048</span><span class="sxs-lookup"><span data-stu-id="13b03-130">2048</span></span>  
<span data-ttu-id="13b03-131">シーケンス付きのアプリケーションパッケージを保存できません。</span><span class="sxs-lookup"><span data-stu-id="13b03-131">The sequenced application package cannot be saved.</span></span>

<a href="" id="4096"></a><span data-ttu-id="13b03-132">4096</span><span class="sxs-lookup"><span data-stu-id="13b03-132">4096</span></span>  
<span data-ttu-id="13b03-133">指定されたパッケージ名 (/PACKAGENAME) が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="13b03-133">The specified package name (/PACKAGENAME) is not valid.</span></span>

<a href="" id="8192"></a><span data-ttu-id="13b03-134">8192</span><span class="sxs-lookup"><span data-stu-id="13b03-134">8192</span></span>  
<span data-ttu-id="13b03-135">指定したブロックサイズ (/KB) が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="13b03-135">The specified block size (/BLOCKSIZE) is not valid.</span></span>

<a href="" id="16384"></a><span data-ttu-id="13b03-136">16384</span><span class="sxs-lookup"><span data-stu-id="13b03-136">16384</span></span>  
<span data-ttu-id="13b03-137">指定された圧縮の種類 (圧縮) が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="13b03-137">The specified compression type (/COMPRESSION) is not valid.</span></span>

<a href="" id="32768"></a><span data-ttu-id="13b03-138">32768</span><span class="sxs-lookup"><span data-stu-id="13b03-138">32768</span></span>  
<span data-ttu-id="13b03-139">指定されたプロジェクトパスが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="13b03-139">The specified project path is not valid.</span></span>

<a href="" id="65536"></a><span data-ttu-id="13b03-140">65536</span><span class="sxs-lookup"><span data-stu-id="13b03-140">65536</span></span>  
<span data-ttu-id="13b03-141">指定されたアップグレードパラメーターが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="13b03-141">The specified upgrade parameter is not valid.</span></span>

<a href="" id="131072"></a><span data-ttu-id="13b03-142">131072</span><span class="sxs-lookup"><span data-stu-id="13b03-142">131072</span></span>  
<span data-ttu-id="13b03-143">指定されたアップグレードプロジェクトパラメーターが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="13b03-143">The specified upgrade project parameter is not valid.</span></span>

<a href="" id="262144"></a><span data-ttu-id="13b03-144">262144</span><span class="sxs-lookup"><span data-stu-id="13b03-144">262144</span></span>  
<span data-ttu-id="13b03-145">指定したデコードパスパラメーターが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="13b03-145">The specified decode path parameter is not valid.</span></span>

<a href="" id="525288"></a><span data-ttu-id="13b03-146">525288</span><span class="sxs-lookup"><span data-stu-id="13b03-146">525288</span></span>  
<span data-ttu-id="13b03-147">パッケージ名が指定されていません。</span><span class="sxs-lookup"><span data-stu-id="13b03-147">The package name is not specified.</span></span>

## <span data-ttu-id="13b03-148">関連トピック</span><span class="sxs-lookup"><span data-stu-id="13b03-148">Related topics</span></span>


[<span data-ttu-id="13b03-149">Application Virtualization Sequencer リファレンス</span><span class="sxs-lookup"><span data-stu-id="13b03-149">Application Virtualization Sequencer Reference</span></span>](application-virtualization-sequencer-reference.md)

[<span data-ttu-id="13b03-150">Sequencer コマンド ライン パラメーター</span><span class="sxs-lookup"><span data-stu-id="13b03-150">Sequencer Command-Line Parameters</span></span>](sequencer-command-line-parameters.md)

 

 





