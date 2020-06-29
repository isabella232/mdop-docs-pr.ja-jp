---
title: Windows コントロール パネルで既定の BitLocker 暗号化を非表示にする方法
description: Windows コントロール パネルで既定の BitLocker 暗号化を非表示にする方法
author: dansimp
ms.assetid: 6674aa51-2b5d-4e4a-8b43-2cc18d008285
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: eda8fafbd7b3ebf414520354eba6def2e97f6237
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824084"
---
# Windows コントロール パネルで既定の BitLocker 暗号化を非表示にする方法


Microsoft BitLocker の管理と監視 (MBAM) では、Microsoft BitLocker の管理および監視クライアントコンピューター (BitLocker 暗号化オプション) 向けにカスタマイズされたコントロールパネルを提供しています。 このカスタマイズされたコントロールパネルは、BitLocker ドライブ暗号化と呼ばれる、既定の Windows BitLocker コントロールパネルを置き換えることができます。 コントロールパネルの [システムとセキュリティ] の下にあるカスタマイズされたコントロールパネルを使用すると、ユーザーは PIN とパスワードを管理したり、ドライブのロックを解除したり、管理者がドライブの暗号化を解除したり、BitLocker ドライブの暗号化を停止または再開したりするためのインターフェイスを非表示にすることができます。

**Windows のコントロールパネルで既定の BitLocker ドライブ暗号化を非表示にするには**

1.  グループポリシー管理コンソール (GPMC)、高度なグループポリシー管理 (AGPM)、または、BitLocker グループポリシーコンピューターのローカルグループポリシーエディターで、[ユーザーの**構成**] を参照します。

2.  次に、[**ポリシー**] をクリックし、[**管理用テンプレート**] を選択して、[**コントロールパネル**] をクリックします。

3.  [**詳細**] ウィンドウで、[**指定したコントロールパネルの項目を非表示**にする] をダブルクリックし、[**有効**] を選びます。

4.  [**表示**] をクリックし、[**追加**] をクリックして、「Microsoft」と入力します **。** このポリシーでは、Windows の [コントロールパネル] から既定の Windows BitLocker 管理ツールを非表示にします。コントロールパネルで、ユーザーは [システムとセキュリティ] の下にある更新された MBAM BitLocker 暗号化オプションツールを開くことができます。

## 関連トピック


[MBAM 2.0 グループ ポリシー オブジェクトの展開](deploying-mbam-20-group-policy-objects-mbam-2.md)

 

 





