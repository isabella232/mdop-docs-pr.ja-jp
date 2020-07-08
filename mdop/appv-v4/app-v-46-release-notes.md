---
title: App-V 4.6 リリース ノート
description: App-V 4.6 リリース ノート
author: dansimp
ms.assetid: a3eba129-edac-48bf-a933-3bf43a9873e5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9eee3c309a927a72155dec707d8dd95f43e90fb9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822367"
---
# App-V 4.6 リリース ノート


これらのリリースノートを検索するには、CTRL キーを押しながら F キーを押します。

**重要** Microsoft Application Virtualization (App-v) 管理システムをインストールする前に、これらのリリースノートをよくお読みください。 これらのリリースノートには、Application Virtualization (App-v) 4.6 を正常にインストールするために必要な情報が含まれています。 このドキュメントには、製品のドキュメントでは利用できない情報が含まれています。 これらのリリースノートと他の App-v ドキュメントの間に不一致がある場合は、最新の変更を、権威を持つものとして扱う必要があります。

 

## セキュリティの脆弱性とウイルスから保護する


セキュリティの脆弱性やウイルスから保護するために、インストールされている新しいソフトウェアに使用できる最新のセキュリティ更新プログラムをインストールすることが重要です。 詳細については、 [Microsoft セキュリティ Web サイト](https://go.microsoft.com/fwlink/?LinkId=3482)() を参照してください https://go.microsoft.com/fwlink/?LinkId=3482) 。

## Application Virtualization 4.6 の既知の問題


このセクションでは、Microsoft Application Virtualization (App-v) 4.6 の問題に関する最新情報について説明します。 これらの問題は製品ドキュメントには記載されていないため、場合によっては、既存の製品ドキュメントに矛盾が生じることがあります。 この問題は、可能な限り将来のリリースで解決されます。

### アプリ-V 4.5 Sequencer によって生成された Windows Installer ファイルを実行している、読み込み/インストールエラー

App-v 4.5 Sequencer によって生成された Windows Installer ファイルを実行しようとすると、App-v 4.6 クライアントで実行しようとすると、ロード/インストールエラーが生成されます。 "このパッケージには Microsoft Application Virtualization Client 4.5 以降が必要です" というメッセージが表示されます。 以下の回避策を使用してください。

WORKAROUNDOpen は、App-v 4.5 SP1 Sequencer または App-v 4.6 Sequencer のいずれかを使用して古いパッケージを作成し、パッケージの新しい .msi ファイルを生成します。

**注** または、コマンドプロンプトで、また*は/の* *msi*パラメーター (など) を使用して、新しい .msi ファイルを生成することもでき `SFTSequencer /Open:”package.sprj” /MSI` ます。 詳細については、[コマンドラインを使用して仮想アプリケーションをアップグレードする方法](how-to-upgrade-a-virtual-application-by-using-the-command-line.md)に関する説明を参照してください。

 

### リリースノートの著作権情報

このドキュメントは "現在のところ" として提供されています。 このドキュメントに記載されている情報および見解 (URL 等のインターネット Web サイトに関する情報を含む) は、将来予告なしに変更されることがあります。 使用のリスクを負うことができます。

ここに示すいくつかの例は、例示のためだけに用意されており、架空のものでもあります。実際の関連付けや接続は意図していないか、または推定する必要があります。

このドキュメントは、マイクロソフト製品に含まれる知的財産に対していかなる法的権利も付与しません。 お客様は、内部的な参照目的に限り、このドキュメントを複製して使用することができます。 このドキュメントは、内部的な参照目的に合わせて変更できます。



Microsoft、Active Directory、ActiveSync、ActiveX、Excel、SQL Server、windows、windows PowerShell、windows Server、Windows Vista は、Microsoft の会社グループの商標です。

その他のすべての商標は、該当する所有者に帰属します。

 

 





