---
title: App-V Desktop Client のセキュリティ
description: App-V Desktop Client のセキュリティ
author: dansimp
ms.assetid: 216b9c16-7bb4-4f94-b9d8-810501285008
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 26add6f855780113613cf1591c41722643954477
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822317"
---
# <span data-ttu-id="45efa-103">App-V Desktop Client のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="45efa-103">App-V Desktop Client Security</span></span>


<span data-ttu-id="45efa-104">App-v デスクトップクライアントには、以前のバージョンの製品では使用できなかったさまざまなセキュリティ機能強化が用意されています。</span><span class="sxs-lookup"><span data-stu-id="45efa-104">The App-V Desktop Client provides many security enhancements that were not available in previous versions of the product.</span></span> <span data-ttu-id="45efa-105">これらの変更により、既定ではより高いレベルのセキュリティが提供され、クライアント設定の構成が行われます。</span><span class="sxs-lookup"><span data-stu-id="45efa-105">These changes provide higher levels of security by default and through configuration of the client settings.</span></span>

<span data-ttu-id="45efa-106">**注** コンピューターに app-v デスクトップクライアントをインストールすると、ソフトウェアは既定で最も安全な設定になります。</span><span class="sxs-lookup"><span data-stu-id="45efa-106">**Note** When you install the App-V Desktop Client on a computer, the software defaults to the most secure settings.</span></span> <span data-ttu-id="45efa-107">ただし、アップグレードする場合、クライアントの以前の設定は保持されます。</span><span class="sxs-lookup"><span data-stu-id="45efa-107">However, when upgrading, the previous settings of the client persist.</span></span>

 

<span data-ttu-id="45efa-108">既定では、App-v デスクトップクライアントは、管理者以外のユーザーが公開の更新およびストリームアプリケーションを実行できるようにするために必要なアクセス許可のみを構成します。</span><span class="sxs-lookup"><span data-stu-id="45efa-108">By default, the App-V Desktop Client is configured only with the permissions required to allow a non-administrative user to perform a publishing refresh and stream applications.</span></span> <span data-ttu-id="45efa-109">App-v デスクトップクライアントには、次のような追加のセキュリティ強化機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="45efa-109">Additional security enhancements provided in the App-V Desktop Client include the following:</span></span>

-   <span data-ttu-id="45efa-110">既定では、OSD キャッシュ更新は発行の更新プロセスによってのみ許可されています。</span><span class="sxs-lookup"><span data-stu-id="45efa-110">By default, an OSD cache update is allowed only by the publishing refresh process.</span></span>

-   <span data-ttu-id="45efa-111">ログファイル ( `sftlog.txt` ) は、クライアントへのローカル管理アクセス権を持つアカウントによってのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="45efa-111">The log file (`sftlog.txt`) is accessible only by accounts with local administrative access to the client.</span></span>

-   <span data-ttu-id="45efa-112">ログファイルに最大サイズが設定されました。</span><span class="sxs-lookup"><span data-stu-id="45efa-112">The log file now has a maximum size.</span></span>

-   <span data-ttu-id="45efa-113">ログファイルは、アーカイブ設定によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="45efa-113">The log files are managed through archive settings.</span></span>

-   <span data-ttu-id="45efa-114">システムイベントログが実行されました。</span><span class="sxs-lookup"><span data-stu-id="45efa-114">System Event logging is now performed.</span></span>

## <span data-ttu-id="45efa-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="45efa-115">Permissions</span></span>


<span data-ttu-id="45efa-116">デスクトップクライアントをインストールした後は、Microsoft が提供するレジストリまたは ADM テンプレートを使用して、MMC または個々のクライアントを通じて、他のセキュリティ設定を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="45efa-116">After you install the Desktop Client, you can configure other security settings through the MMC, or on an individual client by using the registry or the ADM Template provided by Microsoft.</span></span> <span data-ttu-id="45efa-117">App-v デスクトップクライアントには、管理者以外のユーザーがデスクトップクライアントのすべての機能にアクセスすることを制限するように設定できる権限があります。</span><span class="sxs-lookup"><span data-stu-id="45efa-117">The App-V Desktop Client has permissions that you can set to restrict non-administrative users from accessing all the features of the Desktop Client.</span></span> <span data-ttu-id="45efa-118">権限の完全な一覧については、「App-v Client ヘルプファイルまたは app-v の操作ガイド」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45efa-118">For a full list of permissions, please see the App-V Client Help file or App-V Operations Guide.</span></span>

<span data-ttu-id="45efa-119">**重要** 特に、複数のユーザーによって共有されている (ターミナルサーバーなどの) システムで、アクセス権を変更した場合の影響を慎重に検討してください。</span><span class="sxs-lookup"><span data-stu-id="45efa-119">**Important** Carefully consider the consequences of changing access rights, especially on systems that are shared by multiple users, such as Terminal Servers.</span></span>

 

<span data-ttu-id="45efa-120">**注** 環境内のユーザーがコンピューターのローカル管理者権限を持っている場合、アクセス許可は無視されます。</span><span class="sxs-lookup"><span data-stu-id="45efa-120">**Note** If users in the environment have local administrator privileges for their computers, the permissions are ignored.</span></span>

 

### <span data-ttu-id="45efa-121">ADM テンプレート</span><span class="sxs-lookup"><span data-stu-id="45efa-121">ADM Template</span></span>

<span data-ttu-id="45efa-122">Microsoft Application Virtualization (App-v) では、グループポリシーによって最も一般的なクライアントの設定を構成するために使用できる ADM テンプレートが導入されています。</span><span class="sxs-lookup"><span data-stu-id="45efa-122">Microsoft Application Virtualization (App-V) introduces an ADM Template that you can use to configure the most common client settings through Group Policies.</span></span> <span data-ttu-id="45efa-123">このテンプレートを使用すると、管理者は一元管理モデルを使用して、多くのクライアント設定を実装して変更することができます。</span><span class="sxs-lookup"><span data-stu-id="45efa-123">This template enables administrators to implement and change many of the client settings through a centralized administration model.</span></span> <span data-ttu-id="45efa-124">ADM テンプレートで利用できる設定の一部は、[セキュリティ設定] です。</span><span class="sxs-lookup"><span data-stu-id="45efa-124">Some of the settings available in the ADM Template are security settings.</span></span>

<span data-ttu-id="45efa-125">**重要** ADM テンプレートを使用する場合は、設定がグループポリシーの基本設定であり、完全に管理されたグループポリシーではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="45efa-125">**Important** When using the ADM Template, remember that the settings are Group Policy preference settings and not fully managed Group Policies.</span></span>

 

<span data-ttu-id="45efa-126">使用している環境にクライアントを正常に展開するための ADM テンプレート、具体的な設定、およびガイダンスの詳細については、「App-v ADM テンプレートのホワイトペーパー」を参照してください [https://go.microsoft.com/fwlink/LinkId=122063](https://go.microsoft.com/fwlink/?LinkId=122063) 。</span><span class="sxs-lookup"><span data-stu-id="45efa-126">For a full description of the ADM Template, the specific settings, and guidance to successfully deploy clients in your environment, see the App-V ADM Template white paper at [https://go.microsoft.com/fwlink/LinkId=122063](https://go.microsoft.com/fwlink/?LinkId=122063).</span></span>

## <span data-ttu-id="45efa-127">OSD ファイルの種類の関連付けの削除</span><span class="sxs-lookup"><span data-stu-id="45efa-127">Removing OSD File Type Associations</span></span>


<span data-ttu-id="45efa-128">組織でユーザーが OSD ファイルから直接アプリケーションを開く必要がない場合は、クライアント上のファイルの種類の関連付けを削除することで、セキュリティを強化できます。</span><span class="sxs-lookup"><span data-stu-id="45efa-128">If your organization does not require users to open applications directly from an OSD file, you can enhance security by removing the file type associations on the client.</span></span> <span data-ttu-id="45efa-129">`HKEY_CURRENT_USERS`OSD のキーと `Softgird.osd.file` レジストリエディターを使用して、キーを削除します。</span><span class="sxs-lookup"><span data-stu-id="45efa-129">Remove the `HKEY_CURRENT_USERS` keys for OSD and `Softgird.osd.file` by using the registry editor.</span></span> <span data-ttu-id="45efa-130">このプロセスをログオンスクリプトまたはインストール後のスクリプトに追加して、これらの変更を自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="45efa-130">You can put this process into a logon script or into a post-installation script to automate these changes.</span></span>

 

 





