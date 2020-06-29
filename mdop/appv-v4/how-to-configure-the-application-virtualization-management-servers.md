---
title: Application Virtualization Management Server を構成する方法
description: Application Virtualization Management Server を構成する方法
author: dansimp
ms.assetid: a9f96148-bf2d-486f-98c2-23409bfb0935
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d6d54dd213efb8d5cbff5d0e730e6dc08c8d19b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817844"
---
# Application Virtualization Management Server を構成する方法


仮想化されたアプリケーションをアプリケーションの仮想化デスクトップクライアントまたはリモートデスクトップサービス (以前のターミナルサービス) のクライアントにストリーミングできるようにするには、Application Virtualization Management Server が構成されている必要があります。 サーバーを構成するときは、SFT ファイルが読み込まれて保存される*コンテンツディレクトリ*を設定することになります。 SFT ファイルには、仮想化されたアプリケーション (またはアプリケーション) が含まれています。

**重要** Application Virtualization サーバーは、RTSP または RTSPS プロトコルのみを使って、SFT ファイルをデスクトップクライアントとリモートデスクトップサービスのクライアントにストリーミングします。 ICO (icon) ファイルと OSD (open software descriptor) ファイルを、別のファイルまたは HTTP サーバーからストリーミングするように構成することができます。

 

**Application Virtualization Management Server を構成するには**

1.  次の手順を実行します。

    [Application Virtualization Management Server をインストールする方法](how-to-install-application-virtualization-management-server.md)

    **注** インストール手順では、[**コンテンツパス**] 画面で \\ コンテンツディレクトリの場所を指定します。

     

2.  \\ コンテンツディレクトリに指定した場所に移動し、必要に応じてディレクトリを作成します。

3.  コンテンツディレクトリが作成されたら、このディレクトリを標準ファイル共有として構成します。

## 関連トピック


[Application Virtualization サーバー ベースのシナリオ](application-virtualization-server-based-scenario.md)

[Application Virtualization のシステム要件](application-virtualization-system-requirements.md)

[電子ソフトウェア配布ベースのシナリオ](electronic-software-distribution-based-scenario.md)

[サーバー ベースの展開用にサーバーを構成する方法](how-to-configure-servers-for-server-based-deployment.md)

 

 





