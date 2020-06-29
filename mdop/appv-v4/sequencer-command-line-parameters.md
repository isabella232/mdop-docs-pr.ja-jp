---
title: Sequencer コマンド ライン パラメーター
description: Sequencer コマンド ライン パラメーター
author: dansimp
ms.assetid: 28fb875a-c302-4d95-b2e0-8dc0c5dbb0f8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ecfa269de04cf3dcba30cbb4a40f9176f03f6571
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815554"
---
# Sequencer コマンド ライン パラメーター


次の Application Virtualization (App-v) Sequencer パラメーターを使用して、アプリケーションの順序を管理したり、コマンドラインを使用して既存の仮想アプリケーションをアップグレードしたりすることができます。 コマンドラインを使用してアプリケーションをシーケンス処理する方法について詳しくは、[コマンドラインを使用して新しいアプリケーションを順序付ける方法](how-to-sequence-a-new-application-by-using-the-command-line.md)をご覧ください。

## Sequencer コマンド ライン パラメーター


<a href="" id="-help-or---"></a>**/HELP または/?**  
コマンドラインを使用してアプリケーションをシーケンス処理するときに使用できるパラメーターに関する情報を表示します。

<a href="" id="-installpackage-or--i"></a>**/INSTALLPACKAGE または/I**  
シーケンス可能なアプリケーションをインストールするために使用される Windows インストーラーまたはバッチファイルを指定します。

<a href="" id="-installpath-or--p"></a>**/INSTALLPATH または/P**  
アプリケーションのパッケージルートディレクトリを指定します。

<a href="" id="-outputfile-or--o"></a>**/OUTPUTFILE または/O**  
生成される SPRJ ファイルのパスとファイル名を指定します。

<a href="" id="-fullload-or--f"></a>**/Fullload または/F**  
すべてのファイルをプライマリ機能ブロックに含めるかどうかを指定します。 コマンドラインで **/fullload**パラメーターを指定した場合、関連付けられているすべてのアプリケーションデータが、プライマリ機能ブロックに追加されます。 コマンドラインで **/fullload**パラメーターが指定されていない場合、関連付けられているアプリケーションデータは、プライマリ機能ブロックに追加されません。

<a href="" id="-packagename-or--k"></a>**/PACKAGENAME または/K**  
シーケンス付けされたアプリケーションに割り当てるパッケージ名を指定します。

<a href="" id="-blocksize"></a>**/BLOCKSIZE**  
パッケージをクライアントコンピューターにストリーミングするために使用される SFT ファイルブロックサイズを指定します。 次のいずれかの値を選ぶことができます。

-   4 KB

-   16 KB

-   32 KB

-   64 KB

ブロックサイズを指定するときは、SFT ファイルのサイズを考慮する必要があります。 ブロックサイズが小さいファイルは、ネットワーク上でのストリーミングには時間がかかりますが、帯域幅の消費が少なくなります。 ブロックサイズが大きいファイルでは、より多くのネットワーク帯域幅が使用されます。

<a href="" id="-compression"></a>**/圧縮**  
クライアントにストリーミングされる SFT ファイルを圧縮するためのメソッドを指定します。

<a href="" id="-msi-or--m"></a>**/MSI または/M**  
シーケンス付きアプリケーションの Windows インストーラーを作成するかどうかを指定します。

<a href="" id="-default"></a>**/DEFAULT**  
仮想アプリケーションパッケージの作成時に使用される既定の SPRJ ファイルを指定します。 このファイルは、アプリケーションを初めてシーケンスするときに、sprj テンプレートとして使用されます。

<a href="" id="-upgrade"></a>**/UPGRADE**  
アップグレードされる SPRJ ファイルのパスとファイル名を指定します。

<a href="" id="-decodepath"></a>**/DECODEPATH**  
シーケンス処理対象のアプリケーションパッケージに関連付けられたファイルがインストールされている、シーケンスコンピューター上のディレクトリを指定します。 ディレクトリを指定するときは、次のいずれかの形式を使用します。

-   /decodepath: Q:

-   /decodepath: Q:.

-   /decodepath: "Q:."

-   /decodepath: "Q:"

## 関連トピック


[Application Virtualization Sequencer](application-virtualization-sequencer.md)

[Sequencer コマンド ライン エラー コード](sequencer-command-line-error-codes.md)

 

 





