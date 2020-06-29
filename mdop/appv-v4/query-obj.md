---
title: QUERY OBJ
description: QUERY OBJ
author: dansimp
ms.assetid: 55abf0d1-c779-4172-8357-552ab010933b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 328e9feb96c70080531cbbc666d8ff1b86045ba5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815737"
---
# <span data-ttu-id="26c54-103">QUERY OBJ</span><span class="sxs-lookup"><span data-stu-id="26c54-103">QUERY OBJ</span></span>


<span data-ttu-id="26c54-104">現在のアプリケーション、パッケージ、ファイルの種類の関連付け、または公開サーバーのタブ区切りのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="26c54-104">Returns a tab-delimited list of current applications, packages, file type associations, or publishing servers.</span></span>

`SFTMIME QUERY OBJ:{APP|PACKAGE|TYPE|SERVER} [/SHORT] [/GLOBAL]                 [/LOG log-pathname | /CONSOLE ]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="26c54-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="26c54-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="26c54-106">説明</span><span class="sxs-lookup"><span data-stu-id="26c54-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="26c54-107">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="26c54-107">APP</span></span></p></td>
<td align="left"><p><span data-ttu-id="26c54-108">アプリケーションのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="26c54-108">Returns a list of applications.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="26c54-109">プレゼンテーション</span><span class="sxs-lookup"><span data-stu-id="26c54-109">PACKAGE</span></span></p></td>
<td align="left"><p><span data-ttu-id="26c54-110">パッケージの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="26c54-110">Returns a list of packages.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="26c54-111">TYPE</span><span class="sxs-lookup"><span data-stu-id="26c54-111">TYPE</span></span></p></td>
<td align="left"><p><span data-ttu-id="26c54-112">ファイルの種類の関連付けのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="26c54-112">Returns a list of file type associations.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="26c54-113">SERVER</span><span class="sxs-lookup"><span data-stu-id="26c54-113">SERVER</span></span></p></td>
<td align="left"><p><span data-ttu-id="26c54-114">発行サーバーのリストを返します。</span><span class="sxs-lookup"><span data-stu-id="26c54-114">Returns a list of publishing servers.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="26c54-115">/短い</span><span class="sxs-lookup"><span data-stu-id="26c54-115">/SHORT</span></span></p></td>
<td align="left"><p><span data-ttu-id="26c54-116">各プロパティの完全なプロパティを表示せずに、アプリケーション名、パッケージ、関連付け、またはサーバー名の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="26c54-116">Without displaying the full properties of each, returns a list of application names, packages, associations, or server names.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="26c54-117">/グローバル</span><span class="sxs-lookup"><span data-stu-id="26c54-117">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="26c54-118">アプリケーションの場合は、現在のユーザーがアクセスできるすべてのアプリケーションではなく、既知のすべてのアプリケーションを返します。</span><span class="sxs-lookup"><span data-stu-id="26c54-118">For applications, returns all known applications instead of only the ones the current user has access to.</span></span> <span data-ttu-id="26c54-119">パッケージの場合、現在のユーザーがアクセス権を持っているものだけでなく、すべての既知のパッケージを返します。</span><span class="sxs-lookup"><span data-stu-id="26c54-119">For packages, returns all known packages instead of only the ones the current user has access to.</span></span> <span data-ttu-id="26c54-120">関連付けの場合は、ユーザー固有の関連付けではなく、すべてのユーザーに適用される関連付けだけが返されます。</span><span class="sxs-lookup"><span data-stu-id="26c54-120">For associations, returns only associations that apply to all users, not user-specific ones.</span></span> <span data-ttu-id="26c54-121">サーバーに対して無効です。</span><span class="sxs-lookup"><span data-stu-id="26c54-121">Not valid for servers.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="26c54-122">/LOG</span><span class="sxs-lookup"><span data-stu-id="26c54-122">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="26c54-123">指定した場合、出力は指定したパス名に記録されます。</span><span class="sxs-lookup"><span data-stu-id="26c54-123">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="26c54-124">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="26c54-124">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="26c54-125">指定すると、出力がアクティブなコンソールウィンドウに表示されます (既定)。</span><span class="sxs-lookup"><span data-stu-id="26c54-125">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="26c54-126">バージョン4.6 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="26c54-126">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="26c54-127">/Logu</span><span class="sxs-lookup"><span data-stu-id="26c54-127">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="26c54-128">指定すると、指定したパス名の UNICODE 形式で出力されます。</span><span class="sxs-lookup"><span data-stu-id="26c54-128">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="26c54-129">**注** バージョン4.6 では、新しい列が SFTMIME クエリ OBJ の出力に追加されました。アプリ \ [/GLOBAL\]。</span><span class="sxs-lookup"><span data-stu-id="26c54-129">**Note** In version 4.6, a new column has been added to the output of SFTMIME QUERY OBJ:APP \[/GLOBAL\].</span></span> <span data-ttu-id="26c54-130">出力の最後の列は、アプリケーションが公開されているかどうかを示す数値です。</span><span class="sxs-lookup"><span data-stu-id="26c54-130">The last column of the output is a numeric value that indicates whether an application is published or not.</span></span>

<span data-ttu-id="26c54-131">発行済み = 1 は、Windows インストーラーファイル (.) を使ってアプリケーションをインストールすることで、発行サーバーの更新によってアプリケーションが公開されたことを意味します。MSI)、または SFTMIME のパッケージ追加を実行するか、パッケージマニフェストを使ってパッケージを構成するか、[パッケージの発行] コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="26c54-131">PUBLISHED=1 means the application was published by a Publishing Server refresh, by installing the application by using a Windows Installer file (.MSI), or by running an SFTMIME ADD PACKAGE, CONFIGURE PACKAGE or PUBLISH PACKAGE command by using a package manifest.</span></span>

<span data-ttu-id="26c54-132">発行済み = 0 は、アプリケーションが公開されていないか、クリア操作を実行しているか、SFTMIME の未発行コマンドを実行しているために、そのアプリケーションが公開されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="26c54-132">PUBLISHED=0 means the application has not been published or it is no longer published as a result of performing a Clear operation or running an SFTMIME UNPUBLISH command.</span></span>

<span data-ttu-id="26c54-133">/グローバルパラメーターを使用する場合、公開された状態は、グローバルに公開されているアプリケーションの場合は1、ユーザーコンテキストで公開されたアプリケーションの場合は0になります。</span><span class="sxs-lookup"><span data-stu-id="26c54-133">If you use the /GLOBAL parameter, the PUBLISHED state will be 1 for applications that were published globally and 0 for those applications that were published under user contexts.</span></span> <span data-ttu-id="26c54-134">/グローバルパラメーターを指定しなければ、コマンドを実行しているユーザーのコンテキストで公開されたアプリケーションに対して、公開された状態1が返されます。グローバルに公開されているアプリケーションに対しては、0の状態が返されます。</span><span class="sxs-lookup"><span data-stu-id="26c54-134">Without the /GLOBAL parameter, a PUBLISHED state of 1 is returned for applications published in the context of the user running the command, and a state of 0 is returned for those applications that are published globally.</span></span>

 

<span data-ttu-id="26c54-135">SFTMIME QUERY OBJ コマンドを使って、上に示したすべてのオブジェクト (アプリケーション、パッケージ、ファイルの種類の関連付け、サーバー) に関する情報を照会できます。</span><span class="sxs-lookup"><span data-stu-id="26c54-135">The SFTMIME QUERY OBJ command can be used to query for information on all of the objects shown above—applications, packages, file type associations, and servers.</span></span><span data-ttu-id="26c54-136">通常の運用タスクで SFTMIME クエリ OBJ コマンドを使用する方法を示すために、次の例は、特定のパッケージの OVERRIDEURL パラメーターの値を設定して、パッケージコンテンツへの新しいパスを指定する場合の手順を示しています。</span><span class="sxs-lookup"><span data-stu-id="26c54-136">To show how you might use the SFTMIME QUERY OBJ command in your normal operations tasks, the following example demonstrates the process you would follow if you wanted to set the OVERRIDEURL parameter value for a specific package to specify a new path to the package content.</span></span> 

1.  <span data-ttu-id="26c54-137">構成するパッケージを見つけるには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="26c54-137">To find the package that you want to configure, run the following command:</span></span>

    `SFTMIME QUERY OBJ:PACKAGE`

    <span data-ttu-id="26c54-138">このコマンドは、検出された各パッケージ名を、出力の最初の列 ({AF78ABE1-57D4-4297-89DE-C308684AEDD6} など) の GUID として返します。</span><span class="sxs-lookup"><span data-stu-id="26c54-138">This command returns each discovered package name as a GUID in the first column of output—for example, {AF78ABE1-57D4-4297-89DE-C308684AEDD6}.</span></span>

2.  <span data-ttu-id="26c54-139">OVERRIDEURL パラメーターの値を設定するには、SFTMIME [CONFIGURE パッケージ](configure-package.md)コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="26c54-139">To set the OVERRIDEURL parameter value, you use the SFTMIME [CONFIGURE PACKAGE](configure-package.md) command.</span></span> <span data-ttu-id="26c54-140">たとえば、このパッケージの OVERRIDEURL 値を、 *\\ ¥ server¥*¥¥の値に設定するには、次のように、SFTMIME CONFIGURE package コマンドを使用して、手順1の SFTMIME クエリ OBJ コマンドの出力から選んだパッケージ GUID を指定します。次のようにします。</span><span class="sxs-lookup"><span data-stu-id="26c54-140">For example, to set the OVERRIDEURL value for this package to a value of *\\\\server\\share\\mypackage.sft*, use the SFTMIME CONFIGURE PACKAGE command and give it the selected package GUID from the output of the SFTMIME QUERY OBJ command in step 1, followed by the OVERRIDEURL parameter and its new value, as follows:</span></span>

    `SFTMIME CONFIGURE PACKAGE:"{AF78ABE1-57D4-4297-89DE-C308684AEDD6}" /OVERRIDEURL "\\\\server\\share\\mypackage.sft "`

<span data-ttu-id="26c54-141">バージョン 4.6 SP2 の場合、次のオプションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="26c54-141">For version4.6 SP2, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="26c54-142">/NO-UPDATE-FTA-SHORTCUT</span><span class="sxs-lookup"><span data-stu-id="26c54-142">/NO-UPDATE-FTA-SHORTCUT</span></span></p></td>
<td align="left"><p><span data-ttu-id="26c54-143">/NO-UPDATE-FTA-SHORTCUT フラグの現在の状態を示します。</span><span class="sxs-lookup"><span data-stu-id="26c54-143">Indicates the current state of the /NO-UPDATE-FTA-SHORTCUT flag.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="26c54-144">関連トピック</span><span class="sxs-lookup"><span data-stu-id="26c54-144">Related topics</span></span>


[<span data-ttu-id="26c54-145">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="26c54-145">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





