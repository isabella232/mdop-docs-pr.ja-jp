---
title: UE-V 1.0 の基幹業務アプリケーションを評価するためのチェックリスト
description: UE-V 1.0 の基幹業務アプリケーションを評価するためのチェックリスト
author: dansimp
ms.assetid: 3bfaab30-59f7-4099-abb1-d248ce0086b8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 133bc5d195763b7281fd8d152e153231ac4c4d47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826457"
---
# <span data-ttu-id="cc4c4-103">UE-V 1.0 の基幹業務アプリケーションを評価するためのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="cc4c4-103">Checklist for Evaluating Line-of-Business Applications for UE-V 1.0</span></span>


<span data-ttu-id="cc4c4-104">UE-V の展開に含める基幹業務アプリケーションを評価するには、次の点を考慮します。</span><span class="sxs-lookup"><span data-stu-id="cc4c4-104">To evaluate which line-of-business applications should be included in your UE-V deployment, consider the following:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="cc4c4-105">説明</span><span class="sxs-lookup"><span data-stu-id="cc4c4-105">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="cc4c4-106">このアプリケーションには、ユーザーがカスタマイズできる設定が含まれていますか。</span><span class="sxs-lookup"><span data-stu-id="cc4c4-106">Does this application contain settings that the user can customize?</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="cc4c4-107">これらの設定がローミングしていることは、ユーザーにとって重要ですか?</span><span class="sxs-lookup"><span data-stu-id="cc4c4-107">Is it important for the user that these settings roam?</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="cc4c4-108">これらのユーザー設定は、既にアプリケーション管理または設定ポリシーソリューションによって管理されていますか。</span><span class="sxs-lookup"><span data-stu-id="cc4c4-108">Are these user settings already managed by an application management or settings policy solution?</span></span> <span data-ttu-id="cc4c4-109">UE-V は、アプリケーションの起動と Windows の設定で、ログオン、ロック解除、またはリモート接続イベントにアプリケーション設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="cc4c4-109">UE-V applies application settings at application launch and Windows settings at logon, unlock, or remote connect events.</span></span> <span data-ttu-id="cc4c4-110">UE-V を他の設定ポリシーソリューションと共に使用している場合、ユーザーによっては、ローミング設定で不整合が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cc4c4-110">If you use UE-V with other settings policy solutions, users might experience inconsistency across roamed settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="cc4c4-111">アプリケーションの設定はコンピューターに固有のものですか?</span><span class="sxs-lookup"><span data-stu-id="cc4c4-111">Are the application settings specific to the computer?</span></span> <span data-ttu-id="cc4c4-112">ハードウェアまたは特定のコンピューター構成に関連付けられたアプリケーションの環境設定とカスタマイズは、セッション間で一貫してローミングされず、アプリケーションのパフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cc4c4-112">Application preferences and customizations that are associated with hardware or specific computer configurations do not consistently roam across sessions and can cause a poor application experience.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="cc4c4-113">アプリケーションは、Program Files ディレクトリまたは <strong> ユーザー </strong> \ [ユーザー名] \ AppData locallow ディレクトリにあるファイルディレクトリの設定を保存してい <strong> </strong>  \  <strong> </strong> ますか?</span><span class="sxs-lookup"><span data-stu-id="cc4c4-113">Does the application store settings in the Program Files directory or in the file directory that is located in the <strong>Users</strong> \ [User name] \ <strong>AppData</strong> \ <strong>LocalLow</strong> directory?</span></span> <span data-ttu-id="cc4c4-114">これらの場所のいずれかに保存されているアプリケーションデータは、通常、コンピューターに固有のデータであるため、またはデータが大きすぎてローミングできないため、ユーザーと共に移動することはできません。</span><span class="sxs-lookup"><span data-stu-id="cc4c4-114">Application data that is stored in either of these locations usually should not roam with the user, because this data is specific to the computer or because the data is too large to roam.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="cc4c4-115">ローミングしてはいけない他のアプリケーションデータを含むファイルの設定が、アプリケーションに格納されますか。</span><span class="sxs-lookup"><span data-stu-id="cc4c4-115">Does the application store any settings in a file that contains other application data that should not roam?</span></span> <span data-ttu-id="cc4c4-116">UE-V は、1つの単位としてファイルを同期します。</span><span class="sxs-lookup"><span data-stu-id="cc4c4-116">UE-V synchronizes files as a single unit.</span></span> <span data-ttu-id="cc4c4-117">設定が [設定] 以外のアプリケーションデータを含むファイルに保存されている場合、この追加データを同期すると、アプリケーションのパフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cc4c4-117">If settings are stored in files that include application data other than settings, then synchronizing this additional data may cause a poor application experience.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="cc4c4-118">設定を含むファイルのサイズはどのくらいですか?</span><span class="sxs-lookup"><span data-stu-id="cc4c4-118">How large are the files that contain the settings?</span></span> <span data-ttu-id="cc4c4-119">設定の同期のパフォーマンスは、大きなファイルの影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cc4c4-119">The performance of the settings synchronization can be affected by large files.</span></span> <span data-ttu-id="cc4c4-120">大きなファイルを含めると、設定の同期のパフォーマンスに影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cc4c4-120">Including large files can impact the performance of settings synchronization.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="cc4c4-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="cc4c4-121">Related topics</span></span>


[<span data-ttu-id="cc4c4-122">UE-V の構成方法の計画</span><span class="sxs-lookup"><span data-stu-id="cc4c4-122">Planning for UE-V Configuration Methods</span></span>](planning-for-ue-v-configuration-methods.md)

[<span data-ttu-id="cc4c4-123">UE-V 1.0 の計画</span><span class="sxs-lookup"><span data-stu-id="cc4c4-123">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

 

 





