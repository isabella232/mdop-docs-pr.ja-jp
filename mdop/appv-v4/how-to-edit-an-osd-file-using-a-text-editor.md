---
title: テキスト エディターを使用して OSD ファイルを編集する方法
description: テキスト エディターを使用して OSD ファイルを編集する方法
author: dansimp
ms.assetid: f4263a1b-824f-49b9-8060-b8229c9d9960
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c83547b38cee7e91e8348689583e0542a88dab83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817444"
---
# テキスト エディターを使用して OSD ファイルを編集する方法


テキストエディターを使用して、開いているソフトウェア記述子 (OSD) ファイルを編集するには、次の手順を使用します。

**テキストエディターを使用して OSD ファイルを編集するには**

1.  任意の XML または ASCII テキストエディター (Microsoft メモ帳など) を使用して OSD ファイルを開きます。

    **注** OSD ファイルを変更する前に、インストールディレクトリの XSD ファイルで規定されているスキーマを読みます。 このスキーマに従わないと、シーケンス処理されたアプリケーションが正常に起動できないというエラーが発生する可能性があります。

     

2.  選択した XML または ASCII テキストエディターを使用して、指定されたスキーマと次のガイドラインに従って OSD ファイルを編集します。

    1.  名前付き要素が、softpkg root 要素内で入れ子になっていることを確認し &lt; &gt; ます。

    2.  要素名がすべて大文字であることを確認します。

    3.  属性値は、大文字と小文字が区別されることに注意してください。

    4.  「慎重に入力する」と入力して、XML の仕様を確認します。

## 関連トピック


[[OSD] タブについて](about-the-osd-tab.md)

[OSD ファイルを編集する方法](how-to-edit-an-osd-file.md)

[OSD ファイルの要素](osd-file-elements.md)

 

 





