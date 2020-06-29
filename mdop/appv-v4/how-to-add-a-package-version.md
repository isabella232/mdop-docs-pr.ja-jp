---
title: パッケージのバージョンを追加する方法
description: パッケージのバージョンを追加する方法
author: dansimp
ms.assetid: dbb829c1-e5cb-4a2f-bc17-9a9bb50c671c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a60252e8b43af61ad548df30a93d8fbc9bae0cb7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821404"
---
# パッケージのバージョンを追加する方法


Application Virtualization Server 管理コンソールでパッケージを再処理するときに、次の手順を使用して、ストリーミングのために新しいバージョンをサーバーに追加することができます。

**注** 新しいバージョンでパッケージをアップグレードする場合は、既存のバージョンをそのまま残しておくか、削除してから最新のバージョンを残しておくことができます。 以前のドキュメントとの互換性を維持するために古いバージョンをそのまま残しておくことをお勧めします。また、すべてのユーザーが使用できるようにする前に、新しいバージョンのテストを行うこともできます。

 

**パッケージバージョンを追加するには**

1.  新しい SFT ファイルをアプリケーションサーバーのコンテンツフォルダーにコピーします。 Resequencing で、オープンソフトウェア記述子 (OSD)、icon (ICO)、または Sequencer Project (SPRJ) ファイルに変更が追加されなかった場合は、それらをコピーする必要はありません。 すべてのファイルに同じ日付を表示する場合は、これらのファイルを含めることができます。

2.  Application Virtualization Server 管理コンソールの左側のウィンドウで、[**パッケージ**] ノードを展開します。

3.  アップグレードするパッケージを右クリックし、[**バージョンの追加**] を選択します。

4.  [**パッケージバージョンの追加**] ダイアログボックスで、[**パッケージファイルのフルパス**] フィールドに新しいアプリケーションファイルのパス名を参照するか、入力します。 これは、SFT ファイルである必要があります。

5.  **[次へ]** をクリックします。

6.  [**概要**] ダイアログボックスにファイルの場所が表示され、ファイルのコピーをまだ行っていない場合は、ファイルをコピーするように求められます。 情報を確認したら、[**完了**] をクリックします。

    これで、新しいバージョンが完成し、ストリーミングする準備が整いました。

## 関連トピック


[パッケージを削除する方法](how-to-delete-a-packageserver.md)

[サーバー管理コンソールでパッケージを管理する方法](how-to-manage-packages-in-the-server-management-console.md)

 

 





