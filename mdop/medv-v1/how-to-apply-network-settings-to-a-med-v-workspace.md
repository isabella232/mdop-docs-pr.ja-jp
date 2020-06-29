---
title: MED-V ワークスペースにネットワーク設定を適用する方法
description: MED-V ワークスペースにネットワーク設定を適用する方法
author: dansimp
ms.assetid: 641f46b3-a56f-478a-823b-1d90aa1716b3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5a13227518945e74be9e4b3772af97eadbce3fc4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826517"
---
# MED-V ワークスペースにネットワーク設定を適用する方法


管理者は、各 MED-V ワークスペースのネットワーク設定を定義できます。

[**ネットワーク**] タブの**ポリシー**モジュールで、すべてのネットワーク設定を構成します。

**MED-V ワークスペースにネットワーク設定を適用するには**

1.  構成する MED-V ワークスペースをクリックします。

2.  [**ネットワーク**] ウィンドウで、次の表の説明に従って設定を構成します。

3.  [**ポリシー** ] メニューで、[**コミット**] を選びます。

**MED ワークスペースのネットワークプロパティ**

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
<td align="left"><p>TCP/IP のプロパティ</p></td>
<td align="left"><ul>
<li><p><strong>ホストの IP アドレス (NAT) を使用 </strong> —ワークスペースでは、NAT を使って、発信トラフィック用にホストの ip を共有します。</p></li>
<li><p><strong>ホスト (ブリッジ) とは異なる IP アドレスを使用します </strong> 。 med-v ワークスペースには独自のネットワークアドレスが割り当てられます。通常は DHCP 経由で取得します。</p></li>
</ul>
<p><strong>ホストコンピューターに複数のアダプターがある場合は、[複数のアダプターをワークスペースにマップ </strong> する] チェックボックスをオンにします。 ホストがさまざまなアダプターを使って異なるネットワーク間を移動する場合は、この構成を使用することをお勧めします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DNS サーバー</p></td>
<td align="left"><ul>
<li><p><strong>変更しない </strong> — med-v ワークスペース仮想マシン内で設定されている DNS 設定は変更されません。</p></li>
<li><p><strong>[Host の DNS アドレスを使用する] </strong> : med-v workspace の dns 設定は、ホストの設定と一致するように同期されます。 DNS の同期は動的です。 ホスト上で変更された場合は、MED-V ワークスペースで動的に変更されるように、ホストと定期的に同期されます。</p></li>
<li><p><strong>特定の DNS アドレスを使い </strong> ます。 med-v ワークスペースでは、指定されている特定の dns が使用されます。</p>
<p>" <strong> プライマリ" </strong> フィールドと "セカンダリ" フィールドに、 <strong> </strong> プライマリおよびセカンダリの DNS アドレスを入力します。</p>
<p>[ <strong> Host の dns アドレスを追加 </strong> する] チェックボックスをオンにして、構成済みの dns アドレスにホストを追加します。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>DNS サフィックスを割り当てる</p></td>
<td align="left"><ul>
<li><p><strong>次のサフィックスを割り当てる </strong> : 特定の DNS サフィックスを割り当てるには、このチェックボックスをオンにします。このボックスに、サフィックスを入力するか、カンマで区切った複数のサフィックスを入力します。</p></li>
<li><p><strong>[Host サフィックス </strong> の追加] — DNS アドレスにホストサフィックスを追加するには、このチェックボックスをオンにします。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[MED-V ワークスペースの作成](creating-a-med-v-workspacemedv-10-sp1.md)

[MED-V 管理コンソールのユーザー インターフェイスの使用](using-the-med-v-management-console-user-interface.md)

 

 





