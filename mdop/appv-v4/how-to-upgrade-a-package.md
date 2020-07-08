---
title: パッケージをアップグレードする方法
description: パッケージをアップグレードする方法
author: dansimp
ms.assetid: 831c7556-6f6c-4b3a-aefb-26889094dc1a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0a9b3eca2c996337d79e551784818a421f495316
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816504"
---
# パッケージをアップグレードする方法


自動アップグレードのプロセスは、Application Virtualization Server 管理コンソールでのパッケージバージョンの追加と同じです。 既存のパッケージでアプリケーションを再シーケンスすると、自動アップグレードが実行されます。 次に、この新しいバージョンをサーバーに追加してストリーミングを行うことができます。

新しいバージョンでパッケージをアップグレードする場合は、既存のバージョンをそのまま残しておくか、削除してから最新のバージョンを残しておくことができます。 以前のドキュメントとの互換性を維持するために古いバージョンをそのまま残しておくことをお勧めします。また、すべてのユーザーが使用できるようにする前に、新しいバージョンのテストを行うこともできます。

**パッケージを自動的にアップグレードするには**

1.  新しい SFT ファイルを Application Virtualization サーバーのコンテンツフォルダーにコピーします。

    **注** Resequencing で、Open Software Descriptor (OSD)、icon (ICO)、または Sequencer Project (SPRJ) ファイルを変更した機能が追加されなかった場合は、それらをコピーする必要はありません。 すべてのファイルに同じ日付を表示する場合は、これらのファイルを含めることができます。

     

2.  Application Virtualization Server 管理コンソールの左側のウィンドウで、[**パッケージ**] を展開します。

3.  アップグレードするパッケージを右クリックし、[**バージョンの追加**] を選択します。

4.  [**パッケージバージョンの追加**] ダイアログボックスで、新しいアプリケーションバージョンの完全パス名を [ファイル] フィールド**のフルパス**で参照するか、入力します。 これは、SFT ファイルである必要があります。

5.  **[次へ]** をクリックします。

6.  [**概要**] ダイアログボックスにファイルの場所が表示され、ファイルのコピーをまだ行っていない場合は、ファイルをコピーするように求められます。 情報を確認したら、[**完了**] をクリックします。

    これで、新しいバージョンが完成し、ストリーミングする準備が整いました。

## 関連トピック


[サーバー管理コンソールでパッケージを管理する方法](how-to-manage-packages-in-the-server-management-console.md)

 

 





