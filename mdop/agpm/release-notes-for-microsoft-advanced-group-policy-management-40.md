---
title: Microsoft Advanced Group Policy Management (AGPM) 4.0 リリース ノート
description: Microsoft Advanced Group Policy Management (AGPM) 4.0 リリース ノート
author: dansimp
ms.assetid: 44c19e61-c8e8-48aa-a2c2-20396d14d5bb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c4a279893d4da4121e422af99e7c1708a0126b4e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820394"
---
# <span data-ttu-id="f6d7c-103">Microsoft Advanced Group Policy Management (AGPM) 4.0 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="f6d7c-103">Release Notes for Microsoft Advanced Group Policy Management 4.0</span></span>


<span data-ttu-id="f6d7c-104">2009 年 10 月</span><span class="sxs-lookup"><span data-stu-id="f6d7c-104">October 2009</span></span>

## <span data-ttu-id="f6d7c-105">Microsoft Advanced グループポリシー管理4.0 について</span><span class="sxs-lookup"><span data-stu-id="f6d7c-105">About Microsoft Advanced Group Policy Management 4.0</span></span>


<span data-ttu-id="f6d7c-106">Microsoft Advanced グループポリシー管理 (AGPM) 4.0 は、グループポリシー管理コンソール (GPMC) の機能を拡張します。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-106">Microsoft Advanced Group Policy Management (AGPM) 4.0 extends the capabilities of the Group Policy Management Console (GPMC).</span></span> <span data-ttu-id="f6d7c-107">AGPM は、グループポリシーオブジェクト (Gpo) の包括的な変更管理と改善された管理を提供します。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-107">AGPM provides comprehensive change control and improved management of Group Policy Objects (GPOs).</span></span>

<span data-ttu-id="f6d7c-108">次のドキュメントは、AGPM 4.0 を使い始めるときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-108">The following documents can help you get started with AGPM 4.0.</span></span>

-   <span data-ttu-id="f6d7c-109">AGPM の機能の概要については、「 [Microsoft Advanced グループポリシー管理の概要](https://go.microsoft.com/fwlink/?LinkID=162671)(」を参照してください https://go.microsoft.com/fwlink/?LinkID=162671) 。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-109">For an overview of the capabilities of AGPM, see [Overview of Microsoft Advanced Group Policy Management](https://go.microsoft.com/fwlink/?LinkID=162671) (https://go.microsoft.com/fwlink/?LinkID=162671).</span></span>

-   <span data-ttu-id="f6d7c-110">Agpm 4.0 と AGPM 3.0 との違いについては、「AGPM 4.0 () の[新機能](https://go.microsoft.com/fwlink/?LinkId=160058)」を参照してください https://go.microsoft.com/fwlink/?LinkId=160058) 。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-110">For information about how AGPM 4.0 differs from AGPM 3.0, see [What's New in AGPM 4.0](https://go.microsoft.com/fwlink/?LinkId=160058) (https://go.microsoft.com/fwlink/?LinkId=160058).</span></span>

-   <span data-ttu-id="f6d7c-111">使用している環境に対して AGPM 4.0、AGPM 3.0、または AGPM 2.5 が適切であるかどうかを判断する方法については、「[インストールする agpm のバージョン](https://go.microsoft.com/fwlink/?LinkId=145981)() を選択する」を参照してください https://go.microsoft.com/fwlink/?LinkId=145981) 。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-111">For guidance about how to determine whether AGPM 4.0, AGPM 3.0, or AGPM 2.5 is appropriate for your environment, see [Choosing Which Version of AGPM to Install](https://go.microsoft.com/fwlink/?LinkId=145981) (https://go.microsoft.com/fwlink/?LinkId=145981).</span></span>

-   <span data-ttu-id="f6d7c-112">Agpm と agpm を使用するためのサンプルシナリオのインストール方法についての基本的なガイダンスについては、「 [Microsoft Advanced Group Policy Management 4.0 () のステップバイステップガイド](https://go.microsoft.com/fwlink/?LinkID=153505)」を参照してください https://go.microsoft.com/fwlink/?LinkID=153505) 。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-112">For basic guidance about how to install AGPM and a sample scenario for using AGPM, see [Step-by-Step Guide for Microsoft Advanced Group Policy Management 4.0](https://go.microsoft.com/fwlink/?LinkID=153505) (https://go.microsoft.com/fwlink/?LinkID=153505).</span></span> <span data-ttu-id="f6d7c-113">このガイドは、主に、評価と初回ユーザーに役立つように設計されています。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-113">This guide is primarily designed to help evaluators and first-time users.</span></span>

-   <span data-ttu-id="f6d7c-114">以前のバージョンの AGPM からアップグレードする方法や、組織での AGPM の展開を計画する方法についての詳細なガイダンスについては、 [Microsoft Advanced グループポリシー管理 4.0 () の計画ガイド](https://go.microsoft.com/fwlink/?LinkID=156883)をご覧ください https://go.microsoft.com/fwlink/?LinkID=156883) 。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-114">For information about how to upgrade from an earlier version of AGPM or detailed guidance about how to plan the deployment of AGPM in your organization, see the [Planning Guide for Microsoft Advanced Group Policy Management 4.0](https://go.microsoft.com/fwlink/?LinkID=156883) (https://go.microsoft.com/fwlink/?LinkID=156883).</span></span>

-   <span data-ttu-id="f6d7c-115">AGPM を使って特定のタスクを実行する方法については、「高度なグループポリシー管理4.0 のヘルプ」を参照してください。これは、 [AGPM 4.0 () の操作ガイド](https://go.microsoft.com/fwlink/?LinkId=159872)として TechNet でも利用でき https://go.microsoft.com/fwlink/?LinkId=159872) ます。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-115">For information about how to use AGPM to perform specific tasks, see the Advanced Group Policy Management 4.0 Help, which is also available on TechNet as the [Operations Guide for AGPM 4.0](https://go.microsoft.com/fwlink/?LinkId=159872) (https://go.microsoft.com/fwlink/?LinkId=159872).</span></span>

## <span data-ttu-id="f6d7c-116">詳細情報</span><span class="sxs-lookup"><span data-stu-id="f6d7c-116">More information</span></span>


<span data-ttu-id="f6d7c-117">AGPM の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-117">For more information about AGPM, see the following:</span></span>

-   <span data-ttu-id="f6d7c-118">[高度なグループポリシー管理の TechNet ライブラリ](https://go.microsoft.com/fwlink/?LinkID=146846)(https://go.microsoft.com/fwlink/?LinkID=146846)</span><span class="sxs-lookup"><span data-stu-id="f6d7c-118">[Advanced Group Policy Management TechNet Library](https://go.microsoft.com/fwlink/?LinkID=146846) (https://go.microsoft.com/fwlink/?LinkID=146846)</span></span>

-   <span data-ttu-id="f6d7c-119">[Microsoft デスクトップ最適化パックの TechCenter](https://go.microsoft.com/fwlink/?LinkId=159870) (https://www.microsoft.com/technet/mdop)</span><span class="sxs-lookup"><span data-stu-id="f6d7c-119">[Microsoft Desktop Optimization Pack TechCenter](https://go.microsoft.com/fwlink/?LinkId=159870) (https://www.microsoft.com/technet/mdop)</span></span>

-   <span data-ttu-id="f6d7c-120">[グループポリシー TechCenter](https://go.microsoft.com/fwlink/?LinkId=145531) (https://www.microsoft.com/gp)</span><span class="sxs-lookup"><span data-stu-id="f6d7c-120">[Group Policy TechCenter](https://go.microsoft.com/fwlink/?LinkId=145531) (https://www.microsoft.com/gp)</span></span>

## <span data-ttu-id="f6d7c-121">フィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="f6d7c-121">Providing feedback</span></span>


<span data-ttu-id="f6d7c-122">AGPM に関するフィードバックや質問は、[グループポリシーフォーラム](https://go.microsoft.com/fwlink/?LinkId=145532)() に投稿でき https://go.microsoft.com/fwlink/?LinkId=145532) ます。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-122">You can post feedback or questions about AGPM to the [Group Policy Forum](https://go.microsoft.com/fwlink/?LinkId=145532) (https://go.microsoft.com/fwlink/?LinkId=145532).</span></span>

## <span data-ttu-id="f6d7c-123">AGPM 4.0 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="f6d7c-123">Known issues with AGPM 4.0</span></span>


### <span data-ttu-id="f6d7c-124">[運用からインポート] コマンドでチェックアウトされた GPO に設定がインポートされない</span><span class="sxs-lookup"><span data-stu-id="f6d7c-124">Import from Production command does not import settings into a GPO that is checked out</span></span>

<span data-ttu-id="f6d7c-125">運用環境で GPO を編集する場合は、オフラインアーカイブの gpo を更新するために、その gpo を運用環境からインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-125">If you edit a GPO in the production environment, you must import the GPO from production to update the GPO in the offline archive.</span></span> <span data-ttu-id="f6d7c-126">[**運用サイトからのインポート**] コマンドは、編集が完了する前に最終的な運用バックアップを実行できるようにすることを目的としています。これにより、必要に応じて、運用バックアップにロールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-126">The **Import from Production** command is intended to let you perform a final production backup before you finish editing so that you can roll back to the production backup if it is necessary.</span></span>

<span data-ttu-id="f6d7c-127">[**運用からのインポート**] コマンドを実行したときに、gpo がチェックアウトされている場合、本番の変更は GPO のチェックアウトされたバージョンには反映されません。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-127">If the GPO is checked out when you run the **Import from Production** command, then the production changes are not incorporated into the checked out version of the GPO.</span></span> <span data-ttu-id="f6d7c-128">ただし、インポートされたバージョンの GPO は、そのバージョンが編集できない場合でも、GPO の履歴に追加されます。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-128">However, the imported version of the GPO is added to the history of the GPO even though that version is not available to be edited.</span></span> <span data-ttu-id="f6d7c-129">GPO がチェックインされると、そのバージョンはアーカイブのインポートされたバージョンに優先しますが、どちらも GPO の履歴で利用できます。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-129">When the GPO is checked in, that version will supersede the imported version in the archive, but both are available in the history of the GPO.</span></span>

<span data-ttu-id="f6d7c-130">**回避策:** 運用からインポートする前に、GPO がチェックインされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-130">**Workaround:** Make sure that the GPO is checked in before you import it from production.</span></span> <span data-ttu-id="f6d7c-131">GPO をインポートする前にチェックインしていなかった場合は、[**チェックアウトの取り消し**] コマンドを使用して変更を破棄し、運用からインポートした gpo のバージョンにロールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-131">If the GPO was not checked in before you imported it, you can use the **Undo Check Out** command to discard your changes and roll back to the version of the GPO that you imported from production.</span></span>

### <span data-ttu-id="f6d7c-132">複数のサイトの Active Directory トポロジを使用している環境では、チェックアウトされている Gpo を数分編集できない</span><span class="sxs-lookup"><span data-stu-id="f6d7c-132">Checked out GPOs cannot be edited for several minutes in an environment that uses a multiple site Active Directory topology</span></span>

<span data-ttu-id="f6d7c-133">AGPM は、クライアント/サーバーモデルを使います。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-133">AGPM uses a client/server model.</span></span> <span data-ttu-id="f6d7c-134">AGPM サーバーと AGPM クライアントはそれぞれ、グループポリシー操作の最も近いドメインコントローラーを決定します。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-134">The AGPM Server and the AGPM Client each determine their own closest domain controller for Group Policy operations.</span></span> <span data-ttu-id="f6d7c-135">AGPM クライアントを使って GPO をチェックアウトすると、実際には、オフラインアーカイブから SYSVOL フォルダーの一時フォルダーに GPO をチェックインする AGPM サーバーです。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-135">When you check out a GPO by using an AGPM Client, it is actually the AGPM Server that checks the GPO out from the offline archive to a temporary folder in the SYSVOL folder.</span></span>

<span data-ttu-id="f6d7c-136">AGPM サーバーと AGPM クライアントが別のサイトにある場合、SYSVOL の複製の待機時間のために、ローカルサイトのドメインコントローラーに、いくつかの時間、または最大30分の間、一時的にチェックアウトされた GPO が存在しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-136">If the AGPM Server and the AGPM Client are in different sites, then the temporary checked out GPO may not be present on the local site's domain controller for several minutes or up to 30 minutes due to SYSVOL replication latency.</span></span> <span data-ttu-id="f6d7c-137">この状況では、チェックアウトされた GPO の SYSVOL レプリケーションが発生するまで、AGPM クライアントで GPMC を使ってチェックアウトされた GPO を編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-137">In this situation, you cannot edit the checked out GPO using the GPMC on an AGPM Client until SYSVOL replication of the checked out GPO has occurred.</span></span>

<span data-ttu-id="f6d7c-138">**回避策:** ベストプラクティスとして、接続先の AGPM サーバーと同じサイトに AGPM クライアントを配置する必要があります。これは、チェックアウトされた GPO を編集する前に、SYSVOL のレプリケーションが実行されるのを待つ必要がないためです。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-138">**Workaround:** As a best practice, you should position AGPM Clients in the same site as the AGPM Server to which they connect so that you do not have to wait for SYSVOL replication to occur before you can edit a checked out GPO.</span></span>

### <span data-ttu-id="f6d7c-139">アカウントにアーカイブへのアクセス許可が付与されていない場合、AGPM でバックアップの制限を読み取ることはできません。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-139">AGPM cannot read the backup limit if your account does not have permissions for the archive</span></span>

<span data-ttu-id="f6d7c-140">AGPM クライアントで、AGPM アーカイブへの権限が委任されていないアカウントを使用してログオンする場合は、グループポリシー管理コンソール (GPMC) を起動し、[**制御の変更**] をクリックすると、次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-140">On an AGPM Client, if you log on by using an account that has not been delegated permissions to the AGPM archive, start the Group Policy Management Console (GPMC), and then click **Change Control**, you receive the following error.</span></span>

``` syntax
Failed to read backup purge limit for this domain. 

The following error occurred: 
You do not have sufficient permissions to perform this operation. 
Microsoft.Agpm.AccessDeniedException (80070005)
```

<span data-ttu-id="f6d7c-141">**回避策:** AGPM 管理者 (フルコントロール) に連絡して、アカウントの AGPM へのアクセスを委任するように依頼します。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-141">**Workaround:** Contact an AGPM Administrator (Full Control) and request that they delegate access to AGPM for your account.</span></span> <span data-ttu-id="f6d7c-142">AGPM 管理者の場合は、AGPM 管理者ロールが割り当てられているアカウントを使用してログオンし、追加のアカウントへのアクセスを委任できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-142">If you are an AGPM Administrator, log on by using an account to which the AGPM Administrator role is assigned so that you can delegate access for the additional account.</span></span> <span data-ttu-id="f6d7c-143">詳細については、「AGPM ヘルプ」の「アーカイブへのドメインレベルのアクセスを委任する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-143">For more information, see "Delegate Domain-Level Access to the Archive" in the AGPM Help.</span></span>

## <span data-ttu-id="f6d7c-144">リリースノートの著作権情報</span><span class="sxs-lookup"><span data-stu-id="f6d7c-144">Release notes copyright information</span></span>


<span data-ttu-id="f6d7c-145">このドキュメントに記載されている情報 (URL などのインターネット Web サイトへの参照を含む) は、予告なしに変更される可能性があり、情報提供のみを目的として提供されます。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-145">Information in this document, including URL and other Internet Web site references, is subject to change without notice, and is provided for informational purposes only.</span></span> <span data-ttu-id="f6d7c-146">このドキュメントを使用することによるすべてのリスクは、ユーザーにはとどまりません。 Microsoft Corporation は、明示的または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-146">The entire risk of the use or results of the use of this document remains with the user, and Microsoft Corporation makes no warranties, either express or implied.</span></span> <span data-ttu-id="f6d7c-147">ここで例示した会社、組織、製品、人物、イベントの例は架空のものです。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-147">The example companies, organizations, products, people and events depicted herein are fictitious.</span></span> <span data-ttu-id="f6d7c-148">実際の会社、組織、製品、人物、またはイベントとの関係はありません。また、推定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-148">No association with any real company, organization, product, person or event is intended or should be inferred.</span></span> <span data-ttu-id="f6d7c-149">お客様ご自身の責任において、適用されるすべての著作権関連法規に従ったご使用をお願いします。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-149">Complying with all applicable copyright laws is the responsibility of the user.</span></span> <span data-ttu-id="f6d7c-150">このドキュメントのいかなる部分も、米国 Microsoft Corporation の書面による許諾を受けることなく、検索システムに複製、格納、導入したり、その目的を問わず、いかなる形態や手段であっても、転送することは禁じられています。ここでいう手段とは、電子的、機械的、複写、録音など、すべての手段を含みます。ただしこれは、著作権法上のお客様の権利を制限するものではありません。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-150">Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="f6d7c-151">Microsoft は、このドキュメントに記載されている内容に関して、特許、特許申請、商標、著作権、またはその他の知的財産権を有する場合があります。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-151">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document.</span></span> <span data-ttu-id="f6d7c-152">Microsoft による使用許諾契約書によって明示的に許可されている場合を除き、このドキュメントの提供によって、これらの特許権、商標、著作権、またはその他の知的財産権のライセンスが貴社に供与されることはありません。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-152">Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>



<span data-ttu-id="f6d7c-153">Microsoft、MS-DOS、Windows、WindowsServer、Windows Vista は、U.S.A. やその他の国において、マイクロソフトコーポレーションの登録商標または商標です。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-153">Microsoft, MS-DOS, Windows, WindowsServer, and Windows Vista are either registered trademarks or trademarks of MicrosoftCorporation in the U.S.A. and/or other countries.</span></span>

<span data-ttu-id="f6d7c-154">ここに記載されている実際の会社と製品の名前は、各所有者の商標である場合があります。</span><span class="sxs-lookup"><span data-stu-id="f6d7c-154">The names of actual companies and products mentioned herein may be the trademarks of their respective owners.</span></span>

 

 





