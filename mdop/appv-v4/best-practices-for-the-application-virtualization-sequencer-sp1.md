---
title: Application Virtualization Sequencer のベスト プラクティス
description: Application Virtualization Sequencer のベスト プラクティス
author: dansimp
ms.assetid: 95e5e216-864f-41a1-90d4-b8d7e1eb42a0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d859514fb34185a339c7f2c2734f331e5a99d050
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821997"
---
# <span data-ttu-id="ff6e5-103">Application Virtualization Sequencer のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="ff6e5-103">Best Practices for the Application Virtualization Sequencer</span></span>


<span data-ttu-id="ff6e5-104">このトピックでは、Microsoft Application Virtualization (App-v) Sequencer を実行するためのベストプラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-104">This topic provides best practices for running the Microsoft Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="ff6e5-105">環境で Sequencer を計画して使用する際には、次の推奨事項を確認し、考慮してください。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-105">Review and consider the following recommendations when planning and using the Sequencer in your environment.</span></span>

## <span data-ttu-id="ff6e5-106">優先順位のコンピューター構成のベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="ff6e5-106">Sequencing Computer Configuration Best Practices</span></span>


<span data-ttu-id="ff6e5-107">App-v Sequencer を実行しているコンピューターを構成する場合は、次のベストプラクティスを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-107">The following best practices should be considered when configuring the computer running the App-V Sequencer:</span></span>

-   **<span data-ttu-id="ff6e5-108">類似した構成を持ち、ターゲットコンピューターよりも古いバージョンのオペレーティングシステムを実行しているコンピューターでのシーケンス。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-108">Sequence on a computer that has a similar configuration and that is running an earlier version of the operating system than the target computers.</span></span>**

    <span data-ttu-id="ff6e5-109">Sequencer を実行しているコンピューターが、ターゲットコンピューターよりも前のバージョンのオペレーティングシステムを実行していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-109">Ensure that the computer that is running the Sequencer is running an earlier version of the operating system than the target computers.</span></span> <span data-ttu-id="ff6e5-110">これには、service pack と更新プログラムのバージョンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-110">This includes the service pack and update versions.</span></span> <span data-ttu-id="ff6e5-111">たとえば、ターゲットコンピューターで WindowsVista と WindowsXP を実行している場合は、WindowsXP を実行しているコンピューターでアプリケーションをシーケンスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-111">For example, if the target computers are running WindowsVista and WindowsXP, you should sequence applications on a computer that is running WindowsXP.</span></span> <span data-ttu-id="ff6e5-112">1つのオペレーティングシステムでシーケンスを実行して、別のオペレーティングシステムで仮想化されたアプリケーションを実行できるかどうかは保証されず、特定のアプリケーションとオペレーティングシステムによって異なります。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-112">The ability to sequence on one operating system and run the virtualized application on a different operating system is not guaranteed, and depends on the particular application and operating system.</span></span> <span data-ttu-id="ff6e5-113">問題が発生した場合は、App-v クライアントが実行されているオペレーティングシステム環境と同じオペレーティングシステム環境でのシーケンスが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-113">If you encounter issues, you may be required to sequence on the same operating system environment as the one on which the App-V client is running.</span></span>

-   **<span data-ttu-id="ff6e5-114">複数のパーティションを使用して、Sequencer を実行しているコンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-114">Configure the computer running the Sequencer with multiple partitions.</span></span>**

    <span data-ttu-id="ff6e5-115">少なくとも2つのプライマリパーティションを使用して、Sequencer を実行しているコンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-115">You should configure the computer running the Sequencer with at least two primary partitions.</span></span> <span data-ttu-id="ff6e5-116">最初のパーティション (**C:**) にはオペレーティングシステムを含める必要があり、NTFS ファイルシステムを使って書式設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-116">The first partition (**C:**) should contain the operating system, and it should be formatted using the NTFS file system.</span></span> <span data-ttu-id="ff6e5-117">2番目のパーティション (**Q:**) は、仮想アプリケーションのインストール先のパスとして使用されます。また、NTFS ファイルシステムを使用して書式設定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-117">The second partition (**Q:**) is used as the destination path for the virtual application installation and should also be formatted using the NTFS file system.</span></span>

-   **<span data-ttu-id="ff6e5-118">十分な空きディスク領域がある temp ディレクトリを構成します。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-118">Configure the temp directory with enough free disk space.</span></span>**

    <span data-ttu-id="ff6e5-119">Sequencer では、 **% TMP** % または **% TEMP%** ディレクトリと**スクラッチ**ディレクトリを使ってシーケンス中に一時ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-119">The Sequencer uses the **%TMP%** or **%TEMP%** directory and the **Scratch** directory to store temporary files during sequencing.</span></span> <span data-ttu-id="ff6e5-120">このディレクトリは、Sequencer を実行しているコンピューターで、アプリケーションの推定インストール要件に相当する空きディスク領域を備えたコンピューターで構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-120">You should configure these directories on the computer running the Sequencer with free disk space equivalent to the estimated application installation requirements.</span></span> <span data-ttu-id="ff6e5-121">**スクラッチ**ディレクトリの場所を確認するには、Sequencer コンソールを開き、[**ツール**]、[**オプション**] の順に選択して、[**パス**] タブを選択します。各ハードドライブのパーティションに temp ディレクトリと**スクラッチ**ディレクトリを構成すると、シーケンス中のパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-121">You can verify the location of the **Scratch** directory by opening the Sequencer console and selecting **Tools**, **Options**, and then selecting the **Paths** tab. Configuring the temp directories and the **Scratch** directory on different hard drive partitions can improve performance during sequencing.</span></span>

-   **<span data-ttu-id="ff6e5-122">Microsoft VirtualPC を使用してアプリケーションをシーケンスする。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-122">Sequence applications by using Microsoft VirtualPC.</span></span>**

    <span data-ttu-id="ff6e5-123">ほとんどのアプリケーションを複数回連続して処理します。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-123">You will sequence most applications more than once.</span></span> <span data-ttu-id="ff6e5-124">これを容易にするために、仮想環境で実行されているコンピューターの順序を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-124">To help facilitate this, you should consider sequencing on a computer running in a virtual environment.</span></span> <span data-ttu-id="ff6e5-125">これにより、アプリの順序を設定し、Sequencer を実行しているコンピューター上の最小限の再構成で、クリーンな状態に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-125">This will allow you to sequence an application and revert to a clean state, with minimal reconfiguration, on the computer that is running the Sequencer.</span></span>

    <span data-ttu-id="ff6e5-126">使用している環境で Microsoft Hyper-v を実行している場合は、Hyper-v 仮想コンピューターが実行されているときに、App-v の sequencer が実行されます。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-126">If you are running Microsoft Hyper-V in your environment the App-V sequencer will run when the Hyper-V virtual computer it is running on is:</span></span>

    -   <span data-ttu-id="ff6e5-127">一時停止して再開しました。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-127">paused and resumed.</span></span>

    -   <span data-ttu-id="ff6e5-128">状態が保存され、復元されました。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-128">has its state saved and restored.</span></span>

    -   <span data-ttu-id="ff6e5-129">スナップショットとして保存され、復元されます。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-129">saved as a snapshot and is restored.</span></span>

    -   <span data-ttu-id="ff6e5-130">ライブ移行の一部として別のハードウェアに移行されます。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-130">migrated to different hardware as part of a live migration.</span></span>

-   **<span data-ttu-id="ff6e5-131">新しいアプリケーションをシーケンスする前に、実行中のプログラムを終了してください。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-131">Before you sequence a new application, shut down other running programs.</span></span>**

    <span data-ttu-id="ff6e5-132">シーケンスコンピューターで通常実行されるプロセスとスケジュールされたタスクによって、シーケンス処理の速度が遅くなり、不適切なデータが順番に収集される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-132">Processes and scheduled tasks that normally run on the sequencing computer can slow down the sequencing process and cause irrelevant data to be gathered during sequencing.</span></span> <span data-ttu-id="ff6e5-133">シーケンスを始める前に、不要なすべてのアプリケーションとプログラムを終了しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-133">All unnecessary applications and programs should be shut down before you begin sequencing.</span></span>

-   **<span data-ttu-id="ff6e5-134">ターミナルサービスを実行しているコンピューター上のシーケンス</span><span class="sxs-lookup"><span data-stu-id="ff6e5-134">Sequence on a computer that is running Terminal Services</span></span>**

    <span data-ttu-id="ff6e5-135">ターミナルサービスを実行しているコンピューターでは、sequencer をインストールする前にインストールモードを構成しないでください。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-135">You should not configure the install mode on a computer that is running Terminal Services before you install the sequencer.</span></span>

## <span data-ttu-id="ff6e5-136">優先順位のベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="ff6e5-136">Sequencing Best Practices</span></span>


<span data-ttu-id="ff6e5-137">新しいアプリケーションを順序指定する際には、次のベストプラクティスを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-137">The following best practices should be considered when sequencing a new application:</span></span>

-   

    <span data-ttu-id="ff6e5-138">**注** App-v 4.6 SP1 を実行している場合は、8.3 の名前付け規則に従ったディレクトリを順序付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-138">**Note** If you are running App-V 4.6 SP1 you do not need to sequence to a directory that follows the 8.3 naming convention.</span></span>

     

-   **<span data-ttu-id="ff6e5-139">8.3 の名前付け規則に従って、一意のディレクトリに順序を変更します。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-139">Sequence to a unique directory that follows the 8.3 naming convention.</span></span>**

    <span data-ttu-id="ff6e5-140">すべてのアプリケーションを、8.3 の名前付け規則に従ったディレクトリに順序付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-140">You should sequence all applications to a directory that follows the 8.3 naming convention.</span></span> <span data-ttu-id="ff6e5-141">指定したディレクトリ名は、8文字以下で、その後に3文字のファイル名拡張子 (たとえば、Q:\\MYAPP.) を含むことはできません。 **ABC**。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-141">The specified directory name cannot contain more than eight characters, followed by a three-character file name extension—for example, **Q:\\MYAPP.ABC**.</span></span>

-   **<span data-ttu-id="ff6e5-142">サブディレクトリではなく、ドライブのルート上の移動先フォルダーに順序を指定します。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-142">Sequence to a destination folder on the root of the drive, not to a subdirectory.</span></span>**

    <span data-ttu-id="ff6e5-143">アプリケーションスイートに複数の部分がある場合は、各アプリケーションをメインディレクトリのサブディレクトリにインストールします。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-143">If the application suite has multiple parts, install each application to a subdirectory of the main directory.</span></span> <span data-ttu-id="ff6e5-144">たとえば、パッケージにクライアントと共にアプリケーションが含まれている場合、 **Q:\\AppSuite**をメインディレクトリとして使用し、メインアプリケーションを**Q:\\AppSuite\\Main**にシーケンスし、クライアントを**Q:\\AppSuite\\Client**にシーケンスします。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-144">For example, if a package contains an application along with a client, use **Q:\\AppSuite** as the main directory and sequence the main application to **Q:\\AppSuite\\Main**, and sequence the client to **Q:\\AppSuite\\Client**.</span></span>

-   **<span data-ttu-id="ff6e5-145">インストールフェーズ中にアプリケーションを構成してテストします。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-145">Configure and test the application during the installation phase.</span></span>**

    <span data-ttu-id="ff6e5-146">アプリケーションのインストールを完了するには、アプリケーションのインストールプロセスの一部ではない手動の手順をいくつか実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-146">Completing the installation of an application often requires performing several manual steps that are not part of the application installation process.</span></span> <span data-ttu-id="ff6e5-147">この手順では、データベースへの接続を構成するか、更新されたファイルをコピーする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-147">These steps can involve configuring a connection to a database or copying updated files.</span></span> <span data-ttu-id="ff6e5-148">インストールフェーズでこれらの構成を実行して、アプリケーションを実行し、動作していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-148">You should perform these configurations during the installation phase and then run the application to make sure it works.</span></span>

-   **<span data-ttu-id="ff6e5-149">プログラムが安定するまで、必要に応じて複数回アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-149">Run the application, multiple times if necessary, until the program is stable.</span></span>**

    <span data-ttu-id="ff6e5-150">関連付けられたすべての登録およびダイアログボックスの構成が完了していることを確認するため、インストール中にアプリケーションを複数回実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-150">You should run the application multiple times during the installation to ensure all associated registration and dialog box configurations have been completed.</span></span> <span data-ttu-id="ff6e5-151">インストール中にアプリケーションを複数回開くと、関連アプリケーションの機能のみが**プライマリ機能ブロック**に読み込まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-151">Opening the application multiple times during installation will ensure that only the relevant application features are loaded into the **primary feature block**.</span></span>

-   **<span data-ttu-id="ff6e5-152">アプリケーションに関連付けられているすべての自動更新機能を無効にします。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-152">Disable all automatic update features associated with the application.</span></span>**

    <span data-ttu-id="ff6e5-153">一部のアプリケーションでは、インストール中に最新の更新プログラムを自動的にチェックできます。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-153">Some applications have the ability to check for the latest updates automatically during installation.</span></span> <span data-ttu-id="ff6e5-154">仮想アプリケーションパッケージのバージョン管理をサポートするには、シーケンス中にこの機能を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-154">To assist with versioning of virtual application packages, you should disable this feature during sequencing.</span></span> <span data-ttu-id="ff6e5-155">必要な更新プログラムがある場合は、関連付けられた更新プログラムがインストールされた新しい仮想アプリケーションパッケージの順序を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff6e5-155">If there are required updates, you should sequence a new virtual application package with the associated updates installed.</span></span>

## <span data-ttu-id="ff6e5-156">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ff6e5-156">Related topics</span></span>


[<span data-ttu-id="ff6e5-157">Application Virtualization システムの展開計画</span><span class="sxs-lookup"><span data-stu-id="ff6e5-157">Planning for Application Virtualization System Deployment</span></span>](planning-for-application-virtualization-system-deployment.md)

 

 





