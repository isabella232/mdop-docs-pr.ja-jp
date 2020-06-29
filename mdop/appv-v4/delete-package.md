---
title: DELETE PACKAGE
description: DELETE PACKAGE
author: dansimp
ms.assetid: 8f7a4598-610d-490e-a224-426acce01a9f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a0051967ca308e88d143b8116330f5d770d6086d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821697"
---
# <span data-ttu-id="867c2-103">DELETE PACKAGE</span><span class="sxs-lookup"><span data-stu-id="867c2-103">DELETE PACKAGE</span></span>


<span data-ttu-id="867c2-104">パッケージレコードとそれに関連付けられているアプリケーションを削除します。</span><span class="sxs-lookup"><span data-stu-id="867c2-104">Removes a package record and the applications associated with it.</span></span>

`SFTMIME DELETE PACKAGE:package-name                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="867c2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="867c2-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="867c2-106">説明</span><span class="sxs-lookup"><span data-stu-id="867c2-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="867c2-107">パッケージ: &lt; パッケージ名&gt;</span><span class="sxs-lookup"><span data-stu-id="867c2-107">PACKAGE:&lt;package-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="867c2-108">削除されるパッケージの名前。</span><span class="sxs-lookup"><span data-stu-id="867c2-108">The name of the package to be removed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="867c2-109">/LOG</span><span class="sxs-lookup"><span data-stu-id="867c2-109">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="867c2-110">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="867c2-110">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="867c2-111">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="867c2-111">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="867c2-112">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="867c2-112">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="867c2-113">/GUI</span><span class="sxs-lookup"><span data-stu-id="867c2-113">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="867c2-114">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="867c2-114">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="867c2-115">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="867c2-115">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="867c2-116">/Logu</span><span class="sxs-lookup"><span data-stu-id="867c2-116">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="867c2-117">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="867c2-117">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="867c2-118">**重要** [パッケージの削除] コマンドでは、常にパッケージのグローバル削除が実行され、グローバルなファイルの種類とショートカットのみが削除されます。</span><span class="sxs-lookup"><span data-stu-id="867c2-118">**Important** The DELETE PACKAGE command always performs a global delete of the package and deletes only global file types and shortcuts.</span></span>

<span data-ttu-id="867c2-119">パッケージがグローバルである場合、このコマンドはローカル管理者として実行する必要があります。それ以外の場合は、 **Deleteapp**のアクセス許可のみが必要です。</span><span class="sxs-lookup"><span data-stu-id="867c2-119">If the package is global, this command must be run as local Administrator; otherwise, only **DeleteApp** permission is needed.</span></span>

 

## <span data-ttu-id="867c2-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="867c2-120">Related topics</span></span>


[<span data-ttu-id="867c2-121">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="867c2-121">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





