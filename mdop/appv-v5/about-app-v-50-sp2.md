---
title: App-V 5.0 SP2 について
description: App-V 5.0 SP2 について
author: dansimp
ms.assetid: 16ca8452-cef2-464e-b4b5-c10d4630fa6a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9a476f3bf273717b5a85a4244c5796f893b0c617
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814987"
---
# App-V 5.0 SP2 について


App-v 5.0 SP2 は、強化された統合プラットフォーム、より柔軟な仮想化、仮想化されたアプリケーションのための強力な管理機能を提供します。 詳細については、「 [app-v 5.0 の概要](https://go.microsoft.com/fwlink/p/?LinkId=325265)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=325265) 。

## 標準アプリ-V 5.0 SP2 の機能の変更点


以下のセクションでは、App-v 5.0 SP2 の標準機能の変更点について説明します。

### <a href="" id="bkmk-sp2-supported-cfg"></a>Windows Server 2012 R2 および Windows 8.1 のサポート

App-v 5.0 には Windows Server 2012 R2 および Windows 8.1 のサポートが含まれています。

### <a href="" id="-------------app-v-5-0-sp2-now-supports-folder-redirection-for-the-user-s-roaming-appdata-directory"></a> App-v 5.0 SP2 では、ユーザーのローミングの AppData ディレクトリのフォルダーリダイレクションがサポートされるようになりました

App-v 5.0 SP2 はローミング AppData (% AppData%) をサポートしていますフォルダリダイレクション。 詳細については、「 [app-v でフォルダーリダイレクションを使用するための計画](planning-to-use-folder-redirection-with-app-v.md)」を参照してください。

### <a href="" id="bkmk-pkg-upgr-pendg-tasks"></a>パッケージのアップグレードの改善と保留中のタスク

App-v 5.0 SP2 では、新しいバージョンのパッケージまたは接続グループが公開されている場合、実行中の仮想アプリケーションを閉じるように求められなくなりました。 関連タスクを実行しようとしたときに、パッケージまたは接続グループが使用されている場合は、オブジェクトが使用中であることを示すメッセージが表示され、その操作は後で実行されます。

保留状態になっているタスクは、次の規則に従って実行されます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスクの種類</th>
<th align="left">該当するルール</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ユーザーベースのタスク (パッケージをユーザーに公開するなど)</p></td>
<td align="left"><p>保留中のタスクは、ユーザーがログオフしてから再びログインした後に実行されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>グローバルに基づくタスク (例: 接続グループをグローバルに有効にする)</p></td>
<td align="left"><p>保留中のタスクは、コンピューターをシャットダウンしてから再起動したときに実行されます。</p></td>
</tr>
</tbody>
</table>

 

タスクが保留状態になっている場合、App-v クライアントは、次のように、保留中のタスクのレジストリキーも生成します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ユーザーベースまたはグローバルベースのタスク</th>
<th align="left">レジストリキーが生成される場所</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ユーザーベースのタスク</p></td>
<td align="left"><p>KEY_CURRENT_USER \Software\Microsoft\AppV\Client\PendingTasks</p></td>
</tr>
<tr class="even">
<td align="left"><p>グローバルに基づくタスク</p></td>
<td align="left"><p>HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\PendingTasks</p></td>
</tr>
</tbody>
</table>

 

### App-v 5.0 を使用した Microsoft Office 2013 および Microsoft Office 2010 の仮想化

App-v 5.0 でサポートされている Microsoft Office シナリオの詳細については、次のリンクを参照してください。

[Application Virtualization (APP-V) 5.0 向けの Microsoft Office 2013 の仮想化](../solutions/virtualizing-microsoft-office-2013-for-application-virtualization--app-v--50-solutions.md)

**注** このドキュメントでは、Microsoft Office 2013 App-v 5.0 パッケージの作成に重点を置いて説明します。 また、Microsoft Office 2010 のシナリオについては、「App-v 5.0」もご覧ください。

 

### <a href="" id="-------------app-v-5-0-client-management-user-interface-application"></a> App-v 5.0 クライアント管理ユーザーインターフェイスアプリケーション

以前のバージョンの App-v 5.0 では、クライアント管理ユーザーインターフェイス (UI) は、App-v 5.0 クライアントインストールを使って提供されていました。 App-v 5.0 SP2 の場合、これはサポートされなくなりました。 管理者は、(サポートされているすべての App-v 展開構成を使用して) 仮想アプリケーションとして、またはインストール済みアプリケーションとして、App-v 5.0 クライアント UI を展開するオプションを使用できるようになりました。

詳細については、「 [Microsoft Application Virtualization 5.0 クライアント UI アプリケーション](https://go.microsoft.com/fwlink/p/?LinkId=386345)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=386345) 。

### Side-by-side (SxS) アセンブリの自動パッケージと展開

App-v 5.0 SP2 は、side-by-side (SxS) アセンブリと、App-v 5.0 SP2 クライアントを実行しているコンピューター上での展開を自動的に検出するようになりました。 SxS アセンブリは、主に VC + + 実行時の依存関係または MSXML で構成されています。 以前のバージョンの App-v では、VC ランタイムとの依存関係を持つ仮想アプリケーションでは、これらの依存関係が、App-v 5.0 SP2 クライアントを実行しているコンピューター上でローカルである必要がありました。

次の機能がサポートされるようになりました。

-   アプリ-V 5.0 sequencer は、sequencer を実行しているコンピューターに VC ランタイムが既にインストールされているかどうかに関係なく、パッケージ内の SxS アセンブリを自動的にキャプチャします。

-   App-v 5.0 クライアントは、発行時に必要に応じてクライアントを実行しているコンピューターに、必要な SxS アセンブリを自動的にインストールします。

-   アプリ-V 5.0 sequencer は、sequencer のレポートメカニズムを使って、VC ランタイム依存関係を報告します。

-   App-v 5.0 sequencer では、sequencer を実行しているコンピューターで依存関係が既に利用可能であることを示すイベントで、VC ランタイム依存関係を除外することができるようになりました。

### 公開の更新の改善

App-v 5.0 は、特定のユーザーの一連のアプリケーションを更新する全体的なエクスペリエンスを向上させるために、いくつかの機能をサポートしています。

次の一覧は、公開更新の拡張機能を示しています。

次の一覧には、新しい公開の更新を有効にする方法についての詳細情報が記載されています。

-   **EnablePublishingRefreshUI** -App-v 5.0 クライアントを実行しているコンピューターの公開更新進行状況バーを有効にします。

-   **Hideui** -手動同期中に発行更新の進行状況バーを非表示にします。

### 新しいクライアント構成の設定

次の新しいクライアント構成設定は、App-v 5.0 SP2 で利用できます。

**Enabledynamicvirtualization** -サポートされているシェルの拡張機能、ブラウザーヘルパーオブジェクト、アクティブな X コントロールを仮想アプリケーションで仮想化して実行できるようにします。

詳細については、「[クライアント構成の設定につい](about-client-configuration-settings.md)て」を参照してください。

### <a href="" id="-------------app-v-5-0-shell-extensions"></a> App-v 5.0 シェル拡張機能

App-v 5.0 SP2 では、シェルの拡張機能がサポートされるようになりました。

詳細については、「app-v 5.0 で仮想化された[アプリケーションを作成および管理](creating-and-managing-app-v-50-virtualized-applications.md)する」の「APP-V **5.0 sp2 シェル extension のサポート**」セクションを参照してください。

## <a href="" id="---------app-v-5-0-documentation-updates"></a> App-v 5.0 ドキュメントの更新


App-v 5.0 SP2 には、次のシナリオの更新されたドキュメントが用意されています。

-   [旧バージョンからの移行](migrating-from-a-previous-version-app-v-50.md)

-   [App-V 5.0 について](about-app-v-50.md)

-   [App-v 5.0 レポートについて](about-app-v-50-reporting.md)(よく寄せられる質問セクション)

## MDOP 技術の入手方法


App-v 5.0 は、Microsoft デスクトップ最適化パック (MDOP) に含まれています。 MDOP は、Microsoft ソフトウェアアシュアランスの一部です。 Microsoft ソフトウェアアシュアランスの詳細と MDOP の入手方法については、「 [mdop の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」を参照してください https://go.microsoft.com/fwlink/?LinkId=322049) 。






## 関連トピック


[App-V 5.0 SP2 リリース ノート](release-notes-for-app-v-50-sp2.md)

 

 





