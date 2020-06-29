---
title: MBAM 2.5 での BitLocker 管理の実行
description: MBAM 2.5 での BitLocker 管理の実行
author: dansimp
ms.assetid: 068f3ee0-300c-4083-ba18-7065eef997ad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1a0ee5802f945176914c56659e0ff7e34e93a969
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826007"
---
# MBAM 2.5 での BitLocker 管理の実行


Microsoft BitLocker の管理と監視 (MBAM) を計画して展開すると、それを構成して使用して、組織全体の BitLocker ドライブ暗号化を管理することができます。 このセクションの情報は、Microsoft BitLocker の管理と監視を使用して実行される、インストール後の、日常的に行われる BitLocker 暗号化管理タスクについて説明します。

## TPM ロックアウトをリセットする


トラステッドプラットフォームモジュール (TPM) は、主に暗号化キーを含む基本的なセキュリティ関連の関数を提供するために設計されたマイクロチップです。 通常、TPM はコンピューターのマザーボードにインストールされ、ホストバスアダプターを使ってシステムの残りの部分と通信します。 TPM が搭載されているコンピューターでは、暗号化キーを作成して暗号化することで、TPM だけが暗号化解除されるようにすることができます。

TPM ロックアウトは、ユーザーが誤った PIN を入力した回数が何度も超えた場合に発生する可能性があります。 TPM ロックの前に、ユーザーが不正な PIN を入力できる回数は、製造元によって異なります。 MBAM を使用して、管理と監視の Web サイトで一元キーの回復データシステムにアクセスすることができます。ここでは、コンピューター ID と関連付けられているユーザー識別子を指定すると、TPM 所有者パスワードファイルを取得できます。

[TPM ロックアウトをリセットする方法](how-to-reset-a-tpm-lockout-mbam-25.md)

## ドライブを回復する


データの暗号化を処理している場合、特にエンタープライズ環境では、ハードウェア障害が発生した場合や、社員の変更があった場合、または暗号化キーを紛失した場合に、データをどのように回復できるかを検討してください。

MBAM の暗号化されたドライブ回復機能を使用すると、データをキャプチャして保存できます。また、BitLocker が回復モードに移行したとき、または破損したときに、必要なツールを使用して BitLocker で保護されたボリュームにアクセスすることができます。

[回復モードでドライブを回復する方法](how-to-recover-a-drive-in-recovery-mode-mbam-25.md)

[移動されたドライブを回復する方法](how-to-recover-a-moved-drive-mbam-25.md)

[破損しているドライブを回復する方法](how-to-recover-a-corrupted-drive-mbam-25.md)

## 紛失したコンピューターの BitLocker 暗号化の状態を確認する


MBAM を使用することで、紛失または盗難したコンピューターの最後の既知の BitLocker 暗号化の状態を確認できます。

[紛失したコンピューターの BitLocker 暗号化の状態を確認する方法](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-25.md)

## セルフサービスポータルを使用してコンピューターへのアクセスを回復する


エンドユーザーが BitLocker によって Windows のロックを解除した場合は、このセクションの手順を使用して、そのコンピューターにアクセスするための BitLocker 回復キーを取得することができます。

[セルフサービス ポータルを使用してコンピューターへのアクセス権を再取得する方法](how-to-use-the-self-service-portal-to-regain-access-to-a-computer-mbam-25.md)



## 関連トピック


[MBAM 2.5 の操作](operations-for-mbam-25.md)

 

## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





