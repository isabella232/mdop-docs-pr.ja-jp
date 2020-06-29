---
title: MED-V ワークスペースの Web 設定を構成する方法
description: MED-V ワークスペースの Web 設定を構成する方法
author: dansimp
ms.assetid: 9a6cd28f-7e4f-468f-830a-7b1d9abd3af3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 770d3fa9a03c9754db86ca348390d0b916de6d5d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827067"
---
# <span data-ttu-id="cb5d0-103">MED-V ワークスペースの Web 設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="cb5d0-103">How to Configure Web Settings for a MED-V Workspace</span></span>


<span data-ttu-id="cb5d0-104">Internet Explorer の以前のバージョンでしか表示できない、またはホストオペレーティングシステムに存在しない Web サイトは、MED-V ワークスペース内の Internet Explorer の以前のバージョンで表示できます。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-104">Web sites that can only be displayed in older versions of Internet Explorer and that do not exist in the host operating system can be viewed in older versions of Internet Explorer within the MED-V workspace.</span></span> <span data-ttu-id="cb5d0-105">指定した Web サイトを表示するために、ユーザーは MED-V ワークスペースでブラウザーを開く必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-105">The user does not need to open a browser in the MED-V workspace to view the specified Web sites.</span></span> <span data-ttu-id="cb5d0-106">ユーザーは、ホストでブラウザーを開き、MED-V ワークスペースに自動的にリダイレクトされます。また、その逆も可能です。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-106">The user can open a browser on the host and automatically be redirected to the MED-V workspace and vice versa.</span></span>

<span data-ttu-id="cb5d0-107">次の手順では、MED-V ワークスペースの Web 参照ルールのリストを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-107">The following procedures describe how you can set a list of Web browsing rules for a MED-V workspace.</span></span> <span data-ttu-id="cb5d0-108">ルールに含まれるすべてのサイトは、管理者によって定義された MED-V ワークスペースまたはホストのいずれかで参照できます。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-108">All sites included in the rules can be browsed either in the MED-V workspace or on the host, as defined by the administrator.</span></span> <span data-ttu-id="cb5d0-109">ルール内に定義されていないすべてのサイトは、要求された環境から参照されます。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-109">All sites not defined within the rules are browsed from the environment in which they were requested.</span></span> <span data-ttu-id="cb5d0-110">ただし、それらをグループとして構成し、MED-V ワークスペースまたはホストで参照できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-110">However, you can configure them as a group as well, to be browsed in the MED-V workspace or the host.</span></span>

**<span data-ttu-id="cb5d0-111">注</span><span class="sxs-lookup"><span data-stu-id="cb5d0-111">Note</span></span>**  
<span data-ttu-id="cb5d0-112">[Web 設定] は、Internet Explorer および他のブラウザーに対してのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-112">Web settings are applied only to Internet Explorer and to no other browsers.</span></span>



<span data-ttu-id="cb5d0-113">すべての Web 設定は、[ **web** ] タブの**ポリシー**モジュールで構成されます。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-113">All Web settings are configured in the **Policy** module, on the **Web** tab.</span></span>

## <span data-ttu-id="cb5d0-114">MED-V ワークスペースの Web 設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="cb5d0-114">How to Configure Web Settings for the MED-V Workspace</span></span>


**<span data-ttu-id="cb5d0-115">MED-V ワークスペースの Web 設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="cb5d0-115">To configure Web settings for the MED-V workspace</span></span>**

1.  <span data-ttu-id="cb5d0-116">構成する MED-V ワークスペースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-116">Click the MED-V workspace to be configured.</span></span>

2.  <span data-ttu-id="cb5d0-117">[**次のテーブルで定義された url のリストを参照**する] チェックボックスをオンにして、ユーザーが指定した Web ルールに準拠した url を参照するときに、med-v workspace または host 内のブラウザーにユーザーをリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-117">Select the **Browse the list of URLs defined in the following table** check box to redirect the user to a browser within the MED-V workspace or host, when the user browses to a URL that conforms to the Web rules specified.</span></span>

3.  <span data-ttu-id="cb5d0-118">次のいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-118">Click one of the following:</span></span>

    -   <span data-ttu-id="cb5d0-119">**ワークスペースで**、med-v ワークスペースのブラウザーにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-119">**In the Workspace**—Redirect to a browser in the MED-V workspace.</span></span>

    -   <span data-ttu-id="cb5d0-120">**ホストで**、ホスト上のブラウザーにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-120">**In the host**—Redirect to a browser on the host.</span></span>

4.  <span data-ttu-id="cb5d0-121">[**その他のすべての url を参照**] チェックボックスをオンにして、Web ルールから除外するすべての url を host または med-v ワークスペースにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-121">Select the **Browse all other URLs** check box to redirect all URLs excluded from the Web rules to the host or MED-V workspace.</span></span>

5.  <span data-ttu-id="cb5d0-122">次のいずれかをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-122">Click one of the following:</span></span>

    -   <span data-ttu-id="cb5d0-123">**ワークスペースで、** med-v ワークスペース内のすべての url をブラウザーにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-123">**In the Workspace**—Redirect all other URLs to a browser in the MED-V workspace.</span></span>

    -   <span data-ttu-id="cb5d0-124">**ホスト**の場合: ホスト上のブラウザーに他のすべての url をリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-124">**In the host**—Redirect all other URLs to a browser on the host.</span></span>

6.  <span data-ttu-id="cb5d0-125">[**ポリシー** ] メニューで、[**コミット**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-125">On the **Policy** menu, select **Commit**.</span></span>

## <span data-ttu-id="cb5d0-126">Web ルールを追加する方法</span><span class="sxs-lookup"><span data-stu-id="cb5d0-126">How to Add a Web Rule</span></span>


**<span data-ttu-id="cb5d0-127">Web ルールを追加するには</span><span class="sxs-lookup"><span data-stu-id="cb5d0-127">To add a Web rule</span></span>**

1.  <span data-ttu-id="cb5d0-128">[**次のテーブルで定義された url のリストを参照**します] チェックボックスをオンにして、Web 参照ルールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-128">Select the **Browse the list of URLs defined in the following table** check box to enable the Web browsing rules.</span></span>

2.  <span data-ttu-id="cb5d0-129">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-129">Click **Add**.</span></span>

    <span data-ttu-id="cb5d0-130">新しい Web ルールが追加されます。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-130">A new Web rule is added.</span></span>

3.  <span data-ttu-id="cb5d0-131">次の表で説明するように、Web ルールのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-131">Configure the Web rule properties as described in the following table.</span></span>

4.  <span data-ttu-id="cb5d0-132">[**ポリシー** ] メニューで、[**コミット**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-132">On the **Policy** menu, select **Commit**.</span></span>

**<span data-ttu-id="cb5d0-133">MED-V ワークスペース Web プロパティ</span><span class="sxs-lookup"><span data-stu-id="cb5d0-133">MED-V Workspace Web Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cb5d0-134">プロパティ</span><span class="sxs-lookup"><span data-stu-id="cb5d0-134">Property</span></span></th>
<th align="left"><span data-ttu-id="cb5d0-135">説明</span><span class="sxs-lookup"><span data-stu-id="cb5d0-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cb5d0-136">種類</span><span class="sxs-lookup"><span data-stu-id="cb5d0-136">Type</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="cb5d0-137">ドメインサフィックス </strong> : Value プロパティで指定されているサフィックスで終わる任意のホストアドレスへのアクセス <strong> </strong> 、および Web 閲覧で設定されたオプションに従って設定され <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-137">Domain suffix</strong>—Access to any host address ending with the suffix specified in the <strong>Value</strong> property and is set according to the option set in <strong>Web Browsing</strong>.</span></span></p></li>
<li><p><strong><span data-ttu-id="cb5d0-138">[IP Prefix] </strong> : Value プロパティで指定されたプレフィックスの範囲に含まれる完全な ip アドレスまたは部分的な ip アドレスへのアクセス、 <strong> </strong> および Web 閲覧で設定されたオプションに従って設定され <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-138">IP Prefix</strong>—Access to any full or partial IP address in the range of the prefix specified in the <strong>Value</strong> property and is set according to the option set in <strong>Web Browsing</strong>.</span></span></p></li>
<li><p><strong><span data-ttu-id="cb5d0-139">すべてのローカルアドレス </strong> -&#39; のないすべてのアドレスへのアクセス。 &#39; は、 <strong> Web 閲覧で設定されたオプションに従って設定されます。 </strong></span><span class="sxs-lookup"><span data-stu-id="cb5d0-139">All Local Addresses</strong>—Access to all addresses without a &#39;.&#39; and is set according to the option set in <strong>Web Browsing</strong>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cb5d0-140">値</span><span class="sxs-lookup"><span data-stu-id="cb5d0-140">Value</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="cb5d0-141">[ <strong> </strong> Type] プロパティで [domain suffix] が選択されている場合は <strong> </strong> 、ドメインサフィックスを入力します。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-141">If <strong>Domain suffix</strong> is selected in the <strong>Type</strong> property, enter a domain suffix.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="cb5d0-142">注</span><span class="sxs-lookup"><span data-stu-id="cb5d0-142">Note</span></span></strong><br/><ul>
<li><p><span data-ttu-id="cb5d0-143">&quot; \* &quot; サフィックスの前には入力しないでください。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-143">Do not enter &quot;\*&quot; before the suffix.</span></span></p></li>
<li><p><span data-ttu-id="cb5d0-144">ドメインサフィックスでもエイリアスがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-144">Domain suffixes support aliases as well.</span></span></p></li>
</ul>
</div>
<div>

</div></li>
<li><p><span data-ttu-id="cb5d0-145">[Type] プロパティで IP プレフィックスが選択されている場合は <strong> </strong> 、完全な ip アドレスまたは一部の ip アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-145">If IP Prefix is selected in the <strong>Type</strong> property, enter a full or partial IP address.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="cb5d0-146">Web ルールを削除する方法</span><span class="sxs-lookup"><span data-stu-id="cb5d0-146">How to Delete a Web Rule</span></span>


**<span data-ttu-id="cb5d0-147">Web ルールを削除するには</span><span class="sxs-lookup"><span data-stu-id="cb5d0-147">To delete a Web rule</span></span>**

1.  <span data-ttu-id="cb5d0-148">[ **Web** ] ウィンドウで、削除する web ルールを選びます。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-148">In the **Web** pane, select the Web rule to delete.</span></span>

2.  <span data-ttu-id="cb5d0-149">[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-149">Click **Remove**.</span></span>

    <span data-ttu-id="cb5d0-150">Web ルールが削除されます。</span><span class="sxs-lookup"><span data-stu-id="cb5d0-150">The Web rule is deleted.</span></span>

## <span data-ttu-id="cb5d0-151">関連トピック</span><span class="sxs-lookup"><span data-stu-id="cb5d0-151">Related topics</span></span>


[<span data-ttu-id="cb5d0-152">MED-V 管理コンソールのユーザー インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="cb5d0-152">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="cb5d0-153">MED-V ワークスペースの作成</span><span class="sxs-lookup"><span data-stu-id="cb5d0-153">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)









