---
title: グループポリシーオブジェクトを使用して UE-V 2. x を構成する
description: グループポリシーオブジェクトを使用して UE-V 2. x を構成する
author: dansimp
ms.assetid: 2bb55834-26ee-4f19-9860-dfdf3c797143
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bdff63b948752b9bec83e77e275f1cb20a384463
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824424"
---
# <span data-ttu-id="3ac1e-103">グループポリシーオブジェクトを使用して UE-V 2. x を構成する</span><span class="sxs-lookup"><span data-stu-id="3ac1e-103">Configuring UE-V 2.x with Group Policy Objects</span></span>


<span data-ttu-id="3ac1e-104">一部の Microsoft User Experience Virtualization (UE-V) 2.0、2.1、2.1 SP1 グループポリシー設定は、コンピューターに対して定義することができ、その他のグループポリシー設定をユーザーに対して定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-104">Some Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 Group Policy settings can be defined for computers, and other Group Policy settings can be defined for users.</span></span> <span data-ttu-id="3ac1e-105">UE-V グループポリシー ADMX ファイルをインストールする方法については、「 [ue-v 2 グループポリシーの Admx テンプレートのインストール](https://technet.microsoft.com/library/dn458891.aspx#admx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-105">For information about how to install UE-V Group Policy ADMX files, see [Installing the UE-V 2 Group Policy ADMX Templates](https://technet.microsoft.com/library/dn458891.aspx#admx).</span></span>

<span data-ttu-id="3ac1e-106">UE-V 用に次のポリシー設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-106">The following policy settings can be configured for UE-V.</span></span>

**<span data-ttu-id="3ac1e-107">グループ ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="3ac1e-107">Group Policy settings</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3ac1e-108">グループポリシー設定の名前</span><span class="sxs-lookup"><span data-stu-id="3ac1e-108">Group Policy setting name</span></span></th>
<th align="left"><span data-ttu-id="3ac1e-109">ターゲット</span><span class="sxs-lookup"><span data-stu-id="3ac1e-109">Target</span></span></th>
<th align="left"><span data-ttu-id="3ac1e-110">グループポリシーの設定の説明</span><span class="sxs-lookup"><span data-stu-id="3ac1e-110">Group Policy setting description</span></span></th>
<th align="left"><span data-ttu-id="3ac1e-111">構成オプション</span><span class="sxs-lookup"><span data-stu-id="3ac1e-111">Configuration options</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ac1e-112">連絡するリンクテキスト</span><span class="sxs-lookup"><span data-stu-id="3ac1e-112">Contact IT Link Text</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-113">コンピューターのみ</span><span class="sxs-lookup"><span data-stu-id="3ac1e-113">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-114">このグループポリシー設定では、会社設定センターの [連絡先 IT URL] ハイパーリンクのテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-114">This Group Policy setting specifies the text of the Contact IT URL hyperlink in the Company Settings Center.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-115">このグループポリシー設定を有効にした場合、[会社設定センター] の URL へのリンクに、指定したテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-115">If you enable this Group Policy setting, the Company Settings Center displays the specified text in the link to the Contact IT URL.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ac1e-116">お問い合わせ先の URL</span><span class="sxs-lookup"><span data-stu-id="3ac1e-116">Contact IT URL</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-117">コンピューターのみ</span><span class="sxs-lookup"><span data-stu-id="3ac1e-117">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-118">このグループポリシー設定では、会社設定センターの [連絡先 IT] リンクの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-118">This Group Policy setting specifies the URL for the Contact IT link in the Company Settings Center.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-119">この設定を有効にした場合、会社設定センターでは、指定した URL へのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-119">If you enable this setting, the Company Settings Center Contact IT text links to the specified URL.</span></span> <span data-ttu-id="3ac1e-120">Link は、HTTP や mailto などの標準プロトコルのいずれでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-120">The link can be of any standard protocol, such as HTTP or mailto.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ac1e-121">同期プロバイダーを使用しない</span><span class="sxs-lookup"><span data-stu-id="3ac1e-121">Do not use the sync provider</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-122">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="3ac1e-122">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-123">このグループポリシー設定を使用すると、UE-V が同期プロバイダー機能を使用するかどうかを構成できます。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-123">By using this Group Policy setting, you can configure whether UE-V uses the sync provider feature.</span></span> <span data-ttu-id="3ac1e-124">このポリシー設定では、ユーザー設定のインポートが延期された場合に通知を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-124">This policy setting also lets you enable notification to appear when the import of user settings is delayed.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-125">この設定を有効にして、UE-V Agent が同期プロバイダーを使用しないように設定します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-125">Enable this setting to configure the UE-V Agent not to use the sync provider.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ac1e-126">初めて使用するときの通知</span><span class="sxs-lookup"><span data-stu-id="3ac1e-126">First Use Notification</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-127">コンピューターのみ</span><span class="sxs-lookup"><span data-stu-id="3ac1e-127">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-128">このグループポリシー設定では、UE-V の場合に表示される通知領域の通知を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-128">This Group Policy setting enables a notification in the notification area that appears when the UE-V</span></span></p>
<p><span data-ttu-id="3ac1e-129">エージェントは初めて実行されます。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-129">agent runs for the first time.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-130">既定値は有効です。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-130">The default is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ac1e-131">Windows のローミングの設定</span><span class="sxs-lookup"><span data-stu-id="3ac1e-131">Roam Windows settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-132">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="3ac1e-132">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-133">このグループポリシー設定では、Windows 設定の同期を構成します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-133">This Group Policy setting configures the synchronization of Windows settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-134">コンピューター間で同期する Windows の設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-134">Select which Windows settings synchronize between computers.</span></span></p>
<p><span data-ttu-id="3ac1e-135">既定では、Windows のテーマ、デスクトップの設定、および簡単操作の設定は、同じオペレーティングシステムバージョンのコンピューター間で設定を同期します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-135">By default, Windows themes, desktop settings, and Ease of Access settings synchronize settings between computers of the same operating system version.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ac1e-136">設定パッケージサイズの警告しきい値</span><span class="sxs-lookup"><span data-stu-id="3ac1e-136">Settings package size warning threshold</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-137">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="3ac1e-137">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-138">このグループポリシー設定では、設定パッケージのファイルサイズが定義されたしきい値に達したときに報告するように UE-V Agent を構成できます。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-138">This Group Policy setting lets you configure the UE-V Agent to report when a settings package file size reaches a defined threshold.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-139">設定パッケージサイズの優先しきい値をキロバイト (KB) で指定します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-139">Specify the preferred threshold for settings package sizes in kilobytes (KB).</span></span></p>
<p><span data-ttu-id="3ac1e-140">既定では、UE-V Agent にはパッケージファイルサイズのしきい値はありません。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-140">By default, the UE-V Agent does not have a package file size threshold.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ac1e-141">設定の記憶域のパス</span><span class="sxs-lookup"><span data-stu-id="3ac1e-141">Settings storage path</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-142">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="3ac1e-142">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-143">このグループポリシー設定では、ユーザー設定を保存する場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-143">This Group Policy setting configures where the user settings are to be stored.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-144">汎用名前付け規則 (UNC) のパスと \Server\SettingsShare%username%. などの変数を入力します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-144">Enter a Universal Naming Convention (UNC) path and variables such as \Server\SettingsShare%username%.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ac1e-145">設定テンプレートカタログのパス</span><span class="sxs-lookup"><span data-stu-id="3ac1e-145">Settings template catalog path</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-146">コンピューターのみ</span><span class="sxs-lookup"><span data-stu-id="3ac1e-146">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-147">このグループポリシー設定では、カスタム設定の場所テンプレートが保存されている場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-147">This Group Policy setting configures where custom settings location templates are stored.</span></span> <span data-ttu-id="3ac1e-148">このポリシー設定では、UE-V Agent と共にインストールされた既定の Microsoft テンプレートの代わりにカタログを使用するかどうかも構成します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-148">This policy setting also configures whether the catalog is to be used to replace the default Microsoft templates that are installed with the UE-V Agent.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-149">\Server\TemplateShare やコンピューター上のフォルダーの場所など、汎用名前付け規則 (UNC) パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-149">Enter a Universal Naming Convention (UNC) path such as \Server\TemplateShare or a folder location on the computer.</span></span></p>
<p><span data-ttu-id="3ac1e-150">既定の Microsoft テンプレートを置き換えるには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-150">Select the check box to replace the default Microsoft templates.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ac1e-151">従量制課金接続で設定を同期する</span><span class="sxs-lookup"><span data-stu-id="3ac1e-151">Sync settings over metered connections</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-152">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="3ac1e-152">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-153">このグループポリシー設定では、UE-V が従量制課金接続で設定を同期するかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-153">This Group Policy setting defines whether UE-V synchronizes settings over metered connections.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-154">既定では、UE-V Agent で従量制課金接続で設定を同期しません。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-154">By default, the UE-V Agent does not synchronize settings over a metered connection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ac1e-155">ローミング中の従量制課金接続で設定を同期する</span><span class="sxs-lookup"><span data-stu-id="3ac1e-155">Sync settings over metered connections even when roaming</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-156">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="3ac1e-156">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-157">このグループポリシー設定では、データ接続がローミングモードの場合など、自宅のプロバイダーネットワーク以外の従量制課金接続で、UE-V が設定を同期するかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-157">This Group Policy setting defines whether UE-V synchronizes settings over metered connections outside of the home provider network, for example, when the data connection is in roaming mode.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-158">既定では、UE-V は、従量制課金接続の設定をローミングモードでは同期しません。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-158">By default, UE-V does not synchronize settings over a metered connection when it is in roaming mode.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ac1e-159">同期タイムアウト</span><span class="sxs-lookup"><span data-stu-id="3ac1e-159">Synchronization timeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-160">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="3ac1e-160">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-161">このグループポリシー設定では、コンピューターがリモート設定の場所からユーザー設定を取得したときにタイムアウトするまでの時間 (ミリ秒単位) を構成します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-161">This Group Policy setting configures the number of milliseconds that the computer waits before a time-out when it retrieves user settings from the remote settings location.</span></span> <span data-ttu-id="3ac1e-162">リモート記憶域の場所が利用できず、ユーザーが同期プロバイダーを使用していない場合は、アプリケーションの開始がこのミリ秒単位で遅延します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-162">If the remote storage location is unavailable, and the user does not use the sync provider, the application start is delayed by this many milliseconds.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-163">優先同期のタイムアウト (ミリ秒単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-163">Specify the preferred synchronization time-out in milliseconds.</span></span> <span data-ttu-id="3ac1e-164">既定値は2000ミリ秒です。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-164">The default value is 2000 milliseconds.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ac1e-165">トレイアイコン</span><span class="sxs-lookup"><span data-stu-id="3ac1e-165">Tray Icon</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-166">コンピューターのみ</span><span class="sxs-lookup"><span data-stu-id="3ac1e-166">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-167">このグループポリシー設定では、User Experience Virtualization (UE-V) トレイアイコンを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-167">This Group Policy setting enables the User Experience Virtualization (UE-V) tray icon.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-168">既定値は有効です。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-168">The default is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ac1e-169">User Experience Virtualization (UE-V) を使用する</span><span class="sxs-lookup"><span data-stu-id="3ac1e-169">Use User Experience Virtualization (UE-V)</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-170">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="3ac1e-170">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-171">このグループポリシー設定では、User Experience Virtualization (UE-V) を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-171">This Group Policy setting lets you enable or disable User Experience Virtualization (UE-V).</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-172">このグループポリシー設定を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-172">Enable or disable this Group Policy setting.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="3ac1e-173">**注** さらに、グループポリシー設定は、多くのデスクトップアプリケーションや Windows アプリで利用できます。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-173">**Note** In addition, Group Policy settings are available for many desktop applications and Windows apps.</span></span> <span data-ttu-id="3ac1e-174">これらの設定を使って、特定のアプリケーションの設定の同期を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-174">You can use these settings to enable or disable settings synchronization for specific applications.</span></span>

 

**<span data-ttu-id="3ac1e-175">Windows アプリのグループポリシー設定</span><span class="sxs-lookup"><span data-stu-id="3ac1e-175">Windows App Group Policy settings</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3ac1e-176">グループポリシー設定の名前</span><span class="sxs-lookup"><span data-stu-id="3ac1e-176">Group Policy setting name</span></span></th>
<th align="left"><span data-ttu-id="3ac1e-177">ターゲット</span><span class="sxs-lookup"><span data-stu-id="3ac1e-177">Target</span></span></th>
<th align="left"><span data-ttu-id="3ac1e-178">グループポリシーの設定の説明</span><span class="sxs-lookup"><span data-stu-id="3ac1e-178">Group Policy setting description</span></span></th>
<th align="left"><span data-ttu-id="3ac1e-179">構成オプション</span><span class="sxs-lookup"><span data-stu-id="3ac1e-179">Configuration options</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ac1e-180">Windows アプリを同期しない</span><span class="sxs-lookup"><span data-stu-id="3ac1e-180">Do not synchronize Windows Apps</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-181">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="3ac1e-181">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-182">このグループポリシー設定では、UE-V Agent で Windows アプリの設定を同期するかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-182">This Group Policy setting defines whether the UE-V Agent synchronizes settings for Windows apps.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-183">既定では、Windows アプリを同期します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-183">The default is to synchronize Windows apps.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3ac1e-184">Windows アプリの一覧</span><span class="sxs-lookup"><span data-stu-id="3ac1e-184">Windows App List</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-185">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="3ac1e-185">Computer and User</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-186">この設定では、Windows アプリとその状態のファミリーパッケージ名が一覧表示されます。これは、UE-V がアプリの設定を同期するかどうかを明示的に示しています。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-186">This setting lists the family package names of the Windows apps and states expressly whether UE-V synchronizes that app’s settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-187">この設定を使って、他のすべての Windows アプリの設定が同期されている場合でも、アプリの設定を UE-V で同期させないように指定できます。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-187">You can use this setting to specify that settings of an app are never synchronized by UE-V, even if the settings of all other Windows apps are synchronized.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3ac1e-188">一覧にない Windows アプリを同期する</span><span class="sxs-lookup"><span data-stu-id="3ac1e-188">Sync Unlisted Windows Apps</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-189">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="3ac1e-189">Computer and User</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-190">このグループポリシー設定では、windows アプリリストに明示的に記載されていない Windows アプリ用の UE-V Agent の既定の設定同期動作を定義します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-190">This Group Policy setting defines the default settings sync behavior of the UE-V Agent for Windows apps that are not explicitly listed in the Windows app list.</span></span></p></td>
<td align="left"><p><span data-ttu-id="3ac1e-191">既定では、UE-V Agent は Windows アプリリストに含まれている Windows アプリの設定のみを同期します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-191">By default, the UE-V Agent only synchronizes settings of those Windows apps that are included in the Windows app list.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="3ac1e-192">Windows アプリの同期の詳細については、「 [Windows アプリの一覧](https://technet.microsoft.com/library/dn458925.aspx#win8applist)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-192">For more information about synchronizing Windows apps, see [Windows App List](https://technet.microsoft.com/library/dn458925.aspx#win8applist).</span></span>

**<span data-ttu-id="3ac1e-193">コンピューターの対象となるグループポリシー設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="3ac1e-193">To configure computer-targeted Group Policy settings</span></span>**

1.  <span data-ttu-id="3ac1e-194">UE-V コンピューターのグループポリシー設定を管理するドメインコントローラーとして機能するコンピューターで、グループポリシー管理コンソール (GPMC) または Advanced グループポリシー管理 (AGPM) を使用します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-194">Use the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) on the computer that acts as a domain controller to manage Group Policy settings for UE-V computers.</span></span> <span data-ttu-id="3ac1e-195">[**コンピューターの構成**] に移動し、[**ポリシー**] を選択し、[**管理用テンプレート**] をクリックして、[ **Windows コンポーネント**] をクリックし、[ **Microsoft User Experience Virtualization**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-195">Navigate to **Computer configuration**, select **Policies**, select **Administrative Templates**, click **Windows Components**, and then select **Microsoft User Experience Virtualization**.</span></span>

2.  <span data-ttu-id="3ac1e-196">編集するグループポリシー設定を選びます。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-196">Select the Group Policy setting to be edited.</span></span>

**<span data-ttu-id="3ac1e-197">ユーザーを対象としたグループポリシー設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="3ac1e-197">To configure user-targeted Group Policy settings</span></span>**

1.  <span data-ttu-id="3ac1e-198">ドメインコントローラーコンピューターの Microsoft デスクトップ最適化パック (MDOP) でグループポリシー管理コンソール (GPMC) または Advanced グループポリシー管理 (AGPM) ツールを使って、UE-V のグループポリシー設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-198">Use the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) tool in Microsoft Desktop Optimization Pack (MDOP) on the domain controller computer to manage Group Policy settings for UE-V.</span></span> <span data-ttu-id="3ac1e-199">[**ユーザーの構成**] に移動し、[**ポリシー**] を選択し、[**管理用テンプレート**]、[ **Windows コンポーネント**]、[ **Microsoft User Experience Virtualization**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-199">Navigate to **User configuration**, select **Policies**, select **Administrative Templates**, click **Windows Components**, and then select **Microsoft User Experience Virtualization**.</span></span>

2.  <span data-ttu-id="3ac1e-200">[編集済みのグループポリシー] 設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-200">Select the edited Group Policy setting.</span></span>

<span data-ttu-id="3ac1e-201">UE-V Agent では、次の優先順位に従って同期が決定されます。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-201">The UE-V Agent uses the following order of precedence to determine synchronization.</span></span>

**<span data-ttu-id="3ac1e-202">UE-V の設定の優先順位</span><span class="sxs-lookup"><span data-stu-id="3ac1e-202">Order of precedence for UE-V settings</span></span>**

1.  <span data-ttu-id="3ac1e-203">グループポリシー設定によって管理されるユーザーを対象とした設定-これらの構成設定は、のグループポリシーによってレジストリキーに保存され `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration` ます。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-203">User-targeted settings that are managed by Group Policy settings - These configuration settings are stored in the registry key by Group Policy under `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration`.</span></span>

2.  <span data-ttu-id="3ac1e-204">グループポリシー設定によって管理されるコンピューターターゲット設定-これらの構成設定は、のグループポリシーによってレジストリキーに保存され `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration` ます。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-204">Computer-targeted settings that are managed by Group Policy settings - These configuration settings are stored in the registry key by Group Policy under `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration`.</span></span>

3.  <span data-ttu-id="3ac1e-205">Windows PowerShell または Windows management Instrumentation (WMI) を使用して、現在のユーザーによって定義された構成設定: これらの構成設定は、次のレジストリの場所にある UE-V エージェントによって保存さ `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration` れます。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-205">Configuration settings that are defined by the current user by using Windows PowerShell or Windows management Instrumentation (WMI) - These configuration settings are stored by the UE-V Agent under this registry location: `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration`.</span></span>

4.  <span data-ttu-id="3ac1e-206">Windows PowerShell または WMI を使用して、コンピューターに対して定義されている構成設定。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-206">Configuration settings that are defined for the computer by using Windows PowerShell or WMI.</span></span> <span data-ttu-id="3ac1e-207">この構成設定は、次のレジストリの場所にある UE-V エージェントによって保存さ `HKEY_LOCAL_MACHINE\Software\Microsoft\Uev\Agent\Configuration` れます。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-207">These configuration settings are stored by the UE-V Agent under this registry location: `HKEY_LOCAL_MACHINE\Software\Microsoft\Uev\Agent\Configuration`.</span></span>

    <span data-ttu-id="3ac1e-208">**Ue-v のご提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-208">**Got a suggestion for UE-V**?</span></span> <span data-ttu-id="3ac1e-209">[ここで](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-209">Add or vote on suggestions [here](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization).</span></span> <span data-ttu-id="3ac1e-210">**Ue-v の問題が発生した場合**</span><span class="sxs-lookup"><span data-stu-id="3ac1e-210">**Got a UE-V issue**?</span></span> <span data-ttu-id="3ac1e-211">Ue-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)を使用します。</span><span class="sxs-lookup"><span data-stu-id="3ac1e-211">Use the [UE-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopuev).</span></span>

## <span data-ttu-id="3ac1e-212">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3ac1e-212">Related topics</span></span>


[<span data-ttu-id="3ac1e-213">UE-V 2. x の管理</span><span class="sxs-lookup"><span data-stu-id="3ac1e-213">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="3ac1e-214">UE-V 2.x の構成を管理する</span><span class="sxs-lookup"><span data-stu-id="3ac1e-214">Manage Configurations for UE-V 2.x</span></span>](manage-configurations-for-ue-v-2x-new-uevv2.md)

 

 





