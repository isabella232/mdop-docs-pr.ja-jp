---
title: App-V サーバー用にファイアウォールを構成する
description: App-V サーバー用にファイアウォールを構成する
author: dansimp
ms.assetid: f779c450-6c6f-46a8-ac66-5e82e0689d55
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 92db727eb060546ab71f2c647f2d89b662be5c64
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821817"
---
# App-V サーバー用にファイアウォールを構成する


Microsoft Application Virtualization (App-v) Management サーバーまたはストリーミングサーバーをインストールして、RTSP または RTSPS プロトコルを使用するように構成したら、App-v プログラムのファイアウォール例外を作成する必要があります。

## Application Virtualization Management Server のファイアウォール例外の構成


**sghwdsptr.exe**と**sghwsvr.exe**のファイアウォール例外を作成します。 これらのプログラムは、32ビットオペレーティングシステム上のフォルダー Virt ¥¥¥ System Center app Virt Management server¥ files に記載されています。 64ビット版のオペレーティングシステムを使用している場合、このフォルダーは c/c/Virt files (x86) の下にあります。 \\ Microsoft System Center App Virt Management Server\\ app Management Server\\bin.

## Application Virtualization Streaming Server のファイアウォール例外の構成


**sglwdsptr.exe**と**sglwsvr.exe**のファイアウォール例外を作成します。 これらのプログラムは、32ビットオペレーティングシステム上のフォルダー Virt Virt ¥¥ System Center app xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx 64ビット版のオペレーティングシステムを使用している場合、このフォルダーは c/c/Virt ファイル (x86) の下にあります。 \\ Microsoft System Center App Streaming Server\\ app Virt ストリーミング Server\\bin.

## 関連トピック


[サーバー ベースの展開用にサーバーを構成する方法](how-to-configure-servers-for-server-based-deployment.md)

[既定のアプリケーションをインストールして構成する方法](how-to-install-and-configure-the-default-application.md)

 

 





