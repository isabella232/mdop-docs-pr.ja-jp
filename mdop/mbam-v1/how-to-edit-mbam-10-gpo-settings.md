---
title: MBAM 1.0 GPO 設定を編集する方法
description: MBAM 1.0 GPO 設定を編集する方法
author: dansimp
ms.assetid: 03d12fbc-4302-43fc-9b38-440607d778a1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 824fbc2fe0d8f2b00c32de177733e4e327cf4d44
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824284"
---
# <span data-ttu-id="62d7c-103">MBAM 1.0 GPO 設定を編集する方法</span><span class="sxs-lookup"><span data-stu-id="62d7c-103">How to Edit MBAM 1.0 GPO Settings</span></span>


<span data-ttu-id="62d7c-104">Microsoft BitLocker の管理と監視 (MBAM) を正常に展開するには、まず Microsoft BitLocker の管理と監視の実装で使用するグループポリシーを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62d7c-104">To successfully deploy Microsoft BitLocker Administration and Monitoring (MBAM), you must first determine the Group Policies that you will use in your implementation of Microsoft BitLocker Administration and Monitoring.</span></span> <span data-ttu-id="62d7c-105">利用可能なさまざまなポリシーの詳細については、「 [MBAM 1.0 グループポリシーの要件の計画](planning-for-mbam-10-group-policy-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62d7c-105">For more information about the various available policies, see [Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md).</span></span> <span data-ttu-id="62d7c-106">使用するポリシーを決定したら、MBAM ポリシー設定が含まれている1つまたは複数のグループポリシーオブジェクト (GPO) を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62d7c-106">After you have determined the policies that you are going to use, you then must modify one or more Group Policy Objects (GPO) that include the MBAM policy settings.</span></span>

<span data-ttu-id="62d7c-107">次の手順では、推奨される基本的なグループポリシーオブジェクト (GPO) 設定を構成して、MBAM で組織のクライアントコンピューターの BitLocker 暗号化を管理できるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="62d7c-107">The following steps describe how to configure the basic, recommended Group Policy object (GPO) settings to enable MBAM to manage BitLocker encryption for your organization’s client computers.</span></span>

**<span data-ttu-id="62d7c-108">MBAM クライアント GPO 設定を編集するには</span><span class="sxs-lookup"><span data-stu-id="62d7c-108">To edit the MBAM Client GPO settings</span></span>**

1.  <span data-ttu-id="62d7c-109">MBAM グループポリシーテンプレートがインストールされているコンピューターで、MBAM サービスが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="62d7c-109">On a computer that has MBAM Group Policy template installed, make sure that MBAM services are enabled.</span></span>

2.  <span data-ttu-id="62d7c-110">グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) MDOP 製品を使用して、次の操作を行います。 [**コンピューターの構成**]、[**ポリシー**]、[**管理用テンプレート**] の順にクリックし、[ **Windows コンポーネント**] をクリックして、[ **MDOP (BitLocker 管理)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62d7c-110">Use the Group Policy Management Console (GPMC.msc) or the Advanced Group Policy Management (AGPM) MDOP product for these actions: Select **Computer configuration**, choose **Policies**, click **Administrative Templates**, select **Windows Components**, and then click **MDOP MBAM (BitLocker Management)**.</span></span>

3.  <span data-ttu-id="62d7c-111">クライアントコンピューターで MBAM クライアントサービスを有効にするために必要なグループポリシーオブジェクト設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="62d7c-111">Edit the Group Policy Object settings that are required to enable MBAM Client services on client computers.</span></span> <span data-ttu-id="62d7c-112">次の表のポリシーごとに、[**ポリシーグループ**] を選択し、**ポリシー**をクリックして、**設定**を構成します。</span><span class="sxs-lookup"><span data-stu-id="62d7c-112">For each policy in the table that follows, select **Policy Group**, click the **Policy**, and then configure the **Setting**.</span></span>

    <span data-ttu-id="62d7c-113">ポリシーグループ</span><span class="sxs-lookup"><span data-stu-id="62d7c-113">Policy Group</span></span>

    <span data-ttu-id="62d7c-114">ポリシー</span><span class="sxs-lookup"><span data-stu-id="62d7c-114">Policy</span></span>

    <span data-ttu-id="62d7c-115">設定</span><span class="sxs-lookup"><span data-stu-id="62d7c-115">Setting</span></span>

    <span data-ttu-id="62d7c-116">クライアントの管理</span><span class="sxs-lookup"><span data-stu-id="62d7c-116">Client Management</span></span>

    <span data-ttu-id="62d7c-117">MBAM サービスを設定する</span><span class="sxs-lookup"><span data-stu-id="62d7c-117">Configure MBAM Services</span></span>

    <span data-ttu-id="62d7c-118">有効。</span><span class="sxs-lookup"><span data-stu-id="62d7c-118">Enabled.</span></span> <span data-ttu-id="62d7c-119">**Mbam Recovery と Hardware service のエンドポイント**を設定し、**保存する BitLocker 回復情報を選択**します。</span><span class="sxs-lookup"><span data-stu-id="62d7c-119">Set **MBAM Recovery and Hardware service endpoint** and **Select BitLocker recovery information to store**.</span></span>

    <span data-ttu-id="62d7c-120">**Mbam コンプライアンスサービスのエンドポイント**を設定し、**状態レポートの頻度 (分) を入力**します。</span><span class="sxs-lookup"><span data-stu-id="62d7c-120">Set **MBAM compliance service endpoint** and **Enter status report frequency in (minutes)**.</span></span>

    <span data-ttu-id="62d7c-121">ハードウェアの互換性のチェックを許可する</span><span class="sxs-lookup"><span data-stu-id="62d7c-121">Allow hardware compatibility checking</span></span>

    <span data-ttu-id="62d7c-122">無効になります。</span><span class="sxs-lookup"><span data-stu-id="62d7c-122">Disabled.</span></span> <span data-ttu-id="62d7c-123">このポリシーは既定で有効になっていますが、基本的な MBAM の実装では必要ありません。</span><span class="sxs-lookup"><span data-stu-id="62d7c-123">This policy is enabled by default, but is not needed for a basic MBAM implementation.</span></span>

    <span data-ttu-id="62d7c-124">オペレーティングシステムドライブ</span><span class="sxs-lookup"><span data-stu-id="62d7c-124">Operating System Drive</span></span>

    <span data-ttu-id="62d7c-125">オペレーティングシステムドライブの暗号化の設定</span><span class="sxs-lookup"><span data-stu-id="62d7c-125">Operating system drive encryption settings</span></span>

    <span data-ttu-id="62d7c-126">有効。</span><span class="sxs-lookup"><span data-stu-id="62d7c-126">Enabled.</span></span> <span data-ttu-id="62d7c-127">**オペレーティングシステムドライブの [プロテクター] を**設定します。</span><span class="sxs-lookup"><span data-stu-id="62d7c-127">Set **Select protector for operating system drive**.</span></span> <span data-ttu-id="62d7c-128">この操作は、オペレーティングシステムドライブのデータを MBAM キー回復サーバーに保存するために必要です。</span><span class="sxs-lookup"><span data-stu-id="62d7c-128">This is required to save operating system drive data to the MBAM Key Recovery server.</span></span>

    <span data-ttu-id="62d7c-129">リムーバブルドライブ</span><span class="sxs-lookup"><span data-stu-id="62d7c-129">Removable Drive</span></span>

    <span data-ttu-id="62d7c-130">リムーバブルドライブでの BitLocker の使用を制御する</span><span class="sxs-lookup"><span data-stu-id="62d7c-130">Control Use of BitLocker on removable drives</span></span>

    <span data-ttu-id="62d7c-131">有効。</span><span class="sxs-lookup"><span data-stu-id="62d7c-131">Enabled.</span></span> <span data-ttu-id="62d7c-132">MBAM キー回復サーバーにリムーバブルドライブのデータを保存する場合は、この操作が必要です。</span><span class="sxs-lookup"><span data-stu-id="62d7c-132">This is required if MBAM will save removable drive data to the MBAM Key Recovery server.</span></span>

    <span data-ttu-id="62d7c-133">固定ドライブ</span><span class="sxs-lookup"><span data-stu-id="62d7c-133">Fixed Drive</span></span>

    <span data-ttu-id="62d7c-134">固定ドライブでの BitLocker の使用を制御する</span><span class="sxs-lookup"><span data-stu-id="62d7c-134">Control Use of BitLocker on fixed drives</span></span>

    <span data-ttu-id="62d7c-135">有効。</span><span class="sxs-lookup"><span data-stu-id="62d7c-135">Enabled.</span></span> <span data-ttu-id="62d7c-136">MBAM キー回復サーバーに固定ドライブのデータを保存する場合は、この操作が必要です。</span><span class="sxs-lookup"><span data-stu-id="62d7c-136">This is required if MBAM will save fixed drive data to the MBAM Key Recovery server.</span></span>

    <span data-ttu-id="62d7c-137">**BitLocker で保護されたドライブをどのように回復**して、**データ回復エージェントを許可**するかを選択します。</span><span class="sxs-lookup"><span data-stu-id="62d7c-137">Set **Choose how BitLocker-protected drives can be recovered** and **Allow data recovery agent**.</span></span>



~~~
**Important**  
Depending on the policies that your organization decides to deploy, you may have to configure additional policies. See [Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md) for Group Policy configuration details for all of the available MBAM GPO policy options.
~~~



## <span data-ttu-id="62d7c-138">関連トピック</span><span class="sxs-lookup"><span data-stu-id="62d7c-138">Related topics</span></span>


[<span data-ttu-id="62d7c-139">MBAM 1.0 グループ ポリシー オブジェクトの展開</span><span class="sxs-lookup"><span data-stu-id="62d7c-139">Deploying MBAM 1.0 Group Policy Objects</span></span>](deploying-mbam-10-group-policy-objects.md)









