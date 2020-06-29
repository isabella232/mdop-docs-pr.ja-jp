---
title: パッケージ ルート ディレクトリを作成する方法
description: パッケージ ルート ディレクトリを作成する方法
author: dansimp
ms.assetid: bcfe3bd4-6c60-409a-8ffa-cc22f27194b1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c9e1e7be71627d4e55eff7a4e2582a21b834876d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817627"
---
# パッケージ ルート ディレクトリを作成する方法


パッケージルートディレクトリは、シーケンス付けされたアプリケーションのファイルがインストールされる、App-v Sequencer を実行しているコンピューター上のディレクトリです。 このディレクトリは、シーケンスされたアプリケーションをストリーミングするコンピューター上でも実質的に存在します。 新しいアプリケーションのインストールを監視する前に、パッケージルートディレクトリを作成する必要があります。

パッケージルートディレクトリを作成したら、アプリケーションのシーケンスを開始できます。 新しいアプリケーションのシーケンスの詳細については、「 [Sequencer をインストールする方法](how-to-install-the-sequencer.md)」を参照してください。

**パッケージルートディレクトリを作成するには**

1.  パッケージルートディレクトリを作成するには、App-v Sequencer を実行しているコンピューターで、Q:\\ drive を指定したネットワークの場所にマップします。 指定した場所には、順序を設定するアプリケーションを保存するための十分な領域がある必要があります。

2.  新しい仮想アプリケーションに使用できるディレクトリを作成するには、Q:\\ ドライブ上にフォルダーを作成し、それに名前を割り当てます。

    **重要** パッケージルートディレクトリに保存される仮想アプリケーションファイルに割り当てる名前では、8.3 の名前付け形式を使用する必要があります。 ファイル名は、3文字のファイル名拡張子を持つ8文字以内にする必要があります。

     

## 関連トピック


[Application Virtualization Sequencer のタスク](tasks-for-the-application-virtualization-sequencer.md)

 

 





