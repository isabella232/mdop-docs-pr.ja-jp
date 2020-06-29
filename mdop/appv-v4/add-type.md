---
title: ADD TYPE
description: ADD TYPE
author: dansimp
ms.assetid: 8f1d3978-9977-4851-9f46-fee6aefa3535
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4d2dcfb24a32dc733aa91b5534e0011090ef12b9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822384"
---
# <span data-ttu-id="dd182-103">ADD TYPE</span><span class="sxs-lookup"><span data-stu-id="dd182-103">ADD TYPE</span></span>


<span data-ttu-id="dd182-104">指定したファイルの種類の関連付けを追加します。</span><span class="sxs-lookup"><span data-stu-id="dd182-104">Adds the specified file type association.</span></span>

`SFTMIME ADD TYPE:file-extension /APP application [/ICON icon-pathname]                 [/DESCRIPTION type-desc] [/CONTENT-TYPE content-type] [/GLOBAL]                 [/PERCEIVED-TYPE perceived-type] [/PROGID progid]                 [/CONFIRMOPEN {YES|NO}] [/SHOWEXT {YES|NO}]                 [/NEWMENU {YES|NO}]  [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="dd182-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dd182-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="dd182-106">説明</span><span class="sxs-lookup"><span data-stu-id="dd182-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd182-107">種類: &lt; ファイル拡張子&gt;</span><span class="sxs-lookup"><span data-stu-id="dd182-107">TYPE:&lt;file-extension&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd182-108">指定されたアプリケーションに関連付けられるファイル名拡張子。</span><span class="sxs-lookup"><span data-stu-id="dd182-108">The file name extension that will be associated with the application specified.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd182-109">/APP &lt; application&gt;</span><span class="sxs-lookup"><span data-stu-id="dd182-109">/APP &lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd182-110">アプリケーションの名前とバージョン (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="dd182-110">The name and version (optional) of the application.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd182-111">/アイコン &lt; のアイコン-パス名&gt;</span><span class="sxs-lookup"><span data-stu-id="dd182-111">/ICON &lt;icon-pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd182-112">アイコンファイルのパスまたは URL。</span><span class="sxs-lookup"><span data-stu-id="dd182-112">The path or URL for the icon file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd182-113">/DESCRIPTION &lt; type-desc&gt;</span><span class="sxs-lookup"><span data-stu-id="dd182-113">/DESCRIPTION &lt;type-desc&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd182-114">ファイルの種類のわかりやすい名前です。</span><span class="sxs-lookup"><span data-stu-id="dd182-114">The user-friendly name for the file type.</span></span> <span data-ttu-id="dd182-115">既定値は &quot; EXTENSION ファイルです。&quot;</span><span class="sxs-lookup"><span data-stu-id="dd182-115">Defaults to &quot;EXTENSION File.&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd182-116">コンテンツタイプを入力してください &lt;&gt;</span><span class="sxs-lookup"><span data-stu-id="dd182-116">/CONTENT-TYPE &lt;content-type&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd182-117">ファイルのコンテンツタイプ。</span><span class="sxs-lookup"><span data-stu-id="dd182-117">The content type of the file.</span></span> <span data-ttu-id="dd182-118">既定値は &quot; application/softricity です。&quot;</span><span class="sxs-lookup"><span data-stu-id="dd182-118">Defaults to &quot;application/softricity-extension.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd182-119">/グローバル</span><span class="sxs-lookup"><span data-stu-id="dd182-119">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd182-120">存在する場合、このコンピューター上のすべてのユーザーがパッケージを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="dd182-120">If present, the package will be available for all users on this computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd182-121">/PERCEIVED-TYPE &lt; の知覚型&gt;</span><span class="sxs-lookup"><span data-stu-id="dd182-121">/PERCEIVED-TYPE &lt;perceived-type&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd182-122">認識されているファイルの種類。</span><span class="sxs-lookup"><span data-stu-id="dd182-122">The perceived type of the file.</span></span> <span data-ttu-id="dd182-123">既定値は何もありません。</span><span class="sxs-lookup"><span data-stu-id="dd182-123">Defaults to nothing.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd182-124">/Progid &lt; progid&gt;</span><span class="sxs-lookup"><span data-stu-id="dd182-124">/PROGID &lt;progid&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd182-125">ファイルの種類のプログラム識別子。</span><span class="sxs-lookup"><span data-stu-id="dd182-125">The programmatic identifier for the file type.</span></span> <span data-ttu-id="dd182-126">既定では、Virt に設定します。</span><span class="sxs-lookup"><span data-stu-id="dd182-126">Defaults to App Virt.extension.File.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd182-127">/CONFIRMOPEN</span><span class="sxs-lookup"><span data-stu-id="dd182-127">/CONFIRMOPEN</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd182-128">この種類のファイルをダウンロードするユーザーに対して、ファイルを開くか保存するかをたずねるメッセージを表示するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="dd182-128">Indicates whether users downloading a file of this type should be asked whether to open or save the file.</span></span> <span data-ttu-id="dd182-129">既定値は [はい] です。</span><span class="sxs-lookup"><span data-stu-id="dd182-129">Defaults to YES.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd182-130">/SHOWEXT</span><span class="sxs-lookup"><span data-stu-id="dd182-130">/SHOWEXT</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd182-131">ユーザーがすべての拡張機能を非表示にすることを要求している場合でも、ファイルの拡張子を常に表示する必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="dd182-131">Indicates whether the file's extension should always be shown, even if the user has requested that all extensions be hidden.</span></span> <span data-ttu-id="dd182-132">既定値は NO です。</span><span class="sxs-lookup"><span data-stu-id="dd182-132">Defaults to NO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd182-133">/新規メニュー</span><span class="sxs-lookup"><span data-stu-id="dd182-133">/NEWMENU</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd182-134">シェルの <strong> [新規] メニューにエントリを追加する必要があるかどうかを示し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="dd182-134">Indicates whether an entry should be added to the shell's <strong>New</strong> menu.</span></span> <span data-ttu-id="dd182-135">既定値は NO です。</span><span class="sxs-lookup"><span data-stu-id="dd182-135">Defaults to NO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd182-136">/LOG</span><span class="sxs-lookup"><span data-stu-id="dd182-136">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd182-137">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="dd182-137">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd182-138">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="dd182-138">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd182-139">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="dd182-139">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="dd182-140">/GUI</span><span class="sxs-lookup"><span data-stu-id="dd182-140">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd182-141">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd182-141">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="dd182-142">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="dd182-142">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="dd182-143">/Logu</span><span class="sxs-lookup"><span data-stu-id="dd182-143">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="dd182-144">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="dd182-144">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="dd182-145">関連トピック</span><span class="sxs-lookup"><span data-stu-id="dd182-145">Related topics</span></span>


[<span data-ttu-id="dd182-146">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="dd182-146">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





