---
title: UE-V 1.0 の設定テンプレート カタログの展開
description: UE-V 1.0 の設定テンプレート カタログの展開
author: dansimp
ms.assetid: 0e6ab5ef-8eeb-40b4-be7b-a841bd83be96
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f342daa958607a077fa5eb2a27ec705c8d99e67f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826634"
---
# UE-V 1.0 の設定テンプレート カタログの展開


カスタム設定の場所テンプレートは、Microsoft User Experience Virtualization (UE-V) コンピューター上のフォルダーパスまたはサーバーメッセージブロック (SMB) ネットワーク共有上のフォルダーパスに保存できます。 コンピューター上のスケジュールされたタスクが、この場所から新しいまたは更新されたテンプレートを確認します。 タスクでは、この場所が毎日1回チェックされ、このフォルダー内のテンプレートに基づいて同期動作が更新されます。 前回のチェック後にこのフォルダーで追加または更新されるテンプレートは、UE-V agent によって登録されます。 UE-V agent deregisters テンプレートはこのフォルダーから削除されました。 スケジュールされたタスクはシステムとして実行されます。 少なくとも、ネットワーク共有は、ドメインコンピューターグループに対するアクセス許可を付与する必要があります。 さらに、保存されたテンプレートを管理する管理者にネットワーク共有フォルダーへのアクセス許可を付与します。 カスタム設定の場所テンプレートの詳細については、「 [ue-v 1.0 のカスタムテンプレートの展開を計画](planning-for-custom-template-deployment-for-ue-v-10.md)する」を参照してください。

**UE-V の設定テンプレートカタログを構成するには**

1.  UE-V 設定テンプレートカタログを保存するコンピューター上に新しいフォルダーを作成します。

2.  設定テンプレートカタログフォルダーに対して、次の共有レベル (SMB) のアクセス許可を設定します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>ユーザーアカウント</strong></th>
    <th align="left"><strong>権限の推奨</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>すべてのユーザー</p></td>
    <td align="left"><p>権限なし</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>ドメインコンピューター</p></td>
    <td align="left"><p>アクセス許可レベルの読み取り</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>管理者</p></td>
    <td align="left"><p>読み取り/書き込みアクセス許可レベル</p></td>
    </tr>
    </tbody>
    </table>

     

3.  設定テンプレートカタログフォルダーに対して、次の NTFS アクセス許可を設定します。

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">ユーザーアカウント</th>
    <th align="left">推奨されるアクセス許可</th>
    <th align="left">適用対象</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>作成者/所有者</p></td>
    <td align="left"><p>フルコントロール</p></td>
    <td align="left"><p>このフォルダー、サブフォルダー、ファイル</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>ドメインコンピューター</p></td>
    <td align="left"><p>フォルダーの内容の一覧表示と読み取り</p></td>
    <td align="left"><p>このフォルダー、サブフォルダー、ファイル</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>すべてのユーザー</p></td>
    <td align="left"><p>権限なし</p></td>
    <td align="left"><p>権限なし</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>管理者</p></td>
    <td align="left"><p>フルコントロール</p></td>
    <td align="left"><p>このフォルダー、サブフォルダー、ファイル</p></td>
    </tr>
    </tbody>
    </table>

     

4.  [ **OK** ] をクリックしてダイアログボックスを閉じます。

## 関連トピック


[UE-V 1.0 の展開](deploying-ue-v-10.md)

[UE-V 1.0 のカスタム テンプレートの展開計画](planning-for-custom-template-deployment-for-ue-v-10.md)

 

 





