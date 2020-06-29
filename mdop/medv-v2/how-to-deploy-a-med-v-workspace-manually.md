---
title: MED-V ワークスペースを手動で展開する方法
description: MED-V ワークスペースを手動で展開する方法
author: dansimp
ms.assetid: 94bfb209-2230-49b6-bb40-9c6ab088dbf4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3f13d06e2232681f87df7a71b9a3ef3269b4f9ce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827277"
---
# MED-V ワークスペースを手動で展開する方法


場合によっては、会社が電子ソフトウェア配布システムを使用してアプリケーションを展開していない場合などに、手動で MED-V のワークスペースを展開することができます。

このセクションでは、MED-V ワークスペースを手動で展開する方法について説明します。

**MED-V ワークスペースを手動で展開するには**

1.  すべての必須アプリケーションと MED-V ワークスペースパッケージファイルを共有ドライブまたは DVD にコピーします。 必要なアプリケーションとファイルの一覧を次に示します。

    -   **Windows 仮想 PC**。 詳細については、「[インストールの前提条件を構成する](configure-installation-prerequisites.md)」を参照してください。

    -   **Windows VIRTUAL PC の追加と更新**。 詳細については、「[インストールの前提条件を構成する](configure-installation-prerequisites.md)」を参照してください。

    -   **Med-v Host Agent インストールファイル**–ホストエージェント (med-v \ _HostAgent \ _Setup インストールファイル) をインストールします。

        **Warning**  
        MED-V Host Agent をインストールする前に Internet Explorer を閉じます。そうでないと、後で URL リダイレクションを使用して競合が発生する可能性があります。 また、配布中にコンピューターを再起動することを指定して、この操作を行うこともできます。



~~~
-   **MED-V Workspace Installer, VHD, and Setup Executable** – created with the **MED-V Workspace Packager**. For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).

    **Important**  
    The compressed VHD file (.medv) and the Setup executable program (setup.exe) must be in the same folder as the MED-V workspace installer.
~~~



2. 記載されている順序に従って、以下をインストールします。 エンドユーザーは、この作業を手動で実行するか、または次のようなスクリプトを作成してインストールすることができます。

   -   Windows 仮想 pc と Windows 仮想 PC の追加と更新。 コンピューターの再起動が必要です。

   -   MED-V ホストエージェント。

       **注**  
       実行されている場合は、MED-V Host Agent のインストールが終了する前に、Internet Explorer を再起動する必要があります。



~~~
-   The MED-V workspace package.

    Install the MED-V workspace by running the setup.exe program that is included in the MED-V workspace package files.
~~~

3. 初回のセットアップを完了します。

   MED-V ワークスペースをインストールした後、MED-V を開始するオプションがあります。 これにより、MED-V ホストエージェントが開始されます。 この時点で MED-V を開始するか、または後で MED-V Host Agent を起動して初めてセットアップを完了することができます。

   MED-V Host Agent を起動するには、[**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Enterprise デスクトップ仮想化**]、[ **med-v host agent**] の順にクリックします。

## 関連トピック


[電子ソフトウェア配布システムによって MED-V ワークスペースを展開する方法](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md)

[Windows 7 イメージで MED-V ワークスペースを展開する方法](how-to-deploy-a-med-v-workspace-in-a-windows-7-image.md)

[MED-V ワークスペース パッケージの展開](deploying-the-med-v-workspace-package.md)









