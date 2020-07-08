---
title: MED-V ワークスペースの仮想マシンのセットアップを構成する方法
description: MED-V ワークスペースの仮想マシンのセットアップを構成する方法
author: dansimp
ms.assetid: 50bbf58b-842c-4b63-bb93-3783903f6c7d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d0ba24f0e9aa5befeaf385acf06273a53feaae29
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827074"
---
# MED-V ワークスペースの仮想マシンのセットアップを構成する方法


すべての仮想マシンセットアップ構成設定は、[ **VM のセットアップ**] タブの**ポリシー**モジュールで構成されます。

## 永続的な MED-V ワークスペースの仮想マシンセットアップを構成する方法


**永続的な MED-V ワークスペースの仮想マシンのセットアップを構成するには**

1.  構成する永続的な MED ワークスペースをクリックします。

2.  [**永続的な VM のセットアップ**] セクションで、次の表の説明に従ってプロパティを構成します。

    **注**  
    永続的な VM のセットアッププロパティは、持続的な MED-V ワークスペースでのみ有効になります。



3.  [**ポリシー** ] メニューで、[**コミット**] を選びます。

**永続的な VM のセットアッププロパティ**

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
<td align="left"><p>VM セットアップを実行する</p></td>
<td align="left"><p>このチェックボックスをオンにすると、MED-V ワークスペースを初めて実行したときにセットアップスクリプトが実行されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>スクリプトエディター</p></td>
<td align="left"><p>[] をクリックして、セットアップスクリプトを構成します。 詳細については、「 <a href="how-to-set-up-script-actions.md" data-raw-source="[How to Set Up Script Actions](how-to-set-up-script-actions.md)"> スクリプト操作を設定する方法」を参照してください </a> 。</p>
<div class="alert">
<strong>注</strong><br/><p>このボタンは <strong> 、[VM のセットアップスクリプトを実行] が選択されている場合にのみ有効です </strong> 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>スクリプトの実行時に表示されるメッセージ</p></td>
<td align="left"><p>スクリプトの実行中に表示されるメッセージ。 空白のままにすると、既定のメッセージが表示されます。</p>
<div class="alert">
<strong>注</strong><br/><p>このフィールドは <strong> 、VM セットアップスクリプトを実行した場合にのみ有効になり </strong> ます。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## Revertible MED-V ワークスペースの仮想マシンセットアップを構成する方法


**Revertible MED-V ワークスペースの仮想マシンのセットアップを構成するには**

1.  構成する revertible MED ワークスペースをクリックします。

2.  **REVERTIBLE VM のセットアップ**セクションで、次の表の説明に従ってプロパティを構成します。

    **注**  
    Revertible VM のセットアッププロパティは、revertible MED ワークスペースに対してのみ有効になります。



3.  [**ポリシー** ] メニューで、[**コミット**] を選びます。

**Revertible VM のセットアッププロパティ**

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
<td align="left"><p>コンピューター名パターンに基づいて VM の名前を変更する</p></td>
<td align="left"><p>このチェックボックスをオンにすると、同じ MED-V ワークスペースを使用して複数のコンピューターを区別できるように、MED-V ワークスペースを使用して、各コンピューターに一意の名前を割り当てることができます。</p>
<p>コンピューターのイメージ名の構成の詳細については、「 <a href="how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md" data-raw-source="[How to Configure VM Computer Name Pattern Properties](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)"> VM コンピューター名パターンプロパティを構成する方法」を参照してください </a> 。</p></td>
</tr>
</tbody>
</table>



## 関連トピック


[MED-V 管理コンソールのユーザー インターフェイスの使用](using-the-med-v-management-console-user-interface.md)

[MED-V ワークスペースの作成](creating-a-med-v-workspacemedv-10-sp1.md)

[仮想マシンの構成の例](examples-of-virtual-machine-configurationsv2.md)









