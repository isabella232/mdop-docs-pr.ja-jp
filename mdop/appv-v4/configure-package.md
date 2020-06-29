---
title: CONFIGURE PACKAGE
description: CONFIGURE PACKAGE
author: dansimp
ms.assetid: acc7eaa8-6ada-47b9-a655-2ca2537605b9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dc8b315b68349cc9834316786b0bf15d4ac3c5cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819347"
---
# <span data-ttu-id="dcf20-103">CONFIGURE PACKAGE</span><span class="sxs-lookup"><span data-stu-id="dcf20-103">CONFIGURE PACKAGE</span></span>


<span data-ttu-id="dcf20-104">パッケージマニフェストファイル、パッケージソース、ロードトリガーの種類、またはパッケージのターゲットの読み込みをユーザーが変更できるようにします。</span><span class="sxs-lookup"><span data-stu-id="dcf20-104">Enables the user to change a package manifest file, package source, load trigger types, or load target for a package.</span></span>

`SFTMIME CONFIGURE PACKAGE:package-name [/MANIFEST manifest-path]                 [/OVERRIDEURL url] [/AUTOLOADNEVER] [/AUTOLOADONREFRESH]                 [/AUTOLOADONLOGIN] [/AUTOLOADONLAUNCH]                 [/AUTOLOADTARGET {NONE|ALL|PREVUSED}]                 [/LOG log-pathname | /CONSOLE | /GUI]                 [/NO-UPDATE-FTA-SHORTCUT {TRUE|FALSE} {/GLOBAL}]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dcf20-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dcf20-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="dcf20-106">説明</span><span class="sxs-lookup"><span data-stu-id="dcf20-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dcf20-107">パッケージ: &lt; パッケージ名&gt;</span><span class="sxs-lookup"><span data-stu-id="dcf20-107">PACKAGE:&lt;package-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf20-108">ユーザーが表示できるパッケージのわかりやすい名前。</span><span class="sxs-lookup"><span data-stu-id="dcf20-108">User-visible and user-friendly name for the package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dcf20-109">/マニフェスト &lt; マニフェストパス&gt;</span><span class="sxs-lookup"><span data-stu-id="dcf20-109">/MANIFEST &lt;manifest-path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf20-110">パッケージに含まれているアプリケーションとそのすべての発行情報を一覧表示するマニフェストファイルのパスまたは URL。</span><span class="sxs-lookup"><span data-stu-id="dcf20-110">The path or URL of the manifest file that lists the applications included in the package and all of their publishing information.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dcf20-111">/OVERRIDEURL &lt; URL&gt;</span><span class="sxs-lookup"><span data-stu-id="dcf20-111">/OVERRIDEURL &lt;URL&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf20-112">パッケージの SFT ファイルの場所。</span><span class="sxs-lookup"><span data-stu-id="dcf20-112">The location of the package's SFT file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dcf20-113">/Autoloadnever</span><span class="sxs-lookup"><span data-stu-id="dcf20-113">/AUTOLOADNEVER</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf20-114">パッケージのバックグラウンド読み込みが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="dcf20-114">Background loading is turned off for the package.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dcf20-115">/Autoloadonrefresh</span><span class="sxs-lookup"><span data-stu-id="dcf20-115">/AUTOLOADONREFRESH</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf20-116">バックグラウンド読み込みは、発行の更新後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="dcf20-116">Background loading is performed after a publishing refresh.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dcf20-117">/Autoloadonlogin</span><span class="sxs-lookup"><span data-stu-id="dcf20-117">/AUTOLOADONLOGIN</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf20-118">バックグラウンド読み込みは、ユーザーがログインしたときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="dcf20-118">Background loading is performed when a user logs in.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dcf20-119">/Autoloadonlaunch</span><span class="sxs-lookup"><span data-stu-id="dcf20-119">/AUTOLOADONLAUNCH</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf20-120">バックグラウンド読み込みは、ユーザーがパッケージからアプリケーションを開始した後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="dcf20-120">Background loading is performed after a user starts an application from the package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dcf20-121">/Autoloadターゲット &lt; ターゲット&gt;</span><span class="sxs-lookup"><span data-stu-id="dcf20-121">/AUTOLOADTARGET &lt;target&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf20-122">パッケージから自動読み込みされるアプリケーションを示します。</span><span class="sxs-lookup"><span data-stu-id="dcf20-122">Indicates which applications from the package will be autoloaded.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dcf20-123">-</span><span class="sxs-lookup"><span data-stu-id="dcf20-123">NONE</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf20-124">Autoloadonxxx フラグの有無にかかわらず、自動読み込みは実行されません。</span><span class="sxs-lookup"><span data-stu-id="dcf20-124">No autoloading will be performed despite the presence of any /AUTOLOADONxxx flags.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dcf20-125">[ALL] (すべて)</span><span class="sxs-lookup"><span data-stu-id="dcf20-125">ALL</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf20-126">自動ロードトリガーが有効になっている場合、パッケージ内のすべてのアプリケーションは、起動されたかどうかに関係なく、キャッシュに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="dcf20-126">If an autoload trigger is enabled, all applications in the package will be loaded into cache regardless of whether they have ever been launched.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dcf20-127">PREVUSED</span><span class="sxs-lookup"><span data-stu-id="dcf20-127">PREVUSED</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf20-128">自動ロードトリガーが有効になっている場合、このパッケージ内のアプリケーションがユーザーによって以前に起動された場合、パッケージは読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="dcf20-128">If an autoload trigger is enabled, the package will load if any applications in this package have previously been started by a user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dcf20-129">/LOG</span><span class="sxs-lookup"><span data-stu-id="dcf20-129">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf20-130">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="dcf20-130">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dcf20-131">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="dcf20-131">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf20-132">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="dcf20-132">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dcf20-133">/GUI</span><span class="sxs-lookup"><span data-stu-id="dcf20-133">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf20-134">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dcf20-134">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="dcf20-135">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="dcf20-135">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dcf20-136">/Logu</span><span class="sxs-lookup"><span data-stu-id="dcf20-136">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf20-137">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="dcf20-137">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="dcf20-138">バージョン 4.6 SP2 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="dcf20-138">For version4.6 SP2, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dcf20-139">[/NO-UPDATE-FTA-SHORTCUT {TRUE |FALSE} {/GLOBAL}]</span><span class="sxs-lookup"><span data-stu-id="dcf20-139">[/NO-UPDATE-FTA-SHORTCUT {TRUE|FALSE} {/GLOBAL}]</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf20-140">TRUE に設定すると、ユーザーごと、または/グローバルフラグが指定されている場合はグローバルに、パッケージのレジストリ値が作成されます。</span><span class="sxs-lookup"><span data-stu-id="dcf20-140">If set to TRUE, a registry value is created for the package, either per user, or globally if the /GLOBAL flag is specified.</span></span></p>
<p><span data-ttu-id="dcf20-141">FALSE に設定すると、レジストリ値が削除され、パッケージのファイルの種類の関連付け (FTA) が再インストールされます。</span><span class="sxs-lookup"><span data-stu-id="dcf20-141">If set to FALSE, the registry value is removed and the file type associations (FTA) for the package are reinstalled.</span></span></p>
<p><span data-ttu-id="dcf20-142">指定しない場合、標準の FTA とショートカットの発行動作が行われます。</span><span class="sxs-lookup"><span data-stu-id="dcf20-142">If not specified, normal FTA and shortcut publishing behavior occurs.</span></span> <span data-ttu-id="dcf20-143">App-v 4.6 SP2 クライアントでその後の公開更新操作を実行した場合は、このレジストリ値が設定されているパッケージのショートカットと FTAs は変更されません。また、フラグをリセットしない限り、ショートカットと FTAs はシステムのスタートアップまたはユーザーログインで登録されません。</span><span class="sxs-lookup"><span data-stu-id="dcf20-143">If you perform any subsequent publishing refresh operations on the App-V 4.6 SP2 client, the shortcuts and FTAs for packages that have this registry value set will not be changed, and the shortcuts and FTAs will not be registered at system startup or user login unless you reset the flag.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dcf20-144">/グローバル</span><span class="sxs-lookup"><span data-stu-id="dcf20-144">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="dcf20-145">/NO-UPDATE-FTA-SHORTCUT フラグと連携して動作します。</span><span class="sxs-lookup"><span data-stu-id="dcf20-145">Works in conjunction with the /NO-UPDATE-FTA-SHORTCUT flag.</span></span> <span data-ttu-id="dcf20-146">/グローバルフラグが存在する場合は、そのパッケージのレジストリ値がすべてのユーザーに対して作成されることを示します。</span><span class="sxs-lookup"><span data-stu-id="dcf20-146">If the /GLOBAL flag is present, it indicates that a registry value will be created for that package for all users.</span></span> <span data-ttu-id="dcf20-147">既定では、このユーザーに対してのみレジストリ値が作成されます。</span><span class="sxs-lookup"><span data-stu-id="dcf20-147">By default, the registry value is created only for this user.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="dcf20-148">関連トピック</span><span class="sxs-lookup"><span data-stu-id="dcf20-148">Related topics</span></span>


[<span data-ttu-id="dcf20-149">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="dcf20-149">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





