---
title: パッケージのバージョンを無視するように接続グループを構成する方法
description: パッケージのバージョンを無視するように接続グループを構成する方法
author: dansimp
ms.assetid: db16b095-dbe2-42c7-863d-b0d5d91b2f4c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 026ef1b3a2aa073a684b1fe5da4f79aa1067072d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813931"
---
# パッケージのバージョンを無視するように接続グループを構成する方法


Microsoft Application Virtualization (App-v) 5.1 では、任意のバージョンのパッケージを使用するように接続グループを構成することができます。これにより、パッケージのアップグレードが簡素化され、作成する必要がある接続グループの数が少なくなります。

以前のバージョンの App-v でパッケージをアップグレードするには、接続グループの無効化、接続グループの XML 定義ファイルの変更など、いくつかの手順を実行する必要がありました。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-V 5.1 でのタスクの説明</th>
<th align="left">App-v 5.1 でタスクを実行する方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>接続グループを構成して、任意のバージョンのパッケージを受け入れることができます。これにより、接続グループを無効にすることなくパッケージをアップグレードできます。</p>
<p><strong>機能のしくみ:</strong></p>
<ul>
<li><p>接続グループが複数のバージョンのパッケージにアクセスできる場合は、最新バージョンが使用されます。</p></li>
<li><p>接続グループに、バージョンが正しくないオプションのパッケージが含まれている場合、そのパッケージは無視され、接続グループの仮想環境の作成がブロックされることはありません。</p></li>
<li><p>接続グループに、バージョンが正しくないオプションのパッケージが含まれている場合、接続グループの仮想環境を作成することはできません。</p></li>
</ul></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">メソッド</th>
<th align="left">手順</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v Server –管理コンソール</p></td>
<td align="left"><ol>
<li><p>管理コンソールで、[接続グループ] を選択し <strong> </strong> ます。</p></li>
<li><p>接続グループライブラリから適切な接続グループを選択します。</p></li>
<li><p>[ <strong> </strong> 接続されているパッケージ] ウィンドウで [編集] をクリックします。</p></li>
<li><p><strong>パッケージ名の横にある [すべてのバージョンを使用する] </strong> チェックボックスをオンにし、[適用] をクリックし <strong> </strong> ます。</p></li>
</ol>
<p>パッケージの追加またはアップグレードの詳細については、「 <a href="how-to-add-or-upgrade-packages-by-using-the-management-console-51-gb18030.md" data-raw-source="[How to Add or Upgrade Packages by Using the Management Console](how-to-add-or-upgrade-packages-by-using-the-management-console-51-gb18030.md)"> 管理コンソールを使用してパッケージを追加またはアップグレードする方法」を参照してください </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>スタンドアロンコンピューター上の app-v クライアント</p></td>
<td align="left"><ol>
<li><p>接続グループの XML ドキュメントを作成します。</p></li>
<li><p>パッケージをアップグレードするには、 <strong> パッケージ </strong> タグ属性 <strong> VersionID </strong> をアスタリスク () に設定し <strong>*</strong> ます。</p></li>
<li><p>次のコマンドレットを使用して、接続グループを追加し、接続グループの XML ドキュメントへのパスを含めます。</p>
<p><strong>Add-AppvClientConnectionGroup</strong></p></li>
<li><p>パッケージをアップグレードする場合は、次のコマンドレットを使用して、古いパッケージを削除し、アップグレードされたパッケージを追加して、アップグレードされたパッケージを公開します。</p>
<ul>
<li><p>RemoveAppvClientPackage</p></li>
<li><p>Add-AppvClientPackage</p></li>
<li><p>公開-AppvClientPackage</p></li>
</ul></li>
</ol>
<p>詳細については、以下を参照してください。</p>
<ul>
<li><p>このセクションの XML ファイルの例 ( <strong> オプションのパッケージを含む接続グループの xml ファイル) </strong> : <a href="how-to-use-optional-packages-in-connection-groups51.md#bkmk-apps-plugs-optional" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups51.md#bkmk-apps-plugs-optional)"> 接続グループでオプションパッケージを使用する方法</a></p></li>
<li><p><a href="how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.1 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md)">PowerShell を使用してスタンドアロン コンピューターで実行されている App-V 5.1 パッケージを管理する方法</a></p></li>
</ul></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 






## 関連トピック


[接続グループの管理](managing-connection-groups51.md)

 

 





