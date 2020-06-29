---
title: 共有コンテンツ ストア モードの App-V 5.0 Client のインストール方法
description: 共有コンテンツ ストア モードの App-V 5.0 Client のインストール方法
author: dansimp
ms.assetid: 88f09e6f-19e7-48ea-965a-907052d1a02f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 704ea6c1e4b1ba4670a4e52d754b8e6e5a9fb8f4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814058"
---
# 共有コンテンツ ストア モードの App-V 5.0 Client のインストール方法


Microsoft Application Virtualization (App-v) 5.0 クライアントをインストールするには、次の手順を使用して、App-v 5.0 Shared Content Store (SCS) モードを使用するようにします。 必要なすべての前提条件が、インストール先のコンピューターにインストールされていることを確認する必要があります。 [App-v 5.0 の前提条件](app-v-50-prerequisites.md)については、次のリンクを使用してください。

**注** 必要に応じてこの手順を実行する前に、既存のバージョンの App-v 5.0 クライアントをアンインストールしてください。

 

SCS モードの詳細については、「 [Microsoft App の共有コンテンツストア-V 5.0 –バックグラウンドでの共有コンテンツストア ()](https://go.microsoft.com/fwlink/?LinkId=316879) 」を参照してください https://go.microsoft.com/fwlink/?LinkId=316879) 。

**SCS モード用に App-v 5.0 クライアントをインストールして構成する**

1.  アプリがインストールされているコンピューターに、App-v 5.0 クライアントのインストールファイルをコピーします。 インストールファイルが保存されているディレクトリからコマンドラインを開き、インストールしているクライアントのバージョンに応じて、次のいずれかのオプションを選択します。

    -   RDS バージョンの App-v 5.0 クライアントの種類をインストールするには、 **appv\_client\_setup\_rds.exe/sharedcontentstoremode = 1/q**

    -   App-v 5.0 クライアントの種類の標準バージョンをインストールするには、 **appv\_client\_setup.exe/sharedcontentstoremode = 1/q**

        **重要** サイレントインストールを実行する必要があります。インストールは失敗します。

         

2.  インストールが完了したら、クライアントを実行しているコンピューターにパッケージを展開することができます。また、すべてのパッケージコンテンツはネットワーク経由でストリーミングされます。

    App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[App-V 5.0 Sequencer および Client の展開](deploying-the-app-v-50-sequencer-and-client.md)

 

 





