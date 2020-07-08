---
title: アーカイブの管理
description: アーカイブの管理
author: dansimp
ms.assetid: b11a3d71-74ea-4dd7-b243-6f2880b7af2d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 682d720b4095dbfa6a7cc4d868109f57c4f54641
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820557"
---
# アーカイブの管理


[高度なグループポリシー管理 (AGPM)] は、AGPM 管理者 (フルコントロール) として、アーカイブへのアクセスを管理し、アーカイブに保存されている各グループポリシーオブジェクト (GPO) のバージョン数を制限するオプションを備えています。 アーカイブ内の Gpo へのアクセスは、ドメインレベルまたは GPO レベルで委任できます。 さらに、障害が発生した場合に復元できるようにアーカイブのバックアップを作成することもできます。

AGPM 管理者として、GPO をファイルにエクスポートし、そのファイルを別のフォレストにコピーして、そのフォレストのドメインに GPO をインポートすることができます。 エディターとは異なり、GPO バックアップのポリシー設定は、作成時に新しい制御された GPO に直接インポートできます。 GPO のエクスポート方法の詳細については、「 [gpo をファイルにエクスポート](export-a-gpo-to-a-file.md)する」を参照してください。

-   [アーカイブへのドメイン レベルのアクセスを委任する](delegate-domain-level-access-to-the-archive-agpm40.md)

-   [アーカイブ内の個々の GPO へのアクセスを委任する](delegate-access-to-an-individual-gpo-in-the-archive-agpm40.md)

-   [保存される GPO のバージョンを制限する](limit-the-gpo-versions-stored-agpm40.md)

-   [ファイルから GPO をインポートする](import-a-gpo-from-a-file-agpmadmin.md)

-   [アーカイブをバックアップする](back-up-the-archive-agpm40.md)

-   [バックアップからアーカイブを復元する](restore-the-archive-from-a-backup-agpm40.md)

### その他の参照情報

-   運用環境で Gpo へのアクセスを委任する方法については、「[運用環境へのアクセスを](delegate-access-to-the-production-environment-agpm40.md)委任する」を参照してください。

-   アーカイブの移動方法については、「 [AGPM サーバーとアーカイブの移動](move-the-agpm-server-and-the-archive-agpm40.md)」を参照してください。

-   [AGPM 管理者タスクの実行](performing-agpm-administrator-tasks-agpm40.md)

 

 





