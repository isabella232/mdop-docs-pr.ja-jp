---
title: MED-V ワークスペースのソフトウェア更新プログラムの管理
description: MED-V ワークスペースのソフトウェア更新プログラムの管理
author: dansimp
ms.assetid: a28d6dcd-cb9f-46ba-8dac-1d990837a3a3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 696238a2f5ad9b7e5120f75f6cd09d890d12519b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824814"
---
# MED-V ワークスペースのソフトウェア更新プログラムの管理


展開された MED-V ワークスペースでアプリケーションのソフトウェア更新プログラムを提供するために、いくつかの異なるオプションが用意されています。

**注** MED-V で自動更新を受信する方法を定義する構成設定を指定する方法については、「 [Med-v ワークスペースの自動更新を管理](managing-automatic-updates-for-med-v-workspaces.md)する」を参照してください。

 

**MED-V ワークスペースでのソフトウェアの更新**

1.  **電子ソフトウェア配布システムを使用する**

    組織でソフトウェア配布システム (ESD) システムを使ってソフトウェアを展開している場合は、物理コンピューター上のアプリケーションの更新プログラムを提供する場合と同じように、MED-V ワークスペースでアプリケーションのソフトウェア更新プログラムを提供することができます。

2.  **グループポリシーを使用する**

    組織がグループポリシーを使用してソフトウェアを展開する場合は、物理コンピューター上のアプリケーションの更新プログラムを提供する場合と同じように、アプリを使用して、MED-V ワークスペースのアプリケーションのソフトウェア更新プログラムを提供することができます。

3.  **Application Virtualization (APP-V) を使用する**

    MED-V と App-v を併用する場合は、ソフトウェアの更新に必要な手順に従って、MED-V ワークスペース内のアプリケーションのソフトウェア更新プログラムを提供できます。 詳細については、「 [Application Virtualization](https://go.microsoft.com/fwlink/?LinkId=122939) (」を参照してください https://go.microsoft.com/fwlink/?LinkId=122939) 。

4.  **コアイメージのソフトウェアの更新**

    MED-V のベストプラクティスと見なされることはありませんが、ソフトウェア更新プログラムをコアイメージ上のアプリケーションにインストールできます。 更新プログラムをインストールした後で、元のアプリを展開したときと同じように、MED-V ワークスペースをエンタープライズに再展開することができます。

    **重要** この方法では、ソフトウェアの更新プログラムを管理することはお勧めしません。 また、コアイメージのソフトウェアを更新して、MED-V ワークスペースをエンタープライズに再展開する場合は、最初にセットアップをもう一度実行する必要があります。仮想マシンに保存されたデータはすべて失われます。

     

## 関連トピック


[MED-V ワークスペースの自動更新の管理](managing-automatic-updates-for-med-v-workspaces.md)

[アプリケーションの公開をテストする方法](how-to-test-application-publishing.md)

[MED-V ワークスペースでアプリケーションを公開および公開を取り消す方法](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)

 

 





