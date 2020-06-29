---
title: MBAM 2.5 グループ ポリシー設定の編集
description: MBAM 2.5 グループ ポリシー設定の編集
author: dansimp
ms.assetid: a50b6b0c-6818-4419-8447-d0520a533dba
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0f6d180cba6dc721ff7de1607d57f90184303d88
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812595"
---
# <span data-ttu-id="b03bc-103">MBAM 2.5 グループ ポリシー設定の編集</span><span class="sxs-lookup"><span data-stu-id="b03bc-103">Editing the MBAM 2.5 Group Policy Settings</span></span>


<span data-ttu-id="b03bc-104">Microsoft BitLocker の管理と監視 (MBAM) を正常に展開するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b03bc-104">To successfully deploy Microsoft BitLocker Administration and Monitoring (MBAM), you have to:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b03bc-105">タスク</span><span class="sxs-lookup"><span data-stu-id="b03bc-105">Task</span></span></th>
<th align="left"><span data-ttu-id="b03bc-106">詳細情報</span><span class="sxs-lookup"><span data-stu-id="b03bc-106">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b03bc-107">MBAM 2.5 グループポリシーテンプレートをコピーします。</span><span class="sxs-lookup"><span data-stu-id="b03bc-107">Copy the MBAM 2.5 Group Policy Templates.</span></span></p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)"><span data-ttu-id="b03bc-108">MBAM 2.5 グループ ポリシー テンプレートのコピー</span><span class="sxs-lookup"><span data-stu-id="b03bc-108">Copying the MBAM 2.5 Group Policy Templates</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b03bc-109">MBAM の実装で使用するグループポリシーオブジェクト (Gpo) を決定します。</span><span class="sxs-lookup"><span data-stu-id="b03bc-109">Determine which Group Policy Objects (GPOs) you want to use in your MBAM implementation.</span></span> <span data-ttu-id="b03bc-110">組織のニーズに応じて、追加のグループポリシー設定を構成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="b03bc-110">Based on the needs of your organization, you might have to configure additional Group Policy settings.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-25-group-policy-requirements.md" data-raw-source="[Planning for MBAM 2.5 Group Policy Requirements](planning-for-mbam-25-group-policy-requirements.md)"><span data-ttu-id="b03bc-111">MBAM 2.5 の計画グループポリシー要件 </a> – gpo の説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b03bc-111">Planning for MBAM 2.5 Group Policy Requirements</a> – contains descriptions of the GPOs</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b03bc-112">組織のグループポリシー設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="b03bc-112">Set the Group Policy settings for your organization.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="b03bc-113">**重要** **BitLocker ドライブ暗号化**ノードのグループポリシー設定を変更しないようにします。または、mbam が正しく動作しません。</span><span class="sxs-lookup"><span data-stu-id="b03bc-113">**Important** Do not change the Group Policy settings in the **BitLocker Drive Encryption** node, or MBAM will not work correctly.</span></span> <span data-ttu-id="b03bc-114">[ **MDOP mbam (BitLocker Management)** ] ノードでグループポリシー設定を構成すると、mbam が自動的に**bitlocker ドライブ暗号化**設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="b03bc-114">When you configure the Group Policy settings in the **MDOP MBAM (BitLocker Management)** node, MBAM automatically configures the **BitLocker Drive Encryption** settings for you.</span></span>

 

**<span data-ttu-id="b03bc-115">MBAM クライアントのグループポリシー設定を編集するには</span><span class="sxs-lookup"><span data-stu-id="b03bc-115">To edit MBAM Client Group Policy settings</span></span>**

1.  <span data-ttu-id="b03bc-116">MBAM グループポリシーテンプレートがインストールされているコンピューターで、MBAM サービスが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b03bc-116">On a computer that has the MBAM Group Policy Templates installed, make sure that MBAM Services are enabled.</span></span>

2.  <span data-ttu-id="b03bc-117">Mbam グループポリシーテンプレートがインストールされているコンピューターで、グループポリシー管理コンソール (GPMC) または Microsoft Advanced グループポリシー管理の mdop 製品を使用して、**コンピューター構成** &gt; **ポリシー** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **MDOP mbam (BitLocker 管理)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b03bc-117">Using the Group Policy Management Console (GPMC.msc) or the Microsoft Advanced Group Policy Management MDOP product on a computer with the MBAM Group Policy Templates installed, select **Computer configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)**.</span></span>

3.  <span data-ttu-id="b03bc-118">クライアントコンピューターで MBAM クライアントサービスを有効にするために必要なグループポリシー設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="b03bc-118">Edit the Group Policy settings that are required to enable MBAM Client services on client computers.</span></span> <span data-ttu-id="b03bc-119">次の表のポリシーごとに、[**ポリシーグループ**] を選択し、目的の**ポリシー**をクリックして、設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="b03bc-119">For each policy in the following table, select **Policy Group**, click the **Policy** you want, and then configure the settings.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="b03bc-120">ポリシーグループ</span><span class="sxs-lookup"><span data-stu-id="b03bc-120">Policy Group</span></span></th>
    <th align="left"><span data-ttu-id="b03bc-121">ポリシー</span><span class="sxs-lookup"><span data-stu-id="b03bc-121">Policy</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="b03bc-122">クライアントの管理</span><span class="sxs-lookup"><span data-stu-id="b03bc-122">Client Management</span></span></p></td>
    <td align="left"><p><span data-ttu-id="b03bc-123">MBAM サービスを設定する</span><span class="sxs-lookup"><span data-stu-id="b03bc-123">Configure MBAM Services</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="b03bc-124">オペレーティングシステムドライブ</span><span class="sxs-lookup"><span data-stu-id="b03bc-124">Operating System Drive</span></span></p></td>
    <td align="left"><p><span data-ttu-id="b03bc-125">オペレーティングシステムドライブの暗号化の設定</span><span class="sxs-lookup"><span data-stu-id="b03bc-125">Operating system drive encryption settings</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="b03bc-126">リムーバブルドライブ</span><span class="sxs-lookup"><span data-stu-id="b03bc-126">Removable Drive</span></span></p></td>
    <td align="left"><p><span data-ttu-id="b03bc-127">リムーバブルドライブでの BitLocker の使用を制御する</span><span class="sxs-lookup"><span data-stu-id="b03bc-127">Control use of BitLocker on removable drives</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="b03bc-128">固定ドライブ</span><span class="sxs-lookup"><span data-stu-id="b03bc-128">Fixed Drive</span></span></p></td>
    <td align="left"><p><span data-ttu-id="b03bc-129">固定ドライブでの BitLocker の使用を制御する</span><span class="sxs-lookup"><span data-stu-id="b03bc-129">Control use of BitLocker on fixed drives</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

## <span data-ttu-id="b03bc-130">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b03bc-130">Related topics</span></span>


[<span data-ttu-id="b03bc-131">MBAM 2.5 グループ ポリシー要件の計画</span><span class="sxs-lookup"><span data-stu-id="b03bc-131">Planning for MBAM 2.5 Group Policy Requirements</span></span>](planning-for-mbam-25-group-policy-requirements.md)

[<span data-ttu-id="b03bc-132">MBAM 2.5 グループ ポリシー テンプレートのコピー</span><span class="sxs-lookup"><span data-stu-id="b03bc-132">Copying the MBAM 2.5 Group Policy Templates</span></span>](copying-the-mbam-25-group-policy-templates.md)

 
## <span data-ttu-id="b03bc-133">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="b03bc-133">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="b03bc-134">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="b03bc-134">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="b03bc-135">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="b03bc-135">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





