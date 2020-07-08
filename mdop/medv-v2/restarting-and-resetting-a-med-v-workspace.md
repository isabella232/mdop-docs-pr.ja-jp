---
title: MED-V ワークスペースの再開とリセット
description: MED-V ワークスペースの再開とリセット
author: dansimp
ms.assetid: a959cdb3-a727-47c7-967e-e58f224e74de
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 48a644c2ed1668f87eb6e1a78521e780e8b783dd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825424"
---
# MED-V ワークスペースの再開とリセット


トラブルシューティング中に、MED-V ワークスペースを再起動またはリセットする必要がある場合があります。 MED-V ワークスペースの再起動は、基本的に物理コンピューターの再起動と同じです。 MED-V ワークスペースの再インストールをリセットすると、仮想マシンに保存されているすべてのデータが削除されます。 保存されているデータはすべて削除されるため、通常は、MED-V ワークスペースをリセットして、最も重大なトラブルシューティングの問題を解決するか、以前に動作していた MED-V ワークスペースを正常に動作する状態に戻す必要があります。

MED-V 管理ツールキットを開く方法の詳細については、「[管理ツールキットを使用した med-v のトラブルシューティング](troubleshooting-med-v-by-using-the-administration-toolkit.md)」を参照してください。

**MED-V ワークスペースを再起動する**

1.  [ **Med-v 管理ツールキット**] ウィンドウで、[ **Med-v を再起動**する] をクリックします。 ダイアログウィンドウが開き、MED-V ワークスペースを再起動する必要があることを確認する必要があります。

2.  [**再起動**] をクリックします。

    実行されている、または既にリダイレクトされている web サイトを開いているアプリケーションは、MED-V ワークスペースの再起動時に終了されます。

**MED-V ワークスペースのリセット**

1.  [ **Med-v 管理ツールキット**] ウィンドウで、[ **Med-v Workspace のリセット**] をクリックします。 ダイアログウィンドウが開き、MED-V ワークスペースのリセットを確認する必要があります。

    **警告** MED-V ワークスペースをリセットすると、初回のセットアップが再び実行され、元の仮想ハードディスクが再ロードされます。 最初にセットアップを実行してから、MED-V ワークスペースに保存されているすべてのデータが削除されます。

     

2.  **[初期状態に戻す]** をクリックします。

    実行されているか、開かれている web サイトが既に存在する場合は、MED-V ワークスペースをリセットすると、公開されたアプリケーションが終了します。

## 関連トピック


[MED-V ログの表示と構成](viewing-and-configuring-med-v-logs.md)

[MED-V ワークスペースの構成の表示](viewing-med-v-workspace-configurations.md)

 

 





