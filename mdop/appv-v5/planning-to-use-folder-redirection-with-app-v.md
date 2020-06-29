---
title: App-V でフォルダー リダイレクトを使用するための計画
description: App-V でフォルダー リダイレクトを使用するための計画
author: dansimp
ms.assetid: 2a4deeed-fdc0-465c-b88a-3a2fbbf27436
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b25b3531faa495275bf4e478389f44790d8eed9a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813379"
---
# <span data-ttu-id="f7620-103">App-V でフォルダー リダイレクトを使用するための計画</span><span class="sxs-lookup"><span data-stu-id="f7620-103">Planning to Use Folder Redirection with App-V</span></span>


<span data-ttu-id="f7620-104">App-v 5.0 SP2 では、フォルダーリダイレクションの使用がサポートされています。この機能により、ユーザーと管理者はフォルダーのパスを新しい場所にリダイレクトすることができます。</span><span class="sxs-lookup"><span data-stu-id="f7620-104">App-V 5.0 SP2 supports the use of folder redirection, a feature that enables users and administrators to redirect the path of a folder to a new location.</span></span>

<span data-ttu-id="f7620-105">ここでは、以下のトピックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f7620-105">This topic contains the following sections:</span></span>

-   [<span data-ttu-id="f7620-106">フォルダーリダイレクションを使用するための要件</span><span class="sxs-lookup"><span data-stu-id="f7620-106">Requirements for using folder redirection</span></span>](#bkmk-folder-redir-reqs)

-   [<span data-ttu-id="f7620-107">App-v で使用するためにフォルダーのリダイレクトを構成する方法</span><span class="sxs-lookup"><span data-stu-id="f7620-107">How to configure folder redirection for use with App-V</span></span>](#bkmk-folder-redir-cfg)

-   [<span data-ttu-id="f7620-108">フォルダーリダイレクションと app-v の連携</span><span class="sxs-lookup"><span data-stu-id="f7620-108">How folder redirection works with App-V</span></span>](#bkmk-folder-redir-works)

-   [<span data-ttu-id="f7620-109">フォルダーリダイレクションの概要</span><span class="sxs-lookup"><span data-stu-id="f7620-109">Overview of folder redirection</span></span>](#bkmk-folder-redir-overview)

## <a href="" id="bkmk-folder-redir-reqs"></a><span data-ttu-id="f7620-110">フォルダーリダイレクションを使用するための要件とサポートされていないシナリオ</span><span class="sxs-lookup"><span data-stu-id="f7620-110">Requirements and unsupported scenarios for using folder redirection</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f7620-111">要件</span><span class="sxs-lookup"><span data-stu-id="f7620-111">Requirements</span></span></p></td>
<td align="left"><p><span data-ttu-id="f7620-112">% AppData% フォルダーのリダイレクションを使用するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7620-112">To use %AppData% folder redirection, you must:</span></span></p>
<ul>
<li><p><span data-ttu-id="f7620-113">AppData 仮想ファイルシステム (VFS) フォルダーを持つ App-v パッケージがあること。</span><span class="sxs-lookup"><span data-stu-id="f7620-113">Have an App-V package that has an AppData virtual file system (VFS) folder.</span></span></p></li>
<li><p><span data-ttu-id="f7620-114">フォルダーのリダイレクトを有効にし、ユーザーのフォルダーを共有フォルダー (通常はネットワークフォルダー) にリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="f7620-114">Enable folder redirection and redirect users’ folders to a shared folder, typically a network folder.</span></span></p></li>
<li><p><span data-ttu-id="f7620-115">次の両方のどちらか一方または両方をローミングします。</span><span class="sxs-lookup"><span data-stu-id="f7620-115">Roam both or neither of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f7620-116">%Appdata%\Microsoft\AppV\Client\Catalog のファイル</span><span class="sxs-lookup"><span data-stu-id="f7620-116">Files under %appdata%\Microsoft\AppV\Client\Catalog</span></span></p></li>
<li><p><span data-ttu-id="f7620-117">HKEY_CURRENT_USER \Software\Microsoft\AppV\Client\Packages の [レジストリ設定]</span><span class="sxs-lookup"><span data-stu-id="f7620-117">Registry settings under HKEY_CURRENT_USER\Software\Microsoft\AppV\Client\Packages</span></span></p>
<p><span data-ttu-id="f7620-118">詳しくは、「 <a href="application-publishing-and-client-interaction.md#bkmk-clt-inter-roam-reqs" data-raw-source="[Application Publishing and Client Interaction](application-publishing-and-client-interaction.md#bkmk-clt-inter-roam-reqs)"> アプリケーションの発行とクライアントの操作」をご覧ください </a> 。</span><span class="sxs-lookup"><span data-stu-id="f7620-118">For more detail, see <a href="application-publishing-and-client-interaction.md#bkmk-clt-inter-roam-reqs" data-raw-source="[Application Publishing and Client Interaction](application-publishing-and-client-interaction.md#bkmk-clt-inter-roam-reqs)">Application Publishing and Client Interaction</a>.</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="f7620-119">App-v 5.0 SP2 以降のクライアントを実行しているコンピューターにログインしている各ユーザーが、次のフォルダーを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f7620-119">Ensure that the following folders are available to each user who logs into the computer that is running the App-V 5.0 SP2 or later client:</span></span></p>
<ul>
<li><p><span data-ttu-id="f7620-120">% AppData% は、目的のネットワークの場所 (オフラインファイルのサポートありまたはなし) に構成されてい <a href="https://technet.microsoft.com/library/cc780552.aspx" data-raw-source="[Offline Files](https://technet.microsoft.com/library/cc780552.aspx)"> </a> ます。</span><span class="sxs-lookup"><span data-stu-id="f7620-120">%AppData% is configured to the desired network location (with or without <a href="https://technet.microsoft.com/library/cc780552.aspx" data-raw-source="[Offline Files](https://technet.microsoft.com/library/cc780552.aspx)">Offline Files</a> support).</span></span></p></li>
<li><p><span data-ttu-id="f7620-121">% LocalAppData% は目的のローカルフォルダに設定されています。</span><span class="sxs-lookup"><span data-stu-id="f7620-121">%LocalAppData% is configured to the desired local folder.</span></span></p></li>
</ul></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f7620-122">サポートされていないシナリオ</span><span class="sxs-lookup"><span data-stu-id="f7620-122">Unsupported scenarios</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="f7620-123">% LocalAppData% をネットワークドライブとして構成しています。</span><span class="sxs-lookup"><span data-stu-id="f7620-123">Configuring %LocalAppData% as a network drive.</span></span></p></li>
<li><p><span data-ttu-id="f7620-124">複数ユーザーの場合は、[スタート] メニューを1つのフォルダーにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="f7620-124">Redirecting the Start menu to a single folder for multiple users.</span></span></p></li>
<li><p><span data-ttu-id="f7620-125">ローミングの場合 (% AppData%)は、使用できないネットワーク共有にリダイレクトされます。この場合、App-v アプリケーションは次のように起動できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f7620-125">If roaming AppData (%AppData%) is redirected to a network share that is not available, App-V applications will fail to launch as follows:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f7620-126">App-v のバージョン</span><span class="sxs-lookup"><span data-stu-id="f7620-126">App-V version</span></span></th>
<th align="left"><span data-ttu-id="f7620-127">シナリオの説明</span><span class="sxs-lookup"><span data-stu-id="f7620-127">Scenario description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f7620-128">App-v 5.0 ~ app-v 5.0 SP2 plus ホットフィックス</span><span class="sxs-lookup"><span data-stu-id="f7620-128">In App-V 5.0 through App-V 5.0 SP2 plus hotfixes</span></span></p></td>
<td align="left"><p><span data-ttu-id="f7620-129">このエラーは、オフラインファイルが有効になっているかどうかに関係なく発生します。</span><span class="sxs-lookup"><span data-stu-id="f7620-129">This failure will occur regardless of whether Offline Files is enabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f7620-130">App-v 5.0 SP3 の場合</span><span class="sxs-lookup"><span data-stu-id="f7620-130">In App-V 5.0 SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="f7620-131">オフラインファイルで利用できないネットワーク共有が有効になっている場合は、App-v アプリケーションが正常に起動します。</span><span class="sxs-lookup"><span data-stu-id="f7620-131">If the unavailable network share has been enabled for Offline Files, the App-V application will start successfully.</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-folder-redir-cfg"></a><span data-ttu-id="f7620-132">App-v で使用するためにフォルダーのリダイレクトを構成する方法</span><span class="sxs-lookup"><span data-stu-id="f7620-132">How to configure folder redirection for use with App-V</span></span>


<span data-ttu-id="f7620-133">フォルダーのリダイレクトは、デスクトップ、マイドキュメント、写真など、さまざまなフォルダーに適用できます。ただし、App-v アプリケーションの使用に影響を与える唯一のフォルダーは、ユーザーのローミング AppData フォルダー (% AppData%) です。</span><span class="sxs-lookup"><span data-stu-id="f7620-133">Folder redirection can be applied to different folders, such as Desktop, My Documents, My Pictures, etc. However, the only folder that impacts the use of App-V applications is the user’s roaming AppData folder (%AppData%).</span></span> <span data-ttu-id="f7620-134">他のサポートされているフォルダーには、App-v に影響を与えることなく、フォルダーリダイレクションを適用できます。</span><span class="sxs-lookup"><span data-stu-id="f7620-134">You can apply folder redirection to any other supported folders without impacting App-V.</span></span>

## <a href="" id="bkmk-folder-redir-works"></a><span data-ttu-id="f7620-135">フォルダーリダイレクションと app-v の連携</span><span class="sxs-lookup"><span data-stu-id="f7620-135">How folder redirection works with App-V</span></span>


<span data-ttu-id="f7620-136">次の表では、% AppData% がネットワークにリダイレクトされ、この記事の前半で説明した要件を満たしている場合の、フォルダーのリダイレクトの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7620-136">The following table describes how folder redirection works when %AppData% is redirected to a network and when you have met the requirements listed earlier in this article.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f7620-137">仮想環境の状態</span><span class="sxs-lookup"><span data-stu-id="f7620-137">Virtual environment state</span></span></th>
<th align="left"><span data-ttu-id="f7620-138">実行されるアクション</span><span class="sxs-lookup"><span data-stu-id="f7620-138">Action that occurs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f7620-139">仮想環境の開始時</span><span class="sxs-lookup"><span data-stu-id="f7620-139">When the virtual environment starts</span></span></p></td>
<td align="left"><p><span data-ttu-id="f7620-140">仮想ファイルシステム (VFS) AppData フォルダーはローカルの AppData フォルダにマッピングされています (% LocalAppData%)ユーザーのローミング用の AppData フォルダ (% AppData%) の代わりに</span><span class="sxs-lookup"><span data-stu-id="f7620-140">The virtual file system (VFS) AppData folder is mapped to the local AppData folder (%LocalAppData%) instead of to the user’s roaming AppData folder (%AppData%).</span></span></p>
<ul>
<li><p><span data-ttu-id="f7620-141">LocalAppData には、使用中のパッケージのユーザーのローミングの AppData フォルダーのローカルキャッシュが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f7620-141">LocalAppData contains a local cache of the user’s roaming AppData folder for the package in use.</span></span> <span data-ttu-id="f7620-142">ローカルキャッシュは次の場所にあります。</span><span class="sxs-lookup"><span data-stu-id="f7620-142">The local cache is located under:</span></span></p>
<p><code>%LocalAppData%\Microsoft\AppV\Client\VFS\PackageGUID\AppData</code></p></li>
<li><p><span data-ttu-id="f7620-143">ユーザーのローミングの AppData フォルダーからの最新データは、ローカルキャッシュ内の現在のデータにコピーされ、置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="f7620-143">The latest data from the user’s roaming AppData folder is copied to and replaces the data currently in the local cache.</span></span></p></li>
<li><p><span data-ttu-id="f7620-144">仮想環境が実行されている間、データはローカルキャッシュに保存されたままになります。</span><span class="sxs-lookup"><span data-stu-id="f7620-144">While the virtual environment is running, data continues to be saved to the local cache.</span></span> <span data-ttu-id="f7620-145">データは、% LocalAppData% からのみ配信され、エンドユーザーがコンピューターをシャットダウンするまで、% AppData% との間で移動または同期されません。</span><span class="sxs-lookup"><span data-stu-id="f7620-145">Data is served only out of %LocalAppData% and is not moved or synchronized with %AppData% until the end user shuts down the computer.</span></span></p></li>
<li><p><span data-ttu-id="f7620-146">AppData フォルダーへのエントリは、システムコンテキストではなく、ユーザーコンテキストを使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="f7620-146">Entries to the AppData folder are made using the user context, not the system context.</span></span></p></li>
</ul>
<div class="alert">
<strong><span data-ttu-id="f7620-147">注</span><span class="sxs-lookup"><span data-stu-id="f7620-147">Note</span></span></strong><br/><p><span data-ttu-id="f7620-148">App-v クライアントフォルダーリダイレクションは、% AppData% から% LocalAppData% にファイルを移動することができない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7620-148">The App-V client folder redirection sometimes fails to move files from %AppData% to %LocalAppData%.</span></span> <span data-ttu-id="f7620-149">「 <a href="release-notes-for-app-v-50-sp2.md#bkmk-folderredirection" data-raw-source="[Release Notes for App-V 5.0 SP2](release-notes-for-app-v-50-sp2.md#bkmk-folderredirection)"> App-v 5.0 SP2 のリリースノート」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="f7620-149">See <a href="release-notes-for-app-v-50-sp2.md#bkmk-folderredirection" data-raw-source="[Release Notes for App-V 5.0 SP2](release-notes-for-app-v-50-sp2.md#bkmk-folderredirection)">Release Notes for App-V 5.0 SP2</a>.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f7620-150">仮想環境のシャットダウン時</span><span class="sxs-lookup"><span data-stu-id="f7620-150">When the virtual environment shuts down</span></span></p></td>
<td align="left"><p><span data-ttu-id="f7620-151">AppData (ローミング) 内のローカルにキャッシュされたデータは、% AppData% の "本物" ローミング AppData フォルダーに圧縮され、コピーされます。</span><span class="sxs-lookup"><span data-stu-id="f7620-151">The local cached data in AppData (roaming) is zipped up and copied to the “real” roaming AppData folder in %AppData%.</span></span> <span data-ttu-id="f7620-152">最後の既知のアップロードを示すタイムスタンプは、次のレジストリキーとして同時に保存されます。</span><span class="sxs-lookup"><span data-stu-id="f7620-152">A time stamp, which indicates the last known upload, is simultaneously saved as a registry key under:</span></span></p>
<p><code>HKCU\Software\Microsoft\AppV\Client\Packages&amp;lt;PACKAGE_GUID&gt;\AppDataTime</code></p>
<p><span data-ttu-id="f7620-153">冗長性を提供するために、App-v 5.0 は、圧縮されたデータの3つの最新のコピーを% AppData% で保持します。</span><span class="sxs-lookup"><span data-stu-id="f7620-153">To provide redundancy, App-V 5.0 keeps the three most recent copies of the compressed data under %AppData%.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-folder-redir-overview"></a><span data-ttu-id="f7620-154">フォルダーリダイレクションの概要</span><span class="sxs-lookup"><span data-stu-id="f7620-154">Overview of folder redirection</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f7620-155">目的</span><span class="sxs-lookup"><span data-stu-id="f7620-155">Purpose</span></span></p></td>
<td align="left"><p><span data-ttu-id="f7620-156">エンドユーザーが別のフォルダーにリダイレクトされたファイルを、ローカルドライブでまだ存在しているかのように、そのファイルを操作できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f7620-156">Enables end users to work with files, which have been redirected to another folder, as if the files still existed on the local drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f7620-157">説明</span><span class="sxs-lookup"><span data-stu-id="f7620-157">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="f7620-158">フォルダーリダイレクションを使用すると、ユーザーと管理者はフォルダーのパスをネットワーク上の場所にリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="f7620-158">Folder redirection allows users and administrators to redirect the path of a folder to a network location.</span></span> <span data-ttu-id="f7620-159">フォルダー内のドキュメントは、ネットワーク上のどのコンピューターからでもユーザーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="f7620-159">The documents in the folder are available to the user from any computer on the network.</span></span></p>
<ul>
<li><p><span data-ttu-id="f7620-160">フォルダーリダイレクションを使用すると、ユーザーと管理者はフォルダーのパスをネットワーク上の場所にリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="f7620-160">Folder redirection allows users and administrators to redirect the path of a folder to a network location.</span></span> <span data-ttu-id="f7620-161">フォルダー内のドキュメントは、ネットワーク上のどのコンピューターからでもユーザーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="f7620-161">The documents in the folder are available to the user from any computer on the network.</span></span></p></li>
<li><p><span data-ttu-id="f7620-162">新しい場所には、ローカルコンピューター上のフォルダーまたは共有ネットワーク上のフォルダーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f7620-162">The new location can be a folder on the local computer or a folder on a shared network.</span></span></p></li>
<li><p><span data-ttu-id="f7620-163">フォルダーリダイレクションによってファイルがすぐに更新されますが、通常、ユーザーがログインまたはログオフすると、ローミングデータが同期されます。</span><span class="sxs-lookup"><span data-stu-id="f7620-163">Folder redirection updates the files immediately, whereas roaming data is typically synchronized when the user logs in or logs off.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f7620-164">使用例</span><span class="sxs-lookup"><span data-stu-id="f7620-164">Usage example</span></span></p></td>
<td align="left"><p><span data-ttu-id="f7620-165">[ドキュメント] フォルダー (通常はコンピューター&#39;s ローカルハードディスクに保存されている) をネットワーク上の場所にリダイレクトすることができます。</span><span class="sxs-lookup"><span data-stu-id="f7620-165">You can redirect the Documents folder, which is usually stored on the computer&#39;s local hard disk, to a network location.</span></span> <span data-ttu-id="f7620-166">ユーザーは、ネットワーク上の任意のコンピューターからフォルダー内のドキュメントにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f7620-166">The user can access the documents in the folder from any computer on the network.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f7620-167">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="f7620-167">More resources</span></span></p></td>
<td align="left"><p><a href="https://technet.microsoft.com/library/cc778976.aspx" data-raw-source="[Folder redirection overview](https://technet.microsoft.com/library/cc778976.aspx)"><span data-ttu-id="f7620-168">フォルダリダイレクションの概要</span><span class="sxs-lookup"><span data-stu-id="f7620-168">Folder redirection overview</span></span></a></p></td>
</tr>
</tbody>
</table>
















