---
title: パッケージを分岐する方法
description: パッケージを分岐する方法
author: dansimp
ms.assetid: bfe46a8a-f0ee-4a71-9e9c-64ac08aac9c1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2de36fae1a09aeae4d1b7b21ebe00f683e3b3693
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818127"
---
# パッケージを分岐する方法


次の手順を使用して、シーケンスされた既存のアプリケーションパッケージを並べて実行できるように、既存のシーケンスされたアプリケーションパッケージを変更します。 このプロセスは "分岐" と呼ばれます。 仮想アプリケーションパッケージを分岐すると、同じパッケージの2つのバージョンを実行できます。 たとえば、既存のパッケージにサービスパックを適用し、元の順序が付けられた仮想アプリケーションパッケージと並行して実行することができます。

順序付けされた仮想アプリケーションパッケージを分岐するには、次の手順を使用します。

**シーケンス仮想アプリケーションパッケージを分岐するには**

1.  Microsoft Application Virtualization (App-v) Sequencer を開きます。 分岐するパッケージ (sprj) を含むターゲットディレクトリを指定するには、[**ファイル**]、[**開く**] のように選びます。

2.  分岐する順序が付けられたアプリケーションが含まれているディレクトリに移動し、[**開く**] をクリックします。

3.  パッケージのコピーを保存するには、App-v の Sequencer で [**ファイル**]、[**名前を付けて保存**] の順番に選びます。 新しい一意の名前を指定し、パッケージのコピー用に新しい一意のパッケージルートディレクトリを指定します。 **[保存]** をクリックします。

    **重要**  
    新しいパッケージ名を指定する必要があります。パッケージの既存のバージョンは上書きされます。



~~~
The sequencer will automatically generate new GUID files for the new package. The version number associated with the package will also be automatically appended to the OSD file name.
~~~

4. 新しいバージョンを保存した後で、必要な構成の変更を適用し、関連付けられた ICO、OSD、SFT、SPRJ の各ファイルを Application Virtualization (App-v) サーバー上の適切な場所に保存できます。

## 関連トピック


[Application Virtualization Sequencer のタスク](tasks-for-the-application-virtualization-sequencer.md)









