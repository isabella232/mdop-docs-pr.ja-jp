---
title: ADMX テンプレートとグループ ポリシーを使用して App-V 5.0 Client 構成を変更する方法
description: ADMX テンプレートとグループ ポリシーを使用して App-V 5.0 Client 構成を変更する方法
author: dansimp
ms.assetid: 79d03a2b-2586-4ca7-bbaa-bdeb0a694279
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cd257691bf223baa5e2919d83fdbf53d34f271ac
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813842"
---
# ADMX テンプレートとグループ ポリシーを使用して App-V 5.0 Client 構成を変更する方法


ADMX テンプレートとグループポリシーを使用して、app-v 5.0 クライアント設定を構成するには、App-v 5.0 ADMX テンプレートを使用します。

**グループポリシーを使って App-v 5.0 クライアントの構成を変更するには**

1.  App-v 5.0 クライアント構成を変更するには、App-v 5.0 で利用できる許可**Xtemplate**ファイルを探します。

    **注** 次のリンクを使用して、App V 5.0 **ADMX テンプレート**をダウンロード <https://go.microsoft.com/fwlink/p/?LinkId=393941> します。

     

2.  グループポリシーを管理するコンピューター (通常はドメインコントローラー) で、テンプレートの**admx**ファイルを次のディレクトリにコピーします。 ** &lt; インストールドライブ &gt; \ \ Windows \ ポリシー定義**。

    次に、同じコンピューターで、 **adml**ファイルを次のディレクトリにコピーします。 ** &lt; インストールドライブ &gt; \ Windows \ \ ポリシーの定義 \ \ en-us**。

3.  ファイルをコピーした後、グループポリシー管理コンソールを開いて、5.0 アプリに関連付けられているポリシーを変更するには、[**コンピューター構成**  /  **ポリシー**] の  /  **管理用テンプレート**  /  **System**  /  **App**に移動します。

    App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[APP-V 5.0 の展開](deploying-app-v-50.md)

[Client の構成設定について](about-client-configuration-settings.md)

 

 





