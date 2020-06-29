---
title: PowerShell を使用した App-V の管理
description: PowerShell を使用した App-V の管理
author: dansimp
ms.assetid: 1ff4686a-1e19-4eff-b648-ada091281094
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0e7f9171e0ac5589d8f1935e715dfdb9c349192d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814859"
---
# <span data-ttu-id="4fcab-103">PowerShell を使用した App-V の管理</span><span class="sxs-lookup"><span data-stu-id="4fcab-103">Administering App-V by Using PowerShell</span></span>


<span data-ttu-id="4fcab-104">Microsoft Application Virtualization (App-v) 5.0 には、Windows PowerShell コマンドレットが用意されています。これは、管理者がさまざまなアプリ-V 5.0 タスクを実行するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4fcab-104">Microsoft Application Virtualization (App-V) 5.0 provides Windows PowerShell cmdlets, which can help administrators perform various App-V 5.0 tasks.</span></span> <span data-ttu-id="4fcab-105">以下のセクションでは、PowerShell と App-v 5.0 の使用について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="4fcab-105">The following sections provide more information about using PowerShell with App-V 5.0.</span></span>

## <span data-ttu-id="4fcab-106">PowerShell を使用して App-v 5.0 を管理する方法</span><span class="sxs-lookup"><span data-stu-id="4fcab-106">How to administer App-V 5.0 by using PowerShell</span></span>


<span data-ttu-id="4fcab-107">次の PowerShell の手順を使用して、さまざまな App V 5.0 タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="4fcab-107">Use the following PowerShell procedures to perform various App-V 5.0 tasks.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4fcab-108">名前</span><span class="sxs-lookup"><span data-stu-id="4fcab-108">Name</span></span></th>
<th align="left"><span data-ttu-id="4fcab-109">説明</span><span class="sxs-lookup"><span data-stu-id="4fcab-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md" data-raw-source="[How to Load the PowerShell Cmdlets and Get Cmdlet Help](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md)"><span data-ttu-id="4fcab-110">PowerShell コマンドレットを読み込んでコマンドレットのヘルプを取得する方法</span><span class="sxs-lookup"><span data-stu-id="4fcab-110">How to Load the PowerShell Cmdlets and Get Cmdlet Help</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="4fcab-111">PowerShell コマンドレットをインストールして、コマンドレットのヘルプと例を見つける方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4fcab-111">Describes how to install the PowerShell cmdlets and find cmdlet help and examples.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md)"><span data-ttu-id="4fcab-112">PowerShell を使用してスタンドアロン コンピューターで実行されている App-V 5.0 パッケージを管理する方法</span><span class="sxs-lookup"><span data-stu-id="4fcab-112">How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="4fcab-113">PowerShell を使用してスタンドアロンコンピューターでクライアントパッケージのライフサイクルを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4fcab-113">Describes how to manage the client package lifecycle on a stand-alone computer using PowerShell.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md)"><span data-ttu-id="4fcab-114">PowerShell を使用してスタンドアロン コンピューターで接続グループを管理する方法</span><span class="sxs-lookup"><span data-stu-id="4fcab-114">How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="4fcab-115">PowerShell を使用して接続グループを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4fcab-115">Describes how to manage connection groups using PowerShell.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-modify-client-configuration-by-using-powershell.md" data-raw-source="[How to Modify Client Configuration by Using PowerShell](how-to-modify-client-configuration-by-using-powershell.md)"><span data-ttu-id="4fcab-116">PowerShell を使用してクライアント構成を変更する方法</span><span class="sxs-lookup"><span data-stu-id="4fcab-116">How to Modify Client Configuration by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="4fcab-117">PowerShell を使用してクライアントを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4fcab-117">Describes how to modify the client using PowerShell.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-apply-the-user-configuration-file-by-using-powershell.md" data-raw-source="[How to Apply the User Configuration File by Using PowerShell](how-to-apply-the-user-configuration-file-by-using-powershell.md)"><span data-ttu-id="4fcab-118">PowerShell を使用してユーザー構成ファイルを適用する方法</span><span class="sxs-lookup"><span data-stu-id="4fcab-118">How to Apply the User Configuration File by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="4fcab-119">PowerShell を使用してユーザー構成ファイルを適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4fcab-119">Describes how to apply a user configuration file using PowerShell.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-apply-the-deployment-configuration-file-by-using-powershell.md" data-raw-source="[How to Apply the Deployment Configuration File by Using PowerShell](how-to-apply-the-deployment-configuration-file-by-using-powershell.md)"><span data-ttu-id="4fcab-120">PowerShell を使用して展開構成ファイルを適用する方法</span><span class="sxs-lookup"><span data-stu-id="4fcab-120">How to Apply the Deployment Configuration File by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="4fcab-121">PowerShell を使用して展開構成ファイルを適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4fcab-121">Describes how to apply a deployment configuration file using PowerShell.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-sequence-a-package--by-using-powershell-50.md" data-raw-source="[How to Sequence a Package by Using PowerShell](how-to-sequence-a-package--by-using-powershell-50.md)"><span data-ttu-id="4fcab-122">PowerShell を使用してパッケージをシーケンス処理する方法</span><span class="sxs-lookup"><span data-stu-id="4fcab-122">How to Sequence a Package by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="4fcab-123">PowerShell を使用して新しいパッケージを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4fcab-123">Describes how to create a new package using PowerShell.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-create-a-package-accelerator-by-using-powershell.md" data-raw-source="[How to Create a Package Accelerator by Using PowerShell](how-to-create-a-package-accelerator-by-using-powershell.md)"><span data-ttu-id="4fcab-124">PowerShell を使用してパッケージ アクセラレータを作成する方法</span><span class="sxs-lookup"><span data-stu-id="4fcab-124">How to Create a Package Accelerator by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="4fcab-125">PowerShell を使用してパッケージアクセラレータを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4fcab-125">Describes how to create a package accelerator using PowerShell.</span></span> <span data-ttu-id="4fcab-126">パッケージアクセラレータを使うと、大規模で複雑なアプリケーションを自動的にシーケンスできます。</span><span class="sxs-lookup"><span data-stu-id="4fcab-126">You can use package accelerators automatically sequence large, complex applications.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md" data-raw-source="[How to Enable Reporting on the App-V 5.0 Client by Using PowerShell](how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md)"><span data-ttu-id="4fcab-127">PowerShell を使用して App-V 5.0 Client のレポート機能を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="4fcab-127">How to Enable Reporting on the App-V 5.0 Client by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="4fcab-128">App-v 5.0 を実行しているコンピューターでレポート情報を送信できるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4fcab-128">Describes how to enable the computer running the App-V 5.0 to send reporting information.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell.md" data-raw-source="[How to Install the App-V Databases and Convert the Associated Security Identifiers by Using PowerShell](how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell.md)"><span data-ttu-id="4fcab-129">PowerShell を使用して App-v データベースをインストールし、関連付けられたセキュリティ識別子を変換する方法</span><span class="sxs-lookup"><span data-stu-id="4fcab-129">How to Install the App-V Databases and Convert the Associated Security Identifiers by Using PowerShell</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="4fcab-130">アカウント名の配列を取得し、標準形式と16進数形式でそれぞれの名前を対応する SID に変換する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4fcab-130">Describes how to take an array of account names and to convert each of them to the corresponding SID in standard and hexadecimal formats.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="4fcab-131">PowerShell エラー処理</span><span class="sxs-lookup"><span data-stu-id="4fcab-131">PowerShell Error Handling</span></span>


<span data-ttu-id="4fcab-132">App-v 5.0 PowerShell エラー処理については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fcab-132">Use the following table for information about App-V 5.0 PowerShell error handling.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4fcab-133">イベント</span><span class="sxs-lookup"><span data-stu-id="4fcab-133">Event</span></span></th>
<th align="left"><span data-ttu-id="4fcab-134">操作</span><span class="sxs-lookup"><span data-stu-id="4fcab-134">Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fcab-135">埋め込みスクリプトでの RollbackOnError 属性の使用</span><span class="sxs-lookup"><span data-stu-id="4fcab-135">Using the RollbackOnError attribute with embedded scripts</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fcab-136"><strong> </strong> 埋め込みスクリプトと共に RollbackOnError 属性を使うと、次のイベントについては属性が無視されます。</span><span class="sxs-lookup"><span data-stu-id="4fcab-136">When you use the <strong>RollbackOnError</strong> attribute with embedded scripts, the attribute is ignored for the following events:</span></span></p>
<ul>
<li><p><span data-ttu-id="4fcab-137">パッケージの削除</span><span class="sxs-lookup"><span data-stu-id="4fcab-137">Removing a package</span></span></p></li>
<li><p><span data-ttu-id="4fcab-138">パッケージの発行を取り消している</span><span class="sxs-lookup"><span data-stu-id="4fcab-138">Unpublishing a package</span></span></p></li>
<li><p><span data-ttu-id="4fcab-139">仮想環境の終了</span><span class="sxs-lookup"><span data-stu-id="4fcab-139">Terminating a virtual environment</span></span></p></li>
<li><p><span data-ttu-id="4fcab-140">プロセスの終了</span><span class="sxs-lookup"><span data-stu-id="4fcab-140">Terminating a process</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fcab-141">パッケージ名の内容<strong>$</span><span class="sxs-lookup"><span data-stu-id="4fcab-141">Package name contains <strong>$</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="4fcab-142">パッケージ名に文字 () が含まれている場合は、 <strong> $ </strong> 次のように単一引用符 ( <strong> ') を使用する必要があります。 </strong></span><span class="sxs-lookup"><span data-stu-id="4fcab-142">If a package name contains the character ( <strong>$</strong> ), you must use a single-quote ( <strong>‘</strong> ), for example,</span></span></p>
<p><strong><span data-ttu-id="4fcab-143">Add-AppvClientPackage ' Contoso $ App-info '</span><span class="sxs-lookup"><span data-stu-id="4fcab-143">Add-AppvClientPackage ‘Contoso$App.appv’</span></span></strong></p></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="4fcab-144">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4fcab-144">Related topics</span></span>


[<span data-ttu-id="4fcab-145">APP-V 5.0 の操作</span><span class="sxs-lookup"><span data-stu-id="4fcab-145">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





