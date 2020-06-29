---
title: PowerShell コマンドを使用して DaRT のタスクを実行する方法
description: PowerShell コマンドを使用して DaRT のタスクを実行する方法
author: dansimp
ms.assetid: f5a5c5f9-d667-4c85-9e82-7baf0b2aec6e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fdf167ca81281da4e04dae10e34bad6122ec05aa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822597"
---
# <span data-ttu-id="ee51c-103">PowerShell コマンドを使用して DaRT のタスクを実行する方法</span><span class="sxs-lookup"><span data-stu-id="ee51c-103">How to Perform DaRT Tasks by Using PowerShell Commands</span></span>


<span data-ttu-id="ee51c-104">Microsoft 診断/回復ツールセット (DaRT) 10 には、次のような Windows PowerShell コマンドレットのセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ee51c-104">Microsoft Diagnostics and Recovery Toolset (DaRT) 10 provides the following listed set of Windows PowerShell cmdlets.</span></span> <span data-ttu-id="ee51c-105">管理者は、これらの PowerShell コマンドレットを使って、DaRT 回復イメージウィザードではなく、コマンドプロンプトからさまざまな DaRT 10 server タスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="ee51c-105">Administrators can use these PowerShell cmdlets to perform various DaRT 10 server tasks from the command prompt rather than from the DaRT Recovery Image wizard.</span></span>

## <span data-ttu-id="ee51c-106">PowerShell コマンドを使用して DaRT を管理するには</span><span class="sxs-lookup"><span data-stu-id="ee51c-106">To administer DaRT by using PowerShell commands</span></span>


<span data-ttu-id="ee51c-107">DaRT を管理するには、ここで説明する PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ee51c-107">Use the PowerShell cmdlets described here to administer DaRT.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ee51c-108">名前</span><span class="sxs-lookup"><span data-stu-id="ee51c-108">Name</span></span></th>
<th align="left"><span data-ttu-id="ee51c-109">説明</span><span class="sxs-lookup"><span data-stu-id="ee51c-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee51c-110">コピー-DartImage</span><span class="sxs-lookup"><span data-stu-id="ee51c-110">Copy-DartImage</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee51c-111">ISO を CD、DVD、または USB ドライブに焼きます。</span><span class="sxs-lookup"><span data-stu-id="ee51c-111">Burns an ISO to a CD, DVD, or USB drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee51c-112">エクスポート-DartImage</span><span class="sxs-lookup"><span data-stu-id="ee51c-112">Export-DartImage</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee51c-113">DaRT イメージを含むソース WIM ファイルを ISO ファイルに変換できます。</span><span class="sxs-lookup"><span data-stu-id="ee51c-113">Allows the source WIM file, which contains a DaRT image, to be converted into an ISO file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee51c-114">新規-DartConfiguration</span><span class="sxs-lookup"><span data-stu-id="ee51c-114">New-DartConfiguration</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee51c-115">DaRT のツールセットを Windows イメージに適用するために必要な DaRT 構成オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ee51c-115">Creates a DaRT configuration object that is needed to apply a DaRT toolset to a Windows Image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee51c-116">Set-DartImage</span><span class="sxs-lookup"><span data-stu-id="ee51c-116">Set-DartImage</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee51c-117">マウントされた Windows イメージに DartConfiguration オブジェクトを適用します。</span><span class="sxs-lookup"><span data-stu-id="ee51c-117">Applies a DartConfiguration object to a mounted Windows Image.</span></span> <span data-ttu-id="ee51c-118">これには、すべてのファイル、構成、パッケージの依存関係の追加が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ee51c-118">This includes adding all files, configuration, and package dependencies.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="ee51c-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ee51c-119">Related topics</span></span>


[<span data-ttu-id="ee51c-120">PowerShell を使用した DaRT 10 の管理</span><span class="sxs-lookup"><span data-stu-id="ee51c-120">Administering DaRT 10 Using PowerShell</span></span>](administering-dart-10-using-powershell.md)

 

 





