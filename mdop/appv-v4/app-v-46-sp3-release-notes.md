---
title: App-V 4.6 SP3 リリース ノート
description: App-V 4.6 SP3 リリース ノート
author: dansimp
ms.assetid: 206fadeb-59cc-47b4-836f-191ab1c27ff8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: dd0b82c5e12cbe161066a7f4a4e0932cb92cca42
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819794"
---
# App-V 4.6 SP3 リリース ノート


これらのリリースノートを検索するには、CTRL キーを押しながら F キーを押します。

Microsoft Application Virtualization (App-v) 管理システムをインストールする前に、これらのリリースノートをよくお読みください。 これらのリリースノートには、Application Virtualization (App-v) 4.6 SP3 を正常にインストールするために役立つ情報が含まれています。 このドキュメントには、製品のドキュメントでは利用できない情報が含まれています。 これらのリリースノートと他の App-v のドキュメントの間に違いがある場合は、最新の変更を、権威を持つものとして扱う必要があります。 これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。

## セキュリティの脆弱性とウイルスから保護する


セキュリティの脆弱性やウイルスから保護するために、インストールされている新しいソフトウェアに使用できる最新のセキュリティ更新プログラムをインストールすることが重要です。 詳細については、 [Microsoft セキュリティ web サイト](https://go.microsoft.com/fwlink/?LinkId=3482)() を参照してください https://go.microsoft.com/fwlink/?LinkId=3482) 。

## Application Virtualization 4.6 SP3 の既知の問題


このセクションでは、Microsoft Application Virtualization (App-v) 4.6 SP3 の問題に関する最新情報について説明します。 これらの問題は製品ドキュメントには記載されていないため、場合によっては、既存の製品ドキュメントに矛盾が生じることがあります。 可能であれば、以降のリリースでこの問題に対処します。

### 仮想環境内で Microsoft Windows 8.1 上のインターネット Explorer11 を使用してハイパーリンクを開くことができない

仮想環境内からハイパーリンクを開こうとすると、Windows 8.1 で Internet Explorer 11 を使用すると失敗します。 これは、Internet Explorer 11 が既定で有効になっている拡張保護モード (EPM) を使用するようになったためです。これにより、App-v は、必要なレジストリキー、ファイル、通信ポートオブジェクトにアクセスできなくなります。

回避策: App-v パッケージを開く前に、インターネット Explorer11 の EPM を無効にします。 これにより、仮想環境内から Internet Explorer を開くことができるようになります。

## 関連トピック


[Microsoft Application Virtualization 4.6 SP3 について](about-microsoft-application-virtualization-46-sp3.md)

 

 





