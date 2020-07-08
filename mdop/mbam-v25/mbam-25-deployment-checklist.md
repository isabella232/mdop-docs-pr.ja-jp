---
title: MBAM 2.5 の展開チェックリスト
description: MBAM 2.5 の展開チェックリスト
author: dansimp
ms.assetid: 2ba7de17-e3a4-4798-99e0-cd1dc28c5b76
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 11609b3d6d44d62b032e35005e5d967ca6d4e83b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822834"
---
# MBAM 2.5 の展開チェックリスト


このチェックリストを使用すると、スタンドアロンのトポロジを使って、Microsoft BitLocker の管理と監視 (MBAM) 展開を行うときに役立ちます。

**注**  
このチェックリストは、推奨される手順と、Microsoft BitLocker の管理機能と監視機能を展開するときに考慮する必要のある項目の概要を示しています。 このチェックリストをスプレッドシートプログラムにコピーして、用途に合わせてカスタマイズすることをお勧めします。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">タスク</th>
<th align="left">参照先</th>
<th align="left">備考</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM 展開の環境を準備するために、すべての計画手順を確認して完了します。</p></td>
<td align="left"><p><a href="mbam-25-planning-checklist.md" data-raw-source="[MBAM 2.5 Planning Checklist](mbam-25-planning-checklist.md)">MBAM 2.5 の計画チェックリスト</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>サポートされている構成情報を確認して、MBAM が選択されたクライアントとサーバーコンピューターをサポートしていることを確認します。</p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 がサポートされる構成</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM サーバーソフトウェアをインストールします。</p></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">MBAM 2.5 サーバー ソフトウェアのインストール</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM サーバー機能を構成します。</p>
<ul>
<li><p>コンプライアンスと監査データベースと復元データベース</p></li>
<li><p>レポート</p></li>
<li><p>Web アプリケーション</p></li>
<li><p>Configuration Manager の統合トポロジ (このトポロジで MBAM を実行している場合にのみ必要)</p></li>
</ul>
<div class="alert">
<strong>注</strong><br/><p>各機能を構成するサーバーの名前をメモします。 この情報は、構成プロセス全体で使用します。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="configuring-the-mbam-25-server-features.md" data-raw-source="[Configuring the MBAM 2.5 Server Features](configuring-the-mbam-25-server-features.md)">MBAM 2.5 サーバー機能の構成</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM 構成を確認します。</p></td>
<td align="left"><p><a href="validating-the-mbam-25-server-feature-configuration.md" data-raw-source="[Validating the MBAM 2.5 Server Feature Configuration](validating-the-mbam-25-server-feature-configuration.md)">MBAM 2.5 サーバー機能の構成の確認</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM グループポリシーテンプレートをコピーし、グループポリシー設定を編集します。</p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)">MBAM 2.5 グループポリシーテンプレートのコピー </a> と <a href="editing-the-mbam-25-group-policy-settings.md" data-raw-source="[Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md)"> mbam 2.5 グループポリシー設定の編集</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM クライアントソフトウェアを展開します。</p></td>
<td align="left"><p><a href="deploying-the-mbam-25-client.md" data-raw-source="[Deploying the MBAM 2.5 Client](deploying-the-mbam-25-client.md)">MBAM 2.5 クライアントの展開</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>




## 関連トピック


[MBAM 2.5 の展開](deploying-mbam-25.md)




## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。




