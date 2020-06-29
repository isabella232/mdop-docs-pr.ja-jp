---
title: DELETE SERVER
description: DELETE SERVER
author: dansimp
ms.assetid: 4c929639-1c1d-47c3-9225-cc4d7a8736f0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 92af31a818174fb4b0e82a11c918af2484ac2bce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821694"
---
# <span data-ttu-id="3827f-103">DELETE SERVER</span><span class="sxs-lookup"><span data-stu-id="3827f-103">DELETE SERVER</span></span>


<span data-ttu-id="3827f-104">発行サーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="3827f-104">Removes a publishing server.</span></span>

<span data-ttu-id="3827f-105">**注** このコマンドでは、サーバーによってクライアントに公開されたアプリケーションやパッケージは削除されません。</span><span class="sxs-lookup"><span data-stu-id="3827f-105">**Note** This command does not remove any applications or packages published to the client by the server.</span></span> <span data-ttu-id="3827f-106">各アプリケーションについては、SFTMIME**消去アプリ**コマンドを使用して、[**パッケージの削除**] コマンドを実行すると、それらのアプリケーションとパッケージがクライアントから完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="3827f-106">For each application, use the SFTMIME **CLEAR APP** command followed by the **DELETE PACKAGE** command to completely remove those applications and packages from the client.</span></span>

 

`SFTMIME DELETE SERVER:server-name [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3827f-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3827f-107">Parameter</span></span></th>
<th align="left"><span data-ttu-id="3827f-108">説明</span><span class="sxs-lookup"><span data-stu-id="3827f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3827f-109">サーバー: &lt; サーバー名&gt;</span><span class="sxs-lookup"><span data-stu-id="3827f-109">SERVER:&lt;server-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="3827f-110">発行サーバーの表示名。</span><span class="sxs-lookup"><span data-stu-id="3827f-110">The display name of the publishing server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3827f-111">/LOG</span><span class="sxs-lookup"><span data-stu-id="3827f-111">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="3827f-112">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="3827f-112">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3827f-113">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="3827f-113">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="3827f-114">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="3827f-114">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3827f-115">/GUI</span><span class="sxs-lookup"><span data-stu-id="3827f-115">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="3827f-116">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3827f-116">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="3827f-117">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="3827f-117">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3827f-118">/Logu</span><span class="sxs-lookup"><span data-stu-id="3827f-118">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="3827f-119">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="3827f-119">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="3827f-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3827f-120">Related topics</span></span>


[<span data-ttu-id="3827f-121">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="3827f-121">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





