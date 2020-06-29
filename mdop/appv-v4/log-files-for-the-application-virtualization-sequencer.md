---
title: Application Virtualization Sequencer のログ ファイル
description: Application Virtualization Sequencer のログ ファイル
author: dansimp
ms.assetid: 1a296544-eab4-46f9-82ce-3136f8b578af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d8cdf9dbc78ccdd03df5903ef4d42990099a2c53
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816217"
---
# <span data-ttu-id="e5e73-103">Application Virtualization Sequencer のログ ファイル</span><span class="sxs-lookup"><span data-stu-id="e5e73-103">Log Files for the Application Virtualization Sequencer</span></span>


<span data-ttu-id="e5e73-104">Application Virtualization (App-v) Sequencer のログファイルには、アプリケーションの優先順位に関する詳細情報が記載されています。また、機能を確認するときや、問題のトラブルシューティングを行うときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e5e73-104">The log files for the Application Virtualization (App-V) Sequencer provide detailed information about sequencing applications, and they can be helpful when you are verifying functionality or when you are troubleshooting issues.</span></span>

<span data-ttu-id="e5e73-105">次の表は、Sequencer を使用するときに作成されるログファイルとその既定の場所に関する情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="e5e73-105">The following table provides information about the log files and their default locations, which are created when using the Sequencer.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e5e73-106">ログファイル名</span><span class="sxs-lookup"><span data-stu-id="e5e73-106">Log File Name</span></span></th>
<th align="left"><span data-ttu-id="e5e73-107">説明</span><span class="sxs-lookup"><span data-stu-id="e5e73-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e5e73-108">sft-seq-log.txt</span><span class="sxs-lookup"><span data-stu-id="e5e73-108">sft-seq-log.txt</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e5e73-109">アプリケーションの順序付けに関する一般的な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5e73-109">Provides general information about sequencing an application.</span></span> <span data-ttu-id="e5e73-110">このログは、Sequencer エラーのトラブルシューティングの出発点として使用します。</span><span class="sxs-lookup"><span data-stu-id="e5e73-110">Use this log as a starting point for troubleshooting Sequencer errors.</span></span></p>
<p><span data-ttu-id="e5e73-111">ログファイルの場所: <em> %Windir%\Microsoft Application Virtualization Sequencer\Logs</span><span class="sxs-lookup"><span data-stu-id="e5e73-111">Log file location: <em>%windir%\Microsoft Application Virtualization Sequencer\Logs</span></span></em></p>
<p><span data-ttu-id="e5e73-112">[Template Token の値]App-v 4.6 log file location: <em> %windir%\Program Valuapplication Virtualization Sequencer\Logs </em> [Template Token Value]</span><span class="sxs-lookup"><span data-stu-id="e5e73-112">[Template Token Value] App-V4.6 log file location: <em>%windir%\Program Files\Microsoft Application Virtualization Sequencer\Logs</em>[Template Token Value]</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e5e73-113">sftbt.txt</span><span class="sxs-lookup"><span data-stu-id="e5e73-113">sftbt.txt</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e5e73-114">Sequencer のシミュレートされた再起動時に発生する、コンピューターの再起動タスクに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5e73-114">Provides information about computer restart tasks that occur during the Sequencer’s simulated restart.</span></span></p>
<p><span data-ttu-id="e5e73-115">ログファイルの場所: <em> %Windir%\Microsoft Application Virtualization Sequencer\Logs</span><span class="sxs-lookup"><span data-stu-id="e5e73-115">Log file location: <em>%windir%\Microsoft Application Virtualization Sequencer\Logs</span></span></em></p>
<p><span data-ttu-id="e5e73-116">[Template Token の値]App-v 4.6 log file location: <em> %windir%\Program Valuapplication Virtualization Sequencer\Logs </em> [Template Token Value]</span><span class="sxs-lookup"><span data-stu-id="e5e73-116">[Template Token Value] App-V4.6 log file location: <em>%windir%\Program Files\Microsoft Application Virtualization Sequencer\Logs</em>[Template Token Value]</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e5e73-117">SftCallBack.txt</span><span class="sxs-lookup"><span data-stu-id="e5e73-117">SftCallBack.txt</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e5e73-118">シーケンス中に使用されるプロセスに関する一般的な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e5e73-118">Provides general information about processes used during sequencing.</span></span></p>
<p><span data-ttu-id="e5e73-119">ログファイルの場所: <em> %Windir%\Microsoft Application Virtualization Sequencer\Logs</span><span class="sxs-lookup"><span data-stu-id="e5e73-119">Log file location: <em>%windir%\Microsoft Application Virtualization Sequencer\Logs</span></span></em></p>
<p><span data-ttu-id="e5e73-120">[Template Token の値]App-v 4.6 log file location: <em> %windir%\Program Valuapplication Virtualization Sequencer\Logs </em> [Template Token Value]</span><span class="sxs-lookup"><span data-stu-id="e5e73-120">[Template Token Value] App-V4.6 log file location: <em>%windir%\Program Files\Microsoft Application Virtualization Sequencer\Logs</em>[Template Token Value]</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="e5e73-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e5e73-121">Related topics</span></span>


[<span data-ttu-id="e5e73-122">Application Virtualization Sequencer リファレンス</span><span class="sxs-lookup"><span data-stu-id="e5e73-122">Application Virtualization Sequencer Reference</span></span>](application-virtualization-sequencer-reference.md)

 

 





