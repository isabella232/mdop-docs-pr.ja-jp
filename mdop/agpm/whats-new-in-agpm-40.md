---
title: AGPM 4.0 の新機能
description: AGPM 4.0 の新機能
author: dansimp
ms.assetid: 31775f7f-a59c-4e64-a875-0adc9f5bc835
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 82b4445a7d22fb7c1ef4f42d896f11908a22f2f5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820104"
---
# <span data-ttu-id="4ed69-103">AGPM 4.0 の新機能</span><span class="sxs-lookup"><span data-stu-id="4ed69-103">What's New in AGPM 4.0</span></span>


<span data-ttu-id="4ed69-104">Microsoft Advanced グループポリシー管理 (AGPM) 4.0 には、グループポリシーオブジェクト (Gpo) の検索、表示された Gpo の一覧のフィルター処理、別のフォレストへの GPO のエクスポートとインポート、Windows7 と Windows Server2008R2 を実行しているコンピューターへの AGPM のインストールを実行できる新しい機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4ed69-104">Microsoft Advanced Group Policy Management (AGPM)4.0 includes new features that let you search for Group Policy Objects (GPOs), filter the list of GPOs displayed, export and import a GPO to a different forest, and install AGPM on computers running Windows7 and Windows Server2008R2.</span></span>

## <span data-ttu-id="4ed69-105">Gpo を検索してフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="4ed69-105">Search and filter GPOs</span></span>


<span data-ttu-id="4ed69-106">AGPM 4.0 では、特定の属性について Gpo の一覧を検索して、表示された Gpo の一覧をフィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="4ed69-106">In AGPM 4.0, you can search the list of GPOs for specific attributes to filter the list of GPOs displayed.</span></span> <span data-ttu-id="4ed69-107">たとえば、特定の名前、状態、またはコメントを含む Gpo を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="4ed69-107">For example, you can search for GPOs with a particular name, state, or comment.</span></span> <span data-ttu-id="4ed69-108">特定のグループポリシー管理者または特定の日付によって最後に変更された Gpo を検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="4ed69-108">You can also search for GPOs that were last changed by a particular Group Policy administrator or on a particular date.</span></span>

<span data-ttu-id="4ed69-109">"Gpo の書式設定" 属性を使用して複雑な検索文字列を作成することができます。 *1: 検索テキスト 1 GPO 属性 2: 検索テキスト 2...* gpo 属性は、AGPM 内の gpo の一覧の列見出しになります。</span><span class="sxs-lookup"><span data-stu-id="4ed69-109">You can create a complex search string by using the format *GPO attribute 1: search text 1 GPO attribute 2: search text 2…*, where a GPO attribute is any column heading in the list of GPOs in AGPM.</span></span> <span data-ttu-id="4ed69-110">たとえば、チェックインされている、ユーザー Editor03 によって最後に変更された、"MyGPO" というテキストを含むすべての Gpo を検索するには、次のように入力します。「 **name: MyGPO の状態:\*\*\*\*チェックイン済み\*\*\*\*: Editor03**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4ed69-110">For example, to search for all GPOs with names including the text "MyGPO" that are checked in and were last changed by the user Editor03, you would type the following in the Search box: **name: MyGPO state:\*\*\*\*checked in\*\*\*\*changed by: Editor03**.</span></span> <span data-ttu-id="4ed69-111">検索では部分一致が返されるため、GPO 名またはユーザー名の一部を入力し、そのテキストを含むすべての Gpo の一覧をその名前に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="4ed69-111">The search returns partial matches so that you can enter part of a GPO name or user name and view a list of all GPOs that include that text in their name.</span></span>

<span data-ttu-id="4ed69-112">さらに、特定の日付または日付の範囲で変更された Gpo を検索するときに、Windows で検索するときに使用できる特殊な用語を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4ed69-112">Additionally, you can use the same special terms available when you search in Windows to search for GPOs changed on a specific date or range of dates.</span></span> <span data-ttu-id="4ed69-113">たとえば、 **date:\*\*\*\*lastmonth**または**date:\*\*\*\*今週**の日付を変更します。</span><span class="sxs-lookup"><span data-stu-id="4ed69-113">For example, **change date:\*\*\*\*lastmonth** or **change date:\*\*\*\*thisweek**.</span></span>

## <span data-ttu-id="4ed69-114">Gpo を別のフォレストにエクスポートしてインポートする</span><span class="sxs-lookup"><span data-stu-id="4ed69-114">Export and import GPOs to different forests</span></span>


<span data-ttu-id="4ed69-115">AGPM 4.0 を使用すると、1つのフォレストのドメインから2つ目のフォレストのドメインに制御された GPO をコピーできます。</span><span class="sxs-lookup"><span data-stu-id="4ed69-115">Using AGPM 4.0, you can copy a controlled GPO from a domain in one forest to a domain in a second forest.</span></span> <span data-ttu-id="4ed69-116">たとえば、AGPM を使用して1つのフォレストのドメインから CAB ファイルに GPO をエクスポートし、その CAB ファイルを USB ドライブにコピーし、USB ドライブを2番目のフォレストのドメイン内のコンピューターに接続して、2番目のフォレストのドメインの AGPM に GPO をインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="4ed69-116">For example, you can export a GPO from a domain in one forest to a CAB file by using AGPM, copy that CAB file to a USB drive, plug the USB drive into a computer in a domain in a second forest, and import the GPO into AGPM in a domain in the second forest.</span></span> <span data-ttu-id="4ed69-117">GPO を新しい制御された GPO としてインポートするか、またはその gpo をインポートして、チェックアウトされている既存の GPO の設定と置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="4ed69-117">You can either import the GPO as a new controlled GPO, or import it to replace the settings of an existing GPO that is checked out.</span></span>

## <span data-ttu-id="4ed69-118">Windows Server 2008 R2 と Windows 7 のサポート</span><span class="sxs-lookup"><span data-stu-id="4ed69-118">Support for Windows Server 2008 R2 and Windows 7</span></span>


<span data-ttu-id="4ed69-119">AGPM 4.0 は、Windows Server2008R2 と Windows7 をサポートしていますが、Windows Server2008 および WindowsVista® Service Pack1 (SP1) でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4ed69-119">AGPM 4.0 supports Windows Server2008R2 and Windows7, yet still supports Windows Server2008 and WindowsVista® with Service Pack1 (SP1).</span></span> <span data-ttu-id="4ed69-120">ただし、次の表に示すように、新しいオペレーティングシステムと古いオペレーティングシステムの両方が含まれている混在環境には制限があります。</span><span class="sxs-lookup"><span data-stu-id="4ed69-120">However, there are limitations in a mixed environment that includes both the newer and older operating systems, as indicated in the following table.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4ed69-121">AGPM サーバー4.0 が実行されているオペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="4ed69-121">Operating system on which AGPM Server 4.0 runs</span></span></th>
<th align="left"><span data-ttu-id="4ed69-122">AGPM クライアント4.0 が実行されるオペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="4ed69-122">Operating system on which AGPM Client 4.0 runs</span></span></th>
<th align="left"><span data-ttu-id="4ed69-123">AGPM 4.0 サポートの状態</span><span class="sxs-lookup"><span data-stu-id="4ed69-123">Status of AGPM 4.0 support</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4ed69-124">Windows Server2008R2 または Windows7</span><span class="sxs-lookup"><span data-stu-id="4ed69-124">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="4ed69-125">Windows Server2008R2 または Windows7</span><span class="sxs-lookup"><span data-stu-id="4ed69-125">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="4ed69-126">サポートされています</span><span class="sxs-lookup"><span data-stu-id="4ed69-126">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4ed69-127">Windows Server2008R2 または Windows7</span><span class="sxs-lookup"><span data-stu-id="4ed69-127">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="4ed69-128">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="4ed69-128">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="4ed69-129">サポートされていますが、Windows Server2008R2 または Windows7 にのみ存在するポリシー設定や設定項目は編集できません。</span><span class="sxs-lookup"><span data-stu-id="4ed69-129">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2008R2 or Windows7</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4ed69-130">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="4ed69-130">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="4ed69-131">Windows Server2008R2 または Windows7</span><span class="sxs-lookup"><span data-stu-id="4ed69-131">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="4ed69-132">サポートされていません</span><span class="sxs-lookup"><span data-stu-id="4ed69-132">Unsupported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4ed69-133">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="4ed69-133">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="4ed69-134">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="4ed69-134">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="4ed69-135">サポートされますが、Windows Server2008R2 または Windows7 にのみ存在するポリシー設定や基本設定項目は報告または編集できません。</span><span class="sxs-lookup"><span data-stu-id="4ed69-135">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2008R2 or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

 

 





