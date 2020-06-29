---
title: App-V プロジェクト テンプレートを適用する方法 (App-V 4.6 SP1)
description: App-V プロジェクト テンプレートを適用する方法 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 8ef120ab-8cfb-438c-8136-671167b7bd9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5b5f04f3f31838bfb13c19eee5f2314c3a3d291f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821374"
---
# App-V プロジェクト テンプレートを適用する方法 (App-V 4.6 SP1)


App-v プロジェクトテンプレートを使用して、既存の仮想アプリケーションパッケージに関連する一般的な設定を新しい仮想アプリケーションパッケージに適用することができます。 App-v プロジェクトテンプレートを使用すると、アプリケーションのシーケンス処理を開始する前に、共通の設定を構成することで、仮想アプリケーションパッケージの作成プロセスを効率化できます。

**注** 新しい仮想アプリケーションパッケージを作成する場合にのみ、App-v プロジェクトテンプレートを適用できます。 既存の仮想アプリケーションパッケージへのプロジェクトテンプレートの適用はサポートされていません。 さらに、プロジェクトテンプレートをパッケージアクセラレータと組み合わせて使用することはできません。

 

App-v プロジェクトテンプレートの作成について詳しくは、「app-v[プロジェクトテンプレートを作成する (app-v 4.6 SP1)](how-to-create-an-app-v-project-template--app-v-46-sp1-.md)」をご覧ください。

**App-v プロジェクトテンプレートを適用するには**

1.  Microsoft application virtualization sequencer を起動するには、app-v sequencer がインストールされているコンピューターで、[すべてのプログラムを**起動**する] をクリックし  /  **All Programs**  /  ます。**microsoft**application virtualization  /  **microsoft application virtualization Sequencer**。

2.  App-v プロジェクトテンプレートを使用して新しい仮想アプリケーションパッケージを作成するには、 **File**[  /  **テンプレートからのファイルの新規**作成] をクリックします。

3.  使用するプロジェクトテンプレートを選択するには、プロジェクトテンプレートが保存されているディレクトリを参照し、プロジェクトテンプレートを選択して、[**開く**] をクリックします。

4.  新しい仮想アプリケーションパッケージを作成します。 指定したテンプレートと共に保存された設定が、作成する新しい仮想アプリケーションパッケージに適用されます。 新しい仮想アプリケーションパッケージの作成の詳細については、「[シーケンスするアプリケーションの種類 (app-v 4.6 SP1) を決定する方法](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)」および該当する手順を参照してください。

## 関連トピック


[Application Virtualization Sequencer のタスク (APP-V 4.6 SP1)](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

[App-V プロジェクト テンプレートを作成する方法 (App-V 4.6 SP1)](how-to-create-an-app-v-project-template--app-v-46-sp1-.md)

 

 





