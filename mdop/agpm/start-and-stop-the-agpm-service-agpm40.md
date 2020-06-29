---
title: AGPM サービスを開始および停止する
description: AGPM サービスを開始および停止する
author: dansimp
ms.assetid: dcc9566c-c515-4fbe-b7f5-8ac030141307
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3c254cc122c43262ff5ec4cb0bf5a5ab2c77fac3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820207"
---
# <span data-ttu-id="0b1ed-103">AGPM サービスを開始および停止する</span><span class="sxs-lookup"><span data-stu-id="0b1ed-103">Start and Stop the AGPM Service</span></span>


<span data-ttu-id="0b1ed-104">AGPM サービスは、セキュリティプロキシとして機能する Windows サービスであり、アーカイブと運用環境でのグループポリシーオブジェクト (Gpo) へのクライアントアクセスを管理します。</span><span class="sxs-lookup"><span data-stu-id="0b1ed-104">The AGPM Service is a Windows service that acts as a security proxy, managing client access to Group Policy Objects (GPOs) in the archive and production environment.</span></span>

<span data-ttu-id="0b1ed-105">**重要** AGPM サービスを停止または無効にすると、AGPM クライアントがサーバー経由で Gpo の一覧表示や編集などの操作を実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="0b1ed-105">**Important** Stopping or disabling the AGPM Service will prevent AGPM Clients from performing any operations (such as listing or editing GPOs) through the server.</span></span>

 

<span data-ttu-id="0b1ed-106">この手順を完了するには、AGPM サーバー (AGPM サービスがインストールされているコンピューター) へのアクセス権を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="0b1ed-106">A user account with access to the AGPM Server (the computer on which the AGPM Service is installed) is required to complete this procedure.</span></span>

**<span data-ttu-id="0b1ed-107">AGPM サービスを開始または停止するには</span><span class="sxs-lookup"><span data-stu-id="0b1ed-107">To start or stop the AGPM Service</span></span>**

1.  <span data-ttu-id="0b1ed-108">Microsoft Advanced グループポリシー管理サーバー (つまり、AGPM サービス) がインストールされているコンピューターで、[**スタート**] をクリックし、[**コントロールパネル**] をクリックして、[**管理ツール**] をクリックし、[**サービス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0b1ed-108">On the computer on which Microsoft Advanced Group Policy Management - Server (and therefore the AGPM Service) is installed, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **Services**.</span></span>

2.  <span data-ttu-id="0b1ed-109">サービスの一覧で、[ **AGPM サービス**] を右クリックし、[**開始**]、[**再起動**]、または [**停止**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b1ed-109">In the list of services, right-click **AGPM Service** and select **Start**, **Restart**, or **Stop**.</span></span>

    <span data-ttu-id="0b1ed-110">**注意** AGPM サービスの設定は、オペレーティングシステムの**管理ツール**と**サービス**を使って変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="0b1ed-110">**Caution** Do not modify settings for the AGPM Service through **Administrative Tools** and **Services** in the operating system.</span></span> <span data-ttu-id="0b1ed-111">これにより、AGPM サービスが開始されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="0b1ed-111">Doing so can prevent the AGPM Service from starting.</span></span>

     

### <span data-ttu-id="0b1ed-112">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="0b1ed-112">Additional references</span></span>

-   [<span data-ttu-id="0b1ed-113">AGPM サービスの管理</span><span class="sxs-lookup"><span data-stu-id="0b1ed-113">Managing the AGPM Service</span></span>](managing-the-agpm-service-agpm40.md)

 

 





