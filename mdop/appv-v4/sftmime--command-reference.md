---
title: SFTMIME コマンドリファレンス
description: SFTMIME コマンドリファレンス
author: dansimp
ms.assetid: a4a69228-9dd3-4623-b773-899d03c0cf10
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 47aac9110febaf3f349461d74fef840326b1c6e4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815347"
---
# SFTMIME コマンドリファレンス


SFTMIME は、多くのクライアント構成の詳細を管理できるアプリケーションの仮想化 (App-v) によって使用されるコマンドラインインターフェイスです。 このセクションには、すべてのコマンドとそのパラメーターが含まれており、それぞれについて簡単に説明しています。

**重要**  
-   バックスラッシュ文字は必ず前にバックスラッシュを使ってエスケープする必要があります。それ以外の場合は、パスが正しく解析されません。

-   呼び出しプログラムを使って、 **CreateProcess**を使って SFTMIME を呼び出す場合は、最初のパラメーターが sftmime.exe のパスであることを確認する必要があります。

-   SFTMIME **QUERY OBJ**コマンドの出力を、 **findstr**コマンドにパイプして文字列を検索することはできません。

-   **グローバル**スイッチを使用するには、ローカル管理者の権限が必要です。

-   短いパスと相対パスを使用すると、予期しない結果になる可能性があるため、回避する必要があります。 常に完全なパスを使用します。

 

## このセクションの内容


[ADD APP](add-app.md)

[ADD PACKAGE](add-package.md)

[ADD SERVER](add-server.md)

[ADD TYPE](add-type.md)

[CLEAR APP](clear-app.md)

[CLEAR OBJ](clear-obj.md)

[CONFIGURE APP](configure-app.md)

[CONFIGURE PACKAGE](configure-package.md)

[CONFIGURE SERVER](configure-server.md)

[CONFIGURE TYPE](configure-type.md)

[DELETE APP](delete-app.md)

[DELETE OBJ](delete-obj.md)

[DELETE PACKAGE](delete-package.md)

[DELETE SERVER](delete-server.md)

[DELETE TYPE](delete-type.md)

[HELP](help.md)

[LOAD APP](load-app.md)

[LOAD PACKAGE](load-package.md)

[LOCK APP](lock-app.md)

[PUBLISH APP](publish-app.md)

[PUBLISH PACKAGE](publish-package.md)

[QUERY OBJ](query-obj.md)

[REFRESH SERVER](refresh-server.md)

[REPAIR APP](repair-app.md)

[UNLOAD APP](unload-app.md)

[UNLOAD PACKAGE](unload-package.md)

[UNLOCK APP](unlock-app.md)

[UNPUBLISH PACKAGE](unpublish-package.md)

 

 





