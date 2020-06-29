---
title: 電子ソフトウェア配布ベースのシナリオ概要
description: 電子ソフトウェア配布ベースのシナリオ概要
author: dansimp
ms.assetid: e9e94b8a-6cba-4de8-9b57-73897796b6a0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cfbdf40f5ac0f61721c05d0da5cd49e910b16154
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821597"
---
# 電子ソフトウェア配布ベースのシナリオ概要


仮想アプリケーションを展開するために電子ソフトウェア配布 (ESD) ソリューションを使用する予定がある場合は、その判断によって影響を受ける要因を理解することが重要です。 このトピックでは、ESD ベースのシナリオを使用する利点について説明し、展開を進めるときに考慮する必要がある発行およびパッケージのストリーミング方法に関する情報を提供します。

**重要** どちらの ESD ソリューションを使っていても、特定の解決策の要件について理解している必要があります。 Microsoft Endpoint Configuration Manager を使用している場合は、の Configuration Manager のドキュメントを参照してください <https://go.microsoft.com/fwlink/?LinkId=66999> 。

 

既存の ESD システムを使用すると、次のようなメリットが得られます。

-   デュアル管理インフラストラクチャの排除

-   追加ハードウェアのコストを削減する

-   追加のオペレーティングシステムとデータベースライセンスのコストを削減する

## 発行方法


ESD ベースのシナリオを使用する場合、アプリケーションをクライアントに公開するための次の選択肢があります。

-   **スタンドアロンの Windows インストーラー。** Windows Installer ファイルには、マニフェストと、クライアントがパッケージを構成するために使用する OSD ファイルと ICO ファイルが含まれています。 このシナリオではサーバーを使用しないため、Windows Installer ファイルでも、SFT ファイルがクライアントにコピーされます。

-   **パッケージマニフェストを含む Windows インストーラー。** Windows Installer ファイルには、マニフェストと、クライアントがパッケージを構成するために使用する OSD ファイルと ICO ファイルが含まれています。 SFT ファイルがサーバーに保存されています。 コマンドラインパラメーターは、クライアントが SFT ファイルの場所を指定するように指示します。

-   **SFTMIME コマンド。** SFTMIME コマンドは、マニフェスト、OSD、ICO、および SFT の各ファイルと共に使用され、クライアントにパッケージを追加します。 マニフェストファイルは、クライアントコンピューター上に存在するか、UNC パスを介してアクセスできる必要があります。 クライアントの構成とコマンドラインオプションに応じて、OSD、ICO、および SFT の各ファイルは、クライアントコンピューターまたはサーバー上に存在することができます。

上記の発行方法の詳細については、「[発行方法を決定](determine-your-publishing-method.md)する」を参照してください。

## パッケージストリーミングの方法


仮想アプリケーションパッケージ (または SFT ファイル) をサーバーからクライアントにストリーミングするためにアプリケーションの仮想化システムが使用するメソッドを決定する必要があります。 次のストリーミングオプションを使用できます。

-   **Application Virtualization ストリーミングサーバー。** 構成で Application Virtualization Streaming Server を使用している場合、SFT ファイルは、RTSP または RTSPS プロトコルを使ってそのサーバーのクライアントにストリーミングされます。 コンピューターにサーバーソフトウェアをインストールする必要があります。これは、レジストリを使って構成する必要がありますが、この構成は、SQL や Active Directory ドメインサービスなどのサービスに依存しません。 SFT ファイルは、クライアントからアクセスできる場所にサーバー上に格納されます。 公開情報は、任意の配布メカニズムを通じてクライアントに配布できます。 ただし、構成すると、クライアントはパッケージのアップグレードを自動的に受け取り、アクティブなアップグレードがサポートされます。

-   **Application Virtualization Management Server。** 構成で Application Virtualization Management Server を使用している場合、SFT ファイルは、RTSP または RTSPS プロトコルを使ってそのサーバーのクライアントにストリーミングされます。 このサーバーは、Application Virtualization 管理コンソールを使って管理します。 この構成では、SQL データベースと Active Directory services を使用します。 サーバーは発行情報をクライアントに配布できます。そのため、追加の公開メカニズムは必要ありません。

-   **ファイルサーバー。** 構成でファイルサーバーを使用している場合、SFT ファイルは、SMB プロトコルを使用して他のクライアントコンピューターにストリーミングされます。 この構成で使用されるファイルサーバーは、ファイル共有と SFT ファイルにアクセス制御リスト (Acl) を作成することによって管理されます。 クライアントがファイルサーバー上の適切なファイルにアクセスするには、注意を払う必要があります。

-   **IIS サーバー。** 構成で IIS サーバーを使用している場合、SFT ファイルは、HTTP または HTTPS プロトコルを使用してそのサーバーからクライアントにストリーミングされます。 IIS サーバーの構成と管理は簡単です。 クライアントを IIS サーバー上の適切なファイルに接続するには、注意を払う必要があります。

上記のストリーミングメソッドの詳細については、「[ストリーミングメソッドを決定](determine-your-streaming-method.md)する」を参照してください。

## 関連トピック


[Application Virtualization Client インストーラーのコマンド ライン パラメーター](application-virtualization-client-installer-command-line-parameters.md)

[Application Virtualization サーバー ベースのシナリオ](application-virtualization-server-based-scenario.md)

[公開方法の選択](determine-your-publishing-method.md)

[ストリーミング方法の選択](determine-your-streaming-method.md)

[電子ソフトウェア配布ベースのシナリオ](electronic-software-distribution-based-scenario.md)

[SFTMIME コマンドリファレンス](sftmime--command-reference.md)

 

 





