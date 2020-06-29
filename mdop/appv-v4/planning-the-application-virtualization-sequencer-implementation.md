---
title: Application Virtualization Sequencer の実装計画
description: Application Virtualization Sequencer の実装計画
author: dansimp
ms.assetid: 052f32fe-ad13-4921-a8ce-4a657eb2b2bf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ac62991e290dcd2da1c42f025a19365bda239fb8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815894"
---
# <span data-ttu-id="87457-103">Application Virtualization Sequencer の実装計画</span><span class="sxs-lookup"><span data-stu-id="87457-103">Planning the Application Virtualization Sequencer Implementation</span></span>


<span data-ttu-id="87457-104">シーケンスは、仮想アプリケーションとアプリケーションパッケージを作成するためにアプリケーションの仮想化によって使用されるプロセスであり、Application Virtualization Sequencer ソフトウェアがインストールされているコンピューターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87457-104">Sequencing, the process used by Application Virtualization to create virtual applications and application packages, requires the use of a computer with the Application Virtualization Sequencer software installed.</span></span>

<span data-ttu-id="87457-105">シーケンス処理の際には、Sequencer はモニターモードに配置され、シーケンス処理されるアプリケーションはシーケンスコンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="87457-105">During the sequencing process, the Sequencer is placed in monitor mode, and the application to be sequenced is installed on the sequencing computer.</span></span> <span data-ttu-id="87457-106">次に、シーケンス処理されたアプリケーションが起動され、最も重要でよく使われる関数が実行されるため、監視プロセスでは、アプリケーションの実行に必要なアプリケーションパッケージの最小のコンテンツを含むプライマリ機能ブロックを構成できます。</span><span class="sxs-lookup"><span data-stu-id="87457-106">Next, the sequenced application is started, and its most important and commonly used functions are exercised so that the monitoring process can configure the primary feature block, which contains the minimum content in an application package that is necessary for an application to run.</span></span> <span data-ttu-id="87457-107">これらの手順を完了すると、監視モードが停止し、シーケンス処理されたアプリケーションが保存されて、適切な操作が確認されます。</span><span class="sxs-lookup"><span data-stu-id="87457-107">When these steps are complete, monitoring mode is stopped and the sequenced application is saved and tested to verify correct operation.</span></span>

<span data-ttu-id="87457-108">優先順位を付けるためにどのアプリケーションを選ぶかを決定するときは、特定のアプリケーションを順序指定できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="87457-108">When deciding which applications to choose for sequencing, remember that certain applications cannot be sequenced.</span></span> <span data-ttu-id="87457-109">これには、Internet Explorer、デバイスドライバー、起動時にサービスを起動するアプリケーションなど、Windows オペレーティングシステムの特定の部分が含まれます。</span><span class="sxs-lookup"><span data-stu-id="87457-109">These include certain parts of the Windows operating system, such as Internet Explorer, device drivers, and applications that start services at boot time.</span></span>

<span data-ttu-id="87457-110">Sequencer のインストール方法の詳細については、「 [Application Virtualization sequencer をインストールする方法](how-to-install-the-application-virtualization-sequencer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87457-110">For step-by-step information about installing the Sequencer, see [How to Install the Application Virtualization Sequencer](how-to-install-the-application-virtualization-sequencer.md).</span></span>

<span data-ttu-id="87457-111">**重要** すべてのシーケンス処理プランは、企業のセキュリティチームによってレビューおよび承認される必要があります。</span><span class="sxs-lookup"><span data-stu-id="87457-111">**Important** The entire sequencing process plan should be reviewed and approved by your corporate security team.</span></span> <span data-ttu-id="87457-112">一般的に、Sequencer 操作はラボの運用環境とは別に維持されます。</span><span class="sxs-lookup"><span data-stu-id="87457-112">Sequencer operations would usually be kept separate from the production environment in a lab.</span></span> <span data-ttu-id="87457-113">これは、ビジネス要件に基づいて、必要に応じて簡単に、または包括的にすることができます。</span><span class="sxs-lookup"><span data-stu-id="87457-113">This can be as simple or as comprehensive as necessary, based on your business requirements.</span></span> <span data-ttu-id="87457-114">シーケンス処理のコンピューターでは、完了したパッケージを運用サーバーにコピーするために企業ネットワークへの接続が必要になります。</span><span class="sxs-lookup"><span data-stu-id="87457-114">The sequencing computers will need connectivity to the corporate network to copy finished packages over to the production servers.</span></span> <span data-ttu-id="87457-115">ただし、通常はウイルス対策を行わないで運営されているため、企業ネットワーク上にはないものとします。たとえば、ファイアウォールまたは分離されたネットワークセグメントで操作することができます。</span><span class="sxs-lookup"><span data-stu-id="87457-115">However, because they are typically operated without antivirus protection, they must not be on the corporate network unprotected—for example, you might be able to operate behind a firewall or on an isolated network segment.</span></span> <span data-ttu-id="87457-116">分離仮想ネットワークを共有するように構成された仮想マシンを使用することも、受け入れられる方法です。</span><span class="sxs-lookup"><span data-stu-id="87457-116">Using Virtual Machines configured to share an isolated virtual network might also be an acceptable approach.</span></span> <span data-ttu-id="87457-117">企業のセキュリティポリシーに従って、この状況に安全に対処してください。</span><span class="sxs-lookup"><span data-stu-id="87457-117">Follow your corporate security policies to safely address this situation.</span></span>

 

<span data-ttu-id="87457-118">シーケンス処理を計画するための主な手順は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="87457-118">Key steps for planning the sequencing process include the following:</span></span>

-   <span data-ttu-id="87457-119">毎月処理する必要があるアプリケーションの数、それらのアプリケーションのサイズ、今後の更新プログラムの順序を指定するための余裕を追加します。</span><span class="sxs-lookup"><span data-stu-id="87457-119">Consider the number of applications you expect to process each month, the size of those applications, and add an allowance for sequencing future updates.</span></span> <span data-ttu-id="87457-120">パッケージは、最大 4 GB のサイズ、圧縮または非圧縮のいずれかにすることができます。</span><span class="sxs-lookup"><span data-stu-id="87457-120">Packages can be up to 4 GB in size, compressed or uncompressed.</span></span>

-   <span data-ttu-id="87457-121">組織が各アプリケーションのシーケンスを実行するために、系統的で反復可能なプロセスを準備し、文書化します。</span><span class="sxs-lookup"><span data-stu-id="87457-121">Prepare and document a methodical, repeatable process for your organization to follow when sequencing each application.</span></span> <span data-ttu-id="87457-122">これには、各実行のチェックリストとバージョンコントロールのプロセスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87457-122">This should include the use of a checklist for each run, as well as a version control process.</span></span> <span data-ttu-id="87457-123">順序付けされた各アプリケーションの追跡ログを使用することも、パッケージに関する技術的な問題を調査する際に非常に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="87457-123">The use of a tracking log for each sequenced application is also very helpful when investigating possible technical issues with a package.</span></span>

-   <span data-ttu-id="87457-124">シーケンスアプリケーションの場合、処理スループットに最適化された高パフォーマンスのコンピューターを使用します。これには、最低 4 GB の RAM と高速な CPU (3 GHz 以上) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="87457-124">For sequencing applications, use high-performing computers that are optimized for processing throughput, with at least 4 GB of RAM and a fast CPU (3 GHz or faster).</span></span> <span data-ttu-id="87457-125">高速ハードディスクと別個のディスクボリュームを使用すると、パフォーマンスが向上することもあります。</span><span class="sxs-lookup"><span data-stu-id="87457-125">Fast hard disks and the use of separate disk volumes can also improve performance.</span></span> <span data-ttu-id="87457-126">仮想マシンは、簡単にリセットできるため、シーケンスには適しています。また、ローカルパーティション上のクリーンな画像を備えた物理コンピューターを使って、各パッケージの順序付け操作が完了した後ですばやく再イメージングを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="87457-126">Virtual Machines are ideal for sequencing because they can easily be reset, or you can use a physical computer with a clean image on a local partition to enable rapid re-imaging after each package sequencing operation has been completed.</span></span>

    <span data-ttu-id="87457-127">**重要** セーフモードでの App-v sequencer の実行はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="87457-127">**Important** Running the App-V sequencer in Safe Mode is not supported.</span></span>

     

-   <span data-ttu-id="87457-128">Microsoft Office や Java ランタイム環境などの統合要素を含む、シーケンス処理されたアプリケーションのオペレーティング環境を理解していることを確認します。これは、アプリケーションを順序付けする前に、シーケンスコンピューターに何かをインストールする必要があるかどうかを判断することが多いためです。</span><span class="sxs-lookup"><span data-stu-id="87457-128">Verify that you understand the sequenced application’s operating environment, including integration elements such as Microsoft Office or the Java Runtime Environment, because this will often determine whether anything has to be installed on the sequencing computer prior to sequencing the application.</span></span>

-   <span data-ttu-id="87457-129">新しいシーケンス処理の各操作は常に、クリーンな基本イメージで開始するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="87457-129">Ensure that each new sequencing operation always starts with a clean base image.</span></span> <span data-ttu-id="87457-130">優先順位のコンピューターがリセットされたことを確認します。保存した画像を物理コンピューターに復元するか、すべての変更を破棄した後で仮想マシンを再起動します。</span><span class="sxs-lookup"><span data-stu-id="87457-130">Make sure that the sequencing computer has been reset, either by restoring the saved image to a physical computer or by restarting a virtual machine after discarding all changes.</span></span> <span data-ttu-id="87457-131">ベースイメージには、保存する前に Windows Update から適用された最新の更新プログラムが適用されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="87457-131">The base image should have the latest updates applied from Windows Update before saving.</span></span>

-   <span data-ttu-id="87457-132">シーケンス処理中に、固定されたプラットフォームを使用することが重要であるため、ウイルス対策スキャナーや Windows Update などのインストール監視プロセスに干渉する可能性のある、シーケンスコンピューター上のすべての設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="87457-132">Turn off anything on the sequencing computer that can interfere with the install monitoring process, such antivirus scanners and Windows Update, because having a stable platform during the sequencing process is essential.</span></span> <span data-ttu-id="87457-133">この手順ではセキュリティのリスクが深刻であるため、コンピューターとネットワーク、およびシーケンス処理されたアプリケーションパッケージを保護するために、適切な措置が講じられていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="87457-133">Because this step incurs significant security risks, ensure that the correct precautions are taken to protect the computer and network as well as the sequenced application package.</span></span> <span data-ttu-id="87457-134">アプリパッケージの順序を付ける前に、ウイルス対策スキャンを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="87457-134">We recommend that you do an antivirus scan of application packages before sequencing them.</span></span>

-   <span data-ttu-id="87457-135">シーケンス後に各アプリケーションをテストするための詳細なプロセスを含めます。</span><span class="sxs-lookup"><span data-stu-id="87457-135">Include a detailed process for testing each application after sequencing.</span></span> <span data-ttu-id="87457-136">シーケンス処理されたアプリケーションをテストすることによって、仮想化されたアプリケーションをエンドユーザーに展開する前に、正しく機能するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="87457-136">Testing the sequenced application will determine whether it functions correctly and is an essential part of the process prior to deploying the virtualized application to end users.</span></span> <span data-ttu-id="87457-137">エンドユーザーに大規模な展開を行う前にテストを行う最後の手順として、テストグループへの試験的展開を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87457-137">As the final step in testing prior to wide-scale deployment to end users, you should also plan for a pilot deployment to a test group.</span></span>

-   <span data-ttu-id="87457-138">連続したアプリケーションをテストする場合は、同じ種類のコンピューター機器を選択し、会社の運用環境で使用されている同じオペレーティングシステムを実行します。</span><span class="sxs-lookup"><span data-stu-id="87457-138">When testing sequenced applications, choose computer equipment of the same type and running the same operating systems that are in use in the company production environment.</span></span> <span data-ttu-id="87457-139">適切に構成されていれば、仮想マシンと物理マシンのいずれかを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="87457-139">As long as they are configured properly, either virtual machines or physical machines can be used.</span></span>

## <span data-ttu-id="87457-140">関連トピック</span><span class="sxs-lookup"><span data-stu-id="87457-140">Related topics</span></span>


[<span data-ttu-id="87457-141">Application Virtualization Sequencer のハードウェア要件とソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="87457-141">Application Virtualization Sequencer Hardware and Software Requirements</span></span>](application-virtualization-sequencer-hardware-and-software-requirements.md)

[<span data-ttu-id="87457-142">Application Virtualization Sequencer をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="87457-142">How to Install the Application Virtualization Sequencer</span></span>](how-to-install-the-application-virtualization-sequencer.md)

[<span data-ttu-id="87457-143">Application Virtualization Sequencer をアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="87457-143">How to Upgrade the Application Virtualization Sequencer</span></span>](how-to-upgrade-the-application-virtualization-sequencer.md)

[<span data-ttu-id="87457-144">セキュリティと保護の概要</span><span class="sxs-lookup"><span data-stu-id="87457-144">Security and Protection Overview</span></span>](security-and-protection-overview.md)

 

 





