---
title: MBAM 2.0 の展開チェックリスト
description: MBAM 2.0 の展開チェックリスト
author: dansimp
ms.assetid: 7905d31d-f21c-4683-b9c4-95b815e08fab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5d8d0ce1a3ff48d4bf2f84e61b4a578b170264a0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826437"
---
# MBAM 2.0 の展開チェックリスト


このチェックリストは、スタンドアロンのトポロジを使用して、Microsoft BitLocker の管理と監視 (MBAM) 展開を行うときに役立ちます。

**注**  
このチェックリストは、推奨される手順と、Microsoft BitLocker の管理機能と監視機能を展開するときに考慮する項目の概要を示しています。 このチェックリストをスプレッドシートプログラムにコピーして、用途に合わせてカスタマイズすることをお勧めします。



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
<td align="left"><p><a href="mbam-20-planning-checklist-mbam-2.md" data-raw-source="[MBAM 2.0 Planning Checklist](mbam-20-planning-checklist-mbam-2.md)">MBAM 2.0 の計画チェックリスト</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM でサポートされている構成情報を確認して、お使いのクライアントとサーバーのコンピューターが MBAM 機能のインストールでサポートされていることを確認します。</p></td>
<td align="left"><p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">MBAM 2.0 がサポートされる構成</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>Mbam サーバー機能を次の順序で展開するには、MBAM セットアップを実行します。</p>
<ol>
<li><p>回復用データベース</p></li>
<li><p>コンプライアンスと監査データベース</p></li>
<li><p>コンプライアンス監査とレポート</p></li>
<li><p>セルフサービスサーバー</p></li>
<li><p>管理と監視サーバー</p></li>
<li><p>MBAM グループポリシーテンプレート</p></li>
</ol>
<div class="alert">
<strong>注</strong><br/><p>各機能がインストールされているサーバーの名前を追跡します。 この情報は、インストールプロセス全体で使用されます。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="deploying-the-mbam-20-server-infrastructure-mbam-2.md" data-raw-source="[Deploying the MBAM 2.0 Server Infrastructure](deploying-the-mbam-20-server-infrastructure-mbam-2.md)">MBAM 2.0 サーバー インフラストラクチャの展開</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>計画フェーズで作成した Active Directory ドメインサービスセキュリティグループを、適切なローカル MBAM サーバー機能の管理者グループに追加します。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)">MBAM 2.0 管理者ロールの計画 </a> と <a href="how-to-manage-mbam-administrator-roles-mbam-2.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-2.md)"> Mbam 管理者ロールの管理方法</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>必要な MBAM グループポリシーオブジェクトを作成して展開します。</p></td>
<td align="left"><p><a href="deploying-mbam-20-group-policy-objects-mbam-2.md" data-raw-source="[Deploying MBAM 2.0 Group Policy Objects](deploying-mbam-20-group-policy-objects-mbam-2.md)">MBAM 2.0 グループ ポリシー オブジェクトの展開</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>MBAM クライアントソフトウェアを展開します。</p></td>
<td align="left"><p><a href="deploying-the-mbam-20-client-mbam-2.md" data-raw-source="[Deploying the MBAM 2.0 Client](deploying-the-mbam-20-client-mbam-2.md)">MBAM 2.0 クライアントの展開</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## 関連トピック


[MBAM 2.0 の展開](deploying-mbam-20-mbam-2.md)









