---
title: MED-V サーバー コンポーネントをインストールして構成する方法
description: MED-V サーバー コンポーネントをインストールして構成する方法
author: dansimp
ms.assetid: 2d3c5b15-df2c-4ab6-bf78-f47ef8ae7418
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4fb0cc5c9ffe76e987e316d0285f172dd0b76578
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826977"
---
# <span data-ttu-id="029e8-103">MED-V サーバー コンポーネントをインストールして構成する方法</span><span class="sxs-lookup"><span data-stu-id="029e8-103">How to Install and Configure the MED-V Server Component</span></span>


<span data-ttu-id="029e8-104">このセクションでは、MED-V サーバーを[インストール](#bkmk-howtoinstallthemedvserver)して[構成](#bkmk-howtoconfigurethemedvserver)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="029e8-104">This section explains how to [install](#bkmk-howtoinstallthemedvserver) and [configure](#bkmk-howtoconfigurethemedvserver) the MED-V server.</span></span>

## <a href="" id="bkmk-howtoinstallthemedvserver"></a><span data-ttu-id="029e8-105">MED-V サーバーをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="029e8-105">How to Install the MED-V Server</span></span>


**<span data-ttu-id="029e8-106">MED-V サーバーをインストールするには</span><span class="sxs-lookup"><span data-stu-id="029e8-106">To install the MED-V server</span></span>**

1.  <span data-ttu-id="029e8-107">MED-V パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="029e8-107">Install the MED-V Server .msi package.</span></span>

    <span data-ttu-id="029e8-108">MED-V パッケージは*MED-V\_Server\_x.msi*と呼ばれます。ここで、x はバージョン番号です。</span><span class="sxs-lookup"><span data-stu-id="029e8-108">The MED-V Server .msi package is called *MED-V\_Server\_x.msi*, where x is the version number.</span></span>

    <span data-ttu-id="029e8-109">たとえば、 *MED-V\_Server\_1.0.65.msi*とします。</span><span class="sxs-lookup"><span data-stu-id="029e8-109">For example, *MED-V\_Server\_1.0.65.msi*.</span></span>

2.  <span data-ttu-id="029e8-110">**InstallShield ウィザード**の [ようこそ] 画面が表示されたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029e8-110">When the **InstallShield Wizard Welcome** screen appears, click **Next**.</span></span>

3.  <span data-ttu-id="029e8-111">[**使用**許諾契約書] 画面で、使用許諾契約書を読み、[使用許諾**契約書に同意**します] をクリックして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029e8-111">On the **License Agreement** screen, read the license agreement, click **I accept the terms in the license agreement**, and then click **Next**.</span></span>

    <span data-ttu-id="029e8-112">[**インポート先のフォルダー** ] 画面が表示され、既定のインストールフォルダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="029e8-112">The **Destination Folder** screen appears, with the default installation folder displayed.</span></span>

    <span data-ttu-id="029e8-113">既定のインストールフォルダーは、% *SystemVirtualization\\% ¥ Program filesmicrosoft Enterprise Desktop*です。</span><span class="sxs-lookup"><span data-stu-id="029e8-113">The default installation folder is *%systemdrive%\\Program Files\\Microsoft Enterprise Desktop Virtualization\\*.</span></span>

    -   <span data-ttu-id="029e8-114">MED-V をインストールする必要があるフォルダーを変更するには、[**変更**] をクリックし、既存のフォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="029e8-114">To change the folder where MED-V should be installed, click **Change** and browse to an existing folder.</span></span>

4.  <span data-ttu-id="029e8-115">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029e8-115">Click **Next**.</span></span>

5.  <span data-ttu-id="029e8-116">[**プログラムをインストールする準備ができ**ました] 画面で、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029e8-116">On the **Ready to Install the Program** screen, click **Install**.</span></span>

    <span data-ttu-id="029e8-117">MED-V サーバーのインストールが開始されます。</span><span class="sxs-lookup"><span data-stu-id="029e8-117">The MED-V server installation starts.</span></span> <span data-ttu-id="029e8-118">これには数分かかることがあり、画面にテキストが表示されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="029e8-118">This can take several minutes, and the screen might not display text.</span></span> <span data-ttu-id="029e8-119">インストール中に、いくつかの進行状況画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="029e8-119">During installation, several progress screens appear.</span></span> <span data-ttu-id="029e8-120">メッセージが表示されたら、表示される指示に従います。</span><span class="sxs-lookup"><span data-stu-id="029e8-120">If a message appears, follow the instructions provided.</span></span>

6.  <span data-ttu-id="029e8-121">[ **InstallShield ウィザードの完了**] 画面が表示されたら、[**完了**] をクリックしてウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="029e8-121">When the **InstallShield Wizard Completed** screen appears, click **Finish** to complete the wizard.</span></span>

**<span data-ttu-id="029e8-122">注</span><span class="sxs-lookup"><span data-stu-id="029e8-122">Note</span></span>**  
<span data-ttu-id="029e8-123">Microsoft リモートデスクトップ経由で MED-V サーバーをインストールする場合は、次の構文を使用します。 **mstsc/admin**。RDP セッションが本体に送られていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="029e8-123">If you are installing the MED-V server via Microsoft Remote Desktop, use the following syntax: **mstsc/admin**. Ensure that your RDP session is directed to the console.</span></span>



## <a href="" id="bkmk-howtoconfigurethemedvserver"></a><span data-ttu-id="029e8-124">MED-V サーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="029e8-124">How to Configure the MED-V Server</span></span>


<span data-ttu-id="029e8-125">次のサーバー設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="029e8-125">The following server settings can be configured:</span></span>

-   [<span data-ttu-id="029e8-126">Connections</span><span class="sxs-lookup"><span data-stu-id="029e8-126">Connections</span></span>](#bkmk-configuringconnections)

-   [<span data-ttu-id="029e8-127">画像</span><span class="sxs-lookup"><span data-stu-id="029e8-127">Images</span></span>](#bkmk-configuringimages)

-   [<span data-ttu-id="029e8-128">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="029e8-128">Permissions</span></span>](#bkmk-configuringpermissions)

-   [<span data-ttu-id="029e8-129">レポート</span><span class="sxs-lookup"><span data-stu-id="029e8-129">Reports</span></span>](#bkmk-configuringreports)

### <a href="" id="bkmk-configuringconnections"></a><span data-ttu-id="029e8-130">接続を構成する</span><span class="sxs-lookup"><span data-stu-id="029e8-130">Configuring Connections</span></span>

**<span data-ttu-id="029e8-131">接続を構成するには</span><span class="sxs-lookup"><span data-stu-id="029e8-131">To configure connections</span></span>**

1.  <span data-ttu-id="029e8-132">Windows の [スタート] メニューで、[すべてのプログラム] を選びます\*\* &gt; &gt; \*\*。</span><span class="sxs-lookup"><span data-stu-id="029e8-132">On the Windows Start menu, select **All Programs &gt; MED-V &gt; MED-V Server Configuration Manager**.</span></span>

    **<span data-ttu-id="029e8-133">注</span><span class="sxs-lookup"><span data-stu-id="029e8-133">Note</span></span>**  
    <span data-ttu-id="029e8-134">注: サーバーのインストール中に [ **Hyper-v Server 構成マネージャーを起動**する] チェックボックスをオンにした場合、サーバーのインストールが完了すると、med-v サーバー構成マネージャーが自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="029e8-134">Note: If you selected the **Launch MED-V Server Configuration Manager** check box during the server installation, the MED-V server configuration manager starts automatically after the server installation is complete.</span></span>



~~~
The MED-V Server Configuration Manager appears.
~~~

2. <span data-ttu-id="029e8-135">[**接続**] タブで、次のクライアント接続設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="029e8-135">On the **Connections** tab, configure the following client connections settings:</span></span>

   -   <span data-ttu-id="029e8-136">[暗号化されていない**接続 (http)、ポートを使用**する] —指定したポートを使って暗号化されていない接続を有効にするには、このチェックボックスをオン</span><span class="sxs-lookup"><span data-stu-id="029e8-136">**Enable unencrypted connections (http), using port**—Select this check box to enable unencrypted connections using a specified port.</span></span> <span data-ttu-id="029e8-137">[ポート] ボックスに、暗号化されていない接続を受け付けるサーバーポート (http) を入力します。</span><span class="sxs-lookup"><span data-stu-id="029e8-137">In the port box, enter the server port on which to accept unencrypted connections (http).</span></span>

   -   <span data-ttu-id="029e8-138">[**暗号化された接続 (https)、ポートを使用**する] —指定したポートを使って暗号化された接続を有効にするには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="029e8-138">**Enable encrypted connections (https), using port**—Select this check box to enable encrypted connections using a specified port.</span></span> <span data-ttu-id="029e8-139">[ポート] ボックスに、暗号化された接続を受け付けるサーバーポート (https) を入力します。</span><span class="sxs-lookup"><span data-stu-id="029e8-139">In the port box, enter the server port on which to accept encrypted connections (https).</span></span>

       <span data-ttu-id="029e8-140">Https は、MED-V サーバーと MED-V クライアントの間でセキュリティで保護されたトランザクションを確保するために設定できるオプションの構成です。</span><span class="sxs-lookup"><span data-stu-id="029e8-140">Https is an optional configuration which can be set to ensure secure transactions between the MED-V server and MED-V clients.</span></span> <span data-ttu-id="029e8-141">Https を構成するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="029e8-141">To configure https, you must perform the following procedures:</span></span>

       -   <span data-ttu-id="029e8-142">サーバー上で証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="029e8-142">Configure a certificate on the server.</span></span>

       -   <span data-ttu-id="029e8-143">Netsh を使って指定したポートにサーバー証明書を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="029e8-143">Associate the server certificate with the port specified using netsh.</span></span> <span data-ttu-id="029e8-144">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="029e8-144">For information, see the following:</span></span>

           -   [<span data-ttu-id="029e8-145">HTTP (ハイパーテキスト転送プロトコル) の Netsh コマンド</span><span class="sxs-lookup"><span data-stu-id="029e8-145">Netsh Commands for Hypertext Transfer Protocol (HTTP)</span></span>](https://go.microsoft.com/fwlink/?LinkId=183314)

           -   [<span data-ttu-id="029e8-146">方法: SSL 証明書を使用してポートを構成する</span><span class="sxs-lookup"><span data-stu-id="029e8-146">How to: Configure a Port with an SSL Certificate</span></span>](https://go.microsoft.com/fwlink/?LinkID=183315)

           -   [<span data-ttu-id="029e8-147">方法: SSL 証明書を使用してポートを構成する</span><span class="sxs-lookup"><span data-stu-id="029e8-147">How to: Configure a Port with an SSL Certificate</span></span>](https://msdn.microsoft.com/library/ms733791.aspx)

3. <span data-ttu-id="029e8-148">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029e8-148">Click **OK**.</span></span>

### <a href="" id="bkmk-configuringimages"></a><span data-ttu-id="029e8-149">画像の構成</span><span class="sxs-lookup"><span data-stu-id="029e8-149">Configuring Images</span></span>

**<span data-ttu-id="029e8-150">画像を構成するには</span><span class="sxs-lookup"><span data-stu-id="029e8-150">To configure images</span></span>**

1.  <span data-ttu-id="029e8-151">[**画像**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="029e8-151">Click the **Images** tab.</span></span>

2.  <span data-ttu-id="029e8-152">次のイメージ管理設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="029e8-152">Configure the following image management settings:</span></span>

    -   <span data-ttu-id="029e8-153">**VMs ディレクトリ**—仮想マシンディレクトリ (画像が保存されているディレクトリ)。</span><span class="sxs-lookup"><span data-stu-id="029e8-153">**VMs Directory**—The virtual machine directory (the directory where the images are stored).</span></span> <span data-ttu-id="029e8-154">このフィールドには、MED-V サーバーからアクセスできるイメージ配布サーバー上の画像ディレクトリへの UNC パスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="029e8-154">This field contains a UNC path to the image directory on the image distribution server that should be accessible from the MED-V server.</span></span>

    -   <span data-ttu-id="029e8-155">[ **VM URL**の指定: イメージが保存されているサーバーの場所。</span><span class="sxs-lookup"><span data-stu-id="029e8-155">**VMs URL**—The location of the server where the images are stored.</span></span>

3.  <span data-ttu-id="029e8-156">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029e8-156">Click **OK**.</span></span>

### <a href="" id="bkmk-configuringpermissions"></a><span data-ttu-id="029e8-157">権限を構成する</span><span class="sxs-lookup"><span data-stu-id="029e8-157">Configuring Permissions</span></span>

**<span data-ttu-id="029e8-158">権限を構成するには</span><span class="sxs-lookup"><span data-stu-id="029e8-158">To configure permissions</span></span>**

1.  <span data-ttu-id="029e8-159">[**権限**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="029e8-159">Click the **Permissions** tab.</span></span>

2.  <span data-ttu-id="029e8-160">ログインできるすべてのユーザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="029e8-160">A list of all users who can log in is provided.</span></span> <span data-ttu-id="029e8-161">ユーザーに読み取りと書き込みのアクセス許可を適用するには、ユーザーの横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="029e8-161">To apply read and write permissions to a user, select the check box next to the user.</span></span> <span data-ttu-id="029e8-162">ユーザーに読み取り専用のアクセス許可を適用するには、チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="029e8-162">To apply read-only permissions to a user, clear the check box.</span></span>

3.  <span data-ttu-id="029e8-163">ドメインユーザーまたはグループを追加するには、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029e8-163">To add domain users or groups, click **Add**.</span></span>

    <span data-ttu-id="029e8-164">[**ユーザーまたはグループ名の入力**] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="029e8-164">The **Enter User or Group names** dialog box appears.</span></span>

    1.  <span data-ttu-id="029e8-165">次のいずれかの操作を行って、ドメインのユーザーまたはグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="029e8-165">Select domain users or groups by doing one of the following:</span></span>

        -   <span data-ttu-id="029e8-166">[**ユーザーまたはグループ名の入力**] フィールドに、ドメイン内に存在するか、またはコンピューター上のローカルユーザーまたはグループとして存在するユーザーまたはグループを入力します。</span><span class="sxs-lookup"><span data-stu-id="029e8-166">In the **Enter User or Group names** field, type a user or group that exists in the domain or exists as a local user or group on the computer.</span></span> <span data-ttu-id="029e8-167">次に、[**名前の確認**] をクリックして、存在する完全な名前に解決します。</span><span class="sxs-lookup"><span data-stu-id="029e8-167">Then click **Check Names** to resolve it to the full existent name.</span></span>

        -   <span data-ttu-id="029e8-168">[**検索**] をクリックして、[標準の**ユーザーまたはグループの選択**] ダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="029e8-168">Click **Find** to open the standard **Select Users or Groups** dialog box.</span></span> <span data-ttu-id="029e8-169">次に、[ドメインユーザーまたはグループ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="029e8-169">Then select domain users or groups.</span></span>

    2.  <span data-ttu-id="029e8-170">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029e8-170">Click **OK**.</span></span>

4.  <span data-ttu-id="029e8-171">ドメインユーザーまたはグループを削除するには、ユーザーまたはグループを選択し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029e8-171">To remove domain users or groups, select a user or group and click **Remove**.</span></span>

5.  <span data-ttu-id="029e8-172">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029e8-172">Click **OK**.</span></span>

### <a href="" id="bkmk-configuringreports"></a><span data-ttu-id="029e8-173">レポートを構成する</span><span class="sxs-lookup"><span data-stu-id="029e8-173">Configuring Reports</span></span>

**<span data-ttu-id="029e8-174">レポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="029e8-174">To configure reports</span></span>**

1.  <span data-ttu-id="029e8-175">[**レポート**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="029e8-175">Click the **Reports** tab.</span></span>

2.  <span data-ttu-id="029e8-176">レポートをサポートするには、[**レポートを有効**にする] を選択します。</span><span class="sxs-lookup"><span data-stu-id="029e8-176">To support reports, select **Enable reports**.</span></span>

3.  <span data-ttu-id="029e8-177">[**接続文字列**] ボックスに、MSSQL データベースの接続文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="029e8-177">In the **Connection String** box, enter a connection string for the MSSQL database.</span></span>

    -   <span data-ttu-id="029e8-178">SQL Server がリモートサーバーにインストールされている場合は、次の接続文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="029e8-178">When SQL Server is installed on a remote server, use the following connection string:</span></span>

        `Data Source=<ServerName>;Initial Catalog=<DBName>;uid=sa;pwd=<Password>;`

        **<span data-ttu-id="029e8-179">注</span><span class="sxs-lookup"><span data-stu-id="029e8-179">Note</span></span>**  
        <span data-ttu-id="029e8-180">注: SQL Express に接続するには、次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="029e8-180">Note: To connect to SQL Express, use:</span></span> `Data Source=<ServerName>\sqlexpress.`



4.  <span data-ttu-id="029e8-181">データベースを作成するには、[**データベースの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029e8-181">To create the database, click **Create Database**.</span></span>

5.  <span data-ttu-id="029e8-182">接続をテストするには、[**接続テスト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029e8-182">To test the connection, click **Test Connection**.</span></span>

6.  <span data-ttu-id="029e8-183">データベースの消去オプションを構成するには、[**オプションのクリア**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="029e8-183">To configure database clearing options, click **Clear Options**.</span></span>

    <span data-ttu-id="029e8-184">[**データベースオプションのクリア**] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="029e8-184">The **Clear Database Options** dialog box appears.</span></span>

    1.  <span data-ttu-id="029e8-185">次のいずれかのオプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="029e8-185">Choose one of the following options:</span></span>

        -   <span data-ttu-id="029e8-186">[以下の日付**より古いデータをクリア**する (指定の日数よりも古いデータをクリアする)。[数値] ボックスに日数を入力します。</span><span class="sxs-lookup"><span data-stu-id="029e8-186">**Clear data older than**—Clear all data older than the number of days specified; in the number box, enter a number of days.</span></span>

        -   <span data-ttu-id="029e8-187">**データベースからすべてのデータを消去**—データベース内に存在するすべてのデータを消去します。</span><span class="sxs-lookup"><span data-stu-id="029e8-187">**Clear all data from database**—Clear all existent data in the database.</span></span>

        -   <span data-ttu-id="029e8-188">[データベースの削除 **]**: データベースを削除します。</span><span class="sxs-lookup"><span data-stu-id="029e8-188">**Drop database**—Delete the database.</span></span>

    2.  <span data-ttu-id="029e8-189">[ **OK** ] をクリックして変更を適用し、ダイアログボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="029e8-189">Click **OK** to apply changes and close the dialog box.</span></span>

7.  <span data-ttu-id="029e8-190">[ **OK** ] をクリックして変更を保存するか、[**キャンセル**] をクリックして、変更を保存せずにダイアログボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="029e8-190">Click **OK** to save the changes, or click **Cancel** to close the dialog box without saving changes.</span></span>

8.  <span data-ttu-id="029e8-191">メッセージが表示されたら、MED-V サーバーサービスを再起動して、ネットワーク設定に変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="029e8-191">If prompted, restart the MED-V server service to apply changes to the network settings.</span></span>

## <span data-ttu-id="029e8-192">関連トピック</span><span class="sxs-lookup"><span data-stu-id="029e8-192">Related topics</span></span>


[<span data-ttu-id="029e8-193">サポートされる構成</span><span class="sxs-lookup"><span data-stu-id="029e8-193">Supported Configurations</span></span>](supported-configurationsmedv-orientation.md)

[<span data-ttu-id="029e8-194">MED-V サーバー インフラストラクチャを設計する</span><span class="sxs-lookup"><span data-stu-id="029e8-194">Design the MED-V Server Infrastructure</span></span>](design-the-med-v-server-infrastructure.md)









