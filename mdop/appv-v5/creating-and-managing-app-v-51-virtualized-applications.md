---
title: App-V 5.1 仮想化アプリケーションの作成と管理
description: App-V 5.1 仮想化アプリケーションの作成と管理
author: dansimp
ms.assetid: 26be4331-88eb-4cfb-9d82-e63d7ee54576
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 207529fb5d5333694d31a82f44f08b35513dd4d4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814690"
---
# <span data-ttu-id="ac563-103">App-V 5.1 仮想化アプリケーションの作成と管理</span><span class="sxs-lookup"><span data-stu-id="ac563-103">Creating and Managing App-V 5.1 Virtualized Applications</span></span>


<span data-ttu-id="ac563-104">Microsoft Application Virtualization (App-v) 5.1 sequencer を適切に展開したら、それを使って、仮想化されたアプリケーションとして実行するアプリケーションのインストールとセットアップのプロセスを監視および記録することができます。</span><span class="sxs-lookup"><span data-stu-id="ac563-104">After you have properly deployed the Microsoft Application Virtualization (App-V) 5.1 sequencer, you can use it to monitor and record the installation and setup process for an application to be run as a virtualized application.</span></span>

<span data-ttu-id="ac563-105">**注** App-v 5.1 sequencer の構成、シーケンスのベストプラクティス、仮想アプリケーションの作成と更新の例については、「 [Microsoft Application Virtualization 5.0 シーケンスガイド](https://download.microsoft.com/download/F/7/8/F784A197-73BE-48FF-83DA-4102C05A6D44/App-V%205.0%20Sequencing%20Guide.docx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac563-105">**Note** For more information about configuring the App-V 5.1 sequencer, sequencing best practices, and an example of creating and updating a virtual application, see the [Microsoft Application Virtualization 5.0 Sequencing Guide](https://download.microsoft.com/download/F/7/8/F784A197-73BE-48FF-83DA-4102C05A6D44/App-V%205.0%20Sequencing%20Guide.docx).</span></span>

<span data-ttu-id="ac563-106">**注**App-v Sequencer は、"CO_ x" と一致するファイル名を使ったアプリケーションのシーケンスを行うことはできません &lt; &gt; 。 x は任意の数字です。</span><span class="sxs-lookup"><span data-stu-id="ac563-106">**Note** The App-V 5.x Sequencer cannot sequence applications with filenames matching "CO_&lt;x&gt;" where x is any numeral.</span></span> <span data-ttu-id="ac563-107">エラー0x8007139F が生成されます。</span><span class="sxs-lookup"><span data-stu-id="ac563-107">Error 0x8007139F will be generated.</span></span>

## <span data-ttu-id="ac563-108">アプリケーションのシーケンス</span><span class="sxs-lookup"><span data-stu-id="ac563-108">Sequencing an application</span></span>


<span data-ttu-id="ac563-109">App-v 5.1 Sequencer を使用して、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ac563-109">You can use the App-V 5.1 Sequencer to perform the following tasks:</span></span>

-   <span data-ttu-id="ac563-110">App-v 5.1 クライアントを実行しているコンピューターに展開できる仮想パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac563-110">Create virtual packages that can be deployed to computers running the App-V 5.1 client.</span></span>

-   <span data-ttu-id="ac563-111">既存のパッケージをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="ac563-111">Upgrade existing packages.</span></span> <span data-ttu-id="ac563-112">Sequencer を実行しているコンピューター上に既存のパッケージを展開してから、アプリケーションをアップグレードして新しいバージョンを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ac563-112">You can expand an existing package onto the computer running the sequencer and then upgrade the application to create a newer version.</span></span>

-   <span data-ttu-id="ac563-113">既存のパッケージに関連付けられた構成情報を編集します。</span><span class="sxs-lookup"><span data-stu-id="ac563-113">Edit configuration information associated with an existing package.</span></span> <span data-ttu-id="ac563-114">たとえば、ショートカットを追加したり、ファイルの種類の関連付けを変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="ac563-114">For example, you can add a shortcut or modify a file type association.</span></span>

    <span data-ttu-id="ac563-115">**注** ローミングを許可するには、ショートカットを作成し、利用可能なネットワーク上の場所に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac563-115">**Note** You must create shortcuts and save them to an available network location to allow roaming.</span></span> <span data-ttu-id="ac563-116">ショートカットが作成され、プライベートな場所に保存されている場合、そのパッケージは、App-v 5.1 クライアントを実行しているコンピューターにローカルで公開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac563-116">If a shortcut is created and saved in a private location, the package must be published locally to the computer running the App-V 5.1 client.</span></span>
 
-   <span data-ttu-id="ac563-117">既存の仮想パッケージを変換します。</span><span class="sxs-lookup"><span data-stu-id="ac563-117">Convert existing virtual packages.</span></span>

<span data-ttu-id="ac563-118">Sequencer では、 **% TMP% \ \ スクラッチ**または **% TEMP% \ \ スクラッチ**ディレクトリと**temp**ディレクトリを使ってシーケンス中に一時ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="ac563-118">The sequencer uses the **%TMP% \\ Scratch** or **%TEMP% \\ Scratch** directory and the **Temp** directory to store temporary files during sequencing.</span></span> <span data-ttu-id="ac563-119">Sequencer を実行しているコンピューターで、アプリケーションの推定インストール要件と同等の空きディスク領域を持つディレクトリを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac563-119">On the computer that runs the sequencer, you should configure these directories with free disk space equivalent to the estimated application installation requirements.</span></span> <span data-ttu-id="ac563-120">ハードドライブのパーティションごとに temp ディレクトリと Temp ディレクトリを構成すると、シーケンス中のパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="ac563-120">Configuring the temp directories and the Temp directory on different hard drive partitions can help improve performance during sequencing.</span></span>

<span data-ttu-id="ac563-121">Sequencer を使用して新しい仮想アプリケーションを作成すると、次の一覧のファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ac563-121">When you use the sequencer to create a new virtual application, the following listed files are created.</span></span> <span data-ttu-id="ac563-122">これらのファイルは、App-v 5.1 パッケージを構成します。</span><span class="sxs-lookup"><span data-stu-id="ac563-122">These files comprise the App-V 5.1 package.</span></span>

-   <span data-ttu-id="ac563-123">.msi ファイル。</span><span class="sxs-lookup"><span data-stu-id="ac563-123">.msi file.</span></span> <span data-ttu-id="ac563-124">この Windows Installer (.msi) ファイルは、sequencer によって作成され、仮想パッケージをターゲットコンピューターにインストールするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ac563-124">This Windows Installer (.msi) file is created by the sequencer and is used to install the virtual package on target computers.</span></span>

-   <span data-ttu-id="ac563-125">Report.xml ファイル。</span><span class="sxs-lookup"><span data-stu-id="ac563-125">Report.xml file.</span></span> <span data-ttu-id="ac563-126">このファイルでは、sequencer は、シーケンス中に検出されたすべての問題、警告、エラーを保存します。</span><span class="sxs-lookup"><span data-stu-id="ac563-126">In this file, the sequencer saves all issues, warnings, and errors that were discovered during sequencing.</span></span> <span data-ttu-id="ac563-127">パッケージが作成された後に情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac563-127">It displays the information after the package has been created.</span></span> <span data-ttu-id="ac563-128">このレポートで、診断とトラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ac563-128">You can us this report for diagnosing and troubleshooting.</span></span>

-   <span data-ttu-id="ac563-129">appv ファイル。</span><span class="sxs-lookup"><span data-stu-id="ac563-129">.appv file.</span></span> <span data-ttu-id="ac563-130">これは、仮想アプリケーションファイルです。</span><span class="sxs-lookup"><span data-stu-id="ac563-130">This is the virtual application file.</span></span>

-   <span data-ttu-id="ac563-131">展開構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="ac563-131">Deployment configuration file.</span></span> <span data-ttu-id="ac563-132">展開構成ファイルによって、仮想アプリケーションがターゲットコンピューターにどのように展開されるかが決まります。</span><span class="sxs-lookup"><span data-stu-id="ac563-132">The deployment configuration file determines how the virtual application will be deployed to target computers.</span></span>

-   <span data-ttu-id="ac563-133">ユーザー構成ファイル。</span><span class="sxs-lookup"><span data-stu-id="ac563-133">User configuration file.</span></span> <span data-ttu-id="ac563-134">ユーザー構成ファイルによって、ターゲットコンピューターで仮想アプリケーションが実行される方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="ac563-134">The user configuration file determines how the virtual application will run on target computers.</span></span>

<span data-ttu-id="ac563-135">**重要** パッケージコンバーターがセキュリティで保護された場所とディレクトリとして使用する% TMP% と% TEMP% フォルダーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac563-135">**Important** You must configure the %TMP% and %TEMP% folders that the package converter uses to be a secure location and directory.</span></span> <span data-ttu-id="ac563-136">セキュリティで保護された場所には、管理者のみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ac563-136">A secure location is only accessible by an administrator.</span></span> <span data-ttu-id="ac563-137">さらに、パッケージをシーケンス処理するときには、セキュリティで保護された場所にパッケージを保存するか、変換と監視のプロセス中に他のユーザーがログインすることを許可されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ac563-137">Additionally, when you sequence the package you should save the package to a location that is secure, or make sure that no other user is allowed to be logged in during the conversion and monitoring process.</span></span> 

<span data-ttu-id="ac563-138">Sequencer コンソールの [**オプション**] ダイアログボックスには、次のタブがあります。</span><span class="sxs-lookup"><span data-stu-id="ac563-138">The **Options** dialog box in the sequencer console contains the following tabs:</span></span>

-   <span data-ttu-id="ac563-139">**[全般**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ac563-139">**General**.</span></span> <span data-ttu-id="ac563-140">このタブを使用して、シーケンス中に Microsoft 更新プログラムを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ac563-140">Use this tab to enable Microsoft Updates to run during sequencing.</span></span> <span data-ttu-id="ac563-141">順序を構成する仮想化されたパッケージにバージョン番号を追加するには、[**パッケージバージョンをファイル名に追加**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac563-141">Select **Append Package Version to Filename** to configure the sequence to add a version number to the virtualized package that is being sequenced.</span></span> <span data-ttu-id="ac563-142">[**パッケージアクセラレータのソースを常に信頼**する] を選択して、認証を求めるメッセージを表示せずに、パッケージアクセラレータを使用して仮想化されたパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac563-142">Select **Always trust the source of Package Accelerators** to create virtualized packages using a package accelerator without being prompted for authorization.</span></span>

    <span data-ttu-id="ac563-143">**重要** App-V 4.6 を使用して作成されたパッケージアクセラレータは、App-v 5.1 ではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="ac563-143">**Important** Package Accelerators created using App-V4.6 are not supported by App-V 5.1.</span></span>     

-   <span data-ttu-id="ac563-144">**項目を解析**する。</span><span class="sxs-lookup"><span data-stu-id="ac563-144">**Parse Items**.</span></span> <span data-ttu-id="ac563-145">このタブには、仮想環境で解析またはトークン化される、関連付けられているファイルパスの場所が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac563-145">This tab displays the associated file path locations that will be parsed or tokenized into in the virtual environment.</span></span> <span data-ttu-id="ac563-146">トークンは、**高度な編集**の [**パッケージファイル**] タブを使用してファイルを追加する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="ac563-146">Tokens are useful for adding files using the **Package Files** tab in **Advanced Editing**.</span></span>

-   <span data-ttu-id="ac563-147">**除外項目**。</span><span class="sxs-lookup"><span data-stu-id="ac563-147">**Exclusion Items**.</span></span> <span data-ttu-id="ac563-148">このタブを使用して、シーケンス中に監視しないフォルダーとディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac563-148">Use this tab to specify which folders and directories should not be monitored during sequencing.</span></span> <span data-ttu-id="ac563-149">パッケージのローカルアプリデータフォルダーに保存されているローカルアプリケーションデータを追加するには、[**新規**] をクリックし、場所と関連付けられている**マッピングの種類**を指定します。</span><span class="sxs-lookup"><span data-stu-id="ac563-149">To add local application data that is saved in the Local App Data folder in the package, click **New** and specify the location and the associated **Mapping Type**.</span></span> <span data-ttu-id="ac563-150">一部のパッケージでは、このオプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="ac563-150">This option is required for some packages.</span></span>

<span data-ttu-id="ac563-151">App-v 5.1 では、Microsoft Windows サービスを含むアプリケーションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ac563-151">App-V 5.1 supports applications that include Microsoft Windows Services.</span></span> <span data-ttu-id="ac563-152">アプリケーションに Windows サービスが含まれている場合、そのサービスは、sequencer によって監視されている間にインストールされていれば、シーケンス仮想パッケージに含まれます。</span><span class="sxs-lookup"><span data-stu-id="ac563-152">If an application includes a Windows service, the Service will be included in the sequenced virtual package as long as it is installed while being monitored by the sequencer.</span></span> <span data-ttu-id="ac563-153">仮想アプリケーションが最初の実行時に Windows サービスを作成した場合、後でインストールした後、Windows サービスがパッケージに追加されるように、sequencer の監視中にアプリケーションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac563-153">If a virtual application creates a Windows service when it initially runs, then later, after installation, the application must be run while the sequencer is monitoring so that the Windows Service will be added to the package.</span></span> <span data-ttu-id="ac563-154">ローカルシステムアカウントで実行されているサービスのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ac563-154">Only Services that run under the Local System account are supported.</span></span> <span data-ttu-id="ac563-155">AutoStart または遅延 AutoStart 用に構成されているサービスは、パッケージ内の最初の仮想アプリケーションがパッケージの仮想環境内で実行される前に開始されます。</span><span class="sxs-lookup"><span data-stu-id="ac563-155">Services that are configured for AutoStart or Delayed AutoStart are started before the first virtual application in a package runs inside the package’s Virtual Environment.</span></span> <span data-ttu-id="ac563-156">アプリケーションによってオンデマンドで開始されるように構成された Windows サービスは、パッケージ内の仮想アプリケーションが API 呼び出しによってサービスを開始したときに開始されます。</span><span class="sxs-lookup"><span data-stu-id="ac563-156">Windows Services that are configured to be started on demand by an application are started when the virtual application inside the package starts the Service via API call.</span></span>

[<span data-ttu-id="ac563-157">APP-V 5.1 を使用して新しいアプリケーションをシーケンス処理する方法</span><span class="sxs-lookup"><span data-stu-id="ac563-157">How to Sequence a New Application with App-V 5.1</span></span>](how-to-sequence-a-new-application-with-app-v-51-beta-gb18030.md)

## <a href="" id="---------app-v-5-1-shell-extension-support"></a> <span data-ttu-id="ac563-158">App-v 5.1 シェル extension のサポート</span><span class="sxs-lookup"><span data-stu-id="ac563-158">App-V 5.1shell extension support</span></span>


<span data-ttu-id="ac563-159">App-v 5.1 では、シェルの拡張機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ac563-159">App-V 5.1supports shell extensions.</span></span> <span data-ttu-id="ac563-160">シェルの拡張機能が検出され、シーケンス中にパッケージに埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="ac563-160">Shell extensions will be detected and embedded in the package during sequencing.</span></span>

<span data-ttu-id="ac563-161">シェルの拡張機能は、シーケンス処理中にパッケージに自動的に埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="ac563-161">Shell extensions are embedded in the package automatically during the sequencing process.</span></span> <span data-ttu-id="ac563-162">パッケージが公開されると、シェルの拡張機能によって、アプリケーションがローカルにインストールされている場合と同じ機能をユーザーに提供できます。</span><span class="sxs-lookup"><span data-stu-id="ac563-162">When the package is published, the shell extension gives users the same functionality as if the application were locally installed.</span></span>

**<span data-ttu-id="ac563-163">シェルの拡張機能を使用するための要件:</span><span class="sxs-lookup"><span data-stu-id="ac563-163">Requirements for using shell extensions:</span></span>**

-   <span data-ttu-id="ac563-164">埋め込まれたシェルの拡張機能を含むパッケージは、グローバルに公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac563-164">Packages that contain embedded shell extensions must be published globally.</span></span> <span data-ttu-id="ac563-165">アプリケーションでは、シェルの拡張機能を有効にするために、クライアントで追加のセットアップや構成を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ac563-165">The application requires no additional setup or configuration on the client to enable the shell extension functionality.</span></span>

-   <span data-ttu-id="ac563-166">アプリケーション、Sequencer、および App-v クライアントの "ビット" は一致する必要があります。また、シェルの拡張機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="ac563-166">The “bitness” of the application, Sequencer, and App-V client must match, or the shell extensions won’t work.</span></span> <span data-ttu-id="ac563-167">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ac563-167">For example:</span></span>

    -   <span data-ttu-id="ac563-168">このアプリケーションのバージョンは64ビットです。</span><span class="sxs-lookup"><span data-stu-id="ac563-168">The version of the application is 64-bit.</span></span>

    -   <span data-ttu-id="ac563-169">Sequencer は64ビットコンピューターで実行されています。</span><span class="sxs-lookup"><span data-stu-id="ac563-169">The Sequencer is running on a 64-bit computer.</span></span>

    -   <span data-ttu-id="ac563-170">パッケージは、64ビットの App-v クライアントコンピューターに配信されます。</span><span class="sxs-lookup"><span data-stu-id="ac563-170">The package is being delivered to a 64-bit App-V client computer.</span></span>

<span data-ttu-id="ac563-171">次の表に、サポートされているシェルの拡張機能を示します。</span><span class="sxs-lookup"><span data-stu-id="ac563-171">The following table lists the supported shell extensions:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ac563-172">ハンドラー</span><span class="sxs-lookup"><span data-stu-id="ac563-172">Handler</span></span></th>
<th align="left"><span data-ttu-id="ac563-173">説明</span><span class="sxs-lookup"><span data-stu-id="ac563-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ac563-174">コンテキストメニューハンドラー</span><span class="sxs-lookup"><span data-stu-id="ac563-174">Context menu handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="ac563-175">コンテキストメニューにメニュー項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="ac563-175">Adds menu items to the context menu.</span></span> <span data-ttu-id="ac563-176">コンテキストメニューが表示される前に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ac563-176">It is called before the context menu is displayed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ac563-177">ドラッグアンドドロップハンドラー</span><span class="sxs-lookup"><span data-stu-id="ac563-177">Drag-and-drop handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="ac563-178">表示されるコンテキストメニューを右クリック、ドラッグアンドドロップ、変更したときの動作を制御します。</span><span class="sxs-lookup"><span data-stu-id="ac563-178">Controls the action where right-click, drag and drop and modifies the context menu that appears.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ac563-179">ドロップターゲットハンドラー</span><span class="sxs-lookup"><span data-stu-id="ac563-179">Drop target handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="ac563-180">データオブジェクトがドラッグされて、ファイルなどのドロップターゲット上にドロップした後、アクションを制御します。</span><span class="sxs-lookup"><span data-stu-id="ac563-180">Controls the action after a data object is dragged and dropped over a drop target such as a file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ac563-181">データオブジェクトハンドラー</span><span class="sxs-lookup"><span data-stu-id="ac563-181">Data object handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="ac563-182">ファイルがクリップボードにコピーされた後、またはドロップターゲットをドラッグアンドドロップした後にアクションを制御します。</span><span class="sxs-lookup"><span data-stu-id="ac563-182">Controls the action after a file is copied to the clipboard or dragged and dropped over a drop target.</span></span> <span data-ttu-id="ac563-183">ドロップターゲットには、追加のクリップボード形式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ac563-183">It can provide additional clipboard formats to the drop target.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ac563-184">プロパティシートハンドラー</span><span class="sxs-lookup"><span data-stu-id="ac563-184">Property sheet handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="ac563-185">ページをオブジェクトの [プロパティシート] ダイアログボックスに置換または追加します。</span><span class="sxs-lookup"><span data-stu-id="ac563-185">Replaces or adds pages to the property sheet dialog box of an object.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ac563-186">ヒントハンドラー</span><span class="sxs-lookup"><span data-stu-id="ac563-186">Infotip handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="ac563-187">マウスをポイントしたときに、アイテムのフラグとヒント情報を取得し、ポップアップツールヒント内に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="ac563-187">Allows retrieving flags and infotip information for an item and displaying it inside a pop-up tooltip upon mouse hover.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ac563-188">列ハンドラー</span><span class="sxs-lookup"><span data-stu-id="ac563-188">Column handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="ac563-189">Windows エクスプローラーの [詳細] ビューでカスタム列の作成と表示を行うことができ <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="ac563-189">Allows creating and displaying custom columns in <strong>Windows Explorer Details view</strong>.</span></span> <span data-ttu-id="ac563-190">並べ替えとグループ化を拡張するために使うことができます。</span><span class="sxs-lookup"><span data-stu-id="ac563-190">It can be used to extend sorting and grouping.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ac563-191">プレビューハンドラー</span><span class="sxs-lookup"><span data-stu-id="ac563-191">Preview handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="ac563-192">エクスプローラーのプレビューウィンドウにファイルのプレビューが表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="ac563-192">Enables a preview of a file to be displayed in the Windows Explorer Preview pane.</span></span></p></td>
</tr>
</tbody>
</table>

## <span data-ttu-id="ac563-193">書き込み時のコピー (CoW) のファイル拡張子のサポート</span><span class="sxs-lookup"><span data-stu-id="ac563-193">Copy on Write (CoW) file extension support</span></span>

<span data-ttu-id="ac563-194">書き込み時 (CoW) のファイル拡張子を使用すると、アプリが使用されている間、仮想パッケージに含まれている特定の場所に、アプリ5.1 では動的に書き込みを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ac563-194">Copy on write (CoW) file extensions allow App-V 5.1 to dynamically write to specific locations contained in the virtual package while it is being used.</span></span>

<span data-ttu-id="ac563-195">次の表は、VFS ディレクトリにある仮想パッケージに存在する可能性があるファイルの種類を示していますが、App-v 5.1 クライアントを実行しているコンピューターでは更新できません。</span><span class="sxs-lookup"><span data-stu-id="ac563-195">The following table displays the file types that can exist in a virtual package under the VFS directory, but cannot be updated on the computer running the App-V 5.1 client.</span></span> <span data-ttu-id="ac563-196">その他のすべてのファイルとディレクトリは変更できます。</span><span class="sxs-lookup"><span data-stu-id="ac563-196">All other files and directories can be modified.</span></span>

| <span data-ttu-id="ac563-197">ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="ac563-197">File Type</span></span>     |               |               |               |               |               |
|------------   |-------------  |-------------  |------------   |------------   |------------   |
| <span data-ttu-id="ac563-198">acm</span><span class="sxs-lookup"><span data-stu-id="ac563-198">.acm</span></span>          | <span data-ttu-id="ac563-199">asa</span><span class="sxs-lookup"><span data-stu-id="ac563-199">.asa</span></span>          | <span data-ttu-id="ac563-200">.asp</span><span class="sxs-lookup"><span data-stu-id="ac563-200">.asp</span></span>          | <span data-ttu-id="ac563-201">.aspx</span><span class="sxs-lookup"><span data-stu-id="ac563-201">.aspx</span></span>         | <span data-ttu-id="ac563-202">ax</span><span class="sxs-lookup"><span data-stu-id="ac563-202">.ax</span></span>           | <span data-ttu-id="ac563-203">.bat</span><span class="sxs-lookup"><span data-stu-id="ac563-203">.bat</span></span>          |
| <span data-ttu-id="ac563-204">.cer</span><span class="sxs-lookup"><span data-stu-id="ac563-204">.cer</span></span>          | <span data-ttu-id="ac563-205">.chm</span><span class="sxs-lookup"><span data-stu-id="ac563-205">.chm</span></span>          | <span data-ttu-id="ac563-206">clb</span><span class="sxs-lookup"><span data-stu-id="ac563-206">.clb</span></span>          | <span data-ttu-id="ac563-207">.cmd</span><span class="sxs-lookup"><span data-stu-id="ac563-207">.cmd</span></span>          | <span data-ttu-id="ac563-208">.cnt</span><span class="sxs-lookup"><span data-stu-id="ac563-208">.cnt</span></span>          | <span data-ttu-id="ac563-209">cnv</span><span class="sxs-lookup"><span data-stu-id="ac563-209">.cnv</span></span>          |
| <span data-ttu-id="ac563-210">.com</span><span class="sxs-lookup"><span data-stu-id="ac563-210">.com</span></span>          | <span data-ttu-id="ac563-211">.cpl</span><span class="sxs-lookup"><span data-stu-id="ac563-211">.cpl</span></span>          | <span data-ttu-id="ac563-212">cpx</span><span class="sxs-lookup"><span data-stu-id="ac563-212">.cpx</span></span>          | <span data-ttu-id="ac563-213">.crt</span><span class="sxs-lookup"><span data-stu-id="ac563-213">.crt</span></span>          | <span data-ttu-id="ac563-214">.dll</span><span class="sxs-lookup"><span data-stu-id="ac563-214">.dll</span></span>          | <span data-ttu-id="ac563-215">.drv</span><span class="sxs-lookup"><span data-stu-id="ac563-215">.drv</span></span>          |
| <span data-ttu-id="ac563-216">. esc</span><span class="sxs-lookup"><span data-stu-id="ac563-216">.esc</span></span>          | <span data-ttu-id="ac563-217">.exe</span><span class="sxs-lookup"><span data-stu-id="ac563-217">.exe</span></span>          | <span data-ttu-id="ac563-218">.fon</span><span class="sxs-lookup"><span data-stu-id="ac563-218">.fon</span></span>          | <span data-ttu-id="ac563-219">.grp</span><span class="sxs-lookup"><span data-stu-id="ac563-219">.grp</span></span>          | <span data-ttu-id="ac563-220">.hlp</span><span class="sxs-lookup"><span data-stu-id="ac563-220">.hlp</span></span>          | <span data-ttu-id="ac563-221">.hta</span><span class="sxs-lookup"><span data-stu-id="ac563-221">.hta</span></span>          |
| <span data-ttu-id="ac563-222">. ime</span><span class="sxs-lookup"><span data-stu-id="ac563-222">.ime</span></span>          | <span data-ttu-id="ac563-223">.inf</span><span class="sxs-lookup"><span data-stu-id="ac563-223">.inf</span></span>          | <span data-ttu-id="ac563-224">.ins</span><span class="sxs-lookup"><span data-stu-id="ac563-224">.ins</span></span>          | <span data-ttu-id="ac563-225">.isp</span><span class="sxs-lookup"><span data-stu-id="ac563-225">.isp</span></span>          | <span data-ttu-id="ac563-226">。</span><span class="sxs-lookup"><span data-stu-id="ac563-226">.its</span></span>          | <span data-ttu-id="ac563-227">.js</span><span class="sxs-lookup"><span data-stu-id="ac563-227">.js</span></span>           |
| <span data-ttu-id="ac563-228">.jse</span><span class="sxs-lookup"><span data-stu-id="ac563-228">.jse</span></span>          | <span data-ttu-id="ac563-229">.lnk</span><span class="sxs-lookup"><span data-stu-id="ac563-229">.lnk</span></span>          | <span data-ttu-id="ac563-230">.msc</span><span class="sxs-lookup"><span data-stu-id="ac563-230">.msc</span></span>          | <span data-ttu-id="ac563-231">.msi</span><span class="sxs-lookup"><span data-stu-id="ac563-231">.msi</span></span>          | <span data-ttu-id="ac563-232">.msp</span><span class="sxs-lookup"><span data-stu-id="ac563-232">.msp</span></span>          | <span data-ttu-id="ac563-233">.mst</span><span class="sxs-lookup"><span data-stu-id="ac563-233">.mst</span></span>          |
| <span data-ttu-id="ac563-234">mui</span><span class="sxs-lookup"><span data-stu-id="ac563-234">.mui</span></span>          | <span data-ttu-id="ac563-235">nls</span><span class="sxs-lookup"><span data-stu-id="ac563-235">.nls</span></span>          | <span data-ttu-id="ac563-236">.ocx</span><span class="sxs-lookup"><span data-stu-id="ac563-236">.ocx</span></span>          | <span data-ttu-id="ac563-237">pal</span><span class="sxs-lookup"><span data-stu-id="ac563-237">.pal</span></span>          | <span data-ttu-id="ac563-238">.pcd</span><span class="sxs-lookup"><span data-stu-id="ac563-238">.pcd</span></span>          | <span data-ttu-id="ac563-239">.pif</span><span class="sxs-lookup"><span data-stu-id="ac563-239">.pif</span></span>          |
| <span data-ttu-id="ac563-240">.reg</span><span class="sxs-lookup"><span data-stu-id="ac563-240">.reg</span></span>          | <span data-ttu-id="ac563-241">.scf</span><span class="sxs-lookup"><span data-stu-id="ac563-241">.scf</span></span>          | <span data-ttu-id="ac563-242">.scr</span><span class="sxs-lookup"><span data-stu-id="ac563-242">.scr</span></span>          | <span data-ttu-id="ac563-243">sct</span><span class="sxs-lookup"><span data-stu-id="ac563-243">.sct</span></span>          | <span data-ttu-id="ac563-244">.shb</span><span class="sxs-lookup"><span data-stu-id="ac563-244">.shb</span></span>          | <span data-ttu-id="ac563-245">.shs</span><span class="sxs-lookup"><span data-stu-id="ac563-245">.shs</span></span>          |
| <span data-ttu-id="ac563-246">.sys</span><span class="sxs-lookup"><span data-stu-id="ac563-246">.sys</span></span>          | <span data-ttu-id="ac563-247">.tlb</span><span class="sxs-lookup"><span data-stu-id="ac563-247">.tlb</span></span>          | <span data-ttu-id="ac563-248">tsp</span><span class="sxs-lookup"><span data-stu-id="ac563-248">.tsp</span></span>          | <span data-ttu-id="ac563-249">.url</span><span class="sxs-lookup"><span data-stu-id="ac563-249">.url</span></span>          | <span data-ttu-id="ac563-250">.vb</span><span class="sxs-lookup"><span data-stu-id="ac563-250">.vb</span></span>           | <span data-ttu-id="ac563-251">.vbe</span><span class="sxs-lookup"><span data-stu-id="ac563-251">.vbe</span></span>          |
| <span data-ttu-id="ac563-252">.vbs</span><span class="sxs-lookup"><span data-stu-id="ac563-252">.vbs</span></span>          | <span data-ttu-id="ac563-253">.vsmacros</span><span class="sxs-lookup"><span data-stu-id="ac563-253">.vsmacros</span></span>     | <span data-ttu-id="ac563-254">.ws</span><span class="sxs-lookup"><span data-stu-id="ac563-254">.ws</span></span>           | <span data-ttu-id="ac563-255">.wsf</span><span class="sxs-lookup"><span data-stu-id="ac563-255">.wsf</span></span>          | <span data-ttu-id="ac563-256">.wsh</span><span class="sxs-lookup"><span data-stu-id="ac563-256">.wsh</span></span>          |               |


## <span data-ttu-id="ac563-257">既存の仮想アプリケーションパッケージの変更</span><span class="sxs-lookup"><span data-stu-id="ac563-257">Modifying an existing virtual application package</span></span>


<span data-ttu-id="ac563-258">Sequencer を使って既存のパッケージを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="ac563-258">You can use the sequencer to modify an existing package.</span></span> <span data-ttu-id="ac563-259">この操作を行うコンピューターは、アプリケーションの作成に使用したコンピューターのチップアーキテクチャと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac563-259">The computer on which you do this should match the chip architecture of the computer you used to create the application.</span></span> <span data-ttu-id="ac563-260">たとえば、最初に64ビットオペレーティングシステムを実行しているコンピューターを使ってパッケージを並べた場合は、64ビットオペレーティングシステムを実行しているコンピューターを使ってパッケージを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac563-260">For example, if you initially sequenced a package using a computer running a 64-bit operating system, you should modify the package using a computer running a 64-bit operating system.</span></span>

[<span data-ttu-id="ac563-261">既存の仮想アプリケーション パッケージを変更する方法</span><span class="sxs-lookup"><span data-stu-id="ac563-261">How to Modify an Existing Virtual Application Package</span></span>](how-to-modify-an-existing-virtual-application-package-51.md)

## <span data-ttu-id="ac563-262">プロジェクトテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="ac563-262">Creating a project template</span></span>


<span data-ttu-id="ac563-263">Appvt ファイルは、一般的に適用されるカスタマイズされた設定を保存するために使うことができるプロジェクトテンプレートです。</span><span class="sxs-lookup"><span data-stu-id="ac563-263">A .appvt file is a project template that can be used to save commonly applied, customized settings.</span></span> <span data-ttu-id="ac563-264">今後の sequencings では、これらの設定をより簡単に使うことができます。</span><span class="sxs-lookup"><span data-stu-id="ac563-264">You can then more easily use these settings for future sequencings.</span></span>

<span data-ttu-id="ac563-265">App-v 5.1 のプロジェクトテンプレートは、app-v の5.1 アプリケーションアクセラレータがアプリケーション固有であり、App-v の5.1 プロジェクトテンプレートを複数のアプリケーションに適用できるため、app-v 5.1 アプリケーションアクセラレータとは異なります。</span><span class="sxs-lookup"><span data-stu-id="ac563-265">App-V 5.1 project templates differ from App-V 5.1 Application Accelerators because App-V 5.1 Application Accelerators are application-specific, and App-V 5.1 project templates can be applied to multiple applications.</span></span> <span data-ttu-id="ac563-266">また、パッケージアクセラレータを使用して仮想アプリケーションパッケージを作成する場合、プロジェクトテンプレートを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="ac563-266">Additionally, you cannot use a project template when you use a Package Accelerator to create a virtual application package.</span></span> <span data-ttu-id="ac563-267">次の一般的な設定は、App-v 5.1 プロジェクトテンプレートと共に保存されています。</span><span class="sxs-lookup"><span data-stu-id="ac563-267">The following general settings are saved with an App-V 5.1 project template:</span></span>

<span data-ttu-id="ac563-268">テンプレートでは、次のように複数の設定を指定して保存できます。</span><span class="sxs-lookup"><span data-stu-id="ac563-268">A template can specify and store multiple settings as follows:</span></span>

-   <span data-ttu-id="ac563-269">**高度な監視オプション**。</span><span class="sxs-lookup"><span data-stu-id="ac563-269">**Advanced Monitoring Options**.</span></span> <span data-ttu-id="ac563-270">監視中に Microsoft Update を実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ac563-270">Enables Microsoft Update to run during monitoring.</span></span> <span data-ttu-id="ac563-271">ローカル操作オプションの設定を保存する</span><span class="sxs-lookup"><span data-stu-id="ac563-271">Saves allow local interaction option settings</span></span>

-   <span data-ttu-id="ac563-272">**[全般] オプション**。</span><span class="sxs-lookup"><span data-stu-id="ac563-272">**General Options**.</span></span> <span data-ttu-id="ac563-273">**Windows インストーラー**の使用を有効にします。**ファイル名にパッケージバージョンを追加**します。</span><span class="sxs-lookup"><span data-stu-id="ac563-273">Enables the use of **Windows Installer**, **Append Package Version to Filename**.</span></span>

-   **<span data-ttu-id="ac563-274">除外項目。</span><span class="sxs-lookup"><span data-stu-id="ac563-274">Exclusion Items.</span></span>** <span data-ttu-id="ac563-275">除外パターンリストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ac563-275">Contains the Exclusion pattern list.</span></span>

[<span data-ttu-id="ac563-276">プロジェクト テンプレートを作成して使用する方法</span><span class="sxs-lookup"><span data-stu-id="ac563-276">How to Create and Use a Project Template</span></span>](how-to-create-and-use-a-project-template51.md)

## <span data-ttu-id="ac563-277">パッケージアクセラレータの作成</span><span class="sxs-lookup"><span data-stu-id="ac563-277">Creating a package accelerator</span></span>


<span data-ttu-id="ac563-278">**注** 以前のバージョンの App-v を使用して作成されたパッケージアクセラレータは、App-v 5.1 を使って再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac563-278">**Note** Package accelerators created using a previous version of App-V must be recreated using App-V 5.1.</span></span>

<span data-ttu-id="ac563-279">App-v 5.1 パッケージアクセラレータを使って、新しい仮想アプリケーションパッケージを自動的に生成することができます。</span><span class="sxs-lookup"><span data-stu-id="ac563-279">You can use App-V 5.1 package accelerators to automatically generate a new virtual application packages.</span></span> <span data-ttu-id="ac563-280">パッケージアクセラレータの作成が正常に完了したら、パッケージアクセラレータを再利用して共有できます。</span><span class="sxs-lookup"><span data-stu-id="ac563-280">After you have successfully created a package accelerator, you can reuse and share the package accelerator.</span></span>

<span data-ttu-id="ac563-281">場合によっては、パッケージアクセラレータを作成するときに、sequencer を実行するコンピューターにローカルでアプリケーションをインストールすることが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="ac563-281">In some situations, to create the package accelerator, you might have to install the application locally on the computer that runs the sequencer.</span></span> <span data-ttu-id="ac563-282">このような場合は、最初にインストールメディアを使ってパッケージアクセラレータを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac563-282">In such cases, you should first try to create the package accelerator with the installation media.</span></span> <span data-ttu-id="ac563-283">不足している複数のファイルが必要な場合は、sequencer を実行するコンピューターにローカルでアプリケーションをインストールしてから、パッケージアクセラレータを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac563-283">If multiple missing files are required, you should install the application locally to the computer that runs the sequencer, and then create the package accelerator.</span></span>

<span data-ttu-id="ac563-284">パッケージアクセラレータの作成が正常に完了したら、パッケージアクセラレータを再利用して共有できます。</span><span class="sxs-lookup"><span data-stu-id="ac563-284">After you have successfully created a Package Accelerator, you can reuse and share the Package Accelerator.</span></span> <span data-ttu-id="ac563-285">App-v 5.1 パッケージアクセラレータの作成は、高度なタスクです。</span><span class="sxs-lookup"><span data-stu-id="ac563-285">Creating App-V 5.1 Package Accelerators is an advanced task.</span></span> <span data-ttu-id="ac563-286">パッケージアクセラレータには、パスワードとユーザー固有の情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ac563-286">Package Accelerators can contain password and user-specific information.</span></span> <span data-ttu-id="ac563-287">そのため、パッケージアクセラレータと関連するインストールメディアを安全な場所に保存する必要があります。また、パッケージアクセラレータを作成した後で、アプリを作成した後で、app-v 5.1 パッケージアクセラレータが適用されたときに、発行元を確認できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac563-287">Therefore you must save Package Accelerators and the associated installation media in a secure location, and you should digitally sign the Package Accelerator after you create it so that the publisher can be verified when the App-V 5.1 Package Accelerator is applied.</span></span>

[<span data-ttu-id="ac563-288">パッケージ アクセラレータを作成する方法</span><span class="sxs-lookup"><span data-stu-id="ac563-288">How to Create a Package Accelerator</span></span>](how-to-create-a-package-accelerator51.md)

[<span data-ttu-id="ac563-289">APP-V パッケージ アクセラレータを使用して仮想アプリケーション パッケージを作成する方法</span><span class="sxs-lookup"><span data-stu-id="ac563-289">How to Create a Virtual Application Package Using an App-V Package Accelerator</span></span>](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator51.md)

## <span data-ttu-id="ac563-290">Sequencer エラー報告</span><span class="sxs-lookup"><span data-stu-id="ac563-290">Sequencer error reporting</span></span>


<span data-ttu-id="ac563-291">アプリ-V 5.1 Sequencer は、シーケンス中に一般的なシーケンスの問題を検出できます。</span><span class="sxs-lookup"><span data-stu-id="ac563-291">The App-V 5.1 Sequencer can detect common sequencing issues during sequencing.</span></span> <span data-ttu-id="ac563-292">シーケンスウィザードの最後にある [**インストールレポート**] ページには、問題の重大度に応じて、**エラー**、**警告**、および**情報**に分類された診断メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac563-292">The **Installation Report** page at the end of the sequencing wizard displays diagnostic messages categorized into **Errors**, **Warnings**, and **Info** depending on the severity of the issue.</span></span>

<span data-ttu-id="ac563-293">Windows イベントビューアーを使用して、シーケンスエラーに関する追加情報を見つけることもできます。</span><span class="sxs-lookup"><span data-stu-id="ac563-293">You can also find additional information about sequencing errors using the Windows Event Viewer.</span></span>


## <a href="" id="other-resources-for-the-app-v-5-1-sequencer-"></a><span data-ttu-id="ac563-294">アプリのその他のリソース-V 5.1 sequencer</span><span class="sxs-lookup"><span data-stu-id="ac563-294">Other resources for the App-V 5.1 sequencer</span></span>


-   [<span data-ttu-id="ac563-295">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="ac563-295">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

