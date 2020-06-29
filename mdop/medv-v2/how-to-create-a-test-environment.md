---
title: テスト環境を作成する方法
description: テスト環境を作成する方法
author: dansimp
ms.assetid: a0db2299-16f3-4516-8769-7d55ca4a1e98
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ee2ab131f6003b56cce7a60ffea1cd00b067fae3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827287"
---
# テスト環境を作成する方法


エンタープライズ全体で展開する前に、MED-V ワークスペースパッケージをローカルでテストするために使用できるテスト環境を作成するための手順と手順を以下に示します。 このセクションでは、手動で、または電子ソフトウェア配布システムを使用して、テスト環境を作成する方法に関するガイダンスを示します。

**ESD を使ってテスト環境を作成するには**

1.  組織全体でソフトウェアを展開する方法を使用して、次の必要なコンポーネントをテストコンピューターに展開します。 次の順序でインストールします。

    -   **Windows VIRTUAL PC** –まだインストールされていない場合。 詳細については、「[インストールの前提条件を構成する](configure-installation-prerequisites.md)」を参照してください。

    -   **Windows VIRTUAL PC の追加と更新プログラム**(まだインストールされていない場合)。 詳細については、「[インストールの前提条件を構成する](configure-installation-prerequisites.md)」を参照してください。

    -   **Med-v Host Agent インストールファイル**–ホストエージェント (med-v \ _HostAgent \ _Setup インストールファイル) をインストールします。 詳細については、「 [Med-v Host Agent を手動でインストールする方法](how-to-manually-install-the-med-v-host-agent.md)」を参照してください。

    -   Med-v ワークスペースの**インストーラー、VHD、セットアップの実行可能ファイル**( **med-v workspace パッケージャー**で作成) 詳細については、「 [Med-v ワークスペースパッケージを作成する](create-a-med-v-workspace-package.md)」を参照してください。

        **重要** VHD とセットアップの実行可能プログラムは、MED-V ワークスペースインストーラーと同じフォルダーに存在する必要があります。 次に、setup.exe を実行して、MED-V ワークスペースインストーラーをインストールします。

         

2.  すべてのコンポーネントをテストコンピューターにインストールしたら、MED-V Host Agent を実行して、初回のセットアップを開始します。

    [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Enterprise デスクトップ仮想化**]、[ **med-v Host Agent**] の順にクリックします。

    **注** テストコンピューターで MED-V ホストエージェントを物理的に実行できない場合、次にコンピューターを再起動したときに、最初にセットアップが自動的に開始されます。

     

セットアップが初めて開始され、10分以上かかる場合があります。

セットアップの初回実行時に構成設定をテストする方法については、「[初回のセットアップ設定を確認する方法](how-to-verify-first-time-setup-settings.md)」を参照してください。

**テスト環境を手動で作成するには**

1.  Windows 仮想 PC (追加と更新プログラム付き) などの MED-V の前提条件を含む、med-v ホストエージェントをローカルテスト環境にインストールします。 詳細については、「 [Med-v Host Agent を手動でインストールする方法](how-to-manually-install-the-med-v-host-agent.md)」を参照してください。

2.  MED-V ワークスペースファイルをテスト環境にコピーします。 MED-V ワークスペースファイルは、 **Med-v ワークスペースパッケージャー**で指定した移動先フォルダーにあります。

    **重要** VHD とセットアップの実行可能プログラムは、MED-V ワークスペースインストーラーとしてテスト環境の同じフォルダーに存在する必要があります。

     

3.  setup.exe を実行して、MED-V ワークスペースをインストールします。

4.  MED-V ホストエージェントを実行して、初めてセットアップを開始します。

    [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Enterprise デスクトップ仮想化**]、[ **med-v Host Agent**] の順にクリックします。

初めてセットアップを開始したときに、指定した VHD のサイズによっては、完了まで数分かかることがあります。

これで、MED-V ワークスペースで指定した構成、アプリケーション発行、URL リダイレクションのさまざまな設定をテストする準備が整いました。

**注** 既定では、MED-V はゲストの画面ロックポリシーを上書きします。 ただし、ホストコンピューターは画面ロックポリシーを引き続き受け入れているため、これによってセキュリティの問題が発生することはありません。

 

## 関連トピック


[初回使用時のセットアップの設定を確認する方法](how-to-verify-first-time-setup-settings.md)

[アプリケーションの公開をテストする方法](how-to-test-application-publishing.md)

[URL のリダイレクトをテストする方法](how-to-test-url-redirection.md)

 

 





