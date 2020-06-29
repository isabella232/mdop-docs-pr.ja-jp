---
title: 特定のユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.1 パッケージに移行する方法
description: 特定のユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.1 パッケージに移行する方法
author: dansimp
ms.assetid: 19da3776-5ebe-41e1-9890-12b84ef3c1c7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: e2166b0f280153ad62709b21bb3477d0c4277fcd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813867"
---
# <span data-ttu-id="2c2f4-103">特定のユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.1 パッケージに移行する方法</span><span class="sxs-lookup"><span data-stu-id="2c2f4-103">How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.1 for a Specific User</span></span>


<span data-ttu-id="2c2f4-104">ユーザー構成ファイルを使用して、App-v で作成したパッケージを移行するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="2c2f4-104">Use the following procedure to migrate packages created with App-V using the user configuration file.</span></span>

<span data-ttu-id="2c2f4-105">**注** この手順では、最新バージョンの App-v 4.6 が実行されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="2c2f4-105">**Note** This procedure assumes that you are running the latest version of App-V 4.6.</span></span>

**<span data-ttu-id="2c2f4-106">パッケージを変換するには</span><span class="sxs-lookup"><span data-stu-id="2c2f4-106">To convert a package</span></span>**

1. <span data-ttu-id="2c2f4-107">変換するパッケージのユーザー構成ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="2c2f4-107">Locate the user configuration file for the package you want to convert.</span></span> <span data-ttu-id="2c2f4-108">ポリシーを設定するには、 **Userconfiguration**セクションで次の更新を実行します。 \*\*ManagingAuthority TakeoverExtensionPointsFrom46 = "true" PACKAGENAME = &lt; パッケージ ID &gt; \*\*。</span><span class="sxs-lookup"><span data-stu-id="2c2f4-108">To set the policy, perform the following updates in the **userConfiguration** section: **ManagingAuthority TakeoverExtensionPointsFrom46="true" PackageName=&lt;Package ID&gt;**.</span></span>

   <span data-ttu-id="2c2f4-109">ユーザー構成ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2c2f4-109">The following is an example of a user configuration file:</span></span>

   <span data-ttu-id="2c2f4-110">&lt;? xml バージョン = "1.0"?&gt;</span><span class="sxs-lookup"><span data-stu-id="2c2f4-110">&lt;?xml version="1.0" ?&gt;</span></span>

   <span data-ttu-id="2c2f4-111">&lt;UserConfiguration PackageId = &lt; パッケージ ID &gt; DisplayName = &lt; パッケージの名前&gt;</span><span class="sxs-lookup"><span data-stu-id="2c2f4-111">&lt;UserConfiguration PackageId=&lt;Package ID&gt; DisplayName=&lt;Name of the Package&gt;</span></span>

   <span data-ttu-id="2c2f4-112">xmlns = " <https://schemas.microsoft.com/appv/2010/userconfiguration"&gt> ; &lt;ManagingAuthority TakeoverExtensionPointsFrom46 = "true"</span><span class="sxs-lookup"><span data-stu-id="2c2f4-112">xmlns="<https://schemas.microsoft.com/appv/2010/userconfiguration"&gt>; &lt;ManagingAuthority TakeoverExtensionPointsFrom46="true"</span></span>

   <span data-ttu-id="2c2f4-113">PackageName = &lt; パッケージ ID&gt;</span><span class="sxs-lookup"><span data-stu-id="2c2f4-113">PackageName=&lt;Package ID&gt;</span></span>

   <span data-ttu-id="2c2f4-114">&lt;/UserConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="2c2f4-114">&lt;/UserConfiguration&gt;</span></span>

2. <span data-ttu-id="2c2f4-115">App-v 5.1 パッケージを追加するには、管理者特権の PowerShell コマンドプロンプトウィンドウで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2c2f4-115">To add the App-V 5.1 package, type the following in an elevated PowerShell command prompt window:</span></span>

   <span data-ttu-id="2c2f4-116">PS &gt; **$Pkg = AppvClientPackage –** &lt; パッケージの場所へのパスパス&gt;</span><span class="sxs-lookup"><span data-stu-id="2c2f4-116">PS&gt;**$pkg= Add-AppvClientPackage –Path** &lt;Path to package location&gt;</span></span>

   <span data-ttu-id="2c2f4-117">PS &gt; **Publish-AppVClientPackage $Pkg-dynamicuserconfiguration** &lt; Path をユーザー構成ファイルに対して設定します。&gt;</span><span class="sxs-lookup"><span data-stu-id="2c2f4-117">PS&gt;**Publish-AppVClientPackage $pkg -DynamicUserConfiguration** &lt;Path to the user configuration file&gt;</span></span>

3. <span data-ttu-id="2c2f4-118">FTAs またはショートカットを使用してアプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="2c2f4-118">Open the application using FTAs or shortcuts now.</span></span> <span data-ttu-id="2c2f4-119">アプリケーションは、App-v 5.1 を使って開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c2f4-119">The application should open using App-V 5.1.</span></span>

   <span data-ttu-id="2c2f4-120">App-v 4.6 パッケージと変換された app-v 5.1 パッケージはユーザーに公開されますが、アプリケーションの FTAs とショートカットは、App-v 5.1 パッケージで想定されています。</span><span class="sxs-lookup"><span data-stu-id="2c2f4-120">The App-V 4.6 package and the converted App-V 5.1 package are published to the user, but the FTAs and shortcuts for the applications have been assumed by the App-V 5.1 package.</span></span>

   <span data-ttu-id="2c2f4-121">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="2c2f4-121">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="2c2f4-122">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="2c2f4-122">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="2c2f4-123">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="2c2f4-123">Got an App-V issue?</span></span>** <span data-ttu-id="2c2f4-124">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="2c2f4-124">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="2c2f4-125">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2c2f4-125">Related topics</span></span>


[<span data-ttu-id="2c2f4-126">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="2c2f4-126">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

[<span data-ttu-id="2c2f4-127">特定のユーザーの拡張ポイントを App-V 5.1 パッケージから App-V 4.6 パッケージに戻す方法</span><span class="sxs-lookup"><span data-stu-id="2c2f4-127">How to Revert Extension Points From an App-V 5.1 Package to an App-V 4.6 Package for a Specific User</span></span>](how-to-revert-extension-points-from-an-app-v-51-package-to-an-app-v-46-package-for-a-specific-user.md)

 

 





