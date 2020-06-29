---
title: User Experience Virtualization 1.0 SP1 について
description: User Experience Virtualization 1.0 SP1 について
author: dansimp
ms.assetid: 0212d3fb-e882-476c-9496-9eb52301703d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a480ac5d4f4083fc15a724b7cc79390b0caef14
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826894"
---
# User Experience Virtualization 1.0 SP1 について


Microsoft User Experience Virtualization (UE-V) 1.0 Service Pack 1 では、バージョンを1.0.414 から1.0.520 に変更します。 UE-V Agent setup.exe または UE-V Generator setup.exe が起動されると、アップグレードの必要性が検出され、UE-V エージェントまたはジェネレーターがアップグレードされます。

## 現在サポートされているその他の言語


UE-V 1.0 Service Pack 1 には、追加の言語をサポートしている UE-V Agent と UE-V Generator の両方の更新プログラムが用意されています。 サポートされているすべての言語は、セットアッププログラムを実行したときにインストールされます。 UE-V 1 SP1 には、次の言語が含まれています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">UE-V Agent</th>
<th align="left">UE-V Generator</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><ul>
<li><p>簡体字中国語 (PRC) zh-cn&platform-CN</p></li>
</ul>
<ul>
<li><p>繁体字中国語-台湾 zh-cn&platform-TW</p></li>
</ul>
<ul>
<li><p>チェコ語 (チェコ共和国) .cs-CZ</p></li>
</ul>
<ul>
<li><p>デンマーク語 (デンマーク) da-DK</p></li>
</ul>
<ul>
<li><p>オランダ語 (オランダ) nl-NL</p></li>
</ul>
<ul>
<li><p>フィンランド語 (フィンランド) fi</p></li>
</ul>
<ul>
<li><p>フランス語 (フランス) fr-fr</p></li>
</ul>
<ul>
<li><p>ドイツ語 (ドイツ) デデュープ</p></li>
</ul>
<ul>
<li><p>ギリシャ語 (ギリシャ) el-GR</p></li>
</ul>
<ul>
<li><p>ハンガリー語 (ハンガリー) hu-HU</p></li>
</ul>
<ul>
<li><p>イタリア語 (イタリア) it IT IT</p></li>
</ul>
<ul>
<li><p>日本語 (日本) ja-jp</p></li>
</ul>
<ul>
<li><p>韓国語 (韓国) ko-KR</p></li>
</ul>
<ul>
<li><p>ノルウェー語-ノルウェー語 (ブークモール) nb-いいえ</p></li>
</ul>
<ul>
<li><p>ポーランド語 (ポーランド) pl-PL</p></li>
</ul>
<ul>
<li><p>ポルトガル語 (ブラジル) pt-BR</p></li>
</ul>
<ul>
<li><p>ポルトガル語 (ポルトガル) の pt-PT</p></li>
</ul>
<ul>
<li><p>ロシア語 (ロシア) ru-RU</p></li>
</ul>
<ul>
<li><p>スロバキア語 (スロバキア) sk-SK</p></li>
</ul>
<ul>
<li><p>スロベニア語 (スロベニア) sl-SL</p></li>
</ul>
<ul>
<li><p>スペイン語、インターナショナルソート (スペイン) es</p></li>
</ul>
<ul>
<li><p>スウェーデン語 (スウェーデン) sv-SE</p></li>
</ul>
<ul>
<li><p>トルコ語 (トルコ) tr-TR</p></li>
</ul>
<p></p></td>
<td align="left"><ul>
<li><p>簡体字中国語 (PRC) zh-cn&platform-CN</p></li>
</ul>
<ul>
<li><p>繁体字中国語-台湾 zh-cn&platform-TW</p></li>
</ul>
<ul>
<li><p>フランス語 (フランス) fr-fr</p></li>
</ul>
<ul>
<li><p>ドイツ語 (ドイツ) デデュープ</p></li>
</ul>
<ul>
<li><p>イタリア語 (イタリア) it IT IT</p></li>
</ul>
<ul>
<li><p>日本語 (日本) ja-jp</p></li>
</ul>
<ul>
<li><p>韓国語 (韓国) ko-KR</p></li>
</ul>
<ul>
<li><p>ポルトガル語 (ブラジル) pt-BR</p></li>
</ul>
<ul>
<li><p>ロシア語 (ロシア) ru-RU</p></li>
</ul>
<ul>
<li><p>スペイン語、インターナショナルソート (スペイン) es</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**重要** UE-V Agent インストールプログラム (AgentSetup.exe) と UE-V Generator インストールプログラム (ToolSetup.exe) は上記の言語に翻訳されますが、Windows Installer (.msi) ファイルは英語でのみ利用できます。

 

## Office 2007 の設定場所テンプレート


UE-V Agent インストールソフトウェアは、エージェントをインストールし、一般的な Microsoft アプリケーションの設定場所テンプレートの既定のグループを登録します。 Microsoft Office 2007 は、これらのアプリケーションの一部になりました。 Office 2007 テンプレートには、MicrosoftOffice2007.xml と MicrosoftCommunicator2007.xml の2種類があります。 次のアプリケーションでは、これらの設定場所テンプレートで Microsoft Office 2007 の設定を取得します。

-   Microsoft Access 2007

-   Microsoft Communicator 2007

-   Microsoft Excel 2007

-   Microsoft InfoPath 2007

-   Microsoft OneNote 2007

-   Microsoft Outlook 2007

-   Microsoft PowerPoint 2007

-   Microsoft Project 2007

-   Microsoft Publisher 2007

-   Microsoft SharePoint Designer 2007

-   Microsoft Visio 2007

-   Microsoft Word 2007

### Office 2010 の設定場所テンプレートの更新

設定場所テンプレートの更新も行われました。 次のような変更が加えられます。

-   Office 2010 のテンプレートに新しいテンプレートを追加することにより、Microsoft SharePoint Designer 2010 のサポートが追加されました (MicrosoftOffice2010Win32.xml と MicrosoftOffice2010Win64.xml)

-   [ステータスバーのカスタマイズ] (Word、Excel、PowerPoint) などの軽微なバグの修正

## カタログ更新のスケジュールされたタスクがランダム化されるようになりました


テンプレートの自動更新タスクは、新規作成、更新、または削除されたテンプレートの設定テンプレートカタログをチェックします。 このタスクは、SettingsTemplateCatalog が構成されている場合にのみ実行されます。 テンプレートの自動更新タスクは、UE-V Agent インストールディレクトリにある ApplySettingsCatalog.exe ファイルを実行します。また、UE-V SP1 を変更して、1時間を超える更新プログラムをランダム化します。

## Citrix EdgeSight のサポート


Citrix EdgeSight でサーバー上で実行されている UE-V で、競合が検出されました。 UE-V 1.0 SP1 はこの問題を解決します。

## Internet Explorer のお気に入りのインデックス作成


UE-V で Internet Explorer のお気に入りを1台のコンピューターから別のコンピューターに移動すると、同期されたコンピューターのアドレスバーにあるお気に入りのアドレスのインデックス作成が更新されます。 ユーザーがアドレスバーに入力すると、ローミングしたお気に入りが、同期されたコンピューターで利用可能な検索結果として表示されるようになります。

## UE-V Agent および UE-V Generator の新しい setup.exe コマンドラインパラメーター


UE-V 1.0 SP1 のリリースにより、UE-V Agent と UE-V Generator の両方の setup.exe が更新され、次の追加のコマンドラインパラメーターを使用できるようになりました。

1.  `CEIPENABLED` – Microsoft カスタマーエクスペリエンス向上プログラムに含まれるオプションをセットアップで受け入れることができます。

2.  `INSTALLFOLDER` –別のインストールフォルダーをエージェントまたはジェネレーター用に設定できるようにします。

3.  `MUENABLED` – Microsoft Update プログラムに含まれるオプションをセットアップで受け入れることができます。

## セットアップの新しいエラーコード


Ue-v Agent (AgentSetup.exe) の UE-V のセットアップを実行している場合、次のリターンコードをインストールログ "/loglog.txtで表示でき &lt; &gt; ます。"

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>0</p></td>
<td align="left"><p>セットアップが正常に完了しました。</p></td>
</tr>
<tr class="even">
<td align="left"><p>両面</p></td>
<td align="left"><p>以前のバージョンの UE-V が、アンインストールのために使用されました。 UE-V をアンインストールするには、インストールに使用したのと同じバージョンの UE-V を使用します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>-</p></td>
<td align="left"><p>新しいバージョンの UE-V を使用してアンインストールしました。 UE-V をアンインストールするには、インストールに使用したのと同じバージョンの UE-V を使用します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>4d</p></td>
<td align="left"><p>セットアッププログラムから予期しないエラーが発生しました。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>個</p></td>
<td align="left"><p>UE-V のフルバージョンは、試用版 (評価版) の上にインストールできません。 試用版をアンインストールして、もう一度試してください。</p></td>
</tr>
<tr class="even">
<td align="left"><p>=</p></td>
<td align="left"><p>インストール中に予期しないエラーが発生した。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>日</p></td>
<td align="left"><p>.NET 3.5 フレームワークは、Windows 7 または Windows Server2008 R2 コンピューターでは見つかりませんでした。</p></td>
</tr>
<tr class="even">
<td align="left"><p>個</p></td>
<td align="left"><p>オフラインファイル機能は有効ではありません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ファイブ</p></td>
<td align="left"><p>UE-V のセットアッププログラムは、UE-V が既にインストールされているかどうかを判別できないか、またはセットアップファイルにエラーがあったかどうかを判断できません。</p></td>
</tr>
</tbody>
</table>

 

 

 





