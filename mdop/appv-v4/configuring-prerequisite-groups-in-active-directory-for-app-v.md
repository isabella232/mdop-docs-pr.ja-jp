---
title: App-V 用に Active Directory の前提条件グループを構成する
description: App-V 用に Active Directory の前提条件グループを構成する
author: dansimp
ms.assetid: 0010d534-46c0-44a3-b5c1-621b4d5e2c31
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aa1ab6393dee20203b715311d4e1dfdc4c22c679
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821864"
---
# App-V 用に Active Directory の前提条件グループを構成する


Microsoft Application Virtualization (App-v) Management サーバーをインストールする前に、Active Directory で次のオブジェクトを作成する必要があります。 App-v は Active Directory グループを使って、アプリケーションと管理機能へのアクセスを制御します。 これらのグループは、サーバーのインストールプロセスおよびアプリケーションの公開時に使用します。

## Active Directory でアプリケーションの仮想化に必要なグループを設定する


次の表は、App-v のインストールに必要な Active Directory グループを示しています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オブジェクト</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>組織単位 (OU)</p></td>
<td align="left"><p>App-v に必要な特定のグループに対して Active Directory で OU を作成します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 管理グループ</p></td>
<td align="left"><p>App-v 管理サーバーのインストール中に、管理コンソールへの管理アクセスを制御するために、App-v 管理者グループとして使用する Active Directory グループを選択する必要があります。 App-v 管理者のセキュリティグループを作成し、管理コンソールを使う必要があるユーザーごとにこのグループに追加します。 このグループは、App-v Management Server installer から直接作成することはできません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v Users グループ</p></td>
<td align="left"><p>App-v 機能にアクセスするすべてのユーザーアカウントは、一般的なプラットフォームアクセス用に1つのグループに関連付けられたプロバイダーポリシーのメンバーである必要があります。 既存のグループを使用するたとえば、すべてのユーザーが App-v へのアクセス権を持っている場合、または新しいグループを作成する場合は、ドメインユーザー。</p></td>
</tr>
<tr class="even">
<td align="left"><p>アプリケーショングループ</p></td>
<td align="left"><p>App-v は、個々のアプリケーションを Active Directory グループと共に使用する権利を関連付けます。 各アプリケーションの Active Directory グループを作成し、必要に応じてこれらのグループにユーザーを割り当てて、アプリケーションへのユーザーアクセスを制御します。</p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[Application Virtualization の展開要件](application-virtualization-deployment-requirements.md)

[App-V Management Server 用に Windows Server 2008 を構成する方法](how-to-configure-windows-server-2008-for-app-v-management-servers.md)

 

 





