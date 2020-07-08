---
title: App-V アップグレードのチェックリスト
description: App-V アップグレードのチェックリスト
author: dansimp
ms.assetid: 64e317d2-d260-4b67-8a49-ba9ac513087a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ad856ce3067c327f3e604f9269ee384a66a1675a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819737"
---
# App-V アップグレードのチェックリスト


Microsoft Application Virtualization (App-v) 4.5 以降のバージョンにアップグレードする前に、app-v 4.1 より前のバージョンを App-v 4.1 にアップグレードする必要があります。 まずクライアントをアップグレードし、次にサーバーコンポーネントをアップグレードすることを計画する必要があります。 App-v 4.5 にアップグレードされた app-v クライアントは、まだアップグレードされていない App-v サーバーで引き続き動作します。 以前のバージョンのクライアントは、App-v 4.5 にアップグレードされたサーバーではサポートされません。

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
<td align="left"><p>App-v クライアントをアップグレードします。</p></td>
<td align="left"><p><a href="how-to-upgrade-the-application-virtualization-client.md" data-raw-source="[How to Upgrade the Application Virtualization Client](how-to-upgrade-the-application-virtualization-client.md)">Application Virtualization Client をアップグレードする方法</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v のサーバーとデータベースをアップグレードします。</p>
<div class="alert">
<strong>重要</strong><br/><p>App-v データベースへの複数のサーバー共有アクセス権を持っている場合は、データベースのアップグレード中に、これらのすべてのサーバーをオフラインにする必要があります。 データベースのアップグレードについては、通常のビジネス慣行に従う必要がありますが、最初にテストサーバーでデータベースのバックアップコピーを使用してデータベースのアップグレードをテストすることをお勧めします。 次に、最初のアップグレード用にいずれかのサーバーを選択する必要があります。これにより、データベーススキーマがアップグレードされます。 運用データベースが正常にアップグレードされた後、他のサーバー上の App-v ソフトウェアをアップグレードできます。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="how-to-upgrade-the-servers-and-system-components.md" data-raw-source="[How to Upgrade the Servers and System Components](how-to-upgrade-the-servers-and-system-components.md)">サーバーおよびシステム コンポーネントをアップグレードする方法</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 管理 Web サービスをアップグレードします。</p>
<p>この手順は、管理 Web サービスが別のサーバー上にある場合にのみ適用されます。そのため、管理 web サービスをアップグレードするには、サーバーインストーラープログラムを別のサーバー上で実行する必要があります。 それ以外の場合は、前のサーバーアップグレード手順によって、自動的に管理 Web サービスがアップグレードされます。</p></td>
<td align="left"><p><a href="how-to-upgrade-the-servers-and-system-components.md" data-raw-source="[How to Upgrade the Servers and System Components](how-to-upgrade-the-servers-and-system-components.md)">サーバーおよびシステム コンポーネントをアップグレードする方法</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 管理コンソールをアップグレードします。</p>
<p>この手順は、管理コンソールが別のコンピューターにある場合にのみ適用されます。そのため、コンソールをアップグレードするには、別のコンピューターでサーバーインストーラープログラムを実行する必要があります。 それ以外の場合は、前のサーバーアップグレード手順によって管理コンソールがアップグレードされます。</p></td>
<td align="left"><p><a href="how-to-upgrade-the-servers-and-system-components.md" data-raw-source="[How to Upgrade the Servers and System Components](how-to-upgrade-the-servers-and-system-components.md)">サーバーおよびシステム コンポーネントをアップグレードする方法</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v Sequencer をアップグレードします。</p></td>
<td align="left"><p><a href="how-to-upgrade-the-application-virtualization-sequencer.md" data-raw-source="[How to Upgrade the Application Virtualization Sequencer](how-to-upgrade-the-application-virtualization-sequencer.md)">Application Virtualization Sequencer をアップグレードする方法</a></p></td>
</tr>
</tbody>
</table>



## アップグレードに関するその他の考慮事項


-   バージョン4.2 でシーケンスされた仮想アプリケーションパッケージは、バージョン4.5 で使用するために再度順序付けする必要はありません。 ただし、既定のアクセス制御リスト (Acl) を適用したり、Windows インストーラーファイルを生成したりする場合は、仮想パッケージを Microsoft Application Virtualization 4.5 形式にアップグレードすることを検討してください。 これは単純なプロセスであり、既存の仮想アプリケーションパッケージを開いて、App-v 4.5 Sequencer と共に保存するだけで済みます。 これは、アプリの VSequencer コマンドラインインターフェイスを使って自動化できます。 詳細については、「 [App-v を使用して仮想アプリケーションを作成またはアップグレードする方法](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)」を参照してください。

-   4.5 Sequencer の1つの機能は、Windows Installer (.msi) ファイルを、Microsoft Endpoint Configuration Manager などの電子ソフトウェア配布 (ESD) システムとの制御ポイントとして作成できる機能です。 アプリの仮想化のために MSI ツールを使って作成された、Application Virtualization 用の MSI ツールで作成された、アプリの仮想 4.2 4.1 化のための MSI ツールを使って作成された以前の Windows インストーラーファイルは、アプリの hyper-v 4.5 に4.5 インストールされることはありませんが、その後も引き続き機能します。 ただし、アプリ-V 4.5 Sequencer でアップグレードしない限り、削除またはアップグレードすることはできません。 4.5 より前の元の App-v パッケージは、App-v 4.5 Sequencer で開いて、Windows Installer ファイルとして保存する必要があります。

    **注**  
    App-v 4.2 クライアントが既に app-v 4.5 にアップグレードされている場合は、回避策をスクリプト化して、バージョンの4.5 クライアント上のバージョン4.2 パッケージを保存し、それらを管理することができます。 このスクリプトでは、msvcp71.dll と msvcr71.dll の2つのファイルを App-v のインストールフォルダーにコピーし、レジストリキーの下に次のレジストリキーの値を設定する必要があります。 \ [HKEY \ _LOCAL \ _MACHINE ¥ [HKEY \ \]

    "ClientVersion" = "4.2.1.20"

    "GlobalDataDirectory" = "C:\\\\Documents and Settings\\\\All Users\\\\Documents\\\\" (グローバルに書き込み可能な場所)



-   App-v 4.5 Sequencer によって生成された Windows Installer ファイルは、App-v 4.6 クライアントで実行しようとすると、"このパッケージは Microsoft Application Virtualization Client 4.5 以降を必要とします" というエラーメッセージを表示します。 App-v 4.5 SP1 Sequencer または App-v 4.6 Sequencer のいずれかを使用して、古いパッケージを開き、パッケージの新しい .msi ファイルを生成します。

-   作成および保存されたバージョン4.2 のレポートは、サーバーがバージョン4.5 にアップグレードされると上書きされます。 これらのレポートを保持する必要がある場合は、サーバー上の SoftGrid 管理コンソールフォルダーにある SftMMC ファイルのバックアップコピーを保存し、そのコピーを使用してアップグレード中にインストールされた新しい SftMMC を置き換えます。

-   以前のバージョンからのアップグレードの詳細については、「 [Microsoft Application Virtualization 4.5 へのアップグレード](https://go.microsoft.com/fwlink/?LinkId=120358)に関する FAQ (」を参照してください https://go.microsoft.com/fwlink/?LinkId=120358) 。

## <a href="" id="app-v-4-6-client-package-support-"></a>App-v 4.6 クライアントパッケージのサポート


以前のバージョンの App-v で作成されたパッケージを、app-v 4.6 クライアントに展開することができます。 ただし、適切なオペレーティングシステムとチップアーキテクチャの情報が含まれるように、関連する .osd ファイルを変更する必要があります。 次の値を使用できます。

<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">OS 値</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>&lt;OS 値 = "Win2003TS"/&gt;</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;OS 値 = "Win2003TS64"/&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>&lt;OS 値 = "Win2008TS"/&gt;</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;OS 値 = "Win2008TS64"/&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>&lt;OS 値 = "Win2008R2TS64"/&gt;</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;OS 値 = "Win7"/&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>&lt;OS 値 = "Win764"/&gt;</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;OS 値 = "WinVista"/&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>&lt;OS 値 = "WinVista64"/&gt;</p></td>
</tr>
<tr class="even">
<td align="left"><p>&lt;OS 値 = "WinXP"/&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>&lt;OS 値 = "WinXP64"/&gt;</p></td>
</tr>
</tbody>
</table>



新しく作成された32ビットパッケージを実行するには、App-v 4.6 Sequencer がインストールされた32ビットオペレーティングシステムを実行しているコンピューターでアプリケーションをシーケンスする必要があります。 アプリケーションをシーケンスした後、Sequencer コンソールで [**展開**] タブをクリックし、必要に応じて、適切なオペレーティングシステムとチップアーキテクチャを指定します。

**重要**  
64ビットオペレーティングシステムを実行しているコンピューターでシーケンスされたアプリケーションは、64ビットオペレーティングシステムを実行しているコンピューターに展開する必要があります。 App-v 4.6 Sequencer を使用して作成された新しい32ビットパッケージは、App-v 4.5 クライアントを実行しているコンピューターでは実行されません。



新しい64ビットパッケージを App-v 4.6 クライアントで実行するには、App-v 4.6 Sequencer を実行していて、64ビットオペレーティングシステムを実行しているコンピューターでアプリケーションをシーケンスする必要があります。 アプリケーションをシーケンスした後、Sequencer コンソールで [**展開**] タブをクリックし、必要に応じて、適切なオペレーティングシステムとチップアーキテクチャを指定します。

次の表は、さまざまなバージョンの sequencer を使用して作成されたパッケージを実行するクライアントバージョンを示しています。

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
<th align="left"></th>
<th align="left">App-v 4.2 Sequencer を使用したシーケンス</th>
<th align="left">App-v 4.5 Sequencer を使用したシーケンス</th>
<th align="left">32ビット版のアプリを使ったシーケンス (V 4.6 Sequencer)</th>
<th align="left">64ビット版のアプリを使ったシーケンス (V 4.6 Sequencer)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>4.2 クライアント</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>×</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>なし</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.5 クライアント¹</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>×</p></td>
<td align="left"><p>なし</p></td>
</tr>
<tr class="odd">
<td align="left"><p>4.6 クライアント (32 ビット)</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>×</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.6 クライアント (64 ビット)</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>あり</p></td>
</tr>
</tbody>
</table>



¹は、app-v 4.5 クライアントのすべてのバージョン (アプリ-V 4.5、App-v 4.5 CU1、App-v 4.5 SP1 など) に適用されます。









