---
title: UE-V エージェントの展開
description: UE-V エージェントの展開
author: dansimp
ms.assetid: ec1c16c4-4be0-41ff-93bc-3e2b1afb5832
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 19f3b798ad7d3a43b0a274a25dd97b651435de51
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827184"
---
# <span data-ttu-id="46fea-103">UE-V エージェントの展開</span><span class="sxs-lookup"><span data-stu-id="46fea-103">Deploying the UE-V Agent</span></span>


<span data-ttu-id="46fea-104">Microsoft User Experience Virtualization (UE-V) agent は、UE-V を使用してアプリケーションと Windows の設定をローミングする各コンピューターで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46fea-104">The Microsoft User Experience Virtualization (UE-V) agent must run on each computer that uses UE-V to roam application and Windows settings.</span></span> <span data-ttu-id="46fea-105">1つの installer ファイル AgentSetup.exe、32ビットと64ビットの両方のオペレーティングシステムに UE-V エージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="46fea-105">A single installer file, AgentSetup.exe, installs the UE-V agent on both 32-bit and 64-bit operating systems.</span></span> <span data-ttu-id="46fea-106">UE-V Agent のコマンドラインパラメーターは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="46fea-106">The command-line parameters of the UE-V Agent are the following:</span></span>

**<span data-ttu-id="46fea-107">AgentSetup.exe コマンドラインのパラメーター</span><span class="sxs-lookup"><span data-stu-id="46fea-107">AgentSetup.exe command-line parameters</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="46fea-108">コマンドラインパラメーター</span><span class="sxs-lookup"><span data-stu-id="46fea-108">Command-line parameter</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="46fea-109">定義</span><span class="sxs-lookup"><span data-stu-id="46fea-109">Definition</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="46fea-110">備考</span><span class="sxs-lookup"><span data-stu-id="46fea-110">Notes</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="46fea-111">/help または/h または/?</span><span class="sxs-lookup"><span data-stu-id="46fea-111">/help or /h or /?</span></span></p></td>
<td align="left"><p><span data-ttu-id="46fea-112">[AgentSetup.exe の使用状況] ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="46fea-112">Displays the AgentSetup.exe usage dialog.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="46fea-113">SettingsStoragePath</span><span class="sxs-lookup"><span data-stu-id="46fea-113">SettingsStoragePath</span></span></p></td>
<td align="left"><p><span data-ttu-id="46fea-114">設定が保存される場所を定義する汎用名前付け規則 (UNC) パスを示します。</span><span class="sxs-lookup"><span data-stu-id="46fea-114">Indicates the Universal Naming Convention (UNC) path that defines where settings are stored.</span></span></p></td>
<td align="left"><p><span data-ttu-id="46fea-115">% username% または% computername% の環境変数が受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="46fea-115">%username% or %computername% environment variables are accepted.</span></span> <span data-ttu-id="46fea-116">スクリプトには、エスケープされた変数が必要です。</span><span class="sxs-lookup"><span data-stu-id="46fea-116">Scripting may require escaped variables.</span></span></p>
<p><strong><span data-ttu-id="46fea-117">既定値 </strong> : &lt; なし &gt; (Active Directory ユーザーのホーム)</span><span class="sxs-lookup"><span data-stu-id="46fea-117">Default</strong>: &lt;none&gt; (Active Directory user home)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="46fea-118">SettingsTemplateCatalogPath</span><span class="sxs-lookup"><span data-stu-id="46fea-118">SettingsTemplateCatalogPath</span></span></p></td>
<td align="left"><p><span data-ttu-id="46fea-119">新しい設定場所テンプレートがチェックされた場所を定義する汎用名前付け規則 (UNC) パスを示します。</span><span class="sxs-lookup"><span data-stu-id="46fea-119">Indicates the Universal Naming Convention (UNC) path that defines the location that was checked for new settings location templates.</span></span></p></td>
<td align="left"><p><span data-ttu-id="46fea-120">カスタム設定の場所テンプレートでのみ必須</span><span class="sxs-lookup"><span data-stu-id="46fea-120">Only required for custom settings location templates</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="46fea-121">RegisterMSTemplates</span><span class="sxs-lookup"><span data-stu-id="46fea-121">RegisterMSTemplates</span></span></p></td>
<td align="left"><p><span data-ttu-id="46fea-122">インストール時に既定の Microsoft テンプレートを登録する必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="46fea-122">Specifies whether the default Microsoft templates should be registered during installation.</span></span></p></td>
<td align="left"><p><span data-ttu-id="46fea-123">True |返し</span><span class="sxs-lookup"><span data-stu-id="46fea-123">True | False</span></span></p>
<p><strong><span data-ttu-id="46fea-124">既定値 </strong> : True</span><span class="sxs-lookup"><span data-stu-id="46fea-124">Default</strong>: True</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="46fea-125">方法</span><span class="sxs-lookup"><span data-stu-id="46fea-125">SyncMethod</span></span></p></td>
<td align="left"><p><span data-ttu-id="46fea-126">使用する同期方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="46fea-126">Specifies which synchronization method should be used.</span></span></p></td>
<td align="left"><p><span data-ttu-id="46fea-127">OfflineFiles |-</span><span class="sxs-lookup"><span data-stu-id="46fea-127">OfflineFiles | None</span></span></p>
<p><strong><span data-ttu-id="46fea-128">既定 </strong> : offlinefiles</span><span class="sxs-lookup"><span data-stu-id="46fea-128">Default</strong>: OfflineFiles</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="46fea-129">SyncTimeoutInMilliseconds</span><span class="sxs-lookup"><span data-stu-id="46fea-129">SyncTimeoutInMilliseconds</span></span></p></td>
<td align="left"><p><span data-ttu-id="46fea-130">コンピューターが設定の保存場所からユーザー設定を取得したときにタイムアウトするまでの時間 (ミリ秒単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="46fea-130">Specifies the number of milliseconds that the computer waits before timeout when it retrieves user settings from the settings storage location.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="46fea-131">既定値 </strong> : 2000 ミリ秒</span><span class="sxs-lookup"><span data-stu-id="46fea-131">Default</strong>: 2000 milliseconds</span></span></p>
<p><span data-ttu-id="46fea-132">(最大2秒待ちます)</span><span class="sxs-lookup"><span data-stu-id="46fea-132">(wait up to 2 seconds)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="46fea-133">SyncEnabled</span><span class="sxs-lookup"><span data-stu-id="46fea-133">SyncEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="46fea-134">UE-V の同期を有効にするか、無効にするかを指定します。</span><span class="sxs-lookup"><span data-stu-id="46fea-134">Specifies whether UE-V synchronization is enabled or disabled.</span></span></p></td>
<td align="left"><p><span data-ttu-id="46fea-135">True |返し</span><span class="sxs-lookup"><span data-stu-id="46fea-135">True | False</span></span></p>
<p><strong><span data-ttu-id="46fea-136">既定値 </strong> : True</span><span class="sxs-lookup"><span data-stu-id="46fea-136">Default</strong>: True</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="46fea-137">Maxパッケージパッケージ</span><span class="sxs-lookup"><span data-stu-id="46fea-137">MaxPackageSizeInBytes</span></span></p></td>
<td align="left"><p><span data-ttu-id="46fea-138">UE-V agent でファイルのしきい値を超えたことを報告した場合に、設定パッケージのファイルサイズをバイト単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="46fea-138">Specifies a settings package file size in bytes when the UE-V agent reports that files exceed the threshold.</span></span></p></td>
<td align="left"><p><span data-ttu-id="46fea-139">&lt;大きさ&gt;</span><span class="sxs-lookup"><span data-stu-id="46fea-139">&lt;size&gt;</span></span></p>
<p><strong><span data-ttu-id="46fea-140">既定値 </strong> : なし (警告のしきい値なし)</span><span class="sxs-lookup"><span data-stu-id="46fea-140">Default</strong>: none (no warning threshold)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="46fea-141">CEIPEnabled</span><span class="sxs-lookup"><span data-stu-id="46fea-141">CEIPEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="46fea-142">カスタマーエクスペリエンス向上プログラムに参加するための設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="46fea-142">Specifies the setting for participation in the Customer Experience Improvement program.</span></span> <span data-ttu-id="46fea-143">True に設定すると、インストーラー情報が Microsoft カスタマーエクスペリエンス向上プログラムのサイトにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="46fea-143">If set to true, then installer information is uploaded to the Microsoft Customer Experience Improvement Program site.</span></span> <span data-ttu-id="46fea-144">False に設定すると、情報はアップロードされません。</span><span class="sxs-lookup"><span data-stu-id="46fea-144">If set to false, then no information is uploaded.</span></span></p></td>
<td align="left"><p><span data-ttu-id="46fea-145">True |返し</span><span class="sxs-lookup"><span data-stu-id="46fea-145">True | False</span></span></p>
<p><strong><span data-ttu-id="46fea-146">既定値 </strong> : False</span><span class="sxs-lookup"><span data-stu-id="46fea-146">Default</strong>: False</span></span></p>
<p><strong><span data-ttu-id="46fea-147">Windows 7 の </strong> 場合: True</span><span class="sxs-lookup"><span data-stu-id="46fea-147">On Windows 7</strong>: True</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="46fea-148">インストール時に、SettingsStoragePath コマンドラインパラメーターは設定値の保存場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="46fea-148">During installation, the SettingsStoragePath command-line parameter specifies the settings storage location for the settings values.</span></span> <span data-ttu-id="46fea-149">UE-V Agent を展開する前に、設定の保存場所を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="46fea-149">A settings storage location can be defined before deploying the UE-V Agent.</span></span> <span data-ttu-id="46fea-150">設定の保存場所が定義されていない場合、UE-V は Active Directory ユーザーのホームディレクトリを設定の保存場所として使います。</span><span class="sxs-lookup"><span data-stu-id="46fea-150">If no settings storage location is defined, then UE-V uses the Active Directory user Home Directory as the settings storage location.</span></span> <span data-ttu-id="46fea-151">セットアップ時に SettingsStoragePath 構成を指定し、その値の一部として% username% を使用すると、ユーザーがログインするすべてのコンピューターまたはセッションで同じユーザー設定のエクスペリエンスがローミングされます。</span><span class="sxs-lookup"><span data-stu-id="46fea-151">When you specify the SettingsStoragePath configuration during setup and use the %username% as part of the value, this will roam the same user settings experience on all computers or sessions that a user logs into.</span></span> <span data-ttu-id="46fea-152">SettingsStoragePath 値の一部として%username%\\%computername% 変数を指定すると、各コンピューターの設定の操作性が維持されます。</span><span class="sxs-lookup"><span data-stu-id="46fea-152">If you specify the %username%\\%computername% variables as part of the SettingsStoragePath value, this will preserve the settings experience for each computer.</span></span>

<span data-ttu-id="46fea-153">アーキテクチャ固有の Windows インストーラー (.msi) ファイルは、32ビットと64ビットの両方のインストーラーに加えて、UE-V エージェントのインストール用に提供されています。</span><span class="sxs-lookup"><span data-stu-id="46fea-153">Architecture-specific Windows Installer (.msi) files are provided for the UE-V agent installation in addition to the combined 32-bit and 64-bit installer.</span></span> <span data-ttu-id="46fea-154">AgentSetupx86.msi または AgentSetupx64.msi のインストールファイルは、AgentSetup.exe ファイルよりも小さく、エージェントの展開が合理化される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="46fea-154">The AgentSetupx86.msi or AgentSetupx64.msi install files are smaller than the AgentSetup.exe file and might streamline the agent deployments.</span></span> <span data-ttu-id="46fea-155">AgentSetup.exe installer のコマンドラインパラメーターは、Windows インストーラー (.msi) のインストールでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="46fea-155">The command-line parameters for the AgentSetup.exe installer are supported for the Windows Installer (.msi) installation.</span></span>

<span data-ttu-id="46fea-156">**注** UE-V agent のインストールまたはアンインストール中には、AgentSetup.exe ファイルまたは AgentSetup &lt; arch ファイルを使用できますが、両方を使用することはでき &gt; ません。</span><span class="sxs-lookup"><span data-stu-id="46fea-156">**Note** During UE-V agent installation or uninstallation you can either use the AgentSetup.exe file or the AgentSetup&lt;arch&gt;.msi file, but not both.</span></span> <span data-ttu-id="46fea-157">Ue-v agent をインストールするために使用されたのと同じファイルを使用して、UE-V Agent をアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="46fea-157">The same file must be used to uninstall the UE-V Agent as it was used to install the UE-V Agent.</span></span>

 

<span data-ttu-id="46fea-158">UE-V agent をインストールする場合は、必ず正しい変数形式を使用してください。</span><span class="sxs-lookup"><span data-stu-id="46fea-158">Be sure to use the correct variable format when you install the UE-V agent.</span></span> <span data-ttu-id="46fea-159">次の表では、AgentSetup.exe または Windows インストーラー (.msi) のインストールファイルを使用するための展開オプションの例を示します。</span><span class="sxs-lookup"><span data-stu-id="46fea-159">The following table provides examples of deployment options for using the AgentSetup.exe or the Windows Installer (.msi) installation files.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="46fea-160">展開の種類</span><span class="sxs-lookup"><span data-stu-id="46fea-160">Deployment type</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="46fea-161">展開の説明</span><span class="sxs-lookup"><span data-stu-id="46fea-161">Deployment description</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="46fea-162">例</span><span class="sxs-lookup"><span data-stu-id="46fea-162">Example</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="46fea-163">コマンドプロンプト</span><span class="sxs-lookup"><span data-stu-id="46fea-163">Command prompt</span></span></p></td>
<td align="left"><p><span data-ttu-id="46fea-164">コマンドプロンプトから UE-V agent をインストールする場合は、% ^ username% 変数形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="46fea-164">When you install the UE-V agent from a command prompt, use the %^username% variable format.</span></span> <span data-ttu-id="46fea-165">設定の記憶域のパスにスペースが含まれているために引用符が必要な場合は、展開用のバッチスクリプトファイルを使います。</span><span class="sxs-lookup"><span data-stu-id="46fea-165">If quotation marks are needed because of spaces in the settings storage path, use a batch script file for deployment.</span></span></p>
<p></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="46fea-166">バッチスクリプト</span><span class="sxs-lookup"><span data-stu-id="46fea-166">Batch script</span></span></p></td>
<td align="left"><p><span data-ttu-id="46fea-167">UE-V Agent をバッチスクリプトファイルからインストールする場合は、%% username%% 変数形式を使います。</span><span class="sxs-lookup"><span data-stu-id="46fea-167">When you install the UE-V Agent from a batch script file, use the %%username%% variable format.</span></span> <span data-ttu-id="46fea-168">この install メソッドを使う場合は、%% 文字の変数をエスケープする必要があります。</span><span class="sxs-lookup"><span data-stu-id="46fea-168">If you use this install method, you must escape the variable with the %% characters.</span></span> <span data-ttu-id="46fea-169">この文字がないと、スクリプトは実行時ではなく、インストール時に username 変数を展開します。 UE-V は、すべてのユーザーに対して1つの設定の保存場所を使用します。</span><span class="sxs-lookup"><span data-stu-id="46fea-169">Without this character, the script expands the username variable at install time, rather than at run time, causing UE-V to use a single settings storage location for all users.</span></span></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="46fea-170">PowerShell</span><span class="sxs-lookup"><span data-stu-id="46fea-170">PowerShell</span></span></p></td>
<td align="left"><p><span data-ttu-id="46fea-171">PowerShell プロンプトまたは PowerShell スクリプトから UE-V agent をインストールする場合は、% username% 変数形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="46fea-171">When you install the UE-V agent from a PowerShell prompt or PowerShell script, use the %username% variable format.</span></span></p></td>
<td align="left"><p><code>&amp; AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p>
<p><code>&amp; msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="46fea-172">電子ソフトウェアの配布 (Configuration Manager ソフトウェアの展開の展開など)</span><span class="sxs-lookup"><span data-stu-id="46fea-172">Electronic software distribution, such as deployment of Configuration Manager Software Deployment)</span></span></p></td>
<td align="left"><p><span data-ttu-id="46fea-173">Configuration Manager を使用して UE-V Agent をインストールする場合は、^% username ^% 変数形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="46fea-173">When you install the UE-V Agent with Configuration Manager, use the ^%username^% variable format.</span></span></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="46fea-174">**注** U EV エージェントをインストールするには、管理者権限が必要です。 UE-V agent を実行するには、コンピューターの再起動が必要になります。</span><span class="sxs-lookup"><span data-stu-id="46fea-174">**Note** The installation of the U-EV Agent requires Administrator rights and the computer will require a restart before the UE-V agent can run.</span></span>

 

## <span data-ttu-id="46fea-175">ネットワーク共有からの UE-V エージェントの展開方法</span><span class="sxs-lookup"><span data-stu-id="46fea-175">UE-V Agent deployment methods from a network share</span></span>


<span data-ttu-id="46fea-176">UE-V agent を展開するには、次のメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="46fea-176">You can use the following methods to deploy the UE-V agent:</span></span>

-   <span data-ttu-id="46fea-177">Windows インストーラー (.msi) ファイルをインストールできる電子ソフトウェア配布 (ESD) ソリューション。</span><span class="sxs-lookup"><span data-stu-id="46fea-177">An electronic software distribution (ESD) solution that can install a Windows Installer (.msi) file.</span></span>

-   <span data-ttu-id="46fea-178">共有に一元的に保存されている Windows Installer (.msi) ファイルを参照するインストールスクリプト。</span><span class="sxs-lookup"><span data-stu-id="46fea-178">An installation script that references the Windows Installer (.msi) file that is stored centrally on a share.</span></span>

-   <span data-ttu-id="46fea-179">コンピューターでインストールプログラムを手動で実行します。</span><span class="sxs-lookup"><span data-stu-id="46fea-179">Manually running the installation program on the computer.</span></span>

<span data-ttu-id="46fea-180">ネットワーク共有から UE-V agent を展開するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="46fea-180">To deploy the UE-V agent from a network share, use the following steps:</span></span>

**<span data-ttu-id="46fea-181">ネットワーク共有から UE-V Agent をインストールして構成するには</span><span class="sxs-lookup"><span data-stu-id="46fea-181">To install and configure the UE-V Agent from a network share</span></span>**

1.  <span data-ttu-id="46fea-182">ユーザーが "読み取り" アクセス許可を持つネットワーク共有で UE-V agent インストールファイル (AgentSetup.exe) をステージングします。</span><span class="sxs-lookup"><span data-stu-id="46fea-182">Stage the UE-V agent installation file (AgentSetup.exe) on a network share to which users have “read” permission.</span></span>

2.  <span data-ttu-id="46fea-183">UE-V agent をインストールするユーザーコンピューターにスクリプトを展開します。</span><span class="sxs-lookup"><span data-stu-id="46fea-183">Deploy a script to user computers that installs the UE-V agent.</span></span> <span data-ttu-id="46fea-184">スクリプトでは、設定の保存場所を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46fea-184">The script should specify the settings storage location.</span></span>

**<span data-ttu-id="46fea-185">UE-V Agent を更新する</span><span class="sxs-lookup"><span data-stu-id="46fea-185">Update the UE-V Agent</span></span>**

<span data-ttu-id="46fea-186">UE-V エージェントソフトウェアの更新プログラムは、Microsoft Update を通じて提供されます。</span><span class="sxs-lookup"><span data-stu-id="46fea-186">Updates for the UE-V agent software will be provided through Microsoft Update.</span></span> <span data-ttu-id="46fea-187">UE-V agent のアップグレード中に、一般的な Microsoft アプリケーションと Windows 設定用の設定場所テンプレートの既定のグループが更新されることがあります。</span><span class="sxs-lookup"><span data-stu-id="46fea-187">During a UE-V agent upgrade, the default group of settings location templates for common Microsoft applications and Windows settings may be updated.</span></span> <span data-ttu-id="46fea-188">UE-V agent の更新プログラムは、エンタープライズソフトウェア配布 (ESD) インフラストラクチャを使用して展開できます。</span><span class="sxs-lookup"><span data-stu-id="46fea-188">UE-V agent updates can be deployed by using Enterprise Software Distribution (ESD) infrastructure.</span></span>

## <span data-ttu-id="46fea-189">関連トピック</span><span class="sxs-lookup"><span data-stu-id="46fea-189">Related topics</span></span>


[<span data-ttu-id="46fea-190">UE-V 1.0 の展開</span><span class="sxs-lookup"><span data-stu-id="46fea-190">Deploying UE-V 1.0</span></span>](deploying-ue-v-10.md)

[<span data-ttu-id="46fea-191">UE-V 1.0 でサポートされている構成</span><span class="sxs-lookup"><span data-stu-id="46fea-191">Supported Configurations for UE-V 1.0</span></span>](supported-configurations-for-ue-v-10.md)

[<span data-ttu-id="46fea-192">UE-V 1.0 の設定の保存場所の展開</span><span class="sxs-lookup"><span data-stu-id="46fea-192">Deploying the Settings Storage Location for UE-V 1.0</span></span>](deploying-the-settings-storage-location-for-ue-v-10.md)

[<span data-ttu-id="46fea-193">UE-V Generator のインストール</span><span class="sxs-lookup"><span data-stu-id="46fea-193">Installing the UE-V Generator</span></span>](installing-the-ue-v-generator.md)

<span data-ttu-id="46fea-194">User Experience Virtualization Agent の展開</span><span class="sxs-lookup"><span data-stu-id="46fea-194">Deploy the User Experience Virtualization Agent</span></span>
 

 





