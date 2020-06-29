---
title: 別の組織単位で GPO をテストする
description: 別の組織単位で GPO をテストする
author: dansimp
ms.assetid: 9a9e6d22-74e6-41d8-ac2f-12a1b76ad5a0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 509721fdd775c8669399549f6dcc29cb9ebaea2f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818257"
---
# 別の組織単位で GPO をテストする


テスト用の組織単位 (OU) を使って、運用環境に展開する前に同じドメイン内のグループポリシーオブジェクト (Gpo) をテストする場合は、テスト OU へのアクセスに必要なアクセス許可を持っている必要があります。 Test OU の使用は任意です。

**テスト OU を使用するには**

1.  編集用にチェックアウトされた GPO はありますが、**グループポリシー管理コンソール**で、gpo を管理するフォレストとドメインの**グループポリシーオブジェクト**をクリックします。

2.  テストする GPO のチェックアウトコピーをクリックします。 名前の先頭には**\ [AGPM \]** と表示されます。 表示されていない場合は、[**アクション**]、[**更新**] の順にクリックします。 名前はアルファベット順に並べ替えることができ、 **\ [AGPM \]** gpo は通常、一覧の一番上に表示されます。)

3.  GPO を test OU にドラッグします。

4.  テスト OU に GPO へのリンクを作成するかどうかを確認するダイアログボックスで [ **OK** ] をクリックします。

### その他の考慮事項

-   テストが完了すると、GPO をチェックインすると、チェックアウトした GPO のコピーへのリンクが自動的に削除されます。

### その他の参照情報

-   [テスト環境の使用](using-a-test-environment.md)

 

 





