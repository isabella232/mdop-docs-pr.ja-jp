---
title: MED-V エンド ユーザーの認証
description: MED-V エンド ユーザーの認証
author: dansimp
ms.assetid: aaf96eb6-91d1-4f4d-9854-5fc73c7ae7ab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 14c1e95a94f2da76b6b6c5ebd9d4cf14dcf839a7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824887"
---
# <span data-ttu-id="f8494-103">MED-V エンド ユーザーの認証</span><span class="sxs-lookup"><span data-stu-id="f8494-103">Authentication of MED-V End Users</span></span>


<span data-ttu-id="f8494-104">Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 エンドユーザーの認証は、非常に重要なセキュリティの問題です。</span><span class="sxs-lookup"><span data-stu-id="f8494-104">The authentication of Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 end users is a very important security issue.</span></span> <span data-ttu-id="f8494-105">このコンテキストでは、authentication は、MED-V エンドユーザーの id を確認することを意味します。</span><span class="sxs-lookup"><span data-stu-id="f8494-105">In this context, authentication refers to verifying the identity of the MED-V end user.</span></span>

<span data-ttu-id="f8494-106">以下のセクションでは、MED-V でのエンドユーザー認証についての情報とガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="f8494-106">The following section provides information and guidance about end-user authentication in MED-V.</span></span>

## <span data-ttu-id="f8494-107">MED-V でのユーザー認証</span><span class="sxs-lookup"><span data-stu-id="f8494-107">User Authentication in MED-V</span></span>


<span data-ttu-id="f8494-108">通常、MED-V での認証は、ユーザーが最初に MED-V にアクセスしたときと、ユーザーがパスワードを変更したときに、常に2つのレベルで行われます。</span><span class="sxs-lookup"><span data-stu-id="f8494-108">Authentication in MED-V generally occurs at two levels: when a user first accesses MED-V and every time that they change their password.</span></span>

<span data-ttu-id="f8494-109">認証用に MED-V 設定を構成した方法によっては、一般に、MED-V が開始されたとき、または公開されたアプリケーションを初めて開こうとしたときに、ユーザーにパスワードの入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8494-109">Depending on how you have configured MED-V settings for authentication, the end user is typically prompted at some point to enter their password, either the first time MED-V is started or the first time that they try to open a published application.</span></span>

<span data-ttu-id="f8494-110">コントロールできるエンドユーザー認証には、次のようないくつかの側面があります。</span><span class="sxs-lookup"><span data-stu-id="f8494-110">There are several aspects of end-user authentication that you can control, including the following:</span></span>

<span data-ttu-id="f8494-111">エンドユーザーが入力する資格情報が資格情報マネージャーに保存されているかどうか</span><span class="sxs-lookup"><span data-stu-id="f8494-111">Whether the credentials the end user enters are stored in Credential Manager</span></span>

<span data-ttu-id="f8494-112">エンドユーザーにパスワードの入力と保存のオプションが表示される方法</span><span class="sxs-lookup"><span data-stu-id="f8494-112">In what manner the end user is presented with the option of entering and saving their password</span></span>

<span data-ttu-id="f8494-113">企業がエンドユーザー認証を管理するための優先プロセスに応じて、特定の MED-V ワークスペースに対して資格情報のキャッシュを実行するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f8494-113">Depending on your company’s preferred process for managing end-user authentication, you can specify whether credential caching occurs for a particular MED-V workspace.</span></span> <span data-ttu-id="f8494-114">エンドユーザーの資格情報をキャッシュすると、パスワードに対して1回だけの入力が求められるため便利です。</span><span class="sxs-lookup"><span data-stu-id="f8494-114">Caching the credentials of an end user is helpful because they are only prompted one time for their password.</span></span> <span data-ttu-id="f8494-115">エンドユーザーが自分のパスワードを保存することを許可されていない場合、または、新しい med-v セッションを開始するたびに、新しい med-v セッションを開始する場合は、その後でもう一度入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8494-115">If the end user is not allowed to save their password or they decide not to, every time that they start a new MED-V session, they must enter it again.</span></span> <span data-ttu-id="f8494-116">たとえば、エンドユーザーがホストにログオンしたときに、有効になっているが、認証が無効になっている場合、エンドユーザーはログオン時に1回のみプロンプトを表示するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="f8494-116">For example, if MED-V is configured to start when the end user logs on to the host but Authentication is disabled, the end user is only prompted one time during logon.</span></span> <span data-ttu-id="f8494-117">この場合、資格情報はエンドユーザーがホストからログオフするまで有効です。</span><span class="sxs-lookup"><span data-stu-id="f8494-117">In this case, credentials are valid until the end user logs off from the host.</span></span>

<span data-ttu-id="f8494-118">必要に応じて、Credential Manager を使用して、保存されているエンドユーザーの資格情報を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="f8494-118">If it is necessary, you can use Credential Manager to remove any stored end-user credentials.</span></span>

<span data-ttu-id="f8494-119">既定では、資格情報の保存は無効になっていますが、次のいずれかの方法を使用してこの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f8494-119">By default, credential storing is disabled, but you can change this setting through one of the following methods:</span></span>

<span data-ttu-id="f8494-120">**Med-v ワークスペースパッケージを作成しているとき**。</span><span class="sxs-lookup"><span data-stu-id="f8494-120">**While you are creating the MED-V workspace package**.</span></span> <span data-ttu-id="f8494-121">詳細については、「 [Med-v ワークスペースパッケージを作成する](create-a-med-v-workspace-package.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8494-121">For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).</span></span>

<span data-ttu-id="f8494-122">**Med-v ワークスペースを展開**した後。</span><span class="sxs-lookup"><span data-stu-id="f8494-122">**After you have deployed the MED-V workspace**.</span></span> <span data-ttu-id="f8494-123">ターミナルサービスのレジストリキーを設定するには、MED-V コマンドレットパラメーター UxCredentialCacheEnabled を編集します。</span><span class="sxs-lookup"><span data-stu-id="f8494-123">Edit the MED-V cmdlet parameter UxCredentialCacheEnabled to set the Terminal Services registry key.</span></span> <span data-ttu-id="f8494-124">詳細については、「Windows PowerShell のヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8494-124">For more information, see Windows PowerShell Help.</span></span>

<span data-ttu-id="f8494-125">MED-V workspace の展開後に、DisablePasswordSaving という名前のターミナルサービスポリシーを変更して、エンドユーザー認証の環境設定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f8494-125">After MED-V workspace deployment, you can set your preference for end-user authentication by modifying the Terminal Services policy named DisablePasswordSaving.</span></span> <span data-ttu-id="f8494-126">DisablePasswordSaving [RDP クライアント] ダイアログウィンドウに [パスワードを保存する] チェックボックスが表示されるかどうか、および MED-V 資格情報の確認メッセージが表示されるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="f8494-126">DisablePasswordSaving controls whether the password saving check box appears on the RDP client dialog window and whether the MED-V credential prompt is displayed.</span></span>

<span data-ttu-id="f8494-127">DisablePasswordSaving という名前のターミナルサービスポリシーのポリシーパスを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f8494-127">Following is the policy path for the Terminal Services policy named DisablePasswordSaving.</span></span>

**<span data-ttu-id="f8494-128">Regedit.exe</span><span class="sxs-lookup"><span data-stu-id="f8494-128">Regedit:</span></span>**

<span data-ttu-id="f8494-129">HKEY \ _LOCAL \ _MACHINE \ ソフトウェア \\ Machine\\Policies\\DisablePasswordSaving</span><span class="sxs-lookup"><span data-stu-id="f8494-129">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Virtual Machine\\Policies\\DisablePasswordSaving</span></span>

**<span data-ttu-id="f8494-130">注</span><span class="sxs-lookup"><span data-stu-id="f8494-130">Note</span></span>**  
<span data-ttu-id="f8494-131">DisablePasswordSaving に加えた変更は、仮想マシンへの RDP プロンプトにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="f8494-131">The changes that you make to DisablePasswordSaving only affect the RDP prompt to a virtual machine.</span></span>



<span data-ttu-id="f8494-132">次の表に、資格情報の保存方法と、さまざまな構成の効果の設定を構成するさまざまな方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f8494-132">The following table lists the different ways you can configure your settings for credential storing and the effects of the different configurations:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f8494-133">値</span><span class="sxs-lookup"><span data-stu-id="f8494-133">Value</span></span></th>
<th align="left"><span data-ttu-id="f8494-134">構成</span><span class="sxs-lookup"><span data-stu-id="f8494-134">Configuration</span></span></th>
<th align="left"><span data-ttu-id="f8494-135">結果</span><span class="sxs-lookup"><span data-stu-id="f8494-135">Result</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f8494-136">DisablePasswordSaving</span><span class="sxs-lookup"><span data-stu-id="f8494-136">DisablePasswordSaving</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="f8494-137">無効</span><span class="sxs-lookup"><span data-stu-id="f8494-137">Disabled</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="f8494-138">MED-V のプロンプトが表示され、[承諾] のチェックボックスが使用でき、オフになっています。</span><span class="sxs-lookup"><span data-stu-id="f8494-138">The MED-V prompt is presented and a check box to accept is available and cleared.</span></span> <span data-ttu-id="f8494-139">エンドユーザーがチェックボックスをオンにすると、後で使用するために資格情報がキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="f8494-139">If the end user selects the check box, credentials are cached for subsequent use.</span></span> <span data-ttu-id="f8494-140">エンドユーザーにも、パスワードの有効期限が切れるときにのみメッセージが表示されるという利点があります。</span><span class="sxs-lookup"><span data-stu-id="f8494-140">The end user also has the benefit of only being prompted when the password expires.</span></span></p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="f8494-141">エンドユーザーがチェックボックスをオンにしない場合は、MED-V プロンプトではなくリモートデスクトップ接続 (RDC) クライアントのプロンプトが表示され、[受け入れる] チェックボックスはオフになります。</span><span class="sxs-lookup"><span data-stu-id="f8494-141">If the end user does not select the check box, the Remote Desktop Connection (RDC) Client prompt is presented instead of the MED-V prompt, and the check box to accept is cleared.</span></span> <span data-ttu-id="f8494-142">エンドユーザーがチェックボックスをオンにすると、RDC クライアント資格情報が保存され、後で使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f8494-142">If the end user selects the check box, the RDC Client credential is stored for later use.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="f8494-143">重要</span><span class="sxs-lookup"><span data-stu-id="f8494-143">Important</span></span></strong><br/><p><span data-ttu-id="f8494-144">エンドユーザーが資格情報を入力しても、RDC は資格情報を検証しません。</span><span class="sxs-lookup"><span data-stu-id="f8494-144">RDC does not validate credentials when the end user enters them.</span></span> <span data-ttu-id="f8494-145">エンドユーザーが RDC プロンプトを使用して資格情報をキャッシュした場合、正しくない資格情報が保存される可能性があるというリスクがあります。</span><span class="sxs-lookup"><span data-stu-id="f8494-145">If the end user caches the credentials through the RDC prompt, there is a risk that incorrect credentials might be stored.</span></span> <span data-ttu-id="f8494-146">この場合、Windows Credential Manager で間違った資格情報を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8494-146">In this case, the incorrect credentials must be deleted in the Windows Credential Manager.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f8494-147">DisablePasswordSaving</span><span class="sxs-lookup"><span data-stu-id="f8494-147">DisablePasswordSaving</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="f8494-148">有効</span><span class="sxs-lookup"><span data-stu-id="f8494-148">Enabled</span></span></strong></p></td>
<td align="left"><div class="alert">
<strong><span data-ttu-id="f8494-149">注</span><span class="sxs-lookup"><span data-stu-id="f8494-149">Note</span></span></strong><br/><p><span data-ttu-id="f8494-150">この構成では、エンドユーザーの資格情報をキャッシュできないため、安全性は高くなります。</span><span class="sxs-lookup"><span data-stu-id="f8494-150">This configuration is more secure because it does not allow end user credentials to be cached.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



<span data-ttu-id="f8494-151">既定では、MED-V をインストールすると、ゲストでレジストリキーが設定され、"有効期限切れのパスワード" プロンプトが表示されません。</span><span class="sxs-lookup"><span data-stu-id="f8494-151">By default, the MED-V installation sets a registry key in the guest to suppress the "password about to expire" prompt.</span></span> <span data-ttu-id="f8494-152">エンドユーザーは、ホストでパスワードの変更を求められるだけです。</span><span class="sxs-lookup"><span data-stu-id="f8494-152">The end user is only prompted for a password change on the host.</span></span> <span data-ttu-id="f8494-153">ホスト上で更新された資格情報がゲストに渡されます。</span><span class="sxs-lookup"><span data-stu-id="f8494-153">Credentials that are updated on the host are passed to the guest.</span></span>

**<span data-ttu-id="f8494-154">注意</span><span class="sxs-lookup"><span data-stu-id="f8494-154">Caution</span></span>**  
<span data-ttu-id="f8494-155">環境でグループポリシーを使用する場合は、ゲストからのパスワードの入力を求めるメッセージが表示される原因となっているレジストリキーを上書きできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f8494-155">If you use Group Policy in your environment, know that it can override the registry key causing the password prompts from the guest to reappear.</span></span>



### <span data-ttu-id="f8494-156">認証に関するセキュリティの問題</span><span class="sxs-lookup"><span data-stu-id="f8494-156">Security Concerns with Authentication</span></span>

<span data-ttu-id="f8494-157">エンドユーザーの資格情報をキャッシュすると、ユーザーエクスペリエンスが最大限に向上しますが、そのリスクについて注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8494-157">Even though caching the end user’s credentials provides the best user experience, you must be aware of the risks involved.</span></span>

<span data-ttu-id="f8494-158">資格情報のキャッシュが有効になっている場合、エンドユーザーのドメイン資格情報は、Windows Credential Manager 内の元に戻せる形式で格納されます。</span><span class="sxs-lookup"><span data-stu-id="f8494-158">When credential caching is enabled, the end user’s domain credential is stored in a reversible format within the Windows Credential Manager.</span></span> <span data-ttu-id="f8494-159">このため、攻撃者は、システムレベルプロセスまたはエンドユーザープロセスとして実行されるツールを作成し、エンドユーザーの資格情報を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="f8494-159">As a result, an attacker could write a tool that runs as either a system level process or an end user process and that retrieves the end user's credentials.</span></span> <span data-ttu-id="f8494-160">このリスクを軽減するには、DisablePasswordSaving を**Enabled**に設定します。</span><span class="sxs-lookup"><span data-stu-id="f8494-160">You can only lessen this risk by setting DisablePasswordSaving to **Enabled**.</span></span>

<span data-ttu-id="f8494-161">この問題は、MED-V 認証を無効にしたときに、ターミナルサービスのポリシー設定が有効になっている場合にも発生します。</span><span class="sxs-lookup"><span data-stu-id="f8494-161">This same concern exists when MED-V authentication is disabled but the Terminal Services policy setting is enabled.</span></span>

## <span data-ttu-id="f8494-162">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f8494-162">Related topics</span></span>


[<span data-ttu-id="f8494-163">MED-V 操作のセキュリティのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="f8494-163">Security Best Practices for MED-V Operations</span></span>](security-best-practices-for-med-v-operations.md)









