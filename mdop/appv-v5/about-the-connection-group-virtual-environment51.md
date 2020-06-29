---
title: 接続グループの仮想環境について
description: 接続グループの仮想環境について
author: dansimp
ms.assetid: b7bb0e3d-8cd5-45a9-b84e-c9ab4196a18c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 43f30c2100fc982170f15c305b03cd338b5d8afd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814883"
---
# <span data-ttu-id="eac9c-103">接続グループの仮想環境について</span><span class="sxs-lookup"><span data-stu-id="eac9c-103">About the Connection Group Virtual Environment</span></span>


**<span data-ttu-id="eac9c-104">このトピックの内容は以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="eac9c-104">In this topic:</span></span>**

-   [<span data-ttu-id="eac9c-105">パッケージの優先順位を決定する方法</span><span class="sxs-lookup"><span data-stu-id="eac9c-105">How package priority is determined</span></span>](#bkmk-pkg-priority-deter)

-   [<span data-ttu-id="eac9c-106">同一のパッケージパスを接続グループ内の1つの仮想ディレクトリにマージする</span><span class="sxs-lookup"><span data-stu-id="eac9c-106">Merging identical package paths into one virtual directory in connection groups</span></span>](#bkmk-merged-root-ve-exp)

## <a href="" id="bkmk-pkg-priority-deter"></a><span data-ttu-id="eac9c-107">パッケージの優先順位を決定する方法</span><span class="sxs-lookup"><span data-stu-id="eac9c-107">How package priority is determined</span></span>


<span data-ttu-id="eac9c-108">仮想環境とその現在の状態は、個々のパッケージではなく、接続グループと関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="eac9c-108">The virtual environment and its current state are associated with the connection group, not with the individual packages.</span></span> <span data-ttu-id="eac9c-109">App-v パッケージが接続グループから削除された場合、接続グループの一部として存在していた状態は、パッケージと共に移行されません。</span><span class="sxs-lookup"><span data-stu-id="eac9c-109">If an App-V package is removed from the connection group, the state that existed as part of the connection group will not migrate with the package.</span></span>

<span data-ttu-id="eac9c-110">同じパッケージが2つの異なる接続グループに含まれている場合は、どの接続グループのアプリを使うかを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eac9c-110">If the same package is a part of two different connection groups, you have to indicate which connection group App-V should use.</span></span> <span data-ttu-id="eac9c-111">たとえば、1つの接続グループに2つのパッケージがあり、それぞれが同じレジストリ DWORD 値を定義していることがあります。</span><span class="sxs-lookup"><span data-stu-id="eac9c-111">For example, you might have two packages in a connection group that each define the same registry DWORD value.</span></span>

<span data-ttu-id="eac9c-112">使用される接続グループは、 **Appconnectiongroup** XML ドキュメント内でパッケージが表示される順序に基づいています。</span><span class="sxs-lookup"><span data-stu-id="eac9c-112">The connection group that is used is based on the order in which a package appears inside the **AppConnectionGroup** XML document:</span></span>

-   <span data-ttu-id="eac9c-113">最初のパッケージの優先順位が最も高くなります。</span><span class="sxs-lookup"><span data-stu-id="eac9c-113">The first package has the highest precedence.</span></span>

-   <span data-ttu-id="eac9c-114">2番目のパッケージでは、2番目の優先順位が最も高くなります。</span><span class="sxs-lookup"><span data-stu-id="eac9c-114">The second package has the second highest precedence.</span></span>

<span data-ttu-id="eac9c-115">次の例のセクションを検討してください。</span><span class="sxs-lookup"><span data-stu-id="eac9c-115">Consider the following example section:</span></span>

```xml
<appv:Packages><appv:PackagePackageId="A8731008-4523-4713-83A4-CD1363907160"VersionId="E889951B-7F30-418B-A69C-B37283BC0DB9"/><appv:PackagePackageId="1DC709C8-309F-4AB4-BD47-F75926D04276"VersionId="01F1943B-C778-40AD-BFAD-AC34A695DF3C"/><appv:PackagePackageId="04220DCA-EE77-42BE-A9F5-96FD8E8593F2"VersionId="E15EFFE9-043D-4C01-BC52-AD2BD1E8BAFA"/></appv:Packages>
```

<span data-ttu-id="eac9c-116">次に示すように、最初のパッケージと3番目のパッケージで同じ DWORD 値 ABC (HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region) が定義されているものとします。</span><span class="sxs-lookup"><span data-stu-id="eac9c-116">Assume that same DWORD value ABC (HKEY\_LOCAL\_MACHINE\\software\\contoso\\finapp\\region) is defined in the first and third package, such as:</span></span>

-   <span data-ttu-id="eac9c-117">パッケージ 1 (A8731008-4523-4713-83A4-CD1363907160): HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region = 5</span><span class="sxs-lookup"><span data-stu-id="eac9c-117">Package 1 (A8731008-4523-4713-83A4-CD1363907160): HKEY\_LOCAL\_MACHINE\\software\\contoso\\finapp\\region=5</span></span>

-   <span data-ttu-id="eac9c-118">パッケージ 3 (04220DCA-EE77-42BE-A9F5-96FD8E8593F2): HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region = 10</span><span class="sxs-lookup"><span data-stu-id="eac9c-118">Package 3 (04220DCA-EE77-42BE-A9F5-96FD8E8593F2): HKEY\_LOCAL\_MACHINE\\software\\contoso\\finapp\\region=10</span></span>

<span data-ttu-id="eac9c-119">パッケージ1が最初に表示されるため、AppConnectionGroup の仮想環境には、1つの DWORD 値 5 (HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region = 5) があります。</span><span class="sxs-lookup"><span data-stu-id="eac9c-119">Since Package 1 appears first, the AppConnectionGroup's virtual environment will have the single DWORD value of 5 (HKEY\_LOCAL\_MACHINE\\software\\contoso\\finapp\\region=5).</span></span> <span data-ttu-id="eac9c-120">つまり、パッケージ1、パッケージ2、およびパッケージ3の仮想アプリケーションは、HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region. を照会すると、値5をすべて表示することを意味します。</span><span class="sxs-lookup"><span data-stu-id="eac9c-120">This means that the virtual applications in Package 1, Package 2, and Package 3 will all see the value 5 when they query for HKEY\_LOCAL\_MACHINE\\software\\contoso\\finapp\\region.</span></span>

<span data-ttu-id="eac9c-121">その他の仮想環境リソースも同様に解決されますが、通常のケースでは、レジストリで競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="eac9c-121">Other virtual environment resources are resolved similarly, but the usual case is that the collisions occur in the registry.</span></span>

## <a href="" id="bkmk-merged-root-ve-exp"></a><span data-ttu-id="eac9c-122">同一のパッケージパスを接続グループ内の1つの仮想ディレクトリにマージする</span><span class="sxs-lookup"><span data-stu-id="eac9c-122">Merging identical package paths into one virtual directory in connection groups</span></span>


<span data-ttu-id="eac9c-123">接続グループ内の2つ以上のパッケージに同一のディレクトリパスが含まれている場合、そのパスは接続グループの仮想環境内の1つの仮想ディレクトリにマージされます。</span><span class="sxs-lookup"><span data-stu-id="eac9c-123">If two or more packages in a connection group contain identical directory paths, the paths are merged into a single virtual directory inside the connection group virtual environment.</span></span> <span data-ttu-id="eac9c-124">このパスの結合によって、1つのパッケージに含まれるアプリケーションが、別のパッケージに含まれているファイルにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="eac9c-124">This merging of paths allows an application in one package to access files that are in a different package.</span></span>

<span data-ttu-id="eac9c-125">接続グループからパッケージを削除すると、そのパッケージに含まれているアプリケーションは、接続グループ内の残りのパッケージ内のファイルにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="eac9c-125">When you remove a package from a connection group, the applications in that removed package are no longer able to access files in the remaining packages in the connection group.</span></span>

<span data-ttu-id="eac9c-126">App-v が接続グループ内のファイルの名前を検索する順序は、接続グループのマニフェストファイルに指定されている順序で指定されています。</span><span class="sxs-lookup"><span data-stu-id="eac9c-126">The order in which App-V looks up a file’s name in the connection group is specified by the order in which the App-V packages are listed in the connection group manifest file.</span></span>

<span data-ttu-id="eac9c-127">次の例は、**パッケージ a**と**パッケージ B**の接続グループでのファイル名参照の順序と関係を示しています。</span><span class="sxs-lookup"><span data-stu-id="eac9c-127">The following example shows the order and relationship of a file name lookup in a connection group for **Package A** and **Package B**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="eac9c-128">パッケージ A</span><span class="sxs-lookup"><span data-stu-id="eac9c-128">Package A</span></span></th>
<th align="left"><span data-ttu-id="eac9c-129">パッケージ B</span><span class="sxs-lookup"><span data-stu-id="eac9c-129">Package B</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="eac9c-130">C:\Windows\System32</span><span class="sxs-lookup"><span data-stu-id="eac9c-130">C:\Windows\System32</span></span></p></td>
<td align="left"><p><span data-ttu-id="eac9c-131">C:\Windows\System32</span><span class="sxs-lookup"><span data-stu-id="eac9c-131">C:\Windows\System32</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="eac9c-132">C:\ apptest</span><span class="sxs-lookup"><span data-stu-id="eac9c-132">C:\AppTest</span></span></p></td>
<td align="left"><p><span data-ttu-id="eac9c-133">C:\ apptest</span><span class="sxs-lookup"><span data-stu-id="eac9c-133">C:\AppTest</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="eac9c-134">上の例では、仮想化されたアプリケーションが特定のファイルを検索しようとすると、一致するファイルパスに対してパッケージ A が最初に検索されます。</span><span class="sxs-lookup"><span data-stu-id="eac9c-134">In the example above, when a virtualized application tries to find a specific file, Package A is searched first for a matching file path.</span></span> <span data-ttu-id="eac9c-135">一致するパスが見つからない場合は、次のマッピングルールを使用して、パッケージ B が検索されます。</span><span class="sxs-lookup"><span data-stu-id="eac9c-135">If a matching path is not found, Package B is searched, using the following mapping rules:</span></span>

-   <span data-ttu-id="eac9c-136">両方のアプリケーションパッケージの同じ仮想フォルダー階層内に**test.txt**という名前のファイルが存在する場合は、最初に一致したファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="eac9c-136">If a file named **test.txt** exists in the same virtual folder hierarchy in both application packages, the first matching file is used.</span></span>

-   <span data-ttu-id="eac9c-137">1つのアプリケーションパッケージの仮想フォルダー階層内に**bar.txt**という名前のファイルが存在する場合は、最初に一致するファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="eac9c-137">If a file named **bar.txt** exists in the virtual folder hierarchy of one application package, but not in the other, the first matching file is used.</span></span>






## <span data-ttu-id="eac9c-138">関連トピック</span><span class="sxs-lookup"><span data-stu-id="eac9c-138">Related topics</span></span>


[<span data-ttu-id="eac9c-139">接続グループの管理</span><span class="sxs-lookup"><span data-stu-id="eac9c-139">Managing Connection Groups</span></span>](managing-connection-groups51.md)

 

 





