---
title: MBAM 2.5 サーバー ソフトウェアのインストール
description: MBAM 2.5 サーバー ソフトウェアのインストール
author: dansimp
ms.assetid: b9dbe697-5400-4bac-acfb-ee6dc6586c30
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6612bf52aa53ae693694d7ac02c5cab212d4e24f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823394"
---
# MBAM 2.5 サーバー ソフトウェアのインストール


このトピックでは、microsoft bitlocker の管理と監視 (MBAM) 2.5 サーバーソフトウェアをインストールする方法について説明します。 Microsoft BitLocker の管理と監視のセットアップウィザードを使用するか、コマンドラインパラメーターを使用します。 MBAM 2.5 サーバー機能を構成している各サーバーに対して、サーバーのインストールプロセスを繰り返します。 インストールが完了したら、サーバー機能を構成する手順について「 [MBAM 2.5 サーバー機能を構成](configuring-the-mbam-25-server-features.md)する」を参照してください。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">開始する前に</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MBAM 2.5 の計画情報を確認する</p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件</a></p></li>
<li><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 がサポートされる構成</a></p></li>
<li><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)">MBAM 2.5 のアーキテクチャの概要</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>ログファイルを取得する方法を確認する</p></td>
<td align="left"><p>既定では、ログファイルはローカルコンピューターの% temp% フォルダーに作成されます。 ログファイルを% temp% フォルダーではなく特定の場所に書き込むには <strong> </strong> 、/log の <strong> location 引数を使用し </strong> &lt; <em> </em> &gt; ます。</p>
<p>追加のイベントは、 <strong> Mbam セットアップ </strong> または <strong> Mbam-Web </strong> ノード ([ <strong> アプリケーションとサービスログ] の [Microsoft Windows] の下 &gt; &gt; </strong> ) の [イベントビューアー] に記録される場合があります。 たとえば、MBAM をアンインストールした場合、アンインストーラーは、EventViewer の MBAM セットアップと MBAM Web ログもアンインストールします。</p></td>
</tr>
</tbody>
</table>

 

## Microsoft BitLocker の管理と監視のセットアップウィザードを使用して MBAM 2.5 サーバーソフトウェアをインストールする


Microsoft BitLocker の管理と監視のセットアップウィザードを使用して、MBAM サーバーソフトウェアをインストールするには、次の手順を使用します。

**ウィザードを使用して MBAM 2.5 サーバーソフトウェアをインストールするには**

1.  MBAM をインストールするサーバーで**MBAMserversetup.exe**を実行して、Microsoft BitLocker の管理と監視のセットアップウィザードを開始します。

2.  [**ようこそ**] ページで、[**次へ**] をクリックします。

3.  Microsoft ソフトウェアライセンス条項を読んで同意し、[**次へ**] をクリックしてインストールを続行します。

4.  更新プログラムを確認するときに Microsoft Update を使用するかどうかを選択し、[**次へ**] をクリックします。

5.  カスタマーエクスペリエンス向上プログラムに参加するかどうかを選択し、[**次へ**] をクリックします。

6.  インストールを開始するには、[**インストール**] をクリックします。

7.  MBAM サーバーソフトウェアのインストールが完了した後でサーバーの機能を構成するには、[**ウィザードを終了した後に MBAM サーバーの構成を実行**する] チェックボックスをオンにします。 または、[**スタート**] メニューで作成した**mbam server 構成**ショートカットを使用して、mbam を後で構成することもできます。

8.  **[完了]** をクリックします。

## コマンドプロンプトウィンドウを使用して MBAM 2.5 サーバーソフトウェアをインストールする


コマンドプロンプトで、次のコマンドのようなコマンドを入力して、MBAM サーバーソフトウェアをインストールします。

``` syntax
MbamServerSetup.exe MBAMServerInstall.log
CEIPENABLED=True OPTIN_FOR_MICROFOST_UPDATES=True INSTALLDIR=c:\mbaminstall
```

次の表では、MBAM 2.5 サーバーソフトウェアをインストールするためのコマンドラインパラメーターについて説明します。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">パラメーター</th>
<th align="left">パラメーター値</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>CEIPENABLED</p></td>
<td align="left"><p>True False</p></td>
<td align="left"><p>True-カスタマーエクスペリエンス向上プログラムに参加します。これにより、どの MBAM 機能を改善することができます。</p>
<p>False –カスタマーエクスペリエンス向上プログラムに参加しないでください。</p></td>
</tr>
<tr class="even">
<td align="left"><p>OPTIN_FOR_MICROSOFT_UPDATES</p></td>
<td align="left"><p>True False</p></td>
<td align="left"><p>True-Microsoft Update を使用して、コンピューターをセキュリティで保護し、Windows やその他の Microsoft 製品 (MBAM を含む) を最新の状態に保ちます。</p>
<p>False – Microsoft Update を使用しない</p></td>
</tr>
<tr class="odd">
<td align="left"><p>INSTALLDIR</p></td>
<td align="left"><p>&lt;パス&gt;</p></td>
<td align="left"><p>MBAM をインストールする場所。</p>
<p>例:</p>
<p>INSTALLDIR = c:\ mbaminstall</p></td>
</tr>
<tr class="even">
<td align="left"><p>FORCE_UNINSTALL</p></td>
<td align="left"><p>True False</p></td>
<td align="left"><p>True-すべての機能を削除できない場合でも、MBAM のアンインストールプロセスを続行します。</p>
<p>アンインストールカスタムアクションによって追加された MBAM サーバー機能の削除に失敗した場合は、アンインストールは失敗し、MBAM はインストールされたままになります。</p>
<p>どちらの場合も、MBAM をアンインストールしようとしたときに正常に削除されたすべての機能は削除されます。</p></td>
</tr>
</tbody>
</table>

 



## 関連トピック


[MBAM 2.5 の展開](deploying-mbam-25.md)

[MBAM 2.5 サーバー機能の構成](configuring-the-mbam-25-server-features.md)

 

## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





