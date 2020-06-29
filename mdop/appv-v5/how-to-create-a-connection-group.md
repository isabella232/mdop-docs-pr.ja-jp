---
title: 接続グループを作成する方法
description: 接続グループを作成する方法
author: dansimp
ms.assetid: 9d272052-2d28-4e41-989c-89610482a0ca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 816fc3b37be056ed54a88c394ef64fa1edaf47ee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814339"
---
# 接続グループを作成する方法


以下の手順を使用して、App-v 管理コンソールを使用して接続グループを作成します。 PowerShell を使用して接続グループを作成する方法については、「 [Powershell を使用してスタンドアロンコンピューターで接続グループを管理する方法](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md)」を参照してください。

接続グループにパッケージを配置すると、そのパッケージのルートパスがマージされます。 パッケージを削除した場合、残りのパッケージだけがマージされたルートを保持します。

**接続グループを作成するには**

1.  App-v 5.0 管理コンソールで、[**パッケージ**] を選びます。

2.  [**接続グループ**] を選択して、接続グループライブラリを表示します。

3.  [**接続グループの追加**] を選択して、新しい接続グループを作成します。

4.  [**新しい接続グループ**] ウィンドウで、グループの説明を入力します。

5.  [接続**されているパッケージ**] ウィンドウで [**編集**] をクリックして、新しいアプリケーションを接続グループに追加します。

6.  [**ライブラリ全体のパッケージ**] ウィンドウで、追加するアプリケーションを選択し、矢印をクリックしてアプリケーションを追加します。

    アプリケーションを削除するには、[パッケージ] ウィンドウ**で**削除するアプリケーションを選択し、矢印をクリックします。

    接続グループ内のアプリケーションの優先順位を再度するには、 **[パッケージ**] ウィンドウの [パッケージ] の矢印を使用します。

    **重要** 既定では、特定のアプリケーションに関連付けられている Active Directory ドメインサービスのアクセス構成は、接続グループに追加されません。 Active Directory access の構成を移行するには、[**パッケージアクセスの追加**] を選択します。これは、[**パッケージ**] ウィンドウにあります。

     

7.  すべてのアプリケーションを追加して Active Directory アクセスを構成したら、[**適用**] をクリックします。

    App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[APP-V 5.0 の操作](operations-for-app-v-50.md)

[接続グループの管理](managing-connection-groups.md)

 

 





