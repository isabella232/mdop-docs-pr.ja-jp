---
title: Web ベース アプリケーションの仮想環境を作成する方法
description: Web ベース アプリケーションの仮想環境を作成する方法
author: dansimp
ms.assetid: d2b16e9d-369c-4bd6-b2a0-16dd24c0e32c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3a53bec6869b3af9666775600b181c57eec3be93
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817664"
---
# Web ベース アプリケーションの仮想環境を作成する方法


分離する web アプリケーションの仮想環境を個別に作成することができます。 個別の web 環境を作成することは、web ベースのアプリケーションのプラグインに、互いに競合する構成が必要な場合に便利です。

**Web ベースのアプリケーションの仮想環境を作成するには**

1.  シーケンスウィザードを開きます。 アプリケーションのシーケンスの詳細については[、「新しいアプリケーションを順序付ける方法」を](how-to-sequence-a-new-application.md)参照してください。

2.  [**モニターのインストール**] ページで、アプリケーションのインストールの監視を開始するには、[**監視の開始**] をクリックします。 Web ブラウザーを開き、アプリケーションに関連付けられているインストーラファイルに移動します。 アプリケーションをインストールし、必要なポストインストール構成タスクを実行します。

3.  アプリケーションを確実に起動するには、アプリケーションを3回開きます。

4.  同じ仮想環境内に存在する必要があるその他のアプリケーションをインストールして構成します。

5.  シーケンスウィザードの残りの手順を完了します。

6.  アプリケーションを保存するには、[**ファイル**] を選択し、[**保存**] をクリックします。

## 関連トピック


[Application Virtualization Sequencer のタスク](tasks-for-the-application-virtualization-sequencer.md)

 

 





