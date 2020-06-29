---
title: コマンド ラインを使用してシーケンス処理されたアプリケーションを開く方法
description: コマンド ラインを使用してシーケンス処理されたアプリケーションを開く方法
author: dansimp
ms.assetid: dc23ee65-8aea-470e-bb3f-a2f2b06cb241
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c99ab6b41947fc255afa9cad5b3ed2e22e672c3e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816917"
---
# コマンド ラインを使用してシーケンス処理されたアプリケーションを開く方法


仮想アプリケーションパッケージは、コマンドラインを使用して開くことができます。 **コマンド**プロンプトは管理者として実行する必要があります。

コマンドラインを使用してシーケンス処理されたアプリケーションパッケージを開くには、次の手順を使用します。

**コマンドラインを使用してシーケンスされたアプリケーションを開くには**

1.  コマンドプロンプトを開くには、[**開始**] をクリックして、[**実行**] を選択し、「 **cmd**」と入力して、[ **OK]** をクリックします。

2.  コマンドプロンプトで「 **cd\ \** 」と入力して、Sequencer がインストールされているディレクトリへのパスを指定し、enter キーを押し**ます。**

3.  コマンドプロンプトで、次のコマンドを入力します。斜体のテキストは、入力した値に置き換えられます。

    SFTSequencer/open:*"開くために sprj ファイルを指定してください"*

    Enter**キーを押します**。

4.  次のオプションのパラメーターを指定することもできます。 コマンドプロンプトで、次のコマンドを入力します。斜体のテキストは、入力した値に置き換えられます。

    /PACKAGENAME: "*パッケージ名を指定します"*

    /MSI-関連付けられている Microsoft Windows インストーラーの生成を指定します。

    /COMPRESS –パッケージを圧縮するかどうかを指定します。 既定では、パッケージは圧縮されません。

    Enter**キーを押します**。

    **注** インストーラーパッケージまたは Windows Installer パッケージにグラフィカルなユーザーインターフェイスが含まれている場合は、コマンドラインパラメーターを指定した後に表示されます。

     

## 関連トピック


[コマンド ラインを使用して仮想アプリケーションを管理する方法](how-to-manage-virtual-applications-using-the-command-line.md)

 

 





