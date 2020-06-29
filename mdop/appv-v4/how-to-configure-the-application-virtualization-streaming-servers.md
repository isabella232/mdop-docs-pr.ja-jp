---
title: Application Virtualization Streaming Server を構成する方法
description: Application Virtualization Streaming Server を構成する方法
author: dansimp
ms.assetid: 3e2dde35-9d72-40ba-9fdf-d0338bd4d561
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a0ec5497b010d18bcba60e81e96cbe6334c27fb8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817824"
---
# Application Virtualization Streaming Server を構成する方法


仮想アプリケーションをアプリケーションの仮想化デスクトップクライアントまたはリモートデスクトップサービス (以前のターミナルサービス) のクライアントにストリーミングできるようにするには、Application Virtualization ストリーミングサーバーが構成されている必要があります。 サーバーを構成するときは、SFT ファイルが読み込まれて保存される*コンテンツディレクトリ*を設定することになります。 SFT ファイルには、仮想アプリケーション (またはアプリケーション) が含まれています。

**重要** Application Virtualization サーバーは、RTSP または RTSPS プロトコルのみを使って、SFT ファイルをデスクトップクライアントとリモートデスクトップサービスのクライアントにストリーミングします。 ICO (icon) ファイルと OSD (open software descriptor) ファイルを、別のファイルまたは HTTP サーバーからストリーミングするように構成することができます。

 

**Application Virtualization ストリーミングサーバーを構成するには**

1.  Application Virtualization ストリーミングサーバーのインストール手順を完了します。 インストール手順では、[**コンテンツパス**] 画面で \\ コンテンツディレクトリの場所を指定します。

2.  \\ コンテンツディレクトリで指定した場所に移動し、必要に応じてディレクトリを作成します。

3.  コンテンツディレクトリが作成されたら、このディレクトリを標準ファイル共有として構成します。

4.  コンテンツディレクトリと、コンテンツディレクトリの下にあるパッケージフォルダーへの NTFS ファイルシステムの権限を構成します。 各アプリケーションにどのユーザーがアクセスできるかを定義する Active Directory ドメインサービスのセキュリティグループを使用する必要があります。

## 関連トピック


[Application Virtualization サーバー ベースのシナリオ](application-virtualization-server-based-scenario.md)

[電子ソフトウェア配布ベースのシナリオ](electronic-software-distribution-based-scenario.md)

[Application Virtualization Management Server を構成する方法](how-to-configure-the-application-virtualization-management-servers.md)

[ファイル サーバーを構成する方法](how-to-configure-the-file-server.md)

[IIS のサーバーを構成する方法](how-to-configure-the-server-for-iis.md)

 

 





