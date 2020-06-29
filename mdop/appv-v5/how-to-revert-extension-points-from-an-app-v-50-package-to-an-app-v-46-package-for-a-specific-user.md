---
ms.reviewer: ''
title: 特定のユーザーの拡張ポイントを App-V 5.0 パッケージから App-V 4.6 パッケージに戻す方法
description: 特定のユーザーの拡張ポイントを App-V 5.0 パッケージから App-V 4.6 パッケージに戻す方法
ms.assetid: f1d2ab1f-0831-4976-b49f-169511d3382a
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 2a0660024734806c508043cc2db030c96cfd16a2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813739"
---
# <span data-ttu-id="70097-103">特定のユーザーの拡張ポイントを App-V 5.0 パッケージから App-V 4.6 パッケージに戻す方法</span><span class="sxs-lookup"><span data-stu-id="70097-103">How to Revert Extension Points From an App-V 5.0 Package to an App-V 4.6 Package for a Specific User</span></span>

<span data-ttu-id="70097-104">*注:*\* App-V 4.6 はメインストリームサポートを終了しました。</span><span class="sxs-lookup"><span data-stu-id="70097-104">*Note:*\* App-V 4.6 has exited Mainstream support.</span></span>

<span data-ttu-id="70097-105">次の手順を使用して、ユーザー構成ファイルを使用して、App-v 5.0 パッケージを App-v ファイル形式に戻します。</span><span class="sxs-lookup"><span data-stu-id="70097-105">Use the following procedure to revert an App-V 5.0 package to the App-V file format using the user configuration file.</span></span>

**<span data-ttu-id="70097-106">パッケージを元に戻すには</span><span class="sxs-lookup"><span data-stu-id="70097-106">To revert a package</span></span>**

1.  <span data-ttu-id="70097-107">App-v 4.6 パッケージがユーザーに公開されていることを確認します。ただし、FTAs とのショート5.0 カットは、次の移行方法を使用して、app-v [4.6 パッケージから特定のユーザーに対して拡張ポイントをアプリ-v 5.0 に移行する方法について説明](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md)しています。</span><span class="sxs-lookup"><span data-stu-id="70097-107">Ensure that App-V 4.6 package is published to the users but the FTAs and shortcuts have been assumed by App-V 5.0 package using the following migration method, [How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.0 for a Specific User](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md).</span></span>

    <span data-ttu-id="70097-108">変換されたパッケージの展開構成ファイルの**Userconfiguration**セクションでポリシーを設定するには、 **userconfiguration**セクションに対して次の更新を行います。 \*\*ManagingAuthority TakeoverExtensionPointsFrom46 = "FALSE" PackageName = &lt; パッケージ ID &gt; \*\*</span><span class="sxs-lookup"><span data-stu-id="70097-108">In the **userConfiguration** section of the deployment configuration file for the converted package, to set the policy, make the following update to the **userConfiguration** section: **ManagingAuthority TakeoverExtensionPointsFrom46="false" PackageName=&lt;Package ID&gt;**</span></span>

2.  <span data-ttu-id="70097-109">昇格されたコマンドプロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="70097-109">From an elevated command prompt, type:</span></span>

    <span data-ttu-id="70097-110">PS &gt; **Publish-AppVClientPackage $pkg –** &lt; ユーザー構成ファイルへの dynamicuserconfigurationpath パス&gt;</span><span class="sxs-lookup"><span data-stu-id="70097-110">PS&gt;**Publish-AppVClientPackage $pkg –DynamicUserConfigurationPath** &lt;path to user configuration file&gt;</span></span>

3.  <span data-ttu-id="70097-111">公開更新を実行するか、アプリ-V 4.6 の次のスケジュールされた発行更新を待ちます。</span><span class="sxs-lookup"><span data-stu-id="70097-111">Perform a publishing refresh, or wait for the next scheduled publishing refresh for the App-V 4.6.</span></span> <span data-ttu-id="70097-112">FTAs またはショートカットを使用してアプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="70097-112">Open the application using FTAs or shortcuts.</span></span> <span data-ttu-id="70097-113">アプリケーションは、App-v 4.6 SP2 を使って開くようになりました。</span><span class="sxs-lookup"><span data-stu-id="70097-113">The Application should now open using App-V 4.6 SP2.</span></span>

    **<span data-ttu-id="70097-114">注</span><span class="sxs-lookup"><span data-stu-id="70097-114">Note</span></span>**  
    <span data-ttu-id="70097-115">App-v 5.0 パッケージが不要になった場合は、app-v 5.0 パッケージの発行を取り消すことができます。また、拡張ポイントは自動的に App V 4.6 に戻ります。</span><span class="sxs-lookup"><span data-stu-id="70097-115">If you do not need the App-V 5.0 package anymore, you can unpublish the App-V 5.0 package and the extension points will automatically revert to App-V 4.6.</span></span>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="70097-116">関連トピック</span><span class="sxs-lookup"><span data-stu-id="70097-116">Related topics</span></span>


[<span data-ttu-id="70097-117">APP-V 5.0 の操作</span><span class="sxs-lookup"><span data-stu-id="70097-117">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)












