---
title: 高度なグループ ポリシーの管理のトラブルシューティング
description: 高度なグループ ポリシーの管理のトラブルシューティング
author: dansimp
ms.assetid: f58849cf-6c5b-44d8-b356-0ed7a5b24cee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c22b9a0983b26252ee0d9c8d99b63cd4ab5dc2b6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818254"
---
# <span data-ttu-id="f26da-103">高度なグループ ポリシーの管理のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f26da-103">Troubleshooting Advanced Group Policy Management</span></span>


<span data-ttu-id="f26da-104">このセクションでは、高度なグループポリシー管理 (AGPM) を使用してグループポリシーオブジェクト (Gpo) を管理するときに発生する可能性がある一般的な問題をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="f26da-104">This section lists a few common issues you may encounter when using Advanced Group Policy Management (AGPM) to manage Group Policy objects (GPOs).</span></span>

## <span data-ttu-id="f26da-105">どのような問題が発生していますか?</span><span class="sxs-lookup"><span data-stu-id="f26da-105">What problems are you having?</span></span>


-   [<span data-ttu-id="f26da-106">アーカイブにアクセスできません</span><span class="sxs-lookup"><span data-stu-id="f26da-106">I am unable to access an archive</span></span>](#bkmk-access-an-archive)

-   [<span data-ttu-id="f26da-107">GPO の状態は、グループポリシーの管理者によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f26da-107">The GPO state varies for different Group Policy administrators</span></span>](#bkmk-state-varies)

-   [<span data-ttu-id="f26da-108">AGPM サーバー接続を変更できません</span><span class="sxs-lookup"><span data-stu-id="f26da-108">I am unable to modify the AGPM Server connection</span></span>](#bkmk-modify-archive-location)

-   [<span data-ttu-id="f26da-109">既定のテンプレートを変更できない、または Gpo の表示、作成、編集、名前の変更、展開、または削除を行うことができない</span><span class="sxs-lookup"><span data-stu-id="f26da-109">I am unable to change the default template or view, create, edit, rename, deploy, or delete GPOs</span></span>](#bkmk-perform-task)

-   [<span data-ttu-id="f26da-110">特定の GPO 名を使用できない</span><span class="sxs-lookup"><span data-stu-id="f26da-110">I am unable to use a particular GPO name</span></span>](#bkmk-use-particular-name)

-   [<span data-ttu-id="f26da-111">AGPM メール通知を受信できない</span><span class="sxs-lookup"><span data-stu-id="f26da-111">I am not receiving AGPM e-mail notifications</span></span>](#bkmk-email)

-   [<span data-ttu-id="f26da-112">AGPM サービスでポート4600を使用できない</span><span class="sxs-lookup"><span data-stu-id="f26da-112">I cannot use port 4600 for the AGPM Service</span></span>](#bkmk-port)

-   [<span data-ttu-id="f26da-113">AGPM サービスは開始されません。</span><span class="sxs-lookup"><span data-stu-id="f26da-113">The AGPM Service will not start</span></span>](#bkmk-not-start)

-   [<span data-ttu-id="f26da-114">グループポリシーソフトウェアのインストールでソフトウェアのインストールに失敗する</span><span class="sxs-lookup"><span data-stu-id="f26da-114">Group Policy Software Installation fails to install software</span></span>](#bkmk-software-installation)

### <a href="" id="bkmk-access-an-archive"></a><span data-ttu-id="f26da-115">アーカイブにアクセスできません</span><span class="sxs-lookup"><span data-stu-id="f26da-115">I am unable to access an archive</span></span>

-   <span data-ttu-id="f26da-116">**原因**: アーカイブ用の正しいサーバーとポートを選択していません。</span><span class="sxs-lookup"><span data-stu-id="f26da-116">**Cause**: You have not selected the correct server and port for the archive.</span></span>

-   <span data-ttu-id="f26da-117">**解決方法**:</span><span class="sxs-lookup"><span data-stu-id="f26da-117">**Solution**:</span></span>

    -   <span data-ttu-id="f26da-118">AGPM 管理者の場合: 「 [Agpm サーバー接続を構成](configure-the-agpm-server-connection.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f26da-118">If you are an AGPM Administrator: See [Configure the AGPM Server Connection](configure-the-agpm-server-connection.md).</span></span>

    -   <span data-ttu-id="f26da-119">AGPM 管理者ではない場合: agpm 管理者からの AGPM サーバーの接続の詳細を要求します。</span><span class="sxs-lookup"><span data-stu-id="f26da-119">If you are not an AGPM Administrator: Request connection details for the AGPM Server from an AGPM Administrator.</span></span> <span data-ttu-id="f26da-120">「 [AGPM サーバー接続を構成する](configure-the-agpm-server-connection-reviewer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f26da-120">See [Configure the AGPM Server Connection](configure-the-agpm-server-connection-reviewer.md).</span></span>

-   <span data-ttu-id="f26da-121">**原因**: 高度なグループポリシー管理サービスが実行されていません。</span><span class="sxs-lookup"><span data-stu-id="f26da-121">**Cause**: The Advanced Group Policy Management Service is not running.</span></span>

-   <span data-ttu-id="f26da-122">**解決方法**:</span><span class="sxs-lookup"><span data-stu-id="f26da-122">**Solution**:</span></span>

    -   <span data-ttu-id="f26da-123">AGPM 管理者の場合: AGPM サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="f26da-123">If you are an AGPM Administrator: Start the AGPM Service.</span></span> <span data-ttu-id="f26da-124">詳細については、「 [AGPM サービスの開始と停止](start-and-stop-the-agpm-service.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f26da-124">For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service.md).</span></span>

    -   <span data-ttu-id="f26da-125">AGPM 管理者ではない場合: AGPM 管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="f26da-125">If you are not an AGPM Administrator: Contact an AGPM Administrator for assistance.</span></span>

### <a href="" id="bkmk-state-varies"></a><span data-ttu-id="f26da-126">GPO の状態は、グループポリシーの管理者によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f26da-126">The GPO state varies for different Group Policy administrators</span></span>

-   <span data-ttu-id="f26da-127">**原因**: グループポリシーの管理者が、同じアーカイブに対して異なる AGPM サーバーを選択しています。</span><span class="sxs-lookup"><span data-stu-id="f26da-127">**Cause**: Different Group Policy administrators have selected different AGPM Servers for the same archive.</span></span>

-   <span data-ttu-id="f26da-128">**解決方法**:</span><span class="sxs-lookup"><span data-stu-id="f26da-128">**Solution**:</span></span>

    -   <span data-ttu-id="f26da-129">AGPM 管理者の場合: 「 [Agpm サーバー接続を構成](configure-the-agpm-server-connection.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f26da-129">If you are an AGPM Administrator: See [Configure the AGPM Server Connection](configure-the-agpm-server-connection.md).</span></span>

    -   <span data-ttu-id="f26da-130">AGPM 管理者ではない場合: agpm 管理者からの AGPM サーバーの接続の詳細を要求します。</span><span class="sxs-lookup"><span data-stu-id="f26da-130">If you are not an AGPM Administrator: Request connection details for the AGPM Server from an AGPM Administrator.</span></span> <span data-ttu-id="f26da-131">「 [AGPM サーバー接続を構成する](configure-the-agpm-server-connection-reviewer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f26da-131">See [Configure the AGPM Server Connection](configure-the-agpm-server-connection-reviewer.md).</span></span>

### <a href="" id="bkmk-modify-archive-location"></a><span data-ttu-id="f26da-132">AGPM サーバー接続を変更できません</span><span class="sxs-lookup"><span data-stu-id="f26da-132">I am unable to modify the AGPM Server connection</span></span>

-   <span data-ttu-id="f26da-133">**原因**: [ **AGPM サーバー** ] タブの設定が利用できない場合、Agpm サーバーは管理用テンプレートを使用して一元的に構成されています。</span><span class="sxs-lookup"><span data-stu-id="f26da-133">**Cause**: If the settings on the **AGPM Server** tab are unavailable, the AGPM Server has been centrally configured using an Administrative template.</span></span>

-   <span data-ttu-id="f26da-134">**解決方法**:</span><span class="sxs-lookup"><span data-stu-id="f26da-134">**Solution**:</span></span>

    -   <span data-ttu-id="f26da-135">AGPM 管理者の場合: [ **Agpm サーバー** ] タブの設定を使用できない場合は、「 [agpm サーバー接続を構成する](configure-the-agpm-server-connection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f26da-135">If you are an AGPM Administrator: If the settings on the **AGPM Server** tab are unavailable, see [Configure the AGPM Server Connection](configure-the-agpm-server-connection.md).</span></span>

    -   <span data-ttu-id="f26da-136">AGPM 管理者ではない場合: [ **Agpm サーバー** ] タブの設定を使用できない場合は、agpm サーバーを変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f26da-136">If you are not an AGPM Administrator: If the settings on the **AGPM Server** tab are unavailable, you do not need to modify the AGPM Server.</span></span>

### <a href="" id="bkmk-perform-task"></a><span data-ttu-id="f26da-137">既定のテンプレートを変更できない、または Gpo の表示、作成、編集、名前の変更、展開、または削除を行うことができない</span><span class="sxs-lookup"><span data-stu-id="f26da-137">I am unable to change the default template or view, create, edit, rename, deploy, or delete GPOs</span></span>

-   <span data-ttu-id="f26da-138">**原因**: タスクを実行するのに必要な権限を持つ役割が割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="f26da-138">**Cause**: You have not been assigned a role with the permissions required to perform the task or tasks.</span></span>

-   <span data-ttu-id="f26da-139">**解決方法**:</span><span class="sxs-lookup"><span data-stu-id="f26da-139">**Solution**:</span></span>

    -   <span data-ttu-id="f26da-140">AGPM 管理者の場合: 「[ドメインレベルのアクセスを委任](delegate-domain-level-access.md)する」と「[個々の GPO へのアクセスを委任する」を](delegate-access-to-an-individual-gpo.md)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f26da-140">If you are an AGPM Administrator: See [Delegate Domain-Level Access](delegate-domain-level-access.md) and [Delegate Access to an Individual GPO](delegate-access-to-an-individual-gpo.md).</span></span> <span data-ttu-id="f26da-141">AGPM 権限は、現在アーカイブ内のすべての Gpo にドメインから伝播されます。</span><span class="sxs-lookup"><span data-stu-id="f26da-141">AGPM permissions will cascade from the domain to all GPOs currently in the archive.</span></span> <span data-ttu-id="f26da-142">新しいグループポリシー管理者は、ドメインレベルで追加されるため、そのアクセス許可は、**このオブジェクトと入れ子になったオブジェクト**に適用されるように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f26da-142">As new Group Policy administrators are added at the domain level, their permissions must be set to apply to **This object and nested objects**.</span></span> <span data-ttu-id="f26da-143">タスクを実行できるロールと、タスクを実行するために必要な権限の詳細については、そのタスクのヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f26da-143">For details about which roles can perform a task and what permissions are necessary to perform a task, refer to the help for that task.</span></span>

    -   <span data-ttu-id="f26da-144">AGPM 管理者ではない場合に、追加の役割または権限が必要な場合は、AGPM 管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="f26da-144">If you are not an AGPM Administrator and you require additional roles or permissions: Contact an AGPM Administrator for assistance.</span></span> <span data-ttu-id="f26da-145">エディターを使用している場合は、GPO の作成、GPO の展開、または本番環境からの GPO の削除のプロセスを開始できますが、承認者または AGPM 管理者が要求を承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f26da-145">Note that if you are an Editor, you can begin the process of creating a GPO, deploying a GPO, or deleting a GPO from the production environment, but an Approver or AGPM Administrator must approve your request.</span></span>

### <a href="" id="bkmk-use-particular-name"></a><span data-ttu-id="f26da-146">特定の GPO 名を使用できない</span><span class="sxs-lookup"><span data-stu-id="f26da-146">I am unable to use a particular GPO name</span></span>

-   <span data-ttu-id="f26da-147">**原因**: gpo 名が既に使われているか、gpo を一覧表示する権限がありません。</span><span class="sxs-lookup"><span data-stu-id="f26da-147">**Cause**: Either the GPO name is already in use or you lack permission to list the GPO.</span></span>

-   <span data-ttu-id="f26da-148">**解決方法**:</span><span class="sxs-lookup"><span data-stu-id="f26da-148">**Solution**:</span></span>

    -   <span data-ttu-id="f26da-149">[**コントロール**]、[**非コントロール**]、または [**保留中**] タブに GPO 名が表示される場合は、別の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="f26da-149">If the GPO name appears on the **Controlled**, **Uncontrolled**, or **Pending** tab, choose another name.</span></span> <span data-ttu-id="f26da-150">展開されている GPO の名前が変更されているが、まだ再配置されていない場合は、その名前は運用環境での古い名前の下に表示されます。そのため、古い名前はまだ使用されています。</span><span class="sxs-lookup"><span data-stu-id="f26da-150">If a GPO that has been deployed is renamed but not yet redeployed, it will be displayed under its old name in the production environment—therefore, the old name is still in use.</span></span> <span data-ttu-id="f26da-151">GPO を再展開して、運用環境での名前を更新し、別の GPO で使用するためにその名前を解放します。</span><span class="sxs-lookup"><span data-stu-id="f26da-151">Redeploy the GPO to update its name in the production environment and release that name for use by another GPO.</span></span>

    -   <span data-ttu-id="f26da-152">[**コントロール**]、[**非コントロール**]、または [**保留中**] タブに gpo 名が表示されない場合は、gpo を一覧表示するアクセス許可がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f26da-152">If the GPO name does not appear on the **Controlled**, **Uncontrolled**, or **Pending** tab, you may lack permission to list the GPO.</span></span> <span data-ttu-id="f26da-153">許可を要求するには、AGPM 管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="f26da-153">To request permission, contact an AGPM Administrator.</span></span>

### <a href="" id="bkmk-email"></a><span data-ttu-id="f26da-154">AGPM メール通知を受信できない</span><span class="sxs-lookup"><span data-stu-id="f26da-154">I am not receiving AGPM e-mail notifications</span></span>

-   <span data-ttu-id="f26da-155">**原因**: 有効な SMTP メールサーバーとメールアドレスが指定されていないか、電子メール通知を生成する操作が実行されていません。</span><span class="sxs-lookup"><span data-stu-id="f26da-155">**Cause**: A valid SMTP e-mail server and e-mail address has not been provided, or no action has been taken that generates an e-mail notification.</span></span>

-   <span data-ttu-id="f26da-156">**解決方法**:</span><span class="sxs-lookup"><span data-stu-id="f26da-156">**Solution**:</span></span>

    -   <span data-ttu-id="f26da-157">Agpm 管理者の場合: agpm によって送信される保留中のアクションに関する電子メール通知の場合、AGPM 管理者は、[**ドメイン委任**] タブで承認者の有効な SMTP メールサーバーとメールアドレスを指定する必要があります。詳細については、「[電子メールの通知を構成する](configure-e-mail-notification.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f26da-157">If you are an AGPM Administrator: For e-mail notifications about pending actions to be sent by AGPM, an AGPM Administrator must provide a valid SMTP e-mail server and e-mail addresses for Approvers on the **Domain Delegation** tab. For more information, see [Configure E-Mail Notification](configure-e-mail-notification.md).</span></span>

    -   <span data-ttu-id="f26da-158">メール通知が生成されるのは、編集者、または GPO の作成、展開、または削除に必要なアクセス許可を持っていない他のグループポリシー管理者が、いずれかのアクションの要求を送信した場合にのみ生成されます。</span><span class="sxs-lookup"><span data-stu-id="f26da-158">E-mail notifications are generated only when an Editor, Reviewer, or other Group Policy administrator who lacks the permission necessary to create, deploy, or delete a GPO submits a request for one of those actions to occur.</span></span> <span data-ttu-id="f26da-159">リクエストの承認または拒否に関する自動通知はありません。</span><span class="sxs-lookup"><span data-stu-id="f26da-159">There is no automatic notification of approval or rejection of a request.</span></span>

### <a href="" id="bkmk-port"></a><span data-ttu-id="f26da-160">AGPM サービスでポート4600を使用できない</span><span class="sxs-lookup"><span data-stu-id="f26da-160">I cannot use port 4600 for the AGPM Service</span></span>

-   <span data-ttu-id="f26da-161">**原因**: 既定では、AGPM サービスがリッスンするポートは、ポート4600です。</span><span class="sxs-lookup"><span data-stu-id="f26da-161">**Cause**: By default, the port on which the AGPM Service listens is port 4600.</span></span>

-   <span data-ttu-id="f26da-162">**解決方法**: ポート4600が AGPM サービスで利用できない場合は、別のポートを使用するように各アーカイブインデックスファイルを変更し、すべてのグループポリシー管理者の AGPM サーバーを更新します。</span><span class="sxs-lookup"><span data-stu-id="f26da-162">**Solution**: If port 4600 is not available for the AGPM Service, modify each archive index file to use another port and then update the AGPM Server for all Group Policy administrators.</span></span> <span data-ttu-id="f26da-163">詳細については、「 [AGPM サービスがリッスンするポートの変更](modify-the-port-on-which-the-agpm-service-listens.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f26da-163">For more information, see [Modify the Port on Which the AGPM Service Listens](modify-the-port-on-which-the-agpm-service-listens.md).</span></span>

### <a href="" id="bkmk-not-start"></a><span data-ttu-id="f26da-164">AGPM サービスは開始されません。</span><span class="sxs-lookup"><span data-stu-id="f26da-164">The AGPM Service will not start</span></span>

-   <span data-ttu-id="f26da-165">**原因**:**管理ツール**と**サービス**の下にあるオペレーティングシステムで AGPM サービスの設定を変更しました。</span><span class="sxs-lookup"><span data-stu-id="f26da-165">**Cause**: You have modified settings for the AGPM Service in the operating system under **Administrative Tools** and **Services**.</span></span>

-   <span data-ttu-id="f26da-166">**解決策**: [**プログラムの追加と削除**] の下にある**Microsoft Advanced グループポリシー管理**の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="f26da-166">**Solution**: Modify the settings for **Microsoft Advanced Group Policy Management - Server** under **Add or Remove Programs**.</span></span> <span data-ttu-id="f26da-167">詳細については、「 [AGPM サービスアカウントを変更](modify-the-agpm-service-account.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f26da-167">For more information, see [Modify the AGPM Service Account](modify-the-agpm-service-account.md).</span></span>

### <a href="" id="bkmk-software-installation"></a><span data-ttu-id="f26da-168">グループポリシーソフトウェアのインストールでソフトウェアのインストールに失敗する</span><span class="sxs-lookup"><span data-stu-id="f26da-168">Group Policy Software Installation fails to install software</span></span>

-   <span data-ttu-id="f26da-169">**原因**: AGPM は、グループポリシーソフトウェアインストールパッケージの整合性を維持します。</span><span class="sxs-lookup"><span data-stu-id="f26da-169">**Cause**: AGPM preserves the integrity of Group Policy Software Installation packages.</span></span> <span data-ttu-id="f26da-170">Gpo はオフラインで編集されますが、パッケージとキャッシュされたクライアント情報の間のリンクは保持されます。</span><span class="sxs-lookup"><span data-stu-id="f26da-170">Although GPOs are edited offline, links between packages as well as cached client information are preserved.</span></span> <span data-ttu-id="f26da-171">これは仕様です。</span><span class="sxs-lookup"><span data-stu-id="f26da-171">This is by design.</span></span>

-   <span data-ttu-id="f26da-172">**解決策**: AGPM を使って GPO をオフラインで編集する場合は、チェックアウトしたコピーではなく、展開された gpo を参照するように、別の gpo 内のパッケージのグループポリシーソフトウェアのインストールアップグレードを構成します。</span><span class="sxs-lookup"><span data-stu-id="f26da-172">**Solution**: When editing a GPO offline with AGPM, configure any Group Policy Software Installation upgrade of a package in another GPO to reference the deployed GPO, not the checked-out copy.</span></span> <span data-ttu-id="f26da-173">エディターは、展開された GPO の**読み取り**アクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f26da-173">The Editor must have **Read** permission for the deployed GPO.</span></span>

 

 





