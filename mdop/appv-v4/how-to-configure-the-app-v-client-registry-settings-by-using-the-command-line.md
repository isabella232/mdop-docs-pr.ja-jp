---
title: コマンド ラインを使用して App-V Client レジストリ設定を構成する方法
description: コマンド ラインを使用して App-V Client レジストリ設定を構成する方法
author: dansimp
ms.assetid: 3e3d873f-13d2-402f-97b4-f62d0c399171
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c424f39c8209ca641f6073838ebcb8726acc9e25
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817897"
---
# コマンド ラインを使用して App-V Client レジストリ設定を構成する方法


コマンドラインを使用してインストール中に Application Virtualization (App-v) クライアントを展開して構成した後、1つ以上のクライアント構成の設定を変更する必要がある場合があります。 これは、次のいずれかの方法を使用して、適切なレジストリキーを編集することで実現されます。

-   レジストリエディターを直接使用する

-   .Reg ファイルを使用する

-   VBScript または Windows PowerShell などのスクリプト言語を使用する

また、使用できる ADM テンプレートもあります。 ADM テンプレートの詳細については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=121835> 。

**注意** エラーによりコンピューターが不安定な状態になる可能性があるため、レジストリを編集するときは注意してください。 レジストリの編集に関連する標準のビジネスプラクティスに従ってください。 テスト環境で提案されたすべての変更を、運用コンピューターに展開する前に徹底的にテストします。

 

## このセクションの内容


**重要** 64ビットのコンピューターでは、次のセクションに記載されているキーと値は、HKEY \ _LOCAL \ _MACHINE ¥ pc \\ wow6432node¥の各デバイスにあります。

 

<a href="" id="how-to-reset-the-filesystem-cache"></a>[FileSystem キャッシュをリセットする方法](how-to-reset-the-filesystem-cache.md)  
ファイルシステムキャッシュをリセットするために必要な情報を提供します。

<a href="" id="how-to-change-the-size-of-the-filesystem-cache"></a>[FileSystem キャッシュのサイズを変更する方法](how-to-change-the-size-of-the-filesystem-cache.md)  
キャッシュのサイズを変更する方法について説明します。

<a href="" id="how-to-use-the-cache-space-management-feature"></a>[キャッシュ領域管理機能を使用する方法](how-to-use-the-cache-space-management-feature.md)  
キャッシュスペース管理機能を構成する方法について説明します。

<a href="" id="how-to-configure-the-client-log-file"></a>[クライアント ログ ファイルを構成する方法](how-to-configure-the-client-log-file.md)  
クライアントログファイルを制御するさまざまなレジストリキーの値と、それらを変更する方法について説明します。

<a href="" id="how-to-configure-user-permissions"></a>[ユーザーのアクセス許可を構成する方法](how-to-configure-user-permissions.md)  
ユーザーのアクセス許可を制御するレジストリキーを識別し、いくつかのアクセス許可を変更する方法の例を示します。

<a href="" id="how-to-configure-the-client-for-application-package-retrieval"></a>[アプリケーション パッケージを取得するためにクライアントを構成する方法](how-to-configure-the-client-for-application-package-retrieval.md)  
さまざまなソースからパッケージコンテンツ、アイコン、ファイルの種類の関連付けを取得するようにクライアントを構成する方法について説明し、正しいパス形式の例をいくつか示します。

<a href="" id="how-to-configure-the-client-for-disconnected-operation-mode"></a>[非接続操作モードのクライアントを構成する方法](how-to-configure-the-client-for-disconnected-operation-mode.md)  
切断された操作モードに関連するさまざまな設定を構成する方法について説明します。

<a href="" id="how-to-configure-shortcut-and-file-type-association-behavior"></a>[ショートカットとファイルの種類の関連付け動作を構成する方法](how-to-configure-shortcut-and-file-type-association-behavior-46-only.md)  
App-v クライアントでのショートカットとファイルの種類の関連付けを制御するレジストリキーの値について説明し、その構成方法について詳しく説明します。

## 関連トピック


[Application Virtualization Client](application-virtualization-client.md)

 

 





