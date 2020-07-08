---
title: ファイル サーバーを構成する方法
description: ファイル サーバーを構成する方法
author: dansimp
ms.assetid: 0977554c-1741-411b-85e7-7e1cd017542f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a8971ad5c9f83dec4d0c77a16f1093ef7026b5c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817784"
---
# ファイル サーバーを構成する方法


次の手順を使用して、ファイル共有として使用されるローカルコンピューターを構成し、Application Virtualization デスクトップクライアントとリモートデスクトップサービス (旧ターミナルサービス) のクライアントにストリームアプリケーションを設定することができます。 このシナリオは、既存のハードウェア環境にサーバーインフラストラクチャを追加したくない場合に使用されます。

ローカルオフィスにインストールされているファイル共有への配布ポイントとして Application Virtualization Management Server を使用している場合、仮想アプリケーションをファイル共有として使用するコンピューターにストリーミングできるようにするには、このサーバーを構成する必要があります。 サーバーとファイル共有を構成すると、SFT ファイルが読み込まれ、保存されるコンテンツディレクトリを設定することになります。 SFT ファイルには、仮想アプリケーション (またはアプリケーション) が含まれています。

**重要** アプリケーションの仮想化デスクトップクライアントとリモートデスクトップサービスのクライアントに適切にストリーミングするアプリケーションの場合、SFT ファイルは、仮想アプリケーションを保存しているサーバー上のコンテンツディレクトリからストリーミングします。ICO (icon) ファイルと OSD (open software descriptor) ファイルは、別のサーバーからストリーミングするように構成できます。

 

**Application Virtualization ファイルサーバーを構成するには**

1.  配布ポイントとして使用されるサーバーを構成するには、次のインストール手順を実行します。

    [Application Virtualization Management Server をインストールする方法](how-to-install-application-virtualization-management-server.md)

    **注** インストール手順では、[**コンテンツパス**] 画面で \\ コンテンツディレクトリの場所を指定します。

     

2.  ファイル共有として使用している各コンピューターにサーバーをインストールしたときに指定したディレクトリに対応する、\\ コンテンツディレクトリを作成します。

    **重要** アプリケーションの仮想化デスクトップクライアントを構成して、アプリケーションの仮想化サーバーまたは IIS サーバーからではなく、ファイル共有として使用しているコンピューターからアプリケーションをストリーミングします。

     

3.  \\ コンテンツディレクトリが作成されたら、このディレクトリを標準ファイル共有として構成します。

## 関連トピック


[Application Virtualization サーバー ベースのシナリオ](application-virtualization-server-based-scenario.md)

[電子ソフトウェア配布ベースのシナリオ](electronic-software-distribution-based-scenario.md)

[Application Virtualization Management Server を構成する方法](how-to-configure-the-application-virtualization-management-servers.md)

[Application Virtualization Streaming Server を構成する方法](how-to-configure-the-application-virtualization-streaming-servers.md)

[IIS のサーバーを構成する方法](how-to-configure-the-server-for-iis.md)

 

 





