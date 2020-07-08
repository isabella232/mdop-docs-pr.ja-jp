---
title: ユーザー単位で公開されるパッケージとグローバルに公開されるパッケージを含む接続グループを作成する方法
description: ユーザー単位で公開されるパッケージとグローバルに公開されるパッケージを含む接続グループを作成する方法
author: dansimp
ms.assetid: 82f7ea7f-7b14-4506-8940-fdcd6c3e117f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: c98981180133881909db17d19cb42771f94bd66a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814354"
---
# ユーザー単位で公開されるパッケージとグローバルに公開されるパッケージを含む接続グループを作成する方法
次のいずれかの方法を使用して、ユーザーに公開されたパッケージとグローバルに公開されたパッケージの両方を含む、ユーザーの権利を持つ接続グループを作成できます。

-   [PowerShell コマンドレットを使用してユーザーのタイトルの接続グループを作成する方法](#bkmk-posh-userentitled-cg)

-   [App-v Server を使用してユーザーのタイトルの接続グループを作成する方法](#bkmk-appvserver-userentitled-cg)

**始める前に知っておくべきこと:**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">サポートされていないシナリオと潜在的な問題</th>
<th align="left">結果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>グローバルタイトルの接続グループには、ユーザーに公開されたパッケージを含めることはできません。</p></td>
<td align="left"><p>接続グループは失敗します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>パッケージをグローバルに公開して、そのパッケージを省略可能な状態にしていないユーザー公開接続グループを作成した場合でも、別の接続グループでパッケージを使用している <strong> 場合でも、 &lt; &gt; </strong> パッケージの発行を取り下げるために、パッケージの発行を停止することができます。</p></td>
<td align="left"><p>他の接続グループがそのパッケージを使用している場合、そのパッケージはこれらの接続グループで失敗します。</p>
<p>別の接続グループで使用されているオプション以外のパッケージを誤って非公開にしないようにするには、省略可能なパッケージ以外の接続グループを追跡することをお勧めします。</p></td>
</tr>
</tbody>
</table>

 
<a href="" id="bkmk-posh-userentitled-cg"></a>**PowerShell コマンドレットを使用してユーザーのタイトルの接続グループを作成する方法**

1.  次のコマンドを使用して、パッケージを追加して公開します。

    **AppvClientPackage Package1 \ _AppV \ _file \ _Path**

    **Add-AppvClientPackage Package2 \ _AppV \ _file \ _Path**

    **Publish-AppvClientPackage-PackageId Package1 \ _ID-VersionId Package1 \ _Version ID-グローバル**

    **Publish-AppvClientPackage-PackageId Package2 \ _ID-VersionIdPackage2 \ _ID**

2.  接続グループの XML ファイルを作成します。 詳細については、「[接続グループファイルについ](about-the-connection-group-file.md)て」を参照してください。

3.  次のコマンドを使用して、接続グループを追加して公開します。

    **AppvClientConnectionGroup 接続 \ _Group \ _XML \ _file \ _Path**

    **Enable-AppvClientConnectionGroup-GroupId CG \ _Group \ _ID-VersionId CG \ _Version \ _ID**

<a href="" id="bkmk-appvserver-userentitled-cg"></a>**App-v Server を使用して、ユーザーのタイトルの接続グループを作成する方法**

1.  App-v 5.0 管理コンソールを開きます。

2.  [「管理コンソールを使用してパッケージを公開する方法](how-to-publish-a-package-by-using-the-management-console-50.md)」の指示に従って、グローバルとユーザーにパッケージを公開します。

3.  「接続グループを[作成](how-to-create-a-connection-group.md)して接続グループを作成する方法」の指示に従って、ユーザーに公開されたパッケージとグローバルに公開されたパッケージを追加します。

    App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[接続グループの管理](managing-connection-groups.md)

[接続グループでオプション パッケージを使用する方法](how-to-use-optional-packages-in-connection-groups.md)

 

 





