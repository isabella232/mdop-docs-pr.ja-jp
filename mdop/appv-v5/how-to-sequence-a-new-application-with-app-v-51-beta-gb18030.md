---
title: APP-V 5.1 を使用して新しいアプリケーションをシーケンス処理する方法
description: APP-V 5.1 を使用して新しいアプリケーションをシーケンス処理する方法
author: dansimp
ms.assetid: 7d7699b1-0cb8-450d-94e7-5af937e16c21
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 43edd9357e31f4884ed7baec3d35fa01bf2abe54
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813715"
---
# <span data-ttu-id="f0c78-103">APP-V 5.1 を使用して新しいアプリケーションをシーケンス処理する方法</span><span class="sxs-lookup"><span data-stu-id="f0c78-103">How to Sequence a New Application with App-V 5.1</span></span>


**<span data-ttu-id="f0c78-104">順序付けを開始する前に確認または実行するには</span><span class="sxs-lookup"><span data-stu-id="f0c78-104">To review or do before you start sequencing</span></span>**

1.  <span data-ttu-id="f0c78-105">作成する仮想化されたアプリケーションパッケージの種類を特定します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-105">Determine the type of virtualized application package you want to create:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="f0c78-106">アプリケーションの種類</span><span class="sxs-lookup"><span data-stu-id="f0c78-106">Application type</span></span></th>
    <th align="left"><span data-ttu-id="f0c78-107">説明</span><span class="sxs-lookup"><span data-stu-id="f0c78-107">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="f0c78-108">標準</span><span class="sxs-lookup"><span data-stu-id="f0c78-108">Standard</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f0c78-109">アプリケーションまたは一連のアプリケーションを含むパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-109">Creates a package that contains an application or a suite of applications.</span></span> <span data-ttu-id="f0c78-110">これは、ほとんどのアプリケーションの種類で推奨されるオプションです。</span><span class="sxs-lookup"><span data-stu-id="f0c78-110">This is the preferred option for most application types.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="f0c78-111">アドオンまたはプラグイン</span><span class="sxs-lookup"><span data-stu-id="f0c78-111">Add-on or plug-in</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f0c78-112">Microsoft Excel のプラグインなど、標準アプリケーションの機能を拡張するパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-112">Creates a package that extends the functionality of a standard application, for example, a plug-in for Microsoft Excel.</span></span> <span data-ttu-id="f0c78-113">さらに、ネイティブにインストールされたアプリケーションの場合、または接続グループを使用してリンクされている別のパッケージの場合は、プラグインを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-113">Additionally, you can use plug-ins for natively installed applications, or for another package that is linked by using connection groups.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="f0c78-114">ミドルウェア</span><span class="sxs-lookup"><span data-stu-id="f0c78-114">Middleware</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f0c78-115">標準アプリケーション (たとえば、Java) で必要なパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-115">Creates a package that is required by a standard application, for example, Java.</span></span> <span data-ttu-id="f0c78-116">ミドルウェアパッケージは、接続グループを使用して他のパッケージにリンクするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-116">Middleware packages are used for linking to other packages by using connection groups.</span></span></p></td>
    </tr>
    </tbody>
    </table>



2.  <span data-ttu-id="f0c78-117">必要なすべてのインストールファイルを、sequencer を実行しているコンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-117">Copy all required installation files to the computer that is running the sequencer.</span></span>

3.  <span data-ttu-id="f0c78-118">アプリケーションの順序を設定する前に、仮想環境のバックアップイメージを作成してから、アプリケーションのシーケンスを完了した後でそのイメージに戻します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-118">Make a backup image of your virtual environment before sequencing an application, and then revert to that image each time after you finish sequencing an application.</span></span>

4.  <span data-ttu-id="f0c78-119">次の項目を確認します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-119">Review the following items:</span></span>

    -   <span data-ttu-id="f0c78-120">アプリケーションのインストーラーによって、新規または既存のファイルまたはディレクトリへのセキュリティアクセスが変更された場合、これらの変更はパッケージ内でキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="f0c78-120">If an application installer changes the security access to a new or existing file or directory, those changes are not captured in the package.</span></span>

    -   <span data-ttu-id="f0c78-121">仮想化されたパッケージのターゲットボリュームに対して短いパスが無効になっている場合は、作成された後もショートパスを無効にしているボリュームにパッケージをシーケンスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0c78-121">If short paths have been disabled for the virtualized package’s target volume, you must also sequence the package to a volume that was created and still has short-paths disabled.</span></span> <span data-ttu-id="f0c78-122">システムボリュームにすることはできません。</span><span class="sxs-lookup"><span data-stu-id="f0c78-122">It cannot be the system volume.</span></span>

> [!NOTE]  
> <span data-ttu-id="f0c78-123">App-v Sequencer は、"CO_ x" と一致するファイル名を使ったアプリケーションのシーケンスを行うことはできません &lt; &gt; 。 x は任意の数字です。</span><span class="sxs-lookup"><span data-stu-id="f0c78-123">The App-V 5.x Sequencer cannot sequence applications with filenames matching "CO_&lt;x&gt;" where x is any numeral.</span></span> <span data-ttu-id="f0c78-124">エラー0x8007139F が生成されます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-124">Error 0x8007139F will be generated.</span></span>

**<span data-ttu-id="f0c78-125">新しい標準アプリケーションを順序を作成するには</span><span class="sxs-lookup"><span data-stu-id="f0c78-125">To sequence a new standard application</span></span>**

1.  <span data-ttu-id="f0c78-126">Sequencer を実行しているコンピューターで、[**すべてのプログラム**]、[ **microsoft application virtualization**]、[ **microsoft application virtualization sequencer**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-126">On the computer that runs the sequencer, click **All Programs**, and then Click **Microsoft Application Virtualization**, and then click **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="f0c78-127">Sequencer で、[**新しい仮想アプリケーションパッケージの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-127">In the sequencer, click **Create a New Virtual Application Package**.</span></span> <span data-ttu-id="f0c78-128">[**パッケージの作成 (既定)**] を選び、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-128">Select **Create Package (default)**, and then click **Next**.</span></span>

3.  <span data-ttu-id="f0c78-129">[**コンピューターの準備**] ページで、パッケージの作成に失敗する可能性がある問題、またはパッケージに不要なデータが含まれている可能性がある問題を確認します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-129">On the **Prepare Computer** page, review the issues that could cause the package creation to fail or could cause the package to contain unnecessary data.</span></span> <span data-ttu-id="f0c78-130">続行する前に、発生する可能性があるすべての問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0c78-130">You should resolve all potential issues before you continue.</span></span> <span data-ttu-id="f0c78-131">修正が完了したら、[**更新**] をクリックして更新された情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-131">After making any corrections, click **Refresh** to display the updated information.</span></span> <span data-ttu-id="f0c78-132">すべての潜在的な問題を解決したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-132">After you have resolved all potential issues, click **Next**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f0c78-133">ウイルススキャンソフトウェアを無効にする必要がある場合は、まず sequencer を実行するコンピューターをスキャンして、不要なファイルや悪意のあるファイルがパッケージに追加されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0c78-133">If you are required to disable virus scanning software, you should first scan the computer that runs the sequencer in order to ensure that no unwanted or malicious files could be added to the package.</span></span>



~~~
> [!NOTE]  
> There is currently no way to disable Windows Defender in Windows 10. If you receive a warning, you can safely ignore it. It is unlikely that Windows Defender will affect sequencing at all.
~~~



4. <span data-ttu-id="f0c78-134">[**アプリケーションの種類**] ページで、[**標準アプリケーション (既定)** ] チェックボックスをオンにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-134">On the **Type of Application** page, click the **Standard Application (default)** check box, and then click **Next**.</span></span>

5. <span data-ttu-id="f0c78-135">[**インストーラーの選択**] ページで [**参照**] をクリックして、アプリケーションのインストールファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-135">On the **Select Installer** page, click **Browse** and specify the installation file for the application.</span></span>

   > [!NOTE]  
   > <span data-ttu-id="f0c78-136">指定したアプリケーションインストーラーによって、既存または新規のファイルまたはディレクトリへのセキュリティアクセスが変更された場合、関連付けられた変更はパッケージにキャプチャされません。</span><span class="sxs-lookup"><span data-stu-id="f0c78-136">If the specified application installer modifies security access to a file or directory, existing or new, the associated changes will not be captured into the package.</span></span>



~~~
If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Perform a Custom Installation** check box, and then Click **Next**.
~~~

6. <span data-ttu-id="f0c78-137">[**パッケージ名**] ページで、パッケージに関連付ける名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-137">On the **Package Name** page, type a name that will be associated with the package.</span></span> <span data-ttu-id="f0c78-138">パッケージに追加されるアプリケーションの目的とバージョンを識別するのに役立つ名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-138">Use a name that helps identify the purpose and version of the application that will be added to the package.</span></span> <span data-ttu-id="f0c78-139">パッケージ名は、App-v 5.0 管理コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-139">The package name is displayed in the App-V 5.0 Management Console.</span></span>

   <span data-ttu-id="f0c78-140">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-140">Click **Next**.</span></span>

7. <span data-ttu-id="f0c78-141">**インストール**ページで、sequencer とアプリケーションインストーラーの準備ができたら、アプリのインストールを続行して、sequencer がインストールプロセスを監視できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-141">On the **Installation** page, when the sequencer and application installer are ready you can proceed to install the application so that the sequencer can monitor the installation process.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="f0c78-142">常にセキュリティで保護された場所にアプリケーションをインストールし、監視中に sequencer を実行しているコンピューターに他のユーザーがログオンしていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0c78-142">You should always install applications to a secure location and make sure no other users are logged on to the computer running the sequencer during monitoring.</span></span>



~~~
Use the application's installation process to perform the installation. If additional installation files must be run as part of the installation, click **Run** to locate and run the additional installation files. When you are finished with the installation, select **I am finished installing**. Click **Next**.
~~~

8. <span data-ttu-id="f0c78-143">**インストール**ページで、sequencer が仮想化されたアプリケーションパッケージを構成するまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-143">On the **Installation** page, wait while the sequencer configures the virtualized application package.</span></span>

9. <span data-ttu-id="f0c78-144">[**ソフトウェアの構成**] ページで、必要に応じてパッケージに含まれるプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-144">On the **Configure Software** page, optionally run the programs contained in the package.</span></span> <span data-ttu-id="f0c78-145">この手順によって、対象のコンピューターにパッケージを展開して実行する前に、必要なライセンスまたは構成タスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-145">This step allows you to complete any necessary license or configuration tasks before you deploy and run the package on target computers.</span></span> <span data-ttu-id="f0c78-146">すべてのプログラムを一度に実行するには、1つ以上のプログラムを選択し、[**すべて実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-146">To run all the programs at one time, select at least one program, and then click **Run All**.</span></span> <span data-ttu-id="f0c78-147">特定のプログラムを実行するには、プログラムを選択して、[選択して**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-147">To run specific programs, select the program or programs, and then click **Run Selected**.</span></span> <span data-ttu-id="f0c78-148">必要な構成タスクを完了して、アプリケーションを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-148">Complete the required configuration tasks and then close the applications.</span></span> <span data-ttu-id="f0c78-149">すべてのプログラムが実行されるまで数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="f0c78-149">You may need to wait several minutes for all programs to run.</span></span>

   > [!NOTE]  
   > <span data-ttu-id="f0c78-150">初めて実行するには、一覧に表示されていないアプリケーションのタスクを使用して、アプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-150">To run first-use tasks for any application that is not available in the list, open the application.</span></span> <span data-ttu-id="f0c78-151">この手順では、関連する情報がキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-151">The associated information will be captured during this step.</span></span>



~~~
Click **Next**.
~~~

10. <span data-ttu-id="f0c78-152">[**インストールレポート**] ページで、これまでに順序付けした仮想化されたアプリケーションパッケージに関する情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-152">On the **Installation Report** page, you can review information about the virtualized application package you have just sequenced.</span></span> <span data-ttu-id="f0c78-153">さら**に詳しい**情報を取得するには、イベントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-153">In **Additional Information**, double-click an event to obtain more detailed information.</span></span> <span data-ttu-id="f0c78-154">続行するには、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-154">To proceed, click **Next**.</span></span>

11. <span data-ttu-id="f0c78-155">[**ユーザー設定**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-155">The **Customize** page is displayed.</span></span> <span data-ttu-id="f0c78-156">仮想アプリケーションのインストールと構成が完了したら、[**今すぐ停止**] を選択し、この手順の手順14に進んでください。</span><span class="sxs-lookup"><span data-stu-id="f0c78-156">If you are finished installing and configuring the virtual application, select **Stop now** and skip to step 14 of this procedure.</span></span> <span data-ttu-id="f0c78-157">次のいずれかのカスタマイズを実行するには、[**カスタマイズ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-157">To perform either of the following customizations, select **Customize**.</span></span>

    -   <span data-ttu-id="f0c78-158">ストリーミング用の仮想パッケージを準備します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-158">Prepare the virtual package for streaming.</span></span> <span data-ttu-id="f0c78-159">ストリーミングにより、仮想アプリケーションパッケージがターゲットコンピューターで実行されるときのエクスペリエンスが向上しました。</span><span class="sxs-lookup"><span data-stu-id="f0c78-159">Streaming improves the experience when the virtual application package is run on target computers.</span></span>

    -   <span data-ttu-id="f0c78-160">このパッケージを実行できるオペレーティングシステムを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-160">Specify the operating systems that can run this package.</span></span>

    <span data-ttu-id="f0c78-161">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-161">Click **Next**.</span></span>

12. <span data-ttu-id="f0c78-162">[**ストリーミング**] ページで、各プログラムを実行して、ターゲットコンピューターで最適化し、より効率的に実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-162">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="f0c78-163">すべてのアプリケーションが実行されるまでに数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="f0c78-163">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="f0c78-164">すべてのアプリケーションが実行されたら、各アプリケーションを閉じて、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-164">After all applications have run, close each of the applications, and then click **Next**.</span></span>

   > [!NOTE]  
   > <span data-ttu-id="f0c78-165">この手順でアプリケーションを開かない場合、既定のストリーミングメソッドはオンデマンドストリーミング配信です。</span><span class="sxs-lookup"><span data-stu-id="f0c78-165">If you do not open any applications during this step, the default streaming method is on-demand streaming delivery.</span></span> <span data-ttu-id="f0c78-166">つまり、アプリは開くことができるまでビット単位でダウンロードされ、バックグラウンド読み込みの構成方法によって、アプリケーションの残りの部分が読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-166">This means applications will be downloaded bit by bit until it can be opened, and then depending on how the background loading is configured, will load the rest of the application.</span></span>



13. <span data-ttu-id="f0c78-167">[**ターゲット OS** ] ページで、このパッケージを実行できるオペレーティングシステムを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-167">On the **Target OS** page, specify the operating systems that can run this package.</span></span> <span data-ttu-id="f0c78-168">環境内でサポートされているすべてのオペレーティングシステムでこのパッケージを実行できるようにするには、[**このパッケージをすべてのオペレーティングシステムで実行できるように**する] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-168">To allow all supported operating systems in your environment to run this package, select **Allow this package to run on any operating system**.</span></span> <span data-ttu-id="f0c78-169">特定のオペレーティングシステムでのみ実行されるようにこのパッケージを構成するには、[**このパッケージを次のオペレーティングシステムでのみ実行できるよう**にする] を選び、このパッケージを実行できるオペレーティングシステムを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-169">To configure this package to run only on specific operating systems, select **Allow this package to run only on the following operating systems** and select the operating systems that can run this package.</span></span> <span data-ttu-id="f0c78-170">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-170">Click **Next**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="f0c78-171">ここで指定したオペレーティングシステムが、優先順位を設定するアプリケーションによってサポートされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-171">Make sure that the operating systems you specify here are supported by the application you are sequencing.</span></span>



14. <span data-ttu-id="f0c78-172">[**パッケージの作成**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-172">The **Create Package** page is displayed.</span></span> <span data-ttu-id="f0c78-173">パッケージを保存せずに変更するには、パッケージ**エディターを使用してパッケージを保存せずに変更するに**は、[続行] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-173">To modify the package without saving it, select **Continue to modify package without saving using the package editor**.</span></span> <span data-ttu-id="f0c78-174">このオプションでは、sequencer コンソールでパッケージが開き、保存する前にパッケージを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-174">This option opens the package in the sequencer console so that you can modify the package before it is saved.</span></span> <span data-ttu-id="f0c78-175">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-175">Click **Next**.</span></span>

   <span data-ttu-id="f0c78-176">パッケージをすぐに保存するには、[**今すぐパッケージを保存**する (既定)] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-176">To save the package immediately, select **Save the package now** (default).</span></span> <span data-ttu-id="f0c78-177">パッケージに関連付けるオプションの**コメント**を追加します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-177">Add optional **Comments** to be associated with the package.</span></span> <span data-ttu-id="f0c78-178">コメントは、プログラムのバージョンやパッケージに関するその他の情報を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-178">Comments are useful for identifying the program version and other information about the package.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="f0c78-179">**コメント**と**説明**では、印刷できない文字がシステムでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f0c78-179">The system does not support non-printable characters in **Comments** and **Descriptions**.</span></span>



~~~
The default **Save Location** is also displayed on this page. To change the default location, click **Browse** and specify the new location. Click **Create**.
~~~

15. <span data-ttu-id="f0c78-180">**完了**ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-180">The **Completion** page is displayed.</span></span> <span data-ttu-id="f0c78-181">必要に応じて**仮想アプリケーションパッケージレポート**ウィンドウの情報を確認し、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-181">Review the information in the **Virtual Application Package Report** pane as needed, then click **Close**.</span></span> <span data-ttu-id="f0c78-182">この情報は、パッケージを作成したディレクトリにある**Report.xml**ファイルでも確認できます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-182">This information is also available in the **Report.xml** file that is located in the directory where the package was created.</span></span>

   <span data-ttu-id="f0c78-183">このパッケージは、sequencer で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f0c78-183">The package is now available in the sequencer.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="f0c78-184">仮想アプリケーションパッケージを正常に作成した後、sequencer を実行しているコンピューターで仮想アプリケーションパッケージを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="f0c78-184">After you have successfully created a virtual application package, you cannot run the virtual application package on the computer that is running the sequencer.</span></span>



**<span data-ttu-id="f0c78-185">アドオンまたはプラグインアプリケーションの順序を管理するには</span><span class="sxs-lookup"><span data-stu-id="f0c78-185">To sequence an add-on or plug-in application</span></span>**

1. > [!NOTE]  
   > <span data-ttu-id="f0c78-186">次の手順を実行する前に、sequencer を実行しているコンピューターに親アプリケーションをローカルにインストールします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-186">Before performing the following procedure, install the parent application locally on the computer that is running the sequencer.</span></span> <span data-ttu-id="f0c78-187">または、親アプリケーションが仮想化されている場合は、アドオンまたはプラグインのワークフローの手順に従って、コンピューター上の親アプリケーションを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-187">Or if you have the parent application virtualized, you can follow the steps in the add-on or plug-in workflow to unpack the parent application on the computer.</span></span>
   >
   > <span data-ttu-id="f0c78-188">たとえば、Microsoft Excel のプラグインの順序を付ける場合は、sequencer を実行しているコンピューターに Microsoft Excel をローカルにインストールします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-188">For example, if you are sequencing a plug-in for Microsoft Excel, install Microsoft Excel locally on the computer that is running the sequencer.</span></span> <span data-ttu-id="f0c78-189">また、アプリケーションがターゲットコンピューターにインストールされているディレクトリに、親アプリケーションもインストールします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-189">Also install the parent application in the same directory where the application is installed on target computers.</span></span> <span data-ttu-id="f0c78-190">プラグインまたはアドオンを既存の仮想アプリケーションパッケージと共に使用する場合は、親仮想アプリケーションパッケージを作成したときに使用したのと同じ仮想アプリケーションドライブにアプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-190">If the plug-in or add-on is going to be used with an existing virtual application package, install the application on the same virtual application drive that was used when you created the parent virtual application package.</span></span>



~~~
On the computer that runs the sequencer, click **All Programs**, and then Click **Microsoft Application Virtualization**, and then click **Microsoft Application Virtualization Sequencer**.
~~~

2. <span data-ttu-id="f0c78-191">*<strong><em>Sequencer で、[* </em> 新しい仮想アプリケーションパッケージの作成] をクリックし </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-191">\*<strong><em>In the sequencer, click \*</em>Create a New Virtual Application Package</strong>.</span></span> <span data-ttu-id="f0c78-192">[**パッケージの作成 (既定)**] を選び、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-192">Select **Create Package (default)**, and then click **Next**.</span></span>

3. <span data-ttu-id="f0c78-193">[**コンピューターの準備**] ページで、パッケージの作成に失敗する可能性がある問題、またはパッケージに不要なデータが含まれている可能性がある問題を確認します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-193">On the **Prepare Computer** page, review the issues that might cause the package creation to fail or could cause the package to contain unnecessary data.</span></span> <span data-ttu-id="f0c78-194">続行する前に、発生する可能性があるすべての問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0c78-194">You should resolve all potential issues before you continue.</span></span> <span data-ttu-id="f0c78-195">修正が完了したら、[**更新**] をクリックして更新された情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-195">After making any corrections, click **Refresh** to display the updated information.</span></span> <span data-ttu-id="f0c78-196">すべての潜在的な問題を解決したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-196">After you have resolved all potential issues, click **Next**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="f0c78-197">ウイルススキャンソフトウェアを無効にする必要がある場合は、まず sequencer を実行するコンピューターをスキャンして、不要なファイルや悪意のあるファイルがパッケージに追加されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0c78-197">If you are required to disable virus scanning software, you should first scan the computer that runs the sequencer in order to ensure that no unwanted or malicious files could be added to the package.</span></span>



4. <span data-ttu-id="f0c78-198">[**アプリケーションの種類**] ページで、[**アドオンまたはプラグイン**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-198">On the **Type of Application** page, select **Add-on or Plug-in**, and then click **Next**.</span></span>

5. <span data-ttu-id="f0c78-199">[**インストーラーの選択**] ページで [**参照**] をクリックし、アドオンまたはプラグインのインストールファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-199">On the **Select Installer** page, click **Browse** and specify the installation file for the add-on or plug-in.</span></span> <span data-ttu-id="f0c78-200">アドオンまたはプラグインに関連するインストーラファイルがなく、すべてのインストール手順を手動で実行する場合は、[**このオプションを選択してカスタムインストールを実行**する] チェックボックスをオンにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-200">If the add-on or plug-in does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

6. <span data-ttu-id="f0c78-201">[**インストールプライマリ**] ページで、sequencer を実行しているコンピューターにプライマリアプリケーションがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-201">On the **Install Primary** page, ensure that the primary application is installed on the computer that runs the sequencer.</span></span> <span data-ttu-id="f0c78-202">または、sequencer を実行するコンピューターにローカルに保存されている既存のパッケージを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-202">Alternatively, you can expand an existing package that has been saved locally on the computer that runs the sequencer.</span></span> <span data-ttu-id="f0c78-203">これを行うには、[**パッケージの展開**] をクリックして、パッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-203">To do this, click **Expand Package**, and then select the package.</span></span> <span data-ttu-id="f0c78-204">親プログラムを展開またはインストールしたら、[**プライマリ親プログラムをインストールしまし**た] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-204">After you have expanded or installed the parent program, select **I have installed the primary parent program**.</span></span>

   <span data-ttu-id="f0c78-205">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-205">Click **Next**.</span></span>

7. <span data-ttu-id="f0c78-206">[**パッケージ名**] ページで、パッケージに関連付ける名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-206">On the **Package Name** page, type a name that will be associated with the package.</span></span> <span data-ttu-id="f0c78-207">パッケージに追加されるアプリケーションの目的とバージョンを識別するのに役立つ名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-207">Use a name that helps identify the purpose and version of the application that will be added to the package.</span></span> <span data-ttu-id="f0c78-208">パッケージ名は、App-v 5.0 管理コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-208">The package name will be displayed in the App-V 5.0 Management Console.</span></span>

   <span data-ttu-id="f0c78-209">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-209">Click **Next**.</span></span>

8. <span data-ttu-id="f0c78-210">**インストール**ページで、sequencer とアプリケーションインストーラーの準備ができたら、プラグインまたはアドインアプリケーションをインストールして、sequencer がインストールプロセスを監視できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-210">On the **Installation** page, when the sequencer and application installer are ready you can proceed to install the plug-in or add-in application so the sequencer can monitor the installation process.</span></span> <span data-ttu-id="f0c78-211">アプリケーションのインストールプロセスを使用して、インストールを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-211">Use the application's installation process to perform the installation.</span></span> <span data-ttu-id="f0c78-212">インストールの一部として追加のインストールファイルを実行する必要がある場合は、[**実行**] をクリックして、追加のインストールファイルを見つけて実行します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-212">If additional installation files must be run as part of the installation, click **Run** and locate and run the additional installation files.</span></span> <span data-ttu-id="f0c78-213">インストールが完了したら、[インストールを**完了**しました] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-213">When you are finished with the installation, select **I am finished installing**, and then click **Next**.</span></span>

9. <span data-ttu-id="f0c78-214">[**インストールレポート**] ページで、順序付けした仮想アプリケーションパッケージに関する情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-214">On the **Installation Report** page, you can review information about the virtual application package that you just sequenced.</span></span> <span data-ttu-id="f0c78-215">[**追加情報**] に表示される情報について詳しくは、イベントをダブルクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="f0c78-215">For a more detailed explanation about the information displayed in **Additional Information**, double-click the event.</span></span> <span data-ttu-id="f0c78-216">情報を確認したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-216">After you have reviewed the information, click **Next**.</span></span>

10. <span data-ttu-id="f0c78-217">[**ユーザー設定**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-217">The **Customize** page is displayed.</span></span> <span data-ttu-id="f0c78-218">仮想アプリケーションのインストールと構成が完了したら、[**今すぐ停止**] を選んで、この手順の手順12に進んでください。</span><span class="sxs-lookup"><span data-stu-id="f0c78-218">If you are finished installing and configuring the virtual application, select **Stop now** and skip to step 12 of this procedure.</span></span> <span data-ttu-id="f0c78-219">次のいずれかのカスタマイズを実行するには、[**カスタマイズ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-219">To perform either of the following customizations, select **Customize**.</span></span>

    -   <span data-ttu-id="f0c78-220">低速または信頼性の低いネットワークでパッケージが実行される方法を最適化します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-220">Optimize how the package will run across a slow or unreliable network.</span></span>

    -   <span data-ttu-id="f0c78-221">このパッケージを実行できるオペレーティングシステムを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-221">Specify the operating systems that can run this package.</span></span>

    <span data-ttu-id="f0c78-222">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-222">Click **Next**.</span></span>

11. <span data-ttu-id="f0c78-223">[**ストリーミング**] ページで、各プログラムを実行して、ターゲットコンピューターで最適化し、より効率的に実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-223">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="f0c78-224">ストリーミングによって、仮想アプリケーションパッケージが、待機時間の長いネットワーク上のターゲットコンピューターで実行されると、エクスペリエンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-224">Streaming improves the experience when the virtual application package is run on target computers on high-latency networks.</span></span> <span data-ttu-id="f0c78-225">すべてのアプリケーションが実行されるまでに数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="f0c78-225">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="f0c78-226">すべてのアプリケーションが実行されたら、各アプリケーションを終了します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-226">After all applications have run, close each of the applications.</span></span> <span data-ttu-id="f0c78-227">また、アプリを開く前に完全にダウンロードされるようにするには、[**アプリケーションの強制ダウンロード**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-227">You can also configure the package to be required to be fully downloaded before opening by selecting the **Force applications to be downloaded** check-box.</span></span> <span data-ttu-id="f0c78-228">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-228">Click **Next**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="f0c78-229">必要に応じて、この手順を実行すると、アプリケーションの読み込みが停止することがあります。</span><span class="sxs-lookup"><span data-stu-id="f0c78-229">If necessary, you can stop an application from loading during this step.</span></span> <span data-ttu-id="f0c78-230">[**アプリケーションの起動**] ダイアログボックスで、[**停止**] をクリックし、いずれかのチェックボックスをオンにします。すべての**アプリケーションを終了**するか、**このアプリケーションのみを停止**します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-230">In the **Application Launch** dialog box, click **Stop** and select one of the check boxes: **Stop all applications** or **Stop this application only**.</span></span>



12. <span data-ttu-id="f0c78-231">[**ターゲット OS** ] ページで、このパッケージを実行できるオペレーティングシステムを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-231">On the **Target OS** page, specify the operating systems that can run this package.</span></span> <span data-ttu-id="f0c78-232">環境内でサポートされているすべてのオペレーティングシステムでこのパッケージを実行できるようにするには、[**このパッケージをすべてのオペレーティングシステムで実行できるよう**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-232">To allow all supported operating systems in your environment to run this package, select the **Allow this package to run on any operating system** check box.</span></span> <span data-ttu-id="f0c78-233">特定のオペレーティングシステムでのみ実行されるようにこのパッケージを構成するには、[**次のオペレーティングシステムでのみこのパッケージを実行**する] チェックボックスをオンにして、このパッケージを実行できるオペレーティングシステムを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-233">To configure this package to run only on specific operating systems, select the **Allow this package to run only on the following operating systems** check box, and then select the operating systems that can run this package.</span></span> <span data-ttu-id="f0c78-234">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-234">Click **Next**.</span></span>

13. <span data-ttu-id="f0c78-235">[**パッケージの作成**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-235">The **Create Package** page is displayed.</span></span> <span data-ttu-id="f0c78-236">パッケージを保存せずに変更するには、[**パッケージエディターを使ってパッケージを保存せずに変更するには、続行する**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-236">To modify the package without saving it, select **Continue to modify package without saving using the package editor** check box.</span></span> <span data-ttu-id="f0c78-237">このオプションでは、sequencer コンソールでパッケージが開き、保存する前にパッケージを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-237">This option opens the package in the sequencer console so that you can modify the package before it is saved.</span></span> <span data-ttu-id="f0c78-238">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-238">Click **Next**.</span></span>

    <span data-ttu-id="f0c78-239">パッケージを今すぐ保存するには、[**パッケージの保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-239">To save the package immediately, select **Save the package now**.</span></span> <span data-ttu-id="f0c78-240">必要に応じて、パッケージに関連付けられている**説明**を追加します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-240">Optionally, add a **Description** that will be associated with the package.</span></span> <span data-ttu-id="f0c78-241">説明は、パッケージについてのバージョンとその他の情報を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-241">Descriptions are useful for identifying the version and other information about the package.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f0c78-242">コメントと説明では、印刷できない文字がシステムでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f0c78-242">The system does not support non-printable characters in Comments and Descriptions.</span></span>



~~~
The default **Save Location** is also displayed on this page. To change the default location, click **Browse** and specify the new location. Click **Create**.
~~~

**<span data-ttu-id="f0c78-243">ミドルウェアアプリケーションのシーケンスを行うには</span><span class="sxs-lookup"><span data-stu-id="f0c78-243">To sequence a middleware application</span></span>**

1. <span data-ttu-id="f0c78-244">Sequencer を実行しているコンピューターで、[**すべてのプログラム**]、[ **microsoft application virtualization**]、[ **microsoft application virtualization sequencer**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-244">On the computer that runs the sequencer, click **All Programs**, and then Click **Microsoft Application Virtualization**, and then click **Microsoft Application Virtualization Sequencer**.</span></span>

2. <span data-ttu-id="f0c78-245">*<strong><em>Sequencer で、[* </em> 新しい仮想アプリケーションパッケージの作成] をクリックし </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-245">\*<strong><em>In the sequencer, click \*</em>Create a New Virtual Application Package</strong>.</span></span> <span data-ttu-id="f0c78-246">[**パッケージの作成 (既定)**] を選び、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-246">Select **Create Package (default)**, and then click **Next**.</span></span>

3. <span data-ttu-id="f0c78-247">[**コンピューターの準備**] ページで、パッケージの作成に失敗する可能性がある問題、またはパッケージに不要なデータが含まれている可能性がある問題を確認します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-247">On the **Prepare Computer** page, review the issues that could cause the package creation to fail or could cause the package to contain unnecessary data.</span></span> <span data-ttu-id="f0c78-248">続行する前に、発生する可能性があるすべての問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0c78-248">You should resolve all potential issues before you continue.</span></span> <span data-ttu-id="f0c78-249">修正が完了したら、[**更新**] をクリックして更新された情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-249">After making any corrections, click **Refresh** to display the updated information.</span></span> <span data-ttu-id="f0c78-250">すべての潜在的な問題を解決したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-250">After you have resolved all potential issues, click **Next**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="f0c78-251">ウイルススキャンソフトウェアを無効にする必要がある場合は、まず、不要なファイルまたは悪意のあるファイルがパッケージに追加されないように、アプリ-V 5.0 Sequencer を実行しているコンピューターをスキャンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0c78-251">If you are required to disable virus scanning software, you should first scan the computer that runs the App-V 5.0 Sequencer in order to ensure that no unwanted or malicious files can be added to the package.</span></span>



4. <span data-ttu-id="f0c78-252">[**アプリケーションの種類**] ページで、[**ミドルウェア**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-252">On the **Type of Application** page, select **Middleware**, and then click **Next**.</span></span>

5. <span data-ttu-id="f0c78-253">[**インストーラーの選択**] ページで [**参照**] をクリックして、アプリケーションのインストールファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-253">On the **Select Installer** page, click **Browse** and specify the installation file for the application.</span></span> <span data-ttu-id="f0c78-254">アプリケーションに関連付けられたインストーラーファイルがなく、インストール手順を手動で実行する場合は、[**このオプションを選択してカスタムインストールを実行**する] チェックボックスをオンにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-254">If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

6. <span data-ttu-id="f0c78-255">[**パッケージ名**] ページで、パッケージに関連付ける名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-255">On the **Package Name** page, type a name that will be associated with the package.</span></span> <span data-ttu-id="f0c78-256">パッケージに追加されるアプリケーションの目的とバージョンを識別するのに役立つ名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-256">Use a name that helps identify the purpose and version of the application that will be added to the package.</span></span> <span data-ttu-id="f0c78-257">パッケージ名は、App-v 5.0 管理コンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-257">The package name is displayed in the App-V 5.0 Management Console.</span></span>

   <span data-ttu-id="f0c78-258">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-258">Click **Next**.</span></span>

7. <span data-ttu-id="f0c78-259">**インストール**ページで、sequencer とミドルウェアアプリケーションのインストーラーの準備ができたら、アプリをインストールして、sequencer がインストールプロセスを監視できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-259">On the **Installation** page, when the sequencer and middleware application installer are ready you can proceed to install the application so that the sequencer can monitor the installation process.</span></span> <span data-ttu-id="f0c78-260">アプリケーションのインストールプロセスを使用して、インストールを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-260">Use the application's installation process to perform the installation.</span></span> <span data-ttu-id="f0c78-261">インストールの一部として追加のインストールファイルを実行する必要がある場合は、[**実行**] をクリックして、追加のインストールファイルを見つけて実行します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-261">If additional installation files must be run as part of the installation, click **Run**, to locate and run the additional installation files.</span></span> <span data-ttu-id="f0c78-262">インストールが完了したら、[**インストールを完了**しました] チェックボックスをオンにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-262">When you are finished with the installation, select the **I am finished installing** check box, and then click **Next**.</span></span>

8. <span data-ttu-id="f0c78-263">**インストール**ページで、sequencer が仮想アプリケーションパッケージを構成するまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-263">On the **Installation** page, wait while the sequencer configures the virtual application package.</span></span>

9. <span data-ttu-id="f0c78-264">[**インストールレポート**] ページで、順序付けされた仮想アプリケーションパッケージに関する情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-264">On the **Installation Report** page, you can review information about the virtual application package that you have just sequenced.</span></span> <span data-ttu-id="f0c78-265">さら**に詳しい**情報を取得するには、イベントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-265">In **Additional Information**, double-click an event to obtain more detailed information.</span></span> <span data-ttu-id="f0c78-266">続行するには、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-266">To proceed, click **Next**.</span></span>

10. <span data-ttu-id="f0c78-267">[**ターゲット OS** ] ページで、このパッケージを実行できるオペレーティングシステムを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-267">On the **Target OS** page, specify the operating systems that can run this package.</span></span> <span data-ttu-id="f0c78-268">環境でサポートされているすべてのオペレーティングシステムでこのパッケージを実行できるようにするには、[**このパッケージをすべてのオペレーティングシステムで実行できるよう**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-268">To enable all supported operating systems in your environment to run this package, select the **Allow this package to run on any operating system** check box.</span></span> <span data-ttu-id="f0c78-269">特定のオペレーティングシステムのみで実行するようにこのパッケージを構成するには、[**次のオペレーティングシステムでのみこのパッケージを実行**する] チェックボックスをオンにして、このパッケージを実行できるオペレーティングシステムを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-269">To configure this package to run only on specific operating systems, select the **Allow this package to run only on the following operating systems** check box and select the operating systems that can run this package.</span></span> <span data-ttu-id="f0c78-270">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-270">Click **Next**.</span></span>

11. <span data-ttu-id="f0c78-271">[**パッケージの作成**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-271">On the **Create Package** page is displayed.</span></span> <span data-ttu-id="f0c78-272">パッケージを保存せずに変更するには、パッケージ**エディターを使用してパッケージを保存せずに変更するに**は、[続行] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-272">To modify the package without saving it, select **Continue to modify package without saving using the package editor**.</span></span> <span data-ttu-id="f0c78-273">このオプションでは、sequencer コンソールでパッケージが開き、保存する前にパッケージを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-273">This option opens the package in the sequencer console so that you can modify the package before it is saved.</span></span> <span data-ttu-id="f0c78-274">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-274">Click **Next**.</span></span>

    <span data-ttu-id="f0c78-275">パッケージを今すぐ保存するには、[**パッケージの保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-275">To save the package immediately, select **Save the package now**.</span></span> <span data-ttu-id="f0c78-276">必要に応じて、パッケージに関連付ける**説明**を追加します。</span><span class="sxs-lookup"><span data-stu-id="f0c78-276">Optionally, add a **Description** to be associated with the package.</span></span> <span data-ttu-id="f0c78-277">説明は、プログラムのバージョンやパッケージに関するその他の情報を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-277">Descriptions are useful for identifying the program version and other information about the package.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f0c78-278">コメントと説明では、印刷できない文字がシステムでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f0c78-278">The system does not support non-printable characters in Comments and Descriptions.</span></span>



~~~
The default **Save Location** is also displayed on this page. To change the default location, click **Browse** and specify the new location. Click **Create**.
~~~

12. <span data-ttu-id="f0c78-279">**完了**ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-279">The **Completion** page is displayed.</span></span> <span data-ttu-id="f0c78-280">必要に応じて**仮想アプリケーションパッケージレポート**ウィンドウの情報を確認し、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-280">Review the information in the **Virtual Application Package Report** pane as needed, then click **Close**.</span></span> <span data-ttu-id="f0c78-281">この情報は、この手順の手順11で指定したディレクトリにある**Report.xml**ファイルでも確認できます。</span><span class="sxs-lookup"><span data-stu-id="f0c78-281">This information is also available in the **Report.xml** file that is located in the directory specified in step 11 of this procedure.</span></span>

   <span data-ttu-id="f0c78-282">このパッケージは、sequencer で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f0c78-282">The package is now available in the sequencer.</span></span> <span data-ttu-id="f0c78-283">パッケージのプロパティを編集するには、[ **\ [パッケージ名 \] の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c78-283">To edit the package properties, click **Edit \[Package Name\]**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="f0c78-284">仮想アプリケーションパッケージを正常に作成した後、sequencer を実行しているコンピューターで仮想アプリケーションパッケージを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="f0c78-284">After you have successfully created a virtual application package, you cannot run the virtual application package on the computer that is running the sequencer.</span></span>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="f0c78-285">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f0c78-285">Related topics</span></span>


[<span data-ttu-id="f0c78-286">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="f0c78-286">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)









