---
title: Application Virtualization Client のトラブルシューティング情報
description: Application Virtualization Client のトラブルシューティング情報
author: dansimp
ms.assetid: 260a8dad-847f-4ec0-b7dd-6e6bc52017ed
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4c2ab332f5f3b7f8cdc40f6d35e8712d55028a60
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815194"
---
# <span data-ttu-id="6d3bc-103">Application Virtualization Client のトラブルシューティング情報</span><span class="sxs-lookup"><span data-stu-id="6d3bc-103">Troubleshooting Information for the Application Virtualization Client</span></span>


<span data-ttu-id="6d3bc-104">このトピックでは、Application Virtualization (App-v) クライアントのさまざまな問題のトラブルシューティングに使用できる情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-104">This topic includes information that you can use to troubleshoot various issues on the Application Virtualization (App-V) Client.</span></span>

## <span data-ttu-id="6d3bc-105">公開の更新に時間がかかる</span><span class="sxs-lookup"><span data-stu-id="6d3bc-105">Publishing Refresh Is Very Slow</span></span>


<span data-ttu-id="6d3bc-106">特定のコンピューターでの公開更新に予想以上に時間がかかる場合、およびクライアントが**IconSourceRoot**設定を使用するように構成されている場合は、 **IconSourceRoot**に無効な URL が含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-106">If publishing refresh on a specific computer takes much longer than expected and if the client is configured to use the **IconSourceRoot** setting, determine whether **IconSourceRoot** contains a nonvalid URL.</span></span> <span data-ttu-id="6d3bc-107">無効な URL を指定すると、更新を公開するときに非常に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-107">A nonvalid URL will cause very long delays during publishing refresh.</span></span>

## <span data-ttu-id="6d3bc-108">ユーザーがサーバーに接続して、切断された操作モードに移行できない</span><span class="sxs-lookup"><span data-stu-id="6d3bc-108">Users Cannot Connect to the Server and Go into Disconnected Operations Mode</span></span>


<span data-ttu-id="6d3bc-109">RTSPS プロトコルで構成されている App-v Management Server を使用している場合、ユーザーが接続できず、切断された操作モードに移行した場合は、サーバー上で使用されている証明書が有効であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-109">When you are using an App-V Management Server configured with the RTSPS protocol, if the users are unable to connect and they go into disconnected operations mode, determine whether the certificate that is being used on the server is valid.</span></span> <span data-ttu-id="6d3bc-110">無効な証明書を使うと、ユーザーは接続できなくなり、切断された操作モードになります。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-110">A nonvalid certificate will prevent users from connecting and will cause them to go into disconnected operations mode.</span></span>

## <a href="" id="users-experience-slow-performance-when-applications-are-not-fully-cached-"></a><span data-ttu-id="6d3bc-111">アプリケーションが完全にキャッシュされていないと、ユーザーによるパフォーマンスの低下が発生する</span><span class="sxs-lookup"><span data-stu-id="6d3bc-111">Users Experience Slow Performance When Applications Are Not Fully Cached</span></span>


<span data-ttu-id="6d3bc-112">アプリケーションが完全にキャッシュされていない場合、ユーザーがアプリケーションを起動または使用したときに、一時的に遅く、または断続的なパフォーマンスが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-112">When applications are not fully cached, users might occasionally experience temporary slow or intermittent performance when they start or use the application.</span></span> <span data-ttu-id="6d3bc-113">たとえば、App-v クライアントがアプリケーションの自動読み込みプロセス中、またはシーケンス外の要求が処理されているときに、いくつかの原因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-113">There are several possible reasons this can occur—for example, when the App-V Client is in the process of auto-loading an application or when an Out Of Sequence request is being processed.</span></span> <span data-ttu-id="6d3bc-114">アプリケーションが完全にキャッシュされると、このような問題は発生しなくなります。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-114">When the applications are fully cached, these problems will no longer occur.</span></span>

## <a href="" id="error-displayed-after-an-update-is-removed-"></a><span data-ttu-id="6d3bc-115">更新プログラムが削除された後に表示されるエラー</span><span class="sxs-lookup"><span data-stu-id="6d3bc-115">Error Displayed After an Update Is Removed</span></span>


<span data-ttu-id="6d3bc-116">次に示すように、適切な Windows Installer 3.1 コマンド形式を使用して、App-v クライアントから更新プログラムを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-116">You must use the correct Windows Installer 3.1 command format to remove an update from the App-V Client, as follows:</span></span>

`Msiexec /I {F82584A0-D706-4D2D-9BC1-7E6D8BE3BB0F} MSIPATCHREMOVE={BE3DD018-9A1F-40FD-9538-C0A995CBD254} /qb /l*v "Uninstall.log"`

<span data-ttu-id="6d3bc-117">以前のコマンド形式を使用すると、 `msiexec /package <GUID> /uninstall <GUID>` エラー 6003 "Application Virtualization client を起動できませんでした" が発生します。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-117">Using the older command format `msiexec /package <GUID> /uninstall <GUID>` will cause error 6003 "Application Virtualization client could not be started".</span></span>

## <span data-ttu-id="6d3bc-118">エラーコード 0A-0000E01E は、アプリケーションを起動しようとすると発生します。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-118">Error Code 0A-0000E01E Occurs When You Try to Start an Application</span></span>


<span data-ttu-id="6d3bc-119">エラーコード 0A-0000E01E は、シーケンス付きのアプリケーションパッケージが破損している可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-119">Error code 0A-0000E01E indicates that the sequenced application package might be corrupt.</span></span> <span data-ttu-id="6d3bc-120">解決策として、パッケージの順序を再処理します。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-120">The solution is to resequence the package.</span></span>

## <span data-ttu-id="6d3bc-121">ユーザーは、Q: ドライブで作成されたファイルにアクセスできません</span><span class="sxs-lookup"><span data-stu-id="6d3bc-121">Users Cannot Access Files They Have Created on the Q: Drive</span></span>


<span data-ttu-id="6d3bc-122">ユーザーが**Q:** ドライブにファイルを保存した場合、ドライブへの読み取り権限がないため、ファイルを取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-122">If users save files to the **Q:** drive, they cannot retrieve them because they do not have read rights to the drive.</span></span> <span data-ttu-id="6d3bc-123">ユーザーは、ファイルを**Q:** ドライブに保存しないでください。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-123">Users should not save files to the **Q:** drive.</span></span>

## <span data-ttu-id="6d3bc-124">ユーザーに1D1 エラーが表示される</span><span class="sxs-lookup"><span data-stu-id="6d3bc-124">User Is Prompted with a 1D1 Error</span></span>


<span data-ttu-id="6d3bc-125">オープンソフトウェア記述子 (OSD) ファイルでファイルのストリーミング URL が正しく設定されていない場合、App-v クライアントは "ファイルが見つかりません" エラーではなく1d1 エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-125">When the file streaming URL is incorrectly set in the Open Software Descriptor (OSD) file, the App-V Client returns a 1d1 error instead of a “file not found” error.</span></span> <span data-ttu-id="6d3bc-126">このエラーは、アプリケーションの開始に失敗し、ユーザーが切断された操作モードになっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-126">This error indicates that the application start failed and the user has been forced into disconnected operations mode.</span></span> <span data-ttu-id="6d3bc-127">ファイルストリーミング URL を修正します。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-127">Correct the file streaming URL.</span></span>

## <span data-ttu-id="6d3bc-128">一部のアプリケーションに関連付けられた無効なアイコン</span><span class="sxs-lookup"><span data-stu-id="6d3bc-128">Incorrect Icons Associated with Some Applications</span></span>


<span data-ttu-id="6d3bc-129">発行操作でアイコンが使用される場合、最初に、アプリでは、元のソースパスが発行操作に指定されたアイコンのパスと一致する項目のアイコンキャッシュを調べて、アイコンのキャッシュされたコピーが既に存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-129">When an icon is to be used in a publishing operation, the App-V Client first determines whether it already has a cached copy of the icon, by looking in the icon cache for an item whose original source path matches the path of the icon given to the publishing operation.</span></span> <span data-ttu-id="6d3bc-130">App-v クライアントで一致が見つかった場合は、既にキャッシュされているアイコンが使用されます。それ以外の場合は、新しいアイコンがキャッシュにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-130">If the App-V Client finds a match, it will use the already-cached icon; otherwise, it will download the new icon into the cache.</span></span> <span data-ttu-id="6d3bc-131">アイコンのパスがスクラッチディレクトリの場合、または新しいアイコンやパッケージを再利用した場合、キャッシュ内の検索で、以前の操作で間違ったアイコンが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-131">If the path to the icon is a scratch directory or if it gets reused for new icons or packages, the lookup in the cache might pick the wrong icon from a previous operation.</span></span>

## <span data-ttu-id="6d3bc-132">アプリケーションを起動するときに資格情報の入力を求めるメッセージがユーザーに表示される</span><span class="sxs-lookup"><span data-stu-id="6d3bc-132">Users Are Prompted for Credentials When Starting an Application</span></span>


<span data-ttu-id="6d3bc-133">ユーザーが、アクセスが制限されている仮想アプリケーションを起動しようとすると、資格情報の入力を求めるメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-133">If a user attempts to start a virtual application to which the system administrator has restricted access, the user might be prompted to enter credentials.</span></span> <span data-ttu-id="6d3bc-134">ユーザーは、アプリケーションを起動するためのアクセス許可を持つアカウントのユーザー名とパスワードを入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-134">The user should type the user name and password for an account that has permission to launch the application and then press ENTER.</span></span>

## <span data-ttu-id="6d3bc-135">App-v クライアントをバージョン4.5 にアップグレードした後、公開の更新に失敗する</span><span class="sxs-lookup"><span data-stu-id="6d3bc-135">Publishing Refresh Fails After Upgrading the App-V Client to Version 4.5</span></span>


<span data-ttu-id="6d3bc-136">ユーザーデータディレクトリが以前は標準以外の場所 (%*AllUsersProfile*%\\Documents\\SoftGrid Client\\Users\\%*username*% に設定されていた場合、コンピューターの管理者権限を持っていないユーザーは、app-v クライアントがアップグレードされた後に、発行の更新に失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-136">If the user data directory was previously placed in a non-standard location (%*AllUsersProfile*%\\Documents\\SoftGrid Client\\Users\\%*username*%), users who do not have administrator privileges on the computer will find that publishing refresh fails after the App-V Client is upgraded.</span></span> <span data-ttu-id="6d3bc-137">アップグレード中、App-v クライアントのグローバルデータディレクトリとそのすべてのサブディレクトリは、管理者のみに限定されたアクセス権を持つように構成されています。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-137">During the upgrade, the App-V Client global data directory and all its subdirectories are configured with restricted access rights for administrators only.</span></span> <span data-ttu-id="6d3bc-138">この問題を回避するには、アップグレードする前にユーザーデータディレクトリを変更して、グローバルデータディレクトリのサブディレクトリにしないようにします。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-138">You can avoid this problem by changing the user data directory before upgrading so that it is not a subdirectory of the global data directory.</span></span>

## <span data-ttu-id="6d3bc-139">インストールに失敗した後、再起動が必要</span><span class="sxs-lookup"><span data-stu-id="6d3bc-139">Reboot Required After Install Failure</span></span>


<span data-ttu-id="6d3bc-140">クライアントのインストールが何らかの理由で失敗し、その後もクライアントをインストールしようとすると、エラー "sftplay failed、エラー = 1072 個" というエラーが表示されるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-140">If the client install fails for any reason and if subsequent attempts to install the client also fail, check the Windows Installer log to see whether it shows an error “sftplay failed, error=1072”.</span></span> <span data-ttu-id="6d3bc-141">その場合は、クライアントを再インストールする前に、コンピューターを再起動してください。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-141">If so, restart the computer before trying to install the client again.</span></span>

## <span data-ttu-id="6d3bc-142">破損した仮想アプリケーションの修復</span><span class="sxs-lookup"><span data-stu-id="6d3bc-142">Repairing a Corrupted Virtual Application</span></span>


<span data-ttu-id="6d3bc-143">何らかの理由で Windows インストーラーパッケージ (MSI) ファイルを使用してインストールされた仮想アプリケーションパッケージが破損した場合は、パッケージを再インストールします。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-143">If for any reason a virtual application package installed using a Windows Installer Package (MSI) file becomes corrupted, reinstall the package.</span></span> <span data-ttu-id="6d3bc-144">Windows インストーラーで利用できる Repair 機能によって、ユーザーのボリュームが更新されることはありません。</span><span class="sxs-lookup"><span data-stu-id="6d3bc-144">The Repair function available in the Windows Installer will not update the user volumes.</span></span>

## <span data-ttu-id="6d3bc-145">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6d3bc-145">Related topics</span></span>


[<span data-ttu-id="6d3bc-146">Application Virtualization Client リファレンス</span><span class="sxs-lookup"><span data-stu-id="6d3bc-146">Application Virtualization Client Reference</span></span>](application-virtualization-client-reference.md)

 

 





