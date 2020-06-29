---
title: 電子ソフトウェア配布を使用して App-V 5.1 パッケージを展開する方法
description: 電子ソフトウェア配布を使用して App-V 5.1 パッケージを展開する方法
author: dansimp
ms.assetid: e1957a5a-1f18-42da-b2c1-a5ae5a4cca7a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a9ed5fbb264f8fb9676d7fa18fe4de8019ea8e79
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814186"
---
# <span data-ttu-id="3b62f-103">電子ソフトウェア配布を使用して App-V 5.1 パッケージを展開する方法</span><span class="sxs-lookup"><span data-stu-id="3b62f-103">How to deploy App-V 5.1 Packages Using Electronic Software Distribution</span></span>


<span data-ttu-id="3b62f-104">電子ソフトウェア配布 (ESD) システムを使用して、app-v 5.1 仮想アプリケーションを app-v クライアントに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="3b62f-104">You can use an electronic software distribution (ESD) system to deploy App-V 5.1 virtual applications to App-V clients.</span></span> <span data-ttu-id="3b62f-105">詳細については、使用している ESD で利用できるドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b62f-105">For details, see the documentation available with the ESD you are using.</span></span>

<span data-ttu-id="3b62f-106">コンポーネントの要件と、ESD を使って App-v パッケージを展開するオプションについては、「[電子ソフトウェア配布システムを使用してアプリ5.1 の展開を計画する](planning-to-deploy-app-v-51-with-an-electronic-software-distribution-system.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b62f-106">For component requirements and options for using an ESD to deploy App-V packages, see [Planning to Deploy App-V 5.1 with an Electronic Software Distribution System](planning-to-deploy-app-v-51-with-an-electronic-software-distribution-system.md).</span></span>

<span data-ttu-id="3b62f-107">ESD を伴う App-v クライアントコンピューターにパッケージを公開するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="3b62f-107">Use one of the following methods to publish packages to App-V client computers with an ESD:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3b62f-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="3b62f-108">Method</span></span></th>
<th align="left"><span data-ttu-id="3b62f-109">説明</span><span class="sxs-lookup"><span data-stu-id="3b62f-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3b62f-110">サードパーティの ESD によって提供される機能</span><span class="sxs-lookup"><span data-stu-id="3b62f-110">Functionality provided by a third-party ESD</span></span></p></td>
<td align="left"><p><span data-ttu-id="3b62f-111">サードパーティの ESD の機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="3b62f-111">Use the functionality in a third-party ESD.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3b62f-112">スタンドアロンの Windows インストーラー</span><span class="sxs-lookup"><span data-stu-id="3b62f-112">Stand-alone Windows Installer</span></span></p></td>
<td align="left"><p><span data-ttu-id="3b62f-113">アプリケーションの最初の順序で作成された関連付けられた Windows インストーラー (.msi) ファイルを使用して、ターゲットクライアントコンピューターにアプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3b62f-113">Install the application on the target client computer by using the associated Windows Installer (.msi) file that is created when you initially sequence an application.</span></span> <span data-ttu-id="3b62f-114">Windows Installer ファイルには、パッケージを構成し、必要なパッケージファイルをクライアントにコピーするために使用される、関連付けられた App-v 5.1 パッケージファイル情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3b62f-114">The Windows Installer file contains the associated App-V 5.1 package file information used to configure a package and copies the required package files to the client.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3b62f-115">PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b62f-115">PowerShell</span></span></p></td>
<td align="left"><p><span data-ttu-id="3b62f-116">PowerShell コマンドレットを使用して、仮想化されたアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="3b62f-116">Use PowerShell cmdlets to deploy virtualized applications.</span></span> <span data-ttu-id="3b62f-117">PowerShell と App-v 5.1 の使用方法の詳細については、「 <a href="administering-app-v-51-by-using-powershell.md" data-raw-source="[Administering App-V 5.1 by Using PowerShell](administering-app-v-51-by-using-powershell.md)"> Powershell を使用したアプリの管理-v 5.1」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="3b62f-117">For more information about using PowerShell and App-V 5.1, see <a href="administering-app-v-51-by-using-powershell.md" data-raw-source="[Administering App-V 5.1 by Using PowerShell](administering-app-v-51-by-using-powershell.md)">Administering App-V 5.1 by Using PowerShell</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="3b62f-118">ESD を使って App-v 5.1 パッケージを展開するには</span><span class="sxs-lookup"><span data-stu-id="3b62f-118">To deploy App-V 5.1 packages by using an ESD</span></span>**

1.  <span data-ttu-id="3b62f-119">環境内のコンピューターに app-v 5.1 Sequencer をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3b62f-119">Install the App-V 5.1 Sequencer on a computer in your environment.</span></span> <span data-ttu-id="3b62f-120">Sequencer のインストールの詳細については、「 [sequencer をインストールする方法](how-to-install-the-sequencer-51beta-gb18030.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b62f-120">For more information about installing the sequencer, see [How to Install the Sequencer](how-to-install-the-sequencer-51beta-gb18030.md).</span></span>

2.  <span data-ttu-id="3b62f-121">アプリ-V 5.1 Sequencer を使って、仮想アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="3b62f-121">Use the App-V 5.1 Sequencer to create virtual application.</span></span> <span data-ttu-id="3b62f-122">仮想アプリケーションの作成について詳しくは、「 [app-v 5.1 で仮想化されたアプリケーションを作成および管理](creating-and-managing-app-v-51-virtualized-applications.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3b62f-122">For information about creating a virtual application, see [Creating and Managing App-V 5.1 Virtualized Applications](creating-and-managing-app-v-51-virtualized-applications.md).</span></span>

3.  <span data-ttu-id="3b62f-123">仮想アプリケーションを作成したら、ESD ソリューションを使用してパッケージを展開します。</span><span class="sxs-lookup"><span data-stu-id="3b62f-123">After you create the virtual application, deploy the package by using your ESD solution.</span></span>

    <span data-ttu-id="3b62f-124">System Center Configuration Manager を使用している場合は、App-v 5.1 と System Center2012 Configuration Manager を使用する方法について、「 [Configuration manager でのアプリケーション管理の概要」を](https://go.microsoft.com/fwlink/?LinkId=281816)参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b62f-124">If you are using System Center Configuration Manager, start by reviewing [Introduction to Application Management in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=281816) for information about using App-V 5.1 and System Center2012 Configuration Manager.</span></span>

    <span data-ttu-id="3b62f-125">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="3b62f-125">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="3b62f-126">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="3b62f-126">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="3b62f-127">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="3b62f-127">Got an App-V issue?</span></span>** <span data-ttu-id="3b62f-128">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="3b62f-128">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="3b62f-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3b62f-129">Related topics</span></span>


[<span data-ttu-id="3b62f-130">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="3b62f-130">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





