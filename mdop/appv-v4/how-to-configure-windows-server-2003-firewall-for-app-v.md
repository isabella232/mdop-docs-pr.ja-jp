---
title: App-V 用に Windows Server 2003 ファイアウォールを構成する方法
description: App-V 用に Windows Server 2003 ファイアウォールを構成する方法
author: dansimp
ms.assetid: 2c0e80f8-41e9-4164-ac83-b23b132b489a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: af75479504b454851ee2efc7ca2638d2daf45053
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817727"
---
# App-V 用に Windows Server 2003 ファイアウォールを構成する方法


次の手順を使用して、WindowsServer 2003 ファイアウォールを App-v 用に構成します。

**WindowsServer 2003 ファイアウォールを App-v 用に構成するには**

1.  **コントロールパネル**で、 **Windows ファイアウォール**を開きます。

    **注** この手順を実行する前にサーバーがファイアウォールサービスを実行するように構成されていない場合は、ファイアウォールサービスを開始するように求められます。

     

2.  ICO ファイルと OSD ファイルが SMB 経由で公開されている場合は、[**例外**] タブで [**ファイルとプリンターの共有**] が有効になっていることを確認します。

    **注** 管理サーバー上の HTTP/HTTPS を使用して、ICO ファイルと OSD ファイルが公開されている場合、HTTP または HTTPS の例外を追加する必要がある場合があります。 ICO ファイルと OSD ファイルをホストしている IIS サーバーが管理サーバーとは別のコンピューターでホストされている場合は、そのコンピューターに例外を追加する必要があります。 パフォーマンスを最大にするには、管理サーバーとは別のサーバー上で ICO ファイルと OSD ファイルをホストすることをお勧めします。

     

3.  管理サーバーサービスの実行可能ファイルのプログラム例外を追加し `sghwdsptr.exe` ます。 この実行可能ファイルの既定のパスは `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\bin` です。

    **注** 管理サーバーで、通信に RTSP を使用している場合は、のプログラム例外も追加する必要があり `sghwsvr.exe` ます。

    App-v ストリーミングサーバーには、RTSPS 通信のプログラム例外が必要です `sglwdsptr.exe` 。 接続用に RTSP を使う App-v Streaming Server では、のプログラム例外も必要です `sglwsvr.exe` 。

     

4.  各例外に対して適切なスコープが構成されていることを確認します。 リスクを軽減するには、コンピューターを削除し、サーバーが応答する IP アドレスを厳密に制限します。

## 関連トピック


[App-V 用に Windows Server 2008 ファイアウォールを構成する方法](how-to-configure-windows-server-2008-firewall-for-app-v.md)

 

 





