---
title: GPO の設定を確認する
description: GPO の設定を確認する
author: dansimp
ms.assetid: e82570b2-d8ce-4bf0-8ad7-8910409f3041
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 681492f423266ce3722bb1a657ee93527c6bdd7b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818334"
---
# GPO の設定を確認する


任意のバージョンのグループポリシーオブジェクト (GPO) 内の設定を確認するために、HTML ベースおよび XML ベースのレポートを生成することができます。

この手順を完了するには、レビュー担当者、編集者、承認者、または AGPM 管理者 (フルコントロール) の役割を持つユーザーアカウント、または高度なグループポリシー管理の必要なアクセス許可が必要です。 詳細については、このトピックの「その他の考慮事項」を参照してください。

**GPO の任意のバージョンで設定を確認するには**

1.  [**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。

2.  [詳細] ウィンドウの [**コンテンツ**] タブで、タブをクリックして gpo を表示します。

3.  GPO をダブルクリックして、その履歴を表示します。

4.  設定を確認する GPO のバージョンを右クリックし、[**設定**] をクリックし、[ **HTML レポート**] または [ **XML レポート**] をクリックして、gpo の設定の概要を表示します。

### その他の考慮事項

-   既定では、この手順を実行するには、レビュー担当者、編集者、承認者、AGPM 管理者 (フルコントロール) である必要があります。 具体的には、GPO の [**リストコンテンツ]** と [**読み取り設定**] のアクセス許可が必要です。 また、Gpo の一覧を表示するには、ドメインの**リストコンテンツ**のアクセス許可が必要です。

### その他の参照情報

-   [レビュー担当者タスクの実行](performing-reviewer-tasks.md)

 

 





