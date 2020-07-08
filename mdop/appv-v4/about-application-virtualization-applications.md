---
title: Application Virtualization アプリケーションについて
description: Application Virtualization アプリケーションについて
author: dansimp
ms.assetid: 3bf833b7-d172-4eef-a9e8-4b4f0c7eb15b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4eeea7a0ec4454aefcdde5196ae15ed029da45b5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820087"
---
# Application Virtualization アプリケーションについて


アプリケーションの仮想化では、アプリケーションは、Microsoft Visio などの実行可能なプログラム*であり、* アプリケーション仮想化のデスクトップクライアントまたはリモートデスクトップサービス (旧ターミナルサービス) のクライアントにストリーミングされます。 アプリケーションをクライアントにストリーミングするには、その前にアプリケーションの仮想化 Sequencer でそのアプリケーションを処理することによって、ストリーミングの準備ができている必要があります。

## アプリケーションを管理する


アプリケーションをユーザーが利用できるようにするには、その前にシステムにアプリケーションを追加する必要があります。 システムにアプリケーションを追加する最も一般的な方法は、アプリケーションをインポートすることです。 この機能にアクセスするには、Application Virtualization Server 管理コンソールで [**アプリケーション**] ノードを右クリックして、[**アプリケーションのインポート**] を選びます。

同時に複数のオープンソフトウェア記述子 (OSD) ファイルをインポートすることも、複数の OSD ファイルを含む Sequencer プロジェクトファイル (SPRJ) をインポートすることもできます。 この機能により、関連するアプリケーションも同様に構成できます。

次の機能を使用して、アプリケーションを管理することもできます。

-   **アプリケーショングループ**—アプリケーションの論理グループを作成して、管理を簡単にすることができます。 グループ (アクセス許可など) に変更が加えられると、その変更はグループ内のすべてのアプリケーションに適用されます。 グループ内のアプリケーションは、異なるパッケージから取得できます。

-   複数**選択**: CTRL キーを押しながらアプリケーションをクリックしてアプリケーションのプロパティを変更することで、複数のアプリケーションを一度に選択できます。 ただし、アプリケーション間の関係を維持する場合は、アプリケーションを保持するアプリケーショングループを作成する必要があります。

-   **クロスシステムコピー**: 1 つの手順で同じバージョンの app-v を実行している別の環境にアプリケーションをコピーできます。 たとえば、アプリケーションの最初の展開と構成を行うユーザー受け入れテスト環境がある場合があります。 テストフェーズが終了したら、同じセットのアプリケーション (権限を含む) を運用環境にレプリケートすることができます。

## 関連トピック


[Application Virtualization パッケージについて](about-application-virtualization-packages.md)

[Application Virtualization サーバー管理コンソールについて](about-the-application-virtualization-server-management-console.md)

[サーバー管理コンソールでアプリケーション グループを管理する方法](how-to-manage-application-groups-in-the-server-management-console.md)

[サーバー管理コンソールでアプリケーションを管理する方法](how-to-manage-applications-in-the-server-management-console.md)

 

 





