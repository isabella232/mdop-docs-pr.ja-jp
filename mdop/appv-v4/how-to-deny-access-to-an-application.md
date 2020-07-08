---
title: アプリケーションへのアクセスを拒否する方法
description: アプリケーションへのアクセスを拒否する方法
author: dansimp
ms.assetid: 14f5e201-7265-462c-b738-57938dc3fc30
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 56a89669ea8c6323023b585d6d58620cd203fc00
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817517"
---
# アプリケーションへのアクセスを拒否する方法


アプリケーションの読み込みと使用を行うには、ユーザーがアプリケーションの**アクセス許可**の一覧に含まれている必要があります。 Application Virtualization Server 管理コンソールは、アプリケーションへのユーザーグループアクセスの明示的な拒否をサポートしていませんが、これを実現するには、アプリケーションのプロパティからユーザーグループを削除できます。

**アプリケーションへのアクセスを拒否するには**

1.  既存のアプリケーションの場合は、左側のウィンドウで [**アプリケーション**] ノードをクリックします。

2.  右側のウィンドウでアプリケーションを右クリックし、[**プロパティ**] を選択します。 次に、[**アクセス許可**] タブを選択します。

3.  ユーザーグループのアクセスを削除するには、ユーザーグループを強調表示し、[**削除**] をクリックします。

4.  **[OK]** をクリックします。

    **注** アプリケーションへのアクセスを制御するために、アプリケーションライセンスを制限することもできます。 Active Directory ドメインサービスで適切なユーザーグループを設定することで、特定のユーザーのセットへのアクセスを許可したり、拒否したりすることが簡単になります。

     

## 関連トピック


[アプリケーションへのアクセスを許可する方法](how-to-grant-access-to-an-application.md)

[サーバー管理コンソールでアプリケーション ライセンスを管理する方法](how-to-manage-application-licenses-in-the-server-management-console.md)

[サーバー管理コンソールでアプリケーションを管理する方法](how-to-manage-applications-in-the-server-management-console.md)

 

 





