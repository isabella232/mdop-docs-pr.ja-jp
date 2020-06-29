---
title: App-V Management Server 用に Windows Server 2008 を構成する方法
description: App-V Management Server 用に Windows Server 2008 を構成する方法
author: dansimp
ms.assetid: 38b4016f-de82-4209-9159-387d20ddee25
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2d1cd7e84ffc0036c98e70a9a0ee1fd3a4ade790
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817724"
---
# App-V Management Server 用に Windows Server 2008 を構成する方法


Microsoft Application Virtualization (App-v) Management Web サービスをインストールする Windows Server 2008 サーバーでは、インターネットインフォメーションサービス (IIS) がサーバー上の役割としてインストールされている必要があります。 次の手順を使用して、Vserver のインストールをサポートするように Windows Server 2008 を構成します。

**Windows Server2008 コンピューターに IIS をインストールするには**

1.  Windows Server2008 コンピューターで、[**スタート**] をクリックし、[**すべてのプログラム**]、[**管理ツール**]、[**サーバーマネージャー** ] の順にクリックしてサーバーマネージャーを起動します。 サーバーマネージャーで、[**役割**] ノードを右クリックし、[役割の**追加**] をクリックして**役割の追加ウィザード**を開始します。

2.  役割の**追加ウィザード**の **[サーバーの役割の選択**] ページで、[ **Web サーバー (IIS)**] を選びます。 メッセージが表示されたら、[**必須機能の追加**] をクリックして、依存機能を追加します。

3.  [**サーバーの役割の選択**] ページで、[**次へ**] をクリックし、もう一度 [**次へ**] をクリックします。

4.  役割の**追加ウィザード**の **[役割サービスの選択**] ページで、次の操作を行います。

    1.  [**アプリケーション開発**] の下の [ **ASP.NET** ] を選択し、メッセージが表示されたら、[**必須ロールサービスの追加**] をクリックして、依存型ロールのサービスと機能を追加します。

    2.  [**セキュリティ**] で、[ **Windows 認証**] を選びます。

    3.  [ **Management Tools** ] ノードで、[ **IIS 管理スクリプトとツール**] を選びます。 [ **IIS6 Management compatibility**] で、[ **IIS6 メタベースの互換性**と**IIS6 の WMI 互換**] の両方が選択されていることを確認して、[**次へ**] をクリックします。

5.  [**インストールオプションの確認**] ページで、[**インストール**] をクリックし、ウィザードの残りの手順を実行します。

6.  [**閉じる**] をクリックして**役割の追加ウィザード**を終了し、[サーバーマネージャー] を閉じます。

## 関連トピック


[Application Virtualization の展開要件](application-virtualization-deployment-requirements.md)

[Application Virtualization の展開およびアップグレードのチェックリスト](application-virtualization-deployment-and-upgrade-checklists.md)

 

 





