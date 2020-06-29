---
title: AGPM サーバー接続を構成する
description: AGPM サーバー接続を構成する
author: dansimp
ms.assetid: bbbb15e8-35e7-403c-b695-7a6ebeb87839
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9b6b065b9855c6edf44456026baa32e8d9a4674f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819074"
---
# <span data-ttu-id="5ff38-103">AGPM サーバー接続を構成する</span><span class="sxs-lookup"><span data-stu-id="5ff38-103">Configure AGPM Server Connections</span></span>


<span data-ttu-id="5ff38-104">グループポリシー管理者は、各グループポリシーオブジェクト (GPO) のすべてのバージョンを中央のアーカイブに保存して、展開されたバージョンの各 GPO にすぐに影響を与えることなく、Gpo をオフラインで表示したり、変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5ff38-104">All versions of each controlled Group Policy Object (GPO) are stored in a central archive so that Group Policy administrators can view and modify GPOs offline without immediately impacting the deployed version of each GPO.</span></span>

<span data-ttu-id="5ff38-105">AGPM 管理者 (フルコントロール) の役割を持つユーザーアカウント、これらの手順で使用された GPO を作成した承認者のユーザーアカウント、または高度なグループポリシー管理 (AGPM) で必要なアクセス許可を持つユーザーアカウントは、すべてのグループポリシー管理者のアーカイブ場所を一元的に構成するために必要な手順です。</span><span class="sxs-lookup"><span data-stu-id="5ff38-105">A user account with the AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO used in these procedures, or a user account with the necessary permissions in Advanced Group Policy Management (AGPM) is required to complete these procedures for centrally configuring archive locations for all Group Policy administrators.</span></span> <span data-ttu-id="5ff38-106">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ff38-106">Review the details in "Additional considerations" in this topic.</span></span>

## <span data-ttu-id="5ff38-107">AGPM サーバー接続を構成する</span><span class="sxs-lookup"><span data-stu-id="5ff38-107">Configuring AGPM Server connections</span></span>


<span data-ttu-id="5ff38-108">AGPM 管理者は、関連付けられた設定を一元的に構成することで、すべてのグループポリシー管理者が同じ AGPM サーバーに接続することを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5ff38-108">As an AGPM Administrator, you can ensure that all Group Policy administrators connect to the same AGPM Server by centrally configuring the associated setting.</span></span> <span data-ttu-id="5ff38-109">環境で、一部またはすべてのドメインに別個の AGPM サーバーが必要な場合は、これらの追加の AGPM サーバーを既定の例外として構成します。</span><span class="sxs-lookup"><span data-stu-id="5ff38-109">If your environment requires separate AGPM Servers for some or all domains, configure those additional AGPM Servers as exceptions to the default.</span></span> <span data-ttu-id="5ff38-110">AGPM サーバー接続を一元的に構成しない場合、各グループポリシー管理者は、各ドメインに対して表示される AGPM サーバーを手動で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ff38-110">If you do not centrally configure AGPM Server connections, each Group Policy administrator must manually configure the AGPM Server to be displayed for each domain.</span></span>

-   [<span data-ttu-id="5ff38-111">すべてのグループポリシー管理者に対して AGPM サーバー接続を構成する</span><span class="sxs-lookup"><span data-stu-id="5ff38-111">Configure an AGPM Server connection for all Group Policy administrators</span></span>](#bkmk-defaultarchiveloc)

-   [<span data-ttu-id="5ff38-112">すべてのグループポリシー管理者に対して、追加の AGPM サーバー接続を構成する</span><span class="sxs-lookup"><span data-stu-id="5ff38-112">Configure additional AGPM Server connections for all Group Policy administrators</span></span>](#bkmk-additionalarchiveloc)

-   [<span data-ttu-id="5ff38-113">アカウントの AGPM サーバー接続を手動で構成する</span><span class="sxs-lookup"><span data-stu-id="5ff38-113">Manually configure an AGPM Server connection for your account</span></span>](#bkmk-manuallyconfigurearchiveloc)

### <a href="" id="bkmk-defaultarchiveloc"></a>

**<span data-ttu-id="5ff38-114">すべてのグループポリシー管理者に対して AGPM サーバー接続を構成するには</span><span class="sxs-lookup"><span data-stu-id="5ff38-114">To configure an AGPM Server connection for all Group Policy administrators</span></span>**

1.  <span data-ttu-id="5ff38-115">[**グループポリシー管理コンソール**] ツリーで、すべてのグループポリシー管理者に適用される GPO を編集します。</span><span class="sxs-lookup"><span data-stu-id="5ff38-115">In the **Group Policy Management Console** tree, edit a GPO that is applied to all Group Policy administrators.</span></span> <span data-ttu-id="5ff38-116">詳細については、「 [GPO を編集する](editing-a-gpo-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ff38-116">(For more information, see [Editing a GPO](editing-a-gpo-agpm40.md).)</span></span>

2.  <span data-ttu-id="5ff38-117">[**グループポリシー管理エディター** ] ウィンドウで、[**ユーザーの構成**]、[**ポリシー**]、[**管理用テンプレート**]、[Windows コンポーネント]、[ **AGPM**] の**各項目**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ff38-117">In the **Group Policy Management Editor** window, click **User Configuration**, **Policies**, **Administrative Templates**, **Windows Components**, and **AGPM**.</span></span>

3.  <span data-ttu-id="5ff38-118">詳細ウィンドウで、[ **agpm: 既定の AGPM サーバーを指定してください (すべてのドメイン)**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ff38-118">In the details pane, double-click **AGPM: Specify default AGPM Server (all domains)**.</span></span>

4.  <span data-ttu-id="5ff38-119">[**プロパティ**] ウィンドウで、[**有効**] チェックボックスをオンにし、完全修飾コンピューター名とポート (たとえば、server.contoso.com:4600) を入力します。</span><span class="sxs-lookup"><span data-stu-id="5ff38-119">In the **Properties** window, select the **Enabled** check box, and type the fully-qualified computer name and port (for example, server.contoso.com:4600).</span></span>

5.  <span data-ttu-id="5ff38-120">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ff38-120">Click **OK**.</span></span> <span data-ttu-id="5ff38-121">追加の AGPM サーバー接続を構成する場合以外は、[**グループポリシー管理エディター** ] ウィンドウを閉じて、GPO を展開します。</span><span class="sxs-lookup"><span data-stu-id="5ff38-121">Unless you want to configure additional AGPM Server connections, close the **Group Policy Management Editor** window and deploy the GPO.</span></span> <span data-ttu-id="5ff38-122">(詳細については、「 [GPO の展開](deploy-a-gpo-agpm40.md)」を参照してください)。グループポリシーが更新されると、すべてのグループポリシーの管理者に対して AGPM サーバー接続が構成されます。</span><span class="sxs-lookup"><span data-stu-id="5ff38-122">(For more information, see [Deploy a GPO](deploy-a-gpo-agpm40.md).) When Group Policy is updated, the AGPM Server connection is configured for all Group Policy administrators.</span></span>

### <a href="" id="bkmk-additionalarchiveloc"></a>

**<span data-ttu-id="5ff38-123">すべてのグループポリシー管理者に対して、追加の AGPM サーバー接続を構成するには</span><span class="sxs-lookup"><span data-stu-id="5ff38-123">To configure additional AGPM Server connections for all Group Policy administrators</span></span>**

1.  <span data-ttu-id="5ff38-124">AGPM サーバー接続が構成されていない場合は、上記の手順に従って、すべてのドメインに対して既定の AGPM サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="5ff38-124">If no AGPM Server connection has been configured, follow the preceding procedure to configure a default AGPM Server for all domains.</span></span>

2.  <span data-ttu-id="5ff38-125">一部またはすべてのドメイン (既定の AGPM サーバーを上書きします) に対して別個の AGPM サーバーを構成するには、[**グループポリシー管理コンソール**] ツリーで、すべてのグループポリシー管理者に適用される GPO を編集します。</span><span class="sxs-lookup"><span data-stu-id="5ff38-125">To configure separate AGPM Servers for some or all domains (overriding the default AGPM Server), in the **Group Policy Management Console** tree, edit a GPO that is applied to all Group Policy administrators.</span></span> <span data-ttu-id="5ff38-126">詳細については、「 [GPO を編集する](editing-a-gpo-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ff38-126">(For more information, see [Editing a GPO](editing-a-gpo-agpm40.md).)</span></span>

3.  <span data-ttu-id="5ff38-127">[**グループポリシー管理エディター** ] ウィンドウで、[**ユーザーの構成**]、[**ポリシー**]、[**管理用テンプレート**]、[ **Windows コンポーネント**]、[ **AGPM**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ff38-127">In the **Group Policy Management Editor** window, click **User Configuration**, **Policies**, **Administrative Templates**, **Windows Components**, and then **AGPM**.</span></span>

4.  <span data-ttu-id="5ff38-128">詳細ウィンドウで、 **agpm: Agpm サーバーを指定**します。</span><span class="sxs-lookup"><span data-stu-id="5ff38-128">In the details pane, double-click **AGPM: Specify AGPM Servers**.</span></span>

5.  <span data-ttu-id="5ff38-129">[**プロパティ**] ウィンドウで、[**有効**] チェックボックスをオンにし、[**表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ff38-129">In the **Properties** window, select the **Enabled** check box, and click **Show**.</span></span>

6.  <span data-ttu-id="5ff38-130">[**コンテンツの表示**] ウィンドウで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5ff38-130">In the **Show Contents** window:</span></span>

    1.  <span data-ttu-id="5ff38-131">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ff38-131">Click **Add**.</span></span>

    2.  <span data-ttu-id="5ff38-132">[**値の名前**] には、ドメイン名 (server1.contoso.com など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="5ff38-132">For **Value Name**, type the domain name (for example, server1.contoso.com).</span></span>

    3.  <span data-ttu-id="5ff38-133">**値**には、このドメインに使用する AGPM サーバー名とポート (たとえば、server2.contoso.com:4600) を入力して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ff38-133">For **Value**, type the AGPM Server name and port to use for this domain (for example, server2.contoso.com:4600), and then click **OK**.</span></span> <span data-ttu-id="5ff38-134">(既定では、AGPM サービスはポート4600をリッスンします。</span><span class="sxs-lookup"><span data-stu-id="5ff38-134">(By default, the AGPM Service listens on port 4600.</span></span> <span data-ttu-id="5ff38-135">別のポートを使用する場合は、「 [AGPM サービスを変更](modify-the-agpm-service-agpm40.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ff38-135">To use a different port, see [Modify the AGPM Service](modify-the-agpm-service-agpm40.md).)</span></span>

    4.  <span data-ttu-id="5ff38-136">既定の AGPM サーバーを使用しないドメインごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5ff38-136">Repeat for each domain not using the default AGPM Server.</span></span>

7.  <span data-ttu-id="5ff38-137">[ **OK** ] をクリックして、[コンテンツと**プロパティ**の**表示**] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5ff38-137">Click **OK** to close the **Show Contents** and **Properties** windows.</span></span>

8.  <span data-ttu-id="5ff38-138">[**グループポリシー管理エディター** ] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5ff38-138">Close the **Group Policy Management Editor** window.</span></span> <span data-ttu-id="5ff38-139">(詳細については、「 [GPO の展開](deploy-a-gpo-agpm40.md)」を参照してください)。グループポリシーが更新されると、すべてのグループポリシーの管理者に対して新しい AGPM サーバー接続が構成されます。</span><span class="sxs-lookup"><span data-stu-id="5ff38-139">(For more information, see [Deploy a GPO](deploy-a-gpo-agpm40.md).) When Group Policy is updated, the new AGPM Server connections are configured for all Group Policy administrators.</span></span>

### <a href="" id="bkmk-manuallyconfigurearchiveloc"></a>

<span data-ttu-id="5ff38-140">AGPM サーバー接続を一元的に構成している場合、すべてのグループポリシー管理者は手動で構成するオプションは利用できません。</span><span class="sxs-lookup"><span data-stu-id="5ff38-140">If you have centrally configured the AGPM Server connection, the option to manually configure it is unavailable for all Group Policy administrators.</span></span>

**<span data-ttu-id="5ff38-141">アカウントに表示する AGPM サーバーを手動で構成するには</span><span class="sxs-lookup"><span data-stu-id="5ff38-141">To manually configure which AGPM Server to display for your account</span></span>**

1.  <span data-ttu-id="5ff38-142">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ff38-142">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="5ff38-143">詳細ウィンドウで、[ **AGPM サーバー** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5ff38-143">In the details pane, click the **AGPM Server** tab.</span></span>

3.  <span data-ttu-id="5ff38-144">このドメイン (たとえば、server.contoso.com) で使用されているアーカイブと、AGPM サービスがリッスンするポート (既定では、ポート 4600) を管理する AGPM サーバーの完全修飾コンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="5ff38-144">Enter the fully-qualified computer name for the AGPM Server that manages the archive used for this domain (for example, server.contoso.com) and the port on which the AGPM Service listens (by default, port 4600).</span></span>

4.  <span data-ttu-id="5ff38-145">[**適用**] をクリックし、[**はい**] をクリックして確認します。</span><span class="sxs-lookup"><span data-stu-id="5ff38-145">Click **Apply**, then click **Yes** to confirm.</span></span>

### <span data-ttu-id="5ff38-146">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="5ff38-146">Additional considerations</span></span>

-   <span data-ttu-id="5ff38-147">すべてのグループポリシーの管理者に対して、AGPM サーバー接続を一元的に構成するための手順を実行するには、GPO の編集と展開が可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ff38-147">You must be able to edit and deploy a GPO to perform the procedures for centrally configuring AGPM Server connections for all Group Policy administrators.</span></span> <span data-ttu-id="5ff38-148">詳細については、「 [gpo を編集](editing-a-gpo-agpm40.md)する」と「 [gpo を展開](deploy-a-gpo-agpm40.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ff38-148">See [Editing a GPO](editing-a-gpo-agpm40.md) and [Deploy a GPO](deploy-a-gpo-agpm40.md) for additional detail.</span></span>

-   <span data-ttu-id="5ff38-149">選択した AGPM サーバーによって、[**コンテンツ**] タブに表示される gpo と、[**ドメイン委任**] タブの設定が適用される場所が決定されます。</span><span class="sxs-lookup"><span data-stu-id="5ff38-149">The selected AGPM Server determines which GPOs are displayed on the **Contents** tab and to what location the **Domain Delegation** tab settings are applied.</span></span> <span data-ttu-id="5ff38-150">管理用テンプレートで一元管理されていない場合は、各グループポリシー管理者がこの設定を構成して、ドメインの AGPM サーバーを指すようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ff38-150">If not centrally managed through the Administrative template, each Group Policy administrator must configure this setting to point to the AGPM Server for the domain.</span></span>

-   <span data-ttu-id="5ff38-151">グループポリシー Creator Owners グループのメンバーシップは制限されている必要があります。 soit は、Gpo へのアクセスの AGPM 管理を回避するために使用されることはありません。</span><span class="sxs-lookup"><span data-stu-id="5ff38-151">Membership in the Group Policy Creator Owners group should be restricted, soit is not used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="5ff38-152">(**グループポリシー管理コンソール**で、gpo を管理するフォレストとドメインの [**グループポリシーオブジェクト**] をクリックし、[**委任**] をクリックして、組織のニーズに合わせて設定を構成します)。</span><span class="sxs-lookup"><span data-stu-id="5ff38-152">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

### <span data-ttu-id="5ff38-153">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="5ff38-153">Additional references</span></span>

-   [<span data-ttu-id="5ff38-154">高度なグループ ポリシーの管理の構成</span><span class="sxs-lookup"><span data-stu-id="5ff38-154">Configuring Advanced Group Policy Management</span></span>](configuring-advanced-group-policy-management-agpm40.md)

 

 





