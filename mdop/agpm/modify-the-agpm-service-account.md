---
title: AGPM サービス アカウントを変更する
description: AGPM サービス アカウントを変更する
author: dansimp
ms.assetid: 0d8d8c7b-f299-4fee-8414-406492156942
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0672ceed2fba17060e17d2ffcfa264da458b9897
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820524"
---
# <span data-ttu-id="3410c-103">AGPM サービス アカウントを変更する</span><span class="sxs-lookup"><span data-stu-id="3410c-103">Modify the AGPM Service Account</span></span>


<span data-ttu-id="3410c-104">AGPM サービスは、セキュリティプロキシとして機能する Windows サービスであり、アーカイブと運用環境でのグループポリシーオブジェクト (Gpo) へのクライアントアクセスを管理します。</span><span class="sxs-lookup"><span data-stu-id="3410c-104">The AGPM Service is a Windows service that acts as a security proxy, managing client access to Group Policy objects (GPOs) in the archive and production environment.</span></span> <span data-ttu-id="3410c-105">このサービスを停止または無効にすると、AGPM クライアントはサーバーを通じて操作を実行できません。</span><span class="sxs-lookup"><span data-stu-id="3410c-105">If this service is stopped or disabled, AGPM clients cannot perform operations through the server.</span></span>

<span data-ttu-id="3410c-106">アーカイブパスと AGPM サービスアカウントは、AGPM サーバーのインストール中に構成されます。また、AGPM サーバー上の**プログラムの追加と削除**を通じて、後から変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="3410c-106">The archive path and AGPM Service Account are configured during the installation of AGPM Server and can be changed afterward through **Add or Remove Programs** on the AGPM Server.</span></span>

<span data-ttu-id="3410c-107">**注意** AGPM サービスの設定は、オペレーティングシステムの**管理ツール**と**サービス**を使って変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="3410c-107">**Caution** Do not modify settings for the AGPM Service through **Administrative Tools** and **Services** in the operating system.</span></span> <span data-ttu-id="3410c-108">これにより、AGPM サービスが開始されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="3410c-108">Doing so can prevent the AGPM Service from starting.</span></span>

 

<span data-ttu-id="3410c-109">この手順を完了するには、Domain Admins グループのメンバーであり、AGPM サーバー (Microsoft Advanced Group Policy Management-Server がインストールされているコンピューター) にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3410c-109">A user account that is a member of the Domain Admins group and has access to the AGPM Server (the computer on which Microsoft Advanced Group Policy Management - Server is installed) is required to complete this procedure.</span></span>

<span data-ttu-id="3410c-110">**重要** AGPM サービスアカウントには、管理する Gpo へのフルアクセス権が必要であり、**サービスアクセス許可としてログオン**する権限が付与されます。</span><span class="sxs-lookup"><span data-stu-id="3410c-110">**Important** The AGPM Service Account must have full access to the GPOs that it will manage and will be granted **Log On As A Service** permission.</span></span> <span data-ttu-id="3410c-111">1つのドメインで Gpo を管理する場合は、プライマリドメインコントローラーのローカルシステムアカウントを AGPM サービスアカウントとして設定することができます。</span><span class="sxs-lookup"><span data-stu-id="3410c-111">If you will be managing GPOs on a single domain, you can make the Local System account for the primary domain controller the AGPM Service Account.</span></span>

<span data-ttu-id="3410c-112">複数のドメインで Gpo を管理する場合や、メンバーサーバーが AGPM サーバーになる場合は、1つのドメインコントローラーのローカルシステムアカウントが他のドメインの Gpo にアクセスできないため、別のアカウントを AGPM サービスアカウントとして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3410c-112">If you will be managing GPOs on multiple domains or if a member server will be the AGPM Server, you should configure a different account as the AGPM Service Account because the Local System account for one domain controller cannot access GPOs on other domains.</span></span>

 

**<span data-ttu-id="3410c-113">AGPM サービスアカウントを変更するには</span><span class="sxs-lookup"><span data-stu-id="3410c-113">To modify the AGPM Service Account</span></span>**

1.  <span data-ttu-id="3410c-114">Microsoft Advanced グループポリシー管理 (Server) がインストールされているコンピューターで、[**スタート**] をクリックし、[**コントロールパネル**] をクリックして、[**プログラムの追加と削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3410c-114">On the computer on which Microsoft Advanced Group Policy Management - Server is installed, click **Start**, click **Control Panel**, click **Add or Remove Programs**.</span></span>

2.  <span data-ttu-id="3410c-115">[ **Microsoft Advanced Group Policy Management-Server**] をクリックし、[**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3410c-115">Click **Microsoft Advanced Group Policy Management - Server**, and then click **Change**.</span></span>

3.  <span data-ttu-id="3410c-116">[**次へ**] をクリックし、[**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3410c-116">Click **Next**, and then click **Modify**.</span></span>

4.  <span data-ttu-id="3410c-117">画面の指示に従って、AGPM サービスの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="3410c-117">Follow the instructions on screen to configure settings for the AGPM Service:</span></span>

    1.  <span data-ttu-id="3410c-118">アーカイブパスの場合は、AGPM サーバーとの相対的なアーカイブの場所を確認または変更します。</span><span class="sxs-lookup"><span data-stu-id="3410c-118">For the archive path, confirm or change the location for the archive relative to the AGPM Server.</span></span> <span data-ttu-id="3410c-119">アーカイブパスは、AGPM サーバー上のフォルダーを指すことができますが、この AGPM サーバーによって管理されるすべての Gpo と履歴データを格納するために十分な領域が必要です。</span><span class="sxs-lookup"><span data-stu-id="3410c-119">The archive path can point to a folder on the AGPM Server or elsewhere, but the location should have sufficient space to store all GPOs and history data managed by this AGPM Server.</span></span>

    2.  <span data-ttu-id="3410c-120">AGPM サービスアカウントの新しい資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="3410c-120">Enter new credentials for the AGPM Service Account.</span></span>

    3.  <span data-ttu-id="3410c-121">アーカイブの所有者の場合は、AGPM 管理者の資格情報 (フルコントロール) を入力します。</span><span class="sxs-lookup"><span data-stu-id="3410c-121">For the archive owner, enter the credentials of an AGPM Administrator (Full Control).</span></span>

5.  <span data-ttu-id="3410c-122">[**変更**] をクリックし、インストールが完了したら [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3410c-122">Click **Change**, and when the installation is complete click **Finish**.</span></span>

### <span data-ttu-id="3410c-123">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="3410c-123">Additional references</span></span>

-   [<span data-ttu-id="3410c-124">AGPM サービスの管理</span><span class="sxs-lookup"><span data-stu-id="3410c-124">Managing the AGPM Service</span></span>](managing-the-agpm-service.md)

 

 





