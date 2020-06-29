---
title: OSD ファイルの要素
description: OSD ファイルの要素
author: dansimp
ms.assetid: 8211b562-7549-4331-8321-144f52574e99
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a8e3ebcf53ff39ecd2ef7ad0feec0bbbcae199db
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816107"
---
# OSD ファイルの要素


Sequencer のインストールディレクトリには、オープンソフトウェア記述子 (OSD) ファイルの有効な構造を定義する XML スキーマファイル**Softricity**が含まれています。 よく使用される OSD 要素の一部を次に示します。

<a href="" id="softpkg"></a>ソフトパッケージ  
ソフトウェアパッケージを定義するすべての要素を含む OSD ファイルのルート要素です。

<a href="" id="codebase"></a>コード  
HREF、FILENAME、GUID の各属性を含む、このパッケージの sft ファイルに関する情報。 HREF 属性は、この特定のパッケージの配布ポイントを変更すると編集できます。

<a href="" id="os"></a>OS  
シーケンスウィザードで最初に設定された値に基づいて、このアプリケーションが実行できるオペレーティングシステムを定義します。 この値には、 **Softricity**で定義された値のみを含めることができます。

<a href="" id="local-interaction-allowed"></a>ローカル \ _INTERACTION \ _ALLOWED  
TRUE に設定すると、特定の仮想環境内ではなく、グローバル名前空間内で名前付きオブジェクト (イベント、ミューテックス、セマフォー、ファイルマッピング、mailslots) を作成できるようになり、仮想アプリケーションとホストオペレーティングシステムのアプリケーションとのやり取りが可能になります。

例: &lt; softpkg の &gt; &lt; 実装&gt;

&lt;VIRTUALENV &gt; &lt; ポリシー&gt;

&lt;ローカル \ _INTERACTION \ _ALLOWED &gt; TRUE

&lt;/LOCAL\ _INTERACTION \ _ALLOWED&gt;

&lt;/ポリシー &gt; &lt; /VIRTUALENV&gt;

&lt;/実装 &gt; &lt; /ソフトパッケージ&gt;

<a href="" id="dependencies"></a>物  
別のパッケージから CODEBASE タグを使用して、動的なスイートコンポジション (他のパッケージに依存) を定義します。

例: &lt; 依存 &gt; &lt; コードの HREF = "rtsps://サーバー/package" GUID = "7579 f4df-2461-4219-BD43-469E1FDC E3" sysgu/osguard "SIZE =" 6572748 "/" SIZE = "" 必須 = "FALSE"/ &gt; &lt; /依存関係&gt;

<a href="" id="package-name"></a>パッケージ名  
シーケンスウィザードの**パッケージ情報**ページに入力されたパッケージの共通名。複数のアプリケーションを含むシーケンス処理されたアプリケーションに使われる単一の名前を指定できます。

<a href="" id="title"></a>部署  
順序を指定するアプリケーションのわかりやすい名前です。

<a href="" id="abstract"></a>抽象  
シーケンスウィザードの**パッケージ情報**ページの [**コメント**] フィールドに入力されたソフトウェアパッケージの短い説明。 ベストプラクティスとしては、Sequencer ワークステーション、Sequencer バージョン、シーケンスエンジニアの名前などのオペレーティングシステムやサービスパックのレベルなどの情報を指定することをお勧めします。

<a href="" id="script"></a>化  
起動、シャットダウン、またはストリーミング中に発生する特定のスクリプトイベントを定義します。

<a href="" id="mgmt-shortcutlist"></a>管理 \ _SHORTCUTLIST  
ウィザードで定義されているすべてのショートカットの一覧です。

<a href="" id="mgmt-fileassociations"></a>管理 \ _FILEASSOCIATIONS  
ウィザードで指定したファイルの種類の一覧。

## 関連トピック


[[OSD] タブについて](about-the-osd-tab.md)

 

 





