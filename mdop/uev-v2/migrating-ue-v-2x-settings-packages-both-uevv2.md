---
title: UE-V の設定パッケージを移行する
description: UE-V の設定パッケージを移行する
author: dansimp
ms.assetid: f79381f4-e142-405c-b728-5c048502aa70
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0aa1f1c36594d69de40306dfa70a4a0cf5c86dbb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825517"
---
# UE-V の設定パッケージを移行する


Microsoft User Experience Virtualization (UE-V) 2.0、2.1、または 2.1 SP1 の展開のライフサイクルでは、新しいサーバーに移行するとき、またはバックアップを実行するときに、ユーザー設定パッケージを再配置することが必要な場合があります。 次のシナリオでは、設定パッケージを移行する必要がある場合があります。

-   既存のサーバーハードウェアをより先進のサーバーにアップグレードします。

-   設定の保存場所の移行テストサーバーから運用サーバーに共有します。

ファイルとフォルダーをコピーするだけでは、セキュリティ設定とアクセス許可は維持されません。 次の手順では、設定パッケージを NTFS ファイルシステムのアクセス許可と共に新しい共有に適切にコピーする方法について説明します。

**新しいサーバーに移行するときに、UE-V 2 設定パッケージを保存するには**

1.  別のサーバー上の新しい場所に、新しいフォルダー (MySettings など) を作成します。

2.  古いサーバー上の古いフォルダー共有の共有を無効にします。

3.  Robocopy で既存の設定パッケージを新しいサーバーにコピーするには

    ``` syntax
    C:\start robocopy "\\servername\E$\MySettings" "\\servername\E$\MySettings" /b /sec /secfix /e /LOG:D:\Robocopylogs\MySettings.txt
    ```

    **注** コピーの進行状況を監視するには、Trace32 などのログビューアーで MySettings.txt を開きます。

     

4.  新しい共有に共有レベルのアクセス許可を付与します。 Robocopy によって設定された NTFS ファイルシステム権限をそのままにしておきます。

    UE-V Agent を実行しているコンピューターでは、 **Settingsstoragepath**構成設定を新しい共有の汎用名前付け規則 (UNC) パスに更新します。

    **Ue-v のご提案をお寄せ**ください。 [ここで](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)候補を追加または投票してください。 **Ue-v の問題が発生した場合** Ue-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)を使用します。

## 関連トピック


[UE-V 2. x の管理](administering-ue-v-2x-new-uevv2.md)

 

 





