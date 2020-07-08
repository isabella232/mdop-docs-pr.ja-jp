---
title: Windows 仮想 PC イメージ上でのアプリケーションのインストール
description: Windows 仮想 PC イメージ上でのアプリケーションのインストール
author: dansimp
ms.assetid: 32651eff-e3c6-4ef4-947d-2beddc695eac
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9bf73fec0b33b37c2553dfe6f923917aa926b8e8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826834"
---
# Windows 仮想 PC イメージ上でのアプリケーションのインストール


Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 で使用する Windows 仮想 PC イメージを作成した後、電子ソフトウェア配布 (ESD) システムやウイルス対策ソフトウェアなど、MED-V を実行するときに役立つその他のコンポーネントをインストールできます。

以下のセクションでは、MED-V イメージにソフトウェアをインストールするのに役立つ情報について説明します。

**注意** 展開後に MED-V ワークスペースの管理が簡単になるようにするには、MED-V イメージにインストールするコンポーネントの数を、必要に応じて、または MED-V の使用時に役立つものに制限することをお勧めします。 たとえば、MED-V の実行は必須ではありませんが、アプリケーションを MED-V ワークスペースにインストールしたり、ウイルス対策ソフトウェアを使用して、イメージのセキュリティを確保したりするために、後で使う ESD システムをインストールすることができます。

 

**MED-V イメージにソフトウェアをインストールする**

1.  現在実行されていない場合は、MED-V 仮想マシンを開きます。

    1.  [**スタート**] をクリックし、[**すべてのプログラム**]、[ **windows 仮想 Pc** ]、[ **windows 仮想 pc**] の順にクリックします。

    2.  MED-V 仮想マシンをダブルクリックします。

2.  仮想マシンのオペレーティングシステム内から、インストールするソフトウェアのインストールファイルを見つけます。

3.  ソフトウェアベンダーから提供されているインストール手順に従います。

    **注** インストールが完了したら、仮想マシンを終了して再起動する必要がある場合があります。

     

MED-V イメージにインストールするソフトウェアまたはアプリケーションについて、この手順を繰り返します。 イメージにプレインストールするアプリケーションの数を制限することをお勧めします。 イメージにアプリケーションやその他のソフトウェアをインストールする場合に推奨される手順は、ESD システムを今すぐプレインストールし、後で使ってソフトウェアをイメージに展開することです。 または、グループポリシーまたは App-v を使用して、MED-V ワークスペースのアプリケーションを追加または削除することもできます。 詳細については、「 [Med-v ワークスペースに展開されたアプリケーションを管理する](managing-applications-deployed-to-med-v-workspaces.md)」を参照してください。

仮想イメージにソフトウェアをインストールする方法の詳細については、次の記事を参照してください。

-   [仮想アプリケーションを公開して使用する](https://go.microsoft.com/fwlink/?LinkId=195926)( https://go.microsoft.com/fwlink/?LinkId=195926) .

-   [Windows VIRTUAL PC ヘルプ](https://go.microsoft.com/fwlink/?LinkId=182378)( https://go.microsoft.com/fwlink/?LinkId=182378) .

必要なソフトウェアをすべて、MED-V イメージにインストールすると、画像をパッケージ化する準備が整います。

## 関連トピック


[MED-V の Windows 仮想 PC イメージの構成](configuring-a-windows-virtual-pc-image-for-med-v.md)

[MED-V イメージを準備する](prepare-a-med-v-image.md)

 

 





