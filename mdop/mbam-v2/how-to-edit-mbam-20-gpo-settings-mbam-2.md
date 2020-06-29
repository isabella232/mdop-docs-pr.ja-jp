---
title: MBAM 2.0 GPO 設定を編集する方法
description: MBAM 2.0 GPO 設定を編集する方法
author: dansimp
ms.assetid: f5ffa93d-b4d2-4317-8a1c-7d2be0264fe3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aaf7c7aab4baba66513edbfa2489fbe53c97dda8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824087"
---
# <span data-ttu-id="de861-103">MBAM 2.0 GPO 設定を編集する方法</span><span class="sxs-lookup"><span data-stu-id="de861-103">How to Edit MBAM 2.0 GPO Settings</span></span>


<span data-ttu-id="de861-104">Microsoft BitLocker の管理と監視 (MBAM) を正常に展開するには、まず Microsoft BitLocker の管理と監視の実装で使用するグループポリシーを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de861-104">To successfully deploy Microsoft BitLocker Administration and Monitoring (MBAM), you first have to determine the Group Policies that you will use in your implementation of Microsoft BitLocker Administration and Monitoring.</span></span> <span data-ttu-id="de861-105">使用可能なさまざまなポリシーの詳細については、「 [MBAM 2.0 グループポリシーの要件](planning-for-mbam-20-group-policy-requirements-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de861-105">See [Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md) for more information on the different policies that are available.</span></span> <span data-ttu-id="de861-106">使用するポリシーを決定したら、MBAM のポリシー設定が含まれている1つ以上のグループポリシーオブジェクト (GPO) を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de861-106">After you have determined the policies that you are going to use, you then must modify one or more Group Policy Objects (GPO) that include the policy settings for MBAM.</span></span>

<span data-ttu-id="de861-107">次の手順を使用して、組織のクライアントコンピューターの BitLocker 暗号化を MBAM で管理できるように、基本的な推奨される GPO 設定を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="de861-107">You can use the following steps to configure the basic, recommended GPO settings to enable MBAM to manage BitLocker encryption for your organization’s client computers.</span></span>

**<span data-ttu-id="de861-108">MBAM クライアント GPO 設定を編集するには</span><span class="sxs-lookup"><span data-stu-id="de861-108">To Edit MBAM Client GPO Settings</span></span>**

1.  <span data-ttu-id="de861-109">MBAM グループポリシーテンプレートがインストールされているコンピューターで、MBAM サービスが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="de861-109">On a computer that has MBAM Group Policy template installed, make sure that MBAM services are enabled.</span></span>

2.  <span data-ttu-id="de861-110">MBAM グループポリシーテンプレートがインストールされているコンピューターで、グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) の MDOP 製品を使用して、[**コンピューターの構成**]、[**ポリシー**]、[**管理用テンプレート**]、[ **Windows コンポーネント**] の順にクリックし、[ **MDOP (BitLocker 管理)**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de861-110">Using the Group Policy Management Console (GPMC.msc) or the Advanced Group Policy Management (AGPM) MDOP product on a computer with the MBAM Group Policy template installed, select **Computer configuration**, choose **Policies**, click **Administrative Templates**, select **Windows Components**, and then click **MDOP MBAM (BitLocker Management)**.</span></span>

3.  <span data-ttu-id="de861-111">クライアントコンピューターで MBAM クライアントサービスを有効にするために必要なグループポリシーオブジェクト設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="de861-111">Edit the Group Policy Object settings that are required to enable MBAM Client services on client computers.</span></span> <span data-ttu-id="de861-112">次の表のポリシーごとに、[**ポリシー] グループ**を選択し、**ポリシー**をクリックして、**設定**を構成します。</span><span class="sxs-lookup"><span data-stu-id="de861-112">For each policy in the table that follows, select **Policy Group**, click the **Policy**, and then configure the **Setting**:</span></span>

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="de861-113">ポリシーグループ</span><span class="sxs-lookup"><span data-stu-id="de861-113">Policy Group</span></span></th>
    <th align="left"><span data-ttu-id="de861-114">ポリシー</span><span class="sxs-lookup"><span data-stu-id="de861-114">Policy</span></span></th>
    <th align="left"><span data-ttu-id="de861-115">設定</span><span class="sxs-lookup"><span data-stu-id="de861-115">Setting</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="de861-116">クライアントの管理</span><span class="sxs-lookup"><span data-stu-id="de861-116">Client Management</span></span></p></td>
    <td align="left"><p><span data-ttu-id="de861-117">MBAM サービスを設定する</span><span class="sxs-lookup"><span data-stu-id="de861-117">Configure MBAM Services</span></span></p></td>
    <td align="left"><p><span data-ttu-id="de861-118">有効。</span><span class="sxs-lookup"><span data-stu-id="de861-118">Enabled.</span></span> <span data-ttu-id="de861-119"><strong>Mbam Recovery と Hardware service のエンドポイントを設定 </strong> し、 <strong> 保存する BitLocker 回復情報を選択し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="de861-119">Set <strong>MBAM Recovery and Hardware service endpoint</strong> and <strong>Select BitLocker recovery information to store</strong>.</span></span> <span data-ttu-id="de861-120"><strong>Mbam コンプライアンスサービスのエンドポイント </strong> を設定し、状態レポートの頻度 (分) を入力します。</span><span class="sxs-lookup"><span data-stu-id="de861-120">Set <strong>MBAM compliance service endpoint</strong> and Enter status report frequency in (minutes).</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="de861-121">オペレーティングシステムドライブ</span><span class="sxs-lookup"><span data-stu-id="de861-121">Operating System Drive</span></span></p></td>
    <td align="left"><p><span data-ttu-id="de861-122">オペレーティングシステムドライブの暗号化の設定</span><span class="sxs-lookup"><span data-stu-id="de861-122">Operating system drive encryption settings</span></span></p></td>
    <td align="left"><p><span data-ttu-id="de861-123">有効。</span><span class="sxs-lookup"><span data-stu-id="de861-123">Enabled.</span></span> <span data-ttu-id="de861-124"><strong>オペレーティングシステムドライブの [プロテクター] を設定 </strong> します。</span><span class="sxs-lookup"><span data-stu-id="de861-124">Set <strong>Select protector for operating system drive</strong>.</span></span> <span data-ttu-id="de861-125">オペレーティングシステムドライブのデータを MBAMKey Recovery サーバーに保存するために必要です。</span><span class="sxs-lookup"><span data-stu-id="de861-125">Required to save operating system drive data to the MBAMKey Recovery server.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="de861-126">リムーバブルドライブ</span><span class="sxs-lookup"><span data-stu-id="de861-126">Removable Drive</span></span></p></td>
    <td align="left"><p><span data-ttu-id="de861-127">リムーバブルドライブでの BitLocker の使用を制御する</span><span class="sxs-lookup"><span data-stu-id="de861-127">Control Use of BitLocker on removable drives</span></span></p></td>
    <td align="left"><p><span data-ttu-id="de861-128">有効。</span><span class="sxs-lookup"><span data-stu-id="de861-128">Enabled.</span></span> <span data-ttu-id="de861-129">MBAM キー回復サーバーにリムーバブルドライブのデータを保存する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="de861-129">Required if MBAM will save removable drive data to the MBAM Key Recovery server.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="de861-130">固定ドライブ</span><span class="sxs-lookup"><span data-stu-id="de861-130">Fixed Drive</span></span></p></td>
    <td align="left"><p><span data-ttu-id="de861-131">固定ドライブでの BitLocker の使用を制御する</span><span class="sxs-lookup"><span data-stu-id="de861-131">Control Use of BitLocker on fixed drives</span></span></p></td>
    <td align="left"><p><span data-ttu-id="de861-132">有効。</span><span class="sxs-lookup"><span data-stu-id="de861-132">Enabled.</span></span> <span data-ttu-id="de861-133">MBAM キー回復サーバーに固定ドライブのデータを保存する場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="de861-133">Required if MBAM will save fixed drive data to the MBAM Key Recovery server.</span></span></p>
    <p><span data-ttu-id="de861-134"><strong>BitLocker で保護されたドライブをどのように回復 </strong> して、データ回復エージェントを許可するかを選択し <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="de861-134">Set <strong>Choose how BitLocker-protected drives can be recovered</strong> and <strong>Allow data recovery agent</strong>.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
**Important**  
Depending on the policies that your organization decides to deploy, you may have to configure additional policies. See [Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md) for Group Policy configuration details for all of the available MBAM GPO policy options.
~~~



## <span data-ttu-id="de861-135">関連トピック</span><span class="sxs-lookup"><span data-stu-id="de861-135">Related topics</span></span>


[<span data-ttu-id="de861-136">MBAM 2.0 グループ ポリシー オブジェクトの展開</span><span class="sxs-lookup"><span data-stu-id="de861-136">Deploying MBAM 2.0 Group Policy Objects</span></span>](deploying-mbam-20-group-policy-objects-mbam-2.md)









