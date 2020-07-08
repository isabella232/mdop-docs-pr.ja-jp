---
title: Windows PowerShell を使用した MBAM 2.5 の管理
description: Windows PowerShell を使用した MBAM 2.5 の管理
author: dansimp
ms.assetid: 64668e76-2cba-433d-8d2d-50df0a4b2997
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 8db305bfbdf79723da2b186dd5cc00406a4089cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812738"
---
# Windows PowerShell を使用した MBAM 2.5 の管理


このトピックでは、ユーザーがロックアウトされたときのコンピューターまたはドライブの回復に関連する、Microsoft BitLocker 管理と監視 (MBAM) 用の Windows PowerShell コマンドレットについて説明します。

MBAM サーバー機能を構成するために使用するコマンドレットについては、「 [Windows PowerShell を使用して mbam 2.5 サーバー機能を構成](configuring-mbam-25-server-features-by-using-windows-powershell.md)する」を参照してください。

## <a href="" id="cmdlets-for-recovering-computers-or-drives-that-are-managed-by-mbam-"></a>MBAM で管理されているコンピューターまたはドライブを回復するためのコマンドレット


MBAM で管理されているコンピューターまたはドライブを回復するには、次の Windows PowerShell コマンドレットを使用します。

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
<td align="left"><p>Get-MbamBitLockerRecoveryKey</p></td>
<td align="left"><p>ユーザーがコンピューターまたは暗号化されたドライブのロックを解除できるようにする MBAM 回復キーを要求します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Get-MbamTPMOwnerPassword</p></td>
<td align="left"><p>Tpm がロックアウトされているときに、トラステッドプラットフォームモジュール (TPM) のロックを解除するために使うことができる TPM 所有者パスワードをユーザーに提供します。これにより、tpm がロックアウトされ、PIN が受け入れられなくなります。</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="---------mbam-cmdlet-help"></a> MBAM コマンドレットのヘルプ


MBAM コマンドレットの Windows PowerShell ヘルプは、次の形式で利用できます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Windows PowerShell ヘルプの形式</th>
<th align="left">詳細情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows PowerShell コマンドプロンプトで、「 <strong> Get-ヘルプ </strong> &lt; <em> コマンドレット」と入力します。</em>&gt;</p></td>
<td align="left"><p>最新の Windows PowerShell コマンドレットをアップロードするには、「 <a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"> Windows Powershell を使用して MBAM 2.5 サーバー機能を構成する」の指示に従います。</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>Web ページとしての TechNet の場合</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393498" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393498">https://go.microsoft.com/fwlink/?LinkId=393498</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Word の .docx ファイルとしてダウンロードセンターで</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393497" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393497">https://go.microsoft.com/fwlink/?LinkId=393497</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>.Pdf ファイルとしてダウンロードセンターで</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393499" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393499">https://go.microsoft.com/fwlink/?LinkId=393499</a></p></td>
</tr>
</tbody>
</table>

 



## 関連トピック


[MBAM 2.5 機能の管理](administering-mbam-25-features.md)

[Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成](configuring-mbam-25-server-features-by-using-windows-powershell.md)

 

## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





