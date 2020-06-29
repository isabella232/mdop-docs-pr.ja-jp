---
title: PowerShell を使用してパッケージをシーケンス処理する方法
description: PowerShell を使用してパッケージをシーケンス処理する方法
author: dansimp
ms.assetid: 6134c6be-937d-4609-a516-92d49154b290
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e1bc2933fdb64080dab3b514784e7f68b0236df9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813691"
---
# PowerShell を使用してパッケージをシーケンス処理する方法


PowerShell を使用して新しい App-v 5.1 パッケージを作成するには、次の手順を使用します。

**注** この手順を実行する前に、sequencer を実行しているコンピューターに関連付けられているインストーラーファイルをコピーする必要があります。また、「[アプリ-V 5.1 sequencer とクライアント展開の計画](planning-for-the-app-v-51-sequencer-and-client-deployment.md)」の「sequencer」セクションを読み、理解していることを確認してください。

 

**PowerShell を使用して新しい仮想アプリケーションを作成するには**

1.  App-v 5.1 sequencer をインストールします。 Sequencer のインストールの詳細について[は、「sequencer をインストールする方法」を](how-to-install-the-sequencer-51beta-gb18030.md)参照してください。

2.  PowerShell 本体を開くには、[**開始**] をクリックし、「 **powershell**」と入力します。 **[Windows PowerShell]** を右クリックし、**[管理者として実行]** を選択します。

3.  PowerShell コンソールを使用して、次のように入力します: **import-module appvsequencer**。

4.  パッケージを作成するには、 **AppvSequencerPackage**コマンドレットを使用します。 パッケージを作成するには、次のパラメーターを指定する必要があります。

    -   **Name** -パッケージの名前を指定します。

    -   **Primaryvirtualapplicationdirectory** -アプリケーションのインストールに使用するディレクトリへのパスを指定します。 このパスは存在している必要があります。

    -   **Installer** -関連するアプリケーションインストーラーへのパスを指定します。

    -   **Path** : パッケージの出力ディレクトリを指定します。

    以下に例を示します。

    **New-AppvSequencerPackage –パッケージ &lt; &gt; ルート-primaryvirtualapplicationdirectory path へのパッケージルートへの名前の名前。 &lt; &gt; &lt; &gt; &lt; 出力パスのインストーラの実行可能ファイルへのインストーラーパス&gt;**

    Sequencer がパッケージを作成するまで待ちます。 PowerShell を使用してパッケージを作成するには時間がかかることがあります。 パッケージが正常に作成されなかった場合は、エラーが返されます。

    次の一覧は、 **AppvSequencerPackage**コマンドレットで使用できるその他のオプションのパラメーターを示しています。

    -   AcceleratorFilePath –パッケージを生成するための、accelerator ファイルへのパスを指定します。

    -   [インストールされているファイルのパス-ローカルにインストールされたファイルが保存される場所へのパスを指定します。

    -   InstallMediaPath-インストールメディアが保存されている場所のパスを指定します。

    -   TemplateFilePath: シーケンス処理をカスタマイズする場合は、テンプレートファイルへのパスを指定します。

    -   FullLoad-アプリを開く前に、5.1 アプリを実行しているコンピューターにパッケージを完全にダウンロードする必要があることを指定します。

    App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[PowerShell を使用した App-V 5.1 の管理](administering-app-v-51-by-using-powershell.md)

 

 





