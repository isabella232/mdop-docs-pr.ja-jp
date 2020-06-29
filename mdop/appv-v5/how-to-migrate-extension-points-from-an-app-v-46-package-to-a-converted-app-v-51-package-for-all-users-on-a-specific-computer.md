---
title: 特定のコンピューター上の全ユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.1 パッケージに移行する方法
description: 特定のコンピューター上の全ユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.1 パッケージに移行する方法
author: dansimp
ms.assetid: 4ef823a5-3106-44c5-aecc-29edf69c2fbb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 7bac244804b46309a0e0a75cb3742dfe22e92e8f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813882"
---
# <span data-ttu-id="438b8-103">特定のコンピューター上の全ユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.1 パッケージに移行する方法</span><span class="sxs-lookup"><span data-stu-id="438b8-103">How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.1 Package for All Users on a Specific Computer</span></span>


<span data-ttu-id="438b8-104">次の手順を使用して、展開構成ファイルを使用して、アプリ-V 4.6 パッケージから app-v 5.1 パッケージに拡張ポイントを移行します。</span><span class="sxs-lookup"><span data-stu-id="438b8-104">Use the following procedure to migrate extension points from an App-V4.6 package to a App-V 5.1 package using the deployment configuration file.</span></span>

<span data-ttu-id="438b8-105">**注** この手順では、最新バージョンの App-v 4.6 が実行されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="438b8-105">**Note** This procedure assumes that you are running the latest version of App-V 4.6.</span></span>  
<span data-ttu-id="438b8-106">次の手順では、App-v 5.1 management server は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="438b8-106">The following procedure does not require an App-V 5.1 management server.</span></span>

 

**<span data-ttu-id="438b8-107">パッケージから展開構成ファイルを使用して、パッケージから変換された App-v 5.1 パッケージに拡張ポイントを移行するには</span><span class="sxs-lookup"><span data-stu-id="438b8-107">To migrate extension points from a package from an App-V4.6 package to a converted App-V 5.1 package using the deployment configuration file</span></span>**

1. <span data-ttu-id="438b8-108">移行するパッケージの展開構成ファイルが含まれているディレクトリを見つけます。</span><span class="sxs-lookup"><span data-stu-id="438b8-108">Locate the directory that contains the deployment configuration file for the package you want to migrate.</span></span> <span data-ttu-id="438b8-109">ポリシーを設定するには、 **Userconfiguration**セクションに対して次の更新を行います。</span><span class="sxs-lookup"><span data-stu-id="438b8-109">To set the policy, make the following update to the **userConfiguration** section:</span></span>

   **<span data-ttu-id="438b8-110">ManagingAuthority TakeoverExtensionPointsFrom46 = "true" PackageName = &lt; パッケージ ID&gt;</span><span class="sxs-lookup"><span data-stu-id="438b8-110">ManagingAuthority TakeoverExtensionPointsFrom46="true" PackageName=&lt;Package ID&gt;</span></span>**

   <span data-ttu-id="438b8-111">展開構成ファイルのコンテンツの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="438b8-111">The following is an example of content from a deployment configuration file:</span></span>

   <span data-ttu-id="438b8-112">&lt;? xml バージョン = "1.0"?&gt;</span><span class="sxs-lookup"><span data-stu-id="438b8-112">&lt;?xml version="1.0" ?&gt;</span></span>

   <span data-ttu-id="438b8-113">&lt;DeploymentConfiguration</span><span class="sxs-lookup"><span data-stu-id="438b8-113">&lt;DeploymentConfiguration</span></span>

   <span data-ttu-id="438b8-114">xmlns = " <https://schemas.microsoft.com/appv/2010/deploymentconfiguration> " PackageId = &lt; パッケージ ID &gt; DisplayName = &lt; 表示名&gt;</span><span class="sxs-lookup"><span data-stu-id="438b8-114">xmlns="<https://schemas.microsoft.com/appv/2010/deploymentconfiguration>" PackageId=&lt;Package ID&gt; DisplayName=&lt;Display Name&gt;</span></span>

   <span data-ttu-id="438b8-115">&lt;コンピューターの \/&gt;</span><span class="sxs-lookup"><span data-stu-id="438b8-115">&lt;MachineConfiguration/&gt;</span></span>

   <span data-ttu-id="438b8-116">&lt;UserConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="438b8-116">&lt;UserConfiguration&gt;</span></span>

   <span data-ttu-id="438b8-117">&lt;ManagingAuthority TakeoverExtensionPointsFrom46 = "true"</span><span class="sxs-lookup"><span data-stu-id="438b8-117">&lt;ManagingAuthority TakeoverExtensionPointsFrom46="true"</span></span>

   <span data-ttu-id="438b8-118">PackageName = &lt; パッケージ ID&gt;</span><span class="sxs-lookup"><span data-stu-id="438b8-118">PackageName=&lt;Package ID&gt;</span></span>

   <span data-ttu-id="438b8-119">&lt;/UserConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="438b8-119">&lt;/UserConfiguration&gt;</span></span>

   <span data-ttu-id="438b8-120">&lt;/Deploymentconfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="438b8-120">&lt;/DeploymentConfiguration&gt;</span></span>

2. <span data-ttu-id="438b8-121">App-v 5.1 パッケージを追加するには、管理者特権の PowerShell コマンドプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="438b8-121">To add the App-V 5.1 package, in an elevated PowerShell command prompt type:</span></span>

   <span data-ttu-id="438b8-122">PS &gt; **$pkg = AppvClientPackage** **–** &lt; パッケージロケーションの path path へのパスパスを &gt;  - **DynamicDeploymentConfiguration** &lt; 展開構成ファイルへのパスを指定します。&gt;</span><span class="sxs-lookup"><span data-stu-id="438b8-122">PS&gt;**$pkg= Add-AppvClientPackage** **–Path** &lt;Path to package location&gt; -**DynamicDeploymentConfiguration** &lt;Path to the deployment configuration file&gt;</span></span>

   <span data-ttu-id="438b8-123">PS &gt; **Publish-AppVClientPackage $pkg**</span><span class="sxs-lookup"><span data-stu-id="438b8-123">PS&gt;**Publish-AppVClientPackage $pkg**</span></span>

3. <span data-ttu-id="438b8-124">移行をテストするには、関連する FTAs またはショートカットを使用して仮想アプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="438b8-124">To test the migration, open the virtual application using associated FTAs or shortcuts.</span></span> <span data-ttu-id="438b8-125">アプリケーションが、App-v 5.1 で開かれます。</span><span class="sxs-lookup"><span data-stu-id="438b8-125">The application opens with App-V 5.1.</span></span> <span data-ttu-id="438b8-126">どちらの場合も、App-v 4.6 パッケージと変換された App-v 5.1 パッケージはユーザーに公開されますが、アプリケーションの FTAs とショートカットは、App-v 5.1 パッケージで想定されています。</span><span class="sxs-lookup"><span data-stu-id="438b8-126">Both, the App-V 4.6 package and the converted App-V 5.1 package are published to the user, but the FTAs and shortcuts for the applications have been assumed by the App-V 5.1 package.</span></span>

   <span data-ttu-id="438b8-127">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="438b8-127">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="438b8-128">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="438b8-128">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="438b8-129">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="438b8-129">Got an App-V issue?</span></span>** <span data-ttu-id="438b8-130">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="438b8-130">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="438b8-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="438b8-131">Related topics</span></span>


[<span data-ttu-id="438b8-132">特定のコンピューター上の全ユーザーの拡張ポイントを App-V 5.1 パッケージから App-V 4.6 パッケージに戻す方法</span><span class="sxs-lookup"><span data-stu-id="438b8-132">How to Revert Extension Points from an App-V 5.1 Package to an App-V 4.6 Package For All Users on a Specific Computer</span></span>](how-to-revert-extension-points-from-an-app-v-51-package-to-an-app-v-46-package-for-all-users-on-a-specific-computer.md)

[<span data-ttu-id="438b8-133">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="438b8-133">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





