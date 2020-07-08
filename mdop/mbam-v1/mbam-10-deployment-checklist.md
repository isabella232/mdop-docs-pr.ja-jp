---
title: MBAM 1.0 の展開チェックリスト
description: MBAM 1.0 の展開チェックリスト
author: dansimp
ms.assetid: 7e00be23-36a0-4b0f-8663-3c4f2c71546d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 96725183af2cb4e3d86d3f42973452c598497773
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812538"
---
# MBAM 1.0 の展開チェックリスト


このチェックリストは、Microsoft BitLocker の管理と監視 (MBAM) を簡単に展開できるように設計されています。

**注**  
このチェックリストは推奨手順の概要を示し、MBAM 機能を展開するときに考慮する必要がある概要の項目の一覧を示します。 このチェックリストをスプレッドシートプログラムにコピーして、特定のニーズに合わせてカスタマイズすることをお勧めします。



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
<td align="left"><p>計画フェーズを完了して、MBAM 展開用のコンピューティング環境を準備します。</p></td>
<td align="left"><p><a href="mbam-10-planning-checklist.md" data-raw-source="[MBAM 1.0 Planning Checklist](mbam-10-planning-checklist.md)">MBAM 1.0 の計画チェックリスト</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM 機能がインストールされていることを確認するために、MBAM サポートされている構成の情報を確認します。</p></td>
<td align="left"><p><a href="mbam-10-supported-configurations.md" data-raw-source="[MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md)">MBAM 1.0 がサポートされる構成</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>Mbam サーバー機能を次の順序で展開するには、MBAM セットアップを実行します。</p>
<ol>
<li><p>回復とハードウェアデータベース</p></li>
<li><p>コンプライアンスステータスデータベース</p></li>
<li><p>コンプライアンス監査とレポート</p></li>
<li><p>管理と監視サーバー</p></li>
<li><p>MBAM グループポリシーテンプレート</p></li>
</ol>
<div class="alert">
<strong>注</strong><br/><p>各機能がインストールされているサーバーの名前を追跡します。 この情報は、インストールプロセス全体で使用されます。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="deploying-the-mbam-10-server-infrastructure.md" data-raw-source="[Deploying the MBAM 1.0 Server Infrastructure](deploying-the-mbam-10-server-infrastructure.md)">MBAM 1.0 サーバー インフラストラクチャの展開</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>計画フェーズで作成した Active Directory ドメインサービスセキュリティグループを、適切なローカル MBAM サーバー機能の管理者グループに追加します。</p></td>
<td align="left"><p><a href="planning-for-mbam-10-administrator-roles.md" data-raw-source="[Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md)">MBAM 1.0 管理者ロールの計画 </a> と <a href="how-to-manage-mbam-administrator-roles-mbam-1.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-1.md)"> Mbam 管理者ロールの管理方法</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>必要な MBAM グループポリシーオブジェクトを作成して展開します。</p></td>
<td align="left"><p><a href="deploying-mbam-10-group-policy-objects.md" data-raw-source="[Deploying MBAM 1.0 Group Policy Objects](deploying-mbam-10-group-policy-objects.md)">MBAM 1.0 グループ ポリシー オブジェクトの展開</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM クライアントソフトウェアを展開します。</p></td>
<td align="left"><p><a href="deploying-the-mbam-10-client.md" data-raw-source="[Deploying the MBAM 1.0 Client](deploying-the-mbam-10-client.md)">MBAM 1.0 クライアントの展開</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## 関連トピック


[MBAM 1.0 の展開](deploying-mbam-10.md)









