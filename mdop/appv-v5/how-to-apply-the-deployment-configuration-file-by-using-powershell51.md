---
title: PowerShell を使用して展開構成ファイルを適用する方法
description: PowerShell を使用して展開構成ファイルを適用する方法
author: dansimp
ms.assetid: 78fe0f15-4a36-41e3-96d6-7d5aa77c1e06
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 49beb7ea4afe46c9b0f1640152c786d7c6ba8663
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814442"
---
# <span data-ttu-id="a93ba-103">PowerShell を使用して展開構成ファイルを適用する方法</span><span class="sxs-lookup"><span data-stu-id="a93ba-103">How to Apply the Deployment Configuration File by Using PowerShell</span></span>


<span data-ttu-id="a93ba-104">動的展開構成ファイルは、パッケージが公開される前に、パッケージが追加されたとき、または App-v 5.1 クライアントを実行しているコンピューターに設定されたときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a93ba-104">The dynamic deployment configuration file is applied when a package is added or set to a computer running the App-V 5.1 client before the package has been published.</span></span> <span data-ttu-id="a93ba-105">このファイルは、App-v 5.1 クライアントを実行しているコンピューター上のすべてのユーザーに対してパッケージの既定の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="a93ba-105">The file configures the default settings for package for all users on the computer running the App-V 5.1 client.</span></span> <span data-ttu-id="a93ba-106">このセクションでは、展開構成ファイルを使用するために使用する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="a93ba-106">This section describes the steps used to use a deployment configuration file.</span></span> <span data-ttu-id="a93ba-107">この手順は、次の例に基づいており、コンピューターに次のパッケージと構成ファイルが存在することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="a93ba-107">The procedure is based on the following example and assumes the following package and configuration files exist on a computer:</span></span>

**<span data-ttu-id="a93ba-108">c:\\Packages\\Contoso\\MyApp.appv</span><span class="sxs-lookup"><span data-stu-id="a93ba-108">c:\\Packages\\Contoso\\MyApp.appv</span></span>**

**<span data-ttu-id="a93ba-109">c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml</span><span class="sxs-lookup"><span data-stu-id="a93ba-109">c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml</span></span>**

**<span data-ttu-id="a93ba-110">PowerShell を使用して展開構成ファイルを適用するには</span><span class="sxs-lookup"><span data-stu-id="a93ba-110">To Apply the Deployment Configuration File Using PowerShell</span></span>**

-   <span data-ttu-id="a93ba-111">特定のコンピューターでパッケージを実行するすべてのユーザーに対して、PowerShell コンソールを使用して、パッケージを実行するすべてのユーザーの新しい既定の構成セットを指定するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a93ba-111">To specify a new default set of configurations for all users who will run the package on a specific computer, using a PowerShell console type the following:</span></span>

    **<span data-ttu-id="a93ba-112">AppVClientPackage – Path c:\\Packages\\Contoso\\MyApp.appv-DynamicDeploymentConfiguration c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml</span><span class="sxs-lookup"><span data-stu-id="a93ba-112">Add-AppVClientPackage –Path c:\\Packages\\Contoso\\MyApp.appv -DynamicDeploymentConfiguration c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml</span></span>**

    **<span data-ttu-id="a93ba-113">注</span><span class="sxs-lookup"><span data-stu-id="a93ba-113">Note</span></span>**  
    <span data-ttu-id="a93ba-114">このコマンドは、結果として得られたオブジェクトを $pkg にキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="a93ba-114">This command captures the resulting object into $pkg.</span></span> <span data-ttu-id="a93ba-115">パッケージがコンピューターに既に存在している場合は、 **AppVclientPackage**コマンドレットを使用して展開構成ドキュメントを適用できます。</span><span class="sxs-lookup"><span data-stu-id="a93ba-115">If the package is already present on the computer, the **Set-AppVclientPackage** cmdlet can be used to apply the deployment configuration document:</span></span>

    **<span data-ttu-id="a93ba-116">Set-AppVClientPackage – Name Myapp – Path c:\\Packages\\Contoso\\MyApp.appv-DynamicDeploymentConfiguration c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml</span><span class="sxs-lookup"><span data-stu-id="a93ba-116">Set-AppVClientPackage –Name Myapp –Path c:\\Packages\\Contoso\\MyApp.appv -DynamicDeploymentConfiguration c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml</span></span>**



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="a93ba-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a93ba-117">Related topics</span></span>


[<span data-ttu-id="a93ba-118">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="a93ba-118">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)









