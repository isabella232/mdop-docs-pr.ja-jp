---
title: UE-V 1.0 のカスタム テンプレートの展開計画
description: UE-V 1.0 のカスタム テンプレートの展開計画
author: dansimp
ms.assetid: be76fc9a-31ca-4290-af11-7640dcb87d50
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5d17f058bff452f88003ab4488daa7afa846f688
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821194"
---
# <span data-ttu-id="958e8-103">UE-V 1.0 のカスタム テンプレートの展開計画</span><span class="sxs-lookup"><span data-stu-id="958e8-103">Planning for Custom Template Deployment for UE-V 1.0</span></span>


<span data-ttu-id="958e8-104">Microsoft User Experience Virtualization (UE-V) では、UE-V でキャプチャおよび適用される設定を定義する設定場所テンプレート (XML ファイル) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="958e8-104">Microsoft User Experience Virtualization (UE-V) uses settings location templates (XML files) that define the settings that are captured and applied by UE-V.</span></span> <span data-ttu-id="958e8-105">UE-V Generator を使って、既定の UE-V テンプレートに含まれているアプリケーション以外のアプリケーションの設定をユーザーがローミングできるように、カスタム設定の場所テンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="958e8-105">You can use the UE-V Generator to create custom settings location templates that let users roam the settings of applications other than those that are included in the default UE-V templates.</span></span> <span data-ttu-id="958e8-106">カスタムテンプレートをテストして、アプリケーションの設定がテスト環境で正しくローミングされていることを確認したら、これらの設定場所テンプレートをエンタープライズ内のコンピューターに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="958e8-106">After you test the custom template to ensure that the application settings roam correctly in a test environment, you can deploy these settings location templates to computers in the enterprise.</span></span>

<span data-ttu-id="958e8-107">カスタム設定の場所テンプレートは、エンタープライズソフトウェア配布 (ESD) などの既存の展開インフラストラクチャと共に、グループポリシーの基本設定を使って、または UE-V 設定テンプレートカタログを構成することによって展開できます。</span><span class="sxs-lookup"><span data-stu-id="958e8-107">You can deploy your custom settings location templates with an existing deployment infrastructure, such as Enterprise Software Distribution (ESD), with Group Policy preferences, or by configuring a UE-V settings template catalog.</span></span> <span data-ttu-id="958e8-108">ESD またはグループポリシーを使用して展開されるテンプレートは、UE-V WMI または PowerShell で登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="958e8-108">Templates that are deployed by using ESD or Group Policy must be registered with UE-V WMI or PowerShell.</span></span>

## <span data-ttu-id="958e8-109">設定テンプレートカタログ</span><span class="sxs-lookup"><span data-stu-id="958e8-109">Settings template catalog</span></span>


<span data-ttu-id="958e8-110">ユーザーエクスペリエンスの仮想化設定テンプレートカタログは、カスタム設定の場所テンプレートをすべて保存する、UE-V のコンピューター上のフォルダーパスまたはサーバーメッセージブロック (SMB) ネットワーク共有です。</span><span class="sxs-lookup"><span data-stu-id="958e8-110">The User Experience Virtualization settings template catalog is a folder path on UE-V computers or a Server Message Block (SMB) network share that stores all the custom settings location templates.</span></span> <span data-ttu-id="958e8-111">UE-V agent は、新しいまたは更新されたテンプレートをこの場所から取得します。</span><span class="sxs-lookup"><span data-stu-id="958e8-111">The UE-V agent retrieves new or updated templates from this location.</span></span> <span data-ttu-id="958e8-112">UE-V agent は、1日に1回この場所をチェックし、このフォルダー内のテンプレートに基づいて同期動作を更新します。</span><span class="sxs-lookup"><span data-stu-id="958e8-112">The UE-V agent checks this location once each day and updates its synchronization behavior based on the templates in this folder.</span></span> <span data-ttu-id="958e8-113">前回フォルダーがチェックされてからこのフォルダーに追加または更新されたテンプレートは、UE-V agent によって登録されます。</span><span class="sxs-lookup"><span data-stu-id="958e8-113">Templates that were added or updated in this folder since the last time that the folder was checked are registered by the UE-V agent.</span></span> <span data-ttu-id="958e8-114">UE-V agent deregisters テンプレートはこのフォルダーから削除されます。</span><span class="sxs-lookup"><span data-stu-id="958e8-114">The UE-V agent deregisters templates that are removed from this folder.</span></span> <span data-ttu-id="958e8-115">既定では、テンプレートは1日に1回、午前3:30 時に登録および登録解除されます。</span><span class="sxs-lookup"><span data-stu-id="958e8-115">By default, templates are registered and unregistered one time per day at 3:30 A.M.</span></span> <span data-ttu-id="958e8-116">タスクスケジューラによるローカル時刻。</span><span class="sxs-lookup"><span data-stu-id="958e8-116">local time by the task scheduler.</span></span> <span data-ttu-id="958e8-117">UE-V のタスクの詳細については、「 [ue-v のスケジュールされたタスクの頻度を変更する](changing-the-frequency-of-ue-v-scheduled-tasks.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="958e8-117">For more information about the UE-V tasks, see [Changing the Frequency of UE-V Scheduled Tasks](changing-the-frequency-of-ue-v-scheduled-tasks.md).</span></span>

<span data-ttu-id="958e8-118">[Install] コマンドラインオプション、グループポリシー、WMI、または PowerShell を使用して、設定テンプレートカタログのパスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="958e8-118">You can configure the settings template catalog path by using the install command-line options, Group Policy, WMI, or PowerShell.</span></span> <span data-ttu-id="958e8-119">設定テンプレートカタログパスに保存されているテンプレートは、スケジュールされたタスクによって自動的に登録および登録解除されます。</span><span class="sxs-lookup"><span data-stu-id="958e8-119">Templates that are stored at the settings template catalog path are automatically registered and unregistered by a scheduled task.</span></span> <span data-ttu-id="958e8-120">必要に応じて、このスケジュールされたタスクをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="958e8-120">You can customize this scheduled task as needed.</span></span>

## <span data-ttu-id="958e8-121">既定の Microsoft テンプレートを置き換える</span><span class="sxs-lookup"><span data-stu-id="958e8-121">Replace the default Microsoft templates</span></span>


<span data-ttu-id="958e8-122">UE-V agent は、一般的な Microsoft アプリケーションと Windows 設定用の設定場所テンプレートの既定のグループをインストールします。</span><span class="sxs-lookup"><span data-stu-id="958e8-122">The UE-V agent installs a default group of settings location templates for common Microsoft applications and Windows settings.</span></span> <span data-ttu-id="958e8-123">エンタープライズでこれらのテンプレートのカスタマイズバージョンが必要な場合、UE-V agent は設定テンプレートカタログを使用するように構成することができます。次に、既定の Microsoft テンプレートを置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="958e8-123">If your enterprise needs customized versions of these templates, the UE-V agent can be configured to use a settings template catalog and you should then replace the default Microsoft templates.</span></span>

<span data-ttu-id="958e8-124">UE-V agent のインストール中に、コマンドラインパラメーターを使用して、 `RegisterMSTemplates` 既定の Microsoft テンプレートの登録を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="958e8-124">During the installation of the UE-V agent, the command-line parameter, `RegisterMSTemplates`, can be used to disable the registration of the default Microsoft templates.</span></span> <span data-ttu-id="958e8-125">UE-V パラメーターの設定方法の詳細については、「 [Ue-v 構成メソッドの計画](planning-for-ue-v-configuration-methods.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="958e8-125">For more information about how to set the UE-V parameters, see [Planning for UE-V Configuration Methods](planning-for-ue-v-configuration-methods.md).</span></span>

<span data-ttu-id="958e8-126">グループポリシーを使用して設定テンプレートカタログのパスを構成する場合は、既定の Microsoft テンプレートを置き換えるかどうかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="958e8-126">When you use Group Policy to configure the settings template catalog path, you can choose to replace the default Microsoft templates.</span></span> <span data-ttu-id="958e8-127">既定の Microsoft テンプレートを置き換えるようにポリシー設定を構成した場合、UE-V agent によってインストールされたすべての既定の Microsoft テンプレートはコンピューターから削除され、設定テンプレートカタログに含まれているテンプレートのみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="958e8-127">If you configure the policy settings to replace the default Microsoft templates, all of the default Microsoft templates that are installed by the UE-V agent will be deleted from the computer, and only the templates that are located in the settings template catalog will be used.</span></span> <span data-ttu-id="958e8-128">既定の Microsoft テンプレートを上書きするには、UE-V Agent 構成設定を `RegisterMSTemplates` true に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="958e8-128">The UE-V Agent configuration setting `RegisterMSTemplates` must be set to true in order to override the default Microsoft template.</span></span>

<span data-ttu-id="958e8-129">**注** 有効にした後にこのポリシー設定を無効にした場合、UE-V agent では既定の Microsoft テンプレートは復元されません。</span><span class="sxs-lookup"><span data-stu-id="958e8-129">**Note** If you disable this policy setting after it has been enabled, the UE-V agent will not restore the default Microsoft templates.</span></span>

 

<span data-ttu-id="958e8-130">既定の Microsoft テンプレートと同じ ID を使用するように設定テンプレートカタログにカスタマイズされたテンプレートがあり、UE-V agent が既定の Microsoft テンプレートと置き換えるように構成されていない場合、カタログ内の Microsoft テンプレートは無視されます。</span><span class="sxs-lookup"><span data-stu-id="958e8-130">If there are customized templates in the settings template catalog that use the same ID as the default Microsoft templates, and the UE-V agent is not configured to replace the default Microsoft templates, the Microsoft templates in the catalog will be ignored.</span></span>

<span data-ttu-id="958e8-131">また、UE-V PowerShell 機能を使用して、既定のテンプレートを置き換えることもできます。</span><span class="sxs-lookup"><span data-stu-id="958e8-131">You can also replace the default templates by using the UE-V PowerShell features.</span></span> <span data-ttu-id="958e8-132">既定の Microsoft テンプレートを PowerShell で置き換えるには、既定の Microsoft テンプレートの登録を解除し、カスタマイズされたテンプレートを登録します。</span><span class="sxs-lookup"><span data-stu-id="958e8-132">To replace the default Microsoft Template with PowerShell, unregister all of the default Microsoft templates, and then register the customized templates.</span></span>

<span data-ttu-id="958e8-133">**注** 新しい設定テンプレートがアプリケーションに展開されている場合でも、古い設定パッケージは設定の保存場所に残ります。</span><span class="sxs-lookup"><span data-stu-id="958e8-133">**Note** Old settings packages remain in the settings storage location even if new settings templates are deployed for an application.</span></span> <span data-ttu-id="958e8-134">これらのパッケージはエージェントによって読み取られることはありませんが、自動的に削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="958e8-134">These packages are not read by the agent, but neither are they automatically deleted.</span></span>

 

## <span data-ttu-id="958e8-135">関連トピック</span><span class="sxs-lookup"><span data-stu-id="958e8-135">Related topics</span></span>


[<span data-ttu-id="958e8-136">UE-V 1.0 の計画</span><span class="sxs-lookup"><span data-stu-id="958e8-136">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

[<span data-ttu-id="958e8-137">UE-V 1.0 を使用して同期するアプリケーションの計画</span><span class="sxs-lookup"><span data-stu-id="958e8-137">Planning Which Applications to Synchronize with UE-V 1.0</span></span>](planning-which-applications-to-synchronize-with-ue-v-10.md)

[<span data-ttu-id="958e8-138">UE-V の構成方法の計画</span><span class="sxs-lookup"><span data-stu-id="958e8-138">Planning for UE-V Configuration Methods</span></span>](planning-for-ue-v-configuration-methods.md)

<span data-ttu-id="958e8-139">カスタムテンプレートの展開を計画する</span><span class="sxs-lookup"><span data-stu-id="958e8-139">Planning for Custom Template Deployment</span></span>
 

 





