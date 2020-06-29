---
title: Management Web Service をインストールする方法
description: Management Web Service をインストールする方法
author: dansimp
ms.assetid: cac296f5-8ca0-4ce7-afdb-859ae207d2f1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4b8cc1b4821cb4041d75003cf7e6ff592e1c5039
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817277"
---
# <span data-ttu-id="da45e-103">Management Web Service をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="da45e-103">How to Install the Management Web Service</span></span>


<span data-ttu-id="da45e-104">ローカルの管理者権限を持つログオンアカウントを使用して、ネットワーク上のターゲットコンピューターに Application Virtualization Management Web サービスをインストールするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="da45e-104">Use the following procedure to install the Application Virtualization Management Web Service on a target computer on the network, with a logon account having local administrative privileges.</span></span> <span data-ttu-id="da45e-105">必須ではありませんが、Web サーバーにこのコンポーネントをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="da45e-105">Although it is not required, we recommended that you install this component on your Web server.</span></span>

**<span data-ttu-id="da45e-106">管理 Web サービスをインストールするには</span><span class="sxs-lookup"><span data-stu-id="da45e-106">To install the Management Web Service</span></span>**

1.  <span data-ttu-id="da45e-107">ターゲットコンピューターに以前のバージョンの Application Virtualization Web サービスがインストールされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="da45e-107">Verify that no previous versions of the Application Virtualization Web Service are installed on your target computer.</span></span>

2.  <span data-ttu-id="da45e-108">ネットワーク上でアプリケーションの仮想化システムセットアッププログラムが保存されている場所に移動します。ネットワークからこのプログラムを実行するか、またはターゲットコンピューターにディレクトリをコピーして、[ **Setup.exe**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="da45e-108">Navigate to the location of the Application Virtualization System setup program on the network, either run this program from the network or copy its directory to the target computer, and then double-click **Setup.exe**.</span></span>

3.  <span data-ttu-id="da45e-109">インストールウィザードが開いたら、[**ようこそ**] ページで [**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da45e-109">After the Installation Wizard opens, on the **Welcome** page, click **Next**.</span></span>

4.  <span data-ttu-id="da45e-110">[**使用許諾契約**書] ページで、使用許諾契約に同意する場合は、[**ライセンス条項に同意**する] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da45e-110">On the **License Agreement** page, to accept the license agreement, select **I accept the license terms and conditions**, and then click **Next**.</span></span>

5.  <span data-ttu-id="da45e-111">[**登録情報**] ページで、**ユーザー名**と組織の情報を指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da45e-111">On the **Registration Information** page, specify the **User Name** and organization information, and then click **Next**.</span></span>

6.  <span data-ttu-id="da45e-112">[**セットアップの種類**] ページで、[**ユーザー設定**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da45e-112">On the **Setup Type** page, click **Custom**, and then click **Next**.</span></span>

    <span data-ttu-id="da45e-113">**注** このコンピューターにインストールした最初のコンポーネントではない場合は、[**プログラムメンテナンス**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da45e-113">**Note** If this is not the first component you installed on this computer, the **Program Maintenance** page is displayed.</span></span> <span data-ttu-id="da45e-114">[**プログラムメンテナンス**] ページで [**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da45e-114">On the **Program Maintenance** page, click **Modify**.</span></span>

     

7.  <span data-ttu-id="da45e-115">[**カスタムセットアップ**] ページで、 **App Virt Management Service**以外のすべてのアプリケーション仮想化システムコンポーネントをオフにして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da45e-115">On the **Custom Setup** page, clear all Application Virtualization System components except **App Virt Management Service**, and then click **Next**.</span></span>

    <span data-ttu-id="da45e-116">**注** コンピューターに既にインストールされているコンポーネントは、[**カスタムセットアップ**] ページでオフにすることで自動的にアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="da45e-116">**Note** If a component is already installed on the computer, by clearing it on the **Custom Setup** page, you will automatically uninstall it.</span></span>

     

8.  <span data-ttu-id="da45e-117">[**データベースサーバー** ] ページで、[**使用可能なデータベースに接続する**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da45e-117">On the **Database Server** page, click **Connect to available database**, and then click **Next**.</span></span>

    <span data-ttu-id="da45e-118">**注** 運用環境では、Microsoft は既存のデータベースに接続することを前提としています。</span><span class="sxs-lookup"><span data-stu-id="da45e-118">**Note** In a production environment, Microsoft assumes that you will connect to an existing database.</span></span> <span data-ttu-id="da45e-119">データベースをインストールする場合は、「[データベースをインストールする方法](how-to-install-a-database.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da45e-119">If you want to install a database, see [How to Install a Database](how-to-install-a-database.md).</span></span> <span data-ttu-id="da45e-120">データベースをインストールした後、手順13に進みます。</span><span class="sxs-lookup"><span data-stu-id="da45e-120">After installing the database, continue with step 13.</span></span>

     

9.  <span data-ttu-id="da45e-121">[**データベースサーバーの種類**] ページで、一覧からデータベースの種類を選び、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da45e-121">On the **Database Server Type** page, select a database type from the list, and then click **Next**.</span></span>

10. <span data-ttu-id="da45e-122">[**データベースサーバーの場所**] ページで、使用可能なサーバーの一覧からデータベースサーバーを選ぶか、[**次のホスト名を使用する**] チェックボックスをオンにし、[**サーバー名**と**ポート番号**] ボックスに情報を入力して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da45e-122">On the **Database Server Location** page, select a database server from the list of available servers or add a server by selecting the **Use the following host name** check box and entering information in the **Server Name** and **Port Number** boxes, and then click **Next**.</span></span>

11. <span data-ttu-id="da45e-123">[**データベースの選択**] ページで、必要なデータベースを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da45e-123">On the **Select Database** page, select the database you want, and then click **Next**.</span></span>

12. <span data-ttu-id="da45e-124">[**データベースユーザーの構成**] ページで、管理 Web サービスがデータストアにアクセスするために使用する資格情報を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da45e-124">On the **Database User Configuration** page, enter the credentials that the Management Web Service will use to access the data store, and then click **Next**.</span></span>

13. <span data-ttu-id="da45e-125">[**プログラムを変更する準備ができ**ました] ページで、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da45e-125">On the **Ready to Modify the Program** page, click **Install**.</span></span>

    <span data-ttu-id="da45e-126">**注** 初めてインストールする場合は、[**プログラムをインストールする準備ができ**ました] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da45e-126">**Note** If this is the first component you install, the **Ready to Install the Program** page is displayed.</span></span> <span data-ttu-id="da45e-127">このページで、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da45e-127">On the page, click **Install**.</span></span>

     

14. <span data-ttu-id="da45e-128">**インストールウィザード**の [完了] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da45e-128">On the **Installation Wizard Completed** page, click **Finish**.</span></span>

## <span data-ttu-id="da45e-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="da45e-129">Related topics</span></span>


[<span data-ttu-id="da45e-130">サーバーおよびシステム コンポーネントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="da45e-130">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)

 

 





