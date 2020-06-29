---
title: APP-V 5.0 Client 管理コンソールの使用
description: APP-V 5.0 Client 管理コンソールの使用
author: dansimp
ms.assetid: 36398307-57dd-40f3-9d4f-b09f44fd37c3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8541e5bc59334b9074a3940dad7cdf0114205d4c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813259"
---
# APP-V 5.0 Client 管理コンソールの使用


このトピックでは、App-v 5.0 クライアントの構成と管理を行う方法について説明します。

## App-v 5.0 クライアント構成を変更する


App-v 5.0 クライアントには、環境でクライアントを実行する方法を決定するために構成可能な設定が関連付けられています。 クライアントを実行するコンピューター、または PowerShell またはグループポリシーを使って、これらの設定を管理できます。 PowerShell またはグループポリシー構成を使用してクライアントを変更する方法の詳細については、「 [Powershell を使用してクライアント構成を変更する方法](how-to-modify-client-configuration-by-using-powershell.md)」を参照してください。

## <a href="" id="the-app-v-5-0-client-management-console-"></a>App-v 5.0 クライアント管理コンソール


App-v 5.0 クライアントに関する情報を取得したり、App-v 5.0 クライアント管理コンソールを使用して特定のタスクを実行したりすることができます。 クライアント管理コンソールで実行できるタスクの多くは、PowerShell を使用して実行することもできます。 各アクションに関連付けられている PowerShell コマンドレットも、次の表に表示されます。 PowerShell の使い方の詳細については、「 [Powershell を使用](administering-app-v-by-using-powershell.md)した App-v の管理」を参照してください。

クライアント管理コンソールには、次に示すメインタブがあります。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タブ</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>概要</p></td>
<td align="left"><p>[ <strong> 概要 </strong> ] タブには、次の要素が含まれます。</p>
<ul>
<li><p>更新-[更新] タイルを使用して、 <strong> </strong> 仮想化されたアプリケーションを更新するか、仮想化された新しいパッケージを受信します。</p>
<p>最後の更新には、 <strong> </strong> 仮想化されたパッケージの現在のバージョンが表示されます。</p></li>
<li><p>すべての仮想アプリケーションをダウンロード- <strong> ダウンロードタイルを使用して、 </strong> 現在のユーザーにプロビジョニングされたすべてのパッケージをダウンロードします。</p>
<p>(関連付けられている PowerShell コマンドレット: <strong>Mount-AppvClientPackage </strong> )</p>
<p></p></li>
<li><p>オフライン作業–このタイルを使用して、すべての自動および手動による仮想アプリケーションの更新を許可しません。</p>
<p>(関連付けられている PowerShell コマンドレット: <strong>Set-AppvPublishServer – UserRefreshEnabled – GlobalRefreshEnabled </strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>仮想アプリ</p></td>
<td align="left"><p>[ <strong> 仮想アプリ </strong> ] タブには、ユーザーに公開されたすべてのパッケージが表示されます。 特定のパッケージをクリックすると、そのパッケージに含まれているすべてのアプリケーションを表示することもできます。 現在使用されているパッケージについての情報と、各パッケージがどの程度コンピューターにダウンロードされているかが表示されます。 パッケージのダウンロードを開始および停止することもできます。 さらに、ユーザーの状態を修復することもできます。 修復すると、パッケージに関連付けられているすべてのユーザーデータが削除されます。</p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>アプリ接続グループ</p></td>
<td align="left"><p>[ <strong> アプリ接続グループ </strong> ] タブには、現在のユーザーが利用できるすべての接続グループが表示されます。 特定の接続グループをクリックすると、選択したグループに含まれるすべてのパッケージが表示されます。 既に使用されている接続グループと、コンピューターにダウンロードされた接続グループの内容に関する情報が表示されます。 さらに、接続グループのダウンロードを開始して停止することもできます。 このセクションを使って修復を開始できます。 修復すると、接続グループに関連付けられているユーザーの状態がすべて削除されます。</p>
<p>(関連付けられている PowerShell コマンドレット: ダウンロード- <strong>Mount-AppvClientConnectionGroup </strong> 。 修復- <strong> AppvClientConnectionGroup </strong> )</p>
<p></p></td>
</tr>
</tbody>
</table>

 

[Client 管理コンソールにアクセスする方法](how-to-access-the-client-management-console.md)

[公開サーバーからパッケージと接続グループの更新を受信するように Client を構成する方法](how-to-configure-the-client-to-receive-package-and-connection-groups-updates-from-the-publishing-server-beta.md)






## 関連トピック


[APP-V 5.0 の操作](operations-for-app-v-50.md)

 

 





