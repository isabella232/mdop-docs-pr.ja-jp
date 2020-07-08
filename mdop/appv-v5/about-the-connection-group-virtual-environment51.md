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
# 接続グループの仮想環境について


**このトピックの内容は以下のとおりです。**

-   [パッケージの優先順位を決定する方法](#bkmk-pkg-priority-deter)

-   [同一のパッケージパスを接続グループ内の1つの仮想ディレクトリにマージする](#bkmk-merged-root-ve-exp)

## <a href="" id="bkmk-pkg-priority-deter"></a>パッケージの優先順位を決定する方法


仮想環境とその現在の状態は、個々のパッケージではなく、接続グループと関連付けられます。 App-v パッケージが接続グループから削除された場合、接続グループの一部として存在していた状態は、パッケージと共に移行されません。

同じパッケージが2つの異なる接続グループに含まれている場合は、どの接続グループのアプリを使うかを指定する必要があります。 たとえば、1つの接続グループに2つのパッケージがあり、それぞれが同じレジストリ DWORD 値を定義していることがあります。

使用される接続グループは、 **Appconnectiongroup** XML ドキュメント内でパッケージが表示される順序に基づいています。

-   最初のパッケージの優先順位が最も高くなります。

-   2番目のパッケージでは、2番目の優先順位が最も高くなります。

次の例のセクションを検討してください。

```xml
<appv:Packages><appv:PackagePackageId="A8731008-4523-4713-83A4-CD1363907160"VersionId="E889951B-7F30-418B-A69C-B37283BC0DB9"/><appv:PackagePackageId="1DC709C8-309F-4AB4-BD47-F75926D04276"VersionId="01F1943B-C778-40AD-BFAD-AC34A695DF3C"/><appv:PackagePackageId="04220DCA-EE77-42BE-A9F5-96FD8E8593F2"VersionId="E15EFFE9-043D-4C01-BC52-AD2BD1E8BAFA"/></appv:Packages>
```

次に示すように、最初のパッケージと3番目のパッケージで同じ DWORD 値 ABC (HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region) が定義されているものとします。

-   パッケージ 1 (A8731008-4523-4713-83A4-CD1363907160): HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region = 5

-   パッケージ 3 (04220DCA-EE77-42BE-A9F5-96FD8E8593F2): HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region = 10

パッケージ1が最初に表示されるため、AppConnectionGroup の仮想環境には、1つの DWORD 値 5 (HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region = 5) があります。 つまり、パッケージ1、パッケージ2、およびパッケージ3の仮想アプリケーションは、HKEY \ _LOCAL \ _MACHINE \\software\\contoso\\finapp\\region. を照会すると、値5をすべて表示することを意味します。

その他の仮想環境リソースも同様に解決されますが、通常のケースでは、レジストリで競合が発生します。

## <a href="" id="bkmk-merged-root-ve-exp"></a>同一のパッケージパスを接続グループ内の1つの仮想ディレクトリにマージする


接続グループ内の2つ以上のパッケージに同一のディレクトリパスが含まれている場合、そのパスは接続グループの仮想環境内の1つの仮想ディレクトリにマージされます。 このパスの結合によって、1つのパッケージに含まれるアプリケーションが、別のパッケージに含まれているファイルにアクセスすることができます。

接続グループからパッケージを削除すると、そのパッケージに含まれているアプリケーションは、接続グループ内の残りのパッケージ内のファイルにアクセスできなくなります。

App-v が接続グループ内のファイルの名前を検索する順序は、接続グループのマニフェストファイルに指定されている順序で指定されています。

次の例は、**パッケージ a**と**パッケージ B**の接続グループでのファイル名参照の順序と関係を示しています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">パッケージ A</th>
<th align="left">パッケージ B</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>C:\Windows\System32</p></td>
<td align="left"><p>C:\Windows\System32</p></td>
</tr>
<tr class="even">
<td align="left"><p>C:\ apptest</p></td>
<td align="left"><p>C:\ apptest</p></td>
</tr>
</tbody>
</table>

 

上の例では、仮想化されたアプリケーションが特定のファイルを検索しようとすると、一致するファイルパスに対してパッケージ A が最初に検索されます。 一致するパスが見つからない場合は、次のマッピングルールを使用して、パッケージ B が検索されます。

-   両方のアプリケーションパッケージの同じ仮想フォルダー階層内に**test.txt**という名前のファイルが存在する場合は、最初に一致したファイルが使用されます。

-   1つのアプリケーションパッケージの仮想フォルダー階層内に**bar.txt**という名前のファイルが存在する場合は、最初に一致するファイルが使用されます。






## 関連トピック


[接続グループの管理](managing-connection-groups51.md)

 

 





