---
title: コンピューターの TPM チップについて
description: コンピューターの TPM チップについて
author: dansimp
ms.assetid: 6f1cf18c-277a-4932-886d-14202ca8d175
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f6df54dc8085c398bacc508fdbbb79a30b0e4204
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823534"
---
# コンピューターの TPM チップについて


BitLocker は、トラステッドプラットフォームモジュール (TPM) チップで使用する場合に追加の保護を提供します。 TPM チップは、コンピューターの製造元によって多くの新しいコンピューターにインストールされるハードウェアコンポーネントです。 Microsoft BitLocker の管理と監視 (MBAM) では、TPM チップに加えて BitLocker を使用して、データの保護を強化し、コンピューターが改ざんされていないことを確認することができます。

## TPM のセットアップ方法


使用しているコンピューターで BitLocker ドライブ暗号化ウィザードを起動すると、TPM が TPM チップを使用するように BitLocker を構成している場合、BitLocker は TPM チップをチェックします。 BitLocker で互換性のある TPM チップが検出された場合は、TPM チップを使用できるようにするために、コンピューターの再起動を求めるメッセージが表示されることがあります。 コンピューターが再起動したら、次の手順に従って、BIOS で TPM チップを構成します (BIOS は、コンピュータソフトウェアの Windows の以前のレイヤーです)。

BitLocker を構成した後、Windows の [コントロールパネル] の [BitLocker 暗号化オプション] ツールを開いて、[ **Tpm 管理**] を選択することにより、tpm チップに関するその他の情報にアクセスできます。

**注** このツールにアクセスするには、コンピューターの管理者資格情報を持っている必要があります。

 

TPM のエラー、BIOS の変更、または特定の Windows の更新プログラムでは、BitLocker によってコンピューターがロックされ、ロック解除するためにヘルプデスクに連絡する必要があります。 使用しているコンピューターの名前とコンピューターのドメインを指定する必要があります。 ヘルプデスクでは、コンピューターのロックを解除するために使用できるパスワードファイルを提供できます。

## TPM の問題のトラブルシューティング


TPM のエラー、BIOS の変更、特定の Windows 更新が発生した場合、BitLocker はコンピューターをロックし、ヘルプデスクに連絡してロックを解除する必要があります。 使用しているコンピューターの名前とコンピューターのドメインを指定する必要があります。 ヘルプデスクでは、コンピューターのロックを解除するために使用できるパスワードファイルを提供できます。

## 関連トピック


[エンド ユーザーが BitLocker を管理するための支援](helping-end-users-manage-bitlocker.md)

[PIN またはパスワードの使用](using-your-pin-or-password.md)

 

 





