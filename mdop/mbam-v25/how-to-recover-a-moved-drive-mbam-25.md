---
title: 移動されたドライブを回復する方法
description: 移動されたドライブを回復する方法
author: dansimp
ms.assetid: 0d38ce7e-bc64-473e-ae85-99b7099ca758
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 9e7e03846e0a94902b699377043237c651939a07
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823344"
---
# 移動されたドライブを回復する方法
このトピックでは、管理と監視の Web サイト (ヘルプデスクとも呼ばれます) を使用して、Microsoft BitLocker の管理と監視 (MBAM) によって暗号化された後に移動したオペレーティングシステムドライブを回復する方法について説明します。 ドライブが移動されると、トラステッドプラットフォームモジュール (TPM) チップが変更されたため、前のコンピューターで使用されていた PIN が受け入れられなくなります。 移動したドライブを回復するには、回復キー ID を取得して回復パスワードを取得する必要があります。

移動したドライブを回復するには、管理と監視の Web サイトの [**ドライブの回復**] 領域を使用する必要があります。 [**ドライブ回復**] 領域にアクセスするには、Mbam ヘルプデスクユーザーロールまたは Mbam Advanced ヘルプデスクユーザーの役割が割り当てられている必要があります。 これらの役割の詳細については、「 [MBAM 2.5 のグループとアカウントの計画](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)」を参照してください。

**移動したドライブを復元するには**
1.  移動したドライブが含まれているコンピューターで、Windows 回復環境 (WinRE) モードでコンピューターを起動するか、Microsoft 診断/回復ツールセット (DaRT) を使用してコンピューターを起動します。

2.  コンピューターが WinRE または DaRT で開始されると、MBAM は、移動されたオペレーティングシステムドライブを固定データドライブとして扱います。 その後、MBAM はドライブの回復パスワード ID を表示し、回復パスワードを要求します。

    **注** 場合によっては、[スタートアッププロセス中に**PIN を忘れ**た場合] をクリックし、回復キー ID を表示するための回復モードを入力することができます。

     

3.  回復キー ID を使用して回復パスワードを取得し、管理と監視の Web サイトからドライブのロックを解除します。 手順については、「[回復モードでドライブを回復する方法](how-to-recover-a-drive-in-recovery-mode-mbam-25.md)」を参照してください。

    移動したドライブが元のコンピューター上の TPM チップを使用するように構成されている場合は、次の手順を実行します。 それ以外の場合は、回復プロセスが完了します。

4.  ドライブのロックを解除して開始プロセスを完了したら、WinRE モードでコマンドプロンプトを開き、コマンドを使って `manage-bde` ドライブの暗号化を解除します。 このツールを使うのは、元の TPM チップがなくても TPM を PIN の保護機能に加えて削除する唯一の方法です。 コマンドの詳細については `manage-bde` 、「[管理-bde](https://go.microsoft.com/fwlink/?LinkId=393567)」を参照してください。

5.  削除が完了したら、コンピューターを通常どおりに起動します。 MBAM agent は、このポリシーを適用して、新しいコンピューターの TPM プラス PIN を使ってドライブを暗号化します。



## 関連トピック


[MBAM 2.5 での BitLocker 管理の実行](performing-bitlocker-management-with-mbam-25.md)

 

## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





