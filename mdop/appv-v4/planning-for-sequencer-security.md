---
title: Sequencer のセキュリティの計画
description: Sequencer のセキュリティの計画
author: dansimp
ms.assetid: 8043cb02-476d-4c28-a850-903a8ac5b2d3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bf1e85e24d93d373add38b5efe51ceb40faae24e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815914"
---
# <span data-ttu-id="418c8-103">Sequencer のセキュリティの計画</span><span class="sxs-lookup"><span data-stu-id="418c8-103">Planning for Sequencer Security</span></span>


<span data-ttu-id="418c8-104">Sequencer の実装が機能し、セキュリティが強化されるように、アプリケーションの仮想化 (App-v) を構成するときに、できるだけ早い段階で実装の推奨事項を組み込みます。</span><span class="sxs-lookup"><span data-stu-id="418c8-104">Incorporate recommended implementation practices as early as possible when configuring Application Virtualization (App-V) so that your Sequencer implementation is functional and more secure.</span></span> <span data-ttu-id="418c8-105">Sequencer を既に構成している場合は、次のベストプラクティスガイドラインを使用して、設計上の決定に再検討し、セキュリティの観点から分析します。</span><span class="sxs-lookup"><span data-stu-id="418c8-105">If you have already configured the Sequencer, use the following best-practice guidelines to revisit your design decisions and analyze them from a security perspective.</span></span>

**<span data-ttu-id="418c8-106">重要</span><span class="sxs-lookup"><span data-stu-id="418c8-106">Important</span></span>**  
<span data-ttu-id="418c8-107">App-v は、Sequencer を実行しているコンピューター上に記録されているすべてのアプリケーション情報を収集し、展開します。</span><span class="sxs-lookup"><span data-stu-id="418c8-107">The App-V Sequencer collects and deploys all application information recorded on the computer running the sequencer.</span></span> <span data-ttu-id="418c8-108">Sequencer を実行しているコンピューターにアクセスするすべてのユーザーが管理者資格情報を持っていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="418c8-108">You should ensure that all users accessing the computer running the Sequencer have administrative credentials.</span></span> <span data-ttu-id="418c8-109">ユーザーアカウントの資格情報を持つユーザーは、[パッケージコンテンツとパッケージファイルの制御] にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="418c8-109">Users with user account credentials should not have access to control package contents and package files.</span></span> <span data-ttu-id="418c8-110">リモートデスクトップサービス (以前のターミナルサービス) を実行しているコンピューターで優先順位を設定する場合は、そのコンピューターが順序付け専用であり、ユーザーアカウントの資格情報を持っているユーザーがシーケンス中にそれに接続していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="418c8-110">If you are sequencing on a computer running Remote Desktop Services (formerly Terminal Services), make sure it is a computer that is dedicated to sequencing and that users with user account credentials are not connected to it during sequencing.</span></span>



## <span data-ttu-id="418c8-111">Sequencer セキュリティのベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="418c8-111">Sequencer Security Best Practices</span></span>


<span data-ttu-id="418c8-112">Application Virtualization (App-v) Sequencer を実装して使用する場合は、次のシナリオと、関連するベストプラクティスを検討してください。</span><span class="sxs-lookup"><span data-stu-id="418c8-112">Consider the following scenarios and the associated best practices when implementing and using the Application Virtualization (App-V) Sequencer:</span></span>

-   <span data-ttu-id="418c8-113">**Sequencer を実行しているコンピューターでウイルススキャン**を実行することをお勧めします。 sequencer を実行しているコンピューターでウイルスをスキャンし、シーケンス処理中に sequencer を実行しているコンピューターでウイルス対策ソフトウェアとマルウェア検出ソフトウェアをすべて無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="418c8-113">**Virus scanning on the computer running the Sequencer**—It is recommended that you scan the computer running the Sequencer for viruses and then disable all antivirus and malware detection software on the computer running the Sequencer during the sequencing process.</span></span> <span data-ttu-id="418c8-114">これにより、シーケンス処理が高速化され、ウイルス対策ソフトウェアやマルウェア対策ソフトウェアコンポーネントがシーケンス処理に影響を及ぼすことを防止できます。</span><span class="sxs-lookup"><span data-stu-id="418c8-114">This will speed the sequencing process and prevent the antivirus and anti-malware software components from interfering with the sequencing process.</span></span> <span data-ttu-id="418c8-115">次に、Sequencer が実行されていないコンピューターにシーケンスパッケージをインストールし、インストールが正常に完了したら、そのコンピューターでウイルスをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="418c8-115">Next install the sequenced package on a computer not running the Sequencer, and after successful installation, scan that computer for viruses.</span></span> <span data-ttu-id="418c8-116">ウイルスが検出された場合、ウイルスに感染したソースファイルを通知し、更新されたインストールソースをウイルスなしで要求するには、ソフトウェアの製造元に連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="418c8-116">If viruses are found, the manufacturer of the software should be contacted to inform them of the infected source files and request an updated installation source without viruses.</span></span> <span data-ttu-id="418c8-117">必要に応じて、インストールフェーズの終了後に Sequencer をスキャンすることができ、ウイルスが検出された場合は、上記のようにソフトウェアの製造元に連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="418c8-117">Optionally, the Sequencer could be scanned after the installation phase and if a virus is found, the software manufacturer should be contacted as mentioned above.</span></span>

    **<span data-ttu-id="418c8-118">注</span><span class="sxs-lookup"><span data-stu-id="418c8-118">Note</span></span>**  
    <span data-ttu-id="418c8-119">アプリケーションでウイルスが検出された場合、アプリケーションはターゲットコンピューターに展開しないでください。</span><span class="sxs-lookup"><span data-stu-id="418c8-119">If a virus is detected in an application, the application should not be deployed to target computers.</span></span>



-   <span data-ttu-id="418c8-120">**Ntfs ファイルでアクセス制御リスト (acl) をキャプチャ**すると、アプリのインストール中に監視されるファイルに対して、ntfs ファイルシステムのアクセス許可がキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="418c8-120">**Capturing access control lists (ACLs) on NTFS files**—The App-V Sequencer captures NTFS file system permissions for the files that are monitored during the installation of the product.</span></span> <span data-ttu-id="418c8-121">この機能により、ローカルにインストールされ、仮想化されていない場合と同様に、アプリケーションの意図した動作をより正確にレプリケートできます。</span><span class="sxs-lookup"><span data-stu-id="418c8-121">This capability allows you to more accurately replicate the intended behavior of the application, as if it were installed locally and not virtualized.</span></span> <span data-ttu-id="418c8-122">一部のシナリオでは、アプリケーションファイル内でアクセスしないようにユーザーが意図した情報を格納する場合があります。</span><span class="sxs-lookup"><span data-stu-id="418c8-122">In some scenarios, an application might store information that users were not intended to access within the application files.</span></span> <span data-ttu-id="418c8-123">たとえば、アプリケーション内のファイルに資格情報情報を格納することができます。</span><span class="sxs-lookup"><span data-stu-id="418c8-123">For example, an application could store credentials information in a file inside of the application.</span></span> <span data-ttu-id="418c8-124">パッケージに Acl が適用されていない場合、ユーザーがアプリの外部でこの情報を表示して使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="418c8-124">If ACLs are not enforced on the package, a user could potentially view and then use this information outside of the application.</span></span>

    **<span data-ttu-id="418c8-125">注</span><span class="sxs-lookup"><span data-stu-id="418c8-125">Note</span></span>**  
    <span data-ttu-id="418c8-126">パスワードなど、暗号化されていないセキュリティ固有の情報を格納するアプリケーションを順序指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="418c8-126">You should not sequence applications that store unencrypted security-specific information, such as passwords, and so on.</span></span>



~~~
During the installation phase, you can modify the default permissions of the files if necessary. After completion of the sequencing process, but before saving the package, you can choose whether to enforce security descriptors that were captured during the installation of the application. By default, App-V will enforce the security descriptors specified during the installation of the application. If you turn off security descriptor enforcement, you should test the application to ensure the removal of associated Access Control Lists (ACL) will not cause the application to perform unexpectedly.
~~~

-   <span data-ttu-id="418c8-127">**Sequencer はレジストリ acl をキャプチャしません**。シーケンサーは、シーケンスのインストールフェーズ中に NTFS ファイルシステム acl をキャプチャしますが、レジストリの acl をキャプチャするわけではありません。</span><span class="sxs-lookup"><span data-stu-id="418c8-127">**Sequencer doesn’t capture registry ACLs**—Although the Sequencer captures the NTFS file system ACLs during the installation phase of sequencing, it does not capture the ACLs for the registry.</span></span> <span data-ttu-id="418c8-128">ユーザーは、サービスを除き、仮想アプリケーションのすべてのレジストリキーにフルアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="418c8-128">Users will have full access to all registry keys for virtual applications except for services.</span></span> <span data-ttu-id="418c8-129">ただし、ユーザーが仮想アプリケーションのレジストリを変更すると、その変更は特定のストア (**uservol \ _sftfs \ _v1**) に保存され、他のユーザーには影響しません。</span><span class="sxs-lookup"><span data-stu-id="418c8-129">However, if a user modifies the registry of a virtual application, the change will be stored in a specific store (**uservol\_sftfs\_v1.pkg**) and will not affect other users.</span></span>

-   <span data-ttu-id="418c8-130">**アプリケーションサービス**-app-v は、仮想化されたアプリケーションの一部であるアプリケーションサービスのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="418c8-130">**Application services**—App-V provides support for application services that are part of a virtualized application.</span></span> <span data-ttu-id="418c8-131">ただし、仮想環境では、ユーザーが実行するセキュリティコンテキストは制限されています。</span><span class="sxs-lookup"><span data-stu-id="418c8-131">However, in the virtual environment, the security context that they will run as is limited.</span></span> <span data-ttu-id="418c8-132">仮想環境でサポートされるセキュリティコンテキストは、ローカルシステム、ローカルサービス、およびネットワークサービスだけです。</span><span class="sxs-lookup"><span data-stu-id="418c8-132">The only security contexts supported in a virtual environment are Local System, Local Service, and Network Service.</span></span> <span data-ttu-id="418c8-133">シーケンス中に、サポートされている3つ以外のアプリケーションサービスに対してセキュリティコンテキストが指定されている場合、ローカルシステムのセキュリティコンテキストが仮想環境に適用されます。</span><span class="sxs-lookup"><span data-stu-id="418c8-133">During sequencing, if a security context is specified for an application service other than the three supported, the Local System security context will be applied in the virtual environment.</span></span> <span data-ttu-id="418c8-134">アプリケーションサービスがローカルサービスまたはネットワークサービスのいずれかを使用するように構成されている場合は、仮想環境で受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="418c8-134">If the application service is configured to use either Local Service or Network Service, it will be honored in the virtual environment.</span></span> <span data-ttu-id="418c8-135">サービスアカウントの構成は、次の3つのセキュリティコンテキストを使用したシーケンス処理中に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="418c8-135">Configuring the service account can be done during the sequencing process using these three security contexts.</span></span>

-   <span data-ttu-id="418c8-136">保存された**セキュリティ情報**: アプリケーションをシーケンス処理するときに、ユーザーとしてアプリケーションをインストールすることができます。また、監視中にアプリケーションをインストールするための自動メソッドを開発することもできます。</span><span class="sxs-lookup"><span data-stu-id="418c8-136">**Persisted security information**—When sequencing applications, you can install the application as a user would or you can develop an automated method for installing the application while being monitored.</span></span> <span data-ttu-id="418c8-137">パッケージから除外されていないものはすべて、そのパッケージの一部としてキャプチャされるため、仮想化された環境で実行するために必要なアセットがアプリケーションに含まれます。</span><span class="sxs-lookup"><span data-stu-id="418c8-137">Everything that is not being excluded from the package will be captured as part of that package so that the application will have the necessary assets to run in a virtualized environment.</span></span> <span data-ttu-id="418c8-138">一部のアプリケーションでは、インストール時に機密性の高いセキュリティ情報 (パスワードなど) が保存されます。保護されていない場合、このセキュリティ情報には、パッケージへのアクセス権を持つ他のユーザーがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="418c8-138">Some applications store sensitive security information (such as passwords) during the installation; if persisted unprotected, this security information could be accessed by other users with access to the package.</span></span> <span data-ttu-id="418c8-139">インストール時に、アプリケーションのインストールでパスワードまたはその他のセキュリティに関する情報を要求された場合は、そのドキュメントを確認して、保存されていない (インストール後に削除される) か、または保護されている (暗号化されている) かを確認します。</span><span class="sxs-lookup"><span data-stu-id="418c8-139">During installation, if an application installation asks for a password or other security-sensitive information, check with the documentation to ensure that it is either not persisted (removed after installation) or, if persisted, that it is protected (encrypted).</span></span>

-   <span data-ttu-id="418c8-140">**仮想アプリケーションパッケージのセキュリティ保護**: 仮想アプリケーションパッケージは、常にネットワーク上のセキュリティで保護された場所に保存され、パッケージが改ざんまたは破損されないように保護します。</span><span class="sxs-lookup"><span data-stu-id="418c8-140">**Securing virtual application packages**—Always save virtual application packages in a secure location on the network to protect the package from being tampered with or corrupted.</span></span>

## <span data-ttu-id="418c8-141">関連トピック</span><span class="sxs-lookup"><span data-stu-id="418c8-141">Related topics</span></span>


[<span data-ttu-id="418c8-142">セキュリティと保護の計画</span><span class="sxs-lookup"><span data-stu-id="418c8-142">Planning for Security and Protection</span></span>](planning-for-security-and-protection.md)









