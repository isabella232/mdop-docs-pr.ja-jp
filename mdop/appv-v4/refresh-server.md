---
title: REFRESH SERVER
description: REFRESH SERVER
author: dansimp
ms.assetid: 232df842-a160-46cd-b60b-f464cd9a0086
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0256e03c152afd7196c2c2a542362ada1c270990
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815727"
---
# <span data-ttu-id="e7572-103">REFRESH SERVER</span><span class="sxs-lookup"><span data-stu-id="e7572-103">REFRESH SERVER</span></span>


<span data-ttu-id="e7572-104">このコマンドは、サーバーから発行情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="e7572-104">This command updates publishing information from a server.</span></span>

`SFTMIME REFRESH SERVER:server-name [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e7572-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e7572-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="e7572-106">説明</span><span class="sxs-lookup"><span data-stu-id="e7572-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e7572-107">サーバー: &lt; サーバー名&gt;</span><span class="sxs-lookup"><span data-stu-id="e7572-107">SERVER:&lt;server-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="e7572-108">サーバーの表示名。</span><span class="sxs-lookup"><span data-stu-id="e7572-108">The display name of the server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e7572-109">/LOG</span><span class="sxs-lookup"><span data-stu-id="e7572-109">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="e7572-110">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="e7572-110">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e7572-111">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="e7572-111">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="e7572-112">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="e7572-112">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e7572-113">/GUI</span><span class="sxs-lookup"><span data-stu-id="e7572-113">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="e7572-114">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7572-114">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="e7572-115">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="e7572-115">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e7572-116">/Logu</span><span class="sxs-lookup"><span data-stu-id="e7572-116">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="e7572-117">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="e7572-117">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="e7572-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e7572-118">Related topics</span></span>


[<span data-ttu-id="e7572-119">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="e7572-119">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





