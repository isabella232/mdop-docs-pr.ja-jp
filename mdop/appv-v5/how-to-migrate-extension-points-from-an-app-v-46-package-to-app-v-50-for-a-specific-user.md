---
title: 特定のユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.0 パッケージに移行する方法
description: 特定のユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.0 パッケージに移行する方法
ms.assetid: dad25992-3c75-4b7d-b4c6-c2edf43baaea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: a17d9dad11092a4c8356983b70bea3c18da1be04
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813875"
---
# <span data-ttu-id="9489e-103">特定のユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.0 パッケージに移行する方法</span><span class="sxs-lookup"><span data-stu-id="9489e-103">How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.0 for a Specific User</span></span>

<span data-ttu-id="9489e-104">*注:*\* App-V 4.6 はメインストリームサポートを終了しました。</span><span class="sxs-lookup"><span data-stu-id="9489e-104">*Note:*\* App-V 4.6 has exited Mainstream support.</span></span>

<span data-ttu-id="9489e-105">ユーザー構成ファイルを使用して、App-v で作成したパッケージを移行するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="9489e-105">Use the following procedure to migrate packages created with App-V using the user configuration file.</span></span>

**<span data-ttu-id="9489e-106">パッケージを変換するには</span><span class="sxs-lookup"><span data-stu-id="9489e-106">To convert a package</span></span>**

1. <span data-ttu-id="9489e-107">変換するパッケージのユーザー構成ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="9489e-107">Locate the user configuration file for the package you want to convert.</span></span> <span data-ttu-id="9489e-108">ポリシーを設定するには、 **Userconfiguration**セクションで次の更新を実行します。 \*\*ManagingAuthority TakeoverExtensionPointsFrom46 = "true" PACKAGENAME = &lt; パッケージ ID &gt; \*\*。</span><span class="sxs-lookup"><span data-stu-id="9489e-108">To set the policy, perform the following updates in the **userConfiguration** section: **ManagingAuthority TakeoverExtensionPointsFrom46="true" PackageName=&lt;Package ID&gt;**.</span></span>

   <span data-ttu-id="9489e-109">ユーザー構成ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9489e-109">The following is an example of a user configuration file:</span></span>

   <span data-ttu-id="9489e-110">&lt;? xml バージョン = "1.0"?&gt;</span><span class="sxs-lookup"><span data-stu-id="9489e-110">&lt;?xml version="1.0" ?&gt;</span></span>

   <span data-ttu-id="9489e-111">&lt;UserConfiguration PackageId = &lt; パッケージ ID &gt; DisplayName = &lt; パッケージの名前&gt;</span><span class="sxs-lookup"><span data-stu-id="9489e-111">&lt;UserConfiguration PackageId=&lt;Package ID&gt; DisplayName=&lt;Name of the Package&gt;</span></span>

   <span data-ttu-id="9489e-112">xmlns = " <https://schemas.microsoft.com/appv/2010/userconfiguration"&gt> ; &lt;ManagingAuthority TakeoverExtensionPointsFrom46 = "true"</span><span class="sxs-lookup"><span data-stu-id="9489e-112">xmlns="<https://schemas.microsoft.com/appv/2010/userconfiguration"&gt>; &lt;ManagingAuthority TakeoverExtensionPointsFrom46="true"</span></span>

   <span data-ttu-id="9489e-113">PackageName = &lt; パッケージ ID&gt;</span><span class="sxs-lookup"><span data-stu-id="9489e-113">PackageName=&lt;Package ID&gt;</span></span>

   <span data-ttu-id="9489e-114">&lt;/UserConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="9489e-114">&lt;/UserConfiguration&gt;</span></span>

2. <span data-ttu-id="9489e-115">App-v 5.0 パッケージを追加するには、管理者特権の PowerShell コマンドプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9489e-115">To add the App-V 5.0 package type the following in an elevated PowerShell command prompt:</span></span>

   <span data-ttu-id="9489e-116">PS &gt; **$Pkg = AppvClientPackage –** &lt; パッケージの場所へのパスパス&gt;</span><span class="sxs-lookup"><span data-stu-id="9489e-116">PS&gt;**$pkg= Add-AppvClientPackage –Path** &lt;Path to package location&gt;</span></span>

   <span data-ttu-id="9489e-117">PS &gt; **Publish-AppVClientPackage $Pkg-dynamicuserconfiguration** &lt; Path をユーザー構成ファイルに対して設定します。&gt;</span><span class="sxs-lookup"><span data-stu-id="9489e-117">PS&gt;**Publish-AppVClientPackage $pkg -DynamicUserConfiguration** &lt;Path to the user configuration file&gt;</span></span>

3. <span data-ttu-id="9489e-118">FTAs またはショートカットを使用してアプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="9489e-118">Open the application using FTAs or shortcuts now.</span></span> <span data-ttu-id="9489e-119">アプリケーションは、App-v 5.0 を使って開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="9489e-119">The application should open using App-V 5.0.</span></span>

   <span data-ttu-id="9489e-120">App-v SP2 パッケージと変換された app-v 5.0 パッケージはユーザーに公開されますが、アプリケーションの FTAs とショートカットは、App-v 5.0 パッケージによって想定されています。</span><span class="sxs-lookup"><span data-stu-id="9489e-120">The App-V SP2 package and the converted App-V 5.0 package are published to the user, but the FTAs and shortcuts for the applications have been assumed by the App-V 5.0 package.</span></span>

   <span data-ttu-id="9489e-121">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="9489e-121">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="9489e-122">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="9489e-122">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="9489e-123">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="9489e-123">Got an App-V issue?</span></span>** <span data-ttu-id="9489e-124">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="9489e-124">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="9489e-125">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9489e-125">Related topics</span></span>


[<span data-ttu-id="9489e-126">APP-V 5.0 の操作</span><span class="sxs-lookup"><span data-stu-id="9489e-126">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





