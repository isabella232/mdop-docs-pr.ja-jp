---
title: 特定のユーザーの拡張ポイントを App-V 5.1 パッケージから App-V 4.6 パッケージに戻す方法
description: 特定のユーザーの拡張ポイントを App-V 5.1 パッケージから App-V 4.6 パッケージに戻す方法
author: dansimp
ms.assetid: bd53c5d6-7fd2-4816-b03b-d59da0a35819
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: a69d6fb5b180161f39aa89e03b52227f32ce4879
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813731"
---
# <span data-ttu-id="4321c-103">特定のユーザーの拡張ポイントを App-V 5.1 パッケージから App-V 4.6 パッケージに戻す方法</span><span class="sxs-lookup"><span data-stu-id="4321c-103">How to Revert Extension Points From an App-V 5.1 Package to an App-V 4.6 Package for a Specific User</span></span>


<span data-ttu-id="4321c-104">次の手順を使用して、ユーザー構成ファイルを使用して、App-v 5.1 パッケージを App-v ファイル形式に戻します。</span><span class="sxs-lookup"><span data-stu-id="4321c-104">Use the following procedure to revert an App-V 5.1 package to the App-V file format using the user configuration file.</span></span>

**<span data-ttu-id="4321c-105">パッケージを元に戻すには</span><span class="sxs-lookup"><span data-stu-id="4321c-105">To revert a package</span></span>**

1.  <span data-ttu-id="4321c-106">App-v 4.6 パッケージがユーザーに公開されていることを確認します。ただし、FTAs とのショート5.1 カットは、次の移行方法を使用して、app-v [4.6 パッケージから特定のユーザーに対して拡張ポイントをアプリ-v 5.1 に移行する方法について説明](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-51-for-a-specific-user.md)しています。</span><span class="sxs-lookup"><span data-stu-id="4321c-106">Ensure that App-V 4.6 package is published to the users but the FTAs and shortcuts have been assumed by App-V 5.1 package using the following migration method, [How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.1 for a Specific User](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-51-for-a-specific-user.md).</span></span>

    <span data-ttu-id="4321c-107">変換されたパッケージの展開構成ファイルの**Userconfiguration**セクションでポリシーを設定するには、 **userconfiguration**セクションに対して次の更新を行います。 \*\*ManagingAuthority TakeoverExtensionPointsFrom46 = "FALSE" PackageName = &lt; パッケージ ID &gt; \*\*</span><span class="sxs-lookup"><span data-stu-id="4321c-107">In the **userConfiguration** section of the deployment configuration file for the converted package, to set the policy, make the following update to the **userConfiguration** section: **ManagingAuthority TakeoverExtensionPointsFrom46="false" PackageName=&lt;Package ID&gt;**</span></span>

2.  <span data-ttu-id="4321c-108">昇格されたコマンドプロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4321c-108">From an elevated command prompt, type:</span></span>

    <span data-ttu-id="4321c-109">PS &gt; **Publish-AppVClientPackage $pkg –** &lt; ユーザー構成ファイルへの dynamicuserconfigurationpath パス&gt;</span><span class="sxs-lookup"><span data-stu-id="4321c-109">PS&gt;**Publish-AppVClientPackage $pkg –DynamicUserConfigurationPath** &lt;path to user configuration file&gt;</span></span>

3.  <span data-ttu-id="4321c-110">公開更新を実行するか、アプリ-V 4.6 の次のスケジュールされた発行更新を待ちます。</span><span class="sxs-lookup"><span data-stu-id="4321c-110">Perform a publishing refresh, or wait for the next scheduled publishing refresh for the App-V 4.6.</span></span> <span data-ttu-id="4321c-111">FTAs またはショートカットを使用してアプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="4321c-111">Open the application using FTAs or shortcuts.</span></span> <span data-ttu-id="4321c-112">アプリケーションは、App-v 4.6 を使って開くようになりました。</span><span class="sxs-lookup"><span data-stu-id="4321c-112">The Application should now open using App-V 4.6.</span></span>

    **<span data-ttu-id="4321c-113">注</span><span class="sxs-lookup"><span data-stu-id="4321c-113">Note</span></span>**  
    <span data-ttu-id="4321c-114">App-v 5.1 パッケージが不要になった場合は、app-v 5.1 パッケージの発行を取り消すことができます。また、拡張ポイントは自動的に App V 4.6 に戻ります。</span><span class="sxs-lookup"><span data-stu-id="4321c-114">If you do not need the App-V 5.1 package anymore, you can unpublish the App-V 5.1 package and the extension points will automatically revert to App-V 4.6.</span></span>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="4321c-115">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4321c-115">Related topics</span></span>


[<span data-ttu-id="4321c-116">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="4321c-116">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)









