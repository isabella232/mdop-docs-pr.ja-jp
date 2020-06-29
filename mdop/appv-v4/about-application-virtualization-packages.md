---
title: Application Virtualization パッケージについて
description: Application Virtualization パッケージについて
author: dansimp
ms.assetid: 69bd35c1-7af3-43db-931b-3074780aa926
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cfe6df90881ea4179fa8cd224609ca6d28ff5f61
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820084"
---
# Application Virtualization パッケージについて


アプリケーションの仮想化では、*パッケージ*はシーケンス処理の出力です。 初めてサーバーにアプリケーションを展開するとき、および新しいバージョンでアプリケーションをアップグレードするときは、パッケージを使用します。 パッケージを使用すると、アプリケーションの仮想化管理サーバーで仮想アプリケーションのバージョンを制御できます。 1つのパッケージには、1つまたは複数のアプリケーションを含めることができます。 各アプリケーションパッケージには、自己完結型の単位として一連のファイルが含まれています。

## パッケージの管理


Sequencer がプロセスの一部として1つ以上のアプリケーションのパッケージを作成した後は、Sequencer で生成されたファイルをアプリケーションの仮想化管理サーバーにコピーして、ストリーミングで利用できるようにすることができます。

利用可能なパッケージは、Application Virtualization 管理コンソールの左側のウィンドウにある [**パッケージ**] コンテナーの下に表示されます。 Sequencer プロジェクト (SPRJ) ファイルまたはオープンソフトウェア記述子 (OSD) ファイルを使用してアプリケーションをインポートすると、関連エントリが [**パッケージ**] コンテナーに表示されます。 Application Virtualization Server 管理コンソールから、パッケージとバージョンを展開、アップグレード、または削除することができます。

各仮想アプリケーションには、関連付けられたパッケージがあります。 このパッケージには、次のファイルが含まれます。

-   SFT —アプリケーションをクライアントにストリーム転送するファイル。

-   OSD — Open Software Descriptor ファイルには、アプリケーションを見つけて起動するために必要な情報が含まれています。

-   ICO —ユーザーインターフェイスやショートカットでアプリケーションを視覚的に表すアイコンファイル。

-   SPRJ — Sequencer プロジェクトファイル。

SPRJ ファイルをインポートすると、既定では、すべてのシーケンスされたアプリケーションを展開に使用できますが、アプリケーションはストリーミングに対して有効になっていません。 パッケージ内のアプリケーションのすべてまたは一部をストリーミングすることを選択できます。 たとえば、Microsoft Office をシーケンスしてインポートした場合、[設定の保存] ウィザードなどのアプリケーションを展開しないようにすることができます。 この場合、展開する各アプリケーションを右クリックして、[**プロパティ**] を選択し、[**有効**] ボックスがオフになっていることを確認します (空白)。 [**有効**] ボックスが選択されているアプリケーションのみが、クライアントコンピューターにストリーミングされます。

パッケージを再シーケンスし、ストリーミング用の新しい SFT ファイルを生成したら、Application Virtualization Server 管理コンソールを使用して、古いパッケージをすばやく簡単にアップグレードできます。

**パッケージノードを**使用する必要がある操作シナリオは、パッケージの新しいバージョン (SFT ファイル) を導入する場合に限られます。 アプリケーションをインポートするたびに、access とライセンスをアプリケーションに割り当てると、Application Virtualization システムはこの情報をパッケージレベルで追跡します。 つまり、アプリケーションを使用するようにユーザーを承認すると、同じパッケージ内のアプリケーションを実行するためのアクセス許可をユーザーに与えることになります。

### パッケージバージョン

パッケージバージョンは、特定の SFT ファイルで表されます。 パッケージをアップグレードする (アプリケーションの更新を適用する、またはアプリケーションをパッケージに追加する) と、新しい SFT ファイルが生成されます。 新しい SFT ファイルを作成するたびに、新しいパッケージバージョンを作成することになります。

Application Virtualization Server 管理コンソールを使用してアプリケーションをインポートすると、パッケージとパッケージバージョンがまだ存在しない場合は、ソフトウェアによって自動的に作成されます。

## 関連トピック


[Application Virtualization アプリケーションについて](about-application-virtualization-applications.md)

[Application Virtualization サーバー管理コンソールについて](about-the-application-virtualization-server-management-console.md)

[サーバー管理コンソールでパッケージを管理する方法](how-to-manage-packages-in-the-server-management-console.md)

 

 





