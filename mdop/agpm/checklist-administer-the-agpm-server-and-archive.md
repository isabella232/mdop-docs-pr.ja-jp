---
title: '[AGPM サーバーとアーカイブを管理する] チェックリスト'
description: '[AGPM サーバーとアーカイブを管理する] チェックリスト'
author: dansimp
ms.assetid: 0b2eb536-c3cc-462f-a42f-27a53f57bc55
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f872a476a4a8ddd93546778c6278c175ec715850
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819154"
---
# <span data-ttu-id="bdaf8-103">チェックリスト: AGPM サーバーとアーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="bdaf8-103">Checklist: Administer the AGPM Server and Archive</span></span>


<span data-ttu-id="bdaf8-104">高度なグループポリシー管理 (AGPM) では、AGPM サービスとアーカイブは、AGPM 管理者 (フルコントロール) によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="bdaf8-104">In Advanced Group Policy Management (AGPM), both the AGPM Service and the archive are managed by AGPM Administrators (Full Control).</span></span> <span data-ttu-id="bdaf8-105">AGPM 管理者向けの一般的なタスクを次に示します。</span><span class="sxs-lookup"><span data-stu-id="bdaf8-105">The following are typical tasks for an AGPM Administrator.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bdaf8-106">頻繁に作業する</span><span class="sxs-lookup"><span data-stu-id="bdaf8-106">Frequent Task</span></span></th>
<th align="left"><span data-ttu-id="bdaf8-107">リファレンス</span><span class="sxs-lookup"><span data-stu-id="bdaf8-107">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bdaf8-108">アーカイブのグループポリシーオブジェクト (Gpo) へのアクセスを委任します。</span><span class="sxs-lookup"><span data-stu-id="bdaf8-108">Delegate access to Group Policy Objects (GPOs) in the archive.</span></span></p></td>
<td align="left"><p><a href="delegate-domain-level-access-to-the-archive-agpm30ops.md" data-raw-source="[Delegate Domain-Level Access to the Archive](delegate-domain-level-access-to-the-archive-agpm30ops.md)"><span data-ttu-id="bdaf8-109">アーカイブへのドメイン レベルのアクセスを委任する</span><span class="sxs-lookup"><span data-stu-id="bdaf8-109">Delegate Domain-Level Access to the Archive</span></span></a></p>
<p><a href="delegate-access-to-an-individual-gpo-in-the-archive-agpm30ops.md" data-raw-source="[Delegate Access to an Individual GPO in the Archive](delegate-access-to-an-individual-gpo-in-the-archive-agpm30ops.md)"><span data-ttu-id="bdaf8-110">アーカイブ内の個々の GPO へのアクセスを委任する</span><span class="sxs-lookup"><span data-stu-id="bdaf8-110">Delegate Access to an Individual GPO in the Archive</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bdaf8-111">アーカイブをバックアップして、障害回復を有効にします。</span><span class="sxs-lookup"><span data-stu-id="bdaf8-111">Back up the archive to enable disaster recovery.</span></span></p></td>
<td align="left"><p><a href="back-up-the-archive.md" data-raw-source="[Back Up the Archive](back-up-the-archive.md)"><span data-ttu-id="bdaf8-112">アーカイブをバックアップする</span><span class="sxs-lookup"><span data-stu-id="bdaf8-112">Back Up the Archive</span></span></a></p></td>
</tr>
</tbody>
</table>

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bdaf8-113">頻度の低いタスク</span><span class="sxs-lookup"><span data-stu-id="bdaf8-113">Infrequent Task</span></span></th>
<th align="left"><span data-ttu-id="bdaf8-114">リファレンス</span><span class="sxs-lookup"><span data-stu-id="bdaf8-114">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bdaf8-115">バックアップからアーカイブを復元して、障害から回復します。</span><span class="sxs-lookup"><span data-stu-id="bdaf8-115">Restore the archive from a backup to recover from a disaster.</span></span></p></td>
<td align="left"><p><a href="restore-the-archive-from-a-backup.md" data-raw-source="[Restore the Archive from a Backup](restore-the-archive-from-a-backup.md)"><span data-ttu-id="bdaf8-116">バックアップからアーカイブを復元する</span><span class="sxs-lookup"><span data-stu-id="bdaf8-116">Restore the Archive from a Backup</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bdaf8-117">AGPM サービス、アーカイブ、またはその両方を別のサーバーに移動します。</span><span class="sxs-lookup"><span data-stu-id="bdaf8-117">Move the AGPM Service, the archive, or both to a different server.</span></span></p></td>
<td align="left"><p><a href="move-the-agpm-server-and-the-archive.md" data-raw-source="[Move the AGPM Server and the Archive](move-the-agpm-server-and-the-archive.md)"><span data-ttu-id="bdaf8-118">AGPM サーバーとアーカイブを移動する</span><span class="sxs-lookup"><span data-stu-id="bdaf8-118">Move the AGPM Server and the Archive</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bdaf8-119">アーカイブパス、AGPM サービスアカウント、または AGPM サービスがリッスンするポートを変更します。</span><span class="sxs-lookup"><span data-stu-id="bdaf8-119">Change the archive path, the AGPM Service Account, or the port on which the AGPM Service listens.</span></span></p></td>
<td align="left"><p><a href="modify-the-agpm-service-agpm30ops.md" data-raw-source="[Modify the AGPM Service](modify-the-agpm-service-agpm30ops.md)"><span data-ttu-id="bdaf8-120">AGPM サービスを変更する</span><span class="sxs-lookup"><span data-stu-id="bdaf8-120">Modify the AGPM Service</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bdaf8-121">AGPM サーバーの一般的な問題のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="bdaf8-121">Troubleshoot common problems with the AGPM Server.</span></span></p></td>
<td align="left"><p><a href="troubleshooting-advanced-group-policy-management-agpm30ops.md" data-raw-source="[Troubleshooting Advanced Group Policy Management](troubleshooting-advanced-group-policy-management-agpm30ops.md)"><span data-ttu-id="bdaf8-122">高度なグループ ポリシーの管理のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bdaf8-122">Troubleshooting Advanced Group Policy Management</span></span></a></p>
<p><a href="configure-logging-and-tracing-agpm30ops.md" data-raw-source="[Configure Logging and Tracing](configure-logging-and-tracing-agpm30ops.md)"><span data-ttu-id="bdaf8-123">ログとトレースを構成する</span><span class="sxs-lookup"><span data-stu-id="bdaf8-123">Configure Logging and Tracing</span></span></a></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="bdaf8-124">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="bdaf8-124">Additional references</span></span>

-   [<span data-ttu-id="bdaf8-125">Microsoft Advanced Group Policy Management 3.0 運用ガイド</span><span class="sxs-lookup"><span data-stu-id="bdaf8-125">Operations Guide for Microsoft Advanced Group Policy Management 3.0</span></span>](operations-guide-for-microsoft-advanced-group-policy-management-30-agpm30ops.md)

 

 





