---
title: MED-V ホスト エージェントを手動でインストールする方法
description: MED-V ホスト エージェントを手動でインストールする方法
author: dansimp
ms.assetid: 4becc90b-6481-4e1f-a4d3-aec74c8821ec
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a7fb44b23a390cf394af2331152955afc2d8eba
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812898"
---
# MED-V ホスト エージェントを手動でインストールする方法


Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 ソリューションに関連するコンポーネントは2つありますが、MED-V Host Agent とゲストエージェントの2つは関連しています。 ホストエージェントはホストコンピューター (Windows 7 を実行しているユーザーのコンピューター) にあり、チャネルを提供して、ホストコンピューターで実行されている MED-V ゲスト (MED-V 仮想マシン) と通信します。 また、アプリケーションの発行などの一部の MED-V 関連機能も提供します。

通常は、会社の推奨されるプロビジョニング方法を使用して、MED-V Host Agent を展開してインストールします。 ただし、企業全体で MED-V を展開する前に、テストのためにホストエージェントをローカルにインストールすることをお勧めします。 このセクションでは、MED-V Host Agent を手動でインストールするためのステップバイステップの手順について説明します。

**注** MED-V ゲストエージェントは、初回セットアップ時に自動的にインストールされます。

 

**重要** MED-V Host Agent をインストールする前に Internet Explorer を閉じます。そうでないと、後で URL リダイレクションを使用して競合が発生する可能性があります。 また、配布中にコンピューターを再起動することを指定して、この操作を行うこともできます。

 

**MED-V ホストエージェントをインストールするには**

1.  ソフトウェアダウンロードの一部として受信した MED-V インストールファイルを見つけます。

2.  MED-V \ _HostAgent \ _Setup インストールファイルをダブルクリックします。

    **Microsoft Enterprise デスクトップ仮想化 (med-v) Host Agent セットアップ**ウィザードが開きます。 **[Next]** をクリックして続行します。

3.  Microsoft ソフトウェアライセンス条項に同意し、[**次へ**] をクリックします。

4.  MED-V ホストエージェントをインストールするための移動先フォルダーを選択します。 **[次へ]** をクリックします。

5.  ホストエージェントのインストールを開始するには、[**インストール**] をクリックします。

6.  インストールが正常に完了したら、[**完了**] をクリックしてウィザードを閉じます。

    ホストエージェントが正常にインストールされたことを確認するには、[**スタート**]、[**すべてのプログラム**]、[ **Microsoft Enterprise デスクトップ仮想化**]、[ **med-v Host Agent**] の順にクリックします。

**注** MED-V ワークスペースをインストールするまでは、MED-V ホストエージェントを起動して実行できますが、機能は提供されません。

 

## 関連トピック


[電子ソフトウェア配布システムによって MED-V コンポーネントを展開する方法](how-to-deploy-the-med-v-components-through-an-electronic-software-distribution-system.md)

[MED-V ワークスペース パッケージ ツールをインストールする方法](how-to-install-the-med-v-workspace-packager.md)

[MED-V コンポーネントをアンインストールする方法](how-to-uninstall-the-med-v-components.md)

 

 





