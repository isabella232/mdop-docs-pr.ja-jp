---
title: App-V インストール後のチェックリスト
description: App-V インストール後のチェックリスト
author: dansimp
ms.assetid: 74db297e-a744-4287-bcc6-0e096ca8b57a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 79728bd2043076b20eb37ba0b1fa6f834a0d94bf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819804"
---
# App-V インストール後のチェックリスト


次のチェックリストは、考慮すべき項目の概要と、Microsoft Application Virtualization (App-v) Management Server、App-v Streaming Server、および App-v Desktop Client のインストールを完了した後に実行する必要がある手順の概要を示しています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ステップ</th>
<th align="left">リファレンス</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v Management Server または Streaming Server サービスのファイアウォール例外を作成します。</p></td>
<td align="left"><p><a href="configuring-the-firewall-for-the-app-v-servers.md" data-raw-source="[Configuring the Firewall for the App-V Servers](configuring-the-firewall-for-the-app-v-servers.md)">App-V サーバー用にファイアウォールを構成する</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>既定のアプリケーションの発行、ストリーミング、テストを行って、App-v システムが正常に動作していることを確認します。</p></td>
<td align="left"><p><a href="how-to-install-and-configure-the-default-application.md" data-raw-source="[How to Install and Configure the Default Application](how-to-install-and-configure-the-default-application.md)">既定のアプリケーションをインストールして構成する方法</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>ApplicationSourceRoot </strong> 、 <strong> IconSourceRoot </strong> 、および <strong> osdsourceroot 設定を使って、アプリまたは他のサーバーを使用してストリーミングを行うように app-v クライアントを構成 </strong> します。</p></td>
<td align="left"><p><a href="how-to-configure-the-client-for-application-package-retrieval.md" data-raw-source="[How to Configure the Client for Application Package Retrieval](how-to-configure-the-client-for-application-package-retrieval.md)">アプリケーション パッケージを取得するためにクライアントを構成する方法</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>オフラインで展開するための、順序付けされたアプリケーションパッケージの .msi ファイルバージョンの使い方について説明します。</p></td>
<td align="left"><p><a href="how-to-publish-a-virtual-application-on-the-client.md" data-raw-source="[How to Publish a Virtual Application on the Client](how-to-publish-a-virtual-application-on-the-client.md)">クライアントで仮想アプリケーションを公開する方法</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>省略App-v データベースの SQL Server データベースミラーリングを構成します。</p></td>
<td align="left"><p><a href="how-to-configure-microsoft-sql-server-mirroring-support-for-app-v.md" data-raw-source="[How to Configure Microsoft SQL Server Mirroring Support for App-V](how-to-configure-microsoft-sql-server-mirroring-support-for-app-v.md)">App-V 用に Microsoft SQL Server ミラーリングのサポートを構成する方法</a></p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[Application Virtualization の展開およびアップグレードのチェックリスト](application-virtualization-deployment-and-upgrade-checklists.md)

 

 





