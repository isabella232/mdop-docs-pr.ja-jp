---
title: App-V パッケージ アクセラレータを作成する方法 (App-V 4.6 SP1)
description: App-V パッケージ アクセラレータを作成する方法 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 585e692e-cebb-48ac-93ab-b2e7eb7ae7ad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: eb806ccf04fcd5ae7db87c5de21e85217739fcbc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817637"
---
# App-V パッケージ アクセラレータを作成する方法 (App-V 4.6 SP1)


App-v パッケージアクセラレータを使用して、新しい仮想アプリケーションパッケージを自動的に生成することができます。 パッケージアクセラレータの作成が正常に完了したら、パッケージアクセラレータを再利用して共有できます。 パッケージアクセラレータの詳細については、「app-v[パッケージアクセラレータについて (app-v 4.6 SP1)](about-app-v-package-accelerators--app-v-46-sp1-.md)」を参照してください。 App-v パッケージアクセラレータの作成は、高度なタスクです。 パッケージアクセラレータには、パスワードとユーザー固有の情報を含めることができます。 そのため、パッケージアクセラレータと関連するインストールメディアを安全な場所に保存する必要があります。また、パッケージアクセラレータを作成した後で、アプリを作成した後で、app-v パッケージアクセラレータが適用されたときにその発行元を確認できるようにする必要があります。

場合によっては、パッケージアクセラレータを作成するときに、Sequencer を実行しているコンピューターにローカルでアプリケーションをインストールすることが必要な場合があります。 まず、インストールメディアを使ってパッケージアクセラレータを作成し、必要なファイルが不足している場合は、Sequencer を実行しているコンピューターにローカルでアプリケーションをインストールしてから、パッケージアクセラレータを作成します。

**重要**  
次の手順を始める前に、次の操作を行う必要があります。

-   Sequencer を実行しているコンピューターにローカルでパッケージアクセラレータを作成するために使用する仮想アプリケーションパッケージをコピーします。

-   仮想アプリケーションパッケージに関連付けられているすべての必要なインストールファイルを、Sequencer を実行しているコンピューターにコピーします。



**重要**  
免責事項: Microsoft Application Virtualization Sequencer は、パッケージアクセラレータの作成に使用しているソフトウェアアプリケーションのライセンス権限を付与していません。 お客様は、本アプリケーションのすべてのエンドユーザライセンス条項を遵守する必要があります。 ソフトウェアアプリケーションのライセンス条項によって、Application Virtualization Sequencer を使用したパッケージアクセラレータの作成が許可されていることを確認する必要があります。



**App-v パッケージアクセラレータを作成するには**

1.  App-v sequencer を実行しているコンピューターで app-v sequencer を起動するには、[すべてのプログラムを**起動**する] をクリックし  /  **All Programs**  /  ます。**microsoft**application virtualization  /  **microsoft application virtualization Sequencer**。

2.  App-v の**パッケージアクセラレータの作成**ウィザードを起動するには、[**ツール**] の [  /  **パッケージアクセラレータの作成**] をクリックします。

3.  [**パッケージの選択**] ページで、パッケージアクセラレータの作成に使用する既存の仮想アプリケーションパッケージを指定するには、[**参照**] をクリックし、既存の仮想アプリケーションパッケージ (sprj ファイル) を探します。

    **ヒント**  
    ローカルで使用する仮想アプリケーションパッケージに関連付けられているファイルを、Sequencer を実行しているコンピューターにコピーします。



~~~
Click **Next**.
~~~

4. [**インストールファイル**] ページで、元の仮想アプリケーションパッケージの作成に使用したインストールファイルが保存されているフォルダーを指定するには、[**参照**] をクリックし、インストールファイルが格納されているディレクトリを選択します。

   **ヒント**  
   Sequencer を実行しているコンピューターに、必要なインストールファイルを含むフォルダーをコピーします。



~~~
If the application is already installed on the computer running the Sequencer, to specify the installation file, select **Files installed on local system**. To use this option, the application must already be installed in the default installation location.
~~~

5. [**情報の収集**] ページで、このウィザードの [**インストールファイル**] ページで指定した場所に見つからなかったファイルを確認します。 表示されたファイルが必要ない場合は、[**これらのファイルを削除**する] を選択し、[**次へ**] をクリックします。 ファイルが必要な場合は、[**前へ**] をクリックし、必要なファイルを [**インストールファイル**] ページで指定したディレクトリにコピーします。

   **注**  
   不要なファイルを削除するか、[**前**へ] をクリックして、このウィザードの次のページに進むために必要なファイルを特定する必要があります。



6. [**ファイルの選択**] ページで、検出されたファイルを慎重に確認し、パッケージアクセラレータから削除する必要があるファイルをクリアします。 アプリケーションを正常に実行するために必要なファイルのみを選択し、[**次へ**] をクリックします。

7. [**アプリケーションの確認**] ページで、パッケージをビルドするために必要なすべてのインストールファイルが表示されていることを確認します。 パッケージアクセラレータを使って新しいパッケージを作成すると、[**アプリケーション**] ウィンドウに表示されるすべてのインストールファイルが、パッケージを作成するために必要です。

   必要に応じて、追加のインストーラファイルを追加するには、[**追加**] をクリックします。 不要なインストールファイルを削除するには、インストーラファイルを選択し、[**削除**] をクリックします。 インストーラーに関連付けられているプロパティを編集するには、[**編集**] をクリックします。 この手順で指定したインストールファイルは、パッケージアクセラレータを使って新しい仮想アプリケーションパッケージを作成するときに必要になります。 表示された情報を確認したら、[**次へ**] をクリックします。

8. **[ガイダンスの選択**] ページで、パッケージアクセラレータに関する情報が含まれているファイルを指定するには、[**参照**] をクリックします。 たとえば、このファイルには、Sequencer を実行するコンピューターの構成方法、ターゲットコンピューターのアプリケーションの必須情報、一般的なメモなどの情報を含めることができます。 パッケージアクセラレータが正常に適用されるために必要なすべての情報を提供する必要があります。 選択するファイルは、リッチテキスト形式 (.rtf) またはテキストファイル (.txt) 形式である必要があります。 **[次へ]** をクリックします。

9. [**パッケージアクセラレータの作成**] ページで、パッケージアクセラレータの保存場所を指定するには、[**参照**] をクリックし、ディレクトリを選択します。

10. [**完了**] ページで、[**パッケージアクセラレータの作成**] ウィザードを閉じるには、[**閉じる**] をクリックします。

   **重要**  
   パッケージアクセラレータが可能な限りセキュリティで保護されるようにするために、パッケージアクセラレータが適用されたときに発行元を確認できるように、常にパッケージアクセラレータにデジタル署名する必要があります。



## 関連トピック


Application Virtualization Sequencer を構成する (App-v 4.6 SP1)[パッケージアクセラレータを適用して仮想アプリケーションパッケージを作成する方法 (app-v 4.6 SP1)](how-to-apply-a-package-accelerator-to-create-a-virtual-application-package---app-v-46-sp1-.md)








