---
title: App-V 5.1 をお使いになる前に
description: App-V 5.1 をお使いになる前に
author: dansimp
ms.assetid: 49a20e1f-0566-4e53-a417-1521393fc974
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ff10f12bc672a24f2837f50bfb1f0033ede3e46f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814547"
---
# App-V 5.1 をお使いになる前に


Microsoft Application Virtualization (App-v) 5.1 を使用すると、管理者は、必要に応じてリアルタイムでサービスとしてアプリケーションを展開、更新、およびサポートできます。 個々のアプリケーションは、ローカルにインストールされた製品から一元的に管理されたサービスに変換され、コンピューターの事前構成やオペレーティングシステムの設定の変更を必要とせずに、どこでも利用できます。

App-v は、次の要素で構成されています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">要素</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v Management Server</p></td>
<td align="left"><ul>
<li><p>App-v インフラストラクチャを管理するための1つの場所を提供します。これにより、仮想アプリケーションは、App-v デスクトップクライアントとリモートデスクトップサービス (旧ターミナルサービス) クライアントの両方に配信されます。</p></li>
<li><p>データストアには Microsoft SQL Server®を使います。ここでは、1つ以上の App-v 管理サーバーが1つの SQL Server データストアを共有できます。</p></li>
<li><p>要求を認証し、セキュリティ、メータリング、監視、データ収集を提供します。 サーバーは Active Directory とサポートツールを使って、ユーザーとアプリケーションを管理します。</p></li>
<li><p>任意のコンピューターから App-v インフラストラクチャを構成できる管理サイトがあります。 アプリケーションの追加と削除、ショートカットの操作、ユーザーとグループへのアクセス許可の割り当て、接続グループの作成を行うことができます。</p></li>
<li><p>App-v Web 管理コンソールと SQL Server データストアの間の通信を有効にします。 これらのコンポーネントは、必要なシステムアーキテクチャに応じて、単一のサーバーコンピューターまたは1つ以上の別のコンピューターにインストールできます。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 発行サーバー</p></td>
<td align="left"><ul>
<li><p>特定のユーザーに対応するアプリケーションを指定して、App-v クライアントを提供します。</p></li>
<li><p>ストリーミング用の仮想アプリケーションパッケージをホストします。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v デスクトップクライアント</p></td>
<td align="left"><ul>
<li><p>仮想アプリケーションを取得します</p></li>
<li><p>クライアントのアプリケーションを公開します</p></li>
<li><p>Windows エンドポイントで実行時に仮想環境を自動的に設定および管理します。</p></li>
<li><p>ユーザー固有の仮想アプリケーション設定 (レジストリやファイルの変更など) を各ユーザー&#39;s プロファイルに保存します。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>App-v リモートデスクトップサービス (RDS) クライアント</p></td>
<td align="left"><p>リモートデスクトップセッションホストサーバーで、共有デスクトップセッションのアプリ V デスクトップクライアントの機能を使用できるようにします。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v Sequencer</p></td>
<td align="left"><ul>
<li><p>は、従来のアプリケーションを仮想アプリケーションに変換するために使用するウィザードベースのツールです。</p></li>
<li><p>"パッケージ" というアプリケーションを生成します。これは次の要素で構成されます。</p>
<ol>
<li><p>シーケンスアプリケーション (APPV) ファイル</p></li>
<li><p>スタンドアロン操作用に構成されたクライアントに展開できる Windows インストーラーファイル (MSI)</p></li>
<li><p>Report.XML、PackageName_DeploymentConfig.XML、PackageName_UserConfig.XML などのいくつかの XML ファイル。 UserConfig と DeploymentConfig の XML ファイルを使って、パッケージの既定の動作に対するカスタムの変更を構成します。</p></li>
</ol></li>
</ul></td>
</tr>
</tbody>
</table>

 

これらの要素の詳細については、「 [app-v 5.1 の高レベルアーキテクチャ](high-level-architecture-for-app-v-51.md)」を参照してください。

この製品を初めて使用する場合は、このドキュメントをよく読むことをお勧めします。 運用環境に展開する前に、テストネットワーク環境で展開計画を検証することをお勧めします。 関連するテクノロジのトレーニングの受講もご検討ください。 Microsoft のトレーニングの機会の詳細については、「Microsoft トレーニングの概要」を参照してください <https://go.microsoft.com/fwlink/p/?LinkId=80347> 。

**注** この管理者ガイドのダウンロード可能なバージョンは利用できません。 ただし、TechNet ライブラリの特別モードでは、記事の選択、コレクションへのグループ化、またはのファイルへのエクスポートを行うことができ <https://go.microsoft.com/fwlink/?LinkId=272491> https://go.microsoft.com/fwlink/?LinkId=272491) ます。

 

このセクションでは、展開計画を開始する前に、製品についての基本的な理解を得るために5.1、app-v 5.1 に関する詳細情報を提供しています。

## App-v 5.1 の概要


-   [App-V 5.1 について](about-app-v-51.md)

    App-v 5.1 の概要と、組織での使用方法について説明します。

-   [App-V 5.1 の評価](evaluating-app-v-51.md)

    組織で使用するために、どのように App-v 5.1 を最適に評価できるかについて説明します。

-   [App-V 5.1 のアーキテクチャの概要](high-level-architecture-for-app-v-51.md)

    App-v 5.1 の機能と連携のしくみについて説明します。

-   [App-V 5.1 のアクセシビリティ](accessibility-for-app-v-51.md)

    障碍のある方がこの製品とそれに対応するドキュメントのアクセシビリティを高めるための機能とサービスについて説明します。

## <a href="" id="other-resources-for-this-product-"></a>この製品のその他のリソース


-   [Microsoft Application Virtualization 5.1 管理者ガイド](microsoft-application-virtualization-51-administrators-guide.md)

-   [App-V 5.1 の計画](planning-for-app-v-51.md)

-   [APP-V 5.1 の展開](deploying-app-v-51.md)

-   [APP-V 5.1 の操作](operations-for-app-v-51.md)

-   [App-V 5.1 のトラブルシューティング](troubleshooting-app-v-51.md)

-   [App-V 5.1 テクニカル リファレンス](technical-reference-for-app-v-51.md)






 

 





