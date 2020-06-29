---
title: MED-V ワークスペースの構成設定の管理
description: MED-V ワークスペースの構成設定の管理
author: dansimp
ms.assetid: 517d04de-c31f-4b50-b2b3-5f8c312ed37b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 97add695f605b71547b564789cce07a1d58763f2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826157"
---
# <span data-ttu-id="ccc72-103">MED-V ワークスペースの構成設定の管理</span><span class="sxs-lookup"><span data-stu-id="ccc72-103">Managing MED-V Workspace Configuration Settings</span></span>


<span data-ttu-id="ccc72-104">Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 では、構成設定がレジストリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-104">Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 stores its configuration settings in the registry.</span></span> <span data-ttu-id="ccc72-105">ここに記載されているレジストリに関する情報は、MED-V サービスをより適切に管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-105">The information we include here about the registry may help you better manage your MED-V services.</span></span>

<span data-ttu-id="ccc72-106">MED-V では、設定値を検索するときに、次の検索パスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-106">MED-V uses the following search path when looking for the resultant settings values:</span></span>

<span data-ttu-id="ccc72-107">MED は、まずマシンのポリシーを検索します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-107">MED-V first looks in the machine policy.</span></span>

<span data-ttu-id="ccc72-108">値が見つからない場合、MED-V はユーザーポリシーで検索されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-108">If the value is not found, MED-V looks in the user policy.</span></span>

<span data-ttu-id="ccc72-109">この値が見つからない場合、MED-V は HKEY \ _LOCAL \ _MACHINE \\ システムハイブで検索されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-109">If the value is not found, MED-V looks in the HKEY\_LOCAL\_MACHINE\\System hive.</span></span>

<span data-ttu-id="ccc72-110">この値が見つからない場合、MED-V は HKEY \ _CURRENT USER registry ハイブで検索されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-110">If the value is not found, MED-V looks in the HKEY\_CURRENT USER registry hive.</span></span>

<span data-ttu-id="ccc72-111">それでも値が見つからない場合、MED-V は既定値を使います。</span><span class="sxs-lookup"><span data-stu-id="ccc72-111">If the value is still not found, MED-V uses the default.</span></span>

<span data-ttu-id="ccc72-112">一般的なベストプラクティスは、HKEY \ _LOCAL \ _MACHINE \\ システムハイブまたはコンピューターポリシーの値を設定することです。</span><span class="sxs-lookup"><span data-stu-id="ccc72-112">A general best practice is to set the value in the HKEY\_LOCAL\_MACHINE\\System hive or in the machine policy.</span></span> <span data-ttu-id="ccc72-113">ただし、エンドユーザーが特定の設定を構成できるようにする場合は、そのままにしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccc72-113">But if you want the end user to be able to configure a particular setting, then you should leave it out.</span></span>

**<span data-ttu-id="ccc72-114">注</span><span class="sxs-lookup"><span data-stu-id="ccc72-114">Note</span></span>**  
<span data-ttu-id="ccc72-115">MED-V ワークスペースを展開する前に、スクリプトエディターを使って、MED-V ワークスペースパッケージャーで作成された Windows PowerShell スクリプト (ps1 ファイル) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-115">Before you deploy your MED-V workspaces, you can use a script editor to change the Windows PowerShell script (.ps1 file) that the MED-V workspace packager created.</span></span> <span data-ttu-id="ccc72-116">詳細については、「 [Windows PowerShell を使用して詳細設定を構成する](configuring-advanced-settings-by-using-windows-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccc72-116">For more information, see [Configuring Advanced Settings by Using Windows PowerShell](configuring-advanced-settings-by-using-windows-powershell.md).</span></span>

<span data-ttu-id="ccc72-117">MED-V のワークスペースを展開したら、レジストリエントリを編集することで、特定の MED-V 構成の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-117">After you have deployed your MED-V workspaces, you can change certain MED-V configuration settings by editing the registry entries.</span></span>



<span data-ttu-id="ccc72-118">このセクションには、すべての構成可能な MED-V レジストリキーの一覧とその使用方法が記載されています。</span><span class="sxs-lookup"><span data-stu-id="ccc72-118">This section lists all the configurable MED-V registry keys and explains their uses.</span></span>

## <span data-ttu-id="ccc72-119">診断キー</span><span class="sxs-lookup"><span data-stu-id="ccc72-119">Diagnostics Key</span></span>


<span data-ttu-id="ccc72-120">次の表では、HKEY \ _LOCAL \ _MACHINE ¥ $ ¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥¥ # # # の各診断キーに関連付けられたレジストリ値に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-120">The following table provides information about the registry values associated with the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Medv\\v2\\Diagnostics key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ccc72-121">名前</span><span class="sxs-lookup"><span data-stu-id="ccc72-121">Name</span></span> </th>
<th align="left"><span data-ttu-id="ccc72-122">型</span><span class="sxs-lookup"><span data-stu-id="ccc72-122">Type</span></span> </th>
<th align="left"><span data-ttu-id="ccc72-123">データ/既定</span><span class="sxs-lookup"><span data-stu-id="ccc72-123">Data/Default</span></span> </th>
<th align="left"><span data-ttu-id="ccc72-124">説明</span><span class="sxs-lookup"><span data-stu-id="ccc72-124">Description</span></span> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-125">EventLogLevel</span><span class="sxs-lookup"><span data-stu-id="ccc72-125">EventLogLevel</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-126">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-126">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-127">既定値 = 3</span><span class="sxs-lookup"><span data-stu-id="ccc72-127">Default=3</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-128">イベントログに記録される情報の種類。</span><span class="sxs-lookup"><span data-stu-id="ccc72-128">The type of information that is logged in the event log.</span></span> <span data-ttu-id="ccc72-129">レベルには次の情報が含まれます: 0 (なし)、1 (エラー)、2 (警告)、3 (情報)、4 (デバッグ)。</span><span class="sxs-lookup"><span data-stu-id="ccc72-129">Levels include the following: 0 (None), 1 (Error), 2 (Warning), 3 (Information), 4 (Debug).</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="ccc72-130">Fts キー</span><span class="sxs-lookup"><span data-stu-id="ccc72-130">Fts Key</span></span>


<span data-ttu-id="ccc72-131">次の表では、HKEY \ _LOCAL \ _MACHINE \ ソフトウェア¥のバージョンに関連付けられているレジストリ値について説明します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-131">The following table provides information about the registry values associated with the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Medv\\v2\\Fts key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ccc72-132">名前</span><span class="sxs-lookup"><span data-stu-id="ccc72-132">Name</span></span></th>
<th align="left"><span data-ttu-id="ccc72-133">型</span><span class="sxs-lookup"><span data-stu-id="ccc72-133">Type</span></span></th>
<th align="left"><span data-ttu-id="ccc72-134">データ/既定</span><span class="sxs-lookup"><span data-stu-id="ccc72-134">Data/Default</span></span></th>
<th align="left"><span data-ttu-id="ccc72-135">説明</span><span class="sxs-lookup"><span data-stu-id="ccc72-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-136">AddUserToAdminGroupEnabled</span><span class="sxs-lookup"><span data-stu-id="ccc72-136">AddUserToAdminGroupEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-137">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-137">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-138">既定値 = 0</span><span class="sxs-lookup"><span data-stu-id="ccc72-138">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-139">初めてセットアップするときに、エンドユーザーを管理者&#39;s グループに自動的に追加するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-139">Configures whether first time setup automatically adds the end user to the administrator&#39;s group.</span></span> <span data-ttu-id="ccc72-140">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="ccc72-140">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-141">0 = false: 初回セットアップでは、管理者&#39;s グループにエンドユーザーが自動的に追加されることはありません。</span><span class="sxs-lookup"><span data-stu-id="ccc72-141">0 = false: First time setup does not automatically add the end user to the administrator&#39;s group.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-142">1 = true: 初回セットアップでは、エンドユーザーが管理者&#39;s グループに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-142">1 = true: First time setup automatically adds the end user to the administrator&#39;s group.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-143">ComputerNameMask</span><span class="sxs-lookup"><span data-stu-id="ccc72-143">ComputerNameMask</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-144">SZ</span><span class="sxs-lookup"><span data-stu-id="ccc72-144">SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-145">MEDV\*</span><span class="sxs-lookup"><span data-stu-id="ccc72-145">MEDV\*</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-146">ゲスト仮想マシン&#39;s コンピューター名の作成に使用するコンピューター名マスク。</span><span class="sxs-lookup"><span data-stu-id="ccc72-146">The computer name mask that is used to create the guest virtual machine&#39;s computer name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-147">マスクには、コンピューター名の一部としてユーザー名を挿入するための% username% タグを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-147">The mask can contain a %username% tag to insert the username as part of the computer name.</span></span> <span data-ttu-id="ccc72-148">同様に、% hostname% タグによって、ホストコンピューターの名前が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-148">Likewise, the %hostname% tag inserts the name of the host computer.</span></span></p>
<p><span data-ttu-id="ccc72-149">&quot; # &quot; マスク内の各文字はランダムな数字に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-149">Every &quot;#&quot; character in the mask is replaced by a random digit.</span></span> <span data-ttu-id="ccc72-150">マスクの末尾にあるアスタリスク (\*) 文字は、ランダムな英数字に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-150">An asterisk (\*) character at the end of the mask is replaced by random alphanumeric characters.</span></span></p>
<p><span data-ttu-id="ccc72-151">% Hostname% と% username% の特定の文字数は、角かっこを使ってキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-151">A specific number of characters from %hostname% and %username% can be captured by using square brackets.</span></span> <span data-ttu-id="ccc72-152">たとえば、 &quot; % username% [3] は、 &quot; ユーザー名の最初の3文字を使います。</span><span class="sxs-lookup"><span data-stu-id="ccc72-152">For example, &quot;%username%[3]&quot; would use the first three characters of the username.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-153">DeleteVMStateTimeout</span><span class="sxs-lookup"><span data-stu-id="ccc72-153">DeleteVMStateTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-154">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-154">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-155">既定値 = 90</span><span class="sxs-lookup"><span data-stu-id="ccc72-155">Default=90</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-156">初回セットアップで仮想マシンを削除しようとしたときのタイムアウト値 (秒単位)。</span><span class="sxs-lookup"><span data-stu-id="ccc72-156">The time-out value, in seconds, when first time setup tries to delete the virtual machine.</span></span> <span data-ttu-id="ccc72-157">範囲 = 0 ~ 2147483647</span><span class="sxs-lookup"><span data-stu-id="ccc72-157">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-158">DetachVfdTimeout</span><span class="sxs-lookup"><span data-stu-id="ccc72-158">DetachVfdTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-159">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-159">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-160">既定値 = 120</span><span class="sxs-lookup"><span data-stu-id="ccc72-160">Default=120</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-161">初めてセットアップしたときに仮想マシンから仮想フロッピーディスクがデタッチされるまでのタイムアウト値 (秒単位)。</span><span class="sxs-lookup"><span data-stu-id="ccc72-161">The time-out value, in seconds, when first time setup tries to detach the virtual floppy disk from the virtual machine.</span></span> <span data-ttu-id="ccc72-162">範囲 = 0 ~ 2147483647</span><span class="sxs-lookup"><span data-stu-id="ccc72-162">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-163">指定 Url</span><span class="sxs-lookup"><span data-stu-id="ccc72-163">DialogUrl</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-164">SZ</span><span class="sxs-lookup"><span data-stu-id="ccc72-164">SZ</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-165">内部 web ページへのリンクを含むカスタマイズ可能な URL。また、初回セットアップのダイアログメッセージで表示されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-165">Customizable URL that links to internal webpage and is displayed by first time setup dialog messages.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-166">ExplorerTimeout</span><span class="sxs-lookup"><span data-stu-id="ccc72-166">ExplorerTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-167">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-167">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-168">既定値 = 900</span><span class="sxs-lookup"><span data-stu-id="ccc72-168">Default=900</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-169">Windows エクスプローラーで最初にセットアップが待機するタイムアウト値 (秒)。</span><span class="sxs-lookup"><span data-stu-id="ccc72-169">The time-out value, in seconds, that first time setup waits for Windows Explorer.</span></span> <span data-ttu-id="ccc72-170">範囲 = 0 ~ 2147483647</span><span class="sxs-lookup"><span data-stu-id="ccc72-170">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-171">障害メッセージ</span><span class="sxs-lookup"><span data-stu-id="ccc72-171">FailureDialogMsg</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-172">MULTI_SZ</span><span class="sxs-lookup"><span data-stu-id="ccc72-172">MULTI_SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-173">リソースファイルにメッセージがあります</span><span class="sxs-lookup"><span data-stu-id="ccc72-173">Message is found in resource file</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-174">初めてセットアップを完了できない場合にエンドユーザーに表示されるカスタマイズ可能なメッセージ。</span><span class="sxs-lookup"><span data-stu-id="ccc72-174">Customizable message that is displayed to the end user when first time setup cannot be completed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-175">GiveUserGroupRightsMaxRetryCount</span><span class="sxs-lookup"><span data-stu-id="ccc72-175">GiveUserGroupRightsMaxRetryCount</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-176">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-176">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-177">既定値 = 3</span><span class="sxs-lookup"><span data-stu-id="ccc72-177">Default=3</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-178">MED-V がエンドユーザーグループの権限を付与する最大の回数。</span><span class="sxs-lookup"><span data-stu-id="ccc72-178">The maximum number of times that MED-V tries to give an end user group rights.</span></span> <span data-ttu-id="ccc72-179">指定された再試行値を超えても、エンドユーザーグループの権限を与えられていない場合は、仮想マシンの準備エラーが原因である可能性が高くなります。その後、MaxRetryCount 値が適用されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-179">Exceeding the specified retry value without being able to successfully give an end user group rights most likely causes a virtual machine preparation failure that is then subject to the MaxRetryCount value.</span></span> <span data-ttu-id="ccc72-180">範囲 = 0 ~ 2147483647</span><span class="sxs-lookup"><span data-stu-id="ccc72-180">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-181">GiveUserGroupRightsTimeout</span><span class="sxs-lookup"><span data-stu-id="ccc72-181">GiveUserGroupRightsTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-182">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-182">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-183">既定値 = 300</span><span class="sxs-lookup"><span data-stu-id="ccc72-183">Default=300</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-184">ユーザーグループの権限を付与するときのタイムアウト値 (秒単位) です。</span><span class="sxs-lookup"><span data-stu-id="ccc72-184">The time-out value, in seconds, when giving a user group rights.</span></span> <span data-ttu-id="ccc72-185">範囲 = 0 ~ 2147483647</span><span class="sxs-lookup"><span data-stu-id="ccc72-185">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-186">LogFilePaths</span><span class="sxs-lookup"><span data-stu-id="ccc72-186">LogFilePaths</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-187">MULTI_SZ</span><span class="sxs-lookup"><span data-stu-id="ccc72-187">MULTI_SZ</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-188">初回のセットアップ時に、MED-V で収集されるログファイルパスの一覧。</span><span class="sxs-lookup"><span data-stu-id="ccc72-188">A list of the log file paths that MED-V collects during first time setup.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-189">MaxPostponeTime</span><span class="sxs-lookup"><span data-stu-id="ccc72-189">MaxPostponeTime</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-190">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-190">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-191">既定値 = 120</span><span class="sxs-lookup"><span data-stu-id="ccc72-191">Default=120</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-192">エンドユーザーが初めてセットアップを延期できる時間の最大数。</span><span class="sxs-lookup"><span data-stu-id="ccc72-192">The maximum number of hours that first time setup can be postponed by the end user.</span></span> <span data-ttu-id="ccc72-193">範囲 = 0 ~ 2147483647</span><span class="sxs-lookup"><span data-stu-id="ccc72-193">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-194">MaxRetryCount</span><span class="sxs-lookup"><span data-stu-id="ccc72-194">MaxRetryCount</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-195">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-195">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-196">既定値 = 3</span><span class="sxs-lookup"><span data-stu-id="ccc72-196">Default=3</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-197">各試行がソフトウェアエラー以外のエラーで終了した場合に、MED-V が仮想マシンの準備を試みる最大回数。</span><span class="sxs-lookup"><span data-stu-id="ccc72-197">The maximum number of times that MED-V tries to prepare a virtual machine if each attempt ends in a failure other than a software error.</span></span> <span data-ttu-id="ccc72-198">仮想マシンの準備に失敗し、初回のセットアップの再試行回数が超過した場合、MED-V は、エンドユーザーにエラーを通知し、再試行するオプションを提供しません。</span><span class="sxs-lookup"><span data-stu-id="ccc72-198">When virtual machine preparation fails and the number of first time setup retries is exceeded, then MED-V informs the end user about the failure and does not give the option to retry.</span></span> <span data-ttu-id="ccc72-199">MED-V が開始されるたびに、カウントが再設定されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-199">The count is re-set every time that MED-V is started.</span></span> <span data-ttu-id="ccc72-200">範囲 = 0 ~ 2147483647</span><span class="sxs-lookup"><span data-stu-id="ccc72-200">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-201">モード</span><span class="sxs-lookup"><span data-stu-id="ccc72-201">Mode</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-202">SZ</span><span class="sxs-lookup"><span data-stu-id="ccc72-202">SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-203">既定値 = 無人</span><span class="sxs-lookup"><span data-stu-id="ccc72-203">Default=Unattended</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-204">初めて設定したユーザーとの対話方法を構成します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-204">Configures how first time setup interacts with the user.</span></span> <span data-ttu-id="ccc72-205">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-205">Possible values are as follows:</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="ccc72-206">対話.</span><span class="sxs-lookup"><span data-stu-id="ccc72-206">Attended.</span></span></strong> <span data-ttu-id="ccc72-207">エンドユーザーは、初回のセットアップ中に情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccc72-207">The end user must enter information during first time setup.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ccc72-208">注</span><span class="sxs-lookup"><span data-stu-id="ccc72-208">Note</span></span></strong><br/><p><span data-ttu-id="ccc72-209">Mini-setup ファイルを作成して、ミニセットアップでユーザーの入力を完了する必要があるようにする場合は、有人モードを選択する必要があり <strong> </strong> ます。または、初回のセットアップ時に問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ccc72-209">If you created the Sysprep.inf file so that Mini-Setup requires user input to complete, then you must select <strong>Attended</strong> mode or problems might occur during first time setup.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="ccc72-210">無人 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="ccc72-210">Unattended</strong>.</span></span> <span data-ttu-id="ccc72-211">仮想マシンは、初回のセットアップ時にエンドユーザーには表示されませんが、最初のセットアップが開始される前にエンドユーザーに確認が求められます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-211">The virtual machine is not shown to the end user during first time setup, but the end user is prompted before first time setup starts.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="ccc72-212">Silent </strong> 。</span><span class="sxs-lookup"><span data-stu-id="ccc72-212">Silent</strong>.</span></span> <span data-ttu-id="ccc72-213">仮想マシンは、初回のセットアップ時にエンドユーザーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="ccc72-213">The virtual machine is not shown to the end user at all during first time setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-214">NonInteractiveRetryTimeoutInc</span><span class="sxs-lookup"><span data-stu-id="ccc72-214">NonInteractiveRetryTimeoutInc</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-215">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-215">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-216">既定値 = 15</span><span class="sxs-lookup"><span data-stu-id="ccc72-216">Default=15</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-217">セットアップを再実行するときの初回セットアップ対話モードでのタイムアウト値 (分単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-217">The time-out value, in minutes, that first time setup must be completed in first time setup interactive mode when re-attempting setup.</span></span> <span data-ttu-id="ccc72-218">範囲 = 0 ~ 2147483647</span><span class="sxs-lookup"><span data-stu-id="ccc72-218">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-219">ノン Interactivetimeout</span><span class="sxs-lookup"><span data-stu-id="ccc72-219">NonInteractiveTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-220">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-220">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-221">既定値 = 45</span><span class="sxs-lookup"><span data-stu-id="ccc72-221">Default=45</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-222">初回のセットアップ対話モードで初めてセットアップするときのタイムアウト値 (分単位)。</span><span class="sxs-lookup"><span data-stu-id="ccc72-222">The time-out value, in minutes, that first time setup must be completed in first time setup interactive mode.</span></span> <span data-ttu-id="ccc72-223">範囲 = 0 ~ 2147483647</span><span class="sxs-lookup"><span data-stu-id="ccc72-223">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-224">PostponeUtcDateTimeLimit</span><span class="sxs-lookup"><span data-stu-id="ccc72-224">PostponeUtcDateTimeLimit</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-225">SZ</span><span class="sxs-lookup"><span data-stu-id="ccc72-225">SZ</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-226">初めてセットアップを延期できる日付と時刻 (UTC 形式)。</span><span class="sxs-lookup"><span data-stu-id="ccc72-226">The date and time, in UTC DateTime format, that first time setup can be postponed.</span></span> <span data-ttu-id="ccc72-227">&quot; &quot; 24 時間制の標準を使用して時間を指定して、yyyy-mm-dd hh: mm の形式で入力します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-227">Enter in the format &quot;yyyy-MM-dd hh:mm&quot; with hours specified by using the 24-hour clock standard.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-228">Retrymsg メッセージ</span><span class="sxs-lookup"><span data-stu-id="ccc72-228">RetryDialogMsg</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-229">MULTI_SZ</span><span class="sxs-lookup"><span data-stu-id="ccc72-229">MULTI_SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-230">リソースファイルにメッセージがあります</span><span class="sxs-lookup"><span data-stu-id="ccc72-230">Message is found in resource file</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-231">初めてセットアップするときにエンドユーザーに表示されるカスタマイズ可能なメッセージ。</span><span class="sxs-lookup"><span data-stu-id="ccc72-231">Customizable message that is displayed to the end user when first time setup must re-attempt setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-232">SetComputerNameEnabled</span><span class="sxs-lookup"><span data-stu-id="ccc72-232">SetComputerNameEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-233">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-233">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-234">既定値 = 0</span><span class="sxs-lookup"><span data-stu-id="ccc72-234">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-235">ゲストの Sysprep.inf ファイルの [UserData] セクションの下にある ComputerName エントリを、指定された ComputerNameMask に応じて更新するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-235">Configures whether the ComputerName entry under the [UserData] section of the Sysprep.inf file in the guest should be updated according to the specified ComputerNameMask.</span></span>   <span data-ttu-id="ccc72-236">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="ccc72-236">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-237">0 = false: Sysprep.inf ファイルの ComputerName エントリは、ComputerNameMask によって更新されません。</span><span class="sxs-lookup"><span data-stu-id="ccc72-237">0 = false: The ComputerName entry in the Sysprep.inf file is not updated according to the ComputerNameMask.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-238">1 = true: Sysprep.inf ファイルの ComputerName エントリは、ComputerNameMask に従って更新されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-238">1 = true: The ComputerName entry in the Sysprep.inf file is updated according to the ComputerNameMask.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-239">SetJoinDomainEnabled</span><span class="sxs-lookup"><span data-stu-id="ccc72-239">SetJoinDomainEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-240">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-240">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-241">既定値 = 0</span><span class="sxs-lookup"><span data-stu-id="ccc72-241">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-242">ゲストの Sysprep.inf ファイルの [Id] セクションにある JoinDomain 設定を、ホスト上の設定と一致するように更新する必要があるかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-242">Configures whether the JoinDomain setting under the [Identification] section of the Sysprep.inf file in the guest should be updated to match the settings on the host.</span></span>  <span data-ttu-id="ccc72-243">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="ccc72-243">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-244">0 = false: Sysprep.inf ファイルの JoinDomain 設定は、ホストの設定に一致するように更新されません。</span><span class="sxs-lookup"><span data-stu-id="ccc72-244">0 = false: The JoinDomain setting in the Sysprep.inf file is not updated to match the settings on the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-245">1 = true: Sysprep.inf ファイルの JoinDomain 設定が、ホストの設定と一致するように更新されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-245">1 = true: The JoinDomain setting in the Sysprep.inf file is updated to match the settings on the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-246">SetMachineObjectOUEnabled</span><span class="sxs-lookup"><span data-stu-id="ccc72-246">SetMachineObjectOUEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-247">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-247">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-248">既定値 = 0</span><span class="sxs-lookup"><span data-stu-id="ccc72-248">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-249">ゲストの Sysprep.inf ファイルの [識別] セクションにある MachineObjectOU 条件設定が、ホストに一致するように更新されるかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-249">Configures whether the MachineObjectOU setting under the [Identification] section of the Sysprep.inf file in the guest is updated to match the host.</span></span>  <span data-ttu-id="ccc72-250">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="ccc72-250">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-251">0 = false: Sysprep.inf ファイルの Machineの条件設定は、ホスト上の設定に一致するように更新されません。</span><span class="sxs-lookup"><span data-stu-id="ccc72-251">0 = false: The MachineObjectOU setting in the Sysprep.inf file is not updated to match the settings on the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-252">1 = true: Sysprep.inf ファイルの Machineの条件設定が、ホストの設定と一致するように更新されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-252">1 = true: The MachineObjectOU setting in the Sysprep.inf file is updated to match the settings on the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-253">SetRegionalSettingsEnabled</span><span class="sxs-lookup"><span data-stu-id="ccc72-253">SetRegionalSettingsEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-254">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-254">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-255">既定値 = 0</span><span class="sxs-lookup"><span data-stu-id="ccc72-255">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-256">ゲストの Sysprep.inf ファイルの [RegionalSettings] セクションの下にある設定が、ホストに一致するように更新されるかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-256">Configures whether the settings under the [RegionalSettings] section of the Sysprep.inf file in the guest are updated to match the host.</span></span>  <span data-ttu-id="ccc72-257">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="ccc72-257">0 = false; 1 = true.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ccc72-258">注</span><span class="sxs-lookup"><span data-stu-id="ccc72-258">Note</span></span></strong><br/><p><span data-ttu-id="ccc72-259">既定では、ゲストのタイムゾーンの設定は、常にホストのタイムゾーンの設定と同期されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-259">By default, the setting for TimeZone in the guest is always synchronized with the TimeZone setting in the host.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-260">0 = false: ゲストの Sysprep.inf ファイルの [RegionalSettings] セクションの下にある設定は、ホストに一致するように更新されません。</span><span class="sxs-lookup"><span data-stu-id="ccc72-260">0 = false: The settings under the [RegionalSettings] section of the Sysprep.inf file in the guest are not updated to match the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-261">1 = true: ゲストの Sysprep.inf ファイルの [RegionalSettings] セクションの下にある設定が、ホストと一致するように更新されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-261">1 = true: The settings under the [RegionalSettings] section of the Sysprep.inf file in the guest are updated to match the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-262">SetUserDataEnabled</span><span class="sxs-lookup"><span data-stu-id="ccc72-262">SetUserDataEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-263">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-263">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-264">既定値 = 0</span><span class="sxs-lookup"><span data-stu-id="ccc72-264">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-265">ゲストの Sysprep.inf ファイルの [UserData] セクションにある FullName と OrgName の設定が、ホストの設定と一致するように更新されるかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-265">Configures whether the FullName and the OrgName settings under the [UserData] section of the Sysprep.inf file in the guest are updated to match the settings on the host.</span></span>  <span data-ttu-id="ccc72-266">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="ccc72-266">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-267">0 = false: Sysprep.inf ファイルの FullName と OrgName の設定は、ホストの設定と一致するように更新されません。</span><span class="sxs-lookup"><span data-stu-id="ccc72-267">0 = false: The FullName and OrgName settings in the Sysprep.inf file are not updated to match the settings on the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-268">1 = true: Sysprep.inf ファイルの FullName と OrgName の設定が、ホストの設定と一致するように更新されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-268">1 = true: The FullName and OrgName settings in the Sysprep.inf file are updated to match the settings on the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-269">StartDialogMsg</span><span class="sxs-lookup"><span data-stu-id="ccc72-269">StartDialogMsg</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-270">MULTI_SZ</span><span class="sxs-lookup"><span data-stu-id="ccc72-270">MULTI_SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-271">リソースファイルにメッセージがあります</span><span class="sxs-lookup"><span data-stu-id="ccc72-271">Message is found in resource file</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-272">初めてセットアップを開始する準備ができた時点でエンドユーザーに表示されるカスタマイズ可能なメッセージ。</span><span class="sxs-lookup"><span data-stu-id="ccc72-272">Customizable message that is displayed to the end user when first time setup is ready to start.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-273">TaskCancelTimeout</span><span class="sxs-lookup"><span data-stu-id="ccc72-273">TaskCancelTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-274">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-274">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-275">既定値 = 30</span><span class="sxs-lookup"><span data-stu-id="ccc72-275">Default=30</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-276">1回目のセットアップで、キャンセル操作のために仮想マシンからの応答を待機するタイムアウト値 (秒単位)。</span><span class="sxs-lookup"><span data-stu-id="ccc72-276">The time-out value, in seconds, that first time setup waits for a response from the virtual machine for a Cancel operation.</span></span> <span data-ttu-id="ccc72-277">範囲 = 0 ~ 2147483647</span><span class="sxs-lookup"><span data-stu-id="ccc72-277">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-278">TaskVMTurnOffTimeout</span><span class="sxs-lookup"><span data-stu-id="ccc72-278">TaskVMTurnOffTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-279">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-279">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-280">既定値 = 60</span><span class="sxs-lookup"><span data-stu-id="ccc72-280">Default=60</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-281">仮想マシンのシャットダウンが最初に実行されるときに設定されるタイムアウト値 (秒単位) です。</span><span class="sxs-lookup"><span data-stu-id="ccc72-281">The time-out value, in seconds, that first time setup waits for the virtual machine to shut down.</span></span> <span data-ttu-id="ccc72-282">範囲 = 0 ~ 2147483647</span><span class="sxs-lookup"><span data-stu-id="ccc72-282">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-283">アップグレードタイムアウト</span><span class="sxs-lookup"><span data-stu-id="ccc72-283">UpgradeTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-284">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-284">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-285">既定値 = 600</span><span class="sxs-lookup"><span data-stu-id="ccc72-285">Default=600</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-286">MED-V ゲストエージェントソフトウェアのアップグレードを試行するまでの時間 (秒単位) です。範囲 = 0 ~ 2147483647</span><span class="sxs-lookup"><span data-stu-id="ccc72-286">The time, in seconds, before an attempted upgrade of the MED-V Guest Agent software times out. Range = 0 to 2147483647.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="ccc72-287">UserExperience キー</span><span class="sxs-lookup"><span data-stu-id="ccc72-287">UserExperience Key</span></span>


<span data-ttu-id="ccc72-288">次の表では、HKEY \ _LOCAL \ _MACHINE \\ ¥ the _USER userexperience キーと、HKEY \ _CURRENT \ \ ソフトウェア¥のユーザーエクスペリエンスキーに関連付けられているレジストリ値について説明します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-288">The following table provides information about the registry values associated with the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Medv\\v2\\UserExperience key and the HKEY\_CURRENT\_USER\\Software\\Microsoft\\Medv\\v2\\UserExperience key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ccc72-289">名前</span><span class="sxs-lookup"><span data-stu-id="ccc72-289">Name</span></span></th>
<th align="left"><span data-ttu-id="ccc72-290">型</span><span class="sxs-lookup"><span data-stu-id="ccc72-290">Type</span></span></th>
<th align="left"><span data-ttu-id="ccc72-291">データ/既定</span><span class="sxs-lookup"><span data-stu-id="ccc72-291">Data/Default</span></span></th>
<th align="left"><span data-ttu-id="ccc72-292">説明</span><span class="sxs-lookup"><span data-stu-id="ccc72-292">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-293">Appはっこう Enabled</span><span class="sxs-lookup"><span data-stu-id="ccc72-293">AppPublishingEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-294">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-294">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-295">Default = 1</span><span class="sxs-lookup"><span data-stu-id="ccc72-295">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-296">ゲストからホストへのアプリケーションのパブリケーションが有効であるかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-296">Configures whether application publication from the guest to the host is enabled.</span></span>  <span data-ttu-id="ccc72-297">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="ccc72-297">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-298">0 = false: ゲストからホストへのアプリケーションの発行を無効にします。</span><span class="sxs-lookup"><span data-stu-id="ccc72-298">0 = false: Disables application publishing from the guest to the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-299">1 = true: ゲストからホストへのアプリケーションの発行を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ccc72-299">1 = true: Enables application publishing from the guest to the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-300">AudioSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="ccc72-300">AudioSharingEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-301">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-301">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-302">Default = 1</span><span class="sxs-lookup"><span data-stu-id="ccc72-302">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-303">ゲストとホストの間でオーディオ i/o デバイスの共有が有効になっているかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-303">Configures whether the sharing of the audio I/O device between the guest and the host is enabled.</span></span>  <span data-ttu-id="ccc72-304">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="ccc72-304">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-305">0 = false: ゲストとホストの間のオーディオ i/o デバイスの共有を無効にします。</span><span class="sxs-lookup"><span data-stu-id="ccc72-305">0 = false: Disables the sharing of the audio I/O device between the guest and the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-306">1 = true: ゲストとホストの間でのオーディオ i/o デバイスの共有を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ccc72-306">1 = true: Enables the sharing of the audio I/O device between the guest and the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-307">クリップボード共有の有効化</span><span class="sxs-lookup"><span data-stu-id="ccc72-307">ClipboardSharingEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-308">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-308">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-309">Default = 1</span><span class="sxs-lookup"><span data-stu-id="ccc72-309">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-310">ゲストとホストの間でクリップボードの共有が有効になっているかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-310">Configures whether the sharing of the Clipboard between the guest and the host is enabled.</span></span>  <span data-ttu-id="ccc72-311">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="ccc72-311">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-312">0 = false: ゲストとホストの間でクリップボードの共有を無効にします。</span><span class="sxs-lookup"><span data-stu-id="ccc72-312">0 = false: Disables the sharing of the Clipboard between the guest and the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-313">1 = true: ゲストとホストの間でクリップボードの共有を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ccc72-313">1 = true: Enables the sharing of the Clipboard between the guest and the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-314">/値のタイムアウト</span><span class="sxs-lookup"><span data-stu-id="ccc72-314">DialogTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-315">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-315">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-316">既定値 = 300</span><span class="sxs-lookup"><span data-stu-id="ccc72-316">Default=300</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-317">初回のセットアップ開始のダイアログがタイムアウトするまでの時間 (秒単位) です。範囲 = 0 ~ 2147483647</span><span class="sxs-lookup"><span data-stu-id="ccc72-317">The time, in seconds, before the first time setup Start Dialog times out. Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-318">HideVmTimeout</span><span class="sxs-lookup"><span data-stu-id="ccc72-318">HideVmTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-319">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-319">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-320">既定値 = 30</span><span class="sxs-lookup"><span data-stu-id="ccc72-320">Default=30</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-321">フルスクリーンの仮想マシンのウィンドウが、長いログオン試行中にエンドユーザーから非表示になっているタイムアウト値 (分単位)。</span><span class="sxs-lookup"><span data-stu-id="ccc72-321">The time-out value, in minutes, that the full-screen virtual machine window is hidden from the end user during a long logon attempt.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-322">LogonStartEnabled</span><span class="sxs-lookup"><span data-stu-id="ccc72-322">LogonStartEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-323">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-323">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-324">Default = 1</span><span class="sxs-lookup"><span data-stu-id="ccc72-324">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-325">エンドユーザーがデスクトップにログオンしたとき、または最初のゲストアプリケーションが開始されたときにゲストを開始するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-325">Configures whether the guest should be started when the end user logs on to the desktop or when the first guest application is started.</span></span>  <span data-ttu-id="ccc72-326">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="ccc72-326">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-327">0 = false: 最初のゲストアプリケーションが開始されたときにゲストが開始されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-327">0 = false: The guest is started when the first guest application is started.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-328">1 = true: エンドユーザーがデスクトップにログオンしたときにゲストが開始されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-328">1 = true: The guest is started when the end user logs on to the desktop.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-329">プリンター共有の有効化</span><span class="sxs-lookup"><span data-stu-id="ccc72-329">PrinterSharingEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-330">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-330">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-331">Default = 1</span><span class="sxs-lookup"><span data-stu-id="ccc72-331">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-332">ゲストとホストの間のプリンターの共有を有効にするかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-332">Configures whether the sharing of printers between the guest and the host is enabled.</span></span>  <span data-ttu-id="ccc72-333">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="ccc72-333">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-334">0 = false: ゲストとホストの間のプリンターの共有を無効にします。</span><span class="sxs-lookup"><span data-stu-id="ccc72-334">0 = false: Disables the sharing of printers between the guest and the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-335">1 = true: ゲストとホストの間でプリンターの共有を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ccc72-335">1 = true: Enables the sharing of printers between the guest and the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-336">RebootAbsoluteDelayTimeout</span><span class="sxs-lookup"><span data-stu-id="ccc72-336">RebootAbsoluteDelayTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-337">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-337">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-338">既定値 = 1440</span><span class="sxs-lookup"><span data-stu-id="ccc72-338">Default=1440</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-339">初回のセットアップで再起動が待機するタイムアウト値 (分単位) です。</span><span class="sxs-lookup"><span data-stu-id="ccc72-339">The time-out value, in minutes, that first time setup waits for a restart.</span></span> <span data-ttu-id="ccc72-340">範囲 = 0 ~ 2147483647</span><span class="sxs-lookup"><span data-stu-id="ccc72-340">Range = 0 to 2147483647.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-341">RedirectUrls</span><span class="sxs-lookup"><span data-stu-id="ccc72-341">RedirectUrls</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-342">MULTI_SZ</span><span class="sxs-lookup"><span data-stu-id="ccc72-342">MULTI_SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-343">指定した URL リスト</span><span class="sxs-lookup"><span data-stu-id="ccc72-343">Specified URL list</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-344">ホストからゲストにリダイレクトされる Url のリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-344">Specifies a list of URLs to be redirected from the host to the guest.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-345">SmartCardLogonEnabled</span><span class="sxs-lookup"><span data-stu-id="ccc72-345">SmartCardLogonEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-346">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-346">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-347">既定値 = 0</span><span class="sxs-lookup"><span data-stu-id="ccc72-347">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-348">スマートカードを使用して、ユーザーを MED-V で認証できるかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-348">Configures whether smart cards can be used to authenticate users to MED-V.</span></span> <span data-ttu-id="ccc72-349">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="ccc72-349">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-350">0 = false: スマートカードは、MED-V を使用してエンドユーザーを認証しません。</span><span class="sxs-lookup"><span data-stu-id="ccc72-350">0 = false: Does not let Smart Cards authenticate end users to MED-V.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-351">1 = true: スマートカードがエンドユーザーを MED-V に対して認証できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ccc72-351">1 = true: Lets Smart Cards authenticate end users to MED-V.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ccc72-352">重要</span><span class="sxs-lookup"><span data-stu-id="ccc72-352">Important</span></span></strong><br/><p><span data-ttu-id="ccc72-353">SmartCardLogonEnabled と CredentialCacheEnabled が両方とも有効になっている場合は、SmartCardLogonEnabled が CredentialCacheEnabled をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="ccc72-353">If SmartCardLogonEnabled and CredentialCacheEnabled are both enabled, SmartCardLogonEnabled overrides CredentialCacheEnabled.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-354">SmartCardSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="ccc72-354">SmartCardSharingEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-355">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-355">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-356">Default = 1</span><span class="sxs-lookup"><span data-stu-id="ccc72-356">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-357">ゲストとホストの間でスマートカードの共有を有効にするかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-357">Configures whether the sharing of Smart Cards between the guest and the host is enabled.</span></span>  <span data-ttu-id="ccc72-358">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="ccc72-358">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-359">0 = false: ゲストとホストの間でスマートカードの共有を無効にします。</span><span class="sxs-lookup"><span data-stu-id="ccc72-359">0 = false: Disables the sharing of Smart Cards between the guest and the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-360">1 = true: ゲストとホストの間でスマートカードの共有を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ccc72-360">1 = true: Enables the sharing of Smart Cards between the guest and the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-361">Usbデバイスの使用を許可する</span><span class="sxs-lookup"><span data-stu-id="ccc72-361">USBDeviceSharingEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-362">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-362">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-363">Default = 1</span><span class="sxs-lookup"><span data-stu-id="ccc72-363">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-364">ゲストとホストの間で USB デバイスの共有を有効にするかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-364">Configures whether the sharing of USB devices between the guest and the host is enabled.</span></span>  <span data-ttu-id="ccc72-365">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="ccc72-365">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-366">0 = false: ゲストとホスト間の USB デバイスの共有を無効にします。</span><span class="sxs-lookup"><span data-stu-id="ccc72-366">0 = false: Disables the sharing of USB devices between the guest and the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-367">1 = true: ゲストとホスト間での USB デバイスの共有を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ccc72-367">1 = true: Enables the sharing of USB devices between the guest and the host.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="ccc72-368">VM キー</span><span class="sxs-lookup"><span data-stu-id="ccc72-368">VM Key</span></span>


<span data-ttu-id="ccc72-369">次の表では、HKEY \ _LOCAL \ _MACHINE ¥のように、または、hkey \ _CURRENT \ _USER ¥という値に関連付けられているレジストリ値に関する情報を提供しています。</span><span class="sxs-lookup"><span data-stu-id="ccc72-369">The following table provides information about the registry values associated with the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Medv\\v2\\VM key and the HKEY\_CURRENT\_USER\\Software\\Microsoft\\Medv\\v2\\VM key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ccc72-370">名前</span><span class="sxs-lookup"><span data-stu-id="ccc72-370">Name</span></span></th>
<th align="left"><span data-ttu-id="ccc72-371">型</span><span class="sxs-lookup"><span data-stu-id="ccc72-371">Type</span></span></th>
<th align="left"><span data-ttu-id="ccc72-372">データ/既定</span><span class="sxs-lookup"><span data-stu-id="ccc72-372">Data/Default</span></span></th>
<th align="left"><span data-ttu-id="ccc72-373">説明</span><span class="sxs-lookup"><span data-stu-id="ccc72-373">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-374">CloseAction</span><span class="sxs-lookup"><span data-stu-id="ccc72-374">CloseAction</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-375">SZ</span><span class="sxs-lookup"><span data-stu-id="ccc72-375">SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-376">Default = HIBERNATE</span><span class="sxs-lookup"><span data-stu-id="ccc72-376">Default=HIBERNATE</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-377">実行されている最後のアプリケーションが終了した後に仮想マシンで実行されるアクション。</span><span class="sxs-lookup"><span data-stu-id="ccc72-377">The action that the virtual machine performs after the last application that is running is closed.</span></span> <span data-ttu-id="ccc72-378">LogonStartEnabled 値が有効になっている場合は、この設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-378">This setting is ignored if the LogonStartEnabled value is enabled.</span></span> <span data-ttu-id="ccc72-379">以下のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="ccc72-379">Possible options are as follows:</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="ccc72-380">休止状態 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="ccc72-380">HIBERNATE</strong> .</span></span> <span data-ttu-id="ccc72-381">このオプションは、仮想マシンで使用されているすべての物理リソース (メモリや CPU など) を解放し、実行されているすべてのアプリケーションと操作の状態を保存します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-381">This option releases all physical resources that the virtual machine is using, such as memory and CPU, and saves the state of all running applications and operations.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="ccc72-382">シャットダウン </strong> します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-382">SHUTDOWN</strong> .</span></span> <span data-ttu-id="ccc72-383">このオプションでは、ゲストオペレーティングシステムを安全にシャットダウンし、仮想マシンで使用されているすべての物理リソース (メモリや CPU など) を解放します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-383">This option shuts down the guest operating system safely and then releases all physical resources that the virtual machine is using, such as memory and CPU.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="ccc72-384">オフに </strong> します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-384">TURN-OFF</strong>.</span></span> <span data-ttu-id="ccc72-385">このオプションをオンにすると、power button をオフにするか、物理コンピューターの電源コードを引き出すのと同じように、データが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ccc72-385">This option can cause data loss because it is the same as turning off the power button or pulling out the power cord on a physical computer.</span></span> <span data-ttu-id="ccc72-386">このオプションは、他の2つのオプションのいずれかを使用できない場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-386">Use this option only if you cannot use one of the other two options.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-387">GuestMemFromHostMem</span><span class="sxs-lookup"><span data-stu-id="ccc72-387">GuestMemFromHostMem</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-388">MULTI_SZ</span><span class="sxs-lookup"><span data-stu-id="ccc72-388">MULTI_SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-389">378、512、1024、1536、2048</span><span class="sxs-lookup"><span data-stu-id="ccc72-389">378, 512, 1024, 1536, 2048</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-390">ゲストのメモリ (MB) 値の一覧。</span><span class="sxs-lookup"><span data-stu-id="ccc72-390">A list of memory (MB) values for the guest.</span></span> <span data-ttu-id="ccc72-391">この値は、ゲストが使用できる RAM の量を決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-391">This value is used to determine how much RAM is available to the guest.</span></span> <span data-ttu-id="ccc72-392">HostMemToGuestMem と組み合わせると、参照テーブルが作成され、ゲスト仮想マシンに割り当てる RAM の量を決定します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-392">Combined with HostMemToGuestMem, a lookup table is created to determine how much RAM to allocate on the guest virtual machine.</span></span> <span data-ttu-id="ccc72-393">指定可能な値は、128から3712までです。</span><span class="sxs-lookup"><span data-stu-id="ccc72-393">Possible values can be from 128 to 3712.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-394">GuestUpdateDuration</span><span class="sxs-lookup"><span data-stu-id="ccc72-394">GuestUpdateDuration</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-395">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-395">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-396">既定値 = 240</span><span class="sxs-lookup"><span data-stu-id="ccc72-396">Default=240</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-397">ゲストが自動的に更新されないようにするには、GuestUpdateTime 値で指定された時刻から開始するまでの時間を分単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-397">The number of minutes that MED-V should keep the guest awake for automatic updating, starting at the time specified in the GuestUpdateTime value.</span></span> <span data-ttu-id="ccc72-398">範囲 = 0 ~ 1440</span><span class="sxs-lookup"><span data-stu-id="ccc72-398">Range = 0 to 1440.</span></span> <span data-ttu-id="ccc72-399">この値をゼロ (0) に設定すると、ゲストの修正プログラム機能は無効になります。</span><span class="sxs-lookup"><span data-stu-id="ccc72-399">Setting this value to zero (0) disables the guest patching functionality.</span></span></p>
<p><span data-ttu-id="ccc72-400">自動更新のゲストの更新プログラムの詳細については、「 <a href="managing-automatic-updates-for-med-v-workspaces.md" data-raw-source="[Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md)"> Med-v ワークスペースの自動更新を管理する」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="ccc72-400">For more information about guest patching for automatic updating, see <a href="managing-automatic-updates-for-med-v-workspaces.md" data-raw-source="[Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md)">Managing Automatic Updates for MED-V Workspaces</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-401">GuestUpdateTime</span><span class="sxs-lookup"><span data-stu-id="ccc72-401">GuestUpdateTime</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-402">SZ</span><span class="sxs-lookup"><span data-stu-id="ccc72-402">SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-403">既定値 = 00:00</span><span class="sxs-lookup"><span data-stu-id="ccc72-403">Default=00:00</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-404">MED-V が自動更新のためにゲストをスリープ状態にする曜日と時間 (分)。24時間制の標準を使用します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-404">The hour and minute each day when MED-V should wake up the guest for automatic updating, by using the 24-hour clock standard.</span></span> <span data-ttu-id="ccc72-405">HH: MM の形式で時刻を指定します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-405">Specify the time in the format HH:MM</span></span>  </p>
<p><span data-ttu-id="ccc72-406">自動更新のゲストの更新プログラムの詳細については、「 <a href="managing-automatic-updates-for-med-v-workspaces.md" data-raw-source="[Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md)"> Med-v ワークスペースの自動更新を管理する」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="ccc72-406">For more information about guest patching for automatic updating, see <a href="managing-automatic-updates-for-med-v-workspaces.md" data-raw-source="[Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md)">Managing Automatic Updates for MED-V Workspaces</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-407">HostMemToGuestMem</span><span class="sxs-lookup"><span data-stu-id="ccc72-407">HostMemToGuestMem</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-408">MULTI_SZ</span><span class="sxs-lookup"><span data-stu-id="ccc72-408">MULTI_SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-409">1024、2048、4096、8192、16384</span><span class="sxs-lookup"><span data-stu-id="ccc72-409">1024, 2048, 4096, 8192, 16384</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-410">ホストで利用可能な RAM によって決定される、ゲストのメモリ (MB) 値の一覧。</span><span class="sxs-lookup"><span data-stu-id="ccc72-410">A list of memory (MB) values for the guest, determined by the RAM available on the host.</span></span> <span data-ttu-id="ccc72-411">GuestMemFromHostMem と組み合わせると、参照テーブルが作成され、ゲスト仮想マシンに割り当てる RAM の量を決定します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-411">Combined with GuestMemFromHostMem, a lookup table is created to determine how much RAM to allocate on the guest virtual machine.</span></span> <span data-ttu-id="ccc72-412">指定可能な値は、1024から16384までです。</span><span class="sxs-lookup"><span data-stu-id="ccc72-412">Possible values can be from 1024 to 16384.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-413">HostMemToGuestMemCalcEnabled</span><span class="sxs-lookup"><span data-stu-id="ccc72-413">HostMemToGuestMemCalcEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-414">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-414">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-415">Default = 1</span><span class="sxs-lookup"><span data-stu-id="ccc72-415">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-416">ゲストに割り当てられているメモリがホスト上にあるメモリから計算されるかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-416">Configures whether the memory allocated for the guest is calculated from the memory present on the host.</span></span>  <span data-ttu-id="ccc72-417">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="ccc72-417">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-418">0 = false: ゲストに割り当てられているメモリは、ホスト上にあるメモリから計算されません。</span><span class="sxs-lookup"><span data-stu-id="ccc72-418">0 = false: The memory allocated for the guest is not calculated from the memory present on the host.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-419">1 = true: ゲストに割り当てられているメモリは、ホスト上にあるメモリから計算されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-419">1 = true: The memory allocated for the guest is calculated from the memory present on the host.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-420">メモリ</span><span class="sxs-lookup"><span data-stu-id="ccc72-420">Memory</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-421">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-421">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-422">既定値 = 512</span><span class="sxs-lookup"><span data-stu-id="ccc72-422">Default=512</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-423">ゲスト仮想マシンに割り当てる必要がある RAM (MB)。</span><span class="sxs-lookup"><span data-stu-id="ccc72-423">The RAM (MB) that should be allocated for the guest virtual machine.</span></span> <span data-ttu-id="ccc72-424">HostMemToGuestMemEnabled 設定が有効になっている場合、この設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-424">This setting is ignored if the HostMemToGuestMemEnabled setting is enabled.</span></span> <span data-ttu-id="ccc72-425">範囲 = 128 ~ 2048</span><span class="sxs-lookup"><span data-stu-id="ccc72-425">Range=128 to 2048.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-426">MultiUserEnabled</span><span class="sxs-lookup"><span data-stu-id="ccc72-426">MultiUserEnabled</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-427">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-427">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-428">既定値 = 0</span><span class="sxs-lookup"><span data-stu-id="ccc72-428">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-429">複数のユーザーが同じ MED-V ワークスペースを共有するかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-429">Configures whether multiple users share the same MED-V workspace.</span></span>  <span data-ttu-id="ccc72-430">0 = false;1 = true。</span><span class="sxs-lookup"><span data-stu-id="ccc72-430">0 = false; 1 = true.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-431">0 = false: 複数のユーザーが、同じ MED-V ワークスペースを共有していません。</span><span class="sxs-lookup"><span data-stu-id="ccc72-431">0 = false: Multiple users do not share the same MED-V workspace.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-432">1 = true: 複数のユーザーが同じ MED-V ワークスペースを共有します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-432">1 = true: Multiple users share the same MED-V workspace.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ccc72-433">NetworkingMode</span><span class="sxs-lookup"><span data-stu-id="ccc72-433">NetworkingMode</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-434">SZ</span><span class="sxs-lookup"><span data-stu-id="ccc72-434">SZ</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-435">Default = NAT</span><span class="sxs-lookup"><span data-stu-id="ccc72-435">Default=NAT</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-436">ゲストで使用されているネットワーク接続の種類。</span><span class="sxs-lookup"><span data-stu-id="ccc72-436">The kind of network connection used on the guest.</span></span> <span data-ttu-id="ccc72-437">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-437">Possible values are as follows:</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="ccc72-438">ブリッジ </strong> 。</span><span class="sxs-lookup"><span data-stu-id="ccc72-438">Bridged</strong>.</span></span> <span data-ttu-id="ccc72-439">MED-V には独自のネットワークアドレスがあります。通常は DHCP 経由で取得します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-439">MED-V has its own network address, typically obtained through DHCP.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong><span data-ttu-id="ccc72-440">NAT </strong> 。</span><span class="sxs-lookup"><span data-stu-id="ccc72-440">NAT</strong>.</span></span> <span data-ttu-id="ccc72-441">MED-V は、ネットワークアドレス変換 (NAT) を使って、発信トラフィック用にホスト&#39;s IP を共有します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-441">MED-V uses Network Address Translation (NAT) to share the host&#39;s IP for outgoing traffic.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-442">TaskTimeout</span><span class="sxs-lookup"><span data-stu-id="ccc72-442">TaskTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-443">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-443">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-444">既定値 = 600</span><span class="sxs-lookup"><span data-stu-id="ccc72-444">Default=600</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-445">通常のタイムアウト値は秒で、MED-V は、タスクが完了するまで待機します。たとえば、再起動やシャットダウンなどの処理が実行されます。</span><span class="sxs-lookup"><span data-stu-id="ccc72-445">A general time-out value, in seconds, that MED-V waits for a task to be completed, such as restarting and shutting down.</span></span> <span data-ttu-id="ccc72-446">範囲 = 0 ~ 2147483647</span><span class="sxs-lookup"><span data-stu-id="ccc72-446">Range = 0 to 2147483647.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="ccc72-447">ゲストのレジストリ設定</span><span class="sxs-lookup"><span data-stu-id="ccc72-447">Guest Registry Settings</span></span>


<span data-ttu-id="ccc72-448">このセクションには、構成可能な MED-V ゲストのレジストリキーの一覧とその使用方法が記載されています。</span><span class="sxs-lookup"><span data-stu-id="ccc72-448">This section lists the configurable MED-V guest registry keys and explains their uses.</span></span>

### <span data-ttu-id="ccc72-449">v2</span><span class="sxs-lookup"><span data-stu-id="ccc72-449">v2</span></span>

<span data-ttu-id="ccc72-450">次の表では、HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Medv\\v2\\ キーに関連付けられているゲストレジストリ値について説明します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-450">The following table provides information about the guest registry value associated with the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Medv\\v2\\ key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ccc72-451">名前</span><span class="sxs-lookup"><span data-stu-id="ccc72-451">Name</span></span> </th>
<th align="left"><span data-ttu-id="ccc72-452">型</span><span class="sxs-lookup"><span data-stu-id="ccc72-452">Type</span></span> </th>
<th align="left"><span data-ttu-id="ccc72-453">データ/既定</span><span class="sxs-lookup"><span data-stu-id="ccc72-453">Data/Default</span></span> </th>
<th align="left"><span data-ttu-id="ccc72-454">説明</span><span class="sxs-lookup"><span data-stu-id="ccc72-454">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ccc72-455">EnableGPWorkarounds</span><span class="sxs-lookup"><span data-stu-id="ccc72-455">EnableGPWorkarounds</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccc72-456">DWORD</span><span class="sxs-lookup"><span data-stu-id="ccc72-456">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-457">Default = 1</span><span class="sxs-lookup"><span data-stu-id="ccc72-457">Default=1</span></span> </p></td>
<td align="left"><p><span data-ttu-id="ccc72-458">キーバッファーポリシーの読み取りと GroupPolicyMinTransferRate を MED-V で処理する方法を構成します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-458">Configures how MED-V handles the keys BufferPolicyReads and GroupPolicyMinTransferRate.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ccc72-459">既定では、MED-V は以下のキーを設定します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-459">By default, MED-V sets these keys as follows:</span></span></p>
<p><span data-ttu-id="ccc72-460">BufferPolicyReads = 1 と GroupPolicyMinTransferRate = 0。</span><span class="sxs-lookup"><span data-stu-id="ccc72-460">BufferPolicyReads=1 and GroupPolicyMinTransferRate=0.</span></span></p>
<p><span data-ttu-id="ccc72-461">必要に応じて EnableGPWorkarounds キーを作成し、MED-V で BufferPolicyReads と GroupPolicyMinTransferRate の既定の設定を変更しない場合は、このキーを0に設定します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-461">Create the EnableGPWorkarounds  key, if it is necessary, and set the key to zero if you do not want MED-V to change the default settings of BufferPolicyReads and GroupPolicyMinTransferRate.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ccc72-462">注</span><span class="sxs-lookup"><span data-stu-id="ccc72-462">Note</span></span></strong><br/><p><span data-ttu-id="ccc72-463">MED-V ワークスペースが NAT モードで実行されている場合、EnableGPWorkarounds は、レジストリキーのバッファーポリシーの読み取りと GroupPolicyMinTransferRate に影響します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-463">If your MED-V workspace is running in NAT mode, EnableGPWorkarounds affects the registry keys BufferPolicyReads and GroupPolicyMinTransferRate.</span></span> <span data-ttu-id="ccc72-464">MED-V ワークスペースがブリッジモードで実行されている場合、EnableGPWorkarounds はレジストリキーバッファーの読み取りにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-464">If your MED-V workspace is running in BRIDGED mode, EnableGPWorkarounds only affects the registry key BufferPolicyReads.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="ccc72-465">1 = true: MED-V は、キーバッファーポリシーの読み取り = 1 と GroupPolicyMinTransferRate = 0 (NAT モードで実行されている場合)、または BufferPolicyReads = 1 だけ (ブリッジモードで実行されている場合) を設定します。</span><span class="sxs-lookup"><span data-stu-id="ccc72-465">1=true: MED-V sets the keys BufferPolicyReads=1 and GroupPolicyMinTransferRate=0 (if running in NAT mode) or just BufferPolicyReads=1 (if running in BRIDGED mode).</span></span></p>
<p><span data-ttu-id="ccc72-466">0 = false: MED-V は、キーバッファーポリシーの読み取りと GroupPolicyMinTransferRate に変更を加えません。</span><span class="sxs-lookup"><span data-stu-id="ccc72-466">0=false: MED-V does not make any changes to the keys BufferPolicyReads and GroupPolicyMinTransferRate.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="ccc72-467">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ccc72-467">Related topics</span></span>


[<span data-ttu-id="ccc72-468">MED-V ワークスペース アプリケーションを管理する</span><span class="sxs-lookup"><span data-stu-id="ccc72-468">Manage MED-V Workspace Applications</span></span>](manage-med-v-workspace-applications.md)

[<span data-ttu-id="ccc72-469">MED-V の URL リダイレクトの管理</span><span class="sxs-lookup"><span data-stu-id="ccc72-469">Manage MED-V URL Redirection</span></span>](manage-med-v-url-redirection.md)

[<span data-ttu-id="ccc72-470">MED-V ワークスペースの設定を管理する</span><span class="sxs-lookup"><span data-stu-id="ccc72-470">Manage MED-V Workspace Settings</span></span>](manage-med-v-workspace-settings.md)









