---
title: Windows Virtual PC アプリケーションの除外一覧
description: Windows Virtual PC アプリケーションの除外一覧
author: dansimp
ms.assetid: 7715f198-f5ed-421e-8740-0cec2ca4ece3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/28/2017
ms.openlocfilehash: 190049ce99865ef237d8d26e14a8279def7da521
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823694"
---
# Windows Virtual PC アプリケーションの除外一覧


場合によっては、MED-V ワークスペースにインストールされているアプリケーションを、ホストコンピューターの [**スタート**] メニューに公開する必要がないことがあります。 このようなアプリケーションは、 [Med-v ワークスペースでアプリケーションを公開し、発行を取り下げる方法](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)の指示に従って、未発行にすることができます。 ただし、プログラムが自動的に更新される場合は、自動的に再公開されることもあります。 これにより、アプリケーションの発行を取り消す必要があります。

Windows 仮想 PC には、ホストの [**スタート**] メニューに公開しないインストール済みのアプリケーションを指定できる "除外リスト" と呼ばれる機能が含まれています。 "除外リスト" は、HKLM\\Software\\Microsoft\\Windows nt¥ currentversion¥ Virtual Machine\\ vpcvappexcludelist key のゲストレジストリにあり、ホストの [**スタート**] メニューに公開されていないアプリケーションの一覧を示しています。 リストされているアプリケーションの自動更新によって自動的に再公開されることはないため、"除外リスト" は、指定したアプリケーションの完全な未発行として考えることができます。

## Windows 仮想 PC の除外リストを使用してアプリケーションを管理する


****

1.  フルスクリーンで MED-V ワークスペースを開きます。

    Med-v 管理ツールキットを使用して、全画面表示モードで MED-V ワークスペースを開く方法について詳しくは、「 [Med-v ワークスペース構成を表示](viewing-med-v-workspace-configurations.md#bkmk-fullscreen)する」をご覧ください。 または、[**スタート**] をクリックし、[**すべてのプログラム**]、[ **windows 仮想 pc**]、[windows 仮想 pc] の順にクリックして、[ **windows 仮想 pc**] をクリックし、med-v ワークスペースをダブルクリックして、完全な画面で手動で開くことができます。

2.  [MED-V workspace Windows Virtual PC] ウィンドウで、レジストリエディターを開きます。

    [**スタート**] をクリックし、[**実行**] をクリックして、「regedit」と入力します。 [ **OK]** をクリックします。

3.  レジストリエディターで、HKLM\\Software\\Microsoft\\Windows nt¥のバージョン \ vp¥ # appexcludelist Registry key を見つけます。

4.  インストールされているアプリケーションの新しいレジストリ値を作成します。この値は、ホストコンピューターの [**スタート**] メニューに公開しないようにします。 たとえば、自動的に公開されるプログラム Microsoft Silverlight の発行を停止する場合は、次の手順を実行します。

    1.  VPCVAppExcludeList レジストリキーが強調表示されている状態で、[**編集**] をクリックし、[**新規作成**] をクリックして、[**文字列値**] をクリックします。

    2.  新しいレジストリ値の名前を入力します。 たとえば、Microsoft Silverlight の場合、sllauncher.exe 入力します。

    3.  新しいレジストリ値をダブルクリックして、値のデータを入力します。

        [値のデータ] は、発行を取り消すコマンドの完全なパスです。 公開しないアプリケーションの [**スタート**] メニューのショートカットを右クリックして、[**プロパティ**] をクリックすると、完全なパスを確認できます。 [**ターゲット**] の下にある**ショートカット**タブに完全なパスが表示されます。

        たとえば、Microsoft Silverlight のプログラムでは、完全なパスは "C:\windows/ファイル名 \\ microsoft Silverlight\\4.0.50917.0\\Silverlight.Configuration.exe" のようになります。

        **重要** 必要に応じて、[値データ] フィールドに入力すると、完全パスから引用符が削除されます。

         

5.  レジストリエディターを終了し、MED-V ワークスペース仮想マシンを再起動します。

    アプリケーションは、MED-V ワークスペースにまだインストールされていますが、ホストコンピューターの [**スタート**] メニューから削除されています。

また、[VPCVAppExcludeList] キーから対応する値を削除することで、除外されたアプリケーションを host **Start**メニューに再公開することもできます。 たとえば、Microsoft Silverlight を再公開するには、レジストリ値 sllauncher.exe を右クリックし、[**削除**] を選択します。

## 関連トピック


[MED-V テクニカル リファレンス](technical-reference-for-med-v.md)

[MED-V ワークスペースでアプリケーションを公開および公開を取り消す方法](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)

 

 





