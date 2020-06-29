---
title: UNPUBLISH PACKAGE
description: UNPUBLISH PACKAGE
author: dansimp
ms.assetid: 1651427c-72a5-4701-bb57-71e14a7a3803
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7704fb3ed03be4864a837767d9e890d28b63f175
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815134"
---
# <span data-ttu-id="38a3b-103">UNPUBLISH PACKAGE</span><span class="sxs-lookup"><span data-stu-id="38a3b-103">UNPUBLISH PACKAGE</span></span>


<span data-ttu-id="38a3b-104">パッケージ全体のショートカットとファイルの種類を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="38a3b-104">Enables you to remove the shortcuts and file types for an entire package.</span></span>

`SFTMIME UNPUBLISH PACKAGE:package-name [/CLEAR] [/GLOBAL]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="38a3b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="38a3b-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="38a3b-106">説明</span><span class="sxs-lookup"><span data-stu-id="38a3b-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="38a3b-107">パッケージ: &lt; パッケージ名&gt;</span><span class="sxs-lookup"><span data-stu-id="38a3b-107">PACKAGE:&lt;package-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="38a3b-108">パッケージの名前。</span><span class="sxs-lookup"><span data-stu-id="38a3b-108">The name of the package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="38a3b-109">/CLEAR</span><span class="sxs-lookup"><span data-stu-id="38a3b-109">/CLEAR</span></span></p></td>
<td align="left"><p><span data-ttu-id="38a3b-110">存在する場合、ユーザー設定も削除されます。</span><span class="sxs-lookup"><span data-stu-id="38a3b-110">If present, user settings will also be removed.</span></span> <span data-ttu-id="38a3b-111">(詳細については、このトピックで後述する重要なメモを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="38a3b-111">(For more information, see the Important note later in this topic.)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="38a3b-112">/グローバル</span><span class="sxs-lookup"><span data-stu-id="38a3b-112">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="38a3b-113">存在する場合、このコンピューター上のすべてのユーザーについてパッケージは非公開になります。</span><span class="sxs-lookup"><span data-stu-id="38a3b-113">If present, the package will be unpublished for all users on this computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="38a3b-114">/LOG</span><span class="sxs-lookup"><span data-stu-id="38a3b-114">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="38a3b-115">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="38a3b-115">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="38a3b-116">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="38a3b-116">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="38a3b-117">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="38a3b-117">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="38a3b-118">/GUI</span><span class="sxs-lookup"><span data-stu-id="38a3b-118">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="38a3b-119">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="38a3b-119">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="38a3b-120">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="38a3b-120">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="38a3b-121">/Logu</span><span class="sxs-lookup"><span data-stu-id="38a3b-121">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="38a3b-122">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="38a3b-122">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="38a3b-123">**重要** [パッケージの発行を**取り消す**] コマンドを実行する前に、アプリの仮想化クライアントにパッケージが既に追加されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="38a3b-123">**Important** Before you can run the **UNPUBLISH PACKAGE** command, the package must already have been added to the Application Virtualization Client.</span></span>

<span data-ttu-id="38a3b-124">**グローバル**を使用するには、**未発行パッケージ**をローカル管理者として実行する必要があります。それ以外の場合は、 **Clearapp**権限のみが必要です。</span><span class="sxs-lookup"><span data-stu-id="38a3b-124">To use **GLOBAL**, **UNPUBLISH PACKAGE** must be run as local Administrator; otherwise, only **ClearApp** permission is needed.</span></span>

<span data-ttu-id="38a3b-125">[**グローバル**で**パッケージを公開**しない] を使用すると、パッケージのグローバルファイルの種類とショートカットがすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="38a3b-125">Using **UNPUBLISH PACKAGE** with **GLOBAL** removes any global file types and shortcuts for the package.</span></span> <span data-ttu-id="38a3b-126">**CLEAR**は適用されません。</span><span class="sxs-lookup"><span data-stu-id="38a3b-126">**CLEAR** is not applicable.</span></span>

<span data-ttu-id="38a3b-127">[**グローバル**で**パッケージを発行**しない] を使用すると、パッケージのユーザーショートカットとファイルの種類が削除され、**明確**に設定されている場合は、ユーザー設定が削除され、ユーザーのコンテキストに応じてバックグラウンドの読み込みが停止します。</span><span class="sxs-lookup"><span data-stu-id="38a3b-127">Using **UNPUBLISH PACKAGE** without **GLOBAL** removes the user shortcuts and file types for the package and, if **CLEAR** is set, also removes user settings and stops background loads under the user’s context.</span></span>

<span data-ttu-id="38a3b-128">"**非公開" パッケージ**は、パッケージの**追加**、**編集**、**公開**のソース ID として使用されたものと同じパッケージ名または GUID から、アプリケーションで動作します。</span><span class="sxs-lookup"><span data-stu-id="38a3b-128">**UNPUBLISH PACKAGE** works on applications from the same package name or GUID that was used as the source ID for **ADD**, **EDIT**, and **PUBLISH PACKAGE**.</span></span>

<span data-ttu-id="38a3b-129">[**パッケージの発行を取り消す**] は、/CLEAR スイッチの使用に関係なく、常にすべてのユーザー設定、ショートカット、およびファイルの種類をクリアします。</span><span class="sxs-lookup"><span data-stu-id="38a3b-129">**UNPUBLISH PACKAGE** always clears all the user settings, shortcuts, and file types regardless of the use of the /CLEAR switch.</span></span>

 

## <span data-ttu-id="38a3b-130">関連トピック</span><span class="sxs-lookup"><span data-stu-id="38a3b-130">Related topics</span></span>


[<span data-ttu-id="38a3b-131">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="38a3b-131">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





