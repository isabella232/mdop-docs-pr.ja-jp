---
title: Administration and Monitoring Web サイトの使用方法
description: Administration and Monitoring Web サイトの使用方法
author: dansimp
ms.assetid: bb96a4e8-d4f4-4e6f-b7db-82d96998bfa6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9b9597e29a5a7a6236cb351d8d6d1f682edce3cf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813043"
---
# Administration and Monitoring Web サイトの使用方法


ヘルプデスクとも呼ばれる管理と監視の Web サイトは、BitLocker ドライブ暗号化の管理インターフェイスです。 次のセクションで説明するように、この web サイトを使用して、レポートの確認、エンドユーザーのドライブの回復、エンドユーザーの TPMs の管理を行うことができます。

**注** スタンドアロントポロジで MBAM を使用している場合は、管理と監視の Web サイトからすべてのレポートを表示します。 Configuration Manager の統合トポロジを使用している場合は、管理と監視の Web サイトから引き続き表示される回復監査レポートを除き、すべてのレポートを Configuration Manager で表示します。 レポートの詳細については、「 [MBAM 2.5 による BitLocker 準拠の監視と報告](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)」を参照してください。

 

## 管理と監視の Web サイトを使用するために必要な役割


管理と監視の Web サイトの特定の領域にアクセスするには、次のいずれかのロールを持っている必要があります。これらは、Active Directory で作成したグループです。 これらのグループには任意の名前を使用できます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Account</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MBAM Advanced ヘルプデスクユーザー</p></td>
<td align="left"><p>管理と監視の Web サイトのすべての領域へのアクセスを提供します。 このロールを持っているユーザーは、エンドユーザーがドライブを回復するときに、エンドユーザーのドメインとユーザー名ではなく、回復キーのみを入力します。 MBAM ヘルプデスクユーザーグループと MBAM Advanced ヘルプデスクユーザーグループの両方のメンバーである場合、MBAM Advanced ヘルプデスクのユーザーグループの権限は、MBAM ヘルプデスクのユーザーグループの権限よりも優先されます。</p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM ヘルプデスクユーザー</p></td>
<td align="left"><p>管理と監視の Web サイトの TPM およびドライブの回復領域へのアクセスを提供します。 この役割を持つユーザーは、いずれかの領域を使用する場合は、エンドユーザーのドメインとアカウント名を含むすべてのフィールドに入力する必要があります。</p>
<p>MBAM ヘルプデスクユーザーグループと MBAM Advanced ヘルプデスクユーザーグループの両方のメンバーである場合、MBAM Advanced ヘルプデスクのユーザーグループの権限は、MBAM ヘルプデスクのユーザーグループの権限よりも優先されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MBAM レポートユーザー</p></td>
<td align="left"><p><strong> </strong> 管理と監視の web サイトの [レポート] 領域にあるレポートへのアクセスを提供します。</p></td>
</tr>
</tbody>
</table>

 

## 管理と監視の Web サイトで実行できるタスク


次の表は、管理と監視の Web サイトで実行できるタスクの概要と、各タスクに関する詳細情報へのリンクを示しています。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスク</th>
<th align="left">タスクにアクセスする Web サイトの領域</th>
<th align="left">説明</th>
<th align="left">詳細情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>レポートの表示</p></td>
<td align="left"><p>レポート</p></td>
<td align="left"><p>レポートを実行して、BitLocker の使用率、コンプライアンス、およびキー回復アクティビティを監視することができます。 レポートには、企業のコンプライアンス、個々のコンピューター、特定のコンピューターの回復キーまたは TPM OwnerAuth パッケージを要求したユーザーに関するデータが用意されています。</p></td>
<td align="left"><p><a href="viewing-mbam-25-reports-for-the-stand-alone-topology.md" data-raw-source="[Viewing MBAM 2.5 Reports for the Stand-alone Topology](viewing-mbam-25-reports-for-the-stand-alone-topology.md)">MBAM 2.5 レポートの表示 (スタンドアロン トポロジ)</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>紛失または盗難されたコンピューターの BitLocker 暗号化の状態を確認する</p></td>
<td align="left"><p>レポート</p></td>
<td align="left"><p>コンピューターが紛失したり盗まれたりした場合に、ボリュームが暗号化されていたかどうかを確認します。</p></td>
<td align="left"><p><a href="how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-25.md" data-raw-source="[How to Determine BitLocker Encryption State of Lost Computers](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-25.md)">紛失したコンピューターの BitLocker 暗号化の状態を確認する方法</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>紛失したドライブを回復する</p></td>
<td align="left"><p>ドライブの回復</p></td>
<td align="left"><p>次のようなドライブを回復します。</p>
<ul>
<li><p>回復モードの場合</p></li>
<li><p>が移動されました</p></li>
<li><p>は破損しています</p></li>
</ul></td>
<td align="left"><ul>
<li><p><a href="how-to-recover-a-drive-in-recovery-mode-mbam-25.md" data-raw-source="[How to Recover a Drive in Recovery Mode](how-to-recover-a-drive-in-recovery-mode-mbam-25.md)">回復モードでドライブを回復する方法</a></p></li>
<li><p><a href="how-to-recover-a-moved-drive-mbam-25.md" data-raw-source="[How to Recover a Moved Drive](how-to-recover-a-moved-drive-mbam-25.md)">移動されたドライブを回復する方法</a></p></li>
<li><p><a href="how-to-recover-a-corrupted-drive-mbam-25.md" data-raw-source="[How to Recover a Corrupted Drive](how-to-recover-a-corrupted-drive-mbam-25.md)">破損しているドライブを回復する方法</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>TPM ロックアウトをリセットする</p></td>
<td align="left"><p>TPM を管理する</p></td>
<td align="left"><p>MBAM クライアントによって収集された TPM データへのアクセスを提供します。 TPM ロックアウトでは、管理と監視の Web サイトを使って、必要なパスワードファイルを取得し、TPM のロックを解除します。</p></td>
<td align="left"><p><a href="how-to-reset-a-tpm-lockout-mbam-25.md" data-raw-source="[How to Reset a TPM Lockout](how-to-reset-a-tpm-lockout-mbam-25.md)">TPM ロックアウトをリセットする方法</a></p></td>
</tr>
</tbody>
</table>

 


## 関連トピック


[MBAM 2.5 での BitLocker 管理の実行](performing-bitlocker-management-with-mbam-25.md)

 

## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





