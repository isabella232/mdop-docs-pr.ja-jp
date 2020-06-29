---
title: アプリケーション ライセンスについて
description: アプリケーション ライセンスについて
author: dansimp
ms.assetid: 6b487641-1627-4e91-b829-04f001008176
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 546bc630b95fe52f960c7bdfb771d3e2561f9318
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820097"
---
# <span data-ttu-id="346d8-103">アプリケーション ライセンスについて</span><span class="sxs-lookup"><span data-stu-id="346d8-103">About Application Licensing</span></span>


<span data-ttu-id="346d8-104">Application Virtualization Server 管理コンソールから直接アプリケーションライセンスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="346d8-104">You can manage application licenses directly from the Application Virtualization Server Management Console.</span></span>

## <span data-ttu-id="346d8-105">ライセンスの種類</span><span class="sxs-lookup"><span data-stu-id="346d8-105">License Types</span></span>


<span data-ttu-id="346d8-106">System Center Application Virtualization システムでは、現在、次のライセンスの種類がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="346d8-106">The System Center Application Virtualization System currently supports the following license types:</span></span>

-   <span data-ttu-id="346d8-107">**無制限ライセンス**: 任意の数の同時ユーザーによるアプリケーションへのアクセスを可能にします。</span><span class="sxs-lookup"><span data-stu-id="346d8-107">**Unlimited License**—Allows access to the application by any number of simultaneous users.</span></span> <span data-ttu-id="346d8-108">このライセンスの方法は、企業全体のライセンスをアプリケーションに関連付ける場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="346d8-108">This method of licensing is appropriate when you want to associate an enterprise-wide license with an application.</span></span>

-   <span data-ttu-id="346d8-109">**同時ライセンス**: アプリケーションの使用を許可する同時ユーザーの最大数を定義できます。</span><span class="sxs-lookup"><span data-stu-id="346d8-109">**Concurrent License**—Enables you to define the maximum number of concurrent users who are allowed to use the application.</span></span>

-   <span data-ttu-id="346d8-110">**"名前付きライセンス"**: 個々のユーザーにライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="346d8-110">**Named License**—Enables you to assign a license to an individual user.</span></span> <span data-ttu-id="346d8-111">名前付きライセンスを使用して、特定のユーザーが常にアプリケーションを実行できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="346d8-111">A named license can be used to ensure that a particular user will always be able to run the application.</span></span>

<span data-ttu-id="346d8-112">同じアプリケーションの同時ライセンスと名前付きライセンスを組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="346d8-112">You can combine concurrent and named licenses for the same application.</span></span>

<span data-ttu-id="346d8-113">ライセンスは既定では無効になっていますが、[**プロバイダーのプロパティ**] ダイアログの [**プロバイダーパイプライン**] タブから有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="346d8-113">Licensing is disabled by default, but you can enable it from the **Provider Pipeline** tab of the **Provider Properties** dialog.</span></span> <span data-ttu-id="346d8-114">ライセンスの有効化と無効化の詳細については、「[アプリケーションのライセンスを設定または無効にする方法](how-to-set-up-or-disable-application-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="346d8-114">For details about enabling and disabling licensing, see [How to Set Up or Disable Application Licensing](how-to-set-up-or-disable-application-licensing.md).</span></span>

## <span data-ttu-id="346d8-115">プロバイダーポリシー</span><span class="sxs-lookup"><span data-stu-id="346d8-115">Provider Policies</span></span>


<span data-ttu-id="346d8-116">プロバイダーポリシーは、アプリケーションサービスプロバイダー (ASP) モデル用に開発されました。</span><span class="sxs-lookup"><span data-stu-id="346d8-116">Provider policies were developed for the Application Service Provider (ASP) model.</span></span> <span data-ttu-id="346d8-117">このモデルでは、1つの ASP で複数のクライアントに対して単一の Application Virtualization システムをホストできます。このシステムでは、各クライアントが分離された状態を維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="346d8-117">In this model, a single ASP can host a single Application Virtualization System for multiple clients, where each client needs to remain isolated.</span></span> <span data-ttu-id="346d8-118">クライアントによっては、異なる要件がある場合があります。たとえば、一方のクライアントでは認証が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="346d8-118">Clients might have dramatically different requirements—for example, one client might require authentication while another does not.</span></span> <span data-ttu-id="346d8-119">プロバイダーポリシーを使って、アクセス許可をクライアントに関連付けることができます。これにより、承認されたユーザーのみが各仮想アプリケーションパッケージにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="346d8-119">You can use provider policies to associate permissions with clients so that only the approved users can access each virtual application or virtual application package.</span></span>

<span data-ttu-id="346d8-120">エンタープライズ顧客の場合、1つ以上のアプリケーションのライセンス要件が厳密である場合は、この機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="346d8-120">For the enterprise customer, you can use this feature when you have strict licensing requirements for one or more applications.</span></span> <span data-ttu-id="346d8-121">この状況では、[**プロバイダーのプロパティ**] ダイアログの [**プロバイダーパイプライン**] タブで、ライセンスコンポーネントが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="346d8-121">Under this situation, the licensing component is disabled on the **Provider Pipeline** tab of the **Provider Properties** dialog.</span></span>

<span data-ttu-id="346d8-122">[**プロバイダーパイプライン**] タブには、認証、承認 (**アクセス許可の設定を適用**)、およびメータリング (**ログの使用状況情報**) を有効にするチェックボックスもあります。</span><span class="sxs-lookup"><span data-stu-id="346d8-122">The **Provider Pipeline** tab also has check boxes to enable authentication, authorization (**Enforce Access Permission Settings**), and metering (**Log Usage Information**).</span></span> <span data-ttu-id="346d8-123">構成に特別な要件がある場合は、 **[詳細設定**] ボタンをクリックして、独自のパイプラインコンポーネントを作成し、それらをシステムに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="346d8-123">If your configuration has special requirements, you can write your own pipeline components and add them to the system by clicking the **Advanced** button.</span></span>

## <span data-ttu-id="346d8-124">アカウント機関</span><span class="sxs-lookup"><span data-stu-id="346d8-124">Account Authorities</span></span>


<span data-ttu-id="346d8-125">Account authority は、Application Virtualization サーバーがインストールされているドメインです。</span><span class="sxs-lookup"><span data-stu-id="346d8-125">The account authority is the domain in which the Application Virtualization Server is installed.</span></span> <span data-ttu-id="346d8-126">サーバーのインストールを続行すると、ドメイン名を入力するように求められます。コンピューターがインストールされているドメインが検出され、既定で使用されます。</span><span class="sxs-lookup"><span data-stu-id="346d8-126">As you proceed through the server installation, you are prompted to supply a domain name; the domain in which the computer is installed is detected and used by default.</span></span> <span data-ttu-id="346d8-127">ユーザーがシステムにログインしようとすると、ユーザーはそのドメインにアクセスする前に、資格情報の入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="346d8-127">When users attempt to log in to the system, they are prompted for their credentials before they can access that domain.</span></span>

<span data-ttu-id="346d8-128">Application Virtualization システムでは、複数のドメインがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="346d8-128">The Application Virtualization System supports multiple domains.</span></span> <span data-ttu-id="346d8-129">ドメイン間で信頼関係が確立されている場合は、他のドメインのユーザーグループにアプリケーションアクセスを付与することができます。</span><span class="sxs-lookup"><span data-stu-id="346d8-129">You can grant application access to user groups in other domains if a trust relationship is established between domains.</span></span> <span data-ttu-id="346d8-130">ユーザーは、各ドメインによって認識される資格情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="346d8-130">Users must supply credentials that are recognized by each domain.</span></span>

<span data-ttu-id="346d8-131">Application Virtualization Server 管理コンソールで、プライマリドメイン (アカウント機関) とそれにアクセスするために使用される資格情報を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="346d8-131">In the Application Virtualization Server Management Console, you can change the primary domain (account authority) and the credentials that are used to access it.</span></span>

## <span data-ttu-id="346d8-132">認証</span><span class="sxs-lookup"><span data-stu-id="346d8-132">Authentication</span></span>


<span data-ttu-id="346d8-133">認証は、ユーザーの id を確認するために使用されるメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="346d8-133">Authentication is the mechanism used to confirm a user's identity.</span></span> <span data-ttu-id="346d8-134">ユーザー名とパスワードが認識されているすべてのユーザーがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="346d8-134">Any user with a recognized user name and password has access.</span></span>

<span data-ttu-id="346d8-135">Application Virtualization システムでは、[**プロバイダーパイプライン**] タブのチェックボックスを使用して、認証を有効または無効にすることができます。既定では、Windows 認証が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="346d8-135">In the Application Virtualization System, you can enable or disable authentication through a check box on the **Provider Pipeline** tab. By default, Windows Authentication is enabled.</span></span>

## <span data-ttu-id="346d8-136">Authorization</span><span class="sxs-lookup"><span data-stu-id="346d8-136">Authorization</span></span>


<span data-ttu-id="346d8-137">承認とは、ユーザーの id を確認するために使用されるプロセスです。</span><span class="sxs-lookup"><span data-stu-id="346d8-137">Authorization is the process used to confirm a user’s identity.</span></span> <span data-ttu-id="346d8-138">ユーザーの id を確認した後、システムへのアクセス権がユーザーに付与されたかどうか、およびユーザーにアクセス権が付与されたアプリケーションを確認します。</span><span class="sxs-lookup"><span data-stu-id="346d8-138">After confirming the user's identity, the system determines whether the user was granted access to the system and to which applications the user was granted access.</span></span> <span data-ttu-id="346d8-139">Application Virtualization Server 管理コンソールには、承認を有効または無効にするための [**プロバイダーパイプライン**] タブの [**アクセス許可の設定を適用**] チェックボックスがあります。</span><span class="sxs-lookup"><span data-stu-id="346d8-139">The Application Virtualization Server Management Console has an **Enforce Access Permission Settings** check box on the **Provider Pipeline** tab to enable or disable authorization.</span></span>

<span data-ttu-id="346d8-140">Application Virtualization システムでは、アクセスは個々のユーザーに対してではなく、ユーザーグループに対してのみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="346d8-140">In the Application Virtualization System, access is granted to a user group only, not to individual users.</span></span>

## <span data-ttu-id="346d8-141">関連トピック</span><span class="sxs-lookup"><span data-stu-id="346d8-141">Related topics</span></span>


[<span data-ttu-id="346d8-142">サーバー管理コンソールでアプリケーション ライセンスを管理する方法</span><span class="sxs-lookup"><span data-stu-id="346d8-142">How to Manage Application Licenses in the Server Management Console</span></span>](how-to-manage-application-licenses-in-the-server-management-console.md)

[<span data-ttu-id="346d8-143">アプリケーション ライセンスをセットアップまたは無効にする方法</span><span class="sxs-lookup"><span data-stu-id="346d8-143">How to Set Up or Disable Application Licensing</span></span>](how-to-set-up-or-disable-application-licensing.md)

[<span data-ttu-id="346d8-144">サーバー管理コンソール: プロバイダー ポリシー ノード</span><span class="sxs-lookup"><span data-stu-id="346d8-144">Server Management Console: Provider Policies Node</span></span>](server-management-console-provider-policies-node.md)

 

 





