---
title: コントロール パネルを使用して MBAM クライアントの BitLocker 暗号化オプションを管理する方法
description: コントロール パネルを使用して MBAM クライアントの BitLocker 暗号化オプションを管理する方法
author: dansimp
ms.assetid: e2ff153e-5770-4a12-b79d-cda998b8a8ab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a42901ac9d8a1a3527712f4cf342b5c0ca9ffdfd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825107"
---
# コントロール パネルを使用して MBAM クライアントの BitLocker 暗号化オプションを管理する方法


Microsoft bitlocker の管理と監視 (MBAM) コントロールパネルアプリケーション (BitLocker 暗号化オプションと呼ばれます) は、Microsoft BitLocker 管理および監視クライアントがインストールされている場合、[**システムとセキュリティ**] の下にあります。 このカスタムの MBAM コントロールパネルは、追加のコントロールパネルです。 既定の Windows BitLocker コントロールパネルに代わるものではありません。 MBAM コントロールパネルを使用すると、暗号化された固定ドライブとリムーバブルドライブのロックを解除し、PIN またはパスワードを管理することもできます。 MBAM コントロールパネルを有効にする方法については、「 [Windows コントロールパネルで既定の BitLocker 暗号化を非表示にする方法](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel-mbam-2.md)」を参照してください。

**MBAM クライアントコントロールパネルを使用するには**

1.  BitLocker 暗号化オプションを開くには、[**スタート**] をクリックし、[**コントロールパネル**] を選択します。 [**コントロールパネル]** が開いたら、[**システムとセキュリティ**] を選びます。

2.  [ **BitLocker 暗号化オプション**] をダブルクリックして、カスタマイズされた mbam コントロールパネルを開きます。 コンピューター上のすべてのハードディスクドライブの一覧と、そのパスワードを管理するためのオプションが表示されます。

    コンピューターのハードディスクドライブの一覧を使用して、暗号化の状態の確認、ドライブのロック解除、またはユーザーとコンピューターの適用除外ポリシーが展開されている場合に BitLocker 保護の除外を要求することができます。

    [BitLocker 暗号化オプション] コントロールパネルでは、管理者以外のユーザーが PIN またはパスワードを管理することもできます。 [ **PIN の管理**] を選ぶと、ユーザーは現在の pin と新しい pin の両方を入力するように求められます (新しい pin の確認に加えて)。 [ **Pin の更新**] を選ぶと、ユーザーが選択した新しい PIN に pin がリセットされます。

    パスワードを管理するには、[**ドライブのロック解除**] を選択し、現在のパスワードを入力します。 ドライブのロックが解除されたら、[**パスワードのリセット**] を選択して、現在のパスワードを変更します。

## 関連トピック


[MBAM 2.0 機能の管理](administering-mbam-20-features-mbam-2.md)

 

 





