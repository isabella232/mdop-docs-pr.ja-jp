---
title: MED-V ワークスペース パッケージ ツールを使用した MED-V ワークスペースの設定の管理
description: MED-V ワークスペース パッケージ ツールを使用した MED-V ワークスペースの設定の管理
author: dansimp
ms.assetid: e4b2c516-b9f8-44f9-9eae-caac6c2af3e7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9905c8da0f1f0678cce9587296526e8f04493c20
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826124"
---
# <span data-ttu-id="19568-103">MED-V ワークスペース パッケージ ツールを使用した MED-V ワークスペースの設定の管理</span><span class="sxs-lookup"><span data-stu-id="19568-103">Managing MED-V Workspace Settings by Using the MED-V Workspace Packager</span></span>


<span data-ttu-id="19568-104">MED-V ワークスペースパッケージャーを使って、MED-V ワークスペースの特定の設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="19568-104">You can use the MED-V Workspace Packager to manage certain settings in the MED-V workspace.</span></span>

**<span data-ttu-id="19568-105">MED-V ワークスペースで設定を管理するには</span><span class="sxs-lookup"><span data-stu-id="19568-105">To manage settings in a MED-V workspace</span></span>**

1. <span data-ttu-id="19568-106">**Med-v ワークスペースのパッケージャー**を開くには、 **[スタート**]、[**すべてのプログラム**]、[ **Microsoft Enterprise デスクトップ仮想化**]、[ **med-v workspace パッケージャー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="19568-106">To open the **MED-V Workspace Packager**, click **Start**, click **All Programs**, click **Microsoft Enterprise Desktop Virtualization**, and then click **MED-V Workspace Packager**.</span></span>

2. <span data-ttu-id="19568-107">**Med-v ワークスペースパッケージャー**のメインパネルで、[**設定の管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19568-107">On the **MED-V Workspace Packager** main panel, click **Manage Settings**.</span></span>

3. <span data-ttu-id="19568-108">[**設定の管理**] ウィンドウで、次のような med-v のワークスペース設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="19568-108">In the **Manage Settings** window, you can configure the following MED-V workspace settings:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="19568-109">MED-V ワークスペースを開始する</span><span class="sxs-lookup"><span data-stu-id="19568-109">Start MED-V workspace</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="19568-110">ユーザーのログオン時に MED-V workspace を起動するか、最初に使用するか、またはエンドユーザーが MED-V ワークスペースを開始するタイミングを決定できるようにするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="19568-110">Choose whether to start the MED-V workspace at user logon, at first use, or to let the end user decide when the MED-V workspace starts.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p><span data-ttu-id="19568-111">MED-V ワークスペースは、エンドユーザーがログオンしている場合、または、公開されたアプリケーションを開く場合や、リダイレクトが必要な URL を入力する場合など、MED-V が必要な操作を最初に実行するときに、次の2つの方法のいずれかで開始されます。</span><span class="sxs-lookup"><span data-stu-id="19568-111">The MED-V workspace starts in one of two ways: either when the end user logs on or when they first perform an action that requires MED-V, such as opening a published application or entering a URL that requires redirection.</span></span></p>
   <p><span data-ttu-id="19568-112">エンドユーザー向けにこの設定を定義するか、または MED-V の開始方法をエンドユーザーが制御できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="19568-112">You can either define this setting for the end user or let the end user control how MED-V starts.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="19568-113">注</span><span class="sxs-lookup"><span data-stu-id="19568-113">Note</span></span></strong><br/><p><span data-ttu-id="19568-114">エンドユーザーによって決定されたことを指定した場合、そのユーザーが遭遇する既定の動作は、ログオン時に MED-V ワークスペースが開始されることです。</span><span class="sxs-lookup"><span data-stu-id="19568-114">If you specify that the end user decides, the default behavior they experience is that the MED-V workspace starts when they log on.</span></span> <span data-ttu-id="19568-115">既定の設定を変更するには、通知領域の MED-V アイコンを右クリックし、[Med-v] の [ユーザー設定] を選び <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="19568-115">They can change the default by right-clicking the MED-V icon in the notification area and selecting <strong>MED-V User Settings</strong>.</span></span> <span data-ttu-id="19568-116">エンドユーザーに対してこの設定を定義した場合は、MED-V の開始方法を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="19568-116">If you define this setting for the end user, they cannot change the way in which MED-V starts.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="19568-117">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="19568-117">Networking</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="19568-118">[ <strong> ネットワーク設定] で [共有] または [ブリッジ] を選択し </strong> <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="19568-118">Select <strong>Shared</strong> or <strong>Bridged</strong> for your networking setting.</span></span> <span data-ttu-id="19568-119">既定値は [共有されてい <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="19568-119">The default is <strong>Shared</strong>.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p><strong><span data-ttu-id="19568-120">共有 </strong> - Med-v workspace は、ネットワークアドレス変換 (NAT) を使って、発信トラフィック用にホスト&#39;s IP を共有します。</span><span class="sxs-lookup"><span data-stu-id="19568-120">Shared</strong> - The MED-V workspace uses Network Address Translation (NAT) to share the host&#39;s IP for outgoing traffic.</span></span></p>
   <p><strong><span data-ttu-id="19568-121">つなぎ </strong> - ます。 med-v ワークスペースには独自のネットワークアドレスがあり、通常は DHCP 経由で取得します。</span><span class="sxs-lookup"><span data-stu-id="19568-121">Bridged</strong> - The MED-V workspace has its own network address, typically obtained through DHCP.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="19568-122">資格情報を保存する</span><span class="sxs-lookup"><span data-stu-id="19568-122">Store credentials</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="19568-123">エンドユーザーの資格情報を保存するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="19568-123">Choose whether you want to store the end user credentials.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p><span data-ttu-id="19568-124">既定の動作では、資格情報の保存機能が無効になっているため、ユーザーがログオンするたびにエンドユーザーの認証を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="19568-124">The default behavior is that credential storing is disabled so that the end user must be authenticated every time that they log on.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="19568-125">重要</span><span class="sxs-lookup"><span data-stu-id="19568-125">Important</span></span></strong><br/><p><span data-ttu-id="19568-126">エンドユーザーの資格情報をキャッシュすると、ユーザーエクスペリエンスが最大限に向上しますが、そのリスクについて注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19568-126">Even though caching the end user’s credentials provides the best user experience, you should be aware of the risks involved.</span></span></p>
   <p><span data-ttu-id="19568-127">エンドユーザーのドメイン資格情報は、Windows Credential Manager の元に戻す形式で格納されます。</span><span class="sxs-lookup"><span data-stu-id="19568-127">The end user’s domain credential is stored in a reversible format in the Windows Credential Manager.</span></span> <span data-ttu-id="19568-128">攻撃者は、パスワードを取得してユーザーの資格情報にアクセスできるプログラムを作成する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="19568-128">An attacker could write a program that retrieves the password and thus gain access to the user’s credentials.</span></span> <span data-ttu-id="19568-129">このリスクを軽減するには、エンドユーザーの資格情報の保存を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="19568-129">You can only lessen this risk by disabling the storing of end user credentials.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



4. <span data-ttu-id="19568-130">[**名前を付けて保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="19568-130">Click **Save as…**</span></span> <span data-ttu-id="19568-131">指定したフォルダーの更新された設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="19568-131">to save the updated configuration settings in the specified folder.</span></span> <span data-ttu-id="19568-132">MED-V は、更新された設定を含むレジストリファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="19568-132">MED-V creates a registry file that contains the updated settings.</span></span> <span data-ttu-id="19568-133">グループポリシーを使用して、更新されたレジストリファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="19568-133">Deploy the updated registry file by using Group Policy.</span></span> <span data-ttu-id="19568-134">グループポリシーの使用方法の詳細については、「[グループポリシーソフトウェアのインストール](https://go.microsoft.com/fwlink/?LinkId=195931)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=195931) 。</span><span class="sxs-lookup"><span data-stu-id="19568-134">For more information about how to use Group Policy, see [Group Policy Software Installation](https://go.microsoft.com/fwlink/?LinkId=195931) (https://go.microsoft.com/fwlink/?LinkId=195931).</span></span>

   <span data-ttu-id="19568-135">また、指定されたフォルダーに Windows PowerShell スクリプトを作成します。このスクリプトは、この更新されたレジストリファイルを再作成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="19568-135">MED-V also creates a Windows PowerShell script in the specified folder that you can use to re-create this updated registry file.</span></span>

## <span data-ttu-id="19568-136">関連トピック</span><span class="sxs-lookup"><span data-stu-id="19568-136">Related topics</span></span>


[<span data-ttu-id="19568-137">MED-V ワークスペースの構成設定の管理</span><span class="sxs-lookup"><span data-stu-id="19568-137">Managing MED-V Workspace Configuration Settings</span></span>](managing-med-v-workspace-configuration-settings.md)

[<span data-ttu-id="19568-138">MED-V ワークスペースの設定を管理する</span><span class="sxs-lookup"><span data-stu-id="19568-138">Manage MED-V Workspace Settings</span></span>](manage-med-v-workspace-settings.md)









