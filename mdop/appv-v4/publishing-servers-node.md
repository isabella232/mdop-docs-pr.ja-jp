---
title: 公開サーバー ノード
description: 公開サーバー ノード
author: dansimp
ms.assetid: b5823c6c-15bc-4e8d-aeeb-acc366ffedd1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8c001e246c63919773d29a2317d5a43937c0813f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815797"
---
# 公開サーバー ノード


[**発行サーバー** ] ノードは、Application Virtualization クライアント管理コンソールの**スコープ**ウィンドウの [ **application virtualization** ] ノードの1つ下のレベルにあります。 このノードを選択すると、[**結果**] ウィンドウに発行サーバーの一覧が表示されます。

[**発行サーバー** ] ノードを右クリックして、次の要素を含むポップアップメニューを表示します。

<a href="" id="new-server"></a>**新しいサーバー**  
このメニュー項目によって、新しいサーバーウィザードが表示されます。 このウィザードは、次の2つのページで構成されています。

1.  サーバーの表示名とサーバーの種類を入力します。

    -   [**表示名**: サーバーに対して表示する名前を入力します。 既定では、このフィールドは空白になります。

    -   [ **Type**]: サーバーの種類のドロップダウンリストからサーバーの種類を選びます。

2.  サーバーの接続設定を指定します。

    -   [ **Host name (ホスト名) 名**: サーバーの名前または IP アドレスを入力します。

    -   [ **Port (ポート**) 数-ポート番号に対応する数値を入力します。 サーバーの種類が "Application Virtualization Server" である場合、既定値は554、サーバーの種類が "標準 HTTP サーバー" の場合は80です。

    -   **Path**: サーバーの種類が "Application virtualization server" または "Enhanced Security Application virtualization server" である場合、このフィールドは既定で "/" に設定され、読み取り専用です。 サーバーの種類が "標準 HTTP サーバー" または "強化されたセキュリティ HTTP サーバー" の場合、[ **Path** ] フィールドも編集できます。

<a href="" id="new-window-from-here"></a>**ここから新しいウィンドウ**  
このメニュー項目を選択すると、選択したノードがルートノードとして新しい管理コンソールが開きます。

<a href="" id="export-list"></a>**エクスポートリスト**  
このメニュー項目を使用して、**結果**ウィンドウの内容を含むタブ区切りのテキストファイルを作成できます。 この項目は、作成するテキストファイルの場所を指定する、標準の [**ファイルの保存**] ダイアログボックスを表示します。

<a href="" id="view"></a>**View**  
メニュー項目のこのポップアップリストでは、[**結果**] ウィンドウの外観と内容を変更することができます。

<a href="" id="refresh"></a>**Refresh**  
この項目を選択すると、管理コンソールが更新されます。

<a href="" id="help"></a>**ヘルプ**  
この項目は、管理コンソールのヘルプシステムを表示します。

## 関連トピック


[公開サーバーの結果ウィンドウ](publishing-servers-results-pane.md)

[公開サーバーの結果ウィンドウの列](publishing-servers-results-pane-columns.md)

 

 





