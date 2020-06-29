---
title: 非接続操作モードのクライアントを構成する方法
description: 非接続操作モードのクライアントを構成する方法
author: dansimp
ms.assetid: 3b48464a-b8b4-494b-93e3-9a6d9bd74652
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1c917d87996a26b330551deb04b1828c31fd3c73
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817817"
---
# 非接続操作モードのクライアントを構成する方法


切断された操作モードでは、Application Virtualization (App-v) Desktop クライアントまたはリモートデスクトップサービス (以前のターミナルサービス) の Application Virtualization (App-v) クライアントを使用して、クライアントが App-v Management Server に接続できない場合に、クライアントのファイルシステムキャッシュに保存されているアプリケーションを実行できます。

**重要** 多数のユーザーをサポートするために複数のリモートデスクトップセッションホスト (RD 度セッションホスト) サーバー (旧ターミナルサーバー) がファーム内にリンクされている大規模な組織では、1つのアプリをサポートするために単一のアプリを使用することで、1つの障害点が示されます。 RDSession ホストファームをサポートするために高可用性を実現するには、2つ以上の App-v 管理サーバーをリンクして、同じデータベースを使用することを検討してください。

 

**切断された操作モードを有効にするには**

-   切断された操作モードを有効にするには、次のレジストリキーの値を1に設定します。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\AllowDisconnectedOperation

**切断された操作モードの使用制限時間を設定するには**

1.  次のレジストリキー値を1に設定します。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\LimitDisconnectedOperation

2.  次のレジストリキー値を、切断操作モードを制限する分単位の時間に設定します。 値の有効な範囲は 1 ~ 999999 です。 既定値は、90日または129600分です。

    HKEY \ _LOCAL \ _MACHINE ¥ $ ¥ (英語) \ すべてのソフトウェア \ ネットワーク \\ dotimeoutminutes

**接続されていない操作モード用にリモートデスクトップサービスのクライアントを構成するには**

1.  切断された操作モードを有効にするには、次のレジストリキー値を1に設定します。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\AllowDisconnectedOperation

2.  切断された操作モードの無制限の使用を許可するには、次のレジストリキー値を 0 (ゼロ) に設定します。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\LimitDisconnectedOperation

3.  パフォーマンスを向上させるために、すべてのパッケージがキャッシュに事前に読み込まれていることを確認します。

## 関連トピック


[非接続操作モード](disconnected-operation-mode.md)

[コマンド ラインを使用して App-V Client レジストリ設定を構成する方法](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





