---
title: 仮想アプリケーション パッケージの追加コンポーネント
description: 仮想アプリケーション パッケージの追加コンポーネント
author: dansimp
ms.assetid: 476b0f40-ebd6-4296-92fa-61fa9495c03c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: d30c2c6561b0d2c08fd75e0c977bf4590d7e6688
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815077"
---
# 仮想アプリケーション パッケージの追加コンポーネント


App-v のアセンブリに依存している、64ビットと32ビットの実行可能ファイルとダイナミックリンクライブラリ (.dll) ファイルが含まれているディレクトリを検出しました。 通常、Sequencer は、パッケージで使用されるすべてのパブリックアセンブリに対してプライベート side-by-side アセンブリを作成します。ただし、32ビットバージョンと64ビットバージョンのプライベートアセンブリを同じディレクトリで作成することはできません。

Sequencer が1つの競合を検出した場合は、次の操作を実行します。

-   ディレクトリに競合があるかどうかにかかわらず、パッケージ全体で既存のすべての64ビットプライベートアセンブリを削除します。

-   32ビットバージョンのプライベート side-by-side アセンブリのみを作成します。

Sequencer を実行しているコンピューターとすべての App-v クライアントコンピューターに、必要なすべての64ビットアセンブリの公開バージョンをネイティブにインストールする必要があります。

必要な既存のパブリックアセンブリを見つけるには、パッケージが保存されているディレクトリを開き、 **VFS**フォルダーを確認します。 たとえば、パッケージのルートが**Q:\\MyApp**である場合は、アプリケーションをシーケンスするときに、 **Q:\\MyApp\\VFS\\CSIDL\ _Windows \\winsxs\\manifests**を探して、既存のパブリックアセンブリをすべて検索します。 これらのファイルの64ビットバージョンでは、常にマニフェスト名の先頭に次のテキストが表示され**ます。** アセンブリの正確な名前とバージョンは、関連付けられているマニフェストファイルに含まれています。

以下のリンクのいずれかを使用して、必要な前提条件の適切なバージョンをダウンロードしてインストールします。

-   [Microsoft Visual C++ 2005 再頒布可能パッケージ (x64)](https://go.microsoft.com/fwlink/?LinkId=152697)

-   [Microsoft Visual C++ 2005 SP1 再頒布可能パッケージ (x64)](https://go.microsoft.com/fwlink/?LinkId=152698)

-   [Microsoft Visual C++ 2008 再頒布可能パッケージ (x64)](https://go.microsoft.com/fwlink/?LinkId=152699)

-   [Microsoft Visual C++ 2008 SP1 再頒布可能パッケージ (x64)](https://go.microsoft.com/fwlink/?LinkId=152700)

 

 





