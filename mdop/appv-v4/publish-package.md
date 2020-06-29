---
title: PUBLISH PACKAGE
description: PUBLISH PACKAGE
author: dansimp
ms.assetid: a33e72dd-194f-4283-8e99-4584ab13de53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 00b63389986f495d9405939245a50575bae453f9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815814"
---
# <span data-ttu-id="de861-103">PUBLISH PACKAGE</span><span class="sxs-lookup"><span data-stu-id="de861-103">PUBLISH PACKAGE</span></span>


<span data-ttu-id="de861-104">パッケージ全体のコンテンツを公開します。</span><span class="sxs-lookup"><span data-stu-id="de861-104">Publishes the contents of an entire package.</span></span>

`SFTMIME PUBLISH PACKAGE:package-name /MANIFEST manifest-path [/GLOBAL]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="de861-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="de861-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="de861-106">説明</span><span class="sxs-lookup"><span data-stu-id="de861-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="de861-107">パッケージ: &lt; パッケージ名&gt;</span><span class="sxs-lookup"><span data-stu-id="de861-107">PACKAGE:&lt;package-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="de861-108">ユーザーが表示できるパッケージのわかりやすい名前。</span><span class="sxs-lookup"><span data-stu-id="de861-108">User-visible and user-friendly name for the package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="de861-109">/マニフェスト &lt; マニフェストパス&gt;</span><span class="sxs-lookup"><span data-stu-id="de861-109">/MANIFEST &lt;manifest-path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="de861-110">パッケージに含まれているアプリケーションとそのすべての発行情報を一覧表示するマニフェストファイルのパスまたは URL。</span><span class="sxs-lookup"><span data-stu-id="de861-110">The path or URL of the manifest file that lists the applications included in the package and all of their publishing information.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="de861-111">/グローバル</span><span class="sxs-lookup"><span data-stu-id="de861-111">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="de861-112">存在する場合、このコンピューター上のすべてのユーザーがパッケージを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="de861-112">If present, the package will be available for all users on this computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="de861-113">/LOG</span><span class="sxs-lookup"><span data-stu-id="de861-113">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="de861-114">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="de861-114">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="de861-115">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="de861-115">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="de861-116">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="de861-116">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="de861-117">/GUI</span><span class="sxs-lookup"><span data-stu-id="de861-117">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="de861-118">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="de861-118">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="de861-119">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="de861-119">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="de861-120">/Logu</span><span class="sxs-lookup"><span data-stu-id="de861-120">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="de861-121">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="de861-121">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="de861-122">**重要** パッケージは、既に Application Virtualization クライアントに追加されている必要があります。マニフェストファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="de861-122">**Important** The package must already have been added to the Application Virtualization Client, and the manifest file is required.</span></span>

<span data-ttu-id="de861-123">**グローバル**パラメーターを使用するには、[パッケージの発行] コマンドをローカルの管理者として実行する必要があります。それ以外の場合は、 **Managetypes**と**publishshortcut**のアクセス許可しか必要ありません。</span><span class="sxs-lookup"><span data-stu-id="de861-123">To use the **GLOBAL** parameter, the PUBLISH PACKAGE command must be run as local Administrator; otherwise, only **ManageTypes** and **PublishShortcut** permissions are needed.</span></span>

<span data-ttu-id="de861-124">**グローバル**パラメーターを指定せずに発行すると、ユーザーはパッケージ内のアプリケーションにアクセスできるようになり、マニフェストに記載されているファイルの種類とショートカットが、ユーザーのプロファイルに発行されます。</span><span class="sxs-lookup"><span data-stu-id="de861-124">Publishing without the **GLOBAL** parameter grants the user access to the applications in the package and publishes the file types and shortcuts listed in the manifest to the user’s profile.</span></span>

<span data-ttu-id="de861-125">**グローバル**パラメーターを指定して発行すると、マニフェストに記載されているファイルの種類とショートカットが "すべてのユーザー" プロファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="de861-125">Publishing with the **GLOBAL** parameter adds the file types and shortcuts listed in the manifest to the “All Users” profile.</span></span>

<span data-ttu-id="de861-126">パッケージがグローバルではなく、**グローバル**パラメーターを使用している場合は、パッケージはグローバルになり、すべてのユーザーが使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="de861-126">If the package is not global before the call and the **GLOBAL** parameter is used, the package is made global and available to all users.</span></span>

 

## <span data-ttu-id="de861-127">関連トピック</span><span class="sxs-lookup"><span data-stu-id="de861-127">Related topics</span></span>


[<span data-ttu-id="de861-128">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="de861-128">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





