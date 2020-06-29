---
title: DELETE TYPE
description: DELETE TYPE
author: dansimp
ms.assetid: f2852723-c894-49f3-a3c5-56f9648bb9ca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0df68c0a0efcd0e269410d1580f7b0a82301c46d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821687"
---
# <span data-ttu-id="cd02e-103">DELETE TYPE</span><span class="sxs-lookup"><span data-stu-id="cd02e-103">DELETE TYPE</span></span>


<span data-ttu-id="cd02e-104">指定したファイルの種類の関連付けを削除します。</span><span class="sxs-lookup"><span data-stu-id="cd02e-104">Removes the specified file type association.</span></span>

`SFTMIME DELETE TYPE:file-extension [/GLOBAL]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cd02e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cd02e-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="cd02e-106">説明</span><span class="sxs-lookup"><span data-stu-id="cd02e-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cd02e-107">種類: &lt; ファイル拡張子&gt;</span><span class="sxs-lookup"><span data-stu-id="cd02e-107">TYPE:&lt;file-extension&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="cd02e-108">削除するファイル名の拡張子。</span><span class="sxs-lookup"><span data-stu-id="cd02e-108">The file name extension to be removed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cd02e-109">/グローバル</span><span class="sxs-lookup"><span data-stu-id="cd02e-109">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="cd02e-110">指定すると、ファイル名拡張子のグローバル関連付けを削除する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="cd02e-110">If specified, indicates that the global association for the file name extension should be removed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cd02e-111">/LOG</span><span class="sxs-lookup"><span data-stu-id="cd02e-111">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="cd02e-112">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="cd02e-112">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cd02e-113">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="cd02e-113">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="cd02e-114">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="cd02e-114">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cd02e-115">/GUI</span><span class="sxs-lookup"><span data-stu-id="cd02e-115">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="cd02e-116">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd02e-116">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="cd02e-117">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="cd02e-117">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cd02e-118">/Logu</span><span class="sxs-lookup"><span data-stu-id="cd02e-118">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="cd02e-119">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="cd02e-119">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="cd02e-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="cd02e-120">Related topics</span></span>


[<span data-ttu-id="cd02e-121">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="cd02e-121">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





