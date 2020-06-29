---
title: 非接続操作モード
description: 非接続操作モード
author: dansimp
ms.assetid: 3f9849ea-ba53-4c68-85d3-87a4218f59c6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6e9534b93f23b17e5258ef5e2d548eb93213f2f8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821624"
---
# 非接続操作モード


切断された操作モードの設定:**アプリケーション仮想化**ノードを右クリックし、[**プロパティ**] を選び、[**接続**] タブをクリックすると、クライアントが application virtualization Management Server に接続できないときに、クライアントのファイルシステムキャッシュに保存されているアプリケーションを実行できるようになります。

サーバーへの接続に失敗した理由として、サーバーの失敗、ネットワークの停止、ネットワークからの切断などがあります。 障害が発生した場合、クライアントは自動的に切断された操作に切り替えます。 接続が切断された後、クライアントでサーバーから追加のデータが要求され、アプリケーションの実行が続行される場合、または切断された操作のタイムアウトが経過した場合、クライアントはサーバーに再接続しようとします。 この接続が失敗すると、アプリケーションはシャットダウンされます。

既定では、切断された操作は有効になっていますが、タイムアウトは90日間に設定されています。 タイムアウト値は、切断操作モードを制限する日数として指定され、1 ~ 999 の値を入力することができます。

## 関連トピック


[非接続操作モード設定を無効化または変更する方法](how-to-disable-or-modify-disconnected-operation-mode-settings.md)

 

 





