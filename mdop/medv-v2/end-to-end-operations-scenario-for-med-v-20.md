---
title: MED-V 2.0 のエンド ツー エンドの操作シナリオ
description: MED-V 2.0 のエンド ツー エンドの操作シナリオ
author: dansimp
ms.assetid: 1d87f5f3-9fc5-4731-8bd1-c155714f34ee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 90a7c2135ad27040ed87dac980b67321eb771574
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826167"
---
# MED-V 2.0 のエンド ツー エンドの操作シナリオ


このサンプルシナリオ Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 では、複数のシナリオをエンドツーエンドで使用して、MED-V の展開と管理を行うことができます。 このサンプルシナリオは、個々のシナリオと手順をコンテキストにまとめる際に役立つケーススタディと考えることができます。

このセクションでは、企業内のエンドツーエンドのソリューションとして、MED-V ワークスペースを作成、展開、および管理するための基本的な情報と手順について説明します。

## MED-V 操作のステップバイステップのシナリオ


MED-V 操作シナリオで実行するステップバイステップの手順には、次のようなものがあります。

-   [Med-v の Windows 仮想 Pc イメージの作成](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc)Med-v の WINDOWS 仮想 pc イメージを作成して構成する方法について説明します。 MED-V ワークスペースをユーザーに提供する前に、med-v の MED-V workspace installer パッケージを作成するために使用する仮想ハードディスク (VHD) を準備する必要があります。

-   [Med-v 用の Windows 仮想 Pc イメージの作成](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installingwindowsxpontovpc)WINDOWS 仮想 pc イメージに WINDOWS XP SP3 オペレーティングシステムをインストールする方法について説明します。 MED を使用するには、MED-V ワークスペースを構築する前に windows の仮想 PC のイメージに Windows XP SP3 がインストールされている必要があります。

-   [Med-v 用の Windows 仮想 Pc イメージを作成する-](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installingnet) .net FRAMEWORK 3.5 SP1 と更新 KB959209 を手動でインストールして、med-v で使用するための準備をする WINDOWS 仮想 pc のイメージにする方法を確認します。 MED には、.NET Framework 3.5 SP1 と update [KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) ( https://go.microsoft.com/fwlink/?LinkId=204950) いくつかの既知のアプリケーション互換性の問題に対処します) が必要です。

-   [Med-v 用の Windows 仮想 PC イメージの作成](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-applypatchestovpc)windows XP イメージを更新して、最新のソフトウェア更新プログラムや、med-v の実行に必要な、または重要な修正プログラムを作成する方法について説明します。

-   [Med-v の Windows 仮想 PC イメージを作成](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installintegration)すると、windows XP のイメージに統合コンポーネントパッケージをインストールする方法がレビューされます。 これらの機能を使うと、仮想環境と物理コンピューターの間の対話性を向上させることができます。

-   [Windows 仮想 PC のイメージにアプリケーションをインストール](installing-applications-on-a-windows-virtual-pc-image.md)すると、電子ソフトウェアの配布システムやウイルス対策ソフトウェアなど、med-v の実行時に役立つ windows XP イメージに特定の種類のソフトウェアをインストールする方法が確認されます。

-   [Windows 仮想 PC イメージを med-v で構成](configuring-a-windows-virtual-pc-image-for-med-v.md)すると、Sysprep を使用してイメージを構成し、med-v で使用できる状態になっていることを確認する方法について説明します。 次に、既成の MED-V イメージを使用して、MED-V ワークスペースパッケージを作成します。

-   [Med-v ワークスペースパッケージを作成](create-a-med-v-workspace-package.md)する企業全体で展開する med-v ワークスペースパッケージを作成する方法について説明します。 MED-V ワークスペースパッケージを展開して、エンドユーザーのコンピューターに MED-V ワークスペースをインストールします。 MED-V ワークスペースとは、エンドユーザーが MED-V によって提供される仮想マシンとやり取りする Windows XP デスクトップ環境です。

-   [Med-v Workspace パッケージをテスト](testing-the-med-v-workspace-package.md)することで、初回のセットアップ設定やアプリケーションの公開など、med-v ワークスペースパッケージの機能をテストできるテスト環境を作成する方法について説明します。 MED-V ワークスペースパッケージのテストが完了し、意図したとおりに機能していることを確認したら、エンタープライズ全体で展開できます。

-   [Med-v ワークスペースパッケージを展開](deploying-the-med-v-workspace-package.md)すると、電子ソフトウェアの配布システムまたは Windows 7 のイメージを使用して、med-v ワークスペースを展開する方法について説明します。 また、必要に応じて、MED-V ワークスペースを手動で展開する方法についても説明します。

-   [Med-v ワークスペースを監視](monitor-med-v-workspaces.md)する med-v ワークスペースの展開を監視して、初回のセットアップが正常に完了したかどうかを確認する方法について説明します。 初回のセットアップが正常に完了するまでは、MED-V が使用可能な状態になっていないため、初回のセットアップの成功を監視することが重要です。 このセクションでは、MED-V に影響を与える可能性があるネットワークの変更を検出するように環境をセットアップする方法についても説明します。

-   [Med-v ワークスペースアプリケーションを管理](manage-med-v-workspace-applications.md)する展開された med-v ワークスペースでアプリケーションをインストールして削除または公開し、発行を取り消す方法について説明します。 このセクションでは、MED-V ワークスペースのソフトウェアを手動で更新する方法と自動更新を管理する方法についても説明します。 MED-V ワークスペースは、組織内の物理コンピューターとまったく同じように、自動ソフトウェア更新プロセスを管理する必要がある個別のオペレーティングシステムが含まれている仮想マシンです。

-   [MED-V URL リダイレクションを管理](manage-med-v-url-redirection.md)する展開された med-v ワークスペースで web アドレスリダイレクション設定を追加および削除する方法について説明します。 レジストリから、または MED-V ワークスペースを再構築することで、URL リダイレクション情報を追加または削除できます。 MED-V ワークスペースパッケージャーのウィザードを使用して、web アドレスリダイレクションを管理することもできます。

-   [Med-v のワークスペース設定を管理](manage-med-v-workspace-settings.md)する Med-v ワークスペースパッケージャーを使って、med-v 構成の設定を表示および編集する方法について説明します。 このセクションには、すべての構成可能な MED-V レジストリキーの一覧と、それぞれの種類、既定値、説明が含まれています。 このセクションには、MED-V ワークスペースでプリンターを管理する方法に関する情報も含まれています。 MED-V 2.0 では、プリンターリダイレクションによって、MED-V 仮想マシンとホストコンピューターの間で一貫した印刷操作を行うことができます。

## 関連トピック


[MED-V の操作](operations-for-med-v.md)

[MED-V 2.0 のエンド ツー エンドのプランニング シナリオ](end-to-end-planning-scenario-for-med-v-20.md)

[MED-V 2.0 のエンド ツー エンドの展開シナリオ](end-to-end-deployment-scenario-for-med-v-20.md)

 

 





