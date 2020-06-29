---
title: 管理者のみが接続グループを有効にできるようにする方法
description: 管理者のみが接続グループを有効にできるようにする方法
author: dansimp
ms.assetid: 42ca3157-5d85-467b-a148-09404f8f737a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 083d6386f02996d35255f90958705798f2cd5fb9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814451"
---
# <span data-ttu-id="cbffb-103">管理者のみが接続グループを有効にできるようにする方法</span><span class="sxs-lookup"><span data-stu-id="cbffb-103">How to Allow Only Administrators to Enable Connection Groups</span></span>


<span data-ttu-id="cbffb-104">(エンドユーザーではなく) 管理者のみが接続グループを有効または無効にできるように、App-v クライアントを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="cbffb-104">You can configure the App-V client so that only administrators (not end users) can enable or disable connection groups.</span></span> <span data-ttu-id="cbffb-105">以前のバージョンの App-v では、エンドユーザーがこれらのタスクを実行できないようにすることはできませんでした。</span><span class="sxs-lookup"><span data-stu-id="cbffb-105">In earlier versions of App-V, you could not prevent end users from performing these tasks.</span></span>

<span data-ttu-id="cbffb-106">**注** 
**この機能は、app-v 5.0 SP3 以降でサポートされています。**</span><span class="sxs-lookup"><span data-stu-id="cbffb-106">**Note**
**This feature is supported starting in App-V 5.0 SP3.**</span></span>

 

<span data-ttu-id="cbffb-107">管理者のみが接続グループを有効または無効にできるようにするには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="cbffb-107">Use one of the following methods to allow only administrators to enable or disable connection groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cbffb-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="cbffb-108">Method</span></span></th>
<th align="left"><span data-ttu-id="cbffb-109">手順</span><span class="sxs-lookup"><span data-stu-id="cbffb-109">Steps</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cbffb-110">グループ ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="cbffb-110">Group Policy setting</span></span></p></td>
<td align="left"><p><span data-ttu-id="cbffb-111">次のグループポリシーオブジェクトノードにある [管理者として公開する] グループポリシー設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="cbffb-111">Enable the “Require publish as administrator” Group Policy setting, which is located in the following Group Policy Object node:</span></span></p>
<p><strong><span data-ttu-id="cbffb-112">コンピューター構成 &gt; ポリシー &gt; 管理用テンプレート &gt; システム &gt; アプリ-V の &gt; 発行</span><span class="sxs-lookup"><span data-stu-id="cbffb-112">Computer Configuration &gt; Policies &gt; Administrative Templates &gt; System &gt; App-V &gt; Publishing</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cbffb-113">PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="cbffb-113">PowerShell cmdlet</span></span></p></td>
<td align="left"><p><span data-ttu-id="cbffb-114"><strong> </strong> <strong> – Requirepublishasadmin パラメーターを指定して AppvClientConfiguration コマンドレットを実行し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="cbffb-114">Run the <strong>Set-AppvClientConfiguration</strong> cmdlet with the <strong>–RequirePublishAsAdmin</strong> parameter.</span></span></p>
<p><span data-ttu-id="cbffb-115">パラメーターの値:</span><span class="sxs-lookup"><span data-stu-id="cbffb-115">Parameter values:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbffb-116">0-偽</span><span class="sxs-lookup"><span data-stu-id="cbffb-116">0 - False</span></span></p></li>
<li><p><span data-ttu-id="cbffb-117">1-True</span><span class="sxs-lookup"><span data-stu-id="cbffb-117">1 - True</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="cbffb-118">例: </strong> AppvClientConfiguration – RequirePublishAsAdmin1</span><span class="sxs-lookup"><span data-stu-id="cbffb-118">Example:</strong>: Set-AppvClientConfiguration –RequirePublishAsAdmin1</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="cbffb-119">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="cbffb-119">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="cbffb-120">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="cbffb-120">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="cbffb-121">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="cbffb-121">Got an App-V issue?</span></span>** <span data-ttu-id="cbffb-122">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="cbffb-122">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="cbffb-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="cbffb-123">Related topics</span></span>


[<span data-ttu-id="cbffb-124">接続グループの管理</span><span class="sxs-lookup"><span data-stu-id="cbffb-124">Managing Connection Groups</span></span>](managing-connection-groups51.md)

 

 





