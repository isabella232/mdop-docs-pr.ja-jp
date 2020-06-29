---
title: LOCK APP
description: LOCK APP
author: dansimp
ms.assetid: 30673433-4364-499f-8116-cb135fe2716f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 319271640c2550fc94479e876a59b30d3b2bf7ae
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816244"
---
# <span data-ttu-id="aa82c-103">LOCK APP</span><span class="sxs-lookup"><span data-stu-id="aa82c-103">LOCK APP</span></span>


<span data-ttu-id="aa82c-104">ファイルシステムキャッシュで指定されたアプリケーションをロックします。</span><span class="sxs-lookup"><span data-stu-id="aa82c-104">Locks the application specified in the file system cache.</span></span>

`SFTMIME LOCK APP:application [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="aa82c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aa82c-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="aa82c-106">説明</span><span class="sxs-lookup"><span data-stu-id="aa82c-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aa82c-107">アプリ: &lt; アプリケーション&gt;</span><span class="sxs-lookup"><span data-stu-id="aa82c-107">APP:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="aa82c-108">ロックするアプリケーションの名前とバージョン (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="aa82c-108">The name and version (optional) of the application to lock.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aa82c-109">/LOG</span><span class="sxs-lookup"><span data-stu-id="aa82c-109">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="aa82c-110">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="aa82c-110">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aa82c-111">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="aa82c-111">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="aa82c-112">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="aa82c-112">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aa82c-113">/GUI</span><span class="sxs-lookup"><span data-stu-id="aa82c-113">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="aa82c-114">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa82c-114">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="aa82c-115">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="aa82c-115">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aa82c-116">/Logu</span><span class="sxs-lookup"><span data-stu-id="aa82c-116">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="aa82c-117">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="aa82c-117">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="aa82c-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="aa82c-118">Related topics</span></span>


[<span data-ttu-id="aa82c-119">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="aa82c-119">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 




