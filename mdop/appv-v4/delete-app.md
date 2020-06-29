---
title: DELETE APP
description: DELETE APP
author: dansimp
ms.assetid: 2f89c0c0-373b-4389-a26d-67b3f9712957
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c27c70ef3227ebaf6b16bcb1fbb4b4e65b7cb7f4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821717"
---
# <span data-ttu-id="457fc-103">DELETE APP</span><span class="sxs-lookup"><span data-stu-id="457fc-103">DELETE APP</span></span>


<span data-ttu-id="457fc-104">ファイルシステムキャッシュからアプリケーションレコードを削除して、表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="457fc-104">Removes an application record from the file system cache to make it no longer visible.</span></span> <span data-ttu-id="457fc-105">ユーザーのショートカットとファイルの種類の関連付けは非表示になりますが、削除されません。</span><span class="sxs-lookup"><span data-stu-id="457fc-105">Users’ shortcuts and file type associations are hidden but not deleted.</span></span> <span data-ttu-id="457fc-106">ユーザー設定は削除されません。</span><span class="sxs-lookup"><span data-stu-id="457fc-106">No user settings are removed.</span></span>

`SFTMIME DELETE APP:application [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="457fc-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="457fc-107">Parameter</span></span></th>
<th align="left"><span data-ttu-id="457fc-108">説明</span><span class="sxs-lookup"><span data-stu-id="457fc-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="457fc-109">アプリ: &lt; アプリケーション&gt;</span><span class="sxs-lookup"><span data-stu-id="457fc-109">APP:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="457fc-110">削除するアプリケーションの名前とバージョン (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="457fc-110">The name and version (optional) of the application to be removed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="457fc-111">/LOG</span><span class="sxs-lookup"><span data-stu-id="457fc-111">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="457fc-112">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="457fc-112">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="457fc-113">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="457fc-113">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="457fc-114">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="457fc-114">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="457fc-115">/GUI</span><span class="sxs-lookup"><span data-stu-id="457fc-115">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="457fc-116">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="457fc-116">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="457fc-117">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="457fc-117">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="457fc-118">/Logu</span><span class="sxs-lookup"><span data-stu-id="457fc-118">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="457fc-119">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="457fc-119">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="457fc-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="457fc-120">Related topics</span></span>


[<span data-ttu-id="457fc-121">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="457fc-121">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





