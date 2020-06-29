---
title: CONFIGURE APP
description: CONFIGURE APP
author: dansimp
ms.assetid: fcfb4f86-8b7c-4208-bca3-955fd067079f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 42ff17e180df262deed3fe79674ad6fda6f0be4e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819377"
---
# <span data-ttu-id="3f04d-103">CONFIGURE APP</span><span class="sxs-lookup"><span data-stu-id="3f04d-103">CONFIGURE APP</span></span>


<span data-ttu-id="3f04d-104">ユーザーがアプリケーションに関連付けられているアイコンを変更できるようにしますが、既存のショートカットまたはファイルの種類の関連付けのアイコンは更新されません。</span><span class="sxs-lookup"><span data-stu-id="3f04d-104">Enables the user to change the icon associated with an application but does not update the icon on existing shortcuts or file type associations.</span></span>

`SFTMIME CONFIGURE APP:application /ICON icon-pathname                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3f04d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3f04d-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="3f04d-106">説明</span><span class="sxs-lookup"><span data-stu-id="3f04d-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f04d-107">アプリ: &lt; アプリケーション&gt;</span><span class="sxs-lookup"><span data-stu-id="3f04d-107">APP:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f04d-108">アプリケーションの名前とバージョン (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="3f04d-108">The name and version (optional) of the application.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3f04d-109">/アイコン &lt; のアイコン-パス名&gt;</span><span class="sxs-lookup"><span data-stu-id="3f04d-109">/ICON &lt;icon-pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f04d-110">アイコンファイルのパスまたは URL。</span><span class="sxs-lookup"><span data-stu-id="3f04d-110">The path or URL for the icon file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f04d-111">/LOG</span><span class="sxs-lookup"><span data-stu-id="3f04d-111">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f04d-112">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="3f04d-112">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3f04d-113">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="3f04d-113">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f04d-114">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="3f04d-114">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f04d-115">/GUI</span><span class="sxs-lookup"><span data-stu-id="3f04d-115">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f04d-116">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f04d-116">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="3f04d-117">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="3f04d-117">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3f04d-118">/Logu</span><span class="sxs-lookup"><span data-stu-id="3f04d-118">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="3f04d-119">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="3f04d-119">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="3f04d-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3f04d-120">Related topics</span></span>


[<span data-ttu-id="3f04d-121">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="3f04d-121">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





