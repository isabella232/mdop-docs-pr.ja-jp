---
title: 特定のコンピューター上の全ユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.0 パッケージに移行する方法
description: 特定のコンピューター上の全ユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.0 パッケージに移行する方法
ms.assetid: 3ae9996f-71d9-4ca1-9aab-25b599158e55
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 3c53104907448edeb894cf4eb9dbb0a24d3229e4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813883"
---
# <span data-ttu-id="bdfb1-103">特定のコンピューター上の全ユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.0 パッケージに移行する方法</span><span class="sxs-lookup"><span data-stu-id="bdfb1-103">How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.0 Package for All Users on a Specific Computer</span></span>

<span data-ttu-id="bdfb1-104">**注:** App-v 4.6 は、メインストリームサポートを終了しました。</span><span class="sxs-lookup"><span data-stu-id="bdfb1-104">**Note:** App-V 4.6 has exited Mainstream support.</span></span>

<span data-ttu-id="bdfb1-105">次の手順を使用して、展開構成ファイルを使用して、アプリ-V 4.6 パッケージから app-v 5.0 パッケージに拡張ポイントを移行します。</span><span class="sxs-lookup"><span data-stu-id="bdfb1-105">Use the following procedure to migrate extension points from an App-V4.6package to a App-V 5.0 package using the deployment configuration file.</span></span>

<span data-ttu-id="bdfb1-106">**注** 次の手順では、App-v 5.0 management server は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bdfb1-106">**Note** The following procedure does not require an App-V 5.0 management server.</span></span>

 

**<span data-ttu-id="bdfb1-107">パッケージから展開構成ファイルを使用して、パッケージから変換された App-v 5.0 パッケージに拡張ポイントを移行するには</span><span class="sxs-lookup"><span data-stu-id="bdfb1-107">To migrate extension points from a package from an App-V4.6 package to a converted App-V 5.0 package using the deployment configuration file</span></span>**

1. <span data-ttu-id="bdfb1-108">移行するパッケージの展開構成ファイルが含まれているディレクトリを見つけます。</span><span class="sxs-lookup"><span data-stu-id="bdfb1-108">Locate the directory that contains the deployment configuration file for the package you want to migrate.</span></span> <span data-ttu-id="bdfb1-109">ポリシーを設定するには、 **Userconfiguration**セクションに対して次の更新を行います。</span><span class="sxs-lookup"><span data-stu-id="bdfb1-109">To set the policy, make the following update to the **userConfiguration** section:</span></span>

   **<span data-ttu-id="bdfb1-110">ManagingAuthority TakeoverExtensionPointsFrom46 = "true" PackageName = &lt; パッケージ ID&gt;</span><span class="sxs-lookup"><span data-stu-id="bdfb1-110">ManagingAuthority TakeoverExtensionPointsFrom46="true" PackageName=&lt;Package ID&gt;</span></span>**

   <span data-ttu-id="bdfb1-111">展開構成ファイルのコンテンツの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bdfb1-111">The following is an example of content from a deployment configuration file:</span></span>

   <span data-ttu-id="bdfb1-112">&lt;? xml バージョン = "1.0"?&gt;</span><span class="sxs-lookup"><span data-stu-id="bdfb1-112">&lt;?xml version="1.0" ?&gt;</span></span>

   <span data-ttu-id="bdfb1-113">&lt;DeploymentConfiguration</span><span class="sxs-lookup"><span data-stu-id="bdfb1-113">&lt;DeploymentConfiguration</span></span>

   <span data-ttu-id="bdfb1-114">xmlns = " <https://schemas.microsoft.com/appv/2010/deploymentconfiguration> " PackageId = &lt; パッケージ ID &gt; DisplayName = &lt; 表示名&gt;</span><span class="sxs-lookup"><span data-stu-id="bdfb1-114">xmlns="<https://schemas.microsoft.com/appv/2010/deploymentconfiguration>" PackageId=&lt;Package ID&gt; DisplayName=&lt;Display Name&gt;</span></span>

   <span data-ttu-id="bdfb1-115">&lt;コンピューターの \/&gt;</span><span class="sxs-lookup"><span data-stu-id="bdfb1-115">&lt;MachineConfiguration/&gt;</span></span>

   <span data-ttu-id="bdfb1-116">&lt;UserConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="bdfb1-116">&lt;UserConfiguration&gt;</span></span>

   <span data-ttu-id="bdfb1-117">&lt;ManagingAuthority TakeoverExtensionPointsFrom46 = "true"</span><span class="sxs-lookup"><span data-stu-id="bdfb1-117">&lt;ManagingAuthority TakeoverExtensionPointsFrom46="true"</span></span>

   <span data-ttu-id="bdfb1-118">PackageName = &lt; パッケージ ID&gt;</span><span class="sxs-lookup"><span data-stu-id="bdfb1-118">PackageName=&lt;Package ID&gt;</span></span>

   <span data-ttu-id="bdfb1-119">&lt;/UserConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="bdfb1-119">&lt;/UserConfiguration&gt;</span></span>

   <span data-ttu-id="bdfb1-120">&lt;/Deploymentconfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="bdfb1-120">&lt;/DeploymentConfiguration&gt;</span></span>

2. <span data-ttu-id="bdfb1-121">App-v 5.0 パッケージを追加するには、管理者特権の PowerShell コマンドプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bdfb1-121">To add the App-V 5.0 package, in an elevated PowerShell command prompt type:</span></span>

   <span data-ttu-id="bdfb1-122">PS &gt; **$pkg = AppvClientPackage** **–** &lt; パッケージロケーションの path path へのパスパスを &gt;  - **DynamicDeploymentConfiguration** &lt; 展開構成ファイルへのパスを指定します。&gt;</span><span class="sxs-lookup"><span data-stu-id="bdfb1-122">PS&gt;**$pkg= Add-AppvClientPackage** **–Path** &lt;Path to package location&gt; -**DynamicDeploymentConfiguration** &lt;Path to the deployment configuration file&gt;</span></span>

   <span data-ttu-id="bdfb1-123">PS &gt; **Publish-AppVClientPackage $pkg**</span><span class="sxs-lookup"><span data-stu-id="bdfb1-123">PS&gt;**Publish-AppVClientPackage $pkg**</span></span>

3. <span data-ttu-id="bdfb1-124">移行をテストするには、関連する FTAs またはショートカットを使用して仮想アプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="bdfb1-124">To test the migration, open the virtual application using associated FTAs or shortcuts.</span></span> <span data-ttu-id="bdfb1-125">アプリケーションが、App-v 5.0 で開かれます。</span><span class="sxs-lookup"><span data-stu-id="bdfb1-125">The application opens with App-V 5.0.</span></span> <span data-ttu-id="bdfb1-126">どちらの場合も、App-v 4.6 パッケージと変換された App-v 5.0 パッケージはユーザーに公開されますが、アプリケーションの FTAs とショートカットは、App-v 5.0 パッケージで想定されています。</span><span class="sxs-lookup"><span data-stu-id="bdfb1-126">Both, the App-V 4.6 package and the converted App-V 5.0 package are published to the user, but the FTAs and shortcuts for the applications have been assumed by the App-V 5.0 package.</span></span>

   <span data-ttu-id="bdfb1-127">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="bdfb1-127">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="bdfb1-128">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="bdfb1-128">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="bdfb1-129">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="bdfb1-129">Got an App-V issue?</span></span>** <span data-ttu-id="bdfb1-130">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="bdfb1-130">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="bdfb1-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bdfb1-131">Related topics</span></span>


[<span data-ttu-id="bdfb1-132">特定のコンピューター上の全ユーザーの拡張ポイントを App-V 5.0 パッケージから App-V 4.6 パッケージに戻す方法</span><span class="sxs-lookup"><span data-stu-id="bdfb1-132">How to Revert Extension Points from an App-V 5.0 Package to an App-V 4.6 Package For All Users on a Specific Computer</span></span>](how-to-revert-extension-points-from-an-app-v-50-package-to-an-app-v-46-package-for-all-users-on-a-specific-computer.md)

[<span data-ttu-id="bdfb1-133">APP-V 5.0 の操作</span><span class="sxs-lookup"><span data-stu-id="bdfb1-133">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





