---
title: UE-V 設定パッケージの移行
description: UE-V 設定パッケージの移行
author: dansimp
ms.assetid: 93d99254-3e17-4e96-92ad-87059d8554a7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d0087f334e916c06e7611d2671d0b50e7d1dd916
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823207"
---
# UE-V 設定パッケージの移行


Microsoft User Experience Virtualization (UE-V) の展開のライフサイクルでは、新しいサーバーまたはバックアップ目的で、ユーザー設定パッケージを再配置する必要がある場合があります。 設定パッケージの移行は、次のシナリオで必要となる場合があります。

-   既存のサーバーハードウェアをより先進のサーバーにアップグレードします。

-   設定の保存場所の移行ラボから運用サーバーへの共有。

ファイルとフォルダーをコピーするだけでは、セキュリティ設定とアクセス許可は維持されません。 次の手順では、設定パッケージのファイルが、NTFS アクセス許可を持つ新しい共有に適切にコピーされます。

**新しいサーバーに移行するときに、UE-V 設定パッケージを保存する方法**

1.  別のサーバー上の新しい場所で、新しいフォルダーを作成します。たとえば、MySettings などです。

2.  古いサーバー上の古いフォルダー共有の共有を無効にします。

3.  コマンドラインから Robocopy を使用して、既存の設定パッケージを新しいサーバーに移動します。 以下に例を示します。

    ``` syntax
    c:\start robocopy "\\servername\E$\MySettings" "\\servername\E$\MySettings" /b /sec /secfix /e /LOG:D:\Robocopylogs\MySettings.txt
    ```

    **注** コピーの進行状況を監視するには、Trace32 などのログファイルリーダーで MySettings.txt を開きます。

     

4.  新しい共有に共有レベルのアクセス許可を付与します。 Robocopy によって設定された NTFS アクセス許可をそのままにします。

    UE-V agent を実行しているコンピューターで、SettingsStoragePath 構成設定を新しい共有の UNC パスに更新します。

## 関連トピック


[UE-V 1.0 の管理](administering-ue-v-10.md)

[UE-V 1.0 の操作](operations-for-ue-v-10.md)

 

 





