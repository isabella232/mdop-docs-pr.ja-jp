---
title: アプリケーション パッケージを取得するためにクライアントを構成する方法
description: アプリケーション パッケージを取得するためにクライアントを構成する方法
author: dansimp
ms.assetid: 891f2739-da7a-46da-b452-b8c0af075525
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f5eeb0b977c6ecd44947d5d1c42d25d47b9e2530
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817827"
---
# アプリケーション パッケージを取得するためにクライアントを構成する方法


クライアントが Application Virtualization (App-v) Management サーバーを公開サーバーとして構成されている場合、既定では、クライアントは、ユーザーが使用を許可されている各パッケージのオープンソフトウェア記述子 (OSD) とパッケージマニフェストファイルをサーバーから取得します。 クライアントは、これらのファイルで定義されているパッケージソース情報を使用して、パッケージコンテンツ、アイコン、ファイルの種類の関連付けを検索する場所を決定します。

クライアントがローカルの App-v ストリーミングサーバーまたは Web サーバーやファイルサーバーなどの別の代替ソースからパッケージコンテンツ (SFT ファイル) を取得する場合は、他のサーバー上のローカルコンテンツ共有をポイントするように、コンピューター上の ApplicationSourceRoot レジストリキーの値を構成できます ()。 OSD ファイルでは、パッケージコンテンツの元のソースパスもそのまま定義されています。 ただし、クライアントは、OSD ファイルのコンテンツパスで指定されているサーバーと共有の代わりに、ApplicationSourceRoot 設定の値を使います。 これにより、クライアントが他のサーバーからコンテンツを取得するようにリダイレクトされます。

また、パッケージマニフェストファイルまたは発行サーバーによって送信されるパスでこれらの設定を上書きする場合は、OSDSourceRoot と IconSourceRoot レジストリキーの値を構成することもできます。 OSDSourceRoot は、公開時にアプリケーションパッケージの OSD ファイル取得のソースの場所を指定します。 IconSourceRoot は、公開時にアプリケーションパッケージのアイコンを取得するためのソースの場所を指定します。

**注**  
-   IconSourceRoot と OSDSourceRoot 設定は、パッケージマニフェストファイル内の値を上書きするため、Windows Installer (.msi) ファイルメソッドを使ってパッケージを展開しようとすると、パッケージマニフェストファイル内の値は、その .msi ファイル内に含まれている値よりも優先されます。

-   Publishing および HTTP (S) ストリーミング操作の両方で、App-v 4.5 SP1 クライアントは、ユーザーのコンピューターの Internet Explorer で構成されているプロキシサーバー設定を使用します。



**ApplicationSourceRoot レジストリキー値を構成するには**

-   UNC パスまたは URL のいずれかを使用して、次のレジストリキー値の ApplicationSourceRoot を構成します。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\ApplicationSourceRoot

    汎用名前付け規則 (UNC) パスの正しい形式は、 **\\\\computername\\sharefolder\\\ [folder \] \ [\ \]**(**フォルダー**は省略可能) です。 **Computername**には完全修飾ドメイン名 (FQDN) または IP アドレスを使用できます。また、**フォルダー**名にはドライブ文字を使用できます。 OSD パスの**\\\\computername\\sharedfolder**または drive 文字の部分のみが置き換えられます。

    URL パスの正しい形式は**protocol://servername: \ [port \] \ [/path\] \ [/\]**。ここで、**ポート**と**パス**は省略可能です。 **Port**が指定されていない場合は、プロトコルの既定のポートが使用されます。 OSD URL の**protocol:/server: port**部分のみが置き換えられます。

    **重要**  
    ApplicationSourceRoot 定義では、環境変数はサポートされていません。



~~~
The following table lists examples of acceptable URL and UNC path formats.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ApplicationSourceRoot</th>
<th align="left">OSD File HREF Path</th>
<th align="left">Result</th>
<th align="left">Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>rtsps://mainserver:322</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>rtsps://mainserver:322/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>rtsps://mainserver:322/prodapps</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>rtsps://mainserver:322/prodapps/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>https://mainserver:443/prodapps</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>https://mainserver:443/prodapps/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>rtsps://mainserver:322/prodapps</p></td>
<td align="left"><p>rtsp://%SFT_APPVSERVER%:554/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>rtsps://mainserver:322/prodapps/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>rtsps://mainserver:322</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>rtsps://mainserver:322/productivity/office2k3.sft</p></td>
<td align="left"><p>‘\’ converted to ‘/’</p></td>
</tr>
<tr class="even">
<td align="left"><p>rtsps://mainserver:322</p></td>
<td align="left"><p>file://\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>rtsps://mainserver:322/productivity/office2k3.sft</p></td>
<td align="left"><p>‘\’ converted to ‘/’</p></td>
</tr>
<tr class="odd">
<td align="left"><p>\\uncserver\share</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>‘/’ converted to ‘\’ and parameter dropped when converting to UNC path</p></td>
</tr>
<tr class="even">
<td align="left"><p>\\uncserver\share\prodapps</p></td>
<td align="left"><p>rtsp://appserver/productivity/office2k3.sft?customer=seq</p></td>
<td align="left"><p>\\uncserver\share\prodapps\productivity\office2k3.sft</p></td>
<td align="left"><p>‘/’ converted to ‘\’ and parameter dropped when converting to UNC path</p></td>
</tr>
<tr class="odd">
<td align="left"><p>M:</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>M:\productivity\office2k3.sft</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>M:\prodapps</p></td>
<td align="left"><p>\\uncserver\share\productivity\office2k3.sft</p></td>
<td align="left"><p>M:\prodapps\productivity\office2k3.sft</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>
~~~



**OSDSourceRoot 値を構成するには**

-   次のレジストリキー値で、[UNC パスまたは URL を使用して OSDSourceRoot を構成します。

    HKEY \ _LOCAL \ _MACHINE ¥ $ ¥¥ \ softgrid¥ 5 \ # # # ¥¥5

    次の例のように、OSDSourceRoot に使用できる形式には、UNC パスと Url が含まれます。

    **\\\\computername\\sharefolder\\resource**または**\\\\computername\\content**または** &lt; drive &gt; : \\ foldername**

    **http://computername/productivity/**/**https://computername/productivity/**

**IconSourceRoot 値を構成するには**

-   UNC パスまたは URL のいずれかを使用して、次のレジストリキー値の IconSourceRoot を構成します。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\IconSourceRoot

    IconSourceRoot の受け付け可能な形式には、次の例のように UNC パスと Url が含まれます。

    **\\\\computername\\sharefolder\\resource**または**\\\\computername\\content**または** &lt; drive &gt; : \\ foldername**

    **http://computername/productivity/**/**https://computername/productivity/**

## 関連トピック


[コマンド ラインを使用して App-V Client レジストリ設定を構成する方法](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)









