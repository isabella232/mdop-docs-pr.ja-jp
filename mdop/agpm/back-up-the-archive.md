---
title: アーカイブをバックアップする
description: アーカイブをバックアップする
author: dansimp
ms.assetid: 400176da-3518-4475-ad19-c96cda6ca7ba
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a75099e7a6624850ee0511cf65feddf63909a0c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819207"
---
# アーカイブをバックアップする


高度なグループポリシー管理 (AGPM) のアーカイブを回復するのに役立ちます。障害が発生した場合は、AGPM 管理者 (フルコントロール) が頻繁にアーカイブをバックアップする必要があります。 既定では、アーカイブは% ¥で作成されます。 ただし、Microsoft Advanced グループポリシー管理サーバーのセットアップ中は、別のパスを指定できます。

この手順を完了するには、agpm サービスがインストールされているコンピューターと、そのアーカイブを含むフォルダーの両方へのアクセス権を持つユーザーアカウントが必要です。

**アーカイブのバックアップを作成するには**

1.  AGPM サービスを停止します。 詳細については、「 [AGPM サービスの開始と停止](start-and-stop-the-agpm-service-agpm30ops.md)」を参照してください。

2.  Windows エクスプローラー、Xcopy、Windows Server®バックアップ、または別のバックアップツールを使用して、[アーカイブ] フォルダーをバックアップします。 非表示、システム、および読み取り専用のファイルをバックアップしてください。

3.  アーカイブバックアップを安全な場所に保存します。

4.  AGPM サービスを再起動します。 詳細については、「 [AGPM サービスの開始と停止](start-and-stop-the-agpm-service-agpm30ops.md)」を参照してください。

**注** AGPM 管理者がアーカイブを頻繁にバックアップしない場合、アーカイブバックアップのグループポリシーオブジェクト (Gpo) は最新の状態にはなりません。 アーカイブバックアップが最新の状態になるように、組織のデイリーバックアップ戦略の一部としてアーカイブをバックアップします。

 

### その他の参照情報

-   [バックアップからアーカイブを復元する](restore-the-archive-from-a-backup.md)

-   [AGPM サーバーとアーカイブを移動する](move-the-agpm-server-and-the-archive.md)

-   [アーカイブの管理](managing-the-archive.md)

 

 





