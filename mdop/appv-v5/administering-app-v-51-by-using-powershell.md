---
title: PowerShell を使用した App-V 5.1 の管理
description: PowerShell を使用した App-V 5.1 の管理
author: dansimp
ms.assetid: 9e10ff07-2cd9-4dc1-9e99-582f90c36081
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f0c64d7e0330ff5d737dfa02d87f156cc3236b04
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814874"
---
# PowerShell を使用した App-V 5.1 の管理


Microsoft Application Virtualization (App-v) 5.1 には、Windows PowerShell コマンドレットが用意されています。これは、管理者がさまざまなアプリ-V 5.1 タスクを実行するのに役立ちます。 以下のセクションでは、PowerShell と App-v 5.1 の使用について詳しく説明します。

## PowerShell を使用して App-v 5.1 を管理する方法


次の PowerShell の手順を使用して、さまざまな App V 5.1 タスクを実行します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名前</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-51.md" data-raw-source="[How to Load the PowerShell Cmdlets and Get Cmdlet Help](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-51.md)">PowerShell コマンドレットを読み込んでコマンドレットのヘルプを取得する方法</a></p></td>
<td align="left"><p>PowerShell コマンドレットをインストールして、コマンドレットのヘルプと例を見つける方法について説明します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.1 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md)">PowerShell を使用してスタンドアロン コンピューターで実行されている App-V 5.1 パッケージを管理する方法</a></p></td>
<td align="left"><p>PowerShell を使用してスタンドアロンコンピューターでクライアントパッケージのライフサイクルを管理する方法について説明します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell51.md" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell51.md)">PowerShell を使用してスタンドアロン コンピューターで接続グループを管理する方法</a></p></td>
<td align="left"><p>PowerShell を使用して接続グループを管理する方法について説明します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-modify-client-configuration-by-using-powershell51.md" data-raw-source="[How to Modify Client Configuration by Using PowerShell](how-to-modify-client-configuration-by-using-powershell51.md)">PowerShell を使用してクライアント構成を変更する方法</a></p></td>
<td align="left"><p>PowerShell を使用してクライアントを変更する方法について説明します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-apply-the-user-configuration-file-by-using-powershell51.md" data-raw-source="[How to Apply the User Configuration File by Using PowerShell](how-to-apply-the-user-configuration-file-by-using-powershell51.md)">PowerShell を使用してユーザー構成ファイルを適用する方法</a></p></td>
<td align="left"><p>PowerShell を使用してユーザー構成ファイルを適用する方法について説明します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-apply-the-deployment-configuration-file-by-using-powershell51.md" data-raw-source="[How to Apply the Deployment Configuration File by Using PowerShell](how-to-apply-the-deployment-configuration-file-by-using-powershell51.md)">PowerShell を使用して展開構成ファイルを適用する方法</a></p></td>
<td align="left"><p>PowerShell を使用して展開構成ファイルを適用する方法について説明します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-sequence-a-package--by-using-powershell-51.md" data-raw-source="[How to Sequence a Package by Using PowerShell](how-to-sequence-a-package--by-using-powershell-51.md)">PowerShell を使用してパッケージをシーケンス処理する方法</a></p></td>
<td align="left"><p>PowerShell を使用して新しいパッケージを作成する方法について説明します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-create-a-package-accelerator-by-using-powershell51.md" data-raw-source="[How to Create a Package Accelerator by Using PowerShell](how-to-create-a-package-accelerator-by-using-powershell51.md)">PowerShell を使用してパッケージ アクセラレータを作成する方法</a></p></td>
<td align="left"><p>PowerShell を使用してパッケージアクセラレータを作成する方法について説明します。 パッケージアクセラレータを使うと、大規模で複雑なアプリケーションを自動的にシーケンスできます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-enable-reporting-on-the-app-v-51-client-by-using-powershell.md" data-raw-source="[How to Enable Reporting on the App-V 5.1 Client by Using PowerShell](how-to-enable-reporting-on-the-app-v-51-client-by-using-powershell.md)">PowerShell を使用して App-V 5.1 Client のレポート機能を有効にする方法</a></p></td>
<td align="left"><p>App-v 5.1 を実行しているコンピューターでレポート情報を送信できるようにする方法について説明します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell51.md" data-raw-source="[How to Install the App-V Databases and Convert the Associated Security Identifiers by Using PowerShell](how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell51.md)">PowerShell を使用して App-v データベースをインストールし、関連付けられたセキュリティ識別子を変換する方法</a></p></td>
<td align="left"><p>アカウント名の配列を取得し、標準形式と16進数形式でそれぞれの名前を対応する SID に変換する方法について説明します。</p></td>
</tr>
</tbody>
</table>

 

**重要** App-v パッケージで実行したスクリプトは、PowerShell 用に構成した実行ポリシーと一致していることを確認してください。

 

## PowerShell エラー処理


App-v 5.1 PowerShell エラー処理については、次の表を参照してください。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">イベント</th>
<th align="left">操作</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>埋め込みスクリプトでの RollbackOnError 属性の使用</p></td>
<td align="left"><p><strong> </strong> 埋め込みスクリプトと共に RollbackOnError 属性を使うと、次のイベントについては属性が無視されます。</p>
<ul>
<li><p>パッケージの削除</p></li>
<li><p>パッケージの発行を取り消している</p></li>
<li><p>仮想環境の終了</p></li>
<li><p>プロセスの終了</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>パッケージ名の内容<strong>$</strong></p></td>
<td align="left"><p>パッケージ名に文字 () が含まれている場合は、 <strong> $ </strong> 次のように単一引用符 ( <strong> ') を使用する必要があります。 </strong></p>
<p><strong>Add-AppvClientPackage ' Contoso $ App-info '</strong></p></td>
</tr>
</tbody>
</table>

 






## 関連トピック


[APP-V 5.1 の操作](operations-for-app-v-51.md)

 

 





