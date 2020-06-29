---
title: REPAIR APP
description: REPAIR APP
author: dansimp
ms.assetid: 892b556b-612d-4531-890e-4cfc2ac88d9f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 791628efd22b0ad429a09e48a82e2d55b45783bd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815724"
---
# <span data-ttu-id="be3bd-103">REPAIR APP</span><span class="sxs-lookup"><span data-stu-id="be3bd-103">REPAIR APP</span></span>


<span data-ttu-id="be3bd-104">このコマンドを実行すると、アプリケーションの個人設定がリセットされます。</span><span class="sxs-lookup"><span data-stu-id="be3bd-104">This command resets your personal settings for an application.</span></span>

`SFTMIME REPAIR APP:application [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="be3bd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="be3bd-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="be3bd-106">説明</span><span class="sxs-lookup"><span data-stu-id="be3bd-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="be3bd-107">アプリ: &lt; アプリケーション&gt;</span><span class="sxs-lookup"><span data-stu-id="be3bd-107">APP:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="be3bd-108">アプリケーションの名前とバージョン (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="be3bd-108">The name and version (optional) of the application.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="be3bd-109">/LOG</span><span class="sxs-lookup"><span data-stu-id="be3bd-109">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="be3bd-110">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="be3bd-110">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="be3bd-111">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="be3bd-111">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="be3bd-112">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="be3bd-112">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="be3bd-113">/GUI</span><span class="sxs-lookup"><span data-stu-id="be3bd-113">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="be3bd-114">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be3bd-114">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="be3bd-115">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="be3bd-115">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="be3bd-116">/Logu</span><span class="sxs-lookup"><span data-stu-id="be3bd-116">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="be3bd-117">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="be3bd-117">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="be3bd-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="be3bd-118">Related topics</span></span>


[<span data-ttu-id="be3bd-119">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="be3bd-119">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





