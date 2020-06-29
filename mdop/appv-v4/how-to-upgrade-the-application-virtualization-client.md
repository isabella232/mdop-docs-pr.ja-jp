---
title: Application Virtualization Client をアップグレードする方法
description: Application Virtualization Client をアップグレードする方法
author: dansimp
ms.assetid: 2a75d8b5-da88-456c-85bb-f5bd3d470f7f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b9748fbdba7c8d2777a06c93295e4582be784dd1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816454"
---
# <span data-ttu-id="97df6-103">Application Virtualization Client をアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="97df6-103">How to Upgrade the Application Virtualization Client</span></span>


<span data-ttu-id="97df6-104">次の手順を使用して、Application Virtualization (App-v) デスクトップクライアントまたはリモートデスクトップサービス (旧ターミナルサービス) の App-v クライアントをアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="97df6-104">You can use the following procedures to upgrade the Application Virtualization (App-V) Desktop Client or the App-V Client for Remote Desktop Services (formerly Terminal Services).</span></span> <span data-ttu-id="97df6-105">クライアントをアップグレードするには、以前にインストールされていた以前のバージョンに新しいバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="97df6-105">You upgrade the client by installing a new version over the previously installed older version.</span></span> <span data-ttu-id="97df6-106">クライアントをアップグレードすると、インストーラーソフトウェアによって仮想アプリケーションのユーザー設定が自動的に保存され、移行されます。</span><span class="sxs-lookup"><span data-stu-id="97df6-106">When you upgrade the clients, the installer software automatically preserves and migrates the user’s settings for virtual applications.</span></span> <span data-ttu-id="97df6-107">セットアッププログラムを実行するには、管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="97df6-107">Administrative rights are required to run the setup program.</span></span>

<span data-ttu-id="97df6-108">**注** Application Virtualization (App-v) 4.5 以降のバージョンへのアップグレード中に、HKCU レジストリキーへのアクセス許可が変更されます。</span><span class="sxs-lookup"><span data-stu-id="97df6-108">**Note** During the upgrade to Application Virtualization (App-V)4.5 or later versions, the permissions to the HKCU registry key are changed.</span></span> <span data-ttu-id="97df6-109">このため、ユーザー構成の切断モードの設定など、以前に設定されたユーザー構成は失われます。</span><span class="sxs-lookup"><span data-stu-id="97df6-109">Because of this, users will lose user configurations that were set previously, such as user-configured Disconnected Mode settings.</span></span> <span data-ttu-id="97df6-110">ユーザーが、アクセス許可のロックダウンを通じてクライアントユーザーインターフェイスの動作をまだ制限していない場合、ユーザーは公開の更新後にこれらの設定をリセットできます。</span><span class="sxs-lookup"><span data-stu-id="97df6-110">If the user is not actively restricted from configuring client user interface behavior through a permission lockdown, the user can reset these preferences after a publishing refresh.</span></span>

 

<span data-ttu-id="97df6-111">**重要** バージョン4.6 以降の App-v クライアントにアップグレードする場合は、コンピューターのオペレーティングシステム32ビットまたは64ビットに適切なインストーラーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97df6-111">**Important** When upgrading to version4.6 or a later version of the App-V Client, you must use the correct installer for the computer’s operating system, 32-bit or 64-bit.</span></span> <span data-ttu-id="97df6-112">インストールが失敗し、誤ったインストーラーを使用した場合にエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97df6-112">The installation will fail and an error message will be displayed if you use the wrong installer.</span></span>

 

**<span data-ttu-id="97df6-113">Application Virtualization デスクトップクライアントをアップグレードするには</span><span class="sxs-lookup"><span data-stu-id="97df6-113">To upgrade the Application Virtualization Desktop Client</span></span>**

1.  <span data-ttu-id="97df6-114">すべての仮想アプリケーションをシャットダウンし、Windows デスクトップ通知領域に表示されている App-v デスクトップクライアントアイコンを右クリックして、[**終了**] を選択して既存のクライアントをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="97df6-114">Shut down all virtual applications, right-click the App-V Desktop Client icon displayed in the Windows desktop notification area, and select **Exit** to shut down the existing client.</span></span>

2.  <span data-ttu-id="97df6-115">適切なインストーラアーカイブファイルを取得してコンピューターに保存したら、それをダブルクリックしてアーカイブを展開します。</span><span class="sxs-lookup"><span data-stu-id="97df6-115">After you have obtained the correct installer archive file and saved it to your computer, double-click it to expand the archive.</span></span>

3.  <span data-ttu-id="97df6-116">[参照] をクリックして setup.exe ファイルを見つけ、[setup.exe] をダブルクリックしてインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="97df6-116">Browse to find the setup.exe file, and double-click setup.exe to start the installation.</span></span>

4.  <span data-ttu-id="97df6-117">ウィザードがシステムをチェックして、すべての必須ソフトウェアがインストールされていることを確認します。存在しない場合は、次のいずれかをインストールするように求められます。</span><span class="sxs-lookup"><span data-stu-id="97df6-117">The wizard checks the system to ensure that all prerequisite software is installed and will prompt you to install any of the following, if missing:</span></span>

    -   <span data-ttu-id="97df6-118">Microsoft VisualC + + 2005SP1 再頒布可能パッケージ (x86)</span><span class="sxs-lookup"><span data-stu-id="97df6-118">Microsoft VisualC++2005SP1 Redistributable Package (x86)</span></span>

    -   <span data-ttu-id="97df6-119">Microsoft Core XML サービス (MSXML) 6.0 SP1 (x86)</span><span class="sxs-lookup"><span data-stu-id="97df6-119">Microsoft Core XML Services (MSXML)6.0SP1 (x86)</span></span>

    -   <span data-ttu-id="97df6-120">Microsoft アプリケーションエラー報告</span><span class="sxs-lookup"><span data-stu-id="97df6-120">Microsoft Application Error Reporting</span></span>

    <span data-ttu-id="97df6-121">**注** バージョン4.6 以降では、ウィザードによって次のソフトウェアの前提条件もインストールされます。</span><span class="sxs-lookup"><span data-stu-id="97df6-121">**Note** For version4.6 and higher, the wizard will also install the following software prerequisite:</span></span>

    -   <span data-ttu-id="97df6-122">Microsoft VisualC + + 2008SP1 再頒布可能パッケージ (x86)</span><span class="sxs-lookup"><span data-stu-id="97df6-122">Microsoft VisualC++2008SP1 Redistributable Package (x86)</span></span>

     

5.  <span data-ttu-id="97df6-123">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97df6-123">Click **Install**.</span></span> <span data-ttu-id="97df6-124">インストールの進行状況が表示され、状態が [**保留中**] から [**インストール**中] に変わります。</span><span class="sxs-lookup"><span data-stu-id="97df6-124">Installation progress is displayed, and the status changes from **Pending** to **Installing**.</span></span> <span data-ttu-id="97df6-125">各手順が正常に完了すると、インストールの状態が**成功**に変わります。</span><span class="sxs-lookup"><span data-stu-id="97df6-125">Installation status changes to **Succeeded** as each step is completed successfully.</span></span>

6.  <span data-ttu-id="97df6-126">[ **Application Virtualization Desktop Client** ] ダイアログが表示され、古いバージョンのクライアントがコンピューターで検出されたことを示すメッセージが表示されたら、[**次**へ] をクリックして新しいバージョンにアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="97df6-126">When the **Application Virtualization Desktop Client** dialog appears and displays a message stating that an older version of the client has been found on the computer, click **Next** to upgrade to the new version.</span></span>

7.  <span data-ttu-id="97df6-127">**ライセンス契約**の画面が表示されたら、ライセンス契約を読み、同意した場合は、[**使用許諾契約書に同意**します] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97df6-127">When the **License Agreement** screen is displayed, read the license agreement, and if you agree, click **I accept the terms in the license agreement**, and then click **Next**.</span></span>

8.  <span data-ttu-id="97df6-128">InstallShield ウィザードで [**プログラムをアップグレードする準備ができ**ました] ダイアログ画面が表示されたら、[**アップグレード**] をクリックしてアップグレードを開始します。</span><span class="sxs-lookup"><span data-stu-id="97df6-128">When the InstallShield Wizard displays the **Ready to Upgrade the Program** dialog screen, click **Upgrade** to begin the upgrade.</span></span> <span data-ttu-id="97df6-129">次の画面は、クライアントがインストールされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="97df6-129">The next screen indicates that the client is being installed.</span></span>

    <span data-ttu-id="97df6-130">**警告** 手順1でクライアントプログラムを終了していない場合は、[**使用中のファイル] の**警告が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="97df6-130">**Warning** If you did not shut down the client program in step 1, you might see a **Files In Use** warning displayed.</span></span> <span data-ttu-id="97df6-131">この問題が発生した場合は、デスクトップ通知領域に表示されている App-v クライアントのアイコンを右クリックし、[**終了**] を選択して、既存のクライアントをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="97df6-131">If this happens, right-click the App-V Client icon displayed in the desktop notification area and select **Exit** to shut down the existing client.</span></span> <span data-ttu-id="97df6-132">次に、[**再試行**] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="97df6-132">Then click **Retry** to continue.</span></span>

     

9.  <span data-ttu-id="97df6-133">インストールが正常に完了すると、コンピューターを再起動するように求められます。</span><span class="sxs-lookup"><span data-stu-id="97df6-133">When the installation completes successfully, you will be prompted to restart the computer.</span></span> <span data-ttu-id="97df6-134">インストールを完了するには、コンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97df6-134">You need to restart the computer to complete the installation.</span></span>

    <span data-ttu-id="97df6-135">**注意** 何らかの理由でアップグレードが失敗した場合は、もう一度アップグレードを試みる前にコンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97df6-135">**Caution** If the upgrade fails for any reason, you will need to restart the computer before attempting the upgrade again.</span></span>

     

**<span data-ttu-id="97df6-136">コマンドラインを使用してアプリケーションの仮想化クライアントをアップグレードするには</span><span class="sxs-lookup"><span data-stu-id="97df6-136">To upgrade the Application Virtualization Client by Using the Command Line</span></span>**

1.  <span data-ttu-id="97df6-137">setup.msi プログラムを使用して App-v クライアントをアップグレードする場合は、必要なすべての必須ソフトウェアがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="97df6-137">If upgrading the App-V client using the setup.msi program, ensure that any necessary prerequisite software has been installed.</span></span>

    **<span data-ttu-id="97df6-138">重要</span><span class="sxs-lookup"><span data-stu-id="97df6-138">Important</span></span>**  
    -   <span data-ttu-id="97df6-139">バージョン4.6 以降の App-v クライアントの場合、setup.msi プログラムはシステムをチェックし、必須のソフトウェアがインストールされていない場合はインストールを続行できないことを示すエラーメッセージが表示され、失敗します。</span><span class="sxs-lookup"><span data-stu-id="97df6-139">For version4.6 and later of the App-V client, the setup.msi program checks the system and will fail with an error message indicating that installation cannot continue if prerequisite software is not installed.</span></span>

    -   <span data-ttu-id="97df6-140">App-v バージョン4.6 の場合、コマンドラインパラメーターはアップグレード時に使用できず、無視されます。</span><span class="sxs-lookup"><span data-stu-id="97df6-140">For App-V version4.6, command-line parameters cannot be used during an upgrade and will be ignored.</span></span>

     

2.  <span data-ttu-id="97df6-141">次のコマンドラインの例では、setup.msi ファイルを使用して、App-v クライアントをアップグレードしています。</span><span class="sxs-lookup"><span data-stu-id="97df6-141">The following command-line example uses the setup.msi file to upgrade the App-V Client.</span></span> <span data-ttu-id="97df6-142">App-v デスクトップクライアントと、リモートデスクトップサービス (以前のターミナルサービス) 用の App-v クライアントのどちらをアップグレードするかによって、適切なクライアントインストーラープログラムを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97df6-142">You will need to use the correct client installer program depending on whether you are upgrading the App-V Desktop Client or the App-V Client for Remote Desktop Services (formerly Terminal Services).</span></span>

    **<span data-ttu-id="97df6-143">msiexec.exe/i "setup.msi"</span><span class="sxs-lookup"><span data-stu-id="97df6-143">msiexec.exe /i "setup.msi"</span></span>**

    <span data-ttu-id="97df6-144">**重要** 引用符は、値にスペースが含まれている場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="97df6-144">**Important** The quotation marks are required only when the value contains a space.</span></span> <span data-ttu-id="97df6-145">一貫性を保つため、前の例のすべてのインスタンスは引用符で囲まれています。</span><span class="sxs-lookup"><span data-stu-id="97df6-145">For consistency, all instances in the preceding example are shown as having quotation marks.</span></span>

     

**<span data-ttu-id="97df6-146">リモートデスクトップサービスのアプリケーション仮想化クライアントをアップグレードするには</span><span class="sxs-lookup"><span data-stu-id="97df6-146">To upgrade the Application Virtualization Client for Remote Desktop Services</span></span>**

1.  <span data-ttu-id="97df6-147">組織の標準ポリシーに従って、リモートデスクトップセッションホスト (RDSession Host) サーバー上でアプリケーションをインストールまたはアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="97df6-147">Follow your organization’s standard policies for installing or upgrading applications on the Remote Desktop Session Host (RDSession Host) server.</span></span> <span data-ttu-id="97df6-148">システムがファームの一部である場合は、サーバーファームから RDSession ホストを削除します。</span><span class="sxs-lookup"><span data-stu-id="97df6-148">If the system is part of a farm, remove the RDSession Host from the server farm.</span></span>

2.  <span data-ttu-id="97df6-149">リモートデスクトップサービス (旧ターミナルサービス) の App-v クライアントをアップグレードするには、RDSession ホストでクライアントを手動でアップグレードできないため、コマンドラインを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97df6-149">To upgrade the App-V Client for Remote Desktop Services (formerly Terminal Services), you must use the command line because you cannot upgrade the client manually on the RDSession Host.</span></span>

    <span data-ttu-id="97df6-150">**注** App-v バージョン4.6 以降では、コマンドラインを使用してクライアントをアップグレードするだけでなく、リモートデスクトップセッションも使うことができます。</span><span class="sxs-lookup"><span data-stu-id="97df6-150">**Note** In App-V version 4.6 and later, in addition to using the command line to upgrade the client, you can also use a Remote Desktop session.</span></span> <span data-ttu-id="97df6-151">リモートデスクトップセッションを開始するために特別なパラメーターを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="97df6-151">No special parameters are required to start the Remote Desktop session.</span></span>

     

3.  <span data-ttu-id="97df6-152">リモートデスクトップサービスのアップグレードが完了したら、クライアントを再起動して、RDSession ホストにログインします。</span><span class="sxs-lookup"><span data-stu-id="97df6-152">After the Client for Remote Desktop Services upgrade is complete, restart and log in to the RDSession Host.</span></span>

4.  <span data-ttu-id="97df6-153">システムを再起動したら、サーバーをサーバーファームに追加します。</span><span class="sxs-lookup"><span data-stu-id="97df6-153">After the system is restarted, add the server to the server farm.</span></span>

    <span data-ttu-id="97df6-154">**注意** 何らかの理由でアップグレードが失敗した場合は、もう一度アップグレードを試みる前にコンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97df6-154">**Caution** If the upgrade fails for any reason, you will need to restart the computer before attempting the upgrade again.</span></span>

     

## <span data-ttu-id="97df6-155">関連トピック</span><span class="sxs-lookup"><span data-stu-id="97df6-155">Related topics</span></span>


[<span data-ttu-id="97df6-156">Application Virtualization の展開およびアップグレードに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="97df6-156">Application Virtualization Deployment and Upgrade Considerations</span></span>](application-virtualization-deployment-and-upgrade-considerations.md)

 

 





