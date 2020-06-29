---
title: 特定のコンピューター上の全ユーザーの拡張ポイントを App-V 5.0 パッケージから App-V 4.6 パッケージに戻す方法
description: 特定のコンピューター上の全ユーザーの拡張ポイントを App-V 5.0 パッケージから App-V 4.6 パッケージに戻す方法
ms.assetid: 2a43ca1b-6847-4dd1-ade2-336ac4ac6af0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 62542e5cd0b9dcb55f6e8f3db4d4f43c011a2839
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813730"
---
# <span data-ttu-id="4f8c2-103">特定のコンピューター上の全ユーザーの拡張ポイントを App-V 5.0 パッケージから App-V 4.6 パッケージに戻す方法</span><span class="sxs-lookup"><span data-stu-id="4f8c2-103">How to Revert Extension Points from an App-V 5.0 Package to an App-V 4.6 Package For All Users on a Specific Computer</span></span>

<span data-ttu-id="4f8c2-104">*注:*\* App-V 4.6 はメインストリームサポートを終了しました。</span><span class="sxs-lookup"><span data-stu-id="4f8c2-104">*Note:*\* App-V 4.6 has exited Mainstream support.</span></span> <span data-ttu-id="4f8c2-105">次の例は、App-v 4.6 SP3 クライアントが既にインストールされていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="4f8c2-105">The following assumes that the App-V 4.6 SP3 client is already installed.</span></span>

<span data-ttu-id="4f8c2-106">次の手順を使用して、展開構成ファイルを使用して、アプリ-V 5.0 パッケージの拡張ポイントを App-v 4.6 ファイル形式に戻します。</span><span class="sxs-lookup"><span data-stu-id="4f8c2-106">Use the following procedure to revert extension points from an App-V 5.0 package to the App-V 4.6 file format using the deployment configuration file.</span></span>

**<span data-ttu-id="4f8c2-107">パッケージを元に戻すには</span><span class="sxs-lookup"><span data-stu-id="4f8c2-107">To revert a package</span></span>**

1.  <span data-ttu-id="4f8c2-108">App-v 4.6 パッケージがユーザーに公開されていることを確認します。ただし、FTAs とショートカットは、次の移行方法を使用して、アプリ-v [4.6 パッケージから、特定のコンピューター上のすべてのユーザーに対して、変換さ5.0 れた app-v 5.0 パッケージに拡張ポイントを移行する方法](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)を示しています。</span><span class="sxs-lookup"><span data-stu-id="4f8c2-108">Ensure that App-V 4.6 package is published to the users but the FTAs and shortcuts have been assumed by App-V 5.0 package using the following migration method, [How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.0 Package for All Users on a Specific Computer](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md).</span></span>

    <span data-ttu-id="4f8c2-109">変換されたパッケージの展開構成ファイルの**Userconfiguration**セクションでポリシーを設定するには、 **userconfiguration**セクションに対して次の更新を行います。 \*\*ManagingAuthority TakeoverExtensionPointsFrom46 = "FALSE" PackageName = &lt; パッケージ ID &gt; \*\*</span><span class="sxs-lookup"><span data-stu-id="4f8c2-109">In the **userConfiguration** section of the deployment configuration file for the converted package, to set the policy, make the following update to the **userConfiguration** section: **ManagingAuthority TakeoverExtensionPointsFrom46="false" PackageName=&lt;Package ID&gt;**</span></span>

2.  <span data-ttu-id="4f8c2-110">昇格されたコマンドプロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4f8c2-110">From an elevated command prompt, type:</span></span>

    <span data-ttu-id="4f8c2-111">PS &gt; **Set-AppvClientPackage $Pkg –動的** &lt; 展開構成ファイルへの dynamicdeploymentconfiguration path&gt;</span><span class="sxs-lookup"><span data-stu-id="4f8c2-111">PS&gt;**Set-AppvClientPackage $pkg –DynamicDeploymentConfiguration** &lt;path to deployment configuration file&gt;</span></span>

    <span data-ttu-id="4f8c2-112">PS &gt; **Publish-AppVClientPackage $Pkg – DynamicUserConfigurationType useDeploymentConfiguration**</span><span class="sxs-lookup"><span data-stu-id="4f8c2-112">PS&gt;**Publish-AppVClientPackage $pkg –DynamicUserConfigurationType useDeploymentConfiguration**</span></span>

3.  <span data-ttu-id="4f8c2-113">公開更新を実行するか、アプリ-V 4.6 SP2 パッケージの次にスケジュールされている発行の更新を待ちます。</span><span class="sxs-lookup"><span data-stu-id="4f8c2-113">Perform a publishing refresh, or wait for the next scheduled publishing refresh for the App-V 4.6 SP2 package.</span></span>

    <span data-ttu-id="4f8c2-114">FTAs またはショートカットを使用してアプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="4f8c2-114">Open the application using FTAs or shortcuts.</span></span> <span data-ttu-id="4f8c2-115">アプリケーションは、App-v 4.6 を使って開くようになりました。</span><span class="sxs-lookup"><span data-stu-id="4f8c2-115">The Application should now open using App-V 4.6.</span></span>

    **<span data-ttu-id="4f8c2-116">注</span><span class="sxs-lookup"><span data-stu-id="4f8c2-116">Note</span></span>**  
    <span data-ttu-id="4f8c2-117">App-v 5.0 パッケージが不要になった場合は、app-v 5.0 パッケージの発行を取り消すことができます。また、拡張ポイントは自動的に App V 4.6 に戻ります。</span><span class="sxs-lookup"><span data-stu-id="4f8c2-117">If you do not need the App-V 5.0 package anymore, you can unpublish the App-V 5.0 package and the extension points will automatically revert to App-V 4.6.</span></span>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="4f8c2-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4f8c2-118">Related topics</span></span>


[<span data-ttu-id="4f8c2-119">APP-V 5.0 の操作</span><span class="sxs-lookup"><span data-stu-id="4f8c2-119">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)









