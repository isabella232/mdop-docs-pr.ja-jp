---
title: IIS のサーバーを構成する方法
description: IIS のサーバーを構成する方法
author: dansimp
ms.assetid: 1fcfc583-322f-4a38-90d0-e64bfa9ee3d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9fe3367698b6f387d4467afdad1b3e17211134d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817744"
---
# IIS のサーバーを構成する方法


仮想アプリケーションをアプリケーションの仮想化デスクトップクライアントとリモートデスクトップサービス (以前のターミナルサービス) のクライアントにストリーミングするには、IIS サーバーが構成されている必要があります。 サーバーを構成するときは、SFT ファイルが読み込まれて保存されるコンテンツディレクトリを設定することになります。 SFT ファイルには、仮想アプリケーション (またはアプリケーション) が含まれています。

**IIS サーバーでコンテンツディレクトリを構成するには**

1.  IIS を実行しているサーバーで、コンテンツディレクトリとして使用するディレクトリを見つけるか、ディレクトリが存在しない場合は作成します。 このディレクトリを標準のファイル共有として構成します。

2.  IIS を実行しているサーバーで、 **Iis Manager**を開き、[既定の web サイト] で、サーバー上で作成したコンテンツディレクトリに対応する仮想ディレクトリを作成します。 **「既読**」がオンになっていることを確認します。

3.  新しく作成された仮想ディレクトリにエイリアスの**内容**を指定します。

4.  この仮想ディレクトリのその他のすべての既定の設定をそのまま使用します。

5.  以前に定義した Active Directory ドメインサービスのセキュリティグループを使用して、コンテンツディレクトリとコンテンツディレクトリの下に、NTFS ファイルシステムの権限を構成します。

**注** IIS を使って ICO ファイルと OSD ファイルを公開する場合は、OSD = TXT の MIME タイプを構成する必要があります。そうしないと、IIS は、ICO ファイルと OSD ファイルをクライアントに提供しません。 IIS を使ってパッケージ (SFT files) を公開している場合は、SFT = Binary の MIME タイプを構成する必要があります。そうしないと、IIS は SFT ファイルをクライアントに提供しません。

 

## 関連トピック


[Application Virtualization サーバー ベースのシナリオ](application-virtualization-server-based-scenario.md)

[電子ソフトウェア配布ベースのシナリオ](electronic-software-distribution-based-scenario.md)

[Application Virtualization Management Server を構成する方法](how-to-configure-the-application-virtualization-management-servers.md)

[Application Virtualization Streaming Server を構成する方法](how-to-configure-the-application-virtualization-streaming-servers.md)

[ファイル サーバーを構成する方法](how-to-configure-the-file-server.md)

 

 





