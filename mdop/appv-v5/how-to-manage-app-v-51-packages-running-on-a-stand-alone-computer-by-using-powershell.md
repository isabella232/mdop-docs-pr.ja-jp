---
title: PowerShell を使用してスタンドアロン コンピューターで実行されている App-V 5.1 パッケージを管理する方法
description: PowerShell を使用してスタンドアロン コンピューターで実行されている App-V 5.1 パッケージを管理する方法
author: dansimp
ms.assetid: c3fd06f6-102f-43d1-a577-d5ced6ac537d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b454014da4e5f349af913d3fea8ea3837598a039
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813915"
---
# PowerShell を使用してスタンドアロン コンピューターで実行されている App-V 5.1 パッケージを管理する方法


以下のセクションでは、PowerShell を使用して、スタンドアロンクライアントコンピューターでさまざまな管理タスクを実行する方法について説明します。

-   [パッケージの一覧を返すには](#bkmk-return-pkgs-standalone-posh)

-   [パッケージを追加するには](#bkmk-add-pkgs-standalone-posh)

-   [パッケージを発行するには](#bkmk-pub-pkg-standalone-posh)

-   [パッケージを特定のユーザーに発行するには](#bkmk-pub-pkg-a-user-standalone-posh)

-   [パッケージを追加して発行するには](#bkmk-add-pub-pkg-standalone-posh)

-   [既存のパッケージの発行を取り消すには](#bkmk-unpub-pkg-standalone-posh)

-   [特定のユーザーに対してパッケージの発行を取り消すには](#bkmk-unpub-pkg-specfc-use)

-   [既存のパッケージを削除するには](#bkmk-remove-pkg-standalone-posh)

-   [管理者のみがパッケージの発行または発行を取り消すことができるようにするには](#bkmk-admins-pub-pkgs)

-   [保留中のパッケージについて (UserPending および GlobalPending)](#bkmk-understd-pend-pkgs)

## <a href="" id="bkmk-return-pkgs-standalone-posh"></a>パッケージの一覧を返すには


特定のユーザーに与えられているパッケージの一覧を返すには、次の情報を使用します。

**コマンドレット**: AppvClientPackage

**パラメーター**:-Name-バージョン-PackageID-VersionID

**例**: AppvClientPackage – Name "ContosoApplication"-バージョン2

## <a href="" id="bkmk-add-pkgs-standalone-posh"></a>パッケージを追加するには


パッケージをコンピューターに追加するには、次の情報を使用します。

**重要** この例では、パッケージのみが追加されます。 パッケージはユーザーまたはコンピューターに発行されません。

 

**コマンドレット**: Add-AppvClientPackage

**例**: $Contoso = Add-AppvClientPackage \\\\path\\to\\appv\\package.appv

## <a href="" id="bkmk-pub-pkg-standalone-posh"></a>パッケージを発行するには


特定のユーザーに追加された、またはコンピューター上のすべてのユーザーに対してグローバルに追加されたパッケージを公開するには、次の情報を使用します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">公開方法</th>
<th align="left">コマンドレットと例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ユーザーへの公開</p></td>
<td align="left"><p><strong>コマンドレット </strong> : Publish-AppvClientPackage</p>
<p><strong>例 </strong> : Publish-AppvClientPackage "ContosoApplication"</p></td>
</tr>
<tr class="even">
<td align="left"><p>グローバルに公開する</p></td>
<td align="left"><p><strong>コマンドレット </strong> : Publish-AppvClientPackage</p>
<p><strong>例 </strong> : Publish-AppvClientPackage "ContosoApplication"-グローバル</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-pub-pkg-a-user-standalone-posh"></a>パッケージを特定のユーザーに発行するには


**注** このパラメーターを使用するには、App-v 5.0 SP2 ホットフィックスパッケージ5以降を使用する必要があります。

 

管理者は、 **AppvClientPackage**コマンドレットでオプションの**UserSID**パラメーターを指定して、特定のユーザーにパッケージを発行できます。このパラメーターは、エンドユーザーのセキュリティ識別子 (SID)**を表します**。

このパラメーターを使用するには:

-   このコマンドレットは、ユーザーまたは管理者セッションから実行できます。

-   パラメーターを使用するには、管理者の資格情報を使ってログインしている必要があります。

-   エンドユーザーはログインしている必要があります。

-   エンドユーザーのセキュリティ識別子 (SID) を指定する必要があります。

**コマンドレット**: Publish-AppvClientPackage

**例**: Publish-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345

## <a href="" id="bkmk-add-pub-pkg-standalone-posh"></a>パッケージを追加して発行するには


パッケージをコンピューターに追加してユーザーに公開するには、次の情報を使用します。

**コマンドレット**: Add-AppvClientPackage

**例**: Add-AppvClientPackage \\\\path\\to\\appv\\package.appv |公開-AppvClientPackage

## <a href="" id="bkmk-unpub-pkg-standalone-posh"></a>既存のパッケージの発行を取り消すには


次の情報を使用して、ユーザーに資格があり、コンピューターからパッケージを削除しないパッケージの発行を取り消すことができます。

**コマンドレット**: AppvClientPackage

**例**: AppvClientPackage "ContosoApplication"

## <a href="" id="bkmk-unpub-pkg-specfc-use"></a>特定のユーザーに対してパッケージの発行を取り消すには


**注** このパラメーターを使用するには、App-v 5.0 SP2 ホットフィックスパッケージ5以降を使用する必要があります。

 

管理者は、オプション **– usersid**パラメーターとして**AppvClientPackage**コマンドレットを使用して、特定のユーザーのパッケージの発行を取り下げることができます。ここで、 **-UserSID**はエンドユーザーのセキュリティ識別子 (SID) を表します。

このパラメーターを使用するには:

-   このコマンドレットは、ユーザーまたは管理者セッションから実行できます。

-   パラメーターを使用するには、管理者の資格情報を使ってログインしている必要があります。

-   エンドユーザーはログインしている必要があります。

-   エンドユーザーのセキュリティ識別子 (SID) を指定する必要があります。

**コマンドレット**: AppvClientPackage

**例**: AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345

## <a href="" id="bkmk-remove-pkg-standalone-posh"></a>既存のパッケージを削除するには


コンピューターからパッケージを削除するには、次の情報を使用します。

**コマンドレット**: Remove-AppvClientPackage

**例**: Remove-AppvClientPackage "ContosoApplication"

**注** アプリ-V コマンドレットは、わかりやすくするために、前の例の変数に割り当てられています。課題は必須ではありません。 [パッケージを追加して公開するに](#bkmk-add-pub-pkg-standalone-posh)は、ほとんどのコマンドレットをに示されているように組み合わせることができます。 詳細なチュートリアルについては、「 [app-v 5.0 クライアント PowerShell (詳細](https://go.microsoft.com/fwlink/?LinkId=324466))」を参照してください。

 

## <a href="" id="bkmk-admins-pub-pkgs"></a>管理者のみがパッケージの発行または発行を取り消すことができるようにするには


**注** 
**この機能は、app-v 5.0 SP3 以降でサポートされています。**

 

次のコマンドレットとパラメーターを使用して、(エンドユーザーではなく) 管理者のみがパッケージを公開または非公開にすることを許可します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>コマンドレット</strong></p></td>
<td align="left"><p>Set-AppvClientConfiguration</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>パラメーター</strong></p></td>
<td align="left"><p>-RequirePublishAsAdmin</p>
<p>パラメーターの値:</p>
<ul>
<li><p>0-偽</p></li>
<li><p>1-True</p></li>
</ul>
<p><strong>例: </strong> AppvClientConfiguration – RequirePublishAsAdmin1</p></td>
</tr>
</tbody>
</table>

 

App-v 管理コンソールを使ってこの構成を設定する方法については、「[管理コンソールを使用してパッケージを公開する方法](how-to-publish-a-package-by-using-the-management-console-51.md)」を参照してください。

## <a href="" id="bkmk-understd-pend-pkgs"></a>保留中のパッケージについて (UserPending および GlobalPending)


**App-v 5.0 SP2 以降**: 現在使用されているパッケージに影響を与える PowerShell コマンドレットを実行すると、実行しようとしているタスクは保留中の状態に置かれます。 たとえば、パッケージ内のアプリケーションを使っているときにパッケージを公開しようとした場合、 **AppvClientPackage**を実行すると、次のように、コマンドレットの出力に保留状態が表示されます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コマンドレットの出力項目</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>UserPending</p></td>
<td align="left"><p>表示されているパッケージに、ユーザーに適用されている保留中のタスクがあるかどうかを示します。</p>
<ul>
<li><p>True</p></li>
<li><p>False</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>GlobalPending</p></td>
<td align="left"><p>表示されているパッケージに、コンピューターにグローバルに適用される保留中のタスクが含まれているかどうかを示します。</p>
<ul>
<li><p>True</p></li>
<li><p>False</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

保留中のタスクは、次のルールに従って後で実行されます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスクの種類</th>
<th align="left">該当するルール</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ユーザーベースのタスク (パッケージをユーザーに公開するなど)</p></td>
<td align="left"><p>保留中のタスクは、ユーザーがログオフしてから再びログインした後に実行されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>グローバルに基づくタスク (例: 接続グループをグローバルに有効にする)</p></td>
<td align="left"><p>保留中のタスクは、コンピューターをシャットダウンしてから再起動したときに実行されます。</p></td>
</tr>
</tbody>
</table>

 

保留中のタスクの詳細については、「 [app-v 5.0 SP2 につい](about-app-v-50-sp2.md#bkmk-pkg-upgr-pendg-tasks)て」を参照してください。

App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[APP-V 5.1 の操作](operations-for-app-v-51.md)

[PowerShell を使用した App-V 5.1 の管理](administering-app-v-51-by-using-powershell.md)

 

 





