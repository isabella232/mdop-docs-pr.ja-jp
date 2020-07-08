---
title: MBAM での BitLocker 管理の実行
description: MBAM での BitLocker 管理の実行
author: dansimp
ms.assetid: 2d24390a-87bf-48b3-96a9-3882d6f2a15c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8d0de3711d5b7c3696783a054ee7c7f8220b5356
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825894"
---
# MBAM での BitLocker 管理の実行


Microsoft BitLocker の管理と監視 (MBAM) を展開した後、MBAM を構成して使用し、エンタープライズ BitLocker 暗号化を管理することができます。 このセクションでは、インストール後に、MBAM を使って実行できる日常的な BitLocker 暗号化管理タスクについて説明します。

## MBAM で TPM ロックアウトをリセットする


トラステッドプラットフォームモジュール (TPM) マイクロチップは、基本的なセキュリティ関連の機能を提供します。 これらの関数は主に、暗号化キーの使用によって実現されます。 通常、TPM はコンピューターまたはノート pc のマザーボードにインストールされ、ハードウェアバスを使ってシステムの残りの部分と通信します。 TPM が搭載されているコンピューターでは、TPM のみが解読できる暗号化キーを作成できます。 TPM ロックアウトは、ユーザーが誤った PIN を何度も入力した場合に発生する可能性があります。 TPM のロックが発生する前に、ユーザーが不正な PIN を入力できる回数は、製造元によって異なります。 MBAM 管理 web サイトのキー回復データシステムでは、TPM 所有者パスワードのリセットファイルを取得できます。

[TPM ロックアウトをリセットする方法](how-to-reset-a-tpm-lockout-mbam-1.md)

## MBAM でドライブを回復する


ハードウェア障害が発生した場合や、ユーザーが変更した場合、または暗号化キーが失われた場合は、暗号化されたドライブからデータを回復する方法を理解していることを確認してください。 MBAM の暗号化されたドライブ回復機能は、ボリュームが回復モードになったとき、または破損したときに、BitLocker で保護されたボリュームにアクセスするために必要なデータと可用性のキャプチャと記憶域を提供します。

[回復モードでドライブを回復する方法](how-to-recover-a-drive-in-recovery-mode-mbam-1.md)

[移動されたドライブを回復する方法](how-to-recover-a-moved-drive-mbam-1.md)

[破損しているドライブを回復する方法](how-to-recover-a-corrupted-drive-mbam-1.md)

## MBAM を使用して紛失したコンピューターの BitLocker 暗号化の状態を確認する


MBAM を使用する場合は、紛失または盗難したコンピューターの最後の既知の BitLocker 暗号化の状態を確認できます。

[紛失したコンピューターの BitLocker 暗号化の状態を確認する方法](how-to-determine-the-bitlocker-encryption-state-of-a-lost-computers-mbam-1.md)

## MBAM での BitLocker 管理を実行するためのその他のリソース


[MBAM 1.0 の操作](operations-for-mbam-10.md)

 

 





