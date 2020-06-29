---
title: AGPM サーバーとアーカイブを移動する
description: AGPM サーバーとアーカイブを移動する
author: dansimp
ms.assetid: 9ec48d3a-c293-45f0-8939-32ccdc062303
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 61ad2eb6e0ea46eef89379894a99469254e0fd5e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822534"
---
# <span data-ttu-id="8663b-103">AGPM サーバーとアーカイブを移動する</span><span class="sxs-lookup"><span data-stu-id="8663b-103">Move the AGPM Server and the Archive</span></span>


<span data-ttu-id="8663b-104">AGPM サーバーとアーカイブがホストされているサーバーを置き換える場合は、AGPM サービスとアーカイブを移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8663b-104">If you are replacing the AGPM Server and the server on which the archive is hosted, you must move the AGPM Service and the archive.</span></span> <span data-ttu-id="8663b-105">必要に応じて、AGPM サービスとアーカイブを個別に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="8663b-105">If you prefer, you can move the AGPM Service and the archive separately.</span></span>

**<span data-ttu-id="8663b-106">注</span><span class="sxs-lookup"><span data-stu-id="8663b-106">Note</span></span>**  
-   <span data-ttu-id="8663b-107">AGPM サーバーは、AGPM サービスと Microsoft Advanced Group Policy Management – Server がインストールされているコンピューターをホストするコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="8663b-107">The AGPM Server is the computer that hosts the AGPM Service and the computer on which Microsoft Advanced Group Policy Management – Server is installed.</span></span>

-   <span data-ttu-id="8663b-108">既定では、アーカイブは AGPM サーバー上でホストされますが、代わりに別のサーバーでホストするためのアーカイブパスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8663b-108">By default, the archive is hosted on the AGPM Server, but you can specify an archive path to host it on another server instead.</span></span>

 

<span data-ttu-id="8663b-109">この手順を完了するには、Domain Admins グループのメンバーで、前の AGPM サーバーにアクセスできるユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="8663b-109">A user account that is a member of the Domain Admins group and has access to the previous and new AGPM Servers is required to complete this procedure.</span></span> <span data-ttu-id="8663b-110">さらに、この手順を完了するために、新しい AGPM サーバーで使用される AGPM サービスアカウントの資格情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8663b-110">Additionally, you must provide credentials for the AGPM Service Account to be used by the new AGPM Server to complete this procedure.</span></span>

**<span data-ttu-id="8663b-111">AGPM サービスとアーカイブを別のサーバーまたはサーバーに移動するには</span><span class="sxs-lookup"><span data-stu-id="8663b-111">To move the AGPM Service and the archive to a different server or servers</span></span>**

1.  <span data-ttu-id="8663b-112">アーカイブをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="8663b-112">Back up the archive.</span></span> <span data-ttu-id="8663b-113">詳細については、「[アーカイブのバックアップを作成](back-up-the-archive-agpm40.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8663b-113">For more information, see [Back Up the Archive](back-up-the-archive-agpm40.md).</span></span>

2.  <span data-ttu-id="8663b-114">AGPM サービスを移動します。</span><span class="sxs-lookup"><span data-stu-id="8663b-114">Move the AGPM Service:</span></span>

    1.  <span data-ttu-id="8663b-115">AGPM サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="8663b-115">Stop the AGPM Service.</span></span> <span data-ttu-id="8663b-116">詳細については、「 [AGPM サービスの開始と停止](start-and-stop-the-agpm-service-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8663b-116">For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service-agpm40.md).</span></span>

    2.  <span data-ttu-id="8663b-117">AGPM サービスをホストする新しいサーバーに Microsoft Advanced グループポリシー管理-Server をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8663b-117">Install Microsoft Advanced Group Policy Management - Server on the new server that will host the AGPM Service.</span></span> <span data-ttu-id="8663b-118">このプロセスでは、AGPM サーバーに対して、アーカイブの場所として新しいアーカイブパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="8663b-118">During this process, you specify the new archive path, the location for the archive in relation to the AGPM Server.</span></span> <span data-ttu-id="8663b-119">詳細については、「 [Microsoft Advanced グループポリシー管理4.0 のステップバイステップガイド](https://go.microsoft.com/fwlink/?LinkId=153505)」 https://go.microsoft.com/fwlink/?LinkId=153505) ( [microsoft advanced group policy](https://go.microsoft.com/fwlink/?LinkId=156883) Management () の計画ガイド () を参照してください https://go.microsoft.com/fwlink/?LinkId=156883) 。</span><span class="sxs-lookup"><span data-stu-id="8663b-119">For more information, see [Step-by-Step Guide for Microsoft Advanced Group Policy Management 4.0](https://go.microsoft.com/fwlink/?LinkId=153505) (https://go.microsoft.com/fwlink/?LinkId=153505) and [Planning Guide for Microsoft Advanced Group Policy Management](https://go.microsoft.com/fwlink/?LinkId=156883) (https://go.microsoft.com/fwlink/?LinkId=156883).</span></span>

    3.  <span data-ttu-id="8663b-120">AGPM 管理者 (フルコントロール) は、新しい AGPM サーバーを使用するすべてのグループポリシー管理者に対して AGPM サーバー接続を構成し、古い AGPM サーバーへの接続を削除する必要があります。それ以外の場合、各グループポリシー管理者は、新しい AGPM サーバー接続を手動で構成し、コンピューター上の AGPM スナップインの古い AGPM サーバー接続を削除</span><span class="sxs-lookup"><span data-stu-id="8663b-120">Either an AGPM Administrator (Full Control) must configure the AGPM Server connection for all Group Policy administrators who will use the new AGPM Server and remove the connection for the old AGPM Server, or else each Group Policy administrator must manually configure the new AGPM Server connection and remove the old AGPM Server connection for the AGPM snap-in on their computer.</span></span> <span data-ttu-id="8663b-121">詳細については、「 [AGPM サーバー接続を構成する](configure-agpm-server-connections-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8663b-121">For more information, see [Configure AGPM Server Connections](configure-agpm-server-connections-agpm40.md).</span></span>

        <span data-ttu-id="8663b-122">**注** ベストプラクティスとして、前の AGPM サーバーから Microsoft Advanced グループポリシー管理– Server をアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8663b-122">**Note** As a best practice, you should uninstall Microsoft Advanced Group Policy Management – Server from the previous AGPM Server.</span></span> <span data-ttu-id="8663b-123">これにより、サーバー上で AGPM サービスが意図せずに再起動されることはなくなり、AGPM サーバーとの接続が残っている場合は混乱を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8663b-123">This will ensure that the AGPM Service cannot be unintentionally restarted on that server and potentially cause confusion if any AGPM Server connections to it remain.</span></span>

         

3.  <span data-ttu-id="8663b-124">アーカイブをホストする新しいサーバーにバックアップからアーカイブをコピーします。</span><span class="sxs-lookup"><span data-stu-id="8663b-124">Copy the archive from the backup to the new server that will host the archive.</span></span> <span data-ttu-id="8663b-125">詳細については、「[バックアップからアーカイブを復元する](restore-the-archive-from-a-backup-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8663b-125">For more information, see [Restore the Archive from a Backup](restore-the-archive-from-a-backup-agpm40.md).</span></span>

    <span data-ttu-id="8663b-126">**重要** AGPM サービスを同時に移行せずに、アーカイブを移動した場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8663b-126">**Important** If you moved the archive without moving the AGPM Service at the same time:</span></span>

    1.  <span data-ttu-id="8663b-127">AGPM サーバーに関連するアーカイブの新しい場所を指すようにアーカイブパスを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8663b-127">You must change the archive path to point to the new location for the archive in relation to the AGPM Server.</span></span> <span data-ttu-id="8663b-128">詳細については、「 [AGPM サービスを変更する](modify-the-agpm-service-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8663b-128">For more information, see [Modify the AGPM Service](modify-the-agpm-service-agpm40.md).</span></span>

    2.  <span data-ttu-id="8663b-129">[ **Domain Delegation** ] タブでパスワードを再入力して確認する必要があります。詳細については、「[電子メールの通知を構成する](configure-e-mail-notification-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8663b-129">You must re-enter and confirm the password on the **Domain Delegation** tab. For more information, see [Configure E-Mail Notification](configure-e-mail-notification-agpm40.md).</span></span>

     

### <span data-ttu-id="8663b-130">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="8663b-130">Additional references</span></span>

-   [<span data-ttu-id="8663b-131">アーカイブをバックアップする</span><span class="sxs-lookup"><span data-stu-id="8663b-131">Back Up the Archive</span></span>](back-up-the-archive-agpm40.md)

-   [<span data-ttu-id="8663b-132">バックアップからアーカイブを復元する</span><span class="sxs-lookup"><span data-stu-id="8663b-132">Restore the Archive from a Backup</span></span>](restore-the-archive-from-a-backup-agpm40.md)

-   [<span data-ttu-id="8663b-133">AGPM サーバー接続を構成する</span><span class="sxs-lookup"><span data-stu-id="8663b-133">Configure AGPM Server Connections</span></span>](configure-agpm-server-connections-agpm40.md)

-   [<span data-ttu-id="8663b-134">AGPM サービスを変更する</span><span class="sxs-lookup"><span data-stu-id="8663b-134">Modify the AGPM Service</span></span>](modify-the-agpm-service-agpm40.md)

-   <span data-ttu-id="8663b-135">[Microsoft Advanced グループポリシー管理4.0 のステップバイステップガイド](https://go.microsoft.com/fwlink/?LinkId=153505)(https://go.microsoft.com/fwlink/?LinkId=153505)</span><span class="sxs-lookup"><span data-stu-id="8663b-135">[Step-by-Step Guide for Microsoft Advanced Group Policy Management 4.0](https://go.microsoft.com/fwlink/?LinkId=153505) (https://go.microsoft.com/fwlink/?LinkId=153505)</span></span>

-   <span data-ttu-id="8663b-136">[Microsoft Advanced グループポリシー管理の計画ガイド](https://go.microsoft.com/fwlink/?LinkId=156883)(https://go.microsoft.com/fwlink/?LinkId=156883)</span><span class="sxs-lookup"><span data-stu-id="8663b-136">[Planning Guide for Microsoft Advanced Group Policy Management](https://go.microsoft.com/fwlink/?LinkId=156883) (https://go.microsoft.com/fwlink/?LinkId=156883)</span></span>

-   [<span data-ttu-id="8663b-137">AGPM 管理者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="8663b-137">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks-agpm40.md)

 

 




