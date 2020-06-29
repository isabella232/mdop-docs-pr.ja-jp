---
title: APP-V 5.0 を使用して新しいアプリケーションをシーケンス処理する方法
description: APP-V 5.0 を使用して新しいアプリケーションをシーケンス処理する方法
author: dansimp
ms.assetid: a263fa84-cd6d-4219-a5c2-eb6a553b826c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 13fdda066f79d918da1970e0cab6c1d6e60f6585
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813722"
---
# <span data-ttu-id="a7a1b-103">APP-V 5.0 を使用して新しいアプリケーションをシーケンス処理する方法</span><span class="sxs-lookup"><span data-stu-id="a7a1b-103">How to Sequence a New Application with App-V 5.0</span></span>


**<span data-ttu-id="a7a1b-104">順序付けを開始する前に確認または実行するには</span><span class="sxs-lookup"><span data-stu-id="a7a1b-104">To review or do before you start sequencing</span></span>**

1.  <span data-ttu-id="a7a1b-105">作成する仮想化されたアプリケーションパッケージの種類を特定します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-105">Determine the type of virtualized application package you want to create:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="a7a1b-106">アプリケーションの種類</span><span class="sxs-lookup"><span data-stu-id="a7a1b-106">Application type</span></span></th>
    <th align="left"><span data-ttu-id="a7a1b-107">説明</span><span class="sxs-lookup"><span data-stu-id="a7a1b-107">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a7a1b-108">標準</span><span class="sxs-lookup"><span data-stu-id="a7a1b-108">Standard</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a7a1b-109">アプリケーションまたは一連のアプリケーションを含むパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-109">Creates a package that contains an application or a suite of applications.</span></span> <span data-ttu-id="a7a1b-110">これは、ほとんどのアプリケーションの種類で推奨されるオプションです。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-110">This is the preferred option for most application types.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="a7a1b-111">アドオンまたはプラグイン</span><span class="sxs-lookup"><span data-stu-id="a7a1b-111">Add-on or plug-in</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a7a1b-112">Microsoft Excel のプラグインなど、標準アプリケーションの機能を拡張するパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-112">Creates a package that extends the functionality of a standard application, for example, a plug-in for Microsoft Excel.</span></span> <span data-ttu-id="a7a1b-113">さらに、ネイティブにインストールされたアプリケーションの場合、または接続グループを使用してリンクされている別のパッケージの場合は、プラグインを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-113">Additionally, you can use plug-ins for natively installed applications, or for another package that is linked by using connection groups.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="a7a1b-114">ミドルウェア</span><span class="sxs-lookup"><span data-stu-id="a7a1b-114">Middleware</span></span></p></td>
    <td align="left"><p><span data-ttu-id="a7a1b-115">標準アプリケーション (たとえば、Java) で必要なパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-115">Creates a package that is required by a standard application, for example, Java.</span></span> <span data-ttu-id="a7a1b-116">ミドルウェアパッケージは、接続グループを使用して他のパッケージにリンクするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-116">Middleware packages are used for linking to other packages by using connection groups.</span></span></p></td>
    </tr>
    </tbody>
    </table>



2.  <span data-ttu-id="a7a1b-117">必要なすべてのインストールファイルを、sequencer を実行しているコンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-117">Copy all required installation files to the computer that is running the sequencer.</span></span>

3.  <span data-ttu-id="a7a1b-118">アプリケーションの順序を設定する前に、仮想環境のバックアップイメージを作成してから、アプリケーションのシーケンスを完了した後でそのイメージに戻します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-118">Make a backup image of your virtual environment before sequencing an application, and then revert to that image each time after you finish sequencing an application.</span></span>

4.  <span data-ttu-id="a7a1b-119">次の項目を確認します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-119">Review the following items:</span></span>

    -   <span data-ttu-id="a7a1b-120">アプリケーションのインストーラーによって、新規または既存のファイルまたはディレクトリへのセキュリティアクセスが変更された場合、これらの変更はパッケージ内でキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-120">If an application installer changes the security access to a new or existing file or directory, those changes are not captured in the package.</span></span>

    -   <span data-ttu-id="a7a1b-121">仮想化されたパッケージのターゲットボリュームに対して短いパスが無効になっている場合は、作成された後もショートパスを無効にしているボリュームにパッケージをシーケンスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-121">If short paths have been disabled for the virtualized package’s target volume, you must also sequence the package to a volume that was created and still has short-paths disabled.</span></span> <span data-ttu-id="a7a1b-122">システムボリュームにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-122">It cannot be the system volume.</span></span>

    -   <span data-ttu-id="a7a1b-123">App-v 5.0 SP3 以降、プライマリ仮想アプリケーションディレクトリ (PVAD) は非表示になっていますが、オンに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-123">Starting in App-V 5.0 SP3, the primary virtual application directory (PVAD) is hidden, but you can turn it back on.</span></span> <span data-ttu-id="a7a1b-124">「 [App-v 5.0 SP3 につい](about-app-v-50-sp3.md#bkmk-pvad-hidden)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-124">See [About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-pvad-hidden).</span></span>

**<span data-ttu-id="a7a1b-125">新しい標準アプリケーションを順序を作成するには</span><span class="sxs-lookup"><span data-stu-id="a7a1b-125">To sequence a new standard application</span></span>**

1.  <span data-ttu-id="a7a1b-126">Sequencer を実行しているコンピューターで、[**すべてのプログラム**]、[ **microsoft application virtualization**]、[ **microsoft application virtualization sequencer**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-126">On the computer that runs the sequencer, click **All Programs**, and then Click **Microsoft Application Virtualization**, and then click **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="a7a1b-127">Sequencer で、[**新しい仮想アプリケーションパッケージの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-127">In the sequencer, click **Create a New Virtual Application Package**.</span></span> <span data-ttu-id="a7a1b-128">[**パッケージの作成 (既定)**] を選び、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-128">Select **Create Package (default)**, and then click **Next**.</span></span>

3.  <span data-ttu-id="a7a1b-129">[**コンピューターの準備**] ページで、パッケージの作成に失敗する可能性がある問題、またはパッケージに不要なデータが含まれている可能性がある問題を確認します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-129">On the **Prepare Computer** page, review the issues that could cause the package creation to fail or could cause the package to contain unnecessary data.</span></span> <span data-ttu-id="a7a1b-130">続行する前に、発生する可能性があるすべての問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-130">You should resolve all potential issues before you continue.</span></span> <span data-ttu-id="a7a1b-131">修正が完了したら、[**更新**] をクリックして更新された情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-131">After making any corrections, click **Refresh** to display the updated information.</span></span> <span data-ttu-id="a7a1b-132">すべての潜在的な問題を解決したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-132">After you have resolved all potential issues, click **Next**.</span></span>

    **<span data-ttu-id="a7a1b-133">重要</span><span class="sxs-lookup"><span data-stu-id="a7a1b-133">Important</span></span>**  
    <span data-ttu-id="a7a1b-134">ウイルススキャンソフトウェアを無効にする必要がある場合は、まず sequencer を実行するコンピューターをスキャンして、不要なファイルや悪意のあるファイルがパッケージに追加されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-134">If you are required to disable virus scanning software, you should first scan the computer that runs the sequencer in order to ensure that no unwanted or malicious files could be added to the package.</span></span>



4.  <span data-ttu-id="a7a1b-135">[**アプリケーションの種類**] ページで、[**標準アプリケーション (既定)** ] チェックボックスをオンにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-135">On the **Type of Application** page, click the **Standard Application (default)** check box, and then click **Next**.</span></span>

5.  <span data-ttu-id="a7a1b-136">[**インストーラーの選択**] ページで [**参照**] をクリックして、アプリケーションのインストールファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-136">On the **Select Installer** page, click **Browse** and specify the installation file for the application.</span></span>

    **<span data-ttu-id="a7a1b-137">注</span><span class="sxs-lookup"><span data-stu-id="a7a1b-137">Note</span></span>**  
    <span data-ttu-id="a7a1b-138">指定したアプリケーションインストーラーによって、既存または新規のファイルまたはディレクトリへのセキュリティアクセスが変更された場合、関連付けられた変更はパッケージにキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-138">If the specified application installer modifies security access to a file or directory, existing or new, the associated changes will not be captured into the package.</span></span>



~~~
If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Perform a Custom Installation** check box, and then Click **Next**.
~~~

6. <span data-ttu-id="a7a1b-139">[**パッケージ名**] ページで、パッケージに関連付ける名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-139">On the **Package Name** page, type a name that will be associated with the package.</span></span> <span data-ttu-id="a7a1b-140">パッケージに追加されるアプリケーションの目的とバージョンを識別するのに役立つ名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-140">Use a name that helps identify the purpose and version of the application that will be added to the package.</span></span> <span data-ttu-id="a7a1b-141">パッケージ名は、App-v 5.0 管理コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-141">The package name is displayed in the App-V 5.0 Management Console.</span></span>

   <span data-ttu-id="a7a1b-142">**プライマリ仮想アプリケーションディレクトリ**には、アプリケーションがターゲットコンピューターにインストールされるパスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-142">The **Primary Virtual Application Directory** displays the path where the application will be installed on target computers.</span></span> <span data-ttu-id="a7a1b-143">この場所を指定するには、[**参照**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-143">To specify this location, select **Browse**.</span></span>

   **<span data-ttu-id="a7a1b-144">注</span><span class="sxs-lookup"><span data-stu-id="a7a1b-144">Note</span></span>**  
   <span data-ttu-id="a7a1b-145">App-v 5.0 SP3 以降、プライマリ仮想アプリケーションディレクトリ (PVAD) は非表示になっていますが、オンに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-145">Starting in App-V 5.0 SP3, the primary virtual application directory (PVAD) is hidden, but you can turn it back on.</span></span> <span data-ttu-id="a7a1b-146">「 [App-v 5.0 SP3 につい](about-app-v-50-sp3.md#bkmk-pvad-hidden)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-146">See [About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-pvad-hidden).</span></span>



~~~
**Important**  
The primary application virtual directory should match the installation location for the application that is being sequenced. For example, if you install Notepad to **C:\\Program Files\\Notepad**; you should configure **C:\\Program Files\\Notepad** as your primary virtual directory. Alternatively, you can choose to set **C:\\Notepad** as the primary virtual application directory, as long as during installation time, you configure the installer to install to **C:\\Notepad**. Editing the Application Virtualization path is an advanced configuration task. For most applications, the default path is recommended for the following reasons:

-   Application Compatibility. Some virtualized applications will not function correctly, or will fail to open if the directories are not configured with identical virtual directory paths.

-   Performance. Since no file system redirection is required, the runtime performance can improve.



**Tip**  
It is recommended that prior to Sequencing an application, you open the associated installer to determine the default installation directory, and then configure that location as the **Primary Virtual Application Directory**.



Click **Next**.
~~~

7. <span data-ttu-id="a7a1b-147">**インストール**ページで、sequencer とアプリケーションインストーラーの準備ができたら、アプリのインストールを続行して、sequencer がインストールプロセスを監視できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-147">On the **Installation** page, when the sequencer and application installer are ready you can proceed to install the application so that the sequencer can monitor the installation process.</span></span>

   **<span data-ttu-id="a7a1b-148">重要</span><span class="sxs-lookup"><span data-stu-id="a7a1b-148">Important</span></span>**  
   <span data-ttu-id="a7a1b-149">常にセキュリティで保護された場所にアプリケーションをインストールし、監視中に sequencer を実行しているコンピューターに他のユーザーがログオンしていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-149">You should always install applications to a secure location and make sure no other users are logged on to the computer running the sequencer during monitoring.</span></span>



~~~
Use the application's installation process to perform the installation. If additional installation files must be run as part of the installation, click **Run** to locate and run the additional installation files. When you are finished with the installation, select **I am finished installing**. Click **Next**.
~~~

8. <span data-ttu-id="a7a1b-150">**インストール**ページで、sequencer が仮想化されたアプリケーションパッケージを構成するまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-150">On the **Installation** page, wait while the sequencer configures the virtualized application package.</span></span>

9. <span data-ttu-id="a7a1b-151">[**ソフトウェアの構成**] ページで、必要に応じてパッケージに含まれるプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-151">On the **Configure Software** page, optionally run the programs contained in the package.</span></span> <span data-ttu-id="a7a1b-152">この手順によって、対象のコンピューターにパッケージを展開して実行する前に、必要なライセンスまたは構成タスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-152">This step allows you to complete any necessary license or configuration tasks before you deploy and run the package on target computers.</span></span> <span data-ttu-id="a7a1b-153">すべてのプログラムを一度に実行するには、1つ以上のプログラムを選択し、[**すべて実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-153">To run all the programs at one time, select at least one program, and then click **Run All**.</span></span> <span data-ttu-id="a7a1b-154">特定のプログラムを実行するには、プログラムを選択して、[選択して**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-154">To run specific programs, select the program or programs, and then click **Run Selected**.</span></span> <span data-ttu-id="a7a1b-155">必要な構成タスクを完了して、アプリケーションを閉じます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-155">Complete the required configuration tasks and then close the applications.</span></span> <span data-ttu-id="a7a1b-156">すべてのプログラムが実行されるまで数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-156">You may need to wait several minutes for all programs to run.</span></span>

   **<span data-ttu-id="a7a1b-157">注</span><span class="sxs-lookup"><span data-stu-id="a7a1b-157">Note</span></span>**  
   <span data-ttu-id="a7a1b-158">初めて実行するには、一覧に表示されていないアプリケーションのタスクを使用して、アプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-158">To run first-use tasks for any application that is not available in the list, open the application.</span></span> <span data-ttu-id="a7a1b-159">この手順では、関連する情報がキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-159">The associated information will be captured during this step.</span></span>



~~~
Click **Next**.
~~~

10. <span data-ttu-id="a7a1b-160">[**インストールレポート**] ページで、これまでに順序付けした仮想化されたアプリケーションパッケージに関する情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-160">On the **Installation Report** page, you can review information about the virtualized application package you have just sequenced.</span></span> <span data-ttu-id="a7a1b-161">さら**に詳しい**情報を取得するには、イベントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-161">In **Additional Information**, double-click an event to obtain more detailed information.</span></span> <span data-ttu-id="a7a1b-162">続行するには、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-162">To proceed, click **Next**.</span></span>

11. <span data-ttu-id="a7a1b-163">[**ユーザー設定**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-163">The **Customize** page is displayed.</span></span> <span data-ttu-id="a7a1b-164">仮想アプリケーションのインストールと構成が完了したら、[**今すぐ停止**] を選択し、この手順の手順14に進んでください。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-164">If you are finished installing and configuring the virtual application, select **Stop now** and skip to step 14 of this procedure.</span></span> <span data-ttu-id="a7a1b-165">次のいずれかのカスタマイズを実行するには、[**カスタマイズ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-165">To perform either of the following customizations, select **Customize**.</span></span>

    -   <span data-ttu-id="a7a1b-166">ストリーミング用の仮想パッケージを準備します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-166">Prepare the virtual package for streaming.</span></span> <span data-ttu-id="a7a1b-167">ストリーミングにより、仮想アプリケーションパッケージがターゲットコンピューターで実行されるときのエクスペリエンスが向上しました。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-167">Streaming improves the experience when the virtual application package is run on target computers.</span></span>

    -   <span data-ttu-id="a7a1b-168">このパッケージを実行できるオペレーティングシステムを指定します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-168">Specify the operating systems that can run this package.</span></span>

    <span data-ttu-id="a7a1b-169">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-169">Click **Next**.</span></span>

12. <span data-ttu-id="a7a1b-170">[**ストリーミング**] ページで、各プログラムを実行して、ターゲットコンピューターで最適化し、より効率的に実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-170">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="a7a1b-171">すべてのアプリケーションが実行されるまでに数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-171">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="a7a1b-172">すべてのアプリケーションが実行されたら、各アプリケーションを閉じて、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-172">After all applications have run, close each of the applications, and then click **Next**.</span></span>

   **<span data-ttu-id="a7a1b-173">注</span><span class="sxs-lookup"><span data-stu-id="a7a1b-173">Note</span></span>**  
   <span data-ttu-id="a7a1b-174">この手順でアプリケーションを開かない場合、既定のストリーミングメソッドはオンデマンドストリーミング配信です。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-174">If you do not open any applications during this step, the default streaming method is on-demand streaming delivery.</span></span> <span data-ttu-id="a7a1b-175">つまり、アプリは開くことができるまでビット単位でダウンロードされ、バックグラウンド読み込みの構成方法によって、アプリケーションの残りの部分が読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-175">This means applications will be downloaded bit by bit until it can be opened, and then depending on how the background loading is configured, will load the rest of the application.</span></span>



13. <span data-ttu-id="a7a1b-176">[**ターゲット OS** ] ページで、このパッケージを実行できるオペレーティングシステムを指定します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-176">On the **Target OS** page, specify the operating systems that can run this package.</span></span> <span data-ttu-id="a7a1b-177">環境内でサポートされているすべてのオペレーティングシステムでこのパッケージを実行できるようにするには、[**このパッケージをすべてのオペレーティングシステムで実行できるように**する] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-177">To allow all supported operating systems in your environment to run this package, select **Allow this package to run on any operating system**.</span></span> <span data-ttu-id="a7a1b-178">特定のオペレーティングシステムでのみ実行されるようにこのパッケージを構成するには、[**このパッケージを次のオペレーティングシステムでのみ実行できるよう**にする] を選び、このパッケージを実行できるオペレーティングシステムを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-178">To configure this package to run only on specific operating systems, select **Allow this package to run only on the following operating systems** and select the operating systems that can run this package.</span></span> <span data-ttu-id="a7a1b-179">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-179">Click **Next**.</span></span>

   **<span data-ttu-id="a7a1b-180">重要</span><span class="sxs-lookup"><span data-stu-id="a7a1b-180">Important</span></span>**  
   <span data-ttu-id="a7a1b-181">ここで指定したオペレーティングシステムが、優先順位を設定するアプリケーションによってサポートされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-181">Make sure that the operating systems you specify here are supported by the application you are sequencing.</span></span>



14. <span data-ttu-id="a7a1b-182">[**パッケージの作成**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-182">The **Create Package** page is displayed.</span></span> <span data-ttu-id="a7a1b-183">パッケージを保存せずに変更するには、パッケージ**エディターを使用してパッケージを保存せずに変更するに**は、[続行] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-183">To modify the package without saving it, select **Continue to modify package without saving using the package editor**.</span></span> <span data-ttu-id="a7a1b-184">このオプションでは、sequencer コンソールでパッケージが開き、保存する前にパッケージを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-184">This option opens the package in the sequencer console so that you can modify the package before it is saved.</span></span> <span data-ttu-id="a7a1b-185">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-185">Click **Next**.</span></span>

   <span data-ttu-id="a7a1b-186">パッケージをすぐに保存するには、[**今すぐパッケージを保存**する (既定)] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-186">To save the package immediately, select **Save the package now** (default).</span></span> <span data-ttu-id="a7a1b-187">パッケージに関連付けるオプションの**コメント**を追加します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-187">Add optional **Comments** to be associated with the package.</span></span> <span data-ttu-id="a7a1b-188">コメントは、プログラムのバージョンやパッケージに関するその他の情報を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-188">Comments are useful for identifying the program version and other information about the package.</span></span>

   **<span data-ttu-id="a7a1b-189">重要</span><span class="sxs-lookup"><span data-stu-id="a7a1b-189">Important</span></span>**  
   <span data-ttu-id="a7a1b-190">**コメント**と**説明**では、印刷できない文字がシステムでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-190">The system does not support non-printable characters in **Comments** and **Descriptions**.</span></span>



~~~
The default **Save Location** is also displayed on this page. To change the default location, click **Browse** and specify the new location. Click **Create**.
~~~

15. <span data-ttu-id="a7a1b-191">**完了**ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-191">The **Completion** page is displayed.</span></span> <span data-ttu-id="a7a1b-192">必要に応じて**仮想アプリケーションパッケージレポート**ウィンドウの情報を確認し、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-192">Review the information in the **Virtual Application Package Report** pane as needed, then click **Close**.</span></span> <span data-ttu-id="a7a1b-193">この情報は、パッケージを作成したディレクトリにある**Report.xml**ファイルでも確認できます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-193">This information is also available in the **Report.xml** file that is located in the directory where the package was created.</span></span>

   <span data-ttu-id="a7a1b-194">このパッケージは、sequencer で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-194">The package is now available in the sequencer.</span></span>

   **<span data-ttu-id="a7a1b-195">重要</span><span class="sxs-lookup"><span data-stu-id="a7a1b-195">Important</span></span>**  
   <span data-ttu-id="a7a1b-196">仮想アプリケーションパッケージを正常に作成した後、sequencer を実行しているコンピューターで仮想アプリケーションパッケージを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-196">After you have successfully created a virtual application package, you cannot run the virtual application package on the computer that is running the sequencer.</span></span>



**<span data-ttu-id="a7a1b-197">アドオンまたはプラグインアプリケーションの順序を管理するには</span><span class="sxs-lookup"><span data-stu-id="a7a1b-197">To sequence an add-on or plug-in application</span></span>**

1.  

    **<span data-ttu-id="a7a1b-198">注</span><span class="sxs-lookup"><span data-stu-id="a7a1b-198">Note</span></span>**  
    <span data-ttu-id="a7a1b-199">次の手順を実行する前に、sequencer を実行しているコンピューターに親アプリケーションをローカルにインストールします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-199">Before performing the following procedure, install the parent application locally on the computer that is running the sequencer.</span></span> <span data-ttu-id="a7a1b-200">または、親アプリケーションが仮想化されている場合は、アドオンまたはプラグインのワークフローの手順に従って、コンピューター上の親アプリケーションを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-200">Or if you have the parent application virtualized, you can follow the steps in the add-on or plug-in workflow to unpack the parent application on the computer.</span></span>

    <span data-ttu-id="a7a1b-201">たとえば、Microsoft Excel のプラグインの順序を付ける場合は、sequencer を実行しているコンピューターに Microsoft Excel をローカルにインストールします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-201">For example, if you are sequencing a plug-in for Microsoft Excel, install Microsoft Excel locally on the computer that is running the sequencer.</span></span> <span data-ttu-id="a7a1b-202">また、アプリケーションがターゲットコンピューターにインストールされているディレクトリに、親アプリケーションもインストールします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-202">Also install the parent application in the same directory where the application is installed on target computers.</span></span> <span data-ttu-id="a7a1b-203">プラグインまたはアドオンを既存の仮想アプリケーションパッケージと共に使用する場合は、親仮想アプリケーションパッケージを作成したときに使用したのと同じ仮想アプリケーションドライブにアプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-203">If the plug-in or add-on is going to be used with an existing virtual application package, install the application on the same virtual application drive that was used when you created the parent virtual application package.</span></span>



~~~
On the computer that runs the sequencer, click **All Programs**, and then Click **Microsoft Application Virtualization**, and then click **Microsoft Application Virtualization Sequencer**.
~~~

2. <span data-ttu-id="a7a1b-204">*<strong><em>Sequencer で、[* </em> 新しい仮想アプリケーションパッケージの作成] をクリックし </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-204">\*<strong><em>In the sequencer, click \*</em>Create a New Virtual Application Package</strong>.</span></span> <span data-ttu-id="a7a1b-205">[**パッケージの作成 (既定)**] を選び、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-205">Select **Create Package (default)**, and then click **Next**.</span></span>

3. <span data-ttu-id="a7a1b-206">[**コンピューターの準備**] ページで、パッケージの作成に失敗する可能性がある問題、またはパッケージに不要なデータが含まれている可能性がある問題を確認します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-206">On the **Prepare Computer** page, review the issues that might cause the package creation to fail or could cause the package to contain unnecessary data.</span></span> <span data-ttu-id="a7a1b-207">続行する前に、発生する可能性があるすべての問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-207">You should resolve all potential issues before you continue.</span></span> <span data-ttu-id="a7a1b-208">修正が完了したら、[**更新**] をクリックして更新された情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-208">After making any corrections, click **Refresh** to display the updated information.</span></span> <span data-ttu-id="a7a1b-209">すべての潜在的な問題を解決したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-209">After you have resolved all potential issues, click **Next**.</span></span>

   **<span data-ttu-id="a7a1b-210">重要</span><span class="sxs-lookup"><span data-stu-id="a7a1b-210">Important</span></span>**  
   <span data-ttu-id="a7a1b-211">ウイルススキャンソフトウェアを無効にする必要がある場合は、まず sequencer を実行するコンピューターをスキャンして、不要なファイルや悪意のあるファイルがパッケージに追加されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-211">If you are required to disable virus scanning software, you should first scan the computer that runs the sequencer in order to ensure that no unwanted or malicious files could be added to the package.</span></span>



4. <span data-ttu-id="a7a1b-212">[**アプリケーションの種類**] ページで、[**アドオンまたはプラグイン**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-212">On the **Type of Application** page, select **Add-on or Plug-in**, and then click **Next**.</span></span>

5. <span data-ttu-id="a7a1b-213">[**インストーラーの選択**] ページで [**参照**] をクリックし、アドオンまたはプラグインのインストールファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-213">On the **Select Installer** page, click **Browse** and specify the installation file for the add-on or plug-in.</span></span> <span data-ttu-id="a7a1b-214">アドオンまたはプラグインに関連するインストーラファイルがなく、すべてのインストール手順を手動で実行する場合は、[**このオプションを選択してカスタムインストールを実行**する] チェックボックスをオンにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-214">If the add-on or plug-in does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

6. <span data-ttu-id="a7a1b-215">[**インストールプライマリ**] ページで、sequencer を実行しているコンピューターにプライマリアプリケーションがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-215">On the **Install Primary** page, ensure that the primary application is installed on the computer that runs the sequencer.</span></span> <span data-ttu-id="a7a1b-216">または、sequencer を実行するコンピューターにローカルに保存されている既存のパッケージを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-216">Alternatively, you can expand an existing package that has been saved locally on the computer that runs the sequencer.</span></span> <span data-ttu-id="a7a1b-217">これを行うには、[**パッケージの展開**] をクリックして、パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-217">To do this, click **Expand Package**, and then select the package.</span></span> <span data-ttu-id="a7a1b-218">親プログラムを展開またはインストールしたら、[**プライマリ親プログラムをインストールしまし**た] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-218">After you have expanded or installed the parent program, select **I have installed the primary parent program**.</span></span>

   <span data-ttu-id="a7a1b-219">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-219">Click **Next**.</span></span>

7. <span data-ttu-id="a7a1b-220">[**パッケージ名**] ページで、パッケージに関連付ける名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-220">On the **Package Name** page, type a name that will be associated with the package.</span></span> <span data-ttu-id="a7a1b-221">パッケージに追加されるアプリケーションの目的とバージョンを識別するのに役立つ名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-221">Use a name that helps identify the purpose and version of the application that will be added to the package.</span></span> <span data-ttu-id="a7a1b-222">パッケージ名は、App-v 5.0 管理コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-222">The package name will be displayed in the App-V 5.0 Management Console.</span></span> <span data-ttu-id="a7a1b-223">**プライマリ仮想アプリケーションディレクトリ**には、アプリケーションのインストール先のパスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-223">The **Primary Virtual Application Directory** displays the path where the application will be installed.</span></span> <span data-ttu-id="a7a1b-224">この場所を指定するには、パスを入力するか、[**参照**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-224">To specify this location, type the path, or click **Browse**.</span></span>

   **<span data-ttu-id="a7a1b-225">注</span><span class="sxs-lookup"><span data-stu-id="a7a1b-225">Note</span></span>**  
   <span data-ttu-id="a7a1b-226">App-v 5.0 SP3 以降、プライマリ仮想アプリケーションディレクトリ (PVAD) は非表示になっていますが、オンに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-226">Starting in App-V 5.0 SP3, the primary virtual application directory (PVAD) is hidden, but you can turn it back on.</span></span> <span data-ttu-id="a7a1b-227">「 [App-v 5.0 SP3 につい](about-app-v-50-sp3.md#bkmk-pvad-hidden)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-227">See [About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-pvad-hidden).</span></span>



~~~
Click **Next**.
~~~

8. <span data-ttu-id="a7a1b-228">**インストール**ページで、sequencer とアプリケーションインストーラーの準備ができたら、プラグインまたはアドインアプリケーションをインストールして、sequencer がインストールプロセスを監視できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-228">On the **Installation** page, when the sequencer and application installer are ready you can proceed to install the plug-in or add-in application so the sequencer can monitor the installation process.</span></span> <span data-ttu-id="a7a1b-229">アプリケーションのインストールプロセスを使用して、インストールを実行します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-229">Use the application's installation process to perform the installation.</span></span> <span data-ttu-id="a7a1b-230">インストールの一部として追加のインストールファイルを実行する必要がある場合は、[**実行**] をクリックして、追加のインストールファイルを見つけて実行します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-230">If additional installation files must be run as part of the installation, click **Run** and locate and run the additional installation files.</span></span> <span data-ttu-id="a7a1b-231">インストールが完了したら、[インストールを**完了**しました] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-231">When you are finished with the installation, select **I am finished installing**, and then click **Next**.</span></span>

9. <span data-ttu-id="a7a1b-232">[**インストールレポート**] ページで、順序付けした仮想アプリケーションパッケージに関する情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-232">On the **Installation Report** page, you can review information about the virtual application package that you just sequenced.</span></span> <span data-ttu-id="a7a1b-233">[**追加情報**] に表示される情報について詳しくは、イベントをダブルクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-233">For a more detailed explanation about the information displayed in **Additional Information**, double-click the event.</span></span> <span data-ttu-id="a7a1b-234">情報を確認したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-234">After you have reviewed the information, click **Next**.</span></span>

10. <span data-ttu-id="a7a1b-235">[**ユーザー設定**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-235">The **Customize** page is displayed.</span></span> <span data-ttu-id="a7a1b-236">仮想アプリケーションのインストールと構成が完了したら、[**今すぐ停止**] を選んで、この手順の手順12に進んでください。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-236">If you are finished installing and configuring the virtual application, select **Stop now** and skip to step 12 of this procedure.</span></span> <span data-ttu-id="a7a1b-237">次のいずれかのカスタマイズを実行するには、[**カスタマイズ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-237">To perform either of the following customizations, select **Customize**.</span></span>

    -   <span data-ttu-id="a7a1b-238">低速または信頼性の低いネットワークでパッケージが実行される方法を最適化します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-238">Optimize how the package will run across a slow or unreliable network.</span></span>

    -   <span data-ttu-id="a7a1b-239">このパッケージを実行できるオペレーティングシステムを指定します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-239">Specify the operating systems that can run this package.</span></span>

    <span data-ttu-id="a7a1b-240">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-240">Click **Next**.</span></span>

11. <span data-ttu-id="a7a1b-241">[**ストリーミング**] ページで、各プログラムを実行して、ターゲットコンピューターで最適化し、より効率的に実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-241">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="a7a1b-242">ストリーミングによって、仮想アプリケーションパッケージが、待機時間の長いネットワーク上のターゲットコンピューターで実行されると、エクスペリエンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-242">Streaming improves the experience when the virtual application package is run on target computers on high-latency networks.</span></span> <span data-ttu-id="a7a1b-243">すべてのアプリケーションが実行されるまでに数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-243">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="a7a1b-244">すべてのアプリケーションが実行されたら、各アプリケーションを終了します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-244">After all applications have run, close each of the applications.</span></span> <span data-ttu-id="a7a1b-245">また、アプリを開く前に完全にダウンロードされるようにするには、[**アプリケーションの強制ダウンロード**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-245">You can also configure the package to be required to be fully downloaded before opening by selecting the **Force applications to be downloaded** check-box.</span></span> <span data-ttu-id="a7a1b-246">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-246">Click **Next**.</span></span>

   **<span data-ttu-id="a7a1b-247">注</span><span class="sxs-lookup"><span data-stu-id="a7a1b-247">Note</span></span>**  
   <span data-ttu-id="a7a1b-248">必要に応じて、この手順を実行すると、アプリケーションの読み込みが停止することがあります。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-248">If necessary, you can stop an application from loading during this step.</span></span> <span data-ttu-id="a7a1b-249">[**アプリケーションの起動**] ダイアログボックスで、[**停止**] をクリックし、いずれかのチェックボックスをオンにします。すべての**アプリケーションを終了**するか、**このアプリケーションのみを停止**します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-249">In the **Application Launch** dialog box, click **Stop** and select one of the check boxes: **Stop all applications** or **Stop this application only**.</span></span>



12. <span data-ttu-id="a7a1b-250">[**ターゲット OS** ] ページで、このパッケージを実行できるオペレーティングシステムを指定します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-250">On the **Target OS** page, specify the operating systems that can run this package.</span></span> <span data-ttu-id="a7a1b-251">環境内でサポートされているすべてのオペレーティングシステムでこのパッケージを実行できるようにするには、[**このパッケージをすべてのオペレーティングシステムで実行できるよう**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-251">To allow all supported operating systems in your environment to run this package, select the **Allow this package to run on any operating system** check box.</span></span> <span data-ttu-id="a7a1b-252">特定のオペレーティングシステムでのみ実行されるようにこのパッケージを構成するには、[**次のオペレーティングシステムでのみこのパッケージを実行**する] チェックボックスをオンにして、このパッケージを実行できるオペレーティングシステムを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-252">To configure this package to run only on specific operating systems, select the **Allow this package to run only on the following operating systems** check box, and then select the operating systems that can run this package.</span></span> <span data-ttu-id="a7a1b-253">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-253">Click **Next**.</span></span>

13. <span data-ttu-id="a7a1b-254">[**パッケージの作成**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-254">The **Create Package** page is displayed.</span></span> <span data-ttu-id="a7a1b-255">パッケージを保存せずに変更するには、[**パッケージエディターを使ってパッケージを保存せずに変更するには、続行する**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-255">To modify the package without saving it, select **Continue to modify package without saving using the package editor** check box.</span></span> <span data-ttu-id="a7a1b-256">このオプションでは、sequencer コンソールでパッケージが開き、保存する前にパッケージを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-256">This option opens the package in the sequencer console so that you can modify the package before it is saved.</span></span> <span data-ttu-id="a7a1b-257">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-257">Click **Next**.</span></span>

   <span data-ttu-id="a7a1b-258">パッケージを今すぐ保存するには、[**パッケージの保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-258">To save the package immediately, select **Save the package now**.</span></span> <span data-ttu-id="a7a1b-259">必要に応じて、パッケージに関連付けられている**説明**を追加します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-259">Optionally, add a **Description** that will be associated with the package.</span></span> <span data-ttu-id="a7a1b-260">説明は、パッケージについてのバージョンとその他の情報を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-260">Descriptions are useful for identifying the version and other information about the package.</span></span>

   **<span data-ttu-id="a7a1b-261">重要</span><span class="sxs-lookup"><span data-stu-id="a7a1b-261">Important</span></span>**  
   <span data-ttu-id="a7a1b-262">コメントと説明では、印刷できない文字がシステムでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-262">The system does not support non-printable characters in Comments and Descriptions.</span></span>



~~~
The default **Save Location** is also displayed on this page. To change the default location, click **Browse** and specify the new location. Click **Create**.
~~~

**<span data-ttu-id="a7a1b-263">ミドルウェアアプリケーションのシーケンスを行うには</span><span class="sxs-lookup"><span data-stu-id="a7a1b-263">To sequence a middleware application</span></span>**

1. <span data-ttu-id="a7a1b-264">Sequencer を実行しているコンピューターで、[**すべてのプログラム**]、[ **microsoft application virtualization**]、[ **microsoft application virtualization sequencer**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-264">On the computer that runs the sequencer, click **All Programs**, and then Click **Microsoft Application Virtualization**, and then click **Microsoft Application Virtualization Sequencer**.</span></span>

2. <span data-ttu-id="a7a1b-265">*<strong><em>Sequencer で、[* </em> 新しい仮想アプリケーションパッケージの作成] をクリックし </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-265">\*<strong><em>In the sequencer, click \*</em>Create a New Virtual Application Package</strong>.</span></span> <span data-ttu-id="a7a1b-266">[**パッケージの作成 (既定)**] を選び、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-266">Select **Create Package (default)**, and then click **Next**.</span></span>

3. <span data-ttu-id="a7a1b-267">[**コンピューターの準備**] ページで、パッケージの作成に失敗する可能性がある問題、またはパッケージに不要なデータが含まれている可能性がある問題を確認します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-267">On the **Prepare Computer** page, review the issues that could cause the package creation to fail or could cause the package to contain unnecessary data.</span></span> <span data-ttu-id="a7a1b-268">続行する前に、発生する可能性があるすべての問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-268">You should resolve all potential issues before you continue.</span></span> <span data-ttu-id="a7a1b-269">修正が完了したら、[**更新**] をクリックして更新された情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-269">After making any corrections, click **Refresh** to display the updated information.</span></span> <span data-ttu-id="a7a1b-270">すべての潜在的な問題を解決したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-270">After you have resolved all potential issues, click **Next**.</span></span>

   **<span data-ttu-id="a7a1b-271">重要</span><span class="sxs-lookup"><span data-stu-id="a7a1b-271">Important</span></span>**  
   <span data-ttu-id="a7a1b-272">ウイルススキャンソフトウェアを無効にする必要がある場合は、まず、不要なファイルまたは悪意のあるファイルがパッケージに追加されないように、アプリ-V 5.0 Sequencer を実行しているコンピューターをスキャンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-272">If you are required to disable virus scanning software, you should first scan the computer that runs the App-V 5.0 Sequencer in order to ensure that no unwanted or malicious files can be added to the package.</span></span>



4. <span data-ttu-id="a7a1b-273">[**アプリケーションの種類**] ページで、[**ミドルウェア**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-273">On the **Type of Application** page, select **Middleware**, and then click **Next**.</span></span>

5. <span data-ttu-id="a7a1b-274">[**インストーラーの選択**] ページで [**参照**] をクリックして、アプリケーションのインストールファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-274">On the **Select Installer** page, click **Browse** and specify the installation file for the application.</span></span> <span data-ttu-id="a7a1b-275">アプリケーションに関連付けられたインストーラーファイルがなく、インストール手順を手動で実行する場合は、[**このオプションを選択してカスタムインストールを実行**する] チェックボックスをオンにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-275">If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

6. <span data-ttu-id="a7a1b-276">[**パッケージ名**] ページで、パッケージに関連付ける名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-276">On the **Package Name** page, type a name that will be associated with the package.</span></span> <span data-ttu-id="a7a1b-277">パッケージに追加されるアプリケーションの目的とバージョンを識別するのに役立つ名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-277">Use a name that helps identify the purpose and version of the application that will be added to the package.</span></span> <span data-ttu-id="a7a1b-278">パッケージ名は、App-v 5.0 管理コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-278">The package name is displayed in the App-V 5.0 Management Console.</span></span> <span data-ttu-id="a7a1b-279">**プライマリ仮想アプリケーションディレクトリ**には、アプリケーションのインストール先のパスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-279">The **Primary Virtual Application Directory** displays the path where the application will be installed.</span></span> <span data-ttu-id="a7a1b-280">この場所を指定するには、パスを入力するか、[**参照**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-280">To specify this location, type the path or click **Browse**.</span></span>

   <span data-ttu-id="a7a1b-281">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-281">Click **Next**.</span></span>

7. <span data-ttu-id="a7a1b-282">**インストール**ページで、sequencer とミドルウェアアプリケーションのインストーラーの準備ができたら、アプリをインストールして、sequencer がインストールプロセスを監視できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-282">On the **Installation** page, when the sequencer and middleware application installer are ready you can proceed to install the application so that the sequencer can monitor the installation process.</span></span> <span data-ttu-id="a7a1b-283">アプリケーションのインストールプロセスを使用して、インストールを実行します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-283">Use the application's installation process to perform the installation.</span></span> <span data-ttu-id="a7a1b-284">インストールの一部として追加のインストールファイルを実行する必要がある場合は、[**実行**] をクリックして、追加のインストールファイルを見つけて実行します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-284">If additional installation files must be run as part of the installation, click **Run**, to locate and run the additional installation files.</span></span> <span data-ttu-id="a7a1b-285">インストールが完了したら、[**インストールを完了**しました] チェックボックスをオンにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-285">When you are finished with the installation, select the **I am finished installing** check box, and then click **Next**.</span></span>

8. <span data-ttu-id="a7a1b-286">**インストール**ページで、sequencer が仮想アプリケーションパッケージを構成するまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-286">On the **Installation** page, wait while the sequencer configures the virtual application package.</span></span>

9. <span data-ttu-id="a7a1b-287">[**インストールレポート**] ページで、順序付けされた仮想アプリケーションパッケージに関する情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-287">On the **Installation Report** page, you can review information about the virtual application package that you have just sequenced.</span></span> <span data-ttu-id="a7a1b-288">さら**に詳しい**情報を取得するには、イベントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-288">In **Additional Information**, double-click an event to obtain more detailed information.</span></span> <span data-ttu-id="a7a1b-289">続行するには、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-289">To proceed, click **Next**.</span></span>

10. <span data-ttu-id="a7a1b-290">[**ターゲット OS** ] ページで、このパッケージを実行できるオペレーティングシステムを指定します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-290">On the **Target OS** page, specify the operating systems that can run this package.</span></span> <span data-ttu-id="a7a1b-291">環境でサポートされているすべてのオペレーティングシステムでこのパッケージを実行できるようにするには、[**このパッケージをすべてのオペレーティングシステムで実行できるよう**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-291">To enable all supported operating systems in your environment to run this package, select the **Allow this package to run on any operating system** check box.</span></span> <span data-ttu-id="a7a1b-292">特定のオペレーティングシステムのみで実行するようにこのパッケージを構成するには、[**次のオペレーティングシステムでのみこのパッケージを実行**する] チェックボックスをオンにして、このパッケージを実行できるオペレーティングシステムを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-292">To configure this package to run only on specific operating systems, select the **Allow this package to run only on the following operating systems** check box and select the operating systems that can run this package.</span></span> <span data-ttu-id="a7a1b-293">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-293">Click **Next**.</span></span>

11. <span data-ttu-id="a7a1b-294">[**パッケージの作成**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-294">On the **Create Package** page is displayed.</span></span> <span data-ttu-id="a7a1b-295">パッケージを保存せずに変更するには、パッケージ**エディターを使用してパッケージを保存せずに変更するに**は、[続行] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-295">To modify the package without saving it, select **Continue to modify package without saving using the package editor**.</span></span> <span data-ttu-id="a7a1b-296">このオプションでは、sequencer コンソールでパッケージが開き、保存する前にパッケージを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-296">This option opens the package in the sequencer console so that you can modify the package before it is saved.</span></span> <span data-ttu-id="a7a1b-297">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-297">Click **Next**.</span></span>

    <span data-ttu-id="a7a1b-298">パッケージを今すぐ保存するには、[**パッケージの保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-298">To save the package immediately, select **Save the package now**.</span></span> <span data-ttu-id="a7a1b-299">必要に応じて、パッケージに関連付ける**説明**を追加します。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-299">Optionally, add a **Description** to be associated with the package.</span></span> <span data-ttu-id="a7a1b-300">説明は、プログラムのバージョンやパッケージに関するその他の情報を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-300">Descriptions are useful for identifying the program version and other information about the package.</span></span>

    **<span data-ttu-id="a7a1b-301">重要</span><span class="sxs-lookup"><span data-stu-id="a7a1b-301">Important</span></span>**  
    <span data-ttu-id="a7a1b-302">コメントと説明では、印刷できない文字がシステムでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-302">The system does not support non-printable characters in Comments and Descriptions.</span></span>



~~~
The default **Save Location** is also displayed on this page. To change the default location, click **Browse** and specify the new location. Click **Create**.
~~~

12. <span data-ttu-id="a7a1b-303">**完了**ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-303">The **Completion** page is displayed.</span></span> <span data-ttu-id="a7a1b-304">必要に応じて**仮想アプリケーションパッケージレポート**ウィンドウの情報を確認し、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-304">Review the information in the **Virtual Application Package Report** pane as needed, then click **Close**.</span></span> <span data-ttu-id="a7a1b-305">この情報は、この手順の手順11で指定したディレクトリにある**Report.xml**ファイルでも確認できます。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-305">This information is also available in the **Report.xml** file that is located in the directory specified in step 11 of this procedure.</span></span>

   <span data-ttu-id="a7a1b-306">このパッケージは、sequencer で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-306">The package is now available in the sequencer.</span></span> <span data-ttu-id="a7a1b-307">パッケージのプロパティを編集するには、[ **\ [パッケージ名 \] の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-307">To edit the package properties, click **Edit \[Package Name\]**.</span></span>

   **<span data-ttu-id="a7a1b-308">重要</span><span class="sxs-lookup"><span data-stu-id="a7a1b-308">Important</span></span>**  
   <span data-ttu-id="a7a1b-309">仮想アプリケーションパッケージを正常に作成した後、sequencer を実行しているコンピューターで仮想アプリケーションパッケージを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="a7a1b-309">After you have successfully created a virtual application package, you cannot run the virtual application package on the computer that is running the sequencer.</span></span>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="a7a1b-310">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a7a1b-310">Related topics</span></span>


[<span data-ttu-id="a7a1b-311">APP-V 5.0 の操作</span><span class="sxs-lookup"><span data-stu-id="a7a1b-311">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)









