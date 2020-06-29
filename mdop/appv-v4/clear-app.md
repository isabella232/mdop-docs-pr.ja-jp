---
title: CLEAR APP
description: CLEAR APP
author: dansimp
ms.assetid: c2e63031-5941-45e4-9863-127231cfa25b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 26f2363bf15bd33d0da3fee48319b215e6791db9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821994"
---
# <span data-ttu-id="55a42-103">CLEAR APP</span><span class="sxs-lookup"><span data-stu-id="55a42-103">CLEAR APP</span></span>


<span data-ttu-id="55a42-104">現在のユーザーの設定とアプリケーションの発行構成をクリアします。</span><span class="sxs-lookup"><span data-stu-id="55a42-104">Clears the current user's settings and publishing configurations for an application.</span></span>

`SFTMIME CLEAR APP:application [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="55a42-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="55a42-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="55a42-106">説明</span><span class="sxs-lookup"><span data-stu-id="55a42-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55a42-107">アプリ: &lt; アプリケーション&gt;</span><span class="sxs-lookup"><span data-stu-id="55a42-107">APP:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="55a42-108">アプリケーションの名前とバージョン (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="55a42-108">The name and version (optional) of the application.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55a42-109">/LOG</span><span class="sxs-lookup"><span data-stu-id="55a42-109">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="55a42-110">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="55a42-110">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55a42-111">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="55a42-111">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="55a42-112">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="55a42-112">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55a42-113">/GUI</span><span class="sxs-lookup"><span data-stu-id="55a42-113">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="55a42-114">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="55a42-114">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="55a42-115">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="55a42-115">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55a42-116">/Logu</span><span class="sxs-lookup"><span data-stu-id="55a42-116">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="55a42-117">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="55a42-117">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="55a42-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="55a42-118">Related topics</span></span>


[<span data-ttu-id="55a42-119">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="55a42-119">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





