---
title: UE-V 1.0 を使用して同期するアプリケーションの計画
description: UE-V 1.0 を使用して同期するアプリケーションの計画
author: dansimp
ms.assetid: c718274f-87b4-47f3-8ef7-5e1bd5557a9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7f2b04942588d0f6efad03d5e0249534cd325c09
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812418"
---
# <span data-ttu-id="e28b7-103">UE-V 1.0 を使用して同期するアプリケーションの計画</span><span class="sxs-lookup"><span data-stu-id="e28b7-103">Planning Which Applications to Synchronize with UE-V 1.0</span></span>


<span data-ttu-id="e28b7-104">Microsoft User Experience Virtualization (UE-V) では、UE-V でキャプチャおよび適用される設定を定義する設定場所テンプレート (XML ファイル) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e28b7-104">Microsoft User Experience Virtualization (UE-V) uses settings location templates (XML files) that define the settings that are captured and applied by UE-V.</span></span> <span data-ttu-id="e28b7-105">UE-V には、定義済みの設定場所テンプレートのセットが含まれています。また、管理者は、エンタープライズで使用されるサードパーティまたは基幹業務アプリケーション用のカスタム設定の場所テンプレートを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e28b7-105">UE-V includes a set of predefined settings location templates and also allows administrators to create custom settings location templates for third-party or line-of-business applications that are used in the enterprise.</span></span>

<span data-ttu-id="e28b7-106">管理者として、どのアプリケーションを UE-V ソリューションに含めるかを検討している場合は、ユーザーによってカスタマイズできる設定と、その設定をどのように保存するかを検討してください。</span><span class="sxs-lookup"><span data-stu-id="e28b7-106">As an administrator, when you consider which applications to include in your UE-V solution, consider which settings can be customized by users, and how and where the application stores its settings.</span></span> <span data-ttu-id="e28b7-107">すべてのアプリケーションには、カスタマイズ可能な設定や、ユーザーによって定期的にカスタマイズできる設定が含まれているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="e28b7-107">Not all applications have settings that can be customized or that are routinely customized by users.</span></span> <span data-ttu-id="e28b7-108">また、アプリケーションの設定によっては、複数のコンピューターまたは環境間での安全なローミングができない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="e28b7-108">In addition, not all applications settings can safely roam across multiple computers or environments.</span></span> <span data-ttu-id="e28b7-109">次の条件を満たす設定を同期します。</span><span class="sxs-lookup"><span data-stu-id="e28b7-109">Synchronize settings that meet the following criteria:</span></span>

-   <span data-ttu-id="e28b7-110">ユーザーがアクセスできる場所に保存される設定。</span><span class="sxs-lookup"><span data-stu-id="e28b7-110">Settings that are stored in user-accessible locations.</span></span> <span data-ttu-id="e28b7-111">たとえば、レジストリの system32 または外部の HKCU セクションに保存されている設定を同期しないようにします。</span><span class="sxs-lookup"><span data-stu-id="e28b7-111">For example, do not synchronize settings that are stored in system32 or outside HKCU section of the registry.</span></span>

-   <span data-ttu-id="e28b7-112">特定のコンピューターに固有の設定ではありません。</span><span class="sxs-lookup"><span data-stu-id="e28b7-112">Settings that are not specific to the particular computer.</span></span> <span data-ttu-id="e28b7-113">たとえば、ネットワークまたはハードウェアの構成を除外します。</span><span class="sxs-lookup"><span data-stu-id="e28b7-113">For example, exclude network or hardware configurations.</span></span>

-   <span data-ttu-id="e28b7-114">データが破損していなくてもコンピューター間で同期できる設定。</span><span class="sxs-lookup"><span data-stu-id="e28b7-114">Settings that can be synchronized between computers without risk of corrupted data.</span></span> <span data-ttu-id="e28b7-115">たとえば、データベースファイルに保存されている設定を使用しないようにします。</span><span class="sxs-lookup"><span data-stu-id="e28b7-115">For example, do not use settings that are stored in a database file.</span></span>

## <span data-ttu-id="e28b7-116">UE-V に含まれる設定場所テンプレート</span><span class="sxs-lookup"><span data-stu-id="e28b7-116">Settings location templates that are included in UE-V</span></span>


**<span data-ttu-id="e28b7-117">UE-V アプリケーション設定の場所テンプレート</span><span class="sxs-lookup"><span data-stu-id="e28b7-117">UE-V application settings location templates</span></span>**

<span data-ttu-id="e28b7-118">UE-V agent インストールソフトウェアは、エージェントをインストールし、一般的な Microsoft アプリケーションの設定場所テンプレートの既定のグループを登録します。</span><span class="sxs-lookup"><span data-stu-id="e28b7-118">The UE-V agent installation software installs the agent and registers a default group of settings location templates for common Microsoft applications.</span></span> <span data-ttu-id="e28b7-119">これらの設定場所テンプレートは、次のアプリケーションの設定値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e28b7-119">These settings location templates capture settings values for the following applications:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="e28b7-120">アプリケーションカテゴリ</span><span class="sxs-lookup"><span data-stu-id="e28b7-120">Application category</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="e28b7-121">説明</span><span class="sxs-lookup"><span data-stu-id="e28b7-121">Description</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e28b7-122">Microsoft Office 2010 アプリケーション</span><span class="sxs-lookup"><span data-stu-id="e28b7-122">Microsoft Office 2010 applications</span></span></p></td>
<td align="left"><p><span data-ttu-id="e28b7-123">Microsoft Word 2010</span><span class="sxs-lookup"><span data-stu-id="e28b7-123">Microsoft Word 2010</span></span></p>
<p><span data-ttu-id="e28b7-124">Microsoft Excel 2010</span><span class="sxs-lookup"><span data-stu-id="e28b7-124">Microsoft Excel 2010</span></span></p>
<p><span data-ttu-id="e28b7-125">Microsoft Outlook 2010</span><span class="sxs-lookup"><span data-stu-id="e28b7-125">Microsoft Outlook 2010</span></span></p>
<p><span data-ttu-id="e28b7-126">Microsoft Access 2010</span><span class="sxs-lookup"><span data-stu-id="e28b7-126">Microsoft Access 2010</span></span></p>
<p><span data-ttu-id="e28b7-127">Microsoft Project 2010</span><span class="sxs-lookup"><span data-stu-id="e28b7-127">Microsoft Project 2010</span></span></p>
<p><span data-ttu-id="e28b7-128">Microsoft PowerPoint 2010</span><span class="sxs-lookup"><span data-stu-id="e28b7-128">Microsoft PowerPoint 2010</span></span></p>
<p><span data-ttu-id="e28b7-129">Microsoft Publisher 2010</span><span class="sxs-lookup"><span data-stu-id="e28b7-129">Microsoft Publisher 2010</span></span></p>
<p><span data-ttu-id="e28b7-130">Microsoft Visio 2010</span><span class="sxs-lookup"><span data-stu-id="e28b7-130">Microsoft Visio 2010</span></span></p>
<p><span data-ttu-id="e28b7-131">Microsoft SharePoint Workspace 2010</span><span class="sxs-lookup"><span data-stu-id="e28b7-131">Microsoft SharePoint Workspace 2010</span></span></p>
<p><span data-ttu-id="e28b7-132">Microsoft InfoPath 2010</span><span class="sxs-lookup"><span data-stu-id="e28b7-132">Microsoft InfoPath 2010</span></span></p>
<p><span data-ttu-id="e28b7-133">Microsoft Lync 2010</span><span class="sxs-lookup"><span data-stu-id="e28b7-133">Microsoft Lync 2010</span></span></p>
<p><span data-ttu-id="e28b7-134">Microsoft OneNote 2010</span><span class="sxs-lookup"><span data-stu-id="e28b7-134">Microsoft OneNote 2010</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e28b7-135">ブラウザーオプション (Internet Explorer 8、Internet Explorer 9、Internet Explorer 10)</span><span class="sxs-lookup"><span data-stu-id="e28b7-135">Browser options (Internet Explorer 8, Internet Explorer 9, and Internet Explorer 10)</span></span></p></td>
<td align="left"><p><span data-ttu-id="e28b7-136">[お気に入り]、[ホーム] ページ、[タブ]、およびツールバー。</span><span class="sxs-lookup"><span data-stu-id="e28b7-136">Favorites, home page, tabs, and toolbars.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e28b7-137">Windows アクセサリ</span><span class="sxs-lookup"><span data-stu-id="e28b7-137">Windows accessories</span></span></p></td>
<td align="left"><p><span data-ttu-id="e28b7-138">電卓、メモ帳、ワードパッド。</span><span class="sxs-lookup"><span data-stu-id="e28b7-138">Calculator, Notepad, WordPad.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="e28b7-139">アプリケーションの設定は、アプリケーションの起動時にアプリケーションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e28b7-139">Application settings are applied to the application when the application is started.</span></span> <span data-ttu-id="e28b7-140">これらは、アプリケーションが閉じるときに保存されます。</span><span class="sxs-lookup"><span data-stu-id="e28b7-140">They are saved when the application closes.</span></span>

**<span data-ttu-id="e28b7-141">UE-V Windows 設定の場所テンプレート</span><span class="sxs-lookup"><span data-stu-id="e28b7-141">UE-V Windows settings location templates</span></span>**

<span data-ttu-id="e28b7-142">ユーザーエクスペリエンスの仮想化には、次の Windows 設定の設定値をキャプチャする設定場所テンプレートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e28b7-142">User Experience Virtualization includes settings location templates that capture settings values for the following Windows settings:</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e28b7-143">Windows の設定</span><span class="sxs-lookup"><span data-stu-id="e28b7-143">Windows settings</span></span></th>
<th align="left"><span data-ttu-id="e28b7-144">説明</span><span class="sxs-lookup"><span data-stu-id="e28b7-144">Description</span></span></th>
<th align="left"><span data-ttu-id="e28b7-145">適用対象</span><span class="sxs-lookup"><span data-stu-id="e28b7-145">Apply on</span></span></th>
<th align="left"><span data-ttu-id="e28b7-146">既定の状態</span><span class="sxs-lookup"><span data-stu-id="e28b7-146">Default state</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e28b7-147">デスクトップの背景</span><span class="sxs-lookup"><span data-stu-id="e28b7-147">Desktop background</span></span></p></td>
<td align="left"><p><span data-ttu-id="e28b7-148">現在アクティブなデスクトップの背景。</span><span class="sxs-lookup"><span data-stu-id="e28b7-148">Currently active desktop background.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e28b7-149">ログオン、ロック解除、リモート接続。</span><span class="sxs-lookup"><span data-stu-id="e28b7-149">Logon, unlock, remote connect.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e28b7-150">有効</span><span class="sxs-lookup"><span data-stu-id="e28b7-150">Enabled</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e28b7-151">コンピューターの簡単操作</span><span class="sxs-lookup"><span data-stu-id="e28b7-151">Ease of Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="e28b7-152">アクセシビリティと入力の設定、拡大鏡、ナレーター、スクリーンキーボード。</span><span class="sxs-lookup"><span data-stu-id="e28b7-152">Accessibility and input settings, magnifier, Narrator, and on-Screen keyboard.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e28b7-153">ログオン、ロック解除、リモート接続。</span><span class="sxs-lookup"><span data-stu-id="e28b7-153">Logon, unlock, remote connect.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e28b7-154">無効</span><span class="sxs-lookup"><span data-stu-id="e28b7-154">Disabled</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e28b7-155">デスクトップの設定</span><span class="sxs-lookup"><span data-stu-id="e28b7-155">Desktop settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="e28b7-156">[スタート] メニューとタスクバーの設定、フォルダーオプション、既定のデスクトップアイコン、追加の時計、および地域と言語の設定。</span><span class="sxs-lookup"><span data-stu-id="e28b7-156">Start menu and Taskbar settings, Folder options, default desktop icons, additional clocks, and region and Language settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e28b7-157">ログオンのみ。</span><span class="sxs-lookup"><span data-stu-id="e28b7-157">Logon only.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e28b7-158">無効</span><span class="sxs-lookup"><span data-stu-id="e28b7-158">Disabled</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="e28b7-159">Windows デスクトップの背景と簡単なアクセス設定は、ユーザーがログオンしたとき、コンピューターのロックが解除されたとき、または別のコンピューターへのリモート接続時に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e28b7-159">The Windows desktop background and Ease of Access settings are applied when the user logs on, when the computer is unlocked, or upon remote connection to another computer.</span></span> <span data-ttu-id="e28b7-160">エージェントは、ユーザーがログオフしたとき、コンピューターがロックされているとき、またはリモート接続が切断されたときに、これらの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="e28b7-160">The agent saves these settings when the user logs off, when the computer is locked, or when a remote connection is disconnected.</span></span> <span data-ttu-id="e28b7-161">既定では、Windows デスクトップの背景設定は、同じオペレーティングシステムバージョンのコンピューター間でローミングされます。</span><span class="sxs-lookup"><span data-stu-id="e28b7-161">By default, Windows desktop background settings are roamed between computers of the same operating system version.</span></span>

<span data-ttu-id="e28b7-162">Windows デスクトップと簡単操作の設定は、ユーザーにデスクトップが表示される前にログオン時に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e28b7-162">Windows desktop and Ease of Access settings are applied at logon before the desktop is presented to the user.</span></span> <span data-ttu-id="e28b7-163">ログオンエクスペリエンスを最適化するために、これらの設定は既定ではローミングされません。</span><span class="sxs-lookup"><span data-stu-id="e28b7-163">To optimize the logon experience, these settings are not roamed by default.</span></span> <span data-ttu-id="e28b7-164">デスクトップと簡単操作の設定は、グループポリシー、PowerShell、WMI を使って有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e28b7-164">Desktop and Ease of Access settings can be enabled by using Group Policy, PowerShell, and WMI.</span></span>

<span data-ttu-id="e28b7-165">UE-V は、異なる言語のオペレーティングシステム間での設定のローミングをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e28b7-165">UE-V does not support the roaming of settings between operating systems with different languages.</span></span> <span data-ttu-id="e28b7-166">たとえば、英語とドイツ語の間の同期はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e28b7-166">For example, synchronization between English and German is not supported.</span></span> <span data-ttu-id="e28b7-167">UE-V がユーザー設定をローミングするすべてのコンピューターの言語は一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e28b7-167">The language of all computers to which UE-V roams the user settings must match.</span></span>

<span data-ttu-id="e28b7-168">**注** Microsoft によって提供される設定の場所テンプレートを変更した場合、ユーザーエクスペリエンスの仮想化は、指定したアプリケーションまたは Windows の [設定] グループで適切に動作しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e28b7-168">**Note** If you change the settings location templates that are provided by Microsoft, User Experience Virtualization might not work properly for the designated application or Windows settings group.</span></span>

 

## <a href="" id="prevent-unintentional-user-settings-configuration-"></a><span data-ttu-id="e28b7-169">意図しないユーザー設定の構成を防ぐ</span><span class="sxs-lookup"><span data-stu-id="e28b7-169">Prevent unintentional user Settings configuration</span></span>


<span data-ttu-id="e28b7-170">ユーザーエクスペリエンスの仮想化では、新しいユーザー設定の情報が確認され、設定の保存場所からその情報が自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="e28b7-170">User Experience Virtualization checks for new user settings information, and downloads that information accordingly from a settings storage location.</span></span> <span data-ttu-id="e28b7-171">次のような場合、ローカルコンピューターに設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="e28b7-171">Then, it applies the settings to the local computer in the following cases:</span></span>

-   <span data-ttu-id="e28b7-172">登録されている UE-V テンプレートが含まれているアプリケーションが起動されるたび。</span><span class="sxs-lookup"><span data-stu-id="e28b7-172">Every time an application is launched that has a registered UE-V template.</span></span>

-   <span data-ttu-id="e28b7-173">ユーザーが自分のコンピューターにログオンしたとき。</span><span class="sxs-lookup"><span data-stu-id="e28b7-173">When a user logs on to their computer.</span></span>

-   <span data-ttu-id="e28b7-174">ユーザーがコンピューターのロックを解除したとき。</span><span class="sxs-lookup"><span data-stu-id="e28b7-174">When a user unlocks their computer.</span></span>

-   <span data-ttu-id="e28b7-175">UE-V がインストールされているリモートデスクトップコンピューターへの接続が行われた場合。</span><span class="sxs-lookup"><span data-stu-id="e28b7-175">When a connection is made to a remote desktop computer that has UE-V installed.</span></span>

<span data-ttu-id="e28b7-176">UE-V がコンピューター A とコンピューター B にインストールされていて、アプリケーションの目的の設定がコンピューター A 上にある場合は、コンピューター A で最初にアプリケーションを開いて閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e28b7-176">If UE-V is installed on computer A and computer B, and the desired settings for the application are on computer A, then computer A must open and close the application first.</span></span> <span data-ttu-id="e28b7-177">最初にコンピューター B でアプリを開いて閉じた場合、コンピューター A 上のアプリケーション設定は、コンピューター B のアプリケーション設定と同じになるように構成されます。</span><span class="sxs-lookup"><span data-stu-id="e28b7-177">If an application is opened and closed on computer B first, then the application settings on computer A will be configured to be the same as the application settings on computer B.</span></span>

<span data-ttu-id="e28b7-178">このシナリオは、Windows の設定にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="e28b7-178">This scenario also applies to Windows settings.</span></span> <span data-ttu-id="e28b7-179">コンピューター B の Windows 設定がコンピューター A の Windows 設定と同じである必要がある場合は、ユーザーがコンピューター A を最初にログオンしてログオフする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e28b7-179">If the Windows settings on computer B should be the same as the Windows settings on computer A, then the user should logon and logoff computer A first.</span></span>

<span data-ttu-id="e28b7-180">目的のユーザー設定が誤った順序で適用されている場合は、設定が上書きされたコンピューター上の特定のアプリケーションまたは Windows 構成の復元操作を実行することで、それらの設定を回復できます。</span><span class="sxs-lookup"><span data-stu-id="e28b7-180">If the desired user settings are applied in the wrong order, they can be recovered by performing a restore operation for the specific application or Windows configuration on the computer on which the settings were overwritten.</span></span> <span data-ttu-id="e28b7-181">詳細については、「 [ue-v 1.0 と同期されたアプリケーションと Windows の設定の復元](restoring-application-and-windows-settings-synchronized-with-ue-v-10.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e28b7-181">For more information, see [Restoring Application and Windows Settings Synchronized with UE-V 1.0](restoring-application-and-windows-settings-synchronized-with-ue-v-10.md).</span></span>

## <span data-ttu-id="e28b7-182">カスタム UE-V 設定場所テンプレート</span><span class="sxs-lookup"><span data-stu-id="e28b7-182">Custom UE-V settings location templates</span></span>


<span data-ttu-id="e28b7-183">ユーザー設定の場所テンプレートは、UE-V Generator を使って作成できます。</span><span class="sxs-lookup"><span data-stu-id="e28b7-183">You can create custom settings location templates by using the UE-V Generator.</span></span> <span data-ttu-id="e28b7-184">テスト環境でカスタム設定場所テンプレートを作成してテストしたら、エンタープライズ内のコンピューターに設定場所テンプレートを展開できます。</span><span class="sxs-lookup"><span data-stu-id="e28b7-184">After you create and test a custom settings location template in a test environment, you can deploy the settings location templates to computers in the enterprise.</span></span> <span data-ttu-id="e28b7-185">カスタム設定の場所テンプレートは、エンタープライズソフトウェア配布 (ESD) メソッドなどの既存の展開インフラストラクチャを使用して展開するか、または UE-V 設定テンプレートカタログを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e28b7-185">Custom settings location templates must be deployed with an existing deployment infrastructure, such as enterprise software distribution (ESD) method, with preferences, or by configuring an UE-V settings template catalog.</span></span> <span data-ttu-id="e28b7-186">ESD またはグループポリシーと共に展開されるテンプレートは、UE-V WMI または PowerShell を使用して登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e28b7-186">Templates that are deployed with ESD or Group Policy must be registered by using UE-V WMI or PowerShell.</span></span> <span data-ttu-id="e28b7-187">カスタム設定の場所テンプレートの詳細については、「 [ue-v 1.0 向けのカスタムテンプレートの展開を計画](planning-for-custom-template-deployment-for-ue-v-10.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e28b7-187">For more information about custom settings location templates, see [Planning for Custom Template Deployment for UE-V 1.0](planning-for-custom-template-deployment-for-ue-v-10.md).</span></span>

<span data-ttu-id="e28b7-188">基幹業務アプリケーションを同期する必要があるかどうかに関するガイダンスについては、「 [ue-v 1.0 の基幹業務アプリケーションを評価するためのチェックリスト](checklist-for-evaluating-line-of-business-applications-for-ue-v-10.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e28b7-188">For guidance on whether a line-of-business application should be synchronized, see [Checklist for Evaluating Line-of-Business Applications for UE-V 1.0](checklist-for-evaluating-line-of-business-applications-for-ue-v-10.md).</span></span>

## <span data-ttu-id="e28b7-189">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e28b7-189">Related topics</span></span>


[<span data-ttu-id="e28b7-190">UE-V 1.0 の計画</span><span class="sxs-lookup"><span data-stu-id="e28b7-190">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

[<span data-ttu-id="e28b7-191">UE-V 1.0 のカスタム テンプレートの展開計画</span><span class="sxs-lookup"><span data-stu-id="e28b7-191">Planning for Custom Template Deployment for UE-V 1.0</span></span>](planning-for-custom-template-deployment-for-ue-v-10.md)

[<span data-ttu-id="e28b7-192">UE-V 1.0 の展開</span><span class="sxs-lookup"><span data-stu-id="e28b7-192">Deploying UE-V 1.0</span></span>](deploying-ue-v-10.md)

 

 





