---
title: MED-V の Windows 仮想 PC イメージの作成
description: MED-V の Windows 仮想 PC イメージの作成
author: dansimp
ms.assetid: fd7c0b1a-0769-4e7b-ad1a-dad19cca081f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: f947479776e84a4c54edb10d583dd21d7ccf6f43
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812683"
---
# MED-V の Windows 仮想 PC イメージの作成


MED-V ワークスペースをユーザーに提供するには、まず Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 用の MED-V workspace installer パッケージを作成するために使用する仮想ハードディスクを準備する必要があります。 必要な仮想ハードディスクを準備するには、後でアプリケーションと URL リダイレクション情報をユーザーに展開できるように、必要なオペレーティングシステム、更新プログラム、ソフトウェアが含まれた Windows 仮想 PC イメージを作成する必要があります。 このセクションでは、仮想ハードディスクを作成する方法に関するガイダンスを示します。

MED-V の仮想イメージを作成するには、次の手順に従う必要があります。

1.  [Windows 仮想 PC イメージを作成する](#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc)

2.  [Windows XP をイメージにインストールする](#bkmk-installingwindowsxpontovpc)

3.  [.NET Framework をイメージにインストールする](#bkmk-installingnet)

4.  [イメージに更新プログラムを適用する](#bkmk-applypatchestovpc)

5.  [統合コンポーネントをインストールする](#bkmk-installintegration)

## <a href="" id="bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc"></a>Windows 仮想 PC イメージの作成


Windows 仮想 PC のイメージを作成するには、Windows Virtual PC のドキュメントを参照してください。

-   [Windows 仮想 PC のホームページ](https://go.microsoft.com/fwlink/?LinkId=148103)( https://go.microsoft.com/fwlink/?LinkId=148103) .

-   [Windows VIRTUAL PC ヘルプ](https://go.microsoft.com/fwlink/?LinkId=182378)( https://go.microsoft.com/fwlink/?LinkId=182378) .

または、仮想イメージの基礎として使用する Windows Imaging (WIM) ファイルが既にある場合は、そのファイルを、MED-V ワークスペースの構築に使用する VHD に変換できます。 WIM を仮想ハードディスクに変換する方法の詳細については、「 [Windows 7 のネイティブ VHD サポート](https://go.microsoft.com/fwlink/?LinkId=195922)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=195922) 。

**重要** MED-V は仮想マシンあたり1つの仮想ハードディスクのみをサポートし、各仮想ディスクには1つのパーティションのみをサポートします。

 

仮想ハードディスクを作成したら、Windows XP をそのイメージにインストールします。

## <a href="" id="bkmk-installingwindowsxpontovpc"></a>Windows 仮想 PC イメージに Windows XP をインストールする


MED を使用するには、MED-V ワークスペースを構築する前に windows の仮想 PC のイメージに Windows XP SP3 がインストールされている必要があります。

Windows XP のインストール方法の詳細については、「[仮想マシンを作成する」および「ゲストオペレーティングシステムをインストール](https://go.microsoft.com/fwlink/?LinkId=182379)する (」を参照してください https://go.microsoft.com/fwlink/?LinkId=182379) 。

## <a href="" id="bkmk-installingnet"></a>.NET Framework 3.5 SP1 の Windows Virtual PC イメージへのインストール


.NET Framework 3.5 SP1 と更新 KB959209 を手動でインストールして、MED-V で使用するために準備する Windows 仮想 PC イメージにする必要があります。 更新[KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) ( https://go.microsoft.com/fwlink/?LinkId=204950) いくつかの既知のアプリケーション互換性の問題に対処してください。

## <a href="" id="bkmk-applypatchestovpc"></a>Windows 仮想 PC のイメージに更新プログラムを適用する


仮想マシンに Windows XP をインストールした後、必要な Windows XP の更新プログラムを、SP3 などのイメージにインストールします。 パフォーマンスを向上させるために、特定のオプションの更新プログラムをインストールすることもできます。

**重要** MED では、Windows XP SP3 がゲストオペレーティングシステムで実行されている必要があります。

 

**警告** Windows XP の更新プログラムをインストールする場合は、MED-V ワークスペースで使用する予定のゲストの Internet Explorer のバージョンがそのままであることを確認してください。 たとえば、MED-V ワークスペースで Internet Explorer 6 を実行する場合は、今すぐインストールする更新プログラムに Internet Explorer 7 または Internet Explorer 8 が含まれていないことを確認してください。 また、自動更新によって Internet Explorer がアップグレードされないようにレジストリを構成することをお勧めします。

 

### オプションのパフォーマンス更新プログラムをインストールする

必須ではありませんが、 [HOTFIX KB972435](https://go.microsoft.com/fwlink/?LinkId=201077) () 用の次の更新プログラムをインストールすることをお勧めし https://go.microsoft.com/fwlink/?LinkId=201077) ます。 この更新プログラムは、ターミナルサービスセッションでの共有フォルダーのパフォーマンスを向上させます。

**注** 更新プログラムは公開されています。 ただし、Microsoft サービスのライセンス契約に同意するように求められる場合があります。 この修正プログラムを取得するには、連続する web ページの指示に従います。

 

### グループポリシーのパフォーマンス更新プログラムを構成する

既定では、グループポリシーは一度に1バイトのコンピューターにダウンロードされます。 これにより、MED-V がドメインに参加しているときに遅延が発生します。 グループポリシーのパフォーマンスを向上させるには、次のレジストリキー値をレジストリに設定します。

レジストリサブキー: HKEY \ _LOCAL \ _MACHINE ¥ (Windows nt¥)

エントリ: バッファーポリシーの読み取り

型: DWORD

値: 1

## <a href="" id="bkmk-installintegration"></a>統合コンポーネントのインストール


Windows Virtual PC には、統合コンポーネントパッケージが含まれています。 これには、仮想環境と物理コンピューターの間の対話性を向上させるための機能が用意されています。 たとえば、統合コンポーネントパッケージでは、ホストとゲストコンピューターの間でマウスを移動することができます。

**重要** MED では、統合コンポーネントパッケージをインストールする必要があります。

 

MED-V で動作するように仮想イメージを構成する場合は、統合コンポーネントパッケージをゲストオペレーティングシステムに手動でインストールして、統合機能を使用できるようにする必要があります。

統合コンポーネントパッケージをインストールして使用する方法の詳細については、次を参照してください。

-   [統合コンポーネントパッケージ () をインストールまたはアップグレードし](https://go.microsoft.com/fwlink/?LinkId=195923) https://go.microsoft.com/fwlink/?LinkId=195923) ます。

-   [統合機能](https://go.microsoft.com/fwlink/?LinkId=195924)( https://go.microsoft.com/fwlink/?LinkId=195924) .

### RemoteApp の更新プログラムをインストールする

統合コンポーネントパッケージをインストールすると、「RemoteApp を有効にするために Windows XP SP3 用の更新プログラム」という更新プログラムをインストールするように求めるメッセージが表示されます。 これは、MED-V に必要なコンポーネントです。

**重要** RemoteApp の更新プログラムをインストールするように求めるメッセージが表示されない場合は、手動でダウンロードしてインストールする必要があります。 この更新プログラムのダウンロード方法の詳細と手順については、「 [WINDOWS XP SP3 で RemoteApp を有効にするための更新プログラム](https://go.microsoft.com/fwlink/?LinkId=195925)」を参照してください https://go.microsoft.com/fwlink/?LinkId=195925) 。

 

### リモートデスクトップを有効にする

既定では、統合コンポーネントパッケージをインストールすると、リモートデスクトップは有効になります。 MED-V が動作するためには、リモートデスクトップが有効になっていることを確認し、それを無効にするグループポリシーは配布しないようにします。

リモートデスクトップを有効にする方法について[は、「リモートデスクトップを有効または無効](https://go.microsoft.com/fwlink/?LinkId=201162)にする (」を参照してください https://go.microsoft.com/fwlink/?LinkId=201162) 。

## Internet Explorer 管理キットを使用して Internet Explorer をカスタマイズする


必要に応じて、Internet Explorer 管理キットを使用して、ゲストオペレーティングシステムで Internet Explorer をカスタマイズすることができます。 詳細については、「 [Internet Explorer 6 管理キットと展開ガイド](https://go.microsoft.com/fwlink/?LinkId=200007)(http://go.microsoft.com/fwlink/?LinkId=200007)」を参照してください。

**警告** MED-V ワークスペースの Internet Explorer のカスタマイズに関連するセキュリティの問題を考慮する必要があります。 詳細については、「 [Med-v 操作のセキュリティのベストプラクティス](security-best-practices-for-med-v-operations.md)」を参照してください。

 

仮想ハードディスクが最新のゲストオペレーティングシステムと共にインストールされた後、イメージにアプリケーションをインストールできます。

## 関連トピック


[Windows 仮想 PC イメージ上でのアプリケーションのインストール](installing-applications-on-a-windows-virtual-pc-image.md)

[MED-V の Windows 仮想 PC イメージの構成](configuring-a-windows-virtual-pc-image-for-med-v.md)

 

 





