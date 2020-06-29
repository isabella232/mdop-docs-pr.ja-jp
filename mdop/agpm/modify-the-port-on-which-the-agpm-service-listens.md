---
title: AGPM サービスがリッスンするポートを変更する
description: AGPM サービスがリッスンするポートを変更する
author: dansimp
ms.assetid: a82c6873-e916-4a04-b263-aa612cd6956b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2af79ecb9bd05acbc55083163903ae14ab44d06
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820487"
---
# <span data-ttu-id="24be6-103">AGPM サービスがリッスンするポートを変更する</span><span class="sxs-lookup"><span data-stu-id="24be6-103">Modify the Port on Which the AGPM Service Listens</span></span>


<span data-ttu-id="24be6-104">AGPM サービスは、セキュリティプロキシとして機能する Windows サービスであり、アーカイブと運用環境でのグループポリシーオブジェクト (Gpo) へのクライアントアクセスを管理します。</span><span class="sxs-lookup"><span data-stu-id="24be6-104">The AGPM Service is a Windows service that acts as a security proxy, managing client access to Group Policy objects (GPOs) in the archive and production environment.</span></span> <span data-ttu-id="24be6-105">既定では、AGPM サービスはポート4600をリッスンします。</span><span class="sxs-lookup"><span data-stu-id="24be6-105">By default, the AGPM Service listens on port 4600.</span></span> <span data-ttu-id="24be6-106">このポートを変更するには、各アーカイブの高度なグループポリシー管理 (AGPM) アーカイブインデックスファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="24be6-106">You can change this port by modifying the Advanced Group Policy Management (AGPM) archive index file for each archive.</span></span>

<span data-ttu-id="24be6-107">**注** AGPM サービスがリッスンするポートを変更する前に、AGPM アーカイブインデックスファイル (gpostate.xml) をバックアップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="24be6-107">**Note** Before modifying the port on which the AGPM Service listens, it is recommended that you back up the AGPM archive index file (gpostate.xml).</span></span> <span data-ttu-id="24be6-108">このファイルは、高度なグループポリシー管理サーバーのインストール中にアーカイブパスとして入力されたフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="24be6-108">This file is located in the folder entered as the archive path during the installation of Advanced Group Policy Management - Server.</span></span> <span data-ttu-id="24be6-109">既定では、このファイルの場所は、AGPM サーバー上の% CommonAppData% \\Microsoft\\AGPM\\gpostate.xml です。</span><span class="sxs-lookup"><span data-stu-id="24be6-109">By default, this location of this file is %CommonAppData%\\Microsoft\\AGPM\\gpostate.xml on the AGPM Server.</span></span> <span data-ttu-id="24be6-110">どのコンピューターでアーカイブをホストしているのかがわからない場合は、アーカイブパスを変更する手順に従って、現在のアーカイブパスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="24be6-110">If you do not know which computer hosts the archive, you can follow the procedure for modifying the archive path to display the current archive path.</span></span> <span data-ttu-id="24be6-111">詳細については、「[アーカイブパスを変更](modify-the-archive-path.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24be6-111">For more information, see [Modify the Archive Path](modify-the-archive-path.md).</span></span>

 

<span data-ttu-id="24be6-112">この手順を完了するには、AGPM サーバー (AGPM サービスがインストールされているコンピューター) とアーカイブインデックスファイルへのアクセス権を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="24be6-112">A user account with access to the AGPM Server (the computer on which the AGPM Service is installed) and the archive index file is required to complete this procedure.</span></span>

**<span data-ttu-id="24be6-113">AGPM サービスがリッスンするポートを変更するには</span><span class="sxs-lookup"><span data-stu-id="24be6-113">To modify the port on which the AGPM Service listens</span></span>**

1.  <span data-ttu-id="24be6-114">アーカイブをホストしているコンピューターで、アーカイブインデックスファイル (gpostate.xml) をテキストエディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="24be6-114">On the computer hosting the archive, open the archive index file (gpostate.xml) in a text editor.</span></span>

2.  <span data-ttu-id="24be6-115">ファイルで、 **agpm: port = "4600"** を検索します。</span><span class="sxs-lookup"><span data-stu-id="24be6-115">In the file, search for **agpm:port="4600"**.</span></span>

3.  <span data-ttu-id="24be6-116">AGPM サービスがリッスンする必要があるポートに**4600**を置き換えます。次に、ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="24be6-116">Replace **4600** with the port on which the AGPM Service should listen; then, save and close the file.</span></span>

4.  <span data-ttu-id="24be6-117">AGPM サーバーで、AGPM サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="24be6-117">On the AGPM Server, restart the AGPM Service.</span></span> <span data-ttu-id="24be6-118">(詳細については、「 [AGPM サービスの開始と停止](start-and-stop-the-agpm-service.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="24be6-118">(For more information, see [Start and Stop the AGPM Service](start-and-stop-the-agpm-service.md).)</span></span>

5.  <span data-ttu-id="24be6-119">各グループポリシー管理者の AGPM サーバー接続のポートを変更します。</span><span class="sxs-lookup"><span data-stu-id="24be6-119">Modify the port in the AGPM Server connection for each Group Policy administrator.</span></span> <span data-ttu-id="24be6-120">詳細については、「 [AGPM サーバー接続を構成する](configure-the-agpm-server-connection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24be6-120">(For more information, see [Configure the AGPM Server Connection](configure-the-agpm-server-connection.md).)</span></span>

6.  <span data-ttu-id="24be6-121">各アーカイブと AGPM サーバーに対してこの手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="24be6-121">Repeat for each archive and AGPM Server.</span></span>

### <span data-ttu-id="24be6-122">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="24be6-122">Additional references</span></span>

-   [<span data-ttu-id="24be6-123">AGPM サービスの管理</span><span class="sxs-lookup"><span data-stu-id="24be6-123">Managing the AGPM Service</span></span>](managing-the-agpm-service.md)

 

 





