---
title: DELETE OBJ
description: DELETE OBJ
author: dansimp
ms.assetid: fb17a261-f378-4ce6-a538-ab2f0ada0f2d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4d74fc1ac098d7dc4dd2f28633e9ca58d4211d74
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821704"
---
# <span data-ttu-id="3140e-103">DELETE OBJ</span><span class="sxs-lookup"><span data-stu-id="3140e-103">DELETE OBJ</span></span>


<span data-ttu-id="3140e-104">すべてのアプリケーションレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="3140e-104">Removes all of your application records.</span></span>

`SFTMIME DELETE OBJ:APP [/GLOBAL] [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3140e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3140e-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="3140e-106">説明</span><span class="sxs-lookup"><span data-stu-id="3140e-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3140e-107">/グローバル</span><span class="sxs-lookup"><span data-stu-id="3140e-107">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="3140e-108">指定すると、すべてのアプリケーションが削除されます。</span><span class="sxs-lookup"><span data-stu-id="3140e-108">If specified, all applications are removed.</span></span> <span data-ttu-id="3140e-109">既定では、現在のユーザーがアクセスできるアプリケーションのみが削除されます。</span><span class="sxs-lookup"><span data-stu-id="3140e-109">By default, only applications the current user has access to are removed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3140e-110">/LOG</span><span class="sxs-lookup"><span data-stu-id="3140e-110">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="3140e-111">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="3140e-111">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3140e-112">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="3140e-112">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="3140e-113">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="3140e-113">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3140e-114">/GUI</span><span class="sxs-lookup"><span data-stu-id="3140e-114">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="3140e-115">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3140e-115">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="3140e-116">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="3140e-116">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3140e-117">/Logu</span><span class="sxs-lookup"><span data-stu-id="3140e-117">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="3140e-118">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="3140e-118">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="3140e-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3140e-119">Related topics</span></span>


[<span data-ttu-id="3140e-120">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="3140e-120">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





