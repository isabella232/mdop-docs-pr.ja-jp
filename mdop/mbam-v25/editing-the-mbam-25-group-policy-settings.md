---
title: MBAM 2.5 グループ ポリシー設定の編集
description: MBAM 2.5 グループ ポリシー設定の編集
author: dansimp
ms.assetid: a50b6b0c-6818-4419-8447-d0520a533dba
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0f6d180cba6dc721ff7de1607d57f90184303d88
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812595"
---
# MBAM 2.5 グループ ポリシー設定の編集


Microsoft BitLocker の管理と監視 (MBAM) を正常に展開するには、次のことを行う必要があります。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスク</th>
<th align="left">詳細情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MBAM 2.5 グループポリシーテンプレートをコピーします。</p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)">MBAM 2.5 グループ ポリシー テンプレートのコピー</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM の実装で使用するグループポリシーオブジェクト (Gpo) を決定します。 組織のニーズに応じて、追加のグループポリシー設定を構成する必要がある場合があります。</p></td>
<td align="left"><p><a href="planning-for-mbam-25-group-policy-requirements.md" data-raw-source="[Planning for MBAM 2.5 Group Policy Requirements](planning-for-mbam-25-group-policy-requirements.md)">MBAM 2.5 の計画グループポリシー要件 </a> – gpo の説明が含まれています。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>組織のグループポリシー設定を設定します。</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

**重要** **BitLocker ドライブ暗号化**ノードのグループポリシー設定を変更しないようにします。または、mbam が正しく動作しません。 [ **MDOP mbam (BitLocker Management)** ] ノードでグループポリシー設定を構成すると、mbam が自動的に**bitlocker ドライブ暗号化**設定を構成します。

 

**MBAM クライアントのグループポリシー設定を編集するには**

1.  MBAM グループポリシーテンプレートがインストールされているコンピューターで、MBAM サービスが有効になっていることを確認します。

2.  Mbam グループポリシーテンプレートがインストールされているコンピューターで、グループポリシー管理コンソール (GPMC) または Microsoft Advanced グループポリシー管理の mdop 製品を使用して、**コンピューター構成** &gt; **ポリシー** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **MDOP mbam (BitLocker 管理)** を選択します。

3.  クライアントコンピューターで MBAM クライアントサービスを有効にするために必要なグループポリシー設定を編集します。 次の表のポリシーごとに、[**ポリシーグループ**] を選択し、目的の**ポリシー**をクリックして、設定を構成します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">ポリシーグループ</th>
    <th align="left">ポリシー</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>クライアントの管理</p></td>
    <td align="left"><p>MBAM サービスを設定する</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>オペレーティングシステムドライブ</p></td>
    <td align="left"><p>オペレーティングシステムドライブの暗号化の設定</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>リムーバブルドライブ</p></td>
    <td align="left"><p>リムーバブルドライブでの BitLocker の使用を制御する</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>固定ドライブ</p></td>
    <td align="left"><p>固定ドライブでの BitLocker の使用を制御する</p></td>
    </tr>
    </tbody>
    </table>

     

## 関連トピック


[MBAM 2.5 グループ ポリシー要件の計画](planning-for-mbam-25-group-policy-requirements.md)

[MBAM 2.5 グループ ポリシー テンプレートのコピー](copying-the-mbam-25-group-policy-templates.md)

 
## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。
 





