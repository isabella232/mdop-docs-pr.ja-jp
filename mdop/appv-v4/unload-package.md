---
title: UNLOAD PACKAGE
description: UNLOAD PACKAGE
author: dansimp
ms.assetid: a076eb5a-ce3d-49e4-ac7a-4d4df10e3477
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fbee040f97bf5675ace7e873741a4270a993a911
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815147"
---
# <span data-ttu-id="7d8c0-103">UNLOAD PACKAGE</span><span class="sxs-lookup"><span data-stu-id="7d8c0-103">UNLOAD PACKAGE</span></span>


<span data-ttu-id="7d8c0-104">ファイルシステムキャッシュからパッケージをアンロードします。</span><span class="sxs-lookup"><span data-stu-id="7d8c0-104">Unloads the package from the file system cache.</span></span>

`SFTMIME UNLOAD PACKAGE:package-name [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7d8c0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7d8c0-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="7d8c0-106">説明</span><span class="sxs-lookup"><span data-stu-id="7d8c0-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7d8c0-107">パッケージ: &lt; パッケージ名&gt;</span><span class="sxs-lookup"><span data-stu-id="7d8c0-107">PACKAGE:&lt;package-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="7d8c0-108">アンロードするパッケージの名前。</span><span class="sxs-lookup"><span data-stu-id="7d8c0-108">The name of the package to unload.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7d8c0-109">/LOG</span><span class="sxs-lookup"><span data-stu-id="7d8c0-109">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="7d8c0-110">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="7d8c0-110">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7d8c0-111">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="7d8c0-111">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="7d8c0-112">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="7d8c0-112">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7d8c0-113">/GUI</span><span class="sxs-lookup"><span data-stu-id="7d8c0-113">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="7d8c0-114">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7d8c0-114">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="7d8c0-115">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="7d8c0-115">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7d8c0-116">/Logu</span><span class="sxs-lookup"><span data-stu-id="7d8c0-116">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="7d8c0-117">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="7d8c0-117">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="7d8c0-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7d8c0-118">Related topics</span></span>


[<span data-ttu-id="7d8c0-119">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="7d8c0-119">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





