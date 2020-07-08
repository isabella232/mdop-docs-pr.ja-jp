---
title: MBAM 2.5 クライアントの前提条件
description: MBAM 2.5 クライアントの前提条件
author: dansimp
ms.assetid: fc230679-9c84-4b99-a77c-bae7e7bf8145
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/23/2017
ms.openlocfilehash: ac5e211e5ea038f47db3d5e68155eb5af38aa231
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826967"
---
# MBAM 2.5 クライアントの前提条件


MBAM クライアントソフトウェアをエンドユーザーのコンピューターにインストールする前に、環境とクライアントコンピューターが次の前提条件を満たしていることを確認します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">受講</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>エンタープライズドメインには、少なくとも1つの Windows Server 2008 (またはそれ以降) のドメインコントローラーが含まれている必要があります。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>クライアントコンピューターは、エンタープライズイントラネットにログオンしている必要があります。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 7 クライアントコンピューターのみ: 各クライアントには、トラステッドプラットフォームモジュール (TPM) 機能 (TPM 1.2 以降) が必要です。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8.1、Windows 10 RTM、または Windows 10 バージョン1511クライアントコンピューターのみ: MBAM で TPM 回復キーを保存および管理できるようにする場合は、TPM 自動プロビジョニング機能を無効にして、mbam を TPM の所有者として設定してから、MBAM を展開する必要があります。</p>
<p>MBAM 2.5 SP1 でのみ、TPM 自動プロビジョニングをオフにする必要はありませんが、tpm グループポリシーオブジェクトが Active Directory へのエスクロー TPM OwnerAuth に設定されていないことを確認する必要があります。</p></td>
<td align="left"><p><a href="mbam-25-security-considerations.md#bkmk-tpm" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md#bkmk-tpm)">MBAM 2.5 のセキュリティに関する考慮事項</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 10 バージョン1607以降では、Windows のみが TPM の所有権を取得できます。 Addiiton では、TPM のプロビジョニング時に Windows は TPM 所有者パスワードを保持しません。</p>
<p>MBAM 2.5 SP1 では、自動プロビジョニングを有効にする必要があります。</p>
</p></td>
<td align="left"><p><a href="https://technet.microsoft.com/itpro/windows/keep-secure/change-the-tpm-owner-password" data-raw-source="[TPM owner password](https://technet.microsoft.com/itpro/windows/keep-secure/change-the-tpm-owner-password)"> </a> 詳細については、TPM 所有者パスワードを参照してください。
</p></td>
</tr>
<tr class="even">
<td align="left"><p>TPM チップは BIOS で有効になっていて、オペレーティングシステムから resettable されている必要があります。</p></td>
<td align="left"><p>詳細については、BIOS のマニュアルを参照してください。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>コンピューターのハードディスクには、少なくとも2つのパーティションが必要であり、NTFS ファイルシステムでフォーマットされている必要があります。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>コンピューターのハードディスクには、TPM と互換性のある BIOS と、コンピューターの起動時に USB デバイスをサポートしている BIOS が含まれている必要があります。</p></td>
<td align="left"><div class="alert">
<strong>注</strong><br/><p>キーボード、ビデオ、マウスが直接接続されていて、キーボード、ビデオ、マウス (KVM) スイッチで管理されていないことを確認します。 KVM スイッチでは、コンピュータの物理機能がハードウェアの物理的な存在を検出してしまう可能性があります。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>プロキシを使っている場合は、システムコンテキストでそのプロキシが表示されている必要があります。 MBAM は、ユーザーコンテキストではなく、システムコンテキストで実行されます。</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



**重要**  
MBAM で BitLocker を使用していた場合は、MBAM をインストールして、既存の TPM 情報を使うことができます。




## 関連トピック


[MBAM 2.5 がサポートされる構成](mbam-25-supported-configurations.md)

[MBAM 2.5 の展開計画](planning-to-deploy-mbam-25.md)


## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。






