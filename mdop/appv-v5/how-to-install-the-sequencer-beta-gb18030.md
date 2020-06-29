---
title: Sequencer をインストールする方法
description: Sequencer をインストールする方法
author: dansimp
ms.assetid: a122caf0-f408-458c-b119-dc84123c1d58
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a8542abfecd7f1d543228ab1a86a59b9ee918947
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813954"
---
# Sequencer をインストールする方法


Microsoft Application Virtualization (App-v) 5.0 sequencer をインストールするには、次の手順を使用します。 Sequencer を実行するコンピューターは、どのバージョンの App-v 5.0 クライアントも実行していない必要があります。

以前のバージョンの App-v のインストールのアップグレードはサポートされません。

**重要** Sequencer の要件の一覧については、「 [app-v 5.0 の前提条件](app-v-50-prerequisites.md)と[アプリ-v 5.0 でサポートされている構成](app-v-50-supported-configurations.md)」を参照してください。

 

コマンドラインを使って、App-v 5.0 sequencer をインストールすることもできます。 次の一覧は、コマンドラインと**appv\_sequencer\_setup.exe**を使って sequencer をインストールするためのオプションに関する情報を示しています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コマンド</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>/INSTALLDIR</p></td>
<td align="left"><p>インストールディレクトリを指定します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/CEIPOPTIN</p></td>
<td align="left"><p>Microsoft カスタマーエクスペリエンス向上プログラムへの参加を有効にします。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/Log</p></td>
<td align="left"><p>インストールログが保存される場所を指定します。既定の場所は <strong> % Temp% です </strong> 。 たとえば、 <strong> C:\ログに </strong> 記録します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/q</p></td>
<td align="left"><p>Quiet またはサイレントインストールを指定します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/Uninstall</p></td>
<td align="left"><p>Sequencer の削除を指定します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/ACCEPTEULA</p></td>
<td align="left"><p>ライセンス契約を承諾します。 これは、無人インストールの場合に必要になります。 使用例: <strong> /ACCEPTEULA </strong> または <strong> /ACCEPTEULA = 1 </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/レイアウト</p></td>
<td align="left"><p>関連付けられているレイアウトアクションを指定します。 また、Windows インストーラー (.msi) とスクリプトファイルも、App-v 5.0 をインストールせずにフォルダーに展開します。 値は予期されません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/Layoutdir</p></td>
<td align="left"><p>レイアウトディレクトリを指定します。 文字列値が必要です。 使用例: <strong> /layoutdir = "C:\ Application Virtualization Client" </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/? または/h または/help</p></td>
<td align="left"><p>関連するヘルプを表示します。</p></td>
</tr>
</tbody>
</table>

 

**App-v 5.0 sequencer をインストールするには**

1.  アプリがインストールされているコンピューターに、App-v 5.0 sequencer インストールファイルをコピーします。 **appv\_sequencer\_setup.exe**をダブルクリックし、[**インストール**] をクリックします。

2.  [**ソフトウェアライセンス条項**] ページで、ライセンス条項を確認する必要があります。 ライセンス条項に同意するには、[**ライセンス条項に同意**する] を選択します。 **[次へ]** をクリックします。

3.  [ **Microsoft update を使用してコンピューターをセキュリティで保護し**、最新の状態に維持する] ページで、microsoft update を有効にするには、[**更新プログラムをチェックするときに Microsoft update を使用する (推奨)** ] を選択します。 Microsoft 更新プログラムの実行を無効にするには、[ **Microsoft Update を使用しない**] を選択します。 **[次へ]** をクリックします。

4.  プログラムに参加するための [**カスタマーエクスペリエンス向上プログラム**] ページで、[**カスタマーエクスペリエンス向上プログラムに参加**する] を選択します。 これにより、App-v 5.0 の使用方法に関する情報を収集することができます。 プログラムに参加したくない場合は、[**プログラムに参加しない**] を選択します。 **[インストール]** をクリックします。

5.  Sequencer を開くには、[**スタート**] をクリックし、[ **Microsoft Application Virtualization sequencer**] をクリックします。

**App-v 5.0 sequencer のインストールのトラブルシューティングを行うには**

-   Sequencer のインストールの詳細については、 **% temp%** フォルダーのエラーログを参照してください。 ログファイルを確認するには、[**スタート**] をクリックし、「 **% temp%**」と入力して、 **appv\_ ログ**を探します。

    App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[App-V の展開計画](planning-to-deploy-app-v.md)

 

 





