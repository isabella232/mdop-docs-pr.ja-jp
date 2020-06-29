---
title: GPO をファイルにエクスポートする
description: GPO をファイルにエクスポートする
author: dansimp
ms.assetid: 0d01b1f7-a6a4-4d0d-9aa7-2d6f1ae93d9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4622930cb0e5b439649cc0445ae2b3d02d7d3224
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820854"
---
# GPO をファイルにエクスポートする


管理されたグループポリシーオブジェクト (GPO) を CAB ファイルにエクスポートして、別のフォレストのドメインにコピーし、そのドメインの高度なグループポリシー管理 (AGPM) に GPO をインポートすることができます。 GPO 設定を新規または既存の GPO にインポートする方法について詳しくは、「[ファイルから gpo をインポート](import-a-gpo-from-a-file-ed.md)する」をご覧ください。

この手順を完了するには、Editor または AGPM 管理者 (フルコントロール) の役割を持つ、または高度なグループポリシー管理 (AGPM) に必要なアクセス許可を持つユーザーアカウントが必要です。詳細については、このトピックの「その他の考慮事項」を参照してください。

**GPO をファイルにエクスポートするには**

1.  [**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。

2.  [**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理された gpo を表示します。

3.  GPO を右クリックし、[**エクスポート先**] をクリックします。

4.  GPO をエクスポートするファイルのファイル名を入力し、[**エクスポート**] をクリックします。 ファイルが存在しない場合は、作成されます。 既に存在する場合は、置き換えられます。

### その他の考慮事項

-   既定では、この手順を実行するには、Editor または AGPM 管理者 (フルコントロール) である必要があります。 具体的には、GPO の [**コンテンツの一覧表示**]、[**設定の読み取り**]、[ **gpo のエクスポート**] のアクセス許可が必要です。

### その他の参照情報

-   [テスト環境の使用](using-a-test-environment.md)

 

 





