---
title: UNLOAD APP
description: UNLOAD APP
author: dansimp
ms.assetid: f0d729ae-8772-498b-be11-1a4b35499c53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f1ae30f5b8c788f8763c2c2b9d1c1956182750d3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815154"
---
# <span data-ttu-id="a5af8-103">UNLOAD APP</span><span class="sxs-lookup"><span data-stu-id="a5af8-103">UNLOAD APP</span></span>


<span data-ttu-id="a5af8-104">アプリケーションおよびパッケージ内の他のすべてのアプリケーションをファイルシステムキャッシュからアンロードします。</span><span class="sxs-lookup"><span data-stu-id="a5af8-104">Unloads the application and all other applications in the package from the file system cache.</span></span>

`SFTMIME UNLOAD APP:application [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a5af8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5af8-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="a5af8-106">説明</span><span class="sxs-lookup"><span data-stu-id="a5af8-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a5af8-107">アプリ: &lt; アプリケーション&gt;</span><span class="sxs-lookup"><span data-stu-id="a5af8-107">APP:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="a5af8-108">アンロードするアプリケーションの名前とバージョン (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="a5af8-108">The name and version (optional) of the application to unload.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a5af8-109">/LOG</span><span class="sxs-lookup"><span data-stu-id="a5af8-109">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="a5af8-110">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="a5af8-110">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a5af8-111">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="a5af8-111">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="a5af8-112">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="a5af8-112">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a5af8-113">/GUI</span><span class="sxs-lookup"><span data-stu-id="a5af8-113">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="a5af8-114">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5af8-114">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="a5af8-115">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="a5af8-115">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a5af8-116">/Logu</span><span class="sxs-lookup"><span data-stu-id="a5af8-116">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="a5af8-117">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="a5af8-117">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="a5af8-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a5af8-118">Related topics</span></span>


[<span data-ttu-id="a5af8-119">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="a5af8-119">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





