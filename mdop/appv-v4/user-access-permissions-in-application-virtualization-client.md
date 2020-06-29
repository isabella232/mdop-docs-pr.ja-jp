---
title: Application Virtualization Client のユーザー アクセス許可
description: Application Virtualization Client のユーザー アクセス許可
author: dansimp
ms.assetid: 7459374c-810c-45e3-b205-fdd1f8514f80
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1083faffb48aa58a0ee0c81b58fae307e53548b8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815117"
---
# <span data-ttu-id="35301-103">Application Virtualization Client のユーザー アクセス許可</span><span class="sxs-lookup"><span data-stu-id="35301-103">User Access Permissions in Application Virtualization Client</span></span>


<span data-ttu-id="35301-104">[**プロパティ**] ダイアログボックスの [**アクセス許可**] タブで、アプリケーションの仮想化クライアントの管理コンソールで [**アプリケーションの仮想化**] ノードを右クリックするとアクセスできるため、管理者はさまざまなクライアント機能を使用するためのアクセス許可をユーザーに与えることができます。</span><span class="sxs-lookup"><span data-stu-id="35301-104">On the **Permissions** tab on the **Properties** dialog box, accessible by right-clicking the **Application Virtualization** node in the Application Virtualization Client Management Console, administrators can grant users permissions to use the various client functions.</span></span>

<span data-ttu-id="35301-105">**注** ユーザーの権限を変更する前に、権限の変更が、ユーザー権限を付与するための組織のガイドラインと一致していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="35301-105">**Note** Before changing users permissions, ensure that any permissions changes are consistent with the organization's guidelines for granting user permissions.</span></span>

 

<span data-ttu-id="35301-106">次の表では、ユーザーに付与できる権限について説明します。</span><span class="sxs-lookup"><span data-stu-id="35301-106">The following table lists and describes the permissions that can be granted to users.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="35301-107">権限名</span><span class="sxs-lookup"><span data-stu-id="35301-107">Permission Name</span></span></th>
<th align="left"><span data-ttu-id="35301-108">説明</span><span class="sxs-lookup"><span data-stu-id="35301-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="35301-109">アプリケーションの追加</span><span class="sxs-lookup"><span data-stu-id="35301-109">Add applications</span></span></p></td>
<td align="left"><p><span data-ttu-id="35301-110">新しいアプリケーションを登録するには、sfttray.exe、sftmime.exe または MMC を使用して、新しい OSD ファイルをクライアントに渡します。</span><span class="sxs-lookup"><span data-stu-id="35301-110">Register new applications by passing a new OSD file to the client by using sfttray.exe, sftmime.exe or the MMC.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="35301-111">ファイルシステムのキャッシュサイズを変更する</span><span class="sxs-lookup"><span data-stu-id="35301-111">Change file system cache size</span></span></p></td>
<td align="left"><p><span data-ttu-id="35301-112">ファイルシステムキャッシュのサイズを大きくします。</span><span class="sxs-lookup"><span data-stu-id="35301-112">Increase the size of the file system cache.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="35301-113">ファイルシステムドライブを変更する</span><span class="sxs-lookup"><span data-stu-id="35301-113">Change file system drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="35301-114">ファイルシステムの別の優先ドライブ文字を選択します。</span><span class="sxs-lookup"><span data-stu-id="35301-114">Select a different preferred drive letter for the file system.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="35301-115">ログ設定を変更する</span><span class="sxs-lookup"><span data-stu-id="35301-115">Change log settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="35301-116">クライアントログファイルのログレベルまたはログパスを変更します。</span><span class="sxs-lookup"><span data-stu-id="35301-116">Change the log level or the log path for the client log file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="35301-117">OSD ファイルの変更</span><span class="sxs-lookup"><span data-stu-id="35301-117">Change OSD files</span></span></p></td>
<td align="left"><p><span data-ttu-id="35301-118">登録されているアプリケーションの OSD ファイルを変更してクライアントに渡します。</span><span class="sxs-lookup"><span data-stu-id="35301-118">Modify OSD files for registered applications and pass them into the client.</span></span> <span data-ttu-id="35301-119">これは、公開の更新には影響しません。</span><span class="sxs-lookup"><span data-stu-id="35301-119">This does not affect publishing refresh.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="35301-120">アプリケーション設定をクリアする</span><span class="sxs-lookup"><span data-stu-id="35301-120">Clear application settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="35301-121">ファイルの種類、ショートカット、現在のユーザーの構成を削除します。</span><span class="sxs-lookup"><span data-stu-id="35301-121">Delete file types, shortcuts and any configurations for the current user.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="35301-122">アプリケーションを削除する</span><span class="sxs-lookup"><span data-stu-id="35301-122">Delete applications</span></span></p></td>
<td align="left"><p><span data-ttu-id="35301-123">コンピューター上のすべてのユーザーに対して、ファイルシステムと OSD キャッシュからアプリケーションへのすべての参照を削除します。</span><span class="sxs-lookup"><span data-stu-id="35301-123">Remove all references to an application from the file system and OSD cache for all users on the computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="35301-124">キャッシュにアプリケーションをインポートする</span><span class="sxs-lookup"><span data-stu-id="35301-124">Import applications into the cache</span></span></p></td>
<td align="left"><p><span data-ttu-id="35301-125">指定した SFT ファイルからファイルシステムキャッシュにアプリケーションデータを直接読み込みます。</span><span class="sxs-lookup"><span data-stu-id="35301-125">Load application data directly from a specified SFT file into the file system cache.</span></span> <span data-ttu-id="35301-126">これはすべてのユーザーに影響します。</span><span class="sxs-lookup"><span data-stu-id="35301-126">This affects all users.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="35301-127">キャッシュにアプリケーションを読み込む</span><span class="sxs-lookup"><span data-stu-id="35301-127">Load applications into the cache</span></span></p></td>
<td align="left"><p><span data-ttu-id="35301-128">アプリの SFT ファイルの読み込みを、構成されているソースから開始します。たとえば、App-v Streaming Server などです。</span><span class="sxs-lookup"><span data-stu-id="35301-128">Start a load of the SFT file for an application from the configured source, such as an App-V Streaming Server.</span></span> <span data-ttu-id="35301-129">これにより、コンピューター上のすべてのユーザーのアプリケーションが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="35301-129">This loads the application for all users on the computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="35301-130">キャッシュ内のアプリケーションのロックとロック解除</span><span class="sxs-lookup"><span data-stu-id="35301-130">Lock and unlock applications in the cache</span></span></p></td>
<td align="left"><p><span data-ttu-id="35301-131">ファイルシステムキャッシュからアプリケーションがアンロードされないようにします。</span><span class="sxs-lookup"><span data-stu-id="35301-131">Prevent or allow applications from being unloaded from the file system cache.</span></span> <span data-ttu-id="35301-132">これは、コンピューター上のすべてのユーザーに影響します。</span><span class="sxs-lookup"><span data-stu-id="35301-132">This affects all users on the computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="35301-133">ファイルの種類の関連付けを管理する</span><span class="sxs-lookup"><span data-stu-id="35301-133">Manage file type associations</span></span></p></td>
<td align="left"><p><span data-ttu-id="35301-134">ファイルの種類の関連付けは、現在のユーザーに対してのみ追加、変更、または削除します。</span><span class="sxs-lookup"><span data-stu-id="35301-134">Add, modify, or delete file type associations for the current user only.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="35301-135">公開の更新設定を管理する</span><span class="sxs-lookup"><span data-stu-id="35301-135">Manage publishing refresh settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="35301-136">コンピューター上のすべてのユーザーに対して公開の更新のタイミングを制御する設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="35301-136">Change settings that control the timing of publishing refreshes for all users on the computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="35301-137">公開サーバーを管理する</span><span class="sxs-lookup"><span data-stu-id="35301-137">Manage publishing servers</span></span></p></td>
<td align="left"><p><span data-ttu-id="35301-138">コンピューター上のすべてのユーザーの発行サーバーを追加、変更、または削除します。</span><span class="sxs-lookup"><span data-stu-id="35301-138">Add, modify, or delete publishing servers for all users on the computer.</span></span> <span data-ttu-id="35301-139">このアクセス許可には、公開の更新設定を管理するアクセス許可が暗黙的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="35301-139">This permission implicitly includes permission to manage publishing refresh settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="35301-140">公開ショートカット</span><span class="sxs-lookup"><span data-stu-id="35301-140">Publish shortcuts</span></span></p></td>
<td align="left"><p><span data-ttu-id="35301-141">登録されているアプリケーションへの新しいショートカットを作成します。</span><span class="sxs-lookup"><span data-stu-id="35301-141">Create new shortcuts to registered applications.</span></span> <span data-ttu-id="35301-142">ユーザーは、ローカルファイルシステムでファイルを作成する権限も持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="35301-142">The user must also have permission to create files in the local file system.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="35301-143">アプリケーションを修復する</span><span class="sxs-lookup"><span data-stu-id="35301-143">Repair applications</span></span></p></td>
<td align="left"><p><span data-ttu-id="35301-144">ショートカットやファイルの種類の関連付けを削除せずに、現在のユーザーのアプリケーション固有の構成を削除します。</span><span class="sxs-lookup"><span data-stu-id="35301-144">Remove application specific configurations for the current user without removing shortcuts or file type associations.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="35301-145">公開の更新を開始する</span><span class="sxs-lookup"><span data-stu-id="35301-145">Start a publishing refresh</span></span></p></td>
<td align="left"><p><span data-ttu-id="35301-146">現在のユーザーのスケジュールされていない公開の更新を開始します。</span><span class="sxs-lookup"><span data-stu-id="35301-146">Start an unscheduled publishing refresh for the current user.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="35301-147">オフラインモードの切り替え</span><span class="sxs-lookup"><span data-stu-id="35301-147">Toggle offline mode</span></span></p></td>
<td align="left"><p><span data-ttu-id="35301-148">すべてのユーザーについて、クライアント全体をオンラインからオフラインモードに変更します。</span><span class="sxs-lookup"><span data-stu-id="35301-148">Change the entire client from online to offline mode for all users.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="35301-149">キャッシュからアプリケーションをアンロードする</span><span class="sxs-lookup"><span data-stu-id="35301-149">Unload applications from the cache</span></span></p></td>
<td align="left"><p><span data-ttu-id="35301-150">ユーザー固有の設定、ショートカット、またはファイルの種類の関連付けを削除することなく、すべてのユーザーに対してファイルシステムキャッシュからアプリケーションデータを消去します。</span><span class="sxs-lookup"><span data-stu-id="35301-150">Clear application data from the file system cache for all users without removing user-specific settings, shortcuts, or file type associations.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="35301-151">すべてのアプリケーションを表示する</span><span class="sxs-lookup"><span data-stu-id="35301-151">View all applications</span></span></p></td>
<td align="left"><p><span data-ttu-id="35301-152">コンピューターに登録されているすべてのユーザーの仮想アプリケーションをユーザーに表示することを許可します。</span><span class="sxs-lookup"><span data-stu-id="35301-152">Allow the user to see the virtual applications for all users registered on the computer.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="35301-153">関連トピック</span><span class="sxs-lookup"><span data-stu-id="35301-153">Related topics</span></span>


[<span data-ttu-id="35301-154">ユーザーのアクセス許可を変更する方法</span><span class="sxs-lookup"><span data-stu-id="35301-154">How to Change User Access Permissions</span></span>](how-to-change-user-access-permissions.md)

 

 





