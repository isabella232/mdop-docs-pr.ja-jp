---
title: MBAM 2.5 サーバー インフラストラクチャの展開
description: MBAM 2.5 サーバー インフラストラクチャの展開
author: dansimp
ms.assetid: e85a60cf-4cc1-4906-8da3-442232c374af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b3ec622ad60c6d5e8528b9e1c38227bc2c463634
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826274"
---
# <span data-ttu-id="20c80-103">MBAM 2.5 サーバー インフラストラクチャの展開</span><span class="sxs-lookup"><span data-stu-id="20c80-103">Deploying the MBAM 2.5 Server Infrastructure</span></span>


<span data-ttu-id="20c80-104">Microsoft BitLocker 管理と監視 (MBAM) 2.5 サーバーインフラストラクチャを展開するには、次の3つの大まかなタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="20c80-104">To deploy the Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 Server infrastructure, you complete the following three high-level tasks:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="20c80-105">タスク</span><span class="sxs-lookup"><span data-stu-id="20c80-105">Task</span></span></th>
<th align="left"><span data-ttu-id="20c80-106">手順を表示する場所</span><span class="sxs-lookup"><span data-stu-id="20c80-106">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20c80-107">Mbam Server 機能を構成する各サーバーに MBAM 2.5 サーバーソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="20c80-107">Install the MBAM 2.5 Server software on each server where you want to configure an MBAM Server feature.</span></span></p></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="20c80-108">MBAM 2.5 サーバー ソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="20c80-108">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="20c80-109">データベース、レポート、web アプリケーション、オプションの System Center Configuration Manager の統合トポロジを構成します。</span><span class="sxs-lookup"><span data-stu-id="20c80-109">Configure the databases, reports, web applications, and the optional System Center Configuration Manager Integration topology.</span></span></p>
<p><span data-ttu-id="20c80-110">MBAM サーバー構成ウィザードまたは Windows PowerShell コマンドレットを使用して、構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="20c80-110">You can use the MBAM Server Configuration wizard or Windows PowerShell cmdlets to do the configuration.</span></span></p></td>
<td align="left"><p><a href="configuring-the-mbam-25-server-features.md" data-raw-source="[Configuring the MBAM 2.5 Server Features](configuring-the-mbam-25-server-features.md)"><span data-ttu-id="20c80-111">MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="20c80-111">Configuring the MBAM 2.5 Server Features</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20c80-112">MBAM サーバーの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="20c80-112">Validate the MBAM Server configuration.</span></span></p></td>
<td align="left"><p><a href="validating-the-mbam-25-server-feature-configuration.md" data-raw-source="[Validating the MBAM 2.5 Server Feature Configuration](validating-the-mbam-25-server-feature-configuration.md)"><span data-ttu-id="20c80-113">MBAM 2.5 サーバー機能の構成の確認</span><span class="sxs-lookup"><span data-stu-id="20c80-113">Validating the MBAM 2.5 Server Feature Configuration</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="20c80-114">関連トピック</span><span class="sxs-lookup"><span data-stu-id="20c80-114">Related topics</span></span>


[<span data-ttu-id="20c80-115">MBAM 2.5 の展開</span><span class="sxs-lookup"><span data-stu-id="20c80-115">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)

 
## <span data-ttu-id="20c80-116">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="20c80-116">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="20c80-117">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="20c80-117">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="20c80-118">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="20c80-118">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





