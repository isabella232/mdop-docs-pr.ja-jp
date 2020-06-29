---
title: サーバーを追加する方法
description: サーバーを追加する方法
author: dansimp
ms.assetid: 1f31678a-8edf-4d35-a812-e4a2abfd979b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7d08b79bcbf34910ce357f39635431d11e3e99bd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821387"
---
# サーバーを追加する方法


アプリケーションの仮想化管理サーバーをより効率的に管理できるように、サーバーグループに整理します。 Application Virtualization Server 管理コンソールでサーバーグループを作成した後、次の手順を使用して、グループにサーバーを追加することができます。

**注** サーバーグループ内のすべてのサーバーは、同じデータストアに接続する必要があります。

 

**サーバーをグループに追加するには**

1.  左側のウィンドウで [**サーバーグループ**] ノードをクリックして、サーバーグループの一覧を展開します。

2.  目的のサーバーグループを右クリックし、[**新しい Application Virtualization Management server**] を選びます。

3.  **新しいサーバーグループウィザード**で、**表示名**と**DNS ホスト名**を入力します。

4.  サーバーキャッシュの [**最大メモリ割り当て**] フィールドと [**メモリ割り当ての警告**] フィールドの既定値のままにして、しきい値警告レベルを指定します。

5.  **[次へ]** をクリックします。

6.  [**接続セキュリティモード**] ダイアログボックスで、[**強化セキュリティを使用**] チェックボックスをオンにし、必要に応じて [拡張セキュリティモード] を選択します。 必要に応じて、**証明書ウィザード**を完了するか、既存の証明書を表示します。

7.  **[次へ]** をクリックします。

8.  [ **App Virt Port Setting** ] ダイアログで、[ **Use Default port** ] または [ **User custom port** ] ラジオボタンを選択し、カスタムポート番号を入力します。

9.  **[完了]** をクリックします。

## 関連トピック


[サーバー グループを作成する方法](how-to-create-a-server-group.md)

[サーバーを削除する方法](how-to-remove-a-server.md)

 

 





