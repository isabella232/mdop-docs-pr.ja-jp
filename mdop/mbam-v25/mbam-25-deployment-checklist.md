---
title: MBAM 2.5 の展開チェックリスト
description: MBAM 2.5 の展開チェックリスト
author: dansimp
ms.assetid: 2ba7de17-e3a4-4798-99e0-cd1dc28c5b76
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 11609b3d6d44d62b032e35005e5d967ca6d4e83b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822834"
---
# <span data-ttu-id="c02a9-103">MBAM 2.5 の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="c02a9-103">MBAM 2.5 Deployment Checklist</span></span>


<span data-ttu-id="c02a9-104">このチェックリストを使用すると、スタンドアロンのトポロジを使って、Microsoft BitLocker の管理と監視 (MBAM) 展開を行うときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c02a9-104">You can use this checklist to help you during Microsoft BitLocker Administration and Monitoring (MBAM) deployment with a Stand-alone topology.</span></span>

**<span data-ttu-id="c02a9-105">注</span><span class="sxs-lookup"><span data-stu-id="c02a9-105">Note</span></span>**  
<span data-ttu-id="c02a9-106">このチェックリストは、推奨される手順と、Microsoft BitLocker の管理機能と監視機能を展開するときに考慮する必要のある項目の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="c02a9-106">This checklist outlines the recommended steps and a high-level list of items to consider when you deploy Microsoft BitLocker Administration and Monitoring features.</span></span> <span data-ttu-id="c02a9-107">このチェックリストをスプレッドシートプログラムにコピーして、用途に合わせてカスタマイズすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c02a9-107">We recommend that you copy this checklist into a spreadsheet program and customize it for your use.</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="c02a9-108">タスク</span><span class="sxs-lookup"><span data-stu-id="c02a9-108">Task</span></span></th>
<th align="left"><span data-ttu-id="c02a9-109">参照先</span><span class="sxs-lookup"><span data-stu-id="c02a9-109">References</span></span></th>
<th align="left"><span data-ttu-id="c02a9-110">備考</span><span class="sxs-lookup"><span data-stu-id="c02a9-110">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="c02a9-111">MBAM 展開の環境を準備するために、すべての計画手順を確認して完了します。</span><span class="sxs-lookup"><span data-stu-id="c02a9-111">Review and complete all planning steps to prepare your environment for MBAM deployment.</span></span></p></td>
<td align="left"><p><a href="mbam-25-planning-checklist.md" data-raw-source="[MBAM 2.5 Planning Checklist](mbam-25-planning-checklist.md)"><span data-ttu-id="c02a9-112">MBAM 2.5 の計画チェックリスト</span><span class="sxs-lookup"><span data-stu-id="c02a9-112">MBAM 2.5 Planning Checklist</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="c02a9-113">サポートされている構成情報を確認して、MBAM が選択されたクライアントとサーバーコンピューターをサポートしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c02a9-113">Review the supported configurations information to ensure that MBAM supports the selected client and server computers.</span></span></p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="c02a9-114">MBAM 2.5 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="c02a9-114">MBAM 2.5 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="c02a9-115">MBAM サーバーソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c02a9-115">Install the MBAM Server software.</span></span></p></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="c02a9-116">MBAM 2.5 サーバー ソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="c02a9-116">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="c02a9-117">MBAM サーバー機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="c02a9-117">Configure the MBAM Server features:</span></span></p>
<ul>
<li><p><span data-ttu-id="c02a9-118">コンプライアンスと監査データベースと復元データベース</span><span class="sxs-lookup"><span data-stu-id="c02a9-118">Compliance and Audit Database and Recovery Database</span></span></p></li>
<li><p><span data-ttu-id="c02a9-119">レポート</span><span class="sxs-lookup"><span data-stu-id="c02a9-119">Reports</span></span></p></li>
<li><p><span data-ttu-id="c02a9-120">Web アプリケーション</span><span class="sxs-lookup"><span data-stu-id="c02a9-120">Web applications</span></span></p></li>
<li><p><span data-ttu-id="c02a9-121">Configuration Manager の統合トポロジ (このトポロジで MBAM を実行している場合にのみ必要)</span><span class="sxs-lookup"><span data-stu-id="c02a9-121">Configuration Manager Integration topology (needed only if you are running MBAM with this topology)</span></span></p></li>
</ul>
<div class="alert">
<strong><span data-ttu-id="c02a9-122">注</span><span class="sxs-lookup"><span data-stu-id="c02a9-122">Note</span></span></strong><br/><p><span data-ttu-id="c02a9-123">各機能を構成するサーバーの名前をメモします。</span><span class="sxs-lookup"><span data-stu-id="c02a9-123">Note the names of the servers on which you configure each feature.</span></span> <span data-ttu-id="c02a9-124">この情報は、構成プロセス全体で使用します。</span><span class="sxs-lookup"><span data-stu-id="c02a9-124">You will use this information throughout the configuration process.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="configuring-the-mbam-25-server-features.md" data-raw-source="[Configuring the MBAM 2.5 Server Features](configuring-the-mbam-25-server-features.md)"><span data-ttu-id="c02a9-125">MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="c02a9-125">Configuring the MBAM 2.5 Server Features</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="c02a9-126">MBAM 構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="c02a9-126">Validate the MBAM configuration.</span></span></p></td>
<td align="left"><p><a href="validating-the-mbam-25-server-feature-configuration.md" data-raw-source="[Validating the MBAM 2.5 Server Feature Configuration](validating-the-mbam-25-server-feature-configuration.md)"><span data-ttu-id="c02a9-127">MBAM 2.5 サーバー機能の構成の確認</span><span class="sxs-lookup"><span data-stu-id="c02a9-127">Validating the MBAM 2.5 Server Feature Configuration</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="c02a9-128">MBAM グループポリシーテンプレートをコピーし、グループポリシー設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="c02a9-128">Copy the MBAM Group Policy Template and edit the Group Policy settings.</span></span></p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)"><span data-ttu-id="c02a9-129">MBAM 2.5 グループポリシーテンプレートのコピー </a> と <a href="editing-the-mbam-25-group-policy-settings.md" data-raw-source="[Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md)"> mbam 2.5 グループポリシー設定の編集</span><span class="sxs-lookup"><span data-stu-id="c02a9-129">Copying the MBAM 2.5 Group Policy Templates</a> and <a href="editing-the-mbam-25-group-policy-settings.md" data-raw-source="[Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md)">Editing the MBAM 2.5 Group Policy Settings</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="c02a9-130">MBAM クライアントソフトウェアを展開します。</span><span class="sxs-lookup"><span data-stu-id="c02a9-130">Deploy the MBAM Client software.</span></span></p></td>
<td align="left"><p><a href="deploying-the-mbam-25-client.md" data-raw-source="[Deploying the MBAM 2.5 Client](deploying-the-mbam-25-client.md)"><span data-ttu-id="c02a9-131">MBAM 2.5 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="c02a9-131">Deploying the MBAM 2.5 Client</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>




## <span data-ttu-id="c02a9-132">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c02a9-132">Related topics</span></span>


[<span data-ttu-id="c02a9-133">MBAM 2.5 の展開</span><span class="sxs-lookup"><span data-stu-id="c02a9-133">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)




## <span data-ttu-id="c02a9-134">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="c02a9-134">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="c02a9-135">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="c02a9-135">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="c02a9-136">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="c02a9-136">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




