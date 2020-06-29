---
title: ADMX テンプレートとグループ ポリシーを使用して App-V 5.1 Client 構成を変更する方法
description: ADMX テンプレートとグループ ポリシーを使用して App-V 5.1 Client 構成を変更する方法
author: dansimp
ms.assetid: 0d9cf13a-b29c-4c87-a776-15fea34027dd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 18363b4fb904d995862ac30634be1350c972d918
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813826"
---
# ADMX テンプレートとグループ ポリシーを使用して App-V 5.1 Client 構成を変更する方法


Microsoft Application Virtualization (App-v) 5.1 ADMX テンプレートを使用して、ADMX テンプレートとグループポリシーを使用して App-v 5.1 クライアント設定を構成します。

**グループポリシーを使って App-v 5.1 クライアントの構成を変更するには**

1.  App-v 5.1 クライアント構成を変更するには、App-v 5.1 で利用できる許可**Xtemplate**ファイルを探します。

    **注** 次のリンクを使用して、App V 5.1 **ADMX テンプレート**をダウンロード <https://go.microsoft.com/fwlink/p/?LinkId=393941> します。

     

2.  グループポリシーを管理するコンピューター (通常はドメインコントローラー) で、テンプレートの**admx**ファイルを次のディレクトリにコピーします。 ** &lt; インストールドライブ &gt; \ \ Windows \ ポリシー定義**。

    次に、同じコンピューターで、 **adml**ファイルを次のディレクトリにコピーします。 ** &lt; インストールドライブ &gt; \ Windows \ \ ポリシーの定義 \ \ en-us**。

3.  ファイルをコピーした後、グループポリシー管理コンソールを開いて、5.1 アプリに関連付けられているポリシーを変更するには、[**コンピューター構成**  /  **ポリシー**] の  /  **管理用テンプレート**  /  **System**  /  **App**に移動します。

    App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[APP-V 5.1 の展開](deploying-app-v-51.md)

[Client の構成設定について](about-client-configuration-settings51.md)

 

 





