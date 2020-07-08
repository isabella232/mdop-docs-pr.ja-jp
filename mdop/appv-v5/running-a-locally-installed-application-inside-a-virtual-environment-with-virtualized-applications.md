---
title: 仮想化環境内にローカルにインストールされたアプリケーションと仮想化アプリケーションとの連携した実行
description: 仮想化環境内にローカルにインストールされたアプリケーションと仮想化アプリケーションとの連携した実行
author: dansimp
ms.assetid: a8affa46-f1f7-416c-8125-9595cfbfdbc7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 10c0f3f3c8a1b88cf1a98fd64fe8f7f49b597a91
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813314"
---
# 仮想化環境内にローカルにインストールされたアプリケーションと仮想化アプリケーションとの連携した実行


ローカルにインストールされたアプリケーションは、Microsoft Application Virtualization (App-v) を使用して仮想環境で実行できます。 次のような場合に、この操作を行うことができます。

-   クライアントコンピューターにローカルでアプリケーションをインストールして実行しますが、そのローカルアプリケーションと連携して動作する特定のプラグインを仮想化して実行します。

-   App-v クライアントパッケージのトラブルシューティングを行い、App-v 仮想環境内でローカルアプリケーションを開く場合。

次のいずれかの方法を使って、App-v 仮想環境内のローカルアプリケーションを開きます。

-   [RunVirtual レジストリキー](#bkmk-runvirtual-regkey)

-   [AppvClientPackage PowerShell コマンドレット](#bkmk-get-appvclientpackage-posh)

-   [コマンドラインスイッチ/appvpid: &lt; PID&gt;](#bkmk-cl-switch-appvpid)

-   [コマンドラインフックスイッチ/appvve: &lt; GUID&gt;](#bkmk-cl-hook-switch-appvve)

各メソッドは基本的に同じタスクを実行しますが、仮想化されたアプリケーションが既に実行されているかどうかによっては、一部のメソッドが他のアプリケーションに適している場合があります。

## <a href="" id="bkmk-runvirtual-regkey"></a>RunVirtual レジストリキー


ローカルにインストールされたアプリケーションをパッケージまたは接続グループの仮想環境に追加するには、次の `RunVirtual` セクションで説明するように、レジストリエディターのレジストリキーにサブキーを追加します。

このレジストリキーを管理するために使用できるグループポリシー設定はありません。そのため、System Center Configuration Manager または別の電子ソフトウェア配布 (ESD) システムを使用するか、手動でレジストリを編集する必要があります。

### <a href="" id="bkmk-"></a>RunVirtual の使用時にパッケージ発行方法がサポートされています

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v のバージョン</th>
<th align="left">サポートされている発行方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 5.0 SP3</p></td>
<td align="left"><p>グローバルまたはユーザーに公開されている</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-V 5.0 ~ app-v 5.0 SP2</p></td>
<td align="left"><p>グローバルに公開</p></td>
</tr>
</tbody>
</table>

 

### サブキーを作成する手順

1.  次の表の情報を使用して、 **MyApp.exe**の実行可能ファイルの名前を使用して、新しいレジストリキーを作成します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">パッケージ発行方法</th>
    <th align="left">レジストリキーを作成する場所</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>グローバルに公開</p></td>
    <td align="left"><p>HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\AppV\Client\RunVirtual</p>
    <p><strong>例 </strong> : HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>ユーザーに公開</p></td>
    <td align="left"><p>HKEY_CURRENT_USER \SOFTWARE\Microsoft\AppV\Client\RunVirtual</p>
    <p><strong>例 </strong> : HKEY_CURRENT_USER \SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>次のような接続グループがあります。</p>
    <ul>
    <li><p>グローバルに、または単にユーザーに公開されるパッケージ</p></li>
    <li><p>グローバルとユーザーに公開されるパッケージ</p></li>
    </ul></td>
    <td align="left"><p>HKEY_LOCAL_MACHINE または HKEY_CURRENT_USER キーのいずれかを指定しますが、次のいずれかが満たされている必要があります。</p>
    <ul>
    <li><p>仮想環境に複数のパッケージを含める場合は、有効な接続グループに含める必要があります。</p></li>
    <li><p>[接続] グループのパッケージの1つのサブキーのみを作成します。 たとえば、グローバルに公開される1つのパッケージと、ユーザーに公開される別のパッケージがある場合は、これらのパッケージのどちらかのサブキーを作成します。 1つのパッケージのみのサブキーを作成しても、接続グループ内のすべてのパッケージとローカルアプリケーションを仮想環境で利用できるようになります。</p></li>
    <li><p>サブキーを作成するキーは、パッケージで使用した発行方法と一致する必要があります。</p>
    <p>たとえば、ユーザーにパッケージを公開した場合、の下にサブキーを作成する必要があり <code>HKEY_CURRENT_USER\SOFTWARE\Microsoft\AppV\Client\RunVirtual</code> ます。</p></li>
    </ul></td>
    </tr>
    </tbody>
    </table>

     

2.  新しいレジストリサブキーの値をパッケージの PackageId と VersionId に設定します。値はアンダースコアで区切ります。

    **書式**: &lt; PackageId &gt; \ _ &lt; VersionId&gt;

    **例**: 4c909996-afc9-4352-b606-0b74542a09c1 \ _Be463724-Oct1-48f1-8604-c4bd7ca92fa

    上の例のアプリケーションでは、次のようなレジストリエクスポートファイル (.reg ファイル) が生成されます。

    ``` syntax
    Windows Registry Editor Version 5.00 
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual] 
    @="" 
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe] 
    @="aaaaaaaa-bbbb-cccc-dddd-eeeeeeee_11111111-2222-3333-4444-555555555
    ```

## <a href="" id="bkmk-get-appvclientpackage-posh"></a>AppvClientPackage PowerShell コマンドレット


**AppVVirtualProcess**コマンドレットを使用してパッケージ名を取得し、指定されたパッケージの仮想環境内でプロセスを開始することができます。 このメソッドにより、パッケージが現在実行されているかどうかに関係なく、App-v パッケージのコンテキスト内で任意のコマンドを起動できます。

次の構文の例を使用して **、パッケージの &lt; &gt; **パッケージの名前を置き換えます。

`$AppVName = Get-AppvClientPackage <Package>`

`Start-AppvVirtualProcess -AppvClientObject $AppVName cmd.exe`

パッケージの正確な名前がわからない場合は、コマンドラインの**AppvClientPackage \ * executable\ \**を使用できます。 <em> ここで、** </em> executable*は、AppvClientPackage \ * Word \ * などのアプリケーションの名前です。

## <a href="" id="bkmk-cl-switch-appvpid"></a>コマンドラインスイッチ/appvpid: &lt; PID&gt;


**/Appvpid: &lt; pid &gt; **スイッチを任意のコマンドに適用することができます。これにより、プロセス ID (pid) を指定して、選択した仮想プロセス内でそのコマンドを実行することができます。 このメソッドを使うと、既に実行されている実行可能ファイルと同じ App-v 環境で、新しい実行可能ファイルが起動します。

例: `cmd.exe /appvpid:8108`

App-v プロセスのプロセス ID (PID) を確認するには、管理者特権のコマンドプロンプトからコマンド**tasklist.exe**を実行します。

## <a href="" id="bkmk-cl-hook-switch-appvve"></a>コマンドラインフックスイッチ/appvve: &lt; GUID&gt;


このスイッチを使用すると、App-v パッケージの仮想環境内でローカルコマンドを実行できます。 仮想環境が既に実行されている必要がある **/appvid**スイッチとは異なり、このスイッチを使用すると仮想環境を開始できます。

引数 `cmd.exe /appvve:<PACKAGEGUID_VERSIONGUID>`

例: `cmd.exe /appvve:aaaaaaaa-bbbb-cccc-dddd-eeeeeeee_11111111-2222-3333-4444-55555555`

アプリケーションのパッケージ GUID とバージョン GUID を取得するには、 **AppvClientPackage**コマンドレットを実行します。 **/Appvve**スイッチを次のように連結します。

-   コロン

-   目的のパッケージのパッケージ GUID

-   アンダースコア

-   目的のパッケージのバージョン ID

パッケージの正確な名前がわからない場合は、コマンドラインの**AppvClientPackage \ * executable\ \** <em> を使用します。ここで、** </em> executable*は、AppvClientPackage \ * Word \ * などのアプリケーションの名前です。

このメソッドにより、パッケージが現在実行されているかどうかに関係なく、App-v パッケージのコンテキスト内で任意のコマンドを起動できます。






## 関連トピック


[App-V 5.0 テクニカル リファレンス](technical-reference-for-app-v-50.md)

 

 





