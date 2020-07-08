---
title: 旧バージョンからの移行
description: 旧バージョンからの移行
author: dansimp
ms.assetid: a13cd353-b22a-48f7-af1e-5d54ede2a7e5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a05bbd498cdb77a1ddf694b1aab6aeb42124775b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813555"
---
# 旧バージョンからの移行


App-v 5.0 を使用すると、既存の App-v 4.6 インフラストラクチャを、より柔軟かつ統合化され、より簡単に5.0 管理できるようになります。

移行戦略を計画するときは、次のセクションを考慮してください。

**注** App-v 4.6 と App-v 5.0 の違いの詳細については、「 [app-v 5.0 について](about-app-v-50.md)」の「app-v **4.6 と app-v 5.0」セクション**を参照してください。

 

## 以前のバージョンの App-v を使用して作成されたパッケージの変換


以前のバージョンの App-v を使用して作成された仮想アプリケーションパッケージをアップグレードするには、パッケージコンバーターユーティリティを使用します。 パッケージコンバーターは、PowerShell を使用してパッケージを変換し、変換が必要なパッケージが多い場合は、プロセスの自動化に役立ちます。

**重要** 既存のパッケージを変換した後は、パッケージを展開する前にパッケージをテストして、変換処理が正常に完了したことを確認する必要があります。

 

**既存のパッケージを変換する前に知っておくべきこと**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">問題</th>
<th align="left">回避策</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>パッケージスクリプトは変換されません。</p></td>
<td align="left"><p>変換されたパッケージをテストします。 必要に応じて、スクリプトを変換します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>パッケージのレジストリ設定の上書きは変換されません。</p></td>
<td align="left"><p>変換されたパッケージをテストします。 必要に応じて、レジストリの上書きを再度追加します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>変換後、DSC を使用する仮想パッケージはリンクされません。</p></td>
<td align="left"><p>接続グループを使ってパッケージをリンクします。 「 <a href="managing-connection-groups.md" data-raw-source="[Managing Connection Groups](managing-connection-groups.md)"> 接続グループの管理」をご覧ください </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>変換中に環境変数の競合が検出されます。</p></td>
<td align="left"><p>関連付けられている .osd ファイル内の競合を解決 <strong> </strong> します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>変換中にハードコーディングされたパスが検出されます。</p></td>
<td align="left"><p>ハードコーディングされたパスは正しく変換されにくくなります。 パッケージコンバーターは、ハードコーディングされたパスを含むファイルを含むパッケージを検出して返します。 ハードコーディングされたパスでファイルを表示し、パッケージにファイルが必要かどうかを確認します。 その場合は、パッケージの順序を再確認することをお勧めします。</p></td>
</tr>
</tbody>
</table>

 

パッケージを変換するときに、エラーが発生したファイルまたはショートカットを確認します。 App-V 4.6 パッケージでアイテムを見つけます。 ハードコードされている可能性があります。 パスを変換します。

**注** 機能を活用する必要がある重要なアプリケーションやアプリケーションを変換するには、App-v 5.0 sequencer を使うことをお勧めします。 「 [App-v 5.0 を使って新しいアプリケーションを順序付けする方法](how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md)」を参照してください。

変換後に変換されたパッケージが開かない場合は、App-v 5.0 sequencer を使用してアプリケーションを再シーケンスすることをお勧めします。

 

[以前のバージョンの APP-V で作成されたパッケージを変換する方法](how-to-convert-a-package-created-in-a-previous-version-of-app-v.md)

## クライアントの移行


次の表は、クライアントをアップグレードするための推奨される方法を示しています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスク</th>
<th align="left">詳細情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>環境を App V 4.6 SP2 にアップグレードする</p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)">アプリケーションの仮想化の展開とアップグレードに関する考慮事項 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>共存を有効にした App-v 5.0 クライアントをインストールします。</p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-46-and-the-app-v--50-client-on-the-same-computer.md" data-raw-source="[How to Deploy the App-V 4.6 and the App-V 5.0 Client on the Same Computer](how-to-deploy-the-app-v-46-and-the-app-v--50-client-on-the-same-computer.md)">同じコンピューターに app-v 4.6 と App-v 5.0 クライアントを展開する方法を説明 </a> します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>アプリ-V 5.0 パッケージのシーケンスとロールアウト。 必要に応じて、App-v 4.6 パッケージの発行を取り消します。</p></td>
<td align="left"><p><a href="how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md" data-raw-source="[How to Sequence a New Application with App-V 5.0](how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md)">App-V 5.0 を使って新しいアプリケーションをシーケンスする方法について説明 </a> します。</p></td>
</tr>
</tbody>
</table>

 

**重要** 共存モードを使用するには、App-v 4.6 SP3 を実行している必要があります。 さらに、パッケージをシーケンス処理するときには、 **[ユーザーの****構成] セクションに**ある [管理権限] 設定を構成する必要があります。

 

## App-v 5.0 Server の完全なインフラストラクチャを移行する


完全な App-v 5.0 インフラストラクチャにアップグレードする直接的な方法はありません。 App-v server のアップグレードについては、次のセクションの情報を参照してください。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスク</th>
<th align="left">詳細情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>環境を App V 4.6 SP3 にアップグレードします。</p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)">アプリケーションの仮想化の展開とアップグレードに関する考慮事項 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>クライアントの App-v 5.0 バージョンを展開します。</p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-client-gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md)">App-v クライアントを展開する方法を説明 </a> します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 5.0 server をインストールします。</p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-50-server-50sp3.md" data-raw-source="[How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)">App-v 5.0 サーバーを展開する方法について説明 </a> します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>既存のパッケージを移行します。</p></td>
<td align="left"><p><strong>この記事の「以前のバージョンの app-v を使用して作成されたパッケージの変換」を参照してください </strong> 。</p></td>
</tr>
</tbody>
</table>

 

## その他の移行タスク


また、エンドポイントの再構成や、App-v 5.0 クライアントを実行しているコンピューター上で以前のバージョンを使用して作成されたパッケージの開くなど、追加の移行タスクを実行することもできます。 次のリンクでは、これらのタスクを実行する方法について詳しく説明します。

[特定のコンピューター上の全ユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.0 パッケージに移行する方法](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)

[特定のユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.0 パッケージに移行する方法](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md)

[特定のコンピューター上の全ユーザーの拡張ポイントを App-V 5.0 パッケージから App-V 4.6 パッケージに戻す方法](how-to-revert-extension-points-from-an-app-v-50-package-to-an-app-v-46-package-for-all-users-on-a-specific-computer.md)

[特定のユーザーの拡張ポイントを App-V 5.0 パッケージから App-V 4.6 パッケージに戻す方法](how-to-revert-extension-points-from-an-app-v-50-package-to-an-app-v-46-package-for-a-specific-user.md)







## App-v の移行タスクを実行するためのその他のリソース


[APP-V 5.0 の操作](operations-for-app-v-50.md)

[簡素化された Microsoft App-V 5.1 Management Server のアップグレード手順](https://go.microsoft.com/fwlink/p/?LinkId=786330)

 

 





