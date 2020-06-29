---
title: コマンド ライン エラー
description: コマンド ライン エラー
author: dansimp
ms.assetid: eea62568-4e90-4877-9cc7-e27ef5c05068
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ab29a77dc15a8c7bd3590b918a7ca8c1ca6e8c0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819407"
---
# コマンド ライン エラー


以下のエラーリストを使用して、コマンドラインの順序付けが正常に機能していない理由を特定します。 また、sequencer ログファイルを表示して、これらのエラーを表示することもできます。

**注** 順序付け時に複数のエラーが表示されることがあります。 さらに、表示されるエラーコードは、2つのエラーコードの合計である場合があります。 たとえば、 */InstallPath*パラメーターと */OutputFile*パラメーターが指定されていない場合、Microsoft System Center Application Virtualization Sequencer は 96 (2 つのエラーコードの合計) を返します。

 

<a href="" id="01"></a>付き  
予期しないエラーが発生しています。

<a href="" id="02"></a>+  
指定したインストールディレクトリ (/INSTALLPACKAGE) が有効ではありません。

<a href="" id="04"></a>04  
指定されたパッケージルートディレクトリ (/INSTALLPATH) が有効ではありません。

<a href="" id="08"></a>08  
指定された */OutputFile*パラメーターが有効ではありません。

<a href="" id="16"></a>16  
インストールディレクトリ (/INSTALLPACKAGE) が指定されていませんでした。

<a href="" id="32"></a>32  
パッケージルートディレクトリ (/INSTALLPATH) が指定されていませんでした。

<a href="" id="64"></a>64  
*/OutputFile*パラメーターが指定されていませんでした。

<a href="" id="128"></a>128  
指定した application virtualization ドライブは有効ではありません。

<a href="" id="256"></a>256  
インストーラーが失敗しました。

<a href="" id="512"></a>512  
アプリケーションのシーケンス処理に失敗しました。

<a href="" id="1024"></a>1024  
インストールされたショートカットの評価に失敗しました。

<a href="" id="2048"></a>2048  
シーケンス付きのアプリケーションパッケージを保存できません。

<a href="" id="4096"></a>4096  
指定されたパッケージ名 (/PACKAGENAME) が有効ではありません。

<a href="" id="8192"></a>8192  
指定したブロックサイズ (/KB <em> ) </em> が有効ではありません。

<a href="" id="16384"></a>16384  
指定された圧縮の種類 (圧縮) が有効ではありません。

<a href="" id="32768"></a>32768  
指定されたプロジェクトパスが有効ではありません。

<a href="" id="65536"></a>65536  
指定されたアップグレードパラメーターが有効ではありません。

<a href="" id="131072"></a>131072  
指定されたアップグレードプロジェクトパラメーターが有効ではありません。

<a href="" id="262144"></a>262144  
指定したデコードパスパラメーターが有効ではありません。

<a href="" id="525288"></a>525288  
パッケージ名が指定されていませんでした。

## 関連トピック


[Sequencer コマンド ラインの使用について](about-using-the-sequencer-command-line.md)

[コマンド ライン パラメーター](command-line-parameters.md)

 

 





