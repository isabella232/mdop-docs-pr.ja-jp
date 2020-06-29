---
title: インストールの前提条件を構成する
description: インストールの前提条件を構成する
author: dansimp
ms.assetid: ff9cf28a-3eac-4b6c-8ce9-bfc202f57947
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 6cd9379804c45a2025064a6eecf363c010980369
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819307"
---
# インストールの前提条件を構成する


次の手順は、Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 をインストールして使用するための前提条件です。

[Windows 仮想 PC](#bkmk-howtoinstallandconfiguremicrosoftvirtualpc7)

[Windows 仮想 PC の更新プログラム](#bkmk-howtoinstallandconfiguremicrosoftvirtualpc7update)

[ウイルス対策/バックアップソフトウェアの構成](#bkmk-antivirusbackupsoftwareconfiguration)

## <a href="" id="bkmk-howtoinstallandconfiguremicrosoftvirtualpc7"></a>Windows 仮想 PC をインストールして構成する方法


**重要** Windows 版の Virtual PC がホストコンピューターに既に存在する場合は、Windows Virtual PC をインストールする前にアンインストールする必要があります。

 

**Windows 仮想 PC をインストールするには**

1.  Microsoft ダウンロードセンター () から[Windows VIRTUAL PC](https://go.microsoft.com/fwlink/?LinkId=195918)をダウンロードし https://go.microsoft.com/fwlink/?LinkId=195918) ます。

2.  ホストコンピューターでインストールファイルを実行して、ウィザードの手順に従います。

**重要** Windows 仮想 PC には、仮想環境と物理コンピューターの間の操作を改善する機能を提供する統合コンポーネントパッケージが含まれています。 たとえば、ホストとゲストコンピューターの間でマウスを移動できるようにします。 MED では、統合コンポーネントパッケージをインストールする必要があります。

 

## <a href="" id="bkmk-howtoinstallandconfiguremicrosoftvirtualpc7update"></a>Windows 仮想 PC の更新プログラムをインストールして構成する方法


KB977206 に関連付けられている Microsoft update により、ハードウェア支援による仮想化 (HAV) テクノロジを備えていないコンピューターで Windows XP モードが有効になります。 ゲストオペレーティングシステムの統合コンポーネントパッケージが、ホストコンピューターにインストールされている Windows 仮想 PC のバージョンと一致しない場合、一部の統合機能が正しく動作しない可能性があるため、この更新プログラムをインストールすることをお勧めします。

**重要** Windows 7 と Service Pack 1 を実行しているホストコンピューターに MED-V をインストールする場合は、この更新プログラムをインストールする必要はありません。

 

**ヒント** ここに記載されている更新に加えて、使用可能なすべての Windows 仮想 PC 更新プログラムを確認して、環境に適した、または必要な更新プログラムを適用することをお勧めします。

 

**Windows 仮想 PC の更新プログラムをインストールするには**

1.  Microsoft ダウンロードセンターから、必要な Windows 仮想 PC の更新プログラムをダウンロードします。

    [32 ビット更新プログラム](https://go.microsoft.com/fwlink/?LinkId=195919)( https://go.microsoft.com/fwlink/?LinkId=195919) .

    [64 ビット更新プログラム](https://go.microsoft.com/fwlink/?LinkId=195920)( https://go.microsoft.com/fwlink/?LinkId=195920) .

2.  ホストコンピューターで管理者モードでインストールファイルを実行し、ウィザードの手順に従います。

    Windows 仮想 PC の修正プログラムパッケージの詳細については、[記事 977206](https://go.microsoft.com/fwlink/?LinkId=195921) () を参照してください https://go.microsoft.com/fwlink/?LinkId=195921) 。

## <a href="" id="bkmk-antivirusbackupsoftwareconfiguration"></a>ウイルス対策/バックアップソフトウェアを構成する方法


ウイルス対策によって仮想デスクトップのパフォーマンスが影響を受けないようにするには、ホストコンピューター上で実行されている任意のウイルス対策またはバックアッププロセスから、次の仮想マシンのファイルの種類を除外することをお勧めします。

-   \*..VMC

-   \*.VUD

-   \*.VSV

-   \*.VHD

## 関連トピック


[環境の前提条件を構成する](configure-environment-prerequisites.md)

[アーキテクチャの概要](high-level-architecturemedv2.md)

[MED-V 2.0 でサポートされる構成](med-v-20-supported-configurations.md)

 

 





