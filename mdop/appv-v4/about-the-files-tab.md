---
title: '[ファイル] タブについて'
description: '[ファイル] タブについて'
author: dansimp
ms.assetid: 3c20e720-4b0f-465b-b7c4-3013dae1c815
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5e71cd0b60f9722da9736fc6987100f5c7bf53ab
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819927"
---
# [ファイル] タブについて


[**ファイル**] タブには、シーケンス処理されたアプリケーションパッケージに含まれているファイルの完全な一覧が表示されます。 左側のウィンドウに、標準のファイル参照形式で、アプリケーションのシーケンス中に作成されたパッケージ内のファイルの完全なリストが表示されます。 これらのファイルには、パッケージルートディレクトリ (アプリケーションのインストールフェーズで指定したディレクトリ)、仮想ファイルシステム (VFS) フォルダー、仮想環境ファイルが含まれます。 右側のウィンドウには、ファイル名、ファイル属性、および Sequencer 属性が表示されます。

## ファイル名と短い名前


<a href="" id="file-name"></a>**ファイル名**  
ファイルの名前は左側のウィンドウに表示されます。 左側のウィンドウに表示されるファイルは、シーケンス中に作成されます。

<a href="" id="short-name"></a>**短い形式の名前**  
これは、左側のウィンドウで選択されているファイルの名前で、8.3 形式の名前付け規則に記載されています。

## ファイルの属性


<a href="" id="file-size"></a>**ファイルサイズ**  
ファイルのサイズ (バイト単位) です。

<a href="" id="file-version"></a>**ファイルのバージョン**  
選択したファイルのバージョン。

<a href="" id="date-created"></a>**作成日**  
選択したファイルが作成された日付と時刻。

<a href="" id="date-modified"></a>**更新日**  
選択したファイルが最後に変更された日付と時刻です。

<a href="" id="file-id"></a>**File ID**  
ファイルの GUID。

## Sequencer 属性


<a href="" id="user-data"></a>**ユーザーデータ**  
この属性は、アプリケーションが個々のユーザーの情報を保持する必要があることを指定する場合に選択します。

<a href="" id="application-data"></a>**アプリケーションデータ**  
この属性は、アプリケーションがユーザーグループの一般的な情報を保持する必要があることを指定する場合に選択します。

<a href="" id="override"></a>**優先**  
選択すると、指定したアプリケーションパッケージがアップグレードされてクライアントにストリーミングされるときに、アプリケーションの仮想化デスクトップクライアントによって対応するファイルが上書きされます。 このチェックボックスがオフの場合、クライアントは、選択したファイルを上書きするかどうかを決定します。

## 関連トピック


[パッケージに含まれているファイルを変更する方法](how-to-modify-the-files-included-in-a-package.md)

[Sequencer Console](sequencer-console.md)

 

 





