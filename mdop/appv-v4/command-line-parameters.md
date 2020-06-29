---
title: コマンド ライン パラメーター
description: コマンド ライン パラメーター
author: dansimp
ms.assetid: d90a0591-f1ce-4cb8-b244-85cc70461922
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 31d6ca1215648e2519e9818817ab5cc779a746d0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819404"
---
# コマンド ライン パラメーター


次の Application Virtualization Sequencer パラメーターを使用して、アプリケーションのシーケンスを実行し、コマンドプロンプトでシーケンス処理されたアプリケーションパッケージをアップグレードします。 Microsoft Application Virtualization Sequencer ディレクトリで、「 **Sftsequencer**」と入力し、その後に適切なパラメーターを入力します。

<a href="" id="-help-or---"></a>*/Help*または */?*  
コマンドラインの順序付けに使用できるパラメーターの一覧を表示するために使用します。

<a href="" id="-installpackage-or--i"></a>*/INSTALLPACKAGE*または */i*  
アプリケーションを順序付けするインストーラーまたはバッチファイルを指定するために使用します。

<a href="" id="-installpath-or--p"></a>*/INSTALLPATH*または */p*  
パッケージルートディレクトリを指定するために使用します。

<a href="" id="-outputfile-or--o"></a>*/OUTPUTFILE*または */o*  
生成される SPRJ ファイルのパスとファイル名を指定するために使用します。

**重要** */OUTPUTFILE*パラメーターは、アップグレードを意図していないパッケージを開くときには使用できません。

 

<a href="" id="-fullload-or--f"></a>*/Fullload*または */f*  
すべてをプライマリ機能ブロックに含めるかどうかを指定します。

<a href="" id="-packagename-or--k"></a>*/PACKAGENAME*または */k*  
シーケンスアプリケーションのパッケージ名を指定するために使用します。

<a href="" id="-blocksize"></a>*/BLOCKSIZE*  
パッケージをクライアントコンピューターにストリーミングするために使用される SFT ファイルブロックサイズを指定します。 次のいずれかの値を選ぶことができます。

-   4 KB

-   16 KB

-   32 KB

-   64 KB

ブロックサイズを指定するときは、SFT ファイルのサイズを考慮する必要があります。 ブロックサイズが小さいファイルは、ネットワーク上でのストリーミングには時間がかかりますが、帯域幅の消費が少なくなります。 ブロックサイズが大きいファイルでは、より多くのネットワーク帯域幅が使用されます。

<a href="" id="-compression"></a>*/圧縮*  
クライアントにストリーミングされるときに、SFT ファイルを圧縮するためのメソッドを指定するために使用します。

<a href="" id="-msi-or--m"></a>*/MSI*または */m*  
シーケンスアプリケーションの Microsoft Windows インストーラーパッケージの生成を指定するために使用します。

<a href="" id="-default"></a>*/DEFAULT*  
仮想アプリケーションパッケージの作成時に使用される既定の SPRJ ファイルを指定します。 このファイルは、アプリケーションを初めてシーケンスするときに、sprj テンプレートとして使用されます。

<a href="" id="-upgrade"></a>*/UPGRADE*  
アップグレードされる SPRJ ファイルのパスとファイル名を指定します。

<a href="" id="-decodepath"></a>*/DECODEPATH*  
シーケンス処理対象のアプリケーションパッケージに関連付けられたファイルがインストールされている、シーケンスコンピューター上のディレクトリを指定します。 ディレクトリを指定するときは、次のいずれかの形式を使用します。

-   /decodepath: Q:

-   /decodepath: Q:.

-   /decodepath: "Q:."

-   /decodepath: "Q:"

## 関連トピック


[Sequencer コマンド ラインの使用について](about-using-the-sequencer-command-line.md)

[コマンド ラインを使用してシーケンス処理されたアプリケーションを開く方法](how-to-open-a-sequenced-application-using-the-command-line.md)

[パッケージを開くコマンドを使用してパッケージをアップグレードする方法](how-to-upgrade-a-package-using-the-open-package-command.md)

 

 





