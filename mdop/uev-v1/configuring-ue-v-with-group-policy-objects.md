---
title: グループ ポリシー オブジェクトを使用した UE-V の構成
description: グループ ポリシー オブジェクトを使用した UE-V の構成
author: dansimp
ms.assetid: 5c9be706-a05f-4397-9a38-e6b73ebff1e5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7e479e6bef1a2b38cf822ffca19ed4220b0c59fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826697"
---
# <span data-ttu-id="e63a1-103">グループ ポリシー オブジェクトを使用した UE-V の構成</span><span class="sxs-lookup"><span data-stu-id="e63a1-103">Configuring UE-V with Group Policy Objects</span></span>


<span data-ttu-id="e63a1-104">一部の Microsoft User Experience Virtualization (UE-V) グループポリシー設定は、コンピューターに対して定義することができ、他のユーザーに対して定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="e63a1-104">Some Microsoft User Experience Virtualization (UE-V) Group Policy settings can be defined for computers and others can be defined for users.</span></span> <span data-ttu-id="e63a1-105">UE-V agent 構成ポリシー設定は、コンピューターまたはユーザーに対して定義することができます。</span><span class="sxs-lookup"><span data-stu-id="e63a1-105">UE-V agent configuration policy settings can be defined for computers or users.</span></span> <span data-ttu-id="e63a1-106">UE-V グループポリシー ADMX ファイルのインストール方法については、「 [Ue-v グループポリシーの Admx テンプレートをインストール](installing-the-ue-v-group-policy-admx-templates.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e63a1-106">For information about how to install UE-V Group Policy ADMX files, see [Installing the UE-V Group Policy ADMX Templates](installing-the-ue-v-group-policy-admx-templates.md).</span></span>

<span data-ttu-id="e63a1-107">UE-V 用に次のポリシー設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="e63a1-107">The following policy settings can be configured for UE-V:</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e63a1-108">ポリシー設定名</span><span class="sxs-lookup"><span data-stu-id="e63a1-108">Policy setting name</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="e63a1-109">ターゲット</span><span class="sxs-lookup"><span data-stu-id="e63a1-109">Target</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="e63a1-110">ポリシー設定の説明</span><span class="sxs-lookup"><span data-stu-id="e63a1-110">Policy setting description</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="e63a1-111">構成オプション</span><span class="sxs-lookup"><span data-stu-id="e63a1-111">Configuration options</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e63a1-112">User Experience Virtualization (UE-V) を使用する</span><span class="sxs-lookup"><span data-stu-id="e63a1-112">Use User Experience Virtualization (UE-V)</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-113">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="e63a1-113">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-114">このポリシー設定では、ユーザーエクスペリエンスの仮想化 (UE-V) を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e63a1-114">This policy setting allows you to enable or disable User Experience Virtualization (UE-V).</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-115">このポリシー設定を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="e63a1-115">Enable or disable this policy setting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e63a1-116">設定の記憶域のパス</span><span class="sxs-lookup"><span data-stu-id="e63a1-116">Settings storage path</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-117">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="e63a1-117">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-118">このポリシー設定では、ユーザー設定を保存する場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="e63a1-118">This policy setting configures where the user settings will be stored.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-119">汎用名前付け規則 (UNC) のパスと \Server\SettingsShare%username%. などの変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="e63a1-119">Provide a Universal Naming Convention (UNC) path and variables such as \Server\SettingsShare%username%.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e63a1-120">設定テンプレートカタログのパス</span><span class="sxs-lookup"><span data-stu-id="e63a1-120">Settings template catalog path</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-121">コンピューターのみ</span><span class="sxs-lookup"><span data-stu-id="e63a1-121">Computers Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-122">このポリシー設定では、カスタム設定の場所テンプレートが保存されている場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="e63a1-122">This policy setting configures where custom settings location templates are stored.</span></span> <span data-ttu-id="e63a1-123">このポリシー設定では、UE-V agent と共にインストールされた既定の Microsoft テンプレートをカタログで置き換えるかどうかも構成します。</span><span class="sxs-lookup"><span data-stu-id="e63a1-123">This policy setting also configures whether the catalog will be used to replace the default Microsoft templates that are installed with the UE-V agent.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-124">\Server\TemplateShare やコンピューター上のフォルダーの場所など、汎用名前付け規則 (UNC) パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e63a1-124">Provide a Universal Naming Convention (UNC) path such as \Server\TemplateShare or a folder location on the computer.</span></span></p>
<p></p>
<p><span data-ttu-id="e63a1-125">既定の Microsoft テンプレートを置き換えるには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e63a1-125">Select the check box to replace the default Microsoft templates.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e63a1-126">オフラインファイルを使わない</span><span class="sxs-lookup"><span data-stu-id="e63a1-126">Do not use Offline Files</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-127">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="e63a1-127">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-128">このポリシー設定では、UE-V で Windows オフラインファイル機能を使用するかどうかを構成できます。</span><span class="sxs-lookup"><span data-stu-id="e63a1-128">This policy setting allows you to configure whether UE-V will use the Windows Offline Files feature.</span></span> <span data-ttu-id="e63a1-129">このポリシー設定では、ユーザー設定のインポートが延期された場合に通知を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e63a1-129">This policy setting also allows you to enable notification to occur when the import of user settings is delayed.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-130">オフラインファイルを使用しないように UE-V Agent を構成するには、この設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="e63a1-130">To configure the UE-V Agent to not use offline files, enable this setting.</span></span></p>
<p></p>
<p><span data-ttu-id="e63a1-131">設定のインポートが延期された場合に通知を受け取るかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="e63a1-131">Specify if notifications should be given when settings import is delayed.</span></span></p>
<p></p>
<p><span data-ttu-id="e63a1-132">通知が表示されるまでの待ち時間 (秒単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="e63a1-132">Specify the length of time in seconds to wait before the notification appears.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e63a1-133">同期タイムアウト</span><span class="sxs-lookup"><span data-stu-id="e63a1-133">Synchronization timeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-134">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="e63a1-134">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-135">このポリシー設定では、コンピューターがリモート設定の場所からユーザー設定を取得するときにタイムアウトするまでの時間 (ミリ秒単位) を構成します。</span><span class="sxs-lookup"><span data-stu-id="e63a1-135">This policy setting configures the number of milliseconds that the computer waits before a timeout when retrieving user settings from the remote settings location.</span></span> <span data-ttu-id="e63a1-136">リモート記憶域の場所が利用できない場合は、アプリケーションの起動がこのミリ秒単位で遅延します。</span><span class="sxs-lookup"><span data-stu-id="e63a1-136">If the remote storage location is unavailable, the application launch is delayed by this many milliseconds.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-137">優先同期タイムアウト (ミリ秒単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="e63a1-137">Specify the preferred synchronization timeout in milliseconds.</span></span> <span data-ttu-id="e63a1-138">既定値は2000ミリ秒です。</span><span class="sxs-lookup"><span data-stu-id="e63a1-138">The default value of 2000 milliseconds.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e63a1-139">パッケージサイズの警告しきい値</span><span class="sxs-lookup"><span data-stu-id="e63a1-139">Package size warning threshold</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-140">コンピューターとユーザー</span><span class="sxs-lookup"><span data-stu-id="e63a1-140">Computers and Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-141">このポリシー設定では、設定パッケージのファイルサイズが定義されたしきい値に達したときに報告するように UE-V agent を構成できます。</span><span class="sxs-lookup"><span data-stu-id="e63a1-141">This policy setting allows you to configure the UE-V agent to report when a settings package file size reaches a defined threshold.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-142">設定パッケージサイズの推奨しきい値を kb 単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="e63a1-142">Specified the preferred threshold for settings package sizes in kilobytes.</span></span></p>
<p><span data-ttu-id="e63a1-143">既定では、UE-V agent にはパッケージファイルサイズのしきい値はありません。</span><span class="sxs-lookup"><span data-stu-id="e63a1-143">By default, the UE-V agent does not have a package file size threshold.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e63a1-144">ローミングアプリケーションの設定</span><span class="sxs-lookup"><span data-stu-id="e63a1-144">Roaming Application settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-145">ユーザーのみ</span><span class="sxs-lookup"><span data-stu-id="e63a1-145">Users Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-146">このポリシー設定は、アプリケーションのユーザー設定のローミングを構成します。</span><span class="sxs-lookup"><span data-stu-id="e63a1-146">This policy setting configures the roaming of user settings of applications.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-147">コンピューター間でローミングする Windows の設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="e63a1-147">Select which Windows settings will roam between computers.</span></span></p>
<p><span data-ttu-id="e63a1-148">既定では、UE-V によって提供される設定テンプレートを持つアプリケーションのユーザー設定は、コンピューター間でローミングされます。</span><span class="sxs-lookup"><span data-stu-id="e63a1-148">By default, the user settings of applications with settings template provided by UE-V are roamed between computers.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e63a1-149">Windows のローミングの設定</span><span class="sxs-lookup"><span data-stu-id="e63a1-149">Roaming Windows settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-150">ユーザーのみ</span><span class="sxs-lookup"><span data-stu-id="e63a1-150">Users Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-151">このポリシー設定では、Windows の設定のローミングを構成します。</span><span class="sxs-lookup"><span data-stu-id="e63a1-151">This policy setting configures the roaming of Windows settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e63a1-152">コンピューター間をローミングするアプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e63a1-152">Select which applications will roam between computers.</span></span></p>
<p><span data-ttu-id="e63a1-153">既定では、Windows のテーマは同じオペレーティングシステムバージョンのコンピューター間でローミングされます。</span><span class="sxs-lookup"><span data-stu-id="e63a1-153">By default, Windows themes are roamed between computers of the same operating system version.</span></span> <span data-ttu-id="e63a1-154">Windows デスクトップの設定と簡単操作の設定はローミングされません。</span><span class="sxs-lookup"><span data-stu-id="e63a1-154">Windows desktop settings and Ease of Access settings are not roamed.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="e63a1-155">コンピューターのターゲットポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="e63a1-155">To configure computer-targeted policies</span></span>**

1.  <span data-ttu-id="e63a1-156">UE-V コンピューターのグループポリシーを管理するドメインコントローラーコンピューターで、グループポリシー管理コンソール (GPMC) または Advanced グループポリシー管理 (AGPM) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e63a1-156">Use the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) on the domain controller computer that manages Group Policy for UE-V computers.</span></span> <span data-ttu-id="e63a1-157">[**コンピューターの構成**] に移動し、[**ポリシー**] を選択し、[**管理用テンプレート**] をクリックして、[ **Windows コンポーネント**] をクリックし、[ **Microsoft User Experience Virtualization**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e63a1-157">Navigate to **Computer configuration**, select **Policies**, select **Administrative Templates**, click **Windows Components**, and then select **Microsoft User Experience Virtualization**.</span></span>

2.  <span data-ttu-id="e63a1-158">編集するポリシー設定を選びます。</span><span class="sxs-lookup"><span data-stu-id="e63a1-158">Select the policy setting to be edited.</span></span>

**<span data-ttu-id="e63a1-159">ユーザーを対象としたポリシーを構成するには</span><span class="sxs-lookup"><span data-stu-id="e63a1-159">To configure user-targeted policies</span></span>**

1.  <span data-ttu-id="e63a1-160">UE-V のグループポリシーを管理するドメインコントローラーコンピューター上のグループポリシー管理コンソール (MDOP) または高度なグループポリシー管理 (AGPM) ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="e63a1-160">Use the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) tool in Microsoft Desktop Optimization Pack (MDOP) on the domain controller computer that manages Group Policy for UE-V.</span></span> <span data-ttu-id="e63a1-161">[**ユーザーの構成**] に移動し、[**ポリシー**] を選択し、[**管理用テンプレート**]、[ **Windows コンポーネント**]、[ **Microsoft User Experience Virtualization**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e63a1-161">Navigate to **User configuration**, select **Policies**, select **Administrative Templates**, click **Windows Components**, and then select **Microsoft User Experience Virtualization**.</span></span>

2.  <span data-ttu-id="e63a1-162">編集したポリシー設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="e63a1-162">Select the policy setting edited.</span></span>

<span data-ttu-id="e63a1-163">UE-V agent では、次の優先順位に従って同期が決定されます。</span><span class="sxs-lookup"><span data-stu-id="e63a1-163">The UE-V agent uses the following order of precedence to determine synchronization.</span></span>

**<span data-ttu-id="e63a1-164">UE-V の設定の優先順位</span><span class="sxs-lookup"><span data-stu-id="e63a1-164">Order of precedence for UE-V settings</span></span>**

1.  <span data-ttu-id="e63a1-165">グループポリシーによって管理されるユーザーによる設定: これらの構成設定は、のグループポリシーによってレジストリキーに保存され `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration` ます。</span><span class="sxs-lookup"><span data-stu-id="e63a1-165">User-targeted settings managed by Group Policy - These configuration settings are stored in the registry key by Group Policy under `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration`.</span></span>

2.  <span data-ttu-id="e63a1-166">グループポリシーによって管理されているコンピューターターゲット設定: これらの構成設定は、のグループポリシーによってレジストリキーに保存され `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration` ます。</span><span class="sxs-lookup"><span data-stu-id="e63a1-166">Computer-targeted settings managed by Group Policy - These configuration settings are stored in the registry key by Group Policy under `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration`.</span></span>

3.  <span data-ttu-id="e63a1-167">PowerShell または WMI を使用して現在のユーザーが定義した構成の設定。これらの構成設定は、次のレジストリの場所にある UE-V エージェントによって保存され `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration` ます。</span><span class="sxs-lookup"><span data-stu-id="e63a1-167">Configuration settings defined by the current user using PowerShell or WMI - These configuration settings are stored by the UE-V agent under this registry location: `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration`.</span></span>

4.  <span data-ttu-id="e63a1-168">PowerShell または WMI を使用してコンピューターに定義された構成の設定。</span><span class="sxs-lookup"><span data-stu-id="e63a1-168">Configuration settings defined for the computer using PowerShell or WMI.</span></span> <span data-ttu-id="e63a1-169">これらの構成設定は、の下にある UE-V エージェントによって保存され `HKEY_LOCAL_MACHINE \Software\Microsoft\Uev\Agent\Configuration` ます。</span><span class="sxs-lookup"><span data-stu-id="e63a1-169">These configuration settings are stored by the UE-V agent under the `HKEY_LOCAL_MACHINE \Software\Microsoft\Uev\Agent\Configuration`.</span></span>

## <span data-ttu-id="e63a1-170">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e63a1-170">Related topics</span></span>


[<span data-ttu-id="e63a1-171">UE-V 1.0 の管理</span><span class="sxs-lookup"><span data-stu-id="e63a1-171">Administering UE-V 1.0</span></span>](administering-ue-v-10.md)

[<span data-ttu-id="e63a1-172">UE-V 1.0 の操作</span><span class="sxs-lookup"><span data-stu-id="e63a1-172">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





