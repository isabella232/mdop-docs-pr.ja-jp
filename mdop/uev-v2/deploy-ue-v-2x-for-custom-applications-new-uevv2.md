---
title: カスタムアプリケーションの UE-V 2. x の展開
description: カスタムアプリケーションの UE-V 2. x の展開
author: dansimp
ms.assetid: f7cb089f-d764-4a93-82b6-926fe0385a23
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 07/19/2016
ms.openlocfilehash: 217f647d948df016c4a6b72736669c2b3305b705
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824404"
---
# <span data-ttu-id="f4d06-103">カスタムアプリケーションの UE-V 2. x の展開</span><span class="sxs-lookup"><span data-stu-id="f4d06-103">Deploy UE-V 2.x for Custom Applications</span></span>


<span data-ttu-id="f4d06-104">Microsoft User Experience Virtualization (UE-V) 2.0。</span><span class="sxs-lookup"><span data-stu-id="f4d06-104">Microsoft User Experience Virtualization (UE-V) 2.0.</span></span> <span data-ttu-id="f4d06-105">2.1 と 2.1 SP1 では、**設定場所テンプレート**と呼ばれる XML ファイルを使用して、デスクトップアプリケーションの設定と Windows デスクトップの設定を監視および同期します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-105">2.1, and 2.1 SP1 use XML files called **settings location templates** to monitor and synchronize desktop application settings and Windows desktop settings between user computers.</span></span> <span data-ttu-id="f4d06-106">既定では、いくつかの設定場所テンプレートが UE-V に含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4d06-106">By default, some settings location templates are included in UE-V.</span></span> <span data-ttu-id="f4d06-107">ただし、既定のテンプレートに含まれていないデスクトップアプリケーションの設定を同期する場合は、UE-V Generator を使って、独自のカスタム設定の場所テンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-107">But if you want to synchronize settings for desktop applications other than those included in the default templates, you can create your own custom settings location templates by using the UE-V Generator.</span></span>

<span data-ttu-id="f4d06-108">「 [Ue-v の展開を準備](prepare-a-ue-v-2x-deployment-new-uevv2.md)する」の計画資料に目を通して、カスタムアプリケーション (サードパーティ、基幹業務など) の設定を同期することにした場合は、このトピックで説明するように、ue-v の機能を展開します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-108">Once you have read through the planning material in [Prepare a UE-V 2.x Deployment](prepare-a-ue-v-2x-deployment-new-uevv2.md) and have decided that you want to synchronize settings for custom applications (third-party, line-of-business, etc.), you will deploy the features of UE-V as described in this topic.</span></span> <span data-ttu-id="f4d06-109">まず、カスタムアプリケーションの設定を同期するために必要な主な手順を示します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-109">To start, here are the main steps required to synchronize settings for custom applications:</span></span>

-   [<span data-ttu-id="f4d06-110">UEV Generator をインストールする</span><span class="sxs-lookup"><span data-stu-id="f4d06-110">Install the UEV Generator</span></span>](#uevgen)

    <span data-ttu-id="f4d06-111">UEV Generator を使って、カスタム XML 設定の場所テンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-111">Use the UEV Generator to create custom XML settings location templates.</span></span>

-   [<span data-ttu-id="f4d06-112">UE-V 設定テンプレートカタログを構成する</span><span class="sxs-lookup"><span data-stu-id="f4d06-112">Configure a UE-V settings template catalog</span></span>](#deploycatalogue)

    <span data-ttu-id="f4d06-113">このパスは、カスタム設定の場所テンプレートが保存されている場所で定義できます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-113">You can define this path where custom settings location templates are stored.</span></span>

-   [<span data-ttu-id="f4d06-114">カスタム設定の場所テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="f4d06-114">Create custom settings location templates</span></span>](#createcustomtemplates)

    <span data-ttu-id="f4d06-115">これらのカスタムテンプレートを使用すると、ユーザーはカスタムアプリケーションの設定を同期できます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-115">These custom templates let users sync settings for custom applications.</span></span>

-   [<span data-ttu-id="f4d06-116">カスタム設定の場所テンプレートを展開する</span><span class="sxs-lookup"><span data-stu-id="f4d06-116">Deploy the custom settings location templates</span></span>](#deploycustomtemplates)

    <span data-ttu-id="f4d06-117">カスタムテンプレートをテストして、設定が正しく同期されていることを確認したら、次のいずれかの方法でこれらのテンプレートを展開できます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-117">After you test the custom template to ensure that settings are synced correctly, you can deploy these templates in one of these ways:</span></span>

    -   <span data-ttu-id="f4d06-118">既存の展開インフラストラクチャ (構成マネージャーなど)</span><span class="sxs-lookup"><span data-stu-id="f4d06-118">Through your existing deployment infrastructure, such as Configuration Manager</span></span>

    -   <span data-ttu-id="f4d06-119">グループポリシーの基本設定を使用する</span><span class="sxs-lookup"><span data-stu-id="f4d06-119">By using Group Policy preferences</span></span>

    -   [<span data-ttu-id="f4d06-120">UE-V 設定テンプレートカタログを展開する</span><span class="sxs-lookup"><span data-stu-id="f4d06-120">Deploy a UE-V settings template catalog</span></span>](#deploycatalogue)

    <span data-ttu-id="f4d06-121">**注** ESD またはグループポリシーを使用して展開されるテンプレートは、UE-V Windows Management Instrumentation (WMI) または Windows PowerShell に登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4d06-121">**Note** Templates that are deployed by using ESD or Group Policy must be registered with UE-V Windows Management Instrumentation (WMI) or Windows PowerShell.</span></span>

     

## <span data-ttu-id="f4d06-122">カスタムアプリケーションの UE-V 2 x の展開を準備する</span><span class="sxs-lookup"><span data-stu-id="f4d06-122">Prepare to Deploy UE-V 2.x for Custom Applications</span></span>


<span data-ttu-id="f4d06-123">カスタムアプリケーションを処理する UE-V 機能の展開を開始する前に、いくつかの点を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4d06-123">Before you start deploying the UE-V features that handle custom applications, there are just a couple things to review.</span></span>

### <span data-ttu-id="f4d06-124">UE-V Generator</span><span class="sxs-lookup"><span data-stu-id="f4d06-124">The UE-V Generator</span></span>

<span data-ttu-id="f4d06-125">UE-V Generator は、アプリケーションがその設定を保存する場所を検出し、キャプチャするために、アプリケーションを監視します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-125">The UE-V Generator monitors an application to discover and capture the locations where the application stores its settings.</span></span> <span data-ttu-id="f4d06-126">監視されるアプリケーションは、従来のアプリケーションである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4d06-126">The application that is monitored must be a traditional application.</span></span> <span data-ttu-id="f4d06-127">次の種類のアプリケーションでは、UE-V Generator を使って設定位置テンプレートを作成できますが、設定場所テンプレートを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="f4d06-127">You use the UE-V Generator to create settings location templates, but it cannot create a settings location template from these application types:</span></span>

-   <span data-ttu-id="f4d06-128">仮想化されたアプリケーション</span><span class="sxs-lookup"><span data-stu-id="f4d06-128">Virtualized applications</span></span>

-   <span data-ttu-id="f4d06-129">ターミナルサービスを通じて提供されるアプリケーション</span><span class="sxs-lookup"><span data-stu-id="f4d06-129">Applications that are offered through Terminal Services</span></span>

-   <span data-ttu-id="f4d06-130">Java アプリケーション</span><span class="sxs-lookup"><span data-stu-id="f4d06-130">Java applications</span></span>

-   <span data-ttu-id="f4d06-131">Windows アプリ  </span><span class="sxs-lookup"><span data-stu-id="f4d06-131">Windows apps</span></span>

<span data-ttu-id="f4d06-132">**注** UE-V settings location テンプレートは、仮想化されたアプリケーションまたはターミナルサービスアプリケーションから作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="f4d06-132">**Note** UE-V settings location templates cannot be created from virtualized applications or Terminal Services applications.</span></span> <span data-ttu-id="f4d06-133">ただし、テンプレートを使用して同期された設定は、それらのアプリケーションに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-133">However, settings that are synchronized by using the templates can be applied to those applications.</span></span> <span data-ttu-id="f4d06-134">仮想デスクトップインフラストラクチャ (VDI) とターミナルサービスアプリケーションをサポートするテンプレートを作成するには、UE-V Generator を使って、アプリケーションのバージョンの Windows インストーラー (.msi) パッケージを開きます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-134">To create templates that support Virtual Desktop Infrastructure (VDI) and Terminal Services applications, open a version of the Windows Installer (.msi) package of the application by using the UE-V Generator.</span></span> <span data-ttu-id="f4d06-135">仮想アプリケーションの同期設定の詳細については、「 [Application Virtualization アプリケーションを使った ue-v の使用](using-ue-v-2x-with-application-virtualization-applications-both-uevv2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4d06-135">For more information about synchronizing settings for virtual applications, see [Using UE-V 2.x with Application Virtualization Applications](using-ue-v-2x-with-application-virtualization-applications-both-uevv2.md).</span></span>

 

<span data-ttu-id="f4d06-136">**除外する場所:** 検出プロセスでは、ユーザーのコンピューターまたはコンピューティング環境の間で設定が適切に同期されない、一般的にアプリケーションソフトウェアファイルを保存する場所を除外します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-136">**Excluded Locations:** The discovery process excludes locations that commonly store application software files that do not synchronize settings well between user computers or computing environments.</span></span> <span data-ttu-id="f4d06-137">既定では、次のように除外されます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-137">By default, these are excluded:</span></span>

-   <span data-ttu-id="f4d06-138">HKEY \ _CURRENT \ _USER のレジストリキーと、ログオンしたユーザーが値を書き込むことができないファイル</span><span class="sxs-lookup"><span data-stu-id="f4d06-138">HKEY\_CURRENT\_USER registry keys and files to which the logged-on user cannot write values</span></span>

-   <span data-ttu-id="f4d06-139">HKEY \ _CURRENT \ _USER のレジストリキーと、Windows オペレーティングシステムのコア機能に関連付けられているファイル</span><span class="sxs-lookup"><span data-stu-id="f4d06-139">HKEY\_CURRENT\_USER registry keys and files that are associated with the core functionality of the Windows operating system</span></span>

-   <span data-ttu-id="f4d06-140">HKEY \ _LOCAL \ _MACHINE ハイブにあるすべてのレジストリキー</span><span class="sxs-lookup"><span data-stu-id="f4d06-140">All registry keys that are located in the HKEY\_LOCAL\_MACHINE hive</span></span>

-   <span data-ttu-id="f4d06-141">Program Files ディレクトリにあるファイル</span><span class="sxs-lookup"><span data-stu-id="f4d06-141">Files that are located in Program Files directories</span></span>

-   <span data-ttu-id="f4d06-142">ユーザーに保存されているファイル (\ \ [ユーザー名 \] \)</span><span class="sxs-lookup"><span data-stu-id="f4d06-142">Files that are located in Users \\ \[User name\] \\ AppData \\ LocalLow</span></span>

-   <span data-ttu-id="f4d06-143">% Systemroot% にある Windows オペレーティングシステムファイル</span><span class="sxs-lookup"><span data-stu-id="f4d06-143">Windows operating system files that are located in %Systemroot%</span></span>

<span data-ttu-id="f4d06-144">除外された場所に格納されているレジストリキーとファイルがアプリケーション設定を同期するために必要な場合は、テンプレートの作成プロセス中に場所を手動で設定場所テンプレートに追加できます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-144">If registry keys and files that are stored in excluded locations are required to synchronize application settings, you can manually add the locations to the settings location template during the template creation process.</span></span>
<span data-ttu-id="f4d06-145">ただし、HKEY \ _CURRENT \ _USER ハイブに対する変更のみが同期されます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-145">However, only changes to the HKEY\_CURRENT\_USER hive will be sync-ed.</span></span>

### <span data-ttu-id="f4d06-146">既定の Microsoft テンプレートを置き換える</span><span class="sxs-lookup"><span data-stu-id="f4d06-146">Replace the default Microsoft templates</span></span>

<span data-ttu-id="f4d06-147">UE-V Agent は、一般的な Microsoft アプリケーションと Windows 設定用の設定場所テンプレートの既定のグループをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f4d06-147">The UE-V Agent installs a default group of settings location templates for common Microsoft applications and Windows settings.</span></span> <span data-ttu-id="f4d06-148">これらのテンプレートをカスタマイズしたり、設定の場所テンプレートを作成してカスタムアプリケーションの設定を同期したりする場合、UE-V Agent は、設定テンプレートカタログを使用してテンプレートを保存するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-148">If you customize these templates, or create settings location templates to synchronize settings for custom applications, the UE-V Agent can be configured to use a settings template catalog to store the templates.</span></span> <span data-ttu-id="f4d06-149">この場合は、[設定] テンプレートカタログに、既定のテンプレートとカスタムテンプレートを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4d06-149">In this case, you will need to include the default templates along with the custom templates in the settings template catalog.</span></span>

<span data-ttu-id="f4d06-150">[Ue-v agent を展開](https://technet.microsoft.com/library/dn458891.aspx#agent)するときは、コマンドラインパラメーターを使用して、 `RegisterMSTemplates` 既定の Microsoft テンプレートの登録を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-150">When you [Deploy a UE-V Agent](https://technet.microsoft.com/library/dn458891.aspx#agent), you can use the command-line parameter `RegisterMSTemplates` to disable the registration of the default Microsoft templates.</span></span>

<span data-ttu-id="f4d06-151">グループポリシーを使用して設定テンプレートカタログのパスを構成する場合は、既定の Microsoft テンプレートを置き換えるかどうかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-151">When you use Group Policy to configure the settings template catalog path, you can choose to replace the default Microsoft templates.</span></span> <span data-ttu-id="f4d06-152">既定の Microsoft テンプレートを置き換えるようにポリシー設定を構成した場合、UE-V Agent によってインストールされた既定の Microsoft テンプレートはすべて削除され、設定テンプレートカタログ内にあるテンプレートだけが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-152">If you configure the policy settings to replace the default Microsoft templates, all of the default Microsoft templates that are installed by the UE-V Agent are deleted and only the templates that are located in the settings template catalog are used.</span></span> <span data-ttu-id="f4d06-153">既定の Microsoft テンプレートを上書きするには、UE-V Agent 構成設定パラメーターを `RegisterMSTemplates` *true*に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4d06-153">The UE-V Agent configuration setting parameter `RegisterMSTemplates` must be set to *true* in order to override the default Microsoft template.</span></span>

<span data-ttu-id="f4d06-154">**注** 有効にした後にこのポリシー設定を無効にした場合、UE-V Agent では既定の Microsoft テンプレートは復元されません。</span><span class="sxs-lookup"><span data-stu-id="f4d06-154">**Note** If you disable this policy setting after it has been enabled, the UE-V Agent does not restore the default Microsoft templates.</span></span>

 

<span data-ttu-id="f4d06-155">既定の Microsoft テンプレートと同じ ID を使用するように設定テンプレートカタログにカスタマイズされたテンプレートがあり、UE-V Agent が既定の Microsoft テンプレートと置き換えるように構成されていない場合、Microsoft テンプレートは無視されます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-155">If there are customized templates in the settings template catalog that use the same ID as the default Microsoft templates, and the UE-V Agent is not configured to replace the default Microsoft templates, the Microsoft templates are ignored.</span></span>

<span data-ttu-id="f4d06-156">UE-V Windows PowerShell 機能を使用して、既定のテンプレートを置き換えることもできます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-156">You can also replace the default templates by using the UE-V Windows PowerShell features.</span></span> <span data-ttu-id="f4d06-157">既定の Microsoft テンプレートを Windows PowerShell に置き換えるには、既定の Microsoft テンプレートの登録を解除し、カスタマイズされたテンプレートを登録します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-157">To replace the default Microsoft template with Windows PowerShell, unregister all of the default Microsoft templates, and then register the customized templates.</span></span>

<span data-ttu-id="f4d06-158">**注** アプリケーションに新しい設定場所のテンプレートを展開しても、古い設定パッケージは [設定の保存] の場所に残ります。</span><span class="sxs-lookup"><span data-stu-id="f4d06-158">**Note** Old settings packages remain in the settings storage location even if you deploy new settings location templates for an application.</span></span> <span data-ttu-id="f4d06-159">これらのパッケージはエージェントによって読み取られることはありませんが、自動的に削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="f4d06-159">These packages are not read by the agent, but neither are they automatically deleted.</span></span>

 

## <a href="" id="uevgen"></a><span data-ttu-id="f4d06-160">UEV Generator ジェネレーターをインストールする</span><span class="sxs-lookup"><span data-stu-id="f4d06-160">Install the UEV 2.x Generator</span></span>


<span data-ttu-id="f4d06-161">コンピューターに Microsoft User Experience Virtualization (UE-V) 2.0 ジェネレーターをインストールします。これを使用すると、カスタム設定の場所テンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-161">Install the Microsoft User Experience Virtualization (UE-V) 2.0 Generator on a computer that you can then use to create a custom settings location template.</span></span> <span data-ttu-id="f4d06-162">このコンピューターには、カスタム設定の場所テンプレートを生成するアプリケーションがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4d06-162">This computer should have the applications installed for which custom settings location templates are to be generated.</span></span>

**<span data-ttu-id="f4d06-163">UE-V Generator をインストールするには</span><span class="sxs-lookup"><span data-stu-id="f4d06-163">To install the UE-V Generator</span></span>**

1.  <span data-ttu-id="f4d06-164">ローカル管理者の権限を持つユーザーとして、UE-V ソフトウェアで提供されている UE-V Generator のインストールファイル**ToolSetup.exe**見つけます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-164">As a user with local administrator rights, locate the UE-V Generator installation file **ToolSetup.exe** provided with the UE-V software.</span></span> <span data-ttu-id="f4d06-165">または、コンピューターのアーキテクチャがわかっている場合は、適切な Windows インストーラー (.msi) ファイル、 **ToolsSetupx64.msi**または**ToolsSetupx86.msi**を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-165">Or, if you know the computer architecture, you can run the appropriate Windows Installer (.msi) file, **ToolsSetupx64.msi** or **ToolsSetupx86.msi**.</span></span>

2.  <span data-ttu-id="f4d06-166">インストールファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4d06-166">Double-click the installation file.</span></span> <span data-ttu-id="f4d06-167">ユーザーエクスペリエンス仮想化ジェネレーターのセットアップウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-167">The User Experience Virtualization Generator Setup wizard opens.</span></span> <span data-ttu-id="f4d06-168">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-168">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="f4d06-169">Microsoft ソフトウェアライセンス条項に同意し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4d06-169">Accept the Microsoft Software License Terms, and then click **Next**.</span></span>

4.  <span data-ttu-id="f4d06-170">Microsoft Update とカスタマーエクスペリエンス向上プログラムのオプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4d06-170">Click the options for Microsoft Updates and the Customer Experience Improvement Program.</span></span>

5.  <span data-ttu-id="f4d06-171">UE-V Generator をインストールする保存先フォルダーを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4d06-171">Select the destination folder in which to install the UE-V Generator, and then click **Next**.</span></span>

6.  <span data-ttu-id="f4d06-172">インストールを開始するには、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4d06-172">Click **Install** to begin the installation.</span></span>

    <span data-ttu-id="f4d06-173">**注** アプリケーションがインストールされる前に、**ユーザーアカウント制御**のプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-173">**Note** A prompt for **User Account Control** appears before the application is installed.</span></span> <span data-ttu-id="f4d06-174">UE-V Generator をインストールするには、アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="f4d06-174">Permission is required to install the UE-V Generator.</span></span>

     

7.  <span data-ttu-id="f4d06-175">インストールが完了したら、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-175">Click **Finish** to close the wizard after the installation is finished.</span></span> <span data-ttu-id="f4d06-176">UE-V Generator を実行するには、コンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4d06-176">You must restart your computer before you can run the UE-V Generator.</span></span>

    <span data-ttu-id="f4d06-177">インストールが正常に完了したことを確認するには、[**スタート**]、[**すべてのプログラム**]、[ **microsoft user Experience Virtualization**]、[ **microsoft user experience virtualization Generator**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4d06-177">To verify that the installation was successful, click **Start**, click **All Programs**, click **Microsoft User Experience Virtualization**, and then click **Microsoft User Experience Virtualization Generator**.</span></span>

    <span data-ttu-id="f4d06-178">**注** UE-V 2 ジェネレーターは、UE-V 2 エージェントのテンプレートを作成するためにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-178">**Note** The UE-V 2 Generator can only be used to create templates for UE-V 2 Agents.</span></span> <span data-ttu-id="f4d06-179">UE-V 1.0 エージェントと UE-V 2 エージェントの混在型展開では、すべての UE-V エージェントをアップグレードするまで、引き続き UE-V 1.0 ジェネレーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4d06-179">In a mixed deployment of UE-V 1.0 Agents and UE-V 2 Agents, you should continue to use the UE-V 1.0 Generator until you have upgraded all UE-V Agents.</span></span>

     

## <a href="" id="deploycatalogue"></a><span data-ttu-id="f4d06-180">設定テンプレートカタログを展開する</span><span class="sxs-lookup"><span data-stu-id="f4d06-180">Deploy a Settings Template Catalog</span></span>


<span data-ttu-id="f4d06-181">ユーザーエクスペリエンスの仮想化設定テンプレートカタログは、カスタム設定の場所テンプレートをすべて保存する、UE-V のコンピューター上のフォルダーパスまたはサーバーメッセージブロック (SMB) ネットワーク共有です。</span><span class="sxs-lookup"><span data-stu-id="f4d06-181">The User Experience Virtualization settings template catalog is a folder path on UE-V computers or a Server Message Block (SMB) network share that stores all the custom settings location templates.</span></span> <span data-ttu-id="f4d06-182">UE-V Agent のスケジュールされたタスクでは、この場所が毎日1回チェックされ、このフォルダー内のテンプレートに基づいて同期動作が更新されます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-182">A scheduled task in the UE-V Agent checks this location one time each day and updates its synchronization behavior, based on the templates in this folder.</span></span>

<span data-ttu-id="f4d06-183">UE-V Agent は、前回フォルダーがチェックされ、削除されたテンプレートの登録を解除した後に、このフォルダーに追加または更新されたテンプレートを登録します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-183">The UE-V Agent registers templates that were added or updated in this folder after the last time that the folder was checked and unregisters templates that are removed.</span></span> <span data-ttu-id="f4d06-184">既定では、テンプレートは1日に1回、午前3:30 時に登録および登録解除されます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-184">By default, templates are registered and unregistered one time per day at 3:30 A.M.</span></span> <span data-ttu-id="f4d06-185">タスクスケジューラとシステム起動時のローカル時刻。</span><span class="sxs-lookup"><span data-stu-id="f4d06-185">local time by the Task Scheduler and at system startup.</span></span> <span data-ttu-id="f4d06-186">このスケジュールされたタスクの頻度をカスタマイズする方法については、「 [ue-v のスケジュールされたタスクの頻度を変更](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4d06-186">To customize the frequency of this scheduled task, see [Changing the Frequency of UE-V 2.x Scheduled Tasks](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md).</span></span>

<span data-ttu-id="f4d06-187">インストールコマンドラインオプション、グループポリシー、WMI、または Windows PowerShell を使用して、設定テンプレートカタログのパスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-187">You can configure the settings template catalog path by using the installation command-line options, Group Policy, WMI, or Windows PowerShell.</span></span> <span data-ttu-id="f4d06-188">設定テンプレートカタログパスに保存されているテンプレートは、スケジュールされたタスクによって自動的に登録および登録解除されます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-188">Templates that are stored at the settings template catalog path are automatically registered and unregistered by a scheduled task.</span></span>

**<span data-ttu-id="f4d06-189">UE-V 2. x の設定テンプレートカタログを構成するには</span><span class="sxs-lookup"><span data-stu-id="f4d06-189">To configure the settings template catalog for UE-V 2.x</span></span>**

1.  <span data-ttu-id="f4d06-190">UE-V 設定テンプレートカタログが保存されているコンピューターに新しいフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-190">Create a new folder on the computer that stores the UE-V settings template catalog.</span></span>

2.  <span data-ttu-id="f4d06-191">設定テンプレートカタログフォルダーに対して、次の共有レベル (SMB) のアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-191">Set the following share-level (SMB) permissions for the settings template catalog folder.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="f4d06-192">ユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="f4d06-192">User account</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="f4d06-193">推奨されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="f4d06-193">Recommended permissions</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="f4d06-194">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="f4d06-194">Everyone</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f4d06-195">権限なし</span><span class="sxs-lookup"><span data-stu-id="f4d06-195">No Permissions</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="f4d06-196">ドメインコンピューター</span><span class="sxs-lookup"><span data-stu-id="f4d06-196">Domain Computers</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f4d06-197">アクセス許可レベルの読み取り</span><span class="sxs-lookup"><span data-stu-id="f4d06-197">Read Permission Levels</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="f4d06-198">管理者</span><span class="sxs-lookup"><span data-stu-id="f4d06-198">Administrators</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f4d06-199">読み取り/書き込みアクセス許可レベル</span><span class="sxs-lookup"><span data-stu-id="f4d06-199">Read/Write Permission Levels</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

3.  <span data-ttu-id="f4d06-200">設定テンプレートカタログフォルダーに対して、次の NTFS ファイルシステム権限を設定します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-200">Set the following NTFS file system permissions for the settings template catalog folder.</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="f4d06-201">ユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="f4d06-201">User account</span></span></th>
    <th align="left"><span data-ttu-id="f4d06-202">推奨されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="f4d06-202">Recommended permissions</span></span></th>
    <th align="left"><span data-ttu-id="f4d06-203">適用対象</span><span class="sxs-lookup"><span data-stu-id="f4d06-203">Apply to</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="f4d06-204">作成者/所有者</span><span class="sxs-lookup"><span data-stu-id="f4d06-204">Creator/Owner</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f4d06-205">フルコントロール</span><span class="sxs-lookup"><span data-stu-id="f4d06-205">Full Control</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f4d06-206">このフォルダー、サブフォルダー、ファイル</span><span class="sxs-lookup"><span data-stu-id="f4d06-206">This Folder, Subfolders and Files</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="f4d06-207">ドメインコンピューター</span><span class="sxs-lookup"><span data-stu-id="f4d06-207">Domain Computers</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f4d06-208">フォルダーの内容の一覧表示と読み取り</span><span class="sxs-lookup"><span data-stu-id="f4d06-208">List Folder Contents and Read</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f4d06-209">このフォルダー、サブフォルダー、ファイル</span><span class="sxs-lookup"><span data-stu-id="f4d06-209">This Folder, Subfolders and Files</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="f4d06-210">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="f4d06-210">Everyone</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f4d06-211">権限なし</span><span class="sxs-lookup"><span data-stu-id="f4d06-211">No Permissions</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f4d06-212">権限なし</span><span class="sxs-lookup"><span data-stu-id="f4d06-212">No Permissions</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="f4d06-213">管理者</span><span class="sxs-lookup"><span data-stu-id="f4d06-213">Administrators</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f4d06-214">フルコントロール</span><span class="sxs-lookup"><span data-stu-id="f4d06-214">Full Control</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f4d06-215">このフォルダー、サブフォルダー、ファイル</span><span class="sxs-lookup"><span data-stu-id="f4d06-215">This Folder, Subfolders and Files</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

4.  <span data-ttu-id="f4d06-216">[ **OK** ] をクリックしてダイアログボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-216">Click **OK** to close the dialog boxes.</span></span>

<span data-ttu-id="f4d06-217">少なくとも、ネットワーク共有は、ドメインコンピューターグループに対するアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4d06-217">At a minimum, the network share must grant permissions for the Domain Computers group.</span></span> <span data-ttu-id="f4d06-218">さらに、保存されたテンプレートを管理する管理者に、ネットワーク共有フォルダーへのアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-218">In addition, grant access permissions for the network share folder to administrators who are to manage the stored templates.</span></span>

## <a href="" id="createcustomtemplates"></a><span data-ttu-id="f4d06-219">カスタム設定の場所テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="f4d06-219">Create Custom Settings Location Templates</span></span>


<span data-ttu-id="f4d06-220">UE-V Generator を使って、基幹業務アプリケーションやその他のカスタムアプリケーションの設定場所テンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-220">Use the UE-V Generator to create settings location templates for line-of-business applications or other custom applications.</span></span> <span data-ttu-id="f4d06-221">アプリケーションのテンプレートが作成されたら、それをコンピューターに展開することで、そのアプリケーションの設定が同期されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-221">After the template for an application is created, you can deploy it to computers so that settings are synchronized for that application.</span></span>

**<span data-ttu-id="f4d06-222">Ue-v Generator を使用して UE-V 設定の場所テンプレートを作成するには</span><span class="sxs-lookup"><span data-stu-id="f4d06-222">To create a UE-V settings location template with the UE-V Generator</span></span>**

1.  <span data-ttu-id="f4d06-223">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **microsoft user Experience Virtualization**]、[ **microsoft user experience virtualization Generator**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f4d06-223">Click **Start**, click **All Programs**, click **Microsoft User Experience Virtualization**, and then click **Microsoft User Experience Virtualization Generator**.</span></span>

2.  <span data-ttu-id="f4d06-224">[**設定場所テンプレートの作成] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="f4d06-224">Click **Create a settings location template**.</span></span>

3.  <span data-ttu-id="f4d06-225">アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-225">Specify the application.</span></span> <span data-ttu-id="f4d06-226">設定場所テンプレートを作成するアプリケーション (.exe) またはアプリケーションショートカット (.lnk) のファイルパスを参照します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-226">Browse to the file path of the application (.exe) or the application shortcut (.lnk) for which you want to create a settings location template.</span></span> <span data-ttu-id="f4d06-227">必要に応じて、コマンドライン引数 (存在する場合) と作業ディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-227">Specify the command-line arguments, if any, and working directory, if any.</span></span> <span data-ttu-id="f4d06-228">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-228">Click **Next** to continue.</span></span>

    <span data-ttu-id="f4d06-229">**注** アプリケーションが起動する前に、システムによって**ユーザーアカウント制御**のプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-229">**Note** Before the application is started, the system displays a prompt for **User Account Control**.</span></span> <span data-ttu-id="f4d06-230">レジストリと、アプリケーションが設定を保存するために使用するファイルの場所を監視するには、アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="f4d06-230">Permission is required to monitor the registry and file locations that the application uses to store settings.</span></span>

     

4.  <span data-ttu-id="f4d06-231">アプリケーションが起動したら、アプリケーションを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-231">After the application starts, close the application.</span></span> <span data-ttu-id="f4d06-232">UE-V Generator は、アプリケーションの設定が保存されている場所を記録します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-232">The UE-V Generator records the locations where the application stores its settings.</span></span>

5.  <span data-ttu-id="f4d06-233">処理が完了したら、[**次へ**] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-233">After the process is completed, click **Next** to continue.</span></span>

6.  <span data-ttu-id="f4d06-234">このアプリケーションで同期する、適切なレジストリ設定の場所と設定ファイルの場所の横にあるチェックボックスを確認して選択します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-234">Review and select the check boxes that are next to the appropriate registry settings locations and settings file locations to synchronize for this application.</span></span> <span data-ttu-id="f4d06-235">この一覧には、設定場所に関する次の2つのカテゴリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4d06-235">The list includes the following two categories for settings locations:</span></span>

    -   <span data-ttu-id="f4d06-236">**標準**: HKEY \ _CURRENT \ _USER キーの下にあるレジストリに保存されているアプリケーション設定、または \\**ユーザー** \ \ \ [ユーザー名 \] **\ \ の**ファイルフォルダーの下にあり  \\  **Roaming**ます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-236">**Standard**: Application settings that are stored in the registry under the HKEY\_CURRENT\_USER keys or in the file folders under \\ **Users** \\ \[User name\] \\ **AppData** \\ **Roaming**.</span></span> <span data-ttu-id="f4d06-237">UE-V Generator では、これらの設定が既定で含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4d06-237">The UE-V Generator includes these settings by default.</span></span>

    -   <span data-ttu-id="f4d06-238">**非標準**: 場所以外に保存されているアプリケーション設定は、[設定] データストレージのベストプラクティスで指定されています (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="f4d06-238">**Nonstandard**: Application settings that are stored outside the locations are specified in the best practices for settings data storage (optional).</span></span> <span data-ttu-id="f4d06-239">これには、**ユーザー** \ \ \ [ユーザー名 \] \ \ **AppData**ローカルのファイルとフォルダーが含ま  \\  **Local**れます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-239">These include files and folders under **Users** \\ \[User name\] \\ **AppData** \\ **Local**.</span></span> <span data-ttu-id="f4d06-240">これらの場所を確認して、設定場所テンプレートに含めるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-240">Review these locations to determine whether to include them in the settings location template.</span></span> <span data-ttu-id="f4d06-241">[場所] チェックボックスをオンにして追加します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-241">Select the locations check boxes to include them.</span></span>

    <span data-ttu-id="f4d06-242">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-242">Click **Next** to continue.</span></span>

7.  <span data-ttu-id="f4d06-243">設定場所テンプレートの**プロパティ**、**レジストリ**の場所、**ファイル**の場所を確認して編集します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-243">Review and edit any **Properties**, **Registry** locations, and **Files** locations for the settings location template.</span></span>

    -   <span data-ttu-id="f4d06-244">[**プロパティ**] タブで、次のプロパティを編集します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-244">Edit the following properties on the **Properties** tab:</span></span>

        -   <span data-ttu-id="f4d06-245">[ **Application name**]: program files プロパティの説明に記載されているアプリケーション名。</span><span class="sxs-lookup"><span data-stu-id="f4d06-245">**Application Name**: The application name that is written in the description of the program files properties.</span></span>

        -   <span data-ttu-id="f4d06-246">[ **Program name**]: プログラムファイルのプロパティから取得したプログラムの名前。</span><span class="sxs-lookup"><span data-stu-id="f4d06-246">**Program name**: The name of the program that is taken from the program file properties.</span></span> <span data-ttu-id="f4d06-247">通常、この名前には .exe ファイル名拡張子が付きます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-247">This name usually has the .exe file name extension.</span></span>

        -   <span data-ttu-id="f4d06-248">[**製品バージョン**: アプリケーションの .exe ファイルの製品バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="f4d06-248">**Product version**: The product version number of the .exe file of the application.</span></span> <span data-ttu-id="f4d06-249">このプロパティは、**ファイルバージョン**と組み合わせて、設定場所テンプレートのターゲットとなるアプリケーションを決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-249">This property, in conjunction with the **File version**, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="f4d06-250">このプロパティは、メジャーバージョン番号を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f4d06-250">This property accepts a major version number.</span></span> <span data-ttu-id="f4d06-251">このプロパティが空の場合、[設定の場所] テンプレートは製品のすべてのバージョンに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-251">If this property is empty, the settings location template applies to all versions of the product.</span></span>

        -   <span data-ttu-id="f4d06-252">**ファイルのバージョン**: アプリケーションの .exe ファイルのファイルバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="f4d06-252">**File version**: The file version number of the .exe file of the application.</span></span> <span data-ttu-id="f4d06-253">このプロパティは**製品バージョン**と組み合わせて、設定場所テンプレートのターゲットとなるアプリケーションを決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-253">This property, in conjunction with the **Product version**, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="f4d06-254">このプロパティは、メジャーバージョン番号を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f4d06-254">This property accepts a major version number.</span></span> <span data-ttu-id="f4d06-255">このプロパティが空の場合は、設定の場所テンプレートがプログラムのすべてのバージョンに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-255">If this property is empty, the settings location template applies to all versions of the program.</span></span>

        -   <span data-ttu-id="f4d06-256">**テンプレート作成者の名前**(省略可能): 設定場所テンプレートの作成者の名前。</span><span class="sxs-lookup"><span data-stu-id="f4d06-256">**Template author name** (optional): The name of the settings location template author.</span></span>

        -   <span data-ttu-id="f4d06-257">**テンプレート作成者のメール**(オプション): 設定場所テンプレートの作成者のメールアドレス。</span><span class="sxs-lookup"><span data-stu-id="f4d06-257">**Template author email** (optional): The email address of the settings location template author.</span></span>

    -   <span data-ttu-id="f4d06-258">[**レジストリ**] タブには、設定場所テンプレートに含まれているレジストリの場所の**キー**と**範囲**が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-258">The **Registry** tab lists the **Key** and **Scope** of the registry locations that are included in the settings location template.</span></span> <span data-ttu-id="f4d06-259">[**タスク**] ドロップダウンメニューを使用して、レジストリの場所を編集します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-259">Edit the registry locations by using the **Tasks** drop-down menu.</span></span> <span data-ttu-id="f4d06-260">タスクを使用すると、新しいキーの追加、既存のキーの名前または範囲の編集、キーの削除、キーが存在する場所のレジストリの参照を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-260">Tasks enable you to add new keys, edit the name or scope of existing keys, delete keys, and browse the registry where the keys are located.</span></span> <span data-ttu-id="f4d06-261">すべての**設定**のスコープを使用して、指定したキーの下にすべてのレジストリ設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-261">Use the **All Settings** scope to include all the registry settings under the specified key.</span></span> <span data-ttu-id="f4d06-262">すべての**設定とサブ**キーを使用して、指定したキー、サブキー、サブキーの設定の下にすべてのレジストリ設定を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-262">Use the **All Settings and Subkeys** to include all the registry settings under the specified key, subkeys, and subkey settings.</span></span>

    -   <span data-ttu-id="f4d06-263">[**ファイル**] タブには、設定場所テンプレートに含まれているファイルの場所のファイルパスとファイルマスクが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-263">The **Files** tab lists the file path and file mask of the file locations that are included in the settings location template.</span></span> <span data-ttu-id="f4d06-264">[**タスク**] ドロップダウンメニューを使用して、ファイルの場所を編集します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-264">Edit the file locations by use of the **Tasks** drop-down menu.</span></span> <span data-ttu-id="f4d06-265">ファイルの場所のタスクでは、新しいファイルまたはフォルダーの場所を追加したり、既存のファイルまたはフォルダーの範囲を編集したり、ファイルまたはフォルダーを削除したり、エクスプローラーで選択した場所を開くことができます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-265">Tasks for file locations enable you to add new files or folder locations, edit the scope of existing files or folders, delete files or folders, and open the selected location in Windows Explorer.</span></span> <span data-ttu-id="f4d06-266">指定したフォルダー内のすべてのファイルを含めるには、[ファイルマスク] を空のままにします。</span><span class="sxs-lookup"><span data-stu-id="f4d06-266">Leave the file mask empty to include all files in the specified folder.</span></span>

8.  <span data-ttu-id="f4d06-267">[**作成**] をクリックし、[**保存**] をクリックして、コンピューターに設定の場所テンプレートを保存します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-267">Click **Create**, and then click **Save** to save the settings location template on the computer.</span></span>

9.  <span data-ttu-id="f4d06-268">[**閉じる**] をクリックして、設定テンプレートウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-268">Click **Close** to close the Settings Template Wizard.</span></span> <span data-ttu-id="f4d06-269">UE-V Generator アプリケーションを終了します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-269">Exit the UE-V Generator application.</span></span>

    <span data-ttu-id="f4d06-270">アプリケーションの設定場所テンプレートを作成したら、テンプレートをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4d06-270">After you have created the settings location template for an application, you should test the template.</span></span> <span data-ttu-id="f4d06-271">ラボ環境にテンプレートを展開してから、エンタープライズで実働環境に配置します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-271">Deploy the template in a lab environment before you put it into production in the enterprise.</span></span>

<span data-ttu-id="f4d06-272">[Ue-v のアプリケーションテンプレートスキーマリファレンス](https://technet.microsoft.com/library/dn763947.aspx)では、ue-v 設定の場所テンプレートの XML 構造について詳しく説明し、これらのファイルを編集するためのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-272">[Application Template Schema Reference for UE-V](https://technet.microsoft.com/library/dn763947.aspx) details the XML structure of the UE-V settings location template and provides guidance for editing these files.</span></span>

## <a href="" id="deploycustomtemplates"></a><span data-ttu-id="f4d06-273">カスタム設定の場所テンプレートを展開する</span><span class="sxs-lookup"><span data-stu-id="f4d06-273">Deploy the Custom Settings Location Templates</span></span>


<span data-ttu-id="f4d06-274">UE-V Generator を使用して設定場所テンプレートを作成したら、アプリケーションの設定が正しく同期されていることを確認するためにテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4d06-274">After you create a settings location template with the UE-V Generator, you should test it to ensure that the application settings are synchronized correctly.</span></span> <span data-ttu-id="f4d06-275">次に、エンタープライズ内のコンピューターに設定場所テンプレートを安全に展開できます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-275">You can then safely deploy the settings location template to computers in the enterprise.</span></span>

<span data-ttu-id="f4d06-276">設定場所テンプレートは、次のいずれかの方法を使用して展開できます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-276">Settings location templates can be deployed by using one of these methods:</span></span>

-   <span data-ttu-id="f4d06-277">System Center Configuration Manager などのエンタープライズソフトウェア配布 (ESD) システム</span><span class="sxs-lookup"><span data-stu-id="f4d06-277">An enterprise software distribution (ESD) system such as System Center Configuration Manager</span></span>

-   <span data-ttu-id="f4d06-278">グループ ポリシーの基本設定</span><span class="sxs-lookup"><span data-stu-id="f4d06-278">Group Policy preferences</span></span>

-   <span data-ttu-id="f4d06-279">UE-V 設定テンプレートカタログ</span><span class="sxs-lookup"><span data-stu-id="f4d06-279">A UE-V settings template catalog</span></span>

<span data-ttu-id="f4d06-280">ESD システムまたはグループポリシーオブジェクトを使用して展開されるテンプレートは、UE-V Windows Management Instrumentation (WMI) または Windows PowerShell を使って登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4d06-280">Templates that are deployed by using an ESD system or Group Policy Objects must be registered through UE-V Windows Management Instrumentation (WMI) or Windows PowerShell.</span></span> <span data-ttu-id="f4d06-281">設定テンプレートカタログの場所に保存されているテンプレートは、UE-V Agent によって自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-281">Templates that are stored in the settings template catalog location are automatically registered by the UE-V Agent.</span></span>

**<span data-ttu-id="f4d06-282">設定テンプレートカタログパスを使用して UE-V 設定の場所テンプレートを展開するには</span><span class="sxs-lookup"><span data-stu-id="f4d06-282">To use the settings template catalog path to deploy UE-V settings location templates</span></span>**

1.  <span data-ttu-id="f4d06-283">設定テンプレートカタログとして定義されているネットワーク共有フォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-283">Browse to the network share folder that is defined as the settings template catalog.</span></span>

2.  <span data-ttu-id="f4d06-284">UE-V のコンピューターに必要な UE-V Agent テンプレートの構成を反映するために、設定テンプレートカタログの設定場所テンプレートを追加、削除、または更新します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-284">Add, remove, or update settings location templates in the settings template catalog to reflect the UE-V Agent template configuration that you want for UE-V computers.</span></span>

    <span data-ttu-id="f4d06-285">**注** コンピューター上のテンプレートが毎日更新されます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-285">**Note** Templates on computers are updated daily.</span></span> <span data-ttu-id="f4d06-286">更新プログラムは、設定テンプレートカタログの変更に基づいています。</span><span class="sxs-lookup"><span data-stu-id="f4d06-286">The update is based on changes to the settings template catalog.</span></span>

     

3.  <span data-ttu-id="f4d06-287">UE-V Agent を実行しているコンピューター上でテンプレートを手動で更新するには、管理者特権のコマンドプロンプトを開き、 \*\*% Program files% ¥ Microsoft User Experience Virtualization \ \ Agent \ \ &lt; x86 または x64 &gt; \*\*を参照して、 **ApplySettingsTemplateCatalog.exe**を実行します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-287">To manually update templates on a computer that runs the UE-V Agent, open an elevated command prompt, and browse to **%Program Files%\\Microsoft User Experience Virtualization \\ Agent \\ &lt;x86 or x64 &gt;**, and then run **ApplySettingsTemplateCatalog.exe**.</span></span>

    <span data-ttu-id="f4d06-288">**注** このプログラムは、コンピューターの3:30 起動時に自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="f4d06-288">**Note** This program runs automatically during computer startup and daily at 3:30 A. M.</span></span> <span data-ttu-id="f4d06-289">カタログに最近追加された新しいテンプレートを収集します。</span><span class="sxs-lookup"><span data-stu-id="f4d06-289">to gather any new templates that were recently added to the catalog.</span></span>

     






## <span data-ttu-id="f4d06-290">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f4d06-290">Related topics</span></span>


[<span data-ttu-id="f4d06-291">UE-V の展開を準備する</span><span class="sxs-lookup"><span data-stu-id="f4d06-291">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[<span data-ttu-id="f4d06-292">UE-V 2.x の必要な機能を展開する</span><span class="sxs-lookup"><span data-stu-id="f4d06-292">Deploy Required Features for UE-V 2.x</span></span>](deploy-required-features-for-ue-v-2x-new-uevv2.md)

 

 





