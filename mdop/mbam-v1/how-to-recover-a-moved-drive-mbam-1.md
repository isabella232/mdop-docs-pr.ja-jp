---
title: 移動されたドライブを回復する方法
description: 移動されたドライブを回復する方法
author: dansimp
ms.assetid: 0c7199d8-9463-4f44-9af3-b70eceeaff1d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e73e0878a3102d56494feb33efa69182029988c2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812930"
---
# 移動されたドライブを回復する方法


Microsoft BitLocker の管理と監視 (MBAM) を使って以前に暗号化されたオペレーティングシステムドライブを移動する場合は、特定の問題を解決する必要があります。 PIN が新しいコンピューターに接続された後、ドライブは、前のコンピューターで使用されていたスタートアップ PIN を受け入れません。 トラステッドプラットフォームモジュール (TPM) チップに変更があったため、PIN は無効とみなされます。 移動したドライブを使用するには、回復キー ID を取得して回復パスワードを取得する必要があります。 この操作を行うには、次の手順を実行します。

**移動したドライブを復元するには**

1.  移動したドライブが含まれているコンピューターで、Windows 回復環境 (WinRE) モードを開始するか、Microsoft 診断/回復ツールセット (DaRT) を使用してコンピューターを起動します。

2.  コンピューターが WinRE または DaRT で開始されると、MBAM は、移動されたオペレーティングシステムドライブをデータドライブとして扱います。 その後、MBAM はドライブの回復パスワード ID を表示し、回復パスワードを要求します。

    **注** 場合によっては、[スタートアッププロセス中に**PIN を忘れ**た場合] をクリックして回復モードに入ることができます。 これにより、回復キー ID も表示されます。

     

3.  MBAM 管理 web サイトで、回復キー ID を使用して回復パスワードを取得し、ドライブのロックを解除します。

4.  移動したドライブが元のコンピューター上の TPM チップを使用するように構成されている場合は、ドライブのロックを解除し、開始プロセスを完了した後に、追加の手順を実行する必要があります。 WinRE モードでは、コマンドプロンプトを開き、 **manage-bde**ツールを使ってドライブの暗号化を解除します。 このツールを使用するのは、元の TPM チップがなくても TPM と PIN の保護を削除する唯一の方法です。

5.  削除が完了したら、システムを通常どおりに起動します。 MBAM agent は、新しいコンピューターの TPM plus PIN を使ってドライブを暗号化するポリシーを適用します。

## 関連トピック


[MBAM での BitLocker 管理の実行](performing-bitlocker-management-with-mbam.md)

 

 





