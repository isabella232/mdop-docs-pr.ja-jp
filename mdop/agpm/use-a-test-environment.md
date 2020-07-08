---
title: テスト環境を使用する
description: テスト環境を使用する
author: dansimp
ms.assetid: b8d7b3ee-030a-4b5b-8223-4a3276fd47a7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2299fb6eaf7c75f6841056f67a05fe025ea19bb7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818234"
---
# テスト環境を使用する


テスト用の組織単位 (OU) を使用して、運用環境に展開する前にグループポリシーオブジェクト (Gpo) をテストする場合、テスト OU へのアクセスに必要なアクセス許可を持っている必要があります。 Test OU の使用はオプションです。

**テスト OU を使用するには**

1.  編集用にチェックアウトされている GPO があるときに、**グループポリシー管理コンソール**で、gpo を管理するフォレストとドメインの**グループポリシーオブジェクト**をクリックします。

2.  テストする GPO のチェックアウトコピーをクリックします。 名前の前に**\ [AGPM \]** と表示されます。 表示されていない場合は、[**アクション**]、[**更新**] の順にクリックします。 名前はアルファベット順に並べ替えることができ、 **\ [AGPM \]** gpo は通常、一覧の一番上に表示されます。)

3.  GPO を [test OU] にドラッグアンドドロップします。

4.  ダイアログボックスで [ **OK** ] をクリックし、テスト OU に GPO へのリンクを作成するかどうかを確認します。

### その他の考慮事項

-   テストが完了すると、GPO をチェックインすると、チェックアウトした GPO のコピーへのリンクが自動的に削除されます。

### その他の参照情報

-   [GPO の編集](editing-a-gpo.md)

 

 





