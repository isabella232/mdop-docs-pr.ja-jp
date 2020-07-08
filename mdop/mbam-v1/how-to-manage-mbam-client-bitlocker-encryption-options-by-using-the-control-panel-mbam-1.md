---
title: コントロール パネルを使用して MBAM クライアントの BitLocker 暗号化オプションを管理する方法
description: コントロール パネルを使用して MBAM クライアントの BitLocker 暗号化オプションを管理する方法
author: dansimp
ms.assetid: c08077e1-5529-468f-9370-c3b33fc258f3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 271147d0e5581f6ce49fe0b46aa83dae6ae4556b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812955"
---
# コントロール パネルを使用して MBAM クライアントの BitLocker 暗号化オプションを管理する方法


BitLocker 暗号化オプションと呼ばれる Microsoft BitLocker の管理と監視 (MBAM) コントロールパネルアプリケーションは、MBAM クライアントがインストールされている場合、[**システムとセキュリティ**] の下にあります。 このカスタマイズされた MBAM コントロールパネルは、既定の Windows BitLocker コントロールパネルに置き換わります。 MBAM コントロールパネルでは、暗号化されたドライブ (固定およびリムーバブル) のロックを解除することができます。また、PIN やパスワードの管理にも役立ちます。 MBAM コントロールパネルを有効にする方法については、「 [Windows コントロールパネルで既定の BitLocker 暗号化を非表示にする方法](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel.md)」を参照してください。

**注** BitLocker クライアントの場合、管理者と運用ログファイルはイベントビューアーにあります。 [**アプリケーションとサービス**] では、  /  **Microsoft**  /  **Windows**の  /  **bitlockermanagement**がログに記録されます。

 

**MBAM クライアントコントロールパネルを使用するには**

1.  BitLocker 暗号化オプションを開くには、[**スタート**] をクリックし、[**コントロールパネル**] を選択します。 [**コントロールパネル]** が開いたら、[**システムとセキュリティ**] を選びます。

2.  [ **BitLocker 暗号化オプション**] をダブルクリックして、カスタマイズされた mbam コントロールパネルを開きます。 コンピューター上のすべてのハードディスクドライブの一覧と、その暗号化状態が表示されます。 PIN またはパスワードを管理するためのオプションも表示されます。

3.  コンピューターのハードディスクドライブの一覧を使用して、暗号化状態の確認、ドライブのロック解除、またはユーザーとコンピューターの除外ポリシーが展開されている場合は、BitLocker 保護の除外を要求します。

4.  管理者以外は、[BitLocker 暗号化オプション] コントロールパネルを使用して Pin またはパスワードを管理することができます。 ユーザーは、[ **pin の管理]** を選ぶことができます。次に、現在の pin と新しい pin の両方を入力します。 また、ユーザーは新しい PIN を確認することもできます。 **UPDATE pin**関数は、ユーザーが選択した新しい PIN に pin をリセットします。

5.  パスワードを管理するには、[**ドライブのロック解除**] を選択し、現在のパスワードを入力します。 ドライブのロックが解除されたら、[**パスワードのリセット**] を選択して、現在のパスワードを変更します。

## 関連トピック


[MBAM 1.0 機能の管理](administering-mbam-10-features.md)

 

 





