---
title: Application Virtualization サーバー ベースのシナリオ概要
description: Application Virtualization サーバー ベースのシナリオ概要
author: dansimp
ms.assetid: 2d91392b-5085-4a5d-94f2-15eed1ed2928
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7b3ac3f10a5b7c7705e6d72c122d52be801a6d50
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822094"
---
# Application Virtualization サーバー ベースのシナリオ概要


Microsoft Application Virtualization 環境でサーバーベースの展開シナリオを使用する予定がある場合は、 *Application Virtualization Management server*と*Application virtualization ストリーミングサーバー*の違いについて理解しておくことが重要です。 このトピックでは、これらの違いについて説明します。パッケージ配信方法、伝送プロトコル、および展開を進めるために考慮する必要がある外部コンポーネントについても説明します。

## Application Virtualization Management Server


Application Virtualization Management Server は、パブリッシング機能とストリーミング機能の両方を実行します。 サーバーは、承認されたユーザーのために、アプリケーションアイコン、ショートカット、ファイルの種類の関連付けを App-v クライアントに公開します。 ユーザー要求が受信された場合、ユーザーは、RTSP または RTSPS プロトコルを使用する認証済みユーザーにデータを必要とするサーバーストリームを受け取ります。 このサーバーを使用するほとんどの構成では、1つ以上の管理サーバーが、構成およびパッケージ情報用の共通データストアを共有しています。

Application Virtualization Management サーバーは Active Directory グループを使って、ユーザーの承認を管理します。 Active Directory ドメインサービスに加えて、これらのサーバーにはデータベースとデータストアを管理するための SQL Server がインストールされています。 管理サーバーは、Microsoft 管理コンソールへのスナップインである Application Virtualization 管理コンソールを通じて制御されます。

アプリケーションの仮想化管理サーバーでは、アプリケーションがエンドユーザーのオンデマンドでストリーミングされるため、これらのサーバーは、信頼性の高い高帯域幅の Lan を備えたシステム構成に最適です。

## Application Virtualization ストリーミングサーバー


Application Virtualization Streaming Server では、管理サーバーによって提供されるのと同じストリーミングとパッケージのアップグレード機能が提供されますが、Active Directory または SQL Server の要件はありません。 ただし、ストリーミングサーバーには公開サービスがなく、ライセンス機能もメータリング機能もありません。 別個の App-v 管理サーバーの発行サービスは、app-v ストリーミングサーバーと組み合わせて使用されます。 App-v ストリーミングサーバーは、従来のサーバー構成のストリーミング機能を使用して、複数の場所でアプリケーションの仮想化を使う必要がある企業のニーズに対応していますが、すべての場所で App-v 管理サーバーをサポートするインフラストラクチャが含まれていない可能性があります。

Application Virtualization Streaming Server は、既存の電子ソフトウェア配布システム (ESD) がある環境でも使うことができます。 ESD を使ってストリーミングアプリケーションを管理します。 Application Virtualization Management Server とは異なり、ストリーミングサーバーでは、SQL や管理コンソールは使用されません。 これらのサーバーは、アクセス制御リスト (Acl) を使用してユーザーの承認を付与します。

## パッケージ配信方法


Application Virtualization サーバーを発行配信方法として使用する予定がある場合は、次のパッケージ配信方法がシナリオで採用されているかどうかを判断する必要があります。

-   *動的なパッケージの配信*

-   *ファイルパッケージ配信からのロード*

### 動的なパッケージの配信

動的なパッケージ配信中に、サーバー (Application Virtualization Management Server、Application Virtualization ストリーミングサーバー、または IIS サーバー) は、オンデマンド展開によって、仮想化されたアプリケーションをエンドユーザーに提供します。 サーバーは、ユーザーが最初にアプリケーションを起動しようとすると (オンデマンドで)、仮想化されたアプリケーションとパッケージをクライアントコンピューターに配信します。 サーバーは、アプリケーションを起動するために必要なブロックのみをストリームします (プライマリ機能ブロック)。 プライマリ機能ブロックがクライアントに配信されると、アプリケーションが実行されます。クライアントは、プライマリ機能ブロックに含まれていないアプリケーションの一部にアクセスする必要がない限り、完全なアプリケーション (段階的な展開) を受け取ることはありません。 この場合、クライアントは、シーケンス外の要求を実行し、セカンダリ機能ブロックはクライアントにストリーミングされます。 動的なパッケージ配信により、アプリケーションを迅速に起動できます。

### ファイルパッケージ配信からのロード

ファイルパッケージ配信からロードするために、サーバーは、ユーザーがアプリケーションを起動する前に、仮想化されたアプリケーションパッケージ全体をクライアントコンピューターに配信します。 このシナリオでは、仮想化されたアプリケーションは、動的配信モデルによって使用される動的な段階的な方法ではなく、完全なパッケージとして提供されます。

**注** 各配信方法では、仮想アプリケーションの最初の配信プロセスと仮想アプリケーションの更新プロセスは同じです。更新された仮想アプリケーションパッケージは、元のアプリケーションパッケージと置き換えられます。

 

次の表では、各パッケージ配信方法の長所と短所を比較しています。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">メソッド</th>
<th align="left">長所</th>
<th align="left">短所</th>
<th align="left">コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>動的なパッケージの配信</p></td>
<td align="left"><p>アプリケーションはオンデマンドで配信され、更新されます。</p>
<p>アプリは、起動時間を最適化するために段階的に配信および更新されます。</p>
<p>更新プログラムは、クライアントデスクトップに自動的に配信されます。</p></td>
<td align="left"><p>サーバーの要件により、エンタープライズトポロジのフットプリントが大きくなります。</p>
<p>アプリケーションのストリーミングは LAN 経由で行う必要があります。WAN 経由の展開シナリオ、またはサーバーとクライアント間の信頼性の低いまたは断続的な接続を使用している場合は、使用できない可能性があります。</p></td>
<td align="left"><p>ストリーミングインフラストラクチャが必要です。</p>
<p>Windows インストーラーは、アプリケーションの仮想化デスクトップクライアントソフトウェアをエンドユーザーのコンピューターに展開するために使用されます。</p>
<p>大企業は、アプリケーションの仮想化ストリーミングサーバーを配布ポイントとして使用する必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ファイルパッケージ配信からのロード</p></td>
<td align="left"><p>一般的なエンタープライズ管理プラクティスとの一貫性。</p>
<p>単体構成のシナリオをサポートします。</p>
<p>マイクロブランチオフィスの問題に対する解決策を提供します。</p></td>
<td align="left"><p>アプリケーションの配信と更新はオンデマンドではできません。</p>
<p>アプリケーションの配信と更新は段階的に行われません。動的配信と相対的にリソース使用量が増加します。</p></td>
<td align="left"><p>IT 組織は、多くの場合、アプリケーションライセンス、ユーザー認証、認証を管理する責任を負います。</p></td>
</tr>
</tbody>
</table>

 

## サーバー関連のプロトコルと外部コンポーネント


次の表に、Application Virtualization Server ベースのシナリオで使用できるサーバーの種類と、それに対応する伝送プロトコルと、特定のサーバー構成をサポートするために必要な外部コンポーネントを示します。 また、この表には、各サーバーの種類のレポートメカニズムとアクティブなアップグレードメカニズムも含まれています。 これらのシナリオではすべて Application Virtualization Management Server が使用されるため、システムに組み込まれている内部レポート機能を使用することができます。 アプリケーションの仮想化管理または Application Virtualization Streaming Server を使って、パッケージをクライアントに配信する場合、ユーザーがクライアントにログインすると、サーバー上のパッケージが自動的にアップグレードされます。IIS サーバーまたはファイルを使用してパッケージをクライアントに配信する場合、クライアント上のパッケージを手動でアップグレードする必要があります。

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
<th align="left">必要な外部コンポーネント</th>
<th align="left">レポート</th>
<th align="left">アクティブなアップグレード</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Application Virtualization Management Server</p></td>
<td align="left"><p>RTSP</p>
<p>RTSPS</p></td>
<td align="left"><p>HTTPS を使用する場合は、IIS サーバーを使用して、ICO ファイルと OSD ファイル、ファイアウォールをダウンロードして、サーバーをインターネットに公開することを防止します。</p></td>
<td align="left"><p>内部</p></td>
<td align="left"><p>サポートされています</p></td>
</tr>
<tr class="even">
<td align="left"><p>Application Virtualization ストリーミングサーバー</p></td>
<td align="left"><p>RTSP</p>
<p>RTSPS</p></td>
<td align="left"><p>メカニズムを使用して、管理サーバーとストリーミングサーバーの間でコンテンツを同期します。 HTTPS を使用する場合は、IIS サーバーを使用して、ICO ファイルと OSD ファイルをダウンロードし、ファイアウォールを使用してサーバーをインターネットに公開されないように保護します。</p></td>
<td align="left"><p>内部</p></td>
<td align="left"><p>サポートされています</p></td>
</tr>
<tr class="odd">
<td align="left"><p>IIS サーバー</p></td>
<td align="left"><p>HTTP</p>
<p>HTTPS</p></td>
<td align="left"><p>メカニズムを使用して、管理サーバーとストリーミングサーバーの間でコンテンツを同期します。 HTTP または HTTPS を使用している場合は、IIS サーバーを使用して、ICO ファイルと OSD ファイル、ファイアウォールをダウンロードして、サーバーをインターネットに公開することを防止します。</p></td>
<td align="left"><p>内部</p></td>
<td align="left"><p>サポートされていません</p></td>
</tr>
<tr class="even">
<td align="left"><p>ファイル</p></td>
<td align="left"><p>SMB</p></td>
<td align="left"><p>管理サーバーとストリーミングサーバー間でコンテンツを同期する方法が必要です。 ファイル共有またはストリーミング機能を使用しているクライアントコンピューターが必要です。</p></td>
<td align="left"><p>内部</p></td>
<td align="left"><p>サポートされていません</p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[電子ソフトウェア配布ベースのシナリオ](electronic-software-distribution-based-scenario.md)

[サーバー ベースの展開用にサーバーを構成する方法](how-to-configure-servers-for-server-based-deployment.md)

[サーバーおよびシステム コンポーネントをインストールする方法](how-to-install-the-servers-and-system-components.md)

 

 





