---
title: PowerShell を使用してユーザー構成ファイルを適用する方法
description: PowerShell を使用してユーザー構成ファイルを適用する方法
author: dansimp
ms.assetid: 986e638c-4a0c-4a7e-be73-f4615e8b8000
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 97b3db253993d6d855384ee5d9771a7f9ff5b64d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814427"
---
# <span data-ttu-id="0d648-103">PowerShell を使用してユーザー構成ファイルを適用する方法</span><span class="sxs-lookup"><span data-stu-id="0d648-103">How to Apply the User Configuration File by Using PowerShell</span></span>


<span data-ttu-id="0d648-104">動的ユーザー構成ファイルは、パッケージが特定のユーザーに公開されたときに適用され、パッケージの実行方法が決定されます。</span><span class="sxs-lookup"><span data-stu-id="0d648-104">The dynamic user configuration file is applied when a package is published to a specific user and determines how the package will run.</span></span>

<span data-ttu-id="0d648-105">ユーザー固有の構成ファイルを指定するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="0d648-105">Use the following procedure to specify a user-specific configuration file.</span></span> <span data-ttu-id="0d648-106">次の手順は、例に基づいています。</span><span class="sxs-lookup"><span data-stu-id="0d648-106">The following procedure is based on the example:</span></span>

**<span data-ttu-id="0d648-107">c:\\Packages\\Contoso\\MyApp.appv</span><span class="sxs-lookup"><span data-stu-id="0d648-107">c:\\Packages\\Contoso\\MyApp.appv</span></span>**

**<span data-ttu-id="0d648-108">ユーザー構成ファイルを適用するには</span><span class="sxs-lookup"><span data-stu-id="0d648-108">To apply a user Configuration file</span></span>**

1.  <span data-ttu-id="0d648-109">PowerShell コンソールを使用してコンピューターにパッケージを追加するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="0d648-109">To add the package to the computer using the PowerShell console type the following command:</span></span>

    <span data-ttu-id="0d648-110">**AppVClientPackage c:\\Packages\\Contoso\\MyApp.appv を追加**します。</span><span class="sxs-lookup"><span data-stu-id="0d648-110">**Add-AppVClientPackage c:\\Packages\\Contoso\\MyApp.appv**.</span></span>

2.  <span data-ttu-id="0d648-111">次のコマンドを使用して、パッケージをユーザーに公開し、更新された動的なユーザー構成ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="0d648-111">Use the following command to publish the package to the user and specify the updated the dynamic user configuration file:</span></span>

    **<span data-ttu-id="0d648-112">Publish-AppVClientPackage $pkg – DynamicUserConfigurationPath c:\\Packages\\Contoso\\config.xml</span><span class="sxs-lookup"><span data-stu-id="0d648-112">Publish-AppVClientPackage $pkg –DynamicUserConfigurationPath c:\\Packages\\Contoso\\config.xml</span></span>**

    <span data-ttu-id="0d648-113">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="0d648-113">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="0d648-114">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="0d648-114">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="0d648-115">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="0d648-115">Got an App-V issue?</span></span>** <span data-ttu-id="0d648-116">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="0d648-116">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="0d648-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0d648-117">Related topics</span></span>


[<span data-ttu-id="0d648-118">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="0d648-118">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





