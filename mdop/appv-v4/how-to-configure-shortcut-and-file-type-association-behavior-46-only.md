---
title: ショートカットとファイルの種類の関連付け動作を構成する方法
description: ショートカットとファイルの種類の関連付け動作を構成する方法
author: dansimp
ms.assetid: d6fd1728-4de6-4066-b36b-d4837d593d40
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 84e3e0cdd43cfc26cf56f1b5ac72560b1c702ae6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817914"
---
# ショートカットとファイルの種類の関連付け動作を構成する方法


ショートカットとファイルの種類の関連付け (FTA) 発行ポリシーは、発行用の XML ファイルによって定義および制御されます。このファイルは発行サーバーによって公開されます。 クライアントはこの情報を受け取ると、アイコンや FTAs などのアプリケーションに関する新たに公開されたデータを追加します。 次に、古い発行データを削除します。

App-v バージョン4.6 では、管理者がこの動作を制御できるように、2つのレジストリキー値が定義されています。 既定では、クライアントコンソールを使用してローカルで作成されたショートカットは保持されるようになりました。

## ショートカットと FTA の動作を変更する方法


クライアント構成レジストリキー "FileTypePolicy" と "ShortcutPolicy" には、2つの新しい DWORD レジストリ値が定義されています。 これらの DWORD レジストリ値は既定では存在しませんが、手動で追加することができます。 構成レジストリキーは、HKEY \ _LOCAL \ _MACHINE ¥¥¥ \ [Wow6432Node\\\] の [\] にあります (\\ 4)。

次の表では、次の4つのポリシー値が定義されています。これらはどちらのレジストリキー値にも適用されます。 次の一覧は、レジストリ設定の数値と、発行更新操作のファイルの種類またはショートカットに適用される動作を示しています。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>名前</p></td>
<td align="left"><p>型</p></td>
<td align="left"><p>データ (例)</p></td>
<td align="left"><p>説明</p></td>
</tr>
<tr class="even">
<td align="left"><p>FileTypePolicy</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>Default = 0x2 (App-v 4.6)</p></td>
<td align="left"><p>(0x0) – "ClientOnly"-同じ公開情報ソースから既存のアイテムを削除し、ローカルに追加されたアイテムのみを残します。</p>
<p>(0x1) – "ServerOnly"-同じ公開情報ソースとローカルに追加されたすべてのアイテムから古いアイテムを削除し、新しいアイテムを追加します。</p>
<p>(0x2) – "ClientAndServer"-同じ公開情報ソースから古いアイテムを削除し、アイテムをローカルに追加したままにして、新しいアイテムを追加します (App-v 4.6 の場合は既定値になります)。</p>
<p>(0x3) – "NoChange"-ファイルの種類またはショートカットに変更を加えない</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ShortcutPolicy</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>Default = 0x2</p></td>
<td align="left"><p>(0x0) – "ClientOnly"-同じ公開情報ソースから既存のアイテムを削除し、アイテムをローカルに追加したままにします。</p>
<p>(0x1) – "ServerOnly"-同じ公開情報ソースとローカルに追加されたすべてのアイテムから古いアイテムを削除し、新しいアイテムを追加します。</p>
<p>(0x2) – "ClientAndServer"-同じ公開情報ソースから古いアイテムを削除し、アイテムをローカルに追加したままにして、新しいアイテムを追加します (存在しない場合は既定値)。</p>
<p>(0x3) – "NoChange"-ファイルの種類またはショートカットに変更を加えない</p></td>
</tr>
</tbody>
</table>

 

**注** テキスト値は、発行 XML ファイルの XML 属性の値を参照します。カスタム HTTP 発行ソリューションを実装している場合は、これらの値を手動で設定できます。

 

 

 





