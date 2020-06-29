---
title: HELP
description: HELP
author: dansimp
ms.assetid: 0ddb5f18-0c0a-45ea-b7c7-2d4749e3d35d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 395e6199529ccbe708aa7d1ac6673ea6f9494ae4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821464"
---
# <span data-ttu-id="4e7e6-103">HELP</span><span class="sxs-lookup"><span data-stu-id="4e7e6-103">HELP</span></span>


<span data-ttu-id="4e7e6-104">Application Virtualization (App-v) で使うことができるさまざまな SFTMIME コマンドに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-104">Displays information about the various SFTMIME commands that can be used in Application Virtualization (App-V).</span></span>

## <span data-ttu-id="4e7e6-105">HELP</span><span class="sxs-lookup"><span data-stu-id="4e7e6-105">HELP</span></span>


`SFTMIME [/? | /HELP [VERB:<verb>]]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4e7e6-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4e7e6-106">Parameter</span></span></th>
<th align="left"><span data-ttu-id="4e7e6-107">説明</span><span class="sxs-lookup"><span data-stu-id="4e7e6-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4e7e6-108">/?,/HELP</span><span class="sxs-lookup"><span data-stu-id="4e7e6-108">/?, /HELP</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e7e6-109">使用状況の情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-109">Displays usage information.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4e7e6-110">動詞</span><span class="sxs-lookup"><span data-stu-id="4e7e6-110">verb</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e7e6-111">実行するコマンド ([追加]、[更新]、[ヘルプ]、[削除] など)。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-111">The command to run, such as ADD, REFRESH, HELP or REMOVE.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4e7e6-112">object</span><span class="sxs-lookup"><span data-stu-id="4e7e6-112">object</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e7e6-113">コマンドの適用対象 (アプリ: 既定のアプリケーションなど) &quot;&quot;</span><span class="sxs-lookup"><span data-stu-id="4e7e6-113">What the command applies to, such as APP:&quot;Default Application.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4e7e6-114">引き</span><span class="sxs-lookup"><span data-stu-id="4e7e6-114">parameters</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e7e6-115">指定した動詞とオブジェクトの省略可能なパラメーター。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-115">Optional parameters for the specified verb and object.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4e7e6-116">/LOG</span><span class="sxs-lookup"><span data-stu-id="4e7e6-116">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e7e6-117">指定したパス名にログ出力を記録します。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-117">Log output to the specified path name.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4e7e6-118">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="4e7e6-118">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e7e6-119">アクティブなコンソールウィンドウに出力を表示します (既定)。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-119">Displays output in the active console window (default).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4e7e6-120">/GUI</span><span class="sxs-lookup"><span data-stu-id="4e7e6-120">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e7e6-121">ダイアログボックスでエラーを表示します (クエリに対しては有効ではありません)。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-121">Displays errors in a dialog box (not valid for queries).</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="4e7e6-122">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-122">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4e7e6-123">/Logu</span><span class="sxs-lookup"><span data-stu-id="4e7e6-123">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e7e6-124">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-124">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="4e7e6-125">次の表で説明されている動詞はサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-125">The verbs described in the following table are supported.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4e7e6-126">ADD</span><span class="sxs-lookup"><span data-stu-id="4e7e6-126">ADD</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e7e6-127">新しいアプリケーション、パッケージ、ファイルの種類の関連付け、または発行サーバーを App-v クライアントに追加します。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-127">Adds a new application, package, file type association, or publishing server to the App-V Client.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4e7e6-128">設定</span><span class="sxs-lookup"><span data-stu-id="4e7e6-128">CONFIGURE</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e7e6-129">アプリケーション、パッケージ、ファイルの種類の関連付け、または発行サーバーの構成を変更します。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-129">Changes the configuration of an application, a package, a file type association, or a publishing server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4e7e6-130">DELETE</span><span class="sxs-lookup"><span data-stu-id="4e7e6-130">DELETE</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e7e6-131">アプリケーション、パッケージ、ファイルの種類の関連付け、またはサーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-131">Removes applications, packages, file type associations, or servers.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4e7e6-132">込む</span><span class="sxs-lookup"><span data-stu-id="4e7e6-132">LOAD</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e7e6-133">ファイルシステムキャッシュにパッケージを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-133">Loads a package into the file system cache.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4e7e6-134">]5D</span><span class="sxs-lookup"><span data-stu-id="4e7e6-134">REPAIR</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e7e6-135">アプリケーションの個人設定をリセットします。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-135">Resets your personal settings for an application.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4e7e6-136">非</span><span class="sxs-lookup"><span data-stu-id="4e7e6-136">REFRESH</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e7e6-137">発行サーバーの更新をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-137">Triggers a publishing server refresh.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4e7e6-138">出版</span><span class="sxs-lookup"><span data-stu-id="4e7e6-138">PUBLISH</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e7e6-139">ユーザーの [スタート] メニュー、デスクトップ、またはその他の指定した場所にアプリケーションのショートカットを公開します。または、パッケージ全体のコンテンツを公開するために使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-139">Publishes an application shortcut to the user's Start menu, desktop, or other specified location, or can be used to publish the contents of an entire package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4e7e6-140">発行</span><span class="sxs-lookup"><span data-stu-id="4e7e6-140">UNPUBLISH</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e7e6-141">パッケージ全体のショートカットとファイルの種類を削除します。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-141">Removes the shortcuts and file types for an entire package.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4e7e6-142">照会</span><span class="sxs-lookup"><span data-stu-id="4e7e6-142">QUERY</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e7e6-143">アプリケーション、パッケージ、ファイルの種類の関連付け、または公開サーバーの現在の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-143">Gets a current list of applications, packages, file type associations, or publishing servers.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4e7e6-144">CLEAR</span><span class="sxs-lookup"><span data-stu-id="4e7e6-144">CLEAR</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e7e6-145">1つまたは複数のアプリケーションの個人用設定とデスクトップの構成を削除します。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-145">Removes your personal settings and desktop configurations for one or more applications.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4e7e6-146">アドイン</span><span class="sxs-lookup"><span data-stu-id="4e7e6-146">UNLOAD</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e7e6-147">ファイルシステムキャッシュからパッケージをアンロードします。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-147">Unloads a package from the file system cache.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4e7e6-148">LOCK</span><span class="sxs-lookup"><span data-stu-id="4e7e6-148">LOCK</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e7e6-149">ファイルシステムキャッシュで指定されたアプリケーションをロックします。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-149">Locks the application specified in the file system cache.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4e7e6-150">ロック</span><span class="sxs-lookup"><span data-stu-id="4e7e6-150">UNLOCK</span></span></p></td>
<td align="left"><p><span data-ttu-id="4e7e6-151">ファイルシステムキャッシュで指定されたアプリケーションのロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-151">Unlocks the application specified in the file system cache.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="4e7e6-152">上記の操作の詳細については、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-152">For more information about the preceding actions, use the following command:</span></span>

`SFTMIME /HELP VERB:verb`

<span data-ttu-id="4e7e6-153">たとえば、次のコマンドでは、ADD 動詞の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e7e6-153">For example, the following command will display information for the ADD verb:</span></span>

`SFTMIME /HELP VERB:ADD`

## <span data-ttu-id="4e7e6-154">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4e7e6-154">Related topics</span></span>


[<span data-ttu-id="4e7e6-155">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="4e7e6-155">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





