---
title: LOAD PACKAGE
description: LOAD PACKAGE
author: dansimp
ms.assetid: eb19116d-e5d0-445c-b2f0-3116a09384d7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 938aa92696c8530c91d9a7acaac42408de534edc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816237"
---
# <span data-ttu-id="16acf-103">LOAD PACKAGE</span><span class="sxs-lookup"><span data-stu-id="16acf-103">LOAD PACKAGE</span></span>


<span data-ttu-id="16acf-104">指定されたパッケージをファイルシステムキャッシュに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="16acf-104">Loads the specified package into the file system cache.</span></span>

`SFTMIME LOAD PACKAGE:package-name [/SFTPATH sft-pathname]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="16acf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="16acf-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="16acf-106">説明</span><span class="sxs-lookup"><span data-stu-id="16acf-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="16acf-107">パッケージ: &lt; パッケージ名&gt;</span><span class="sxs-lookup"><span data-stu-id="16acf-107">PACKAGE:&lt;package-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="16acf-108">読み込むパッケージの名前。</span><span class="sxs-lookup"><span data-stu-id="16acf-108">The name of the package to load.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="16acf-109">/SFTPATH &lt; sft-パス名&gt;</span><span class="sxs-lookup"><span data-stu-id="16acf-109">/SFTPATH &lt;sft-pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="16acf-110">指定されている場合、読み込み元の SFT ファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="16acf-110">If specified, the path to an SFT file to load from.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="16acf-111">/LOG</span><span class="sxs-lookup"><span data-stu-id="16acf-111">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="16acf-112">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="16acf-112">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="16acf-113">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="16acf-113">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="16acf-114">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="16acf-114">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="16acf-115">/GUI</span><span class="sxs-lookup"><span data-stu-id="16acf-115">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="16acf-116">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="16acf-116">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="16acf-117">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="16acf-117">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="16acf-118">/Logu</span><span class="sxs-lookup"><span data-stu-id="16acf-118">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="16acf-119">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="16acf-119">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="16acf-120">**注** SFTPATH が指定されていない場合、クライアントは、OSD ファイル、ApplicationSourceRoot registry key 値、または OverrideURL 設定に基づいて、使用するように構成されているパスを使用してパッケージを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="16acf-120">**Note** If no SFTPATH is specified, the client will load the package by using the path it has been configured to use, based on the OSD file, the ApplicationSourceRoot registry key value, or the OverrideURL setting.</span></span>

<span data-ttu-id="16acf-121">[**パッケージの読み込み**] コマンドは、同期読み込みを実行します。パッケージが完全に読み込まれるか、またはエラー状態になるまでは完了しません。</span><span class="sxs-lookup"><span data-stu-id="16acf-121">The **LOAD PACKAGE** command performs a synchronous load and will not be complete until the package is fully loaded or until it encounters an error condition.</span></span>

 

## <span data-ttu-id="16acf-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="16acf-122">Related topics</span></span>


[<span data-ttu-id="16acf-123">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="16acf-123">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





