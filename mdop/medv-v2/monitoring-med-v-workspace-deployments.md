---
title: MED-V ワークスペースの展開の監視
description: MED-V ワークスペースの展開の監視
author: dansimp
ms.assetid: 5de0cb06-b8a9-48a5-b8b3-836954295765
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6ec4c7c85326e7945aa3d61b7f96872afe24fe37
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827214"
---
# MED-V ワークスペースの展開の監視


Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 の監視機能を使用すると、個々の MED-V ワークスペースに対してクエリを実行して、MED-V ワークスペースが展開された後で初めてエンタープライズ全体でセットアップが成功したかどうかを確認できます。 初回のセットアップが正常に完了するまでは、MED-V が使用可能な状態になっていないため、初回のセットアップの成否を監視することが重要です。

このセクションでは、初回セットアップ時の成功または失敗を監視するときに役立つ情報と指示について説明します。

## MED-V ワークスペースの展開を監視するには


監視機能は、組み込みのインプロセス Windows Management Instrumentation (WMI) プロバイダーで構成されています。これは、WMI クエリ言語を使って照会し、MED-V ワークスペース上のすべてのエンドユーザーに対して初めてセットアップするときの状態を検出することができます。

WMI プロバイダーは、Microsoft .Net Framework 3.5 から WMI プロバイダ拡張フレームワークを使って実装されています。 WMI プロバイダーは LocalService のコンテキストで実行され、\\ProgramData. には、初めてのセットアップ状態が安全に保存されます。

WMI プロバイダーは、 **root\\microsoft\\medv**名前空間に実装され、class **FTS \ _Status**を実装します。これにより、メソッド**setftsstate**が公開されます。 MED では、 **Setftsstate**を使って、初回のセットアップの状態を設定します。

このクラスには、次のプロパティが含まれています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">プロパティ</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>コンピューター</strong></p></td>
<td align="left"><p><strong>読み取り専用 </strong> プロパティ。このプロパティには、初回セットアップでプロビジョニングされたゲスト仮想マシンの名前が含まれます。 このキーには、ゲストが初めてセットアップに失敗したときに使用した名前が含まれています。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>StatusCode</strong></p></td>
<td align="left"><p><strong></strong>初めてセットアップに成功した場合は、0を含む読み取り専用プロパティ。 返されるその他の値は、ログに記録されるエラーのイベント ID に相当します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Time</strong></p></td>
<td align="left"><p>初めてセットアップが完了した UTC 時刻。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>ユーザー</strong></p></td>
<td align="left"><p>初めてのセットアップが実行されたユーザー。</p></td>
</tr>
</tbody>
</table>

 

次のコードは、 **FTS \ _Status**クラスを定義するマネージオブジェクト形式 (MOF) ファイルを示しています。

``` syntax
[dynamic: ToInstance, provider("MedvWmi, Version=2.0.258.0, Culture=neutral, PublicKeyToken=14986c3f172d1c2c")]
class FTS_Status
{
[read, key] string User;
[read] string Machine;
[read] sint32 StatusCode;
[read] datetime Time;
[static, implemented] void SetFtsState([in] sint32 statusCode, [in] string machine);
};
```

最も重要なのは、初回のセットアップが正常に完了していない MED-V のワークスペースであると考えられるため、最初にセットアップに失敗したユーザーのみを返すようにクエリを作成できます。たとえば、次のようにします。

``` syntax
Select * from FTS_Status where StatusCode != 0
```

この場合、監視機能によって、最初のセットアップに失敗した MED-V ワークスペースのリストが返されます。これは、エラーを解決するために適切な操作を実行するために使用できます。

## 関連トピック


[MED-V ワークスペースを監視する](monitor-med-v-workspaces.md)

[初回使用時のセットアップの設定を確認する方法](how-to-verify-first-time-setup-settings.md)

 

 





