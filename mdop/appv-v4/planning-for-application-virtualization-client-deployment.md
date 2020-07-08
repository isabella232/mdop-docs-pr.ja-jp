---
title: Application Virtualization Client の展開計画
description: Application Virtualization Client の展開計画
author: dansimp
ms.assetid: a352f80f-f0f9-4fbf-ac10-24c510b2d6be
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6c9fc4f29020af83a8606827015947e78761f4d7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815954"
---
# Application Virtualization Client の展開計画


仮想アプリケーションパッケージを公開してエンドユーザーのコンピューターに展開する方法を決定したら、Application Virtualization クライアントソフトウェアの展開を計画する必要があります。

アプリケーションの仮想化クライアントは、実際に仮想アプリケーションを実行するコンポーネントです。 Application Virtualization クライアントを使うと、ユーザーはアイコンを操作したり、ファイルの種類をダブルクリックして仮想アプリケーションを開始したりできます。 また、ストリーミングサーバーからのアプリケーションコンテンツのストリーミングを処理し、アプリケーションを起動する前にキャッシュします。 アプリケーションのコンテンツは、アプリケーションを起動するために必要なすべてのコンテンツと、最初のユーザーの操作を処理するために、エンドユーザーのコンピューターにストリーミングされるように構成されています。 Application Virtualization クライアントソフトウェアには、リモートデスクトップサービス (RDSession Host) サーバーシステムで使用される application Virtualization クライアントと、その他のすべてのコンピューターで使用される Application Virtualization Desktop Client という2種類の種類のアプリケーションがあります。

アプリケーションの仮想化クライアントは、アプリケーションの仮想化管理コンソールまたはインストーラーのコマンドラインで、次のようないくつかの重要な設定を含む、インストール時に構成する必要があります。

-   すべてのアプリケーションのアイコンの場所。

-   パッケージ定義情報を含む OSD ファイルの場所。

-   アプリケーションのコンテンツソース。

-   上記の項目を取得するときに使用する通信プロトコル。

-   使用するキャッシュサイズとキャッシュサイズの管理方法。

電子ソフトウェア配布 (ESD) ソリューションを使用するときに、Application Virtualization クライアントソフトウェアの展開を迅速化するには、前の設定を慎重に定義する必要があります。 これは、さまざまな場所にあるコンピューターを使用している場合に、クライアントが異なるソースの場所を使用するように構成する必要がある場合に特に重要です。

**注**  
-   [Icon location] と [OSD file] の値は、Windows Installer または SFTMIME のどちらを使用するかにかかわらず、発行方法を選ぶ際に考慮すべき重要な要素です。 アプリケーションコンテンツソースの設定は、ストリーミングメソッドの選択によって定義されます。

-   展開される可能性のあるすべてのパッケージに対して十分な領域がキャッシュに割り当てられるようにするには、必要に応じてキャッシュを拡大できるように、クライアントを構成するときに、[**空きディスク領域のしきい値を使用**する] 設定を使用します。 または、アプリの V キャッシュに必要なディスク容量を事前に確認して、インストール時にキャッシュサイズを適切に設定します。 キャッシュスペース管理機能の詳細については、「Microsoft Application Virtualization (App-v) Operations Guide の**キャッシュスペース管理機能を使用する方法**」を参照してください。

-   Publishing および HTTP (S) ストリーミング操作の両方で、App-v 4.5 SP1 クライアントは、ユーザーのコンピューターの Internet Explorer で構成されているプロキシサーバー設定を使用します。

クライアントのインストールパラメーターの構成の詳細については、「 [Application Virtualization クライアントインストーラーのコマンドラインパラメーター](application-virtualization-client-installer-command-line-parameters.md)」を参照してください。

 

最後に、デスクトップクライアント用の Application Virtualization デスクトップクライアントソフトウェアの展開方法を決定する必要があります。 各コンピューターにアプリケーションの仮想化デスクトップクライアントを手動で展開することもできますが、ほとんどの組織では、いくつかの自動化されたプロセスを通じてこれを行う必要があります。 中規模または大規模の組織では、実行中の ESD システムがある場合があります。これは、クライアントを展開するのに最適な方法です。 ESD システムが存在しない場合は、組織にソフトウェアをインストールするための標準的な方法を使用できます。 選択肢には、グループポリシーやさまざまなスクリプト手法があります。 使用しているオフィスの数とサイズによっては、この展開プロセスが複雑な場合があり、すべてのコンピューターが適切な構成でクライアントをインストールできるように、構造化されたアプローチを取ることが重要です。

## 関連トピック


[Application Virtualization システムの展開計画](planning-for-application-virtualization-system-deployment.md)

[コマンド ラインを使用してクライアントをインストールする方法](how-to-install-the-client-by-using-the-command-line-new.md)

[クライアントで仮想アプリケーションを公開する方法](how-to-publish-a-virtual-application-on-the-client.md)

[Application Virtualization Client をアップグレードする方法](how-to-upgrade-the-application-virtualization-client.md)

[App-V Client をアンインストールする方法](how-to-uninstall-the-app-v-client.md)

 

 





