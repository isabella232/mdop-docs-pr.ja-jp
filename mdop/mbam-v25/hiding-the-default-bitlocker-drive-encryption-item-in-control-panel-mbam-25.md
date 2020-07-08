---
title: コントロール パネルの既定の BitLocker ドライブ暗号化項目を非表示にする
description: コントロール パネルの既定の BitLocker ドライブ暗号化項目を非表示にする
author: dansimp
ms.assetid: 6e2a9a02-a809-43a1-80a3-1b03c7192c89
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: af395928ca8934bfea4eeb848bbd4ee377987293
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823097"
---
# コントロール パネルの既定の BitLocker ドライブ暗号化項目を非表示にする


このトピックでは、Windows オペレーティングシステムの一部としてコントロールパネルに既定で表示される、 **BitLocker ドライブ暗号化**コントロールパネルの項目を非表示にする方法について説明します。

**注** Microsoft BitLocker の管理と監視 (MBAM) [ **Bitlocker 暗号化オプション**] という追加のカスタムコントロールパネル項目を作成します。これにより、エンドユーザーは PIN とパスワードを管理し、bitlocker をドライブに対して有効にし、暗号化を確認できます。

 

詳細については[、「コントロールパネルの Bitlocker 暗号化オプションと Bitlocker ドライブ暗号化項目](understanding-the-bitlocker-encryption-options-and-bitlocker-drive-encryption-items-in-control-panel.md)について」を参照してください。

-   MBAM と既定のコントロールパネルアイテムの相違点

-   Windows エクスプローラーでドライブを右クリックすると表示される BitLocker ショートカットメニューを**管理**する

**重要** **BitLocker ドライブ暗号化**ノードのグループポリシー設定は変更しないでください。 この場合、MBAM は正しく動作しません。 [ **MDOP mbam (BitLocker Management)** ] ノードでグループポリシー設定を構成すると、mbam が自動的に**bitlocker ドライブ暗号化**設定を構成します。

 

**コントロールパネルの既定の BitLocker ドライブ暗号化項目を非表示にするには**

1.  グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理で、**ユーザー構成** &gt; **ポリシー**の &gt; **管理用テンプレート**の [ &gt; **コントロールパネル]** を参照します。

2.  **詳細**ウィンドウで、[**指定したコントロールパネルの項目を非表示**にする] をダブルクリックし、[**有効**] をクリックします。

3.  [**表示**] をクリックし、[**追加**] をクリックして、「Microsoft」と入力します **。**



## 関連トピック


[コントロール パネルの [BitLocker 暗号化のオプション] 項目と [BitLocker ドライブ暗号化] 項目について](understanding-the-bitlocker-encryption-options-and-bitlocker-drive-encryption-items-in-control-panel.md)

[MBAM 2.5 グループ ポリシー オブジェクトの展開](deploying-mbam-25-group-policy-objects.md)

 

## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





