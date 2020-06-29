---
title: GPO の一覧を検索およびフィルター処理する
description: GPO の一覧を検索およびフィルター処理する
author: dansimp
ms.assetid: 1bc58a38-033c-4aed-9eb4-c239827f5501
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5646a51a37a4ca9195fb9ef858e8c5920ca7738a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820264"
---
# <span data-ttu-id="1810c-103">GPO の一覧を検索およびフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="1810c-103">Search and Filter the List of GPOs</span></span>


<span data-ttu-id="1810c-104">高度なグループポリシー管理 (AGPM) では、グループポリシーオブジェクト (Gpo) の一覧とその属性を検索して、表示された Gpo の一覧をフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="1810c-104">In Advanced Group Policy Management (AGPM), you can search the list of Group Policy Objects (GPOs) and their attributes to filter the list of GPOs displayed.</span></span> <span data-ttu-id="1810c-105">たとえば、特定の名前、状態、またはコメントを含む Gpo を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="1810c-105">For example, you can search for GPOs with a particular name, state, or comment.</span></span> <span data-ttu-id="1810c-106">特定のグループポリシー管理者または特定の日付によって最後に変更された Gpo を検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="1810c-106">You can also search for GPOs that were last changed by a particular Group Policy administrator or on a particular date.</span></span>

## <span data-ttu-id="1810c-107">複雑な検索を実行する</span><span class="sxs-lookup"><span data-stu-id="1810c-107">Performing a complex search</span></span>


<span data-ttu-id="1810c-108">"Gpo の書式設定" 属性を使って複雑な検索を実行することができます。 *1: 検索文字列 1 GPO 属性 2: 検索文字列 2...すべての列の検索文字列*。</span><span class="sxs-lookup"><span data-stu-id="1810c-108">You can perform a complex search by using the format *GPO attribute 1: search string 1 GPO attribute 2: search string 2…all-column search strings*.</span></span> <span data-ttu-id="1810c-109">検索では、大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="1810c-109">The search is not case-sensitive.</span></span>

-   <span data-ttu-id="1810c-110">**GPO 属性:\*\*\*\*コンピューターのバージョン**または**ユーザーのバージョン**以外の AGPM に含まれる gpo の一覧の列見出し。</span><span class="sxs-lookup"><span data-stu-id="1810c-110">**GPO attribute:** Any column heading in the list of GPOs in AGPM other than **Computer Version** or **User Version**.</span></span> <span data-ttu-id="1810c-111">Gpo 属性には、gpo 名、状態、GPO を最後に変更したユーザー、gpo が最近変更された日時、コメント、GPO の状態、GPO に適用された WMI フィルターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1810c-111">GPO attributes include the GPO name, state, user who most recently changed the GPO, date and time when the GPO was most recently changed, comment, GPO status, and WMI filter applied to the GPO.</span></span>

-   <span data-ttu-id="1810c-112">**検索文字列:** 指定した列で検索するテキスト。</span><span class="sxs-lookup"><span data-stu-id="1810c-112">**Search string:** Text for which to search in the specified column.</span></span> <span data-ttu-id="1810c-113">文字列にスペースが含まれている場合は、文字列を引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="1810c-113">If a string includes spaces, you must enclose the string with quotation marks.</span></span>

-   <span data-ttu-id="1810c-114">**すべての列の検索文字列:\*\*\*\*コンピューターのバージョン**と**ユーザーのバージョン**以外の AGPM に含まれる gpo の一覧のすべての列で検索するテキスト。</span><span class="sxs-lookup"><span data-stu-id="1810c-114">**All-column search strings:** Text for which to search in all columns in the list of GPOs in AGPM other than **Computer Version** and **User Version**.</span></span> <span data-ttu-id="1810c-115">複数の文字列をスペースで区切って含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1810c-115">You can include multiple strings separated by spaces.</span></span> <span data-ttu-id="1810c-116">文字列にスペースが含まれている場合は、文字列を引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="1810c-116">If a string includes spaces, you must enclose the string with quotation marks.</span></span>

<span data-ttu-id="1810c-117">各 GPO 属性と検索文字列の組み合わせと、各列の検索文字列は、論理 AND 演算を使って結合されます。</span><span class="sxs-lookup"><span data-stu-id="1810c-117">Each GPO attribute and search string pair and each all-column search string are combined by using a logical AND operation.</span></span> <span data-ttu-id="1810c-118">結果として、指定した各属性に指定した検索文字列が含まれ、すべての列の検索文字列が1つ以上の列に表示されるすべての Gpo の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1810c-118">The result is a list of all GPOs for which each specified attribute includes the specified search string and for which any all-column search strings appear in at least one column.</span></span> <span data-ttu-id="1810c-119">検索では、GPO 名またはユーザー名の一部を入力して、そのテキストが含まれているすべての Gpo の一覧をその名前に表示できるように、文字列の部分一致を返します。</span><span class="sxs-lookup"><span data-stu-id="1810c-119">The search returns any partial matches for strings so that you can enter part of a GPO name or user name and view a list of all GPOs that include that text in their name.</span></span>

<span data-ttu-id="1810c-120">次に、検索の例を示します。</span><span class="sxs-lookup"><span data-stu-id="1810c-120">The following are examples of searches:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1810c-121">検索結果の説明</span><span class="sxs-lookup"><span data-stu-id="1810c-121">Description of search result</span></span></th>
<th align="left"><span data-ttu-id="1810c-122">検索クエリ</span><span class="sxs-lookup"><span data-stu-id="1810c-122">Search query</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1810c-123">テキストの <strong> セキュリティ </strong> と <strong> 北アメリカの名前を含むすべての gpo </strong> 。</span><span class="sxs-lookup"><span data-stu-id="1810c-123">All GPOs with names that include the text <strong>security</strong> and <strong>North America</strong>.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="1810c-124">名前: </strong><strong> セキュリティ </strong><strong> 名: </strong> &quot; <strong> 北アメリカ</strong>&quot;</span><span class="sxs-lookup"><span data-stu-id="1810c-124">name:</strong><strong>security</strong><strong>name:</strong>&quot;<strong>North America</strong>&quot;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1810c-125">すべてのチェックアウトされた Gpo。</span><span class="sxs-lookup"><span data-stu-id="1810c-125">All checked out GPOs.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="1810c-126">状態: </strong> &quot; <strong> チェックアウト済み</strong>&quot;</span><span class="sxs-lookup"><span data-stu-id="1810c-126">state:</strong>&quot;<strong>checked out</strong>&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1810c-127">[管理者] という名前のユーザーによって最近変更されたすべて <strong> </strong> の gpo、および前月以内に変更された。</span><span class="sxs-lookup"><span data-stu-id="1810c-127">All GPOs most recently changed by the user named <strong>Administrator</strong> and most recently changed within the previous month.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="1810c-128">変更者: </strong><strong> 管理者の </strong><strong> 変更日: </strong><strong> lastmonth</span><span class="sxs-lookup"><span data-stu-id="1810c-128">changed by:</strong><strong>Administrator</strong><strong>change date:</strong><strong>lastmonth</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1810c-129">Word <strong> ファイアウォール </strong> が最新のコメントに含まれていて、 <strong> </strong> どの列にも word のセキュリティが表示されるすべての gpo。</span><span class="sxs-lookup"><span data-stu-id="1810c-129">All GPOs in which the word <strong>firewall</strong> is included in the most recent comment and in which the word <strong>security</strong> appears in any column.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="1810c-130">コメント: </strong><strong> ファイアウォールの </strong><strong> セキュリティ</span><span class="sxs-lookup"><span data-stu-id="1810c-130">comment:</strong><strong>firewall</strong><strong>security</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1810c-131">すべての設定の状態が無効になっているすべての Gpo <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="1810c-131">All GPOs that have a status of <strong>All Settings Disabled</strong>.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="1810c-132">gpo の状態: </strong><strong> すべて</span><span class="sxs-lookup"><span data-stu-id="1810c-132">gpo status:</strong><strong>all</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1810c-133">Wmi フィルターという名前の WMI フィルターが適用されていて、 <strong> </strong> ユーザー構成設定の状態が [無効] になっているすべての gpo <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="1810c-133">All GPOs that have a WMI filter named <strong>My WMI Filter</strong> applied and that have a status of <strong>User Configuration Settings Disabled</strong>.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="1810c-134">wmi フィルター: </strong> &quot; <strong> マイ wmi フィルター </strong> &quot; <strong> gpo の状態: </strong><strong> ユーザー</span><span class="sxs-lookup"><span data-stu-id="1810c-134">wmi filter:</strong>&quot;<strong>My WMI Filter</strong>&quot;<strong>gpo status:</strong><strong>user</span></span></strong></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="1810c-135">日付の指定</span><span class="sxs-lookup"><span data-stu-id="1810c-135">Specifying dates</span></span>


<span data-ttu-id="1810c-136">Windows で検索するときに、特定の日付、特定の時刻、または一定期間内に変更された Gpo を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="1810c-136">You can search for GPOs changed on a specific date, at a specific time, or during a span of time by using the same special terms available when you search in Windows.</span></span> <span data-ttu-id="1810c-137">特定の日付または時刻を入力する場合は、[**日付の変更**] 列で使用されている形式を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1810c-137">If entering a specific date or time, you must use the format that is used in the **Change Date** column.</span></span> <span data-ttu-id="1810c-138">次に、[**変更日 (Date** ) 列の検索の例を示します。</span><span class="sxs-lookup"><span data-stu-id="1810c-138">The following are examples of searches of the **Change Date** column:</span></span>

-   <span data-ttu-id="1810c-139">**日付の変更:\*\*\*\*10/10/2009**</span><span class="sxs-lookup"><span data-stu-id="1810c-139">**change date:\*\*\*\*10/10/2009**</span></span>

-   <span data-ttu-id="1810c-140">**日付の変更:\*\*\*\*10/10/2009 9:00:00 AM**</span><span class="sxs-lookup"><span data-stu-id="1810c-140">**change date:\*\*\*\*10/10/2009 9:00:00 AM**</span></span>

-   <span data-ttu-id="1810c-141">**変更日:\*\*\*\*今週**</span><span class="sxs-lookup"><span data-stu-id="1810c-141">**change date:\*\*\*\*thisweek**</span></span>

<span data-ttu-id="1810c-142">[**日付の変更**] 列を検索するときに、大文字と小文字を区別しない次の特別な用語を使用できます。</span><span class="sxs-lookup"><span data-stu-id="1810c-142">You can use the following special terms, which are not case-sensitive, when you search the **Change Date** column:</span></span>

-   **<span data-ttu-id="1810c-143">Today</span><span class="sxs-lookup"><span data-stu-id="1810c-143">Today</span></span>**

-   **<span data-ttu-id="1810c-144">昨日</span><span class="sxs-lookup"><span data-stu-id="1810c-144">Yesterday</span></span>**

-   **<span data-ttu-id="1810c-145">今週</span><span class="sxs-lookup"><span data-stu-id="1810c-145">ThisWeek</span></span>**

-   **<span data-ttu-id="1810c-146">LastWeek</span><span class="sxs-lookup"><span data-stu-id="1810c-146">LastWeek</span></span>**

-   **<span data-ttu-id="1810c-147">今月</span><span class="sxs-lookup"><span data-stu-id="1810c-147">ThisMonth</span></span>**

-   **<span data-ttu-id="1810c-148">最終月</span><span class="sxs-lookup"><span data-stu-id="1810c-148">LastMonth</span></span>**

-   **<span data-ttu-id="1810c-149">TwoMonths</span><span class="sxs-lookup"><span data-stu-id="1810c-149">TwoMonths</span></span>**

-   **<span data-ttu-id="1810c-150">ThreeMonths</span><span class="sxs-lookup"><span data-stu-id="1810c-150">ThreeMonths</span></span>**

-   **<span data-ttu-id="1810c-151">ThisYear</span><span class="sxs-lookup"><span data-stu-id="1810c-151">ThisYear</span></span>**

-   **<span data-ttu-id="1810c-152">LastYear</span><span class="sxs-lookup"><span data-stu-id="1810c-152">LastYear</span></span>**

### <span data-ttu-id="1810c-153">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="1810c-153">Additional considerations</span></span>

-   <span data-ttu-id="1810c-154">既定では、この手順を実行するには、レビュー担当者、編集者、承認者、AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1810c-154">By default, you must be a Reviewer, an Editor, an Approver, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="1810c-155">具体的には、ドメインの**リストコンテンツ**のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1810c-155">Specifically, you must have **List Contents** permission for the domain.</span></span>

-   <span data-ttu-id="1810c-156">GPO 属性の詳細については、「 [[コンテンツ] タブの機能](contents-tab-features-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1810c-156">For more information about GPO attributes, see [Contents Tab Features](contents-tab-features-agpm40.md).</span></span>

### <span data-ttu-id="1810c-157">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="1810c-157">Additional references</span></span>

-   [<span data-ttu-id="1810c-158">Advanced Group Policy Management 4.0</span><span class="sxs-lookup"><span data-stu-id="1810c-158">Advanced Group Policy Management 4.0</span></span>](advanced-group-policy-management-40.md)

 

 





