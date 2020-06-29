---
title: '[プロパティ] タブについて'
description: '[プロパティ] タブについて'
author: dansimp
ms.assetid: a6cf6f51-3778-4c8d-9632-3af4005775d2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4b2d6c3e01dde48fdd6701984f66610ea0333b74
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819924"
---
# [プロパティ] タブについて


[**プロパティ**] タブを使用して、シーケンスされたアプリケーションパッケージに関する基本的な統計情報を表示します。 この情報は、特に記載がない限り、自動的に生成されます。 このタブには、次の要素が含まれています。

## パッケージ情報


<a href="" id="package-name"></a>**パッケージ名**  
1つまたは複数のアプリケーションが含まれている可能性のあるシーケンス付きのアプリケーションパッケージで使用される単一の名前。たとえば、Microsoft Office を使用して、同じ仮想環境で実行される Microsoft Word と Microsoft Excel アプリケーションを含むシーケンス形式のアプリケーションパッケージにラベルを付けることができます。

<a href="" id="comments"></a>**コメント**  
Open Software Descriptor (OSD) file ABSTRACT 要素に表示されるソフトウェアパッケージの短い説明を表示します。 この項目は省略可能です。

<a href="" id="package-version"></a>**パッケージバージョン**  
順序付けされたアプリケーションパッケージのバージョン。

<a href="" id="package-guid"></a>**パッケージ GUID**  
シーケンス付きのアプリケーションパッケージに自動的に割り当てられたグローバル一意識別子 (GUID) は、シーケンス付きのアプリケーションパッケージがストリーミングされているコンピューターで実行されている可能性のある他のシーケンスされたアプリケーションパッケージと区別するために自動的に割り当てられます。

<a href="" id="package-version-guid"></a>**パッケージバージョン GUID**  
順序付けされたアプリケーションパッケージのバージョン GUID。

<a href="" id="root-directory"></a>**ルートディレクトリ**  
シーケンス処理を行っているアプリケーションパッケージのファイルがインストールされているディレクトリ。 このディレクトリは、シーケンスされたアプリケーションパッケージをストリーミングするコンピューター上にも作成されます。 下位互換性を確保することをお勧めします。これは、Q:\\MyApp.1\\. などの Q ドライブのルートにある8.3 形式のディレクトリ名にすることをお勧めします。

<a href="" id="created"></a>**Created**  
シーケンス付きのアプリケーションパッケージが作成された日付と時刻です。

<a href="" id="modified"></a>**変更**  
シーケンス付きのアプリケーションパッケージが最後に変更された日付と時刻です。

<a href="" id="package-size"></a>**パッケージサイズ**  
パッケージのサイズ (mb 単位) です。

<a href="" id="launch-size"></a>**起動サイズ**  
アプリケーションを起動するために必要な SFT ファイルの部分のサイズ (mb 単位) です。

## シーケンスパラメーター


<a href="" id="block-size"></a>**ブロックサイズ**  
ネットワーク経由でストリーミングするために、SFT ファイルが分割されるプライマリ機能ブロックとセカンダリ機能ブロックのサイズを指定します。 すべてのブロックは指定したサイズと等しくなります。ただし、最後のブロックが指定よりも小さくなっている可能性があります。 次のいずれかの値が表示されます。

-   4 KB

-   16 KB

-   32 KB

-   64 KB

**注** 最初のパッケージを作成した後は、ブロックサイズの値は変更できません。

 

## 関連トピック


[パッケージのプロパティを変更する方法](how-to-change-package-properties.md)

[Sequencer Console](sequencer-console.md)

 

 





