---
title: グループ ポリシー オブジェクトを使用した UE-V 2.x の構成
description: グループ ポリシー オブジェクトを使用した UE-V 2.x の構成
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
ms.openlocfilehash: b6c9636df36a53cbf65bf1904965f2809484b99c
ms.sourcegitcommit: bdc377477a8cc9e973fbcdd67c2f07b882c5d61e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "11494062"
---
# <a name="configuring-ue-v-2x-with-group-policy-objects"></a><span data-ttu-id="642ac-103">グループ ポリシー オブジェクトを使用した UE-V 2.x の構成</span><span class="sxs-lookup"><span data-stu-id="642ac-103">Configuring UE-V 2.x with Group Policy Objects</span></span>


<span data-ttu-id="642ac-104">一部の Microsoft User Experience Virtualization (UE-V) 2.0、2.1、および 2.1 SP1 グループ ポリシー設定はコンピューターに対して定義し、他のグループ ポリシー設定はユーザーに対して定義できます。</span><span class="sxs-lookup"><span data-stu-id="642ac-104">Some Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 Group Policy settings can be defined for computers, and other Group Policy settings can be defined for users.</span></span> <span data-ttu-id="642ac-105">UE-V グループ ポリシー ADMX ファイルをインストールする方法については [、「INSTALLING THE UE-V 2 Group Policy ADMX Templates」を参照してください](https://technet.microsoft.com/library/dn458891.aspx#admx)。</span><span class="sxs-lookup"><span data-stu-id="642ac-105">For information about how to install UE-V Group Policy ADMX files, see [Installing the UE-V 2 Group Policy ADMX Templates](https://technet.microsoft.com/library/dn458891.aspx#admx).</span></span>

<span data-ttu-id="642ac-106">次のポリシー設定は、UE-V 用に構成できます。</span><span class="sxs-lookup"><span data-stu-id="642ac-106">The following policy settings can be configured for UE-V.</span></span>

**<span data-ttu-id="642ac-107">グループ ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="642ac-107">Group Policy settings</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="642ac-108">グループ ポリシーの設定名</span><span class="sxs-lookup"><span data-stu-id="642ac-108">Group Policy setting name</span></span></th>
<th align="left"><span data-ttu-id="642ac-109">ターゲット</span><span class="sxs-lookup"><span data-stu-id="642ac-109">Target</span></span></th>
<th align="left"><span data-ttu-id="642ac-110">グループ ポリシー設定の説明</span><span class="sxs-lookup"><span data-stu-id="642ac-110">Group Policy setting description</span></span></th>
<th align="left"><span data-ttu-id="642ac-111">構成オプション</span><span class="sxs-lookup"><span data-stu-id="642ac-111">Configuration options</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="642ac-112">同期方法の構成</span><span class="sxs-lookup"><span data-stu-id="642ac-112">Configure Sync Method</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-113">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="642ac-113">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-114">このグループ ポリシー設定を使用すると、User Experience Virtualization (UE-V) が同期プロバイダー機能を使用するかどうかを構成できます。</span><span class="sxs-lookup"><span data-stu-id="642ac-114">By using this Group Policy setting, you can configure whether User Experience Virtualization (UE-V) uses the sync provider feature.</span></span> <span data-ttu-id="642ac-115">このポリシー設定では、ユーザー設定のインポートが遅れたときに通知を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="642ac-115">This policy setting also lets you enable a notification to appear when the import of user settings is delayed.</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-116">同期プロバイダーを使用しない、または外部同期エンジンを使用する UE-V エージェントを構成するには、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="642ac-116">Enable this setting to configure the UE-V agent not to use the sync provider, or to use the external synchronization engine.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="642ac-117">IT リンク テキストに問い合わせ</span><span class="sxs-lookup"><span data-stu-id="642ac-117">Contact IT Link Text</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-118">コンピューターのみ</span><span class="sxs-lookup"><span data-stu-id="642ac-118">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-119">このグループ ポリシー設定では、会社設定センターの [連絡先の IT URL] ハイパーリンクのテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="642ac-119">This Group Policy setting specifies the text of the Contact IT URL hyperlink in the Company Settings Center.</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-120">このグループ ポリシー設定を有効にすると、会社設定センターは、連絡先 IT URL へのリンクに指定されたテキストを表示します。</span><span class="sxs-lookup"><span data-stu-id="642ac-120">If you enable this Group Policy setting, the Company Settings Center displays the specified text in the link to the Contact IT URL.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="642ac-121">IT URL に問い合わせ</span><span class="sxs-lookup"><span data-stu-id="642ac-121">Contact IT URL</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-122">コンピューターのみ</span><span class="sxs-lookup"><span data-stu-id="642ac-122">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-123">このグループ ポリシー設定では、会社設定センターの [連絡先 IT] リンクの URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="642ac-123">This Group Policy setting specifies the URL for the Contact IT link in the Company Settings Center.</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-124">この設定を有効にした場合、会社設定センターは、指定した URL への IT テキスト リンクに連絡します。</span><span class="sxs-lookup"><span data-stu-id="642ac-124">If you enable this setting, the Company Settings Center Contact IT text links to the specified URL.</span></span> <span data-ttu-id="642ac-125">リンクには、HTTP や mailto などの標準プロトコルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="642ac-125">The link can be of any standard protocol, such as HTTP or mailto.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="642ac-126">初回使用通知</span><span class="sxs-lookup"><span data-stu-id="642ac-126">First Use Notification</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-127">コンピューターのみ</span><span class="sxs-lookup"><span data-stu-id="642ac-127">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-128">このグループ ポリシー設定では、UE-V が表示される通知領域で通知を有効にします。</span><span class="sxs-lookup"><span data-stu-id="642ac-128">This Group Policy setting enables a notification in the notification area that appears when the UE-V</span></span></p>
<p><span data-ttu-id="642ac-129">エージェントが初めて実行されます。</span><span class="sxs-lookup"><span data-stu-id="642ac-129">agent runs for the first time.</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-130">既定値は有効です。</span><span class="sxs-lookup"><span data-stu-id="642ac-130">The default is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="642ac-131">同期前に設定の保存場所に ping を実行する</span><span class="sxs-lookup"><span data-stu-id="642ac-131">Ping the settings storage location before sync</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-132">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="642ac-132">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-133">このポリシー設定では、接続を確認するために設定を同期する前に、UE-V 同期プロバイダーの構成で設定ストレージ パスに ping を実行できます。</span><span class="sxs-lookup"><span data-stu-id="642ac-133">This policy setting allows configuration of the UE-V sync provider to ping the settings storage path before attempting to sync settings in order to verify the connection.</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-134">このグループ ポリシー設定を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="642ac-134">Enable or disable this Group Policy setting.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="642ac-135">設定パッケージのサイズの警告のしきい値</span><span class="sxs-lookup"><span data-stu-id="642ac-135">Settings package size warning threshold</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-136">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="642ac-136">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-137">このグループ ポリシー設定では、設定パッケージ のファイル サイズが定義されたしきい値に達したときに報告する UE-V エージェントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="642ac-137">This Group Policy setting lets you configure the UE-V Agent to report when a settings package file size reaches a defined threshold.</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-138">設定パッケージサイズの優先しきい値をキロバイト (KB) で指定します。</span><span class="sxs-lookup"><span data-stu-id="642ac-138">Specify the preferred threshold for settings package sizes in kilobytes (KB).</span></span></p>
<p><span data-ttu-id="642ac-139">既定では、UE-V エージェントにはパッケージ ファイル サイズのしきい値が設定されません。</span><span class="sxs-lookup"><span data-stu-id="642ac-139">By default, the UE-V Agent does not have a package file size threshold.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="642ac-140">設定ストレージ パス</span><span class="sxs-lookup"><span data-stu-id="642ac-140">Settings storage path</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-141">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="642ac-141">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-142">このグループ ポリシー設定は、ユーザー設定の保存場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="642ac-142">This Group Policy setting configures where the user settings are to be stored.</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-143">汎用名前付け規則 (UNC) パスと、\Server\SettingsShare%username% などの変数を入力します。</span><span class="sxs-lookup"><span data-stu-id="642ac-143">Enter a Universal Naming Convention (UNC) path and variables such as \Server\SettingsShare%username%.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="642ac-144">設定テンプレート のカタログ パス</span><span class="sxs-lookup"><span data-stu-id="642ac-144">Settings template catalog path</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-145">コンピューターのみ</span><span class="sxs-lookup"><span data-stu-id="642ac-145">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-146">このグループ ポリシー設定は、カスタム設定の場所テンプレートの格納場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="642ac-146">This Group Policy setting configures where custom settings location templates are stored.</span></span> <span data-ttu-id="642ac-147">このポリシー設定では、カタログを使用して、UE-V エージェントにインストールされている既定の Microsoft テンプレートを置き換えるかどうかを構成します。</span><span class="sxs-lookup"><span data-stu-id="642ac-147">This policy setting also configures whether the catalog is to be used to replace the default Microsoft templates that are installed with the UE-V Agent.</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-148">\Server\TemplateShare などの汎用名前付け規則 (UNC) パス、またはコンピューター上のフォルダーの場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="642ac-148">Enter a Universal Naming Convention (UNC) path such as \Server\TemplateShare or a folder location on the computer.</span></span></p>
<p><span data-ttu-id="642ac-149">既定の Microsoft テンプレートを置き換えるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="642ac-149">Select the check box to replace the default Microsoft templates.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="642ac-150">メーター接続を使用して設定を同期する</span><span class="sxs-lookup"><span data-stu-id="642ac-150">Sync settings over metered connections</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-151">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="642ac-151">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-152">このグループ ポリシー設定は、UE-V がメーター接続を使用して設定を同期するかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="642ac-152">This Group Policy setting defines whether UE-V synchronizes settings over metered connections.</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-153">既定では、UE-V エージェントは、メーター接続を使用して設定を同期されません。</span><span class="sxs-lookup"><span data-stu-id="642ac-153">By default, the UE-V Agent does not synchronize settings over a metered connection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="642ac-154">ローミング時でも、メーター接続を使用して設定を同期する</span><span class="sxs-lookup"><span data-stu-id="642ac-154">Sync settings over metered connections even when roaming</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-155">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="642ac-155">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-156">このグループ ポリシー設定では、データ接続がローミング モードの場合など、ホーム プロバイダー ネットワークの外部のメーター接続で UE-V が設定を同期するかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="642ac-156">This Group Policy setting defines whether UE-V synchronizes settings over metered connections outside of the home provider network, for example, when the data connection is in roaming mode.</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-157">既定では、UE-V はローミング モードの場合、メーター接続を使用して設定を同期しません。</span><span class="sxs-lookup"><span data-stu-id="642ac-157">By default, UE-V does not synchronize settings over a metered connection when it is in roaming mode.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="642ac-158">同期タイムアウト</span><span class="sxs-lookup"><span data-stu-id="642ac-158">Synchronization timeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-159">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="642ac-159">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-160">このグループ ポリシー設定は、リモート設定の場所からユーザー設定を取得するときに、コンピューターがタイムアウトするまでに待機するミリ秒数を構成します。</span><span class="sxs-lookup"><span data-stu-id="642ac-160">This Group Policy setting configures the number of milliseconds that the computer waits before a time-out when it retrieves user settings from the remote settings location.</span></span> <span data-ttu-id="642ac-161">リモート ストレージの場所が使用できなくなった場合、ユーザーが同期プロバイダーを使用しない場合、アプリケーションの開始は、この数ミリ秒遅れになります。</span><span class="sxs-lookup"><span data-stu-id="642ac-161">If the remote storage location is unavailable, and the user does not use the sync provider, the application start is delayed by this many milliseconds.</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-162">優先する同期タイムアウトをミリ秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="642ac-162">Specify the preferred synchronization time-out in milliseconds.</span></span> <span data-ttu-id="642ac-163">既定値は 2000 ミリ秒です。</span><span class="sxs-lookup"><span data-stu-id="642ac-163">The default value is 2000 milliseconds.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="642ac-164">Windows の設定を同期する</span><span class="sxs-lookup"><span data-stu-id="642ac-164">Synchronize Windows settings</span></span> </p></td>
<td align="left"><p><span data-ttu-id="642ac-165">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="642ac-165">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-166">このグループ ポリシー設定は、Windows 設定の同期を構成します。</span><span class="sxs-lookup"><span data-stu-id="642ac-166">This Group Policy setting configures the synchronization of Windows settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-167">コンピューター間で同期する Windows 設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="642ac-167">Select which Windows settings synchronize between computers.</span></span></p>
<p><span data-ttu-id="642ac-168">既定では、Windows テーマ、デスクトップ設定、および簡単操作設定は、同じオペレーティング システム バージョンのコンピューター間で設定を同期します。</span><span class="sxs-lookup"><span data-stu-id="642ac-168">By default, Windows themes, desktop settings, and Ease of Access settings synchronize settings between computers of the same operating system version.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="642ac-169">トレイ アイコン</span><span class="sxs-lookup"><span data-stu-id="642ac-169">Tray Icon</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-170">コンピューターのみ</span><span class="sxs-lookup"><span data-stu-id="642ac-170">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-171">このグループ ポリシー設定では、UE-V トレイ アイコンを有効にします。</span><span class="sxs-lookup"><span data-stu-id="642ac-171">This Group Policy setting enables the UE-V tray icon.</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-172">既定値は有効です。</span><span class="sxs-lookup"><span data-stu-id="642ac-172">The default is enabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="642ac-173">ユーザー エクスペリエンス仮想化の使用 (UE-V)</span><span class="sxs-lookup"><span data-stu-id="642ac-173">Use User Experience Virtualization (UE-V)</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-174">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="642ac-174">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-175">このグループ ポリシー設定では、UE-V を有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="642ac-175">This Group Policy setting lets you enable or disable UE-V.</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-176">このグループ ポリシー設定を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="642ac-176">Enable or disable this Group Policy setting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="642ac-177">VDI 構成</span><span class="sxs-lookup"><span data-stu-id="642ac-177">VDI Configuration</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-178">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="642ac-178">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-179">このポリシー設定は、プールされた VDI 環境で実行されているコンピューターの UE-V ロールバック情報の同期を構成します。</span><span class="sxs-lookup"><span data-stu-id="642ac-179">This policy setting configures the synchronization of UE-V rollback information for computers running in a pooled VDI environment.</span></span> <span data-ttu-id="642ac-180">このポリシーを有効にすると、UE-V ロールバック状態がログアウト時の設定ストレージの場所にコピーされ、ログイン時に復元されます。</span><span class="sxs-lookup"><span data-stu-id="642ac-180">If this policy is enabled, the UE-V rollback state is copied to the settings storage location on logout and restored on login.</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-181">このグループ ポリシー設定を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="642ac-181">Enable or disable this Group Policy setting.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="642ac-182">備考</span><span class="sxs-lookup"><span data-stu-id="642ac-182">Note</span></span>**  
<span data-ttu-id="642ac-183">さらに、グループ ポリシー設定は、多くのデスクトップ アプリケーションおよび Windows アプリで使用できます。</span><span class="sxs-lookup"><span data-stu-id="642ac-183">In addition, Group Policy settings are available for many desktop applications and Windows apps.</span></span> <span data-ttu-id="642ac-184">これらの設定を使用して、特定のアプリケーションの設定の同期を有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="642ac-184">You can use these settings to enable or disable settings synchronization for specific applications.</span></span>

 

**<span data-ttu-id="642ac-185">Windows App グループ ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="642ac-185">Windows App Group Policy settings</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="642ac-186">グループ ポリシーの設定名</span><span class="sxs-lookup"><span data-stu-id="642ac-186">Group Policy setting name</span></span></th>
<th align="left"><span data-ttu-id="642ac-187">ターゲット</span><span class="sxs-lookup"><span data-stu-id="642ac-187">Target</span></span></th>
<th align="left"><span data-ttu-id="642ac-188">グループ ポリシー設定の説明</span><span class="sxs-lookup"><span data-stu-id="642ac-188">Group Policy setting description</span></span></th>
<th align="left"><span data-ttu-id="642ac-189">構成オプション</span><span class="sxs-lookup"><span data-stu-id="642ac-189">Configuration options</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="642ac-190">Windows アプリを同期しない</span><span class="sxs-lookup"><span data-stu-id="642ac-190">Do not synchronize Windows Apps</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-191">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="642ac-191">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-192">このグループ ポリシー設定は、UE-V エージェントが Windows アプリの設定を同期するかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="642ac-192">This Group Policy setting defines whether the UE-V Agent synchronizes settings for Windows apps.</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-193">既定では、Windows アプリを同期します。</span><span class="sxs-lookup"><span data-stu-id="642ac-193">The default is to synchronize Windows apps.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="642ac-194">Windows アプリの一覧</span><span class="sxs-lookup"><span data-stu-id="642ac-194">Windows App List</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-195">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="642ac-195">Computer and User</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-196">この設定では、Windows アプリのファミリ パッケージ名を一覧表示し、UE-V がアプリの設定を同期するかどうかを明示的に示します。</span><span class="sxs-lookup"><span data-stu-id="642ac-196">This setting lists the family package names of the Windows apps and states expressly whether UE-V synchronizes that app’s settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-197">この設定を使用すると、他のすべての Windows アプリの設定が同期されている場合でも、アプリの設定が UE-V によって同期されません。</span><span class="sxs-lookup"><span data-stu-id="642ac-197">You can use this setting to specify that settings of an app are never synchronized by UE-V, even if the settings of all other Windows apps are synchronized.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="642ac-198">リストに登録されていない Windows アプリの同期</span><span class="sxs-lookup"><span data-stu-id="642ac-198">Sync Unlisted Windows Apps</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-199">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="642ac-199">Computer and User</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-200">このグループ ポリシー設定は、Windows アプリの一覧に明示的に一覧表示されていない WINDOWS アプリの UE-V エージェントの既定の設定同期動作を定義します。</span><span class="sxs-lookup"><span data-stu-id="642ac-200">This Group Policy setting defines the default settings sync behavior of the UE-V Agent for Windows apps that are not explicitly listed in the Windows app list.</span></span></p></td>
<td align="left"><p><span data-ttu-id="642ac-201">既定では、UE-V エージェントは、Windows アプリリストに含まれる Windows アプリの設定のみを同期します。</span><span class="sxs-lookup"><span data-stu-id="642ac-201">By default, the UE-V Agent only synchronizes settings of those Windows apps that are included in the Windows app list.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="642ac-202">Windows アプリの同期の詳細については、「Windows App [List」を参照してください](https://technet.microsoft.com/library/dn458925.aspx#win8applist)。</span><span class="sxs-lookup"><span data-stu-id="642ac-202">For more information about synchronizing Windows apps, see [Windows App List](https://technet.microsoft.com/library/dn458925.aspx#win8applist).</span></span>

**<span data-ttu-id="642ac-203">コンピューターを対象としたグループ ポリシー設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="642ac-203">To configure computer-targeted Group Policy settings</span></span>**

1.  <span data-ttu-id="642ac-204">UE-V コンピューターのグループ ポリシー設定を管理するには、ドメイン コントローラーとして機能するコンピューターのグループ ポリシー管理コンソール (GPMC) または Advanced Group Policy Management (AGPM) を使用します。</span><span class="sxs-lookup"><span data-stu-id="642ac-204">Use the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) on the computer that acts as a domain controller to manage Group Policy settings for UE-V computers.</span></span> <span data-ttu-id="642ac-205">[コンピューターの**構成] に移動**し、[\*\*\*\*\*\*ポリシー]\*\* を選択し、[管理用テンプレート] を選択し **、[Windows コンポーネント**] をクリックして、[Microsoft ユーザー エクスペリエンス仮想化]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="642ac-205">Navigate to **Computer configuration**, select **Policies**, select **Administrative Templates**, click **Windows Components**, and then select **Microsoft User Experience Virtualization**.</span></span>

2.  <span data-ttu-id="642ac-206">編集するグループ ポリシー設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="642ac-206">Select the Group Policy setting to be edited.</span></span>

**<span data-ttu-id="642ac-207">ユーザーが対象とするグループ ポリシー設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="642ac-207">To configure user-targeted Group Policy settings</span></span>**

1.  <span data-ttu-id="642ac-208">UE-V のグループ ポリシー設定を管理するには、ドメイン コントローラー コンピューターの Microsoft デスクトップ最適化パック (MDOP) のグループ ポリシー管理コンソール (GPMC) またはグループ ポリシー管理 (AGPM) ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="642ac-208">Use the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) tool in Microsoft Desktop Optimization Pack (MDOP) on the domain controller computer to manage Group Policy settings for UE-V.</span></span> <span data-ttu-id="642ac-209">[ユーザー構成 **] に移動**し **、[ポリシー]** を選択し、[管理用テンプレート] を選択し **、[Windows コンポーネント**] をクリックし、[Microsoft ユーザー エクスペリエンス仮想化]**を選択します**。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="642ac-209">Navigate to **User configuration**, select **Policies**, select **Administrative Templates**, click **Windows Components**, and then select **Microsoft User Experience Virtualization**.</span></span>

2.  <span data-ttu-id="642ac-210">編集したグループ ポリシー設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="642ac-210">Select the edited Group Policy setting.</span></span>

<span data-ttu-id="642ac-211">UE-V エージェントは、次の優先順位を使用して同期を決定します。</span><span class="sxs-lookup"><span data-stu-id="642ac-211">The UE-V Agent uses the following order of precedence to determine synchronization.</span></span>

**<span data-ttu-id="642ac-212">UE-V 設定の優先順位</span><span class="sxs-lookup"><span data-stu-id="642ac-212">Order of precedence for UE-V settings</span></span>**

1.  <span data-ttu-id="642ac-213">グループ ポリシー設定によって管理されるユーザーを対象とした設定 - これらの構成設定は、[グループ ポリシー] の下の [レジストリ キー] に格納されます `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="642ac-213">User-targeted settings that are managed by Group Policy settings - These configuration settings are stored in the registry key by Group Policy under `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration`.</span></span>

2.  <span data-ttu-id="642ac-214">グループ ポリシー設定によって管理されるコンピューターを対象とした設定 - これらの構成設定は、[グループ ポリシー] の下の [レジストリ キー] に格納されます `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="642ac-214">Computer-targeted settings that are managed by Group Policy settings - These configuration settings are stored in the registry key by Group Policy under `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration`.</span></span>

3.  <span data-ttu-id="642ac-215">Windows PowerShell または Windows 管理インストルメンテーション (WMI) を使用して現在のユーザーによって定義される構成設定 - これらの構成設定は、次のレジストリの場所に UE-V エージェントによって保存 `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration` されます。</span><span class="sxs-lookup"><span data-stu-id="642ac-215">Configuration settings that are defined by the current user by using Windows PowerShell or Windows management Instrumentation (WMI) - These configuration settings are stored by the UE-V Agent under this registry location: `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration`.</span></span>

4.  <span data-ttu-id="642ac-216">ユーザーまたは WMI を使用してコンピューターに対Windows PowerShell構成設定。</span><span class="sxs-lookup"><span data-stu-id="642ac-216">Configuration settings that are defined for the computer by using Windows PowerShell or WMI.</span></span> <span data-ttu-id="642ac-217">これらの構成設定は、次のレジストリの場所に UE-V エージェントによって保存されます `HKEY_LOCAL_MACHINE\Software\Microsoft\Uev\Agent\Configuration` 。</span><span class="sxs-lookup"><span data-stu-id="642ac-217">These configuration settings are stored by the UE-V Agent under this registry location: `HKEY_LOCAL_MACHINE\Software\Microsoft\Uev\Agent\Configuration`.</span></span>

    <span data-ttu-id="642ac-218">**UE-V の提案を受け取った**</span><span class="sxs-lookup"><span data-stu-id="642ac-218">**Got a suggestion for UE-V**?</span></span> <span data-ttu-id="642ac-219">ここで提案を追加または投票 [します](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)。</span><span class="sxs-lookup"><span data-stu-id="642ac-219">Add or vote on suggestions [here](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization).</span></span> <span data-ttu-id="642ac-220">**UE-V の問題が発生しましたか**?</span><span class="sxs-lookup"><span data-stu-id="642ac-220">**Got a UE-V issue**?</span></span> <span data-ttu-id="642ac-221">[UE-V TechNet フォーラムを使用します](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)。</span><span class="sxs-lookup"><span data-stu-id="642ac-221">Use the [UE-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopuev).</span></span>

## <a name="related-topics"></a><span data-ttu-id="642ac-222">関連トピック</span><span class="sxs-lookup"><span data-stu-id="642ac-222">Related topics</span></span>


[<span data-ttu-id="642ac-223">UE-V 2.x の管理</span><span class="sxs-lookup"><span data-stu-id="642ac-223">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="642ac-224">UE-V 2.x の構成を管理する</span><span class="sxs-lookup"><span data-stu-id="642ac-224">Manage Configurations for UE-V 2.x</span></span>](manage-configurations-for-ue-v-2x-new-uevv2.md)

 

 
