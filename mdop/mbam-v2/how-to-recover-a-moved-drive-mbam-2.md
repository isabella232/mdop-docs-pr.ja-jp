---
title: 移動されたドライブを回復する方法
description: 移動されたドライブを回復する方法
author: dansimp
ms.assetid: 697cd78d-962c-411e-901a-2e9220ba6552
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bd0d43f2eea95fe71225a50e7fa68d4fb1c35485
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825064"
---
# 移動されたドライブを回復する方法


Microsoft BitLocker の管理と監視 (MBAM) を使用して暗号化されたオペレーティングシステムドライブを移動すると、トラステッドプラットフォームモジュール (TPM) チップの変更のために、以前のコンピューターで使用されていた PIN がドライブで受け入れられなくなります。 移動したドライブを使用するには、回復キー ID を取得して回復パスワードを取得する方法が必要です。 次の手順を使用して、移動したドライブを回復します。

**移動したドライブを復元するには**

1.  移動したドライブが含まれているコンピューターで、Windows 回復環境 (WinRE) モードでコンピューターを起動するか、Microsoft 診断/回復ツールセット (DaRT) を使用してコンピューターを起動します。

2.  コンピューターが WinRE または DaRT で開始されると、Microsoft BitLocker の管理と監視は、移動されたオペレーティングシステムドライブをデータドライブとして扱います。 その後、MBAM はドライブの回復パスワード ID を表示し、回復パスワードを要求します。

    **注** 場合によっては、[スタートアッププロセス中に**PIN を忘れ**た場合] をクリックし、回復キー ID を表示するための回復モードを入力することができます。

     

3.  回復キー ID を使用して回復パスワードを取得し、管理と監視の web サイトからドライブのロックを解除します。

4.  移動したドライブが元のコンピューター上の TPM チップを使用するように構成されている場合は、ドライブのロックを解除し、開始プロセスを完了した後に、追加の手順を実行する必要があります。 WinRE モードでは、コマンドプロンプトを開き、 **manage-bde**ツールを使ってドライブの暗号化を解除します。 このツールを使うのは、元の TPM チップがなくても TPM と PIN の保護機能を削除する唯一の方法です。

5.  削除が完了したら、コンピューターを通常どおりに起動します。 MBAM agent は、新しいコンピューターの TPM plus PIN を使ってドライブを暗号化するポリシーを適用します。

## 関連トピック


[MBAM での BitLocker 管理の実行](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





