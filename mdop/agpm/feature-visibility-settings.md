---
title: 機能の表示の設定
description: 機能の表示の設定
author: dansimp
ms.assetid: 9db2ba03-fb75-4f95-9138-ec89b9fc8d01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 26f19895d0a9163885779688ba7d89f6d16f2a17
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820807"
---
# <span data-ttu-id="e3e61-103">機能の表示の設定</span><span class="sxs-lookup"><span data-stu-id="e3e61-103">Feature Visibility Settings</span></span>


<span data-ttu-id="e3e61-104">高度なグループポリシー管理 (AGPM) の管理用テンプレート設定を使用すると、これらの設定が適用されているグループポリシーオブジェクト (GPO) の**変更コントロール**ノードと [**履歴**] タブの表示を一元的に構成できます。</span><span class="sxs-lookup"><span data-stu-id="e3e61-104">The Administrative template settings for Advanced Group Policy Management (AGPM) enable you to centrally configure the visibility of the **Change Control** node and **History** tab for Group Policy administrators to whom a Group Policy object (GPO) with these settings is applied.</span></span>

<span data-ttu-id="e3e61-105">グループポリシー管理コンソール (GPMC) で GPO を編集するときに、**グループポリシーオブジェクトエディター**で、[ユーザー構成] \\ [管理 Templates\\Windows Components\\Microsoft 管理コンソール \ \ 制限/許可されている Snap-ins\\Extension スナップイン] の下の設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e3e61-105">The following settings are available under User Configuration\\Administrative Templates\\Windows Components\\Microsoft Management Console\\Restricted/Permitted Snap-ins\\Extension Snap-ins in the **Group Policy Object Editor** when editing a GPO in the Group Policy Management Console (GPMC).</span></span> <span data-ttu-id="e3e61-106">このパスが表示されない場合は、[**管理用テンプレート**] を右クリックして、agpm または agpm テンプレートを追加します。</span><span class="sxs-lookup"><span data-stu-id="e3e61-106">If this path is not visible, right-click **Administrative Templates**, and add the agpm.admx or agpm.adm template.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e3e61-107">設定</span><span class="sxs-lookup"><span data-stu-id="e3e61-107">Setting</span></span></th>
<th align="left"><span data-ttu-id="e3e61-108">効果</span><span class="sxs-lookup"><span data-stu-id="e3e61-108">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e3e61-109">AGPM 変更の制御</span><span class="sxs-lookup"><span data-stu-id="e3e61-109">AGPM Change Control</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e3e61-110">有効になっているか、構成されていない場合は、 <strong> GPMC に [変更コントロール] </strong> ノードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3e61-110">If enabled or not configured, the <strong>Change Control</strong> node is visible in the GPMC.</span></span></p>
<p><span data-ttu-id="e3e61-111">無効にすると、 <strong> GPMC で [変更コントロール] </strong> ノードが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="e3e61-111">If disabled, the <strong>Change Control</strong> node is not visible in the GPMC.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e3e61-112">AGPM リンク拡張機能</span><span class="sxs-lookup"><span data-stu-id="e3e61-112">AGPM Link Extension</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e3e61-113">有効になっているか、構成されていない場合は、 <strong> </strong> リンクされた各 GPO の [履歴] タブが GPMC に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3e61-113">If enabled or not configured, a <strong>History</strong> tab appears in the GPMC for each linked GPO.</span></span></p>
<p><span data-ttu-id="e3e61-114">無効にした場合、 <strong> </strong> リンクされた gpo の [履歴] タブは表示されません。</span><span class="sxs-lookup"><span data-stu-id="e3e61-114">If disabled, the <strong>History</strong> tab is not visible for linked GPOs.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e3e61-115">AGPM GPO 拡張機能</span><span class="sxs-lookup"><span data-stu-id="e3e61-115">AGPM GPO Extension</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e3e61-116">有効になっているか、構成されていない場合は、 <strong> </strong> 各 GPO の GPMC に [履歴] タブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3e61-116">If enabled or not configured, a <strong>History</strong> tab appears in the GPMC for each GPO.</span></span></p>
<p><span data-ttu-id="e3e61-117">無効にした場合、[ <strong> 履歴 </strong> ] タブは gpo に表示されません。</span><span class="sxs-lookup"><span data-stu-id="e3e61-117">If disabled, the <strong>History</strong> tab is not visible for GPOs.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="e3e61-118">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="e3e61-118">Additional references</span></span>

-   [<span data-ttu-id="e3e61-119">管理用テンプレートの設定</span><span class="sxs-lookup"><span data-stu-id="e3e61-119">Administrative Template Settings</span></span>](administrative-template-settings.md)

 

 





