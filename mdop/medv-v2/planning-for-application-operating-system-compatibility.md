---
title: アプリケーションのオペレーティング システムの互換性の計画
description: アプリケーションのオペレーティング システムの互換性の計画
author: dansimp
ms.assetid: cdb0a7f0-9da4-4562-8277-12972eb0fea8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5b10da2c870e5ddc32098136225515cdd0523809
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825467"
---
# <span data-ttu-id="7c034-103">アプリケーションのオペレーティング システムの互換性の計画</span><span class="sxs-lookup"><span data-stu-id="7c034-103">Planning for Application Operating System Compatibility</span></span>


<span data-ttu-id="7c034-104">このトピックでは、アプリケーションのオペレーティングシステムの互換性の問題を解決する方法について説明し、Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 が組織のためのソリューションとしてどのように機能するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7c034-104">This topic helps determine how to resolve application operating system compatibility issues, and discusses how Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 works as a solution for your organization.</span></span>

<span data-ttu-id="7c034-105">このトピックでは、MED-V のビジネス要件と MED-V と Windows XP モードとの比較 (App-v) について説明します。</span><span class="sxs-lookup"><span data-stu-id="7c034-105">This topic discusses the business requirements for MED-V and compares MED-V to Windows XP Mode and Microsoft Application Virtualization (App-V):</span></span>

-   [<span data-ttu-id="7c034-106">MED-V のビジネス要件</span><span class="sxs-lookup"><span data-stu-id="7c034-106">Business Requirements for MED-V</span></span>](#bkmk-whenmedv)

-   [<span data-ttu-id="7c034-107">MED-V と Windows XP モードの利点</span><span class="sxs-lookup"><span data-stu-id="7c034-107">Benefits of MED-V versus Windows XP Mode</span></span>](#bkmk-medvvsxp)

-   [<span data-ttu-id="7c034-108">MED-V と App-v の長所</span><span class="sxs-lookup"><span data-stu-id="7c034-108">Benefits of MED-V versus App-V</span></span>](#bkmk-medvvsappv)

## <a href="" id="bkmk-whenmedv"></a><span data-ttu-id="7c034-109">MED-V のビジネス要件</span><span class="sxs-lookup"><span data-stu-id="7c034-109">Business Requirements for MED-V</span></span>


<span data-ttu-id="7c034-110">会社の IT 部門が Windows 7 にアップグレードするかどうかを決定するときは、基幹業務アプリケーションや web ベースの基幹業務アプリケーションに注意して、これらの機能を新しいオペレーティングシステムで実行できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c034-110">When your company’s IT department is determining whether to upgrade to Windows 7, it must pay attention to its line-of-business applications and web-based line-of-business applications to make certain that these can run on the new operating system.</span></span> <span data-ttu-id="7c034-111">多くの場合、これらのアプリケーションと Url は、以前のバージョンの Windows や Internet Explorer で動作するように作成されているため、新しいオペレーティングシステムでそれらを使用すると問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7c034-111">Often, these applications and URLs were created to work specifically with an older version of Windows or Internet Explorer, and problems can occur when trying to use them in the new operating system.</span></span> <span data-ttu-id="7c034-112">Microsoft には、アップグレード時に発生する可能性があるさまざまな互換性の問題に対処するためのさまざまな方法が用意されています。たとえば、アプリケーション互換性ツールキット (ACT) や Windows 7 のプログラム互換性アシスタントなどです。</span><span class="sxs-lookup"><span data-stu-id="7c034-112">Microsoft offers many different methods for handling the various compatibility issues that can occur when you upgrade, such as the Application Compatibility Toolkit (ACT) and the Windows 7 Program Compatibility Assistant.</span></span> <span data-ttu-id="7c034-113">ただし、すべてのアプリケーションに互換性と修正があることがテストされた後でも、一部のアプリケーションが Windows 7 で正常に動作しない、または解決できないためにコストがかかりすぎます。</span><span class="sxs-lookup"><span data-stu-id="7c034-113">But even after all applications have been tested for compatibility and fixes have been determined, some applications still do not work correctly on Windows 7 or are too costly to resolve.</span></span>

<span data-ttu-id="7c034-114">MED-V を使うと、Windows XP を実行している Windows 仮想 PC 環境を通じて、これらのレガシアプリケーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7c034-114">By using MED-V, you can run these legacy applications through a Windows Virtual PC environment that is running Windows XP.</span></span> <span data-ttu-id="7c034-115">アップグレードする前に、新しいオペレーティングシステムでこれらの問題のあるアプリケーションをテストして検証する必要がなくなったため、Windows 7 への移行がよりスムーズかつ迅速になります。</span><span class="sxs-lookup"><span data-stu-id="7c034-115">Because you no longer have to test and validate these problem applications on the new operating system before upgrading, your migration to Windows 7 is much smoother and quicker.</span></span>

### <span data-ttu-id="7c034-116">MED-V のチェックリストを使用する</span><span class="sxs-lookup"><span data-stu-id="7c034-116">Using MED-V Checklist</span></span>

<span data-ttu-id="7c034-117">次のシナリオのいずれかが該当する場合は、MED-V を検討してください。</span><span class="sxs-lookup"><span data-stu-id="7c034-117">Consider MED-V if any of the following scenarios apply to you:</span></span>

-   <span data-ttu-id="7c034-118">大規模の組織 (500 ユーザーなど) で、Microsoft とのエンタープライズ契約を締結し、Windows 7 へのアップグレードを計画します。</span><span class="sxs-lookup"><span data-stu-id="7c034-118">You are a large organization (for example, 500 users and more), have an Enterprise Agreement with Microsoft, and plan to upgrade to Windows 7.</span></span>

-   <span data-ttu-id="7c034-119">基幹業務アプリケーションをテストし、Windows 7 と互換性のないものがあることを発見しました。</span><span class="sxs-lookup"><span data-stu-id="7c034-119">You have tested your line-of-business applications and have found some that are incompatible with Windows 7.</span></span>

-   <span data-ttu-id="7c034-120">一部の問題のアプリケーションでは、アプリケーションをアップグレードするか、Microsoft から提供されている shim (アプリケーション互換性ツールキット (ACT) など) を使用して互換性の問題を解決しましたが、一部のアプリケーションでは互換性の問題が残っています。</span><span class="sxs-lookup"><span data-stu-id="7c034-120">You have resolved the compatibility issues for some of these problem applications by upgrading the application or by using a Microsoft-provided shim, such as the Application Compatibility Toolkit (ACT), but compatibility issues remain for some applications.</span></span>

-   <span data-ttu-id="7c034-121">互換性のないアプリケーションを実行するためのオプションとして App V が使用されていますが、そのためには、App-v を実装した後でも、対処する必要があるアプリケーションオペレーティングシステムの互換性の問題が引き続き発生します。</span><span class="sxs-lookup"><span data-stu-id="7c034-121">You have considered App-V as an option for delivering the incompatible applications and have concluded that even after you implement App-V, you still have application operating system compatibility issues that you must address.</span></span>

-   <span data-ttu-id="7c034-122">Windows XP モードはソリューションとして見なされ、次の理由から効率的なオプションではないと判断しました。</span><span class="sxs-lookup"><span data-stu-id="7c034-122">You have considered Windows XP Mode as a solution and have determined that it is not an efficient option because:</span></span>

    -   <span data-ttu-id="7c034-123">問題のあるアプリケーションを含む仮想イメージを、個別ではなく、すべてのエンドユーザーに対して同時に展開できるようにする必要がある場合は、その仮想イメージをドメインに自動的に参加させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c034-123">You want to be able to deploy virtual images that contain the problem applications to all end users at the same time, instead of individually, and have the virtual images automatically joined to the domain.</span></span>

    -   <span data-ttu-id="7c034-124">お客様は、従来のアプリケーション (実質的には配信されます) を管理し、各エンドユーザのデスクトップではなく中央の1か所から Windows 仮想 PC 設定を管理することで、より多くのコストがかかると判断しました。</span><span class="sxs-lookup"><span data-stu-id="7c034-124">You have decided it is much more cost effective to manage these legacy applications (that are delivered virtually) and control the Windows Virtual PC settings from a centralized location instead of on each end user’s desktop.</span></span>

    -   <span data-ttu-id="7c034-125">1つのデスクトップではなく、スケールで仮想マシンの更新とサポートを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7c034-125">You want to be able to update and support the virtual machines in scale instead of per desktop.</span></span>

    -   <span data-ttu-id="7c034-126">以前のバージョンの Internet Explorer で実行している Url を仮想マシンにリダイレクトし、後で URL リダイレクションを簡単に管理できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c034-126">You want the ability to redirect URLs that run better on an older version of Internet Explorer to the virtual machines and to easily manage URL redirection later.</span></span>

-   <span data-ttu-id="7c034-127">より多くのコストがかかると判断された場合は、可能な限り早く Windows 7 にアップグレードすることをお勧めします。また、現在のアプリケーションの互換性の問題を解決するまでの時間は、MED-V で利用可能なソリューションを使用していることを意味します。</span><span class="sxs-lookup"><span data-stu-id="7c034-127">You have determined that it would be more cost effective and helpful to upgrade to Windows 7 as soon as possible and have decided to postpone resolving your remaining application compatibility issues until a later date, knowing that you have a solution available in MED-V.</span></span>

## <a href="" id="bkmk-medvvsxp"></a> <span data-ttu-id="7c034-128">MED-V と Windows XP モードの利点</span><span class="sxs-lookup"><span data-stu-id="7c034-128">Benefits of MED-V versus Windows XP Mode</span></span>


<span data-ttu-id="7c034-129">Windows 7 用 windows Virtual PC では、1つのデバイスで同時に複数のバージョンのオペレーティングシステムを実行でき、Windows 7 Professional Edition 以降にも含まれています。</span><span class="sxs-lookup"><span data-stu-id="7c034-129">Windows Virtual PC for Windows 7 lets you run different versions of an operating system at the same time on a single device and is included in Windows 7 Professional Edition and higher.</span></span>

<span data-ttu-id="7c034-130">Windows XP モードの機能では、windows xp の事前定義された環境を作成するための事前構成済みの Windows XP イメージを提供することで、Windows 仮想 PC を活用できます。</span><span class="sxs-lookup"><span data-stu-id="7c034-130">Windows XP Mode functionality takes advantage of Windows Virtual PC by providing a preconfigured Windows XP image that lets you create a virtual Windows XP environment.</span></span> <span data-ttu-id="7c034-131">この仮想環境では、Windows 7 と互換性のないアプリケーションを手動でインストールすることができます。また、Windows Virtual PC 経由でデスクトップからシームレスに実行されます。</span><span class="sxs-lookup"><span data-stu-id="7c034-131">In this virtual environment, you can manually install applications that are incompatible with Windows 7 and that run seamlessly from your desktop through Windows Virtual PC.</span></span>

**<span data-ttu-id="7c034-132">Windows XP モードを使うと、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="7c034-132">By using Windows XP Mode, you can do the following:</span></span>**

-   <span data-ttu-id="7c034-133">Windows 仮想 PC で実行されている仮想マシンの内部に Windows XP と互換性のあるアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="7c034-133">Run applications that are compatible with Windows XP inside a virtual machine that runs in Windows Virtual PC.</span></span>

-   <span data-ttu-id="7c034-134">これらのアプリケーションをホストのデスクトップまたはプログラムメニューに公開します。</span><span class="sxs-lookup"><span data-stu-id="7c034-134">Publish these applications to the host’s desktop or Program menu.</span></span>

<span data-ttu-id="7c034-135">これらの仮想マシンを、Windows 7 へのエンタープライズ移行の一部として大規模な場所に配信する必要がある場合は、仮想マシンをすばやく展開、プロビジョニング、カスタマイズできるようにする必要があります。そのため、設定を制御して簡単にサポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="7c034-135">When you want to deliver these virtual machines on a large scale as part of an enterprise migration to Windows 7, you must be able to deploy the virtual machines quickly, provision, and customize them efficiently, control their settings, and support them easily.</span></span>

<span data-ttu-id="7c034-136">MED-V は Windows XP モードで構築し、企業全体のアプリケーションの互換性を実現します。</span><span class="sxs-lookup"><span data-stu-id="7c034-136">MED-V builds upon Windows XP Mode to deliver enterprise-wide application compatibility.</span></span> <span data-ttu-id="7c034-137">Windows XP モードは、個人や小規模企業への仮想アプリケーション機能の提供に限定されていますが、MED-V を使用すると、企業ネットワーク全体で事前に構成された Windows XP イメージの大規模な展開を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7c034-137">Whereas Windows XP mode is limited to providing virtual application functionality to individuals and small businesses, MED-V allows for large-scale deployments of preconfigured Windows XP images throughout your corporate network.</span></span> <span data-ttu-id="7c034-138">これらの仮想 MED-V ワークスペースの構成、展開、保守のためのエンタープライズ対応の管理ソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="7c034-138">It gives you an enterprise-ready management solution for the configuration, deployment, and maintenance of these virtual MED-V workspaces.</span></span> <span data-ttu-id="7c034-139">また、エンタープライズ管理者は、画像の使用を制御するための一連のポリシーを提供します。</span><span class="sxs-lookup"><span data-stu-id="7c034-139">MED-V also gives enterpriseadministrators a set of policies to control image use.</span></span> <span data-ttu-id="7c034-140">これには、これらの画像内の特定のアプリケーションへのアクセス権を持つユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7c034-140">This includes which users will have access to which specific applications within these images.</span></span>

**<span data-ttu-id="7c034-141">MED-V を使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="7c034-141">By using MED-V, you can do the following:</span></span>**

-   <span data-ttu-id="7c034-142">互換性のないすべてのアプリケーションと URL をテストして解決することなく、新しいオペレーティングシステムにアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="7c034-142">Upgrade to your new operating system without having to test and resolve every incompatible application and URL.</span></span>

-   <span data-ttu-id="7c034-143">ユーザーごとに自動的にドメインに参加してカスタマイズされた仮想 Windows XP のイメージを展開します。</span><span class="sxs-lookup"><span data-stu-id="7c034-143">Deploy virtual Windows XP images that are automatically domain-joined and customized per user.</span></span>

-   <span data-ttu-id="7c034-144">ユーザーにアプリケーションと URL リダイレクション情報をプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="7c034-144">Provision applications and URL redirection information to users.</span></span>

-   <span data-ttu-id="7c034-145">Windows 仮想 PC の設定を制御します。</span><span class="sxs-lookup"><span data-stu-id="7c034-145">Control the Windows Virtual PC settings.</span></span>

-   <span data-ttu-id="7c034-146">監視とトラブルシューティングを通じてエンドポイントを保守およびサポートする。</span><span class="sxs-lookup"><span data-stu-id="7c034-146">Maintain and support endpoints through monitoring and troubleshooting.</span></span>

-   <span data-ttu-id="7c034-147">一時停止状態であっても、ゲストコンピューターに修正プログラムが適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7c034-147">Ensure that guest computers are patched, even if in a suspended state.</span></span>

-   <span data-ttu-id="7c034-148">ユーザーごとの仮想マシンの作成と sysprep の初期化を自動化します。</span><span class="sxs-lookup"><span data-stu-id="7c034-148">Automate per-user virtual machine creation and sysprep initialization.</span></span>

-   <span data-ttu-id="7c034-149">ホストおよびゲストコンピューターの問題を簡単に診断できます。</span><span class="sxs-lookup"><span data-stu-id="7c034-149">Easily diagnose issues on the host and guest computers.</span></span>

-   <span data-ttu-id="7c034-150">Windows 仮想 PC NAT モードによって接続されているゲストコンピューターをシームレスに管理します。</span><span class="sxs-lookup"><span data-stu-id="7c034-150">Seamlessly manage guest computers that are connected through Windows Virtual PC NAT mode.</span></span>

## <a href="" id="bkmk-medvvsappv"></a><span data-ttu-id="7c034-151">MED-V と App-v の長所</span><span class="sxs-lookup"><span data-stu-id="7c034-151">Benefits of MED-V versus App-V</span></span>


<span data-ttu-id="7c034-152">MED-V と App-v は、アプリのオペレーティングシステムの互換性の問題を解決するために簡単に共同作業できる2つの非常に異なるテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="7c034-152">MED-V and App-V are two very different technologies that can easily work together to solve your application operating system compatibility issues.</span></span> <span data-ttu-id="7c034-153">App-v を使用して、各アプリケーション用の個別のパッケージを作成します。各アプリケーションは、他のアプリケーションとは別に保存されます。</span><span class="sxs-lookup"><span data-stu-id="7c034-153">By using App-V, you create an individualized package for each application, each of which is then kept separate from the others.</span></span> <span data-ttu-id="7c034-154">各仮想アプリケーションは、すぐにエンドユーザーに配信することができます。これは、Windows 7 の展開戦略で非常に便利です。</span><span class="sxs-lookup"><span data-stu-id="7c034-154">Each virtual application can then be immediately delivered to the end user, which is very useful for a Windows 7 deployment strategy.</span></span>

<span data-ttu-id="7c034-155">MED-V では、アプリケーションを個別に処理することはできません。</span><span class="sxs-lookup"><span data-stu-id="7c034-155">MED-V does not handle applications individually.</span></span> <span data-ttu-id="7c034-156">代わりに、Windows 7 を実行している同じデスクトップ上に Windows XP の追加のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="7c034-156">Instead, it creates an additional instance of Windows XP on the same desktop that is running Windows 7.</span></span> <span data-ttu-id="7c034-157">組織内の他のデスクトップの場合と同様に、この仮想イメージに必要なだけアプリケーションをインストールして、イメージを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="7c034-157">You can install as many applications as necessary into this virtual image and manage the image just as you would any other desktop in your organization.</span></span>

<span data-ttu-id="7c034-158">さらに、MED-V と App-v を併用して、App-v を介してシーケンス処理された仮想アプリケーションを、MED-V を使ってインストール、公開、管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="7c034-158">In addition, you can use MED-V together with App-V so that virtual applications that are sequenced through App-V are installed, published, and managed by using MED-V.</span></span>

## <span data-ttu-id="7c034-159">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7c034-159">Related topics</span></span>


[<span data-ttu-id="7c034-160">MED-V 展開を定義して計画する</span><span class="sxs-lookup"><span data-stu-id="7c034-160">Define and Plan your MED-V Deployment</span></span>](define-and-plan-your-med-v-deployment.md)

 

 





