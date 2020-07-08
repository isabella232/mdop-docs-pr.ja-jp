---
title: APP-V インストール前のチェックリスト
description: APP-V インストール前のチェックリスト
author: dansimp
ms.assetid: 3af609b1-2c09-4edb-b083-b913b6d5e8c4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 70e71d3dea02daeadedb4cff78c58302ac743dda
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819787"
---
# APP-V インストール前のチェックリスト


次のチェックリストは、考慮する項目の概要と、Microsoft Application Virtualization (App-v) サーバーをインストールする前に実行する必要がある手順の概要を示すものです。

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
<td align="left"><p>使用しているコンピューティング環境が、App-v に必要なサポートされている構成を満たしていることを確認します。</p></td>
<td align="left"><p><a href="application-virtualization-deployment-requirements.md" data-raw-source="[Application Virtualization Deployment Requirements](application-virtualization-deployment-requirements.md)">Application Virtualization の展開要件</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>必要な Active Directory グループとアカウントを構成します。</p></td>
<td align="left"><p><a href="configuring-prerequisite-groups-in-active-directory-for-app-v.md" data-raw-source="[Configuring Prerequisite Groups in Active Directory for App-V](configuring-prerequisite-groups-in-active-directory-for-app-v.md)">App-V 用に Active Directory の前提条件グループを構成する</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>IIS を実行しているサーバーのインターネットインフォメーションサービス (IIS) 設定を構成します。</p></td>
<td align="left"><p><a href="how-to-configure-windows-server-2008-for-app-v-management-servers.md" data-raw-source="[How to Configure Windows Server 2008 for App-V Management Servers](how-to-configure-windows-server-2008-for-app-v-management-servers.md)">App-V Management Server 用に Windows Server 2008 を構成する方法</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>IIS を実行しているサーバーが委任に対して信頼されるように構成します。</p>
<div class="alert">
<strong>注</strong><br/><p>これは、分散システムアーキテクチャを使用して App-v Management Server をインストールする場合にのみ必要です。つまり、App-v 管理コンソール、管理 Web サービス、およびデータベースをさまざまなコンピューターにインストールします。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="how-to-configure-the-server-to-be-trusted-for-delegation.md" data-raw-source="[How to Configure the Server to be Trusted for Delegation](how-to-configure-the-server-to-be-trusted-for-delegation.md)">サーバーを委任に対して信頼されるように構成する方法</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft SQL Server 2008 をインストールします。</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=181924" data-raw-source="[Install SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=181924)">SQL Server 2008 </a> ( <a href="https://go.microsoft.com/fwlink/?LinkId=181924" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=181924"> https://go.microsoft.com/fwlink/?LinkId=181924 </a> ) をインストールします。</p></td>
</tr>
</tbody>
</table>



## 関連トピック


[Application Virtualization の展開およびアップグレードのチェックリスト](application-virtualization-deployment-and-upgrade-checklists.md)

[App-V インストールのチェックリスト](app-v-installation-checklist.md)









