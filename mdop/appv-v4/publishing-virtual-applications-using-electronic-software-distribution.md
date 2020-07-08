---
title: 電子ソフトウェア配布を使用した仮想アプリケーションの公開
description: 電子ソフトウェア配布を使用した仮想アプリケーションの公開
author: dansimp
ms.assetid: 295fbc1d-ed1c-43b4-aeee-0df384d4e630
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a0354fc1226aa78d947dd764a0ab6157b563a321
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815744"
---
# 電子ソフトウェア配布を使用した仮想アプリケーションの公開


電子ソフトウェア配布 (ESD) システムは、低速または高速のネットワーク接続を介して、さまざまなコンピューターにソフトウェアを効率的に移動するように設計されています。 ESD システムを使ったアプリケーションの仮想化では、次のいずれかの方法を使用して仮想アプリケーションパッケージを配布できます。

-   アプリケーションの仮想化 Sequencer によって生成されたパッケージの Windows インストーラーバージョンを使って、各クライアントコンピューターにパッケージを直接配布するように ESD システムを構成します。 Windows Installer ファイルには、アイコン、パッケージ定義情報、およびコンテンツが含まれており、Windows インストーラーを使うと、Windows デスクトップと [スタート] メニューにアイコンが公開され、アプリの仮想化クライアントキャッシュにパッケージコンテンツが読み込まれます。 ユーザーは、セットアップの要件を追加せずに、すぐにアプリケーションを使い始めることができます。 新しいバージョンへのパッケージのアップグレードは、Windows インストーラーを使用して package.msi ファイルをアンインストールしてから、新しいバージョンをインストールすることで実現されます。

-   パッケージコンテンツは、LAN などの適切な帯域幅のネットワーク接続を介してクライアントコンピューターから簡単にアクセスできるソフトウェアの配布ポイントまたはアプリケーションの仮想化ストリーミングサーバーに配置します。 たとえば、各支社で既存の ESD システム配布ポイントのコンピューターを使うことができます。 コマンドラインパラメーターを使用して、クライアントが仮想アプリケーションパッケージをストリーミングするストリーミングソースを定義します。 ESD システムは、Windows インストーラーバージョンのパッケージを各クライアントに展開します。 ESD システムを使って、パッケージコンテンツを含む SFT ファイルをすべてのストリーミングサーバー上のファイル共有にコピーすることもできます。 新しいバージョンへのパッケージのアップグレードは、Windows インストーラーを使用して package.msi ファイルをアンインストールし、新しいバージョンをインストールすることで実現されます。

-   パッケージを展開するために、上記のいずれかのモードで自己完結した Windows インストーラーファイルを使用する代わりに、Application Virtualization コマンドライン言語 SFTMIME を使用して、より詳細な方法で展開を制御できます。 これには、パッケージの管理に関するすべての要素を制御する多くのコマンドが用意されています。 SFTMIME は強力でもありますが、複雑であるため、管理者はすべてのコマンドをスクリプトとして作成して、運用前にテスト環境で完全にテストすることを計画する必要があります。 使用可能な SFTMIME コマンドの詳細については、「 [Sftmime コマンドのリファレンス](sftmime--command-reference.md)」を参照してください。

## 関連トピック


[電子ソフトウェア配布ベースのシナリオ](electronic-software-distribution-based-scenario.md)

[Application Virtualization システムの展開計画](planning-for-application-virtualization-system-deployment.md)

[電子ソフトウェア配布の実装におけるストリーミング ソリューションの計画](planning-your-streaming-solution-in-an-electronic-software-distribution-implementation.md)

[SFTMIME コマンドリファレンス](sftmime--command-reference.md)

 

 





