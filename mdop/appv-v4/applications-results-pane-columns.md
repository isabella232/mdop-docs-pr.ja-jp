---
title: アプリケーションの結果ウィンドウの列
description: アプリケーションの結果ウィンドウの列
author: dansimp
ms.assetid: abae5ce2-40df-4f47-8062-f5eb6295c88c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c0138e40647a6a7d131a08aa03a9c9c1fcb071b3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819497"
---
# アプリケーションの結果ウィンドウの列


Application Virtualization クライアント管理コンソールの [**アプリケーション**] ノードの**結果**ウィンドウには、さまざまな列を表示できます。 **アプリケーション**、**実行中**、**ロック**済み、**パッケージの状態**が既定で表示されます。

**注** 列を追加または削除するには、[**結果**] ウィンドウで右クリックし、[**表示**] を選択して、[**列の追加と削除**] を選択します。

 

リストは、任意の列によって並べ替えることができます。 日付と時刻を含む列は、昇順で並べ替えられます。 日付と時刻が混在し、テキストが含まれている列の場合、日付と時刻は、他のテキストの前にあると見なされます。

次の列を使用できます。

<a href="" id="application"></a>**Application**  
アプリケーション名とバージョンを、スペースで区切って指定します。

<a href="" id="application-in-use"></a>**使用中のアプリケーション**  
いずれかのユーザーがアプリケーションを使用しているか (つまり、それを実行しているか読み込み中か) に応じて、 **[はい]** または [**いいえ**] を表示します。

<a href="" id="app-virt-server"></a>**App Virt Server**  
パッケージがストリーミングされた Application Virtualization server。

<a href="" id="cached-icon-file"></a>**キャッシュアイコンファイル**  
キャッシュ内のアイコンファイルの名前 (現在の実装の GUID)。

<a href="" id="cached-icon-path"></a>**キャッシュされたアイコンのパス**  
キャッシュ内のアイコンファイルの完全なパスです。

<a href="" id="cached-launch-percent"></a>**キャッシュされた起動の割合**  
アプリケーションの起動データの現在のキャッシュ内の割合。

<a href="" id="cached-launch-size--mb-"></a>**キャッシュされた起動サイズ (MB)**  
アプリケーションの起動データ (現在キャッシュ内) の量。

<a href="" id="cached-osd-file"></a>**キャッシュされた OSD ファイル**  
キャッシュ内の OSD ファイルの名前 (現在の実装の GUID)。

<a href="" id="cached-osd-path"></a>**キャッシュされた OSD パス**  
キャッシュ内の OSD ファイルへの完全パス。

<a href="" id="cached-package-percent"></a>**キャッシュされたパッケージの割合**  
現在キャッシュ内にあるパッケージの割合。

<a href="" id="cached-package-size--mb-"></a>**キャッシュされたパッケージサイズ (MB)**  
現在キャッシュ内にあるパッケージの部分のサイズです。

<a href="" id="icon-file"></a>**アイコンファイル**  
アイコンファイルの元の名前。

<a href="" id="icon-path"></a>**アイコンのパス**  
アイコンファイルの元のパスまたは URL。

<a href="" id="last-system-launch"></a>**最終システム起動**  
システムによって最後にアプリケーションが起動された時刻。

<a href="" id="last-user-launch"></a>**前回のユーザー起動**  
ユーザーが最後にアプリケーションを起動した時刻。

<a href="" id="launch-size--mb-"></a>**起動サイズ (MB)**  
アプリケーションを起動するために必要なパッケージデータの未圧縮サイズ。

<a href="" id="locked"></a>**ロック**  
アプリケーションのパッケージがキャッシュ内でロックされているかどうかに応じて、 **[はい]** または [**いいえ**] を表示します。

<a href="" id="name"></a>**名前**  
アプリケーション名。

<a href="" id="osd-file"></a>**OSD ファイル**  
オープンソフトウェア記述子 (OSD) ファイルの元の名前。

<a href="" id="osd-path"></a>**OSD パス**  
OSD ファイルの完全な元のパスまたは URL。

<a href="" id="package-name"></a>**パッケージ名**  
パッケージの名前。

<a href="" id="package-guid"></a>**パッケージ GUID**  
パッケージの GUID です。

<a href="" id="package-size--mb-"></a>**パッケージのサイズ (MB)**  
パッケージ内の圧縮されていないデータの合計サイズ。

<a href="" id="package-status"></a>**パッケージの状態**  
パッケージの現在の動作状態。

<a href="" id="package-url"></a>**パッケージ URL**  
パッケージの URL です。

<a href="" id="package-version"></a>**パッケージバージョン**  
パッケージのバージョン。

<a href="" id="package-version-guid"></a>**パッケージバージョン GUID**  
パッケージバージョンの GUID です。

<a href="" id="running"></a>**Running**  
現在のユーザーがアプリケーションを実行しているかどうかによって **[はい]** または [**いいえ**] と表示されます。

<a href="" id="source"></a>**Source**  
アプリケーションが登場した場所: アプリケーション発行サーバーの名前か、OSD ファイルから直接追加されたアプリケーションの場合は "Local"。

<a href="" id="version"></a>**バージョン**  
アプリケーションのバージョン。

## 関連トピック


[アプリケーション ノード](applications-node.md)

[アプリケーションの結果ウィンドウ](applications-results-pane.md)

[Application Virtualization Client Management Console リファレンス](application-virtualization-client-management-console-reference.md)

 

 





