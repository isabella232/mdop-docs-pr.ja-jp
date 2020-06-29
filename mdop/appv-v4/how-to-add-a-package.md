---
title: パッケージを追加する方法
description: パッケージを追加する方法
author: dansimp
ms.assetid: 5407fdbe-e658-44f6-a9b8-a566b81dedce
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c580d7d131017c52e278adda0208ffcb2e86ccf2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821397"
---
# <span data-ttu-id="07703-103">パッケージを追加する方法</span><span class="sxs-lookup"><span data-stu-id="07703-103">How to Add a Package</span></span>


<span data-ttu-id="07703-104">次のような方法で、Application Virtualization Server 管理コンソールからパッケージを追加できます。</span><span class="sxs-lookup"><span data-stu-id="07703-104">You can add a package from the Application Virtualization Server Management Console in the following ways:</span></span>

-   <span data-ttu-id="07703-105">プロセス内でパッケージを自動的に作成するアプリケーションをインポートします。</span><span class="sxs-lookup"><span data-stu-id="07703-105">Import an application, which creates the package automatically in the process.</span></span>

-   <span data-ttu-id="07703-106">パッケージを手動で追加します。</span><span class="sxs-lookup"><span data-stu-id="07703-106">Add a package manually.</span></span>

<span data-ttu-id="07703-107">アプリケーションを手動で追加するのではなく、インポートすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="07703-107">It is recommended that you import applications instead of adding them manually.</span></span> <span data-ttu-id="07703-108">アプリケーションのインポートの詳細については、「[アプリケーションをインポートする方法](how-to-import-an-applicationserver.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07703-108">For more information about importing applications, see [How to Import an Application](how-to-import-an-applicationserver.md).</span></span>

**<span data-ttu-id="07703-109">パッケージを手動で追加するには</span><span class="sxs-lookup"><span data-stu-id="07703-109">To add a package manually</span></span>**

1.  <span data-ttu-id="07703-110">Application Virtualization Server 管理コンソールで、左側のウィンドウで [**パッケージ**] ノードを右クリックし、[**新しいパッケージ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="07703-110">In the Application Virtualization Server Management Console, right-click the **Packages** node in the left pane and choose **New Package**.</span></span>

2.  <span data-ttu-id="07703-111">[**新しいパッケージ**] ダイアログボックスで、[**パッケージ名**] フィールドに名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="07703-111">In the **New Package** dialog box, type a name in the **Package Name** field.</span></span>

3.  <span data-ttu-id="07703-112">[**パッケージファイルの完全なパス**] フィールドでパス名を参照するか、または入力します。</span><span class="sxs-lookup"><span data-stu-id="07703-112">Browse for or type a path name in the **Full path for package file** field.</span></span> <span data-ttu-id="07703-113">これは、SFT ファイルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="07703-113">This must be an SFT file.</span></span>

    <span data-ttu-id="07703-114">**注** SFT ファイルを参照している場合は、ローカルパス (たとえば、c/c ¥¥ \ _Apps \\ _App \ _Server \\ コンテンツ) をサーバーの静的ホスト名または IP アドレスに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="07703-114">**Note** If you browse to the SFT file, replace the local path (such as C:\\Program Files\\User\_Apps\\Virtual\_App\_Server\\content) with the server's static host name or IP address.</span></span> <span data-ttu-id="07703-115">変数 *% SFT \ _SOFTGRIDSERVER%* を使用するには、クライアントごとのコンピューター構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="07703-115">Using the variable *%SFT\_SOFTGRIDSERVER%* requires per-client computer configuration.</span></span>

    <span data-ttu-id="07703-116">仮想アプリケーションサーバーを参照するダイアログボックスでは、ユーザーがアクセスできる、サーバーの静的ホスト名や IP アドレスなどのネットワークの場所を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07703-116">In dialog boxes that refer to Virtual Application Servers, you must use a network location, such as the server's static host name or IP address, that your users can access.</span></span> <span data-ttu-id="07703-117">アプリケーションの Open Software Descriptor (OSD) ファイルでは、placeholder 変数 *% SFT \ _SOFTGRIDSERER%* をサーバーの静的ホスト名または IP アドレスに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="07703-117">The application's Open Software Descriptor (OSD) file can replace the placeholder variable *%SFT\_SOFTGRIDSERER%* with the server's static host name or IP address.</span></span> <span data-ttu-id="07703-118">Placeholder 変数から脱退する場合は、そのサーバーにアクセスする各クライアントコンピューターでこの変数を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07703-118">If you leave the placeholder variable, you must set this variable on each client computer that will access that server.</span></span> <span data-ttu-id="07703-119">ユーザーまたはシステム変数を、SFT \ _SOFTGRIDSERVER の各コンピューターで設定します。</span><span class="sxs-lookup"><span data-stu-id="07703-119">Set a User or System variable on each computer for SFT\_SOFTGRIDSERVER.</span></span> <span data-ttu-id="07703-120">変数の値は、サーバーの静的ホスト名または IP アドレスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="07703-120">The variable value must be the server's static host name or IP address.</span></span> <span data-ttu-id="07703-121">変数を設定する場合は、クライアントセッションを終了し、Microsoft Windows にログアウトしてから、Microsoft Windows にもう一度ログインして、セッションが実行されていて、変数が設定されていた各コンピューターでセッションを再起動します。</span><span class="sxs-lookup"><span data-stu-id="07703-121">If you set a variable, exit the Client session, log out of and back into Microsoft Windows, and then restart the session on each computer that had a session running and had the variable set.</span></span>

     

4.  <span data-ttu-id="07703-122">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07703-122">Click **Next**.</span></span>

5.  <span data-ttu-id="07703-123">[**概要**] ダイアログボックスにファイルの場所が表示され、ファイルをまだ保存していない場合は、その場所にファイルをコピーするように求められます。</span><span class="sxs-lookup"><span data-stu-id="07703-123">The **Summary** dialog box shows the file location and prompts you to copy the file to the location if you have not already done so.</span></span> <span data-ttu-id="07703-124">情報を確認したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07703-124">Click **Finish** after you have verified the information.</span></span>

    <span data-ttu-id="07703-125">**注** リモートサーバー上でアプリケーションを管理している場合は、次のダイアログボックスで、サーバーのコンテンツルートを基準としたファイルのパスのみを入力します。</span><span class="sxs-lookup"><span data-stu-id="07703-125">**Note** If you are managing applications on a remote server, in the next dialog box, type only the path of the file relative to the server's content root.</span></span>

     

## <span data-ttu-id="07703-126">関連トピック</span><span class="sxs-lookup"><span data-stu-id="07703-126">Related topics</span></span>


[<span data-ttu-id="07703-127">アプリケーションをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="07703-127">How to Import an Application</span></span>](how-to-import-an-applicationserver.md)

[<span data-ttu-id="07703-128">サーバー管理コンソールでパッケージを管理する方法</span><span class="sxs-lookup"><span data-stu-id="07703-128">How to Manage Packages in the Server Management Console</span></span>](how-to-manage-packages-in-the-server-management-console.md)

 

 





