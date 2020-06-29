---
title: LOAD APP
description: LOAD APP
author: dansimp
ms.assetid: 7b727d0c-5423-419d-92ef-7ebbc6343e79
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 02bd6e35da898f5b34f7efc21cbc01a72d555b8d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816247"
---
# <span data-ttu-id="20fa4-103">LOAD APP</span><span class="sxs-lookup"><span data-stu-id="20fa4-103">LOAD APP</span></span>


<span data-ttu-id="20fa4-104">指定したアプリケーションとパッケージ内の他のすべてのアプリケーションをファイルシステムキャッシュに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="20fa4-104">Loads the specified application and all other applications in the package into the file system cache.</span></span>

<span data-ttu-id="20fa4-105">**注** Load **APP**コマンドは、読み込みプロセスを開始し、デスクトップ通知領域に進行状況バーを表示します。</span><span class="sxs-lookup"><span data-stu-id="20fa4-105">**Note** The **LOAD APP** command starts the load process and a progress bar is displayed in the Desktop Notification Area.</span></span> <span data-ttu-id="20fa4-106">コマンドはこのプロセスを開始した直後に終了するため、読み込みエラーは同じ場所に表示されます。</span><span class="sxs-lookup"><span data-stu-id="20fa4-106">The command exits immediately after starting this process, so any load errors are displayed in the same location.</span></span> <span data-ttu-id="20fa4-107">デスクトップ通知領域を使用せずにコマンドラインから読み込みプロセスを開始する場合は、[**パッケージの読み込み**] コマンドを使います。</span><span class="sxs-lookup"><span data-stu-id="20fa4-107">Use the **LOAD PACKAGE** command if you want to start the load process from the command line without using the Desktop Notification Area.</span></span>

 

`SFTMIME LOAD APP:application [/LOG log-pathname | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="20fa4-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="20fa4-108">Parameter</span></span></th>
<th align="left"><span data-ttu-id="20fa4-109">説明</span><span class="sxs-lookup"><span data-stu-id="20fa4-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20fa4-110">アプリ: &lt; アプリケーション&gt;</span><span class="sxs-lookup"><span data-stu-id="20fa4-110">APP:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="20fa4-111">読み込むアプリケーションの名前とバージョン (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="20fa4-111">The name and version (optional) of the application to load.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="20fa4-112">/LOG</span><span class="sxs-lookup"><span data-stu-id="20fa4-112">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="20fa4-113">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="20fa4-113">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20fa4-114">/GUI</span><span class="sxs-lookup"><span data-stu-id="20fa4-114">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="20fa4-115">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="20fa4-115">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="20fa4-116">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="20fa4-116">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="20fa4-117">/Logu</span><span class="sxs-lookup"><span data-stu-id="20fa4-117">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="20fa4-118">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="20fa4-118">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="20fa4-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="20fa4-119">Related topics</span></span>


[<span data-ttu-id="20fa4-120">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="20fa4-120">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





