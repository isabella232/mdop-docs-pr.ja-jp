---
title: 特定のコンピューター上の全ユーザーの拡張ポイントを App-V 5.1 パッケージから App-V 4.6 パッケージに戻す方法
description: 特定のコンピューター上の全ユーザーの拡張ポイントを App-V 5.1 パッケージから App-V 4.6 パッケージに戻す方法
author: dansimp
ms.assetid: 64640b8e-de6b-4006-a33e-353d285af15e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: ce8d5cc0e79be46fd9680a3bea0236bbeb93ea83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813723"
---
# <span data-ttu-id="9aeb3-103">特定のコンピューター上の全ユーザーの拡張ポイントを App-V 5.1 パッケージから App-V 4.6 パッケージに戻す方法</span><span class="sxs-lookup"><span data-stu-id="9aeb3-103">How to Revert Extension Points from an App-V 5.1 Package to an App-V 4.6 Package For All Users on a Specific Computer</span></span>


<span data-ttu-id="9aeb3-104">次の手順を使用して、展開構成ファイルを使用して、アプリ-V 5.1 パッケージの拡張ポイントを App-v 4.6 ファイル形式に戻します。</span><span class="sxs-lookup"><span data-stu-id="9aeb3-104">Use the following procedure to revert extension points from an App-V 5.1 package to the App-V 4.6 file format using the deployment configuration file.</span></span>

**<span data-ttu-id="9aeb3-105">パッケージを元に戻すには</span><span class="sxs-lookup"><span data-stu-id="9aeb3-105">To revert a package</span></span>**

1.  <span data-ttu-id="9aeb3-106">App-v 4.6 パッケージがユーザーに公開されていることを確認します。ただし、FTAs とショートカットは、次の移行方法を使用して、アプリ-v [4.6 パッケージから、特定のコンピューター上のすべてのユーザーに対して、変換さ5.1 れた app-v 5.1 パッケージに拡張ポイントを移行する方法](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-51-package-for-all-users-on-a-specific-computer.md)を示しています。</span><span class="sxs-lookup"><span data-stu-id="9aeb3-106">Ensure that App-V 4.6 package is published to the users but the FTAs and shortcuts have been assumed by App-V 5.1 package using the following migration method, [How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.1 Package for All Users on a Specific Computer](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-51-package-for-all-users-on-a-specific-computer.md).</span></span>

    <span data-ttu-id="9aeb3-107">変換されたパッケージの展開構成ファイルの**Userconfiguration**セクションでポリシーを設定するには、 **userconfiguration**セクションに対して次の更新を行います。 \*\*ManagingAuthority TakeoverExtensionPointsFrom46 = "FALSE" PackageName = &lt; パッケージ ID &gt; \*\*</span><span class="sxs-lookup"><span data-stu-id="9aeb3-107">In the **userConfiguration** section of the deployment configuration file for the converted package, to set the policy, make the following update to the **userConfiguration** section: **ManagingAuthority TakeoverExtensionPointsFrom46="false" PackageName=&lt;Package ID&gt;**</span></span>

2.  <span data-ttu-id="9aeb3-108">昇格されたコマンドプロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9aeb3-108">From an elevated command prompt, type:</span></span>

    <span data-ttu-id="9aeb3-109">PS &gt; **Set-AppvClientPackage $Pkg –動的** &lt; 展開構成ファイルへの dynamicdeploymentconfiguration path&gt;</span><span class="sxs-lookup"><span data-stu-id="9aeb3-109">PS&gt;**Set-AppvClientPackage $pkg –DynamicDeploymentConfiguration** &lt;path to deployment configuration file&gt;</span></span>

    <span data-ttu-id="9aeb3-110">PS &gt; **Publish-AppVClientPackage $Pkg – DynamicUserConfigurationType useDeploymentConfiguration**</span><span class="sxs-lookup"><span data-stu-id="9aeb3-110">PS&gt;**Publish-AppVClientPackage $pkg –DynamicUserConfigurationType useDeploymentConfiguration**</span></span>

3.  <span data-ttu-id="9aeb3-111">公開更新を実行するか、または App-v 4.6 パッケージの次のスケジュールされた発行更新を待ちます。</span><span class="sxs-lookup"><span data-stu-id="9aeb3-111">Perform a publishing refresh, or wait for the next scheduled publishing refresh for the App-V 4.6 package.</span></span>

    <span data-ttu-id="9aeb3-112">FTAs またはショートカットを使用してアプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="9aeb3-112">Open the application using FTAs or shortcuts.</span></span> <span data-ttu-id="9aeb3-113">アプリケーションは、App-v 4.6 を使って開くようになりました。</span><span class="sxs-lookup"><span data-stu-id="9aeb3-113">The Application should now open using App-V 4.6.</span></span>

    **<span data-ttu-id="9aeb3-114">注</span><span class="sxs-lookup"><span data-stu-id="9aeb3-114">Note</span></span>**  
    <span data-ttu-id="9aeb3-115">App-v 5.1 パッケージが不要になった場合は、app-v 5.1 パッケージの発行を取り消すことができます。また、拡張ポイントは自動的に App V 4.6 に戻ります。</span><span class="sxs-lookup"><span data-stu-id="9aeb3-115">If you do not need the App-V 5.1 package anymore, you can unpublish the App-V 5.1 package and the extension points will automatically revert to App-V 4.6.</span></span>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="9aeb3-116">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9aeb3-116">Related topics</span></span>


[<span data-ttu-id="9aeb3-117">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="9aeb3-117">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)









