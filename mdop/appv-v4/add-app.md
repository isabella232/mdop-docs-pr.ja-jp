---
title: ADD APP
description: ADD APP
author: dansimp
ms.assetid: 329fd0c8-a795-49be-b0fd-1367c5b4a34b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ac83c0cf130e8de1d34d42d74e946716e4503246
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819897"
---
# <span data-ttu-id="7e447-103">ADD APP</span><span class="sxs-lookup"><span data-stu-id="7e447-103">ADD APP</span></span>


<span data-ttu-id="7e447-104">アプリケーションレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="7e447-104">Adds an application record.</span></span>

`SFTMIME ADD APP:application /OSD osd-pathname [/ICON icon-pathname] [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7e447-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7e447-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="7e447-106">説明</span><span class="sxs-lookup"><span data-stu-id="7e447-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7e447-107">アプリ: &lt; アプリケーション&gt;</span><span class="sxs-lookup"><span data-stu-id="7e447-107">APP:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="7e447-108">アプリケーションの名前とバージョン (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="7e447-108">The name and version (optional) of the application.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7e447-109">/Osd &lt; osd-pathname&gt;</span><span class="sxs-lookup"><span data-stu-id="7e447-109">/OSD &lt;osd-pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="7e447-110">OSD ファイルのパスまたは URL。</span><span class="sxs-lookup"><span data-stu-id="7e447-110">The path or URL for the OSD file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7e447-111">/アイコン &lt; のアイコン-パス名&gt;</span><span class="sxs-lookup"><span data-stu-id="7e447-111">/ICON &lt;icon-pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="7e447-112">アイコンファイルのパスまたは URL。</span><span class="sxs-lookup"><span data-stu-id="7e447-112">The path or URL for the icon file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7e447-113">/LOG</span><span class="sxs-lookup"><span data-stu-id="7e447-113">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="7e447-114">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="7e447-114">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7e447-115">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="7e447-115">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="7e447-116">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="7e447-116">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7e447-117">/GUI</span><span class="sxs-lookup"><span data-stu-id="7e447-117">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="7e447-118">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e447-118">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="7e447-119">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="7e447-119">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7e447-120">/Logu</span><span class="sxs-lookup"><span data-stu-id="7e447-120">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="7e447-121">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="7e447-121">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="7e447-122">**注** 結果として得られたアプリケーション名は、アプリ: application で指定された名前ではなく、OSD ファイルから取得されます。 &lt; &gt;</span><span class="sxs-lookup"><span data-stu-id="7e447-122">**Note** The resulting name of the application will be taken from the OSD file and not from the name provided in APP:&lt;application&gt;.</span></span>

 

## <span data-ttu-id="7e447-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7e447-123">Related topics</span></span>


[<span data-ttu-id="7e447-124">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="7e447-124">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





