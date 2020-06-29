---
title: PowerShell を使用した MBAM 2.0 の管理
description: PowerShell を使用した MBAM 2.0 の管理
author: dansimp
ms.assetid: d785a8df-0a8c-4d70-abd2-93a762b4f3de
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 736943e707b5d033b8ba6c26641393f02f0cdaf8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823504"
---
# PowerShell を使用した MBAM 2.0 の管理


Microsoft BitLocker の管理と監視 (MBAM) には、次の Windows PowerShell コマンドレットのセットが用意されています。 管理者は、これらの PowerShell コマンドレットを使用して、MBAM 管理 web サイトではなく、コマンドラインからさまざまな Microsoft BitLocker 管理および監視サーバータスクを実行することができます。

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
<td align="left"><p>インストール-Mbam</p></td>
<td align="left"><p>高度なポリシー、暗号化、キーの回復、コンプライアンスレポートを提供する MBAM 機能をインストールします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>アンインストール-Mbam</p></td>
<td align="left"><p>高度なポリシー、暗号化、キーの回復、コンプライアンスレポートのツールを提供する MBAM 機能を削除します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Get-MbamBitLockerRecoveryKey</p></td>
<td align="left"><p>ユーザーがコンピューターまたは暗号化されたドライブのロックを解除できるようにする MBAM 回復キーを要求します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Get-MbamTPMOwnerPassword</p></td>
<td align="left"><p>Tpm がロックアウトされているときに、トラステッドプラットフォームモジュール (TPM) のロックを解除するために使うことができる TPM 所有者パスワードをユーザーに提供します。これにより、tpm がロックアウトされ、PIN が受け入れられなくなります。</p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[MBAM 2.0 の操作](operations-for-mbam-20-mbam-2.md)

 

 





