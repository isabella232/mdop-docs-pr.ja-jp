---
title: Application Virtualization システムの計画と展開ガイド
description: Application Virtualization システムの計画と展開ガイド
author: dansimp
ms.assetid: 6c012e33-9ac6-4cd8-84ff-54f40973833f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 10bcac26fddae2f0e5826dbd7335adda06d3987e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815957"
---
# Application Virtualization システムの計画と展開ガイド


Microsoft Application Virtualization Management は、アプリケーションをコンピューターに直接インストールしなくても、エンドユーザーのコンピューターでアプリケーションを利用できるようにする機能を提供します。 これは、*アプリケーションの順序*付けと呼ばれるプロセスによって可能になります。これにより、各アプリケーションは、クライアントコンピューター上の独立した仮想環境で実行できます。 シーケンス処理されたアプリケーションは、アプリケーションの競合を排除し、クライアントコンピューターを操作することができます。

Application Virtualization クライアントは、エンドユーザーがコンピューターに公開された後にアプリケーションを操作できるようにする Application Virtualization システムコンポーネントです。 クライアントは、仮想化されたアプリケーションが各コンピューターで実行される仮想環境を管理します。 クライアントがコンピューターにインストールされた後、アプリケーションは*発行*と呼ばれるプロセスによってコンピューターから利用できるようにする必要があります。これにより、エンドユーザーは仮想アプリケーションを実行できるようになります。 公開プロセスでは、仮想アプリケーションのアイコンとショートカットがコンピューター (通常は Windows デスクトップまたは [**スタート**] メニュー) に配置され、パッケージ定義とファイルの種類の関連付け情報がコンピューターに配置されます。 公開すると、エンドユーザーのコンピューターでもアプリケーションパッケージのコンテンツを利用できるようになります。

仮想アプリケーションパッケージのコンテンツは、1つまたは複数の Application Virtualization サーバーに配置できます。これにより、オンデマンドでクライアントにストリーミングしてローカルにキャッシュすることができます。 ファイルサーバーと Web サーバーをストリーミングサーバーとして使用することも、Microsoft Endpoint Configuration Manager などの電子ソフトウェア配布システムを使用している場合など、エンドユーザーのコンピューターに直接配置することもできます。 複数サーバーの実装では、すべてのストリーミングサーバーでパッケージコンテンツを保持し、最新の状態に維持するには、包括的なパッケージ管理ソリューションが必要です。 組織の規模によっては、世界中のエンドユーザーが使用できる仮想アプリケーションが数多く必要になる場合もあります。 パッケージを管理して、すべてのユーザーが適切なアプリケーションを使用できるようにするには、そのような要件を満たす必要があります。

「アプリケーション仮想化計画と展開ガイド」では、Microsoft Application Virtualization アプリケーションとそのコンポーネントの理解と展開を強化するために役立つ情報を提供しています。 また、主要な展開シナリオを実装するためのステップバイステップの手順も示します。

## このセクションの内容


<a href="" id="planning-for-application-virtualization-system-deployment"></a>[Application Virtualization システムの展開計画](planning-for-application-virtualization-system-deployment.md)  
アプリケーションの仮想化システムの実装と展開を計画するために必要なガイダンスを示します。

<a href="" id="application-virtualization-deployment-and-upgrade-considerations"></a>[Application Virtualization の展開およびアップグレードに関する考慮事項](application-virtualization-deployment-and-upgrade-considerations.md)  
さまざまなアプリケーションの仮想化コンポーネントとアップグレード情報をインストールするためのハードウェアとソフトウェアの要件について説明します。

<a href="" id="electronic-software-distribution-based-scenario"></a>[電子ソフトウェア配布ベースのシナリオ](electronic-software-distribution-based-scenario.md)  
電子ソフトウェア配布 (ESD) システムを使用したアプリケーションの仮想化の展開について説明します。

<a href="" id="application-virtualization-server-based-scenario"></a>[Application Virtualization サーバー ベースのシナリオ](application-virtualization-server-based-scenario.md)  
Application Virtualization Management Server を使用したアプリケーションの仮想化の展開について説明します。

<a href="" id="stand-alone-delivery-scenario-for-application-virtualization-clients"></a>[Application Virtualization Client のスタンドアロン配信シナリオ](stand-alone-delivery-scenario-for-application-virtualization-clients.md)  
ESD またはサーバーベースのリソースを使わずに、スタンドアロンモードでアプリケーションの仮想化を展開する方法について説明します。

<a href="" id="application-virtualization-reference"></a>[Application Virtualization リファレンス](application-virtualization-reference.md)  
システムコンポーネントのインストールと管理に関連する詳細な技術参考資料が含まれています。

 

 





