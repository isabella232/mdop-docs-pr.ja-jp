---
title: ADD PACKAGE
description: ADD PACKAGE
author: dansimp
ms.assetid: aa83928d-a234-4395-831e-2a7ef786ff53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 925349ce5bdf041b6a8768b5413692966e1cfc1e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822397"
---
# <span data-ttu-id="2e93d-103">ADD PACKAGE</span><span class="sxs-lookup"><span data-stu-id="2e93d-103">ADD PACKAGE</span></span>


<span data-ttu-id="2e93d-104">パッケージレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="2e93d-104">Adds a package record.</span></span> <span data-ttu-id="2e93d-105">パッケージが既に存在する場合は、このコマンドによって既存のパッケージの構成が更新されます。</span><span class="sxs-lookup"><span data-stu-id="2e93d-105">If the package already exists, this command will update the configuration of the existing package.</span></span>

`SFTMIME ADD PACKAGE:package-name /MANIFEST manifest-path                 [/OVERRIDEURL url [/AUTOLOADONREFRESH] [/AUTOLOADONLOGIN]                 [/AUTOLOADONLAUNCH] [/AUTOLOADTARGET {NONE|ALL|PREVUSED}]                 [/GLOBAL] [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2e93d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2e93d-106">Parameter</span></span></th>
<th align="left"><span data-ttu-id="2e93d-107">説明</span><span class="sxs-lookup"><span data-stu-id="2e93d-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2e93d-108">パッケージ: &lt; パッケージ名&gt;</span><span class="sxs-lookup"><span data-stu-id="2e93d-108">PACKAGE:&lt;package-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e93d-109">ユーザーが表示できるパッケージのわかりやすい名前。</span><span class="sxs-lookup"><span data-stu-id="2e93d-109">User-visible and user-friendly name for the package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2e93d-110">/マニフェスト &lt; マニフェストパス&gt;</span><span class="sxs-lookup"><span data-stu-id="2e93d-110">/MANIFEST &lt;manifest-path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e93d-111">パッケージに含まれているアプリケーションとそのすべての発行情報を一覧表示するマニフェストファイルのパス。</span><span class="sxs-lookup"><span data-stu-id="2e93d-111">The path of the manifest file that lists the applications included in the package and all of their publishing information.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2e93d-112">/OVERRIDEURL &lt; URL&gt;</span><span class="sxs-lookup"><span data-stu-id="2e93d-112">/OVERRIDEURL &lt;URL&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e93d-113">パッケージの SFT ファイルの場所。</span><span class="sxs-lookup"><span data-stu-id="2e93d-113">The location of the package's SFT file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2e93d-114">/Autoloadonrefresh</span><span class="sxs-lookup"><span data-stu-id="2e93d-114">/AUTOLOADONREFRESH</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e93d-115">バックグラウンド読み込みは、発行の更新後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="2e93d-115">Background loading is performed after a publishing refresh.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2e93d-116">/Autoloadonlogin</span><span class="sxs-lookup"><span data-stu-id="2e93d-116">/AUTOLOADONLOGIN</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e93d-117">バックグラウンド読み込みは、ユーザーがログインしたときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="2e93d-117">Background loading is performed when a user logs in.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2e93d-118">/Autoloadonlaunch</span><span class="sxs-lookup"><span data-stu-id="2e93d-118">/AUTOLOADONLAUNCH</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e93d-119">バックグラウンド読み込みは、ユーザーがパッケージからアプリケーションを開始した後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="2e93d-119">Background loading is performed after a user starts an application from the package.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2e93d-120">/Autoloadターゲットターゲット</span><span class="sxs-lookup"><span data-stu-id="2e93d-120">/AUTOLOADTARGET target</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e93d-121">パッケージから自動読み込みされるアプリケーションを示します。</span><span class="sxs-lookup"><span data-stu-id="2e93d-121">Indicates which applications from the package will be autoloaded.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2e93d-122">-</span><span class="sxs-lookup"><span data-stu-id="2e93d-122">NONE</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e93d-123">Autoloadonxxx フラグが存在するにもかかわらず、自動読み込みは実行されません。</span><span class="sxs-lookup"><span data-stu-id="2e93d-123">No autoloading will be performed, despite the presence of any /AUTOLOADONxxx flags.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2e93d-124">[ALL] (すべて)</span><span class="sxs-lookup"><span data-stu-id="2e93d-124">ALL</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e93d-125">自動ロードトリガーが有効になっている場合、パッケージ内のすべてのアプリケーションは、前に開始されたかどうかにかかわらずキャッシュに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="2e93d-125">If an autoload trigger is enabled, all applications in the package will be loaded into cache whether or not they have been previously started.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2e93d-126">PREVUSED</span><span class="sxs-lookup"><span data-stu-id="2e93d-126">PREVUSED</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e93d-127">自動ロードトリガーが有効になっている場合、このパッケージ内のアプリケーションがユーザーによって以前に起動された場合、パッケージは読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="2e93d-127">If an autoload trigger is enabled, the package will load if any applications in this package have previously been started by a user.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2e93d-128">/グローバル</span><span class="sxs-lookup"><span data-stu-id="2e93d-128">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e93d-129">存在する場合、このコンピューター上のすべてのユーザーがパッケージを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2e93d-129">If present, the package will be available for all users on this computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2e93d-130">/LOG</span><span class="sxs-lookup"><span data-stu-id="2e93d-130">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e93d-131">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="2e93d-131">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2e93d-132">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="2e93d-132">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e93d-133">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="2e93d-133">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2e93d-134">/GUI</span><span class="sxs-lookup"><span data-stu-id="2e93d-134">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e93d-135">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e93d-135">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="2e93d-136">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="2e93d-136">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2e93d-137">/Logu</span><span class="sxs-lookup"><span data-stu-id="2e93d-137">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="2e93d-138">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="2e93d-138">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="2e93d-139">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2e93d-139">Related topics</span></span>


[<span data-ttu-id="2e93d-140">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="2e93d-140">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





