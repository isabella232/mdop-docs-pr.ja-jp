---
title: Sequencer コマンド ライン エラー コード
description: Sequencer コマンド ライン エラー コード
author: dansimp
ms.assetid: 3d491314-4923-45fd-9839-c541c5e620bd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 74f5bd0c1b66656ac6891dcc1c019254fa36fdac
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815557"
---
# Sequencer コマンド ライン エラー コード


次の一覧は、コマンドラインを使用したアプリケーションの順序付けに関連するエラーを特定するのに役立ちます。 この情報は、関連する App-v のログファイルを表示することでも確認できます。

**注** シーケンス中に複数のエラーが発生する可能性があります。この場合、表示されるエラーコードは、2つのエラーコードの合計である可能性があります。 たとえば、 */InstallPath*パラメーターと */OutputFile*パラメーターが指定されていない場合、app-v Sequencer は**96**(2 つのエラーコードの合計) を返します。

 

<a href="" id="01"></a>付き  
予期しないエラーが発生しています。

<a href="" id="02"></a>+  
指定されたインストールディレクトリ (/INSTALLPACKAGE) が有効ではありません。

<a href="" id="04"></a>04  
指定されたパッケージルートディレクトリ (/INSTALLPATH) が有効ではありません。

<a href="" id="08"></a>08  
指定された */OutputFile*パラメーターが有効ではありません。

<a href="" id="16"></a>16  
インストールディレクトリ (/INSTALLPACKAGE) が指定されていません。

<a href="" id="32"></a>32  
パッケージルートディレクトリ (/INSTALLPATH) が指定されていません。

<a href="" id="64"></a>64  
*/OutputFile*パラメーターが指定されていません。

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
指定したブロックサイズ (/KB) が有効ではありません。

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
パッケージ名が指定されていません。

## 関連トピック


[Application Virtualization Sequencer リファレンス](application-virtualization-sequencer-reference.md)

[Sequencer コマンド ライン パラメーター](sequencer-command-line-parameters.md)

 

 





