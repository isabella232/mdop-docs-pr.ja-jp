---
title: Management Console をインストールする方法
description: Management Console をインストールする方法
author: dansimp
ms.assetid: 586d99c8-bca6-42e2-a39c-a696053142f1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 48f4f69753794cf8099df36828e0502e98414b31
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817304"
---
# <span data-ttu-id="1ef28-103">Management Console をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="1ef28-103">How to Install the Management Console</span></span>


<span data-ttu-id="1ef28-104">次の手順を使用して、ネットワーク上のターゲットコンピューターに Application Virtualization 管理コンソールをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="1ef28-104">You can use the following procedure to install the Application Virtualization Management Console on a target computer on the network.</span></span> <span data-ttu-id="1ef28-105">ターゲットコンピューターの管理者権限を持つネットワークアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ef28-105">You must use a network account that has administrator privileges on the target computer.</span></span> <span data-ttu-id="1ef28-106">コンソールを使って、Application Virtualization System Platform の構成と管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1ef28-106">You can use the console to configure and manage the Application Virtualization System Platform.</span></span>

<span data-ttu-id="1ef28-107">この手順を完了する前に、Application Virtualization Management Web Service をこのコンピューターまたは別のコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ef28-107">Before you can complete this procedure, you must install the Application Virtualization Management Web Service on this or a different computer.</span></span> <span data-ttu-id="1ef28-108">管理 Web サービスを使うと、データストアとドメインコントローラーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1ef28-108">The Management Web Service allows you to access the data store and the domain controller.</span></span> <span data-ttu-id="1ef28-109">Web サービスのインストールの詳細については、「[管理 Web サービスをインストールする方法](how-to-install-the-management-web-service.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ef28-109">For more information about installing the Web service, see [How to Install the Management Web Service](how-to-install-the-management-web-service.md).</span></span>

**<span data-ttu-id="1ef28-110">管理コンソールをインストールするには</span><span class="sxs-lookup"><span data-stu-id="1ef28-110">To install the Management Console</span></span>**

1.  <span data-ttu-id="1ef28-111">ターゲットコンピューターに以前のバージョンの管理コンソールがインストールされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1ef28-111">Verify that no previous versions of the Management Console are installed on the target computer.</span></span>

2.  <span data-ttu-id="1ef28-112">ネットワーク上でアプリケーションの仮想化システムセットアッププログラムが保存されている場所に移動します。ネットワークからこのプログラムを実行するか、またはターゲットコンピューターにディレクトリをコピーして、[ **Setup.exe**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ef28-112">Navigate to the location of the Application Virtualization System setup program on the network, either run this program from the network or copy its directory to the target computer, and then double-click **Setup.exe**.</span></span>

3.  <span data-ttu-id="1ef28-113">[**ようこそ] ページ**で、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ef28-113">On the **Welcome Page**, click **Next**.</span></span>

4.  <span data-ttu-id="1ef28-114">[**使用許諾契約**書] ページで、使用許諾契約に同意する場合は、[**ライセンス条項に同意**する] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ef28-114">On the **License Agreement** page, to accept the license agreement, select **I accept the license terms and conditions**, and then click **Next**.</span></span>

5.  <span data-ttu-id="1ef28-115">[**登録情報**] ページで、**ユーザー名**と**組織**の情報を指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ef28-115">On the **Registration Information** page, specify the **User Name** and **Organization** information, and then click **Next**.</span></span>

6.  <span data-ttu-id="1ef28-116">[**セットアップの種類**] ページで、[**ユーザー設定**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ef28-116">On the **Setup Type** page, click **Custom** and then click **Next**.</span></span>

7.  <span data-ttu-id="1ef28-117">[**カスタムセットアップ**] ページで、[**管理コンソール**を除くすべての Application Virtualization システムコンポーネント] の選択を解除し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ef28-117">On the **Custom Setup** page, deselect all Application Virtualization System components except **Management Console**, and then click **Next**.</span></span>

    <span data-ttu-id="1ef28-118">**注** コンポーネントがコンピューターに既にインストールされている場合は、[カスタムセットアップ] 画面でそのコンポーネントをオフにすると、自動的にアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="1ef28-118">**Note** If a component is already installed on the computer, by deselecting it on the Custom Setup screen, it will automatically be uninstalled.</span></span>

     

8.  <span data-ttu-id="1ef28-119">[**プログラムを変更する準備ができ**ました] 画面で、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ef28-119">On the **Ready to Modify the Program** screen, click **Install**.</span></span>

    <span data-ttu-id="1ef28-120">**注** 初めてインストールする場合は、[**プログラムをインストールする準備ができ**ました] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ef28-120">**Note** If this is the first component you install, the **Ready to Install the Program** page is displayed.</span></span> <span data-ttu-id="1ef28-121">インストールを開始するには、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ef28-121">To start the installation, click **Install**.</span></span>

     

9.  <span data-ttu-id="1ef28-122">**インストールウィザード**の [完了] 画面で、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ef28-122">On the **Installation Wizard Completed** screen, click **Finish**.</span></span> <span data-ttu-id="1ef28-123">[ **Ok** ] をクリックしてコンピューターを再起動し、インストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="1ef28-123">Click **Okay** to restart the computer and complete the installation.</span></span>

10. <span data-ttu-id="1ef28-124">Windows のコントロールパネルで、[**管理ツール**] をダブルクリックし、[**アプリケーション仮想化管理コンソール**] をクリックして、管理コンソールを表示します。</span><span class="sxs-lookup"><span data-stu-id="1ef28-124">In the Windows Control Panel, double-click **Administrative Tools** and then click **Application Virtualization Management Console** to display the Management Console.</span></span>

11. <span data-ttu-id="1ef28-125">[**接続**] アイコンをクリックするか、[ **application virtualization Systems** ] コンテナーを右クリックして、[**アプリケーション仮想化システムに接続する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ef28-125">Click the **Connect** icon, or right-click the **Application Virtualization Systems** container, and then click **Connect to Application Virtualization System**.</span></span>

12. <span data-ttu-id="1ef28-126">[ **Application Virtualization System への接続**] 画面で、管理 Web サービスコンピューターのホスト名とポートを入力し、必要に応じてセキュリティ情報とログイン資格情報を変更して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ef28-126">On the **Connect to Application Virtualization System** screen, enter the host name and port of the Management Web Service computer, change the security information and login credentials if necessary, and then click **OK**.</span></span>

13. <span data-ttu-id="1ef28-127">管理 Web サービスコンピューターに接続した後、[**コンソール**] メニューの [**ファイル**] をクリックし、[**終了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1ef28-127">After connecting to the Management Web Service computer, click **File** on the **Console** menu, and then click **Exit**.</span></span> <span data-ttu-id="1ef28-128">[**はい]** をクリックしてコンソールの設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="1ef28-128">Click **Yes** to save console settings.</span></span>

## <span data-ttu-id="1ef28-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1ef28-129">Related topics</span></span>


[<span data-ttu-id="1ef28-130">サーバーおよびシステム コンポーネントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="1ef28-130">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)

 

 





