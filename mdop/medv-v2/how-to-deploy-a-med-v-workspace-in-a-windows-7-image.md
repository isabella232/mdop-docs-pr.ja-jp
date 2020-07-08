---
title: Windows 7 イメージで MED-V ワークスペースを展開する方法
description: Windows 7 イメージで MED-V ワークスペースを展開する方法
author: dansimp
ms.assetid: a83aba4e-8681-4906-9872-f431c0bb15f9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 49dd796d6f6af425b9000b595a0d828c3cb0035a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827284"
---
# Windows 7 イメージで MED-V ワークスペースを展開する方法


Windows 7 の新規インストールと同じように、企業全体に配布する Windows 7 イメージに、すべての MED-V コンポーネントをインストールすることができます。 エンドユーザーは、MED-V を開始するように構成した [**スタート**] メニューのショートカットをクリックして、med-v ワークスペースのインストールを終了します。 セットアップが初めて開始され、エンドユーザーが指示に従って構成を完了します。

以下のセクションでは、Windows 7 のイメージを使用して、企業全体で MED-V ワークスペースを展開するのに役立つ情報と手順について説明します。

**Windows 7 イメージで MED-V ワークスペースを展開するには**

1.  Windows 7 の標準イメージを作成します。 詳細については、「 [Windows 7 の標準イメージの構築: ステップバイステップガイド](https://go.microsoft.com/fwlink/?LinkId=204843)()」を参照してください https://go.microsoft.com/fwlink/?LinkId=204843) 。

2.  Windows 7 の画像で、windows Virtual PC と Windows 仮想 PC の更新プログラムをインストールします。 詳細については、「[インストールの前提条件を構成する](configure-installation-prerequisites.md)」を参照してください。

3.  MED-V \ _HostAgent \ _Setup インストールファイルを使用して、MED-V ホストエージェントをインストールします。 詳細については、「 [Med-v Host Agent を手動でインストールする方法](how-to-manually-install-the-med-v-host-agent.md)」を参照してください。

    **警告** MED-V ホストエージェントをインストールする前に、Internet Explorer を閉じておく必要があります。そうでないと、後で URL リダイレクションを使用して競合が発生する可能性があります。 また、配布中にコンピューターを再起動することを指定して、この操作を行うこともできます。

     

4.  MED-V ワークスペースパッケージファイルを Windows 7 イメージにコピーします。 MED-V ワークスペースパッケージファイルは、med-v workspace installer、medv ファイル、および**Med-v Workspace パッケージャー**を使って作成したファイルを setup.exe ます。

    **重要** Medv ファイルと setup.exe ファイルは、MED-V workspace installer と同じフォルダーにある必要があります。 次に、setup.exe を実行して、MED-V ワークスペースをインストールします。

     

5.  [**スタート**] メニューのショートカットを構成して、med-v ワークスペースパッケージのインストールを開きます。

    エンドユーザーが必要に応じて MED-V インストールを開始できるようにする、setup.exe ファイルへの [**スタート**] メニューのショートカットを作成します。

6.  会社の標準的な画像展開プロセスを使用して、MED-V を必要とする企業内のコンピューターに Windows 7 イメージを配布します。

エンドユーザーが、MED-V ワークスペースで公開されているアプリケーションにアクセスする必要がある場合、[**スタート**] メニューのショートカットをクリックして、med-v ワークスペースをインストールすることができます。 これにより、初回のセットアップが自動的に開始され、MED-V の構成が完了します。 セットアップの初回完了後、エンドユーザーは [**スタート**] メニューの med-v アプリケーションにアクセスできます。

## 関連トピック


[MED-V 2.0 展開の概要](med-v-20-deployment-overview.md)

[電子ソフトウェア配布システムによって MED-V ワークスペースを展開する方法](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md)

 

 





