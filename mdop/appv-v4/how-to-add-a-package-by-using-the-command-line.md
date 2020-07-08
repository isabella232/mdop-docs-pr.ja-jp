---
title: コマンド ラインを使用してパッケージを追加する方法
description: コマンド ラインを使用してパッケージを追加する方法
author: dansimp
ms.assetid: e75af49e-811a-407a-a7f0-6de8562b9188
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ab418017a075300f308d4ef4c6eceb4f623a05c7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821407"
---
# コマンド ラインを使用してパッケージを追加する方法


次の手順では、特定のコンピューター上の Application Virtualization (App-v) クライアントに仮想アプリケーションパッケージを追加するために必要な手順を示します。

**特定のユーザーの仮想アプリケーションパッケージを追加するには**

-   パッケージを取得するユーザーのユーザーアカウントの下で、次のコマンドを実行します。 このコマンドによって、そのユーザーのパッケージが追加され、公開されます。

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path>`

**仮想アプリケーションパッケージをすべてのユーザー用に追加するには**

-   管理者権限を持つアカウントで次のコマンドを実行します。 コンピューター上のすべてのユーザーに対してパッケージが追加され、公開されます。

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path> /GLOBAL`

**電子ソフトウェア配布システムを使用してパッケージを追加するには**

1.  コンピューターの**システム**アカウントの下でコマンドを実行する電子ソフトウェア配布システムを使用している場合、/グローバルスイッチを使用しない限り、パッケージはそのアカウントに対してのみ公開されます。 次のコマンドを実行して、コンピューター上のすべてのユーザーに対してパッケージを追加し、公開します。

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path> /GLOBAL`

2.  

    特定のユーザーに対してのみパッケージを追加する場合は、[**パッケージの追加**] を実行し、各ユーザーのユーザーアカウントの下で次の [パッケージの**発行**] コマンドを実行して、各ユーザーのパッケージを明示的に公開します。

    `SFTMIME ADD PACKAGE:”name” /MANIFEST <manifest-path>`

    `SFTMIME PUBLISH PACKAGE:”name” /MANIFEST <manifest-path>`

    グローバルパラメーターを指定せずにパッケージを発行すると、ユーザーはパッケージ内のアプリケーションにアクセスできるようになり、マニフェストに記載されているファイルの種類とショートカットがユーザーのプロファイルに発行されます。 必要なアクセス許可は、"ファイルの種類の関連付けを管理する" (**Managetypes**) と "ショートカットの公開" (**publishshortcut**) です。

## 関連トピック


[コマンド ラインを使用してすべての仮想アプリケーションを削除する方法](how-to-delete-all-virtual-applications-by-using-the-command-line.md)

[コマンド ラインを使用してパッケージを削除する方法](how-to-remove-a-package-by-using-the-command-line.md)

 

 





