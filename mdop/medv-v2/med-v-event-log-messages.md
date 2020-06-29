---
title: MED-V のイベント ログ メッセージ
description: MED-V のイベント ログ メッセージ
author: dansimp
ms.assetid: 7ba7344d-153b-4cc4-a00a-5d42aee9986b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b5d8dcf1cce48d6c1e29d46b4db7ac1550aa9477
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823077"
---
# <span data-ttu-id="a5017-103">MED-V のイベント ログ メッセージ</span><span class="sxs-lookup"><span data-stu-id="a5017-103">MED-V Event Log Messages</span></span>


<span data-ttu-id="a5017-104">Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 のログファイルには、エンタープライズでの MED-V の展開と管理の方法についての詳細情報が記載されています。また、機能の確認や問題のトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a5017-104">The log files for Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 provide detailed information about how to deploy and manage MED-V in your enterprise and help verify functionality or help troubleshoot issues.</span></span>

## <span data-ttu-id="a5017-105">イベント Id</span><span class="sxs-lookup"><span data-stu-id="a5017-105">Event IDs</span></span>


<span data-ttu-id="a5017-106">Med-v を展開または管理するときに発生する可能性のある問題のトラブルシューティングに役立つ、MED-V イベント Id の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a5017-106">The following are a list of MED-V event IDs to help troubleshoot issues that you might encounter when you deploy or manage MED-V.</span></span>

### <span data-ttu-id="a5017-107">Ntfs</span><span class="sxs-lookup"><span data-stu-id="a5017-107">Fts</span></span>

<span data-ttu-id="a5017-108">初めてセットアップするときのイベント Id を示しています。</span><span class="sxs-lookup"><span data-stu-id="a5017-108">Shows the event IDs for first time setup.</span></span>

### <span data-ttu-id="a5017-109">イベント ID 3066</span><span class="sxs-lookup"><span data-stu-id="a5017-109">Event ID 3066</span></span>

<span data-ttu-id="a5017-110">仮想マシンの開始操作に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="a5017-110">Start virtual machine operation failed.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-111">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-111">Description</span></span>**  
<span data-ttu-id="a5017-112">MED-V ワークスペースの作成に使用している仮想ハードディスク (VHD) に問題がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a5017-112">A potential problem exists with the virtual hard disk (VHD) that you are using to create a MED-V workspace.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-113">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-113">Solution</span></span>**  
<span data-ttu-id="a5017-114">MED-V 用の VHD で仮想マシンを作成できること、およびそれを開始できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5017-114">Verify that you can create a virtual machine with the VHD for MED-V and that it can be started.</span></span>

### <span data-ttu-id="a5017-115">イベント ID 3071</span><span class="sxs-lookup"><span data-stu-id="a5017-115">Event ID 3071</span></span>

<span data-ttu-id="a5017-116">仮想マシンの準備に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="a5017-116">Virtual machine preparation failed.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-117">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-117">Description</span></span>**  
<span data-ttu-id="a5017-118">初回のセットアップで、多くの問題が発生している可能性がある問題が発生しました。</span><span class="sxs-lookup"><span data-stu-id="a5017-118">A problem occurred with first time setup that might have been caused by many different issues.</span></span> <span data-ttu-id="a5017-119">これには、ネットワーク接続の問題が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a5017-119">These include problems with network connectivity.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-120">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-120">Solution</span></span>**  
<span data-ttu-id="a5017-121">MED-V Host Agent を再起動して、初回のセットアップを再実行します。</span><span class="sxs-lookup"><span data-stu-id="a5017-121">Restart the MED-V Host Agent to rerun first time setup.</span></span>

### <span data-ttu-id="a5017-122">イベント ID 3078</span><span class="sxs-lookup"><span data-stu-id="a5017-122">Event ID 3078</span></span>

<span data-ttu-id="a5017-123">仮想マシンの準備に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="a5017-123">Virtual machine preparation failed.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-124">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-124">Description</span></span>**  
<span data-ttu-id="a5017-125">MED-V ワークスペースの作成に使用している VHD で問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a5017-125">A potential problem exists with the VHD that you are using to create a MED-V workspace.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-126">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-126">Solution</span></span>**  
<span data-ttu-id="a5017-127">MED-V 用の VHD で仮想マシンを作成できること、およびそれを開始できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5017-127">Verify that you can create a virtual machine with the VHD for MED-V and that it can be started.</span></span>

### <span data-ttu-id="a5017-128">イベント ID 3079</span><span class="sxs-lookup"><span data-stu-id="a5017-128">Event ID 3079</span></span>

<span data-ttu-id="a5017-129">仮想マシンの準備を再試行しています。</span><span class="sxs-lookup"><span data-stu-id="a5017-129">Retrying virtual machine preparation.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-130">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-130">Description</span></span>**  
<span data-ttu-id="a5017-131">MED-V は、仮想マシンを準備しようとしています。</span><span class="sxs-lookup"><span data-stu-id="a5017-131">MED-V is trying to prepare the virtual machine.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-132">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-132">Solution</span></span>**  
<span data-ttu-id="a5017-133">何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a5017-133">No action is required.</span></span> <span data-ttu-id="a5017-134">初回のセットアップが完了するのを許可します。</span><span class="sxs-lookup"><span data-stu-id="a5017-134">Let first time setup finish.</span></span>

### <span data-ttu-id="a5017-135">イベント ID 3080</span><span class="sxs-lookup"><span data-stu-id="a5017-135">Event ID 3080</span></span>

<span data-ttu-id="a5017-136">仮想マシンの準備中にクライアントが停止されました。</span><span class="sxs-lookup"><span data-stu-id="a5017-136">The client was stopped when preparing the virtual machine.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-137">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-137">Description</span></span>**  
<span data-ttu-id="a5017-138">仮想マシンの準備をしようとすると、MED-V が予期せず停止します。</span><span class="sxs-lookup"><span data-stu-id="a5017-138">MED-V stops unexpectedly when it tries to prepare the virtual machine.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-139">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-139">Solution</span></span>**  
<span data-ttu-id="a5017-140">MED-V Host Agent を起動して、初回のセットアップを完了させる</span><span class="sxs-lookup"><span data-stu-id="a5017-140">Start the MED-V Host Agent and let first time setup complete</span></span>

### <span data-ttu-id="a5017-141">イベント ID 3084</span><span class="sxs-lookup"><span data-stu-id="a5017-141">Event ID 3084</span></span>

<span data-ttu-id="a5017-142">仮想マシンが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="a5017-142">Virtual machine is not valid.</span></span> <span data-ttu-id="a5017-143">初回のセットアップを再実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5017-143">First time setup needs to be re-run.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-144">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-144">Description</span></span>**  
<span data-ttu-id="a5017-145">MED-V Host Agent で仮想マシンの問題が検出されました。</span><span class="sxs-lookup"><span data-stu-id="a5017-145">The MED-V Host Agent detected a problem with the virtual machine.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-146">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-146">Solution</span></span>**  
<span data-ttu-id="a5017-147">何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a5017-147">No action is required.</span></span> <span data-ttu-id="a5017-148">初回のセットアップが完了するのを許可します。</span><span class="sxs-lookup"><span data-stu-id="a5017-148">Let first time setup finish.</span></span>

### <span data-ttu-id="a5017-149">イベント ID 3099</span><span class="sxs-lookup"><span data-stu-id="a5017-149">Event ID 3099</span></span>

<span data-ttu-id="a5017-150">仮想マシンの開始の呼び出しに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="a5017-150">Call to start virtual machine failed.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-151">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-151">Description</span></span>**  
<span data-ttu-id="a5017-152">MED-V ワークスペースの作成に使用している VHD で問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a5017-152">A potential problem exists with the VHD you are using to create a MED-V workspace.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-153">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-153">Solution</span></span>**  
<span data-ttu-id="a5017-154">MED-V の VHD で仮想マシンを作成し、それを開くことができることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5017-154">Verify that you can create a virtual machine with the VHD for MED-V and that it can be opened.</span></span>

### <span data-ttu-id="a5017-155">VM 管理</span><span class="sxs-lookup"><span data-stu-id="a5017-155">VM Management</span></span>

### <span data-ttu-id="a5017-156">イベント ID 4022</span><span class="sxs-lookup"><span data-stu-id="a5017-156">Event ID 4022</span></span>

<span data-ttu-id="a5017-157">VM にコマンドを発行中に、VMManagerException の致命的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a5017-157">VMManagerException Fatal error while issuing command to VM.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-158">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-158">Description</span></span>**  
<span data-ttu-id="a5017-159">エンドユーザーが、ログオフするか、MED-V ホストをシャットダウンして、MED-V を終了しようとしたか、VMTaskTimeout 構成設定を超えました。</span><span class="sxs-lookup"><span data-stu-id="a5017-159">The end user tried to exit MED-V by logging off or by shutting down the MED-V host, and the VMTaskTimeout configuration setting was exceeded.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-160">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-160">Solution</span></span>**  
<span data-ttu-id="a5017-161">MED-V を再起動します。</span><span class="sxs-lookup"><span data-stu-id="a5017-161">Restart MED-V.</span></span>

### <span data-ttu-id="a5017-162">イベント ID 4028</span><span class="sxs-lookup"><span data-stu-id="a5017-162">Event ID 4028</span></span>

<span data-ttu-id="a5017-163">VM 操作がタイムアウトしました。</span><span class="sxs-lookup"><span data-stu-id="a5017-163">VM Operation timed out.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-164">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-164">Description</span></span>**  
<span data-ttu-id="a5017-165">エンドユーザーが、ログオフするか、ホストをシャットダウンして、MED-V を終了しようとしました。そのため、VMTaskTimeout 構成設定が制限されていました。</span><span class="sxs-lookup"><span data-stu-id="a5017-165">The end user tried to exit MED-V by logging off or by shutting down the host, and the VMTaskTimeout configuration setting was exceeded.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-166">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-166">Solution</span></span>**  
<span data-ttu-id="a5017-167">MED-V を再起動します。</span><span class="sxs-lookup"><span data-stu-id="a5017-167">Restart MED-V.</span></span>

### <span data-ttu-id="a5017-168">イベント ID 4038</span><span class="sxs-lookup"><span data-stu-id="a5017-168">Event ID 4038</span></span>

<span data-ttu-id="a5017-169">Vmsal がエラーメッセージをユーザーに投稿しました。</span><span class="sxs-lookup"><span data-stu-id="a5017-169">Vmsal posted an error message to the user.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-170">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-170">Description</span></span>**  
<span data-ttu-id="a5017-171">MED-V で仮想アプリケーションを開始できなかったことを示すエラーメッセージがエンドユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5017-171">An error message is displayed to the end user stating that MED-V could not start the virtual application.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-172">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-172">Solution</span></span>**  
<span data-ttu-id="a5017-173">エラーが1行に2回以上記録されている場合は、MED-V を停止し、Windows Virtual PC コンソールを使用して仮想マシンに接続して、全画面でアプリケーションを起動してみます。</span><span class="sxs-lookup"><span data-stu-id="a5017-173">If the error is logged two or more times in a row, stop MED-V and connect to the virtual machine by using Windows Virtual PC console and attempt to start the application in Full Screen.</span></span>

### <span data-ttu-id="a5017-174">イベント ID 4040</span><span class="sxs-lookup"><span data-stu-id="a5017-174">Event ID 4040</span></span>

<span data-ttu-id="a5017-175">ゲストサービスがゲストで初期化されていないため、追加機能のリサイクルが行われます。</span><span class="sxs-lookup"><span data-stu-id="a5017-175">Recycling Additions because TerminalServices is not initialized in the guest.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-176">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-176">Description</span></span>**  
<span data-ttu-id="a5017-177">MED-V は仮想マシンでリモートデスクトップサービスが初期化されなかったため、仮想マシンを再起動しました。</span><span class="sxs-lookup"><span data-stu-id="a5017-177">MED-V rebooted the virtual machine because Remote Desktop Services was not initialized on the virtual machine.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-178">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-178">Solution</span></span>**  
<span data-ttu-id="a5017-179">エラーが1行に2回以上記録されている場合は、MED-V を停止し、Windows Virtual PC コンソールを使用して仮想マシンに接続します。</span><span class="sxs-lookup"><span data-stu-id="a5017-179">If the error is logged two or more times in a row, stop MED-V and connect to the virtual machine by using Windows Virtual PC console.</span></span>

### <span data-ttu-id="a5017-180">イベント ID 4042</span><span class="sxs-lookup"><span data-stu-id="a5017-180">Event ID 4042</span></span>

<span data-ttu-id="a5017-181">ゲストの追加をリサイクルできませんでした。</span><span class="sxs-lookup"><span data-stu-id="a5017-181">Failed to recycle additions in the guest.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-182">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-182">Description</span></span>**  
<span data-ttu-id="a5017-183">MED-V は仮想マシンで仮想マシンの追加をリサイクルできませんでした。</span><span class="sxs-lookup"><span data-stu-id="a5017-183">MED-V failed to recycle virtual machine additions on the virtual machine.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-184">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-184">Solution</span></span>**  
<span data-ttu-id="a5017-185">エラーが1行に2回以上記録されている場合は、MED-V を停止し、Windows Virtual PC コンソールを使用して仮想マシンに接続します。</span><span class="sxs-lookup"><span data-stu-id="a5017-185">If the error is logged two or more times in a row, stop MED-V and connect to the virtual machine by using Windows Virtual PC console.</span></span>

### <span data-ttu-id="a5017-186">イベント ID 4043</span><span class="sxs-lookup"><span data-stu-id="a5017-186">Event ID 4043</span></span>

<span data-ttu-id="a5017-187">仮想マシンでの有効期限が切れたパスワードのリセットに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="a5017-187">Failed to reset expired password in the virtual machine.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-188">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-188">Description</span></span>**  
<span data-ttu-id="a5017-189">エンドユーザーは、有効期限が切れる前に、仮想マシンのパスワードをリセットしませんでした。</span><span class="sxs-lookup"><span data-stu-id="a5017-189">The end user did not reset the password in the virtual machine before it expired.</span></span> <span data-ttu-id="a5017-190">この結果、ユーザーはネットワークリソースにアクセスできないか、作業を保存できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a5017-190">As a result, the user might not be able to access network resources or save work.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-191">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-191">Solution</span></span>**  
<span data-ttu-id="a5017-192">MED-V ゲストをシャットダウンして再起動します。</span><span class="sxs-lookup"><span data-stu-id="a5017-192">Shut down the MED-V guest and restart it.</span></span>

### <span data-ttu-id="a5017-193">URL リダイレクション</span><span class="sxs-lookup"><span data-stu-id="a5017-193">URL Redirection</span></span>

### <span data-ttu-id="a5017-194">イベント ID 5005</span><span class="sxs-lookup"><span data-stu-id="a5017-194">Event ID 5005</span></span>

<span data-ttu-id="a5017-195">構成から VM 名を取得できませんでした。ゲストブラウザを起動できません。</span><span class="sxs-lookup"><span data-stu-id="a5017-195">Couldn’t get VM name from configuration; can’t launch guest browser.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-196">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-196">Description</span></span>**  
<span data-ttu-id="a5017-197">URL リダイレクションが、構成から MED-V ワークスペース名を取得できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a5017-197">URL Redirection could not obtain the MED-V workspace name from the configuration.</span></span> <span data-ttu-id="a5017-198">結果として、Windows 仮想 PC に対して、MED-V ワークスペースブラウザーでリダイレクトされた URL を開くように通知することはできません。</span><span class="sxs-lookup"><span data-stu-id="a5017-198">As a result, it cannot inform Windows Virtual PC to open the redirected URL in the MED-V workspace browser.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-199">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-199">Solution</span></span>**  
<span data-ttu-id="a5017-200">MED-V ワークスペースの名前が設定されていることを確認し、C:\\Users\\ &lt; *user* &gt; ¥ virtual Machines ディレクトリの仮想マシン名と一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5017-200">Ensure that the MED-V workspace name is set and that it matches a virtual machine name in the C:\\Users\\&lt;*user*&gt;\\Virtual Machines directory.</span></span> <span data-ttu-id="a5017-201">MED-V ワークスペース名は HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name. にあります。</span><span class="sxs-lookup"><span data-stu-id="a5017-201">The MED-V workspace name is located at HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name.</span></span>

<span data-ttu-id="a5017-202">たとえば、ユーザーが "mattsworkspace" で、ワークスペース名が "" の場合、HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name の値は "mattsworkspace" であり、C:\\Users\\Matt\\Virtual Machines\\mattsworkspace.vcmx. という名前のファイルが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5017-202">For example, if the user is "Matt" and the workspace name is "mattsworkspace", the value of HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name should be "mattsworkspace", and there should be a file that is named C:\\Users\\Matt\\Virtual Machines\\mattsworkspace.vcmx.</span></span>

### <span data-ttu-id="a5017-203">イベント ID 5006</span><span class="sxs-lookup"><span data-stu-id="a5017-203">Event ID 5006</span></span>

<span data-ttu-id="a5017-204">パイプサーバーの作成に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="a5017-204">Failed to create pipe server.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-205">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-205">Description</span></span>**  
<span data-ttu-id="a5017-206">URL リダイレクションサービスが、Internet Explorer と通信するためのパイプサーバーを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a5017-206">The URL Redirection service could not create the pipe server to communicate with Internet Explorer.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-207">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-207">Solution</span></span>**  
<span data-ttu-id="a5017-208">パスが次のように始まるファイルまたはリソースを作成しようとすると、システムイベントログが確認されます。 "\\\\.\\pipe\\MEDVUrlRedirectionPipe\_" は、ユーザーのユーザー名とドメイン名で終わります。</span><span class="sxs-lookup"><span data-stu-id="a5017-208">Check system event logs for attempts to create a file or resource whose path begins similar to the following: "\\\\.\\pipe\\MEDVUrlRedirectionPipe\_" and ends with the user’s user name and domain name.</span></span> <span data-ttu-id="a5017-209">イベントログに表示されない場合は、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a5017-209">If this is not present in the event log, restart the computer.</span></span>

### <span data-ttu-id="a5017-210">ConfigMgr (ゲスト)</span><span class="sxs-lookup"><span data-stu-id="a5017-210">ConfigMgr (Guest)</span></span>

### <span data-ttu-id="a5017-211">イベント ID 7001</span><span class="sxs-lookup"><span data-stu-id="a5017-211">Event ID 7001</span></span>

<span data-ttu-id="a5017-212">ホストネットワーク構成データの書式設定が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="a5017-212">The host network configuration data is not properly formatted.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-213">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-213">Description</span></span>**  
<span data-ttu-id="a5017-214">ホストから受け取ったネットワーク構成が間違った形式の XML 文字列であるか、ホストから返されたネットワーク情報を XML ドキュメントに書き込むことができません。</span><span class="sxs-lookup"><span data-stu-id="a5017-214">Either the network configuration received from the host is an incorrectly formatted XML string, or the network information returned from the host cannot be written to an XML document.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-215">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-215">Solution</span></span>**  
<span data-ttu-id="a5017-216">ホストコンピューターと仮想マシンを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a5017-216">Restart the host computer and the virtual machine.</span></span>

### <span data-ttu-id="a5017-217">イベント ID 7005</span><span class="sxs-lookup"><span data-stu-id="a5017-217">Event ID 7005</span></span>

<span data-ttu-id="a5017-218">ホストネットワーク構成の変更が検出されましたが、ホストのネットワーク構成データが正しく書式設定されていないため、適用できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a5017-218">A change to the host network configuration was detected, but was not able to be applied because the host network configuration data was not properly formatted.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-219">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-219">Description</span></span>**  
<span data-ttu-id="a5017-220">ホストネットワーク構成の変更が仮想マシンに伝達されましたが、エラーのため仮想マシンで処理できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a5017-220">A change to the host network configuration was communicated to the virtual machine, but could not be processed in the virtual machine because of an error.</span></span> <span data-ttu-id="a5017-221">このエラーは、データが正しく書式設定されていないか、Windows Management Instrumentation (WMI) CCMNetworkAdapter インスタンスに情報を設定できないために発生した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a5017-221">This error could be caused by incorrectly formatted data or the inability to set the information into the Windows Management Instrumentation (WMI) CCMNetworkAdapter instance.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-222">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-222">Solution</span></span>**  
<span data-ttu-id="a5017-223">ホストと仮想マシンを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a5017-223">Restart the host and virtual machine.</span></span>

### <span data-ttu-id="a5017-224">ConfigMgr (ホスト)</span><span class="sxs-lookup"><span data-stu-id="a5017-224">ConfigMgr (Host)</span></span>

### <span data-ttu-id="a5017-225">イベント ID 8006</span><span class="sxs-lookup"><span data-stu-id="a5017-225">Event ID 8006</span></span>

<span data-ttu-id="a5017-226">仮想マシンが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="a5017-226">The virtual machine cannot be found.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-227">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-227">Description</span></span>**  
<span data-ttu-id="a5017-228">Windows Virtual PC 7 で仮想マシンが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="a5017-228">Windows Virtual PC 7 cannot locate the virtual machine.</span></span> <span data-ttu-id="a5017-229">仮想マシンが削除、移動、削除、またはアクセスが拒否された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a5017-229">The virtual machine might have been deleted, moved, removed, or access was denied.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-230">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-230">Solution</span></span>**  
<span data-ttu-id="a5017-231">仮想マシンを再インストールします。</span><span class="sxs-lookup"><span data-stu-id="a5017-231">Reinstall the virtual machine.</span></span>

### <span data-ttu-id="a5017-232">イベント ID 8008</span><span class="sxs-lookup"><span data-stu-id="a5017-232">Event ID 8008</span></span>

<span data-ttu-id="a5017-233">ワークステーションのネットワーク構成情報を取得できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a5017-233">The workstation's network configuration information could not be retrieved.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-234">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-234">Description</span></span>**  
<span data-ttu-id="a5017-235">ネットワーク構成情報を MED-V ホストから収集できなかったため、ほとんどの場合、.NET Framework のシステムコールエラーが原因です。</span><span class="sxs-lookup"><span data-stu-id="a5017-235">Network configuration information could not be collected from the MED-V host, most likely because of a system call failure in the .NET Framework.</span></span> <span data-ttu-id="a5017-236">このエラーは、MED-V ホストから返されたネットワーク情報を XML ドキュメントに書き込むことができない場合にも発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a5017-236">This failure can also occur if the network information returned from the MED-V host cannot be written to an XML document.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-237">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-237">Solution</span></span>**  
<span data-ttu-id="a5017-238">ホストワークステーションを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a5017-238">Restart the host workstation.</span></span>

### <span data-ttu-id="a5017-239">イベント ID 8010</span><span class="sxs-lookup"><span data-stu-id="a5017-239">Event ID 8010</span></span>

<span data-ttu-id="a5017-240">仮想マシンでネットワーク構成データを設定できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a5017-240">The network configuration data could not be set in the virtual machine.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-241">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-241">Description</span></span>**  
<span data-ttu-id="a5017-242">MED-V の hostnetwork address translation (NAT) を仮想マシンに伝達できませんでした。仮想マシンが不良な状態にあるか、Windows 仮想 PC の追加がインストールまたは有効にされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a5017-242">The MED-V hostnetwork address translation (NAT) could not be communicated to the virtual machine, most likely because the virtual machine is in a bad state or the Windows Virtual PC Additions were not installed or enabled.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-243">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-243">Solution</span></span>**  
<span data-ttu-id="a5017-244">仮想マシンをシャットダウンして再起動します。</span><span class="sxs-lookup"><span data-stu-id="a5017-244">Shut down and restart the virtual machine.</span></span> <span data-ttu-id="a5017-245">また、仮想マシンの再インストールが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="a5017-245">In addition, you might have to reinstall the virtual machine.</span></span>

### <span data-ttu-id="a5017-246">イベント ID 8011</span><span class="sxs-lookup"><span data-stu-id="a5017-246">Event ID 8011</span></span>

<span data-ttu-id="a5017-247">仮想マシンでネットワーク構成データをリセットできませんでした。</span><span class="sxs-lookup"><span data-stu-id="a5017-247">The network configuration data could not be reset in the virtual machine.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-248">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-248">Description</span></span>**  
<span data-ttu-id="a5017-249">MED-V の hostnetwork configuration (ブリッジ) が仮想マシンに伝達されませんでした。仮想マシンが正しくない状態であるか、Windows 仮想 PC の追加がインストールまたは有効にされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a5017-249">The MED-V hostnetwork configuration (BRIDGED) could not be communicated to the virtual machine, most likely because the virtual machine is in a bad state or the Windows Virtual PC Additions were not installed or enabled.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-250">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-250">Solution</span></span>**  
<span data-ttu-id="a5017-251">仮想マシンをシャットダウンして再起動します。</span><span class="sxs-lookup"><span data-stu-id="a5017-251">Shut down and restart the virtual machine.</span></span> <span data-ttu-id="a5017-252">また、仮想マシンの再インストールが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="a5017-252">In addition, you might have to reinstall the virtual machine.</span></span>

### <span data-ttu-id="a5017-253">プリンターのリダイレクション</span><span class="sxs-lookup"><span data-stu-id="a5017-253">Printer Redirection</span></span>

### <span data-ttu-id="a5017-254">イベント ID 9001</span><span class="sxs-lookup"><span data-stu-id="a5017-254">Event ID 9001</span></span>

<span data-ttu-id="a5017-255">ファイルのアクセス許可エラー。</span><span class="sxs-lookup"><span data-stu-id="a5017-255">File Permission Error.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-256">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-256">Description</span></span>**  
<span data-ttu-id="a5017-257">エンドユーザーが、読み取り用の MED-V プリンターファイルを開く、または作成するために必要なフォルダーにアクセスする権限を持っていない。</span><span class="sxs-lookup"><span data-stu-id="a5017-257">The end user is not authorized to access the folder required to open or create the MED-V printer file for reading.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-258">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-258">Solution</span></span>**  
<span data-ttu-id="a5017-259">User\\AppData\\ path にアクセスできること、およびユーザーに読み取りと書き込みのアクセス許可が与えられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5017-259">Verify that the User\\AppData\\ path can be accessed and that the user has permission to read and write to it.</span></span> <span data-ttu-id="a5017-260">たとえば、ユーザーが "C:\\Users\\Matt\\AppData\\" である場合、パスのと、そのすべてのファイルには読み取りと書き込みのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="a5017-260">For example, if the user is "Matt", the path C:\\Users\\Matt\\AppData\\, and all files therein should have Read and Write permissions.</span></span> <span data-ttu-id="a5017-261">存在する場合、path C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ とそのすべてのファイルには、読み取りと書き込みのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="a5017-261">And if it exists, the path C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ and all files therein should have Read and Write permissions.</span></span>

### <span data-ttu-id="a5017-262">イベント ID 9002</span><span class="sxs-lookup"><span data-stu-id="a5017-262">Event ID 9002</span></span>

<span data-ttu-id="a5017-263">ファイルのアクセス許可エラー。</span><span class="sxs-lookup"><span data-stu-id="a5017-263">File Permission Error.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-264">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-264">Description</span></span>**  
<span data-ttu-id="a5017-265">エンドユーザーは、入力用に MED-V プリンターファイルを開く、または作成するために必要なフォルダーにアクセスする権限がありません。</span><span class="sxs-lookup"><span data-stu-id="a5017-265">The end user is not authorized to access the folder required to open or create the MED-V printer file for writing.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-266">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-266">Solution</span></span>**  
<span data-ttu-id="a5017-267">User\\AppData\\ path にアクセスできること、およびユーザーに読み取りと書き込みのアクセス許可が与えられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5017-267">Ensure that the User\\AppData\\ path can be accessed, and that the user has permission to read and write to it.</span></span> <span data-ttu-id="a5017-268">たとえば、ユーザーが "C:\\Users\\Matt\\AppData\\" である場合、path とそのすべてのファイルには、読み取りと書き込みのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="a5017-268">For example, if the user is "Matt", the path C:\\Users\\Matt\\AppData\\ and all files therein should have Read and Write permissions.</span></span> <span data-ttu-id="a5017-269">存在する場合、path C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ とそのすべてのファイルには、読み取りと書き込みのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="a5017-269">And if it exists, the path C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ and all files therein should have Read and Write permissions.</span></span>

### <span data-ttu-id="a5017-270">イベント ID 9004</span><span class="sxs-lookup"><span data-stu-id="a5017-270">Event ID 9004</span></span>

<span data-ttu-id="a5017-271">MEDV プリンターファイルを保存するためのパスを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a5017-271">Could not create path for storing MEDV printer files.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-272">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-272">Description</span></span>**  
<span data-ttu-id="a5017-273">プリンターのリダイレクションサービスが、ファイルにアクセスできない、またはプリンター情報を保存するために必要なディレクトリを作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a5017-273">The printer redirection service could not access files or create directories required for storing the printer information.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-274">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-274">Solution</span></span>**  
<span data-ttu-id="a5017-275">User\\AppData\\ path にアクセスできること、およびユーザーに読み取りと書き込みのアクセス許可が与えられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5017-275">Verify that the User\\AppData\\ path can be accessed and that the user has permission to read and write to it.</span></span> <span data-ttu-id="a5017-276">たとえば、ユーザーが "C:\\Users\\Matt\\AppData\\" である場合、path とそのすべてのファイルには、読み取りと書き込みのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="a5017-276">For example, if the user is "Matt", the path C:\\Users\\Matt\\AppData\\ and all files therein should have Read and Write permissions.</span></span> <span data-ttu-id="a5017-277">存在する場合、path C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ とそのすべてのファイルには、読み取りと書き込みのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="a5017-277">And if it exists, the path C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ and all files therein should have Read and Write permissions.</span></span>

### <span data-ttu-id="a5017-278">イベント ID 9005</span><span class="sxs-lookup"><span data-stu-id="a5017-278">Event ID 9005</span></span>

<span data-ttu-id="a5017-279">構成から VM 名を取得できませんでした。ゲストインストーラーを起動できません。</span><span class="sxs-lookup"><span data-stu-id="a5017-279">Couldn’t get VM name from configuration; cannot launch guest installer.</span></span> <span data-ttu-id="a5017-280">MED-V を更新できません–ホストネットワークが検出されませんでした。</span><span class="sxs-lookup"><span data-stu-id="a5017-280">Cannot update MED-V – No host network detected.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-281">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-281">Description</span></span>**  
<span data-ttu-id="a5017-282">プリンターのリダイレクトサービスは、MED-V 構成から MED-V ワークスペース名を取得できませんでした。 Windows 仮想 PC に、MED-V ゲスト上のインストーラーを起動するように通知することはできません。</span><span class="sxs-lookup"><span data-stu-id="a5017-282">The printer redirection service was not able to obtain the MED-V workspace name from the MED-V configuration and cannot inform Windows Virtual PC to start the installer on the MED-V guest.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-283">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-283">Solution</span></span>**  
<span data-ttu-id="a5017-284">MED-V ワークスペースの名前が設定されていることを確認し、C:\\Users\\ &lt; *user* &gt; ¥ virtual Machines ディレクトリの仮想マシン名と一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5017-284">Ensure that the MED-V workspace name is set and that it matches a virtual machine name in the C:\\Users\\&lt;*user*&gt;\\Virtual Machines directory.</span></span> <span data-ttu-id="a5017-285">MED-V ワークスペース名は HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name. にあります。</span><span class="sxs-lookup"><span data-stu-id="a5017-285">The MED-V workspace name is located at HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name.</span></span>

<span data-ttu-id="a5017-286">たとえば、ユーザーが "mattsworkspace" で、ワークスペース名が "" である場合、HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name の値は "mattsworkspace" であり、C:\\Users\\Matt\\Virtual Machines\\mattsworkspace.vcmx. という名前のファイルが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5017-286">For example, if the user is "Matt" and the workspace name is "mattsworkspace", the value of HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name should be "mattsworkspace" and there should be a file that is named C:\\Users\\Matt\\Virtual Machines\\mattsworkspace.vcmx.</span></span>

### <span data-ttu-id="a5017-287">アプリケーションの発行</span><span class="sxs-lookup"><span data-stu-id="a5017-287">Application Publishing</span></span>

### <span data-ttu-id="a5017-288">イベント ID 10015</span><span class="sxs-lookup"><span data-stu-id="a5017-288">Event ID 10015</span></span>

<span data-ttu-id="a5017-289">調整プロセス中にファイルシステムエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a5017-289">A file system error occurred during the reconcile process.</span></span> <span data-ttu-id="a5017-290">調整プロセスでは、ファイル名は処理されません &lt; *filename* &gt; が、その他の変更は引き続き処理されます。</span><span class="sxs-lookup"><span data-stu-id="a5017-290">The reconcile process will not process the file &lt;*filename*&gt; but will continue to process any other changes.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-291">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-291">Description</span></span>**  
<span data-ttu-id="a5017-292">ショートカットの作成または削除時に、不正アクセスまたは i/o エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a5017-292">An unauthorized access or I/O error occurred when a shortcut was being created or deleted.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-293">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-293">Solution</span></span>**  
<span data-ttu-id="a5017-294">ファイルのパスにアクセスできること、および指定されたファイルを作成または削除する権限がユーザーに与えられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5017-294">Check that the file path can be accessed and that the user has permissions to create or delete the specified file.</span></span>

### <span data-ttu-id="a5017-295">イベント ID 10021</span><span class="sxs-lookup"><span data-stu-id="a5017-295">Event ID 10021</span></span>

<span data-ttu-id="a5017-296">ファイル &lt; の操作に関するエラー*エラー \ _information* &gt; &lt; *operation\_name* &gt; ファイル名の _name &lt; *filename* &gt; 。</span><span class="sxs-lookup"><span data-stu-id="a5017-296">Error &lt;*error\_information*&gt; for file operation &lt;*operation\_name*&gt; on file &lt;*filename*&gt;.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-297">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-297">Description</span></span>**  
<span data-ttu-id="a5017-298">ショートカットの作成または削除時に、不正アクセスまたは i/o エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="a5017-298">An unauthorized access or I/O error occurred when a shortcut was being created or deleted.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-299">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-299">Solution</span></span>**  
<span data-ttu-id="a5017-300">ファイルのパスにアクセスできること、および指定されたファイルを作成または削除する権限がユーザーに与えられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5017-300">Check that the file path can be accessed and that the user has permissions to create or delete the specified file.</span></span>

### <span data-ttu-id="a5017-301">ゲストの修正プログラム</span><span class="sxs-lookup"><span data-stu-id="a5017-301">Guest Patching</span></span>

### <span data-ttu-id="a5017-302">イベント ID 11001</span><span class="sxs-lookup"><span data-stu-id="a5017-302">Event ID 11001</span></span>

<span data-ttu-id="a5017-303">ゲストウェイクアップタスクの使用状況メッセージ。</span><span class="sxs-lookup"><span data-stu-id="a5017-303">Guest wakeup task usage message.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-304">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-304">Description</span></span>**  
<span data-ttu-id="a5017-305">/Guestウェイクアップオプションの MedvHost.exe が正しく実行されなかったか、コマンドの形式が間違っています。</span><span class="sxs-lookup"><span data-stu-id="a5017-305">MedvHost.exe with the /GuestWakeup option was executed incorrectly, or the command is formatted incorrectly.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-306">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-306">Solution</span></span>**  
<span data-ttu-id="a5017-307">コマンドが次の形式で実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5017-307">Ensure that the command is executed with the following format:</span></span>

<span data-ttu-id="a5017-308">Medvhost.exe/guestウェイクアップ/d: &lt; *duration \ _in \ _minutes* &gt; /v: " &lt; *workspace \ _name* &gt; "</span><span class="sxs-lookup"><span data-stu-id="a5017-308">Medvhost.exe /GuestWakeup /d:&lt; *duration\_in\_minutes*&gt; /v:”&lt; *workspace\_name*&gt;” where</span></span>

<span data-ttu-id="a5017-309">&lt;*期間 \ _in \ _minutes* &gt;仮想マシンがスリープ状態のままになるまでの時間 (既定は 240) と</span><span class="sxs-lookup"><span data-stu-id="a5017-309">&lt;*duration\_in\_minutes*&gt; is the number of minutes that the virtual machine should stay awake (default is 240) and</span></span>

<span data-ttu-id="a5017-310">&lt;*ワークスペース \ _name* &gt;は、起こされる仮想マシンの名前です。</span><span class="sxs-lookup"><span data-stu-id="a5017-310">&lt;*workspace\_name*&gt; is the name of the virtual machine that should be awakened.</span></span>

### <span data-ttu-id="a5017-311">イベント ID 11002</span><span class="sxs-lookup"><span data-stu-id="a5017-311">Event ID 11002</span></span>

<span data-ttu-id="a5017-312">MED-V を更新できません–ホストネットワークが検出されませんでした。</span><span class="sxs-lookup"><span data-stu-id="a5017-312">Cannot update MED-V – No host network detected.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-313">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-313">Description</span></span>**  
<span data-ttu-id="a5017-314">ホストネットワーク接続が検出されなかったため、ゲストの修正プログラムを完了できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a5017-314">Guest patching could not finish because no host network connection was detected.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-315">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-315">Solution</span></span>**  
<span data-ttu-id="a5017-316">ゲストの修正プログラムを実行する前に、MED-V ホストをアクティブなネットワーク接続に接続します。</span><span class="sxs-lookup"><span data-stu-id="a5017-316">Connect the MED-V host to an active network connection before you run guest patching.</span></span>

### <span data-ttu-id="a5017-317">イベント ID 11003</span><span class="sxs-lookup"><span data-stu-id="a5017-317">Event ID 11003</span></span>

<span data-ttu-id="a5017-318">MED を更新できません– A/C powerFailed が実行されていないホストがパイプサーバーの作成に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="a5017-318">Cannot update MED-V – Host not running on A/C powerFailed to create pipe server.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-319">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-319">Description</span></span>**  
<span data-ttu-id="a5017-320">ホストが電源コードではなくバッテリ電源で実行されているように見えるため、ゲストの修正プログラムが完了しませんでした。</span><span class="sxs-lookup"><span data-stu-id="a5017-320">Guest patching could not finish because the host appears to be running on battery power instead of from a power cord.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-321">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-321">Solution</span></span>**  
<span data-ttu-id="a5017-322">ゲストの修正プログラムを実行する前に、ホストコンピューターを電源コードに接続します。</span><span class="sxs-lookup"><span data-stu-id="a5017-322">Connect the host computer to a power cord before you run guest patching.</span></span>

### <span data-ttu-id="a5017-323">クライアント UX</span><span class="sxs-lookup"><span data-stu-id="a5017-323">Client UX</span></span>

### <span data-ttu-id="a5017-324">イベント ID 14003</span><span class="sxs-lookup"><span data-stu-id="a5017-324">Event ID 14003</span></span>

<span data-ttu-id="a5017-325">次のトレイステータスメッセージは長すぎて表示されませんでした: &lt; *トレイ \ _status \ _message*&gt;</span><span class="sxs-lookup"><span data-stu-id="a5017-325">The following tray status message was too long and could not be displayed: &lt;*tray\_status\_message*&gt;</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-326">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-326">Description</span></span>**  
<span data-ttu-id="a5017-327">MED で作成された、トレイのヒントまたは吹き出しメッセージに対して長すぎる予期しない文字列が作成されました。</span><span class="sxs-lookup"><span data-stu-id="a5017-327">MED-V created an unanticipated string that was too long for the tray tooltip or balloon message.</span></span> <span data-ttu-id="a5017-328">結果として、表示されたメッセージが切り詰められました。</span><span class="sxs-lookup"><span data-stu-id="a5017-328">As a result, the displayed message was truncated.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-329">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-329">Solution</span></span>**  
<span data-ttu-id="a5017-330">これは、MED-V がランダムにヒントテキストを作成するときに発生する可能性のあるまれなエラーです。</span><span class="sxs-lookup"><span data-stu-id="a5017-330">This is a rare error that can occur when MED-V is randomly creating the tooltip text.</span></span> <span data-ttu-id="a5017-331">解決策はありません。</span><span class="sxs-lookup"><span data-stu-id="a5017-331">There is no solution.</span></span>

### <span data-ttu-id="a5017-332">イベント ID 14004</span><span class="sxs-lookup"><span data-stu-id="a5017-332">Event ID 14004</span></span>

<span data-ttu-id="a5017-333">MED-V は処理不能な例外が発生したために停止しました。</span><span class="sxs-lookup"><span data-stu-id="a5017-333">MED-V stopped due to an unhandled exception.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-334">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-334">Description</span></span>**  
<span data-ttu-id="a5017-335">処理不能な例外により、MED-V が予期せず停止しました。</span><span class="sxs-lookup"><span data-stu-id="a5017-335">An unhandled exception caused MED-V to stop unexpectedly.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-336">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-336">Solution</span></span>**  
<span data-ttu-id="a5017-337">MED-V を再起動します。</span><span class="sxs-lookup"><span data-stu-id="a5017-337">Restart MED-V.</span></span>

### <span data-ttu-id="a5017-338">イベント ID 14005</span><span class="sxs-lookup"><span data-stu-id="a5017-338">Event ID 14005</span></span>

<span data-ttu-id="a5017-339">サーバーがミューテックスを作成しようとしましたが、既に存在しています。</span><span class="sxs-lookup"><span data-stu-id="a5017-339">Server attempted to create mutex but it already existed.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-340">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-340">Description</span></span>**  
<span data-ttu-id="a5017-341">2つ目の MedvHost.exe のインスタンスがメモリ内に残っています。</span><span class="sxs-lookup"><span data-stu-id="a5017-341">A second instance of MedvHost.exe is stuck in memory.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-342">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-342">Solution</span></span>**  
<span data-ttu-id="a5017-343">TaskManager を開いて、すべての MedvHost.exe のプロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="a5017-343">Open TaskManager and end all MedvHost.exe processes.</span></span>

### <span data-ttu-id="a5017-344">イベント ID 14006</span><span class="sxs-lookup"><span data-stu-id="a5017-344">Event ID 14006</span></span>

<span data-ttu-id="a5017-345">レジストリ値 &lt; *registry \ _value*の変更または削除時にエラーが発生しました &gt; 。</span><span class="sxs-lookup"><span data-stu-id="a5017-345">Error modifying or deleting registry value &lt;*registry\_value*&gt;.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-346">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-346">Description</span></span>**  
<span data-ttu-id="a5017-347">MED-V では、レジストリ内の指定されたエントリを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a5017-347">MED-V is unable to modify the specified entry in the registry.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-348">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-348">Solution</span></span>**  
<span data-ttu-id="a5017-349">管理者の資格情報を使用して MED-V をインストールまたはアンインストールしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5017-349">Ensure that you install or uninstall MED-V with administrative credentials.</span></span>

### <span data-ttu-id="a5017-350">イベント ID 14007</span><span class="sxs-lookup"><span data-stu-id="a5017-350">Event ID 14007</span></span>

<span data-ttu-id="a5017-351">指定されたファイル ( &lt; *ファイル名* &gt; ) が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="a5017-351">The file specified (&lt;*filename*&gt;) is not valid.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-352">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-352">Description</span></span>**  
<span data-ttu-id="a5017-353">インストールまたはアンインストール中に、破損した一時ファイルが MED-V ホストに渡されました。</span><span class="sxs-lookup"><span data-stu-id="a5017-353">During install or uninstall, a corrupted temp file was passed to MED-V host.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-354">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-354">Solution</span></span>**  
<span data-ttu-id="a5017-355">Temp フォルダー内のすべてのファイルを削除し、MED-V を再インストールまたはアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="a5017-355">Delete all files in the Temp folder and reinstall or uninstall MED-V.</span></span>

### <span data-ttu-id="a5017-356">イベント ID 14008</span><span class="sxs-lookup"><span data-stu-id="a5017-356">Event ID 14008</span></span>

<span data-ttu-id="a5017-357">ファイルが見つかりません: ファイル &lt; *名* &gt; 。</span><span class="sxs-lookup"><span data-stu-id="a5017-357">File not found: &lt;*filename*&gt;.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-358">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-358">Description</span></span>**  
<span data-ttu-id="a5017-359">インストールまたはアンインストール中に、必要な temp ファイルのパスが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="a5017-359">During install or uninstall, a path of a required temp file was not found.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-360">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-360">Solution</span></span>**  
<span data-ttu-id="a5017-361">Temp フォルダー内のすべてのファイルを削除し、MED-V を再インストールまたはアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="a5017-361">Delete all files in the Temp folder and reinstall or uninstall MED-V.</span></span>

### <span data-ttu-id="a5017-362">イベント ID 14009</span><span class="sxs-lookup"><span data-stu-id="a5017-362">Event ID 14009</span></span>

<span data-ttu-id="a5017-363">パラメーターファイルのファイル名を読み取れません &lt; *filename* &gt; 。</span><span class="sxs-lookup"><span data-stu-id="a5017-363">Unable to read parameter file &lt;*filename*&gt;.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-364">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-364">Description</span></span>**  
<span data-ttu-id="a5017-365">インストールまたはアンインストールのプロセス中、MED-V は一時ファイルを読み取ることができませんでした。</span><span class="sxs-lookup"><span data-stu-id="a5017-365">During the install or uninstall process, MED-V was unable to read a temp file.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-366">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-366">Solution</span></span>**  
<span data-ttu-id="a5017-367">Temp フォルダー内のすべてのファイルを削除し、MED-V を再インストールまたはアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="a5017-367">Delete all files in the Temp folder and reinstall or uninstall MED-V.</span></span> <span data-ttu-id="a5017-368">さらに、ユーザーに必要な権限と Temp フォルダーへのアクセス許可があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5017-368">In addition, verify that the user has the necessary rights and permissions to the Temp folder.</span></span>

### <span data-ttu-id="a5017-369">イベント ID 14010</span><span class="sxs-lookup"><span data-stu-id="a5017-369">Event ID 14010</span></span>

<span data-ttu-id="a5017-370">パラメータファイル名の逆シリアル化エラー &lt; *filename* &gt; 。</span><span class="sxs-lookup"><span data-stu-id="a5017-370">Error deserializing parameter file &lt;*filename*&gt;.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-371">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-371">Description</span></span>**  
<span data-ttu-id="a5017-372">インストールまたはアンインストールプロセス中に、MED-V で破損した一時ファイルが検出されました。</span><span class="sxs-lookup"><span data-stu-id="a5017-372">During the install or uninstall process, MED-V encountered a corrupted temp file.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-373">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-373">Solution</span></span>**  
<span data-ttu-id="a5017-374">Temp フォルダー内のすべてのファイルを削除し、MED-V を再インストールまたはアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="a5017-374">Delete all files in the Temp folder and reinstall or uninstall MED-V.</span></span> <span data-ttu-id="a5017-375">さらに、ユーザーに必要な権限と Temp フォルダーへのアクセス許可があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5017-375">In addition, verify that the user has the necessary rights and permissions to the Temp folder.</span></span>

### <span data-ttu-id="a5017-376">イベント ID 14011</span><span class="sxs-lookup"><span data-stu-id="a5017-376">Event ID 14011</span></span>

<span data-ttu-id="a5017-377">パラメーターファイルファイル名の逆シリアル化で予期しないエラーが発生 &lt; *filename* &gt; した。</span><span class="sxs-lookup"><span data-stu-id="a5017-377">Unexpected error deserializing parameter file &lt;*filename*&gt;.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-378">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-378">Description</span></span>**  
<span data-ttu-id="a5017-379">インストールまたはアンインストールプロセス中に、MED-V で破損した一時ファイルが検出されました。</span><span class="sxs-lookup"><span data-stu-id="a5017-379">During the install or uninstall process, MED-V encountered a corrupted temp file.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-380">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-380">Solution</span></span>**  
<span data-ttu-id="a5017-381">Temp フォルダー内のすべてのファイルを削除し、MED-V を再インストールまたはアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="a5017-381">Delete all files in the Temp folder and reinstall or uninstall MED-V.</span></span> <span data-ttu-id="a5017-382">さらに、ユーザーに必要な権限と Temp フォルダーへのアクセス許可があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5017-382">In addition, verify that the user has the necessary rights and permissions to the Temp folder.</span></span>

### <span data-ttu-id="a5017-383">イベント ID 14012</span><span class="sxs-lookup"><span data-stu-id="a5017-383">Event ID 14012</span></span>

<span data-ttu-id="a5017-384">&lt;ユーザー名に対してフォルダー*フォルダー \ _name*の設定権限がある場合に、予期しないエラーが発生しました &gt; &lt; *username* &gt; 。</span><span class="sxs-lookup"><span data-stu-id="a5017-384">Unexpected error when settings rights on folder &lt;*folder\_name*&gt; for user &lt;*username*&gt;.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-385">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-385">Description</span></span>**  
<span data-ttu-id="a5017-386">MED-V がインストール時に特定のフォルダーに対して権限と権限を設定できない場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="a5017-386">An error occurs when MED-V is unable to set rights and permissions on certain folders during installation.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-387">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-387">Solution</span></span>**  
<span data-ttu-id="a5017-388">次のフォルダーの管理者権限を確認します。</span><span class="sxs-lookup"><span data-stu-id="a5017-388">Check the administrator rights to the following folders:</span></span>

<span data-ttu-id="a5017-389">@ "% Programdata¥¥ meます。</span><span class="sxs-lookup"><span data-stu-id="a5017-389">@"%ProgramData%\\Microsoft\\Medv\\AllUsers"</span></span>

<span data-ttu-id="a5017-390">@ "% Programdata¥¥¥¥ medvdvdvdvlock"</span><span class="sxs-lookup"><span data-stu-id="a5017-390">@"%ProgramData%\\Microsoft\\Medv\\MedvLock"</span></span>

<span data-ttu-id="a5017-391">@ "%" というデータがあります。</span><span class="sxs-lookup"><span data-stu-id="a5017-391">@"%ProgramData%\\Microsoft\\Medv\\Monitoring"</span></span>

### <span data-ttu-id="a5017-392">イベント ID 14013</span><span class="sxs-lookup"><span data-stu-id="a5017-392">Event ID 14013</span></span>

<span data-ttu-id="a5017-393">ロックファイルの作成時に予期しないエラーが発生した。</span><span class="sxs-lookup"><span data-stu-id="a5017-393">Unexpected error when creating lock file.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="a5017-394">説明</span><span class="sxs-lookup"><span data-stu-id="a5017-394">Description</span></span>**  
<span data-ttu-id="a5017-395">MED がインストール中に、@ "% programdata% ¥¥ medvdv¥ medvlock" フォルダーにファイルを作成できない場合にエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="a5017-395">An error occurs when MED-V is unable to create a file in the @"%ProgramData%\\Microsoft\\Medv\\MedvLock" folder during installation.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="a5017-396">解決策</span><span class="sxs-lookup"><span data-stu-id="a5017-396">Solution</span></span>**  
<span data-ttu-id="a5017-397">MedvLock フォルダーの管理者権限を確認します。</span><span class="sxs-lookup"><span data-stu-id="a5017-397">Check the administrator rights to the MedvLock folder.</span></span>

## <span data-ttu-id="a5017-398">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a5017-398">Related topics</span></span>


[<span data-ttu-id="a5017-399">MED-V のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a5017-399">Troubleshooting MED-V</span></span>](troubleshooting-med-vmedv2.md)

 

 





