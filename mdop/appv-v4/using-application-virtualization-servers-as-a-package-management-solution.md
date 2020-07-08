---
title: パッケージ管理ソリューションとしての Application Virtualization サーバーの使用
description: パッケージ管理ソリューションとしての Application Virtualization サーバーの使用
author: dansimp
ms.assetid: 41597355-e7bb-45e2-b300-7b1724419975
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2b81ed3ab6fa3a70fe4780904059091f22579d9e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815124"
---
# パッケージ管理ソリューションとしての Application Virtualization サーバーの使用


既存の ESD システムで Application Virtualization ソリューションを展開する場合や、使用しない場合は、システムアーキテクチャの中核として、1つ以上の Application Virtualization 管理サーバーをインストールする必要があります。 Application Virtualization Management Server には、専用のサーバーコンピューターが必要です。 Microsoft SQL Server データベースが必要です。 データベースは、同じサーバー上に置くことも、高速 LAN 接続を介してアプリケーションの仮想化管理サーバーからアクセスできる企業のデータベースサーバー上で構成することもできます。 さらに、Application Virtualization management Server または指定した管理ワークステーションに Microsoft Application Virtualization 管理コンソールをインストールする必要があります。また、Microsoft Application Virtualization management Web Service をインストールする必要があります。このサービスは、Application Virtualization Management Server または別の IIS サーバーにインストールすることもできます。 Application virtualization 管理コンソールは、application virtualization management Web サービスに接続するために使用されます。これにより、システム管理者が Application Virtualization Management Server を操作できるようになります。

**注** アプリケーションへのアクセスは Active Directory ドメインサービスのセキュリティグループによって制御されるため、仮想化されたアプリケーションごとにセキュリティグループをセットアップし、各グループに追加されるユーザーを管理するためのプロセスを計画する必要があります。 これらの Active Directory グループを使用するようにサーバーが構成され、サーバーは Active Directory グループメンバーシップに基づいてパッケージへのアクセスを自動的に制御します。

 

## このセクションの内容


<a href="" id="overview-of-the-application-virtualization-system-components"></a>[Application Virtualization システム コンポーネントの概要](overview-of-the-application-virtualization-system-components.md)  
Microsoft Application Virtualization Management System の主要コンポーネントについて説明します。

<a href="" id="publishing-virtual-applications-using-application-virtualization-management-servers"></a>[Application Virtualization Management Server を使用した仮想アプリケーションの公開](publishing-virtual-applications-using-application-virtualization-management-servers.md)  
Application Virtualization Server ベースの展開シナリオで仮想アプリケーションを公開する方法の概要を簡単に説明します。

<a href="" id="planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation"></a>[Application Virtualization サーバー ベースの実装におけるストリーミング ソリューションの計画](planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation.md)  
Application virtualization Management Server ベースの実装と組み合わせて、アプリケーションの仮想化ストリーミングサーバーを使用するために使用できるオプションについて説明します。

## 関連トピック


[Application Virtualization サーバー ベースのシナリオ](application-virtualization-server-based-scenario.md)

[Application Virtualization システムの展開計画](planning-for-application-virtualization-system-deployment.md)

 

 





