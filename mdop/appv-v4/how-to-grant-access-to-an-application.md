---
title: アプリケーションへのアクセスを許可する方法
description: アプリケーションへのアクセスを許可する方法
author: dansimp
ms.assetid: e54d9e84-21f5-488f-b040-25f374d9289f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9cd3dfe4661f09bb7e7d3514a397955cb892be81
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817434"
---
# アプリケーションへのアクセスを許可する方法


管理者は、Application Virtualization Server 管理コンソールを使用して、どのユーザーがどのアプリケーションにアクセスできるかを判断することができます。 この操作は、Sequencer プロジェクト (SPRJ) または Open Software Descriptor (OSD) ファイルをインポートするとき、またはアプリケーションの [**プロパティ**] ダイアログボックスを使っていつでも実行できます。 どちらの方法でも、[**アクセス許可**] オプションを使用してユーザーを追加します。

**アプリケーションへのアクセスを許可するには**

1.  既存のアプリケーションの場合は、左側のウィンドウで [**アプリケーション**] ノードをクリックします。 右側のウィンドウでアプリケーションを右クリックし、[**プロパティ**] を選択します。

2.  [**アクセス許可**] タブを選択します。

3.  ユーザーグループを追加するには、[**追加**] をクリックします。

4.  [**ユーザーグループの追加/編集**] ダイアログボックスで、[ユーザー] グループに移動します。 各フィールドに情報を入力して、ドメインとグループを入力することもできます。

5.  **[OK]** をクリックします。 同じページを持つ他のグループを追加することもできます。

6.  ウィザードが再び表示されたら、[ **OK]** をクリックします。

    **注** アプリケーションへのアクセス許可を付与する前に、Active Directory ドメインサービスでグループを設定する必要があります。

     

## 関連トピック


[アプリケーションへのアクセスを拒否する方法](how-to-deny-access-to-an-application.md)

[サーバー管理コンソールでアプリケーション グループを管理する方法](how-to-manage-application-groups-in-the-server-management-console.md)

[サーバー管理コンソールでアプリケーション ライセンスを管理する方法](how-to-manage-application-licenses-in-the-server-management-console.md)

[アプリケーションを手動で追加する方法](how-to-manually-add-an-application.md)

 

 





