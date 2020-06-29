---
title: 以前のバージョンからの移行計画
description: 以前のバージョンからの移行計画
author: dansimp
ms.assetid: 62967bf1-542f-41b0-838f-c62f3430ac73
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9b239e09da06270b30b401151cf12e817e2cf8d4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815927"
---
# 以前のバージョンからの移行計画


Microsoft Application Virtualization 4.5 以降のバージョンにアップグレードする前に、4.1 より前のバージョンをバージョン4.1 にアップグレードする必要があります。 まずクライアントをアップグレードし、次にサーバーコンポーネントをアップグレードすることを計画する必要があります。 4.5 にアップグレードされているクライアントは、まだアップグレードされていないアプリケーション仮想化サーバーで動作し続けます。 以前のバージョンのクライアントは、4.5 にアップグレードされたサーバーではサポートされません。 システムコンポーネントのアップグレードの詳細については、「 [Application Virtualization の展開とアップグレードに関する考慮事項](application-virtualization-deployment-and-upgrade-considerations.md)」を参照してください。

移行を成功させるためには、Application Virtualization システムコンポーネントを次の順序でアップグレードする必要があります。

1.  **Microsoft Application Virtualization クライアント。** 詳細なアップグレード手順については、「 [Application Virtualization クライアントをアップグレードする方法](how-to-upgrade-the-application-virtualization-client.md)」を参照してください。

2.  **Microsoft Application Virtualization サーバーとデータベース。** 詳細なアップグレード手順については、「[サーバーとシステムコンポーネントをアップグレードする方法](how-to-upgrade-the-servers-and-system-components.md)」を参照してください。

    **注** Application Virtualization データベースへのサーバー共有アクセス権が複数ある場合は、データベースのアップグレード中に、それらのすべてのサーバーをオフラインにする必要があります。 データベースのアップグレードについては、通常のビジネス慣行に従う必要がありますが、最初にテストサーバーでデータベースのバックアップコピーを使用してデータベースのアップグレードをテストすることをお勧めします。 次に、最初のアップグレード用にいずれかのサーバーを選択する必要があります。これにより、データベーススキーマがアップグレードされます。 運用データベースのアップグレードが正常に完了したら、他のサーバーをアップグレードできます。

     

3.  **Microsoft Application Virtualization Management Web サービス。** この手順は、管理 Web サービスが別のサーバー上にある場合にのみ適用されます。この場合、Web サービスをアップグレードするためにサーバーインストーラープログラムを別のサーバー上で実行する必要があります。 それ以外の場合は、前のサーバーアップグレード手順によって、自動的に管理 Web サービスがアップグレードされます。

4.  **Microsoft Application Virtualization 管理コンソール。** この手順は、管理コンソールが別のコンピューターにある場合にのみ適用されます。そのため、コンソールをアップグレードするには、別のコンピューターでサーバーインストーラープログラムを実行する必要があります。 それ以外の場合は、前のサーバーアップグレード手順によって管理コンソールがアップグレードされます。

5.  **Microsoft Application Virtualization Sequencer。** 詳細な手順については、「 [Application Virtualization Sequencer をインストールする方法](how-to-install-the-application-virtualization-sequencer.md)」を参照してください。 バージョン4.2 でシーケンスされた仮想アプリケーションパッケージは、バージョン4.5 での使用のために順序を変更する必要はありません。 ただし、既定のアクセス制御リスト (Acl) を適用したり、Windows インストーラーファイルを生成したりする場合は、仮想パッケージを Microsoft Application Virtualization 4.5 形式にアップグレードすることを検討してください。 これは単純なプロセスであり、既存の仮想アプリケーションパッケージを開いて、4.5 Sequencer として保存するだけで済みます。 これは、Application Virtualization Sequencer コマンドラインインターフェイスを使用して自動化できます。

## <a href="" id="app-v-4-6-client-package-support-"></a>App-v 4.6 クライアントパッケージのサポート


以前のバージョンの App-v で作成されたパッケージを、app-v 4.6 クライアントに展開することができます。 ただし、適切なオペレーティングシステムとチップアーキテクチャの情報が含まれるように、関連する **.osd**ファイルを変更する必要があります。 次の値を使用します。

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

 

新しく作成された32ビットパッケージを実行するには、アプリを実行するコンピューターで、32ビットのオペレーティングシステムを実行しているコンピューター (app-v 4.6 Sequencer がインストールされているコンピューター) でアプリケーションをシーケンスする必要があります。 アプリケーションをシーケンスした後、Sequencer コンソールで [**展開**] タブを選択し、必要に応じて、適切なオペレーティングシステムとチップアーキテクチャを指定します。

**重要** 64ビットオペレーティングシステムを実行しているコンピューターでシーケンスされたアプリケーションは、64ビットオペレーティングシステムを実行しているコンピューターに展開する必要があります。 App-v 4.6 Sequencer を使用して作成された新しい32ビットパッケージは、app-v 4.5 クライアントを実行しているコンピューターでは実行されません。

 

新しい64ビットパッケージを App-v 4.6 クライアントで実行するには、App-v 4.6 Sequencer を実行しているコンピューターで、64ビットオペレーティングシステムを実行しているコンピューターにアプリケーションをシーケンスする必要があります。 アプリケーションをシーケンスした後、Sequencer コンソールで [**展開**] タブを選択し、必要に応じて、適切なオペレーティングシステムとチップアーキテクチャを指定します。

次の表は、さまざまなバージョンの Sequencer を使用して作成されたパッケージを実行するクライアントバージョンを示しています。

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">App-v 4.2 Sequencer を使用したシーケンス</th>
<th align="left">App-v 4.5 Sequencer を使用したシーケンス</th>
<th align="left">32ビット版のアプリを使ったシーケンス (V 4.6 Sequencer)</th>
<th align="left">64ビット版のアプリを使ったシーケンス (V 4.6 Sequencer)</th>
<th align="left">32ビット版のアプリを使ったシーケンス-V 4.6 SP1 Sequencer</th>
<th align="left">64ビット版のアプリを使ったシーケンス-V 4.6 SP1 Sequencer</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>4.2 クライアント</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>×</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>なし</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.5 クライアント¹</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>可</p></td>
<td align="left"><p>×</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>なし</p></td>
</tr>
<tr class="odd">
<td align="left"><p>4.6 クライアント (32 ビット)</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>要</p></td>
<td align="left"><p>可</p></td>
<td align="left"><p>未対応</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>×</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.6 クライアント (64 ビット)</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>要</p></td>
<td align="left"><p>要</p></td>
<td align="left"><p>要</p></td>
<td align="left"><p>要</p></td>
<td align="left"><p>要</p></td>
</tr>
<tr class="odd">
<td align="left"><p>4.6 SP1 クライアント</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>要</p></td>
<td align="left"><p>可</p></td>
<td align="left"><p>未対応</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>×</p></td>
</tr>
<tr class="even">
<td align="left"><p>4.6 SP1 クライアント (64 ビット)</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>要</p></td>
<td align="left"><p>要</p></td>
<td align="left"><p>要</p></td>
<td align="left"><p>要</p></td>
<td align="left"><p>要</p></td>
</tr>
</tbody>
</table>

 

¹アプリ-v 4.5、app-v 4.5 CU1、および App-v 4.5 SP1 を含む、すべてのバージョンの App-v 4.5 クライアントに適用されます。

## その他の移行に関する考慮事項


App-v 4.5 Sequencer の機能の1つは、Microsoft Endpoint Configuration Manager などの電子ソフトウェア配布 (ESD) システムとの仮想アプリケーションパッケージの相互運用性の制御ポイントとして、Windows Installer ファイル (.msi) を作成する機能です。 以前に4.5 にアップグレードされた、アプリの仮想化用の .msi ツールを使用して作成された Windows Installer ファイルは、4.5 クライアントにはインストールできませんが、その後も4.5 にインストールされています。 ただし、4.5 Sequencer でアップグレードしない限り、削除またはアップグレードすることはできません。 元の4.5 仮想アプリケーションパッケージは、4.5 Sequencer で開いてから、Windows Installer ファイルとして保存する必要があります。

**注** App-v 4.2 クライアントが既に4.5 にアップグレードされている場合は、スクリプトを使用して、4.5 クライアント上の4.2 パッケージを保存し、それらを管理できるようにすることができます。 このスクリプトでは、msvcp71.dll と msvcr71.dll の2つのファイルを App-v のインストールフォルダーにコピーし、レジストリキー \ [HKEY \ _LOCAL \ _MACHINE ¥¥のレジストリキーの値を設定する必要があります (例:

"ClientVersion" = "4.2.1.20"

"GlobalDataDirectory" = "C:\\\\Documents and Settings\\\\All Users\\\\Documents\\\\" (グローバルに書き込み可能な場所)

 

App-v 4.5 Sequencer によって生成された Windows Installer ファイルは、App-v 4.6 クライアントで実行しようとすると、"このパッケージは Microsoft Application Virtualization Client 4.5 以降を必要とします" というエラーメッセージを表示します。 App-v 4.5 SP1 Sequencer または App-v 4.6 Sequencer のいずれかを使用して、古いパッケージを開き、パッケージ用の新しい .msi を生成します。

作成および保存された4.2 レポートは、サーバーが4.5 にアップグレードされると上書きされます。 これらのレポートを保持する必要がある場合は、サーバー上の SoftGrid 管理コンソールフォルダーにある SftMMC ファイルのバックアップコピーを保存し、そのコピーを使用してアップグレード中にインストールされた新しい SftMMC を置き換えます。

以前のバージョンからのアップグレードの詳細については、「 [Microsoft Application Virtualization 4.5 へのアップグレード](https://go.microsoft.com/fwlink/?LinkId=120358)に関する FAQ (」を参照してください https://go.microsoft.com/fwlink/?LinkId=120358) 。

## 関連トピック


[Application Virtualization システムの展開計画](planning-for-application-virtualization-system-deployment.md)

 

 





