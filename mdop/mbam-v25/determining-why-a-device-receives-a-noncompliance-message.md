---
title: デバイスがコンプライアンス非対応メッセージを受信する理由の特定
description: デバイスがコンプライアンス非対応メッセージを受信する理由の特定
author: dansimp
ms.assetid: 793df330-a0ee-4759-b53a-95618ac74428
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/22/2017
ms.openlocfilehash: ce1d344676ebf4328506228f1bfa87c76e8036f9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824574"
---
# デバイスがコンプライアンス非対応メッセージを受信する理由の特定


以下の違反コードは、WMI によって提供され、特定のデバイスが非準拠として MBAM によって報告される理由について説明します。

WMI の表示には、推奨される方法を使用できます。 PowerShell を使用している場合は、 `gwmi -class mbam_volume -Namespace root\microsoft\mbam` powershell プロンプトから実行し、理由違反を検索します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コンプライアンス以外のコード</th>
<th align="left">準拠していない理由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>0</p></td>
<td align="left"><p>AES 256 ではない暗号強度。</p></td>
</tr>
<tr class="even">
<td align="left"><p>件</p></td>
<td align="left"><p>MBAM ポリシーでは、このボリュームは暗号化する必要がありますが、暗号化されません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>両面</p></td>
<td align="left"><p>MBAM ポリシーの場合、このボリュームは暗号化されないようにする必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>-</p></td>
<td align="left"><p>MBAM ポリシーでは、このボリュームは TPM プロテクターを使用する必要がありますが、そうではありません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>4d</p></td>
<td align="left"><p>MBAM ポリシーには、このボリュームで TPM + PIN プロテクターを使用する必要がありますが、そうではありません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>個</p></td>
<td align="left"><p>MBAM ポリシーでは、TPM コンピューター以外では準拠して報告できません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>=</p></td>
<td align="left"><p>ボリュームには TPM プロテクターがありますが、TPM は表示されません (BIOS で TPM を無効にした後に、回復キーを使用してブートしますか?)。</p></td>
</tr>
<tr class="even">
<td align="left"><p>日</p></td>
<td align="left"><p>MBAM ポリシーにはパスワードプロテクターを使用する必要がありますが、このボリュームにはありません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>個</p></td>
<td align="left"><p>MBAM ポリシーには、パスワード保護機能を使用せず、パスワード保護機能が含まれている必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ファイブ</p></td>
<td align="left"><p>MBAM ポリシーには、このボリュームで自動ロック解除プロテクターを使用する必要がありますが、どちらも指定されていません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>常用</p></td>
<td align="left"><p>MBAM ポリシーでは、このボリュームは自動ロック解除機能を使用しないが、1つだけである必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>折り</p></td>
<td align="left"><p>ポリシーの競合が検出されたため、MBAM がこのボリュームを準拠として報告できません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>以内</p></td>
<td align="left"><p>システムボリュームは、OS のボリュームを暗号化するために必要ですが、表示されません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>14</p></td>
<td align="left"><p>ボリュームの保護は一時停止されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>14</p></td>
<td align="left"><p>AutoUnlock unsafe (OS のボリュームが暗号化されている場合を除く)。</p></td>
</tr>
<tr class="even">
<td align="left"><p>マート</p></td>
<td align="left"><p>ポリシーには最低 cypher 強度が必要です。 XTS は AES-128 ビット、実際の cypher 強度はこれより弱くなります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>16</p></td>
<td align="left"><p>ポリシーには最低 cypher 強度が必要です。 XTS は AES-256 ビット、実際の cypher 強度はこれより弱くなります。</p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[MBAM 2.5 テクニカル リファレンス](technical-reference-for-mbam-25.md)

[Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成](configuring-mbam-25-server-features-by-using-windows-powershell.md)

 
## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。
 





