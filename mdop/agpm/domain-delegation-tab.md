---
title: '[ドメインの委任] タブ'
description: '[ドメインの委任] タブ'
author: dansimp
ms.assetid: 15a9bfff-e25b-4b62-9ebc-521a5f4eae96
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d49083bcefe6c7edcb3a95dc63d2249826d50327
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818627"
---
# [ドメインの委任] タブ


[**変更] コントロール**ウィンドウの [**ドメインの委任**] タブには、アーカイブへのドメインレベルのアクセス権を持つグループポリシー管理者の一覧が表示され、それぞれの役割が示されます。 さらに、このタブでは、AGPM 管理者 (フルコントロール) を使用して、エディター、承認者、校閲者、その他の AGPM 管理者に対してドメインレベルの権限を構成することができます。 [**ドメインの委任**] タブには、ドメインレベルでの高度なグループポリシー管理 (AGPM) の電子メール通知とロールベースの委任の構成という2つのセクションがあります。

## メール通知の設定


このタブの [電子メール通知] セクションには、AGPM で操作が保留中の場合に通知を受け取る承認者が示されます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">設定</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>アップグレード前</strong></p></td>
<td align="left"><p>承認者に通知が送信される AGPM エイリアス。 複数のドメインがある環境では、環境全体で同じエイリアスを使用するか、ドメインごとに異なるエイリアスを使用することができます。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>アップグレード後</strong></p></td>
<td align="left"><p>通知が送信される承認者の電子メールアドレスのコンマ区切りリスト</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>SMTP サーバー</strong></p></td>
<td align="left"><p>メールサーバーの名前 (mail.contoso.com など)</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>ユーザー名</strong></p></td>
<td align="left"><p>SMTP サーバーへのアクセス権を持つユーザー</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>パスワード</strong></p></td>
<td align="left"><p>SMTP サーバーに対する認証のためのユーザーパスワード</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>パスワードの確認</strong></p></td>
<td align="left"><p>ユーザーのパスワードを確認する</p></td>
</tr>
</tbody>
</table>

 

## ドメインレベルの役割ベースの委任


このタブの [ロールベースの委任] セクションに表示される、AGPM 管理者は、アーカイブへのアクセス権を持つドメインの各グループとユーザーに対して、許可、拒否、継承された権限を委任することができます。 AGPM 管理者は、標準の AGPM ロール (エディター、承認者、レビュー担当者、AGPM 管理者) を使用するか、グループポリシー管理者ごとに権限のカスタマイズされた組み合わせを使って、ドメイン全体の権限を構成できます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ボタン</th>
<th align="left">効果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Add</strong></p></td>
<td align="left"><p>セキュリティ記述子に新しいエントリを追加します。 Active Directory 内のすべてのユーザーまたはグループをグループポリシーの管理者として追加できます。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>[削除]</strong></p></td>
<td align="left"><p>選択したグループポリシーの管理者を [アクセス制御] の一覧から削除します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>プロパティ</strong></p></td>
<td align="left"><p>選択したグループポリシー管理者のプロパティを表示します。 [プロパティ] ページは、[ <strong> Active Directory ユーザーとコンピューター] のオブジェクトに対して表示されるものと同じです </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>詳細設定</strong></p></td>
<td align="left"><p><strong>Access コントロールリストエディターを開き </strong> ます。</p></td>
</tr>
</tbody>
</table>

 

### その他の考慮事項

-   特定のタスクに関連するロールと権限の詳細については、「 [AGPM 管理者タスク](performing-agpm-administrator-tasks.md)を実行する」、「[エディタータスクを実行](performing-editor-tasks.md)する」、「[承認者タスク](performing-approver-tasks.md)を実行する」、「[校閲者タスク](performing-reviewer-tasks.md)を実行する」のタスクを参照してください。

### その他の参照情報

-   [ユーザー インターフェイス: 高度なグループ ポリシーの管理](user-interface-advanced-group-policy-management.md)

-   [AGPM 管理者タスクの実行](performing-agpm-administrator-tasks.md)

 

 





