---
title: AGPM サービスを変更する
description: AGPM サービスを変更する
author: dansimp
ms.assetid: 3239d088-bb86-4ec4-bc56-dbe8f1c710f5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: be39b170ef4cdc14c0f447bb6bd09a4ea92c82fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820497"
---
# <span data-ttu-id="9c7e3-103">AGPM サービスを変更する</span><span class="sxs-lookup"><span data-stu-id="9c7e3-103">Modify the AGPM Service</span></span>


<span data-ttu-id="9c7e3-104">AGPM サービスは、セキュリティプロキシとして機能する Windows サービスであり、ドメインのアーカイブと運用環境でのグループポリシーオブジェクト (Gpo) へのクライアントアクセスを管理します。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-104">The AGPM Service is a Windows service that acts as a security proxy, managing client access to Group Policy Objects (GPOs) in the archive and production environment of the domain.</span></span> <span data-ttu-id="9c7e3-105">このサービスを停止または無効にすると、AGPM クライアントはサーバーを通じて操作を実行できません。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-105">If this service is stopped or disabled, AGPM Clients cannot perform operations through the server.</span></span> <span data-ttu-id="9c7e3-106">アーカイブパス、AGPM サービスアカウント、AGPM サービスがリッスンするポートを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-106">You can modify the archive path, the AGPM Service Account, and the port on which the AGPM Service listens.</span></span>

<span data-ttu-id="9c7e3-107">**注意** AGPM サービスの設定は、オペレーティングシステムの**管理ツール**と**サービス**を使って変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-107">**Caution** Do not modify settings for the AGPM Service through **Administrative Tools** and **Services** in the operating system.</span></span> <span data-ttu-id="9c7e3-108">これにより、AGPM サービスが開始されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-108">Doing so can prevent the AGPM Service from starting.</span></span>

 

<span data-ttu-id="9c7e3-109">この手順を完了するには、Domain Admins グループのメンバーであり、AGPM サーバー (Microsoft Advanced Group Policy Management-Server がインストールされているコンピューター) にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-109">A user account that is a member of the Domain Admins group and has access to the AGPM Server (the computer on which Microsoft Advanced Group Policy Management - Server is installed) is required to complete this procedure.</span></span> <span data-ttu-id="9c7e3-110">さらに、この手順を完了するには、AGPM サービスアカウントの資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-110">Additionally, you must provide credentials for the AGPM Service Account to complete this procedure.</span></span>

**<span data-ttu-id="9c7e3-111">AGPM サービスを変更するには</span><span class="sxs-lookup"><span data-stu-id="9c7e3-111">To modify the AGPM Service</span></span>**

1.  <span data-ttu-id="9c7e3-112">Microsoft Advanced グループポリシー管理 (Server) がインストールされているコンピューターで、[**スタート**]、[**コントロールパネル**]、[**プログラム**]、[**プログラムと機能**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-112">On the computer on which Microsoft Advanced Group Policy Management - Server is installed, click **Start**, **Control Panel**, **Programs**, and **Programs and Features**.</span></span>

2.  <span data-ttu-id="9c7e3-113">[ **Microsoft Advanced Group Policy Management-Server**] を右クリックし、[**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-113">Right-click **Microsoft Advanced Group Policy Management - Server**, and then click **Change**.</span></span>

3.  <span data-ttu-id="9c7e3-114">[**次へ**] をクリックし、[**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-114">Click **Next**, and then click **Modify**.</span></span>

4.  <span data-ttu-id="9c7e3-115">次の手順に従って AGPM サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-115">Follow the instructions to configure the AGPM Service:</span></span>

    1.  <span data-ttu-id="9c7e3-116">[**アーカイブパス**] ダイアログボックスで、AGPM サーバーを基準としたアーカイブの新しい場所を入力するか、現在のアーカイブパスを確認して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-116">In the **Archive Path** dialog box, enter a new location for the archive relative to the AGPM Server, or confirm the current archive path, and then click **Next**.</span></span>

        <span data-ttu-id="9c7e3-117">**重要** アーカイブパスは、AGPM サーバー上のフォルダーを指すことができますが、この AGPM サーバーによって管理されるすべての Gpo と履歴データを格納するために十分な領域が必要です。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-117">**Important** The archive path can point to a folder on the AGPM Server or elsewhere, but the location should have sufficient space to store all GPOs and history data managed by this AGPM Server.</span></span>

         

    2.  <span data-ttu-id="9c7e3-118">[ **Agpm サービスアカウント**] ダイアログボックスで、agpm サービスを実行するサービスアカウントの資格情報を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-118">In the **AGPM Service Account** dialog box, enter credentials for a service account under which the AGPM Service will run, and click **Next**.</span></span>

        <span data-ttu-id="9c7e3-119">**重要** インストールを変更すると、AGPM サービスアカウントの資格情報が消去されます。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-119">**Important** Modifying the installation clears the credentials for the AGPM Service Account.</span></span> <span data-ttu-id="9c7e3-120">資格情報を再入力する必要がありますが、元のインストール時に使用された資格情報と一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-120">You must re-enter credentials, but they are not required to match the credentials used during the original installation.</span></span>

        <span data-ttu-id="9c7e3-121">AGPM サービスアカウントには、管理する Gpo へのフルアクセス権が必要であり、**サービスアクセス許可としてログオン**する権限が付与されます。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-121">The AGPM Service Account must have full access to the GPOs that it will manage and will be granted **Log On As A Service** permission.</span></span> <span data-ttu-id="9c7e3-122">1つのドメインで Gpo を管理する場合は、プライマリドメインコントローラーのローカルシステムアカウントを AGPM サービスアカウントとして設定することができます。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-122">If you will be managing GPOs on a single domain, you can make the Local System account for the primary domain controller the AGPM Service Account.</span></span>

        <span data-ttu-id="9c7e3-123">複数のドメインで Gpo を管理する場合や、メンバーサーバーが AGPM サーバーになる場合は、1つのドメインコントローラーのローカルシステムアカウントが他のドメインの Gpo にアクセスできないため、別のアカウントを AGPM サービスアカウントとして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-123">If you will be managing GPOs on multiple domains or if a member server will be the AGPM Server, you should configure a different account as the AGPM Service Account because the Local System account for one domain controller cannot access GPOs on other domains.</span></span>

         

    3.  <span data-ttu-id="9c7e3-124">[**アーカイブの所有者**] ダイアログボックスで、Agpm 管理者 (フルコントロール) または Agpm 管理者のグループのユーザー名を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-124">In the **Archive Owner** dialog box, enter the user name of an AGPM Administrator (Full Control) or group of AGPM Administrators, and click **Next**.</span></span>

        <span data-ttu-id="9c7e3-125">**注** インストールを変更すると、アーカイブの所有者の資格情報が消去されます。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-125">**Note** Modifying the installation clears the credentials for the Archive Owner.</span></span> <span data-ttu-id="9c7e3-126">資格情報を再入力する必要がありますが、元のインストール時に使用された資格情報と一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-126">You must re-enter credentials, but they are not required to match the credentials used during the original installation.</span></span>

         

    4.  <span data-ttu-id="9c7e3-127">[**ポートの構成**] ダイアログボックスで、AGPM サービスで現在選択されているポートをリッスンする、または確認する新しいポートを入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-127">In the **Port Configuration** dialog box, type a new port on which the AGPM Service should listen or confirm the port currently selected, and click **Next**.</span></span>

        <span data-ttu-id="9c7e3-128">**注** 既定では、AGPM サービスはポート4600をリッスンします。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-128">**Note** By default, the AGPM Service listens on port 4600.</span></span>

        <span data-ttu-id="9c7e3-129">ポートの例外を手動で構成する場合や、ポートの例外を構成するルールがある場合は、[**ファイアウォールにポートの例外を追加**する] チェックボックスをオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-129">If you manually configure port exceptions or have rules configuring port exceptions, you can clear the **Add port exception to firewall** check box.</span></span>

         

5.  <span data-ttu-id="9c7e3-130">[**変更**] をクリックし、インストールが完了したら [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-130">Click **Change**, and when the installation is complete click **Finish**.</span></span>

6.  <span data-ttu-id="9c7e3-131">AGPM サービスがリッスンするポートを変更した場合は、各グループポリシー管理者の AGPM サーバー接続のポートを変更します。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-131">If you have changed the port on which the AGPM Service listens, modify the port in the AGPM Server connection for each Group Policy administrator.</span></span> <span data-ttu-id="9c7e3-132">詳細については、「 [AGPM サーバー接続を構成する](configure-agpm-server-connections-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-132">(For more information, see [Configure AGPM Server Connections](configure-agpm-server-connections-agpm40.md).)</span></span>

7.  <span data-ttu-id="9c7e3-133">構成の変更を適用する各 AGPM サーバーについて、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9c7e3-133">Repeat for each AGPM Server to which the configuration changes should be applied.</span></span>

### <span data-ttu-id="9c7e3-134">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="9c7e3-134">Additional references</span></span>

-   [<span data-ttu-id="9c7e3-135">AGPM サービスの管理</span><span class="sxs-lookup"><span data-stu-id="9c7e3-135">Managing the AGPM Service</span></span>](managing-the-agpm-service-agpm40.md)

 

 





