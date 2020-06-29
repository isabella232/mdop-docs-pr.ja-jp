---
title: App-V プロジェクト テンプレートを作成する方法 (App-V 4.6 SP1)
description: App-V プロジェクト テンプレートを作成する方法 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 7e87fba2-b72a-4bc9-92b8-220e25aae99a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4e264d5c41b663bc9c450dc642e2b26297ee7ea1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817647"
---
# App-V プロジェクト テンプレートを作成する方法 (App-V 4.6 SP1)


App-v プロジェクトテンプレートを使用して、既存の仮想アプリケーションパッケージに関連付けられた、一般的に適用される設定を保存できます。 これらの設定は、仮想アプリケーションパッケージの作成プロセスを合理化するための新しい仮想アプリケーションパッケージを環境で作成するときに適用できます。

**注** 新しい仮想アプリケーションパッケージを作成する場合にのみ、App-v プロジェクトテンプレートを適用できます。 既存の仮想アプリケーションパッケージへのプロジェクトテンプレートの適用はサポートされていません。

 

App-v プロジェクトテンプレートの適用の詳細については、「app-v[プロジェクトテンプレートを適用する方法 (app-v 4.6 SP1)](how-to-apply-an-app-v-project-template--app-v-46-sp1-.md)」を参照してください。

App-v のプロジェクトテンプレートは、アプリケーション固有であり、app-v プロジェクトテンプレートを複数のアプリケーションに適用できるため、App-v アプリケーションアクセラレータとは異なります。 また、パッケージアクセラレータを使用して仮想アプリケーションパッケージを作成する場合、プロジェクトテンプレートを使用することはできません。

次の一般的な設定は、App-v プロジェクトテンプレートと共に保存されます。

-   **高度な監視オプション**。 監視中に Microsoft Update が実行されるようにし**ます。**

-   **パッケージ展開の設定**。 **プロトコル**、**ホスト名**、**ポート**、**パス**、**オペレーティングシステム**、**セキュリティ記述子の強制**、 **MSI の作成**、パッケージの**圧縮**が含まれます。

-   **[全般] オプション**。 **Microsoft Windows Installer (MSI)** パッケージを生成し、**イベントの仮想化**、**サービスの仮想**化、**ファイル名へのパッケージバージョンの追加**を許可します。

-   **除外項目**。 除外パターンリストが含まれています。

**プロジェクトテンプレートを作成するには**

1.  App-v sequencer を実行しているコンピューターで app-v sequencer を起動するには、[すべてのプログラムを**起動**する] をクリックし  /  **All Programs**  /  ます。**microsoft**application virtualization  /  **microsoft application virtualization Sequencer**。

2.  現在、仮想アプリケーションパッケージが App-v Sequencer で開かれている場合は、手順3に進んでください。 App-v プロジェクトテンプレートと共に保存する設定を含む既存の仮想アプリケーションパッケージを開くには、[**ファイル**を開く] をクリックし、  /  **Open** [**パッケージ**の**編集**] をクリックします。 [**パッケージの選択**] ページで [**参照**] をクリックし、開く仮想アプリケーションパッケージを探します。 **[編集]** をクリックします。

3.  App-v Sequencer コンソールで、[**ファイル**  /  **をテンプレートとして保存**] をクリックします。 新しいテンプレートと共に保存される設定を確認したら、[ **OK]** をクリックします。 新しい App-v プロジェクトテンプレートに関連付ける名前を指定します。 **[保存]** をクリックします。

    新しい App-v プロジェクトテンプレートは、この手順の手順3で指定したディレクトリに保存されます。

## 関連トピック


[Application Virtualization Sequencer のタスク (APP-V 4.6 SP1)](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

[App-V プロジェクト テンプレートを適用する方法 (App-V 4.6 SP1)](how-to-apply-an-app-v-project-template--app-v-46-sp1-.md)

 

 





