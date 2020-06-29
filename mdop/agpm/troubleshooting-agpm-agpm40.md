---
title: AGPM のトラブルシューティング
description: AGPM のトラブルシューティング
author: dansimp
ms.assetid: bedcd817-beb2-47bf-aebd-e3923c4fd06f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b44612cb9e3737a8d8f3109f76b0c9325d183383
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820154"
---
# <span data-ttu-id="c4315-103">AGPM のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c4315-103">Troubleshooting AGPM</span></span>


<span data-ttu-id="c4315-104">このセクションでは、高度なグループポリシー管理 (AGPM) を使用してグループポリシーオブジェクト (Gpo) を管理するときに発生する可能性がある一般的な問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4315-104">This section lists common issues that you may encounter when you use Advanced Group Policy Management (AGPM) to manage Group Policy Objects (GPOs).</span></span> <span data-ttu-id="c4315-105">ここに記載されていない問題を診断するには、AGPM 管理者 (フルコントロール) でログとトレースを使用すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="c4315-105">To diagnose issues not listed here, it may be helpful for an AGPM Administrator (Full Control) to use logging and tracing.</span></span> <span data-ttu-id="c4315-106">詳細については、「[ログとトレースを構成する](configure-logging-and-tracing-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4315-106">For more information, see [Configure Logging and Tracing](configure-logging-and-tracing-agpm40.md).</span></span>

**<span data-ttu-id="c4315-107">注</span><span class="sxs-lookup"><span data-stu-id="c4315-107">Note</span></span>**  
-   <span data-ttu-id="c4315-108">GPO の以前のバージョンにロールバックするときに問題が発生した場合は、「[以前のバージョンの gpo にロールバックする](roll-back-to-an-earlier-version-of-a-gpo-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4315-108">For information about rolling back to an earlier version of a GPO if there are problems, see [Roll Back to an Earlier Version of a GPO](roll-back-to-an-earlier-version-of-a-gpo-agpm40.md).</span></span>

-   <span data-ttu-id="c4315-109">バックアップから完全なアーカイブを復元して、障害から回復する方法については、「[バックアップからアーカイブを復元](restore-the-archive-from-a-backup-agpm40.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4315-109">For information about how to recover from a disaster by restoring the complete archive from a backup, see [Restore the Archive from a Backup](restore-the-archive-from-a-backup-agpm40.md).</span></span>

 

## <span data-ttu-id="c4315-110">どのような問題が発生していますか?</span><span class="sxs-lookup"><span data-stu-id="c4315-110">What problems are you having?</span></span>


-   [<span data-ttu-id="c4315-111">アーカイブにアクセスできません</span><span class="sxs-lookup"><span data-stu-id="c4315-111">I am unable to access an archive</span></span>](#bkmk-access-an-archive)

-   [<span data-ttu-id="c4315-112">GPO の状態は、グループポリシーの管理者によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c4315-112">The GPO state varies for different Group Policy administrators</span></span>](#bkmk-state-varies)

-   [<span data-ttu-id="c4315-113">AGPM サーバー接続を変更できません</span><span class="sxs-lookup"><span data-stu-id="c4315-113">I am unable to modify the AGPM Server connection</span></span>](#bkmk-modify-archive-location)

-   [<span data-ttu-id="c4315-114">既定のテンプレートを変更できない、または Gpo の表示、作成、編集、名前の変更、展開、または削除を行うことができない</span><span class="sxs-lookup"><span data-stu-id="c4315-114">I am unable to change the default template or view, create, edit, rename, deploy, or delete GPOs</span></span>](#bkmk-perform-task)

-   [<span data-ttu-id="c4315-115">特定の GPO 名を使用できない</span><span class="sxs-lookup"><span data-stu-id="c4315-115">I am unable to use a particular GPO name</span></span>](#bkmk-use-particular-name)

-   [<span data-ttu-id="c4315-116">AGPM メール通知を受信できない</span><span class="sxs-lookup"><span data-stu-id="c4315-116">I am not receiving AGPM e-mail notifications</span></span>](#bkmk-email)

-   [<span data-ttu-id="c4315-117">AGPM サービスでポート4600を使用できない</span><span class="sxs-lookup"><span data-stu-id="c4315-117">I cannot use port 4600 for the AGPM Service</span></span>](#bkmk-port)

-   [<span data-ttu-id="c4315-118">AGPM サービスは開始されません。</span><span class="sxs-lookup"><span data-stu-id="c4315-118">The AGPM Service will not start</span></span>](#bkmk-not-start)

-   [<span data-ttu-id="c4315-119">グループポリシーソフトウェアのインストールでソフトウェアのインストールに失敗する</span><span class="sxs-lookup"><span data-stu-id="c4315-119">Group Policy Software Installation fails to install software</span></span>](#bkmk-software-installation)

-   [<span data-ttu-id="c4315-120">新しい AGPM サーバーにアーカイブを復元したときにエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="c4315-120">An error occurred when I restored the archive to a new AGPM Server</span></span>](#bkmk-error-on-restore)

### <a href="" id="bkmk-access-an-archive"></a><span data-ttu-id="c4315-121">アーカイブにアクセスできません</span><span class="sxs-lookup"><span data-stu-id="c4315-121">I am unable to access an archive</span></span>

-   <span data-ttu-id="c4315-122">**原因**: アーカイブ用の正しいサーバーとポートを選択していません。</span><span class="sxs-lookup"><span data-stu-id="c4315-122">**Cause**: You have not selected the correct server and port for the archive.</span></span>

-   <span data-ttu-id="c4315-123">**解決方法**:</span><span class="sxs-lookup"><span data-stu-id="c4315-123">**Solution**:</span></span>

    -   <span data-ttu-id="c4315-124">AGPM 管理者の場合: 「 [Agpm サーバー接続を構成](configure-agpm-server-connections-agpm40.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4315-124">If you are an AGPM Administrator: See [Configure AGPM Server Connections](configure-agpm-server-connections-agpm40.md).</span></span>

    -   <span data-ttu-id="c4315-125">AGPM 管理者ではない場合: agpm 管理者からの AGPM サーバーの接続の詳細を要求します。</span><span class="sxs-lookup"><span data-stu-id="c4315-125">If you are not an AGPM Administrator: Request connection details for the AGPM Server from an AGPM Administrator.</span></span> <span data-ttu-id="c4315-126">「 [AGPM サーバー接続を構成する](configure-an-agpm-server-connection-agpm40.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c4315-126">See [Configure an AGPM Server Connection](configure-an-agpm-server-connection-agpm40.md).</span></span>

-   <span data-ttu-id="c4315-127">**原因**: AGPM サービスが実行されていません。</span><span class="sxs-lookup"><span data-stu-id="c4315-127">**Cause**: The AGPM Service is not running.</span></span>

-   <span data-ttu-id="c4315-128">**解決方法**:</span><span class="sxs-lookup"><span data-stu-id="c4315-128">**Solution**:</span></span>

    -   <span data-ttu-id="c4315-129">AGPM 管理者の場合: AGPM サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="c4315-129">If you are an AGPM Administrator: Start the AGPM Service.</span></span> <span data-ttu-id="c4315-130">詳細については、「 [AGPM サービスの開始と停止](start-and-stop-the-agpm-service-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4315-130">For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service-agpm40.md).</span></span>

    -   <span data-ttu-id="c4315-131">AGPM 管理者ではない場合: AGPM 管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="c4315-131">If you are not an AGPM Administrator: Contact an AGPM Administrator for assistance.</span></span>

### <a href="" id="bkmk-state-varies"></a><span data-ttu-id="c4315-132">GPO の状態は、グループポリシーの管理者によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c4315-132">The GPO state varies for different Group Policy administrators</span></span>

-   <span data-ttu-id="c4315-133">**原因**: グループポリシーの管理者が、同じアーカイブに対して異なる AGPM サーバーを選択しています。</span><span class="sxs-lookup"><span data-stu-id="c4315-133">**Cause**: Different Group Policy administrators have selected different AGPM Servers for the same archive.</span></span>

-   <span data-ttu-id="c4315-134">**解決方法**:</span><span class="sxs-lookup"><span data-stu-id="c4315-134">**Solution**:</span></span>

    -   <span data-ttu-id="c4315-135">AGPM 管理者の場合: 「 [Agpm サーバー接続を構成](configure-agpm-server-connections-agpm40.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4315-135">If you are an AGPM Administrator: See [Configure AGPM Server Connections](configure-agpm-server-connections-agpm40.md).</span></span>

    -   <span data-ttu-id="c4315-136">AGPM 管理者ではない場合: agpm 管理者からの AGPM サーバーの接続の詳細を要求します。</span><span class="sxs-lookup"><span data-stu-id="c4315-136">If you are not an AGPM Administrator: Request connection details for the AGPM Server from an AGPM Administrator.</span></span> <span data-ttu-id="c4315-137">「 [AGPM サーバー接続を構成する](configure-an-agpm-server-connection-agpm40.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c4315-137">See [Configure an AGPM Server Connection](configure-an-agpm-server-connection-agpm40.md).</span></span>

### <a href="" id="bkmk-modify-archive-location"></a><span data-ttu-id="c4315-138">AGPM サーバー接続を変更できません</span><span class="sxs-lookup"><span data-stu-id="c4315-138">I am unable to modify the AGPM Server connection</span></span>

-   <span data-ttu-id="c4315-139">**原因**: [ **AGPM サーバー** ] タブの設定が利用できない場合、Agpm サーバーは管理用テンプレートを使用して一元的に構成されています。</span><span class="sxs-lookup"><span data-stu-id="c4315-139">**Cause**: If the settings on the **AGPM Server** tab are unavailable, the AGPM Server has been centrally configured using an Administrative template.</span></span>

-   <span data-ttu-id="c4315-140">**解決方法**:</span><span class="sxs-lookup"><span data-stu-id="c4315-140">**Solution**:</span></span>

    -   <span data-ttu-id="c4315-141">AGPM 管理者の場合: [ **Agpm サーバー** ] タブの設定を使用できない場合は、「 [agpm サーバー接続を構成](configure-agpm-server-connections-agpm40.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4315-141">If you are an AGPM Administrator: If the settings on the **AGPM Server** tab are unavailable, see [Configure AGPM Server Connections](configure-agpm-server-connections-agpm40.md).</span></span>

    -   <span data-ttu-id="c4315-142">AGPM 管理者ではない場合: [ **Agpm サーバー** ] タブの設定を使用できない場合は、agpm サーバーを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c4315-142">If you are not an AGPM Administrator: If the settings on the **AGPM Server** tab are unavailable, you do not need to modify the AGPM Server.</span></span>

### <a href="" id="bkmk-perform-task"></a><span data-ttu-id="c4315-143">既定のテンプレートを変更できない、または Gpo の表示、作成、編集、名前の変更、展開、または削除を行うことができない</span><span class="sxs-lookup"><span data-stu-id="c4315-143">I am unable to change the default template or view, create, edit, rename, deploy, or delete GPOs</span></span>

-   <span data-ttu-id="c4315-144">**原因**: タスクを実行するのに必要な権限を持つ役割が割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="c4315-144">**Cause**: You have not been assigned a role with the permissions required to perform the task or tasks.</span></span>

-   <span data-ttu-id="c4315-145">**解決方法**:</span><span class="sxs-lookup"><span data-stu-id="c4315-145">**Solution**:</span></span>

    -   <span data-ttu-id="c4315-146">AGPM 管理者の場合: アーカイブ[へのドメインレベルのアクセスを委任](delegate-domain-level-access-to-the-archive-agpm40.md)し、[アーカイブ内の個々の GPO へのアクセスを委任](delegate-access-to-an-individual-gpo-in-the-archive-agpm40.md)します。</span><span class="sxs-lookup"><span data-stu-id="c4315-146">If you are an AGPM Administrator: See [Delegate Domain-Level Access to the Archive](delegate-domain-level-access-to-the-archive-agpm40.md) and [Delegate Access to an Individual GPO in the Archive](delegate-access-to-an-individual-gpo-in-the-archive-agpm40.md).</span></span> <span data-ttu-id="c4315-147">AGPM 権限は、現在アーカイブ内のすべての Gpo にドメインから伝播されます。</span><span class="sxs-lookup"><span data-stu-id="c4315-147">AGPM permissions will cascade from the domain to all GPOs currently in the archive.</span></span> <span data-ttu-id="c4315-148">タスクを実行できるロールと、タスクを実行するために必要な権限の詳細については、そのタスクのヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4315-148">For details about which roles can perform a task and which permissions are necessary to perform a task, refer to the help for that task.</span></span>

    -   <span data-ttu-id="c4315-149">AGPM 管理者ではない場合に、追加の役割または権限が必要な場合は、AGPM 管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="c4315-149">If you are not an AGPM Administrator and you require additional roles or permissions: Contact an AGPM Administrator for assistance.</span></span> <span data-ttu-id="c4315-150">エディターを使用している場合、GPO の作成、GPO の展開、またはドメインの運用環境からの GPO の削除のプロセスを開始することはできますが、承認者または AGPM 管理者が要求を承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4315-150">Be aware that if you are an Editor, you can begin the process of creating a GPO, deploying a GPO, or deleting a GPO from the production environment of the domain, but an Approver or AGPM Administrator must approve your request.</span></span>

### <a href="" id="bkmk-use-particular-name"></a><span data-ttu-id="c4315-151">特定の GPO 名を使用できない</span><span class="sxs-lookup"><span data-stu-id="c4315-151">I am unable to use a particular GPO name</span></span>

-   <span data-ttu-id="c4315-152">**原因**: gpo 名が既に使われているか、gpo を一覧表示する権限がありません。</span><span class="sxs-lookup"><span data-stu-id="c4315-152">**Cause**: Either the GPO name is already in use or you lack permission to list the GPO.</span></span>

-   <span data-ttu-id="c4315-153">**解決方法**:</span><span class="sxs-lookup"><span data-stu-id="c4315-153">**Solution**:</span></span>

    -   <span data-ttu-id="c4315-154">[**コントロール**]、[**非コントロール**]、または [**保留中**] タブに GPO 名が表示される場合は、別の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4315-154">If the GPO name appears on the **Controlled**, **Uncontrolled**, or **Pending** tab, choose another name.</span></span> <span data-ttu-id="c4315-155">展開された GPO の名前が変更されているが、まだ再展開されていない場合は、ドメインの運用環境では、古い名前の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c4315-155">If a GPO that was deployed is renamed but not yet redeployed, it will be displayed under its old name in the production environment of the domain.</span></span> <span data-ttu-id="c4315-156">そのため、古い名前はまだ使用されています。</span><span class="sxs-lookup"><span data-stu-id="c4315-156">Therefore, the old name is still being used.</span></span> <span data-ttu-id="c4315-157">GPO を再展開して、運用環境での名前を更新し、別の GPO で使用するためにその名前を解放します。</span><span class="sxs-lookup"><span data-stu-id="c4315-157">Redeploy the GPO to update its name in the production environment and release that name for use by another GPO.</span></span>

    -   <span data-ttu-id="c4315-158">[**コントロール**]、[**非コントロール**]、または [**保留中**] タブに gpo 名が表示されない場合は、gpo を一覧表示するアクセス許可がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c4315-158">If the GPO name does not appear on the **Controlled**, **Uncontrolled**, or **Pending** tab, you may lack permission to list the GPO.</span></span> <span data-ttu-id="c4315-159">許可を要求するには、AGPM 管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="c4315-159">To request permission, contact an AGPM Administrator.</span></span>

### <a href="" id="bkmk-email"></a><span data-ttu-id="c4315-160">AGPM メール通知を受信できない</span><span class="sxs-lookup"><span data-stu-id="c4315-160">I am not receiving AGPM e-mail notifications</span></span>

-   <span data-ttu-id="c4315-161">**原因**: 有効な SMTP メールサーバーとメールアドレスが指定されていないか、電子メール通知を生成する操作が実行されていません。</span><span class="sxs-lookup"><span data-stu-id="c4315-161">**Cause**: A valid SMTP e-mail server and e-mail address has not been provided, or no action has been taken that generates an e-mail notification.</span></span>

-   <span data-ttu-id="c4315-162">**解決方法**:</span><span class="sxs-lookup"><span data-stu-id="c4315-162">**Solution**:</span></span>

    -   <span data-ttu-id="c4315-163">Agpm 管理者の場合: agpm によって送信される保留中のアクションに関する電子メール通知の場合、AGPM 管理者は、[**ドメイン委任**] タブで承認者の有効な SMTP メールサーバーとメールアドレスを指定する必要があります。詳細については、「[電子メールの通知を構成する](configure-e-mail-notification-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4315-163">If you are an AGPM Administrator: For e-mail notifications about pending actions to be sent by AGPM, an AGPM Administrator must provide a valid SMTP e-mail server and e-mail addresses for Approvers on the **Domain Delegation** tab. For more information, see [Configure E-Mail Notification](configure-e-mail-notification-agpm40.md).</span></span>

    -   <span data-ttu-id="c4315-164">メール通知が生成されるのは、編集者、または GPO の作成、展開、または削除に必要なアクセス許可を持っていない他のグループポリシー管理者が、いずれかのアクションの要求を送信した場合にのみ生成されます。</span><span class="sxs-lookup"><span data-stu-id="c4315-164">E-mail notifications are generated only when an Editor, Reviewer, or other Group Policy administrator who lacks the permission necessary to create, deploy, or delete a GPO submits a request for one of those actions to occur.</span></span> <span data-ttu-id="c4315-165">リクエストの承認または拒否に関する自動通知はありません。</span><span class="sxs-lookup"><span data-stu-id="c4315-165">There is no automatic notification of approval or rejection of a request.</span></span>

### <a href="" id="bkmk-port"></a><span data-ttu-id="c4315-166">AGPM サービスでポート4600を使用できない</span><span class="sxs-lookup"><span data-stu-id="c4315-166">I cannot use port 4600 for the AGPM Service</span></span>

-   <span data-ttu-id="c4315-167">**原因**: 既定では、AGPM サービスがリッスンするポートは、ポート4600です。</span><span class="sxs-lookup"><span data-stu-id="c4315-167">**Cause**: By default, the port on which the AGPM Service listens is port 4600.</span></span>

-   <span data-ttu-id="c4315-168">**解決方法**: ポート4600が agpm サービスで利用できない場合は、agpm サーバーのポート構成を別のポートを使用するように変更してから、agpm クライアントの agpm サーバー接続でポートを更新します。</span><span class="sxs-lookup"><span data-stu-id="c4315-168">**Solution**: If port 4600 is not available for the AGPM Service, modify the port configuration on the AGPM Server to use another port and then update the port in the AGPM Server connection for AGPM Clients.</span></span> <span data-ttu-id="c4315-169">詳細については、「 [AGPM サービスを変更する](modify-the-agpm-service-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4315-169">For more information, see [Modify the AGPM Service](modify-the-agpm-service-agpm40.md).</span></span>

### <a href="" id="bkmk-not-start"></a><span data-ttu-id="c4315-170">AGPM サービスは開始されません。</span><span class="sxs-lookup"><span data-stu-id="c4315-170">The AGPM Service will not start</span></span>

-   <span data-ttu-id="c4315-171">**原因**:**管理ツール**と**サービス**の下にあるオペレーティングシステムで AGPM サービスの設定を変更しました。</span><span class="sxs-lookup"><span data-stu-id="c4315-171">**Cause**: You have modified settings for the AGPM Service in the operating system under **Administrative Tools** and **Services**.</span></span>

-   <span data-ttu-id="c4315-172">**解決策**: コントロールパネルの [**プログラムと機能**] で、 **Microsoft Advanced グループポリシー管理**の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="c4315-172">**Solution**: Modify the settings for **Microsoft Advanced Group Policy Management - Server** under **Programs and Features** in Control Panel.</span></span> <span data-ttu-id="c4315-173">詳細については、「 [AGPM サービスを変更する](modify-the-agpm-service-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4315-173">For more information, see [Modify the AGPM Service](modify-the-agpm-service-agpm40.md).</span></span>

### <a href="" id="bkmk-software-installation"></a><span data-ttu-id="c4315-174">グループポリシーソフトウェアのインストールでソフトウェアのインストールに失敗する</span><span class="sxs-lookup"><span data-stu-id="c4315-174">Group Policy Software Installation fails to install software</span></span>

-   <span data-ttu-id="c4315-175">**原因**: AGPM は、グループポリシーソフトウェアインストールパッケージの整合性を維持します。</span><span class="sxs-lookup"><span data-stu-id="c4315-175">**Cause**: AGPM preserves the integrity of Group Policy Software Installation packages.</span></span> <span data-ttu-id="c4315-176">Gpo はオフラインで編集されますが、キャッシュされたクライアント情報に加えて、パッケージ間のリンクは保持されます。</span><span class="sxs-lookup"><span data-stu-id="c4315-176">Although GPOs are edited offline, links between packages in addition to cached client information are preserved.</span></span> <span data-ttu-id="c4315-177">これは仕様です。</span><span class="sxs-lookup"><span data-stu-id="c4315-177">This is by design.</span></span>

-   <span data-ttu-id="c4315-178">**解決策**: AGPM を使用してオフラインで gpo を編集する場合は、チェックアウトしたコピーではなく、展開された gpo を参照するように、別の gpo 内のパッケージのグループポリシーソフトウェアのインストールアップグレードを構成します。</span><span class="sxs-lookup"><span data-stu-id="c4315-178">**Solution**: When you edit a GPO offline with AGPM, configure any Group Policy Software Installation upgrade of a package in another GPO to reference the deployed GPO, not the checked-out copy.</span></span> <span data-ttu-id="c4315-179">エディターは、展開された GPO の**読み取り**アクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4315-179">The Editor must have **Read** permission for the deployed GPO.</span></span>

### <a href="" id="bkmk-error-on-restore"></a><span data-ttu-id="c4315-180">新しい AGPM サーバーにアーカイブを復元したときにエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="c4315-180">An error occurred when I restored the archive to a new AGPM Server</span></span>

-   <span data-ttu-id="c4315-181">**原因**: セキュリティ上の理由から、[ **Domain Delegation** ] タブで入力したパスワードを保護する暗号化によって、アーカイブが別のコンピューターに移動された場合、パスワードが失敗します。</span><span class="sxs-lookup"><span data-stu-id="c4315-181">**Cause**: For security reasons, the encryption protecting the password entered on the **Domain Delegation** tab causes the password to fail if the archive is moved to another computer.</span></span>

-   <span data-ttu-id="c4315-182">**解決策**: [ **Domain Delegation** ] タブでパスワードを再入力して確認します。詳細については、「[電子メールの通知を構成する](configure-e-mail-notification-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4315-182">**Solution**: Re-enter and confirm the password on the **Domain Delegation** tab. For more information, see [Configure E-Mail Notification](configure-e-mail-notification-agpm40.md).</span></span>

 

 





