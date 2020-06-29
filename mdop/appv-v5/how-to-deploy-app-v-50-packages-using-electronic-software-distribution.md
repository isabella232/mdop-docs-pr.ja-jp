---
title: 電子ソフトウェア配布を使用して App-V 5.0 パッケージを展開する方法
description: 電子ソフトウェア配布を使用して App-V 5.0 パッケージを展開する方法
author: dansimp
ms.assetid: 08e5e05b-dbb8-4be7-b2d8-721ef627da81
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 33af02c5e9fad7408f9719ecd1a7fa90eacfeb29
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814187"
---
# <span data-ttu-id="727bc-103">電子ソフトウェア配布を使用して App-V 5.0 パッケージを展開する方法</span><span class="sxs-lookup"><span data-stu-id="727bc-103">How to deploy App-V 5.0 Packages Using Electronic Software Distribution</span></span>


<span data-ttu-id="727bc-104">電子ソフトウェア配布 (ESD) システムを使用して、app-v 5.0 仮想アプリケーションを app-v クライアントに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="727bc-104">You can use an electronic software distribution (ESD) system to deploy App-V 5.0 virtual applications to App-V clients.</span></span> <span data-ttu-id="727bc-105">詳細については、使用している ESD で利用できるドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="727bc-105">For details, see the documentation available with the ESD you are using.</span></span>

<span data-ttu-id="727bc-106">コンポーネントの要件と、ESD を使って App-v パッケージを展開するオプションについては、「[電子ソフトウェア配布システムを使用してアプリ5.0 の展開を計画する](planning-to-deploy-app-v-50-with-an-electronic-software-distribution-system.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="727bc-106">For component requirements and options for using an ESD to deploy App-V packages, see [Planning to Deploy App-V 5.0 with an Electronic Software Distribution System](planning-to-deploy-app-v-50-with-an-electronic-software-distribution-system.md).</span></span>

<span data-ttu-id="727bc-107">ESD を伴う App-v クライアントコンピューターにパッケージを公開するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="727bc-107">Use one of the following methods to publish packages to App-V client computers with an ESD:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="727bc-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="727bc-108">Method</span></span></th>
<th align="left"><span data-ttu-id="727bc-109">説明</span><span class="sxs-lookup"><span data-stu-id="727bc-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="727bc-110">サードパーティの ESD によって提供される機能</span><span class="sxs-lookup"><span data-stu-id="727bc-110">Functionality provided by a third-party ESD</span></span></p></td>
<td align="left"><p><span data-ttu-id="727bc-111">サードパーティの ESD の機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="727bc-111">Use the functionality in a third-party ESD.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="727bc-112">スタンドアロンの Windows インストーラー</span><span class="sxs-lookup"><span data-stu-id="727bc-112">Stand-alone Windows Installer</span></span></p></td>
<td align="left"><p><span data-ttu-id="727bc-113">アプリケーションの最初の順序で作成された関連付けられた Windows インストーラー (.msi) ファイルを使用して、ターゲットクライアントコンピューターにアプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="727bc-113">Install the application on the target client computer by using the associated Windows Installer (.msi) file that is created when you initially sequence an application.</span></span> <span data-ttu-id="727bc-114">Windows Installer ファイルには、パッケージを構成し、必要なパッケージファイルをクライアントにコピーするために使用される、関連付けられた App-v 5.0 パッケージファイル情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="727bc-114">The Windows Installer file contains the associated App-V 5.0 package file information used to configure a package and copies the required package files to the client.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="727bc-115">PowerShell</span><span class="sxs-lookup"><span data-stu-id="727bc-115">PowerShell</span></span></p></td>
<td align="left"><p><span data-ttu-id="727bc-116">PowerShell コマンドレットを使用して、仮想化されたアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="727bc-116">Use PowerShell cmdlets to deploy virtualized applications.</span></span> <span data-ttu-id="727bc-117">PowerShell と App-v 5.0 の使用方法について詳しくは、「PowerShell を使用した app-v の管理」をご覧ください <a href="administering-app-v-by-using-powershell.md" data-raw-source="[Administering App-V by Using PowerShell](administering-app-v-by-using-powershell.md)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="727bc-117">For more information about using PowerShell and App-V 5.0, see <a href="administering-app-v-by-using-powershell.md" data-raw-source="[Administering App-V by Using PowerShell](administering-app-v-by-using-powershell.md)">Administering App-V by Using PowerShell</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="727bc-118">ESD を使って App-v 5.0 パッケージを展開するには</span><span class="sxs-lookup"><span data-stu-id="727bc-118">To deploy App-V 5.0 packages by using an ESD</span></span>**

1.  <span data-ttu-id="727bc-119">環境内のコンピューターに app-v 5.0 Sequencer をインストールします。</span><span class="sxs-lookup"><span data-stu-id="727bc-119">Install the App-V 5.0 Sequencer on a computer in your environment.</span></span> <span data-ttu-id="727bc-120">Sequencer のインストールの詳細については、「 [sequencer をインストールする方法](how-to-install-the-sequencer-beta-gb18030.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="727bc-120">For more information about installing the sequencer, see [How to Install the Sequencer](how-to-install-the-sequencer-beta-gb18030.md).</span></span>

2.  <span data-ttu-id="727bc-121">アプリ-V 5.0 Sequencer を使って、仮想アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="727bc-121">Use the App-V 5.0 Sequencer to create virtual application.</span></span> <span data-ttu-id="727bc-122">仮想アプリケーションの作成について詳しくは、「 [app-v 5.0 で仮想化されたアプリケーションを作成および管理](creating-and-managing-app-v-50-virtualized-applications.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="727bc-122">For information about creating a virtual application, see [Creating and Managing App-V 5.0 Virtualized Applications](creating-and-managing-app-v-50-virtualized-applications.md).</span></span>

3.  <span data-ttu-id="727bc-123">仮想アプリケーションを作成したら、ESD ソリューションを使用してパッケージを展開します。</span><span class="sxs-lookup"><span data-stu-id="727bc-123">After you create the virtual application, deploy the package by using your ESD solution.</span></span>

    <span data-ttu-id="727bc-124">System Center Configuration Manager を使用している場合は、App-v 5.0 と System Center2012 Configuration Manager を使用する方法について、「 [Configuration manager でのアプリケーション管理の概要」を](https://go.microsoft.com/fwlink/?LinkId=281816)参照してください。</span><span class="sxs-lookup"><span data-stu-id="727bc-124">If you are using System Center Configuration Manager, start by reviewing [Introduction to Application Management in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=281816) for information about using App-V 5.0 and System Center2012 Configuration Manager.</span></span>

    <span data-ttu-id="727bc-125">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="727bc-125">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="727bc-126">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="727bc-126">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="727bc-127">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="727bc-127">Got an App-V issue?</span></span>** <span data-ttu-id="727bc-128">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="727bc-128">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="727bc-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="727bc-129">Related topics</span></span>


[<span data-ttu-id="727bc-130">APP-V 5.0 の操作</span><span class="sxs-lookup"><span data-stu-id="727bc-130">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





