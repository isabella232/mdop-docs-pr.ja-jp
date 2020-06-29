---
title: App-V 5.1 のリリース ノート
description: App-V 5.1 のリリース ノート
author: dansimp
ms.assetid: 62c5be3b-0a46-4512-93ed-97c23184f343
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 09/26/2016
ms.openlocfilehash: 7437a16bc10b21bb15b0f8307c2711177e78cb72
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813307"
---
# <span data-ttu-id="0d603-103">App-V 5.1 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="0d603-103">Release Notes for App-V 5.1</span></span>


<span data-ttu-id="0d603-104">Microsoft Application Virtualization (App-v) 5.1 の既知の問題を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="0d603-104">The following are known issues in Microsoft Application Virtualization (App-V) 5.1.</span></span>

## <span data-ttu-id="0d603-105">Windows 10 で App-v 5.0 SP3 Management Server と App-v 5.1 クライアントの間での公開更新中にエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="0d603-105">Error occurs during publishing refresh between App-V 5.0 SP3 Management Server and App-V 5.1 Client on Windows 10</span></span>


<span data-ttu-id="0d603-106">アプリ-V 5.0 SP3 management サーバーから Windows 10 の App-v 5.1 クライアントにパッケージを同期すると、公開の更新中にエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="0d603-106">An error is generated during publishing refresh when synchronizing packages from the App-V 5.0 SP3 management server to an App-V 5.1 client on Windows 10 .</span></span> <span data-ttu-id="0d603-107">このエラーは、発行 URL で指定された Windows 10 オペレーティングシステムがアプリ-V 5.0 SP3 サーバーによって認識されないために発生します。</span><span class="sxs-lookup"><span data-stu-id="0d603-107">This error occurs because the App-V 5.0 SP3 server does not understand the Windows 10 operating system that is specified in the publishing URL.</span></span> <span data-ttu-id="0d603-108">この問題は、App-v 5.1 公開サーバーでは修正されていますが、backported のバージョンでは5.0 使用できません。</span><span class="sxs-lookup"><span data-stu-id="0d603-108">The issue is fixed for App-V 5.1 publishing server, but is not backported to versions of App-V 5.0 SP3 or earlier.</span></span>

<span data-ttu-id="0d603-109">**対応策**: App-v 5.0 management server を、Windows 10 クライアント用の App-v 5.1 management server にアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="0d603-109">**Workaround**: Upgrade the App-V 5.0 Management server to the App-V 5.1 Management server for Windows 10 Clients.</span></span>

## <span data-ttu-id="0d603-110">カスタム構成は、グローバルに公開されるパッケージ (app-v 5.1 サーバーを使用して設定されている場合) には適用されません。</span><span class="sxs-lookup"><span data-stu-id="0d603-110">Custom configurations do not get applied for packages that will be published globally if they are set using the App-V 5.1 Server</span></span>


<span data-ttu-id="0d603-111">マシンアカウントが含まれている広告グループにパッケージを割り当て、そのグループにカスタム構成を適用する場合は、カスタム構成はこれらのコンピューターに適用されません。</span><span class="sxs-lookup"><span data-stu-id="0d603-111">If you assign a package to an AD group that contains machine accounts and apply a custom configuration to that group using the App-V Server, the custom configuration will not be applied to those machines.</span></span> <span data-ttu-id="0d603-112">App-v 5.1 クライアントは、コンピューターアカウントに割り当てられているパッケージをグローバルに公開します。</span><span class="sxs-lookup"><span data-stu-id="0d603-112">The App-V 5.1 Client will publish packages assigned to a machine account globally.</span></span> <span data-ttu-id="0d603-113">ただし、各ユーザーのプロファイルにユーザーごとのカスタム構成ファイルが格納されます。</span><span class="sxs-lookup"><span data-stu-id="0d603-113">However, it stores custom configuration files per user in each user’s profile.</span></span> <span data-ttu-id="0d603-114">グローバルに公開されたパッケージには、このカスタム構成へのアクセス権がありません。</span><span class="sxs-lookup"><span data-stu-id="0d603-114">Globally published packages will not have access to this custom configuration.</span></span>

<span data-ttu-id="0d603-115">**回避策**: 次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0d603-115">**Workaround**: Do one of the following:</span></span>

-   <span data-ttu-id="0d603-116">ユーザーアカウントのみを含むグループにパッケージを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0d603-116">Assign the package to groups containing only user accounts.</span></span> <span data-ttu-id="0d603-117">これにより、パッケージのカスタム構成が各ユーザーのプロファイルに保存され、適切に適用されるようになります。</span><span class="sxs-lookup"><span data-stu-id="0d603-117">This will ensure that the package’s custom configuration will be stored in each user’s profile and will be applied correctly.</span></span>

-   <span data-ttu-id="0d603-118">カスタム展開構成ファイルを作成し、– DynamicDeploymentConfiguration パラメーターを指定して AppvClientPackage コマンドレットを使用し、クライアントのパッケージに適用します。</span><span class="sxs-lookup"><span data-stu-id="0d603-118">Create a custom deployment configuration file and apply it to the package on the client using the Add-AppvClientPackage cmdlet with the –DynamicDeploymentConfiguration parameter.</span></span> <span data-ttu-id="0d603-119">詳細については[、「app-v 5.1 の動的構成につい](about-app-v-51-dynamic-configuration.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d603-119">See [About App-V 5.1 Dynamic Configuration](about-app-v-51-dynamic-configuration.md) for more information.</span></span>

-   <span data-ttu-id="0d603-120">App-v 5.1 Sequencer を使用して、カスタム構成で新しいパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="0d603-120">Create a new package with the custom configuration using the App-V 5.1 Sequencer.</span></span>

## <span data-ttu-id="0d603-121">新しい App-v 5.1 Server をインストールした後に、サーバーファイルが削除されない</span><span class="sxs-lookup"><span data-stu-id="0d603-121">Server files not deleted after new App-V 5.1 Server installation</span></span>


<span data-ttu-id="0d603-122">App-v 5.0 SP1 サーバーをアンインストールして、App-v 5.1 サーバーをインストールした場合、インストールが失敗し、不適切なバージョンの管理サーバーがインストールされ、エラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d603-122">If you uninstall the App-V 5.0 SP1 Server and then install the App-V 5.1 Server, the installation fails, the wrong version of the Management server is installed, and an error message is returned.</span></span> <span data-ttu-id="0d603-123">この問題は、App-v 5.0 SP1 をアンインストールするときにサーバーファイルが削除されないために発生します。そのため、インストールプロセスでは、新しいインストールの代わりにアップグレードが行われます。</span><span class="sxs-lookup"><span data-stu-id="0d603-123">The issue occurs because the Server files are not being deleted when you uninstall App-V 5.0 SP1, so the installation process does an upgrade instead of a new installation.</span></span>

<span data-ttu-id="0d603-124">**回避策**: app-v 5.1 のインストールを開始する前に、このレジストリキーを削除します。</span><span class="sxs-lookup"><span data-stu-id="0d603-124">**Workaround**: Delete this registry key before you start installing App-V 5.1:</span></span>

<span data-ttu-id="0d603-125">[HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall] の下で、値データ "Microsoft Application Virtualization (App-v) Server" を使用して、DWORD 値 "DisplayName" を含むインストール GUID キーを見つけて削除します。</span><span class="sxs-lookup"><span data-stu-id="0d603-125">Under HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall, locate and delete the installation GUID key that contains the DWORD value "DisplayName" with value data "Microsoft Application Virtualization (App-V) Server".</span></span> <span data-ttu-id="0d603-126">これは、削除する必要があるキーのみです。</span><span class="sxs-lookup"><span data-stu-id="0d603-126">This is the only key that should be deleted.</span></span>

## <span data-ttu-id="0d603-127">手動で追加したファイルの種類の関連付けが正しく保存されない</span><span class="sxs-lookup"><span data-stu-id="0d603-127">File type associations added manually are not saved correctly</span></span>


<span data-ttu-id="0d603-128">アプリケーションパッケージに手動で追加したファイルの種類の関連付けは、アプリケーションアップグレードウィザードの終了時に [ショートカット] タブと [FTAs] タブを使って適切に保存されません。</span><span class="sxs-lookup"><span data-stu-id="0d603-128">File type associations added to an application package manually using the Shortcuts and FTAs tab at the end of the application upgrade wizard are not saved correctly.</span></span> <span data-ttu-id="0d603-129">保存されているパッケージをもう一度更新したときに、App-v クライアントまたは Sequencer にそれらのアプリを表示することはできません。</span><span class="sxs-lookup"><span data-stu-id="0d603-129">They will not be available to the App-V Client or to the Sequencer when updating the saved package again.</span></span>

<span data-ttu-id="0d603-130">**回避策**: ファイルの種類の関連付けを追加するには、変更するパッケージを開いて、更新ウィザードを実行します。</span><span class="sxs-lookup"><span data-stu-id="0d603-130">**Workaround**: To add a file type association, open the package for modification and run the update wizard.</span></span> <span data-ttu-id="0d603-131">インストール手順で、オペレーティングシステムを使用して新しいファイルの種類の関連付けを追加します。</span><span class="sxs-lookup"><span data-stu-id="0d603-131">During the Installation step, add the new file type association through the operating system.</span></span> <span data-ttu-id="0d603-132">Sequencer は、システムレジストリ内の新しい関連付けを検出し、それをパッケージの仮想レジストリに追加します。この場所でクライアントが利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0d603-132">The sequencer will detect the new association in the system registry and add it to the package’s virtual registry, where it will be available to the client.</span></span>

## <span data-ttu-id="0d603-133">AppLocker でも管理されているクライアントに共有コンテンツストア (SCS) モードでパッケージをストリーミングすると、追加のデータがローカルディスクに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="0d603-133">When streaming packages in Shared Content Store (SCS) mode to a client that is also managed with AppLocker, additional data is written to the local disk.</span></span>


<span data-ttu-id="0d603-134">クライアントのローカルディスクに書き込まれるデータの量を減らすために、アプリ-V 5.1 クライアントで SCS モードを有効にして、パッケージの内容をオンデマンドでストリーミングすることができます。</span><span class="sxs-lookup"><span data-stu-id="0d603-134">To decrease the amount of data written to a client’s local disk, you can enable SCS mode on the App-V 5.1 Client to stream the contents of a package on demand.</span></span> <span data-ttu-id="0d603-135">ただし、AppLocker がパッケージ内のアプリケーションを管理している場合、一部のデータはクライアントのローカルディスクに書き込まれ、それ以外の書き込みは行われません。</span><span class="sxs-lookup"><span data-stu-id="0d603-135">However, if AppLocker manages an application within the package, some data might be written to the client’s local disk that would not otherwise be written.</span></span>

<span data-ttu-id="0d603-136">**回避策**: なし</span><span class="sxs-lookup"><span data-stu-id="0d603-136">**Workaround**: None</span></span>

## <span data-ttu-id="0d603-137">管理コンソールの [パッケージの追加] ダイアログボックスで、Chrome または Firefox を使用している場合、[参照] ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="0d603-137">In the Management Console Add Package dialog box, the Browse button is not available when using Chrome or Firefox</span></span>


<span data-ttu-id="0d603-138">管理コンソールの [パッケージ] ページで、右下隅にある [**追加] または [アップグレード**] をクリックすると、[**パッケージの追加**] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d603-138">On the Packages page of the Management Console, if you click **Add or Upgrade** in the lower-right corner, the **Add Package** dialog box appears.</span></span> <span data-ttu-id="0d603-139">ブラウザーとして Chrome または Firefox を使用して管理コンソールにアクセスしている場合は、パッケージの場所を参照できません。</span><span class="sxs-lookup"><span data-stu-id="0d603-139">If you are accessing the Management Console using Chrome or Firefox as your browser, you will not be able to browse to the location of the package.</span></span>

<span data-ttu-id="0d603-140">**回避策**: パッケージへのパスを入力するか、コピーして、[**パッケージの追加**] 入力フィールドに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="0d603-140">**Workaround**: Type or copy and paste the path to the package into the **Add Package** input field.</span></span> <span data-ttu-id="0d603-141">管理コンソールにこのパスへのアクセス権がある場合は、パッケージを追加できます。</span><span class="sxs-lookup"><span data-stu-id="0d603-141">If the Management Console has access to this path, you will be able to add the package.</span></span> <span data-ttu-id="0d603-142">パッケージがネットワーク共有上にある場合は、次の手順に従って、エクスプローラーを使用して場所を参照できます。</span><span class="sxs-lookup"><span data-stu-id="0d603-142">If the package is on a network share, you can browse to the location using File Explorer by doing these steps:</span></span>

1.  <span data-ttu-id="0d603-143">**Shift**キーを押しながらパッケージファイルを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="0d603-143">While pressing **Shift**, right-click on the package file</span></span>

2.  <span data-ttu-id="0d603-144">[**パスとしてコピー** ] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="0d603-144">Select **Copy as path**</span></span>

3.  <span data-ttu-id="0d603-145">[**パッケージの追加**] ダイアログボックスの入力フィールドにパスを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="0d603-145">Paste the path into the **Add Package** dialog box input field</span></span>

## <a href="" id="upgrading-app-v-management-server-to-5-1-sometimes-fails-with-the-message--a-database-error-occurred-"></a><span data-ttu-id="0d603-146">App-v 管理サーバーを5.1 にアップグレードすると、"データベースエラーが発生しました" というメッセージが表示される場合がある</span><span class="sxs-lookup"><span data-stu-id="0d603-146">Upgrading App-V Management Server to 5.1 sometimes fails with the message “A database error occurred”</span></span>


<span data-ttu-id="0d603-147">App-v 5.0 SP1 Management Server をインストールしてから、複数の接続グループが構成されて有効になっているときに、App-v 5.1 サーバーにアップグレードしようとすると、次のエラーが表示されます。 "データベースエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="0d603-147">If you install the App-V 5.0 SP1 Management Server, and then try to upgrade to App-V 5.1 Server when multiple connection groups are configured and enabled, the following error is displayed: “A database error occurred.</span></span> <span data-ttu-id="0d603-148">理由: ' 無効な列名 ' PackageOptional '。</span><span class="sxs-lookup"><span data-stu-id="0d603-148">Reason: 'Invalid column name 'PackageOptional'.</span></span> <span data-ttu-id="0d603-149">列名 ' VersionOptional "が無効です。</span><span class="sxs-lookup"><span data-stu-id="0d603-149">Invalid column name 'VersionOptional'.”</span></span>

<span data-ttu-id="0d603-150">**回避策**: SQL データベースで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0d603-150">**Workaround**: Run this command on your SQL database:</span></span>

`ALTER TABLE AppVManagement.dbo.PackageGroupMembers ADD PackageOptional bit NOT NULL DEFAULT 0, VersionOptional bit NOT NULL DEFAULT 0`

<span data-ttu-id="0d603-151">ここで、"AppVManagement" はデータベースの名前です。</span><span class="sxs-lookup"><span data-stu-id="0d603-151">where “AppVManagement” is the name of the database.</span></span>

## <span data-ttu-id="0d603-152">省略可能なパッケージを追加または削除すると、ユーザーによって公開された接続グループでパッケージを開くことができない</span><span class="sxs-lookup"><span data-stu-id="0d603-152">Users cannot open a package in a user-published connection group if you add or remove an optional package</span></span>


<span data-ttu-id="0d603-153">RDS クライアントを実行している環境、またはコンピューターに複数のユーザーが同時に接続している環境では、ログインしたユーザーは、オプションのパッケージが接続グループに追加または削除された場合に、ユーザーによって公開された接続グループ内のパッケージのアプリケーションを開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="0d603-153">In environments that are running the RDS Client or that have multiple concurrent users per computer, logged-in users cannot open applications in packages that are in a user-published connection group if an optional package is added to or removed from the connection group.</span></span>

<span data-ttu-id="0d603-154">**回避策**: ユーザーにログアウトしてから、もう一度ログインします。</span><span class="sxs-lookup"><span data-stu-id="0d603-154">**Workaround**: Have users log out and then log back in.</span></span>

## <span data-ttu-id="0d603-155">接続グループがユーザーに対してのみ公開されているときに、誤ってエラーメッセージが表示される</span><span class="sxs-lookup"><span data-stu-id="0d603-155">Error message is erroneously displayed when the connection group is published only to the user</span></span>


<span data-ttu-id="0d603-156">AppvClientConnectionGroup を実行すると、接続グループがユーザーに対してのみ公開されている場合でも、次のエラーが表示されます。 "内部アプリ-V 統合エラー: パッケージは、ユーザーに対して統合されていません。"</span><span class="sxs-lookup"><span data-stu-id="0d603-156">When you run Repair-AppvClientConnectionGroup, the following error is displayed, even when the connection group is published only to the user: “Internal App-V Integration error: Package not integrated for the user.</span></span> <span data-ttu-id="0d603-157">パッケージがコンピューターに追加され、ユーザーに公開されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0d603-157">Please ensure that the package is added to the machine and published to the user.”</span></span>

<span data-ttu-id="0d603-158">**回避策**: 次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0d603-158">**Workaround**: Do one of the following:</span></span>

-   <span data-ttu-id="0d603-159">接続グループ内のすべてのパッケージを公開します。</span><span class="sxs-lookup"><span data-stu-id="0d603-159">Publish all packages in a connection group.</span></span>

    <span data-ttu-id="0d603-160">この問題は、修復される接続グループに、存在しないか、ユーザーが使用できない (つまり、グローバルでもユーザーに公開されていない) パッケージが含まれている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="0d603-160">The problem arises when the connection group being repaired has packages that are missing or not available to the user (that is, not published globally or to the user).</span></span> <span data-ttu-id="0d603-161">ただし、すべての接続グループのパッケージが利用できる場合は、すべてのパッケージが公開されていることを確認して、修復を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0d603-161">However, the repair will work if all of the connection group’s packages are available, so ensure that all packages are published.</span></span>

-   <span data-ttu-id="0d603-162">Repair-AppvClientConnectionGroup コマンドではなく、AppvClientPackage コマンドを使用して、パッケージを個別に修復します。</span><span class="sxs-lookup"><span data-stu-id="0d603-162">Repair packages individually using the Repair-AppvClientPackage command rather than the Repair-AppvClientConnectionGroup command.</span></span>

    <span data-ttu-id="0d603-163">ユーザーが利用できるパッケージを特定し、各パッケージで AppvClientPackage コマンドを1回実行します。</span><span class="sxs-lookup"><span data-stu-id="0d603-163">Determine which packages are available to users and then run the Repair-AppvClientPackage command once for each package.</span></span> <span data-ttu-id="0d603-164">PowerShell コマンドレットを使用して、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0d603-164">Use PowerShell cmdlets to do the following:</span></span>

    1.  <span data-ttu-id="0d603-165">接続グループ内のすべてのパッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="0d603-165">Get all the packages in a connection group.</span></span>

    2.  <span data-ttu-id="0d603-166">各パッケージが現在公開されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0d603-166">Check to see if each package is currently published.</span></span>

    3.  <span data-ttu-id="0d603-167">パッケージが現在公開されている場合は、そのパッケージで AppvClientPackage を実行します。</span><span class="sxs-lookup"><span data-stu-id="0d603-167">If the package is currently published, run Repair-AppvClientPackage on that package.</span></span>

## <span data-ttu-id="0d603-168">Sequencer で正しく表示されないアイコン</span><span class="sxs-lookup"><span data-stu-id="0d603-168">Icons not displayed properly in Sequencer</span></span>


<span data-ttu-id="0d603-169">アプリでパッケージを変更すると、[ショートカット] タブと [ファイルの種類の関連付け] タブのアイコンが正しく表示されません。</span><span class="sxs-lookup"><span data-stu-id="0d603-169">Icons in the Shortcuts and File Type Associations tab are not displayed correctly when modifying a package in the App-V Sequencer.</span></span> <span data-ttu-id="0d603-170">この問題は、アイコンのサイズが16x16 または32x32 ではない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="0d603-170">This problem occurs when the size of the icons are not 16x16 or 32x32.</span></span>

<span data-ttu-id="0d603-171">**回避策**: アイコンの16x16 または32x32 のアイコンのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="0d603-171">**Workaround**: Only use icons that are 16x16 or 32x32.</span></span>

## <span data-ttu-id="0d603-172">InsertVersionInfo スクリプトが管理データベースに必要なくなりました</span><span class="sxs-lookup"><span data-stu-id="0d603-172">InsertVersionInfo.sql script no longer required for the Management Database</span></span>


<span data-ttu-id="0d603-173">InsertVersionInfo スクリプトは、アプリ-V 5.0 SP3 より後のバージョンの App-v 管理データベースでは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="0d603-173">The InsertVersionInfo.sql script is not required for versions of the App-V management database later than App-V 5.0 SP3.</span></span>

<span data-ttu-id="0d603-174">アクセス許可の sql スクリプトは、[サポート技術情報の記事 3031340](https://support.microsoft.com/kb/3031340)の**手順 2**に従って更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0d603-174">The Permissions.sql script should be updated according to **Step 2** in [KB article 3031340](https://support.microsoft.com/kb/3031340).</span></span>

<span data-ttu-id="0d603-175">**重要** 
App-v 5.0 SP3 より後のバージョンの App-v では、**手順 1**は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="0d603-175">**Important**
**Step 1** is not required for versions of App-V later than App-V 5.0 SP3.</span></span>

 

## <span data-ttu-id="0d603-176">Microsoft Visual Studio 2012 はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="0d603-176">Microsoft Visual Studio 2012 not supported</span></span>


<span data-ttu-id="0d603-177">App-v 5.1 は Visual Studio 2012 をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="0d603-177">App-V 5.1 does not support Visual Studio 2012.</span></span>

<span data-ttu-id="0d603-178">**回避策**: なし</span><span class="sxs-lookup"><span data-stu-id="0d603-178">**Workaround**: None</span></span>

## <span data-ttu-id="0d603-179">アプリケーションファイル名の制限 (app-v)</span><span class="sxs-lookup"><span data-stu-id="0d603-179">Application filename restrictions for App-V 5.x Sequencer</span></span>


<span data-ttu-id="0d603-180">App-v Sequencer は、"CO_ x" と一致するファイル名を使ったアプリケーションのシーケンスを行うことはできません &lt; &gt; 。 x は任意の数字です。</span><span class="sxs-lookup"><span data-stu-id="0d603-180">The App-V 5.x Sequencer cannot sequence applications with filenames matching "CO_&lt;x&gt;" where x is any numeral.</span></span> <span data-ttu-id="0d603-181">エラー0x8007139F が生成されます。</span><span class="sxs-lookup"><span data-stu-id="0d603-181">Error 0x8007139F will be generated.</span></span>

<span data-ttu-id="0d603-182">**回避策**: 別のファイル名を使用してください。</span><span class="sxs-lookup"><span data-stu-id="0d603-182">**Workaround**: Use a different filename</span></span>

## <span data-ttu-id="0d603-183">パッケージのマウント時に "ファイルが見つかりません" というエラーが断続的に表示される</span><span class="sxs-lookup"><span data-stu-id="0d603-183">Intermittent "File Not Found" error when Mounting a Package</span></span>


<span data-ttu-id="0d603-184">パッケージをマウントするときに、"ファイルが見つかりませんでした" (0x80070002) エラーが生成されることがあります。</span><span class="sxs-lookup"><span data-stu-id="0d603-184">Occasionally when mounting a package, a "File Not Found" (0x80070002) error is generated.</span></span> <span data-ttu-id="0d603-185">通常、このエラーは、App-v パッケージ内のフォルダーに多くのファイル (20K など) が含まれている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="0d603-185">Typically, this occurs when a folder in an App-V package contains many files ( i.e. 20K or more).</span></span> <span data-ttu-id="0d603-186">これにより、ストリーミングに予想以上に時間がかかり、"ファイルが見つかりません" というエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="0d603-186">This can cause streaming to take longer than expected and to time out which generates the "File Not Found" error.</span></span>

<span data-ttu-id="0d603-187">**回避策**: HF06 以降では、新しいレジストリキーが導入され、この期間を延長できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0d603-187">**Workaround**: Starting with HF06, a new registry key has been introduced to enable extending this time-out period.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="80%" />
</colgroup>
<tbody>
<tr>
<td align="left"><span data-ttu-id="0d603-188">パス</span><span class="sxs-lookup"><span data-stu-id="0d603-188">Path</span></span></td>
<td align="left"><span data-ttu-id="0d603-189">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\AppV\Client\Streaming</span><span class="sxs-lookup"><span data-stu-id="0d603-189">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\Streaming</span></span></td>
</tr>
<tr>
<td align="left"><span data-ttu-id="0d603-190">設定</span><span class="sxs-lookup"><span data-stu-id="0d603-190">Setting</span></span></td>
<td align="left"><span data-ttu-id="0d603-191">StreamResponseWaitTimeout</span><span class="sxs-lookup"><span data-stu-id="0d603-191">StreamResponseWaitTimeout</span></span></td>
</tr>
<tr>
<td align="left"><span data-ttu-id="0d603-192">DataType</span><span class="sxs-lookup"><span data-stu-id="0d603-192">DataType</span></span></td>
<td align="left"><span data-ttu-id="0d603-193">DWORD</span><span class="sxs-lookup"><span data-stu-id="0d603-193">DWORD</span></span></td>
</tr>
<tr>
<td align="left"><span data-ttu-id="0d603-194">数量</span><span class="sxs-lookup"><span data-stu-id="0d603-194">Units</span></span></td>
<td align="left"><span data-ttu-id="0d603-195">間隔</span><span class="sxs-lookup"><span data-stu-id="0d603-195">Seconds</span></span></td>
</tr>
<tr>
<td align="left"><span data-ttu-id="0d603-196">既定値</span><span class="sxs-lookup"><span data-stu-id="0d603-196">Default</span></span></td>
<td align="left"><span data-ttu-id="0d603-197">個</span><span class="sxs-lookup"><span data-stu-id="0d603-197">5</span></span><br />
<strong><span data-ttu-id="0d603-198">注 </strong> : この値は、レジストリキーが定義されていない場合、または値 = 5 が指定されている場合に既定になり &lt; ます。</span><span class="sxs-lookup"><span data-stu-id="0d603-198">Note</strong>: this value is the default if the registry key is not defined or a value &lt;=5 is specified.</span></span>
</td>
</tr>
</tbody>
</table>






## <span data-ttu-id="0d603-199">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0d603-199">Related topics</span></span>


[<span data-ttu-id="0d603-200">App-V 5.1 について</span><span class="sxs-lookup"><span data-stu-id="0d603-200">About App-V 5.1</span></span>](about-app-v-51.md)

 

 





