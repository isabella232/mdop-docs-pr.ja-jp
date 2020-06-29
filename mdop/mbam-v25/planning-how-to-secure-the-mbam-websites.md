---
title: MBAM Web サイトをセキュリティで保護する方法の計画
description: MBAM Web サイトをセキュリティで保護する方法の計画
author: dansimp
ms.assetid: aea1d137-62cf-4da4-9989-541e0b5ad8d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 223c9397ad7933e11051c289c3dbcab63940fbc5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825024"
---
# <span data-ttu-id="27123-103">MBAM Web サイトをセキュリティで保護する方法の計画</span><span class="sxs-lookup"><span data-stu-id="27123-103">Planning How to Secure the MBAM Websites</span></span>


<span data-ttu-id="27123-104">このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) 2.5 の管理と監視を行うための次の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="27123-104">This topic describes the following methods for securing the Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 Administration and Monitoring Website and Self-Service Portal:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="27123-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="27123-105">Method</span></span></th>
<th align="left"><span data-ttu-id="27123-106">必須または省略可能ですか?</span><span class="sxs-lookup"><span data-stu-id="27123-106">Required or optional?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="27123-107">証明書を使用して MBAM web サイトを保護する</span><span class="sxs-lookup"><span data-stu-id="27123-107">Using certificates to secure MBAM websites</span></span></p></td>
<td align="left"><p><span data-ttu-id="27123-108">省略可能、強く推奨</span><span class="sxs-lookup"><span data-stu-id="27123-108">Optional, but highly recommended</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="27123-109">アプリケーションプールアカウントのサービスプリンシパル名 (SPN) を登録しています</span><span class="sxs-lookup"><span data-stu-id="27123-109">Registering Service Principal Names (SPN) for the application pool account</span></span></p></td>
<td align="left"><p><span data-ttu-id="27123-110">必須かどうか</span><span class="sxs-lookup"><span data-stu-id="27123-110">Required</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="27123-111">MBAM の展開をセキュリティで保護する方法について詳しくは、「 [mbam 2.5 のセキュリティに関する考慮事項](mbam-25-security-considerations.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="27123-111">For more information about how to secure your MBAM deployment, see [MBAM 2.5 Security Considerations](mbam-25-security-considerations.md).</span></span>

## <span data-ttu-id="27123-112">証明書を使用して MBAM web サイトを保護する</span><span class="sxs-lookup"><span data-stu-id="27123-112">Using certificates to secure MBAM websites</span></span>


<span data-ttu-id="27123-113">以下の間の通信をセキュリティで保護するために証明書を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="27123-113">We recommend that you use a certificate to secure the communication between the:</span></span>

-   <span data-ttu-id="27123-114">MBAM クライアントと web サービス</span><span class="sxs-lookup"><span data-stu-id="27123-114">MBAM Client and the web services</span></span>

-   <span data-ttu-id="27123-115">ブラウザーと、Web サイトとセルフサービスポータル web サイトの管理と監視</span><span class="sxs-lookup"><span data-stu-id="27123-115">Browser and the Administration and Monitoring Website and the Self-Service Portal websites</span></span>

<span data-ttu-id="27123-116">証明書の要求とインストールの詳細については、「[インターネットサーバー証明書を構成する](https://technet.microsoft.com/library/cc731977.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27123-116">For information about requesting and installing a certificate, see [Configuring Internet Server Certificates](https://technet.microsoft.com/library/cc731977.aspx).</span></span>

**<span data-ttu-id="27123-117">注</span><span class="sxs-lookup"><span data-stu-id="27123-117">Note</span></span>**  
<span data-ttu-id="27123-118">Windows PowerShell を使用している場合にのみ、web サイトと web サービスをさまざまなサーバーで構成できます。</span><span class="sxs-lookup"><span data-stu-id="27123-118">You can configure the websites and web services on different servers only if you are using Windows PowerShell.</span></span> <span data-ttu-id="27123-119">MBAM サーバー構成ウィザードを使って web サイトを構成する場合は、同じサーバー上で web サイトと web サービスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27123-119">If you use the MBAM Server Configuration wizard to configure the websites, you must configure the websites and the web services on the same server.</span></span>



<span data-ttu-id="27123-120">Web サービスとデータベース間の通信をセキュリティで保護するために、SQL Server で暗号化を強制することもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="27123-120">To secure the communication between the web services and the databases, we also recommend that you force encryption in SQL Server.</span></span> <span data-ttu-id="27123-121">Web サービスと SQL Server の間の通信など、SQL Server へのすべての接続をセキュリティで保護する方法については、「 [Mbam 2.5 セキュリティに関する考慮事項](mbam-25-security-considerations.md#bkmk-secure-databases)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27123-121">For information about securing all connections to SQL Server, including communication between the web services and SQL Server, see [MBAM 2.5 Security Considerations](mbam-25-security-considerations.md#bkmk-secure-databases).</span></span>

## <span data-ttu-id="27123-122">アプリケーションプールアカウントの Spn の登録</span><span class="sxs-lookup"><span data-stu-id="27123-122">Registering SPNs for the application pool account</span></span>


<span data-ttu-id="27123-123">MBAM サーバーが管理および監視 Web サイトとセルフサービスポータルからの通信を認証できるようにするには、web アプリケーションプールに使用しているドメインアカウントの下で、ホスト名にサービスプリンシパル名 (SPN) を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27123-123">To enable the MBAM Servers to authenticate communication from the Administration and Monitoring Website and the Self-Service Portal, you must register a Service Principal Name (SPN) for the host name under the domain account that you are using for the web application pool.</span></span>

<span data-ttu-id="27123-124">このトピックでは、次の種類のホスト名の Spn を登録する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="27123-124">This topic contains instructions on how to register SPNs for the following types of host names:</span></span>

-   <span data-ttu-id="27123-125">完全修飾ドメイン名</span><span class="sxs-lookup"><span data-stu-id="27123-125">Fully qualified domain name</span></span>

-   <span data-ttu-id="27123-126">NetBIOS 名</span><span class="sxs-lookup"><span data-stu-id="27123-126">NetBIOS name</span></span>

-   <span data-ttu-id="27123-127">仮想名</span><span class="sxs-lookup"><span data-stu-id="27123-127">Virtual name</span></span>

### <span data-ttu-id="27123-128">最初の MBAM インストール用に Spn を作成する前に</span><span class="sxs-lookup"><span data-stu-id="27123-128">Before you create SPNs for an initial MBAM installation</span></span>

<span data-ttu-id="27123-129">Spn の作成を開始する前に、次の表の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="27123-129">Review the information in the following table before you start creating SPNs.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="27123-130">タスクまたはアイテム</span><span class="sxs-lookup"><span data-stu-id="27123-130">Task or item</span></span></th>
<th align="left"><span data-ttu-id="27123-131">詳細情報</span><span class="sxs-lookup"><span data-stu-id="27123-131">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="27123-132">Active Directory ドメインサービス (AD DS) でサービスアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="27123-132">Create a service account in Active Directory Domain Services (AD DS).</span></span></p></td>
<td align="left"><p><span data-ttu-id="27123-133">サービスアカウントは、MBAM web サイトのセキュリティを確保するために、AD DS で作成するユーザーアカウントです。</span><span class="sxs-lookup"><span data-stu-id="27123-133">The service account is a user account that you create in AD DS to provide security for the MBAM websites.</span></span> <span data-ttu-id="27123-134">MBAM web サイトはアプリケーションプールの下で実行されます。 id はサービスアカウントの名前です。</span><span class="sxs-lookup"><span data-stu-id="27123-134">The MBAM websites run under an application pool, whose identity is the name of the service account.</span></span> <span data-ttu-id="27123-135">次に、Spn がアプリケーションプールアカウントに登録されます。</span><span class="sxs-lookup"><span data-stu-id="27123-135">The SPNs are then registered in the application pool account.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="27123-136">注</span><span class="sxs-lookup"><span data-stu-id="27123-136">Note</span></span></strong><br/><p><span data-ttu-id="27123-137">すべての web サーバーに同じアプリケーションプールアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27123-137">You must use the same application pool account for all web servers.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="27123-138">IIS/IUSRS グループアカウントまたはアプリケーションプールアカウントに必要な権限が付与されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="27123-138">Verify that either the IIS-IUSRS group account or the application pool account has been granted the necessary rights.</span></span></p></td>
<td align="left"><p><span data-ttu-id="27123-139">確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27123-139">To check this, follow these steps:</span></span></p>
<ol>
<li><p><span data-ttu-id="27123-140"><strong>ローカルセキュリティポリシーエディターを開き、 </strong> [ローカルポリシー] ノードを展開し <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="27123-140">Open the <strong>Local Security Policy editor</strong> and expand the <strong>Local Policies</strong> node.</span></span></p></li>
<li><p><span data-ttu-id="27123-141">[ <strong> ユーザー権利の割り当て] ノードを選択し、右側の </strong> <strong> ウィンドウで [認証後にクライアントを偽装 </strong> し、 <strong> バッチジョブとしてログオンする] グループポリシー設定をダブルクリックし </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="27123-141">Select the <strong>User Rights Assignment</strong> node, and double-click the <strong>Impersonate a client after authentication</strong> and <strong>Log on as a batch job</strong> Group Policy settings in the right pane.</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="27123-142">ドメイン管理者アカウントを使用して MBAM web サイトを構成した場合、MBAM によって Spn が作成されます。</span><span class="sxs-lookup"><span data-stu-id="27123-142">If you configure the MBAM websites by using a domain administrative account, MBAM will create the SPNs for you.</span></span></p></td>
<td align="left"><p><span data-ttu-id="27123-143">ドメイン管理アカウントを使用して MBAM web サイトを構成する場合は、このトピックの手順に従って、使用しているホスト名の種類に対して手動で Spn を登録します。</span><span class="sxs-lookup"><span data-stu-id="27123-143">If you configure the MBAM websites by using a domain administrative account, follow the steps in this topic to register SPNs manually for the type of host name that you are using.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="27123-144">完全修飾ドメインホスト名を使用しているときに Spn を登録する</span><span class="sxs-lookup"><span data-stu-id="27123-144">Registering SPNs when you use a fully qualified domain host name</span></span>

<span data-ttu-id="27123-145">MBAM を構成するときに完全修飾ドメインホスト名を使用している場合は、次の例に示すように、SPN を1つだけ登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27123-145">If you use a fully qualified domain host name when you configure MBAM, you have to register only one SPN, as shown in the following example.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="27123-146">必要な作業</span><span class="sxs-lookup"><span data-stu-id="27123-146">What you need to do</span></span></th>
<th align="left"><span data-ttu-id="27123-147">例と詳細情報</span><span class="sxs-lookup"><span data-stu-id="27123-147">Examples and more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="27123-148">完全修飾ドメイン名の SPN を登録します。</span><span class="sxs-lookup"><span data-stu-id="27123-148">Register an SPN for the fully qualified domain name.</span></span></p></td>
<td align="left"><p><code>Setspn -s http/mybitlockerrecovery.contoso.com contoso\mbamapppooluser</code></p>
<p><span data-ttu-id="27123-149">完全修飾ホスト名は <strong> mybitlockerrecovery.contoso.com </strong> であり、web アプリケーションプールに使用されているドメインアカウントは <strong> contoso\mbamapppooluser です </strong> 。</span><span class="sxs-lookup"><span data-stu-id="27123-149">The fully qualified host name is <strong>mybitlockerrecovery.contoso.com</strong>, and the domain account used for the web application pool is <strong>contoso\mbamapppooluser</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="27123-150">アプリケーションプールアカウントに登録する SPN の制約付き委任を構成します。</span><span class="sxs-lookup"><span data-stu-id="27123-150">Configure constrained delegation for the SPN that you are registering for the application pool account.</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=394335" data-raw-source="[Configuring Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=394335)"><span data-ttu-id="27123-151">制約付き委任の構成</span><span class="sxs-lookup"><span data-stu-id="27123-151">Configuring Constrained Delegation</span></span></a></p>
<p><span data-ttu-id="27123-152">この要件は、MBAM 2.5 にのみ適用されます。MBAM 2.5 SP1 では必要ありません。</span><span class="sxs-lookup"><span data-stu-id="27123-152">This requirement only applies to MBAM 2.5; it is not necessary in MBAM 2.5 SP1.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="27123-153">NetBIOS ホスト名を使用する場合の Spn の登録</span><span class="sxs-lookup"><span data-stu-id="27123-153">Registering SPNs when you use a NetBIOS host name</span></span>

<span data-ttu-id="27123-154">MBAM を構成するときに NetBIOS ホスト名を使う場合は、次の例に示すように、NetBIOS 名に1つの SPN を登録し、完全修飾ドメイン名には別の SPN を登録します。</span><span class="sxs-lookup"><span data-stu-id="27123-154">If you use a NetBIOS host name when you configure MBAM, register one SPN for the NetBIOS name, and another SPN for the fully qualified domain name, as shown in the following examples.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="27123-155">必要な作業</span><span class="sxs-lookup"><span data-stu-id="27123-155">What you need to do</span></span></th>
<th align="left"><span data-ttu-id="27123-156">例と詳細情報</span><span class="sxs-lookup"><span data-stu-id="27123-156">Examples and more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="27123-157">NetBIOS ホスト名の SPN を登録します。</span><span class="sxs-lookup"><span data-stu-id="27123-157">Register an SPN for the NetBIOS host name.</span></span></p></td>
<td align="left"><p><code>Setspn -s http/nbname01 contoso\mbamapppooluser</code></p>
<p><span data-ttu-id="27123-158">NetBIOS のホスト名は <strong> nbname01 </strong> であり、web アプリケーションプールに使用されているドメインアカウントは <strong> contoso\mbamapppooluser です </strong> 。</span><span class="sxs-lookup"><span data-stu-id="27123-158">The NetBIOS host name is <strong>nbname01</strong>, and the domain account used for the web application pool is <strong>contoso\mbamapppooluser</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="27123-159">完全修飾ドメイン名の SPN を登録します。</span><span class="sxs-lookup"><span data-stu-id="27123-159">Register an SPN for the fully qualified domain name.</span></span></p></td>
<td align="left"><p><code>Setspn –s http/nbname01.corp.contoso.com contoso\mbamapppooluser</code></p>
<p><span data-ttu-id="27123-160">完全修飾ドメイン名は <strong> nbname01.contoso.com </strong> であり、web アプリケーションプールに使用されているドメインアカウントは <strong> contoso\mbamapppooluser です </strong> 。</span><span class="sxs-lookup"><span data-stu-id="27123-160">The fully qualified domain name is <strong>nbname01.contoso.com</strong>, and the domain account used for the web application pool is <strong>contoso\mbamapppooluser</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="27123-161">アプリケーションプールアカウントに登録する Spn の制約付き委任を構成します。</span><span class="sxs-lookup"><span data-stu-id="27123-161">Configure constrained delegation for the SPNs that you are registering for the application pool account.</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=394335" data-raw-source="[Configuring Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=394335)"><span data-ttu-id="27123-162">制約付き委任の構成</span><span class="sxs-lookup"><span data-stu-id="27123-162">Configuring Constrained Delegation</span></span></a></p>
<p><span data-ttu-id="27123-163">この要件は、MBAM 2.5 にのみ適用されます。MBAM 2.5 SP1 では必要ありません。</span><span class="sxs-lookup"><span data-stu-id="27123-163">This requirement only applies to MBAM 2.5; it is not necessary in MBAM 2.5 SP1.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-regvirtualspn"></a><span data-ttu-id="27123-164">仮想ホスト名を使用するときの Spn の登録</span><span class="sxs-lookup"><span data-stu-id="27123-164">Registering SPNs when you use a virtual host name</span></span>

<span data-ttu-id="27123-165">完全修飾ドメイン名である仮想ホスト名で MBAM を構成する場合は、その仮想ホスト名の SPN を1つだけ登録します。</span><span class="sxs-lookup"><span data-stu-id="27123-165">If you configure MBAM with a virtual host name that is a fully qualified domain name, register only one SPN for the virtual host name.</span></span> <span data-ttu-id="27123-166">構成する仮想ホスト名が完全修飾ドメイン名ではない場合は、次の例に示すように、完全修飾ドメイン名を指定する2つ目の SPN を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27123-166">If the virtual host name that you configure is not a fully qualified domain name, you must create a second SPN that specifies the fully qualified domain name, as described in the following examples.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="27123-167">必要な作業</span><span class="sxs-lookup"><span data-stu-id="27123-167">What you need to do</span></span></th>
<th align="left"><span data-ttu-id="27123-168">例と詳細情報</span><span class="sxs-lookup"><span data-stu-id="27123-168">Examples and more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="27123-169">仮想ホスト名が完全修飾ドメイン名の場合、この例では、SPN を1つだけ登録します。</span><span class="sxs-lookup"><span data-stu-id="27123-169">If your virtual host name is a fully qualified domain name, as in this example, register only one SPN.</span></span></p></td>
<td align="left"><p><code>Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></p>
<p><span data-ttu-id="27123-170">この例では、仮想ホスト名は <strong> mbamvirtual.contoso.com で </strong> あり、web アプリケーションプールに使用されているドメインアカウントは <strong> contoso\mbamapppooluser です </strong> 。</span><span class="sxs-lookup"><span data-stu-id="27123-170">In the example, the virtual host name is <strong>mbamvirtual.contoso.com</strong>, and the domain account used for the web application pool is <strong>contoso\mbamapppooluser</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="27123-171">仮想ホスト名が完全修飾ドメイン名ではない場合は、この追加の SPN を登録します。</span><span class="sxs-lookup"><span data-stu-id="27123-171">Register this additional SPN if your virtual host name is not a fully qualified domain name.</span></span></p></td>
<td align="left"><p><code>Setspn -s http/mbamvirtual contoso\mbamapppooluser</code></p>
<p><span data-ttu-id="27123-172">この例では、仮想ホスト名は <strong> mbamvirtual </strong> で、web アプリケーションプールに使用されるドメインアカウントは <strong> contoso\mbamapppooluser です </strong> 。</span><span class="sxs-lookup"><span data-stu-id="27123-172">In the example, the virtual host name is <strong>mbamvirtual</strong>, and the domain account used for the web application pool is <strong>contoso\mbamapppooluser</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="27123-173">仮想ホスト名が完全修飾ドメイン名ではない場合は、この追加の SPN を登録します。</span><span class="sxs-lookup"><span data-stu-id="27123-173">Register this additional SPN if your virtual host name is not a fully qualified domain name.</span></span></p></td>
<td align="left"><p><code>Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></p>
<p><span data-ttu-id="27123-174">この例では、仮想ホスト名は <strong> mbamvirtual.contoso.com で </strong> あり、web アプリケーションプールに使用されているドメインアカウントは <strong> contoso\mbamapppooluser です </strong> 。</span><span class="sxs-lookup"><span data-stu-id="27123-174">In the example, the virtual host name is <strong>mbamvirtual.contoso.com</strong>, and the domain account used for the web application pool is <strong>contoso\mbamapppooluser</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="27123-175">ドメインネームサーバー (DNS) サーバーで、カスタムホスト名の "A record" を作成し、web サーバーまたはロードバランサーをポイントします。</span><span class="sxs-lookup"><span data-stu-id="27123-175">On the Domain Name Server (DNS) server, create an “A record” for the custom host name and point it to a web server or a load balancer.</span></span></p></td>
<td align="left"><p><span data-ttu-id="27123-176">「DNS ホストレコードを構成する」の「DNS ホスト A レコードを構成する」セクションを参照してください <a href="https://go.microsoft.com/fwlink/?LinkId=394337" data-raw-source="[Configure DNS Host Records](https://go.microsoft.com/fwlink/?LinkId=394337)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="27123-176">See the “To configure DNS Host A Records” section in <a href="https://go.microsoft.com/fwlink/?LinkId=394337" data-raw-source="[Configure DNS Host Records](https://go.microsoft.com/fwlink/?LinkId=394337)">Configure DNS Host Records</a>.</span></span></p>
<p><span data-ttu-id="27123-177">CNAMES の代わりにレコードを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="27123-177">We recommend that you use A records instead of CNAMES.</span></span> <span data-ttu-id="27123-178">CNAMES を使ってドメインアドレスを指定している場合は、アプリケーションプールアカウントに web サーバー名の Spn も登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27123-178">If you use CNAMES to point to the domain address, you must also register SPNs for the web server name in the application pool account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="27123-179">アプリケーションプールアカウントに登録する Spn の制約付き委任を構成します。</span><span class="sxs-lookup"><span data-stu-id="27123-179">Configure constrained delegation for the SPNs that you are registering for the application pool account.</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=394335" data-raw-source="[Configuring Constrained Delegation](https://go.microsoft.com/fwlink/?LinkId=394335)"><span data-ttu-id="27123-180">制約付き委任の構成</span><span class="sxs-lookup"><span data-stu-id="27123-180">Configuring Constrained Delegation</span></span></a></p>
<p><span data-ttu-id="27123-181">この要件は、MBAM 2.5 にのみ適用されます。MBAM 2.5 SP1 では必要ありません。</span><span class="sxs-lookup"><span data-stu-id="27123-181">This requirement only applies to MBAM 2.5; it is not necessary in MBAM 2.5 SP1.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-registerspn"></a><span data-ttu-id="27123-182">以前のバージョンの MBAM からアップグレードするときに SPN を登録する</span><span class="sxs-lookup"><span data-stu-id="27123-182">Registering an SPN when you upgrade from previous versions of MBAM</span></span>

<span data-ttu-id="27123-183">次の場合のみ、このセクションの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27123-183">Complete the steps in this section only if you want to:</span></span>

-   <span data-ttu-id="27123-184">以前のバージョンの MBAM からアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="27123-184">Upgrade from a previous version of MBAM.</span></span>

-   <span data-ttu-id="27123-185">ロードバランスまたは分散構成で MBAM 2.5 で web サイトを実行します。現在は、読み込みが分散されていない構成で実行されています。</span><span class="sxs-lookup"><span data-stu-id="27123-185">Run the websites in MBAM 2.5 in a load-balanced or distributed configuration, and you are currently running in a configuration that is not load balanced.</span></span>

<span data-ttu-id="27123-186">アプリケーションプールアカウントではなく、コンピューターアカウントに既に Spn が登録されている場合、MBAM は既存の Spn を使用し、負荷分散または分散構成で web サイトを構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="27123-186">If you already registered SPNs on the machine account rather than in an application pool account, MBAM uses the existing SPNs, and you cannot configure the websites in a load-balanced or distributed configuration.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="27123-187">必要な作業</span><span class="sxs-lookup"><span data-stu-id="27123-187">What you need to do</span></span></th>
<th align="left"><span data-ttu-id="27123-188">例と詳細情報</span><span class="sxs-lookup"><span data-stu-id="27123-188">Examples and more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="27123-189">Active Directory ドメインサービス (AD DS) でアプリケーションプールアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="27123-189">Create an application pool account in Active Directory Domain Services (AD DS).</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="27123-190">現在インストールされている web サイトと web サービスを削除します。</span><span class="sxs-lookup"><span data-stu-id="27123-190">Remove the currently installed websites and web services.</span></span></p></td>
<td align="left"><p><a href="removing-mbam-server-features-or-software.md" data-raw-source="[Removing MBAM Server Features or Software](removing-mbam-server-features-or-software.md)"><span data-ttu-id="27123-191">MBAM サーバーの機能またはソフトウェアの削除</span><span class="sxs-lookup"><span data-stu-id="27123-191">Removing MBAM Server Features or Software</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="27123-192">コンピューターアカウントから Spn を削除します。</span><span class="sxs-lookup"><span data-stu-id="27123-192">Remove SPNs from the machine account.</span></span></p></td>
<td align="left"><p><code>Setspn –d http/mbamwebserver mbamwebserver</code></p>
<p><code>Setspn –d http/mbamwebserver.contoso.com mbamwebserver</code></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="27123-193">アプリケーションプールアカウントに Spn を登録します。</span><span class="sxs-lookup"><span data-stu-id="27123-193">Register SPNs in the application pool account.</span></span></p></td>
<td align="left"><p><span data-ttu-id="27123-194"><a href="#bkmk-regvirtualspn" data-raw-source="[Registering SPNs when you use a virtual host name](#bkmk-regvirtualspn)">仮想ホスト名を使用するときに、spn を登録する手順に従い </a> ます。</span><span class="sxs-lookup"><span data-stu-id="27123-194">Follow the steps for <a href="#bkmk-regvirtualspn" data-raw-source="[Registering SPNs when you use a virtual host name](#bkmk-regvirtualspn)">Registering SPNs when you use a virtual host name</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="27123-195">Web アプリケーションと web サービスを再構成します。</span><span class="sxs-lookup"><span data-stu-id="27123-195">Reconfigure the web applications and web services.</span></span></p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)"><span data-ttu-id="27123-196">MBAM 2.5 Web アプリケーションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="27123-196">How to Configure the MBAM 2.5 Web Applications</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="27123-197">構成に使用する方法に応じて、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="27123-197">Do one of the following, depending on the method you use for the configuration:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="27123-198">方法</span><span class="sxs-lookup"><span data-stu-id="27123-198">Method</span></span></th>
<th align="left"><span data-ttu-id="27123-199">詳細</span><span class="sxs-lookup"><span data-stu-id="27123-199">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="27123-200">MBAM サーバー構成ウィザード</span><span class="sxs-lookup"><span data-stu-id="27123-200">MBAM Server Configuration wizard</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="27123-201">[ <strong> Web サービスアプリケーションプールドメインアカウント] フィールドにアプリケーションプールアカウントを入力し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="27123-201">Enter the application pool account in the <strong>Web service application pool domain account</strong> field.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><code>Enable-MbamWebApplication</code> <span data-ttu-id="27123-202">Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="27123-202">Windows PowerShell cmdlet</span></span></p></td>
<td align="left"><p><span data-ttu-id="27123-203">パラメーターにアカウントを入力し <code>WebServiceApplicationPoolCredential</code> ます。</span><span class="sxs-lookup"><span data-stu-id="27123-203">Enter the account in the <code>WebServiceApplicationPoolCredential</code> parameter.</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
<td align="left"><div class="alert">
<strong><span data-ttu-id="27123-204">重要</span><span class="sxs-lookup"><span data-stu-id="27123-204">Important</span></span></strong><br/><p><span data-ttu-id="27123-205">入力するホスト名は、Spn を作成する仮想ホスト名と同じ名前である必要があります。</span><span class="sxs-lookup"><span data-stu-id="27123-205">The host name that you enter must be the same name as the virtual host name for which you are creating the SPNs.</span></span> <span data-ttu-id="27123-206">また、web ファームでは、ホスト名とアプリケーションプールの資格情報が、構成しているすべてのサーバーで同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="27123-206">Also, in your web farm, the host names and the application pool credentials must be the same on every server that you are configuring.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="27123-207">MBAM で web アプリケーションを構成する場合は、Spn の登録が試みられますが、この操作は、MBAM をインストールするサーバーのドメイン管理者権限を持っている場合にのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="27123-207">When MBAM configures the web applications, it will try to register the SPNs for you, but it can do so only if you have Domain Admin rights on the server on which you are installing MBAM.</span></span> <span data-ttu-id="27123-208">これらの権利を持っていない場合は、構成を完了することはできますが、MBAM の前後に Spn を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27123-208">If you do not have these rights, you can complete the configuration, but you will have to set the SPNs before or after you configure MBAM.</span></span></p></td>
</tr>
</tbody>
</table>

## <span data-ttu-id="27123-209">必要な要求のフィルター処理の設定</span><span class="sxs-lookup"><span data-stu-id="27123-209">Required Request Filtering Settings</span></span>

 <span data-ttu-id="27123-210">アプリケーションが予期したとおりに動作するには、[リストにないファイル名拡張子の許可] が必要です。</span><span class="sxs-lookup"><span data-stu-id="27123-210">'Allow unlisted file name extensions' is required for the application to operate as expected.</span></span>  <span data-ttu-id="27123-211">この方法については、「Microsoft BitLocker の管理と監視」「> 要求のフィルター処理」を参照してください。 > 編集機能の設定があります。</span><span class="sxs-lookup"><span data-stu-id="27123-211">This can be found by navigating to the 'Microsoft BitLocker Administration and Monitoring' -> Request Filtering -> Edit Feature Settings.</span></span>


## <span data-ttu-id="27123-212">関連トピック</span><span class="sxs-lookup"><span data-stu-id="27123-212">Related topics</span></span>


[<span data-ttu-id="27123-213">MBAM 2.5 に対応する環境の準備</span><span class="sxs-lookup"><span data-stu-id="27123-213">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)

[<span data-ttu-id="27123-214">MBAM 2.5 展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="27123-214">MBAM 2.5 Deployment Prerequisites</span></span>](mbam-25-deployment-prerequisites.md)





## <span data-ttu-id="27123-215">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="27123-215">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="27123-216">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="27123-216">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="27123-217">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="27123-217">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>



