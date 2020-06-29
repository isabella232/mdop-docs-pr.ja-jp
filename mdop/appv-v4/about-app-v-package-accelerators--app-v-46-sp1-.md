---
title: App-V パッケージ アクセラレータについて (App-V 4.6 SP1)
description: App-V パッケージ アクセラレータについて (App-V 4.6 SP1)
author: manikadhiman
ms.assetid: fc2d2375-8f17-4a6d-b374-771cb947cb8c
ms.reviewer: ''
manager: dansimp
ms.author: v-madhi
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cb7b8e6fa9482838283257843caf4b291c03bf2d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820094"
---
# <span data-ttu-id="fa068-103">App-V パッケージ アクセラレータについて (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="fa068-103">About App-V Package Accelerators (App-V 4.6 SP1)</span></span>


<span data-ttu-id="fa068-104">App-v パッケージアクセラレータを使用して、大規模で複雑なアプリケーションに自動的に対応することができます。</span><span class="sxs-lookup"><span data-stu-id="fa068-104">You can use App-V Package Accelerators to automatically sequence large, complex applications.</span></span> <span data-ttu-id="fa068-105">さらに、App-v パッケージアクセラレータを適用するときに、仮想アプリケーションパッケージを作成するためにアプリケーションを手動でインストールする必要があるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="fa068-105">Additionally, when you apply an App-V Package Accelerator, you are not always required to manually install an application to create the virtual application package.</span></span>

<span data-ttu-id="fa068-106">**注** 場合によっては、パッケージアクセラレータを使う前に、App-v Sequencer を実行しているコンピューターにアプリケーションをローカルでインストールするように求めるメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="fa068-106">**Note** In some cases, you are prompted to install an application locally to the computer running the App-V Sequencer before you can use the Package Accelerator.</span></span> <span data-ttu-id="fa068-107">アプリケーションをインストールする必要がある場合は、アプリケーションの既定の場所にアプリケーションをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa068-107">If you have to install an application, you must install the application to the application’s default location.</span></span> <span data-ttu-id="fa068-108">このインストールは、App-v Sequencer では監視されません。</span><span class="sxs-lookup"><span data-stu-id="fa068-108">This installation is not monitored by App-V Sequencer.</span></span> <span data-ttu-id="fa068-109">App-v パッケージアクセラレータが作成されると、パッケージアクセラレータの作成者は、アプリケーションをローカルでインストールする必要があるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="fa068-109">When the App-V Package Accelerator is created, the author of the Package Accelerator determines whether to install an application locally is required.</span></span>

 

<span data-ttu-id="fa068-110">App-v パッケージアクセラレータと関連するインストールメディアから必要なファイルを抽出して、アプリケーションのインストールを監視せずに仮想パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="fa068-110">App-V Sequencer extracts the required files from the App-V Package Accelerator and associated installation media to create a virtual package without having to monitor the installation of the application.</span></span>

<span data-ttu-id="fa068-111">**重要** 免責事項: Microsoft Application Virtualization Sequencer は、パッケージアクセラレータの作成に使用しているソフトウェアアプリケーションのライセンス権限を付与していません。</span><span class="sxs-lookup"><span data-stu-id="fa068-111">**Important** Disclaimer: The Microsoft Application Virtualization Sequencer does not give you any license rights to the software application you are using to create a Package Accelerator.</span></span> <span data-ttu-id="fa068-112">お客様は、本アプリケーションのすべてのエンドユーザライセンス条項を遵守する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa068-112">You must abide by all end user license terms for such application.</span></span> <span data-ttu-id="fa068-113">ソフトウェアアプリケーションのライセンス条項によって、Application Virtualization Sequencer を使用したパッケージアクセラレータの作成が許可されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa068-113">It is your responsibility to make sure the software application’s license terms allow you to create a Package Accelerator using Application Virtualization Sequencer.</span></span>

 

<span data-ttu-id="fa068-114">App-v パッケージアクセラレータとプロジェクトテンプレートは互いに異なります。</span><span class="sxs-lookup"><span data-stu-id="fa068-114">App-V Package Accelerators and project templates differ from each other.</span></span> <span data-ttu-id="fa068-115">パッケージアクセラレータは、アプリケーションに固有です。</span><span class="sxs-lookup"><span data-stu-id="fa068-115">Package Accelerators are application-specific.</span></span> <span data-ttu-id="fa068-116">プロジェクトテンプレートを使用すると、ユーザーは組織固有の一般的な設定を保存して、複数のアプリケーションに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="fa068-116">Project templates enable users to save commonly used settings specific to an organization and apply them to multiple applications.</span></span> <span data-ttu-id="fa068-117">また、コマンドプロンプトでプロジェクトテンプレートを作成することもできますが、これに対して、アプリのパッケージアクセラレータを作成するには、アプリの Sequencer コンソールを使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa068-117">You can also create project templates at the command prompt, while in contrast, you must use the App-V Sequencer console to create Package Accelerators.</span></span> <span data-ttu-id="fa068-118">さらに、パッケージアクセラレータを使用してパッケージを作成し、プロジェクトテンプレートを適用することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fa068-118">Additionally, creating a package by using a Package Accelerator and applying a project template is not supported.</span></span>

## <span data-ttu-id="fa068-119">App-v パッケージアクセラレータの共有</span><span class="sxs-lookup"><span data-stu-id="fa068-119">Sharing App-V Package Accelerators</span></span>


<span data-ttu-id="fa068-120">このセクションでは、パッケージアクセラレータの共有方法に関するベストプラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fa068-120">This section provides best practice information about how to share Package Accelerators.</span></span> <span data-ttu-id="fa068-121">パッケージアクセラレータの共有を計画している場合は、コンピューター名、ユーザーアカウント情報、関連するアプリケーションに関する情報などの情報がパッケージアクセラレータに含まれている可能性があります。次の一覧では、パッケージアクセラレータの作成時に考慮する必要がある方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fa068-121">If you plan to share Package Accelerators, information such as computer names, user account information, and information about the associated applications might be included in the Package Accelerators.The following list describes methods you should consider when creating Package Accelerators:</span></span>

-   <span data-ttu-id="fa068-122">**ユーザー名**。</span><span class="sxs-lookup"><span data-stu-id="fa068-122">**User name**.</span></span> <span data-ttu-id="fa068-123">App-v Sequencer を実行しているコンピューターにログオンするときは、コンピューター/ドメインを管理するための組み込みの**管理者**アカウントなどの一般的なユーザーアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa068-123">When you log on to the computer running App-V Sequencer, you should use a generic user account, such as the built-in **administrator** account for administering the computer / domain.</span></span> <span data-ttu-id="fa068-124">既存のユーザー名に基づくアカウントは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="fa068-124">You should not use an account that is based on an existing user name.</span></span>

-   <span data-ttu-id="fa068-125">**コンピューター名**。</span><span class="sxs-lookup"><span data-stu-id="fa068-125">**Computer Name**.</span></span> <span data-ttu-id="fa068-126">Sequencer を実行しているコンピューターの一般的な非識別名を指定します。</span><span class="sxs-lookup"><span data-stu-id="fa068-126">Specify a general, non-identifying name for the computer running the Sequencer.</span></span>

-   <span data-ttu-id="fa068-127">**サーバーの URL**。</span><span class="sxs-lookup"><span data-stu-id="fa068-127">**Server URL**.</span></span> <span data-ttu-id="fa068-128">Sequencer コンソールの [**展開**] タブで、サーバー URL 構成情報の既定の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="fa068-128">In the Sequencer console, on the **Deployment** tab, use the default settings for the server URL configuration information.</span></span>

-   <span data-ttu-id="fa068-129">**アプリケーション**。</span><span class="sxs-lookup"><span data-stu-id="fa068-129">**Applications**.</span></span> <span data-ttu-id="fa068-130">パッケージアクセラレータの作成時に、Sequencer を実行しているコンピューターにインストールされているアプリケーションの一覧を共有しない場合は、 **appv\_manifest.xml**ファイルを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa068-130">If you do not want to share the list of applications that were installed on the computer running the Sequencer when you created the Package Accelerator, you must delete the **appv\_manifest.xml** file.</span></span> <span data-ttu-id="fa068-131">このファイルは、仮想アプリケーションパッケージのパッケージルートディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="fa068-131">This file is located in the package root directory of the virtual application package.</span></span>

<span data-ttu-id="fa068-132">また、仮想アプリケーションパッケージに関連付けられた設定や構成ファイルを確認して、アプリケーションに個人情報が含まれていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa068-132">You should also review any settings or configuration files associated with the virtual application package to ensure the applications do not contain any personal information.</span></span>

## <span data-ttu-id="fa068-133">App-v パッケージアクセラレータをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="fa068-133">Securing App-V Package Accelerators</span></span>


<span data-ttu-id="fa068-134">常に、app-v パッケージアクセラレータと関連するインストールメディアをネットワーク上の安全な場所に保存して、App-v パッケージアクセラレータを保護し、インストールファイルが改ざんされたり、破損したりしないようにします。</span><span class="sxs-lookup"><span data-stu-id="fa068-134">Always save App-V Package Accelerators and any associated installation media in a secure location on the network to protect the App-V Package Accelerators and the installation files from being tampered with or becoming corrupted.</span></span> <span data-ttu-id="fa068-135">パッケージアクセラレータにはパスワードとユーザー固有の情報が含まれていることもあるため、App-V パッケージアクセラレータはセキュリティで保護された場所に保存する必要があります。また、パッケージアクセラレータが適用されたときに発行元を確認できるように、パッケージアクセラレータの作成後にデジタル署名を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa068-135">Because Package Accelerators can also contain password and user-specific information, you must save App-V Package Accelerators in a secure location, and you must digitally sign the Package Accelerator after you create it so that the publisher can be verified when the Package Accelerator is applied.</span></span> <span data-ttu-id="fa068-136">デジタル署名の詳細については、「[デジタル署名のセキュリティに関するガイドライン](https://go.microsoft.com/fwlink/?LinkId=204705)」を参照してください。共通条件セキュリティ ( https://go.microsoft.com/fwlink/?LinkId=204705) .</span><span class="sxs-lookup"><span data-stu-id="fa068-136">For more information about digital signatures, see [Application Guidelines on Digital Signature Practices for Common Criteria Security](https://go.microsoft.com/fwlink/?LinkId=204705) (https://go.microsoft.com/fwlink/?LinkId=204705).</span></span>

## <span data-ttu-id="fa068-137">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fa068-137">Related topics</span></span>


[<span data-ttu-id="fa068-138">App-V パッケージ アクセラレータを作成する方法 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="fa068-138">How to Create App-V Package Accelerators (App-V 4.6 SP1)</span></span>](how-to-create-app-v-package-accelerators--app-v-46-sp1-.md)

[<span data-ttu-id="fa068-139">パッケージアクセラレータを適用して仮想アプリケーションパッケージを作成する方法 (App-v 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="fa068-139">How to Apply a Package Accelerator to Create a Virtual Application Package (App-V 4.6 SP1)</span></span>](how-to-apply-a-package-accelerator-to-create-a-virtual-application-package---app-v-46-sp1-.md)

 

 





