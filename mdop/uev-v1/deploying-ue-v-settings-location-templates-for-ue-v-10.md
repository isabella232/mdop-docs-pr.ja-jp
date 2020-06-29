---
title: UE-V 1.0 の UE-V 設定場所テンプレートの展開
description: UE-V 1.0 の UE-V 設定場所テンプレートの展開
author: dansimp
ms.assetid: 7e0cc553-14f7-40fa-828a-281c8d2d1934
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b276fb9d6c0b3749f9818483869dfe98bbc147c7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827124"
---
# <span data-ttu-id="7e158-103">UE-V 1.0 の UE-V 設定場所テンプレートの展開</span><span class="sxs-lookup"><span data-stu-id="7e158-103">Deploying UE-V Settings Location Templates for UE-V 1.0</span></span>


<span data-ttu-id="7e158-104">Microsoft User Experience Virtualization (UE-V) では、ユーザーエクスペリエンスの仮想化によってキャプチャおよび適用される設定を定義する設定場所テンプレート (XML ファイル) を使用します。</span><span class="sxs-lookup"><span data-stu-id="7e158-104">Microsoft User Experience Virtualization (UE-V) uses settings location templates (XML files) that define the settings that are captured and applied by User Experience Virtualization.</span></span> <span data-ttu-id="7e158-105">UE-V には、標準テンプレートのセット、および、カスタム設定の場所テンプレートを作成できる、UE-V Generator のツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7e158-105">UE-V includes a set of standard templates, as well as a tool, the UE-V Generator, which allows you to create custom settings location templates.</span></span> <span data-ttu-id="7e158-106">設定場所テンプレートを作成したら、テスト環境でアプリケーション設定が正しく移動されるようにテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e158-106">After you create a settings location template, you should test it to ensure that the application settings roam correctly in a test environment.</span></span> <span data-ttu-id="7e158-107">次に、エンタープライズ内のコンピューターに設定場所テンプレートを安全に展開できます。</span><span class="sxs-lookup"><span data-stu-id="7e158-107">You can then safely deploy the settings location template to computers in the enterprise.</span></span>

<span data-ttu-id="7e158-108">設定場所テンプレートは、エンタープライズソフトウェア配布 (ESD)、グループポリシー設定、または UE-V 設定テンプレートカタログを使って展開できます。</span><span class="sxs-lookup"><span data-stu-id="7e158-108">Settings location templates can be deployed by using enterprise software distribution (ESD), Group Policy preferences, or by configuring a UE-V settings template catalog.</span></span> <span data-ttu-id="7e158-109">ESD またはグループポリシーを使用して展開されるテンプレートは、UE-V WMI または PowerShell を使って登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e158-109">Templates that are deployed by using an ESD or Group Policy must be registered through UE-V WMI or PowerShell.</span></span> <span data-ttu-id="7e158-110">設定テンプレートカタログの場所に保存されているテンプレートは、UE-V agent によって自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="7e158-110">Templates that are stored in the settings template catalog location are automatically registered by the UE-V agent.</span></span>

## <span data-ttu-id="7e158-111">設定テンプレートカタログのパスを使用して設定場所テンプレートを展開する</span><span class="sxs-lookup"><span data-stu-id="7e158-111">Deploy the settings location templates with a settings template catalog path</span></span>


<span data-ttu-id="7e158-112">UE-V の設定の場所テンプレートカタログのパスは、次のメソッドを使用して定義できます。グループポリシー、エージェントインストールのコマンドラインパラメーター、WMI、または PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7e158-112">The UE-V settings location template catalog path can be defined by using the following methods: Group Policy, the agent install command-line parameters, WMI, or PowerShell.</span></span> <span data-ttu-id="7e158-113">テンプレートカタログのパスを定義した後、UE-V agent はこの場所から新しいまたは更新されたテンプレートを取得します。</span><span class="sxs-lookup"><span data-stu-id="7e158-113">After the template catalog path has been defined, the UE-V agent retrieves the new or updated templates from this location.</span></span> <span data-ttu-id="7e158-114">UE-V agent は、1日に1回この場所をチェックし、このフォルダー内のテンプレートに基づいて同期動作を更新します。</span><span class="sxs-lookup"><span data-stu-id="7e158-114">The UE-V agent checks this location once each day and updates its synchronization behavior based on the templates found in this folder.</span></span> <span data-ttu-id="7e158-115">前回のチェック後にこのフォルダーで追加または更新されたテンプレートは、UE-V agent によって登録されます。</span><span class="sxs-lookup"><span data-stu-id="7e158-115">Templates that have been added or updated in this folder since the last check are registered by the UE-V agent.</span></span> <span data-ttu-id="7e158-116">UE-V agent では、このフォルダーから削除されたテンプレートの登録を解除することもできます。</span><span class="sxs-lookup"><span data-stu-id="7e158-116">The UE-V agent also unregisters templates that have been removed from this folder.</span></span> <span data-ttu-id="7e158-117">テンプレートは、タスクスケジューラによって1日に登録および登録解除されます。</span><span class="sxs-lookup"><span data-stu-id="7e158-117">Templates are registered and unregistered one time per day by the task scheduler.</span></span>

**<span data-ttu-id="7e158-118">設定テンプレートカタログパスを使用して UE-V 設定の場所テンプレートを展開するには</span><span class="sxs-lookup"><span data-stu-id="7e158-118">To use settings template catalog path to deploy UE-V settings location templates</span></span>**

1.  <span data-ttu-id="7e158-119">設定テンプレートカタログとして定義されている [ネットワーク共有] フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="7e158-119">Navigate to the network share folder that is defined as the settings template catalog.</span></span>

2.  <span data-ttu-id="7e158-120">設定テンプレートカタログの設定場所テンプレートを追加、削除、または更新して、UE-V を搭載したコンピューターに必要な UE-V agent テンプレートの構成を反映させます。</span><span class="sxs-lookup"><span data-stu-id="7e158-120">Add, remove, or update settings location templates in the settings template catalog to reflect the desired UE-V agent template configuration for UE-V computers.</span></span>

3.  <span data-ttu-id="7e158-121">コンピューター上のテンプレートは、設定テンプレートカタログの変更に基づいて毎日更新されます。</span><span class="sxs-lookup"><span data-stu-id="7e158-121">Templates on computers are updated daily based on changes to the settings template catalog.</span></span>

4.  <span data-ttu-id="7e158-122">昇格したコマンドプロンプトを開き、 **% program file% ¥ Microsoft User Experience Virtualization \ \ agent \ \ &lt; x86 または &gt; x64**に移動して、ue-v エージェントを実行しているコンピューター上でテンプレートを手動で更新するには、 **ApplySettingsTemplateCatalog.exe**を実行します。</span><span class="sxs-lookup"><span data-stu-id="7e158-122">Open an elevated command prompt and navigate to **%program files%\\Microsoft user Experience Virtualization \\ Agent \\ &lt;x86 or x64 &gt;**, and then run **ApplySettingsTemplateCatalog.exe** to manually update templates on a computer that runs the UE-V agent.</span></span>

## <span data-ttu-id="7e158-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7e158-123">Related topics</span></span>


[<span data-ttu-id="7e158-124">Microsoft User Experience Virtualization (UE-V) 1.0</span><span class="sxs-lookup"><span data-stu-id="7e158-124">Microsoft User Experience Virtualization (UE-V) 1.0</span></span>](index.md)

[<span data-ttu-id="7e158-125">UE-V 1.0 の展開</span><span class="sxs-lookup"><span data-stu-id="7e158-125">Deploying UE-V 1.0</span></span>](deploying-ue-v-10.md)

[<span data-ttu-id="7e158-126">UE-V 1.0 を使用して同期するアプリケーションの計画</span><span class="sxs-lookup"><span data-stu-id="7e158-126">Planning Which Applications to Synchronize with UE-V 1.0</span></span>](planning-which-applications-to-synchronize-with-ue-v-10.md)

 

 





