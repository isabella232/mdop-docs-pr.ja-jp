---
title: MBAM での BitLocker 管理の実行
description: MBAM での BitLocker 管理の実行
author: dansimp
ms.assetid: 9bfc6c67-f12c-4daa-8f08-5884fb47443c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d261ec4fa789cd331209afe1c2f1858d627209a3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826497"
---
# MBAM での BitLocker 管理の実行


Microsoft BitLocker の管理と監視 (MBAM) を計画して展開すると、それを構成して使用し、エンタープライズ BitLocker 暗号化を管理することができます。 このセクションの情報は、Microsoft BitLocker の管理と監視を使用して実行される、インストール後の日常的な BitLocker 暗号化管理タスクについて説明しています。

## MBAM を使用して TPM ロックアウトをリセットする


トラステッドプラットフォームモジュール (TPM) は、主に暗号化キーを含む基本的なセキュリティ関連の関数を提供するために設計されたマイクロチップです。 通常、TPM はコンピューターまたはノート pc のマザーボードにインストールされ、ハードウェアバスを使ってシステムの残りの部分と通信します。 TPM が搭載されているコンピューターには、TPM のみが解読できるように、暗号化キーを作成して暗号化する機能があります。

TPM ロックアウトは、ユーザーが誤った PIN を入力した回数が何度も超えた場合に発生する可能性があります。 TPM のロックが発生する前に、ユーザーが不正な PIN を入力できる回数は、製造元によって異なります。 MBAM を使用して、管理と監視の web サイトで中央キー回復データシステムにアクセスできます。ここでは、コンピューター ID と関連付けられたユーザー識別子を指定すると、TPM 所有者パスワードファイルを取得できます。

[TPM ロックアウトをリセットする方法](how-to-reset-a-tpm-lockout-mbam-2.md)

## MBAM でドライブを回復する


データの暗号化を処理している場合、特にエンタープライズ環境では、ハードウェア障害が発生した場合や、社員の変更があった場合、または暗号化キーを紛失した場合に、データをどのように回復できるかを検討してください。

MBAM の暗号化ドライブ回復機能を使用すると、データをキャプチャして保存できます。また、BitLocker が回復モードに移行したとき、または破損したときに、必要なツールを使用して BitLocker で保護されたボリュームにアクセスできるようになります。

[回復モードでドライブを回復する方法](how-to-recover-a-drive-in-recovery-mode-mbam-2.md)

[移動されたドライブを回復する方法](how-to-recover-a-moved-drive-mbam-2.md)

[破損しているドライブを回復する方法](how-to-recover-a-corrupted-drive-mbam-2.md)

## MBAM を使用して紛失したコンピューターの BitLocker 暗号化の状態を確認する


MBAM を使用して、紛失または盗難したコンピューターの最後の既知の BitLocker 暗号化の状態を判断できます。

[紛失したコンピューターの BitLocker 暗号化の状態を確認する方法](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-2.md)

## セルフサービスポータルを使用してコンピューターへのアクセスを回復する


エンドユーザーが BitLocker によって Windows のロックを解除した場合は、このセクションの手順を使用して、そのコンピューターにアクセスするための BitLocker 回復キーを取得することができます。

[セルフサービス ポータルを使用してコンピューターへのアクセス権を再取得する方法](how-to-use-the-self-service-portal-to-regain-access-to-a-computer.md)

## MBAM での BitLocker 管理を実行するためのその他のリソース


[MBAM 2.0 の操作](operations-for-mbam-20-mbam-2.md)

 

 





