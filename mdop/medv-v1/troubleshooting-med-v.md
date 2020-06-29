---
title: MED-V のトラブルシューティング
description: MED-V のトラブルシューティング
author: dansimp
ms.assetid: f43dae36-6485-4e06-9c66-0a646e27079d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 38d13be699a92368ff258026acd8e0d5f0e28cd6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825864"
---
# <span data-ttu-id="e9305-103">MED-V のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e9305-103">Troubleshooting MED-V</span></span>


<span data-ttu-id="e9305-104">このセクションでは、Microsoft Enterprise デスクトップ仮想化 (MED-V) の一般的な問題のトラブルシューティングに役立つ情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e9305-104">This section provides information to help troubleshoot general issues with Microsoft Enterprise Desktop Virtualization (MED-V).</span></span>

## <span data-ttu-id="e9305-105">ホストの解像度を変更して、MED-V ワークスペースを最大化すると、デスクトップが黒く表示される</span><span class="sxs-lookup"><span data-stu-id="e9305-105">Changing the host resolution and then maximizing the MED-V workspace causes the desktop to appear black</span></span>


<span data-ttu-id="e9305-106">完全なデスクトップモードで作業している場合は、ホストの解像度を変更して、MED-V ワークスペースウィンドウを最大化すると、デスクトップが黒くなり、MED-V ワークスペースが応答しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="e9305-106">When working in full desktop mode, if you change the host resolution and then maximize the MED-V workspace window, the desktop appears black and the MED-V workspace might not respond.</span></span>

### <span data-ttu-id="e9305-107">解決策</span><span class="sxs-lookup"><span data-stu-id="e9305-107">Solution</span></span>

<span data-ttu-id="e9305-108">[停止] をクリックして、MED-V ワークスペースを起動します。</span><span class="sxs-lookup"><span data-stu-id="e9305-108">Stop and then start the MED-V workspace.</span></span>

## <span data-ttu-id="e9305-109">ネットワークアダプターが無効になっている状態で MED-V ワークスペースを起動した後、そのアダプターを有効にしてもネットワーク接続が復元されない</span><span class="sxs-lookup"><span data-stu-id="e9305-109">Starting a MED-V workspace with a network adapter disabled and then later enabling the adapter does not restore network connectivity</span></span>


<span data-ttu-id="e9305-110">ブリッジモードで MED-V のワークスペースを構成し、ネットワークアダプターが無効になっている間に MED-V ワークスペースを起動した場合、そのアダプターを経由したネットワーク接続は復元されません。</span><span class="sxs-lookup"><span data-stu-id="e9305-110">If you configure a MED-V workspace in bridge mode and then start the MED-V workspace while a network adapter is disabled, if the adapter is later enabled, the network connectivity through that adapter is not restored.</span></span>

### <span data-ttu-id="e9305-111">解決策</span><span class="sxs-lookup"><span data-stu-id="e9305-111">Solution</span></span>

<span data-ttu-id="e9305-112">[停止] をクリックして、MED-V ワークスペースを起動します。</span><span class="sxs-lookup"><span data-stu-id="e9305-112">Stop and then start the MED-V workspace.</span></span>

## <span data-ttu-id="e9305-113">画像は、コンピューターごとに1つの Windows ユーザーのみが使用できます。</span><span class="sxs-lookup"><span data-stu-id="e9305-113">An image can be used by only one Windows user per computer</span></span>


<span data-ttu-id="e9305-114">MED-V ワークスペースのイメージは、イメージをダウンロードまたはインポートした Windows ユーザーのみが使用できます。</span><span class="sxs-lookup"><span data-stu-id="e9305-114">A MED-V workspace image can be used only by the Windows user who downloaded or imported the image.</span></span> <span data-ttu-id="e9305-115">このユーザーは、ダウンロードした画像が保存されているフォルダーへのアクセス許可を持つ管理者から唯一のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="e9305-115">This user is the only user aside from administrators who have permissions to the folder where the downloaded images are located.</span></span>

### <span data-ttu-id="e9305-116">解決策</span><span class="sxs-lookup"><span data-stu-id="e9305-116">Solution</span></span>

<span data-ttu-id="e9305-117">イメージストアのアクセス制御リスト (ACL) を手動で変更します。</span><span class="sxs-lookup"><span data-stu-id="e9305-117">Manually change the access control list (ACL) on the image store.</span></span>

## <span data-ttu-id="e9305-118">ユーザー権利を有効にして構成マネージャーを使用して MED-V をインストールすると、アンインストールが失敗する</span><span class="sxs-lookup"><span data-stu-id="e9305-118">When installing MED-V by using Configuration Manager with users rights enabled, uninstall fails</span></span>


<span data-ttu-id="e9305-119">MED-V が Microsoft System Center Configuration Manager を使用してインストールされていて、パッケージの実行モードが [ユーザーの権限] に設定されている場合、アンインストールは失敗し、管理ユーザーのみが MED-V をアンインストールできることを示すエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9305-119">If MED-V is installed by using Microsoft System Center Configuration Manager and the run mode of the package is set to users rights, uninstall fails with an error message that says that only administrative users can uninstall MED-V.</span></span>

### <span data-ttu-id="e9305-120">解決策</span><span class="sxs-lookup"><span data-stu-id="e9305-120">Solution</span></span>

<span data-ttu-id="e9305-121">MED-V の構成マネージャーパッケージを作成する場合は、[実行] モードを [管理者権限] に設定します。</span><span class="sxs-lookup"><span data-stu-id="e9305-121">When creating a Configuration Manager package for MED-V, set the run mode to administrative rights.</span></span>

## <span data-ttu-id="e9305-122">インストール後にクライアントを実行するようにインストールが構成されている企業展開システムを使用して MED-V をインストールする場合、クライアントを実行できない</span><span class="sxs-lookup"><span data-stu-id="e9305-122">When installing MED-V by using a corporate deployment system, where the installation is configured to run the client following installation, you cannot run the client</span></span>


<span data-ttu-id="e9305-123">MED-V が企業展開システムを使用してインストールされ、インストールパッケージがインストール後に実行されるように設定されている場合、クライアントがシステムアカウントで実行された後、クライアントが実行されていることを確認するには (通知領域ではなく)、クライアントが実行中であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9305-123">If MED-V is installed by using a corporate deployment system and the installation package is configured to run MED-V client following the installation, after the client is running under the system account, you cannot see that the client is running (except in the notification area), and you cannot interact with it.</span></span>

### <span data-ttu-id="e9305-124">解決策</span><span class="sxs-lookup"><span data-stu-id="e9305-124">Solution</span></span>

<span data-ttu-id="e9305-125">企業展開システムを使用して MED-V をインストールする場合は、 *START \ _MEDV = 0* . msi パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="e9305-125">When installing MED-V by using a corporate deployment system, use the *START\_MEDV=0* .msi parameter.</span></span>

## <span data-ttu-id="e9305-126">MED-V のテストイメージを起動できない</span><span class="sxs-lookup"><span data-stu-id="e9305-126">MED-V test image fails to start</span></span>


<span data-ttu-id="e9305-127">MED-V のテストイメージの開始に失敗した場合は、そのイメージは復元されず、今後のすべての起動が失敗し、"GINA の読み込みに失敗しました" というエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9305-127">If a MED-V test image fails to start, it will never recover and all future startups will fail with a “GINA fail to load” error message.</span></span>

### <span data-ttu-id="e9305-128">解決策</span><span class="sxs-lookup"><span data-stu-id="e9305-128">Solution</span></span>

<span data-ttu-id="e9305-129">既存のテストイメージを削除し、再作成します。</span><span class="sxs-lookup"><span data-stu-id="e9305-129">Delete the existing test image and then re-create it.</span></span>

## <span data-ttu-id="e9305-130">間違った資格情報でドメインに参加しようとすると、その画像がドメインに参加することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="e9305-130">After attempting to join a domain with the wrong credentials, the image never succeeds in joining the domain</span></span>


<span data-ttu-id="e9305-131">仮想マシンの初回セットアップスクリプトの一部である、参加ドメインの構築ブロックで構成エラーが発生した場合、ドメインに参加しようとすると、MED-V ワークスペースが失敗します。</span><span class="sxs-lookup"><span data-stu-id="e9305-131">If there is a configuration error in the join domain building block, which is part of the virtual machine first-time setup script, it causes the MED-V workspace to fail when attempting to join a domain.</span></span> <span data-ttu-id="e9305-132">構成エラーが修復された後、MED-V ワークスペースに含まれる画像はドメインに参加できません。</span><span class="sxs-lookup"><span data-stu-id="e9305-132">After the configuration error is repaired, the image included in the MED-V workspace cannot join the domain.</span></span>

### <span data-ttu-id="e9305-133">解決策</span><span class="sxs-lookup"><span data-stu-id="e9305-133">Solution</span></span>

<span data-ttu-id="e9305-134">画像が配置されている場合は、イメージを再配布します。</span><span class="sxs-lookup"><span data-stu-id="e9305-134">If the image was deployed, redistribute the image.</span></span> <span data-ttu-id="e9305-135">イメージがテストイメージの場合は、イメージを再作成します。</span><span class="sxs-lookup"><span data-stu-id="e9305-135">If the image was a test image, re-create the image.</span></span>

## <span data-ttu-id="e9305-136">MED-V は複数のモニターをサポートしていません</span><span class="sxs-lookup"><span data-stu-id="e9305-136">MED-V does not support multiple monitors</span></span>


<span data-ttu-id="e9305-137">MED では、複数のモニターでの公開アプリケーションの表示はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e9305-137">MED-V does not support displaying published applications across multiple monitors.</span></span> <span data-ttu-id="e9305-138">公開されたアプリケーションとその他のクライアントウィンドウが間違った画面に表示されることがあり、画面が切断された後に、接続されているモニターが空白で表示されるように画面をモニターに送信しようとすることがあります。</span><span class="sxs-lookup"><span data-stu-id="e9305-138">Published applications and other client windows may be displayed in the wrong screen, and sometimes after a screen is disconnected, MED-V attempts to send the screen to the monitor so that the connected monitor appears blank.</span></span>

### <span data-ttu-id="e9305-139">解決策</span><span class="sxs-lookup"><span data-stu-id="e9305-139">Solution</span></span>

<span data-ttu-id="e9305-140">追加の画面を切断し、クライアントを再起動します。</span><span class="sxs-lookup"><span data-stu-id="e9305-140">Disconnect the additional screen, and restart the client.</span></span>

## <span data-ttu-id="e9305-141">MED-V ワークスペースの起動中にホストがクラッシュすると、MED ワークスペースが起動しない場合がある</span><span class="sxs-lookup"><span data-stu-id="e9305-141">MED-V workspace might fail to start if the host crashes during MED-V workspace startup</span></span>


<span data-ttu-id="e9305-142">MED-V ワークスペースの起動プロセス中にホストがクラッシュし、"ルート要素が見つからない" というエラーメッセージが表示される場合、MED-V ワークスペースによって空の仮想マシン構成 (VMC) ファイルにデータが追加されることがあります。これにより、起動プロセスが失敗します。</span><span class="sxs-lookup"><span data-stu-id="e9305-142">If the host crashes during the MED-V workspace startup process and an error message appears that says “Root element is missing,” the MED-V workspace might add data to an empty virtual machine configuration (VMC) file, which will cause the startup process to fail.</span></span>

### <span data-ttu-id="e9305-143">解決策</span><span class="sxs-lookup"><span data-stu-id="e9305-143">Solution</span></span>

<span data-ttu-id="e9305-144">ベースイメージから、空の VMC ファイルを VMC ファイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e9305-144">Replace the empty VMC file with a VMC file from the base image.</span></span>

## <span data-ttu-id="e9305-145">キーボードが公開されたアプリケーションウィンドウで応答しない</span><span class="sxs-lookup"><span data-stu-id="e9305-145">The keyboard does not respond in published application windows</span></span>


<span data-ttu-id="e9305-146">MED-V ワークスペースでは、公開されたアプリケーションがフォーカスされているときに Windows ロゴキーを押すと、公開されたアプリケーションウィンドウでキーボードが応答しなくなります。</span><span class="sxs-lookup"><span data-stu-id="e9305-146">In a MED-V workspace, if you press the Windows logo key when a published application is in focus, the keyboard no longer responds in published application windows.</span></span>

### <span data-ttu-id="e9305-147">解決策</span><span class="sxs-lookup"><span data-stu-id="e9305-147">Solution</span></span>

<span data-ttu-id="e9305-148">公開アプリケーションがフォーカスされているときに、Windows ロゴキーを押します。</span><span class="sxs-lookup"><span data-stu-id="e9305-148">Press the Windows logo key while a published application is in focus.</span></span>

## <span data-ttu-id="e9305-149">ドメインの MED-V ワークスペースでドメインの資格情報が更新されない</span><span class="sxs-lookup"><span data-stu-id="e9305-149">A domain MED-V workspace does not update domain credentials</span></span>


<span data-ttu-id="e9305-150">ドメイン環境で永続的な MED-V ワークスペースを使用している場合、ドメインパスワードを変更しても、MED-V クライアントは MED-V ワークスペースドメインの資格情報を更新しません。</span><span class="sxs-lookup"><span data-stu-id="e9305-150">When using a persistent MED-V workspace in a domain environment, if you change your domain password, the MED-V client does not update the MED-V workspace domain credentials.</span></span> <span data-ttu-id="e9305-151">公開されたアプリケーションがネットワークリソースにアクセスしようとすると、資格情報の有効期限が切れたことを通知するエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9305-151">When a published application attempts to access a network resource, you will receive an error message notifying you that your credentials expired.</span></span>

### <span data-ttu-id="e9305-152">解決策</span><span class="sxs-lookup"><span data-stu-id="e9305-152">Solution</span></span>

<span data-ttu-id="e9305-153">MED-V ワークスペースオペレーティングシステムを再起動します。</span><span class="sxs-lookup"><span data-stu-id="e9305-153">Restart the MED-V workspace operating system.</span></span>

## <span data-ttu-id="e9305-154">最大化された公開済みアプリケーション windows でホストタスクバーをカバーする</span><span class="sxs-lookup"><span data-stu-id="e9305-154">Maximized published application windows cover the host taskbar</span></span>


<span data-ttu-id="e9305-155">公開されているアプリケーションウィンドウを全画面表示に最大化すると、ホストタスクバーが隠れている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e9305-155">If you maximize a published application window to full screen, it might cover the host taskbar.</span></span>

### <span data-ttu-id="e9305-156">解決策</span><span class="sxs-lookup"><span data-stu-id="e9305-156">Solution</span></span>

<span data-ttu-id="e9305-157">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e9305-157">Do one of the following:</span></span>

<span data-ttu-id="e9305-158">公開されたアプリケーションウィンドウを最小化して通知領域にアクセスし、MED-V ワークスペースを再起動します。</span><span class="sxs-lookup"><span data-stu-id="e9305-158">Minimize the published application window to gain access to the notification area, and restart the MED-V workspace.</span></span>

<span data-ttu-id="e9305-159">公開されているアプリケーションウィンドウを最小化し、ウィンドウを最大化された状態に復元します。</span><span class="sxs-lookup"><span data-stu-id="e9305-159">Minimize the published application window, and then restore the window to its maximized state.</span></span>

## <span data-ttu-id="e9305-160">MED-V Server 構成マネージャーでのユーザーまたはグループの追加が機能しない</span><span class="sxs-lookup"><span data-stu-id="e9305-160">Adding users or groups in the MED-V Server Configuration Manager does not work</span></span>


<span data-ttu-id="e9305-161">**[ユーザーまたは**グループの選択] ダイアログボックスでユーザーまたはグループを追加すると、選択したユーザーまたはグループは、Med-v サーバー構成マネージャーのアクセス制御リストに追加されません。</span><span class="sxs-lookup"><span data-stu-id="e9305-161">When adding users or groups in the **Select Users or Groups** dialog box, the selected users or groups are not added to the access control list in the MED-V Server Configuration Manager.</span></span>

### <span data-ttu-id="e9305-162">解決策</span><span class="sxs-lookup"><span data-stu-id="e9305-162">Solution</span></span>

<span data-ttu-id="e9305-163">[ユーザーまたは**グループ名の入力**] ダイアログボックスを使用して、ユーザーまたはグループを追加します。</span><span class="sxs-lookup"><span data-stu-id="e9305-163">Add users or groups using the **Enter User or Group names** dialog box.</span></span> <span data-ttu-id="e9305-164">詳細については、「 [Med-v サーバーコンポーネントをインストールして構成する方法](how-to-install-and-configure-the-med-v-server-component.md#bkmk-configuringpermissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9305-164">For detailed information, see [How to Install and Configure the MED-V Server Component](how-to-install-and-configure-the-med-v-server-component.md#bkmk-configuringpermissions).</span></span>

## <span data-ttu-id="e9305-165">Windows 7 版 windows 7 がインストールされているコンピューターで、MED-V が機能しない</span><span class="sxs-lookup"><span data-stu-id="e9305-165">MED-V does not work on computers with Windows Virtual PC for Windows 7 installed</span></span>


<span data-ttu-id="e9305-166">MED には Windows 仮想 PC2007 が必要です。</span><span class="sxs-lookup"><span data-stu-id="e9305-166">MED-V requires Windows Virtual PC2007.</span></span> <span data-ttu-id="e9305-167">Windows Virtual PC for Windows7 と Virtual PC2007 SP1 を同じコンピューターにインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e9305-167">Windows Virtual PC for Windows7 and Virtual PC2007 SP1 cannot be installed on the same computer.</span></span>

### <span data-ttu-id="e9305-168">解決策</span><span class="sxs-lookup"><span data-stu-id="e9305-168">Solution</span></span>

<span data-ttu-id="e9305-169">Virtual PC2007 SP1 と MED-V をインストールする前に、Windows7 用の Virtual PC をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="e9305-169">Uninstall Virtual PC for Windows7 before installing Virtual PC2007 SP1 and MED-V.</span></span>

## <a href="" id="med-v-does-not-support-virtual-pc-and-windows-xp-mode-images-"></a><span data-ttu-id="e9305-170">MED-V では、Virtual PC および WindowsXP モードのイメージはサポートされません</span><span class="sxs-lookup"><span data-stu-id="e9305-170">MED-V does not support Virtual PC and WindowsXP Mode images</span></span>


<span data-ttu-id="e9305-171">MED-V 1.0 SP1 は、Windows Virtual PC for Windows7 によって作成された画像をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e9305-171">MED-V1.0 SP1 does not support images created by Windows Virtual PC for Windows7.</span></span> <span data-ttu-id="e9305-172">Virtual PC for Windows7 image を使用している場合、クライアントは起動時に失敗します。</span><span class="sxs-lookup"><span data-stu-id="e9305-172">If a Virtual PC for Windows7 image is used, the client will fail during startup.</span></span>

### <span data-ttu-id="e9305-173">解決策</span><span class="sxs-lookup"><span data-stu-id="e9305-173">Solution</span></span>

<span data-ttu-id="e9305-174">Virtual PC2007 SP1 を使用して、MED-V イメージを作成します。</span><span class="sxs-lookup"><span data-stu-id="e9305-174">Create MED-V images by using Virtual PC2007 SP1.</span></span>

## <span data-ttu-id="e9305-175">Windows ファイアウォールで仮想 PC2007 SP1 のネットワークアクティビティをブロックする</span><span class="sxs-lookup"><span data-stu-id="e9305-175">Windows firewall blocks Virtual PC2007 SP1 network activity</span></span>


<span data-ttu-id="e9305-176">既定では、Windows ファイアウォールは仮想 PC2007 SP1 ネットワークアクティビティをブロックし、クライアントコンピューターで仮想 PC2007 SP1 が開始されると、そのスタートアップシーケンスとすべてのネットワークアクセスをブロックするファイアウォールメッセージがあります。</span><span class="sxs-lookup"><span data-stu-id="e9305-176">By default, Windows firewall blocks Virtual PC2007 SP1 network activity, and when Virtual PC2007 SP1 initiates on the client computer, there is a firewall message that blocks its startup sequence and all network access.</span></span>

### <span data-ttu-id="e9305-177">解決策</span><span class="sxs-lookup"><span data-stu-id="e9305-177">Solution</span></span>

<span data-ttu-id="e9305-178">MED-V がエンドユーザーによって使用される前にグループポリシーを使用して、ファイアウォールの例外を更新します。</span><span class="sxs-lookup"><span data-stu-id="e9305-178">Update the firewall exception by using Group Policy before MED-V is used by the end user.</span></span>

## <span data-ttu-id="e9305-179">クライアントをアップグレードすると、エラーメッセージが表示される</span><span class="sxs-lookup"><span data-stu-id="e9305-179">When upgrading the client an error message appears</span></span>


<span data-ttu-id="e9305-180">クライアントを MED-V 1.0 から MED-V 1.0 SP1 にアップグレードするときに、MED-V ワークスペースが定義されていないことを通知するメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="e9305-180">When upgrading the client from MED-V1.0 to MED-V1.0 SP1, a message may appear notifying you that no MED-V workspace is defined.</span></span>

### <span data-ttu-id="e9305-181">解決策</span><span class="sxs-lookup"><span data-stu-id="e9305-181">Solution</span></span>

<span data-ttu-id="e9305-182">クライアントを閉じて再起動します。</span><span class="sxs-lookup"><span data-stu-id="e9305-182">Close the client and restart it.</span></span>

## <span data-ttu-id="e9305-183">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e9305-183">Related topics</span></span>


[<span data-ttu-id="e9305-184">MED-V 1.0 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="e9305-184">MED-V 1.0 Release Notes</span></span>](med-v-10-release-notesmedv-10.md)

[<span data-ttu-id="e9305-185">MED-V 1.0 SP1 および SP2 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="e9305-185">MED-V 1.0 SP1 and SP2 Release Notes</span></span>](med-v-10-sp1-and-sp2-release-notesmedv-10-sp1.md)

 

 





