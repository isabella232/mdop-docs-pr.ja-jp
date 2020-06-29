---
title: UE-V 1.0 のアーキテクチャの概要
description: UE-V 1.0 のアーキテクチャの概要
author: dansimp
ms.assetid: d54f9f10-1a4d-4e56-802d-22d51646e1cc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 76703cf4c7297401e6516830bf194cef741d60ec
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827097"
---
# <span data-ttu-id="4e5cc-103">UE-V 1.0 のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="4e5cc-103">High-Level Architecture for UE-V 1.0</span></span>


<span data-ttu-id="4e5cc-104">このトピックでは、Microsoft User Experience Virtualization (UE-V) 設定のローミングソリューションの高レベルのアーキテクチャ要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-104">This topic describes high-level architectural elements of the Microsoft User Experience Virtualization (UE-V) settings roaming solution.</span></span> <span data-ttu-id="4e5cc-105">次の要素は、標準の UE-V 展開に含まれています。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-105">The following elements are part of a standard UE-V deployment.</span></span>

![ue-v agent アーキテクチャ図](images/ue-vagentarchitecturaldiagram.gif)

<span data-ttu-id="4e5cc-107">UE-V Agent は、UE-V の [設定] の場所テンプレートで指定されているように、アプリケーションとオペレーティングシステムのプロセスを監視します。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-107">The UE-V Agent monitors the applications and the operating system processes as they are identified in the UE-V settings location templates.</span></span> <span data-ttu-id="4e5cc-108">アプリケーションまたはオペレーティングシステムが起動すると、設定が設定パッケージから読み取られ、コンピューターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-108">When the application or operating system starts, the settings are read from the settings package and applied to the computer.</span></span> <span data-ttu-id="4e5cc-109">アプリケーションが閉じるか、オペレーティングシステムがロックまたはシャットダウンされると、設定は、設定の保存場所にある UE-V 設定パッケージに保存されます。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-109">When the application closes or when the operating system is locked or shut down, settings are saved in a UE-V settings package in the settings storage location.</span></span>

## <span data-ttu-id="4e5cc-110">設定の保存場所</span><span class="sxs-lookup"><span data-stu-id="4e5cc-110">Settings storage location</span></span>


<span data-ttu-id="4e5cc-111">設定の保存場所は、ユーザーエクスペリエンス仮想化エージェントが読み取りと書き込みの設定にアクセスするファイル共有です。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-111">The settings storage location is a file share that the User Experience Virtualization agent accesses to read and write settings.</span></span> <span data-ttu-id="4e5cc-112">この場所は、Active Directory のホームディレクトリか、UE-V のインストール時に定義されます。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-112">This location is either the Active Directory home directory or defined during the UE-V installation.</span></span> <span data-ttu-id="4e5cc-113">UE-V agent のインストール中に場所を設定するか、後でグループポリシー、WMI、または PowerShell を使用して場所を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-113">You can set the location during the installation of the UE-V agent, or you can set it later with Group Policy, WMI, or PowerShell.</span></span> <span data-ttu-id="4e5cc-114">この場所は、ユーザーがアクセスできる一般的なファイル共有に配置できます。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-114">The location can be on any common file share that users can access.</span></span> <span data-ttu-id="4e5cc-115">インストール時に設定の保存場所が設定されていない場合、UE-V は Active Directory のホームディレクトリを使用します。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-115">If no setting storage location is set during installation then UE-V will use the home directory in Active Directory.</span></span> <span data-ttu-id="4e5cc-116">UE-V agent は、場所を確認し、ユーザー設定の保存とアクセスを行うユーザーから非表示になっているシステムフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-116">The UE-V agent verifies the location and creates a system folder that is hidden from the user in which to store and access the user settings.</span></span> <span data-ttu-id="4e5cc-117">設定記憶域の詳細については、「 [ue-v の環境の準備](preparing-your-environment-for-ue-v.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-117">For more information about settings storage, see [Preparing Your Environment for UE-V](preparing-your-environment-for-ue-v.md).</span></span>

## <span data-ttu-id="4e5cc-118">UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="4e5cc-118">UE-V Agent</span></span>


<span data-ttu-id="4e5cc-119">UE-V agent は、ユーザーエクスペリエンスの仮想化によって同期される設定を持つ各コンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-119">The UE-V agent is installed on each computer with settings that are synchronized by User Experience Virtualization.</span></span> <span data-ttu-id="4e5cc-120">エージェントは、設定に加えられたすべての変更について、登録済みアプリケーションとオペレーティングシステムを監視し、それらの設定をコンピューター間で同期します。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-120">The agent monitors the registered applications and the operating system for any changes to that are made to settings, and it synchronizes those settings between computers.</span></span> <span data-ttu-id="4e5cc-121">設定は、アプリケーションの起動時に設定の保存場所からアプリケーションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-121">Settings are applied from the settings storage location to the application when the application is started.</span></span> <span data-ttu-id="4e5cc-122">設定は、アプリケーションが閉じるときに設定の保存場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-122">The settings are then saved back to the settings storage location when the application closes.</span></span> <span data-ttu-id="4e5cc-123">オペレーティングシステムの設定は、ユーザーがログオンしたとき、コンピューターのロックが解除されたとき、またはユーザーがリモートデスクトッププロトコル (RDP) を使ってリモートでコンピューターに接続したときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-123">The operating system settings are applied when the user logs on, when the computer is unlocked, or when the user connects remotely to the computer by using remote desktop protocol (RDP).</span></span> <span data-ttu-id="4e5cc-124">エージェントは、ユーザーがログオフしたとき、コンピューターがロックされているとき、またはリモート接続が切断されたときに設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-124">The agent saves settings when the user logs off, when the computer is locked, or when a remote connection is disconnected.</span></span> <span data-ttu-id="4e5cc-125">UE-V Agent の詳細については、「 [ue-v の環境の準備](preparing-your-environment-for-ue-v.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-125">For more information about the UE-V Agent, see [Preparing Your Environment for UE-V](preparing-your-environment-for-ue-v.md).</span></span>

## <a href="" id="bkmk-settingslocationtemplate"></a><span data-ttu-id="4e5cc-126">設定場所テンプレート</span><span class="sxs-lookup"><span data-stu-id="4e5cc-126">Settings location templates</span></span>


<span data-ttu-id="4e5cc-127">設定場所テンプレートは、ユーザーエクスペリエンスの仮想化によって監視される設定の場所を定義する XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-127">The settings location template is an XML file that defines the settings locations to be monitored by User Experience Virtualization.</span></span> <span data-ttu-id="4e5cc-128">これらの設定テンプレートで定義された設定の場所のみが、UE-V Agent を実行しているコンピューターでキャプチャまたは適用されます。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-128">Only the settings locations defined in these settings templates are captured or applied on computers running the UE-V Agent.</span></span> <span data-ttu-id="4e5cc-129">設定場所テンプレートには、コンピューター上の値が格納されている場所のみが設定されています。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-129">The settings location template does not contain settings values, only the locations where values are stored on the computer.</span></span>

<span data-ttu-id="4e5cc-130">UE-V には、一部の Microsoft アプリケーションや Windows 設定の設定の場所を指定する、設定の場所テンプレートのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-130">UE-V includes a set of settings location templates that specify settings locations for some Microsoft applications and Windows settings.</span></span> <span data-ttu-id="4e5cc-131">管理者は、UE-V Generator を使用して、カスタム設定の場所テンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-131">An administrator can create custom settings location templates by using the UE-V Generator.</span></span>

[<span data-ttu-id="4e5cc-132">UE-V 1.0 を使用して同期するアプリケーションの計画</span><span class="sxs-lookup"><span data-stu-id="4e5cc-132">Planning Which Applications to Synchronize with UE-V 1.0</span></span>](planning-which-applications-to-synchronize-with-ue-v-10.md)

[<span data-ttu-id="4e5cc-133">UE-V 1.0 のカスタム テンプレートの展開計画</span><span class="sxs-lookup"><span data-stu-id="4e5cc-133">Planning for Custom Template Deployment for UE-V 1.0</span></span>](planning-for-custom-template-deployment-for-ue-v-10.md)

[<span data-ttu-id="4e5cc-134">カスタム UE-V テンプレートと UE-V Generator の操作</span><span class="sxs-lookup"><span data-stu-id="4e5cc-134">Working with Custom UE-V Templates and the UE-V Generator</span></span>](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

## <span data-ttu-id="4e5cc-135">設定パッケージ</span><span class="sxs-lookup"><span data-stu-id="4e5cc-135">Settings packages</span></span>


<span data-ttu-id="4e5cc-136">アプリケーションの設定と Windows の設定は、UE-V Agent によって作成される設定パッケージに保存されます。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-136">Application settings and Windows settings are stored in settings packages, which are created by the UE-V Agent.</span></span> <span data-ttu-id="4e5cc-137">設定パッケージは、設定場所テンプレートで表示される設定のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-137">A settings package is a collection of the settings that are represented in the settings location templates.</span></span> <span data-ttu-id="4e5cc-138">これらの設定パッケージは、ローカルに保存され、設定の保存場所にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-138">These settings packages are built, locally stored, and then copied to the settings storage location.</span></span> <span data-ttu-id="4e5cc-139">"最終書き込み wins" は、1人のユーザーが複数のコンピューターをストレージの場所に同期したときに保持される設定を決定します。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-139">“Last write wins” determines which settings are preserved when a single user synchronizes the more than one computer to a storage location.</span></span> <span data-ttu-id="4e5cc-140">1台のコンピューターで実行されるエージェントは、他のコンピューターで実行されているエージェントとは無関係に、設定の場所の読み取りと書き込みを行います。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-140">The agent that runs on one computer reads and writes to the settings location independent of agents that run on other computers.</span></span> <span data-ttu-id="4e5cc-141">最後に書き込まれた設定と値は、次のエージェントが設定の保存場所から読み取りを行ったときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-141">The most recently written settings and values are applied when the next agent reads from the settings storage location.</span></span>

![ue-v generator プロセス](images/ue-vgeneratorprocess.gif)

## <span data-ttu-id="4e5cc-143">設定テンプレートカタログ</span><span class="sxs-lookup"><span data-stu-id="4e5cc-143">Settings template catalog</span></span>


<span data-ttu-id="4e5cc-144">設定テンプレートカタログは、UE-V のコンピューター上のフォルダーパス、またはカスタム設定の場所テンプレートをすべて保存するサーバーメッセージブロック (SMB) ネットワーク共有です。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-144">The settings template catalog is a folder path on UE-V computers or a Server Message Block (SMB) network share that stores all the custom settings location templates.</span></span> <span data-ttu-id="4e5cc-145">UE-V agent は、新しいまたは更新されたテンプレートをこの場所から取得します。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-145">The UE-V agent retrieves new or updated templates from this location.</span></span> <span data-ttu-id="4e5cc-146">UE-V agent は、毎日この場所をチェックし、このフォルダー内のテンプレートに基づいて同期動作を更新します。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-146">The UE-V agent checks this location once each day and it updates its synchronization behavior based on the templates in this folder.</span></span> <span data-ttu-id="4e5cc-147">前回のチェック以降、このフォルダーで追加または更新されたテンプレートは、UE-V エージェントによって登録されます。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-147">The templates that were added or updated in this folder since the last check are registered by the UE-V agent.</span></span> <span data-ttu-id="4e5cc-148">UE-V agent は、このフォルダーから削除されたテンプレートを deregisters します。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-148">The UE-V agent deregisters the templates that were removed from this folder.</span></span> <span data-ttu-id="4e5cc-149">テンプレートは、タスクスケジューラによって1日に登録および登録解除されます。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-149">Templates are registered and unregistered one time per day by the task scheduler.</span></span> <span data-ttu-id="4e5cc-150">UE-V に含まれている既定の設定場所テンプレートのみを使用する場合は、設定テンプレートカタログは不要です。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-150">If you will use only the default settings location templates that are included with UE-V, then a settings template catalog is unnecessary.</span></span> <span data-ttu-id="4e5cc-151">設定展開カタログの詳細については、「 [ue-v 1.0 向けのカスタムテンプレートの展開を計画](planning-for-custom-template-deployment-for-ue-v-10.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-151">For more information about settings deployment catalogs, see [Planning for Custom Template Deployment for UE-V 1.0](planning-for-custom-template-deployment-for-ue-v-10.md).</span></span>

## <span data-ttu-id="4e5cc-152">ユーザーエクスペリエンスの仮想化ジェネレーター</span><span class="sxs-lookup"><span data-stu-id="4e5cc-152">User Experience Virtualization Generator</span></span>


<span data-ttu-id="4e5cc-153">ユーザーエクスペリエンスの仮想化ジェネレーターを使用すると、エンタープライズで使用され、ローミング設定ソリューションに含めるアプリケーションの設定の場所を保存する、カスタム設定の場所テンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-153">The User Experience Virtualization Generator enables you to create custom settings location templates which will store the settings locations of the applications that are used in the enterprise and that you want to include in the roaming settings solution.</span></span> <span data-ttu-id="4e5cc-154">UE-V Generator は、レジストリ値の位置とアプリケーションの設定ファイルを検出し、その場所を設定場所テンプレートの XML ファイルに記録します。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-154">The UE-V Generator will seek to discover the locations of registry values and the settings files for applications and then it will record those locations in a settings location template XML file.</span></span> <span data-ttu-id="4e5cc-155">次に、これらの設定場所テンプレートをユーザーコンピューターに配布できます。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-155">You can then distribute these settings location templates to the user computers.</span></span> <span data-ttu-id="4e5cc-156">UE-V Generator を使用すると、管理者は、既存のテンプレートを編集したり、別の XML エディターで作成されたテンプレートを検証したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-156">The UE-V Generator also allows an administrator to edit an existing template or validate a template that was created with another XML editor.</span></span>

<span data-ttu-id="4e5cc-157">UE-V Generator は、アプリケーションを監視し、その設定が保存されている場所を記録します。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-157">The UE-V Generator monitors an application to discover and record where it stores its settings.</span></span> <span data-ttu-id="4e5cc-158">これを行うには、HKEY \ _CURRENT \ _USER registry、または**users**の下にあるファイルフォルダーの中で、アプリが読み取りまたは書き込みを行う場所を監視します。 \ \ [ユーザー名 \] **\ \ の**ユーザー名 \] \ | ユーザー  \\  **Roaming and Users**名 \] \ **appdata**  \\  **ローカル**。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-158">To do this, it monitors where the application reads or writes in the HKEY\_CURRENT\_USER registry or in the file folders under **Users** \\ \[User name\] \\ **AppData** \\ **Roaming and Users** \\ \[User name\] \\ **AppData** \\ **Local**.</span></span>

<span data-ttu-id="4e5cc-159">検出プロセスでは、ログインしたユーザーが値を書き込むことができないレジストリキーとファイルは除外されます。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-159">The discovery process excludes registry keys and files to which the logged-in user cannot write values.</span></span> <span data-ttu-id="4e5cc-160">これらは、XML ファイルには含まれません。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-160">None of these will be included in the XML file.</span></span> <span data-ttu-id="4e5cc-161">また、検出プロセスでは、Windows オペレーティングシステムのコア機能に関連付けられたレジストリキーとファイルは除外されます。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-161">The discovery process also excludes registry keys and files that are associated with the core functionality of the Windows operating system.</span></span>

<span data-ttu-id="4e5cc-162">UE-V Generator の詳細については、「 [Ue-v generator のインストール](installing-the-ue-v-generator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e5cc-162">For more information about the UE-V Generator, see [Installing the UE-V Generator](installing-the-ue-v-generator.md).</span></span>

## <span data-ttu-id="4e5cc-163">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4e5cc-163">Related topics</span></span>


[<span data-ttu-id="4e5cc-164">Microsoft User Experience Virtualization (UE-V) 1.0</span><span class="sxs-lookup"><span data-stu-id="4e5cc-164">Microsoft User Experience Virtualization (UE-V) 1.0</span></span>](index.md)

[<span data-ttu-id="4e5cc-165">User Experience Virtualization 1.0 の概要</span><span class="sxs-lookup"><span data-stu-id="4e5cc-165">Getting Started With User Experience Virtualization 1.0</span></span>](getting-started-with-user-experience-virtualization-10.md)

[<span data-ttu-id="4e5cc-166">User Experience Virtualization 1.0 について</span><span class="sxs-lookup"><span data-stu-id="4e5cc-166">About User Experience Virtualization 1.0</span></span>](about-user-experience-virtualization-10.md)

[<span data-ttu-id="4e5cc-167">カスタム UE-V テンプレートと UE-V Generator の操作</span><span class="sxs-lookup"><span data-stu-id="4e5cc-167">Working with Custom UE-V Templates and the UE-V Generator</span></span>](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

 

 





