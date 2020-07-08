---
title: コントロール パネルの [BitLocker 暗号化のオプション] 項目と [BitLocker ドライブ暗号化] 項目について
description: コントロール パネルの [BitLocker 暗号化のオプション] 項目と [BitLocker ドライブ暗号化] 項目について
author: dansimp
ms.assetid: f8a01cc2-0c77-48b9-8351-8194e80b0cf8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 739b65680ebfdf19f006ee8f3079f7c7e602f697
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812771"
---
# コントロール パネルの [BitLocker 暗号化のオプション] 項目と [BitLocker ドライブ暗号化] 項目について


このトピックでは、 **Bitlocker 暗号化オプション**と**bitlocker ドライブ暗号化**コントロールパネルの項目について説明し、次の内容について説明します。

-   アイテムの作成方法

-   実行できるタスク

-   **BitLocker を管理**するショートカットメニューが表示されていて、非表示になっているかどうか、既定で表示されるように設定する方法を教えてください。

## BitLocker 暗号化オプションと BitLocker ドライブ暗号化コントロールパネル項目


次の表は、各コントロールパネルの項目から実行できるタスクと、それらの項目がどのように作成されるかを示しています。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">BitLocker 暗号化オプション (MBAM)</th>
<th align="left">BitLocker ドライブ暗号化 (Windows)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>実行できるタスク</p></td>
<td align="left"><ul>
<li><p>PIN またはパスワードを変更する</p></li>
<li><p>ドライブの暗号化の状態を確認する</p></li>
<li><p>TPM 管理コンソールを開く</p></li>
<li><p>[BitLocker をオンにする]</p></li>
</ul></td>
<td align="left"><ul>
<li><p>ドライブの保護の中断</p></li>
<li><p>回復キーをバックアップする</p></li>
<li><p>PIN を変更する</p></li>
<li><p>ドライブの BitLocker をオフにする</p></li>
<li><p>ドライブに対して BitLocker を有効にする</p></li>
<li><p>TPM 管理コンソールを開く</p></li>
<li><p>ドライブの暗号化を解除する (MBAM クライアントがインストールされていない場合にのみ表示されます)</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>コントロールパネル項目の作成方法</p></td>
<td align="left"><p>MBAM クライアントをインストールすると、コントロールパネルで作成されます。 この項目は非表示にすることはできません。</p>
<div class="alert">
<strong>注</strong><br/><p>この項目は、既定の BitLocker ドライブ暗号化コントロールパネルの項目に加えて、置き換えられることはありません。</p>
</div>
<div>

</div></td>
<td align="left"><p>コントロールパネルでは、既定で Windows オペレーティングシステムの一部として表示されますが、非表示にすることもできます。</p>
<p>非表示にするには、「 <a href="hiding-the-default-bitlocker-drive-encryption-item-in-control-panel-mbam-25.md" data-raw-source="[Hiding the Default BitLocker Drive Encryption Item in Control Panel](hiding-the-default-bitlocker-drive-encryption-item-in-control-panel-mbam-25.md)"> コントロールパネルの既定の BitLocker ドライブ暗号化項目を非表示にする」を参照してください </a> 。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="-manage-bitlocker--shortcut-menu"></a>[BitLocker の管理] ショートカットメニュー


次の表では、MBAM クライアントがインストールされているかどうかによって [ **BitLocker の管理**] ショートカットメニューの違いを説明します。 "ショートカットメニュー" という用語は、Windows エクスプローラーでドライブを右クリックすると表示されるオプションを指します。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">MBAM クライアントをインストールする場合</th>
<th align="left">MBAM クライアントがインストールされていない場合</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ショートカットメニューの表示</p></td>
<td align="left"><p>[BitLocker の管理] オプションが非表示になっています。</p>
<p>ショートカットメニューに [BitLocker の管理] オプションが表示されるようにするには、ドライブの暗号化を解除するオプションが表示されます。次のレジストリキーを削除します。</p>
<pre class="syntax" space="preserve"><code>HKEY_CLASSES_ROOT\Drive\Shell\manage-bde \REG_SZ LegacyDisable</code></pre></td>
<td align="left"><p>ショートカットメニューに [BitLocker の管理] オプションが表示されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ユーザーが実行できる操作</p></td>
<td align="left"><p>ショートカットが非表示になっている場合、ユーザーは BitLocker ドライブ暗号化コントロールパネルの項目を開くことができますが、ドライブの暗号化解除オプションは利用できません。</p></td>
<td align="left"><p>ショートカットが表示されている状態で、[BitLocker の管理] オプションを選択すると、 <strong> </strong> Bitlocker ドライブ暗号化コントロールパネルの項目が開きます。これにより、ドライブの暗号化を解除するオプションが表示されます。</p></td>
</tr>
</tbody>
</table>




## 関連トピック


[MBAM 2.5 機能の管理](administering-mbam-25-features.md)



## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





