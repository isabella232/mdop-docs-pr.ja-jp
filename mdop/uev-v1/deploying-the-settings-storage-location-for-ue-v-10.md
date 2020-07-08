---
title: UE-V 1.0 の設定の保存場所の展開
description: UE-V 1.0 の設定の保存場所の展開
author: dansimp
ms.assetid: b187d44d-649b-487e-98d3-a61ee2be8c2f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c179be0882bc6a0efc0f11f21fc231f03b63b0fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826637"
---
# UE-V 1.0 の設定の保存場所の展開


Microsoft User Experience Virtualization (UE-V) の展開には、設定パッケージファイルにユーザー設定が保存されている設定の保存場所が必要です。 設定の保存場所は、次の2つの方法のいずれかで構成できます。

-   **Active directory ホームディレクトリ**– active directory のユーザーに対してホームディレクトリが定義されている場合、ue-v agent はこの場所を使用して、設定場所パッケージを保存します。 UE-V agent は、ホームディレクトリのルートの下にユーザー固有のストレージフォルダーを動的に作成します。 設定の保存場所が定義されていない場合、エージェントは Active Directory のホームディレクトリのみを使用します。

-   **設定の保存共有を作成**する–設定の記憶域の共有は、ue-v ユーザーがアクセスできる標準ネットワーク共有です。

## UE-V 設定の記憶域共有を展開する


設定の保存共有を作成する場合は、アクセス権が必要なユーザーにのみアクセスを制限する必要があります。 以下の表に必要な権限が表示されています。

**UE-V ネットワーク共有を展開するには**

1.  UE-V ユーザーの新しいセキュリティグループを作成します。

2.  UE-V 設定パッケージを保存する中央のコンピューターに新しいフォルダーを作成し、そのフォルダーへのグループアクセス許可を UE-V ユーザーに付与します。 UE-V をサポートしている管理者には、この共有フォルダーへのアクセス許可が必要です。

3.  [記憶域の場所の設定] フォルダーに対して、次の共有レベル (SMB) の権限を設定します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>ユーザーアカウント</strong></th>
    <th align="left"><strong>推奨されるアクセス許可</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>すべてのユーザー</p></td>
    <td align="left"><p>権限なし</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UE-V ユーザーのセキュリティグループ</p></td>
    <td align="left"><p>フルコントロール</p></td>
    </tr>
    </tbody>
    </table>

     

4.  [設定の保存場所] フォルダーに、次の NTFS 権限を設定します。

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>ユーザーアカウント</strong></th>
    <th align="left"><strong>推奨されるアクセス許可</strong></th>
    <th align="left"><strong>Folder</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>作成者/所有者</p></td>
    <td align="left"><p>フルコントロール</p></td>
    <td align="left"><p>サブフォルダーとファイルのみ</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UE-V ユーザーのセキュリティグループ</p></td>
    <td align="left"><p>フォルダーの一覧/データの読み取り、フォルダーの作成/データの追加を行う</p></td>
    <td align="left"><p>このフォルダーのみ</p></td>
    </tr>
    </tbody>
    </table>

     

5.  [ **OK** ] をクリックしてダイアログボックスを閉じます。

このアクセス許可構成により、ユーザーは設定ストレージのフォルダーを作成できます。 UE-V agent は、 `settingspackage` ユーザーのコンテキストで実行されているときに、フォルダーを作成し、セキュリティで保護します。 ユーザーは、フォルダーに対してフルコントロールを受け取り `settingspackage` ます。 他のユーザーがこのフォルダーへのアクセス権を継承していない。 個々のユーザーディレクトリを作成してセキュリティで保護する必要はありません。これは、ユーザーのコンテキストで実行されるエージェントによって自動的に実行されるためです。

**注** セキュリティの追加は、設定の記憶域共有に対して Windows server を使用したときに構成できます。 UE-V は、ローカル管理者のグループまたは現在のユーザーが、設定パッケージが保存されているフォルダーの所有者であるかどうかを確認するように構成できます。 追加のセキュリティを有効にするには、次の操作を行います。

1.  "RepositoryOwnerCheckEnabled" という名前の**REG \ _DWORD**のレジストリキーを**HKEY \ _LOCAL \ _MACHINE ¥ # ¥ agent¥に追加します。**

2.  レジストリキーの値を1に設定します。

 

## 関連トピック


[UE-V 1.0 の展開](deploying-ue-v-10.md)

[UE-V 1.0 でサポートされている構成](supported-configurations-for-ue-v-10.md)

ユーザーエクスペリエンスの仮想化設定のテンプレートと設定パッケージ用の中央記憶域の展開[Ue-v Generator のインストール](installing-the-ue-v-generator.md)

[UE-V エージェントの展開](deploying-the-ue-v-agent.md)

 

 





