---
title: プロジェクト テンプレートを作成して使用する方法
description: プロジェクト テンプレートを作成して使用する方法
author: dansimp
ms.assetid: e5ac1dc8-a88f-4b16-8e3c-df07ef5e4c3b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: de3471eca39d3804e8c5f070c5ec37560fae5dc5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814250"
---
# プロジェクト テンプレートを作成して使用する方法


App-v 5.1 プロジェクトテンプレートを使用して、既存の仮想アプリケーションパッケージに関連付けられている一般的に適用される設定を保存することができます。 これらの設定は、環境に新しい仮想アプリケーションパッケージを作成するときに適用できます。 プロジェクトテンプレートを使うと、仮想アプリケーションパッケージの作成プロセスを効率化することができます。

**注**  
パッケージのアップグレード中に、場合によっては、App-v 5.1 プロジェクトテンプレートを適用することができます。 たとえば、カスタムの除外リストを使ってアプリケーションをシーケンスした場合、関連付けられたテンプレートを作成して保存してから、シーケンス処理されたアプリケーションのアップグレード中に使用できるようにすることをお勧めします。



App-v 5.1 のプロジェクトテンプレートは、app-v の5.1 アプリケーションアクセラレータがアプリケーション固有であり、App-v の5.1 プロジェクトテンプレートを複数のアプリケーションに適用できるため、app-v 5.1 アプリケーションアクセラレータとは異なります。

新しいテンプレートを作成して適用するには、次の手順を使用します。

**プロジェクトテンプレートを作成するには**

1.  Sequencer を実行しているコンピューターで app-v 5.1 sequencer を起動するには、[すべてのプログラムを**起動**する] をクリックし  /  **All Programs**  /  ます。**microsoft**application virtualization  /  **microsoft application virtualization sequencer**。

2.  **注**  
    現在、仮想アプリケーションパッケージが App-v 5.1 Sequencer コンソールで開かれている場合は、手順3に進んでください。



~~~
To open the existing virtual application package that contains the settings you want to save with the App-V 5.1 project template, click **File** / **Open**, and then click **Edit Package**. On the **Select Package** page, click **Browse** and locate the virtual application package that you want to open. Click **Edit**.
~~~

3. App-v 5.1 Sequencer コンソールでテンプレートファイルを保存するには、[ファイルを**File**  /  **テンプレートとして保存**] をクリックします。 新しいテンプレートと共に保存される設定を確認したら、[ **OK]** をクリックします。 新しい App-v 5.1 プロジェクトテンプレートに関連付ける名前を指定します。 [保存] をクリックします。

   新しい App-v 5.1 プロジェクトテンプレートは、この手順の手順3で指定したディレクトリに保存されます。

**プロジェクトテンプレートを適用するには**

1.  **重要**  
    プロジェクトテンプレートを使用して、パッケージアクセラレータと組み合わせて仮想アプリケーションパッケージを作成することはサポートされていません。



~~~
To start the App-V 5.1 sequencer, on the computer that is running the sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.
~~~

2. App-v 5.1 プロジェクトテンプレートを使用して新しい仮想アプリケーションパッケージを作成またはアップグレードするには **、[**  /  **テンプレートから新規**作成] をクリックします。

3. 使用するプロジェクトテンプレートを選択するには、プロジェクトテンプレートが保存されているディレクトリを参照し、プロジェクトテンプレートを選択して、[**開く**] をクリックします。

   新しい仮想アプリケーションパッケージを作成します。 指定したテンプレートと共に保存された設定が、作成する新しい仮想アプリケーションパッケージに適用されます。

   App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[APP-V 5.1 の操作](operations-for-app-v-51.md)









