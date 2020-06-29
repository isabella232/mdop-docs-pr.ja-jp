---
title: 操作のトラブルシューティング
description: 操作のトラブルシューティング
author: dansimp
ms.assetid: 948d7869-accd-44da-974f-93409234dee7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 126b5fae517c59914dcb7fb155ef4ad47278b5bd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812739"
---
# <span data-ttu-id="eaa7d-103">操作のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="eaa7d-103">Operations Troubleshooting</span></span>


<span data-ttu-id="eaa7d-104">このトピックでは、Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 での一般的な操作の問題のトラブルシューティングに役立つ情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-104">This topic includes information that you can use to help troubleshoot general operational issues in Microsoft Enterprise Desktop Virtualization (MED-V) 2.0.</span></span>

## <span data-ttu-id="eaa7d-105">MED-V 操作の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="eaa7d-105">Troubleshooting Issues in MED-V Operations</span></span>


<span data-ttu-id="eaa7d-106">以下は、エンドユーザーが MED-V とソリューションを実行したときに発生する可能性のある問題のうち、これらの問題のトラブルシューティングに役立ついくつかの問題を示しています。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-106">The following are some issues end users might encounter when they run MED-V and solutions to help troubleshoot these issues:</span></span>

<span data-ttu-id="eaa7d-107">**ドキュメントのリダイレクションは失敗**します。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-107">**Documentation Redirection Fails**.</span></span> <span data-ttu-id="eaa7d-108">通常、この問題は、エンドユーザーの [マイドキュメント] フォルダーがネットワーク上の場所をポイントしている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-108">This issue typically occurs when an end user’s My Documents folder points to a network location.</span></span> <span data-ttu-id="eaa7d-109">Windows では、別の共有フォルダーからの共有の作成はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-109">Windows does not support creating a share from another shared folder.</span></span> <span data-ttu-id="eaa7d-110">ドライブまたはフォルダーがゲストにリダイレクトされると、RDP\\Windows Virtual PC でそのフォルダーの共有が作成されます。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-110">When a drive or folder is redirected to the guest, RDP\\Windows Virtual PC creates a share for that folder.</span></span> <span data-ttu-id="eaa7d-111">したがって、ホストの [マイドキュメント] フォルダーで既に共有をポイントしている場合、RDP\\Windows Virtual PC で共有の共有を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-111">Therefore, if the My Documents folder on the host is already pointing to a share, RDP\\Windows Virtual PC cannot create a share of a share.</span></span>

<span data-ttu-id="eaa7d-112">この問題の別の原因として、ネットワークリソースに接続するために必要な資格情報が、ユーザーのドメイン資格情報と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-112">Another possible cause of this issue is that the credentials that are required to connect to the network resource might differ from the user’s domain credentials.</span></span> <span data-ttu-id="eaa7d-113">MED は、ホストでドキュメントがリダイレクトされたことを検出し、その情報をゲストに送信して、ネットワークリソースを再接続する場合があります。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-113">MED-V might be detecting that documents are redirected on the host, send that information to the guest, and then try to reconnect the network resource.</span></span> <span data-ttu-id="eaa7d-114">ユーザーの資格情報が認証されない場合、MED-V で認証の試行が停止することがあります。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-114">If the user’s credentials do not authenticate, MED-V might stop trying to authenticate.</span></span>

**<span data-ttu-id="eaa7d-115">解決策</span><span class="sxs-lookup"><span data-stu-id="eaa7d-115">Solution</span></span>**

<span data-ttu-id="eaa7d-116">この問題を解決するには、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-116">Try one of the following to resolve this issue:</span></span>

-   <span data-ttu-id="eaa7d-117">Active Directory 内のユーザーのルートディレクトリを設定します。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-117">Set the user’s root directory inside Active Directory.</span></span> <span data-ttu-id="eaa7d-118">その後、ゲストとホストは同じネットワークリソースに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-118">The guest and host should then connect to the same network resource.</span></span>

-   <span data-ttu-id="eaa7d-119">[マイドキュメント] フォルダーを UNC パスにリダイレクトする代わりに、それをドライブ文字にマップします (ホスト上で、ネットワークリソースをポイントするドライブをマップします)。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-119">Instead of redirecting the My Documents folder to a UNC path, map it to a drive letter (on the host, map a drive that points to the network resource).</span></span> <span data-ttu-id="eaa7d-120">次に、[マイドキュメント] フォルダーを UNC パスの代わりにドライブ文字を使用するように設定できます。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-120">The My Documents folder can then be set to use the drive letter instead of the UNC path.</span></span> <span data-ttu-id="eaa7d-121">その後、ゲストは、同じマップされたドライブに期待どおりにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-121">The guest will then redirect to that same mapped drive as expected.</span></span>

-   <span data-ttu-id="eaa7d-122">ゲストで、[マイドキュメント] フォルダーをネットワークリソースにリダイレクトするスタートアップスクリプトを作成し、必要に応じて追加の資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-122">Create a startup script in the guest that redirects the My Documents folder to the network resource and provides additional credentials as needed.</span></span>

<span data-ttu-id="eaa7d-123">**URL リダイレクションは失敗**します。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-123">**URL Redirection Fails**.</span></span> <span data-ttu-id="eaa7d-124">ホストからゲストへのリダイレクト用に指定した URL が、意図したとおりにリダイレクトされないか、web サイトが存在しないことを示すエラーメッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-124">A URL that you have specified for redirection from the host to the guest is not redirecting as intended or is returning an error message that indicates that the website does not exist.</span></span>

**<span data-ttu-id="eaa7d-125">解決策</span><span class="sxs-lookup"><span data-stu-id="eaa7d-125">Solution</span></span>**

<span data-ttu-id="eaa7d-126">このエラーは、URL リダイレクション情報にスペルミスがあるか、アスタリスク (\ \*) などの文字が間違って使用されている場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-126">This error can occur when there is a misspelling or incorrect use of characters, such as asterisk (\*), in the URL redirection information.</span></span> <span data-ttu-id="eaa7d-127">URL リダイレクションのレジストリ値を確認し、誤りがあれば修正します。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-127">Check the registry value for URL redirection and correct any mistakes.</span></span>

<span data-ttu-id="eaa7d-128">レジストリキーが呼び出され、通常、次の場所 `RedirectUrls` にあります。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-128">The registry key is called `RedirectUrls` and is typically located at:</span></span>

<span data-ttu-id="eaa7d-129">Computer¥¥ \ Key\ _LOCAL \ _MACHINE ¥¥¥¥¥¥¥¥¥ |</span><span class="sxs-lookup"><span data-stu-id="eaa7d-129">Computer\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MEDV\\v2\\UserExperience</span></span>

<span data-ttu-id="eaa7d-130">**タスクバーのアイコンが誤解を招く**ことがあります。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-130">**Icon in Taskbar Misleading**.</span></span> <span data-ttu-id="eaa7d-131">既定では、公開されたアプリケーションとリダイレクトされた Url について、エンドユーザーのタスクバーに表示されるアイコンは、Windows 仮想 PC のアイコンです。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-131">By default, the icon that appears in an end user’s taskbar for published applications and redirected URLs is the icon for Windows Virtual PC.</span></span> <span data-ttu-id="eaa7d-132">エンドユーザーがこのような既定の動作を認識していない場合は、タスクバーを見てアプリを見つけたときに、混乱を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-132">If an end user is not aware of this default behavior, they can become confused when looking at the taskbar to locate their application.</span></span>

**<span data-ttu-id="eaa7d-133">解決策</span><span class="sxs-lookup"><span data-stu-id="eaa7d-133">Solution</span></span>**

<span data-ttu-id="eaa7d-134">この既定の動作を回避する唯一の方法は、次のようにタスクバーのプロパティのユーザー設定を変更することです。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-134">The only way to avoid this default behavior is to change the user settings for the taskbar properties as follows:</span></span>

1.  <span data-ttu-id="eaa7d-135">タスクバーを右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-135">Right-click the taskbar and then click **Properties**.</span></span>

2.  <span data-ttu-id="eaa7d-136">[**タスクバーと [スタート] メニューのプロパティ**] ダイアログボックスで、[**タスクバー** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-136">In the **Taskbar and Start Menu Properties** dialog box, click the **Taskbar** tab.</span></span>

3.  <span data-ttu-id="eaa7d-137">[**タスクバーのボタン**] ボックスのドロップダウンバーで、[**結合しない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-137">In the drop-down bar for the **Taskbar buttons** box, select **Never combine**.</span></span>

4.  <span data-ttu-id="eaa7d-138">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-138">Click **OK**.</span></span>

<span data-ttu-id="eaa7d-139">公開アプリケーションの予期しているアイコンとリダイレクトされた Url が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-139">The expected icons for published applications and redirected URLs are displayed.</span></span>

<span data-ttu-id="eaa7d-140">**2 人目のユーザーがログオンを試みた場合、または仮想マシンが使用されて**いる場合に警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-140">**Warning Issued if Second User Attempts Log on or if Virtual Machine is in Use**.</span></span> <span data-ttu-id="eaa7d-141">最初のユーザーが MED-V を実行しているときに、2番目のユーザーが MED-V ワークスペースにログオンすると、警告メッセージが発行されます。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-141">A warning message is issued when a second user logs on to a MED-V workspace while a first user is still running MED-V.</span></span> <span data-ttu-id="eaa7d-142">また、仮想マシンを使用している間に MED-V が開始されている場合 (たとえば、[**スタート**] メニューで [WINDOWS 仮想 PC] から仮想マシンを起動した場合など) も、警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-142">The warning is also issued if MED-V is started while the virtual machine is being used, for example, if the virtual machine was started through Windows Virtual PC on the **Start** menu.</span></span> <span data-ttu-id="eaa7d-143">エンドユーザーが警告メッセージを受け取ると、MED-V はシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-143">When the end user accepts the warning message, MED-V shuts down.</span></span>

**<span data-ttu-id="eaa7d-144">解決策</span><span class="sxs-lookup"><span data-stu-id="eaa7d-144">Solution</span></span>**

<span data-ttu-id="eaa7d-145">エンドユーザーは、ログオンを試みる前に、他のすべてのユーザーが MED-V からログオフすることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-145">An end user must verify that all other users are logged off MED-V before they try to log on.</span></span> <span data-ttu-id="eaa7d-146">これにより、MED-V の他のインスタンスが実行されておらず、Windows 仮想 PC が仮想マシンの制御に含まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-146">This ensures that no other instance of MED-V is running and that Windows Virtual PC is not in control of the virtual machine.</span></span>

<span data-ttu-id="eaa7d-147">**初回のセットアップ時にビープ音が鳴り**ます。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-147">**Beeps Heard During First Time Setup**.</span></span> <span data-ttu-id="eaa7d-148">場合によっては、MED-V が最初に実行されているときにビープ音が聞こえます。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-148">Occasionally, beeps are heard while MED-V is running first time setup.</span></span> <span data-ttu-id="eaa7d-149">これは、エンドユーザーの混乱を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-149">This can be confusing to an end user.</span></span> <span data-ttu-id="eaa7d-150">ビープ音は、シャットダウンなどの特定の操作を実行したときに仮想マシンから発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-150">The beeps are originating from the virtual machine when it performs certain actions, such as shutting down.</span></span>

**<span data-ttu-id="eaa7d-151">解決策</span><span class="sxs-lookup"><span data-stu-id="eaa7d-151">Solution</span></span>**

<span data-ttu-id="eaa7d-152">各仮想マシンの開始シーケンスの先頭に「net stop beep」コマンドを指定して、ビープサービスを停止できます。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-152">You can stop the beep service by specifying the "net stop beep" command at the beginning of each virtual machine start sequence.</span></span> <span data-ttu-id="eaa7d-153">または、"sc config beep start = disabled" コマンドを指定して、ビープサービスを無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-153">Or you can disable the beep service by specifying the “sc config beep start= disabled" command.</span></span> <span data-ttu-id="eaa7d-154">これらのコマンドは、画像を封印する前か、Sysprep の一部として指定できます。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-154">You can specify these commands either before you seal the image or as part of Sysprep.</span></span>

<span data-ttu-id="eaa7d-155">**ブリッジモードの Med-v ワークスペース用に複数のネットワーク接続が作成さ**れます。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-155">**Multiple Network Connections Created for MED-V Workspaces in BRIDGED Mode**.</span></span> <span data-ttu-id="eaa7d-156">初めてセットアップするときに、NAT モード用に構成されている MED-V ワークスペースを作成した場合、Windows 仮想 PC では1つのネットワーク接続のみが作成されます。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-156">If first time setup is creating a MED-V workspace that is configured for NAT mode, it only creates a single network connection in Windows Virtual PC.</span></span> <span data-ttu-id="eaa7d-157">ただし、初めてセットアップするときに、ブリッジモード用に構成されている MED-V ワークスペースを作成している場合は、コンピューターにインストールされているネットワークアダプターごとに個別のネットワーク接続が作成されます。これにより、MED-V は、どのネットワークアダプターがアクティブであるかを判断できないためです。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-157">However, if first time setup is creating a MED-V workspace that is configured for BRIDGED mode, it creates a separate network connection for each network adapter that is installed in the computer, because MED-V cannot determine which network adapter is active.</span></span> <span data-ttu-id="eaa7d-158">これにより、ローミングユーザーは常に有線およびワイヤレス接続用のネットワークアダプターを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-158">This also ensures that roaming users always have a network adapter available for wired and wireless connections.</span></span>

**<span data-ttu-id="eaa7d-159">解決策</span><span class="sxs-lookup"><span data-stu-id="eaa7d-159">Solution</span></span>**

<span data-ttu-id="eaa7d-160">なし。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-160">None.</span></span>

<span data-ttu-id="eaa7d-161">**終了時に、Med-v アプリケーションが長すぎて応答**しません。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-161">**MED-V Application is Unresponsive for Too Long when Closing**.</span></span> <span data-ttu-id="eaa7d-162">場合によっては、終了しようとしているときに、MED-V アプリケーションが応答を停止することがあります。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-162">In some instances, a MED-V application stops responding when it is trying to close.</span></span>

**<span data-ttu-id="eaa7d-163">解決策</span><span class="sxs-lookup"><span data-stu-id="eaa7d-163">Solution</span></span>**

<span data-ttu-id="eaa7d-164">WaitToKillAppTimeout が応答しなくなったアプリケーションを閉じるまでの時間の長さを指定するには、ゲスト仮想マシンのレジストリキーを設定します。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-164">You can specify the length of time that MED-V waits to close unresponsive applications by setting the WaitToKillAppTimeout registry key in the guest virtual machine.</span></span> <span data-ttu-id="eaa7d-165">詳細については、「 [WINDOWS XP でプロセスを正常に終了するために、シャットダウン時間を延長する方法](https://go.microsoft.com/fwlink/?LinkId=206819)」を参照してください https://go.microsoft.com/fwlink/?LinkId=206819) 。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-165">For more information, see [How To Increase Shutdown Time So That Processes Can Quit Properly in Windows XP](https://go.microsoft.com/fwlink/?LinkId=206819) (https://go.microsoft.com/fwlink/?LinkId=206819).</span></span>

<span data-ttu-id="eaa7d-166">**ゲスト仮想マシンで公開されたアプリケーションのショートカットの名前を変更しても、ホストの公開された名前は変更されません**。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-166">**Renaming a Published Application Shortcut in the Guest Virtual Machine does not Change the Published Name in the Host**.</span></span> <span data-ttu-id="eaa7d-167">ショートカットを作成してアプリケーションを公開し、ゲスト仮想マシンのショートカットの名前を変更すると、元のアプリケーション名はホストの [**スタート**] メニューに残ります。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-167">When you publish an application by creating a shortcut and then rename the shortcut in the guest virtual machine, the original application name remains in the host **Start** menu.</span></span> <span data-ttu-id="eaa7d-168">プログラムは期待どおりに実行されますが、プログラムは常に元の名前を保持します。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-168">The program continues to run as expected, however the program will always retain the original name.</span></span>

**<span data-ttu-id="eaa7d-169">解決策</span><span class="sxs-lookup"><span data-stu-id="eaa7d-169">Solution</span></span>**

<span data-ttu-id="eaa7d-170">なし。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-170">None.</span></span> <span data-ttu-id="eaa7d-171">これは、Windows 仮想 PC の既知の動作です。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-171">This is a known behavior of Windows Virtual PC.</span></span>

<span data-ttu-id="eaa7d-172">**ゲスト仮想マシンのショートカットを移動しても、ホストコンピューターの [スタート] メニューの場所は更新されません**。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-172">**Moving a Shortcut in the Guest Virtual Machine does not Update the Location on the Host Computer Start Menu**.</span></span> <span data-ttu-id="eaa7d-173">ホストコンピューターの [**スタート**] メニューに公開されている med-v アプリケーションのショートカットは、レジストリにカタログ登録されます。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-173">MED-V application shortcuts that are published to the host computer **Start** menu are cataloged in the registry.</span></span> <span data-ttu-id="eaa7d-174">アプリケーションのショートカットをサブフォルダーに移動しても、その変更を反映するようにレジストリが更新されることはありません。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-174">If you move an application shortcut into a subfolder, the registry is not updated to reflect the change.</span></span>

**<span data-ttu-id="eaa7d-175">解決策</span><span class="sxs-lookup"><span data-stu-id="eaa7d-175">Solution</span></span>**

<span data-ttu-id="eaa7d-176">MED-V アプリケーションショートカットの場所を変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-176">Follow these steps to change the location of a MED-V application shortcut:</span></span>

1.  <span data-ttu-id="eaa7d-177">MED-V が実行されている場合は、MED-V ゲスト仮想マシンで Windows エクスプローラーを開きます。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-177">When MED-V is running, open up Windows Explorer on the MED-V guest virtual machine.</span></span>

2.  <span data-ttu-id="eaa7d-178">"%ALLUSERSPROFILE%\\Start menu¥ Programs" ディレクトリを参照します。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-178">Browse to the "%ALLUSERSPROFILE%\\Start Menu\\Programs" directory.</span></span>

3.  <span data-ttu-id="eaa7d-179">[スタート] メニューまたは [プログラム] フォルダーからアプリケーションのショートカットを移動します。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-179">Move the application shortcuts out of the startmenu or programs folders.</span></span>

4.  <span data-ttu-id="eaa7d-180">約30秒後に、ホストコンピューターの [**スタート**] メニューからショートカットが削除されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-180">After about 30 seconds, validate that the shortcuts are removed from the host computer **Start** menu.</span></span>

5.  <span data-ttu-id="eaa7d-181">アプリケーションのショートカットを、[スタート] メニューの [プログラム] ディレクトリの下にある新しいプログラムフォルダーに戻します。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-181">Move the application shortcuts back in to the new program folders under the Start Menu\\Programs directory.</span></span>

6.  <span data-ttu-id="eaa7d-182">約30秒後に、ホストコンピューターの [**スタート**] メニューでショートカットが更新されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-182">After about 30 seconds, validate that the shortcuts are updated in the host computer **Start** Menu.</span></span>

<span data-ttu-id="eaa7d-183">**公開されたアプリケーションは、アイドル状態になるとタイムアウトする可能性が**あります。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-183">**Published Applications can Time Out after Sitting Idle**.</span></span> <span data-ttu-id="eaa7d-184">場合によっては、公開されたアプリケーションがしばらくアイドル状態になっていると、時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-184">In some cases, published applications will time out if they have sat idle for some time.</span></span> <span data-ttu-id="eaa7d-185">この状況は、IPsec が有効であり、MED-V ワークスペースが NAT モードで構成されている場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-185">This situation only occurs if IPsec is enabled and the MED-V workspace is configured for NAT mode.</span></span> <span data-ttu-id="eaa7d-186">この状況は、ブリッジモードで実行している場合は発生しません。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-186">This situation does not occur if running in BRIDGED mode.</span></span>

**<span data-ttu-id="eaa7d-187">解決策</span><span class="sxs-lookup"><span data-stu-id="eaa7d-187">Solution</span></span>**

<span data-ttu-id="eaa7d-188">NAT モードで MED-V ワークスペースを実行している場合は、IPsec を無効にします。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-188">Disable IPsec when you are running the MED-V workspace in NAT mode.</span></span>

<span data-ttu-id="eaa7d-189">**公開されたアプリケーションをタスクバーにピン留めするのは、med-v をバイパス**します。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-189">**Pinning a Published Application to the Taskbar Bypasses MED-V**.</span></span> <span data-ttu-id="eaa7d-190">エンドユーザーが公開されたアプリケーションをタスクバーにピン留めしてアプリケーションを閉じると、次にアプリケーションをタスクバーアイコンから開いたときに MED-V がバイパスされます。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-190">If an end user pins a published application to the taskbar and then closes the application, MED-V is bypassed the next time that the application is opened from the taskbar icon.</span></span> <span data-ttu-id="eaa7d-191">代わりに、アプリケーションは VMSAL ウィンドウで直接開きます。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-191">Instead, the application opens directly in a VMSAL window.</span></span>

**<span data-ttu-id="eaa7d-192">解決策</span><span class="sxs-lookup"><span data-stu-id="eaa7d-192">Solution</span></span>**

<span data-ttu-id="eaa7d-193">MED-V に公開されているアプリケーションをタスクバーにピン留めしないでください。</span><span class="sxs-lookup"><span data-stu-id="eaa7d-193">Do not pin the applications published in MED-V to the taskbar.</span></span>

## <span data-ttu-id="eaa7d-194">関連トピック</span><span class="sxs-lookup"><span data-stu-id="eaa7d-194">Related topics</span></span>


[<span data-ttu-id="eaa7d-195">MED-V 操作のセキュリティのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="eaa7d-195">Security Best Practices for MED-V Operations</span></span>](security-best-practices-for-med-v-operations.md)

[<span data-ttu-id="eaa7d-196">展開のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="eaa7d-196">Deployment Troubleshooting</span></span>](deployment-troubleshooting.md)

 

 





