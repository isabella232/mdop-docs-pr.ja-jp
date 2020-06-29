---
title: バックアップからアーカイブを復元する
description: バックアップからアーカイブを復元する
author: dansimp
ms.assetid: b83f6173-a236-4da2-b16e-8df20920d4cc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3a1b7039ad587cf9c8d7f914fe3b963e12ba8949
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818397"
---
# <span data-ttu-id="1ce3b-103">バックアップからアーカイブを復元する</span><span class="sxs-lookup"><span data-stu-id="1ce3b-103">Restore the Archive from a Backup</span></span>


<span data-ttu-id="1ce3b-104">障害が発生して、高度なグループポリシー管理 (AGPM) のアーカイブが破損した場合、または破棄された場合、AGPM 管理者 (フルコントロール) では、事前に準備されているバックアップコピーからアーカイブを復元することができます。その後、アーカイブ内に存在しないグループポリシーオブジェクト (Gpo) を、ドメインの運用環境</span><span class="sxs-lookup"><span data-stu-id="1ce3b-104">If a disaster occurs and the archive for Advanced Group Policy Management (AGPM) is damaged or destroyed, an AGPM Administrator (Full Control) can restore the archive from a backup copy prepared in advance and then import from the production environment of the domain any Group Policy Objects (GPOs) that are not in the archive or for which the version in production is more current than that in the archive.</span></span> <span data-ttu-id="1ce3b-105">アーカイブバックアップを別のサーバーに復元する方法について詳しくは、「 [AGPM サーバーとアーカイブの移動](move-the-agpm-server-and-the-archive-agpm40.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1ce3b-105">For information about how to restore an archive backup to a different server, see [Move the AGPM Server and the Archive](move-the-agpm-server-and-the-archive-agpm40.md).</span></span>

<span data-ttu-id="1ce3b-106">この手順を完了するには、AGPM サーバー (AGPM サービスがインストールされているコンピューター) とアーカイブが含まれているフォルダーへのアクセス権を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="1ce3b-106">A user account that has access to the AGPM Server (the computer on which the AGPM Service is installed) and to the folder that contains the archive is required to complete this procedure.</span></span>

**<span data-ttu-id="1ce3b-107">バックアップからアーカイブを復元するには</span><span class="sxs-lookup"><span data-stu-id="1ce3b-107">To restore the archive from a backup</span></span>**

1.  <span data-ttu-id="1ce3b-108">AGPM サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="1ce3b-108">Stop the AGPM Service.</span></span> <span data-ttu-id="1ce3b-109">詳細については、「 [AGPM サービスの開始と停止](start-and-stop-the-agpm-service-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ce3b-109">For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service-agpm40.md).</span></span>

2.  <span data-ttu-id="1ce3b-110">既存のアーカイブを削除します。</span><span class="sxs-lookup"><span data-stu-id="1ce3b-110">Remove the existing archive.</span></span> <span data-ttu-id="1ce3b-111">既定では、[アーカイブ] フォルダーは [\ programdata% ¥] と表示されますが、Microsoft Advanced グループポリシー管理をインストールした AGPM 管理者は、セットアップ時に別の場所を入力した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1ce3b-111">By default, the archive folder is %ProgramData%\\Microsoft\\AGPM, however the AGPM Administrator who installed Microsoft Advanced Group Policy Management - Server may have entered a different location during setup.</span></span>

3.  <span data-ttu-id="1ce3b-112">アーカイブパス、AGPM サービスアカウント、アーカイブ所有者、リッスンポートを構成して、アーカイブフォルダーを再作成します。</span><span class="sxs-lookup"><span data-stu-id="1ce3b-112">Re-create the archive folder by configuring the archive path, AGPM Service Account, Archive Owner, and listening port.</span></span> <span data-ttu-id="1ce3b-113">元のインストール時に使用したものと同じ値を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1ce3b-113">Using the same values as used during the original installation is not necessary.</span></span> <span data-ttu-id="1ce3b-114">詳細については、「 [AGPM サービスを変更する](modify-the-agpm-service-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ce3b-114">For more information, see [Modify the AGPM Service](modify-the-agpm-service-agpm40.md).</span></span>

4.  <span data-ttu-id="1ce3b-115">アーカイブバックアップの内容を [アーカイブ] フォルダーにコピーし、サブフォルダーとファイルをコピーして、各サブフォルダーとファイルがアーカイブフォルダーのアクセス許可を継承するようにします。</span><span class="sxs-lookup"><span data-stu-id="1ce3b-115">Copy the contents of the archive backup to the archive folder, copying the subfolders and files to make sure that each subfolder and file inherits the permissions of the archive folder.</span></span> <span data-ttu-id="1ce3b-116">[アーカイブ] フォルダーを上書きしないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="1ce3b-116">Be careful not to overwrite the archive folder.</span></span>

5.  <span data-ttu-id="1ce3b-117">アーカイブバックアップ内の GPO が運用環境のその GPO のコピーよりも最新であるかどうかがわからない場合は、差分レポートを生成し、その設定を比較します。</span><span class="sxs-lookup"><span data-stu-id="1ce3b-117">If you not sure about whether a GPO in the archive backup is more current than the copy of that GPO in production, generate a difference report and compare their settings.</span></span> <span data-ttu-id="1ce3b-118">詳細については、「 [gpo、gpo のバージョン、またはテンプレートの違い](identify-differences-between-gpos-gpo-versions-or-templates-agpm40.md)を確認する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ce3b-118">For more information, see [Identify Differences Between GPOs, GPO Versions, or Templates](identify-differences-between-gpos-gpo-versions-or-templates-agpm40.md).</span></span>

6.  <span data-ttu-id="1ce3b-119">AGPM サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="1ce3b-119">Restart the AGPM Service.</span></span> <span data-ttu-id="1ce3b-120">詳細については、「 [AGPM サービスの開始と停止](start-and-stop-the-agpm-service-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ce3b-120">For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service-agpm40.md).</span></span>

### <span data-ttu-id="1ce3b-121">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="1ce3b-121">Additional references</span></span>

-   [<span data-ttu-id="1ce3b-122">アーカイブをバックアップする</span><span class="sxs-lookup"><span data-stu-id="1ce3b-122">Back Up the Archive</span></span>](back-up-the-archive-agpm40.md)

-   [<span data-ttu-id="1ce3b-123">AGPM サーバーとアーカイブを移動する</span><span class="sxs-lookup"><span data-stu-id="1ce3b-123">Move the AGPM Server and the Archive</span></span>](move-the-agpm-server-and-the-archive-agpm40.md)

-   [<span data-ttu-id="1ce3b-124">アーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="1ce3b-124">Managing the Archive</span></span>](managing-the-archive-agpm40.md)

 

 





