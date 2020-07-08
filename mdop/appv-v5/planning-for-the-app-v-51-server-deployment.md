---
title: App-V 5.1 Server の展開計画
description: App-V 5.1 Server の展開計画
author: dansimp
ms.assetid: eedd97c9-bee0-4749-9d1e-ab9528fba398
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 31e3a116eb511356b061e6ccb18c7e25c060a66e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813435"
---
# App-V 5.1 Server の展開計画


Microsoft Application Virtualization (App-v) 5.1 サーバーインフラストラクチャは、企業の要件に基づいて1つまたは複数のサーバーコンピューターにインストールできる専門的な機能のセットで構成されています。

## App-v 5.1 Server の展開を計画する


App-v 5.1 サーバーは、次の機能で構成されています。

-   管理サーバー– App-v 5.1 インフラストラクチャの全体的な管理機能を提供します。

-   管理データベース– App-v 5.1 管理のデータベース展開が容易になります。

-   公開サーバー–仮想アプリケーションのホスティング機能とストリーミング機能を提供します。

-   レポートサーバー– App-v 5.1 reporting services を提供します。

-   レポートデータベース– App-v 5.1 レポートのデータベース展開を容易にします。

次の一覧は、App-v 5.1 サーバーインフラストラクチャをインストールするための推奨される方法を示しています。

-   App-v 5.1 サーバーをインストールします。 詳細については、「 [app-v 5.1 サーバーを展開する方法](how-to-deploy-the-app-v-51-server.md)」を参照してください。

-   データベース、レポート、管理の各機能を別々のコンピューターにインストールします。 詳細については、「[管理データベースとレポートデータベースを管理サービスおよびレポートサービスから別のコンピューターにインストールする方法](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services51.md)」を参照してください。

-   電子ソフトウェア配布 (ESD) を使用します。 詳細については、「[電子ソフトウェアの配布を使用して app-v 5.1 パッケージを展開する方法](how-to-deploy-app-v-51-packages-using-electronic-software-distribution.md)」を参照してください。

-   すべてのサーバー機能を1台のコンピューターにインストールします。

## <a href="" id="---------app-v-5-1-server-interaction"></a> App-v 5.1 Server の対話式操作


このセクションでは、さまざまな App-v 5.1 サーバーの役割が互いにどのように連携するかについて説明します。

App-v 5.1 Management Server には、パッケージのリポジトリと割り当てられた構成が含まれています。 管理サーバーに登録されている発行サーバーの場合、関連付けられたメタデータは、App-v 5.1 クライアントを実行しているコンピューターから発行された更新要求を受信するときに使用する発行サーバーに提供されます。 1つの管理サーバーによって管理される app-v 5.1 発行サーバーは、さまざまなクライアントでサービスを提供でき、異なる web サイト名とポートバインドを持つことができます。 さらに、同じ管理サーバーによって管理されるすべての発行サーバーは、互いに複製されます。

**注** Management サーバーでは、ロードバランシングは実行されません。 関連付けられているメタデータは、クライアント要求の処理時に使用するために発行サーバーに渡されます。

 

## サーバー関連のプロトコルと外部機能


次の例は、App-v 5.1 サーバーで使用されるサーバー関連のプロトコルに関する情報を示しています。 この表には、各サーバーの種類のレポートメカニズムも含まれています。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">サーバーの種類</th>
<th align="left">プロトコル</th>
<th align="left">必要な外部機能</th>
<th align="left">レポート</th>
<th align="left"></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>IIS サーバー</p></td>
<td align="left"><p>HTTP</p>
<p>HTTPS</p></td>
<td align="left"><p>このサーバープロトコルの組み合わせでは、管理サーバーとストリーミングサーバー間でコンテンツを同期するメカニズムが必要になります。 HTTP または HTTPS を使用する場合は、IIS サーバーとファイアウォールを使用して、サーバーが公開されないようにインターネットを保護します。</p></td>
<td align="left"><p>内部</p></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><p>ファイル</p></td>
<td align="left"><p>SMB</p></td>
<td align="left"><p>このサーバープロトコルの組み合わせでは、管理サーバーとストリーミングサーバーの間でコンテンツを同期することがサポートされている必要があります。 クライアントコンピューターでファイル共有またはストリーミング機能を使用します。</p></td>
<td align="left"><p>内部</p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

 






## 関連トピック


[App-V の展開計画](planning-to-deploy-app-v51.md)

[App-V 5.1 Server の展開](deploying-the-app-v-51-server.md)

 

 





