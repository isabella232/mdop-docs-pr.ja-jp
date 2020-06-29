---
title: PowerShell を使用してスタンドアロン コンピューターで接続グループを管理する方法
description: PowerShell を使用してスタンドアロン コンピューターで接続グループを管理する方法
author: dansimp
ms.assetid: b73ae74d-8a6f-4bb3-b1f2-0067c7bd5212
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 32dd4f9c5ad1ba4ae9e25246d5ec52a6363ef303
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813923"
---
# PowerShell を使用してスタンドアロン コンピューターで接続グループを管理する方法


App-v 接続グループでは、すべての仮想アプリケーションを1つの仮想環境内のパッケージの定義済みセットとして実行できます。 たとえば、個別のパッケージを使用してアプリケーションとそのプラグインを仮想化して、1つの接続グループで実行することができます。

接続グループの XML ファイルは、App-v クライアントをインストールしたコンピューターで実行される接続グループを定義します。 接続グループの XML ファイルとその構成方法については、「[接続グループファイルについ](about-the-connection-group-file.md)て」を参照してください。

このトピックでは、次の手順について説明します。

-   [接続グループに App-v パッケージを追加して発行するには](#bkmk-add-pub-pkgs-in-cg)

-   [App-v クライアントで接続グループを追加して有効にするには](#bkmk-add-enable-cg-on-clt)

-   [特定のユーザーに対して接続グループを有効または無効にするには](#bkmk-enable-cg-for-user-poshtopic)

-   [管理者のみが接続グループを有効にできるようにするには](#bkmk-admin-only-posh-topic-cg)

<a href="" id="bkmk-add-pub-pkgs-in-cg"></a>**接続グループに App-v パッケージを追加して発行するには**

1.  App-v クライアントを実行しているコンピューターに app-v 5.0 パッケージを追加して発行するには、次のコマンドを入力します。

    Add-AppvClientPackage – path c:\\tmpstore\\quartfin.appv |公開-AppvClientPackage

2.  接続グループ内の各パッケージについて、**手順 1**を繰り返します。

<a href="" id="bkmk-add-enable-cg-on-clt"></a>**App-v クライアントで接続グループを追加して有効にするには**

1.  次のコマンドを入力して、接続グループを追加します。

    Add-AppvClientConnectionGroup – path c:\\tmpstore\\financ.xml

2.  次のコマンドを入力して、接続グループを有効にします。

    Enable-AppvClientConnectionGroup – name "財務アプリケーション"

    メンバーパッケージ内の仮想アプリケーションがターゲットコンピューターで実行されると、接続グループの仮想環境内で実行され、接続グループ内の他のパッケージ内のすべての仮想アプリケーションで使用できるようになります。

<a href="" id="bkmk-enable-cg-for-user-poshtopic"></a>**特定のユーザーに対して接続グループを有効または無効にするには**

1.  パラメーターの説明と要件を確認します。

    -   このパラメーターを使用すると、管理者は特定のユーザーに対して接続グループを有効または無効にすることができます。

    -   このパラメーターを使用するには、App-v 5.0 SP2 ホットフィックスパッケージ5以降を使用する必要があります。

    -   このコマンドレットは、ユーザーまたは管理者セッションから実行できます。

    -   パラメーターを使用するには、管理者の資格情報を使ってログインしている必要があります。

    -   エンドユーザーはログインしている必要があります。

    -   エンドユーザーのセキュリティ識別子 (SID) を指定する必要があります。

2.  次のコマンドレットを使用して、オプションの [ **usersid]** パラメーターを追加します。ここで、 **-UserSID**はエンドユーザーのセキュリティ識別子 (SID) を表します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">コマンドレット</th>
    <th align="left">例</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Enable-AppVClientConnectionGroup</p></td>
    <td align="left"><p>Enable-AppVClientConnectionGroup "ConnectionGroupA"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Disable-AppVClientConnectionGroup</p></td>
    <td align="left"><p>Disable-AppVClientConnectionGroup "ConnectionGroupA"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</p></td>
    </tr>
    </tbody>
    </table>

<a href="" id="bkmk-admin-only-posh-topic-cg"></a>**管理者のみが接続グループを有効にできるようにするには**

1.  このコマンドレットを使用するための説明と要件を確認します。

    -   このコマンドレットとパラメーターを使用して、管理者 (エンドユーザーではない) だけが接続グループを有効または無効にできるように、App-v クライアントを構成します。

    -   このコマンドレットを使用するには、少なくとも App-v 5.0 SP3 を使用している必要があります。

2.  次のコマンドレットとパラメーターを実行します。

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">コマンドレット</th>
    <th align="left">パラメーターと値</th>
    <th align="left">例</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Set-AppvClientConfiguration</p></td>
    <td align="left"><p>– RequirePublishAsAdmin</p>
    <ul>
    <li><p>0-偽</p></li>
    <li><p>1-True</p></li>
    </ul></td>
    <td align="left"><p>Set-AppvClientConfiguration – RequirePublishAsAdmin1</p></td>
    </tr>
    </tbody>
    </table>

    App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[APP-V 5.0 の操作](operations-for-app-v-50.md)

[PowerShell を使用した App-V の管理](administering-app-v-by-using-powershell.md)

 

 





