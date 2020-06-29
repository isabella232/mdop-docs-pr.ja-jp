---
title: Application Virtualization のシーケンスウィザードの [詳細オプション] ページ
description: Application Virtualization のシーケンスウィザードの [詳細オプション] ページ
author: dansimp
ms.assetid: 2c4c5d95-d55e-463d-a851-8486f6a724f2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 716fa27852f1cadfebec31a267ce1b9b581b8ff7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819597"
---
# Application Virtualization のシーケンスウィザードの [詳細オプション] ページ


Application Virtualization (App-v) シーケンスウィザードの **[詳細オプション**] ページを使用して、インストールするアプリケーションの詳細オプションを指定します。 このページには、次の表に示す要素が含まれています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名前</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>ブロックサイズ</strong></p></td>
<td align="left"><p>ネットワーク経由でストリーミングしたときに、SFT ファイルが分割されるブロックのサイズを指定する場合に使用します。 すべてのブロックは指定したサイズと等しくなります。ただし、最後のブロックが指定よりも小さくなっている可能性があります。 次のいずれかの値を選びます。</p>
<ul>
<li><p><strong>4 KB</strong></p></li>
<li><p><strong>16 KB</strong></p></li>
<li><p><strong>32 KB</strong></p></li>
<li><p><strong>64 KB</strong></p></li>
</ul>
<div class="alert">
<strong>注</strong><br/><p>ブロックサイズを選択するときは、SFT ファイルのサイズとネットワーク帯域幅を考慮します。 ブロックサイズが小さいファイルは、ネットワーク上でのストリーミングには時間がかかりますが、帯域幅の消費が少なくなります。 ブロックサイズが大きいファイルは、より速くストリーミングされる可能性がありますが、より多くのネットワーク帯域幅を使用します。 実験を通じて、ネットワーク上のストリーミングアプリケーションに最適なブロックサイズを見つけることができます。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><strong>監視中に Microsoft Update を有効にする</strong></p></td>
<td align="left"><p>シーケンスウィザード&#39;s 監視段階での Microsoft 更新プログラムのインストールを有効にします。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Dll を再配置する</strong></p></td>
<td align="left"><p>サポートされているダイナミックリンクライブラリを、RAM 内の連続した領域にマッピングし、メモリを節約し、パフォーマンスを向上させることができます。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>戻る</strong></p></td>
<td align="left"><p>シーケンスウィザード&#39;s の前のページにアクセスします。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Next</strong></p></td>
<td align="left"><p>シーケンスウィザード&#39;s の次のページにアクセスします。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Cancel</strong></p></td>
<td align="left"><p>シーケンスウィザードの操作を終了します。</p></td>
</tr>
</tbody>
</table>



\ [テンプレートトークンの値 \]

[App-v シーケンスウィザード] の **[詳細オプション**] ページを使用して、順序を設定するアプリケーションの詳細オプションを指定します。 このページには、次の表に示す要素が含まれています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名前</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>監視中に Microsoft Update を実行することを許可する</strong></p></td>
<td align="left"><p>アプリケーションシーケンスの監視フェーズ中にソフトウェアの更新をアプリケーションに適用するかどうかを指定します。 このオプションは、アプリケーションのインストールを正常に完了するために更新プログラムが必要な場合に役立ちます。 既定では、このオプションは選択されていません。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Dll を再配置する</strong></p></td>
<td align="left"><p>サポートされているダイナミックリンクライブラリの、RAM 内の連続した領域への再マッピングを有効にします。 このオプションを選ぶと、メモリの管理やアプリケーションのパフォーマンスの向上に役立ちます。 既定では、このオプションは選択されていません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>戻る</strong></p></td>
<td align="left"><p>ウィザードの前のページに移動します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Next</strong></p></td>
<td align="left"><p>ウィザードの次のページに移動します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Cancel</strong></p></td>
<td align="left"><p>設定を破棄してウィザードを終了します。</p></td>
</tr>
</tbody>
</table>



\ [テンプレートトークンの値 \]

## 関連トピック


[シーケンス ウィザード](sequencing-wizard.md)









