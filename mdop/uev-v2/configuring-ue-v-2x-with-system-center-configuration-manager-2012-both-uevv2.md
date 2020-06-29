---
title: System Center Configuration Manager 2012 で UE-V を構成する
description: System Center Configuration Manager 2012 で UE-V を構成する
author: dansimp
ms.assetid: 9a4e2a74-7646-4a77-b58f-2b4456487295
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 2ff9ccc1a17db31471549ece37461558768c3a2b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824407"
---
# <span data-ttu-id="f011a-103">System Center Configuration Manager 2012 で UE-V を構成する</span><span class="sxs-lookup"><span data-stu-id="f011a-103">Configuring UE-V 2.x with System Center Configuration Manager 2012</span></span>


<span data-ttu-id="f011a-104">Microsoft User Experience Virtualization (UE-V) 2.0、2.1、または 2.1 SP1 をインストールした後、必要な機能を使用するには、UE-V が構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f011a-104">After you install Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, or 2.1 SP1 and their required features, UE-V must be configured.</span></span> <span data-ttu-id="f011a-105">UE-V 構成パックでは、管理者は System Center Configuration Manager 2012 SP1 以降のコンプライアンス設定機能を使用して、UE-V および Configuration Manager がインストールされているサイト間で一貫した構成を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="f011a-105">The UE-V Configuration Pack provides a way for administrators to use the Compliance Settings feature of System Center Configuration Manager 2012 SP1 or later to apply consistent configurations across sites where UE-V and Configuration Manager are installed.</span></span>

## <span data-ttu-id="f011a-106">UE-V 構成パックでサポートされる機能</span><span class="sxs-lookup"><span data-stu-id="f011a-106">UE-V Configuration Pack supported features</span></span>


<span data-ttu-id="f011a-107">UE-V 構成パックには、次のタスクを実行するためのツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f011a-107">The UE-V Configuration Pack includes tools to perform the following tasks:</span></span>

-   <span data-ttu-id="f011a-108">UE-V 設定の場所テンプレートの配布ベースラインを作成または更新します。</span><span class="sxs-lookup"><span data-stu-id="f011a-108">Create or update UE-V settings location template distribution baselines.</span></span>

    -   <span data-ttu-id="f011a-109">登録または登録解除する UE-V テンプレートを定義する</span><span class="sxs-lookup"><span data-stu-id="f011a-109">Define UE-V templates to be registered or unregistered</span></span>

    -   <span data-ttu-id="f011a-110">テンプレートが追加または更新されたときの UE-V テンプレート構成項目とベースラインの更新</span><span class="sxs-lookup"><span data-stu-id="f011a-110">Update UE-V template configuration items and baselines as templates are added or updated</span></span>

    -   <span data-ttu-id="f011a-111">標準構成項目の修復を使用して UE-V テンプレートを配布および登録する</span><span class="sxs-lookup"><span data-stu-id="f011a-111">Distribute and register UE-V templates using standard Configuration Item remediation</span></span>

-   <span data-ttu-id="f011a-112">UE-V Agent policy 構成項目を作成または更新して、これらの設定を設定またはクリアします。</span><span class="sxs-lookup"><span data-stu-id="f011a-112">Create or update a UE-V Agent policy configuration item to set or clear these settings.</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="f011a-113">最大パッケージサイズ</span><span class="sxs-lookup"><span data-stu-id="f011a-113">Max package size</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f011a-114">Windows アプリの同期を有効/無効にする</span><span class="sxs-lookup"><span data-stu-id="f011a-114">Enable/disable Windows app sync</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f011a-115">アプリケーションの起動時に同期を待つ</span><span class="sxs-lookup"><span data-stu-id="f011a-115">Wait for sync on application start</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="f011a-116">インポートの遅延を設定する</span><span class="sxs-lookup"><span data-stu-id="f011a-116">Setting import delay</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f011a-117">一覧にない Windows アプリを同期する</span><span class="sxs-lookup"><span data-stu-id="f011a-117">Sync unlisted Windows apps</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f011a-118">ログオン時に同期を待つ</span><span class="sxs-lookup"><span data-stu-id="f011a-118">Wait for sync on logon</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="f011a-119">設定のインポート通知</span><span class="sxs-lookup"><span data-stu-id="f011a-119">Settings import notification</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f011a-120">IT の連絡先 URL</span><span class="sxs-lookup"><span data-stu-id="f011a-120">IT contact URL</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f011a-121">同期のタイムアウトを待つ</span><span class="sxs-lookup"><span data-stu-id="f011a-121">Wait for sync timeout</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="f011a-122">設定の記憶域のパス</span><span class="sxs-lookup"><span data-stu-id="f011a-122">Settings storage path</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f011a-123">IT 担当者に連絡する説明のテキスト</span><span class="sxs-lookup"><span data-stu-id="f011a-123">IT contact descriptive text</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f011a-124">設定テンプレートカタログのパス</span><span class="sxs-lookup"><span data-stu-id="f011a-124">Settings template catalog path</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="f011a-125">同期の有効化</span><span class="sxs-lookup"><span data-stu-id="f011a-125">Sync enablement</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f011a-126">有効になっているトレイアイコン</span><span class="sxs-lookup"><span data-stu-id="f011a-126">Tray icon enabled</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f011a-127">UE-V agent service を開始/停止する</span><span class="sxs-lookup"><span data-stu-id="f011a-127">Start/Stop UE-V agent service</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="f011a-128">同期方法</span><span class="sxs-lookup"><span data-stu-id="f011a-128">Sync method</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f011a-129">初めて使用するときの通知</span><span class="sxs-lookup"><span data-stu-id="f011a-129">First use notification</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f011a-130">ローミング設定を行う Windows アプリを定義する</span><span class="sxs-lookup"><span data-stu-id="f011a-130">Define which Windows apps will roam settings</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="f011a-131">同期のタイムアウト</span><span class="sxs-lookup"><span data-stu-id="f011a-131">Sync timeout</span></span></p></td>
    <td align="left"><p></p></td>
    <td align="left"><p></p></td>
    </tr>
    </tbody>
    </table>

     

-   <span data-ttu-id="f011a-132">UE-V が実行されていることを確認して、コンプライアンスを確認します。</span><span class="sxs-lookup"><span data-stu-id="f011a-132">Verify compliance by confirming that UE-V is running.</span></span>

## <span data-ttu-id="f011a-133">UE-V Agent Policy 構成項目を生成する</span><span class="sxs-lookup"><span data-stu-id="f011a-133">Generate a UE-V Agent Policy Configuration Item</span></span>


<span data-ttu-id="f011a-134">すべての UE-V エージェントのポリシーと構成は、UevAgentPolicyGenerator.exe ツールを使用して生成された単一の構成項目を通じて配布されます。</span><span class="sxs-lookup"><span data-stu-id="f011a-134">All UE-V Agent policy and configuration is distributed through a single configuration item that is generated using the UevAgentPolicyGenerator.exe tool.</span></span> <span data-ttu-id="f011a-135">このツールは、XML 構成ファイルから目的の構成を読み取り、コンピューターをコンプライアンスにするために必要な検出と修復の設定を含む CI を作成します。</span><span class="sxs-lookup"><span data-stu-id="f011a-135">This tool reads the desired configuration from an XML configuration file and creates a CI containing the discovery and remediation settings needed to bring the machine into compliance.</span></span>

<span data-ttu-id="f011a-136">UE-V Agent policy 構成項目の CAB ファイルは、次のパラメーターを含む UevTemplateBaselineGenerator.exe コマンドラインツールを使って作成されます。</span><span class="sxs-lookup"><span data-stu-id="f011a-136">The UE-V Agent policy configuration item CAB file is created using the UevTemplateBaselineGenerator.exe command line tool, which has these parameters:</span></span>

-   <span data-ttu-id="f011a-137">サイトの &lt; サイトコード&gt;</span><span class="sxs-lookup"><span data-stu-id="f011a-137">Site &lt;site code&gt;</span></span>

-   <span data-ttu-id="f011a-138">PolicyName &lt; name &gt; オプション: 存在しない場合は "Ue-v agent Policy" の既定値</span><span class="sxs-lookup"><span data-stu-id="f011a-138">PolicyName &lt;name&gt; Optional: Defaults to “UE-V Agent Policy” if not present</span></span>

-   <span data-ttu-id="f011a-139">PolicyDescription &lt; description &gt; オプション: 存在しない場合は説明が表示される</span><span class="sxs-lookup"><span data-stu-id="f011a-139">PolicyDescription &lt;description&gt; Optional: A description is provided if not present</span></span>

-   <span data-ttu-id="f011a-140">CabFilePath で &lt; 構成項目への完全パスを設定します。CAB ファイル&gt;</span><span class="sxs-lookup"><span data-stu-id="f011a-140">CabFilePath &lt;full path to configuration item .CAB file&gt;</span></span>

-   <span data-ttu-id="f011a-141">&lt;エージェント構成 XML ファイルへのフルパスを設定する&gt;</span><span class="sxs-lookup"><span data-stu-id="f011a-141">ConfigurationFile &lt;full path to agent configuration XML file&gt;</span></span>

<span data-ttu-id="f011a-142">**注** これらのスクリプトを環境内で実行できるようにするには、PowerShell の実行ポリシーを変更する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f011a-142">**Note** It might be necessary to change the PowerShell execution policy to allow these scripts to run in your environment.</span></span> <span data-ttu-id="f011a-143">Configuration Manager コンソールで次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f011a-143">Perform these steps in the Configuration Manager console:</span></span>

1.  <span data-ttu-id="f011a-144">**管理 &gt; クライアント設定の &gt; プロパティ**を選択する</span><span class="sxs-lookup"><span data-stu-id="f011a-144">Select **Administration &gt; Client Settings &gt; Properties**</span></span>

2.  <span data-ttu-id="f011a-145">[**ユーザーエージェント**] タブで、 **PowerShell 実行ポリシー**を [**バイパス**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="f011a-145">In the **User Agent** tab, set the **PowerShell Execution Policy** to **Bypass**</span></span>

<a href="" id="create"></a>**<span data-ttu-id="f011a-146">最初の UE-V ポリシー構成項目を作成する</span><span class="sxs-lookup"><span data-stu-id="f011a-146">Create the First UE-V Policy Configuration Item</span></span>**

1.  <span data-ttu-id="f011a-147">既定の設定構成ファイルを、UE-V 構成パックのインストールディレクトリから ConfigMgr 管理コンソールに表示される場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="f011a-147">Copy the default settings configuration file from the UE-V Config Pack installation directory to a location visible to your ConfigMgr Admin Console:</span></span>

    ``` syntax
    C:\Program Files (x86)\Microsoft User Experience Virtualization\ConfigPack\AgentConfiguration.xml c:\<target path>
    ```

    <span data-ttu-id="f011a-148">既定の構成ファイルには、次の5つのセクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f011a-148">The default configuration file contains five sections:</span></span>

    <a href="" id="computer-policy"></a>**<span data-ttu-id="f011a-149">コンピューターポリシー</span><span class="sxs-lookup"><span data-stu-id="f011a-149">Computer Policy</span></span>**  
    <span data-ttu-id="f011a-150">すべての UE-V のコンピューターレベル設定。</span><span class="sxs-lookup"><span data-stu-id="f011a-150">All UE-V machine level settings.</span></span> <span data-ttu-id="f011a-151">DesiredState 属性には、</span><span class="sxs-lookup"><span data-stu-id="f011a-151">The DesiredState attribute can be</span></span>

    -   <span data-ttu-id="f011a-152">レジストリで割り当てられた値を使用するように**設定**する</span><span class="sxs-lookup"><span data-stu-id="f011a-152">**Set** to have the value assigned in the registry</span></span>

    -   <span data-ttu-id="f011a-153">**オフ**にして設定を削除する</span><span class="sxs-lookup"><span data-stu-id="f011a-153">**Clear** to remove the setting</span></span>

    -   <span data-ttu-id="f011a-154">構成項目を現在の状態のままにしておくための**アンマネージ**</span><span class="sxs-lookup"><span data-stu-id="f011a-154">**Unmanaged** to have the configuration item left at its current state</span></span>

    <span data-ttu-id="f011a-155">このセクションの線は削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="f011a-155">Do not remove lines from this section.</span></span> <span data-ttu-id="f011a-156">代わりに、Configuration Manager で現在の値または既定の値を変更しない場合は、DesiredState を ' Unmanaged ' に設定します。</span><span class="sxs-lookup"><span data-stu-id="f011a-156">Instead, set the DesiredState to ‘Unmanaged’ if you do not want Configuration Manager to alter current or default values.</span></span>

    <a href="" id="currentcomputeruserpolicy"></a>**<span data-ttu-id="f011a-157">CurrentComputerUserPolicy</span><span class="sxs-lookup"><span data-stu-id="f011a-157">CurrentComputerUserPolicy</span></span>**  
    <span data-ttu-id="f011a-158">すべての UE-V のユーザーレベル設定。</span><span class="sxs-lookup"><span data-stu-id="f011a-158">All UE-V user level settings.</span></span> <span data-ttu-id="f011a-159">これらのエントリは、ユーザーのコンピューター設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="f011a-159">These entries override the machine settings for a user.</span></span> <span data-ttu-id="f011a-160">DesiredState 属性には、</span><span class="sxs-lookup"><span data-stu-id="f011a-160">The DesiredState attribute can be</span></span>

    -   <span data-ttu-id="f011a-161">レジストリで割り当てられた値を使用するように**設定**する</span><span class="sxs-lookup"><span data-stu-id="f011a-161">**Set** to have the value assigned in the registry</span></span>

    -   <span data-ttu-id="f011a-162">**オフ**にして設定を削除する</span><span class="sxs-lookup"><span data-stu-id="f011a-162">**Clear** to remove the setting</span></span>

    -   <span data-ttu-id="f011a-163">構成項目を現在の状態のままにしておくための**アンマネージ**</span><span class="sxs-lookup"><span data-stu-id="f011a-163">**Unmanaged** to have the configuration item left at its current state</span></span>

    <span data-ttu-id="f011a-164">このセクションの線は削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="f011a-164">Do not remove lines from this section.</span></span> <span data-ttu-id="f011a-165">代わりに、Configuration Manager で現在の値または既定の値を変更しない場合は、DesiredState を ' Unmanaged ' に設定します。</span><span class="sxs-lookup"><span data-stu-id="f011a-165">Instead, set the DesiredState to ‘Unmanaged’ if you do not want Configuration Manager to alter current or default values.</span></span>

    <a href="" id="services"></a>**<span data-ttu-id="f011a-166">サービス</span><span class="sxs-lookup"><span data-stu-id="f011a-166">Services</span></span>**  
    <span data-ttu-id="f011a-167">このセクションのサービス操作の項目を制御します。</span><span class="sxs-lookup"><span data-stu-id="f011a-167">Entries in this section control service operation.</span></span> <span data-ttu-id="f011a-168">既定の構成ファイルには、UevAgentService のエントリが1つ含まれています。</span><span class="sxs-lookup"><span data-stu-id="f011a-168">The default configuration file contains a single entry for the UevAgentService.</span></span> <span data-ttu-id="f011a-169">DesiredState 属性は、**実行**または**停止**に設定できます。</span><span class="sxs-lookup"><span data-stu-id="f011a-169">The DesiredState attribute can be set to **Running** or **Stopped**.</span></span>

    <a href="" id="windows8appscomputerpolicy"></a>**<span data-ttu-id="f011a-170">Windows8AppsComputerPolicy</span><span class="sxs-lookup"><span data-stu-id="f011a-170">Windows8AppsComputerPolicy</span></span>**  
    <span data-ttu-id="f011a-171">すべてのコンピューターレベルの Windows アプリ同期設定。</span><span class="sxs-lookup"><span data-stu-id="f011a-171">All machine level Windows app synchronization settings.</span></span> <span data-ttu-id="f011a-172">このセクションに記載されている各パッケージには、DesiredState を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f011a-172">Each PackageFamilyName listed in this section can be assigned a DesiredState of</span></span>

    -   <span data-ttu-id="f011a-173">設定をローミングにすることを**許可**</span><span class="sxs-lookup"><span data-stu-id="f011a-173">**Enabled** to have settings roam</span></span>

    -   <span data-ttu-id="f011a-174">**無効**。ローミングから設定できないようにする</span><span class="sxs-lookup"><span data-stu-id="f011a-174">**Disabled** to prevent settings from roaming</span></span>

    -   <span data-ttu-id="f011a-175">UE-V コントロールからエントリが削除されるようにすることを**オフ**にしました</span><span class="sxs-lookup"><span data-stu-id="f011a-175">**Cleared** to have the entry removed from UE-V control</span></span>

    <span data-ttu-id="f011a-176">このセクションには、PowerShell コマンドレット GetAppxPackage を使って表示できるインストール済み Windows アプリの一覧に基づいて、追加の行を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="f011a-176">Additional lines can be added to this section based on the list of installed Windows apps that can be viewed using the PowerShell cmdlet GetAppxPackage.</span></span>

    <a href="" id="windows8appscurrentcomputeruserpolicy"></a>**<span data-ttu-id="f011a-177">Windows8AppsCurrentComputerUserPolicy</span><span class="sxs-lookup"><span data-stu-id="f011a-177">Windows8AppsCurrentComputerUserPolicy</span></span>**  
    <span data-ttu-id="f011a-178">個々のユーザーに対してコンピューターの設定を上書きする設定を使用して、Windows8AppsComputerPolicy と同じです。</span><span class="sxs-lookup"><span data-stu-id="f011a-178">Identical to the Windows8AppsComputerPolicy with settings that override machine settings for an individual user.</span></span>

2.  <span data-ttu-id="f011a-179">目的の状態と値のフィールドを変更して構成ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="f011a-179">Edit the configuration file by changing the desired state and value fields.</span></span>

3.  <span data-ttu-id="f011a-180">ConfigMgr 管理コンソールを実行しているコンピューターで、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f011a-180">Run this command on a machine running the ConfigMgr Admin Console:</span></span>

    ``` syntax
    C:\Program Files (x86)\Microsoft User Experience Virtualization\ConfigPack\UevAgentPolicyGenerator.exe –Site ABC –CabFilePath "C:\MyCabFiles\UevPolicyItem.cab" –ConfigurationFile "c:\AgentConfiguration.xml"
    ```

4.  <span data-ttu-id="f011a-181">ConfigMgr コンソールまたは PowerShell インポート-CMConfigurationItem を使用して CAB ファイルをインポートする</span><span class="sxs-lookup"><span data-stu-id="f011a-181">Import the CAB file using ConfigMgr console or PowerShell Import-CMConfigurationItem</span></span>

**<span data-ttu-id="f011a-182">UE-V ポリシー構成項目を更新する</span><span class="sxs-lookup"><span data-stu-id="f011a-182">Update a UE-V Policy Configuration Item</span></span>**

1.  <span data-ttu-id="f011a-183">目的の状態と値のフィールドを変更して構成ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="f011a-183">Edit the configuration file by changing the desired state and value fields.</span></span>

2.  <span data-ttu-id="f011a-184">[[最初の Ue-v ポリシー構成] 項目](#create)の手順3からコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f011a-184">Run the command from Step 3 in [Create the First UE-V Policy Configuration Item](#create).</span></span> <span data-ttu-id="f011a-185">PolicyName パラメーターで名前を変更した場合は、必ず同じ名前を入力してください。</span><span class="sxs-lookup"><span data-stu-id="f011a-185">If you changed the name with the PolicyName parameter, make sure you enter the same name.</span></span>

3.  <span data-ttu-id="f011a-186">CAB ファイルを再インポートします。</span><span class="sxs-lookup"><span data-stu-id="f011a-186">Reimport the CAB file.</span></span> <span data-ttu-id="f011a-187">ConfigMgr のバージョンが更新されます。</span><span class="sxs-lookup"><span data-stu-id="f011a-187">The version in ConfigMgr will be updated.</span></span>

## <span data-ttu-id="f011a-188">UE-V テンプレートのベースラインを生成する</span><span class="sxs-lookup"><span data-stu-id="f011a-188">Generate a UE-V Template Baseline</span></span>
<span data-ttu-id="f011a-189">UE-V テンプレートは、複数の構成項目を含むベースラインを使って配布されます。</span><span class="sxs-lookup"><span data-stu-id="f011a-189">UE-V templates are distributed using a baseline containing multiple configuration items.</span></span> <span data-ttu-id="f011a-190">各構成項目には、1つの UE-V テンプレートをインストールするために必要な検出と修復のスクリプトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f011a-190">Each configuration item contains the discovery and remediation scripts needed to install one UE-V template.</span></span> <span data-ttu-id="f011a-191">実際の UE-V テンプレートは、標準の構成項目機能を使用して、配布用の修復スクリプト内に埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="f011a-191">The actual UE-V template is embedded within the remediation script for distribution using standard Configuration Item functionality.</span></span>

<span data-ttu-id="f011a-192">UE-V テンプレートベースラインは、次のパラメーターを含む UevTemplateBaselineGenerator.exe コマンドラインツールを使って作成されます。</span><span class="sxs-lookup"><span data-stu-id="f011a-192">The UE-V template baseline is created using the UevTemplateBaselineGenerator.exe command line tool, which has these parameters:</span></span>

-   <span data-ttu-id="f011a-193">サイトの &lt; サイトコード&gt;</span><span class="sxs-lookup"><span data-stu-id="f011a-193">Site &lt;site code&gt;</span></span>

-   <span data-ttu-id="f011a-194">BaselineName &lt; name &gt; (オプション: 存在しない場合は、既定で "Ue-v のテンプレート配布ベースライン")</span><span class="sxs-lookup"><span data-stu-id="f011a-194">BaselineName &lt;name&gt; (Optional: defaults to “UE-V Template Distribution Baseline” if not present)</span></span>

-   <span data-ttu-id="f011a-195">BaselineDescription &lt; description &gt; (オプション: 存在しない場合は説明が表示されます)</span><span class="sxs-lookup"><span data-stu-id="f011a-195">BaselineDescription &lt;description&gt; (Optional: a description is provided if not present)</span></span>

-   <span data-ttu-id="f011a-196">TemplateFolder &lt; ue-v テンプレートフォルダー&gt;</span><span class="sxs-lookup"><span data-stu-id="f011a-196">TemplateFolder &lt;UE-V template folder&gt;</span></span>

-   <span data-ttu-id="f011a-197">コンマ区切りの &lt; テンプレートファイルの一覧を登録する&gt;</span><span class="sxs-lookup"><span data-stu-id="f011a-197">Register &lt;comma separated template file list&gt;</span></span>

-   <span data-ttu-id="f011a-198">コンマ区切りテンプレートリストの登録を解除する &lt;&gt;</span><span class="sxs-lookup"><span data-stu-id="f011a-198">Unregister &lt;comma separated template list&gt;</span></span>

-   <span data-ttu-id="f011a-199">&lt;生成するベースライン CAB ファイルの CabFilePath フルパス&gt;</span><span class="sxs-lookup"><span data-stu-id="f011a-199">CabFilePath &lt;Full path to baseline CAB file to generate&gt;</span></span>

<span data-ttu-id="f011a-200">結果として、構成マネージャーへのインポートの準備ができたベースライン CAB ファイルが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f011a-200">The result is a baseline CAB file that is ready for import into Configuration Manager.</span></span> <span data-ttu-id="f011a-201">将来の日付でテンプレートを更新または追加した場合は、同じベースライン名を使用してコマンドを再実行できます。</span><span class="sxs-lookup"><span data-stu-id="f011a-201">If at a future date, you update or add a template, you can rerun the command using the same baseline name.</span></span> <span data-ttu-id="f011a-202">変更されたテンプレートの CI バージョンの更新に、CAB の結果をインポートします。</span><span class="sxs-lookup"><span data-stu-id="f011a-202">Importing the CAB results in CI version updates on the changed templates.</span></span>

### <a href="" id="create2"></a><span data-ttu-id="f011a-203">最初の UE-V テンプレートベースラインを作成する</span><span class="sxs-lookup"><span data-stu-id="f011a-203">Create the First UE-V Template Baseline</span></span>

1.  <span data-ttu-id="f011a-204">ConfigMgr 管理コンソールを実行しているコンピューターに表示される安定したフォルダーの場所に、"マスタ" の UE-V テンプレートセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="f011a-204">Create a “master” set of UE-V templates in a stable folder location visible to the machine running your ConfigMgr Admin Console.</span></span> <span data-ttu-id="f011a-205">テンプレートが追加または更新されると、このフォルダーは配布用にプルされます。</span><span class="sxs-lookup"><span data-stu-id="f011a-205">As templates are added or updated, this folder is where they are pulled for distribution.</span></span> <span data-ttu-id="f011a-206">テンプレートの最初の一覧は、UE-V がインストールされているコンピューターからコピーできます。</span><span class="sxs-lookup"><span data-stu-id="f011a-206">The initial list of templates can be copied from a machine with UE-V installed.</span></span> <span data-ttu-id="f011a-207">既定のテンプレートの場所は¥ c/Virtualization\\Templates.</span><span class="sxs-lookup"><span data-stu-id="f011a-207">The default template location is C:\\Program Files\\Microsoft User Experience Virtualization\\Templates.</span></span>

2.  <span data-ttu-id="f011a-208">テンプレートジェネレーターコマンドを追加できる text.bat ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="f011a-208">Create a text.bat file where you can add the template generator command.</span></span> <span data-ttu-id="f011a-209">これは省略可能ですが、コマンドパラメーターを保存すると再生成がより簡単になります。</span><span class="sxs-lookup"><span data-stu-id="f011a-209">This is optional, but will make regeneration simpler if you save the command parameters.</span></span>

3.  <span data-ttu-id="f011a-210">ベースラインを生成するためのコマンドとパラメーターを .bat ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="f011a-210">Add the command and parameters to the .bat file that will generate the baseline.</span></span> <span data-ttu-id="f011a-211">次の例では、メモ帳と電卓を配布する基準計画を作成します。</span><span class="sxs-lookup"><span data-stu-id="f011a-211">The following example creates a baseline that distributes Notepad and Calculator:</span></span>

    ``` syntax
    C:\Program Files (x86)\Microsoft User Experience Virtualization\ConfigPack\UevTemplateBaselineGenerator.exe –Site "ABC" –TemplateFolder "C:\ProductionUevTemplates" –Register "MicrosoftNotepad.xml, MicrosoftCalculator.xml" –CabFilePath "C:\MyCabFiles\UevTemplateBaseline.cab"
    ```

4.  <span data-ttu-id="f011a-212">.Bat ファイルを実行して、構成マネージャーへのインポートの準備が整った UevTemplateBaseline.cab を作成します。</span><span class="sxs-lookup"><span data-stu-id="f011a-212">Run the .bat file to create UevTemplateBaseline.cab ready for import into Configuration Manager.</span></span>

### <span data-ttu-id="f011a-213">UE-V テンプレートベースラインを更新する</span><span class="sxs-lookup"><span data-stu-id="f011a-213">Update a UE-V Template Baseline</span></span>

<span data-ttu-id="f011a-214">テンプレートジェネレーターはテンプレートのバージョンを使って、テンプレートを更新する必要があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="f011a-214">The template generator uses the template version to determine if a template should be updated.</span></span> <span data-ttu-id="f011a-215">テンプレートを変更してバージョンを更新すると、ベースラインジェネレーターは、マスターフォルダー内のテンプレートと ConfigMgr サーバー上の CI に含まれているテンプレートを比較します。</span><span class="sxs-lookup"><span data-stu-id="f011a-215">If you make a template change and update the version, the baseline generator compares the template in your master folder with the template contained in the CI on the ConfigMgr server.</span></span> <span data-ttu-id="f011a-216">相違点が見つかった場合は、生成された基準計画と変更された CI のバージョンが更新されます。</span><span class="sxs-lookup"><span data-stu-id="f011a-216">If a difference is found, the generated baseline and modified CI versions are updated.</span></span>

<span data-ttu-id="f011a-217">新しいメモ帳テンプレートを配布するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f011a-217">To distribute a new Notepad template, you would perform these steps:</span></span>

1.  <span data-ttu-id="f011a-218">テンプレートの version 要素にあるテンプレートとテンプレートのバージョンを更新し &lt; &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="f011a-218">Update the template and template version located in the &lt;Version&gt; element of the template.</span></span>

2.  <span data-ttu-id="f011a-219">テンプレートをマスターテンプレートディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="f011a-219">Copy the template to your master template directory.</span></span>

3.  <span data-ttu-id="f011a-220">「[最初の Ue-v テンプレートベースラインを作成](#create2)する」の手順3で作成した .bat ファイルでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f011a-220">Run the command in the .bat file that you created in Step 3 in [Create the First UE-V Template Baseline](#create2).</span></span>

4.  <span data-ttu-id="f011a-221">本体または PowerShell のインポート用のベースラインを使用して、生成された CAB ファイルを ConfigMgr にインポートします。</span><span class="sxs-lookup"><span data-stu-id="f011a-221">Import the generated CAB file into ConfigMgr using the console or PowerShell Import-CMBaseline.</span></span>

## <span data-ttu-id="f011a-222">UE-V 構成パックを入手する</span><span class="sxs-lookup"><span data-stu-id="f011a-222">Get the UE-V Configuration Pack</span></span>


<span data-ttu-id="f011a-223">Configuration Manager 2012 SP1 以降の UE-V 構成パックは、[ここ](https://go.microsoft.com/fwlink/?LinkId=317263)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f011a-223">The UE-V Configuration Pack for Configuration Manager 2012 SP1 or later can be downloaded [here](https://go.microsoft.com/fwlink/?LinkId=317263).</span></span>






## <span data-ttu-id="f011a-224">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f011a-224">Related topics</span></span>


[<span data-ttu-id="f011a-225">UE-V 2.x の構成を管理する</span><span class="sxs-lookup"><span data-stu-id="f011a-225">Manage Configurations for UE-V 2.x</span></span>](manage-configurations-for-ue-v-2x-new-uevv2.md)

 

 





