---
title: Windows コントロール パネルで既定の BitLocker 暗号化を非表示にする方法
description: Windows コントロール パネルで既定の BitLocker 暗号化を非表示にする方法
author: dansimp
ms.assetid: c8503743-220c-497c-9785-e2feeca484d6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 67a61763e556f8c3b93825220dbbd61a14b7d6f4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824507"
---
# Windows コントロール パネルで既定の BitLocker 暗号化を非表示にする方法


Microsoft BitLocker の管理と監視 (MBAM) は、「BitLocker 暗号化オプション」と呼ばれる MBAM クライアントコンピューター用にカスタマイズされたコントロールパネルを提供します。 このカスタマイズされたコントロールパネルでは、BitLocker ドライブ暗号化という名前の既定の Windows BitLocker コントロールパネルを置き換えることができます。 Windows コントロールパネルの [システムとセキュリティ] の下にある [BitLocker 暗号化オプション] コントロールパネルを使用すると、ユーザーは PIN とパスワードを管理したり、ドライブのロックを解除したり、管理者がドライブの暗号化を解除したり、BitLocker 暗号化を停止または再開したりするためのインターフェイスを非表示にすることができます。

**Windows の [コントロールパネル] で既定の BitLocker 暗号化を非表示にするには**

1.  グループポリシー管理コンソール (GPMC)、高度なグループポリシー管理 (AGPM)、または、BitLocker グループポリシーコンピューターのローカルグループポリシーエディターを使用して、**ユーザーの構成**を参照します。

2.  [**ポリシー**] をクリックし、[**管理用テンプレート**] をクリックして、[**コントロールパネル**] をクリックします。

3.  **詳細**ウィンドウで、[**指定したコントロールパネルの項目を非表示**にする] をダブルクリックし、[**有効**] を選びます。

4.  [**表示**] をクリックし、 **[追加] をクリック**して、「Microsoft」と入力します。 このポリシーでは、windows の [コントロールパネル] から既定の Windows BitLocker 管理ツールを非表示にし、ユーザーが Windows のコントロールパネルから更新された MBAM BitLocker 暗号化オプションツールを開くことができるようにします。

## 関連トピック


[MBAM 1.0 グループ ポリシー オブジェクトの展開](deploying-mbam-10-group-policy-objects.md)

 

 





