---
title: 既定のアプリケーションをインストールして構成する方法
description: 既定のアプリケーションをインストールして構成する方法
author: dansimp
ms.assetid: 5c5d5ad1-af40-4f83-8234-39e972f2c29a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1083de7a8ebf94bce0b41c0d3c3edf350a9aff38
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817367"
---
# <span data-ttu-id="924cd-103">既定のアプリケーションをインストールして構成する方法</span><span class="sxs-lookup"><span data-stu-id="924cd-103">How to Install and Configure the Default Application</span></span>


<span data-ttu-id="924cd-104">既定のアプリケーションはインストールの一部として提供され、インストール時に Microsoft Application Virtualization (App-v) 管理サーバーに自動的にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="924cd-104">The default application is provided as part of the installation and is automatically copied to the Microsoft Application Virtualization (App-V) Management Server during installation.</span></span> <span data-ttu-id="924cd-105">これは、管理サーバーが正しくインストールおよび構成されていることを確認するために使われますが、ユーザーがアクセスできるように Microsoft Application Virtualization (App-v) クライアントに公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="924cd-105">It is used to verify that the Management Server was installed and configured correctly, but it has to be published to the Microsoft Application Virtualization (App-V) Client so that the user can access it.</span></span>

<span data-ttu-id="924cd-106">既定のアプリケーションを公開してストリーム処理するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="924cd-106">Use the following procedures to publish the default application and to stream it.</span></span>

**<span data-ttu-id="924cd-107">既定のアプリケーションを発行するには</span><span class="sxs-lookup"><span data-stu-id="924cd-107">To publish the default application</span></span>**

1.  <span data-ttu-id="924cd-108">インストール時に指定した App-v 管理者グループのメンバーであるアカウントを使用して、App-v 管理サーバーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="924cd-108">Log on to the App-V Management Server by using an account that is a member of the App-V Administrators group specified during installation.</span></span>

2.  <span data-ttu-id="924cd-109">App-v 管理サーバーで、[**スタート**] をクリックし、[**管理ツール**] をクリックして、[ **Application Virtualization 管理コンソール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="924cd-109">On the App-V Management Server, click **Start**, click **Administrative Tools**, and then click **Application Virtualization Management Console**.</span></span>

3.  <span data-ttu-id="924cd-110">App-v の管理コンソールで、[**操作**] をクリックし、[**アプリケーション仮想化システムに接続する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="924cd-110">In the App-V Management Console, click **Actions**, and then click **Connect to Application Virtualization System**.</span></span>

4.  <span data-ttu-id="924cd-111">[**接続の構成**] ページで、[**セキュリティで保護された接続を使用する**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="924cd-111">On the **Configure Connection** page, clear the **Use Secure Connection** check box.</span></span>

5.  <span data-ttu-id="924cd-112">[ **Web サービスホスト名**] ボックスに、App-v Management Server の完全修飾ドメイン名 (FQDN) を入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="924cd-112">In the **Web Service Host Name** box, type the fully qualified domain name (FQDN) of the App-V Management Server, and then click **OK**.</span></span>

    <span data-ttu-id="924cd-113">**注** 管理サーバーにインストールされている場合は、Web サービスホスト名として**localhost**を使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="924cd-113">**Note** You can also use **localhost** for the Web Service Host name if it is installed on the Management Server.</span></span>

     

6.  <span data-ttu-id="924cd-114">App-v 管理コンソールで、**サーバー**ノードを右クリックし、[**システムオプション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="924cd-114">In the App-V Management Console, right-click the **Server** node, and click **System Options**.</span></span>

7.  <span data-ttu-id="924cd-115">[**全般**] タブの [**既定のコンテンツパス**] ボックスに、インストール時にサーバー上で作成したコンテンツフォルダーへの汎用名前付け規則 (UNC) パスを入力します。たとえば、\\ \ \ Server 名 \\ コンテンツの場合は、[ &lt; &gt; **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="924cd-115">On the **General** tab, in the **Default Content Path** box, enter the Universal Naming Convention (UNC) path to the Content folder you created on the server during installation; for example, \\\\&lt;Server Name&gt;\\Content, and then click **OK**.</span></span>

    <span data-ttu-id="924cd-116">**重要** クライアントが名前を正しく解決できるように、サーバー名には FQDN を使用します。</span><span class="sxs-lookup"><span data-stu-id="924cd-116">**Important** Use the FQDN for the server name so that the client can resolve the name correctly.</span></span>

     

8.  <span data-ttu-id="924cd-117">App-v 管理コンソールのナビゲーションウィンドウで、**サーバー**ノードを展開し、[**アプリケーション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="924cd-117">In the App-V Management Console, in the navigation pane, expand the **Server** node, and then click **Applications**.</span></span>

9.  <span data-ttu-id="924cd-118">[トピック] ウィンドウで、[**既定のアプリケーション**] をクリックし、[**操作**] ウィンドウの [**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="924cd-118">In the topic pane, click **Default Application**, and then, in the **Actions** pane, click **Properties**.</span></span>

10. <span data-ttu-id="924cd-119">[**プロパティ**] ダイアログボックスで、[ **OSD Path** ] ボックスの横にある [**参照**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="924cd-119">In the **Properties** dialog box, next to the **OSD Path** box, click **Browse**.</span></span>

11. <span data-ttu-id="924cd-120">[**ファイルを開く**] ダイアログボックスで、インストール時にサーバー上で作成したコンテンツフォルダーへの UNC パスを入力します。たとえば、\\ \ \ Server 名 \\ [コンテンツ] のように &lt; &gt; 入力し、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="924cd-120">In the **Open** dialog box, enter the UNC path to the Content folder you created on the server during installation; for example, \\\\&lt;Server Name&gt;\\Content, and press ENTER.</span></span> <span data-ttu-id="924cd-121">実際のサーバー名を使用する必要があります。ここでは**localhost**は使用できません。</span><span class="sxs-lookup"><span data-stu-id="924cd-121">You must use the actual server name and cannot use the **localhost** here.</span></span>

    <span data-ttu-id="924cd-122">**重要** [ **OSD path** ] と [ **Icon path]** の両方のボックスの値が UNC 形式 (たとえば、\\ \ \ &lt; Server Name &gt; ¥¥¥¥¥¥¥¥¥¥) であり、サーバーのインストール時に作成したコンテンツフォルダーをポイントしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="924cd-122">**Important** Ensure that the values in both the **OSD Path** and **Icon Path** boxes are in UNC format (for example, \\\\&lt;Server Name&gt;\\Content\\DefaultApp.ico), and point to the Content folder you created when installing the server.</span></span> <span data-ttu-id="924cd-123">**Localhost** 、または c:\windows/ファイル名などのドライブ文字を含むファイルパスを使わないでください。\\..コンテンツ.</span><span class="sxs-lookup"><span data-stu-id="924cd-123">Do not use **localhost** or a file path containing a drive letter such as C:\\Program Files\\..\\..\\Content.</span></span>

     

12. <span data-ttu-id="924cd-124">DefaultApp ファイルを選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="924cd-124">Select the DefaultApp.osd file, and click **Open**.</span></span>

13. <span data-ttu-id="924cd-125">上記の手順を繰り返して、アイコンのパスを設定します。</span><span class="sxs-lookup"><span data-stu-id="924cd-125">Repeat the previous steps to configure the icon path.</span></span>

14. <span data-ttu-id="924cd-126">[**アクセス許可**] タブをクリックして、アプリケーションに対するアクセス許可が app-v Users グループに付与されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="924cd-126">Click the **Access Permissions** tab, and confirm that the App-V Users group has access permissions to the application.</span></span>

15. <span data-ttu-id="924cd-127">[**ショートカット**] タブをクリックし、[**ユーザーのデスクトップに発行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="924cd-127">Click the **Shortcuts** tab, and then click **Publish to User’s Desktop**.</span></span> <span data-ttu-id="924cd-128">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="924cd-128">Click **OK**.</span></span>

16. <span data-ttu-id="924cd-129">Windows エクスプローラーを開き、コンテンツディレクトリを見つけます。</span><span class="sxs-lookup"><span data-stu-id="924cd-129">Open Windows Explorer, and locate the Content directory.</span></span>

17. <span data-ttu-id="924cd-130">DefaultApp ファイルをダブルクリックして、メモ帳で開きます。</span><span class="sxs-lookup"><span data-stu-id="924cd-130">Double-click the DefaultApp.osd file, and open it with Notepad.</span></span>

18. <span data-ttu-id="924cd-131">**HREF**タグを含む行を見つけて、次のコードに変更します。</span><span class="sxs-lookup"><span data-stu-id="924cd-131">Locate the line that contains the **HREF** tag, and change it to the following code:</span></span>

         `CODEBASEHREF=”RTSP://<FQDN of your server>:554/DefaultApp.sft”`

    <span data-ttu-id="924cd-132">RTSPS を使用している場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="924cd-132">Or, if you are using RTSPS:</span></span>

         `CODEBASEHREF=”RTSPS://<FQDN of your server>:322/DefaultApp.sft”`

19. <span data-ttu-id="924cd-133">DefaultApp ファイルを閉じて、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="924cd-133">Close the DefaultApp.osd file, and save the changes.</span></span>

**<span data-ttu-id="924cd-134">既定のアプリケーションをストリーミングするには</span><span class="sxs-lookup"><span data-stu-id="924cd-134">To stream the default application</span></span>**

1.  <span data-ttu-id="924cd-135">App-v クライアントがインストールされているコンピューターで、サーバーのインストール時に指定した Application Virtualization Users グループのメンバーであるユーザーとしてログオンします。</span><span class="sxs-lookup"><span data-stu-id="924cd-135">On the computer that has the App-V Client installed, log on as a user who is a member of the Application Virtualization Users group specified during server installation.</span></span>

2.  <span data-ttu-id="924cd-136">デスクトップでは、 **Application Virtualization の既定のアプリケーション**のショートカットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="924cd-136">On the desktop, the **Default Application Virtualization Application** shortcut appears.</span></span> <span data-ttu-id="924cd-137">ショートカットをダブルクリックして、アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="924cd-137">Double-click the shortcut to start the application.</span></span>

3.  <span data-ttu-id="924cd-138">Windows 通知領域の上に表示されるステータスバーに、アプリケーションが起動していることが報告されます。</span><span class="sxs-lookup"><span data-stu-id="924cd-138">A status bar, displayed above the Windows notification area, reports that the application is starting.</span></span> <span data-ttu-id="924cd-139">アプリケーションが正常に起動すると、既定のアプリケーションのタイトル画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="924cd-139">If the application startup is successful, the title screen for the default application is displayed.</span></span> <span data-ttu-id="924cd-140">[ **OK** ] をクリックしてダイアログボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="924cd-140">Click **OK** to close the dialog box.</span></span> <span data-ttu-id="924cd-141">これで、App-v システムが正常に動作していることが確認されました。</span><span class="sxs-lookup"><span data-stu-id="924cd-141">You have now confirmed that the App-V system is running correctly.</span></span>

## <span data-ttu-id="924cd-142">関連トピック</span><span class="sxs-lookup"><span data-stu-id="924cd-142">Related topics</span></span>


[<span data-ttu-id="924cd-143">サーバー ベースの展開用にサーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="924cd-143">How to Configure Servers for Server-Based Deployment</span></span>](how-to-configure-servers-for-server-based-deployment.md)

 

 





