---
title: 公開サーバーからパッケージと接続グループの更新を受信するように Client を構成する方法
description: 公開サーバーからパッケージと接続グループの更新を受信するように Client を構成する方法
author: dansimp
ms.assetid: 23b2d03a-20ce-4973-99ee-748f3b682207
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 034cf5255d75bbaf6a5e65357bd5b3d472344f03
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814394"
---
# 公開サーバーからパッケージと接続グループの更新を受信するように Client を構成する方法


App-v 5.1 発行サーバーを使用してパッケージと接続グループを展開すると、単一ポイント管理と高いスケーラビリティが実現されるため便利です。

次の手順を使用して、公開サーバーから更新プログラムを受け取るように、App-v 5.1 クライアントを構成します。

**注** 次の手順では、管理サーバーが**MyMgmtSrv**という名前のコンピューターにインストールされており、発行サーバーが**MyPubSrv**という名前のコンピューターにインストールされています。

 

**公開サーバーから更新プログラムを受信するように App-v 5.1 クライアントを構成するには**

1.  App-v 5.1 management と発行サーバーを展開し、必要なパッケージと接続グループを追加します。 パッケージと接続グループの追加の詳細については、「[管理コンソールを使用してパッケージを追加またはアップグレードする方法](how-to-add-or-upgrade-packages-by-using-the-management-console-51-gb18030.md)」と「[接続グループを作成する方法](how-to-create-a-connection-group51.md)」を参照してください。

2.  管理コンソールを開くには、次のリンクをクリックし、ブラウザーを開いて次のように入力し http://MyMgmtSrv/AppvManagement/Console.html ます。 web ブラウザーで、すべてのパッケージと接続グループをインポート、公開、entitle して、特定のユーザーのセットに必要となるすべてのパッケージと接続グループを設定します。

3.  App-v 5.1 クライアントを実行しているコンピューターで、管理者特権の PowerShell コマンドプロンプトを開き、次のコマンドを実行します。

    **AppvPublishingServer-Name ABC-URL http://MyPubSrv/AppvPublishing**

    このコマンドは、指定した発行サーバーを構成します。 次のような出力が表示されます。

    Id: 1

    SetByGroupPolicy: False

    名前: ABC

    URL: http://MyPubSrv/AppvPublishing

    GlobalRefreshEnabled: False

    GlobalRefreshOnLogon: False

    GlobalRefreshInterval: 0

    GlobalRefreshIntervalUnit: Day

    UserRefreshEnabled: True

    UserRefreshOnLogon True

    UserRefreshInterval: 0

    UserRefreshIntervalUnit: Day

    返された Id –この例では1

4.  App-v 5.1 クライアントを実行しているコンピューターで、PowerShell コマンドプロンプトを開き、次のコマンドを入力します。

    **同期-AppvPublishingServer-ServerId 1**

    このコマンドは、管理サーバーで構成されたパッケージと接続グループの権限に基づいて、特定のクライアントに対して追加または削除する必要があるパッケージと接続グループの発行サーバーを照会します。

    App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[APP-V 5.1 の操作](operations-for-app-v-51.md)

 

 





