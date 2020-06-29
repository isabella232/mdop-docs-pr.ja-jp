---
title: PowerShell を使用した MBAM 1.0 の管理
description: PowerShell を使用した MBAM 1.0 の管理
author: dansimp
ms.assetid: 3bf2eca5-4ab7-4e84-9e80-c0c7d709647b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3547bee9b2efc58252bb6f0a1cb0aa4c484e4e80
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825137"
---
# PowerShell を使用した MBAM 1.0 の管理


Microsoft BitLocker の管理と監視 (MBAM) には、次の Windows PowerShell コマンドレットのセットが用意されています。 管理者は、これらの PowerShell コマンドレットを使って、MBAM 管理 web サイトではなく、コマンドプロンプトからさまざまな MBAM サーバータスクを実行することができます。

## PowerShell を使用して MBAM を管理する方法


MBAM を管理するには、ここで説明した PowerShell コマンドレットを使用します。

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
<td align="left"><p>追加-Mbamハードウェアタイプ</p></td>
<td align="left"><p>MBAM ハードウェアインベントリに新しいハードウェアモデルを追加します。 このコマンドレットでは、BitLocker ドライブ暗号化のハードウェアがサポートされているかどうかを指定することもできます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Get-MbamBitLockerRecoveryKey</p></td>
<td align="left"><p>ユーザーがコンピューターまたは暗号化されたドライブのロックを解除できるようにする MBAM 回復キーを要求します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ダウンロード-Mbamハードウェアタイプ</p></td>
<td align="left"><p>ハードウェアモデルに互換性があるか、BitLocker ドライブ暗号化との互換性がないかを示すデータを含むマスターハードウェアインベントリを取得します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Get-MbamTPMOwnerPassword</p></td>
<td align="left"><p>ユーザーが TPM (Trusted Platform Module) アクセスを管理するための TPM 所有者パスワードを提供します。 TPM がロックされている場合、ユーザーは PIN を受け入れなくなります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>インストール-Mbam</p></td>
<td align="left"><p>高度なグループポリシー、暗号化、キーの回復、コンプライアンスレポートのツールを提供する MBAM 機能をインストールします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>削除-Mbamハードウェアタイプ</p></td>
<td align="left"><p>ハードウェアインベントリからハードウェアモデルを削除します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Set-Mbamハードウェアタイプ</p></td>
<td align="left"><p>マスターハードウェアインベントリを管理することで、ハードウェアモデルが BitLocker 暗号化を実行できるかどうかを指定します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>アンインストール-Mbam</p></td>
<td align="left"><p>高度なポリシー、暗号化、キーの回復、コンプライアンスレポートのツールを提供する、以前にインストールされた MBAM 機能を削除します。</p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[MBAM 1.0 の操作](operations-for-mbam-10.md)

 

 





