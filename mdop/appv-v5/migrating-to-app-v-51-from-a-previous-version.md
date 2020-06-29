---
title: 以前のバージョンから APP-V 5.1 への移行
description: 以前のバージョンから APP-V 5.1 への移行
author: dansimp
ms.assetid: e7ee0edc-7544-4c0a-aaca-d922a33bc1bb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7fb6ddbfed4f6fd1ae9613d2ee86361a51918a65
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813554"
---
# 以前のバージョンから APP-V 5.1 への移行


Microsoft Application Virtualization (App-v) 5.1 を使用すると、既存のアプリ-V 4.6 または App-v 5.0 インフラストラクチャを、より柔軟かつ統合化され、より簡単に5.1 管理することができます。
ただし、App-v から app-v 5.1 に直接移行することはできません。最初に App-v 5.0 に移行する必要があります。 App-v から app-v への移行の詳細については、「[以前のバージョンから移行](migrating-from-a-previous-version-app-v-50.md)5.0 する」を参照してください。  

**注** App-v 5.1 パッケージは、app-v 5.0 パッケージとまったく同じです。 バージョン間のパッケージ形式は変更されていないため、App-v 5.0 パッケージを App-v 5.1 パッケージに変換する必要はありません。

App-v 4.6 と App-v 5.1 の違いの詳細については、「 [app-v 5.0 について](about-app-v-50.md)」の「app-v **4.6 と app-v 5.0」セクション**を参照してください。

 

## <a href="" id="bkmk-pkgconvimprove"></a>App-v 5.1 パッケージコンバーターの改善


これで、パッケージコンバーターを使用して、スクリプトを含む App-v 4.6 パッケージ、ソースからのレジストリ情報とスクリプトをパッケージコンバーター出力に含めることができるようになりました。

また、この `–OSDsToIncludeInPackage` パラメーターをコマンドレットと共に使用して、 `ConvertFrom-AppvLegacyPackage` どの .osd ファイルの情報が変換され、新しいパッケージ内に配置されるかを指定することもできます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">アプリの新バージョン-V 5.1</th>
<th align="left">App-v 5.1 より前</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>新しい .xml ファイルは、パッケージに関連付けられている .osd ファイルに対応して作成されます。これらのファイルには、次の情報が含まれます。</p>
<ul>
<li><p>環境変数</p></li>
<li><p>ショートカット</p></li>
<li><p>ファイルの種類の関連付け</p></li>
<li><p>レジストリ情報</p></li>
<li><p>スクリプト</p></li>
</ul>
<p>ソースディレクトリの .osd ファイルのサブセットから、パラメーターを使ってパッケージに情報を追加することができるようになりました <code>-OSDsToIncludeInPackage</code> 。</p></td>
<td align="left"><p>パッケージに関連付けられている .osd ファイルに含まれているレジストリ情報とスクリプトは、パッケージコンバーター出力に含まれていませんでした。</p>
<p>パッケージコンバーターは、新しいパッケージに、ソースディレクトリ内のすべての .osd ファイルからの情報を設定します。</p></td>
</tr>
</tbody>
</table>

 

### 変換ステートメントの例

新しいプロセスについて理解するには、次のパッケージコンバータステートメントの例を確認し `ConvertFrom-AppvLegacyPackage` ます。

**ソースディレクトリ (\\\\OldPkgStore\\ContosoApp) には、次のものが含まれています。**

-   ContosoApp

-   ContosoApp.msi

-   ContosoApp.sprj

-   ContosoApp\_manifest.xml

-   X. osd

-   Y .osd

-   Z-.osd

**このコマンドを実行します。**

``` syntax
ConvertFrom-AppvLegacyPackage –SourcePath \\OldPkgStore\ContosoApp\ 
-DestinationPath \\NewPkgStore\ContosoApp\
-OSDsToIncludeInPackage X.osd,Y.osd
```

**以下は、移行先ディレクトリ (\\\\NewPkgStore\\ContosoApp) で作成されます。**

-   ContosoApp

-   ContosoApp.msi

-   ContosoApp\_DeploymentConfig.xml

-   ContosoApp\_UserConfig.xml

-   X\_Config.xml

-   Y\_Config.xml

-   Z\_Config.xml

**上の例では、次のようになります。**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">これらのソースディレクトリファイル...</th>
<th align="left">...は、次の宛先ディレクトリファイルに変換されます...</th>
<th align="left">...これらのアイテムは</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><ul>
<li><p>X. osd</p></li>
<li><p>Y .osd</p></li>
<li><p>Z-.osd</p></li>
</ul></td>
<td align="left"><ul>
<li><p>X_Config.xml</p></li>
<li><p>Y_Config.xml</p></li>
<li><p>Z_Config.xml</p></li>
</ul></td>
<td align="left"><ul>
<li><p>環境変数</p></li>
<li><p>ショートカット</p></li>
<li><p>ファイルの種類の関連付け</p></li>
<li><p>レジストリ情報</p></li>
<li><p>スクリプト</p></li>
</ul></td>
<td align="left"><p>各 .osd ファイルは、ここに記載されている項目を含む、個別の .xml ファイルに変換されます。これらのファイルは、ここに記載されているアプリ-V 5.1 展開構成形式になっています。 これらの項目は、必要に応じて、これらの .xml ファイルからコピーし、展開構成またはユーザー構成ファイルに配置することができます。</p>
<p>この例には、ソースディレクトリの3つの .osd ファイルに対応する3つの .xml ファイルがあります。 各 .xml ファイルには、環境変数、ショートカット、ファイルの種類の関連付け、レジストリ情報、スクリプトが含まれており、対応する .osd ファイルが含まれています。</p></td>
</tr>
<tr class="even">
<td align="left"><ul>
<li><p>X. osd</p></li>
<li><p>Y .osd</p></li>
</ul></td>
<td align="left"><ul>
<li><p>ContosoApp</p></li>
<li><p>ContosoApp_DeploymentConfig.xml</p></li>
<li><p>ContosoApp_UserConfig.xml</p></li>
</ul></td>
<td align="left"><ul>
<li><p>環境変数</p></li>
<li><p>ショートカット</p></li>
<li><p>ファイルの種類の関連付け</p></li>
</ul></td>
<td align="left"><p>パラメーターで指定された .osd ファイルからの情報 <code>-OSDsToIncludeInPackage</code> が変換され、パッケージ内に配置されます。 次に、コンバーターは展開構成ファイルとユーザー構成ファイルにパッケージの内容を設定します。これは、新しいパッケージの順序付けの場合と同様です。</p>
<p>この例では、環境変数、ショートカット、およびファイルの種類の関連付けが X. .osd と Y パッケージに含まれており、これらの情報の一部も展開構成ファイルとユーザー構成ファイルに含まれています。 X. osd と Y はパラメーターの引数として指定されているために使われます <code>-OSDsToIncludeInPackage</code> 。 このパッケージには、これらの引数の1つとして含まれていないため、Z-index からの情報はパッケージに含まれていませんでした。</p></td>
</tr>
</tbody>
</table>

 

## 以前のバージョンの App-v を使用して作成されたパッケージの変換


Package converter ユーティリティーを使って、app-v 5.0 のバージョンを使って作成された仮想アプリケーションパッケージをアップグレードしてください。 パッケージコンバーターは、PowerShell を使用してパッケージを変換し、変換が必要なパッケージが多い場合は、プロセスの自動化に役立ちます。

**重要** 既存のパッケージを変換した後は、パッケージを展開する前にパッケージをテストして、変換処理が正常に完了したことを確認する必要があります。

 

**既存のパッケージを変換する前に知っておくべきこと**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">問題</th>
<th align="left">回避策</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>変換後、DSC を使用する仮想パッケージはリンクされません。</p></td>
<td align="left"><p>接続グループを使ってパッケージをリンクします。 「 <a href="managing-connection-groups51.md" data-raw-source="[Managing Connection Groups](managing-connection-groups51.md)"> 接続グループの管理」をご覧ください </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>変換中に環境変数の競合が検出されます。</p></td>
<td align="left"><p>関連付けられている .osd ファイル内の競合を解決 <strong> </strong> します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>変換中にハードコーディングされたパスが検出されます。</p></td>
<td align="left"><p>ハードコーディングされたパスは正しく変換されにくくなります。 パッケージコンバーターは、ハードコーディングされたパスを含むファイルを含むパッケージを検出して返します。 ハードコーディングされたパスでファイルを表示し、パッケージにファイルが必要かどうかを確認します。 その場合は、パッケージの順序を再確認することをお勧めします。</p></td>
</tr>
</tbody>
</table>

 

パッケージを変換するときに、エラーが発生したファイルまたはショートカットを確認します。 App-V 4.6 パッケージでアイテムを見つけます。 ハードコードされたパスである可能性があります。 パスを変換します。

**注** 機能を活用する必要がある重要なアプリケーションやアプリケーションを変換するには、App-v 5.1 sequencer を使うことをお勧めします。 「 [App-v 5.1 を使って新しいアプリケーションを順序付けする方法](how-to-sequence-a-new-application-with-app-v-51-beta-gb18030.md)」を参照してください。

変換後に変換されたパッケージが開かない場合は、App-v 5.1 sequencer を使用してアプリケーションを再シーケンスすることをお勧めします。

 

[以前のバージョンの APP-V で作成されたパッケージを変換する方法](how-to-convert-a-package-created-in-a-previous-version-of-app-v51.md)

## クライアントの移行


次の表は、クライアントをアップグレードするための推奨される方法を示しています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスク</th>
<th align="left">詳細情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>環境を最新バージョンの App-v にアップグレードする-V 4.6</p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)">アプリケーションの仮想化の展開とアップグレードに関する考慮事項 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>共存を有効にした App-v 5.1 クライアントをインストールします。</p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md" data-raw-source="[How to Deploy the App-V 4.6 and the App-V 5.1 Client on the Same Computer](how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md)">同じコンピューターに app-v 4.6 と App-v 5.1 クライアントを展開する方法を説明 </a> します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>アプリ-V 5.1 パッケージのシーケンスとロールアウト。 必要に応じて、App-v 4.6 パッケージの発行を取り消します。</p></td>
<td align="left"><p><a href="how-to-sequence-a-new-application-with-app-v-51-beta-gb18030.md" data-raw-source="[How to Sequence a New Application with App-V 5.1](how-to-sequence-a-new-application-with-app-v-51-beta-gb18030.md)">App-V 5.1 を使って新しいアプリケーションをシーケンスする方法について説明 </a> します。</p></td>
</tr>
</tbody>
</table>

 

**重要** 共存モードを使用するには、最新バージョンの App-v を実行している必要があります。 さらに、パッケージをシーケンス処理するときには、 **[ユーザーの****構成] セクションに**ある [管理権限] 設定を構成する必要があります。

 

## App-v 5.1 Server の完全なインフラストラクチャを移行する


完全な App-v 5.1 インフラストラクチャにアップグレードする直接的な方法はありません。 App-v server のアップグレードについては、次のセクションの情報を参照してください。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスク</th>
<th align="left">詳細情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>環境を最新バージョンの App-v 4.6 にアップグレードします。</p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)">アプリケーションの仮想化の展開とアップグレードに関する考慮事項 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>クライアントの App-v 5.1 バージョンを展開します。</p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-client-51gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-51gb18030.md)">App-v クライアントを展開する方法を説明 </a> します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 5.1 server をインストールします。</p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-51-server.md" data-raw-source="[How to Deploy the App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md)">App-v 5.1 サーバーを展開する方法について説明 </a> します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>既存のパッケージを移行します。</p></td>
<td align="left"><p><strong>この記事の「以前のバージョンの app-v を使用して作成されたパッケージの変換」を参照してください </strong> 。</p></td>
</tr>
</tbody>
</table>

 

## その他の移行タスク


また、エンドポイントの再構成や、App-v 5.1 クライアントを実行しているコンピューター上で以前のバージョンを使用して作成されたパッケージの開くなど、追加の移行タスクを実行することもできます。 次のリンクでは、これらのタスクを実行する方法について詳しく説明します。

[特定のコンピューター上の全ユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.1 パッケージに移行する方法](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-51-package-for-all-users-on-a-specific-computer.md)

[特定のユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.1 パッケージに移行する方法](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-51-for-a-specific-user.md)

[特定のコンピューター上の全ユーザーの拡張ポイントを App-V 5.1 パッケージから App-V 4.6 パッケージに戻す方法](how-to-revert-extension-points-from-an-app-v-51-package-to-an-app-v-46-package-for-all-users-on-a-specific-computer.md)

[特定のユーザーの拡張ポイントを App-V 5.1 パッケージから App-V 4.6 パッケージに戻す方法](how-to-revert-extension-points-from-an-app-v-51-package-to-an-app-v-46-package-for-a-specific-user.md)







## App-v の移行タスクを実行するためのその他のリソース


[APP-V 5.1 の操作](operations-for-app-v-51.md)

[簡素化された Microsoft App-V 5.1 Management Server のアップグレード手順](https://go.microsoft.com/fwlink/p/?LinkId=786330)

 

 





