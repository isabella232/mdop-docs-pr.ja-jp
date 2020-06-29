---
title: CONFIGURE TYPE
description: CONFIGURE TYPE
author: dansimp
ms.assetid: 2caf9433-5449-486f-ab94-83ee8e44d7f1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9b70cdd1b27eba0109183f1eb9cfb42f08b3f341
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821937"
---
# <span data-ttu-id="0dc6e-103">CONFIGURE TYPE</span><span class="sxs-lookup"><span data-stu-id="0dc6e-103">CONFIGURE TYPE</span></span>


<span data-ttu-id="0dc6e-104">ユーザーがファイルの種類の関連付けの設定を変更できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0dc6e-104">Enables the user to change settings for a file type association.</span></span>

`SFTMIME CONFIGURE TYPE:file-extension [/GLOBAL] [/APP application]                 [/ICON icon-pathname] [/DESCRIPTION type-desc]                 [/CONTENT-TYPE content-type] [/PERCEIVED-TYPE perceived-type]                 [/PROGID progid] [/CONFIRMOPEN {YES|NO}]                 [/SHOWEXT {YES|NO}] [/NEWMENU {YES|NO}]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0dc6e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0dc6e-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="0dc6e-106">説明</span><span class="sxs-lookup"><span data-stu-id="0dc6e-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0dc6e-107">種類: &lt; ファイル拡張子&gt;</span><span class="sxs-lookup"><span data-stu-id="0dc6e-107">TYPE:&lt;file-extension&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="0dc6e-108">構成するファイル名の拡張子。</span><span class="sxs-lookup"><span data-stu-id="0dc6e-108">The file name extension to be configured.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0dc6e-109">/APP &lt; application&gt;</span><span class="sxs-lookup"><span data-stu-id="0dc6e-109">/APP &lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="0dc6e-110">このファイルの種類を関連付けるアプリケーションの名前とバージョン (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="0dc6e-110">The name and version (optional) of the application to associate this file type with.</span></span> <span data-ttu-id="0dc6e-111">PROGID で指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="0dc6e-111">Cannot be specified with PROGID.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0dc6e-112">/アイコン &lt; のアイコン-パス名&gt;</span><span class="sxs-lookup"><span data-stu-id="0dc6e-112">/ICON &lt;icon-pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="0dc6e-113">アイコンファイルのパスまたは URL。</span><span class="sxs-lookup"><span data-stu-id="0dc6e-113">The path or URL for the icon file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0dc6e-114">/DESCRIPTION &lt; type-desc&gt;</span><span class="sxs-lookup"><span data-stu-id="0dc6e-114">/DESCRIPTION &lt;type-desc&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="0dc6e-115">ファイルの種類のわかりやすい名前です。</span><span class="sxs-lookup"><span data-stu-id="0dc6e-115">The user-friendly name for the file type.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0dc6e-116">コンテンツタイプを入力してください &lt;&gt;</span><span class="sxs-lookup"><span data-stu-id="0dc6e-116">/CONTENT-TYPE &lt;content-type&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="0dc6e-117">ファイルのコンテンツタイプ。</span><span class="sxs-lookup"><span data-stu-id="0dc6e-117">The content type of the file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0dc6e-118">/グローバル</span><span class="sxs-lookup"><span data-stu-id="0dc6e-118">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="0dc6e-119">存在する場合、ユーザー固有のものではなく、すべてのユーザーに適用される関連付けを編集する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="0dc6e-119">If present, indicates that the association that applies to all users should be edited, not the user-specific one.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0dc6e-120">/PERCEIVED-TYPE &lt; の知覚型&gt;</span><span class="sxs-lookup"><span data-stu-id="0dc6e-120">/PERCEIVED-TYPE &lt;perceived-type&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="0dc6e-121">認識されているファイルの種類。</span><span class="sxs-lookup"><span data-stu-id="0dc6e-121">The perceived type of the file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0dc6e-122">/Progid &lt; progid&gt;</span><span class="sxs-lookup"><span data-stu-id="0dc6e-122">/PROGID &lt;progid&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="0dc6e-123">拡張子が別のファイルの種類に関連付けられていることを示します。</span><span class="sxs-lookup"><span data-stu-id="0dc6e-123">Indicates that the extension should be associated with a different file type.</span></span> <span data-ttu-id="0dc6e-124">以前のファイルの種類は削除されません。</span><span class="sxs-lookup"><span data-stu-id="0dc6e-124">The previous file type is not deleted.</span></span> <span data-ttu-id="0dc6e-125">アプリ、アイコン、説明、CONFIRMOPEN、または SHOWEXT と共に指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="0dc6e-125">Cannot be specified with APP, ICON, DESCRIPTION, CONFIRMOPEN, or SHOWEXT.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0dc6e-126">/CONFIRMOPEN</span><span class="sxs-lookup"><span data-stu-id="0dc6e-126">/CONFIRMOPEN</span></span></p></td>
<td align="left"><p><span data-ttu-id="0dc6e-127">この種類のファイルをダウンロードするユーザーに対して、ファイルを開くか保存するかをたずねるメッセージを表示するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0dc6e-127">Indicates whether users downloading a file of this type should be asked whether to open or save the file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0dc6e-128">/SHOWEXT</span><span class="sxs-lookup"><span data-stu-id="0dc6e-128">/SHOWEXT</span></span></p></td>
<td align="left"><p><span data-ttu-id="0dc6e-129">ユーザーがすべての拡張機能を非表示にすることを要求している場合でも、ファイルの拡張子を常に表示する必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0dc6e-129">Indicates whether the file's extension should always be shown, even if the user has requested that all extensions be hidden.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0dc6e-130">/新規メニュー</span><span class="sxs-lookup"><span data-stu-id="0dc6e-130">/NEWMENU</span></span></p></td>
<td align="left"><p><span data-ttu-id="0dc6e-131">シェルの <strong> [新規] メニューにエントリを追加する必要があるかどうかを示し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="0dc6e-131">Indicates whether an entry should be added to the shell's <strong>New</strong> menu.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0dc6e-132">/LOG</span><span class="sxs-lookup"><span data-stu-id="0dc6e-132">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="0dc6e-133">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="0dc6e-133">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0dc6e-134">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="0dc6e-134">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="0dc6e-135">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="0dc6e-135">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0dc6e-136">/GUI</span><span class="sxs-lookup"><span data-stu-id="0dc6e-136">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="0dc6e-137">指定すると、Windows のダイアログボックスに出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0dc6e-137">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="0dc6e-138">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="0dc6e-138">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0dc6e-139">/Logu</span><span class="sxs-lookup"><span data-stu-id="0dc6e-139">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="0dc6e-140">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="0dc6e-140">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="0dc6e-141">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0dc6e-141">Related topics</span></span>


[<span data-ttu-id="0dc6e-142">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="0dc6e-142">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





