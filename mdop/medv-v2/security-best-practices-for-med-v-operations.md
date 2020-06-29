---
title: MED-V 操作のセキュリティのベスト プラクティス
description: MED-V 操作のセキュリティのベスト プラクティス
author: dansimp
ms.assetid: 231e2b9a-8b49-42fe-93b5-2ef12fe17bac
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4353a15c756dba8cf44f530c2077546e3f9288cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825397"
---
# <span data-ttu-id="59f6c-103">MED-V 操作のセキュリティのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="59f6c-103">Security Best Practices for MED-V Operations</span></span>


<span data-ttu-id="59f6c-104">承認された管理者は、ユーザーの情報を保護し、MED-V ワークスペースの展開中および組織のセキュリティを維持する責任を負います。</span><span class="sxs-lookup"><span data-stu-id="59f6c-104">As an authorized administrator, you are responsible to protect the information of the users and maintain security of your organization during and after the deployment of MED-V workspaces.</span></span> <span data-ttu-id="59f6c-105">特に、次の問題を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="59f6c-105">In particular, consider the following issues.</span></span>

<span data-ttu-id="59f6c-106">**Med-v ワークスペースで Internet Explorer をカスタマイズ**します。</span><span class="sxs-lookup"><span data-stu-id="59f6c-106">**Customizing Internet Explorer in the MED-V workspace**.</span></span> <span data-ttu-id="59f6c-107">以前のバージョンの Windows オペレーティングシステムと Internet Explorer のバージョンは、現在のバージョンとしてはセキュリティで保護されていません。</span><span class="sxs-lookup"><span data-stu-id="59f6c-107">Earlier versions of the Windows operating system and of Internet Explorer are not as secure as current versions.</span></span> <span data-ttu-id="59f6c-108">そのため、MED-V ワークスペースの Internet Explorer は、閲覧や、セキュリティリスクを引き起こす可能性のあるその他のアクティビティを防ぐように構成されています。</span><span class="sxs-lookup"><span data-stu-id="59f6c-108">Therefore, Internet Explorer in the MED-V workspace is configured to prevent browsing and other activities that can pose security risks.</span></span> <span data-ttu-id="59f6c-109">さらに、MED-V ワークスペースの Internet Explorer のインターネットセキュリティゾーン設定は、最上位レベルに設定されています。</span><span class="sxs-lookup"><span data-stu-id="59f6c-109">In addition, the Internet security zone setting for Internet Explorer in the MED-V workspace is set to the highest level.</span></span> <span data-ttu-id="59f6c-110">既定では、MED-V ワークスペースパッケージを作成するときに、これらの構成は両方とも、MED-V Workspace パッケージャーで設定されます。</span><span class="sxs-lookup"><span data-stu-id="59f6c-110">By default, both of these configurations are set in the MED-V Workspace Packager when you create your MED-V workspace package.</span></span>

<span data-ttu-id="59f6c-111">Internet Explorer 管理キット (IEAK) を使用するか、MED-V ワークスペースパッケージャーで既定値を変更することで、MED-V ワークスペースで Internet Explorer をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="59f6c-111">By using Internet Explorer Administration Kit (IEAK) or by changing the defaults in the MED-V Workspace Packager, you can customize Internet Explorer in the MED-V workspace.</span></span> <span data-ttu-id="59f6c-112">ただし、安全を確保するために、MED-V ワークスペースで Internet Explorer をカスタマイズすると、Internet Explorer の以前のバージョンに存在するセキュリティ上のリスクに組織を公開できます。</span><span class="sxs-lookup"><span data-stu-id="59f6c-112">However, realize that if you customize Internet Explorer in the MED-V workspace in such a way as to make it less secure, you can expose your organization to those security risks that are present in older versions of Internet Explorer.</span></span>

<span data-ttu-id="59f6c-113">セキュリティの観点から、MED-V ワークスペースの Internet Explorer を管理するためのベストプラクティスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="59f6c-113">From a security perspective, best practices for managing Internet Explorer in the MED-V workspace are as follows:</span></span>

-   <span data-ttu-id="59f6c-114">MED-V ワークスペースパッケージを作成する場合は、既定の設定のままにして、MED-V ワークスペースの Internet Explorer が、閲覧や、セキュリティリスクを引き起こす可能性のあるその他のアクティビティを防ぐように構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="59f6c-114">When creating your MED-V workspace package, leave the defaults set so that Internet Explorer in the MED-V workspace is configured to prevent browsing and other activities that can pose security risks.</span></span>

-   <span data-ttu-id="59f6c-115">MED-V ワークスペースパッケージを作成する場合は、既定の設定のままにして、インターネットセキュリティゾーンのセキュリティ設定が最上位レベルのままになるようにします。</span><span class="sxs-lookup"><span data-stu-id="59f6c-115">When creating your MED-V workspace package, leave the defaults set so that the security setting for the Internet security zone remains at the highest level.</span></span>

-   <span data-ttu-id="59f6c-116">会社のイントラネット以外のドメインをブロックするようにエンタープライズプロキシまたは Internet Explorer コンテンツアドバイザーを構成します。</span><span class="sxs-lookup"><span data-stu-id="59f6c-116">Configure your enterprise proxy or Internet Explorer Content Advisor to block domains that are outside your company’s intranet.</span></span>

**<span data-ttu-id="59f6c-117">共有コンピューター上のすべてのユーザーに対して、MED-V ワークスペースを構成する。</span><span class="sxs-lookup"><span data-stu-id="59f6c-117">Configuring a MED-V workspace for all users on a shared computer.</span></span>** <span data-ttu-id="59f6c-118">共有コンピューター上のすべてのユーザーがアクセスできるように MED-V ワークスペースを構成する場合、そのシステム上のすべてのユーザーに対して読み取りと書き込みのアクセス許可を与える場所にゲスト仮想マシン (VHD) が配置されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="59f6c-118">When configuring a MED-V workspace so that it can be accessed by all users on a shared computer, realize that the guest virtual machine (VHD) is put in a location that gives Read and Write access to all users on that system.</span></span>

**<span data-ttu-id="59f6c-119">ドメインに参加するためのプロキシアカウントを構成する。</span><span class="sxs-lookup"><span data-stu-id="59f6c-119">Configuring a proxy account for domain joining.</span></span>** <span data-ttu-id="59f6c-120">仮想マシンをドメインに参加させるためのプロキシアカウントを構成する場合、エンドユーザーがプロキシアカウントの資格情報を取得できることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59f6c-120">When configuring a proxy account for joining virtual machines to the domain, you must know that it is possible for an end user to obtain the proxy account credentials.</span></span> <span data-ttu-id="59f6c-121">そのため、アカウントのユーザー権限の制限など、必要な予防措置を講じて、エンドユーザーが問題の原因となる資格情報を使用しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="59f6c-121">Thus, necessary precautions must be taken, such as limiting account user rights, to prevent an end user from using the credentials for causing harm.</span></span>

**<span data-ttu-id="59f6c-122">Sysprep 構成。</span><span class="sxs-lookup"><span data-stu-id="59f6c-122">Sysprep Configuration.</span></span>** <span data-ttu-id="59f6c-123">Sysprep.inf ファイルは既定で暗号化されていますが、仮想マシンに正常にログオンできる特定のエンドユーザーによって、コンテンツの暗号化を解除して読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="59f6c-123">Although the Sysprep.inf file is encrypted by default, its contents can be decrypted and read by any determined end user who can successfully log on to the virtual machine.</span></span> <span data-ttu-id="59f6c-124">この方法では、Windows のプロダクトキーに加えて、Sysprep.inf ファイルに資格情報が含まれている場合があるため、セキュリティの問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="59f6c-124">This raises security concerns because the Sysprep.inf file can contain credentials in addition to a Windows product key.</span></span>

<span data-ttu-id="59f6c-125">このリスクを軽減するには、仮想マシンをドメインに参加させるための制限付きアカウントを設定し、Sysprep を構成するときにそのアカウントの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="59f6c-125">You can lessen this risk by setting up a limited account for joining virtual machines to the domain and specifying the credentials for that account when configuring Sysprep.</span></span> <span data-ttu-id="59f6c-126">または、Sysprep と first time のセットアップを**有人**モードで実行するように構成することもできます。また、仮想マシンをドメインに参加させるための資格情報をエンドユーザーに提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59f6c-126">Alternately, you can also configure Sysprep and first time setup to run in **Attended** mode and require end users to provide their credentials for joining the virtual machine to the domain.</span></span>

<span data-ttu-id="59f6c-127">MED-V のベストプラクティスは、リモートデスクトップ接続 (RDC) クライアントを介してゲストに接続するためのエンドユーザー権限を付与するアカウントで FtsCompletion.exe が実行されるように指定することです。</span><span class="sxs-lookup"><span data-stu-id="59f6c-127">A MED-V best practice is to specify that FtsCompletion.exe is run under an account that gives the end user rights to connect to the guest through the Remote Desktop Connection (RDC) Client.</span></span>

**<span data-ttu-id="59f6c-128">エンドユーザー認証。</span><span class="sxs-lookup"><span data-stu-id="59f6c-128">End-user authentication.</span></span>** <span data-ttu-id="59f6c-129">エンドユーザー資格情報のキャッシュを有効にすると、MED-V の最適なユーザーエクスペリエンスが提供されますが、だれかがエンドユーザーの資格情報にアクセスできる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="59f6c-129">Enabling the caching of end-user credentials provides the best user experience of MED-V, but creates the potential that someone could gain access to the end user’s credentials.</span></span> <span data-ttu-id="59f6c-130">このリスクを軽減する唯一の方法は、 **Med-v ワークスペースのパッケージャー**で、エンドユーザーの資格情報が保存されないように指定することです。</span><span class="sxs-lookup"><span data-stu-id="59f6c-130">The only way to lessen this risk is by specifying on the **MED-V Workspace Packager** that end-user credentials are not stored.</span></span> <span data-ttu-id="59f6c-131">エンドユーザーの認証の詳細については、「 [med-v のエンドユーザーの認証](authentication-of-med-v-end-users.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59f6c-131">For more information about authentication of end users, see [Authentication of MED-V End Users](authentication-of-med-v-end-users.md).</span></span>

## <span data-ttu-id="59f6c-132">関連トピック</span><span class="sxs-lookup"><span data-stu-id="59f6c-132">Related topics</span></span>


[<span data-ttu-id="59f6c-133">操作のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="59f6c-133">Operations Troubleshooting</span></span>](operations-troubleshooting-medv2.md)

[<span data-ttu-id="59f6c-134">Microsoft Enterprise デスクトップ仮想化2.0</span><span class="sxs-lookup"><span data-stu-id="59f6c-134">Microsoft Enterprise Desktop Virtualization 2.0</span></span>](index.md)

 

 





