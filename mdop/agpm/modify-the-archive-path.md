---
title: アーカイブのパスを変更する
description: アーカイブのパスを変更する
author: dansimp
ms.assetid: 6d90daf9-58db-4166-b5b3-e84bb261164a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1fc6ba2bf415d3d1bc67144d0dec1030c6173026
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820494"
---
# <span data-ttu-id="69135-103">アーカイブのパスを変更する</span><span class="sxs-lookup"><span data-stu-id="69135-103">Modify the Archive Path</span></span>


<span data-ttu-id="69135-104">アーカイブパスは、AGPM サーバーとの相対的なアーカイブの場所です。</span><span class="sxs-lookup"><span data-stu-id="69135-104">The archive path is the location of the archive relative to the AGPM Server.</span></span> <span data-ttu-id="69135-105">アーカイブパスは、AGPM サーバー上のフォルダーまたは同じフォレスト内の別のサーバー上のフォルダーを指すことができます。</span><span class="sxs-lookup"><span data-stu-id="69135-105">The archive path can point to a folder on the AGPM Server or on another server in the same forest.</span></span>

<span data-ttu-id="69135-106">アーカイブパスと AGPM サービスアカウントは、AGPM サーバーのインストール中に構成されます。また、AGPM サーバー上の**プログラムの追加と削除**を通じて、後から変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="69135-106">The archive path and AGPM Service Account are configured during the installation of AGPM Server and can be changed afterward through **Add or Remove Programs** on the AGPM Server.</span></span>

<span data-ttu-id="69135-107">この手順を完了するには、Domain Admins グループのメンバーであり、AGPM サーバー (Microsoft Advanced Group Policy Management-Server がインストールされているコンピューター) にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="69135-107">A user account that is a member of the Domain Admins group and has access to the AGPM Server (the computer on which Microsoft Advanced Group Policy Management - Server is installed) is required to complete this procedure.</span></span>

**<span data-ttu-id="69135-108">アーカイブパスを変更するには</span><span class="sxs-lookup"><span data-stu-id="69135-108">To modify the archive path</span></span>**

1.  <span data-ttu-id="69135-109">Microsoft Advanced グループポリシー管理 (Server) がインストールされているコンピューターで、[**スタート**] をクリックし、[**コントロールパネル**] をクリックして、[**プログラムの追加と削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69135-109">On the computer on which Microsoft Advanced Group Policy Management - Server is installed, click **Start**, click **Control Panel**, click **Add or Remove Programs**.</span></span>

2.  <span data-ttu-id="69135-110">[ **Microsoft Advanced Group Policy Management-Server**] をクリックし、[**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69135-110">Click **Microsoft Advanced Group Policy Management - Server**, and then click **Change**.</span></span>

3.  <span data-ttu-id="69135-111">[**次へ**] をクリックし、[**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69135-111">Click **Next**, and then click **Modify**.</span></span>

4.  <span data-ttu-id="69135-112">画面の指示に従って、AGPM サービスの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="69135-112">Follow the instructions on screen to configure settings for the AGPM Service:</span></span>

    1.  <span data-ttu-id="69135-113">[アーカイブパス] には、AGPM サーバーを基準としたアーカイブの新しい場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="69135-113">For the archive path, enter a new location for the archive relative to the AGPM Server.</span></span> <span data-ttu-id="69135-114">アーカイブパスは、AGPM サーバー上のフォルダーを指すことができますが、この AGPM サーバーによって管理されるすべての Gpo と履歴データを格納するために十分な領域が必要です。</span><span class="sxs-lookup"><span data-stu-id="69135-114">The archive path can point to a folder on the AGPM Server or elsewhere, but the location should have sufficient space to store all GPOs and history data managed by this AGPM Server.</span></span>

    2.  <span data-ttu-id="69135-115">AGPM サービスアカウントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="69135-115">Enter credentials for the AGPM Service Account.</span></span>

        <span data-ttu-id="69135-116">**重要** インストールを変更すると、AGPM サービスアカウントの資格情報が消去されます。</span><span class="sxs-lookup"><span data-stu-id="69135-116">**Important** Modifying the installation clears the credentials for the AGPM Service Account.</span></span> <span data-ttu-id="69135-117">資格情報を再入力する必要がありますが、元のインストール時に使用された資格情報と一致する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="69135-117">You must re-enter credentials, but they are not required to match the credentials used during the original installation.</span></span>

        <span data-ttu-id="69135-118">AGPM サービスアカウントには、管理する Gpo へのフルアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="69135-118">The AGPM Service Account must have full access to the GPOs that it will manage.</span></span> <span data-ttu-id="69135-119">1つのドメインで Gpo を管理する場合は、プライマリドメインコントローラーのローカルシステムアカウントを AGPM サービスアカウントとして設定することができます。</span><span class="sxs-lookup"><span data-stu-id="69135-119">If you will be managing GPOs on a single domain, you can make the Local System account for the primary domain controller the AGPM Service Account.</span></span>

        <span data-ttu-id="69135-120">複数のドメインで Gpo を管理する場合や、メンバーサーバーが AGPM サーバーになる場合は、1つのドメインコントローラーのローカルシステムアカウントが他のドメインの Gpo にアクセスできないため、別のアカウントを AGPM サービスアカウントとして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69135-120">If you will be managing GPOs on multiple domains or if a member server will be the AGPM Server, you should configure a different account as the AGPM Service Account because the Local System account for one domain controller cannot access GPOs on other domains.</span></span>

         

    3.  <span data-ttu-id="69135-121">アーカイブの所有者の場合は、AGPM 管理者の資格情報 (フルコントロール) を入力します。</span><span class="sxs-lookup"><span data-stu-id="69135-121">For the archive owner, enter the credentials of an AGPM Administrator (Full Control).</span></span>

5.  <span data-ttu-id="69135-122">[**変更**] をクリックし、インストールが完了したら [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69135-122">Click **Change**, and when the installation is complete click **Finish**.</span></span>

### <span data-ttu-id="69135-123">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="69135-123">Additional references</span></span>

-   [<span data-ttu-id="69135-124">AGPM サービスの管理</span><span class="sxs-lookup"><span data-stu-id="69135-124">Managing the AGPM Service</span></span>](managing-the-agpm-service.md)

 

 





