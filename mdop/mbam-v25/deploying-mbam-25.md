---
title: MBAM 2.5 の展開
description: MBAM 2.5 の展開
author: dansimp
ms.assetid: 45403607-1f4d-42fe-8413-0d4da01808a6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0cfa0a190530186211cd96884b2e32e9c65881f1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826284"
---
# <span data-ttu-id="030cf-103">MBAM 2.5 の展開</span><span class="sxs-lookup"><span data-stu-id="030cf-103">Deploying MBAM 2.5</span></span>


<span data-ttu-id="030cf-104">この情報を使用して、Microsoft BitLocker の管理と監視 (MBAM) 2.5 サーバー機能を展開して構成し、以前のバージョンから MBAM 2.5 にアップグレードしたり、MBAM サーバー機能を削除したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="030cf-104">Use this information to identify the procedures you can follow to deploy and configure Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 Server features to upgrade to MBAM 2.5 from previous versions, or to remove MBAM Server features.</span></span>

## <span data-ttu-id="030cf-105">展開情報</span><span class="sxs-lookup"><span data-stu-id="030cf-105">Deployment information</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="030cf-106">トピックの説明</span><span class="sxs-lookup"><span data-stu-id="030cf-106">Topic description</span></span></th>
<th align="left"><span data-ttu-id="030cf-107">トピックへのリンク</span><span class="sxs-lookup"><span data-stu-id="030cf-107">Links to topics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><ul>
<li><p><span data-ttu-id="030cf-108">展開トポロジのオプション。</span><span class="sxs-lookup"><span data-stu-id="030cf-108">Deployment topology options.</span></span></p></li>
<li><p><span data-ttu-id="030cf-109">MBAM サーバーソフトウェアをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="030cf-109">How to install the MBAM Server software.</span></span></p></li>
<li><p><span data-ttu-id="030cf-110">MBAM サーバー機能を構成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="030cf-110">How to configure the MBAM Server features.</span></span></p></li>
</ul></td>
<td align="left"><p><a href="deploying-the-mbam-25-server-infrastructure.md" data-raw-source="[Deploying the MBAM 2.5 Server Infrastructure](deploying-the-mbam-25-server-infrastructure.md)"><span data-ttu-id="030cf-111">MBAM 2.5 サーバー インフラストラクチャの展開</span><span class="sxs-lookup"><span data-stu-id="030cf-111">Deploying the MBAM 2.5 Server Infrastructure</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="030cf-112">Mbam クライアントとエンタープライズの BitLocker 暗号化ポリシーを管理するために必要な MBAM グループポリシーテンプレートをダウンロードして展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="030cf-112">How to download and deploy the MBAM Group Policy Templates, which are required to manage MBAM Clients and BitLocker encryption policies in the enterprise.</span></span></p></td>
<td align="left"><p><a href="deploying-mbam-25-group-policy-objects.md" data-raw-source="[Deploying MBAM 2.5 Group Policy Objects](deploying-mbam-25-group-policy-objects.md)"><span data-ttu-id="030cf-113">MBAM 2.5 グループ ポリシー オブジェクトの展開</span><span class="sxs-lookup"><span data-stu-id="030cf-113">Deploying MBAM 2.5 Group Policy Objects</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="030cf-114">MBAM クライアントの Windows インストーラーファイルを使用して MBAM クライアントソフトウェアを展開する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="030cf-114">How to use the MBAM Client Windows Installer files to deploy the MBAM Client software.</span></span></p></td>
<td align="left"><p><a href="deploying-the-mbam-25-client.md" data-raw-source="[Deploying the MBAM 2.5 Client](deploying-the-mbam-25-client.md)"><span data-ttu-id="030cf-115">MBAM 2.5 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="030cf-115">Deploying the MBAM 2.5 Client</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="030cf-116">MBAM Server 機能と MBAM クライアントの展開に役立つチェックリスト。</span><span class="sxs-lookup"><span data-stu-id="030cf-116">Checklist that can assist you in deploying the MBAM Server features and MBAM Client.</span></span></p></td>
<td align="left"><p><a href="mbam-25-deployment-checklist.md" data-raw-source="[MBAM 2.5 Deployment Checklist](mbam-25-deployment-checklist.md)"><span data-ttu-id="030cf-117">MBAM 2.5 の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="030cf-117">MBAM 2.5 Deployment Checklist</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="030cf-118">以前のバージョンから MBAM にアップグレードする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="030cf-118">How to upgrade MBAM from previous versions.</span></span></p></td>
<td align="left"><p><a href="upgrading-to-mbam-25-or-mbam-25-sp1-from-previous-versions.md" data-raw-source="[Upgrading to MBAM 2.5 or MBAM 2.5 SP1 from Previous Versions](upgrading-to-mbam-25-or-mbam-25-sp1-from-previous-versions.md)"><span data-ttu-id="030cf-119">以前のバージョンから MBAM 2.5 または MBAM 2.5 SP1 へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="030cf-119">Upgrading to MBAM 2.5 or MBAM 2.5 SP1 from Previous Versions</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="030cf-120">MBAM サーバーの機能またはソフトウェアを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="030cf-120">How to remove MBAM Server features or software.</span></span></p></td>
<td align="left"><p><a href="removing-mbam-server-features-or-software.md" data-raw-source="[Removing MBAM Server Features or Software](removing-mbam-server-features-or-software.md)"><span data-ttu-id="030cf-121">MBAM サーバーの機能またはソフトウェアの削除</span><span class="sxs-lookup"><span data-stu-id="030cf-121">Removing MBAM Server Features or Software</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="030cf-122">MBAM の展開に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="030cf-122">Other resources for deploying MBAM</span></span>


[<span data-ttu-id="030cf-123">Microsoft BitLocker Administration and Monitoring 2.5</span><span class="sxs-lookup"><span data-stu-id="030cf-123">Microsoft BitLocker Administration and Monitoring 2.5</span></span>](index.md)

[<span data-ttu-id="030cf-124">MBAM 2.5 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="030cf-124">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)

[<span data-ttu-id="030cf-125">MBAM 2.5 の計画</span><span class="sxs-lookup"><span data-stu-id="030cf-125">Planning for MBAM 2.5</span></span>](planning-for-mbam-25.md)

[<span data-ttu-id="030cf-126">MBAM 2.5 の操作</span><span class="sxs-lookup"><span data-stu-id="030cf-126">Operations for MBAM 2.5</span></span>](operations-for-mbam-25.md)

[<span data-ttu-id="030cf-127">MBAM 2.5 のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="030cf-127">Troubleshooting MBAM 2.5</span></span>](troubleshooting-mbam-25.md)

[<span data-ttu-id="030cf-128">MBAM 2.5 テクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="030cf-128">Technical Reference for MBAM 2.5</span></span>](technical-reference-for-mbam-25.md)

[<span data-ttu-id="030cf-129">スタンドアロン構成での MBAM 2.5 の展開</span><span class="sxs-lookup"><span data-stu-id="030cf-129">Deploying MBAM 2.5 in a stand-alone configuration</span></span>](https://support.microsoft.com/kb/3046555)

## <span data-ttu-id="030cf-130">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="030cf-130">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="030cf-131">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="030cf-131">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="030cf-132">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="030cf-132">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>

 

 





