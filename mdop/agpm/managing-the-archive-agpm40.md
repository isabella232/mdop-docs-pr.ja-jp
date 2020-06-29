---
title: アーカイブの管理
description: アーカイブの管理
author: dansimp
ms.assetid: b11a3d71-74ea-4dd7-b243-6f2880b7af2d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 682d720b4095dbfa6a7cc4d868109f57c4f54641
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820557"
---
# <span data-ttu-id="c5ef6-103">アーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="c5ef6-103">Managing the Archive</span></span>


<span data-ttu-id="c5ef6-104">[高度なグループポリシー管理 (AGPM)] は、AGPM 管理者 (フルコントロール) として、アーカイブへのアクセスを管理し、アーカイブに保存されている各グループポリシーオブジェクト (GPO) のバージョン数を制限するオプションを備えています。</span><span class="sxs-lookup"><span data-stu-id="c5ef6-104">In Advanced Group Policy Management (AGPM), as an AGPM Administrator (Full Control), you manage access to the archive and have the option to limit the number of versions of each Group Policy Object (GPO) stored in the archive.</span></span> <span data-ttu-id="c5ef6-105">アーカイブ内の Gpo へのアクセスは、ドメインレベルまたは GPO レベルで委任できます。</span><span class="sxs-lookup"><span data-stu-id="c5ef6-105">You can delegate access to GPOs in the archive at the domain level or GPO level.</span></span> <span data-ttu-id="c5ef6-106">さらに、障害が発生した場合に復元できるようにアーカイブのバックアップを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="c5ef6-106">Additionally, you can back up the archive so that you may be able to recover it if a disaster occurs.</span></span>

<span data-ttu-id="c5ef6-107">AGPM 管理者として、GPO をファイルにエクスポートし、そのファイルを別のフォレストにコピーして、そのフォレストのドメインに GPO をインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="c5ef6-107">As an AGPM Administrator, you can export a GPO to a file, copy the file to another forest, and then import the GPO into a domain in that forest.</span></span> <span data-ttu-id="c5ef6-108">エディターとは異なり、GPO バックアップのポリシー設定は、作成時に新しい制御された GPO に直接インポートできます。</span><span class="sxs-lookup"><span data-stu-id="c5ef6-108">Unlike an Editor, you can import policy settings from a GPO backup directly into a new controlled GPO when you create it.</span></span> <span data-ttu-id="c5ef6-109">GPO のエクスポート方法の詳細については、「 [gpo をファイルにエクスポート](export-a-gpo-to-a-file.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5ef6-109">For information about how to export a GPO, see [Export a GPO to a File](export-a-gpo-to-a-file.md).</span></span>

-   [<span data-ttu-id="c5ef6-110">アーカイブへのドメイン レベルのアクセスを委任する</span><span class="sxs-lookup"><span data-stu-id="c5ef6-110">Delegate Domain-Level Access to the Archive</span></span>](delegate-domain-level-access-to-the-archive-agpm40.md)

-   [<span data-ttu-id="c5ef6-111">アーカイブ内の個々の GPO へのアクセスを委任する</span><span class="sxs-lookup"><span data-stu-id="c5ef6-111">Delegate Access to an Individual GPO in the Archive</span></span>](delegate-access-to-an-individual-gpo-in-the-archive-agpm40.md)

-   [<span data-ttu-id="c5ef6-112">保存される GPO のバージョンを制限する</span><span class="sxs-lookup"><span data-stu-id="c5ef6-112">Limit the GPO Versions Stored</span></span>](limit-the-gpo-versions-stored-agpm40.md)

-   [<span data-ttu-id="c5ef6-113">ファイルから GPO をインポートする</span><span class="sxs-lookup"><span data-stu-id="c5ef6-113">Import a GPO from a File</span></span>](import-a-gpo-from-a-file-agpmadmin.md)

-   [<span data-ttu-id="c5ef6-114">アーカイブをバックアップする</span><span class="sxs-lookup"><span data-stu-id="c5ef6-114">Back Up the Archive</span></span>](back-up-the-archive-agpm40.md)

-   [<span data-ttu-id="c5ef6-115">バックアップからアーカイブを復元する</span><span class="sxs-lookup"><span data-stu-id="c5ef6-115">Restore the Archive from a Backup</span></span>](restore-the-archive-from-a-backup-agpm40.md)

### <span data-ttu-id="c5ef6-116">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="c5ef6-116">Additional references</span></span>

-   <span data-ttu-id="c5ef6-117">運用環境で Gpo へのアクセスを委任する方法については、「[運用環境へのアクセスを](delegate-access-to-the-production-environment-agpm40.md)委任する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5ef6-117">For information about how to delegate access to GPOs in the production environment, see [Delegate Access to the Production Environment](delegate-access-to-the-production-environment-agpm40.md).</span></span>

-   <span data-ttu-id="c5ef6-118">アーカイブの移動方法については、「 [AGPM サーバーとアーカイブの移動](move-the-agpm-server-and-the-archive-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5ef6-118">For information about how to move the archive, see [Move the AGPM Server and the Archive](move-the-agpm-server-and-the-archive-agpm40.md).</span></span>

-   [<span data-ttu-id="c5ef6-119">AGPM 管理者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="c5ef6-119">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks-agpm40.md)

 

 





