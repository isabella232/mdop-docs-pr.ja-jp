---
title: MED-V ワークスペース パッケージを作成する
description: MED-V ワークスペース パッケージを作成する
author: dansimp
ms.assetid: 3f75fe73-41ac-4389-ae21-5efb2d437f4d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e20cf4cc9394c4a5e90178fff4fc36ed83c12d60
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823264"
---
# <span data-ttu-id="71643-103">MED-V ワークスペース パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="71643-103">Create a MED-V Workspace Package</span></span>


<span data-ttu-id="71643-104">MED-V ワークスペースとは、エンドユーザーが MED-V によって提供される仮想マシンと対話する Windows XP デスクトップ環境です。</span><span class="sxs-lookup"><span data-stu-id="71643-104">A MED-V workspace is the Windows XP desktop environment where end users interact with the virtual machine provided by MED-V.</span></span> <span data-ttu-id="71643-105">管理者が、MED-V ワークスペースを作成し、カスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="71643-105">The administrator creates and customizes the MED-V workspace.</span></span> <span data-ttu-id="71643-106">ワークスペースは、MED-V ワークスペースの規則と機能を定義するイメージとグループポリシーで構成されます。</span><span class="sxs-lookup"><span data-stu-id="71643-106">The workspace consists of an image and the Group Policy that defines the rules and functionality of the MED-V workspace.</span></span>

<span data-ttu-id="71643-107">独自の構成、設定、およびルールを使用してカスタマイズされた、複数の MED-V ワークスペースを作成できます。</span><span class="sxs-lookup"><span data-stu-id="71643-107">You can create multiple MED-V workspaces, each customized with its own configuration, settings, and rules.</span></span> <span data-ttu-id="71643-108">ユーザー、グループ、または複数のユーザーまたはグループを各 MED-V ワークスペースに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="71643-108">A user, group, or multiple users or groups can be associated with each MED-V workspace.</span></span> <span data-ttu-id="71643-109">カスタマイズを行うと、そのユーザーまたはグループに対してのみ、MED-V ワークスペースを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="71643-109">The customization makes that MED-V workspace available only for that user or group.</span></span>

<span data-ttu-id="71643-110">**Med-v Workspace パッケージャー**を使って、med-v ワークスペースを作成します。</span><span class="sxs-lookup"><span data-stu-id="71643-110">Use the **MED-V Workspace Packager** to create MED-V workspaces.</span></span> <span data-ttu-id="71643-111">**Med-v ワークスペースパッケージャー**は、次の2つの主なセクションに分かれています。</span><span class="sxs-lookup"><span data-stu-id="71643-111">The **MED-V Workspace Packager** is divided into two main sections:</span></span>

-   <span data-ttu-id="71643-112">MED-V ワークスペースの作成と管理に使う3つのボタンが含まれているメインパネル。</span><span class="sxs-lookup"><span data-stu-id="71643-112">A main panel that includes three buttons that you use to create and manage MED-V workspaces.</span></span> <span data-ttu-id="71643-113">[ **Med ワークスペースパッケージを作成**する] ボタンをクリックすると、med-v ワークスペースを作成するために使用する**Med ワークスペースパッケージの作成ウィザード**が開きます。</span><span class="sxs-lookup"><span data-stu-id="71643-113">The **Create a MED-V Workspace Package** button opens the **Create MED-V Workspace Package Wizard** that you use to create your MED-V workspaces.</span></span>

-   <span data-ttu-id="71643-114">Windows の右側の**ヘルプセンター**には、med-v ワークスペースの作成、テスト、管理に役立つ情報とガイダンスが記載されています。</span><span class="sxs-lookup"><span data-stu-id="71643-114">A **Help Center** on the right-hand side of the window that provides information and guidance to help you create, test, and manage your MED-V workspaces.</span></span>

**<span data-ttu-id="71643-115">重要</span><span class="sxs-lookup"><span data-stu-id="71643-115">Important</span></span>**  
<span data-ttu-id="71643-116">**Med-v Workspace パッケージャー**を使用するには、まず、Windows PowerShell の実行ポリシーが [制限なし] に設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71643-116">Before you can use the **MED-V Workspace Packager**, you must first make sure that the Windows PowerShell execution policy is set to Unrestricted.</span></span>

`Set-ExecutionPolicy Unrestricted`

<span data-ttu-id="71643-117">さらに、 **Med-v ワークスペースパッケージャー**を実行するコンピューターの SAN ポリシーは、"オンラインですべて" に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="71643-117">In addition, the SAN policy for the computer on which the **MED-V Workspace Packager** is run must be set to “Online All”.</span></span> <span data-ttu-id="71643-118">SAN ポリシーの設定を確認するには、管理者の資格情報を使用して、コマンドプロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="71643-118">To check the setting of the SAN policy, run the following commands at a command prompt with administrative credentials:</span></span>

`diskpart.exe`

`DISKPART> san`

`DISKPART> exit`

<span data-ttu-id="71643-119">必要に応じて、管理者の資格情報を使用して、コマンドプロンプトで次のコマンドを入力して、SAN ポリシーを "オンライン" に変更します。</span><span class="sxs-lookup"><span data-stu-id="71643-119">If it is necessary, change the SAN policy to "Online All" by typing the following commands at the command prompt with administrative credentials:</span></span>

`diskpart.exe`

`DISKPART> san policy=onlineall`

`DISKPART> exit`



**<span data-ttu-id="71643-120">重要</span><span class="sxs-lookup"><span data-stu-id="71643-120">Important</span></span>**  
<span data-ttu-id="71643-121">仮想ハードディスクのマウントと MED-V ワークスペースパッケージの構築に使用するコンピューターに、自動ディスク暗号化ソフトウェアがインストールされている場合は、起動する前にソフトウェアを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="71643-121">If automatic disk encryption software is installed on the computer that you use to mount the virtual hard disk and build the MED-V workspace package, you must disable the software before you start.</span></span> <span data-ttu-id="71643-122">それ以外の場合は、他のコンピューターで MED-V ワークスペースを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="71643-122">Otherwise, you cannot use the MED-V workspace on any other computer.</span></span>



<span data-ttu-id="71643-123">ここで提供する情報は、MED-V ワークスペース展開パッケージの作成に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="71643-123">The information we provide here can help you create your MED-V workspace deployment package.</span></span>

## <a href="" id="bkmk-prereq"></a><span data-ttu-id="71643-124">前提条件</span><span class="sxs-lookup"><span data-stu-id="71643-124">Prerequisites</span></span>


<span data-ttu-id="71643-125">MED-V ワークスペース展開パッケージの作成を開始する前に、次のアイテムへのアクセス権があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="71643-125">Before you start to build your MED-V workspace deployment package, verify that you have access to the following items:</span></span>

-   **<span data-ttu-id="71643-126">Windows XP の準備された画像</span><span class="sxs-lookup"><span data-stu-id="71643-126">A prepared Windows XP image</span></span>**

    <span data-ttu-id="71643-127">MED-V で使用する Windows XP イメージを作成する方法の詳細については、「 [Med-v イメージを準備](prepare-a-med-v-image.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71643-127">For more information about how to create a Windows XP image for use with MED-V, see [Prepare a MED-V Image](prepare-a-med-v-image.md).</span></span>

-   **<span data-ttu-id="71643-128">URL リダイレクション情報が含まれているテキストファイルまたはリスト</span><span class="sxs-lookup"><span data-stu-id="71643-128">A text file or list that contains URL redirection information</span></span>**

    <span data-ttu-id="71643-129">URL リダイレクションテキストファイルまたはリストには、ホストコンピューターから、MED-V ワークスペースの Internet Explorer にリダイレクトする Url が含まれています。</span><span class="sxs-lookup"><span data-stu-id="71643-129">Your URL redirection text file or list contains those URLs that you want redirected from the host computer to Internet Explorer in the MED-V workspace.</span></span> <span data-ttu-id="71643-130">パッケージウィザードを使って MED-V ワークスペースを作成する場合は、このリダイレクト情報をインポート、入力、またはコピーして貼り付けて、パッケージの作成プロセスのいずれかの手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="71643-130">When you are using the packaging wizard to create your MED-V workspace, you import, type, or copy and paste this redirection information as one of the steps in the package creation process.</span></span>

    **<span data-ttu-id="71643-131">注</span><span class="sxs-lookup"><span data-stu-id="71643-131">Note</span></span>**  
    <span data-ttu-id="71643-132">MED-V の URL リダイレクションは、プロトコル HTTP と HTTPS のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="71643-132">URL redirection in MED-V only supports the protocols HTTP and HTTPS.</span></span> <span data-ttu-id="71643-133">MED-V では、FTP やその他のプロトコルのサポートは提供されません。</span><span class="sxs-lookup"><span data-stu-id="71643-133">MED-V does not provide support for FTP or any other protocols.</span></span>



~~~
Enter each web address on a single line, for example:

http://www.contoso.com/webapps/webapp1

http://www.contoso.com/webapps/webapp2

http://\*.contoso.com

http://www.contoso.com/webapps/\*

**Important**  
If you import a text file that includes a URL that uses special characters (such as ~ ! @ \# and so on), make sure that you specify UTF-8 encoding when you save the text file. Special characters do not import correctly into the MED-V Workspace Packager if the text file was saved using the default ANSI encoding.
~~~



## <span data-ttu-id="71643-134">MED-V workspace パッケージャーコンピューターの言語以外の言語の MED-V ワークスペースをパッケージ化する</span><span class="sxs-lookup"><span data-stu-id="71643-134">Packaging a MED-V Workspace for a Language Other than the Language of the MED-V Workspace Packager Computer</span></span>


<span data-ttu-id="71643-135">既定では、MED-V ワークスペースでは、コンピューターの言語と英語の文字の文字がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="71643-135">By default, the MED-V workspace supports characters in both the language of the computer and in English.</span></span> <span data-ttu-id="71643-136">コンピューターにインストールされているもの以外の言語用の MED-V ワークスペースを作成するには、MED-V のワークスペース名の後に、PowerShell スクリプト (. ps1) に **-loc \ [locale \]** を指定します。</span><span class="sxs-lookup"><span data-stu-id="71643-136">To create a MED-V workspace for a language other than the one installed on the computer, specify **-loc \[locale\]** in the PowerShell script (.ps1) after the MED-V workspace name.</span></span>

<span data-ttu-id="71643-137">Med-v workspace パッケージャーコンピューターの既定の言語以外の言語で MED ワークスペースパッケージを作成するには、MED-V ワークスペースパッケージャーを実行し、ロケールに応じて出力スクリプトを変更して、既定の言語でスクリプトを生成します。</span><span class="sxs-lookup"><span data-stu-id="71643-137">To create a MED-V workspace package in a language other than the default language of the MED-V Workspace Packager computer, generate a script in the default language by running the MED-V Workspace Packager and then modifying the output script as required for your locale.</span></span> <span data-ttu-id="71643-138">このスクリプトは、パッケージ化時に指定された MED-V ワークスペースの出力ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="71643-138">The script is located in the MED-V workspace output directory that was specified during packaging.</span></span> <span data-ttu-id="71643-139">ロケール設定の名前はにあります。次のディレクトリにあるファイルを WXL します。</span><span class="sxs-lookup"><span data-stu-id="71643-139">The names of the locale settings are on the .WXL files in the following directory:</span></span>

<span data-ttu-id="71643-140">Virtualization\\WindowsPowerShell\\Modules\\Microsoft.Medv.Administration.Commands.WorkspacePackager\\locale ¥¥ \\ Microsoft Enterprise デスクトップ</span><span class="sxs-lookup"><span data-stu-id="71643-140">C:\\Program Files\\Microsoft Enterprise Desktop Virtualization\\WindowsPowerShell\\Modules\\Microsoft.Medv.Administration.Commands.WorkspacePackager\\locale</span></span>

## <span data-ttu-id="71643-141">MED-V ワークスペースパッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="71643-141">Creating a MED-V Workspace Package</span></span>


<span data-ttu-id="71643-142">MED-V ワークスペースパッケージを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="71643-142">To create a MED-V workspace package, follow these steps:</span></span>

****

1.  <span data-ttu-id="71643-143">**Med-v ワークスペースのパッケージャー**を開くには、 **[スタート**]、[**すべてのプログラム**]、[ **Microsoft Enterprise デスクトップ仮想化**]、[ **med-v workspace パッケージャー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="71643-143">To open the **MED-V Workspace Packager**, click **Start**, click **All Programs**, click **Microsoft Enterprise Desktop Virtualization**, and then click **MED-V Workspace Packager**.</span></span>

2.  <span data-ttu-id="71643-144">**Med-v ワークスペースパッケージャー**メインパネルで、[ **Med-v ワークスペースパッケージの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="71643-144">On the **MED-V Workspace Packager** main panel, click **Create a MED-V Workspace Package**.</span></span>

    <span data-ttu-id="71643-145">MED-V を作成する med-v**ワークスペースパッケージウィザード**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="71643-145">The MED-V **Create MED-V Workspace Package Wizard** appears.</span></span> <span data-ttu-id="71643-146">このウィザードは、次のページで構成されています。</span><span class="sxs-lookup"><span data-stu-id="71643-146">The wizard consists of the following pages:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="71643-147">パッケージ情報</span><span class="sxs-lookup"><span data-stu-id="71643-147">Package Information</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="71643-148">MED-V ワークスペースの名前を指定し、MED-V ワークスペースパッケージファイルが保存されているフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="71643-148">Specify a name for the MED-V workspace and select a folder where the MED-V workspace package files are saved.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="71643-149">Windows XP のイメージを選ぶ</span><span class="sxs-lookup"><span data-stu-id="71643-149">Select Windows XP Image</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="71643-150">Windows XP の仮想 PC イメージを準備します。</span><span class="sxs-lookup"><span data-stu-id="71643-150">Specify your prepared Windows XP Virtual PC image.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="71643-151">初回のセットアップ</span><span class="sxs-lookup"><span data-stu-id="71643-151">First Time Setup</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="71643-152">初回のセットアップ時に実行される MED-V のセットアッププロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="71643-152">Specify the setup process that MED-V follows during first time setup.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="71643-153">MED-V メッセージ</span><span class="sxs-lookup"><span data-stu-id="71643-153">MED-V Messages</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="71643-154">最初のセットアップ時にエンドユーザーに表示されるヘルプ情報のメッセージと省略可能な URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="71643-154">Specify the messages and optional URL for Help information that the end user sees during first time setup.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="71643-155">コンピューターに名前を付ける</span><span class="sxs-lookup"><span data-stu-id="71643-155">Naming Computers</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="71643-156">MED-V 仮想マシンの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="71643-156">Specify how the MED-V virtual machine is named.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="71643-157">ホストから設定をコピーする</span><span class="sxs-lookup"><span data-stu-id="71643-157">Copy Settings from Host</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="71643-158">MED-V ワークスペースの設定を定義する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="71643-158">Specify how the settings for the MED-V workspace are defined.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="71643-159">起動とネットワーク</span><span class="sxs-lookup"><span data-stu-id="71643-159">Startup and Networking</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="71643-160">MED-V ワークスペース、ネットワーク、ユーザーの資格情報を開始するための設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="71643-160">Specify the settings for starting the MED-V workspace, networking, and user credentials.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong><span data-ttu-id="71643-161">Web リダイレクション</span><span class="sxs-lookup"><span data-stu-id="71643-161">Web Redirection</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="71643-162">MED-V ワークスペースの Internet Explorer にリダイレクトするテキストファイルまたは Url の一覧を指定します。</span><span class="sxs-lookup"><span data-stu-id="71643-162">Specify a text file or a list of the URLs you want redirected to Internet Explorer in the MED-V workspace.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="71643-163">まとめ</span><span class="sxs-lookup"><span data-stu-id="71643-163">Summary</span></span></strong></p></td>
    <td align="left"><p><span data-ttu-id="71643-164">MED-V ワークスペースの設定を確認し、MED-V ワークスペース展開パッケージの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="71643-164">Verify your MED-V workspace settings and start to build your MED-V workspace deployment package.</span></span></p></td>
    </tr>
    </tbody>
    </table>



3.  <span data-ttu-id="71643-165">[**パッケージ情報**] ページで、med-v ワークスペースの名前を入力し、med-v ワークスペースパッケージファイルが保存されているフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="71643-165">On the **Package Information** page, enter a name for the MED-V workspace and select a folder where the MED-V workspace package files are saved.</span></span>

    **<span data-ttu-id="71643-166">Warning</span><span class="sxs-lookup"><span data-stu-id="71643-166">Warning</span></span>**  
    <span data-ttu-id="71643-167">MED-V ワークスペースに名前を指定し、続行するフォルダーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71643-167">You must name the MED-V workspace and specify a folder to continue.</span></span>



~~~
After you have finished, click **Next**.
~~~

4. <span data-ttu-id="71643-168">**[WINDOWS Xp イメージの選択**] ページで、準備済みの MED-V Windows XP 仮想 PC イメージ (.vhd ファイル) の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="71643-168">On the **Select Windows XP Image** page, specify the location of your prepared MED-V Windows XP Virtual PC image (.vhd file).</span></span>

   **<span data-ttu-id="71643-169">Warning</span><span class="sxs-lookup"><span data-stu-id="71643-169">Warning</span></span>**  
   <span data-ttu-id="71643-170">続行するには、Windows XP の VHD イメージを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71643-170">You must specify a Windows XP VHD image to continue.</span></span>



~~~
After you have finished, click **Next**.
~~~

5. <span data-ttu-id="71643-171">[**初回セットアップ**] ページで、有人または無人での初回セットアップを実行するかどうか、または共有コンピューターのすべてのエンドユーザーに対して個別に使用するか、または使用するかを選択します。</span><span class="sxs-lookup"><span data-stu-id="71643-171">On the **First Time Setup** page, select whether you want first time setup to run while attended or unattended and whether you want the MED-V workspace used separately or used by all end users on a shared computer.</span></span>

   <span data-ttu-id="71643-172">**通知なしで無人セットアップ**を選択した場合、セットアップを初めて実行する前にエンドユーザーには通知されず、最初のセットアップ時に仮想マシンがエンドユーザーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="71643-172">If you select **Unattended setup, without any notification**, the end user is not informed before first time setup is run and the virtual machine is not shown to the end user during first time setup.</span></span> <span data-ttu-id="71643-173">さらに、最初に完全無人モードで実行された場合、メッセージは必要ないため、ウィザードの**Med-v メッセージ**ページは非表示になっています。</span><span class="sxs-lookup"><span data-stu-id="71643-173">In addition, the **MED-V Messages** page of the wizard is hidden because no messages are required if first time setup runs in a completely unattended mode.</span></span>

   <span data-ttu-id="71643-174">[無人セットアップ] を選択した**が、最初にセットアップを開始する前にエンド**ユーザーに通知する場合、セットアップが初めて実行される前にエンドユーザーに通知されます。</span><span class="sxs-lookup"><span data-stu-id="71643-174">If you select **Unattended setup, but notify end users before first time setup begins**, the end user is informed before first time setup is run.</span></span> <span data-ttu-id="71643-175">ただし、仮想マシンは、初めてセットアップするときにエンドユーザーに表示されません。</span><span class="sxs-lookup"><span data-stu-id="71643-175">However, the virtual machine is not shown to the end user during first time setup.</span></span>

   <span data-ttu-id="71643-176">エンドユーザーが初めてセットアップするときに情報を入力する必要がある場合は、[**有人セットアップ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="71643-176">Select **Attended setup** if the end user must enter information during first time setup.</span></span>

   <span data-ttu-id="71643-177">既定の動作は**無人セットアップですが、最初のセットアップが開始される前にエンドユーザーに通知**します。</span><span class="sxs-lookup"><span data-stu-id="71643-177">The default behavior is **Unattended setup, but notify end users before first time setup begins**.</span></span>

   **<span data-ttu-id="71643-178">注意</span><span class="sxs-lookup"><span data-stu-id="71643-178">Caution</span></span>**  
   <span data-ttu-id="71643-179">Mini-setup ファイルを作成して、ミニセットアップでユーザーの入力を完了する必要がある場合は、[**有人セットアップ**] を選択するか、初めてセットアップするときに問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="71643-179">If you created the Sysprep.inf file so that Mini-Setup requires user input to complete, you must select **Attended setup** or problems might occur during first time setup.</span></span>



~~~
You can also specify how a MED-V workspace is used on computers that are shared by multiple end users. You can decide that you want to create a unique MED-V workspace for each end user or that you want the MED-V workspace made available to all end users who share the computer. The default is that the MED-V workspace is unique for each end user.

**Important**  
We recommend that you disable the fast user switching feature in Windows if you configure the MED-V workspace to be accessed by all users on a shared computer. Problems can occur if an end user logs on by using the fast user switching feature in Windows when another user is still logged on.



**Tip**  
When you create a name mask for the MED-V workspace on the **Naming Computers** page, make sure that each virtual machine on a shared computer has a unique computer name.



You can also specify whether the MED-V workspace is added to the Administrators group or administrator credentials are managed outside MED-V. By default, the MED-V workspace is not automatically added to the Administrators group.

After you have finished, click **Next**.
~~~

6. <span data-ttu-id="71643-180">[ **MED メッセージ**] ページで、最初のセットアップ時にエンドユーザーに表示される次のメッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="71643-180">On the **MED-V Messages** page, specify the following messages that the end user sees during first time setup:</span></span>

   -   <span data-ttu-id="71643-181">エンドユーザーが最初にセットアップを開始したときに表示されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="71643-181">The message that the end user sees when first time setup starts.</span></span>

   -   <span data-ttu-id="71643-182">初めてセットアップに失敗した場合またはエラーが発生した場合にエンドユーザーに表示されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="71643-182">The message that the end user sees if first time setup fails or an error occurs.</span></span>

   **<span data-ttu-id="71643-183">注</span><span class="sxs-lookup"><span data-stu-id="71643-183">Note</span></span>**  
   <span data-ttu-id="71643-184">[**無人セットアップ]** が選択さ**れている**場合、ウィザードの [ **med-v メッセージ**] ページは表示されません。</span><span class="sxs-lookup"><span data-stu-id="71643-184">The **MED-V Messages** page of the wizard is hidden if you selected **Unattended setup, without any notification** on the **First Time Setup** page.</span></span>



~~~
You can also specify an optional URL location for help information that is provided to the end user when first time setup is running.

For example, the URL can point to an internal IT webpage with answers to questions such as "How long will this take and how will I know when it has completed?" or "What do you do if you get an error message?"

**Note**  
If you specify a URL, a link is shown during first time setup that points the end user to this help information. If you do not specify a URL, no link is provided.



After you have finished, click **Next**.
~~~

7. <span data-ttu-id="71643-185">[**コンピューターの名前付け**] ページでは、コンピューターの名前付けを med-v で管理するか、Sysprep などのシステム管理ツールで管理するかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="71643-185">On the **Naming Computers** page, you can specify whether computer naming is managed by MED-V or by a system management tool, such as Sysprep.</span></span> <span data-ttu-id="71643-186">既定では、コンピューターの名前付けはシステム管理ツールによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="71643-186">The default is that computer naming is managed by a system management tool.</span></span>

   <span data-ttu-id="71643-187">コンピューターの名前付けが MED-V で管理されるように指定する場合は、ドロップダウンリストから定義済みのコンピューターの名前付け規則 (マスク) を選択します。</span><span class="sxs-lookup"><span data-stu-id="71643-187">If you specify that computer naming is managed by MED-V, select a predefined computer naming convention (mask) from the drop-down list.</span></span> <span data-ttu-id="71643-188">サンプルのコンピューター名のプレビューは、MED-V ワークスペースパッケージの作成に使用しているコンピューターに基づいて表示されます。</span><span class="sxs-lookup"><span data-stu-id="71643-188">A preview of a sample computer name appears that is based on the computer that you are using to build the MED-V workspace package.</span></span>

   <span data-ttu-id="71643-189">カスタムの名前付け規則のいずれかを選択すると、指定できるフィールドは次の文字に制限されます。</span><span class="sxs-lookup"><span data-stu-id="71643-189">If you select one of the custom naming conventions, the fields you can specify are limited to the following characters:</span></span>

   -   <span data-ttu-id="71643-190">"プレフィックス" フィールドと "敬称" フィールドの文字数は、A ~ Z、a ~ z、0-9、特殊文字に制限されています。</span><span class="sxs-lookup"><span data-stu-id="71643-190">The prefix and suffix fields are limited to the characters A-Z, a-z, 0-9, and the special characters !</span></span> <span data-ttu-id="71643-191">@ \ # $% ^ & ()-\ _ ' {}</span><span class="sxs-lookup"><span data-stu-id="71643-191">@ \# $ % ^ & ( ) - \_ ' { } .</span></span> <span data-ttu-id="71643-192">~.</span><span class="sxs-lookup"><span data-stu-id="71643-192">and ~.</span></span>

   -   <span data-ttu-id="71643-193">[Hostname] および [username] フィールドは、0 ~ 9 の数字に制限されています。</span><span class="sxs-lookup"><span data-stu-id="71643-193">The hostname and username fields are limited to the digits 0 through 9.</span></span>

   **<span data-ttu-id="71643-194">重要</span><span class="sxs-lookup"><span data-stu-id="71643-194">Important</span></span>**  
   <span data-ttu-id="71643-195">コンピューター名は一意であり、最大15文字に制限されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="71643-195">Computer names must be unique and are limited to a maximum of 15 characters.</span></span> <span data-ttu-id="71643-196">コンピューターの名前付け方法を決定する際には、複数のコンピューターを所有している、またはコンピューターを共有しているエンドユーザーを検討してください。また、ネットワークで競合を引き起こす可能性のあるコンピューター名のマスクを使用しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="71643-196">When you decide on your computer naming method, consider end users who have multiple computers or that share a computer, and avoid using computer name masks that could cause a collision on the network.</span></span>



~~~
**Caution**  
The computer name settings that you specify on this page override those specified in the Sysprep.inf answer file.



After you have finished, click **Next**.
~~~

8. <span data-ttu-id="71643-197">[**ホストからの設定のコピー** ] ページでは、次の設定を選択して、med-v ワークスペースの構成方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="71643-197">On the **Copy Settings from Host** page, you can select the following settings to specify how the MED-V workspace is configured:</span></span>

   **<span data-ttu-id="71643-198">注意</span><span class="sxs-lookup"><span data-stu-id="71643-198">Caution</span></span>**  
   <span data-ttu-id="71643-199">このページで指定した設定は、ホストコンピューターから MED-V ワークスペースにコピーされます。これは、Sysprep.inf 応答ファイルで指定された設定より優先されます。</span><span class="sxs-lookup"><span data-stu-id="71643-199">The settings that you specify on this page that are copied from the host computer to the MED-V workspace override those specified in the Sysprep.inf answer file.</span></span>



~~~
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Copy regional settings</strong></p></td>
<td align="left"><p>Select this check box to copy the regional settings from the host computer to the MED-V workspace.</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>If you select this check box, the following settings are set in the Sysprep.inf file:</p>
<pre class="syntax" space="preserve"><code>[RegionalSettings]
Language
SystemLocale
UserLocale
UserLocale_DefaultUser
InputLocale
InputLocale_DefaultUser
</code></pre></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Copy user settings</strong></p></td>
<td align="left"><p>Select this check box to copy certain user settings, such as user name and company name, from the host to the MED-V workspace.</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>If you select this check box, the following settings are set in the Sysprep.inf file:</p>
<pre class="syntax" space="preserve"><code>[UserData]
OrgName
FullName</code></pre>
<div class="alert">
<strong>Note</strong>  
<p>Personal settings, such as Internet browsing history, are not copied over to the MED-V workspace.</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Copy domain name</strong></p></td>
<td align="left"><p>Select this check box to let the guest join the same domain as the host.</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><div class="alert">
<strong>Important</strong>  
<p>The MED-V guest must be configured to join a domain that lets users log on by using the credentials that they use to log on to the MED-V host.</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Copy domain organizational unit</strong></p></td>
<td align="left"><p>Select this check box to copy the domain organizational unit from the host computer to the MED-V workspace. This check box is only enabled if you select to copy the domain name from the host computer.</p></td>
</tr>
</tbody>
</table>



After you have finished, click **Next**.
~~~

9. <span data-ttu-id="71643-200">[**起動とネットワーク**] ページでは、次の設定の既定の動作を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="71643-200">On the **Startup and Networking** page, you can change the default behavior for the following settings:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="71643-201">MED-V ワークスペースを開始する</span><span class="sxs-lookup"><span data-stu-id="71643-201">Start MED-V workspace</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="71643-202">ユーザーのログオン時に MED-V workspace を起動するか、最初に使用するか、またはエンドユーザーが MED-V ワークスペースを開始するタイミングを決定できるようにするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="71643-202">Choose whether to start the MED-V workspace at user logon, at first use, or to let the end user decide when the MED-V workspace starts.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p><span data-ttu-id="71643-203">MED-V ワークスペースは、エンドユーザーがログオンしたとき、または公開されたアプリケーションを開くときや、リダイレクトが必要な URL を入力するときなど、MED-V が必要なアクションを最初に開始したときに、次の2つの方法のいずれかで開始されます。</span><span class="sxs-lookup"><span data-stu-id="71643-203">The MED-V workspace starts in one of two ways: either when the end user logs on or when they first start an action that requires MED-V, such as opening a published application or entering a URL that requires redirection.</span></span></p>
   <p><span data-ttu-id="71643-204">エンドユーザー向けにこの設定を定義するか、または MED-V の開始方法をエンドユーザーが制御できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="71643-204">You can either define this setting for the end user or let the end user control how MED-V starts.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="71643-205">注</span><span class="sxs-lookup"><span data-stu-id="71643-205">Note</span></span></strong><br/><p><span data-ttu-id="71643-206">エンドユーザーによって決定されたことを指定した場合、そのユーザーが遭遇する既定の動作は、ログオン時に MED-V ワークスペースが開始されることです。</span><span class="sxs-lookup"><span data-stu-id="71643-206">If you specify that the end user decides, the default behavior they experience is that the MED-V workspace starts when they log on.</span></span> <span data-ttu-id="71643-207">既定の設定を変更するには、通知領域の MED-V アイコンを右クリックし、[Med-v] の [ユーザー設定] を選び <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="71643-207">They can change the default by right-clicking the MED-V icon in the notification area and selecting <strong>MED-V User Settings</strong>.</span></span> <span data-ttu-id="71643-208">エンドユーザーに対してこの設定を定義した場合は、MED-V の開始方法を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="71643-208">If you define this setting for the end user, they cannot change how MED-V starts.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="71643-209">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="71643-209">Networking</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="71643-210">[ <strong> ネットワーク設定] で [共有] または [ブリッジ] を選択し </strong> <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="71643-210">Select <strong>Shared</strong> or <strong>Bridged</strong> for your networking setting.</span></span> <span data-ttu-id="71643-211">既定値は [共有されてい <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="71643-211">The default is <strong>Shared</strong>.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p><strong><span data-ttu-id="71643-212">共有 </strong> - Med-v workspace は、ネットワークアドレス変換 (NAT) を使って、発信トラフィック用にホスト&#39;s IP を共有します。</span><span class="sxs-lookup"><span data-stu-id="71643-212">Shared</strong> - The MED-V workspace uses Network Address Translation (NAT) to share the host&#39;s IP for outgoing traffic.</span></span></p>
   <p><strong><span data-ttu-id="71643-213">つなぎ </strong> - ます。 med-v ワークスペースには独自のネットワークアドレスがあり、通常は DHCP 経由で取得します。</span><span class="sxs-lookup"><span data-stu-id="71643-213">Bridged</strong> - The MED-V workspace has its own network address, typically obtained through DHCP.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="71643-214">資格情報を保存する</span><span class="sxs-lookup"><span data-stu-id="71643-214">Store credentials</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="71643-215">エンドユーザーの資格情報を保存するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="71643-215">Choose whether you want to store the end user credentials.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p><span data-ttu-id="71643-216">既定の動作では、資格情報の保存機能が無効になっているため、ユーザーがログオンするたびにエンドユーザーの認証を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="71643-216">The default behavior is that credential storing is disabled so that the end user must be authenticated every time that they log on.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="71643-217">重要</span><span class="sxs-lookup"><span data-stu-id="71643-217">Important</span></span></strong><br/><p><span data-ttu-id="71643-218">エンドユーザーの資格情報をキャッシュすると、ユーザーエクスペリエンスが最大限に向上しますが、そのリスクについて注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71643-218">Even though caching the end user’s credentials provides the best user experience, you should be aware of the risks involved.</span></span></p>
   <p><span data-ttu-id="71643-219">エンドユーザーのドメイン資格情報は、Windows Credential Manager の元に戻す形式で格納されます。</span><span class="sxs-lookup"><span data-stu-id="71643-219">The end user’s domain credential is stored in a reversible format in the Windows Credential Manager.</span></span> <span data-ttu-id="71643-220">このため、攻撃者は、パスワードを取得してユーザーの資格情報にアクセスできるプログラムを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="71643-220">As a result, an attacker could write a program that retrieves the password and could gain access to the user’s credentials.</span></span> <span data-ttu-id="71643-221">このリスクを軽減するには、エンドユーザーの資格情報の保存を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="71643-221">You can only lessen this risk by disabling the storing of end-user credentials.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



~~~
After you have finished, click **Next**.
~~~

10. <span data-ttu-id="71643-222">[ **Web リダイレクション**] ページでは、med-v ワークスペースの Internet Explorer にリダイレクトされる url の一覧を入力、貼り付け、またはインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="71643-222">On the **Web Redirection** page, you can enter, paste, or import a list of the URLs that are redirected to Internet Explorer in the MED-V workspace.</span></span> <span data-ttu-id="71643-223">URL リダイレクション情報を構成する方法の詳細については、「[前提条件](#bkmk-prereq)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71643-223">For more information about how to configure your URL redirection information, see [Prerequisites](#bkmk-prereq).</span></span>

   <span data-ttu-id="71643-224">また、MED-V ワークスペースの Internet Explorer がエンドユーザーに対してどのように構成されるかを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="71643-224">You can also specify how Internet Explorer in the MED-V workspace is configured for end users.</span></span> <span data-ttu-id="71643-225">既定では、インターネットゾーンのセキュリティレベルは [高] に設定されています。</span><span class="sxs-lookup"><span data-stu-id="71643-225">By default, the Internet zone security level is set to High.</span></span> <span data-ttu-id="71643-226">また、アドレスバーなどの一部の既定の参照機能も削除されます。</span><span class="sxs-lookup"><span data-stu-id="71643-226">Also, certain default browsing capabilities, such as the address bar, are removed.</span></span> <span data-ttu-id="71643-227">MED-V ワークスペースの Internet Explorer の既定の構成では、より安全な参照環境がエンドユーザーに提供されます。</span><span class="sxs-lookup"><span data-stu-id="71643-227">This default configuration of Internet Explorer in the MED-V workspace provides a more secure browsing environment for end users.</span></span>

   **<span data-ttu-id="71643-228">注意</span><span class="sxs-lookup"><span data-stu-id="71643-228">Caution</span></span>**  
   <span data-ttu-id="71643-229">既定の設定を変更することで、MED-V ワークスペースで Internet Explorer をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="71643-229">By changing the default settings, you can customize Internet Explorer in the MED-V workspace.</span></span> <span data-ttu-id="71643-230">ただし、既定の設定を変更してセキュリティを保護しないようにすると、Internet Explorer の以前のバージョンで使用されているセキュリティ上のリスクに組織が公開されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="71643-230">However, realize that if you change the default settings so as to make them less secure, you can expose your organization to those security risks that are present in older versions of Internet Explorer.</span></span> <span data-ttu-id="71643-231">詳細については、「 [Med-v 操作のセキュリティのベストプラクティス](security-best-practices-for-med-v-operations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71643-231">For more information, see [Security Best Practices for MED-V Operations](security-best-practices-for-med-v-operations.md).</span></span>



~~~
After you have finished, click **Next**.
~~~

11. <span data-ttu-id="71643-232">[**概要**] ページで、この med-v ワークスペースのパッケージ設定を確認できます。</span><span class="sxs-lookup"><span data-stu-id="71643-232">On the **Summary** page, you can review the packaging settings for this MED-V workspace.</span></span> <span data-ttu-id="71643-233">設定を変更する場合は、[**前**へ] ボタンをクリックして、関連するページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="71643-233">If you want to change any settings, click the **Previous** button to return to the relevant page.</span></span> <span data-ttu-id="71643-234">設定の確認が完了したら、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="71643-234">After you have finished reviewing the settings, click **Create**.</span></span>

   <span data-ttu-id="71643-235">パッケージの作成の進行状況を表示するために、 **MED ワークスペースパッケージの作成ウィザード**の [**完了**] ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="71643-235">The **Completion** page of the **Create MED-V Workspace Package Wizard** opens to show the progress of the package creation.</span></span>

   **<span data-ttu-id="71643-236">注</span><span class="sxs-lookup"><span data-stu-id="71643-236">Note</span></span>**  
   <span data-ttu-id="71643-237">指定した VHD のサイズによっては、MED-V ワークスペースパッケージの作成プロセスが完了するまで数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="71643-237">The MED-V workspace package creation process might take several minutes to complete, depending on the size of the VHD specified.</span></span>



~~~
If the MED-V workspace package is created successfully, the **Completion** page displays a list of the files that you created and their respective locations. The following is a list of the files that are created and their descriptions:

-   **setup.exe**—an installation program that you deploy and run on end-user computers to install the MED-V workspaces.

-   **&lt;*workspace\_name*&gt;.msi**—an installer file that you deploy to the end-user computers. The setup.exe file will run this file to install the MED-V workspaces.

-   **&lt;*vhd\_name*&gt;.medv**—a compressed VHD file that you deploy to the end-user computers. The setup.exe file uses it when it installs the MED-V workspaces.

-   **&lt;*workspace\_name*&gt;.reg**—the configuration settings that are installed when the setup.exe, &lt;*workspace\_name*&gt;.msi, and &lt;*vhd\_name*&gt;.medv files are deployed and setup.exe is run.

-   **&lt;*workspace\_name*&gt;.ps1**—a Windows PowerShell script that you can use to rebuild the registry file and re-build the MED-V workspace package.

    **Important**  
    Before deployment, you can edit configuration settings by updating the .ps1 file that has your preferred method of script editing, such as Windows PowerShell. After you change the .ps1 file, use that file to rebuild the MED-V workspace package that you deploy to your enterprise. For more information, see [Configuring Advanced Settings by Using Windows PowerShell](configuring-advanced-settings-by-using-windows-powershell.md).

    However, after the MED-V workspace is deployed, you must edit configuration settings through the registry. For a list and description of the configuration settings, see [Managing MED-V Workspace Configuration Settings](managing-med-v-workspace-configuration-settings.md).
~~~



12. <span data-ttu-id="71643-238">[**閉じる**] をクリックしてパッケージウィザードを閉じ、 **Med-v ワークスペースパッケージャー**に戻ります。</span><span class="sxs-lookup"><span data-stu-id="71643-238">Click **Close** to close the packaging wizard and return to the **MED-V Workspace Packager**.</span></span>

<span data-ttu-id="71643-239">MED-V ワークスペースパッケージを展開する前にテストできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="71643-239">Your MED-V workspace package is now ready for testing before deployment.</span></span>

## <span data-ttu-id="71643-240">関連トピック</span><span class="sxs-lookup"><span data-stu-id="71643-240">Related topics</span></span>


[<span data-ttu-id="71643-241">Windows PowerShell を使用した高度な設定の構成</span><span class="sxs-lookup"><span data-stu-id="71643-241">Configuring Advanced Settings by Using Windows PowerShell</span></span>](configuring-advanced-settings-by-using-windows-powershell.md)

[<span data-ttu-id="71643-242">MED-V ワークスペース パッケージのテスト</span><span class="sxs-lookup"><span data-stu-id="71643-242">Testing the MED-V Workspace Package</span></span>](testing-the-med-v-workspace-package.md)

[<span data-ttu-id="71643-243">MED-V イメージを準備する</span><span class="sxs-lookup"><span data-stu-id="71643-243">Prepare a MED-V Image</span></span>](prepare-a-med-v-image.md)









