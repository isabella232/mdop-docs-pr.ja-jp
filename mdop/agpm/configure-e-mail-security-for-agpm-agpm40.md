---
title: AGPM の電子メール セキュリティを構成する
description: AGPM の電子メール セキュリティを構成する
author: dansimp
ms.assetid: b9c48894-0a10-4d03-8027-50ed3b02485a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a384c2a21f912ca7ec55a5e4c74ca7062bfe864c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818994"
---
# <span data-ttu-id="2b6dd-103">AGPM の電子メール セキュリティを構成する</span><span class="sxs-lookup"><span data-stu-id="2b6dd-103">Configure E-Mail Security for AGPM</span></span>


<span data-ttu-id="2b6dd-104">既定では、高度なグループポリシー管理 (AGPM) での操作のために送信されたメール通知は暗号化されず、SMTP ポート25経由で送信されます。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-104">By default, e-mail notifications sent because of actions in Advanced Group Policy Management (AGPM) are not encrypted and are sent through SMTP port 25.</span></span> <span data-ttu-id="2b6dd-105">ただし、レジストリ設定を使用して、Secure Sockets Layer (SSL) 暗号化を使用するかどうか、どの SMTP ポートを使うかを指定することによって、AGPM の電子メールセキュリティを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-105">However, you can configure e-mail security for AGPM by using registry settings to specify whether to use Secure Sockets Layer (SSL) encryption and which SMTP port to use.</span></span>

<span data-ttu-id="2b6dd-106">AGPM メール通知を暗号化することにより、組織のセキュリティに関する機密情報を明らかにしているユーザーを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-106">By encrypting AGPM e-mail notifications, you can better protect those that could reveal sensitive information about your organization’s security.</span></span> <span data-ttu-id="2b6dd-107">電子メール通知は、リモートメールサーバー経由で中継され、一部のコンプライアンス規則で必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-107">Encrypting e-mail notifications is recommended when they are being relayed through remote mail servers, and may be required by some compliance regulations.</span></span>

<span data-ttu-id="2b6dd-108">**注意** レジストリの編集を誤ると、システムに重大な損害を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-108">**Caution** Incorrectly editing the registry may severely damage your system.</span></span> <span data-ttu-id="2b6dd-109">レジストリに変更を加える前に、コンピューター上の重要なデータをバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-109">Before making changes to the registry, you should back up any valued data on the computer.</span></span>

 

<span data-ttu-id="2b6dd-110">AGPM 管理者 (フルコントロール) の役割を持つユーザーアカウント、これらの手順で使用したグループポリシーオブジェクト (GPO) を作成した承認者のユーザーアカウント、または AGPM で必要なアクセス許可を持つユーザーアカウントは、これらの手順を完了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-110">A user account that has the AGPM Administrator (Full Control) role, the user account of the Approver who created the Group Policy Object (GPO) used in these procedures, or a user account that has the necessary permissions in AGPM is required to complete these procedures.</span></span> <span data-ttu-id="2b6dd-111">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-111">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="2b6dd-112">グループポリシーの基本設定を使用して、AGPM の電子メールセキュリティを構成するには</span><span class="sxs-lookup"><span data-stu-id="2b6dd-112">To configure e-mail security for AGPM by using Group Policy preferences</span></span>**

1.  <span data-ttu-id="2b6dd-113">[**グループポリシー管理コンソール**] ツリーで、メールのセキュリティを構成するすべての AGPM サーバーに適用される GPO を編集します。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-113">In the **Group Policy Management Console** tree, edit a GPO that is applied to all AGPM Servers for which you want to configure e-mail security.</span></span> <span data-ttu-id="2b6dd-114">詳細については、「 [GPO を編集する](editing-a-gpo-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-114">(For more information, see [Editing a GPO](editing-a-gpo-agpm40.md).)</span></span>

2.  <span data-ttu-id="2b6dd-115">[**グループポリシー管理エディター** ] ウィンドウで、[**コンピューターの構成**]、[**基本**設定]、[ **Windows の設定**]、[**レジストリ**フォルダー] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-115">In the **Group Policy Management Editor** window, expand the **Computer Configuration**, **Preferences**, **Windows Settings**, and **Registry** folders.</span></span>

3.  <span data-ttu-id="2b6dd-116">コンソールツリーで、[**レジストリ**] を右クリックし、[**新規作成**] をポイントして、[**コレクションアイテム**] をクリックし、「 **AGPM メールのセキュリティ**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-116">In the console tree, right-click **Registry**, point to **New**, click **Collection Item**, and type **AGPM e-mail security**.</span></span>

4.  <span data-ttu-id="2b6dd-117">暗号化を有効にするためのレジストリ設定項目を作成します。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-117">Create a Registry preference item to turn on encryption:</span></span>

    1.  <span data-ttu-id="2b6dd-118">コンソールツリーで、[ **AGPM メールセキュリティ**] を右クリックし、[**新規作成**] をポイントして、[**レジストリアイテム**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-118">In the console tree, right-click **AGPM e-mail security**, point to **New**, and then click **Registry Item**.</span></span>

    2.  <span data-ttu-id="2b6dd-119">[**新しいレジストリのプロパティ**] ダイアログボックスで、[**更新**] アクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-119">In the **New Registry Properties** dialog box, select the **Update** action.</span></span>

    3.  <span data-ttu-id="2b6dd-120">**Hive**の場合、[ **HKEY \ _LOCAL \ _MACHINE**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-120">For **Hive**, select **HKEY\_LOCAL\_MACHINE**.</span></span>

    4.  <span data-ttu-id="2b6dd-121">[**キーパス**] に「**ソフトウェア**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-121">For **Key Path**, type **SOFTWARE\\Microsoft\\AGPM**.</span></span>

    5.  <span data-ttu-id="2b6dd-122">[**値の名前**] に「 **EncryptSmtp**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-122">For **Value name**, type **EncryptSmtp**.</span></span>

    6.  <span data-ttu-id="2b6dd-123">**値の種類**については、[ **REG \ _DWORD**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-123">For **Value type**, select **REG\_DWORD**.</span></span>

    7.  <span data-ttu-id="2b6dd-124">[**基準**] で [**小数点揃え**] を選択し、[**値のデータ**] には「 **1** 」を入力して SSL 暗号化を使用するか、または [ **0** ] をクリックして暗号化なしでメールを送信します。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-124">For **Base**, select **Decimal**, and for **Value data**, type **1** to use SSL encryption, or **0** to let e-mail to be sent without encryption.</span></span> <span data-ttu-id="2b6dd-125">既定では、暗号化されていないメールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-125">By default, e-mail is sent without encryption.</span></span> <span data-ttu-id="2b6dd-126">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-126">Click **OK**.</span></span>

5.  <span data-ttu-id="2b6dd-127">SMTP ポートを指定するレジストリ設定項目を作成します。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-127">Create a Registry preference item to specify the SMTP port:</span></span>

    1.  <span data-ttu-id="2b6dd-128">コンソールツリーで、[ **AGPM メールセキュリティ**] を右クリックし、[**新規作成**] をポイントして、[**レジストリアイテム**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-128">In the console tree, right-click **AGPM E-mail security**, point to **New**, and then click **Registry Item**.</span></span>

    2.  <span data-ttu-id="2b6dd-129">[**新しいレジストリのプロパティ**] ダイアログボックスで、[**更新**] アクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-129">In the **New Registry Properties** dialog box, select the **Update** action.</span></span>

    3.  <span data-ttu-id="2b6dd-130">**Hive**の場合、[ **HKEY \ _LOCAL \ _MACHINE**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-130">For **Hive**, select **HKEY\_LOCAL\_MACHINE**.</span></span>

    4.  <span data-ttu-id="2b6dd-131">[**キーパス**] ダイアログボックスに「**ソフトウェア**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-131">For **Key Path** dialog box, type **SOFTWARE\\Microsoft\\AGPM**.</span></span>

    5.  <span data-ttu-id="2b6dd-132">[**値の名前**] に「 **smtpport**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-132">For **Value name**, type **SmtpPort**.</span></span>

    6.  <span data-ttu-id="2b6dd-133">**値の種類**については、[ **REG \ _DWORD**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-133">For **Value type**, select **REG\_DWORD**.</span></span>

    7.  <span data-ttu-id="2b6dd-134">[**ベース**] で [**小数点**] を選択し、[**値のデータ**] には SMTP ポートのポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-134">For **Base**, select **Decimal**, and for **Value data**, type a port number for the SMTP port.</span></span> <span data-ttu-id="2b6dd-135">既定では、暗号化が有効になっていない場合は、ポート25、SSL 暗号化が有効になっている場合は [ポート 587] となります。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-135">By default, the SMTP port is port 25 if encryption is not enabled or port 587 if SSL encryption is enabled.</span></span> <span data-ttu-id="2b6dd-136">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-136">Click **OK**.</span></span>

6.  <span data-ttu-id="2b6dd-137">[**グループポリシー管理エディター** ] ウィンドウを閉じて、GPO をチェックインして展開します。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-137">Close the **Group Policy Management Editor** window, and then check in and deploy the GPO.</span></span> <span data-ttu-id="2b6dd-138">詳細については、「 [GPO の展開](deploy-a-gpo-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-138">For more information, see [Deploy a GPO](deploy-a-gpo-agpm40.md).</span></span>

### <span data-ttu-id="2b6dd-139">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="2b6dd-139">Additional considerations</span></span>

-   <span data-ttu-id="2b6dd-140">グループポリシーの基本設定を使用して、レジストリ設定を構成するために GPO の編集と展開ができる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-140">You must be able to edit and deploy a GPO to configure registry settings by using Group Policy Preferences.</span></span> <span data-ttu-id="2b6dd-141">詳細については、「 [gpo を編集](editing-a-gpo-agpm40.md)する」と「 [gpo を展開](deploy-a-gpo-agpm40.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b6dd-141">See [Editing a GPO](editing-a-gpo-agpm40.md) and [Deploy a GPO](deploy-a-gpo-agpm40.md) for additional detail.</span></span>

### <span data-ttu-id="2b6dd-142">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="2b6dd-142">Additional references</span></span>

-   [<span data-ttu-id="2b6dd-143">高度なグループ ポリシーの管理の構成</span><span class="sxs-lookup"><span data-stu-id="2b6dd-143">Configuring Advanced Group Policy Management</span></span>](configuring-advanced-group-policy-management-agpm40.md)

 

 





