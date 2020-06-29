---
title: PUBLISH APP
description: PUBLISH APP
author: dansimp
ms.assetid: f25f06a8-ca23-435b-a0c2-16a5f39b6b97
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b2ccb19255786ee47a8356feef14be1c4d9b4fb2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815817"
---
# <span data-ttu-id="a14b1-103">PUBLISH APP</span><span class="sxs-lookup"><span data-stu-id="a14b1-103">PUBLISH APP</span></span>


<span data-ttu-id="a14b1-104">ユーザーのスタートメニュー、デスクトップ、またはその他の指定した場所にアプリケーションのショートカットを公開します。</span><span class="sxs-lookup"><span data-stu-id="a14b1-104">Publishes an application shortcut to the user's Start menu, desktop, or other specified location.</span></span>

`SFTMIME PUBLISH APP:application                 {/DESKTOP | /START | /TARGET target-path} [/ICON icon-pathname]                 [/DISPLAY display-name] [/ARGS command-args...]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a14b1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a14b1-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="a14b1-106">説明</span><span class="sxs-lookup"><span data-stu-id="a14b1-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a14b1-107">アプリケーション: &lt; アプリケーション&gt;</span><span class="sxs-lookup"><span data-stu-id="a14b1-107">APPLICATION:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="a14b1-108">アプリケーションの名前とバージョン (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="a14b1-108">The name and version (optional) of the application.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a14b1-109">/デスクトップ</span><span class="sxs-lookup"><span data-stu-id="a14b1-109">/DESKTOP</span></span></p></td>
<td align="left"><p><span data-ttu-id="a14b1-110">ユーザーのデスクトップへのショートカットを公開します。</span><span class="sxs-lookup"><span data-stu-id="a14b1-110">Publishes a shortcut to the user's desktop.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a14b1-111">/START</span><span class="sxs-lookup"><span data-stu-id="a14b1-111">/START</span></span></p></td>
<td align="left"><p><span data-ttu-id="a14b1-112">[スタート] メニューの [プログラム] フォルダーにある Application Virtualization Applications フォルダーへのショートカットを公開します。</span><span class="sxs-lookup"><span data-stu-id="a14b1-112">Publishes a shortcut to the Application Virtualization Applications folder in the Programs folder of the Start menu.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a14b1-113">/TARGET &lt; TARGET-path&gt;</span><span class="sxs-lookup"><span data-stu-id="a14b1-113">/TARGET &lt;target-path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="a14b1-114">ショートカットが公開される絶対パス。</span><span class="sxs-lookup"><span data-stu-id="a14b1-114">The absolute path where the shortcut should be published.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a14b1-115">/アイコン &lt; のアイコン-パス名&gt;</span><span class="sxs-lookup"><span data-stu-id="a14b1-115">/ICON &lt;icon-pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="a14b1-116">アイコンファイルのパスまたは URL。</span><span class="sxs-lookup"><span data-stu-id="a14b1-116">The path or URL for the icon file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a14b1-117">/DISPLAY &lt; の表示名&gt;</span><span class="sxs-lookup"><span data-stu-id="a14b1-117">/DISPLAY &lt;display-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="a14b1-118">ショートカットの表示名。</span><span class="sxs-lookup"><span data-stu-id="a14b1-118">The display name for the shortcut.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a14b1-119">/Args &lt; コマンド-引数&gt;</span><span class="sxs-lookup"><span data-stu-id="a14b1-119">/ARGS &lt;command-args&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="a14b1-120">アプリケーションに渡されるパラメーター。</span><span class="sxs-lookup"><span data-stu-id="a14b1-120">Parameters to be passed to the application.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a14b1-121">/LOG</span><span class="sxs-lookup"><span data-stu-id="a14b1-121">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="a14b1-122">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="a14b1-122">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a14b1-123">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="a14b1-123">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="a14b1-124">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="a14b1-124">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a14b1-125">/GUI</span><span class="sxs-lookup"><span data-stu-id="a14b1-125">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="a14b1-126">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a14b1-126">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="a14b1-127">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="a14b1-127">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a14b1-128">/Logu</span><span class="sxs-lookup"><span data-stu-id="a14b1-128">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="a14b1-129">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="a14b1-129">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="a14b1-130">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a14b1-130">Related topics</span></span>


[<span data-ttu-id="a14b1-131">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="a14b1-131">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





